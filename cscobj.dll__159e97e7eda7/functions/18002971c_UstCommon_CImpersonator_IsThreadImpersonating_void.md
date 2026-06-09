# UstCommon::CImpersonator::_IsThreadImpersonating(void)

- ea: `0x18002971c`
- end: `0x180029852`
- name: `?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ`
- size: `310`
- prototype: `bool __fastcall(UstCommon::CImpersonator *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800289d4`

## callees

- `0x18000f5cc`
- `0x180014068`
- `0x180027fac`
- `0x18002971c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002978c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002978c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180029736`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002974d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002974d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall UstCommon::CImpersonator::_IsThreadImpersonating(UstCommon::CImpersonator *this)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  BOOL v3; // eax
  __int64 v4; // rcx
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
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
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
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    LastError = GetLastError();
    v6 = 14;
LABEL_10:
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v6, WPP_313c576492293c0704086ae70e07ed75_Traceguids, LastError);
    v4 = WPP_GLOBAL_Control;
  }
LABEL_11:
  if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 2) != 0 )
  {
    v7 = L"YES";
    if ( !v1 )
      v7 = L"NO";
    WPP_SF_S(*(_QWORD *)(v4 + 16), 16, WPP_313c576492293c0704086ae70e07ed75_Traceguids, v7);
  }
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18002971c  mov     [rsp+arg_18], rbx
0x180029721  mov     [rsp+TokenInformation], rcx
0x180029726  push    rbp
0x180029727  sub     rsp, 30h
0x18002972b  xor     bl, bl
0x18002972d  mov     [rsp+38h+TokenHandle], 0
0x180029736  call    cs:__imp_GetCurrentThread
0x18002973c  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180029741  mov     edx, 8; DesiredAccess
0x180029746  lea     r8d, [rdx-7]; OpenAsSelf
0x18002974a  mov     rcx, rax; ThreadHandle
0x18002974d  call    cs:__imp_OpenThreadToken
0x180029753  lea     rbp, WPP_GLOBAL_Control
0x18002975a  test    eax, eax
0x18002975c  jz      short loc_1800297C8
0x18002975e  mov     dword ptr [rsp+38h+TokenInformation], 0
0x180029766  mov     [rsp+38h+arg_8], 0
0x18002976e  lea     rax, [rsp+38h+arg_8]
0x180029773  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180029778  mov     r9d, 4; TokenInformationLength
0x18002977e  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180029783  lea     edx, [r9+5]; TokenInformationClass
0x180029787  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18002978c  call    cs:__imp_GetTokenInformation
0x180029792  mov     rcx, cs:WPP_GLOBAL_Control
0x180029799  test    eax, eax
0x18002979b  jz      short loc_1800297AC
0x18002979d  mov     eax, dword ptr [rsp+38h+TokenInformation]
0x1800297a1  add     eax, 0FFFFFFFEh
0x1800297a4  cmp     eax, 1
0x1800297a7  setbe   bl
0x1800297aa  jmp     short loc_180029806
0x1800297ac  cmp     rcx, rbp
0x1800297af  jz      loc_18002983B
0x1800297b5  test    byte ptr [rcx+1Ch], 2
0x1800297b9  jz      short loc_180029806
0x1800297bb  call    cs:__imp_GetLastError
0x1800297c1  mov     edx, 0Eh
0x1800297c6  jmp     short loc_1800297E5
0x1800297c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297cf  cmp     rcx, rbp
0x1800297d2  jz      short loc_18002983B
0x1800297d4  test    byte ptr [rcx+1Ch], 2
0x1800297d8  jz      short loc_180029806
0x1800297da  call    cs:__imp_GetLastError
0x1800297e0  mov     edx, 0Fh
0x1800297e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297ec  mov     r9d, eax
0x1800297ef  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x1800297f6  mov     rcx, [rcx+10h]
0x1800297fa  call    WPP_SF_d
0x1800297ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180029806  cmp     rcx, rbp
0x180029809  jz      short loc_18002983B
0x18002980b  test    byte ptr [rcx+1Ch], 2
0x18002980f  jz      short loc_18002983B
0x180029811  lea     rax, aNo; "NO"
0x180029818  lea     r9, aYes; "YES"
0x18002981f  test    bl, bl
0x180029821  cmovz   r9, rax
0x180029825  mov     edx, 10h
0x18002982a  lea     r8, WPP_313c576492293c0704086ae70e07ed75_Traceguids
0x180029831  mov     rcx, [rcx+10h]
0x180029835  call    WPP_SF_S
0x18002983a  nop
0x18002983b  lea     rcx, [rsp+38h+TokenHandle]
0x180029840  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180029845  mov     al, bl
0x180029847  mov     rbx, [rsp+38h+arg_18]
0x18002984c  add     rsp, 30h
0x180029850  pop     rbp
0x180029851  retn
```
