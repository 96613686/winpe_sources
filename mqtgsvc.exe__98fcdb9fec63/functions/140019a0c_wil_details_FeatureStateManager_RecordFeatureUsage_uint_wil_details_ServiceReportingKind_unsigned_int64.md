# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140019a0c`
- end: `0x140019acf`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `195`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x14001b140`

## callees

- `0x140016e8c`
- `0x140017254`
- `0x140017578`
- `0x140017b80`
- `0x140017bc4`
- `0x140019604`
- `0x140019964`
- `0x140019a0c`
- `0x14001bd6c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140019a8d`
- `KERNEL32!CreateThreadpoolTimer` at `0x140019a8d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140019a5b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140019a5b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-38h] BYREF
  char v11; // [rsp+60h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(
         *((wil::details_abi::FeatureStateData **)a1 + 3),
         a2,
         a3,
         a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    v10 = (RTL_SRWLOCK *)(a1 + 32);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x140019a0c  push    rbx
0x140019a0e  push    rbp
0x140019a0f  push    rsi
0x140019a10  push    rdi
0x140019a11  sub     rsp, 38h
0x140019a15  mov     rbx, r9
0x140019a18  mov     esi, r8d
0x140019a1b  mov     ebp, edx
0x140019a1d  mov     rdi, rcx
0x140019a20  cmp     byte ptr [rcx], 0
0x140019a23  jz      loc_140019AC6
0x140019a29  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140019a2e  test    al, al
0x140019a30  jz      loc_140019AC6
0x140019a36  mov     r9, rbx
0x140019a39  mov     r8d, esi
0x140019a3c  mov     edx, ebp
0x140019a3e  mov     rcx, [rdi+18h]
0x140019a42  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140019a47  test    al, al
0x140019a49  jz      short loc_140019AC6
0x140019a4b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140019a50  test    al, al
0x140019a52  jnz     short loc_140019AC6
0x140019a54  lea     rbx, [rdi+20h]
0x140019a58  mov     rcx, rbx; SRWLock
0x140019a5b  call    cs:__imp_AcquireSRWLockExclusive
0x140019a61  mov     [rsp+58h+var_38], rbx
0x140019a66  cmp     byte ptr [rdi+41h], 0
0x140019a6a  jnz     short loc_140019ABB
0x140019a6c  lea     rbx, [rdi+30h]
0x140019a70  cmp     qword ptr [rbx], 0
0x140019a74  jnz     short loc_140019AA8
0x140019a76  lea     rcx, [rsp+58h+arg_0]; this
0x140019a7b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140019a80  xor     r8d, r8d; pcbe
0x140019a83  mov     rdx, rdi; pv
0x140019a86  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140019a8d  call    cs:__imp_CreateThreadpoolTimer
0x140019a93  mov     rdx, rax
0x140019a96  mov     rcx, rbx
0x140019a99  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140019a9e  lea     rcx, [rsp+58h+arg_0]; this
0x140019aa3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140019aa8  mov     r8d, 493E0h
0x140019aae  lea     rdx, [rdi+41h]
0x140019ab2  mov     rcx, rbx
0x140019ab5  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140019aba  nop
0x140019abb  lea     rcx, [rsp+58h+var_38]
0x140019ac0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140019ac5  nop
0x140019ac6  add     rsp, 38h
0x140019aca  pop     rdi
0x140019acb  pop     rsi
0x140019acc  pop     rbp
0x140019acd  pop     rbx
0x140019ace  retn
```
