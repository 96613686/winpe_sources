# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180022f84`
- end: `0x180023093`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180024470`

## callees

- `0x180017564`
- `0x1800176dc`
- `0x180022f84`
- `0x1800230d4`
- `0x180023108`
- `0x180023140`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022fe2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023069`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022fe2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023069`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023030`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002307f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023030`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002307f`

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
0x180022f84  push    rbx
0x180022f86  push    rbp
0x180022f87  push    rsi
0x180022f88  push    rdi
0x180022f89  push    r14
0x180022f8b  push    r15
0x180022f8d  sub     rsp, 28h
0x180022f91  mov     r15, r9
0x180022f94  mov     ebx, r8d
0x180022f97  mov     r14d, edx
0x180022f9a  mov     rsi, rcx
0x180022f9d  cmp     byte ptr [rcx], 0
0x180022fa0  jz      loc_180023086
0x180022fa6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180022fab  test    al, al
0x180022fad  jz      loc_180023086
0x180022fb3  mov     rdi, [rsi+18h]
0x180022fb7  cmp     ebx, 0FEh
0x180022fbd  jz      short loc_18002303C
0x180022fbf  cmp     ebx, 0C8h
0x180022fc5  jb      short loc_180022FDF
0x180022fc7  cmp     ebx, 100h
0x180022fcd  jl      loc_180023086
0x180022fd3  cmp     ebx, 200h
0x180022fd9  jnb     loc_180023086
0x180022fdf  mov     rcx, rdi; SRWLock
0x180022fe2  call    cs:__imp_AcquireSRWLockExclusive
0x180022fe8  cmp     ebx, 7
0x180022feb  ja      short loc_180022FF7
0x180022fed  mov     eax, 0CCh
0x180022ff2  bt      eax, ebx
0x180022ff5  jb      short loc_180023017
0x180022ff7  lea     eax, [rbx-100h]
0x180022ffd  cmp     eax, 7Fh
0x180023000  jbe     short loc_180023017
0x180023002  mov     r9d, r15d
0x180023005  lea     rcx, [rdi+48h]
0x180023009  mov     r8d, r14d
0x18002300c  mov     edx, ebx
0x18002300e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180023013  mov     bl, al
0x180023015  jmp     short loc_180023028
0x180023017  mov     r8d, r14d
0x18002301a  mov     edx, ebx
0x18002301c  lea     rcx, [rdi+8]
0x180023020  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180023025  mov     bl, [rdi+40h]
0x180023028  test    rdi, rdi
0x18002302b  jz      short loc_180023036
0x18002302d  mov     rcx, rdi; SRWLock
0x180023030  call    cs:__imp_ReleaseSRWLockExclusive
0x180023036  test    bl, bl
0x180023038  jz      short loc_180023086
0x18002303a  jmp     short loc_180023044
0x18002303c  mov     rcx, rdi; SRWLock
0x18002303f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180023044  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002304b  jnz     short loc_180023086
0x18002304d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180023054  test    rax, rax
0x180023057  jz      short loc_180023062
0x180023059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002305e  test    al, al
0x180023060  jnz     short loc_180023086
0x180023062  lea     rbx, [rsi+20h]
0x180023066  mov     rcx, rbx; SRWLock
0x180023069  call    cs:__imp_AcquireSRWLockExclusive
0x18002306f  mov     rcx, rsi; pv
0x180023072  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180023077  test    rbx, rbx
0x18002307a  jz      short loc_180023086
0x18002307c  mov     rcx, rbx; SRWLock
0x18002307f  call    cs:__imp_ReleaseSRWLockExclusive
0x180023085  nop
0x180023086  add     rsp, 28h
0x18002308a  pop     r15
0x18002308c  pop     r14
0x18002308e  pop     rdi
0x18002308f  pop     rsi
0x180023090  pop     rbp
0x180023091  pop     rbx
0x180023092  retn
```
