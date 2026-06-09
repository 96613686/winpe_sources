# Windows::ApplicationModel::Internal::FullTrustProcessLauncherInternal::ValidateCapability(ushort const *)

- ea: `0x18004d20c`
- end: `0x18004d33f`
- name: `?ValidateCapability@FullTrustProcessLauncherInternal@Internal@ApplicationModel@Windows@@CAXPEBG@Z`
- size: `307`
- prototype: `static void(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ba10`
- `0x18004bd60`

## callees

- `0x180010a84`
- `0x180015ec8`
- `0x18002031c`
- `0x180020338`
- `0x18004d20c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d262`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004d262`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d247`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004d247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d2d7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004d216`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18004d216`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004d280`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004d280`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004d2a2`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004d2a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18004d20c  mov     [rsp+arg_0], rcx
0x18004d211  push    rbx; int
0x18004d212  sub     rsp, 20h
0x18004d216  call    cs:__imp_CoImpersonateClient
0x18004d21d  nop     dword ptr [rax+rax+00h]
0x18004d222  mov     rcx, [rsp+28h]; this
0x18004d227  test    eax, eax
0x18004d229  js      loc_18004D303
0x18004d22f  mov     [rsp+28h+arg_9], 1
0x18004d234  and     [rsp+28h+hObject], 0
0x18004d23a  lea     rcx, [rsp+28h+hObject]
0x18004d23f  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18004d244  mov     rbx, rax
0x18004d247  call    cs:__imp_GetCurrentThread
0x18004d24e  nop     dword ptr [rax+rax+00h]
0x18004d253  mov     r9, rbx; TokenHandle
0x18004d256  mov     edx, 8; DesiredAccess
0x18004d25b  lea     r8d, [rdx-7]; OpenAsSelf
0x18004d25f  mov     rcx, rax; ThreadHandle
0x18004d262  call    cs:__imp_OpenThreadToken
0x18004d269  nop     dword ptr [rax+rax+00h]
0x18004d26e  mov     rcx, [rsp+28h]; this
0x18004d273  test    eax, eax
0x18004d275  jz      loc_18004D318
0x18004d27b  mov     [rsp+28h+arg_9], 0
0x18004d280  call    cs:__imp_CoRevertToSelf
0x18004d287  nop     dword ptr [rax+rax+00h]
0x18004d28c  mov     byte ptr [rsp+28h+arg_0], 0
0x18004d291  lea     r8, [rsp+28h+arg_0]
0x18004d296  lea     rdx, aRunfulltrust; "runFullTrust"
0x18004d29d  mov     rcx, [rsp+28h+hObject]
0x18004d2a2  call    cs:__imp_CapabilityCheck
0x18004d2a9  nop     dword ptr [rax+rax+00h]
0x18004d2ae  mov     rcx, [rsp+28h]; this
0x18004d2b3  test    eax, eax
0x18004d2b5  js      short loc_18004D32A
0x18004d2b7  cmp     byte ptr [rsp+28h+arg_0], 0
0x18004d2bc  setnz   al
0x18004d2bf  mov     rcx, [rsp+28h]; this
0x18004d2c4  test    al, al
0x18004d2c6  jz      short loc_18004D2EB
0x18004d2c8  mov     rcx, [rsp+28h+hObject]; hObject
0x18004d2cd  lea     rax, [rcx-1]
0x18004d2d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d2d5  ja      short loc_18004D2E4
0x18004d2d7  call    cs:__imp_CloseHandle
0x18004d2de  nop     dword ptr [rax+rax+00h]
0x18004d2e3  nop
0x18004d2e4  add     rsp, 20h
0x18004d2e8  pop     rbx
0x18004d2e9  retn
0x18004d2eb  mov     r9d, 80070005h; char *
0x18004d2f1  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d2f8  mov     edx, 0CBh; void *
0x18004d2fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d303  mov     r9d, eax; char *
0x18004d306  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d30d  mov     edx, 0BDh; void *
0x18004d312  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004d318  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d31f  mov     edx, 0C4h; void *
0x18004d324  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004d32a  mov     r9d, eax; char *
0x18004d32d  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18004d334  mov     edx, 0C9h; void *
0x18004d339  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
