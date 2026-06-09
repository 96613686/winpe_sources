# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180023c84`
- end: `0x180023dc6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180025ef0`

## callees

- `0x18001d064`
- `0x18001d224`
- `0x180023c84`
- `0x180023e44`
- `0x180023e7c`
- `0x180023eb4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023da0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023da0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023cf1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d84`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023cf1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023d84`

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
0x180023c84  mov     [rsp+arg_0], rbx
0x180023c89  mov     [rsp+arg_8], rbp
0x180023c8e  mov     [rsp+arg_10], rsi
0x180023c93  push    rdi
0x180023c94  push    r14
0x180023c96  push    r15
0x180023c98  sub     rsp, 20h
0x180023c9c  cmp     byte ptr [rcx], 0
0x180023c9f  mov     r15, r9
0x180023ca2  mov     ebx, r8d
0x180023ca5  mov     r14d, edx
0x180023ca8  mov     rsi, rcx
0x180023cab  jz      loc_180023DAC
0x180023cb1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180023cb6  test    al, al
0x180023cb8  jz      loc_180023DAC
0x180023cbe  mov     rdi, [rsi+18h]
0x180023cc2  cmp     ebx, 0FEh
0x180023cc8  jz      loc_180023D57
0x180023cce  cmp     ebx, 0C8h
0x180023cd4  jb      short loc_180023CEE
0x180023cd6  cmp     ebx, 100h
0x180023cdc  jl      loc_180023DAC
0x180023ce2  cmp     ebx, 200h
0x180023ce8  jnb     loc_180023DAC
0x180023cee  mov     rcx, rdi; SRWLock
0x180023cf1  call    cs:__imp_AcquireSRWLockExclusive
0x180023cf8  nop     dword ptr [rax+rax+00h]
0x180023cfd  cmp     ebx, 7
0x180023d00  ja      short loc_180023D0C
0x180023d02  mov     eax, 0CCh
0x180023d07  bt      eax, ebx
0x180023d0a  jb      short loc_180023D2C
0x180023d0c  lea     eax, [rbx-100h]
0x180023d12  cmp     eax, 7Fh
0x180023d15  jbe     short loc_180023D2C
0x180023d17  lea     rcx, [rdi+48h]
0x180023d1b  mov     r9d, r15d
0x180023d1e  mov     r8d, r14d
0x180023d21  mov     edx, ebx
0x180023d23  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180023d28  mov     bl, al
0x180023d2a  jmp     short loc_180023D3D
0x180023d2c  mov     r8d, r14d
0x180023d2f  lea     rcx, [rdi+8]
0x180023d33  mov     edx, ebx
0x180023d35  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180023d3a  mov     bl, [rdi+40h]
0x180023d3d  test    rdi, rdi
0x180023d40  jz      short loc_180023D51
0x180023d42  mov     rcx, rdi; SRWLock
0x180023d45  call    cs:__imp_ReleaseSRWLockExclusive
0x180023d4c  nop     dword ptr [rax+rax+00h]
0x180023d51  test    bl, bl
0x180023d53  jz      short loc_180023DAC
0x180023d55  jmp     short loc_180023D5F
0x180023d57  mov     rcx, rdi; SRWLock
0x180023d5a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180023d5f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180023d66  jnz     short loc_180023DAC
0x180023d68  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023d6f  test    rax, rax
0x180023d72  jz      short loc_180023D7D
0x180023d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d79  test    al, al
0x180023d7b  jnz     short loc_180023DAC
0x180023d7d  lea     rbx, [rsi+20h]
0x180023d81  mov     rcx, rbx; SRWLock
0x180023d84  call    cs:__imp_AcquireSRWLockExclusive
0x180023d8b  nop     dword ptr [rax+rax+00h]
0x180023d90  mov     rcx, rsi; pv
0x180023d93  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180023d98  test    rbx, rbx
0x180023d9b  jz      short loc_180023DAC
0x180023d9d  mov     rcx, rbx; SRWLock
0x180023da0  call    cs:__imp_ReleaseSRWLockExclusive
0x180023da7  nop     dword ptr [rax+rax+00h]
0x180023dac  mov     rbx, [rsp+38h+arg_0]
0x180023db1  mov     rbp, [rsp+38h+arg_8]
0x180023db6  mov     rsi, [rsp+38h+arg_10]
0x180023dbb  add     rsp, 20h
0x180023dbf  pop     r15
0x180023dc1  pop     r14
0x180023dc3  pop     rdi
0x180023dc4  retn
```
