# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x1800f86fc`
- end: `0x1800f8985`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `649`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800f79fc`
- `0x1800f7ef0`

## callees

- `0x18005f560`
- `0x18006038c`
- `0x180062418`
- `0x180063074`
- `0x180063094`
- `0x180064018`
- `0x1800efd64`
- `0x1800f0b30`
- `0x1800f83bc`
- `0x1800f86fc`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f87ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800f87ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f882a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f88ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f8948`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f882a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f88ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f8948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f87fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f880f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f88bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f87fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f880f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f88bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f8936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f881a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f881a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f88cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f8962`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f88cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f8962`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800f88d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800f88d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f88e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800f88e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800f88a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800f88a6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800f8857`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800f8857`

## string_xrefs

- `0x1800f87ca`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800f8886`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`
- `0x1800f8901`: `onecore\internal\sdk\inc\wil\opensource/wil/registry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
        wil::details **a1,
        _QWORD *a2,
        char a3,
        __int64 a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  unsigned int v10; // ebx
  wil::details *v12; // rcx
  HANDLE Event; // rsi
  void *v14; // rbx
  DWORD LastError; // ebp
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // eax
  void *v19; // rdx
  unsigned int v20; // r8d
  int v21; // eax
  int LastErrorFailHr; // eax
  PTP_WAIT ThreadpoolWait; // rbp
  const char *v24; // r9
  struct _TP_WAIT *v25; // rsi
  DWORD v26; // ebx
  wil::details *v27; // rsi
  DWORD v28; // ebx
  struct wil::details::registry_watcher_state *v29; // rdx
  BOOL fAsynchronous; // [rsp+20h] [rbp-48h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    if ( *(_QWORD *)(a4 + 112) )
    {
      v8[14] = v8 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 16LL))(*(_QWORD *)(a4 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 112) + 24LL))(*(_QWORD *)(a4 + 112));
      *(_QWORD *)(a4 + 112) = 0;
    }
    else
    {
      v8[14] = 0;
    }
    v9[15] = *a2;
    *a2 = 0;
    v9[16] = 0;
    v9[17] = 0;
    *((_BYTE *)v9 + 144) = a3;
    *((_DWORD *)v9 + 37) = 1;
    v9[19] = 0;
  }
  else
  {
    v9 = 0;
  }
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
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v14 = (void *)v9[16];
    if ( v14 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v14) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
      SetLastError(LastError);
    }
    v9[16] = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v10 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCBC,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_24:
      wil::details::registry_watcher_state::~registry_watcher_state((wil::details::registry_watcher_state *)v9);
      operator delete(v9, (const struct std::nothrow_t *)0xA0);
      return v10;
    }
  }
  v18 = RegNotifyChangeKeyValue((HKEY)v9[15], *((unsigned __int8 *)v9 + 144), 0x10000005u, (HANDLE)v9[16], 1);
  if ( v18 )
  {
    v21 = wil::details::in1diag3::Return_Win32(retaddr, v19, v20, (const char *)v18, fAsynchronousa);
LABEL_23:
    v10 = v21;
    goto LABEL_24;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     v9,
                     0);
  v25 = (struct _TP_WAIT *)v9[17];
  if ( v25 )
  {
    v26 = GetLastError();
    SetThreadpoolWait(v25, 0, 0);
    WaitForThreadpoolWaitCallbacks(v25, 1);
    CloseThreadpoolWait(v25);
    SetLastError(v26);
  }
  v9[17] = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    v21 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xCC5,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/registry.h",
            v24);
    goto LABEL_23;
  }
  v27 = *a1;
  if ( *a1 )
  {
    v28 = GetLastError();
    wil::details::delete_registry_watcher_state(v27, v29);
    SetLastError(v28);
  }
  *a1 = (wil::details *)v9;
  SetThreadpoolWait((PTP_WAIT)v9[17], (HANDLE)v9[16], 0);
  return 0;
}

```

## disassembly

```asm
0x1800f86fc  push    rbx
0x1800f86fe  push    rbp
0x1800f86ff  push    rsi
0x1800f8700  push    rdi
0x1800f8701  push    r14
0x1800f8703  sub     rsp, 40h
0x1800f8707  mov     rbx, r9
0x1800f870a  mov     bpl, r8b
0x1800f870d  mov     rsi, rdx
0x1800f8710  mov     r14, rcx
0x1800f8713  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f871a  mov     ecx, 0A0h; unsigned __int64
0x1800f871f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800f8724  mov     rdi, rax
0x1800f8727  mov     [rsp+68h+var_38], rax
0x1800f872c  test    rax, rax
0x1800f872f  jz      loc_1800F87B6
0x1800f8735  cmp     qword ptr [rbx+70h], 0
0x1800f873a  jnz     short loc_1800F8746
0x1800f873c  mov     qword ptr [rax+70h], 0
0x1800f8744  jmp     short loc_1800F8776
0x1800f8746  lea     rdx, [rax+8]
0x1800f874a  mov     [rax+70h], rdx
0x1800f874e  mov     rcx, [rbx+70h]
0x1800f8752  mov     rax, [rcx]
0x1800f8755  mov     rax, [rax+10h]
0x1800f8759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f875e  mov     rcx, [rbx+70h]
0x1800f8762  mov     rax, [rcx]
0x1800f8765  mov     rax, [rax+18h]
0x1800f8769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f876e  mov     qword ptr [rbx+70h], 0
0x1800f8776  mov     rax, [rsi]
0x1800f8779  mov     [rdi+78h], rax
0x1800f877d  mov     qword ptr [rsi], 0
0x1800f8784  mov     qword ptr [rdi+80h], 0
0x1800f878f  mov     qword ptr [rdi+88h], 0
0x1800f879a  mov     [rdi+90h], bpl
0x1800f87a1  mov     dword ptr [rdi+94h], 1
0x1800f87ab  xor     eax, eax
0x1800f87ad  mov     [rdi+98h], rax
0x1800f87b4  jmp     short loc_1800F87B8
0x1800f87b6  xor     edi, edi
0x1800f87b8  test    rdi, rdi
0x1800f87bb  jnz     short loc_1800F87E2
0x1800f87bd  mov     rcx, [rsp+68h]; this
0x1800f87c2  mov     ebx, 8007000Eh
0x1800f87c7  mov     r9d, ebx; char *
0x1800f87ca  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f87d1  mov     edx, 0CBBh; void *
0x1800f87d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f87db  mov     eax, ebx
0x1800f87dd  jmp     loc_1800F896A
0x1800f87e2  mov     r9d, 1F0003h; dwDesiredAccess
0x1800f87e8  xor     r8d, r8d; dwFlags
0x1800f87eb  xor     edx, edx; lpName
0x1800f87ed  xor     ecx, ecx; lpEventAttributes
0x1800f87ef  call    cs:__imp_CreateEventExW
0x1800f87f5  mov     rsi, rax
0x1800f87f8  test    rax, rax
0x1800f87fb  jz      short loc_1800F8873
0x1800f87fd  call    cs:__imp_GetLastError
0x1800f8803  mov     rbx, [rdi+80h]
0x1800f880a  test    rbx, rbx
0x1800f880d  jz      short loc_1800F8830
0x1800f880f  call    cs:__imp_GetLastError
0x1800f8815  mov     ebp, eax
0x1800f8817  mov     rcx, rbx; hObject
0x1800f881a  call    cs:__imp_CloseHandle
0x1800f8820  test    eax, eax
0x1800f8822  jz      loc_1800F8975
0x1800f8828  mov     ecx, ebp; dwErrCode
0x1800f882a  call    cs:__imp_SetLastError
0x1800f8830  mov     [rdi+80h], rsi
0x1800f8837  movzx   edx, byte ptr [rdi+90h]; bWatchSubtree
0x1800f883e  mov     [rsp+68h+fAsynchronous], 1; unsigned int
0x1800f8846  mov     r9, [rdi+80h]; hEvent
0x1800f884d  mov     r8d, 10000005h; dwNotifyFilter
0x1800f8853  mov     rcx, [rdi+78h]; hKey
0x1800f8857  call    cs:__imp_RegNotifyChangeKeyValue
0x1800f885d  test    eax, eax
0x1800f885f  jz      short loc_1800F8899
0x1800f8861  mov     rcx, [rsp+68h]; this
0x1800f8866  mov     r9d, eax; char *
0x1800f8869  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f886e  jmp     loc_1800F8912
0x1800f8873  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800f8878  mov     ebx, eax
0x1800f887a  test    eax, eax
0x1800f887c  jns     short loc_1800F8837
0x1800f887e  mov     rcx, [rsp+68h]; this
0x1800f8883  mov     r9d, eax; char *
0x1800f8886  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f888d  mov     edx, 0CBCh; void *
0x1800f8892  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8897  jmp     short loc_1800F8914
0x1800f8899  xor     r8d, r8d; pcbe
0x1800f889c  mov     rdx, rdi; pv
0x1800f889f  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800f88a6  call    cs:__imp_CreateThreadpoolWait
0x1800f88ac  mov     rbp, rax
0x1800f88af  mov     rsi, [rdi+88h]
0x1800f88b6  test    rsi, rsi
0x1800f88b9  jz      short loc_1800F88F0
0x1800f88bb  call    cs:__imp_GetLastError
0x1800f88c1  mov     ebx, eax
0x1800f88c3  xor     r8d, r8d; pftTimeout
0x1800f88c6  xor     edx, edx; h
0x1800f88c8  mov     rcx, rsi; pwa
0x1800f88cb  call    cs:__imp_SetThreadpoolWait
0x1800f88d1  mov     edx, 1; fCancelPendingCallbacks
0x1800f88d6  mov     rcx, rsi; pwa
0x1800f88d9  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800f88df  mov     rcx, rsi; pwa
0x1800f88e2  call    cs:__imp_CloseThreadpoolWait
0x1800f88e8  mov     ecx, ebx; dwErrCode
0x1800f88ea  call    cs:__imp_SetLastError
0x1800f88f0  mov     [rdi+88h], rbp
0x1800f88f7  test    rbp, rbp
0x1800f88fa  jnz     short loc_1800F892E
0x1800f88fc  mov     rcx, [rsp+68h]; this
0x1800f8901  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800f8908  mov     edx, 0CC5h; void *
0x1800f890d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f8912  mov     ebx, eax
0x1800f8914  mov     rcx, rdi; this
0x1800f8917  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x1800f891c  mov     edx, 0A0h; struct std::nothrow_t *
0x1800f8921  mov     rcx, rdi; void *
0x1800f8924  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f8929  jmp     loc_1800F87DB
0x1800f892e  mov     rsi, [r14]
0x1800f8931  test    rsi, rsi
0x1800f8934  jz      short loc_1800F894E
0x1800f8936  call    cs:__imp_GetLastError
0x1800f893c  mov     ebx, eax
0x1800f893e  mov     rcx, rsi; this
0x1800f8941  call    ?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z; wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)
0x1800f8946  mov     ecx, ebx; dwErrCode
0x1800f8948  call    cs:__imp_SetLastError
0x1800f894e  mov     [r14], rdi
0x1800f8951  xor     r8d, r8d; pftTimeout
0x1800f8954  mov     rdx, [rdi+80h]; h
0x1800f895b  mov     rcx, [rdi+88h]; pwa
0x1800f8962  call    cs:__imp_SetThreadpoolWait
0x1800f8968  xor     eax, eax
0x1800f896a  add     rsp, 40h
0x1800f896e  pop     r14
0x1800f8970  pop     rdi
0x1800f8971  pop     rsi
0x1800f8972  pop     rbp
0x1800f8973  pop     rbx
0x1800f8974  retn
0x1800f8975  mov     rcx, [rsp+68h]; this
0x1800f897a  mov     edx, 0A0Bh; void *
0x1800f897f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
