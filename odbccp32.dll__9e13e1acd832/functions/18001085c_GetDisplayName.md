# GetDisplayName

- ea: `0x18001085c`
- end: `0x180010972`
- name: `GetDisplayName`
- size: `278`
- prototype: `__int64 __fastcall(__int64, wchar_t *, unsigned int, _DWORD *, int *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180010140`
- `0x180010668`
- `0x180010978`
- `0x1800110e8`

## callees

- `0x180002e14`
- `0x18001085c`
- `0x180010cdc`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall GetDisplayName(__int64 a1, wchar_t *a2, unsigned int a3, _DWORD *a4, int *a5)
{
  size_t v6; // rbx
  int v9; // ecx
  int v10; // eax
  int v11; // ebp
  __int64 result; // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-308h] BYREF
  int v14; // [rsp+38h] [rbp-300h]
  int v15; // [rsp+3Ch] [rbp-2FCh]
  wchar_t pszSrc[344]; // [rsp+40h] [rbp-2F8h] BYREF

  v6 = a3;
  memset_0(v13, 0, 0x2B8u);
  v9 = 8;
  if ( a2 && (_DWORD)v6 )
    v9 = 520;
  v15 = -1;
  v10 = v9 | 0x4001;
  if ( !a4 )
    v10 = v9;
  v11 = v10 | 0x800;
  if ( !a5 )
    v11 = v10;
  result = g_pfnSHGetFileInfoW;
  if ( g_pfnSHGetFileInfoW || (result = GetShell32Procs("SHGetFileInfoW"), (g_pfnSHGetFileInfoW = result) != 0) )
  {
    ((void (__fastcall *)(__int64, _QWORD, _BYTE *, __int64, int))result)(a1, 0, v13, 696, v11);
    if ( a2 && (_DWORD)v6 )
      StringCchCopyW(a2, v6, pszSrc);
    if ( a4 )
      *a4 = v14;
    if ( a5 )
      *a5 = v15;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001085c  push    rbx
0x18001085e  push    rbp
0x18001085f  push    rsi
0x180010860  push    rdi
0x180010861  push    r14
0x180010863  push    r15
0x180010865  sub     rsp, 308h
0x18001086c  mov     rax, cs:__security_cookie
0x180010873  xor     rax, rsp
0x180010876  mov     [rsp+338h+var_48], rax
0x18001087e  mov     rdi, [rsp+338h+arg_20]
0x180010886  mov     r14, rdx
0x180010889  mov     ebx, r8d
0x18001088c  mov     r15, rcx
0x18001088f  xor     edx, edx; Val
0x180010891  lea     rcx, [rsp+338h+var_308]; void *
0x180010896  mov     r8d, 2B8h; Size
0x18001089c  mov     rsi, r9
0x18001089f  call    memset_0
0x1800108a4  mov     ecx, 8
0x1800108a9  test    r14, r14
0x1800108ac  jz      short loc_1800108B8
0x1800108ae  test    ebx, ebx
0x1800108b0  mov     eax, 208h
0x1800108b5  cmovnz  ecx, eax
0x1800108b8  mov     eax, ecx
0x1800108ba  mov     [rsp+338h+var_2FC], 0FFFFFFFFh
0x1800108c2  or      eax, 4001h
0x1800108c7  test    rsi, rsi
0x1800108ca  cmovz   eax, ecx
0x1800108cd  mov     ebp, eax
0x1800108cf  bts     ebp, 0Bh
0x1800108d3  test    rdi, rdi
0x1800108d6  cmovz   ebp, eax
0x1800108d9  mov     rax, cs:g_pfnSHGetFileInfoW
0x1800108e0  test    rax, rax
0x1800108e3  jnz     short loc_180010904
0x1800108e5  lea     rdx, aShgetfileinfow_0; "SHGetFileInfoW"
0x1800108ec  lea     rcx, aShgetfileinfow; "SHGetFileInfoW"
0x1800108f3  call    GetShell32Procs
0x1800108f8  mov     cs:g_pfnSHGetFileInfoW, rax
0x1800108ff  test    rax, rax
0x180010902  jz      short loc_180010952
0x180010904  mov     r9d, 2B8h
0x18001090a  mov     [rsp+338h+var_318], ebp
0x18001090e  lea     r8, [rsp+338h+var_308]
0x180010913  xor     edx, edx
0x180010915  mov     rcx, r15
0x180010918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001091d  test    r14, r14
0x180010920  jz      short loc_180010937
0x180010922  cmp     ebx, 1
0x180010925  jb      short loc_180010937
0x180010927  mov     rdx, rbx; cchDest
0x18001092a  lea     r8, [rsp+338h+pszSrc]; pszSrc
0x18001092f  mov     rcx, r14; pszDest
0x180010932  call    StringCchCopyW
0x180010937  test    rsi, rsi
0x18001093a  jz      short loc_180010942
0x18001093c  mov     ecx, [rsp+338h+var_300]
0x180010940  mov     [rsi], ecx
0x180010942  test    rdi, rdi
0x180010945  jz      short loc_18001094D
0x180010947  mov     ecx, [rsp+338h+var_2FC]
0x18001094b  mov     [rdi], ecx
0x18001094d  mov     eax, 1
0x180010952  mov     rcx, [rsp+338h+var_48]
0x18001095a  xor     rcx, rsp; StackCookie
0x18001095d  call    __security_check_cookie
0x180010962  add     rsp, 308h
0x180010969  pop     r15
0x18001096b  pop     r14
0x18001096d  pop     rdi
0x18001096e  pop     rsi
0x18001096f  pop     rbp
0x180010970  pop     rbx
0x180010971  retn
```
