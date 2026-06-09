# CUserProfileService::_StopService(void)

- ea: `0x1800374bc`
- end: `0x18003753e`
- name: `?_StopService@CUserProfileService@@AEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CUserProfileService *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180037214`

## callees

- `0x18002729c`
- `0x180027c64`
- `0x1800374bc`
- `0x18003d678`
- `0x18004b1bc`
- `0x18004efe0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003751f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18003751f`
- `ext-ms-win-profile-profsvc-l1-1-0!StopRoamingClassFactories` at `0x1800374db`
- `ext-ms-win-profile-profsvc-l1-1-0!StopRoamingClassFactories` at `0x1800374db`

## pseudocode

```c
__int64 __fastcall CUserProfileService::_StopService(struct _TP_CLEANUP_GROUP **this)
{
  __int64 v2; // rcx
  unsigned int v3; // edx
  struct _TP_CLEANUP_GROUP *v4; // rcx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  wil::EnterCriticalSection(&v6, this);
  if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v2) )
    StopRoamingClassFactories();
  CUserProfileManager::Uninitialize((CUserProfileManager *)g_pProfMgr);
  if ( g_pProfMgr )
    CUserProfileManager::`scalar deleting destructor'((CUserProfileManager *)g_pProfMgr, v3);
  v4 = this[7];
  g_pProfMgr = 0;
  if ( v4 )
    CloseThreadpoolCleanupGroupMembers(v4, 1, 0);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v6);
  return 0;
}

```

## disassembly

```asm
0x1800374bc  push    rbx
0x1800374be  sub     rsp, 20h
0x1800374c2  mov     rbx, rcx
0x1800374c5  mov     rdx, rcx
0x1800374c8  lea     rcx, [rsp+28h+arg_0]
0x1800374cd  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800374d2  call    IsWaitForNetworkForRoamingProfilePresent
0x1800374d7  test    al, al
0x1800374d9  jz      short loc_1800374E7
0x1800374db  call    cs:__imp_StopRoamingClassFactories
0x1800374e2  nop     dword ptr [rax+rax+00h]
0x1800374e7  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; this
0x1800374ee  call    ?Uninitialize@CUserProfileManager@@QEAAXXZ; CUserProfileManager::Uninitialize(void)
0x1800374f3  mov     rcx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; this
0x1800374fa  test    rcx, rcx
0x1800374fd  jz      short loc_180037504
0x1800374ff  call    ??_GCUserProfileManager@@QEAAPEAXI@Z; CUserProfileManager::`scalar deleting destructor'(uint)
0x180037504  mov     rcx, [rbx+38h]; ptpcg
0x180037508  mov     cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA, 0; CUserProfileManager * g_pProfMgr
0x180037513  test    rcx, rcx
0x180037516  jz      short loc_18003752B
0x180037518  xor     r8d, r8d; pvCleanupContext
0x18003751b  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18003751f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180037526  nop     dword ptr [rax+rax+00h]
0x18003752b  lea     rcx, [rsp+28h+arg_0]
0x180037530  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180037535  xor     eax, eax
0x180037537  add     rsp, 20h
0x18003753b  pop     rbx
0x18003753c  retn
```
