# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wil::event_watcher_options,wistd::function<void (void)> &&)

- ea: `0x1801177c4`
- end: `0x180117921`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAXW4event_watcher_options@2@$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18011771c`

## callees

- `0x180081130`
- `0x18008daac`
- `0x18008e194`
- `0x18008ead4`
- `0x180099dd4`
- `0x1800f2448`
- `0x180117004`
- `0x180117254`
- `0x1801177c4`
- `0x180117954`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180117875`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180117875`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801178e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1801178e4`

## string_xrefs

- `0x180117855`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180117898`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18011790f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        __int64 a1,
        __int64 a2,
        int a3,
        const char *a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned int LastError; // ebx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v12; // r9
  unsigned int v13; // edx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x116C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v17 = a2;
  v8 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v15 = (int)v8;
  if ( v8 )
  {
    wistd::function<void (void)>::function<void (void)>(v8, a4);
    v9[15] = a2;
    v17 = 0;
    v9[16] = 0;
    *((_DWORD *)v9 + 34) = a3;
    *((_DWORD *)v9 + 35) = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1173,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v15);
LABEL_9:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    return LastError;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                     v9,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v9 + 16,
    ThreadpoolWait);
  if ( !v9[16] )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1176,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                  v12);
    wil::details::event_watcher_state::`scalar deleting destructor'((wil::details::event_watcher_state *)v9, v13);
    goto LABEL_9;
  }
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
    a1,
    v9);
  if ( (a3 & 2) == 0 )
    SetThreadpoolWait(*(PTP_WAIT *)(*(_QWORD *)a1 + 128LL), *(HANDLE *)(*(_QWORD *)a1 + 120LL), 0);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
  return 0;
}

```

## disassembly

```asm
0x1801177c4  mov     [rsp+arg_0], rbx
0x1801177c9  mov     [rsp+arg_10], rbp
0x1801177ce  push    rsi
0x1801177cf  push    rdi
0x1801177d0  push    r14
0x1801177d2  sub     rsp, 30h
0x1801177d6  mov     r14, r9
0x1801177d9  mov     ebp, r8d
0x1801177dc  mov     rbx, rdx
0x1801177df  mov     rsi, rcx
0x1801177e2  test    rdx, rdx
0x1801177e5  jz      loc_18011790A
0x1801177eb  mov     [rsp+48h+arg_8], rdx
0x1801177f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801177f7  mov     ecx, 90h; unsigned __int64
0x1801177fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180117801  mov     rdi, rax
0x180117804  mov     qword ptr [rsp+48h+var_28], rax; int
0x180117809  test    rax, rax
0x18011780c  jz      short loc_180117841
0x18011780e  mov     rdx, r14
0x180117811  mov     rcx, rax
0x180117814  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x180117819  mov     [rdi+78h], rbx
0x18011781d  mov     [rsp+48h+arg_8], 0
0x180117826  mov     qword ptr [rdi+80h], 0
0x180117831  mov     [rdi+88h], ebp
0x180117837  xor     eax, eax
0x180117839  mov     [rdi+8Ch], eax
0x18011783f  jmp     short loc_180117843
0x180117841  xor     edi, edi
0x180117843  test    rdi, rdi
0x180117846  jnz     short loc_180117868
0x180117848  mov     rcx, [rsp+48h]; this
0x18011784d  mov     ebx, 8007000Eh
0x180117852  mov     r9d, ebx; char *
0x180117855  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18011785c  mov     edx, 1173h; void *
0x180117861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117866  jmp     short loc_1801178B4
0x180117868  xor     r8d, r8d; pcbe
0x18011786b  mov     rdx, rdi; pv
0x18011786e  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180117875  call    cs:__imp_CreateThreadpoolWait
0x18011787b  lea     rbx, [rdi+80h]
0x180117882  mov     rdx, rax
0x180117885  mov     rcx, rbx
0x180117888  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x18011788d  cmp     qword ptr [rbx], 0
0x180117891  jnz     short loc_1801178C2
0x180117893  mov     rcx, [rsp+48h]; this
0x180117898  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18011789f  mov     edx, 1176h; void *
0x1801178a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801178a9  mov     ebx, eax
0x1801178ab  mov     rcx, rdi; this
0x1801178ae  call    ??_Gevent_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::event_watcher_state::`scalar deleting destructor'(uint)
0x1801178b3  nop
0x1801178b4  lea     rcx, [rsp+48h+arg_8]
0x1801178b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801178be  mov     eax, ebx
0x1801178c0  jmp     short loc_1801178F7
0x1801178c2  mov     rdx, rdi
0x1801178c5  mov     rcx, rsi
0x1801178c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x1801178cd  test    bpl, 2
0x1801178d1  jnz     short loc_1801178EB
0x1801178d3  mov     rcx, [rsi]
0x1801178d6  xor     r8d, r8d; pftTimeout
0x1801178d9  mov     rdx, [rcx+78h]; h
0x1801178dd  mov     rcx, [rcx+80h]; pwa
0x1801178e4  call    cs:__imp_SetThreadpoolWait
0x1801178ea  nop
0x1801178eb  lea     rcx, [rsp+48h+arg_8]
0x1801178f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801178f5  xor     eax, eax
0x1801178f7  mov     rbx, [rsp+48h+arg_0]
0x1801178fc  mov     rbp, [rsp+48h+arg_10]
0x180117901  add     rsp, 30h
0x180117905  pop     r14
0x180117907  pop     rdi
0x180117908  pop     rsi
0x180117909  retn
0x18011790a  mov     rcx, [rsp+48h]; this
0x18011790f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180117916  mov     edx, 116Ch; void *
0x18011791b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
