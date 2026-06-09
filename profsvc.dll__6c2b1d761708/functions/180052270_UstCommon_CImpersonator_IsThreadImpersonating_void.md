# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x180052270`
- end: `0x1800523c8`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `344`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800362dc`

## callees

- `0x1800084bc`
- `0x18001a680`
- `0x180052270`
- `0x18005245c`
- `0x1800524a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005232c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005232c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052351`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800522b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800522b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052295`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800522f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800522f7`

## pseudocode

```c
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  _QWORD *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  const wchar_t *v9; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  TokenHandle = 0;
  v1 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    LastError = GetLastError();
    v7 = 15;
    goto LABEL_10;
  }
  LODWORD(TokenInformation) = 0;
  ReturnLength = 0;
  v3 = GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  v4 = WPP_GLOBAL_Control;
  if ( v3 )
  {
    v1 = (unsigned int)((_DWORD)TokenInformation - 2) <= 1;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v7 = 14;
LABEL_10:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v6, LastError);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    v8 = v4[2];
    v9 = L"YES";
    if ( !v1 )
      v9 = L"NO";
    WPP_SF_S(v8, 16, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v9);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180052270  mov     rax, rsp
0x180052273  mov     [rax+20h], rbx
0x180052277  mov     [rax+8], rcx
0x18005227b  push    rbp
0x18005227c  sub     rsp, 30h
0x180052280  xor     edx, edx
0x180052282  mov     qword ptr [rax+18h], 0
0x18005228a  lea     rcx, [rax+18h]
0x18005228e  xor     bl, bl
0x180052290  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180052295  call    cs:__imp_GetCurrentThread
0x18005229c  nop     dword ptr [rax+rax+00h]
0x1800522a1  mov     edx, 8; DesiredAccess
0x1800522a6  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800522ab  mov     rcx, rax; ThreadHandle
0x1800522ae  lea     r8d, [rdx-7]; OpenAsSelf
0x1800522b2  call    cs:__imp_OpenThreadToken
0x1800522b9  nop     dword ptr [rax+rax+00h]
0x1800522be  lea     rbp, WPP_GLOBAL_Control
0x1800522c5  test    eax, eax
0x1800522c7  jz      short loc_18005233F
0x1800522c9  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800522ce  lea     rax, [rsp+38h+arg_8]
0x1800522d3  mov     r9d, 4; TokenInformationLength
0x1800522d9  mov     dword ptr [rsp+38h+TokenInformation], 0
0x1800522e1  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800522e6  mov     [rsp+38h+arg_8], 0
0x1800522ee  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800522f3  lea     edx, [r9+5]; TokenInformationClass
0x1800522f7  call    cs:__imp_GetTokenInformation
0x1800522fe  nop     dword ptr [rax+rax+00h]
0x180052303  mov     rcx, cs:WPP_GLOBAL_Control
0x18005230a  test    eax, eax
0x18005230c  jz      short loc_18005231D
0x18005230e  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x180052312  add     eax, 0FFFFFFFEh
0x180052315  cmp     eax, 1
0x180052318  setbe   bl
0x18005231b  jmp     short loc_18005237C
0x18005231d  cmp     rcx, rbp
0x180052320  jz      loc_1800523B0
0x180052326  test    byte ptr [rcx+1Ch], 2
0x18005232a  jz      short loc_18005237C
0x18005232c  call    cs:__imp_GetLastError
0x180052333  nop     dword ptr [rax+rax+00h]
0x180052338  mov     edx, 0Eh
0x18005233d  jmp     short loc_180052362
0x18005233f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052346  cmp     rcx, rbp
0x180052349  jz      short loc_1800523B0
0x18005234b  test    byte ptr [rcx+1Ch], 2
0x18005234f  jz      short loc_18005237C
0x180052351  call    cs:__imp_GetLastError
0x180052358  nop     dword ptr [rax+rax+00h]
0x18005235d  mov     edx, 0Fh
0x180052362  mov     rcx, cs:WPP_GLOBAL_Control
0x180052369  mov     r9d, eax
0x18005236c  mov     rcx, [rcx+10h]
0x180052370  call    WPP_SF_D
0x180052375  mov     rcx, cs:WPP_GLOBAL_Control
0x18005237c  cmp     rcx, rbp
0x18005237f  jz      short loc_1800523B0
0x180052381  test    byte ptr [rcx+1Ch], 2
0x180052385  jz      short loc_1800523B0
0x180052387  mov     rcx, [rcx+10h]
0x18005238b  lea     rax, aNo; "NO"
0x180052392  test    bl, bl
0x180052394  lea     r9, aYes; "YES"
0x18005239b  mov     edx, 10h
0x1800523a0  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x1800523a7  cmovz   r9, rax
0x1800523ab  call    WPP_SF_S
0x1800523b0  lea     rcx, [rsp+38h+TokenHandle]
0x1800523b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800523ba  mov     al, bl
0x1800523bc  mov     rbx, [rsp+38h+arg_18]
0x1800523c1  add     rsp, 30h
0x1800523c5  pop     rbp
0x1800523c6  retn
```
