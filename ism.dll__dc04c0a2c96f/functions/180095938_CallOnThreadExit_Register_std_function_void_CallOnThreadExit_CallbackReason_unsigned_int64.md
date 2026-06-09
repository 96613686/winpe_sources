# CallOnThreadExit::Register(std::function<void (CallOnThreadExit::CallbackReason)>,unsigned __int64 *)

- ea: `0x180095938`
- end: `0x180095ac6`
- name: `?Register@CallOnThreadExit@@YAXV?$function@$$A6AXW4CallbackReason@CallOnThreadExit@@@Z@std@@PEA_K@Z`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180095024`

## callees

- `0x180033c84`
- `0x18003ce4c`
- `0x180081130`
- `0x180082780`
- `0x180095938`
- `0x180095eb0`
- `0x180154fc8`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180095a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180095a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800959e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800959e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800959ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800959ed`
- `msvcp_win!_Mtx_unlock` at `0x180095aa3`
- `msvcp_win!_Mtx_unlock` at `0x180095aa3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180095a5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180095a5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180095a93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180095a93`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180095a2e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180095a2e`

## string_xrefs

- `0x180095a3d`: `onecoreuap\windows\moderncore\inputv2\utilities\callonthreadexit\callonthreadexit.cpp`
- `0x180095a7a`: `onecoreuap\windows\moderncore\inputv2\utilities\callonthreadexit\callonthreadexit.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CallOnThreadExit::Register(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rcx
  HANDLE CurrentProcess; // rbx
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  PTP_WAIT ThreadpoolWait; // rax
  const char *v11; // r9
  struct _TP_WAIT *v12; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a2 = 0;
  std::_Mutex_base::lock((std::_Mutex_base *)qword_180243070);
  std::list<CallOnThreadExit::CallbackData>::_Emplace<>(v4, qword_1802438D8);
  v5 = *(_QWORD *)(qword_1802438D8 + 8) + 16LL;
  if ( v5 != a1 )
  {
    std::_Func_class<void,>::~_Func_class<void,>(*(_QWORD *)(qword_1802438D8 + 8) + 16LL);
    v6 = *(_QWORD *)(a1 + 56);
    if ( v6 )
    {
      if ( v6 == a1 )
      {
        *(_QWORD *)(v5 + 56) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, v5);
        std::_Func_class<void,>::~_Func_class<void,>(a1);
      }
      else
      {
        *(_QWORD *)(v5 + 56) = v6;
        *(_QWORD *)(a1 + 56) = 0;
      }
    }
  }
  *(_QWORD *)(v5 + 64) = ++qword_1802443C8;
  *(_DWORD *)(v5 + 72) = GetCurrentThreadId();
  CurrentProcess = GetCurrentProcess();
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v5 + 80,
    0);
  CurrentThread = GetCurrentThread();
  if ( !DuplicateHandle(CurrentProcess, CurrentThread, CurrentProcess, (LPHANDLE)(v5 + 80), 0, 0, 2u) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\callonthreadexit\\callonthreadexit.cpp",
      v9);
  ThreadpoolWait = CreateThreadpoolWait(CallOnThreadExit::CallOnThreadExitStatic, (PVOID)v5, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    v5 + 88,
    ThreadpoolWait);
  v12 = *(struct _TP_WAIT **)(v5 + 88);
  if ( !v12 )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\callonthreadexit\\callonthreadexit.cpp",
      v11);
  SetThreadpoolWait(v12, *(HANDLE *)(v5 + 80), 0);
  *a2 = *(_QWORD *)(v5 + 64);
  _Mtx_unlock((_Mtx_t)qword_180243070);
  return std::_Func_class<void,>::~_Func_class<void,>(a1);
}

```

## disassembly

```asm
0x180095938  mov     [rsp+arg_10], rbx
0x18009593d  mov     [rsp+arg_0], rcx
0x180095942  push    rsi
0x180095943  push    rdi
0x180095944  push    r12
0x180095946  push    r14
0x180095948  push    r15
0x18009594a  sub     rsp, 40h
0x18009594e  mov     r14, rdx
0x180095951  mov     rsi, rcx
0x180095954  mov     qword ptr [rdx], 0
0x18009595b  lea     r12, qword_180243070
0x180095962  mov     [rsp+68h+arg_8], r12
0x180095967  mov     rcx, r12; this
0x18009596a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18009596f  nop
0x180095970  mov     rdx, cs:qword_1802438D8
0x180095977  call    ??$_Emplace@$$V@?$list@UCallbackData@CallOnThreadExit@@V?$allocator@UCallbackData@CallOnThreadExit@@@std@@@std@@QEAAPEAU?$_List_node@UCallbackData@CallOnThreadExit@@PEAX@1@QEAU21@@Z; std::list<CallOnThreadExit::CallbackData>::_Emplace<>(std::_List_node<CallOnThreadExit::CallbackData,void *> * const)
0x18009597c  mov     rax, cs:qword_1802438D8
0x180095983  mov     rdi, [rax+8]
0x180095987  add     rdi, 10h
0x18009598b  cmp     rdi, rsi
0x18009598e  jz      short loc_1800959CF
0x180095990  mov     rcx, rdi
0x180095993  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180095998  mov     rcx, [rsi+38h]
0x18009599c  test    rcx, rcx
0x18009599f  jz      short loc_1800959CF
0x1800959a1  cmp     rcx, rsi
0x1800959a4  jnz     short loc_1800959C3
0x1800959a6  mov     rax, [rcx]
0x1800959a9  mov     rdx, rdi
0x1800959ac  mov     rax, [rax+8]
0x1800959b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959b5  mov     [rdi+38h], rax
0x1800959b9  mov     rcx, rsi
0x1800959bc  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800959c1  jmp     short loc_1800959CF
0x1800959c3  mov     [rdi+38h], rcx
0x1800959c7  mov     qword ptr [rsi+38h], 0
0x1800959cf  mov     rax, cs:qword_1802443C8
0x1800959d6  inc     rax
0x1800959d9  mov     cs:qword_1802443C8, rax
0x1800959e0  mov     [rdi+40h], rax
0x1800959e4  call    cs:__imp_GetCurrentThreadId
0x1800959ea  mov     [rdi+48h], eax
0x1800959ed  call    cs:__imp_GetCurrentProcess
0x1800959f3  mov     rbx, rax
0x1800959f6  lea     r15, [rdi+50h]
0x1800959fa  xor     edx, edx
0x1800959fc  mov     rcx, r15
0x1800959ff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180095a04  call    cs:__imp_GetCurrentThread
0x180095a0a  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180095a12  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180095a1a  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180095a22  mov     r9, r15; lpTargetHandle
0x180095a25  mov     r8, rbx; hTargetProcessHandle
0x180095a28  mov     rdx, rax; hSourceHandle
0x180095a2b  mov     rcx, rbx; hSourceProcessHandle
0x180095a2e  call    cs:__imp_DuplicateHandle
0x180095a34  mov     rcx, [rsp+68h]; this
0x180095a39  test    eax, eax
0x180095a3b  jnz     short loc_180095A4D
0x180095a3d  lea     r8, aOnecoreuapWind_219; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095a44  lea     edx, [rax+47h]; void *
0x180095a47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095a4d  xor     r8d, r8d; pcbe
0x180095a50  mov     rdx, rdi; pv
0x180095a53  lea     rcx, ?CallOnThreadExitStatic@CallOnThreadExit@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x180095a5a  call    cs:__imp_CreateThreadpoolWait
0x180095a60  mov     rdx, rax
0x180095a63  lea     rcx, [rdi+58h]
0x180095a67  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180095a6c  mov     rax, [rsp+68h]
0x180095a71  mov     rcx, [rdi+58h]; pwa
0x180095a75  test    rcx, rcx
0x180095a78  jnz     short loc_180095A8D
0x180095a7a  lea     r8, aOnecoreuapWind_219; "onecoreuap\\windows\\moderncore\\inputv"...
0x180095a81  lea     edx, [rcx+4Eh]; void *
0x180095a84  mov     rcx, rax; this
0x180095a87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180095a8d  xor     r8d, r8d; pftTimeout
0x180095a90  mov     rdx, [r15]; h
0x180095a93  call    cs:__imp_SetThreadpoolWait
0x180095a99  mov     rax, [rdi+40h]
0x180095a9d  mov     [r14], rax
0x180095aa0  mov     rcx, r12; _Mtx_t
0x180095aa3  call    cs:__imp__Mtx_unlock
0x180095aa9  nop
0x180095aaa  mov     rcx, rsi
0x180095aad  mov     rbx, [rsp+68h+arg_10]
0x180095ab5  add     rsp, 40h
0x180095ab9  pop     r15
0x180095abb  pop     r14
0x180095abd  pop     r12
0x180095abf  pop     rdi
0x180095ac0  pop     rsi
0x180095ac1  jmp     ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
```
