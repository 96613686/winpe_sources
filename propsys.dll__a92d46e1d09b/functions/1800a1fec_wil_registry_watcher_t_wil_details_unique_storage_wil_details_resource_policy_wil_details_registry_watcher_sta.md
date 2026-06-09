# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800a1fec`
- end: `0x1800a21ab`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2cb4`

## callees

- `0x180025dd4`
- `0x180051638`
- `0x18006944c`
- `0x18006946c`
- `0x18006958c`
- `0x18006f1fc`
- `0x1800724ec`
- `0x180072660`
- `0x18009b724`
- `0x18009cb1c`
- `0x18009cd2c`
- `0x1800a1fec`
- `0x1800a3654`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a206f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800a206f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2084`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800a2115`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800a2115`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a2195`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a2195`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a20e3`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800a20e3`

## string_xrefs

- `0x1800a204a`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800a20aa`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800a20f5`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x1800a2157`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4)
{
  void *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rbx
  wil::details *v12; // rcx
  HANDLE Event; // rsi
  HANDLE *v14; // rdi
  int LastErrorFailHr; // eax
  unsigned int v16; // edi
  unsigned int v17; // edx
  unsigned int v18; // eax
  int LastError; // eax
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v21; // r9
  struct _TP_WAIT *v22; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  _QWORD v25[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  v25[0] = v8;
  if ( v8 )
  {
    LOBYTE(v9) = a3;
    v10 = wil::details::registry_watcher_state::registry_watcher_state(v8, a2, v9, a4);
  }
  else
  {
    v10 = 0;
  }
  if ( !v10 )
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
    v14 = (HANDLE *)(v10 + 128);
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v10 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v16 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_18:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v10,
        v17);
      return v16;
    }
    v14 = (HANDLE *)(v10 + 128);
  }
  v18 = RegNotifyChangeKeyValue(*(HKEY *)(v10 + 120), *(unsigned __int8 *)(v10 + 144), 0x10000005u, *v14, 1);
  if ( v18 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xCC2,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
                  (const char *)v18,
                  fAsynchronousa);
LABEL_17:
    v16 = LastError;
    goto LABEL_18;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  v22 = *(struct _TP_WAIT **)(v10 + 136);
  if ( v22 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v25);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v22);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v25);
  }
  *(_QWORD *)(v10 + 136) = ThreadpoolWait;
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
    v10);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 136LL), *(HANDLE *)(*(_QWORD *)a1 + 128LL), 0);
  return 0;
}

```

## disassembly

```asm
0x1800a1fec  mov     [rsp+arg_10], rbx
0x1800a1ff1  push    rsi
0x1800a1ff2  push    rdi
0x1800a1ff3  push    r14
0x1800a1ff5  sub     rsp, 40h
0x1800a1ff9  mov     rsi, r9
0x1800a1ffc  mov     bl, r8b
0x1800a1fff  mov     rdi, rdx
0x1800a2002  mov     r14, rcx
0x1800a2005  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a200c  mov     ecx, 0A0h; unsigned __int64
0x1800a2011  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a2016  mov     [rsp+58h+var_28], rax
0x1800a201b  test    rax, rax
0x1800a201e  jz      short loc_1800A2036
0x1800a2020  mov     r9, rsi
0x1800a2023  mov     r8b, bl
0x1800a2026  mov     rdx, rdi
0x1800a2029  mov     rcx, rax
0x1800a202c  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800a2031  mov     rbx, rax
0x1800a2034  jmp     short loc_1800A2038
0x1800a2036  xor     ebx, ebx
0x1800a2038  test    rbx, rbx
0x1800a203b  jnz     short loc_1800A2062
0x1800a203d  mov     rcx, [rsp+58h]; this
0x1800a2042  mov     ebx, 8007000Eh
0x1800a2047  mov     r9d, ebx; char *
0x1800a204a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a2051  mov     edx, 0CBBh; void *
0x1800a2056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a205b  mov     eax, ebx
0x1800a205d  jmp     loc_1800A219D
0x1800a2062  mov     r9d, 1F0003h; dwDesiredAccess
0x1800a2068  xor     r8d, r8d; dwFlags
0x1800a206b  xor     edx, edx; lpName
0x1800a206d  xor     ecx, ecx; lpEventAttributes
0x1800a206f  call    cs:__imp_CreateEventExW
0x1800a2075  mov     rsi, rax
0x1800a2078  test    rax, rax
0x1800a207b  jz      short loc_1800A2097
0x1800a207d  lea     rdi, [rbx+80h]
0x1800a2084  call    cs:__imp_GetLastError
0x1800a208a  mov     rdx, rsi
0x1800a208d  mov     rcx, rdi
0x1800a2090  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800a2095  jmp     short loc_1800A20C7
0x1800a2097  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a209c  mov     edi, eax
0x1800a209e  test    eax, eax
0x1800a20a0  jns     short loc_1800A20C0
0x1800a20a2  mov     rcx, [rsp+58h]; this
0x1800a20a7  mov     r9d, eax; char *
0x1800a20aa  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a20b1  mov     edx, 0CBCh; void *
0x1800a20b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a20bb  jmp     loc_1800A216A
0x1800a20c0  lea     rdi, [rbx+80h]
0x1800a20c7  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x1800a20ce  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x1800a20d6  mov     r9, [rdi]; hEvent
0x1800a20d9  mov     r8d, 10000005h; dwNotifyFilter
0x1800a20df  mov     rcx, [rbx+78h]; hKey
0x1800a20e3  call    cs:__imp_RegNotifyChangeKeyValue
0x1800a20e9  test    eax, eax
0x1800a20eb  jz      short loc_1800A2108
0x1800a20ed  mov     rcx, [rsp+58h]; this
0x1800a20f2  mov     r9d, eax; char *
0x1800a20f5  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a20fc  mov     edx, 0CC2h; void *
0x1800a2101  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a2106  jmp     short loc_1800A2168
0x1800a2108  xor     r8d, r8d; pcbe
0x1800a210b  mov     rdx, rbx; pv
0x1800a210e  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800a2115  call    cs:__imp_CreateThreadpoolWait
0x1800a211b  mov     rdi, rax
0x1800a211e  mov     rsi, [rbx+88h]
0x1800a2125  test    rsi, rsi
0x1800a2128  jz      short loc_1800A2146
0x1800a212a  lea     rcx, [rsp+58h+var_28]; this
0x1800a212f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800a2134  mov     rcx, rsi; pwa
0x1800a2137  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x1800a213c  lea     rcx, [rsp+58h+var_28]; this
0x1800a2141  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800a2146  mov     [rbx+88h], rdi
0x1800a214d  test    rdi, rdi
0x1800a2150  jnz     short loc_1800A2176
0x1800a2152  mov     rcx, [rsp+58h]; this
0x1800a2157  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a215e  mov     edx, 0CC5h; void *
0x1800a2163  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a2168  mov     edi, eax
0x1800a216a  mov     rcx, rbx; this
0x1800a216d  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x1800a2172  mov     eax, edi
0x1800a2174  jmp     short loc_1800A219D
0x1800a2176  mov     rdx, rbx
0x1800a2179  mov     rcx, r14
0x1800a217c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x1800a2181  mov     rcx, [r14]
0x1800a2184  xor     r8d, r8d; pftTimeout
0x1800a2187  mov     rdx, [rcx+80h]; h
0x1800a218e  mov     rcx, [rcx+88h]; pwa
0x1800a2195  call    cs:__imp_SetThreadpoolWait
0x1800a219b  xor     eax, eax
0x1800a219d  mov     rbx, [rsp+58h+arg_10]
0x1800a21a2  add     rsp, 40h
0x1800a21a6  pop     r14
0x1800a21a8  pop     rdi
0x1800a21a9  pop     rsi
0x1800a21aa  retn
```
