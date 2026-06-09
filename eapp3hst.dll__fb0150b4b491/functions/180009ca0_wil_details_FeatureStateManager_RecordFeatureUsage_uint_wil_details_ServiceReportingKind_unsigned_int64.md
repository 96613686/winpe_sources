# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009ca0`
- end: `0x180009d7a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000b520`

## callees

- `0x18000508c`
- `0x180005f54`
- `0x180007038`
- `0x18000986c`
- `0x180009ca0`
- `0x180009d80`
- `0x180009e9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009cfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009cfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d41`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = (RTL_SRWLOCK *)(a1 + 32);
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
0x180009ca0  mov     [rsp+arg_8], rbx
0x180009ca5  mov     [rsp+arg_10], rbp
0x180009caa  push    rsi
0x180009cab  push    rdi
0x180009cac  push    r14
0x180009cae  sub     rsp, 20h
0x180009cb2  mov     rbp, r9
0x180009cb5  mov     ebx, r8d
0x180009cb8  mov     r14d, edx
0x180009cbb  mov     rdi, rcx
0x180009cbe  cmp     byte ptr [rcx], 0
0x180009cc1  jz      loc_180009D67
0x180009cc7  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009ccc  test    al, al
0x180009cce  jz      loc_180009D67
0x180009cd4  mov     rsi, [rdi+18h]
0x180009cd8  cmp     ebx, 0FEh
0x180009cde  jz      short loc_180009D29
0x180009ce0  cmp     ebx, 0C8h
0x180009ce6  jb      short loc_180009CF8
0x180009ce8  cmp     ebx, 100h
0x180009cee  jl      short loc_180009D67
0x180009cf0  cmp     ebx, 200h
0x180009cf6  jnb     short loc_180009D67
0x180009cf8  mov     rcx, rsi; SRWLock
0x180009cfb  call    cs:__imp_AcquireSRWLockExclusive
0x180009d01  mov     [rsp+38h+arg_0], rsi
0x180009d06  mov     r9, rbp
0x180009d09  mov     r8d, ebx
0x180009d0c  mov     edx, r14d
0x180009d0f  mov     rcx, rsi
0x180009d12  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009d17  mov     bl, al
0x180009d19  lea     rcx, [rsp+38h+arg_0]
0x180009d1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009d23  test    bl, bl
0x180009d25  jz      short loc_180009D67
0x180009d27  jmp     short loc_180009D31
0x180009d29  mov     rcx, rsi; this
0x180009d2c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009d31  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180009d36  test    al, al
0x180009d38  jnz     short loc_180009D67
0x180009d3a  lea     rbx, [rdi+20h]
0x180009d3e  mov     rcx, rbx; SRWLock
0x180009d41  call    cs:__imp_AcquireSRWLockExclusive
0x180009d47  mov     [rsp+38h+arg_0], rbx
0x180009d4c  lea     rdx, [rdi+41h]
0x180009d50  lea     rcx, [rdi+30h]
0x180009d54  mov     r8, rdi
0x180009d57  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x180009d5c  lea     rcx, [rsp+38h+arg_0]
0x180009d61  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009d66  nop
0x180009d67  mov     rbx, [rsp+38h+arg_8]
0x180009d6c  mov     rbp, [rsp+38h+arg_10]
0x180009d71  add     rsp, 20h
0x180009d75  pop     r14
0x180009d77  pop     rdi
0x180009d78  pop     rsi
0x180009d79  retn
```
