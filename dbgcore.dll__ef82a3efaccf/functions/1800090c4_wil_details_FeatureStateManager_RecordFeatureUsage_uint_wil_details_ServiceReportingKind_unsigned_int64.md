# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800090c4`
- end: `0x1800091dc`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b7e0`

## callees

- `0x18000657c`
- `0x180006630`
- `0x1800090c4`
- `0x18000921c`
- `0x180009250`
- `0x180009288`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000912b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000912b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800091c8`

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
  __int64 v10; // rcx
  char v11; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v10)) )
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
      v11 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v11 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4,
              -2);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v11 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800090c4  push    rbx
0x1800090c6  push    rbp
0x1800090c7  push    rsi
0x1800090c8  push    rdi
0x1800090c9  push    r14
0x1800090cb  push    r15
0x1800090cd  sub     rsp, 38h
0x1800090d1  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800090da  mov     r15, r9
0x1800090dd  mov     ebx, r8d
0x1800090e0  mov     r14d, edx
0x1800090e3  mov     rsi, rcx
0x1800090e6  cmp     byte ptr [rcx], 0
0x1800090e9  jz      loc_1800091CF
0x1800090ef  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800090f4  test    al, al
0x1800090f6  jz      loc_1800091CF
0x1800090fc  mov     rdi, [rsi+18h]
0x180009100  cmp     ebx, 0FEh
0x180009106  jz      short loc_180009185
0x180009108  cmp     ebx, 0C8h
0x18000910e  jb      short loc_180009128
0x180009110  cmp     ebx, 100h
0x180009116  jl      loc_1800091CF
0x18000911c  cmp     ebx, 200h
0x180009122  jnb     loc_1800091CF
0x180009128  mov     rcx, rdi; SRWLock
0x18000912b  call    cs:__imp_AcquireSRWLockExclusive
0x180009131  cmp     ebx, 7
0x180009134  ja      short loc_180009140
0x180009136  mov     eax, 0CCh
0x18000913b  bt      eax, ebx
0x18000913e  jb      short loc_180009160
0x180009140  lea     eax, [rbx-100h]
0x180009146  cmp     eax, 7Fh
0x180009149  jbe     short loc_180009160
0x18000914b  mov     r9d, r15d
0x18000914e  lea     rcx, [rdi+48h]
0x180009152  mov     r8d, r14d
0x180009155  mov     edx, ebx
0x180009157  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000915c  mov     bl, al
0x18000915e  jmp     short loc_180009171
0x180009160  mov     r8d, r14d
0x180009163  mov     edx, ebx
0x180009165  lea     rcx, [rdi+8]
0x180009169  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000916e  mov     bl, [rdi+40h]
0x180009171  test    rdi, rdi
0x180009174  jz      short loc_18000917F
0x180009176  mov     rcx, rdi; SRWLock
0x180009179  call    cs:__imp_ReleaseSRWLockExclusive
0x18000917f  test    bl, bl
0x180009181  jz      short loc_1800091CF
0x180009183  jmp     short loc_18000918D
0x180009185  mov     rcx, rdi; SRWLock
0x180009188  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000918d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180009194  jnz     short loc_1800091CF
0x180009196  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000919d  test    rax, rax
0x1800091a0  jz      short loc_1800091AB
0x1800091a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a7  test    al, al
0x1800091a9  jnz     short loc_1800091CF
0x1800091ab  lea     rbx, [rsi+20h]
0x1800091af  mov     rcx, rbx; SRWLock
0x1800091b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800091b8  mov     rcx, rsi; pv
0x1800091bb  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800091c0  test    rbx, rbx
0x1800091c3  jz      short loc_1800091CF
0x1800091c5  mov     rcx, rbx; SRWLock
0x1800091c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091ce  nop
0x1800091cf  add     rsp, 38h
0x1800091d3  pop     r15
0x1800091d5  pop     r14
0x1800091d7  pop     rdi
0x1800091d8  pop     rsi
0x1800091d9  pop     rbp
0x1800091da  pop     rbx
0x1800091db  retn
```
