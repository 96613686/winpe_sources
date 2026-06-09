# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wistd::function<void (void)> &&)

- ea: `0x1800a8c3c`
- end: `0x1800a8e4b`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002cdb8`

## callees

- `0x180008450`
- `0x180008618`
- `0x18000933c`
- `0x18000a4e0`
- `0x180039ba8`
- `0x1800a8b64`
- `0x1800a8c3c`
- `0x1800f8314`
- `0x1800f876c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8d84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8de1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8d84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8de1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8d9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8d3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8d3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a8dbb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800a8cfa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800a8cfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800a8d2d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800a8d2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8d1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8dd2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8d1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800a8dd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800a8d36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800a8d36`

## string_xrefs

- `0x1800a8cbe`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1800a8d55`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1800a8e19`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        wil::details::event_watcher_state **a1,
        void *a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rbx
  void *v7; // rax
  void *v8; // rsi
  void *v9; // rdi
  unsigned int v10; // r8d
  const char *v11; // r9
  PTP_WAIT ThreadpoolWait; // rbp
  const char *v14; // r9
  struct _TP_WAIT *v15; // r15
  DWORD LastError; // edi
  unsigned int v17; // edi
  unsigned int v18; // r8d
  const char *v19; // r9
  wil::details::event_watcher_state *v20; // rbp
  DWORD v21; // edi
  unsigned int v22; // r8d
  const char *v23; // r9
  int v24; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a2;
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF5E,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v24 = (int)a2;
  v7 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    wistd::function<void (void)>::function<void (void)>(v7, a3);
    *((_QWORD *)v8 + 15) = v5;
    v5 = 0;
    *((_QWORD *)v8 + 16) = 0;
    v9 = 0;
  }
  else
  {
    v8 = 0;
    v9 = v5;
  }
  if ( v8 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                       v8,
                       0);
    v15 = (struct _TP_WAIT *)*((_QWORD *)v8 + 16);
    if ( v15 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v15, 0, 0);
      WaitForThreadpoolWaitCallbacks(v15, 1);
      CloseThreadpoolWait(v15);
      SetLastError(LastError);
    }
    *((_QWORD *)v8 + 16) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v20 = *a1;
      if ( *a1 )
      {
        v21 = GetLastError();
        wil::details::event_watcher_state::~event_watcher_state(v20);
        operator delete(v20);
        SetLastError(v21);
      }
      *a1 = (wil::details::event_watcher_state *)v8;
      SetThreadpoolWait(*((PTP_WAIT *)v8 + 16), *((HANDLE *)v8 + 15), 0);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      return 0;
    }
    else
    {
      v17 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF65,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
              v14);
      wil::details::event_watcher_state::~event_watcher_state((wil::details::event_watcher_state *)v8);
      operator delete(v8);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v18, v19);
      return v17;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF62,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v24);
    if ( v9 )
    {
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v10, v11);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800a8c3c  mov     [rsp+arg_8], rbx
0x1800a8c41  mov     [rsp+arg_18], rbp
0x1800a8c46  push    rsi
0x1800a8c47  push    rdi
0x1800a8c48  push    r12
0x1800a8c4a  push    r14
0x1800a8c4c  push    r15
0x1800a8c4e  sub     rsp, 30h
0x1800a8c52  mov     rdi, r8
0x1800a8c55  mov     rbx, rdx
0x1800a8c58  mov     r14, rcx
0x1800a8c5b  test    rdx, rdx
0x1800a8c5e  jz      loc_1800A8E14
0x1800a8c64  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800a8c69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a8c70  mov     r12d, 88h
0x1800a8c76  mov     ecx, r12d; unsigned __int64
0x1800a8c79  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a8c7e  mov     rsi, rax
0x1800a8c81  mov     [rsp+58h+var_30], rax
0x1800a8c86  test    rax, rax
0x1800a8c89  jz      short loc_1800A8CA7
0x1800a8c8b  mov     rdx, rdi
0x1800a8c8e  mov     rcx, rax
0x1800a8c91  call    ??0?$function@$$A6AXXZ@wistd@@QEAA@$$QEAV01@@Z; wistd::function<void (void)>::function<void (void)>(wistd::function<void (void)> &&)
0x1800a8c96  mov     [rsi+78h], rbx
0x1800a8c9a  xor     ebx, ebx
0x1800a8c9c  mov     [rsi+80h], rbx
0x1800a8ca3  xor     edi, edi
0x1800a8ca5  jmp     short loc_1800A8CAC
0x1800a8ca7  xor     esi, esi
0x1800a8ca9  mov     rdi, rbx
0x1800a8cac  test    rsi, rsi
0x1800a8caf  jnz     short loc_1800A8CED
0x1800a8cb1  mov     rcx, [rsp+58h]; this
0x1800a8cb6  mov     esi, 8007000Eh
0x1800a8cbb  mov     r9d, esi; char *
0x1800a8cbe  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800a8cc5  mov     edx, 0F62h; void *
0x1800a8cca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8ccf  nop
0x1800a8cd0  test    rdi, rdi
0x1800a8cd3  jz      short loc_1800A8CE6
0x1800a8cd5  mov     rcx, rbx; hObject
0x1800a8cd8  call    cs:__imp_CloseHandle
0x1800a8cde  test    eax, eax
0x1800a8ce0  jz      loc_1800A8E2B
0x1800a8ce6  mov     eax, esi
0x1800a8ce8  jmp     loc_1800A8DED
0x1800a8ced  xor     r8d, r8d; pcbe
0x1800a8cf0  mov     rdx, rsi; pv
0x1800a8cf3  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x1800a8cfa  call    cs:__imp_CreateThreadpoolWait
0x1800a8d00  mov     rbp, rax
0x1800a8d03  mov     r15, [rsi+80h]
0x1800a8d0a  test    r15, r15
0x1800a8d0d  jz      short loc_1800A8D44
0x1800a8d0f  call    cs:__imp_GetLastError
0x1800a8d15  mov     edi, eax
0x1800a8d17  xor     r8d, r8d; pftTimeout
0x1800a8d1a  xor     edx, edx; h
0x1800a8d1c  mov     rcx, r15; pwa
0x1800a8d1f  call    cs:__imp_SetThreadpoolWait
0x1800a8d25  mov     edx, 1; fCancelPendingCallbacks
0x1800a8d2a  mov     rcx, r15; pwa
0x1800a8d2d  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800a8d33  mov     rcx, r15; pwa
0x1800a8d36  call    cs:__imp_CloseThreadpoolWait
0x1800a8d3c  mov     ecx, edi; dwErrCode
0x1800a8d3e  call    cs:__imp_SetLastError
0x1800a8d44  mov     [rsi+80h], rbp
0x1800a8d4b  test    rbp, rbp
0x1800a8d4e  jnz     short loc_1800A8D96
0x1800a8d50  mov     rcx, [rsp+58h]; this
0x1800a8d55  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800a8d5c  mov     edx, 0F65h; void *
0x1800a8d61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8d66  mov     edi, eax
0x1800a8d68  mov     rcx, rsi; this
0x1800a8d6b  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x1800a8d70  mov     rdx, r12
0x1800a8d73  mov     rcx, rsi; Block
0x1800a8d76  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a8d7b  nop
0x1800a8d7c  test    rbx, rbx
0x1800a8d7f  jz      short loc_1800A8D92
0x1800a8d81  mov     rcx, rbx; hObject
0x1800a8d84  call    cs:__imp_CloseHandle
0x1800a8d8a  test    eax, eax
0x1800a8d8c  jz      loc_1800A8E3B
0x1800a8d92  mov     eax, edi
0x1800a8d94  jmp     short loc_1800A8DED
0x1800a8d96  mov     rbp, [r14]
0x1800a8d99  test    rbp, rbp
0x1800a8d9c  jz      short loc_1800A8DC1
0x1800a8d9e  call    cs:__imp_GetLastError
0x1800a8da4  mov     edi, eax
0x1800a8da6  mov     rcx, rbp; this
0x1800a8da9  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x1800a8dae  mov     rdx, r12
0x1800a8db1  mov     rcx, rbp; Block
0x1800a8db4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a8db9  mov     ecx, edi; dwErrCode
0x1800a8dbb  call    cs:__imp_SetLastError
0x1800a8dc1  mov     [r14], rsi
0x1800a8dc4  xor     r8d, r8d; pftTimeout
0x1800a8dc7  mov     rdx, [rsi+78h]; h
0x1800a8dcb  mov     rcx, [rsi+80h]; pwa
0x1800a8dd2  call    cs:__imp_SetThreadpoolWait
0x1800a8dd8  nop
0x1800a8dd9  test    rbx, rbx
0x1800a8ddc  jz      short loc_1800A8DEB
0x1800a8dde  mov     rcx, rbx; hObject
0x1800a8de1  call    cs:__imp_CloseHandle
0x1800a8de7  test    eax, eax
0x1800a8de9  jz      short loc_1800A8E04
0x1800a8deb  xor     eax, eax
0x1800a8ded  mov     rbx, [rsp+58h+arg_8]
0x1800a8df2  mov     rbp, [rsp+58h+arg_18]
0x1800a8df7  add     rsp, 30h
0x1800a8dfb  pop     r15
0x1800a8dfd  pop     r14
0x1800a8dff  pop     r12
0x1800a8e01  pop     rdi
0x1800a8e02  pop     rsi
0x1800a8e03  retn
0x1800a8e04  mov     rcx, [rsp+58h]; this
0x1800a8e09  mov     edx, 9D1h; void *
0x1800a8e0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800a8e14  mov     rcx, [rsp+58h]; this
0x1800a8e19  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800a8e20  mov     edx, 0F5Eh; void *
0x1800a8e25  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a8e2b  mov     rcx, [rsp+58h]; this
0x1800a8e30  mov     edx, 9D1h; void *
0x1800a8e35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800a8e3b  mov     rcx, [rsp+58h]; this
0x1800a8e40  mov     edx, 9D1h; void *
0x1800a8e45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
