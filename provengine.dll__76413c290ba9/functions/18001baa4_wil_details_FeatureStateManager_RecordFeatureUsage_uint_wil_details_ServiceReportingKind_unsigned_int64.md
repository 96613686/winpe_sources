# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001baa4`
- end: `0x18001bbb3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180020770`

## callees

- `0x180013544`
- `0x1800135f8`
- `0x18001baa4`
- `0x18001bbbc`
- `0x18001bbf0`
- `0x18001bc28`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bb89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bb9f`

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
0x18001baa4  push    rbx
0x18001baa6  push    rbp
0x18001baa7  push    rsi
0x18001baa8  push    rdi
0x18001baa9  push    r14
0x18001baab  push    r15
0x18001baad  sub     rsp, 28h
0x18001bab1  mov     r15, r9
0x18001bab4  mov     ebx, r8d
0x18001bab7  mov     r14d, edx
0x18001baba  mov     rsi, rcx
0x18001babd  cmp     byte ptr [rcx], 0
0x18001bac0  jz      loc_18001BBA6
0x18001bac6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001bacb  test    al, al
0x18001bacd  jz      loc_18001BBA6
0x18001bad3  mov     rdi, [rsi+18h]
0x18001bad7  cmp     ebx, 0FEh
0x18001badd  jz      short loc_18001BB5C
0x18001badf  cmp     ebx, 0C8h
0x18001bae5  jb      short loc_18001BAFF
0x18001bae7  cmp     ebx, 100h
0x18001baed  jl      loc_18001BBA6
0x18001baf3  cmp     ebx, 200h
0x18001baf9  jnb     loc_18001BBA6
0x18001baff  mov     rcx, rdi; SRWLock
0x18001bb02  call    cs:__imp_AcquireSRWLockExclusive
0x18001bb08  cmp     ebx, 7
0x18001bb0b  ja      short loc_18001BB17
0x18001bb0d  mov     eax, 0CCh
0x18001bb12  bt      eax, ebx
0x18001bb15  jb      short loc_18001BB37
0x18001bb17  lea     eax, [rbx-100h]
0x18001bb1d  cmp     eax, 7Fh
0x18001bb20  jbe     short loc_18001BB37
0x18001bb22  mov     r9d, r15d
0x18001bb25  lea     rcx, [rdi+48h]
0x18001bb29  mov     r8d, r14d
0x18001bb2c  mov     edx, ebx
0x18001bb2e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001bb33  mov     bl, al
0x18001bb35  jmp     short loc_18001BB48
0x18001bb37  mov     r8d, r14d
0x18001bb3a  mov     edx, ebx
0x18001bb3c  lea     rcx, [rdi+8]
0x18001bb40  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001bb45  mov     bl, [rdi+40h]
0x18001bb48  test    rdi, rdi
0x18001bb4b  jz      short loc_18001BB56
0x18001bb4d  mov     rcx, rdi; SRWLock
0x18001bb50  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bb56  test    bl, bl
0x18001bb58  jz      short loc_18001BBA6
0x18001bb5a  jmp     short loc_18001BB64
0x18001bb5c  mov     rcx, rdi; SRWLock
0x18001bb5f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001bb64  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001bb6b  jnz     short loc_18001BBA6
0x18001bb6d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001bb74  test    rax, rax
0x18001bb77  jz      short loc_18001BB82
0x18001bb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb7e  test    al, al
0x18001bb80  jnz     short loc_18001BBA6
0x18001bb82  lea     rbx, [rsi+20h]
0x18001bb86  mov     rcx, rbx; SRWLock
0x18001bb89  call    cs:__imp_AcquireSRWLockExclusive
0x18001bb8f  mov     rcx, rsi; pv
0x18001bb92  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001bb97  test    rbx, rbx
0x18001bb9a  jz      short loc_18001BBA6
0x18001bb9c  mov     rcx, rbx; SRWLock
0x18001bb9f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bba5  nop
0x18001bba6  add     rsp, 28h
0x18001bbaa  pop     r15
0x18001bbac  pop     r14
0x18001bbae  pop     rdi
0x18001bbaf  pop     rsi
0x18001bbb0  pop     rbp
0x18001bbb1  pop     rbx
0x18001bbb2  retn
```
