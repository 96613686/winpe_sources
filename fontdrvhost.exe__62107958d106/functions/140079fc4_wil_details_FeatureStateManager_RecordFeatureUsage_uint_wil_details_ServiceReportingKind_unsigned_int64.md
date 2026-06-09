# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140079fc4`
- end: `0x14007a09e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14007b310`

## callees

- `0x140071820`
- `0x140075664`
- `0x140077030`
- `0x140078588`
- `0x140079fc4`
- `0x14007a0a4`
- `0x14007a1a4`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14007a01f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14007a065`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14007a01f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14007a065`

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
0x140079fc4  mov     [rsp+arg_8], rbx
0x140079fc9  mov     [rsp+arg_10], rbp
0x140079fce  push    rsi
0x140079fcf  push    rdi
0x140079fd0  push    r14
0x140079fd2  sub     rsp, 20h
0x140079fd6  mov     rbp, r9
0x140079fd9  mov     ebx, r8d
0x140079fdc  mov     r14d, edx
0x140079fdf  mov     rdi, rcx
0x140079fe2  cmp     byte ptr [rcx], 0
0x140079fe5  jz      loc_14007A08B
0x140079feb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140079ff0  test    al, al
0x140079ff2  jz      loc_14007A08B
0x140079ff8  mov     rsi, [rdi+18h]
0x140079ffc  cmp     ebx, 0FEh
0x14007a002  jz      short loc_14007A04D
0x14007a004  cmp     ebx, 0C8h
0x14007a00a  jb      short loc_14007A01C
0x14007a00c  cmp     ebx, 100h
0x14007a012  jl      short loc_14007A08B
0x14007a014  cmp     ebx, 200h
0x14007a01a  jnb     short loc_14007A08B
0x14007a01c  mov     rcx, rsi; SRWLock
0x14007a01f  call    cs:__imp_AcquireSRWLockExclusive
0x14007a025  mov     [rsp+38h+arg_0], rsi
0x14007a02a  mov     r9, rbp
0x14007a02d  mov     r8d, ebx
0x14007a030  mov     edx, r14d
0x14007a033  mov     rcx, rsi
0x14007a036  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14007a03b  mov     bl, al
0x14007a03d  lea     rcx, [rsp+38h+arg_0]
0x14007a042  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007a047  test    bl, bl
0x14007a049  jz      short loc_14007A08B
0x14007a04b  jmp     short loc_14007A055
0x14007a04d  mov     rcx, rsi; this
0x14007a050  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14007a055  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14007a05a  test    al, al
0x14007a05c  jnz     short loc_14007A08B
0x14007a05e  lea     rbx, [rdi+20h]
0x14007a062  mov     rcx, rbx; SRWLock
0x14007a065  call    cs:__imp_AcquireSRWLockExclusive
0x14007a06b  mov     [rsp+38h+arg_0], rbx
0x14007a070  lea     rdx, [rdi+41h]
0x14007a074  lea     rcx, [rdi+30h]
0x14007a078  mov     r8, rdi
0x14007a07b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x14007a080  lea     rcx, [rsp+38h+arg_0]
0x14007a085  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007a08a  nop
0x14007a08b  mov     rbx, [rsp+38h+arg_8]
0x14007a090  mov     rbp, [rsp+38h+arg_10]
0x14007a095  add     rsp, 20h
0x14007a099  pop     r14
0x14007a09b  pop     rdi
0x14007a09c  pop     rsi
0x14007a09d  retn
```
