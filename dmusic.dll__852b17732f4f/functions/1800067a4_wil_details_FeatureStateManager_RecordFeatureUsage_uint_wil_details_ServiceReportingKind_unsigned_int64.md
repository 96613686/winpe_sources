# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800067a4`
- end: `0x1800068b3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008980`

## callees

- `0x180004584`
- `0x1800046fc`
- `0x1800067a4`
- `0x180006934`
- `0x180006968`
- `0x1800069a0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006889`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006802`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006889`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006850`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000689f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006850`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000689f`

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
0x1800067a4  push    rbx
0x1800067a6  push    rbp
0x1800067a7  push    rsi
0x1800067a8  push    rdi
0x1800067a9  push    r14
0x1800067ab  push    r15
0x1800067ad  sub     rsp, 28h
0x1800067b1  mov     r15, r9
0x1800067b4  mov     ebx, r8d
0x1800067b7  mov     r14d, edx
0x1800067ba  mov     rsi, rcx
0x1800067bd  cmp     byte ptr [rcx], 0
0x1800067c0  jz      loc_1800068A6
0x1800067c6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800067cb  test    al, al
0x1800067cd  jz      loc_1800068A6
0x1800067d3  mov     rdi, [rsi+18h]
0x1800067d7  cmp     ebx, 0FEh
0x1800067dd  jz      short loc_18000685C
0x1800067df  cmp     ebx, 0C8h
0x1800067e5  jb      short loc_1800067FF
0x1800067e7  cmp     ebx, 100h
0x1800067ed  jl      loc_1800068A6
0x1800067f3  cmp     ebx, 200h
0x1800067f9  jnb     loc_1800068A6
0x1800067ff  mov     rcx, rdi; SRWLock
0x180006802  call    cs:__imp_AcquireSRWLockExclusive
0x180006808  cmp     ebx, 7
0x18000680b  ja      short loc_180006817
0x18000680d  mov     eax, 0CCh
0x180006812  bt      eax, ebx
0x180006815  jb      short loc_180006837
0x180006817  lea     eax, [rbx-100h]
0x18000681d  cmp     eax, 7Fh
0x180006820  jbe     short loc_180006837
0x180006822  mov     r9d, r15d
0x180006825  lea     rcx, [rdi+48h]
0x180006829  mov     r8d, r14d
0x18000682c  mov     edx, ebx
0x18000682e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006833  mov     bl, al
0x180006835  jmp     short loc_180006848
0x180006837  mov     r8d, r14d
0x18000683a  mov     edx, ebx
0x18000683c  lea     rcx, [rdi+8]
0x180006840  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006845  mov     bl, [rdi+40h]
0x180006848  test    rdi, rdi
0x18000684b  jz      short loc_180006856
0x18000684d  mov     rcx, rdi; SRWLock
0x180006850  call    cs:__imp_ReleaseSRWLockExclusive
0x180006856  test    bl, bl
0x180006858  jz      short loc_1800068A6
0x18000685a  jmp     short loc_180006864
0x18000685c  mov     rcx, rdi; SRWLock
0x18000685f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006864  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000686b  jnz     short loc_1800068A6
0x18000686d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006874  test    rax, rax
0x180006877  jz      short loc_180006882
0x180006879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000687e  test    al, al
0x180006880  jnz     short loc_1800068A6
0x180006882  lea     rbx, [rsi+20h]
0x180006886  mov     rcx, rbx; SRWLock
0x180006889  call    cs:__imp_AcquireSRWLockExclusive
0x18000688f  mov     rcx, rsi; pv
0x180006892  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006897  test    rbx, rbx
0x18000689a  jz      short loc_1800068A6
0x18000689c  mov     rcx, rbx; SRWLock
0x18000689f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068a5  nop
0x1800068a6  add     rsp, 28h
0x1800068aa  pop     r15
0x1800068ac  pop     r14
0x1800068ae  pop     rdi
0x1800068af  pop     rsi
0x1800068b0  pop     rbp
0x1800068b1  pop     rbx
0x1800068b2  retn
```
