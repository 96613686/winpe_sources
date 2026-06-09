# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180008c58`
- end: `0x180008e04`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b80`

## callees

- `0x180002d58`
- `0x180003760`
- `0x18000398c`
- `0x1800042d8`
- `0x180005504`
- `0x180005524`
- `0x1800060e0`
- `0x18000815c`
- `0x180008464`
- `0x180008490`
- `0x1800087f4`
- `0x180008c58`
- `0x180008e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008cd8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ced`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008df2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180008df2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180008d72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180008d72`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008d4c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180008d4c`

## string_xrefs

- `0x180008cb3`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180008d13`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180008db4`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // rbx
  wil::details *v11; // rcx
  HANDLE Event; // rsi
  HANDLE *v13; // rdi
  int LastErrorFailHr; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v21; // r9
  struct _TP_WAIT *v22; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  _QWORD v25[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = v8;
  if ( v8 )
    v9 = wil::details::registry_watcher_state::registry_watcher_state((__int64)v8, a2, a3, a4);
  else
    v9 = 0;
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCBB,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    v13 = (HANDLE *)(v9 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v9 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v11);
    v15 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_18:
      wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v9);
      return v15;
    }
    v13 = (HANDLE *)(v9 + 128);
  }
  v16 = RegNotifyChangeKeyValue(*(HKEY *)(v9 + 120), *(unsigned __int8 *)(v9 + 144), 0x10000005u, *v13, 1);
  if ( v16 )
  {
    LastError = wil::details::in1diag3::Return_Win32(retaddr, v17, v18, (const char *)v16, fAsynchronousa);
LABEL_17:
    v15 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v9,
                     0);
  v22 = *(struct _TP_WAIT **)(v9 + 136);
  if ( v22 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v25);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v22);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v25);
  }
  *(_QWORD *)(v9 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xCC5,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  v21);
    goto LABEL_17;
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
0x180008c58  push    rbx
0x180008c5a  push    rsi
0x180008c5b  push    rdi
0x180008c5c  push    r14
0x180008c5e  sub     rsp, 48h
0x180008c62  mov     rbx, r9
0x180008c65  mov     dil, r8b
0x180008c68  mov     rsi, rdx
0x180008c6b  mov     r14, rcx
0x180008c6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008c75  mov     ecx, 0A0h; unsigned __int64
0x180008c7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008c7f  mov     [rsp+68h+var_38], rax
0x180008c84  test    rax, rax
0x180008c87  jz      short loc_180008C9F
0x180008c89  mov     r9, rbx
0x180008c8c  mov     r8b, dil
0x180008c8f  mov     rdx, rsi
0x180008c92  mov     rcx, rax
0x180008c95  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180008c9a  mov     rbx, rax
0x180008c9d  jmp     short loc_180008CA1
0x180008c9f  xor     ebx, ebx
0x180008ca1  test    rbx, rbx
0x180008ca4  jnz     short loc_180008CCB
0x180008ca6  mov     rcx, [rsp+68h]; this
0x180008cab  mov     ebx, 8007000Eh
0x180008cb0  mov     r9d, ebx; char *
0x180008cb3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008cba  mov     edx, 0CBBh; void *
0x180008cbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cc4  mov     eax, ebx
0x180008cc6  jmp     loc_180008DFA
0x180008ccb  mov     r9d, 1F0003h; dwDesiredAccess
0x180008cd1  xor     r8d, r8d; dwFlags
0x180008cd4  xor     edx, edx; lpName
0x180008cd6  xor     ecx, ecx; lpEventAttributes
0x180008cd8  call    cs:__imp_CreateEventExW
0x180008cde  mov     rsi, rax
0x180008ce1  test    rax, rax
0x180008ce4  jz      short loc_180008D00
0x180008ce6  lea     rdi, [rbx+80h]
0x180008ced  call    cs:__imp_GetLastError
0x180008cf3  mov     rdx, rsi
0x180008cf6  mov     rcx, rdi
0x180008cf9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008cfe  jmp     short loc_180008D30
0x180008d00  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008d05  mov     edi, eax
0x180008d07  test    eax, eax
0x180008d09  jns     short loc_180008D29
0x180008d0b  mov     rcx, [rsp+68h]; this
0x180008d10  mov     r9d, eax; char *
0x180008d13  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008d1a  mov     edx, 0CBCh; void *
0x180008d1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d24  jmp     loc_180008DC7
0x180008d29  lea     rdi, [rbx+80h]
0x180008d30  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x180008d37  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x180008d3f  mov     r9, [rdi]; hEvent
0x180008d42  mov     r8d, 10000005h; dwNotifyFilter
0x180008d48  mov     rcx, [rbx+78h]; hKey
0x180008d4c  call    cs:__imp_RegNotifyChangeKeyValue
0x180008d52  test    eax, eax
0x180008d54  jz      short loc_180008D65
0x180008d56  mov     rcx, [rsp+68h]; this
0x180008d5b  mov     r9d, eax; char *
0x180008d5e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008d63  jmp     short loc_180008DC5
0x180008d65  xor     r8d, r8d; pcbe
0x180008d68  mov     rdx, rbx; pv
0x180008d6b  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180008d72  call    cs:__imp_CreateThreadpoolWait
0x180008d78  mov     rdi, rax
0x180008d7b  mov     rsi, [rbx+88h]
0x180008d82  test    rsi, rsi
0x180008d85  jz      short loc_180008DA3
0x180008d87  lea     rcx, [rsp+68h+var_38]; this
0x180008d8c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008d91  mov     rcx, rsi; pwa
0x180008d94  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x180008d99  lea     rcx, [rsp+68h+var_38]; this
0x180008d9e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008da3  mov     [rbx+88h], rdi
0x180008daa  test    rdi, rdi
0x180008dad  jnz     short loc_180008DD3
0x180008daf  mov     rcx, [rsp+68h]; this
0x180008db4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180008dbb  mov     edx, 0CC5h; void *
0x180008dc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008dc5  mov     edi, eax
0x180008dc7  mov     rcx, rbx; this
0x180008dca  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180008dcf  mov     eax, edi
0x180008dd1  jmp     short loc_180008DFA
0x180008dd3  mov     rdx, rbx
0x180008dd6  mov     rcx, r14
0x180008dd9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180008dde  mov     rcx, [r14]
0x180008de1  xor     r8d, r8d; pftTimeout
0x180008de4  mov     rdx, [rcx+80h]; h
0x180008deb  mov     rcx, [rcx+88h]; pwa
0x180008df2  call    cs:__imp_SetThreadpoolWait
0x180008df8  xor     eax, eax
0x180008dfa  add     rsp, 48h
0x180008dfe  pop     r14
0x180008e00  pop     rdi
0x180008e01  pop     rsi
0x180008e02  pop     rbx
0x180008e03  retn
```
