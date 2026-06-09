# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000ad74`
- end: `0x18000ae83`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ca10`

## callees

- `0x180009314`
- `0x1800093c8`
- `0x18000ad74`
- `0x18000aec4`
- `0x18000aef8`
- `0x18000af30`
- `0x180017010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae20`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae6f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae20`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ae6f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000add2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ae59`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000add2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ae59`

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
0x18000ad74  push    rbx
0x18000ad76  push    rbp
0x18000ad77  push    rsi
0x18000ad78  push    rdi
0x18000ad79  push    r14
0x18000ad7b  push    r15
0x18000ad7d  sub     rsp, 28h
0x18000ad81  mov     r15, r9
0x18000ad84  mov     ebx, r8d
0x18000ad87  mov     r14d, edx
0x18000ad8a  mov     rsi, rcx
0x18000ad8d  cmp     byte ptr [rcx], 0
0x18000ad90  jz      loc_18000AE76
0x18000ad96  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ad9b  test    al, al
0x18000ad9d  jz      loc_18000AE76
0x18000ada3  mov     rdi, [rsi+18h]
0x18000ada7  cmp     ebx, 0FEh
0x18000adad  jz      short loc_18000AE2C
0x18000adaf  cmp     ebx, 0C8h
0x18000adb5  jb      short loc_18000ADCF
0x18000adb7  cmp     ebx, 100h
0x18000adbd  jl      loc_18000AE76
0x18000adc3  cmp     ebx, 200h
0x18000adc9  jnb     loc_18000AE76
0x18000adcf  mov     rcx, rdi; SRWLock
0x18000add2  call    cs:__imp_AcquireSRWLockExclusive
0x18000add8  cmp     ebx, 7
0x18000addb  ja      short loc_18000ADE7
0x18000addd  mov     eax, 0CCh
0x18000ade2  bt      eax, ebx
0x18000ade5  jb      short loc_18000AE07
0x18000ade7  lea     eax, [rbx-100h]
0x18000aded  cmp     eax, 7Fh
0x18000adf0  jbe     short loc_18000AE07
0x18000adf2  mov     r9d, r15d
0x18000adf5  lea     rcx, [rdi+48h]
0x18000adf9  mov     r8d, r14d
0x18000adfc  mov     edx, ebx
0x18000adfe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ae03  mov     bl, al
0x18000ae05  jmp     short loc_18000AE18
0x18000ae07  mov     r8d, r14d
0x18000ae0a  mov     edx, ebx
0x18000ae0c  lea     rcx, [rdi+8]
0x18000ae10  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ae15  mov     bl, [rdi+40h]
0x18000ae18  test    rdi, rdi
0x18000ae1b  jz      short loc_18000AE26
0x18000ae1d  mov     rcx, rdi; SRWLock
0x18000ae20  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae26  test    bl, bl
0x18000ae28  jz      short loc_18000AE76
0x18000ae2a  jmp     short loc_18000AE34
0x18000ae2c  mov     rcx, rdi; SRWLock
0x18000ae2f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ae34  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ae3b  jnz     short loc_18000AE76
0x18000ae3d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ae44  test    rax, rax
0x18000ae47  jz      short loc_18000AE52
0x18000ae49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4e  test    al, al
0x18000ae50  jnz     short loc_18000AE76
0x18000ae52  lea     rbx, [rsi+20h]
0x18000ae56  mov     rcx, rbx; SRWLock
0x18000ae59  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae5f  mov     rcx, rsi; pv
0x18000ae62  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000ae67  test    rbx, rbx
0x18000ae6a  jz      short loc_18000AE76
0x18000ae6c  mov     rcx, rbx; SRWLock
0x18000ae6f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ae75  nop
0x18000ae76  add     rsp, 28h
0x18000ae7a  pop     r15
0x18000ae7c  pop     r14
0x18000ae7e  pop     rdi
0x18000ae7f  pop     rsi
0x18000ae80  pop     rbp
0x18000ae81  pop     rbx
0x18000ae82  retn
```
