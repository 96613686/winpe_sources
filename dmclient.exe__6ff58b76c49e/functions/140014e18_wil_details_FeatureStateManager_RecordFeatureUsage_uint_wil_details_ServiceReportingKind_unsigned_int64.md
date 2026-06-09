# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140014e18`
- end: `0x140014f27`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400167d0`

## callees

- `0x140013728`
- `0x1400137dc`
- `0x140014e18`
- `0x140014f30`
- `0x140014f64`
- `0x140014f9c`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014e76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014efd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014e76`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014efd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014ec4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014f13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014ec4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014f13`

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
0x140014e18  push    rbx
0x140014e1a  push    rbp
0x140014e1b  push    rsi
0x140014e1c  push    rdi
0x140014e1d  push    r14
0x140014e1f  push    r15
0x140014e21  sub     rsp, 28h
0x140014e25  mov     r15, r9
0x140014e28  mov     ebx, r8d
0x140014e2b  mov     r14d, edx
0x140014e2e  mov     rsi, rcx
0x140014e31  cmp     byte ptr [rcx], 0
0x140014e34  jz      loc_140014F1A
0x140014e3a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140014e3f  test    al, al
0x140014e41  jz      loc_140014F1A
0x140014e47  mov     rdi, [rsi+18h]
0x140014e4b  cmp     ebx, 0FEh
0x140014e51  jz      short loc_140014ED0
0x140014e53  cmp     ebx, 0C8h
0x140014e59  jb      short loc_140014E73
0x140014e5b  cmp     ebx, 100h
0x140014e61  jl      loc_140014F1A
0x140014e67  cmp     ebx, 200h
0x140014e6d  jnb     loc_140014F1A
0x140014e73  mov     rcx, rdi; SRWLock
0x140014e76  call    cs:__imp_AcquireSRWLockExclusive
0x140014e7c  cmp     ebx, 7
0x140014e7f  ja      short loc_140014E8B
0x140014e81  mov     eax, 0CCh
0x140014e86  bt      eax, ebx
0x140014e89  jb      short loc_140014EAB
0x140014e8b  lea     eax, [rbx-100h]
0x140014e91  cmp     eax, 7Fh
0x140014e94  jbe     short loc_140014EAB
0x140014e96  mov     r9d, r15d
0x140014e99  lea     rcx, [rdi+48h]
0x140014e9d  mov     r8d, r14d
0x140014ea0  mov     edx, ebx
0x140014ea2  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140014ea7  mov     bl, al
0x140014ea9  jmp     short loc_140014EBC
0x140014eab  mov     r8d, r14d
0x140014eae  mov     edx, ebx
0x140014eb0  lea     rcx, [rdi+8]
0x140014eb4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140014eb9  mov     bl, [rdi+40h]
0x140014ebc  test    rdi, rdi
0x140014ebf  jz      short loc_140014ECA
0x140014ec1  mov     rcx, rdi; SRWLock
0x140014ec4  call    cs:__imp_ReleaseSRWLockExclusive
0x140014eca  test    bl, bl
0x140014ecc  jz      short loc_140014F1A
0x140014ece  jmp     short loc_140014ED8
0x140014ed0  mov     rcx, rdi; SRWLock
0x140014ed3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140014ed8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140014edf  jnz     short loc_140014F1A
0x140014ee1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014ee8  test    rax, rax
0x140014eeb  jz      short loc_140014EF6
0x140014eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ef2  test    al, al
0x140014ef4  jnz     short loc_140014F1A
0x140014ef6  lea     rbx, [rsi+20h]
0x140014efa  mov     rcx, rbx; SRWLock
0x140014efd  call    cs:__imp_AcquireSRWLockExclusive
0x140014f03  mov     rcx, rsi; pv
0x140014f06  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140014f0b  test    rbx, rbx
0x140014f0e  jz      short loc_140014F1A
0x140014f10  mov     rcx, rbx; SRWLock
0x140014f13  call    cs:__imp_ReleaseSRWLockExclusive
0x140014f19  nop
0x140014f1a  add     rsp, 28h
0x140014f1e  pop     r15
0x140014f20  pop     r14
0x140014f22  pop     rdi
0x140014f23  pop     rsi
0x140014f24  pop     rbp
0x140014f25  pop     rbx
0x140014f26  retn
```
