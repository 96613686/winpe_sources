# CThreadLocalValue::~CThreadLocalValue(void)

- ea: `0x180007c10`
- end: `0x180007c77`
- name: `??1CThreadLocalValue@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CThreadLocalValue *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c340`

## callees

- `0x180007c10`
- `0x18000b980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180007c20`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180007c20`

## pseudocode

```c
void __fastcall CThreadLocalValue::~CThreadLocalValue(DWORD *this)
{
  signed int LastError; // eax

  if ( *this != -1 && !TlsFree(*this) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      WPP_SF_dd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids,
        *this,
        LastError);
  }
}

```

## disassembly

```asm
0x180007c10  push    rbx
0x180007c12  sub     rsp, 30h
0x180007c16  cmp     dword ptr [rcx], 0FFFFFFFFh
0x180007c19  mov     rbx, rcx
0x180007c1c  jz      short loc_180007C71
0x180007c1e  mov     ecx, [rcx]; dwTlsIndex
0x180007c20  call    cs:__imp_TlsFree
0x180007c26  test    eax, eax
0x180007c28  jnz     short loc_180007C71
0x180007c2a  call    cs:__imp_GetLastError
0x180007c30  test    eax, eax
0x180007c32  jle     short loc_180007C3C
0x180007c34  movzx   eax, ax
0x180007c37  or      eax, 80070000h
0x180007c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c43  lea     rdx, WPP_GLOBAL_Control
0x180007c4a  cmp     rcx, rdx
0x180007c4d  jz      short loc_180007C71
0x180007c4f  cmp     byte ptr [rcx+19h], 3
0x180007c53  jb      short loc_180007C71
0x180007c55  mov     r9d, [rbx]
0x180007c58  lea     r8, WPP_6832bfcad6a83d600ea9b71b84ed660d_Traceguids
0x180007c5f  mov     rcx, [rcx+10h]
0x180007c63  mov     edx, 0Bh
0x180007c68  mov     [rsp+38h+var_18], eax
0x180007c6c  call    WPP_SF_dd
0x180007c71  add     rsp, 30h
0x180007c75  pop     rbx
0x180007c76  retn
```
