# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800058e4`
- end: `0x1800059f2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007340`

## callees

- `0x180003d34`
- `0x180003de8`
- `0x1800058e4`
- `0x180005a30`
- `0x180005a64`
- `0x180005a9c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800059c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800059c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800059df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800059df`

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
0x1800058e4  push    rbx
0x1800058e6  push    rbp
0x1800058e7  push    rsi
0x1800058e8  push    rdi
0x1800058e9  push    r14
0x1800058eb  push    r15
0x1800058ed  sub     rsp, 28h
0x1800058f1  cmp     byte ptr [rcx], 0
0x1800058f4  mov     r15, r9
0x1800058f7  mov     ebx, r8d
0x1800058fa  mov     r14d, edx
0x1800058fd  mov     rsi, rcx
0x180005900  jz      loc_1800059E5
0x180005906  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000590b  test    al, al
0x18000590d  jz      loc_1800059E5
0x180005913  mov     rdi, [rsi+18h]
0x180005917  cmp     ebx, 0FEh
0x18000591d  jz      short loc_18000599C
0x18000591f  cmp     ebx, 0C8h
0x180005925  jb      short loc_18000593F
0x180005927  cmp     ebx, 100h
0x18000592d  jl      loc_1800059E5
0x180005933  cmp     ebx, 200h
0x180005939  jnb     loc_1800059E5
0x18000593f  mov     rcx, rdi; SRWLock
0x180005942  call    cs:__imp_AcquireSRWLockExclusive
0x180005948  cmp     ebx, 7
0x18000594b  ja      short loc_180005957
0x18000594d  mov     eax, 0CCh
0x180005952  bt      eax, ebx
0x180005955  jb      short loc_180005977
0x180005957  lea     eax, [rbx-100h]
0x18000595d  cmp     eax, 7Fh
0x180005960  jbe     short loc_180005977
0x180005962  mov     r9d, r15d
0x180005965  lea     rcx, [rdi+48h]
0x180005969  mov     r8d, r14d
0x18000596c  mov     edx, ebx
0x18000596e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005973  mov     bl, al
0x180005975  jmp     short loc_180005988
0x180005977  mov     r8d, r14d
0x18000597a  lea     rcx, [rdi+8]
0x18000597e  mov     edx, ebx
0x180005980  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005985  mov     bl, [rdi+40h]
0x180005988  test    rdi, rdi
0x18000598b  jz      short loc_180005996
0x18000598d  mov     rcx, rdi; SRWLock
0x180005990  call    cs:__imp_ReleaseSRWLockExclusive
0x180005996  test    bl, bl
0x180005998  jz      short loc_1800059E5
0x18000599a  jmp     short loc_1800059A4
0x18000599c  mov     rcx, rdi; SRWLock
0x18000599f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800059a4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800059ab  jnz     short loc_1800059E5
0x1800059ad  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800059b4  test    rax, rax
0x1800059b7  jz      short loc_1800059C2
0x1800059b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059be  test    al, al
0x1800059c0  jnz     short loc_1800059E5
0x1800059c2  lea     rbx, [rsi+20h]
0x1800059c6  mov     rcx, rbx; SRWLock
0x1800059c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800059cf  mov     rcx, rsi; pv
0x1800059d2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800059d7  test    rbx, rbx
0x1800059da  jz      short loc_1800059E5
0x1800059dc  mov     rcx, rbx; SRWLock
0x1800059df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800059e5  add     rsp, 28h
0x1800059e9  pop     r15
0x1800059eb  pop     r14
0x1800059ed  pop     rdi
0x1800059ee  pop     rsi
0x1800059ef  pop     rbp
0x1800059f0  pop     rbx
0x1800059f1  retn
```
