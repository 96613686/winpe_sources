# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180010090`
- end: `0x18001019e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800111d0`

## callees

- `0x18000e24c`
- `0x18000e300`
- `0x180010090`
- `0x1800101a4`
- `0x1800101d8`
- `0x180010210`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800100ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010175`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800100ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010175`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001013c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001018b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001013c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001018b`

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
0x180010090  push    rbx
0x180010092  push    rbp
0x180010093  push    rsi
0x180010094  push    rdi
0x180010095  push    r14
0x180010097  push    r15
0x180010099  sub     rsp, 28h
0x18001009d  cmp     byte ptr [rcx], 0
0x1800100a0  mov     r15, r9
0x1800100a3  mov     ebx, r8d
0x1800100a6  mov     r14d, edx
0x1800100a9  mov     rsi, rcx
0x1800100ac  jz      loc_180010191
0x1800100b2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800100b7  test    al, al
0x1800100b9  jz      loc_180010191
0x1800100bf  mov     rdi, [rsi+18h]
0x1800100c3  cmp     ebx, 0FEh
0x1800100c9  jz      short loc_180010148
0x1800100cb  cmp     ebx, 0C8h
0x1800100d1  jb      short loc_1800100EB
0x1800100d3  cmp     ebx, 100h
0x1800100d9  jl      loc_180010191
0x1800100df  cmp     ebx, 200h
0x1800100e5  jnb     loc_180010191
0x1800100eb  mov     rcx, rdi; SRWLock
0x1800100ee  call    cs:__imp_AcquireSRWLockExclusive
0x1800100f4  cmp     ebx, 7
0x1800100f7  ja      short loc_180010103
0x1800100f9  mov     eax, 0CCh
0x1800100fe  bt      eax, ebx
0x180010101  jb      short loc_180010123
0x180010103  lea     eax, [rbx-100h]
0x180010109  cmp     eax, 7Fh
0x18001010c  jbe     short loc_180010123
0x18001010e  mov     r9d, r15d
0x180010111  lea     rcx, [rdi+48h]
0x180010115  mov     r8d, r14d
0x180010118  mov     edx, ebx
0x18001011a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001011f  mov     bl, al
0x180010121  jmp     short loc_180010134
0x180010123  mov     r8d, r14d
0x180010126  lea     rcx, [rdi+8]
0x18001012a  mov     edx, ebx
0x18001012c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180010131  mov     bl, [rdi+40h]
0x180010134  test    rdi, rdi
0x180010137  jz      short loc_180010142
0x180010139  mov     rcx, rdi; SRWLock
0x18001013c  call    cs:__imp_ReleaseSRWLockExclusive
0x180010142  test    bl, bl
0x180010144  jz      short loc_180010191
0x180010146  jmp     short loc_180010150
0x180010148  mov     rcx, rdi; SRWLock
0x18001014b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180010150  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180010157  jnz     short loc_180010191
0x180010159  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180010160  test    rax, rax
0x180010163  jz      short loc_18001016E
0x180010165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001016a  test    al, al
0x18001016c  jnz     short loc_180010191
0x18001016e  lea     rbx, [rsi+20h]
0x180010172  mov     rcx, rbx; SRWLock
0x180010175  call    cs:__imp_AcquireSRWLockExclusive
0x18001017b  mov     rcx, rsi; pv
0x18001017e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180010183  test    rbx, rbx
0x180010186  jz      short loc_180010191
0x180010188  mov     rcx, rbx; SRWLock
0x18001018b  call    cs:__imp_ReleaseSRWLockExclusive
0x180010191  add     rsp, 28h
0x180010195  pop     r15
0x180010197  pop     r14
0x180010199  pop     rdi
0x18001019a  pop     rsi
0x18001019b  pop     rbp
0x18001019c  pop     rbx
0x18001019d  retn
```
