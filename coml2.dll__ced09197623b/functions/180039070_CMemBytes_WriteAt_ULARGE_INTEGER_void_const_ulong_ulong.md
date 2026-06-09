# CMemBytes::WriteAt(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x180039070`
- end: `0x18003914f`
- name: `?WriteAt@CMemBytes@@UEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `223`
- prototype: `int(CMemBytes *__hidden this, union _ULARGE_INTEGER, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180039070`
- `0x18003f54c`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800390ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800390ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180039132`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180039132`

## string_xrefs

- `0x1800390fd`: `onecoreuap\com\coml2\util\memlockbytes.cpp`

## pseudocode

```c
__int64 __fastcall CMemBytes::WriteAt(
        CMemBytes *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
        unsigned int a4,
        unsigned int *a5)
{
  size_t v6; // rbp
  DWORD LowPart; // ebx
  DWORD v9; // ecx
  unsigned int v11; // r14d
  char *v12; // rax
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = a4;
  LowPart = a2.LowPart;
  if ( a5 )
    *a5 = 0;
  v9 = a2.LowPart + a4;
  if ( a2.LowPart + a4 < a2.LowPart )
    return 2147942487LL;
  v11 = 0;
  if ( v9 <= **((_DWORD **)this + 3)
    || (v11 = (*(__int64 (__fastcall **)(CMemBytes *, _QWORD))(*(_QWORD *)this + 48LL))(this, v9)) == 0 )
  {
    v12 = (char *)GlobalLock(*(HGLOBAL *)(*((_QWORD *)this + 3) + 16LL));
    if ( !v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\com\\coml2\\util\\memlockbytes.cpp",
        (const char *)0x8003001DLL,
        v13);
      return 2147680285LL;
    }
    memcpy_0(&v12[LowPart], a3, v6);
    GlobalUnlock(*(HGLOBAL *)(*((_QWORD *)this + 3) + 16LL));
    if ( a5 )
      *a5 = v6;
  }
  return v11;
}

```

## disassembly

```asm
0x180039070  push    rbx
0x180039072  push    rbp
0x180039073  push    rsi
0x180039074  push    rdi
0x180039075  push    r14
0x180039077  push    r15
0x180039079  sub     rsp, 28h
0x18003907d  mov     rdi, [rsp+58h+arg_20]
0x180039085  mov     r15, r8
0x180039088  mov     ebp, r9d
0x18003908b  mov     rbx, rdx
0x18003908e  mov     rsi, rcx
0x180039091  test    rdi, rdi
0x180039094  jz      short loc_18003909C
0x180039096  mov     dword ptr [rdi], 0
0x18003909c  lea     ecx, [rdx+rbp]
0x18003909f  cmp     ecx, ebx
0x1800390a1  jnb     short loc_1800390AD
0x1800390a3  mov     eax, 80070057h
0x1800390a8  jmp     loc_180039142
0x1800390ad  mov     rax, [rsi+18h]
0x1800390b1  xor     r14d, r14d
0x1800390b4  cmp     ecx, [rax]
0x1800390b6  jbe     short loc_1800390E5
0x1800390b8  mov     rax, [rsi]
0x1800390bb  mov     dword ptr [rsp+58h+arg_20], ecx
0x1800390c2  mov     rcx, rsi
0x1800390c5  mov     dword ptr [rsp+58h+arg_20+4], r14d
0x1800390cd  mov     rdx, [rsp+58h+arg_20]
0x1800390d5  mov     rax, [rax+30h]
0x1800390d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390de  mov     r14d, eax
0x1800390e1  test    eax, eax
0x1800390e3  jnz     short loc_18003913F
0x1800390e5  mov     rcx, [rsi+18h]
0x1800390e9  mov     rcx, [rcx+10h]; hMem
0x1800390ed  call    cs:__imp_GlobalLock
0x1800390f3  test    rax, rax
0x1800390f6  jnz     short loc_18003911A
0x1800390f8  mov     rcx, [rsp+58h]; this
0x1800390fd  lea     r8, aOnecoreuapComC_1; "onecoreuap\\com\\coml2\\util\\memlockby"...
0x180039104  mov     ebx, 8003001Dh
0x180039109  mov     edx, 185h; void *
0x18003910e  mov     r9d, ebx; char *
0x180039111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039116  mov     eax, ebx
0x180039118  jmp     short loc_180039142
0x18003911a  mov     ecx, ebx
0x18003911c  mov     r8, rbp; Size
0x18003911f  add     rcx, rax; void *
0x180039122  mov     rdx, r15; Src
0x180039125  call    memcpy_0
0x18003912a  mov     rcx, [rsi+18h]
0x18003912e  mov     rcx, [rcx+10h]; hMem
0x180039132  call    cs:__imp_GlobalUnlock
0x180039138  test    rdi, rdi
0x18003913b  jz      short loc_18003913F
0x18003913d  mov     [rdi], ebp
0x18003913f  mov     eax, r14d
0x180039142  add     rsp, 28h
0x180039146  pop     r15
0x180039148  pop     r14
0x18003914a  pop     rdi
0x18003914b  pop     rsi
0x18003914c  pop     rbp
0x18003914d  pop     rbx
0x18003914e  retn
```
