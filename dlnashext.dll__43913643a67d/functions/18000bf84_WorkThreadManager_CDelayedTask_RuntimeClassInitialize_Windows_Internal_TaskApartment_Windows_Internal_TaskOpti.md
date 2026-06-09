# WorkThreadManager::CDelayedTask::RuntimeClassInitialize(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,ulong,Windows::Internal::IComPoolTask *)

- ea: `0x18000bf84`
- end: `0x18000c0d4`
- name: `?RuntimeClassInitialize@CDelayedTask@WorkThreadManager@@QEAAJW4TaskApartment@Internal@Windows@@W4TaskOptions@45@KKPEAUIComPoolTask@45@@Z`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030a50`

## callees

- `0x180005f60`
- `0x180009740`
- `0x18000bf84`
- `0x18000c0dc`
- `0x18000c130`
- `0x18000c548`
- `0x18000c5bc`
- `0x180011954`
- `0x1800316ac`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c033`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c033`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0c3`

## string_xrefs

- `0x18000c002`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000c04f`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CDelayedTask::RuntimeClassInitialize(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  WorkThreadManager::TaskData *v9; // rax
  unsigned int v10; // edx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v13; // r9
  int v14; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  WorkThreadManager::TaskData *v17; // [rsp+70h] [rbp+8h] BYREF

  v9 = (WorkThreadManager::TaskData *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v14 = 0;
    v9 = (WorkThreadManager::TaskData *)WorkThreadManager::TaskData::TaskData(v9, a2, a3, a4);
  }
  v17 = v9;
  wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
    a1 + 32,
    &v17);
  if ( v17 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v17, v10);
  if ( *(_QWORD *)(a1 + 32) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        _lambda_c517a792861221b2815f232f7f0c7973_::_lambda_invoker_cdecl_,
                        (PVOID)a1,
                        0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      a1 + 24,
      ThreadpoolTimer);
    if ( *(_QWORD *)(a1 + 24) )
    {
      v17 = (WorkThreadManager::TaskData *)(-10000LL * a5);
      pftDueTime = (struct _FILETIME)v17;
      if ( *(_QWORD *)(a1 + 40) != a1 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        v17 = *(WorkThreadManager::TaskData **)(a1 + 40);
        *(_QWORD *)(a1 + 40) = a1;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      }
      SetThreadpoolTimer(*(PTP_TIMER *)(a1 + 24), &pftDueTime, 0, 0);
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x19C,
               (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
               v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v14);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000bf84  push    rbx
0x18000bf86  push    rbp
0x18000bf87  push    rsi
0x18000bf88  push    rdi
0x18000bf89  sub     rsp, 48h
0x18000bf8d  mov     ebp, edx
0x18000bf8f  mov     rbx, rcx
0x18000bf92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf99  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000bf9e  mov     edi, r9d
0x18000bfa1  mov     esi, r8d
0x18000bfa4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bfa9  test    rax, rax
0x18000bfac  jz      short loc_18000BFD4
0x18000bfae  mov     r10, [rsp+68h+arg_28]
0x18000bfb6  mov     r9d, edi
0x18000bfb9  mov     [rsp+68h+var_40], r10
0x18000bfbe  mov     r8d, esi
0x18000bfc1  mov     edx, ebp
0x18000bfc3  mov     qword ptr [rsp+68h+var_48], 0; int
0x18000bfcc  mov     rcx, rax
0x18000bfcf  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x18000bfd4  lea     rdx, [rsp+68h+arg_0]
0x18000bfd9  mov     [rsp+68h+arg_0], rax
0x18000bfde  lea     rcx, [rbx+20h]
0x18000bfe2  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x18000bfe7  mov     rcx, [rsp+68h+arg_0]; this
0x18000bfec  test    rcx, rcx
0x18000bfef  jz      short loc_18000BFF6
0x18000bff1  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000bff6  cmp     qword ptr [rbx+20h], 0
0x18000bffb  jnz     short loc_18000C022
0x18000bffd  mov     rcx, [rsp+68h]; this
0x18000c002  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000c009  mov     ebx, 8007000Eh
0x18000c00e  mov     edx, 191h; void *
0x18000c013  mov     r9d, ebx; char *
0x18000c016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c01b  mov     eax, ebx
0x18000c01d  jmp     loc_18000C0CB
0x18000c022  xor     r8d, r8d; pcbe
0x18000c025  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c517a792861221b2815f232f7f0c7973_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c02c  mov     rdx, rbx; pv
0x18000c02f  lea     rdi, [rbx+18h]
0x18000c033  call    cs:__imp_CreateThreadpoolTimer
0x18000c039  mov     rdx, rax
0x18000c03c  mov     rcx, rdi
0x18000c03f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000c044  cmp     qword ptr [rdi], 0
0x18000c048  jnz     short loc_18000C062
0x18000c04a  mov     rcx, [rsp+68h]; this
0x18000c04f  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000c056  mov     edx, 19Ch; void *
0x18000c05b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c060  jmp     short loc_18000C0CB
0x18000c062  mov     eax, [rsp+68h+arg_20]
0x18000c069  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000c070  mov     rcx, rax
0x18000c073  mov     dword ptr [rsp+68h+arg_0], eax
0x18000c077  shr     rcx, 20h
0x18000c07b  mov     dword ptr [rsp+68h+arg_0+4], ecx
0x18000c07f  mov     rax, [rsp+68h+arg_0]
0x18000c084  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000c089  cmp     [rbx+28h], rbx
0x18000c08d  jz      short loc_18000C0B5
0x18000c08f  mov     rax, [rbx]
0x18000c092  mov     rcx, rbx
0x18000c095  mov     rax, [rax+8]
0x18000c099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09e  mov     rax, [rbx+28h]
0x18000c0a2  lea     rcx, [rsp+68h+arg_0]
0x18000c0a7  mov     [rsp+68h+arg_0], rax
0x18000c0ac  mov     [rbx+28h], rbx
0x18000c0b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c0b5  mov     rcx, [rdi]; pti
0x18000c0b8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c0bd  xor     r9d, r9d; msWindowLength
0x18000c0c0  xor     r8d, r8d; msPeriod
0x18000c0c3  call    cs:__imp_SetThreadpoolTimer
0x18000c0c9  xor     eax, eax
0x18000c0cb  add     rsp, 48h
0x18000c0cf  pop     rdi
0x18000c0d0  pop     rsi
0x18000c0d1  pop     rbp
0x18000c0d2  pop     rbx
0x18000c0d3  retn
```
