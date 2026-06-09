# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800060dc`
- end: `0x180006153`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180007780`

## callees

- `0x180002920`
- `0x180003884`
- `0x1800041f4`
- `0x180005d1c`
- `0x180006034`
- `0x1800060dc`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180006123`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006123`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  _BYTE *v9; // [rsp+50h] [rbp+8h] BYREF

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
    v9 = a1 + 32;
    wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x1800060dc  push    rbx
0x1800060de  push    rbp
0x1800060df  push    rsi
0x1800060e0  push    rdi
0x1800060e1  sub     rsp, 28h
0x1800060e5  mov     rbx, r9
0x1800060e8  mov     esi, r8d
0x1800060eb  mov     ebp, edx
0x1800060ed  mov     rdi, rcx
0x1800060f0  cmp     byte ptr [rcx], 0
0x1800060f3  jz      short loc_18000614A
0x1800060f5  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800060fa  test    al, al
0x1800060fc  jz      short loc_18000614A
0x1800060fe  mov     r9, rbx
0x180006101  mov     r8d, esi
0x180006104  mov     edx, ebp
0x180006106  mov     rcx, [rdi+18h]
0x18000610a  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000610f  test    al, al
0x180006111  jz      short loc_18000614A
0x180006113  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180006118  test    al, al
0x18000611a  jnz     short loc_18000614A
0x18000611c  lea     rbx, [rdi+20h]
0x180006120  mov     rcx, rbx; SRWLock
0x180006123  call    cs:__imp_AcquireSRWLockExclusive
0x180006129  mov     [rsp+48h+arg_0], rbx
0x18000612e  lea     rdx, [rdi+41h]
0x180006132  lea     rcx, [rdi+30h]
0x180006136  mov     r8, rdi
0x180006139  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000613e  nop
0x18000613f  lea     rcx, [rsp+48h+arg_0]
0x180006144  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006149  nop
0x18000614a  add     rsp, 28h
0x18000614e  pop     rdi
0x18000614f  pop     rsi
0x180006150  pop     rbp
0x180006151  pop     rbx
0x180006152  retn
```
