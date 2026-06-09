# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x18004ef50`
- end: `0x18004f085`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `309`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035d5c`

## callees

- `0x18000a9b8`
- `0x180016e00`
- `0x18004ef50`
- `0x18004f108`
- `0x18004f14c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f015`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ef8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ef8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ef75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ef75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004efcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004efcb`

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
0x18004ef50  mov     rax, rsp
0x18004ef53  mov     [rax+20h], rbx
0x18004ef57  mov     [rax+8], rcx
0x18004ef5b  push    rbp
0x18004ef5c  sub     rsp, 30h
0x18004ef60  xor     edx, edx
0x18004ef62  mov     qword ptr [rax+18h], 0
0x18004ef6a  lea     rcx, [rax+18h]
0x18004ef6e  xor     bl, bl
0x18004ef70  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004ef75  call    cs:__imp_GetCurrentThread
0x18004ef7b  mov     edx, 8; DesiredAccess
0x18004ef80  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004ef85  mov     rcx, rax; ThreadHandle
0x18004ef88  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ef8c  call    cs:__imp_OpenThreadToken
0x18004ef92  lea     rbp, WPP_GLOBAL_Control
0x18004ef99  test    eax, eax
0x18004ef9b  jz      short loc_18004F003
0x18004ef9d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18004efa2  lea     rax, [rsp+38h+arg_8]
0x18004efa7  mov     r9d, 4; TokenInformationLength
0x18004efad  mov     dword ptr [rsp+38h+TokenInformation], 0
0x18004efb5  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004efba  mov     [rsp+38h+arg_8], 0
0x18004efc2  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004efc7  lea     edx, [r9+5]; TokenInformationClass
0x18004efcb  call    cs:__imp_GetTokenInformation
0x18004efd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004efd8  test    eax, eax
0x18004efda  jz      short loc_18004EFEB
0x18004efdc  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x18004efe0  add     eax, 0FFFFFFFEh
0x18004efe3  cmp     eax, 1
0x18004efe6  setbe   bl
0x18004efe9  jmp     short loc_18004F03A
0x18004efeb  cmp     rcx, rbp
0x18004efee  jz      short loc_18004F06E
0x18004eff0  test    byte ptr [rcx+1Ch], 2
0x18004eff4  jz      short loc_18004F03A
0x18004eff6  call    cs:__imp_GetLastError
0x18004effc  mov     edx, 0Eh
0x18004f001  jmp     short loc_18004F020
0x18004f003  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f00a  cmp     rcx, rbp
0x18004f00d  jz      short loc_18004F06E
0x18004f00f  test    byte ptr [rcx+1Ch], 2
0x18004f013  jz      short loc_18004F03A
0x18004f015  call    cs:__imp_GetLastError
0x18004f01b  mov     edx, 0Fh
0x18004f020  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f027  mov     r9d, eax
0x18004f02a  mov     rcx, [rcx+10h]
0x18004f02e  call    WPP_SF_D
0x18004f033  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f03a  cmp     rcx, rbp
0x18004f03d  jz      short loc_18004F06E
0x18004f03f  test    byte ptr [rcx+1Ch], 2
0x18004f043  jz      short loc_18004F06E
0x18004f045  mov     rcx, [rcx+10h]
0x18004f049  lea     rax, aNo; "NO"
0x18004f050  test    bl, bl
0x18004f052  lea     r9, aYes; "YES"
0x18004f059  mov     edx, 10h
0x18004f05e  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x18004f065  cmovz   r9, rax
0x18004f069  call    WPP_SF_S
0x18004f06e  lea     rcx, [rsp+38h+TokenHandle]
0x18004f073  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f078  mov     al, bl
0x18004f07a  mov     rbx, [rsp+38h+arg_18]
0x18004f07f  add     rsp, 30h
0x18004f083  pop     rbp
0x18004f084  retn
```
