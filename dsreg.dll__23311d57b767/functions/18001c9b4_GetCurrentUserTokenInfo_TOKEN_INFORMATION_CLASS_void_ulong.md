# GetCurrentUserTokenInfo(_TOKEN_INFORMATION_CLASS,void * *,ulong *)

- ea: `0x18001c9b4`
- end: `0x18001cb85`
- name: `?GetCurrentUserTokenInfo@@YAJW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z`
- size: `465`
- prototype: `__int64 __fastcall(TOKEN_INFORMATION_CLASS TokenInformationClass, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012eb8`
- `0x1800b1dac`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180012cf0`
- `0x18001c9b4`
- `0x1800307c4`
- `0x18003334c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c9fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c9fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c9e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c9e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ca28`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001ca28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ca17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ca17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cafc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cafc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ca84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001caf2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ca84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001caf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb67`

## string_xrefs

- `0x18001ca48`: `GetCurrentUserTokenInfo`
- `0x18001cabf`: `GetCurrentUserTokenInfo`
- `0x18001cb37`: `GetCurrentUserTokenInfo`
- `0x18001cb51`: `GetCurrentUserTokenInfo`
- `0x18001ca3e`: `OpenProcessToken`
- `0x18001caa3`: `GetTokenInformation`
- `0x18001ca64`: `OpenThreadToken`

## pseudocode

```c
__int64 __fastcall GetCurrentUserTokenInfo(TOKEN_INFORMATION_CLASS TokenInformationClass, void **a2, unsigned int *a3)
{
  void *v3; // rsi
  int v6; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  const wchar_t *v10; // r8
  __int64 v11; // r9
  DWORD v12; // eax
  unsigned int v13; // edi
  DWORD v14; // eax
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  int v18; // [rsp+64h] [rbp+1Ch]

  v18 = HIDWORD(a3);
  v3 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCurrentUserTokenInfo", L"ppInfo");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetCurrentUserTokenInfo", L"ppInfo");
    goto LABEL_29;
  }
  v6 = 0;
  *a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError != 1008 )
  {
    if ( LastError )
    {
      v10 = L"OpenThreadToken";
      goto LABEL_7;
    }
LABEL_11:
    if ( !GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, &TokenInformationLength) )
    {
      v12 = GetLastError();
      v6 = 0;
      if ( v12 != 122 )
        v6 = v12;
      if ( v6 )
      {
        v11 = (unsigned int)v6;
LABEL_16:
        v10 = L"GetTokenInformation";
        goto LABEL_8;
      }
      v6 = 0;
    }
    v3 = SafeAlloc(TokenInformationLength);
    if ( v3 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenInformationClass, v3, TokenInformationLength, &TokenInformationLength) )
      {
        v14 = GetLastError();
        v6 = v14;
        if ( v14 )
        {
          v11 = v14;
          goto LABEL_16;
        }
      }
      v13 = 0;
      *a2 = v3;
      v3 = 0;
    }
    else
    {
      v13 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetCurrentUserTokenInfo");
    }
    if ( !v6 )
      goto LABEL_29;
    goto LABEL_25;
  }
  v6 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_11;
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
    goto LABEL_11;
  v10 = L"OpenProcessToken";
LABEL_7:
  v11 = LastError;
LABEL_8:
  Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"GetCurrentUserTokenInfo", v10, v11);
LABEL_25:
  if ( v6 > 0 )
    v13 = (unsigned __int16)v6 | 0x80070000;
  else
    v13 = v6;
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  SafeFree(v3);
  return v13;
}

```

## disassembly

```asm
0x18001c9b4  mov     rax, rsp
0x18001c9b7  mov     [rax+8], rbx
0x18001c9bb  mov     [rax+18h], r8
0x18001c9bf  push    rsi
0x18001c9c0  push    rdi
0x18001c9c1  push    r14
0x18001c9c3  sub     rsp, 30h
0x18001c9c7  xor     esi, esi
0x18001c9c9  mov     qword ptr [rax+10h], 0
0x18001c9d1  mov     [rax+18h], esi
0x18001c9d4  mov     r14, rdx
0x18001c9d7  mov     edi, ecx
0x18001c9d9  test    rdx, rdx
0x18001c9dc  jz      loc_18001CB2B
0x18001c9e2  xor     ebx, ebx
0x18001c9e4  mov     [rdx], rbx
0x18001c9e7  call    cs:__imp_GetCurrentThread
0x18001c9ed  mov     rcx, rax; ThreadHandle
0x18001c9f0  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18001c9f5  lea     edx, [rsi+8]; DesiredAccess
0x18001c9f8  lea     r8d, [rsi+1]; OpenAsSelf
0x18001c9fc  call    cs:__imp_OpenThreadToken
0x18001ca02  test    eax, eax
0x18001ca04  jnz     short loc_18001CA6D
0x18001ca06  call    cs:__imp_GetLastError
0x18001ca0c  mov     ebx, eax
0x18001ca0e  cmp     eax, 3F0h
0x18001ca13  jnz     short loc_18001CA60
0x18001ca15  xor     ebx, ebx
0x18001ca17  call    cs:__imp_GetCurrentProcess
0x18001ca1d  mov     rcx, rax; ProcessHandle
0x18001ca20  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18001ca25  lea     edx, [rsi+8]; DesiredAccess
0x18001ca28  call    cs:__imp_OpenProcessToken
0x18001ca2e  test    eax, eax
0x18001ca30  jnz     short loc_18001CA6D
0x18001ca32  call    cs:__imp_GetLastError
0x18001ca38  mov     ebx, eax
0x18001ca3a  test    eax, eax
0x18001ca3c  jz      short loc_18001CA6D
0x18001ca3e  lea     r8, aOpenprocesstok; "OpenProcessToken"
0x18001ca45  mov     r9d, eax
0x18001ca48  lea     rdx, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x18001ca4f  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001ca56  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001ca5b  jmp     loc_18001CB18
0x18001ca60  test    eax, eax
0x18001ca62  jz      short loc_18001CA6D
0x18001ca64  lea     r8, aOpenthreadtoke; "OpenThreadToken"
0x18001ca6b  jmp     short loc_18001CA45
0x18001ca6d  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18001ca72  lea     rax, [rsp+48h+TokenInformationLength]
0x18001ca77  xor     r9d, r9d; TokenInformationLength
0x18001ca7a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001ca7f  xor     r8d, r8d; TokenInformation
0x18001ca82  mov     edx, edi; TokenInformationClass
0x18001ca84  call    cs:__imp_GetTokenInformation
0x18001ca8a  test    eax, eax
0x18001ca8c  jnz     short loc_18001CAAE
0x18001ca8e  call    cs:__imp_GetLastError
0x18001ca94  xor     ebx, ebx
0x18001ca96  cmp     eax, 7Ah ; 'z'
0x18001ca99  cmovnz  ebx, eax
0x18001ca9c  test    ebx, ebx
0x18001ca9e  jz      short loc_18001CAAC
0x18001caa0  mov     r9d, ebx
0x18001caa3  lea     r8, aGettokeninform; "GetTokenInformation"
0x18001caaa  jmp     short loc_18001CA48
0x18001caac  xor     ebx, ebx
0x18001caae  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18001cab2  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18001cab7  mov     rsi, rax
0x18001caba  test    rax, rax
0x18001cabd  jnz     short loc_18001CAD9
0x18001cabf  lea     rdx, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x18001cac6  mov     edi, 8007000Eh
0x18001cacb  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18001cad2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18001cad7  jmp     short loc_18001CB14
0x18001cad9  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001cade  lea     rax, [rsp+48h+TokenInformationLength]
0x18001cae3  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18001cae8  mov     r8, rsi; TokenInformation
0x18001caeb  mov     edx, edi; TokenInformationClass
0x18001caed  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001caf2  call    cs:__imp_GetTokenInformation
0x18001caf8  test    eax, eax
0x18001cafa  jnz     short loc_18001CB0D
0x18001cafc  call    cs:__imp_GetLastError
0x18001cb02  mov     ebx, eax
0x18001cb04  test    eax, eax
0x18001cb06  jz      short loc_18001CB0D
0x18001cb08  mov     r9d, eax
0x18001cb0b  jmp     short loc_18001CAA3
0x18001cb0d  xor     edi, edi
0x18001cb0f  mov     [r14], rsi
0x18001cb12  xor     esi, esi
0x18001cb14  test    ebx, ebx
0x18001cb16  jz      short loc_18001CB5D
0x18001cb18  test    ebx, ebx
0x18001cb1a  jg      short loc_18001CB20
0x18001cb1c  mov     edi, ebx
0x18001cb1e  jmp     short loc_18001CB5D
0x18001cb20  movzx   edi, bx
0x18001cb23  or      edi, 80070000h
0x18001cb29  jmp     short loc_18001CB5D
0x18001cb2b  lea     r8, aPpinfo; "ppInfo"
0x18001cb32  mov     edi, 80070057h
0x18001cb37  lea     rdx, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x18001cb3e  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18001cb45  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001cb4a  lea     rdx, aPpinfo; "ppInfo"
0x18001cb51  lea     rcx, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x18001cb58  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001cb5d  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18001cb62  test    rcx, rcx
0x18001cb65  jz      short loc_18001CB6D
0x18001cb67  call    cs:__imp_CloseHandle
0x18001cb6d  mov     rcx, rsi; lpMem
0x18001cb70  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18001cb75  mov     rbx, [rsp+48h+arg_0]
0x18001cb7a  mov     eax, edi
0x18001cb7c  add     rsp, 30h
0x18001cb80  pop     r14
0x18001cb82  pop     rdi
0x18001cb83  pop     rsi
0x18001cb84  retn
```
