# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140008884`
- end: `0x140008993`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000a9d0`

## callees

- `0x140006930`
- `0x1400069e4`
- `0x140008884`
- `0x1400089d4`
- `0x140008a08`
- `0x140008a40`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400088e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008969`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400088e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008930`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000897f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008930`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000897f`

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
0x140008884  push    rbx
0x140008886  push    rbp
0x140008887  push    rsi
0x140008888  push    rdi
0x140008889  push    r14
0x14000888b  push    r15
0x14000888d  sub     rsp, 28h
0x140008891  mov     r15, r9
0x140008894  mov     ebx, r8d
0x140008897  mov     r14d, edx
0x14000889a  mov     rsi, rcx
0x14000889d  cmp     byte ptr [rcx], 0
0x1400088a0  jz      loc_140008986
0x1400088a6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400088ab  test    al, al
0x1400088ad  jz      loc_140008986
0x1400088b3  mov     rdi, [rsi+18h]
0x1400088b7  cmp     ebx, 0FEh
0x1400088bd  jz      short loc_14000893C
0x1400088bf  cmp     ebx, 0C8h
0x1400088c5  jb      short loc_1400088DF
0x1400088c7  cmp     ebx, 100h
0x1400088cd  jl      loc_140008986
0x1400088d3  cmp     ebx, 200h
0x1400088d9  jnb     loc_140008986
0x1400088df  mov     rcx, rdi; SRWLock
0x1400088e2  call    cs:__imp_AcquireSRWLockExclusive
0x1400088e8  cmp     ebx, 7
0x1400088eb  ja      short loc_1400088F7
0x1400088ed  mov     eax, 0CCh
0x1400088f2  bt      eax, ebx
0x1400088f5  jb      short loc_140008917
0x1400088f7  lea     eax, [rbx-100h]
0x1400088fd  cmp     eax, 7Fh
0x140008900  jbe     short loc_140008917
0x140008902  mov     r9d, r15d
0x140008905  lea     rcx, [rdi+48h]
0x140008909  mov     r8d, r14d
0x14000890c  mov     edx, ebx
0x14000890e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008913  mov     bl, al
0x140008915  jmp     short loc_140008928
0x140008917  mov     r8d, r14d
0x14000891a  mov     edx, ebx
0x14000891c  lea     rcx, [rdi+8]
0x140008920  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008925  mov     bl, [rdi+40h]
0x140008928  test    rdi, rdi
0x14000892b  jz      short loc_140008936
0x14000892d  mov     rcx, rdi; SRWLock
0x140008930  call    cs:__imp_ReleaseSRWLockExclusive
0x140008936  test    bl, bl
0x140008938  jz      short loc_140008986
0x14000893a  jmp     short loc_140008944
0x14000893c  mov     rcx, rdi; SRWLock
0x14000893f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140008944  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000894b  jnz     short loc_140008986
0x14000894d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008954  test    rax, rax
0x140008957  jz      short loc_140008962
0x140008959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000895e  test    al, al
0x140008960  jnz     short loc_140008986
0x140008962  lea     rbx, [rsi+20h]
0x140008966  mov     rcx, rbx; SRWLock
0x140008969  call    cs:__imp_AcquireSRWLockExclusive
0x14000896f  mov     rcx, rsi; pv
0x140008972  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140008977  test    rbx, rbx
0x14000897a  jz      short loc_140008986
0x14000897c  mov     rcx, rbx; SRWLock
0x14000897f  call    cs:__imp_ReleaseSRWLockExclusive
0x140008985  nop
0x140008986  add     rsp, 28h
0x14000898a  pop     r15
0x14000898c  pop     r14
0x14000898e  pop     rdi
0x14000898f  pop     rsi
0x140008990  pop     rbp
0x140008991  pop     rbx
0x140008992  retn
```
