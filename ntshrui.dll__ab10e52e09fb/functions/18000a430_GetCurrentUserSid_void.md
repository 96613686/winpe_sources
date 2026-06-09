# GetCurrentUserSid(void * *)

- ea: `0x18000a430`
- end: `0x18000a5f0`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `448`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009c50`
- `0x180059d74`
- `0x18005a228`
- `0x18005a488`
- `0x18005a4c8`
- `0x180067504`
- `0x1800675cc`
- `0x18007129c`
- `0x1800719c4`
- `0x180072f1c`

## callees

- `0x1800098dc`
- `0x18000a430`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a48f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a485`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a485`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a46a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a46a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a595`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a5a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a5a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a54d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a54d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a4dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a4dc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a4fe`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a4fe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a535`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a535`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a50b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a50b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a51f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a51f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5e5`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int Error; // ebx
  void *v5; // rsi
  void *v6; // rcx
  DWORD LengthSid; // ebp
  HLOCAL v8; // rax
  void *v9; // rdi
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-98h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-90h] BYREF
  void *TokenInformation; // [rsp+40h] [rbp-88h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_7;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
    Error = -2147467259;
  }
  else if ( Error == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_7:
      ReturnLength = 88;
      if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, 0x58u, &ReturnLength) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_13;
      }
      v5 = TokenInformation;
      Error = -2147024809;
      v6 = TokenInformation;
      *a1 = 0;
      if ( !IsValidSid(v6) )
        goto LABEL_13;
      LengthSid = GetLengthSid(v5);
      Error = -2147024882;
      v8 = LocalAlloc(0x40u, LengthSid);
      v9 = v8;
      if ( !v8 )
        goto LABEL_13;
      if ( CopySid(LengthSid, v8, v5) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          LocalFree(v9);
          goto LABEL_13;
        }
      }
      *a1 = v9;
LABEL_13:
      CloseHandle(TokenHandle);
      return (unsigned int)Error;
    }
    Error = ResultFromKnownLastError();
  }
  if ( Error >= 0 )
    goto LABEL_7;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a430  mov     [rsp+arg_8], rbx
0x18000a435  mov     [rsp+arg_10], rbp
0x18000a43a  push    rsi
0x18000a43b  push    rdi
0x18000a43c  push    r14
0x18000a43e  sub     rsp, 0B0h
0x18000a445  mov     rax, cs:__security_cookie
0x18000a44c  xor     rax, rsp
0x18000a44f  mov     [rsp+0C8h+var_28], rax
0x18000a457  mov     r14, rcx
0x18000a45a  mov     qword ptr [rcx], 0
0x18000a461  mov     [rsp+0C8h+TokenHandle], 0
0x18000a46a  call    cs:__imp_GetCurrentThread
0x18000a470  mov     esi, 1
0x18000a475  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x18000a47a  mov     rcx, rax; ThreadHandle
0x18000a47d  mov     r8d, esi; OpenAsSelf
0x18000a480  lea     edi, [rsi+7]
0x18000a483  mov     edx, edi; DesiredAccess
0x18000a485  call    cs:__imp_OpenThreadToken
0x18000a48b  test    eax, eax
0x18000a48d  jnz     short loc_18000A4BB
0x18000a48f  call    cs:__imp_GetLastError
0x18000a495  mov     ebx, eax
0x18000a497  test    eax, eax
0x18000a499  jg      loc_18000A587
0x18000a49f  test    ebx, ebx
0x18000a4a1  jns     loc_18000A57D
0x18000a4a7  cmp     ebx, 800703F0h
0x18000a4ad  jz      loc_18000A595
0x18000a4b3  test    ebx, ebx
0x18000a4b5  js      loc_18000A553
0x18000a4bb  mov     rcx, [rsp+0C8h+TokenHandle]; TokenHandle
0x18000a4c0  lea     rax, [rsp+0C8h+var_90]
0x18000a4c5  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18000a4cb  mov     [rsp+0C8h+ReturnLength], rax; ReturnLength
0x18000a4d0  lea     r8, [rsp+0C8h+TokenInformation]; TokenInformation
0x18000a4d5  mov     [rsp+0C8h+var_90], r9d
0x18000a4da  mov     edx, esi; TokenInformationClass
0x18000a4dc  call    cs:__imp_GetTokenInformation
0x18000a4e2  test    eax, eax
0x18000a4e4  jz      loc_18000A5BF
0x18000a4ea  mov     rsi, [rsp+0C8h+TokenInformation]
0x18000a4ef  mov     ebx, 80070057h
0x18000a4f4  mov     rcx, rsi; pSid
0x18000a4f7  mov     qword ptr [r14], 0
0x18000a4fe  call    cs:__imp_IsValidSid
0x18000a504  test    eax, eax
0x18000a506  jz      short loc_18000A548
0x18000a508  mov     rcx, rsi; pSid
0x18000a50b  call    cs:__imp_GetLengthSid
0x18000a511  mov     edx, eax; uBytes
0x18000a513  mov     ecx, 40h ; '@'; uFlags
0x18000a518  mov     ebp, eax
0x18000a51a  mov     ebx, 8007000Eh
0x18000a51f  call    cs:__imp_LocalAlloc
0x18000a525  mov     rdi, rax
0x18000a528  test    rax, rax
0x18000a52b  jz      short loc_18000A548
0x18000a52d  mov     r8, rsi; pSourceSid
0x18000a530  mov     rdx, rax; pDestinationSid
0x18000a533  mov     ecx, ebp; nDestinationSidLength
0x18000a535  call    cs:__imp_CopySid
0x18000a53b  test    eax, eax
0x18000a53d  jz      loc_18000A5D3
0x18000a543  xor     ebx, ebx
0x18000a545  mov     [r14], rdi
0x18000a548  mov     rcx, [rsp+0C8h+TokenHandle]; hObject
0x18000a54d  call    cs:__imp_CloseHandle
0x18000a553  mov     eax, ebx
0x18000a555  mov     rcx, [rsp+0C8h+var_28]
0x18000a55d  xor     rcx, rsp; StackCookie
0x18000a560  call    __security_check_cookie
0x18000a565  lea     r11, [rsp+0C8h+var_18]
0x18000a56d  mov     rbx, [r11+28h]
0x18000a571  mov     rbp, [r11+30h]
0x18000a575  mov     rsp, r11
0x18000a578  pop     r14
0x18000a57a  pop     rdi
0x18000a57b  pop     rsi
0x18000a57c  retn
0x18000a57d  mov     ebx, 80004005h
0x18000a582  jmp     loc_18000A4B3
0x18000a587  movzx   ebx, ax
0x18000a58a  or      ebx, 80070000h
0x18000a590  jmp     loc_18000A49F
0x18000a595  call    cs:__imp_GetCurrentProcess
0x18000a59b  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x18000a5a0  mov     edx, edi; DesiredAccess
0x18000a5a2  mov     rcx, rax; ProcessHandle
0x18000a5a5  call    cs:__imp_OpenProcessToken
0x18000a5ab  test    eax, eax
0x18000a5ad  jnz     loc_18000A4BB
0x18000a5b3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a5b8  mov     ebx, eax
0x18000a5ba  jmp     loc_18000A4B3
0x18000a5bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a5c4  mov     ebx, eax
0x18000a5c6  test    eax, eax
0x18000a5c8  js      loc_18000A548
0x18000a5ce  jmp     loc_18000A4EA
0x18000a5d3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a5d8  mov     ebx, eax
0x18000a5da  test    eax, eax
0x18000a5dc  jns     loc_18000A545
0x18000a5e2  mov     rcx, rdi; hMem
0x18000a5e5  call    cs:__imp_LocalFree
0x18000a5eb  jmp     loc_18000A548
```
