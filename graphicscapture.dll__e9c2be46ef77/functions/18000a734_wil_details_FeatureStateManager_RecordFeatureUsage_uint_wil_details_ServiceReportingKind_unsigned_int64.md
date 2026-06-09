# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a734`
- end: `0x18000a80e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000c0a0`

## callees

- `0x180006b0c`
- `0x180007c28`
- `0x1800085f8`
- `0x18000a378`
- `0x18000a734`
- `0x18000a814`
- `0x18000a92c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a78f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a78f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7d5`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  _BYTE *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  _BYTE *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (_BYTE *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = a1 + 32;
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v11 = v8;
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x18000a734  mov     [rsp+arg_8], rbx
0x18000a739  mov     [rsp+arg_10], rbp
0x18000a73e  push    rsi
0x18000a73f  push    rdi
0x18000a740  push    r14
0x18000a742  sub     rsp, 20h
0x18000a746  mov     rbp, r9
0x18000a749  mov     ebx, r8d
0x18000a74c  mov     r14d, edx
0x18000a74f  mov     rdi, rcx
0x18000a752  cmp     byte ptr [rcx], 0
0x18000a755  jz      loc_18000A7FB
0x18000a75b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a760  test    al, al
0x18000a762  jz      loc_18000A7FB
0x18000a768  mov     rsi, [rdi+18h]
0x18000a76c  cmp     ebx, 0FEh
0x18000a772  jz      short loc_18000A7BD
0x18000a774  cmp     ebx, 0C8h
0x18000a77a  jb      short loc_18000A78C
0x18000a77c  cmp     ebx, 100h
0x18000a782  jl      short loc_18000A7FB
0x18000a784  cmp     ebx, 200h
0x18000a78a  jnb     short loc_18000A7FB
0x18000a78c  mov     rcx, rsi; SRWLock
0x18000a78f  call    cs:__imp_AcquireSRWLockExclusive
0x18000a795  mov     [rsp+38h+arg_0], rsi
0x18000a79a  mov     r9, rbp
0x18000a79d  mov     r8d, ebx
0x18000a7a0  mov     edx, r14d
0x18000a7a3  mov     rcx, rsi
0x18000a7a6  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000a7ab  mov     bl, al
0x18000a7ad  lea     rcx, [rsp+38h+arg_0]
0x18000a7b2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a7b7  test    bl, bl
0x18000a7b9  jz      short loc_18000A7FB
0x18000a7bb  jmp     short loc_18000A7C5
0x18000a7bd  mov     rcx, rsi; this
0x18000a7c0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a7c5  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000a7ca  test    al, al
0x18000a7cc  jnz     short loc_18000A7FB
0x18000a7ce  lea     rbx, [rdi+20h]
0x18000a7d2  mov     rcx, rbx; SRWLock
0x18000a7d5  call    cs:__imp_AcquireSRWLockExclusive
0x18000a7db  mov     [rsp+38h+arg_0], rbx
0x18000a7e0  lea     rdx, [rdi+41h]
0x18000a7e4  lea     rcx, [rdi+30h]
0x18000a7e8  mov     r8, rdi
0x18000a7eb  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000a7f0  lea     rcx, [rsp+38h+arg_0]
0x18000a7f5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a7fa  nop
0x18000a7fb  mov     rbx, [rsp+38h+arg_8]
0x18000a800  mov     rbp, [rsp+38h+arg_10]
0x18000a805  add     rsp, 20h
0x18000a809  pop     r14
0x18000a80b  pop     rdi
0x18000a80c  pop     rsi
0x18000a80d  retn
```
