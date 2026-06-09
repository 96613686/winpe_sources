# DsRolepMakeAltRegistry

- ea: `0x180017c98`
- end: `0x180017fa8`
- name: `DsRolepMakeAltRegistry`
- size: `784`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, wchar_t *lpPathName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016e94`

## callees

- `0x180008ea4`
- `0x180008fd4`
- `0x180017c98`
- `0x180018134`
- `0x180018358`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017daa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180017daa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180017d33`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180017d33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f39`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017d04`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017d04`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017e97`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017f2f`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017e97`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180017f2f`

## string_xrefs

- `0x180017d17`: `Failed to retrieve environmental variable "temp" - 0x%x\n`
- `0x180017d8f`: `Failed to format temp registry path 0x%x\n`
- `0x180017dd7`: `Failed to create temp directory for temp registry files 0x%x, %ws\n`
- `0x180017df0`: `Making copy of IFM registry to temp directry: %ws\n`
- `0x180017f51`: `Failed to copy file from %ws to %ws with 0x%x\n`
- `0x180017ed0`: `\security`
- `0x180017f0a`: `\security`

## pseudocode

```c
__int64 __fastcall DsRolepMakeAltRegistry(STRSAFE_LPCWSTR pszSrc, wchar_t *lpPathName)
{
  DWORD LastError; // ebx
  unsigned __int16 v5; // ax
  size_t v6; // rdx
  __int64 v7; // r14
  __int64 v8; // rax
  size_t v9; // rdx
  __int64 v10; // rax
  size_t v11; // rdx
  __int64 v12; // rax
  size_t v13; // rdx
  int wYear; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+20h] [rbp-E0h]
  int wMonth; // [rsp+28h] [rbp-D8h]
  int wDay; // [rsp+30h] [rbp-D0h]
  int wMinute; // [rsp+38h] [rbp-C8h]
  int wSecond; // [rsp+40h] [rbp-C0h]
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDest[264]; // [rsp+270h] [rbp+170h] BYREF

  SystemTime = 0;
  if ( pszSrc && *pszSrc )
  {
    *lpPathName = 0;
    if ( GetEnvironmentVariableW(L"temp", Buffer, 0x105u) )
    {
      GetSystemTime(&SystemTime);
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wDay = SystemTime.wDay;
      wMonth = SystemTime.wMonth;
      wYear = SystemTime.wYear;
      v5 = StringCbPrintfW(
             lpPathName,
             0x105u,
             L"%ws\\ifm-reg-%d-%d-%d-%d-%d",
             Buffer,
             wYear,
             wMonth,
             wDay,
             wMinute,
             wSecond);
      LastError = v5;
      if ( v5 )
      {
        *lpPathName = 0;
        DsRolepLogPrintRoutine(1, "Failed to format temp registry path 0x%x\n", v5);
        goto LABEL_24;
      }
      if ( CreateDirectoryW(lpPathName, 0) )
      {
        DsRolepLogPrintRoutine(4, "Making copy of IFM registry to temp directry: %ws\n", lpPathName);
        StringCchCopyW(Buffer, 0x105u, pszSrc);
        v7 = -1;
        v8 = -1;
        do
          ++v8;
        while ( Buffer[v8] );
        StringCchCatNW(Buffer, v6, L"\\system", 260 - v8);
        StringCchCopyW(pszDest, 0x105u, lpPathName);
        v10 = -1;
        do
          ++v10;
        while ( pszDest[v10] );
        StringCchCatNW(pszDest, v9, L"\\system", 260 - v10);
        if ( CopyFileW(Buffer, pszDest, 1) )
        {
          StringCchCopyW(Buffer, 0x105u, pszSrc);
          v12 = -1;
          do
            ++v12;
          while ( Buffer[v12] );
          StringCchCatNW(Buffer, v11, L"\\security", 260 - v12);
          StringCchCopyW(pszDest, 0x105u, lpPathName);
          do
            ++v7;
          while ( pszDest[v7] );
          StringCchCatNW(pszDest, v13, L"\\security", 260 - v7);
          if ( CopyFileW(Buffer, pszDest, 1) )
            return LastError;
        }
        LODWORD(v16) = GetLastError();
        LastError = v16;
        DsRolepLogPrintRoutine(1, "Failed to copy file from %ws to %ws with 0x%x\n", Buffer, pszDest, v16);
      }
      else
      {
        if ( GetLastError() )
          LastError = GetLastError();
        else
          LastError = 87;
        *lpPathName = 0;
        DsRolepLogPrintRoutine(
          1,
          "Failed to create temp directory for temp registry files 0x%x, %ws\n",
          lpPathName,
          LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "Failed to retrieve environmental variable \"temp\" - 0x%x\n", LastError);
    }
    if ( !LastError )
      return LastError;
LABEL_24:
    if ( *lpPathName )
    {
      NtdspClearDirectory(lpPathName);
      *lpPathName = 0;
    }
    return LastError;
  }
  return 87;
}

```

## disassembly

```asm
0x180017c98  mov     [rsp-8+arg_10], rbx
0x180017c9d  push    rbp
0x180017c9e  push    rsi
0x180017c9f  push    rdi
0x180017ca0  push    r12
0x180017ca2  push    r13
0x180017ca4  push    r14
0x180017ca6  push    r15
0x180017ca8  lea     rbp, [rsp-390h]
0x180017cb0  sub     rsp, 490h
0x180017cb7  mov     rax, cs:__security_cookie
0x180017cbe  xor     rax, rsp
0x180017cc1  mov     [rbp+3C0h+var_40], rax
0x180017cc8  xor     r13d, r13d
0x180017ccb  xorps   xmm0, xmm0
0x180017cce  mov     rdi, rdx
0x180017cd1  mov     r15, rcx
0x180017cd4  movups  xmmword ptr [rsp+4C0h+SystemTime.wYear], xmm0
0x180017cd9  test    rcx, rcx
0x180017cdc  jz      loc_180017F79
0x180017ce2  cmp     [rcx], r13w
0x180017ce6  jz      loc_180017F79
0x180017cec  mov     [rdx], r13w
0x180017cf0  lea     rcx, Name; "temp"
0x180017cf7  mov     esi, 105h
0x180017cfc  lea     rdx, [rsp+4C0h+Buffer]; lpBuffer
0x180017d01  mov     r8d, esi; nSize
0x180017d04  call    cs:__imp_GetEnvironmentVariableW
0x180017d0a  test    eax, eax
0x180017d0c  jnz     short loc_180017D2E
0x180017d0e  call    cs:__imp_GetLastError
0x180017d14  mov     r8d, eax
0x180017d17  lea     rdx, aFailedToRetrie; "Failed to retrieve environmental variab"...
0x180017d1e  lea     ecx, [r13+1]
0x180017d22  mov     ebx, eax
0x180017d24  call    DsRolepLogPrintRoutine
0x180017d29  jmp     loc_180017F5F
0x180017d2e  lea     rcx, [rsp+4C0h+SystemTime]; lpSystemTime
0x180017d33  call    cs:__imp_GetSystemTime
0x180017d39  movzx   ecx, [rsp+4C0h+SystemTime.wMinute]
0x180017d3e  movzx   edx, [rsp+4C0h+SystemTime.wDay]
0x180017d43  movzx   r8d, [rsp+4C0h+SystemTime.wMonth]
0x180017d49  movzx   r9d, [rsp+4C0h+SystemTime.wYear]
0x180017d4f  movzx   eax, [rsp+4C0h+SystemTime.wSecond]
0x180017d54  mov     [rsp+4C0h+var_480], eax
0x180017d58  mov     [rsp+4C0h+var_488], ecx
0x180017d5c  mov     rcx, rdi; pszDest
0x180017d5f  mov     [rsp+4C0h+var_490], edx
0x180017d63  mov     rdx, rsi; cbDest
0x180017d66  mov     [rsp+4C0h+var_498], r8d
0x180017d6b  lea     r8, aWsIfmRegDDDDD; "%ws\\ifm-reg-%d-%d-%d-%d-%d"
0x180017d72  mov     dword ptr [rsp+4C0h+var_4A0], r9d
0x180017d77  lea     r9, [rsp+4C0h+Buffer]
0x180017d7c  call    StringCbPrintfW
0x180017d81  movzx   ebx, ax
0x180017d84  test    ebx, ebx
0x180017d86  jz      short loc_180017DA5
0x180017d88  mov     r8d, ebx
0x180017d8b  mov     [rdi], r13w
0x180017d8f  lea     rdx, aFailedToFormat; "Failed to format temp registry path 0x%"...
0x180017d96  mov     ecx, 1
0x180017d9b  call    DsRolepLogPrintRoutine
0x180017da0  jmp     loc_180017F63
0x180017da5  xor     edx, edx; lpSecurityAttributes
0x180017da7  mov     rcx, rdi; lpPathName
0x180017daa  call    cs:__imp_CreateDirectoryW
0x180017db0  test    eax, eax
0x180017db2  jnz     short loc_180017DED
0x180017db4  call    cs:__imp_GetLastError
0x180017dba  test    eax, eax
0x180017dbc  jz      short loc_180017DC8
0x180017dbe  call    cs:__imp_GetLastError
0x180017dc4  mov     ebx, eax
0x180017dc6  jmp     short loc_180017DCD
0x180017dc8  mov     ebx, 57h ; 'W'
0x180017dcd  mov     r9d, ebx
0x180017dd0  mov     [rdi], r13w
0x180017dd4  mov     r8, rdi
0x180017dd7  lea     rdx, aFailedToCreate_0; "Failed to create temp directory for tem"...
0x180017dde  mov     ecx, 1
0x180017de3  call    DsRolepLogPrintRoutine
0x180017de8  jmp     loc_180017F5F
0x180017ded  mov     r8, rdi
0x180017df0  lea     rdx, aMakingCopyOfIf; "Making copy of IFM registry to temp dir"...
0x180017df7  mov     ecx, 4
0x180017dfc  call    DsRolepLogPrintRoutine
0x180017e01  mov     r8, r15; pszSrc
0x180017e04  lea     rcx, [rsp+4C0h+Buffer]; pszDest
0x180017e09  mov     rdx, rsi; cchDest
0x180017e0c  call    StringCchCopyW
0x180017e11  or      r14, 0FFFFFFFFFFFFFFFFh
0x180017e15  lea     r11, [rsp+4C0h+Buffer]
0x180017e1a  mov     rax, r14
0x180017e1d  inc     rax
0x180017e20  cmp     [r11+rax*2], r13w
0x180017e25  jnz     short loc_180017E1D
0x180017e27  mov     r12d, 104h
0x180017e2d  lea     r8, aSystem; "\\system"
0x180017e34  mov     r9d, r12d
0x180017e37  lea     rcx, [rsp+4C0h+Buffer]; pszDest
0x180017e3c  sub     r9, rax; cchToAppend
0x180017e3f  call    StringCchCatNW
0x180017e44  mov     r8, rdi; pszSrc
0x180017e47  lea     rcx, [rbp+3C0h+pszDest]; pszDest
0x180017e4e  mov     rdx, rsi; cchDest
0x180017e51  call    StringCchCopyW
0x180017e56  mov     rax, r14
0x180017e59  lea     r11, [rbp+3C0h+pszDest]
0x180017e60  inc     rax
0x180017e63  cmp     [r11+rax*2], r13w
0x180017e68  jnz     short loc_180017E60
0x180017e6a  mov     r9, r12
0x180017e6d  lea     r8, aSystem; "\\system"
0x180017e74  sub     r9, rax; cchToAppend
0x180017e77  lea     rcx, [rbp+3C0h+pszDest]; pszDest
0x180017e7e  call    StringCchCatNW
0x180017e83  mov     esi, 1
0x180017e88  lea     rdx, [rbp+3C0h+pszDest]; lpNewFileName
0x180017e8f  mov     r8d, esi; bFailIfExists
0x180017e92  lea     rcx, [rsp+4C0h+Buffer]; lpExistingFileName
0x180017e97  call    cs:__imp_CopyFileW
0x180017e9d  test    eax, eax
0x180017e9f  jz      loc_180017F39
0x180017ea5  mov     r8, r15; pszSrc
0x180017ea8  lea     rcx, [rsp+4C0h+Buffer]; pszDest
0x180017ead  mov     r15d, 105h
0x180017eb3  mov     edx, r15d; cchDest
0x180017eb6  call    StringCchCopyW
0x180017ebb  mov     rax, r14
0x180017ebe  lea     r11, [rsp+4C0h+Buffer]
0x180017ec3  inc     rax
0x180017ec6  cmp     [r11+rax*2], r13w
0x180017ecb  jnz     short loc_180017EC3
0x180017ecd  mov     r9, r12
0x180017ed0  lea     r8, aSecurity_0; "\\security"
0x180017ed7  sub     r9, rax; cchToAppend
0x180017eda  lea     rcx, [rsp+4C0h+Buffer]; pszDest
0x180017edf  call    StringCchCatNW
0x180017ee4  mov     r8, rdi; pszSrc
0x180017ee7  lea     rcx, [rbp+3C0h+pszDest]; pszDest
0x180017eee  mov     rdx, r15; cchDest
0x180017ef1  call    StringCchCopyW
0x180017ef6  lea     r11, [rbp+3C0h+pszDest]
0x180017efd  inc     r14
0x180017f00  cmp     [r11+r14*2], r13w
0x180017f05  jnz     short loc_180017EFD
0x180017f07  sub     r12, r14
0x180017f0a  lea     r8, aSecurity_0; "\\security"
0x180017f11  mov     r9, r12; cchToAppend
0x180017f14  lea     rcx, [rbp+3C0h+pszDest]; pszDest
0x180017f1b  call    StringCchCatNW
0x180017f20  mov     r8d, esi; bFailIfExists
0x180017f23  lea     rdx, [rbp+3C0h+pszDest]; lpNewFileName
0x180017f2a  lea     rcx, [rsp+4C0h+Buffer]; lpExistingFileName
0x180017f2f  call    cs:__imp_CopyFileW
0x180017f35  test    eax, eax
0x180017f37  jnz     short loc_180017F75
0x180017f39  call    cs:__imp_GetLastError
0x180017f3f  lea     r9, [rbp+3C0h+pszDest]
0x180017f46  mov     ecx, esi
0x180017f48  lea     r8, [rsp+4C0h+Buffer]
0x180017f4d  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180017f51  lea     rdx, aFailedToCopyFi; "Failed to copy file from %ws to %ws wit"...
0x180017f58  mov     ebx, eax
0x180017f5a  call    DsRolepLogPrintRoutine
0x180017f5f  test    ebx, ebx
0x180017f61  jz      short loc_180017F75
0x180017f63  cmp     [rdi], r13w
0x180017f67  jz      short loc_180017F75
0x180017f69  mov     rcx, rdi; lpPathName
0x180017f6c  call    NtdspClearDirectory
0x180017f71  mov     [rdi], r13w
0x180017f75  mov     eax, ebx
0x180017f77  jmp     short loc_180017F7E
0x180017f79  mov     eax, 57h ; 'W'
0x180017f7e  mov     rcx, [rbp+3C0h+var_40]
0x180017f85  xor     rcx, rsp; StackCookie
0x180017f88  call    __security_check_cookie
0x180017f8d  mov     rbx, [rsp+4C0h+arg_10]
0x180017f95  add     rsp, 490h
0x180017f9c  pop     r15
0x180017f9e  pop     r14
0x180017fa0  pop     r13
0x180017fa2  pop     r12
0x180017fa4  pop     rdi
0x180017fa5  pop     rsi
0x180017fa6  pop     rbp
0x180017fa7  retn
```
