# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800cb104`
- end: `0x1800cb268`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d30a4`

## callees

- `0x18007dc50`
- `0x180081130`
- `0x18008daac`
- `0x18008ead4`
- `0x1800cb104`
- `0x1800cb270`
- `0x1800f2448`
- `0x1801176c4`
- `0x1801b447c`
- `0x1801b6fdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800cb1c2`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800cb1c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800cb1f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800cb1f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800cb256`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800cb256`

## string_xrefs

- `0x1800cb159`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800cb190`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800cb1d4`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800cb217`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

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
  __int64 v9; // rdi
  unsigned int v10; // ebx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v13; // edx
  unsigned int v14; // eax
  unsigned int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v17; // r9
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v7 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v7 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state(v7, a2, v8, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return v10;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v9 + 128, 0);
  v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      fAsynchronous);
LABEL_14:
    wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v9, v13);
    return v10;
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
LABEL_13:
    v10 = LastError;
    goto LABEL_14;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                     (PVOID)v9,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 136,
    ThreadpoolWait);
  if ( !*(_QWORD *)(v9 + 136) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
                  v17);
    goto LABEL_13;
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
0x1800cb104  push    rbx
0x1800cb106  push    rsi
0x1800cb107  push    rdi
0x1800cb108  push    r14
0x1800cb10a  sub     rsp, 48h
0x1800cb10e  mov     rbx, r9
0x1800cb111  mov     rdi, rdx
0x1800cb114  mov     r14, rcx
0x1800cb117  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cb11e  mov     ecx, 0A0h; unsigned __int64
0x1800cb123  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800cb128  mov     [rsp+68h+var_38], rax
0x1800cb12d  test    rax, rax
0x1800cb130  jz      short loc_1800CB145
0x1800cb132  mov     r9, rbx
0x1800cb135  mov     rdx, rdi
0x1800cb138  mov     rcx, rax
0x1800cb13b  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800cb140  mov     rdi, rax
0x1800cb143  jmp     short loc_1800CB147
0x1800cb145  xor     edi, edi
0x1800cb147  test    rdi, rdi
0x1800cb14a  jnz     short loc_1800CB171
0x1800cb14c  mov     rcx, [rsp+68h]; this
0x1800cb151  mov     ebx, 8007000Eh
0x1800cb156  mov     r9d, ebx; char *
0x1800cb159  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cb160  mov     edx, 0CBBh; void *
0x1800cb165  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb16a  mov     eax, ebx
0x1800cb16c  jmp     loc_1800CB25E
0x1800cb171  lea     rsi, [rdi+80h]
0x1800cb178  xor     edx, edx
0x1800cb17a  mov     rcx, rsi
0x1800cb17d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800cb182  mov     ebx, eax
0x1800cb184  test    eax, eax
0x1800cb186  jns     short loc_1800CB1A6
0x1800cb188  mov     rcx, [rsp+68h]; this
0x1800cb18d  mov     r9d, eax; char *
0x1800cb190  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cb197  mov     edx, 0CBCh; void *
0x1800cb19c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb1a1  jmp     loc_1800CB22A
0x1800cb1a6  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x1800cb1ad  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1800cb1b5  mov     r9, [rsi]; hEvent
0x1800cb1b8  mov     r8d, 10000005h; dwNotifyFilter
0x1800cb1be  mov     rcx, [rdi+78h]; hKey
0x1800cb1c2  call    cs:__imp_RegNotifyChangeKeyValue
0x1800cb1c8  test    eax, eax
0x1800cb1ca  jz      short loc_1800CB1E7
0x1800cb1cc  mov     rcx, [rsp+68h]; this
0x1800cb1d1  mov     r9d, eax; char *
0x1800cb1d4  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cb1db  mov     edx, 0CC2h; void *
0x1800cb1e0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cb1e5  jmp     short loc_1800CB228
0x1800cb1e7  xor     r8d, r8d; pcbe
0x1800cb1ea  mov     rdx, rdi; pv
0x1800cb1ed  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800cb1f4  call    cs:__imp_CreateThreadpoolWait
0x1800cb1fa  lea     rbx, [rdi+88h]
0x1800cb201  mov     rdx, rax
0x1800cb204  mov     rcx, rbx
0x1800cb207  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x1800cb20c  cmp     qword ptr [rbx], 0
0x1800cb210  jnz     short loc_1800CB237
0x1800cb212  mov     rcx, [rsp+68h]; this
0x1800cb217  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cb21e  mov     edx, 0CC5h; void *
0x1800cb223  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cb228  mov     ebx, eax
0x1800cb22a  mov     rcx, rdi; this
0x1800cb22d  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800cb232  jmp     loc_1800CB16A
0x1800cb237  mov     rdx, rdi
0x1800cb23a  mov     rcx, r14
0x1800cb23d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1800cb242  mov     rcx, [r14]
0x1800cb245  xor     r8d, r8d; pftTimeout
0x1800cb248  mov     rdx, [rcx+80h]; h
0x1800cb24f  mov     rcx, [rcx+88h]; pwa
0x1800cb256  call    cs:__imp_SetThreadpoolWait
0x1800cb25c  xor     eax, eax
0x1800cb25e  add     rsp, 48h
0x1800cb262  pop     r14
0x1800cb264  pop     rdi
0x1800cb265  pop     rsi
0x1800cb266  pop     rbx
0x1800cb267  retn
```
