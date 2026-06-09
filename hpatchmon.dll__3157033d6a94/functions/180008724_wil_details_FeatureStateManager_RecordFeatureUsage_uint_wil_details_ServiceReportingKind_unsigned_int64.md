# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008724`
- end: `0x180008833`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c040`

## callees

- `0x180005844`
- `0x1800059bc`
- `0x180008724`
- `0x1800088b4`
- `0x1800088e8`
- `0x180008920`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008782`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008782`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008809`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000881f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000881f`

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
0x180008724  push    rbx
0x180008726  push    rbp
0x180008727  push    rsi
0x180008728  push    rdi
0x180008729  push    r14
0x18000872b  push    r15
0x18000872d  sub     rsp, 28h
0x180008731  mov     r15, r9
0x180008734  mov     ebx, r8d
0x180008737  mov     r14d, edx
0x18000873a  mov     rsi, rcx
0x18000873d  cmp     byte ptr [rcx], 0
0x180008740  jz      loc_180008826
0x180008746  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000874b  test    al, al
0x18000874d  jz      loc_180008826
0x180008753  mov     rdi, [rsi+18h]
0x180008757  cmp     ebx, 0FEh
0x18000875d  jz      short loc_1800087DC
0x18000875f  cmp     ebx, 0C8h
0x180008765  jb      short loc_18000877F
0x180008767  cmp     ebx, 100h
0x18000876d  jl      loc_180008826
0x180008773  cmp     ebx, 200h
0x180008779  jnb     loc_180008826
0x18000877f  mov     rcx, rdi; SRWLock
0x180008782  call    cs:__imp_AcquireSRWLockExclusive
0x180008788  cmp     ebx, 7
0x18000878b  ja      short loc_180008797
0x18000878d  mov     eax, 0CCh
0x180008792  bt      eax, ebx
0x180008795  jb      short loc_1800087B7
0x180008797  lea     eax, [rbx-100h]
0x18000879d  cmp     eax, 7Fh
0x1800087a0  jbe     short loc_1800087B7
0x1800087a2  mov     r9d, r15d
0x1800087a5  lea     rcx, [rdi+48h]
0x1800087a9  mov     r8d, r14d
0x1800087ac  mov     edx, ebx
0x1800087ae  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800087b3  mov     bl, al
0x1800087b5  jmp     short loc_1800087C8
0x1800087b7  mov     r8d, r14d
0x1800087ba  mov     edx, ebx
0x1800087bc  lea     rcx, [rdi+8]
0x1800087c0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800087c5  mov     bl, [rdi+40h]
0x1800087c8  test    rdi, rdi
0x1800087cb  jz      short loc_1800087D6
0x1800087cd  mov     rcx, rdi; SRWLock
0x1800087d0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087d6  test    bl, bl
0x1800087d8  jz      short loc_180008826
0x1800087da  jmp     short loc_1800087E4
0x1800087dc  mov     rcx, rdi; SRWLock
0x1800087df  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800087e4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800087eb  jnz     short loc_180008826
0x1800087ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800087f4  test    rax, rax
0x1800087f7  jz      short loc_180008802
0x1800087f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087fe  test    al, al
0x180008800  jnz     short loc_180008826
0x180008802  lea     rbx, [rsi+20h]
0x180008806  mov     rcx, rbx; SRWLock
0x180008809  call    cs:__imp_AcquireSRWLockExclusive
0x18000880f  mov     rcx, rsi; pv
0x180008812  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008817  test    rbx, rbx
0x18000881a  jz      short loc_180008826
0x18000881c  mov     rcx, rbx; SRWLock
0x18000881f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008825  nop
0x180008826  add     rsp, 28h
0x18000882a  pop     r15
0x18000882c  pop     r14
0x18000882e  pop     rdi
0x18000882f  pop     rsi
0x180008830  pop     rbp
0x180008831  pop     rbx
0x180008832  retn
```
