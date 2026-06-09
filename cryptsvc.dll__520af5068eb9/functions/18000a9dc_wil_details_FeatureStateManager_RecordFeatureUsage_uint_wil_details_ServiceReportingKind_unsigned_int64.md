# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a9dc`
- end: `0x18000aab2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `214`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000ce40`

## callees

- `0x18000a9dc`
- `0x18000aab8`
- `0x18000ab44`
- `0x18000ab64`
- `0x18000af7c`
- `0x18000afb0`
- `0x1800143a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa6a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aa6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000aa4e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // rsi
  wil *v9; // rcx
  char v10; // bl
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(RTL_SRWLOCK **)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(wil::details_abi::FeatureStateData **)(a1 + 24));
LABEL_5:
    if ( !wil::ProcessShutdownInProgress(v9) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(
        (_QWORD *)(a1 + 48),
        (_BYTE *)(a1 + 65),
        (void *)a1);
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24));
    v11 = v8;
    v10 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    if ( v10 )
      goto LABEL_5;
  }
}

```

## disassembly

```asm
0x18000a9dc  mov     [rsp+arg_8], rbx
0x18000a9e1  mov     [rsp+arg_10], rbp
0x18000a9e6  push    rsi
0x18000a9e7  push    rdi
0x18000a9e8  push    r14
0x18000a9ea  sub     rsp, 20h
0x18000a9ee  cmp     byte ptr [rcx], 0
0x18000a9f1  mov     rbp, r9
0x18000a9f4  mov     ebx, r8d
0x18000a9f7  mov     r14d, edx
0x18000a9fa  mov     rdi, rcx
0x18000a9fd  jz      short loc_18000AA54
0x18000a9ff  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aa04  test    al, al
0x18000aa06  jz      short loc_18000AA54
0x18000aa08  mov     rsi, [rdi+18h]
0x18000aa0c  cmp     ebx, 0FEh
0x18000aa12  jnz     loc_18000AA98
0x18000aa18  mov     rcx, rsi; this
0x18000aa1b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000aa20  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000aa25  test    al, al
0x18000aa27  jnz     short loc_18000AA54
0x18000aa29  lea     rbx, [rdi+20h]
0x18000aa2d  mov     rcx, rbx; SRWLock
0x18000aa30  call    cs:__imp_AcquireSRWLockExclusive
0x18000aa36  lea     rdx, [rdi+41h]
0x18000aa3a  mov     r8, rdi
0x18000aa3d  lea     rcx, [rdi+30h]
0x18000aa41  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000aa46  test    rbx, rbx
0x18000aa49  jz      short loc_18000AA54
0x18000aa4b  mov     rcx, rbx; SRWLock
0x18000aa4e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000aa54  mov     rbx, [rsp+38h+arg_8]
0x18000aa59  mov     rbp, [rsp+38h+arg_10]
0x18000aa5e  add     rsp, 20h
0x18000aa62  pop     r14
0x18000aa64  pop     rdi
0x18000aa65  pop     rsi
0x18000aa66  retn
0x18000aa67  mov     rcx, rsi; SRWLock
0x18000aa6a  call    cs:__imp_AcquireSRWLockExclusive
0x18000aa70  mov     r9, rbp
0x18000aa73  mov     [rsp+38h+arg_0], rsi
0x18000aa78  mov     r8d, ebx
0x18000aa7b  mov     edx, r14d
0x18000aa7e  mov     rcx, rsi
0x18000aa81  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000aa86  lea     rcx, [rsp+38h+arg_0]
0x18000aa8b  mov     bl, al
0x18000aa8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000aa92  test    bl, bl
0x18000aa94  jnz     short loc_18000AA20
0x18000aa96  jmp     short loc_18000AA54
0x18000aa98  cmp     ebx, 0C8h
0x18000aa9e  jb      short loc_18000AA67
0x18000aaa0  cmp     ebx, 100h
0x18000aaa6  jl      short loc_18000AA54
0x18000aaa8  cmp     ebx, 200h
0x18000aaae  jnb     short loc_18000AA54
0x18000aab0  jmp     short loc_18000AA67
```
