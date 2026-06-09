# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x18001ae58`
- end: `0x18001af99`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `321`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800019b0`

## callees

- `0x180011454`
- `0x18001a46c`
- `0x18001ae58`
- `0x18001afc8`
- `0x18001b008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ae7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ae7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ae94`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ae94`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aed3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aed3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  UstCommon::CImpersonator *v4; // rcx
  DWORD LastError; // eax
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  UstCommon::CImpersonator *TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = this;
  v1 = 0;
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
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
  if ( WPP_GLOBAL_Control == (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
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
  if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
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
0x18001ae58  mov     rax, rsp
0x18001ae5b  mov     [rax+20h], rbx
0x18001ae5f  mov     [rax+8], rcx
0x18001ae63  push    rbp
0x18001ae64  sub     rsp, 30h
0x18001ae68  xor     bl, bl
0x18001ae6a  mov     qword ptr [rax+18h], 0
0x18001ae72  xor     edx, edx
0x18001ae74  lea     rcx, [rax+18h]
0x18001ae78  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001ae7d  call    cs:__imp_GetCurrentThread
0x18001ae83  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18001ae88  mov     edx, 8; DesiredAccess
0x18001ae8d  lea     r8d, [rdx-7]; OpenAsSelf
0x18001ae91  mov     rcx, rax; ThreadHandle
0x18001ae94  call    cs:__imp_OpenThreadToken
0x18001ae9a  lea     rbp, WPP_GLOBAL_Control
0x18001aea1  test    eax, eax
0x18001aea3  jz      short loc_18001AF0F
0x18001aea5  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18001aead  mov     [rsp+38h+arg_8], 0
0x18001aeb5  lea     rax, [rsp+38h+arg_8]
0x18001aeba  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18001aebf  mov     r9d, 4; TokenInformationLength
0x18001aec5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18001aeca  lea     edx, [r9+5]; TokenInformationClass
0x18001aece  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18001aed3  call    cs:__imp_GetTokenInformation
0x18001aed9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aee0  test    eax, eax
0x18001aee2  jz      short loc_18001AEF3
0x18001aee4  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x18001aee8  add     eax, 0FFFFFFFEh
0x18001aeeb  cmp     eax, 1
0x18001aeee  setbe   bl
0x18001aef1  jmp     short loc_18001AF4D
0x18001aef3  cmp     rcx, rbp
0x18001aef6  jz      loc_18001AF82
0x18001aefc  test    byte ptr [rcx+1Ch], 2
0x18001af00  jz      short loc_18001AF4D
0x18001af02  call    cs:__imp_GetLastError
0x18001af08  mov     edx, 0Eh
0x18001af0d  jmp     short loc_18001AF2C
0x18001af0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af16  cmp     rcx, rbp
0x18001af19  jz      short loc_18001AF82
0x18001af1b  test    byte ptr [rcx+1Ch], 2
0x18001af1f  jz      short loc_18001AF4D
0x18001af21  call    cs:__imp_GetLastError
0x18001af27  mov     edx, 0Fh
0x18001af2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af33  mov     r9d, eax
0x18001af36  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18001af3d  mov     rcx, [rcx+10h]
0x18001af41  call    WPP_SF_d
0x18001af46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af4d  cmp     rcx, rbp
0x18001af50  jz      short loc_18001AF82
0x18001af52  test    byte ptr [rcx+1Ch], 2
0x18001af56  jz      short loc_18001AF82
0x18001af58  lea     rax, aNo; "NO"
0x18001af5f  lea     r9, aYes; "YES"
0x18001af66  test    bl, bl
0x18001af68  cmovz   r9, rax
0x18001af6c  mov     edx, 10h
0x18001af71  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18001af78  mov     rcx, [rcx+10h]
0x18001af7c  call    WPP_SF_S
0x18001af81  nop
0x18001af82  lea     rcx, [rsp+38h+TokenHandle]
0x18001af87  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001af8c  mov     al, bl
0x18001af8e  mov     rbx, [rsp+38h+arg_18]
0x18001af93  add     rsp, 30h
0x18001af97  pop     rbp
0x18001af98  retn
```
