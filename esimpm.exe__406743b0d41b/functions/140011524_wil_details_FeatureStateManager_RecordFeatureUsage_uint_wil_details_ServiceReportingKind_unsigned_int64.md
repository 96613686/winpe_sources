# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140011524`
- end: `0x140011633`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140013840`

## callees

- `0x14000f594`
- `0x14000f70c`
- `0x140011524`
- `0x1400116b4`
- `0x1400116e8`
- `0x140011720`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400115d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001161f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400115d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001161f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011582`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011609`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011582`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140011609`

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
0x140011524  push    rbx
0x140011526  push    rbp
0x140011527  push    rsi
0x140011528  push    rdi
0x140011529  push    r14
0x14001152b  push    r15
0x14001152d  sub     rsp, 28h
0x140011531  mov     r15, r9
0x140011534  mov     ebx, r8d
0x140011537  mov     r14d, edx
0x14001153a  mov     rsi, rcx
0x14001153d  cmp     byte ptr [rcx], 0
0x140011540  jz      loc_140011626
0x140011546  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001154b  test    al, al
0x14001154d  jz      loc_140011626
0x140011553  mov     rdi, [rsi+18h]
0x140011557  cmp     ebx, 0FEh
0x14001155d  jz      short loc_1400115DC
0x14001155f  cmp     ebx, 0C8h
0x140011565  jb      short loc_14001157F
0x140011567  cmp     ebx, 100h
0x14001156d  jl      loc_140011626
0x140011573  cmp     ebx, 200h
0x140011579  jnb     loc_140011626
0x14001157f  mov     rcx, rdi; SRWLock
0x140011582  call    cs:__imp_AcquireSRWLockExclusive
0x140011588  cmp     ebx, 7
0x14001158b  ja      short loc_140011597
0x14001158d  mov     eax, 0CCh
0x140011592  bt      eax, ebx
0x140011595  jb      short loc_1400115B7
0x140011597  lea     eax, [rbx-100h]
0x14001159d  cmp     eax, 7Fh
0x1400115a0  jbe     short loc_1400115B7
0x1400115a2  mov     r9d, r15d
0x1400115a5  lea     rcx, [rdi+48h]
0x1400115a9  mov     r8d, r14d
0x1400115ac  mov     edx, ebx
0x1400115ae  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400115b3  mov     bl, al
0x1400115b5  jmp     short loc_1400115C8
0x1400115b7  mov     r8d, r14d
0x1400115ba  mov     edx, ebx
0x1400115bc  lea     rcx, [rdi+8]
0x1400115c0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400115c5  mov     bl, [rdi+40h]
0x1400115c8  test    rdi, rdi
0x1400115cb  jz      short loc_1400115D6
0x1400115cd  mov     rcx, rdi; SRWLock
0x1400115d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400115d6  test    bl, bl
0x1400115d8  jz      short loc_140011626
0x1400115da  jmp     short loc_1400115E4
0x1400115dc  mov     rcx, rdi; SRWLock
0x1400115df  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400115e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400115eb  jnz     short loc_140011626
0x1400115ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400115f4  test    rax, rax
0x1400115f7  jz      short loc_140011602
0x1400115f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115fe  test    al, al
0x140011600  jnz     short loc_140011626
0x140011602  lea     rbx, [rsi+20h]
0x140011606  mov     rcx, rbx; SRWLock
0x140011609  call    cs:__imp_AcquireSRWLockExclusive
0x14001160f  mov     rcx, rsi; pv
0x140011612  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140011617  test    rbx, rbx
0x14001161a  jz      short loc_140011626
0x14001161c  mov     rcx, rbx; SRWLock
0x14001161f  call    cs:__imp_ReleaseSRWLockExclusive
0x140011625  nop
0x140011626  add     rsp, 28h
0x14001162a  pop     r15
0x14001162c  pop     r14
0x14001162e  pop     rdi
0x14001162f  pop     rsi
0x140011630  pop     rbp
0x140011631  pop     rbx
0x140011632  retn
```
