# SdbpGetPathAppPatch

- ea: `0x1408266c0`
- end: `0x1408267a4`
- name: `SdbpGetPathAppPatch`
- size: `228`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1406cde60`
- `0x1406cdfe0`
- `0x1408268f0`
- `0x1408269d0`

## callees

- `0x1406dc8c0`
- `0x1408266c0`
- `0x140829038`
- `0x140829334`
- `0x1408c2f88`

## string_xrefs

- `0x140826771`: `SdbpGetPathAppPatch`
- `0x140826764`: `AslPathToSystemPathBuf failed [%x]`
- `0x14082673f`: `AslPathCombine failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatch(NTSTRSAFE_PWSTR pszDest, size_t cchDest, const wchar_t *a3)
{
  const wchar_t *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  __int128 v11; // [rsp+30h] [rbp-258h] BYREF
  int v12; // [rsp+40h] [rbp-248h]
  wchar_t pszSrc[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = a3;
  v12 = *(_DWORD *)L"h";
  v11 = *(_OWORD *)L"\\AppPatch";
  if ( cchDest < 0xA )
    return 3221225507LL;
  *pszDest = 0;
  pszSrc[0] = 0;
  if ( !a3 )
    v3 = &cchOriginalDestLength;
  v7 = AslPathCombine(&v11, v3, pszSrc, 260);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathCombine failed [%x]";
    v10 = 953;
LABEL_9:
    AslLogCallPrintf(1, (unsigned int)"SdbpGetPathAppPatch", v10, (_DWORD)v9, v7);
    return v8;
  }
  v7 = AslPathToSystemPathBuf(pszDest, cchDest, pszSrc);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = "AslPathToSystemPathBuf failed [%x]";
    v10 = 959;
    goto LABEL_9;
  }
  return v8;
}

```

## disassembly

```asm
0x1408266c0  push    rbx
0x1408266c2  push    rsi
0x1408266c3  push    rdi
0x1408266c4  sub     rsp, 270h
0x1408266cb  mov     rax, cs:__security_cookie
0x1408266d2  xor     rax, rsp
0x1408266d5  mov     [rsp+288h+var_28], rax
0x1408266dd  mov     eax, dword ptr cs:aApppatch_0+10h; "h"
0x1408266e3  mov     r10, r8
0x1408266e6  mov     [rsp+288h+var_248], eax
0x1408266ea  mov     rsi, rdx
0x1408266ed  mov     rdi, rcx
0x1408266f0  movups  xmm0, xmmword ptr cs:aApppatch_0; "\\AppPatch"
0x1408266f7  movups  [rsp+288h+var_258], xmm0
0x1408266fc  cmp     rdx, 0Ah
0x140826700  jnb     short loc_140826709
0x140826702  mov     eax, 0C0000023h
0x140826707  jmp     short loc_140826788
0x140826709  xor     eax, eax
0x14082670b  lea     r8, [rsp+288h+pszSrc]
0x140826710  mov     [rcx], ax
0x140826713  test    r10, r10
0x140826716  mov     [rsp+288h+pszSrc], ax
0x14082671b  lea     rcx, [rsp+288h+var_258]
0x140826720  lea     rax, cchOriginalDestLength
0x140826727  mov     r9d, 104h
0x14082672d  cmovz   r10, rax
0x140826731  mov     rdx, r10
0x140826734  call    AslPathCombine
0x140826739  mov     ebx, eax
0x14082673b  test    eax, eax
0x14082673d  jns     short loc_14082674E
0x14082673f  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140826746  mov     r8d, 3B9h
0x14082674c  jmp     short loc_140826771
0x14082674e  lea     r8, [rsp+288h+pszSrc]; pszSrc
0x140826753  mov     rdx, rsi; cchDest
0x140826756  mov     rcx, rdi; pszDest
0x140826759  call    AslPathToSystemPathBuf
0x14082675e  mov     ebx, eax
0x140826760  test    eax, eax
0x140826762  jns     short loc_140826786
0x140826764  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x14082676b  mov     r8d, 3BFh
0x140826771  lea     rdx, aSdbpgetpathapp_0; "SdbpGetPathAppPatch"
0x140826778  mov     [rsp+288h+var_268], eax
0x14082677c  mov     ecx, 1
0x140826781  call    AslLogCallPrintf
0x140826786  mov     eax, ebx
0x140826788  mov     rcx, [rsp+288h+var_28]
0x140826790  xor     rcx, rsp; StackCookie
0x140826793  call    __security_check_cookie
0x140826798  add     rsp, 270h
0x14082679f  pop     rdi
0x1408267a0  pop     rsi
0x1408267a1  pop     rbx
0x1408267a2  retn
```
