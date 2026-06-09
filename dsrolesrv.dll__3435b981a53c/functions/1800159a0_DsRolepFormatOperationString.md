# DsRolepFormatOperationString

- ea: `0x1800159a0`
- end: `0x180015c0a`
- name: `DsRolepFormatOperationString`
- size: `618`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b914`
- `0x1800150cc`
- `0x180015c10`
- `0x180015d84`
- `0x180016374`
- `0x180016538`

## callees

- `0x180015670`
- `0x1800159a0`
- `0x180020dbc`
- `0x18002c012`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015be3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015be3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015baa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015baa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015aa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015aa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a02`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015a02`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015b42`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180015b42`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015aaf`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180015aaf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015ae5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015b27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015ae5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180015b27`
- `ntdll!NtOpenThreadToken` at `0x180015a91`
- `ntdll!NtOpenThreadToken` at `0x180015a91`

## string_xrefs

- `0x180015a54`: `Cannot get user Token for Format Message: %d\n`
- `0x180015b52`: `Cannot reset to system security setting: %d\n`

## pseudocode

```c
DWORD DsRolepFormatOperationString(DWORD dwMessageId, _QWORD *a2, ...)
{
  DWORD LastError; // ebx
  BOOL v5; // edi
  int v6; // esi
  DWORD ImpersonationToken; // eax
  DWORD v8; // eax
  __int64 v9; // rax
  SIZE_T v10; // rdi
  HLOCAL v11; // rax
  LPWSTR lpBuffer; // [rsp+48h] [rbp-C0h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v15[1040]; // [rsp+68h] [rbp-A0h] BYREF
  va_list va; // [rsp+4D8h] [rbp+3D0h] BYREF

  va_start(va, a2);
  lpBuffer = (LPWSTR)v15;
  va_copy(Arguments, va);
  if ( !lpSource )
  {
    lpSource = GetModuleHandleW(L"DSROLESRV");
    if ( !lpSource )
      return GetLastError();
  }
  LastError = 0;
  v5 = 0;
  v6 = 0;
  if ( NewTokenHandle )
    goto LABEL_11;
  ImpersonationToken = DsRolepGetImpersonationToken(&NewTokenHandle);
  LastError = ImpersonationToken;
  if ( ImpersonationToken )
  {
    NewTokenHandle = 0;
    if ( ImpersonationToken != 1725 )
      DsRolepLogPrintRoutine(2, "Cannot get user Token for Format Message: %d\n", ImpersonationToken);
    LastError = 0;
  }
  else
  {
    v6 = 1;
  }
  if ( NewTokenHandle )
  {
LABEL_11:
    TokenHandle = 0;
    if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle) < 0 )
      v5 = ImpersonateLoggedOnUser(NewTokenHandle);
    else
      CloseHandle(TokenHandle);
  }
  if ( !FormatMessageW(0x800u, lpSource, dwMessageId, 0, lpBuffer, 0x200u, &Arguments) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      if ( FormatMessageW(0x900u, lpSource, dwMessageId, 0, (LPWSTR)&lpBuffer, 0, &Arguments) )
        LastError = 0;
      else
        LastError = GetLastError();
    }
  }
  if ( v5 && !RevertToSelf() )
  {
    v8 = GetLastError();
    DsRolepLogPrintRoutine(2, "Cannot reset to system security setting: %d\n", v8);
  }
  if ( NewTokenHandle && v6 )
  {
    CloseHandle(NewTokenHandle);
    NewTokenHandle = 0;
  }
  if ( !LastError )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpBuffer[v9] );
    v10 = 2 * v9 + 2;
    v11 = LocalAlloc(0x40u, v10);
    *a2 = v11;
    if ( v11 )
      memcpy_0(v11, lpBuffer, v10);
    else
      LastError = 8;
  }
  if ( lpBuffer != (LPWSTR)v15 )
    LocalFree(lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x1800159a0  mov     rax, rsp
0x1800159a3  mov     [rax+10h], rdx
0x1800159a7  mov     [rax+18h], r8
0x1800159ab  mov     [rax+20h], r9
0x1800159af  push    rbp
0x1800159b0  push    rbx
0x1800159b1  push    rsi
0x1800159b2  push    rdi
0x1800159b3  push    r14
0x1800159b5  push    r15
0x1800159b7  lea     rbp, [rax-3B8h]
0x1800159be  sub     rsp, 488h
0x1800159c5  mov     rax, cs:__security_cookie
0x1800159cc  xor     rax, rsp
0x1800159cf  mov     [rbp+3B0h+var_40], rax
0x1800159d6  lea     rax, [rsp+60h]
0x1800159db  xor     r15d, r15d
0x1800159de  cmp     cs:lpSource, r15
0x1800159e5  mov     r14d, ecx
0x1800159e8  mov     [rsp+4B0h+var_470], rax
0x1800159ed  lea     rax, [rbp+3B0h+arg_10]
0x1800159f4  mov     [rsp+4B0h+Arguments], rax
0x1800159f9  jnz     short loc_180015A1F
0x1800159fb  lea     rcx, aDsrolesrv; "DSROLESRV"
0x180015a02  call    cs:__imp_GetModuleHandleW
0x180015a08  mov     cs:lpSource, rax
0x180015a0f  test    rax, rax
0x180015a12  jnz     short loc_180015A1F
0x180015a14  call    cs:__imp_GetLastError
0x180015a1a  jmp     loc_180015BEB
0x180015a1f  cmp     cs:NewTokenHandle, r15
0x180015a26  mov     ebx, r15d
0x180015a29  mov     edi, r15d
0x180015a2c  mov     esi, r15d
0x180015a2f  jnz     short loc_180015A78
0x180015a31  lea     rcx, NewTokenHandle; NewTokenHandle
0x180015a38  call    DsRolepGetImpersonationToken
0x180015a3d  mov     ebx, eax
0x180015a3f  test    eax, eax
0x180015a41  jz      short loc_180015A6A
0x180015a43  mov     cs:NewTokenHandle, r15
0x180015a4a  cmp     eax, 6BDh
0x180015a4f  jz      short loc_180015A65
0x180015a51  mov     r8d, eax
0x180015a54  lea     rdx, aCannotGetUserT_0; "Cannot get user Token for Format Messag"...
0x180015a5b  mov     ecx, 2
0x180015a60  call    DsRolepLogPrintRoutine
0x180015a65  mov     ebx, r15d
0x180015a68  jmp     short loc_180015A6F
0x180015a6a  mov     esi, 1
0x180015a6f  cmp     cs:NewTokenHandle, r15
0x180015a76  jz      short loc_180015AB7
0x180015a78  lea     r9, [rsp+4B0h+TokenHandle]; TokenHandle
0x180015a7d  mov     [rsp+4B0h+TokenHandle], r15
0x180015a82  mov     r8b, 1; OpenAsSelf
0x180015a85  mov     edx, 8; DesiredAccess
0x180015a8a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180015a91  call    cs:__imp_NtOpenThreadToken
0x180015a97  test    eax, eax
0x180015a99  js      short loc_180015AA8
0x180015a9b  mov     rcx, [rsp+4B0h+TokenHandle]; hObject
0x180015aa0  call    cs:__imp_CloseHandle
0x180015aa6  jmp     short loc_180015AB7
0x180015aa8  mov     rcx, cs:NewTokenHandle; hToken
0x180015aaf  call    cs:__imp_ImpersonateLoggedOnUser
0x180015ab5  mov     edi, eax
0x180015ab7  mov     rcx, [rsp+4B0h+var_470]
0x180015abc  lea     rax, [rsp+4B0h+Arguments]
0x180015ac1  mov     rdx, cs:lpSource; lpSource
0x180015ac8  xor     r9d, r9d; dwLanguageId
0x180015acb  mov     [rsp+30h], rax; Arguments
0x180015ad0  mov     r8d, r14d; dwMessageId
0x180015ad3  mov     [rsp+4B0h+nSize], 200h; nSize
0x180015adb  mov     [rsp+4B0h+lpBuffer], rcx; lpBuffer
0x180015ae0  mov     ecx, 800h; dwFlags
0x180015ae5  call    cs:__imp_FormatMessageW
0x180015aeb  test    eax, eax
0x180015aed  jnz     short loc_180015B3E
0x180015aef  call    cs:__imp_GetLastError
0x180015af5  mov     ebx, eax
0x180015af7  cmp     eax, 7Ah ; 'z'
0x180015afa  jnz     short loc_180015B3E
0x180015afc  mov     rdx, cs:lpSource; lpSource
0x180015b03  lea     rax, [rsp+4B0h+Arguments]
0x180015b08  mov     [rsp+30h], rax; Arguments
0x180015b0d  xor     r9d, r9d; dwLanguageId
0x180015b10  lea     rax, [rsp+4B0h+var_470]
0x180015b15  mov     [rsp+4B0h+nSize], r15d; nSize
0x180015b1a  mov     r8d, r14d; dwMessageId
0x180015b1d  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180015b22  mov     ecx, 900h; dwFlags
0x180015b27  call    cs:__imp_FormatMessageW
0x180015b2d  test    eax, eax
0x180015b2f  jnz     short loc_180015B3B
0x180015b31  call    cs:__imp_GetLastError
0x180015b37  mov     ebx, eax
0x180015b39  jmp     short loc_180015B3E
0x180015b3b  mov     ebx, r15d
0x180015b3e  test    edi, edi
0x180015b40  jz      short loc_180015B66
0x180015b42  call    cs:__imp_RevertToSelf
0x180015b48  test    eax, eax
0x180015b4a  jnz     short loc_180015B66
0x180015b4c  call    cs:__imp_GetLastError
0x180015b52  lea     rdx, aCannotResetToS; "Cannot reset to system security setting"...
0x180015b59  mov     ecx, 2
0x180015b5e  mov     r8d, eax
0x180015b61  call    DsRolepLogPrintRoutine
0x180015b66  mov     rcx, cs:NewTokenHandle; hObject
0x180015b6d  test    rcx, rcx
0x180015b70  jz      short loc_180015B83
0x180015b72  test    esi, esi
0x180015b74  jz      short loc_180015B83
0x180015b76  call    cs:__imp_CloseHandle
0x180015b7c  mov     cs:NewTokenHandle, r15
0x180015b83  test    ebx, ebx
0x180015b85  jnz     short loc_180015BD4
0x180015b87  mov     rcx, [rsp+4B0h+var_470]
0x180015b8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015b90  inc     rax
0x180015b93  cmp     [rcx+rax*2], r15w
0x180015b98  jnz     short loc_180015B90
0x180015b9a  lea     rdi, ds:2[rax*2]
0x180015ba2  mov     ecx, 40h ; '@'; uFlags
0x180015ba7  mov     rdx, rdi; uBytes
0x180015baa  call    cs:__imp_LocalAlloc
0x180015bb0  mov     rcx, [rbp+3B0h+arg_8]
0x180015bb7  mov     [rcx], rax
0x180015bba  test    rax, rax
0x180015bbd  jnz     short loc_180015BC4
0x180015bbf  lea     ebx, [rax+8]
0x180015bc2  jmp     short loc_180015BD4
0x180015bc4  mov     rdx, [rsp+4B0h+var_470]; Src
0x180015bc9  mov     r8, rdi; Size
0x180015bcc  mov     rcx, rax; void *
0x180015bcf  call    memcpy_0
0x180015bd4  mov     rcx, [rsp+4B0h+var_470]; hMem
0x180015bd9  lea     rax, [rsp+60h]
0x180015bde  cmp     rcx, rax
0x180015be1  jz      short loc_180015BE9
0x180015be3  call    cs:__imp_LocalFree
0x180015be9  mov     eax, ebx
0x180015beb  mov     rcx, [rbp+3B0h+var_40]
0x180015bf2  xor     rcx, rsp; StackCookie
0x180015bf5  call    __security_check_cookie
0x180015bfa  add     rsp, 488h
0x180015c01  pop     r15
0x180015c03  pop     r14
0x180015c05  pop     rdi
0x180015c06  pop     rsi
0x180015c07  pop     rbx
0x180015c08  pop     rbp
0x180015c09  retn
```
