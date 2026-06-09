# FwGetCanonicalPathName

- ea: `0x1800030b0`
- end: `0x180003198`
- name: `FwGetCanonicalPathName`
- size: `232`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180002b30`

## callees

- `0x1800030b0`
- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003107`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x1800030fd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x1800030fd`

## string_xrefs

- `0x180003110`: `PathCanonicalize`
- `0x180003117`: `FwGetCanonicalPathName`
- `0x18000316f`: `FwGetCanonicalPathName`
- `0x18000317d`: `FwGetCanonicalPathName`

## pseudocode

```c
__int64 __fastcall FwGetCanonicalPathName(LPCWSTR pszPath, _QWORD *a2)
{
  unsigned __int64 v3; // rax
  DWORD LastError; // eax
  unsigned int v5; // ebx
  int v7; // eax
  __int64 v8; // rdx
  WCHAR pszBuf[264]; // [rsp+20h] [rbp-228h] BYREF

  *a2 = 0;
  v3 = -1;
  do
    ++v3;
  while ( pszPath[v3] );
  if ( v3 >= 0x104 )
  {
    v5 = -2147024809;
    goto LABEL_10;
  }
  if ( PathCanonicalizeW(pszBuf, pszPath) )
  {
    v7 = FwStringCopy(pszBuf);
    v5 = v7;
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      goto LABEL_11;
    }
    if ( *a2 )
      return v5;
    v5 = -2147467261;
LABEL_10:
    v8 = v5;
LABEL_11:
    FwReportReturnError("FwGetCanonicalPathName", v8);
    return (unsigned int)FwReportReturnError("FwGetCanonicalPathName", v5);
  }
  LastError = GetLastError();
  v5 = FwReportErrorAsWinError("FwGetCanonicalPathName", "PathCanonicalize", LastError);
  if ( (v5 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwGetCanonicalPathName", v5);
  return v5;
}

```

## disassembly

```asm
0x1800030b0  mov     [rsp+arg_10], rbx
0x1800030b5  mov     [rsp+arg_18], rsi
0x1800030ba  push    rdi
0x1800030bb  sub     rsp, 240h
0x1800030c2  mov     rax, cs:__security_cookie
0x1800030c9  xor     rax, rsp
0x1800030cc  mov     [rsp+248h+var_18], rax
0x1800030d4  xor     esi, esi
0x1800030d6  mov     rdi, rdx
0x1800030d9  mov     [rdx], rsi
0x1800030dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800030e0  inc     rax
0x1800030e3  cmp     [rcx+rax*2], si
0x1800030e7  jnz     short loc_1800030E0
0x1800030e9  cmp     rax, 104h
0x1800030ef  jnb     loc_18000318D
0x1800030f5  mov     rdx, rcx; pszPath
0x1800030f8  lea     rcx, [rsp+248h+pszBuf]; pszBuf
0x1800030fd  call    cs:__imp_PathCanonicalizeW
0x180003103  test    eax, eax
0x180003105  jnz     short loc_180003150
0x180003107  call    cs:__imp_GetLastError
0x18000310d  mov     r8d, eax
0x180003110  lea     rdx, aPathcanonicali; "PathCanonicalize"
0x180003117  lea     rcx, aFwgetcanonical; "FwGetCanonicalPathName"
0x18000311e  call    FwReportErrorAsWinError
0x180003123  mov     ebx, eax
0x180003125  test    eax, eax
0x180003127  js      short loc_18000317B
0x180003129  mov     eax, ebx
0x18000312b  mov     rcx, [rsp+248h+var_18]
0x180003133  xor     rcx, rsp; StackCookie
0x180003136  call    __security_check_cookie
0x18000313b  lea     r11, [rsp+248h+var_8]
0x180003143  mov     rbx, [r11+20h]
0x180003147  mov     rsi, [r11+28h]
0x18000314b  mov     rsp, r11
0x18000314e  pop     rdi
0x18000314f  retn
0x180003150  mov     rdx, rdi
0x180003153  lea     rcx, [rsp+248h+pszBuf]; Src
0x180003158  call    FwStringCopy
0x18000315d  mov     ebx, eax
0x18000315f  test    eax, eax
0x180003161  js      short loc_180003194
0x180003163  cmp     [rdi], rsi
0x180003166  jnz     short loc_180003129
0x180003168  mov     ebx, 80004003h
0x18000316d  mov     edx, ebx
0x18000316f  lea     rcx, aFwgetcanonical; "FwGetCanonicalPathName"
0x180003176  call    FwReportReturnError
0x18000317b  mov     edx, ebx
0x18000317d  lea     rcx, aFwgetcanonical; "FwGetCanonicalPathName"
0x180003184  call    FwReportReturnError
0x180003189  mov     ebx, eax
0x18000318b  jmp     short loc_180003129
0x18000318d  mov     ebx, 80070057h
0x180003192  jmp     short loc_18000316D
0x180003194  mov     edx, eax
0x180003196  jmp     short loc_18000316F
```
