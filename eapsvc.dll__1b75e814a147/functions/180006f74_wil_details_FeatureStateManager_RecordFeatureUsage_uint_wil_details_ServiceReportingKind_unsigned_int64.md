# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006f74`
- end: `0x180007083`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009510`

## callees

- `0x180004e64`
- `0x180004fdc`
- `0x180006f74`
- `0x180007104`
- `0x180007138`
- `0x180007170`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007059`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007020`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000706f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007020`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000706f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rdi
  int v9; // eax
  char v10; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      wil::details::FeatureStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)a1);
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), a3 <= 7) && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x180006f74  push    rbx
0x180006f76  push    rbp
0x180006f77  push    rsi
0x180006f78  push    rdi
0x180006f79  push    r14
0x180006f7b  push    r15
0x180006f7d  sub     rsp, 28h
0x180006f81  mov     r15, r9
0x180006f84  mov     ebx, r8d
0x180006f87  mov     r14d, edx
0x180006f8a  mov     rsi, rcx
0x180006f8d  cmp     byte ptr [rcx], 0
0x180006f90  jz      loc_180007076
0x180006f96  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006f9b  test    al, al
0x180006f9d  jz      loc_180007076
0x180006fa3  mov     rdi, [rsi+18h]
0x180006fa7  cmp     ebx, 0FEh
0x180006fad  jz      short loc_18000702C
0x180006faf  cmp     ebx, 0C8h
0x180006fb5  jb      short loc_180006FCF
0x180006fb7  cmp     ebx, 100h
0x180006fbd  jl      loc_180007076
0x180006fc3  cmp     ebx, 200h
0x180006fc9  jnb     loc_180007076
0x180006fcf  mov     rcx, rdi; SRWLock
0x180006fd2  call    cs:__imp_AcquireSRWLockExclusive
0x180006fd8  cmp     ebx, 7
0x180006fdb  ja      short loc_180006FE7
0x180006fdd  mov     eax, 0CCh
0x180006fe2  bt      eax, ebx
0x180006fe5  jb      short loc_180007007
0x180006fe7  lea     eax, [rbx-100h]
0x180006fed  cmp     eax, 7Fh
0x180006ff0  jbe     short loc_180007007
0x180006ff2  mov     r9d, r15d
0x180006ff5  lea     rcx, [rdi+48h]
0x180006ff9  mov     r8d, r14d
0x180006ffc  mov     edx, ebx
0x180006ffe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007003  mov     bl, al
0x180007005  jmp     short loc_180007018
0x180007007  mov     r8d, r14d
0x18000700a  mov     edx, ebx
0x18000700c  lea     rcx, [rdi+8]
0x180007010  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007015  mov     bl, [rdi+40h]
0x180007018  test    rdi, rdi
0x18000701b  jz      short loc_180007026
0x18000701d  mov     rcx, rdi; SRWLock
0x180007020  call    cs:__imp_ReleaseSRWLockExclusive
0x180007026  test    bl, bl
0x180007028  jz      short loc_180007076
0x18000702a  jmp     short loc_180007034
0x18000702c  mov     rcx, rdi; SRWLock
0x18000702f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007034  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000703b  jnz     short loc_180007076
0x18000703d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007044  test    rax, rax
0x180007047  jz      short loc_180007052
0x180007049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704e  test    al, al
0x180007050  jnz     short loc_180007076
0x180007052  lea     rbx, [rsi+20h]
0x180007056  mov     rcx, rbx; SRWLock
0x180007059  call    cs:__imp_AcquireSRWLockExclusive
0x18000705f  mov     rcx, rsi; pv
0x180007062  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007067  test    rbx, rbx
0x18000706a  jz      short loc_180007076
0x18000706c  mov     rcx, rbx; SRWLock
0x18000706f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007075  nop
0x180007076  add     rsp, 28h
0x18000707a  pop     r15
0x18000707c  pop     r14
0x18000707e  pop     rdi
0x18000707f  pop     rsi
0x180007080  pop     rbp
0x180007081  pop     rbx
0x180007082  retn
```
