# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180011534`
- end: `0x180011642`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180012600`

## callees

- `0x180010c2c`
- `0x180010ce0`
- `0x180011534`
- `0x180011648`
- `0x18001167c`
- `0x1800116b4`
- `0x180014010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800115e0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001162f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800115e0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001162f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011592`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011619`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011592`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011619`

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
0x180011534  push    rbx
0x180011536  push    rbp
0x180011537  push    rsi
0x180011538  push    rdi
0x180011539  push    r14
0x18001153b  push    r15
0x18001153d  sub     rsp, 28h
0x180011541  cmp     byte ptr [rcx], 0
0x180011544  mov     r15, r9
0x180011547  mov     ebx, r8d
0x18001154a  mov     r14d, edx
0x18001154d  mov     rsi, rcx
0x180011550  jz      loc_180011635
0x180011556  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001155b  test    al, al
0x18001155d  jz      loc_180011635
0x180011563  mov     rdi, [rsi+18h]
0x180011567  cmp     ebx, 0FEh
0x18001156d  jz      short loc_1800115EC
0x18001156f  cmp     ebx, 0C8h
0x180011575  jb      short loc_18001158F
0x180011577  cmp     ebx, 100h
0x18001157d  jl      loc_180011635
0x180011583  cmp     ebx, 200h
0x180011589  jnb     loc_180011635
0x18001158f  mov     rcx, rdi; SRWLock
0x180011592  call    cs:__imp_AcquireSRWLockExclusive
0x180011598  cmp     ebx, 7
0x18001159b  ja      short loc_1800115A7
0x18001159d  mov     eax, 0CCh
0x1800115a2  bt      eax, ebx
0x1800115a5  jb      short loc_1800115C7
0x1800115a7  lea     eax, [rbx-100h]
0x1800115ad  cmp     eax, 7Fh
0x1800115b0  jbe     short loc_1800115C7
0x1800115b2  mov     r9d, r15d
0x1800115b5  lea     rcx, [rdi+48h]
0x1800115b9  mov     r8d, r14d
0x1800115bc  mov     edx, ebx
0x1800115be  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800115c3  mov     bl, al
0x1800115c5  jmp     short loc_1800115D8
0x1800115c7  mov     r8d, r14d
0x1800115ca  lea     rcx, [rdi+8]
0x1800115ce  mov     edx, ebx
0x1800115d0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800115d5  mov     bl, [rdi+40h]
0x1800115d8  test    rdi, rdi
0x1800115db  jz      short loc_1800115E6
0x1800115dd  mov     rcx, rdi; SRWLock
0x1800115e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800115e6  test    bl, bl
0x1800115e8  jz      short loc_180011635
0x1800115ea  jmp     short loc_1800115F4
0x1800115ec  mov     rcx, rdi; SRWLock
0x1800115ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800115f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800115fb  jnz     short loc_180011635
0x1800115fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011604  test    rax, rax
0x180011607  jz      short loc_180011612
0x180011609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160e  test    al, al
0x180011610  jnz     short loc_180011635
0x180011612  lea     rbx, [rsi+20h]
0x180011616  mov     rcx, rbx; SRWLock
0x180011619  call    cs:__imp_AcquireSRWLockExclusive
0x18001161f  mov     rcx, rsi; pv
0x180011622  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180011627  test    rbx, rbx
0x18001162a  jz      short loc_180011635
0x18001162c  mov     rcx, rbx; SRWLock
0x18001162f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011635  add     rsp, 28h
0x180011639  pop     r15
0x18001163b  pop     r14
0x18001163d  pop     rdi
0x18001163e  pop     rsi
0x18001163f  pop     rbp
0x180011640  pop     rbx
0x180011641  retn
```
