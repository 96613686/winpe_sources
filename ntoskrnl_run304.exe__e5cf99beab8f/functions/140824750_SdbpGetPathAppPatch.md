# SdbpGetPathAppPatch

- ea: `0x140824750`
- end: `0x140824834`
- name: `SdbpGetPathAppPatch`
- size: `228`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1406cb200`
- `0x1406cb380`
- `0x140824980`
- `0x140824a60`

## callees

- `0x1406d9d70`
- `0x140824750`
- `0x1408270c8`
- `0x1408273c4`
- `0x14097d158`

## string_xrefs

- `0x1408247f4`: `AslPathToSystemPathBuf failed [%x]`
- `0x140824801`: `SdbpGetPathAppPatch`
- `0x1408247cf`: `AslPathCombine failed [%x]`

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
0x140824750  push    rbx
0x140824752  push    rsi
0x140824753  push    rdi
0x140824754  sub     rsp, 270h
0x14082475b  mov     rax, cs:__security_cookie
0x140824762  xor     rax, rsp
0x140824765  mov     [rsp+288h+var_28], rax
0x14082476d  mov     eax, dword ptr cs:aApppatch_0+10h; "h"
0x140824773  mov     r10, r8
0x140824776  mov     [rsp+288h+var_248], eax
0x14082477a  mov     rsi, rdx
0x14082477d  mov     rdi, rcx
0x140824780  movups  xmm0, xmmword ptr cs:aApppatch_0; "\\AppPatch"
0x140824787  movups  [rsp+288h+var_258], xmm0
0x14082478c  cmp     rdx, 0Ah
0x140824790  jnb     short loc_140824799
0x140824792  mov     eax, 0C0000023h
0x140824797  jmp     short loc_140824818
0x140824799  xor     eax, eax
0x14082479b  lea     r8, [rsp+288h+pszSrc]
0x1408247a0  mov     [rcx], ax
0x1408247a3  test    r10, r10
0x1408247a6  mov     [rsp+288h+pszSrc], ax
0x1408247ab  lea     rcx, [rsp+288h+var_258]
0x1408247b0  lea     rax, cchOriginalDestLength
0x1408247b7  mov     r9d, 104h
0x1408247bd  cmovz   r10, rax
0x1408247c1  mov     rdx, r10
0x1408247c4  call    AslPathCombine
0x1408247c9  mov     ebx, eax
0x1408247cb  test    eax, eax
0x1408247cd  jns     short loc_1408247DE
0x1408247cf  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x1408247d6  mov     r8d, 3B9h
0x1408247dc  jmp     short loc_140824801
0x1408247de  lea     r8, [rsp+288h+pszSrc]; pszSrc
0x1408247e3  mov     rdx, rsi; cchDest
0x1408247e6  mov     rcx, rdi; pszDest
0x1408247e9  call    AslPathToSystemPathBuf
0x1408247ee  mov     ebx, eax
0x1408247f0  test    eax, eax
0x1408247f2  jns     short loc_140824816
0x1408247f4  lea     r9, aAslpathtosyste; "AslPathToSystemPathBuf failed [%x]"
0x1408247fb  mov     r8d, 3BFh
0x140824801  lea     rdx, aSdbpgetpathapp_0; "SdbpGetPathAppPatch"
0x140824808  mov     [rsp+288h+var_268], eax
0x14082480c  mov     ecx, 1
0x140824811  call    AslLogCallPrintf
0x140824816  mov     eax, ebx
0x140824818  mov     rcx, [rsp+288h+var_28]
0x140824820  xor     rcx, rsp; StackCookie
0x140824823  call    __security_check_cookie
0x140824828  add     rsp, 270h
0x14082482f  pop     rdi
0x140824830  pop     rsi
0x140824831  pop     rbx
0x140824832  retn
```
