# SplitUserDomain(ushort const *,STRU *,STRU *,ushort const *,int *)

- ea: `0x18002c888`
- end: `0x18002c950`
- name: `?SplitUserDomain@@YAJPEBGPEAVSTRU@@10PEAH@Z`
- size: `200`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU *, struct STRU *, const unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015554`
- `0x18001b3ac`
- `0x180039e28`
- `0x180046780`

## callees

- `0x18002c888`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18002c8b8`
- `msvcrt!wcspbrk` at `0x18002c8b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c8cc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c900`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c92f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c8cc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c900`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002c92f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002c90b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002c90b`

## pseudocode

```c
int __fastcall SplitUserDomain(
        const unsigned __int16 *a1,
        struct STRU *a2,
        struct STRU *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  int result; // eax
  const unsigned __int16 *v12; // rbx
  __int64 v13; // r8
  int v14; // eax
  int v15; // ecx

  if ( !a2 || !a3 )
    return -2147024809;
  v9 = wcspbrk(a1, L"/\\");
  v10 = v9;
  if ( !v9 )
  {
    result = STRU::Copy(a3, a4);
    if ( result < 0 )
      return result;
    v12 = a1;
    if ( a5 )
      *a5 = 1;
    goto LABEL_13;
  }
  v13 = v9 - a1;
  if ( (_DWORD)v13 )
    result = STRU::Copy(a3, a1, v13);
  else
    result = STRU::Copy(a3, L".");
  if ( result >= 0 )
  {
    v12 = v10 + 1;
    if ( a5 )
      *a5 = 0;
LABEL_13:
    v14 = STRU::Copy(a2, v12);
    v15 = 0;
    if ( v14 < 0 )
      return v14;
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x18002c888  push    rbx
0x18002c88a  push    rbp
0x18002c88b  push    rsi
0x18002c88c  push    rdi
0x18002c88d  push    r14
0x18002c88f  sub     rsp, 20h
0x18002c893  mov     rbp, r9
0x18002c896  mov     rsi, r8
0x18002c899  mov     r14, rdx
0x18002c89c  mov     rdi, rcx
0x18002c89f  test    rdx, rdx
0x18002c8a2  jz      loc_18002C940
0x18002c8a8  test    r8, r8
0x18002c8ab  jz      loc_18002C940
0x18002c8b1  lea     rdx, Control; "/\\"
0x18002c8b8  call    cs:__imp_wcspbrk
0x18002c8be  mov     rbx, rax
0x18002c8c1  mov     rcx, rsi
0x18002c8c4  test    rax, rax
0x18002c8c7  jnz     short loc_18002C8EB
0x18002c8c9  mov     rdx, rbp
0x18002c8cc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002c8d2  test    eax, eax
0x18002c8d4  js      short loc_18002C945
0x18002c8d6  mov     rax, [rsp+48h+arg_20]
0x18002c8db  mov     rbx, rdi
0x18002c8de  test    rax, rax
0x18002c8e1  jz      short loc_18002C929
0x18002c8e3  mov     dword ptr [rax], 1
0x18002c8e9  jmp     short loc_18002C929
0x18002c8eb  mov     r8, rbx
0x18002c8ee  sub     r8, rdi
0x18002c8f1  sar     r8, 1
0x18002c8f4  test    r8d, r8d
0x18002c8f7  jnz     short loc_18002C908
0x18002c8f9  lea     rdx, asc_18004E6A0; "."
0x18002c900  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002c906  jmp     short loc_18002C911
0x18002c908  mov     rdx, rdi
0x18002c90b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002c911  test    eax, eax
0x18002c913  js      short loc_18002C945
0x18002c915  mov     rax, [rsp+48h+arg_20]
0x18002c91a  add     rbx, 2
0x18002c91e  test    rax, rax
0x18002c921  jz      short loc_18002C929
0x18002c923  mov     dword ptr [rax], 0
0x18002c929  mov     rdx, rbx
0x18002c92c  mov     rcx, r14
0x18002c92f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002c935  xor     ecx, ecx
0x18002c937  test    eax, eax
0x18002c939  cmovs   ecx, eax
0x18002c93c  mov     eax, ecx
0x18002c93e  jmp     short loc_18002C945
0x18002c940  mov     eax, 80070057h
0x18002c945  add     rsp, 20h
0x18002c949  pop     r14
0x18002c94b  pop     rdi
0x18002c94c  pop     rsi
0x18002c94d  pop     rbp
0x18002c94e  pop     rbx
0x18002c94f  retn
```
