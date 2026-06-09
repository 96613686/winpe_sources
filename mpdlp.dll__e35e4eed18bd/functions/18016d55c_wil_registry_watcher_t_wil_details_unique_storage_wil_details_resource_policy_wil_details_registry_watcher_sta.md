# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18016d55c`
- end: `0x18016d706`
- name: `?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18016d414`

## callees

- `0x180065394`
- `0x18010d4dc`
- `0x18016adec`
- `0x18016ae9c`
- `0x18016c8dc`
- `0x18016cbac`
- `0x18016cc98`
- `0x18016cdc4`
- `0x18016cfe4`
- `0x18016d000`
- `0x18016d55c`
- `0x18016d750`
- `0x18016d7e0`

## import_xrefs

- `KERNEL32!SetThreadpoolWait` at `0x18016d6f0`
- `KERNEL32!SetThreadpoolWait` at `0x18016d6f0`
- `KERNEL32!CreateThreadpoolWait` at `0x18016d670`
- `KERNEL32!CreateThreadpoolWait` at `0x18016d670`
- `KERNEL32!CreateEventExW` at `0x18016d5e6`
- `KERNEL32!CreateEventExW` at `0x18016d5e6`
- `KERNEL32!GetLastError` at `0x18016d5f4`
- `KERNEL32!GetLastError` at `0x18016d5f4`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18016d621`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18016d621`

## string_xrefs

- `0x18016d5ba`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`
- `0x18016d650`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`
- `0x18016d6b2`: `src\epp\Dlp\EndpointDlp\inc\wil\registryDlp.h`

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
  HANDLE Event; // rdi
  unsigned int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  int LastError; // eax
  unsigned int v18; // edx
  int LastErrorFailHr; // eax
  unsigned int v20; // edi
  PTP_WAIT ThreadpoolWait; // rdi
  const char *v22; // r9
  struct _TP_WAIT *v23; // rsi
  BOOL fAsynchronous; // [rsp+20h] [rbp-38h]
  BOOL fAsynchronousa; // [rsp+20h] [rbp-38h]
  _QWORD v26[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v26[0] = v8;
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
      (void *)0xEA,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h",
      (const char *)0x8007000ELL,
      fAsynchronous);
    return 2147942414LL;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v10 + 128,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
    v20 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h",
        (const char *)(unsigned int)LastErrorFailHr,
        fAsynchronous);
LABEL_17:
      wil::details::registry_watcher_state::`scalar deleting destructor'(
        (wil::details::registry_watcher_state *)v10,
        v18);
      return v20;
    }
  }
  v14 = RegNotifyChangeKeyValue(
          *(HKEY *)(v10 + 120),
          *(unsigned __int8 *)(v10 + 144),
          0x10000005u,
          *(HANDLE *)(v10 + 128),
          1);
  if ( v14 )
  {
    LastError = wil::details::in1diag3::Return_Win32(retaddr, v15, v16, (const char *)v14, fAsynchronousa);
LABEL_16:
    v20 = LastError;
    goto LABEL_17;
  }
  ThreadpoolWait = CreateThreadpoolWait(
                     wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::callback,
                     (PVOID)v10,
                     0);
  v23 = *(struct _TP_WAIT **)(v10 + 136);
  if ( v23 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v26);
    wil::details::DestroyThreadPoolWait<0>::Destroy(v23);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v26);
  }
  *(_QWORD *)(v10 + 136) = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF1,
                  (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\registryDlp.h",
                  v22);
    goto LABEL_16;
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
0x18016d55c  mov     [rsp+arg_10], rbx
0x18016d561  push    rsi
0x18016d562  push    rdi
0x18016d563  push    r14
0x18016d565  sub     rsp, 40h
0x18016d569  mov     rsi, r9
0x18016d56c  mov     bl, r8b
0x18016d56f  mov     rdi, rdx
0x18016d572  mov     r14, rcx
0x18016d575  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18016d57c  mov     ecx, 0A0h; unsigned __int64
0x18016d581  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18016d586  mov     [rsp+58h+var_28], rax
0x18016d58b  test    rax, rax
0x18016d58e  jz      short loc_18016D5A6
0x18016d590  mov     r9, rsi
0x18016d593  mov     r8b, bl
0x18016d596  mov     rdx, rdi
0x18016d599  mov     rcx, rax
0x18016d59c  call    ??0registry_watcher_state@details@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::details::registry_watcher_state::registry_watcher_state(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18016d5a1  mov     rbx, rax
0x18016d5a4  jmp     short loc_18016D5A8
0x18016d5a6  xor     ebx, ebx
0x18016d5a8  test    rbx, rbx
0x18016d5ab  jnz     short loc_18016D5D2
0x18016d5ad  mov     rcx, [rsp+58h]; this
0x18016d5b2  mov     ebx, 8007000Eh
0x18016d5b7  mov     r9d, ebx; char *
0x18016d5ba  lea     r8, aSrcEppDlpEndpo_3; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x18016d5c1  mov     edx, 0EAh; void *
0x18016d5c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016d5cb  mov     eax, ebx
0x18016d5cd  jmp     loc_18016D6F8
0x18016d5d2  lea     rsi, [rbx+80h]
0x18016d5d9  mov     r9d, 1F0003h; dwDesiredAccess
0x18016d5df  xor     r8d, r8d; dwFlags
0x18016d5e2  xor     edx, edx; lpName
0x18016d5e4  xor     ecx, ecx; lpEventAttributes
0x18016d5e6  call    cs:__imp_CreateEventExW
0x18016d5ec  mov     rdi, rax
0x18016d5ef  test    rax, rax
0x18016d5f2  jz      short loc_18016D63D
0x18016d5f4  call    cs:__imp_GetLastError
0x18016d5fa  mov     rdx, rdi
0x18016d5fd  mov     rcx, rsi
0x18016d600  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18016d605  movzx   edx, byte ptr [rbx+90h]; bWatchSubtree
0x18016d60c  mov     [rsp+58h+fAsynchronous], 1; unsigned int
0x18016d614  mov     r9, [rsi]; hEvent
0x18016d617  mov     r8d, 10000005h; dwNotifyFilter
0x18016d61d  mov     rcx, [rbx+78h]; hKey
0x18016d621  call    cs:__imp_RegNotifyChangeKeyValue
0x18016d627  test    eax, eax
0x18016d629  jz      short loc_18016D663
0x18016d62b  mov     rcx, [rsp+58h]; this
0x18016d630  mov     r9d, eax; char *
0x18016d633  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18016d638  jmp     loc_18016D6C3
0x18016d63d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18016d642  mov     edi, eax
0x18016d644  test    eax, eax
0x18016d646  jns     short loc_18016D605
0x18016d648  mov     rcx, [rsp+58h]; this
0x18016d64d  mov     r9d, eax; char *
0x18016d650  lea     r8, aSrcEppDlpEndpo_3; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x18016d657  mov     edx, 0EBh; void *
0x18016d65c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016d661  jmp     short loc_18016D6C5
0x18016d663  xor     r8d, r8d; pcbe
0x18016d666  mov     rdx, rbx; pv
0x18016d669  lea     rcx, ?callback@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x18016d670  call    cs:__imp_CreateThreadpoolWait
0x18016d676  mov     rdi, rax
0x18016d679  mov     rsi, [rbx+88h]
0x18016d680  test    rsi, rsi
0x18016d683  jz      short loc_18016D6A1
0x18016d685  lea     rcx, [rsp+58h+var_28]; this
0x18016d68a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18016d68f  mov     rcx, rsi; pwa
0x18016d692  call    ?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z; wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)
0x18016d697  lea     rcx, [rsp+58h+var_28]; this
0x18016d69c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18016d6a1  mov     [rbx+88h], rdi
0x18016d6a8  test    rdi, rdi
0x18016d6ab  jnz     short loc_18016D6D1
0x18016d6ad  mov     rcx, [rsp+58h]; this
0x18016d6b2  lea     r8, aSrcEppDlpEndpo_3; "src\\epp\\Dlp\\EndpointDlp\\inc\\wil\\r"...
0x18016d6b9  mov     edx, 0F1h; void *
0x18016d6be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18016d6c3  mov     edi, eax
0x18016d6c5  mov     rcx, rbx; this
0x18016d6c8  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x18016d6cd  mov     eax, edi
0x18016d6cf  jmp     short loc_18016D6F8
0x18016d6d1  mov     rdx, rbx
0x18016d6d4  mov     rcx, r14
0x18016d6d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18016d6dc  mov     rcx, [r14]
0x18016d6df  xor     r8d, r8d; pftTimeout
0x18016d6e2  mov     rdx, [rcx+80h]; h
0x18016d6e9  mov     rcx, [rcx+88h]; pwa
0x18016d6f0  call    cs:__imp_SetThreadpoolWait
0x18016d6f6  xor     eax, eax
0x18016d6f8  mov     rbx, [rsp+58h+arg_10]
0x18016d6fd  add     rsp, 40h
0x18016d701  pop     r14
0x18016d703  pop     rdi
0x18016d704  pop     rsi
0x18016d705  retn
```
