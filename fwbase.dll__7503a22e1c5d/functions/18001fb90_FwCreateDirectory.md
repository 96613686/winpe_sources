# FwCreateDirectory

- ea: `0x18001fb90`
- end: `0x18001fcbe`
- name: `FwCreateDirectory`
- size: `302`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x18001e1d0`
- `0x18001fb90`
- `0x18002f38c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc44`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001fc3a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001fc3a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18001fbf6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18001fbf6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18001fc05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathSkipRootW` at `0x18001fc05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x18001fbe7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCanonicalizeW` at `0x18001fbe7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18001fc1d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18001fc6c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18001fc1d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18001fc6c`

## string_xrefs

- `0x18001fc58`: `mpssvc.dll`
- `0x18001fbca`: `FwCreateDirectory`
- `0x18001fc7e`: `FwCreateDirectory`
- `0x18001fc92`: `FwCreateDirectory`
- `0x18001fc77`: `CreateDirectoryW`

## pseudocode

```c
__int64 __fastcall FwCreateDirectory(LPCWSTR pszPath)
{
  unsigned __int64 v1; // rax
  unsigned int v2; // ebx
  BOOL IsRelativeW; // eax
  WCHAR *v4; // rcx
  LPWSTR v5; // rax
  LPWSTR NextComponentW; // rax
  WCHAR *v8; // rdi
  WCHAR v9; // si
  DWORD LastError; // eax
  WCHAR pszBuf[264]; // [rsp+20h] [rbp-248h] BYREF

  v1 = -1;
  do
    ++v1;
  while ( pszPath[v1] );
  if ( v1 <= 0x104 && PathCanonicalizeW(pszBuf, pszPath) )
  {
    IsRelativeW = PathIsRelativeW(pszBuf);
    v4 = pszBuf;
    if ( !IsRelativeW )
    {
      v5 = PathSkipRootW(pszBuf);
      if ( !v5 )
        return 2147942487LL;
      v4 = v5;
    }
    NextComponentW = PathFindNextComponentW(v4);
    v2 = 0;
    while ( 1 )
    {
      v8 = NextComponentW;
      if ( !NextComponentW )
        break;
      v9 = *NextComponentW;
      *NextComponentW = 0;
      if ( !CreateDirectoryW(pszBuf, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError )
          {
            v2 = FwReportErrorAsWinError("FwCreateDirectory", "CreateDirectoryW", LastError);
            if ( (v2 & 0x80000000) == 0 )
              return v2;
            return (unsigned int)FwReportReturnError("FwCreateDirectory", v2);
          }
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", 0, 0);
        }
      }
      *v8 = v9;
      NextComponentW = PathFindNextComponentW(v8);
    }
  }
  else
  {
    v2 = -2147024809;
    FwReportReturnError("FwCreateDirectory", 2147942487LL);
    return (unsigned int)FwReportReturnError("FwCreateDirectory", v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18001fb90  push    rbx
0x18001fb92  push    rbp
0x18001fb93  push    rsi
0x18001fb94  push    rdi
0x18001fb95  sub     rsp, 248h
0x18001fb9c  mov     rax, cs:__security_cookie
0x18001fba3  xor     rax, rsp
0x18001fba6  mov     [rsp+268h+var_38], rax
0x18001fbae  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fbb2  xor     ebp, ebp
0x18001fbb4  inc     rax
0x18001fbb7  cmp     [rcx+rax*2], bp
0x18001fbbb  jnz     short loc_18001FBB4
0x18001fbbd  cmp     rax, 104h
0x18001fbc3  jbe     short loc_18001FBDF
0x18001fbc5  mov     eax, 80070057h
0x18001fbca  lea     rcx, aFwcreatedirect_0; "FwCreateDirectory"
0x18001fbd1  mov     edx, eax
0x18001fbd3  mov     ebx, eax
0x18001fbd5  call    FwReportReturnError
0x18001fbda  jmp     loc_18001FC90
0x18001fbdf  mov     rdx, rcx; pszPath
0x18001fbe2  lea     rcx, [rsp+268h+pszBuf]; pszBuf
0x18001fbe7  call    cs:__imp_PathCanonicalizeW
0x18001fbed  test    eax, eax
0x18001fbef  jz      short loc_18001FBC5
0x18001fbf1  lea     rcx, [rsp+268h+pszBuf]; pszPath
0x18001fbf6  call    cs:__imp_PathIsRelativeW
0x18001fbfc  lea     rcx, [rsp+268h+pszBuf]; pszPath
0x18001fc01  test    eax, eax
0x18001fc03  jnz     short loc_18001FC1D
0x18001fc05  call    cs:__imp_PathSkipRootW
0x18001fc0b  test    rax, rax
0x18001fc0e  jnz     short loc_18001FC1A
0x18001fc10  mov     eax, 80070057h
0x18001fc15  jmp     loc_18001FCA2
0x18001fc1a  mov     rcx, rax; pszPath
0x18001fc1d  call    cs:__imp_PathFindNextComponentW
0x18001fc23  mov     ebx, ebp
0x18001fc25  mov     rdi, rax
0x18001fc28  test    rax, rax
0x18001fc2b  jz      short loc_18001FCA0
0x18001fc2d  movzx   esi, word ptr [rax]
0x18001fc30  lea     rcx, [rsp+268h+pszBuf]; lpPathName
0x18001fc35  xor     edx, edx; lpSecurityAttributes
0x18001fc37  mov     [rax], bp
0x18001fc3a  call    cs:__imp_CreateDirectoryW
0x18001fc40  test    eax, eax
0x18001fc42  jnz     short loc_18001FC66
0x18001fc44  call    cs:__imp_GetLastError
0x18001fc4a  cmp     eax, 0B7h
0x18001fc4f  jz      short loc_18001FC66
0x18001fc51  test    eax, eax
0x18001fc53  jnz     short loc_18001FC74
0x18001fc55  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "winError != NO_ERROR", "CreateDirectoryW failed")
0x18001fc58  lea     rcx, aMpssvcDll_0; "mpssvc.dll"
0x18001fc5f  xor     edx, edx
0x18001fc61  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001fc66  mov     rcx, rdi; pszPath
0x18001fc69  mov     [rdi], si
0x18001fc6c  call    cs:__imp_PathFindNextComponentW
0x18001fc72  jmp     short loc_18001FC25
0x18001fc74  mov     r8d, eax
0x18001fc77  lea     rdx, aCreatedirector; "CreateDirectoryW"
0x18001fc7e  lea     rcx, aFwcreatedirect_0; "FwCreateDirectory"
0x18001fc85  call    FwReportErrorAsWinError
0x18001fc8a  mov     ebx, eax
0x18001fc8c  test    eax, eax
0x18001fc8e  jns     short loc_18001FCA0
0x18001fc90  mov     edx, ebx
0x18001fc92  lea     rcx, aFwcreatedirect_0; "FwCreateDirectory"
0x18001fc99  call    FwReportReturnError
0x18001fc9e  mov     ebx, eax
0x18001fca0  mov     eax, ebx
0x18001fca2  mov     rcx, [rsp+268h+var_38]
0x18001fcaa  xor     rcx, rsp; StackCookie
0x18001fcad  call    __security_check_cookie
0x18001fcb2  add     rsp, 248h
0x18001fcb9  pop     rdi
0x18001fcba  pop     rsi
0x18001fcbb  pop     rbp
0x18001fcbc  pop     rbx
0x18001fcbd  retn
```
