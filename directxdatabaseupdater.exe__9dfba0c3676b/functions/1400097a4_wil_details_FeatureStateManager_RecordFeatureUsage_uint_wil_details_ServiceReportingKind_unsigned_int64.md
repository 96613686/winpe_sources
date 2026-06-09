# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1400097a4`
- end: `0x14000987e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14000d4b0`

## callees

- `0x140004094`
- `0x140005e18`
- `0x140006d68`
- `0x14000942c`
- `0x1400097a4`
- `0x140009884`
- `0x140009984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400097ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009845`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400097ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009845`

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
0x1400097a4  mov     [rsp+arg_8], rbx
0x1400097a9  mov     [rsp+arg_10], rbp
0x1400097ae  push    rsi
0x1400097af  push    rdi
0x1400097b0  push    r14
0x1400097b2  sub     rsp, 20h
0x1400097b6  mov     rbp, r9
0x1400097b9  mov     ebx, r8d
0x1400097bc  mov     r14d, edx
0x1400097bf  mov     rdi, rcx
0x1400097c2  cmp     byte ptr [rcx], 0
0x1400097c5  jz      loc_14000986B
0x1400097cb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400097d0  test    al, al
0x1400097d2  jz      loc_14000986B
0x1400097d8  mov     rsi, [rdi+18h]
0x1400097dc  cmp     ebx, 0FEh
0x1400097e2  jz      short loc_14000982D
0x1400097e4  cmp     ebx, 0C8h
0x1400097ea  jb      short loc_1400097FC
0x1400097ec  cmp     ebx, 100h
0x1400097f2  jl      short loc_14000986B
0x1400097f4  cmp     ebx, 200h
0x1400097fa  jnb     short loc_14000986B
0x1400097fc  mov     rcx, rsi; SRWLock
0x1400097ff  call    cs:__imp_AcquireSRWLockExclusive
0x140009805  mov     [rsp+38h+arg_0], rsi
0x14000980a  mov     r9, rbp
0x14000980d  mov     r8d, ebx
0x140009810  mov     edx, r14d
0x140009813  mov     rcx, rsi
0x140009816  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000981b  mov     bl, al
0x14000981d  lea     rcx, [rsp+38h+arg_0]
0x140009822  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140009827  test    bl, bl
0x140009829  jz      short loc_14000986B
0x14000982b  jmp     short loc_140009835
0x14000982d  mov     rcx, rsi; this
0x140009830  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140009835  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000983a  test    al, al
0x14000983c  jnz     short loc_14000986B
0x14000983e  lea     rbx, [rdi+20h]
0x140009842  mov     rcx, rbx; SRWLock
0x140009845  call    cs:__imp_AcquireSRWLockExclusive
0x14000984b  mov     [rsp+38h+arg_0], rbx
0x140009850  lea     rdx, [rdi+41h]
0x140009854  lea     rcx, [rdi+30h]
0x140009858  mov     r8, rdi
0x14000985b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x140009860  lea     rcx, [rsp+38h+arg_0]
0x140009865  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000986a  nop
0x14000986b  mov     rbx, [rsp+38h+arg_8]
0x140009870  mov     rbp, [rsp+38h+arg_10]
0x140009875  add     rsp, 20h
0x140009879  pop     r14
0x14000987b  pop     rdi
0x14000987c  pop     rsi
0x14000987d  retn
```
