# GetRemotePathFromILinkInfo(_ilinkinfoW const *,ushort *,int)

- ea: `0x180005110`
- end: `0x180005237`
- name: `?GetRemotePathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z`
- size: `295`
- prototype: `void __fastcall(const CHAR *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005240`

## callees

- `0x180001bd0`
- `0x180004840`
- `0x180005110`
- `0x180005721`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180005207`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180005207`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005185`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005185`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800051ba`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800051ba`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800051d6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800051ed`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800051d6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800051ed`

## pseudocode

```c
void __fastcall GetRemotePathFromILinkInfo(const CHAR *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rbx
  PWSTR v5; // rax
  PWSTR v6; // rax
  PCWSTR ppszServer; // [rsp+30h] [rbp-248h] BYREF
  WCHAR WideCharStr[264]; // [rsp+40h] [rbp-238h] BYREF

  memset_0(WideCharStr, 0, 0x208u);
  GetRemotePathFromCNRLink((const struct _cnrlink *)&a1[*((unsigned int *)a1 + 5)], a2);
  if ( *((_DWORD *)a1 + 1) == 28 )
  {
    v4 = WideCharStr;
    MultiByteToWideChar(0, 0, &a1[*((unsigned int *)a1 + 6)], -1, WideCharStr, 260);
  }
  else
  {
    v4 = (unsigned __int16 *)&a1[*((unsigned int *)a1 + 8)];
    if ( !v4 )
      goto LABEL_6;
  }
  if ( *v4 )
  {
    CatPath(a2, v4);
    return;
  }
LABEL_6:
  ppszServer = 0;
  if ( !PathIsUNCEx(a2, &ppszServer)
    || (v5 = StrChrW(ppszServer, 0x5Cu)) == 0
    || (v6 = StrChrW(v5 + 1, 0x5Cu)) == 0
    || v6[1] )
  {
    PathRemoveBackslashW(a2);
  }
}

```

## disassembly

```asm
0x180005110  mov     [rsp+arg_10], rbx
0x180005115  push    rbp
0x180005116  push    rsi
0x180005117  push    rdi
0x180005118  sub     rsp, 260h
0x18000511f  mov     rax, cs:__security_cookie
0x180005126  xor     rax, rsp
0x180005129  mov     [rsp+278h+var_28], rax
0x180005131  mov     rsi, rdx
0x180005134  mov     rdi, rcx
0x180005137  xor     edx, edx; Val
0x180005139  lea     rcx, [rsp+278h+WideCharStr]; void *
0x18000513e  mov     r8d, 208h; Size
0x180005144  call    memset_0
0x180005149  mov     ecx, [rdi+14h]
0x18000514c  mov     rdx, rsi; unsigned __int16 *
0x18000514f  add     rcx, rdi; struct _cnrlink *
0x180005152  call    ?GetRemotePathFromCNRLink@@YAXPEBU_cnrlink@@PEAGH@Z; GetRemotePathFromCNRLink(_cnrlink const *,ushort *,int)
0x180005157  xor     ebp, ebp
0x180005159  cmp     dword ptr [rdi+4], 1Ch
0x18000515d  jnz     short loc_180005193
0x18000515f  mov     r8d, [rdi+18h]
0x180005163  lea     rax, [rsp+278h+WideCharStr]
0x180005168  add     r8, rdi; lpMultiByteStr
0x18000516b  mov     [rsp+278h+cchWideChar], 104h; cchWideChar
0x180005173  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180005177  mov     [rsp+278h+lpWideCharStr], rax; lpWideCharStr
0x18000517c  xor     edx, edx; dwFlags
0x18000517e  lea     rbx, [rsp+278h+WideCharStr]
0x180005183  xor     ecx, ecx; CodePage
0x180005185  call    cs:__imp_MultiByteToWideChar
0x18000518c  nop     dword ptr [rax+rax+00h]
0x180005191  jmp     short loc_18000519B
0x180005193  mov     ebx, [rdi+20h]
0x180005196  add     rbx, rdi
0x180005199  jz      short loc_1800051AD
0x18000519b  cmp     [rbx], bp
0x18000519e  jz      short loc_1800051AD
0x1800051a0  mov     rdx, rbx; unsigned __int16 *
0x1800051a3  mov     rcx, rsi; unsigned __int16 *
0x1800051a6  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x1800051ab  jmp     short loc_180005213
0x1800051ad  lea     rdx, [rsp+278h+ppszServer]; ppszServer
0x1800051b2  mov     [rsp+278h+ppszServer], rbp
0x1800051b7  mov     rcx, rsi; pszPath
0x1800051ba  call    cs:__imp_PathIsUNCEx
0x1800051c1  nop     dword ptr [rax+rax+00h]
0x1800051c6  test    eax, eax
0x1800051c8  jz      short loc_180005204
0x1800051ca  mov     rcx, [rsp+278h+ppszServer]; pszStart
0x1800051cf  mov     ebx, 5Ch ; '\'
0x1800051d4  mov     edx, ebx; wMatch
0x1800051d6  call    cs:__imp_StrChrW
0x1800051dd  nop     dword ptr [rax+rax+00h]
0x1800051e2  test    rax, rax
0x1800051e5  jz      short loc_180005204
0x1800051e7  mov     edx, ebx; wMatch
0x1800051e9  lea     rcx, [rax+2]; pszStart
0x1800051ed  call    cs:__imp_StrChrW
0x1800051f4  nop     dword ptr [rax+rax+00h]
0x1800051f9  test    rax, rax
0x1800051fc  jz      short loc_180005204
0x1800051fe  cmp     [rax+2], bp
0x180005202  jz      short loc_180005213
0x180005204  mov     rcx, rsi; pszPath
0x180005207  call    cs:__imp_PathRemoveBackslashW
0x18000520e  nop     dword ptr [rax+rax+00h]
0x180005213  mov     rcx, [rsp+278h+var_28]
0x18000521b  xor     rcx, rsp; StackCookie
0x18000521e  call    __security_check_cookie
0x180005223  mov     rbx, [rsp+278h+arg_10]
0x18000522b  add     rsp, 260h
0x180005232  pop     rdi
0x180005233  pop     rsi
0x180005234  pop     rbp
0x180005235  retn
```
