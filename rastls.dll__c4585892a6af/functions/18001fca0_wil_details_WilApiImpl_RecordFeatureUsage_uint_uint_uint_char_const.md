# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001fca0`
- end: `0x18001fded`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `333`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18001fca0`
- `0x18001fdf4`
- `0x180020d40`
- `0x18002c6dc`
- `0x18002c88c`
- `0x18002c8b0`
- `0x18002c8f8`
- `0x18002c91c`
- `0x18003ba10`
- `0x18003eaac`
- `0x18003f0d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fd00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fd00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001fd68`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001fd68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, unsigned int a2, unsigned int a3)
{
  int v4; // esi
  unsigned int v5; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  int v7; // [rsp+20h] [rbp-48h] BYREF
  __int16 v8; // [rsp+24h] [rbp-44h]
  __int16 v9; // [rsp+26h] [rbp-42h]
  unsigned int v10; // [rsp+28h] [rbp-40h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp-38h] BYREF

  v4 = (int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v5 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      if ( wil::details::g_featureStateManager && !wil::ProcessShutdownInProgress(this) )
      {
        AcquireSRWLockExclusive(&SRWLock);
        v11 = &SRWLock;
        v9 = 0;
        v7 = v4;
        v8 = v5;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back(
          (wil::details_abi::heap_buffer *)((char *)&xmmword_1800A35B8 + 8),
          &v7,
          0xCu);
        if ( !byte_1800A3518 )
        {
          if ( !qword_1800A3510 )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                                &wil::details::g_featureStateManager,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &qword_1800A3510,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)&qword_1800A3510, &byte_1800A3518, 5000);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
    }
    else if ( a3 || v5 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v5,
        a3);
    }
    else
    {
      wil_RtlStagingConfig_RecordFeatureUsage(this, v5, a2 >> 31);
    }
  }
  else
  {
    wil::details::FeatureStateManager::FlushUsage((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager);
  }
}

```

## disassembly

```asm
0x18001fca0  push    rbx
0x18001fca2  push    rbp
0x18001fca3  push    rsi
0x18001fca4  push    rdi
0x18001fca5  sub     rsp, 48h
0x18001fca9  mov     edi, r8d
0x18001fcac  mov     esi, ecx
0x18001fcae  mov     ebx, edx
0x18001fcb0  btr     ebx, 1Fh
0x18001fcb4  test    ecx, ecx
0x18001fcb6  jnz     short loc_18001FCD2
0x18001fcb8  test    r8d, r8d
0x18001fcbb  jnz     short loc_18001FCD2
0x18001fcbd  test    ebx, ebx
0x18001fcbf  jnz     short loc_18001FCD2
0x18001fcc1  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001fcc8  call    ?FlushUsage@FeatureStateManager@details@wil@@QEAAXXZ; wil::details::FeatureStateManager::FlushUsage(void)
0x18001fccd  jmp     loc_18001FDE3
0x18001fcd2  bt      ebx, 1Eh
0x18001fcd6  jnb     loc_18001FDB3
0x18001fcdc  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001fce3  jz      loc_18001FDB1
0x18001fce9  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001fcee  test    al, al
0x18001fcf0  jnz     loc_18001FDB1
0x18001fcf6  lea     rbp, SRWLock
0x18001fcfd  mov     rcx, rbp; SRWLock
0x18001fd00  call    cs:__imp_AcquireSRWLockExclusive
0x18001fd07  nop     dword ptr [rax+rax+00h]
0x18001fd0c  mov     [rsp+68h+var_38], rbp
0x18001fd11  xor     eax, eax
0x18001fd13  mov     [rsp+68h+var_42], ax
0x18001fd18  mov     [rsp+68h+var_48], esi
0x18001fd1c  mov     [rsp+68h+var_44], bx
0x18001fd21  mov     [rsp+68h+var_40], edi
0x18001fd25  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001fd29  lea     rdx, [rsp+68h+var_48]; void *
0x18001fd2e  lea     rcx, xmmword_1800A35B8+8; this
0x18001fd35  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001fd3a  cmp     cs:byte_1800A3518, 0
0x18001fd41  jnz     short loc_18001FDA6
0x18001fd43  cmp     cs:qword_1800A3510, 0
0x18001fd4b  jnz     short loc_18001FD8D
0x18001fd4d  lea     rcx, [rsp+68h+var_48]; this
0x18001fd52  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001fd57  xor     r8d, r8d; pcbe
0x18001fd5a  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001fd61  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001fd68  call    cs:__imp_CreateThreadpoolTimer
0x18001fd6f  nop     dword ptr [rax+rax+00h]
0x18001fd74  mov     rdx, rax
0x18001fd77  lea     rcx, qword_1800A3510
0x18001fd7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001fd83  lea     rcx, [rsp+68h+var_48]; this
0x18001fd88  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001fd8d  mov     r8d, 1388h
0x18001fd93  lea     rdx, byte_1800A3518
0x18001fd9a  lea     rcx, qword_1800A3510
0x18001fda1  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001fda6  lea     rcx, [rsp+68h+var_38]
0x18001fdab  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001fdb0  nop
0x18001fdb1  jmp     short loc_18001FDE3
0x18001fdb3  test    r8d, r8d
0x18001fdb6  jnz     short loc_18001FDCF
0x18001fdb8  cmp     ebx, 0FEh
0x18001fdbe  jz      short loc_18001FDCF
0x18001fdc0  shr     edx, 1Fh
0x18001fdc3  mov     r8d, edx
0x18001fdc6  mov     edx, ebx
0x18001fdc8  call    wil_RtlStagingConfig_RecordFeatureUsage
0x18001fdcd  jmp     short loc_18001FDE3
0x18001fdcf  mov     r9, rdi
0x18001fdd2  mov     r8d, ebx
0x18001fdd5  mov     edx, esi
0x18001fdd7  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001fdde  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001fde3  add     rsp, 48h
0x18001fde7  pop     rdi
0x18001fde8  pop     rsi
0x18001fde9  pop     rbp
0x18001fdea  pop     rbx
0x18001fdeb  retn
```
