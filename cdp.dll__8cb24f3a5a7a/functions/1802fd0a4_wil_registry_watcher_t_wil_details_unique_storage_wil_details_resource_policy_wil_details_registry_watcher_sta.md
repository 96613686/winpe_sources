# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1802fd0a4`
- end: `0x1802fd224`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d76e4`

## callees

- `0x1800874fc`
- `0x180087560`
- `0x1800d4e0c`
- `0x180149448`
- `0x18014946c`
- `0x1801fc9fc`
- `0x18023ac94`
- `0x1802fc818`
- `0x1802fcc4c`
- `0x1802fcc78`
- `0x1802fd0a4`
- `0x1802fd280`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1802fd212`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1802fd212`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1802fd192`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1802fd192`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802fd160`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1802fd160`

## string_xrefs

- `0x1802fd0f9`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1802fd12e`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1802fd172`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1802fd1d4`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v12; // edi
  unsigned int v13; // edx
  unsigned int v14; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v17; // r9
  struct _TP_WAIT *v18; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v21[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v21[0] = v7;
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128);
  v12 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_15:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v9, v13);
    return v12;
  }
  v14 = RegNotifyChangeKeyValue(
          *(HKEY *)(v9 + 120),
          *(unsigned __int8 *)(v9 + 144),
          0x10000005u,
          *(HANDLE *)(v9 + 128),
          1);
  if ( v14 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  (const char *)v14,
                  fAsynchronousa);
LABEL_14:
    v12 = LastError;
    goto LABEL_15;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  v18 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v18 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v21);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v18);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v21);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v17);
    goto LABEL_14;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v9);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1802fd0a4  push    rbx
0x1802fd0a6  push    rsi
0x1802fd0a7  push    rdi
0x1802fd0a8  push    r14
0x1802fd0aa  sub     rsp, 48h
0x1802fd0ae  mov     rbx, r9
0x1802fd0b1  mov     rdi, rdx
0x1802fd0b4  mov     r14, rcx
0x1802fd0b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802fd0be  mov     ecx, 0A0h; unsigned __int64
0x1802fd0c3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1802fd0c8  mov     [rsp+68h+var_38], rax
0x1802fd0cd  test    rax, rax
0x1802fd0d0  jz      short loc_1802FD0E5
0x1802fd0d2  mov     r9, rbx
0x1802fd0d5  mov     rdx, rdi
0x1802fd0d8  mov     rcx, rax
0x1802fd0db  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1802fd0e0  mov     rbx, rax
0x1802fd0e3  jmp     short loc_1802FD0E7
0x1802fd0e5  xor     ebx, ebx
0x1802fd0e7  test    rbx, rbx
0x1802fd0ea  jnz     short loc_1802FD111
0x1802fd0ec  mov     rcx, [rsp+68h]; this
0x1802fd0f1  mov     ebx, 8007000Eh
0x1802fd0f6  mov     r9d, ebx; char *
0x1802fd0f9  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802fd100  mov     edx, 0CBBh; void *
0x1802fd105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fd10a  mov     eax, ebx
0x1802fd10c  jmp     loc_1802FD21A
0x1802fd111  lea     rsi, [rbx+80h]
0x1802fd118  mov     rcx, rsi
0x1802fd11b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1802fd120  mov     edi, eax
0x1802fd122  test    eax, eax
0x1802fd124  jns     short loc_1802FD144
0x1802fd126  mov     rcx, [rsp+68h]; this
0x1802fd12b  mov     r9d, eax; char *
0x1802fd12e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802fd135  mov     edx, 0CBCh; void *
0x1802fd13a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802fd13f  jmp     loc_1802FD1E7
0x1802fd144  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x1802fd14b  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1802fd153  mov     r9, [rsi]; hEvent
0x1802fd156  mov     r8d, 10000005h; dwNotifyFilter
0x1802fd15c  mov     rcx, [rbx+78h]; hKey
0x1802fd160  call    cs:__imp_RegNotifyChangeKeyValue
0x1802fd166  test    eax, eax
0x1802fd168  jz      short loc_1802FD185
0x1802fd16a  mov     rcx, [rsp+68h]; this
0x1802fd16f  mov     r9d, eax; char *
0x1802fd172  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802fd179  mov     edx, 0CC2h; void *
0x1802fd17e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802fd183  jmp     short loc_1802FD1E5
0x1802fd185  xor     r8d, r8d; pcbe
0x1802fd188  mov     rdx, rbx; pv
0x1802fd18b  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1802fd192  call    cs:__imp_CreateThreadpoolWait
0x1802fd198  mov     rdi, rax
0x1802fd19b  mov     rsi, [rbx+88h]
0x1802fd1a2  test    rsi, rsi
0x1802fd1a5  jz      short loc_1802FD1C3
0x1802fd1a7  lea     rcx, [rsp+68h+var_38]; this
0x1802fd1ac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1802fd1b1  mov     rcx, rsi; pwa
0x1802fd1b4  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1802fd1b9  lea     rcx, [rsp+68h+var_38]; this
0x1802fd1be  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1802fd1c3  mov     [rbx+88h], rdi
0x1802fd1ca  test    rdi, rdi
0x1802fd1cd  jnz     short loc_1802FD1F3
0x1802fd1cf  mov     rcx, [rsp+68h]; this
0x1802fd1d4  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1802fd1db  mov     edx, 0CC5h; void *
0x1802fd1e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802fd1e5  mov     edi, eax
0x1802fd1e7  mov     rcx, rbx; this
0x1802fd1ea  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1802fd1ef  mov     eax, edi
0x1802fd1f1  jmp     short loc_1802FD21A
0x1802fd1f3  mov     rdx, rbx
0x1802fd1f6  mov     rcx, r14
0x1802fd1f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1802fd1fe  mov     rcx, [r14]
0x1802fd201  xor     r8d, r8d; pftTimeout
0x1802fd204  mov     rdx, [rcx+80h]; h
0x1802fd20b  mov     rcx, [rcx+88h]; pwa
0x1802fd212  call    cs:__imp_SetThreadpoolWait
0x1802fd218  xor     eax, eax
0x1802fd21a  add     rsp, 48h
0x1802fd21e  pop     r14
0x1802fd220  pop     rdi
0x1802fd221  pop     rsi
0x1802fd222  pop     rbx
0x1802fd223  retn
```
