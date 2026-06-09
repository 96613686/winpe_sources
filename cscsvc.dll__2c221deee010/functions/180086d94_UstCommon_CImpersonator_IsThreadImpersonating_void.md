# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x180086d94`
- end: `0x180086eca`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `310`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008674c`

## callees

- `0x180036394`
- `0x18003c488`
- `0x180085d94`
- `0x180086d94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086e52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086dae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180086dae`
- `ADVAPI32!OpenThreadToken` at `0x180086dc5`
- `ADVAPI32!OpenThreadToken` at `0x180086dc5`
- `ADVAPI32!GetTokenInformation` at `0x180086e04`
- `ADVAPI32!GetTokenInformation` at `0x180086e04`

## pseudocode

```c
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  CObjectMonitor *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  v1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_11;
    LastError = GetLastError();
    v6 = 15;
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
  if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    v6 = 14;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_313c576492293c0704086ae70e07ed75_Traceguids, LastError);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( v4 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    v7 = L"YES";
    if ( !v1 )
      v7 = L"NO";
    WPP_SF_S(*((_QWORD *)v4 + 2), 16, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v7);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180086d94  mov     [rsp+arg_18], rbx
0x180086d99  mov     [rsp+TokenInformation], rcx
0x180086d9e  push    rbp
0x180086d9f  sub     rsp, 30h
0x180086da3  xor     bl, bl
0x180086da5  mov     [rsp+38h+TokenHandle], 0
0x180086dae  call    cs:__imp_GetCurrentThread
0x180086db4  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180086db9  mov     edx, 8; DesiredAccess
0x180086dbe  lea     r8d, [rdx-7]; OpenAsSelf
0x180086dc2  mov     rcx, rax; ThreadHandle
0x180086dc5  call    cs:__imp_OpenThreadToken
0x180086dcb  lea     rbp, WPP_GLOBAL_Control
0x180086dd2  test    eax, eax
0x180086dd4  jz      short loc_180086E40
0x180086dd6  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180086dde  mov     [rsp+38h+arg_8], 0
0x180086de6  lea     rax, [rsp+38h+arg_8]
0x180086deb  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180086df0  mov     r9d, 4; TokenInformationLength
0x180086df6  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180086dfb  lea     edx, [r9+5]; TokenInformationClass
0x180086dff  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180086e04  call    cs:__imp_GetTokenInformation
0x180086e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e11  test    eax, eax
0x180086e13  jz      short loc_180086E24
0x180086e15  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x180086e19  add     eax, 0FFFFFFFEh
0x180086e1c  cmp     eax, 1
0x180086e1f  setbe   bl
0x180086e22  jmp     short loc_180086E7E
0x180086e24  cmp     rcx, rbp
0x180086e27  jz      loc_180086EB3
0x180086e2d  test    byte ptr [rcx+1Ch], 2
0x180086e31  jz      short loc_180086E7E
0x180086e33  call    cs:__imp_GetLastError
0x180086e39  mov     edx, 0Eh
0x180086e3e  jmp     short loc_180086E5D
0x180086e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e47  cmp     rcx, rbp
0x180086e4a  jz      short loc_180086EB3
0x180086e4c  test    byte ptr [rcx+1Ch], 2
0x180086e50  jz      short loc_180086E7E
0x180086e52  call    cs:__imp_GetLastError
0x180086e58  mov     edx, 0Fh
0x180086e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e64  mov     r9d, eax
0x180086e67  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180086e6e  mov     rcx, [rcx+10h]
0x180086e72  call    WPP_SF_d
0x180086e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e7e  cmp     rcx, rbp
0x180086e81  jz      short loc_180086EB3
0x180086e83  test    byte ptr [rcx+1Ch], 2
0x180086e87  jz      short loc_180086EB3
0x180086e89  lea     rax, aNo_0; "NO"
0x180086e90  lea     r9, aYes; "YES"
0x180086e97  test    bl, bl
0x180086e99  cmovz   r9, rax
0x180086e9d  mov     edx, 10h
0x180086ea2  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180086ea9  mov     rcx, [rcx+10h]
0x180086ead  call    WPP_SF_S
0x180086eb2  nop
0x180086eb3  lea     rcx, [rsp+38h+TokenHandle]
0x180086eb8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086ebd  mov     al, bl
0x180086ebf  mov     rbx, [rsp+38h+arg_18]
0x180086ec4  add     rsp, 30h
0x180086ec8  pop     rbp
0x180086ec9  retn
```
