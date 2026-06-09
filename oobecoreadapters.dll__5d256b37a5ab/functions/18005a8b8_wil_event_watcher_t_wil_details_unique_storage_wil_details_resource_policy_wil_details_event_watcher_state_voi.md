# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x18005a8b8`
- end: `0x18005aa17`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18005aa98`

## callees

- `0x180003ffc`
- `0x1800050f4`
- `0x180005378`
- `0x1800054a4`
- `0x1800059bc`
- `0x1800076b4`
- `0x1800076d4`
- `0x18005878c`
- `0x1800596dc`
- `0x180059a44`
- `0x18005a8b8`
- `0x18005ab70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a9e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a9e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a95e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a95e`

## string_xrefs

- `0x18005a93e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005a9a0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_take_hevent_ownership(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  unsigned int LastError; // edi
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v11; // r9
  struct _TP_WAIT *v12; // rsi
  unsigned int v13; // edx
  int v15[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0x116C, a3, a4);
  v17 = a2;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  *(_QWORD *)v15 = v7;
  if ( v7 )
  {
    wistd::function<void (void)>::function<void (void)>(v7, a4);
    v8[15] = a2;
    v17 = 0;
    v8[16] = 0;
    v8[17] = 0;
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v15[0]);
LABEL_11:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::wait_callback,
                     v8,
                     0);
  v12 = (struct _TP_WAIT *)v8[16];
  if ( v12 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v15);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
  }
  v8[16] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1176,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                  v11);
    wil::details::event_watcher_state::`scalar deleting destructor'((wil::details::event_watcher_state *)v8, v13);
    goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v8);
  SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 128LL), *(HANDLE *)(*(_QWORD *)a1 + 120LL), 0);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return 0;
}

```

## disassembly

```asm
0x18005a8b8  mov     [rsp+arg_0], rbx
0x18005a8bd  push    rsi
0x18005a8be  push    rdi
0x18005a8bf  push    r14
0x18005a8c1  sub     rsp, 30h
0x18005a8c5  mov     rsi, r9
0x18005a8c8  mov     rdi, rdx
0x18005a8cb  mov     r14, rcx
0x18005a8ce  test    rdx, rdx
0x18005a8d1  jz      loc_18005AA07
0x18005a8d7  mov     [rsp+48h+arg_8], rdx
0x18005a8dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005a8e3  mov     ecx, 90h; unsigned __int64
0x18005a8e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005a8ed  mov     rbx, rax
0x18005a8f0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18005a8f5  test    rax, rax
0x18005a8f8  jz      short loc_18005A92A
0x18005a8fa  mov     rdx, rsi
0x18005a8fd  mov     rcx, rax
0x18005a900  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x18005a905  mov     [rbx+78h], rdi
0x18005a909  mov     [rsp+48h+arg_8], 0
0x18005a912  mov     qword ptr [rbx+80h], 0
0x18005a91d  mov     qword ptr [rbx+88h], 0
0x18005a928  jmp     short loc_18005A92C
0x18005a92a  xor     ebx, ebx
0x18005a92c  test    rbx, rbx
0x18005a92f  jnz     short loc_18005A951
0x18005a931  mov     rcx, [rsp+48h]; this
0x18005a936  mov     edi, 8007000Eh
0x18005a93b  mov     r9d, edi; char *
0x18005a93e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005a945  mov     edx, 1173h; void *
0x18005a94a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a94f  jmp     short loc_18005A9BC
0x18005a951  xor     r8d, r8d; pcbe
0x18005a954  mov     rdx, rbx; pv
0x18005a957  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005a95e  call    cs:__imp_CreateThreadpoolWait
0x18005a964  mov     rdi, rax
0x18005a967  mov     rsi, [rbx+80h]
0x18005a96e  test    rsi, rsi
0x18005a971  jz      short loc_18005A98F
0x18005a973  lea     rcx, [rsp+48h+var_28]; this
0x18005a978  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005a97d  mov     rcx, rsi; pwa
0x18005a980  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18005a985  lea     rcx, [rsp+48h+var_28]; this
0x18005a98a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005a98f  mov     [rbx+80h], rdi
0x18005a996  test    rdi, rdi
0x18005a999  jnz     short loc_18005A9CA
0x18005a99b  mov     rcx, [rsp+48h]; this
0x18005a9a0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005a9a7  mov     edx, 1176h; void *
0x18005a9ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005a9b1  mov     edi, eax
0x18005a9b3  mov     rcx, rbx; this
0x18005a9b6  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x18005a9bb  nop
0x18005a9bc  lea     rcx, [rsp+48h+arg_8]
0x18005a9c1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005a9c6  mov     eax, edi
0x18005a9c8  jmp     short loc_18005A9F9
0x18005a9ca  mov     rdx, rbx
0x18005a9cd  mov     rcx, r14
0x18005a9d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x18005a9d5  mov     rcx, [r14]
0x18005a9d8  xor     r8d, r8d; pftTimeout
0x18005a9db  mov     rdx, [rcx+78h]; h
0x18005a9df  mov     rcx, [rcx+80h]; pwa
0x18005a9e6  call    cs:__imp_SetThreadpoolWait
0x18005a9ec  nop
0x18005a9ed  lea     rcx, [rsp+48h+arg_8]
0x18005a9f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005a9f7  xor     eax, eax
0x18005a9f9  mov     rbx, [rsp+48h+arg_0]
0x18005a9fe  add     rsp, 30h
0x18005aa02  pop     r14
0x18005aa04  pop     rdi
0x18005aa05  pop     rsi
0x18005aa06  retn
0x18005aa07  mov     rcx, [rsp+48h]; this
0x18005aa0c  mov     edx, 116Ch; void *
0x18005aa11  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
