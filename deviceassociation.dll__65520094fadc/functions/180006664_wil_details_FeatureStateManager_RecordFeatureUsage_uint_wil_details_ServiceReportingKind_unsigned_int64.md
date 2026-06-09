# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006664`
- end: `0x180006772`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007f60`

## callees

- `0x180004b54`
- `0x180004c08`
- `0x180006664`
- `0x1800067b0`
- `0x1800067e4`
- `0x18000681c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000675f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006710`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000675f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006749`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800066c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006749`

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
0x180006664  push    rbx
0x180006666  push    rbp
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  push    r14
0x18000666b  push    r15
0x18000666d  sub     rsp, 28h
0x180006671  cmp     byte ptr [rcx], 0
0x180006674  mov     r15, r9
0x180006677  mov     ebx, r8d
0x18000667a  mov     r14d, edx
0x18000667d  mov     rsi, rcx
0x180006680  jz      loc_180006765
0x180006686  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000668b  test    al, al
0x18000668d  jz      loc_180006765
0x180006693  mov     rdi, [rsi+18h]
0x180006697  cmp     ebx, 0FEh
0x18000669d  jz      short loc_18000671C
0x18000669f  cmp     ebx, 0C8h
0x1800066a5  jb      short loc_1800066BF
0x1800066a7  cmp     ebx, 100h
0x1800066ad  jl      loc_180006765
0x1800066b3  cmp     ebx, 200h
0x1800066b9  jnb     loc_180006765
0x1800066bf  mov     rcx, rdi; SRWLock
0x1800066c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800066c8  cmp     ebx, 7
0x1800066cb  ja      short loc_1800066D7
0x1800066cd  mov     eax, 0CCh
0x1800066d2  bt      eax, ebx
0x1800066d5  jb      short loc_1800066F7
0x1800066d7  lea     eax, [rbx-100h]
0x1800066dd  cmp     eax, 7Fh
0x1800066e0  jbe     short loc_1800066F7
0x1800066e2  mov     r9d, r15d
0x1800066e5  lea     rcx, [rdi+48h]
0x1800066e9  mov     r8d, r14d
0x1800066ec  mov     edx, ebx
0x1800066ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800066f3  mov     bl, al
0x1800066f5  jmp     short loc_180006708
0x1800066f7  mov     r8d, r14d
0x1800066fa  lea     rcx, [rdi+8]
0x1800066fe  mov     edx, ebx
0x180006700  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006705  mov     bl, [rdi+40h]
0x180006708  test    rdi, rdi
0x18000670b  jz      short loc_180006716
0x18000670d  mov     rcx, rdi; SRWLock
0x180006710  call    cs:__imp_ReleaseSRWLockExclusive
0x180006716  test    bl, bl
0x180006718  jz      short loc_180006765
0x18000671a  jmp     short loc_180006724
0x18000671c  mov     rcx, rdi; SRWLock
0x18000671f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006724  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000672b  jnz     short loc_180006765
0x18000672d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006734  test    rax, rax
0x180006737  jz      short loc_180006742
0x180006739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673e  test    al, al
0x180006740  jnz     short loc_180006765
0x180006742  lea     rbx, [rsi+20h]
0x180006746  mov     rcx, rbx; SRWLock
0x180006749  call    cs:__imp_AcquireSRWLockExclusive
0x18000674f  mov     rcx, rsi; pv
0x180006752  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006757  test    rbx, rbx
0x18000675a  jz      short loc_180006765
0x18000675c  mov     rcx, rbx; SRWLock
0x18000675f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006765  add     rsp, 28h
0x180006769  pop     r15
0x18000676b  pop     r14
0x18000676d  pop     rdi
0x18000676e  pop     rsi
0x18000676f  pop     rbp
0x180006770  pop     rbx
0x180006771  retn
```
