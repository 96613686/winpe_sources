# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::ValidateCapability(ushort const *)

- ea: `0x18004ee68`
- end: `0x18004ef9e`
- name: `?ValidateCapability@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CAXPEBG@Z`
- size: `310`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d580`
- `0x18004d8d0`

## callees

- `0x1800125f4`
- `0x180017aa4`
- `0x1800210fc`
- `0x180021118`
- `0x18004ee68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eea6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004eec1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004eec1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef36`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004eedf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004eedf`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004ee72`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004ee72`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004ef01`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004ef01`

## pseudocode

```c
void __fastcall Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::ValidateCapability(
        const unsigned __int16 *a1)
{
  HRESULT v1; // eax
  void **v2; // rbx
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  int v5; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  const unsigned __int16 *v8; // [rsp+30h] [rbp+8h] BYREF
  char v9; // [rsp+39h] [rbp+11h]
  HANDLE hObject; // [rsp+40h] [rbp+18h] BYREF

  v8 = a1;
  v1 = CoImpersonateClient();
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v1,
      v6);
  v9 = 1;
  hObject = 0;
  v2 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, v2) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      v4);
  v9 = 0;
  CoRevertToSelf();
  LOBYTE(v8) = 0;
  v5 = CapabilityCheck(hObject, L"runFullTrust", &v8);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)(unsigned int)v5,
      v6);
  if ( !(_BYTE)v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fulltrustprocesslauncher.cpp",
      (const char *)0x80070005LL,
      v6);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18004ee68  mov     [rsp+arg_0], rcx
0x18004ee6d  push    rbx; int
0x18004ee6e  sub     rsp, 20h
0x18004ee72  call    cs:__imp_CoImpersonateClient
0x18004ee79  nop     dword ptr [rax+rax+00h]
0x18004ee7e  mov     rcx, [rsp+28h]; this
0x18004ee83  test    eax, eax
0x18004ee85  js      loc_18004EF62
0x18004ee8b  mov     [rsp+28h+arg_9], 1
0x18004ee90  mov     [rsp+28h+hObject], 0
0x18004ee99  lea     rcx, [rsp+28h+hObject]
0x18004ee9e  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18004eea3  mov     rbx, rax
0x18004eea6  call    cs:__imp_GetCurrentThread
0x18004eead  nop     dword ptr [rax+rax+00h]
0x18004eeb2  mov     r9, rbx; TokenHandle
0x18004eeb5  mov     edx, 8; DesiredAccess
0x18004eeba  lea     r8d, [rdx-7]; OpenAsSelf
0x18004eebe  mov     rcx, rax; ThreadHandle
0x18004eec1  call    cs:__imp_OpenThreadToken
0x18004eec8  nop     dword ptr [rax+rax+00h]
0x18004eecd  mov     rcx, [rsp+28h]; this
0x18004eed2  test    eax, eax
0x18004eed4  jz      loc_18004EF77
0x18004eeda  mov     [rsp+28h+arg_9], 0
0x18004eedf  call    cs:__imp_CoRevertToSelf
0x18004eee6  nop     dword ptr [rax+rax+00h]
0x18004eeeb  mov     byte ptr [rsp+28h+arg_0], 0
0x18004eef0  lea     r8, [rsp+28h+arg_0]
0x18004eef5  lea     rdx, aRunfulltrust; "runFullTrust"
0x18004eefc  mov     rcx, [rsp+28h+hObject]
0x18004ef01  call    cs:__imp_CapabilityCheck
0x18004ef08  nop     dword ptr [rax+rax+00h]
0x18004ef0d  mov     rcx, [rsp+28h]; this
0x18004ef12  test    eax, eax
0x18004ef14  js      short loc_18004EF89
0x18004ef16  cmp     byte ptr [rsp+28h+arg_0], 0
0x18004ef1b  setnz   al
0x18004ef1e  mov     rcx, [rsp+28h]; this
0x18004ef23  test    al, al
0x18004ef25  jz      short loc_18004EF4A
0x18004ef27  mov     rcx, [rsp+28h+hObject]; hObject
0x18004ef2c  lea     rax, [rcx-1]
0x18004ef30  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ef34  ja      short loc_18004EF43
0x18004ef36  call    cs:__imp_CloseHandle
0x18004ef3d  nop     dword ptr [rax+rax+00h]
0x18004ef42  nop
0x18004ef43  add     rsp, 20h
0x18004ef47  pop     rbx
0x18004ef48  retn
0x18004ef4a  mov     r9d, 80070005h; char *
0x18004ef50  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ef57  mov     edx, 0CBh; void *
0x18004ef5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ef62  mov     r9d, eax; char *
0x18004ef65  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ef6c  mov     edx, 0BDh; void *
0x18004ef71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ef77  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ef7e  mov     edx, 0C4h; void *
0x18004ef83  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004ef89  mov     r9d, eax; char *
0x18004ef8c  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004ef93  mov     edx, 0C9h; void *
0x18004ef98  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
