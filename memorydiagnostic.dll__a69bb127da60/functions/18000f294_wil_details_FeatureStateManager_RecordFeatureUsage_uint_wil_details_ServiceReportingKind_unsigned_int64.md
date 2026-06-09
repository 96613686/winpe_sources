# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000f294`
- end: `0x18000f3a3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180014b10`

## callees

- `0x18000ac74`
- `0x18000adf4`
- `0x18000f294`
- `0x18000f424`
- `0x18000f458`
- `0x18000f490`
- `0x180023010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f2f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f379`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f2f2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000f379`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f340`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f38f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f340`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000f38f`

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
0x18000f294  push    rbx
0x18000f296  push    rbp
0x18000f297  push    rsi
0x18000f298  push    rdi
0x18000f299  push    r14
0x18000f29b  push    r15
0x18000f29d  sub     rsp, 28h
0x18000f2a1  mov     r15, r9
0x18000f2a4  mov     ebx, r8d
0x18000f2a7  mov     r14d, edx
0x18000f2aa  mov     rsi, rcx
0x18000f2ad  cmp     byte ptr [rcx], 0
0x18000f2b0  jz      loc_18000F396
0x18000f2b6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f2bb  test    al, al
0x18000f2bd  jz      loc_18000F396
0x18000f2c3  mov     rdi, [rsi+18h]
0x18000f2c7  cmp     ebx, 0FEh
0x18000f2cd  jz      short loc_18000F34C
0x18000f2cf  cmp     ebx, 0C8h
0x18000f2d5  jb      short loc_18000F2EF
0x18000f2d7  cmp     ebx, 100h
0x18000f2dd  jl      loc_18000F396
0x18000f2e3  cmp     ebx, 200h
0x18000f2e9  jnb     loc_18000F396
0x18000f2ef  mov     rcx, rdi; SRWLock
0x18000f2f2  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2f8  cmp     ebx, 7
0x18000f2fb  ja      short loc_18000F307
0x18000f2fd  mov     eax, 0CCh
0x18000f302  bt      eax, ebx
0x18000f305  jb      short loc_18000F327
0x18000f307  lea     eax, [rbx-100h]
0x18000f30d  cmp     eax, 7Fh
0x18000f310  jbe     short loc_18000F327
0x18000f312  mov     r9d, r15d
0x18000f315  lea     rcx, [rdi+48h]
0x18000f319  mov     r8d, r14d
0x18000f31c  mov     edx, ebx
0x18000f31e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f323  mov     bl, al
0x18000f325  jmp     short loc_18000F338
0x18000f327  mov     r8d, r14d
0x18000f32a  mov     edx, ebx
0x18000f32c  lea     rcx, [rdi+8]
0x18000f330  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000f335  mov     bl, [rdi+40h]
0x18000f338  test    rdi, rdi
0x18000f33b  jz      short loc_18000F346
0x18000f33d  mov     rcx, rdi; SRWLock
0x18000f340  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f346  test    bl, bl
0x18000f348  jz      short loc_18000F396
0x18000f34a  jmp     short loc_18000F354
0x18000f34c  mov     rcx, rdi; SRWLock
0x18000f34f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f354  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f35b  jnz     short loc_18000F396
0x18000f35d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f364  test    rax, rax
0x18000f367  jz      short loc_18000F372
0x18000f369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f36e  test    al, al
0x18000f370  jnz     short loc_18000F396
0x18000f372  lea     rbx, [rsi+20h]
0x18000f376  mov     rcx, rbx; SRWLock
0x18000f379  call    cs:__imp_AcquireSRWLockExclusive
0x18000f37f  mov     rcx, rsi; pv
0x18000f382  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000f387  test    rbx, rbx
0x18000f38a  jz      short loc_18000F396
0x18000f38c  mov     rcx, rbx; SRWLock
0x18000f38f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f395  nop
0x18000f396  add     rsp, 28h
0x18000f39a  pop     r15
0x18000f39c  pop     r14
0x18000f39e  pop     rdi
0x18000f39f  pop     rsi
0x18000f3a0  pop     rbp
0x18000f3a1  pop     rbx
0x18000f3a2  retn
```
