# STRA::Copy(char const *)

- ea: `0x18000ddb0`
- end: `0x18000de7e`
- name: `?Copy@STRA@@QEAAJPEBD@Z`
- size: `206`
- prototype: `__int64 __fastcall(STRA *__hidden this, const char *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001a60`
- `0x18001dea0`

## callees

- `0x18000ddb0`
- `0x18000de90`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de4a`

## pseudocode

```c
signed int __fastcall STRA::Copy(void **this, const char *Src)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  _BYTE *v6; // rax
  signed int result; // eax
  unsigned int v8; // edx

  if ( !Src )
    return -2147024809;
  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  v5 = *((unsigned int *)this + 10);
  if ( v5 >= (unsigned __int64)(unsigned int)v4 + 1 )
    goto LABEL_5;
  v8 = v4 + 128;
  if ( (unsigned __int64)(unsigned int)v4 + 128 > 0xFFFFFFFF )
  {
    SetLastError(0x216u);
    return 0;
  }
  if ( v8 <= (unsigned int)v5 || BUFFER::ReallocStorage((BUFFER *)this, v8) )
  {
LABEL_5:
    memcpy_0(this[4], Src, (unsigned int)v4);
    v6 = this[4];
    *((_DWORD *)this + 12) = v4;
    v6[(unsigned int)v4] = 0;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000ddb0  mov     [rsp+arg_10], rbp
0x18000ddb5  push    rdi
0x18000ddb6  sub     rsp, 20h
0x18000ddba  mov     rdi, rdx
0x18000ddbd  mov     rbp, rcx
0x18000ddc0  test    rdx, rdx
0x18000ddc3  jz      loc_18000DE77
0x18000ddc9  mov     [rsp+28h+arg_0], rbx
0x18000ddce  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000ddd5  mov     [rsp+28h+arg_8], rsi
0x18000ddda  nop     word ptr [rax+rax+00h]
0x18000dde0  inc     rbx
0x18000dde3  cmp     byte ptr [rdx+rbx], 0
0x18000dde7  jnz     short loc_18000DDE0
0x18000dde9  mov     ecx, [rcx+28h]
0x18000ddec  mov     esi, ebx
0x18000ddee  lea     rax, [rsi+1]
0x18000ddf2  cmp     rcx, rax
0x18000ddf5  jb      short loc_18000DE29
0x18000ddf7  mov     rcx, [rbp+20h]; void *
0x18000ddfb  mov     r8, rsi; Size
0x18000ddfe  mov     rdx, rdi; Src
0x18000de01  call    memcpy_0
0x18000de06  mov     rax, [rbp+20h]
0x18000de0a  mov     [rbp+30h], ebx
0x18000de0d  mov     byte ptr [rsi+rax], 0
0x18000de11  xor     eax, eax
0x18000de13  mov     rsi, [rsp+28h+arg_8]
0x18000de18  mov     rbx, [rsp+28h+arg_0]
0x18000de1d  mov     rbp, [rsp+28h+arg_10]
0x18000de22  add     rsp, 20h
0x18000de26  pop     rdi
0x18000de27  retn
0x18000de29  lea     rdx, [rsi+80h]; unsigned int
0x18000de30  mov     eax, 0FFFFFFFFh
0x18000de35  cmp     rdx, rax
0x18000de38  ja      short loc_18000DE64
0x18000de3a  cmp     edx, ecx
0x18000de3c  jbe     short loc_18000DDF7
0x18000de3e  mov     rcx, rbp; this
0x18000de41  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x18000de46  test    al, al
0x18000de48  jnz     short loc_18000DDF7
0x18000de4a  call    cs:__imp_GetLastError
0x18000de51  nop     dword ptr [rax+rax+00h]
0x18000de56  test    eax, eax
0x18000de58  jle     short loc_18000DE13
0x18000de5a  movzx   eax, ax
0x18000de5d  or      eax, 80070000h
0x18000de62  jmp     short loc_18000DE13
0x18000de64  mov     ecx, 216h; dwErrCode
0x18000de69  call    cs:__imp_SetLastError
0x18000de70  nop     dword ptr [rax+rax+00h]
0x18000de75  jmp     short loc_18000DE11
0x18000de77  mov     eax, 80070057h
0x18000de7c  jmp     short loc_18000DE1D
```
