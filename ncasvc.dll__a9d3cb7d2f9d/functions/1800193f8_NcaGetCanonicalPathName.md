# NcaGetCanonicalPathName

- ea: `0x1800193f8`
- end: `0x18001951a`
- name: `NcaGetCanonicalPathName`
- size: `290`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x180019520`

## callees

- `0x1800033bc`
- `0x180004f04`
- `0x1800193f8`
- `0x1800199b4`
- `0x180019c70`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019489`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x180019479`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x180019479`

## string_xrefs

- `0x18001949f`: `NcaGetCanonicalPathName`
- `0x1800194d6`: `NcaGetCanonicalPathName`
- `0x1800194e4`: `NcaGetCanonicalPathName`
- `0x180019498`: `PathCanonicalize`

## pseudocode

```c
__int64 __fastcall NcaGetCanonicalPathName(LPCWSTR pszPath, _QWORD *a2)
{
  unsigned __int64 v4; // rax
  unsigned int v5; // ebx
  DWORD LastError; // eax
  int v7; // eax
  __int64 v8; // rdx
  WCHAR pszBuf[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( pszPath[v4] );
  if ( v4 >= 0x104 )
  {
    v5 = -2147024809;
LABEL_15:
    v8 = v5;
    goto LABEL_16;
  }
  if ( !PathCanonicalizeW(pszBuf, pszPath) )
  {
    LastError = GetLastError();
    v5 = NcaReportErrorAsWinError("NcaGetCanonicalPathName", "PathCanonicalize", LastError);
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    return (unsigned int)NcaReportReturnError("NcaGetCanonicalPathName", v5);
  }
  v7 = NcaStringCopy(pszBuf);
  v5 = v7;
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
LABEL_16:
    NcaReportReturnError("NcaGetCanonicalPathName", v8);
    return (unsigned int)NcaReportReturnError("NcaGetCanonicalPathName", v5);
  }
  if ( !*a2 )
  {
    v5 = -2147467261;
    goto LABEL_15;
  }
  return v5;
}

```

## disassembly

```asm
0x1800193f8  mov     [rsp+arg_10], rbx
0x1800193fd  mov     [rsp+arg_18], rsi
0x180019402  push    rdi
0x180019403  sub     rsp, 240h
0x18001940a  mov     rax, cs:__security_cookie
0x180019411  xor     rax, rsp
0x180019414  mov     [rsp+248h+var_18], rax
0x18001941c  mov     rdi, rdx
0x18001941f  mov     rbx, rcx
0x180019422  mov     rcx, cs:WPP_GLOBAL_Control
0x180019429  lea     rax, WPP_GLOBAL_Control
0x180019430  cmp     rcx, rax
0x180019433  jz      short loc_180019450
0x180019435  test    byte ptr [rcx+1Ch], 8
0x180019439  jz      short loc_180019450
0x18001943b  mov     rcx, [rcx+10h]
0x18001943f  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019446  mov     edx, 1Ch
0x18001944b  call    WPP_SF_
0x180019450  xor     esi, esi
0x180019452  mov     [rdi], rsi
0x180019455  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019459  inc     rax
0x18001945c  cmp     [rbx+rax*2], si
0x180019460  jnz     short loc_180019459
0x180019462  cmp     rax, 104h
0x180019468  jb      short loc_180019471
0x18001946a  mov     ebx, 80070057h
0x18001946f  jmp     short loc_1800194D4
0x180019471  mov     rdx, rbx; pszPath
0x180019474  lea     rcx, [rsp+248h+pszBuf]; pszBuf
0x180019479  call    cs:__imp_PathCanonicalizeW
0x180019480  nop     dword ptr [rax+rax+00h]
0x180019485  test    eax, eax
0x180019487  jnz     short loc_1800194B3
0x180019489  call    cs:__imp_GetLastError
0x180019490  nop     dword ptr [rax+rax+00h]
0x180019495  mov     r8d, eax
0x180019498  lea     rdx, aPathcanonicali; "PathCanonicalize"
0x18001949f  lea     rcx, aNcagetcanonica; "NcaGetCanonicalPathName"
0x1800194a6  call    NcaReportErrorAsWinError
0x1800194ab  mov     ebx, eax
0x1800194ad  test    eax, eax
0x1800194af  js      short loc_1800194E2
0x1800194b1  jmp     short loc_1800194F2
0x1800194b3  mov     rdx, rdi
0x1800194b6  lea     rcx, [rsp+248h+pszBuf]; Src
0x1800194bb  call    NcaStringCopy
0x1800194c0  mov     ebx, eax
0x1800194c2  test    eax, eax
0x1800194c4  jns     short loc_1800194CA
0x1800194c6  mov     edx, eax
0x1800194c8  jmp     short loc_1800194D6
0x1800194ca  cmp     [rdi], rsi
0x1800194cd  jnz     short loc_1800194F2
0x1800194cf  mov     ebx, 80004003h
0x1800194d4  mov     edx, ebx
0x1800194d6  lea     rcx, aNcagetcanonica; "NcaGetCanonicalPathName"
0x1800194dd  call    NcaReportReturnError
0x1800194e2  mov     edx, ebx
0x1800194e4  lea     rcx, aNcagetcanonica; "NcaGetCanonicalPathName"
0x1800194eb  call    NcaReportReturnError
0x1800194f0  mov     ebx, eax
0x1800194f2  mov     eax, ebx
0x1800194f4  mov     rcx, [rsp+248h+var_18]
0x1800194fc  xor     rcx, rsp; StackCookie
0x1800194ff  call    __security_check_cookie
0x180019504  lea     r11, [rsp+248h+var_8]
0x18001950c  mov     rbx, [r11+20h]
0x180019510  mov     rsi, [r11+28h]
0x180019514  mov     rsp, r11
0x180019517  pop     rdi
0x180019518  retn
```
