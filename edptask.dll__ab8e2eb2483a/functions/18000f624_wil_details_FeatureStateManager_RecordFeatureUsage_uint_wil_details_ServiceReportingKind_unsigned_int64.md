# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f624`
- end: `0x18000f733`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180011810`

## callees

- `0x180008400`
- `0x180008578`
- `0x18000f624`
- `0x18000f774`
- `0x18000f7a8`
- `0x18000f7e0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f6d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f71f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f6d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f71f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f682`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f709`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f682`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f709`

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

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1) )
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
0x18000f624  push    rbx
0x18000f626  push    rbp
0x18000f627  push    rsi
0x18000f628  push    rdi
0x18000f629  push    r14
0x18000f62b  push    r15
0x18000f62d  sub     rsp, 28h
0x18000f631  mov     r15, r9
0x18000f634  mov     ebx, r8d
0x18000f637  mov     r14d, edx
0x18000f63a  mov     rsi, rcx
0x18000f63d  cmp     byte ptr [rcx], 0
0x18000f640  jz      loc_18000F726
0x18000f646  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f64b  test    al, al
0x18000f64d  jz      loc_18000F726
0x18000f653  mov     rdi, [rsi+18h]
0x18000f657  cmp     ebx, 0FEh
0x18000f65d  jz      short loc_18000F6DC
0x18000f65f  cmp     ebx, 0C8h
0x18000f665  jb      short loc_18000F67F
0x18000f667  cmp     ebx, 100h
0x18000f66d  jl      loc_18000F726
0x18000f673  cmp     ebx, 200h
0x18000f679  jnb     loc_18000F726
0x18000f67f  mov     rcx, rdi; SRWLock
0x18000f682  call    cs:__imp_AcquireSRWLockExclusive
0x18000f688  cmp     ebx, 7
0x18000f68b  ja      short loc_18000F697
0x18000f68d  mov     eax, 0CCh
0x18000f692  bt      eax, ebx
0x18000f695  jb      short loc_18000F6B7
0x18000f697  lea     eax, [rbx-100h]
0x18000f69d  cmp     eax, 7Fh
0x18000f6a0  jbe     short loc_18000F6B7
0x18000f6a2  mov     r9d, r15d
0x18000f6a5  lea     rcx, [rdi+48h]
0x18000f6a9  mov     r8d, r14d
0x18000f6ac  mov     edx, ebx
0x18000f6ae  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f6b3  mov     bl, al
0x18000f6b5  jmp     short loc_18000F6C8
0x18000f6b7  mov     r8d, r14d
0x18000f6ba  mov     edx, ebx
0x18000f6bc  lea     rcx, [rdi+8]
0x18000f6c0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f6c5  mov     bl, [rdi+40h]
0x18000f6c8  test    rdi, rdi
0x18000f6cb  jz      short loc_18000F6D6
0x18000f6cd  mov     rcx, rdi; SRWLock
0x18000f6d0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f6d6  test    bl, bl
0x18000f6d8  jz      short loc_18000F726
0x18000f6da  jmp     short loc_18000F6E4
0x18000f6dc  mov     rcx, rdi; SRWLock
0x18000f6df  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f6e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f6eb  jnz     short loc_18000F726
0x18000f6ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f6f4  test    rax, rax
0x18000f6f7  jz      short loc_18000F702
0x18000f6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6fe  test    al, al
0x18000f700  jnz     short loc_18000F726
0x18000f702  lea     rbx, [rsi+20h]
0x18000f706  mov     rcx, rbx; SRWLock
0x18000f709  call    cs:__imp_AcquireSRWLockExclusive
0x18000f70f  mov     rcx, rsi; pv
0x18000f712  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000f717  test    rbx, rbx
0x18000f71a  jz      short loc_18000F726
0x18000f71c  mov     rcx, rbx; SRWLock
0x18000f71f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f725  nop
0x18000f726  add     rsp, 28h
0x18000f72a  pop     r15
0x18000f72c  pop     r14
0x18000f72e  pop     rdi
0x18000f72f  pop     rsi
0x18000f730  pop     rbp
0x18000f731  pop     rbx
0x18000f732  retn
```
