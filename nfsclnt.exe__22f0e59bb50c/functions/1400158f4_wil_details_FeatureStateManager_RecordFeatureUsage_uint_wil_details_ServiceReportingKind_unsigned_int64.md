# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1400158f4`
- end: `0x140015a02`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1400171f0`

## callees

- `0x140013de4`
- `0x140013e98`
- `0x1400158f4`
- `0x140015a40`
- `0x140015a74`
- `0x140015aac`
- `0x140019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400159a0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400159ef`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400159a0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400159ef`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015952`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400159d9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015952`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400159d9`

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
0x1400158f4  push    rbx
0x1400158f6  push    rbp
0x1400158f7  push    rsi
0x1400158f8  push    rdi
0x1400158f9  push    r14
0x1400158fb  push    r15
0x1400158fd  sub     rsp, 28h
0x140015901  cmp     byte ptr [rcx], 0
0x140015904  mov     r15, r9
0x140015907  mov     ebx, r8d
0x14001590a  mov     r14d, edx
0x14001590d  mov     rsi, rcx
0x140015910  jz      loc_1400159F5
0x140015916  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001591b  test    al, al
0x14001591d  jz      loc_1400159F5
0x140015923  mov     rdi, [rsi+18h]
0x140015927  cmp     ebx, 0FEh
0x14001592d  jz      short loc_1400159AC
0x14001592f  cmp     ebx, 0C8h
0x140015935  jb      short loc_14001594F
0x140015937  cmp     ebx, 100h
0x14001593d  jl      loc_1400159F5
0x140015943  cmp     ebx, 200h
0x140015949  jnb     loc_1400159F5
0x14001594f  mov     rcx, rdi; SRWLock
0x140015952  call    cs:__imp_AcquireSRWLockExclusive
0x140015958  cmp     ebx, 7
0x14001595b  ja      short loc_140015967
0x14001595d  mov     eax, 0CCh
0x140015962  bt      eax, ebx
0x140015965  jb      short loc_140015987
0x140015967  lea     eax, [rbx-100h]
0x14001596d  cmp     eax, 7Fh
0x140015970  jbe     short loc_140015987
0x140015972  mov     r9d, r15d
0x140015975  lea     rcx, [rdi+48h]
0x140015979  mov     r8d, r14d
0x14001597c  mov     edx, ebx
0x14001597e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140015983  mov     bl, al
0x140015985  jmp     short loc_140015998
0x140015987  mov     r8d, r14d
0x14001598a  lea     rcx, [rdi+8]
0x14001598e  mov     edx, ebx
0x140015990  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140015995  mov     bl, [rdi+40h]
0x140015998  test    rdi, rdi
0x14001599b  jz      short loc_1400159A6
0x14001599d  mov     rcx, rdi; SRWLock
0x1400159a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1400159a6  test    bl, bl
0x1400159a8  jz      short loc_1400159F5
0x1400159aa  jmp     short loc_1400159B4
0x1400159ac  mov     rcx, rdi; SRWLock
0x1400159af  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400159b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400159bb  jnz     short loc_1400159F5
0x1400159bd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400159c4  test    rax, rax
0x1400159c7  jz      short loc_1400159D2
0x1400159c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400159ce  test    al, al
0x1400159d0  jnz     short loc_1400159F5
0x1400159d2  lea     rbx, [rsi+20h]
0x1400159d6  mov     rcx, rbx; SRWLock
0x1400159d9  call    cs:__imp_AcquireSRWLockExclusive
0x1400159df  mov     rcx, rsi; pv
0x1400159e2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1400159e7  test    rbx, rbx
0x1400159ea  jz      short loc_1400159F5
0x1400159ec  mov     rcx, rbx; SRWLock
0x1400159ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1400159f5  add     rsp, 28h
0x1400159f9  pop     r15
0x1400159fb  pop     r14
0x1400159fd  pop     rdi
0x1400159fe  pop     rsi
0x1400159ff  pop     rbp
0x140015a00  pop     rbx
0x140015a01  retn
```
