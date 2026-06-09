# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000fb84`
- end: `0x18000fcc7`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180015940`

## callees

- `0x18000adb0`
- `0x18000af64`
- `0x18000fb84`
- `0x18000fd44`
- `0x18000fd7c`
- `0x18000fdb4`
- `0x180024010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fbf1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fc84`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fbf1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fc84`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fc45`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fca0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fc45`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fca0`

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
0x18000fb84  mov     [rsp+arg_0], rbx
0x18000fb89  mov     [rsp+arg_8], rbp
0x18000fb8e  mov     [rsp+arg_10], rsi
0x18000fb93  push    rdi
0x18000fb94  push    r14
0x18000fb96  push    r15
0x18000fb98  sub     rsp, 20h
0x18000fb9c  mov     r15, r9
0x18000fb9f  mov     ebx, r8d
0x18000fba2  mov     r14d, edx
0x18000fba5  mov     rsi, rcx
0x18000fba8  cmp     byte ptr [rcx], 0
0x18000fbab  jz      loc_18000FCAD
0x18000fbb1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000fbb6  test    al, al
0x18000fbb8  jz      loc_18000FCAD
0x18000fbbe  mov     rdi, [rsi+18h]
0x18000fbc2  cmp     ebx, 0FEh
0x18000fbc8  jz      loc_18000FC57
0x18000fbce  cmp     ebx, 0C8h
0x18000fbd4  jb      short loc_18000FBEE
0x18000fbd6  cmp     ebx, 100h
0x18000fbdc  jl      loc_18000FCAD
0x18000fbe2  cmp     ebx, 200h
0x18000fbe8  jnb     loc_18000FCAD
0x18000fbee  mov     rcx, rdi; SRWLock
0x18000fbf1  call    cs:__imp_AcquireSRWLockExclusive
0x18000fbf8  nop     dword ptr [rax+rax+00h]
0x18000fbfd  cmp     ebx, 7
0x18000fc00  ja      short loc_18000FC0C
0x18000fc02  mov     eax, 0CCh
0x18000fc07  bt      eax, ebx
0x18000fc0a  jb      short loc_18000FC2C
0x18000fc0c  lea     eax, [rbx-100h]
0x18000fc12  cmp     eax, 7Fh
0x18000fc15  jbe     short loc_18000FC2C
0x18000fc17  lea     rcx, [rdi+48h]
0x18000fc1b  mov     r9d, r15d
0x18000fc1e  mov     r8d, r14d
0x18000fc21  mov     edx, ebx
0x18000fc23  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000fc28  mov     bl, al
0x18000fc2a  jmp     short loc_18000FC3D
0x18000fc2c  mov     r8d, r14d
0x18000fc2f  mov     edx, ebx
0x18000fc31  lea     rcx, [rdi+8]
0x18000fc35  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000fc3a  mov     bl, [rdi+40h]
0x18000fc3d  test    rdi, rdi
0x18000fc40  jz      short loc_18000FC51
0x18000fc42  mov     rcx, rdi; SRWLock
0x18000fc45  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc4c  nop     dword ptr [rax+rax+00h]
0x18000fc51  test    bl, bl
0x18000fc53  jz      short loc_18000FCAD
0x18000fc55  jmp     short loc_18000FC5F
0x18000fc57  mov     rcx, rdi; SRWLock
0x18000fc5a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000fc5f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000fc66  jnz     short loc_18000FCAD
0x18000fc68  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000fc6f  test    rax, rax
0x18000fc72  jz      short loc_18000FC7D
0x18000fc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc79  test    al, al
0x18000fc7b  jnz     short loc_18000FCAD
0x18000fc7d  lea     rbx, [rsi+20h]
0x18000fc81  mov     rcx, rbx; SRWLock
0x18000fc84  call    cs:__imp_AcquireSRWLockExclusive
0x18000fc8b  nop     dword ptr [rax+rax+00h]
0x18000fc90  mov     rcx, rsi; pv
0x18000fc93  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000fc98  test    rbx, rbx
0x18000fc9b  jz      short loc_18000FCAD
0x18000fc9d  mov     rcx, rbx; SRWLock
0x18000fca0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fca7  nop     dword ptr [rax+rax+00h]
0x18000fcac  nop
0x18000fcad  mov     rbx, [rsp+38h+arg_0]
0x18000fcb2  mov     rbp, [rsp+38h+arg_8]
0x18000fcb7  mov     rsi, [rsp+38h+arg_10]
0x18000fcbc  add     rsp, 20h
0x18000fcc0  pop     r15
0x18000fcc2  pop     r14
0x18000fcc4  pop     rdi
0x18000fcc5  retn
```
