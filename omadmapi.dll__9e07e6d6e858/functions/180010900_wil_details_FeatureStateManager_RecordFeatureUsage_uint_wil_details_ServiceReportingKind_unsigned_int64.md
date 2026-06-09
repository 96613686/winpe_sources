# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180010900`
- end: `0x180010a2c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800138d0`

## callees

- `0x18000bd0c`
- `0x18000beb4`
- `0x180010900`
- `0x180010ab4`
- `0x180010aec`
- `0x180010b24`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800109b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010a11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010962`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800109f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010962`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800109f5`

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
0x180010900  push    rbx
0x180010902  push    rbp
0x180010903  push    rsi
0x180010904  push    rdi
0x180010905  push    r14
0x180010907  push    r15
0x180010909  sub     rsp, 28h
0x18001090d  mov     r15, r9
0x180010910  mov     ebx, r8d
0x180010913  mov     r14d, edx
0x180010916  mov     rsi, rcx
0x180010919  cmp     byte ptr [rcx], 0
0x18001091c  jz      loc_180010A1E
0x180010922  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180010927  test    al, al
0x180010929  jz      loc_180010A1E
0x18001092f  mov     rdi, [rsi+18h]
0x180010933  cmp     ebx, 0FEh
0x180010939  jz      loc_1800109C8
0x18001093f  cmp     ebx, 0C8h
0x180010945  jb      short loc_18001095F
0x180010947  cmp     ebx, 100h
0x18001094d  jl      loc_180010A1E
0x180010953  cmp     ebx, 200h
0x180010959  jnb     loc_180010A1E
0x18001095f  mov     rcx, rdi; SRWLock
0x180010962  call    cs:__imp_AcquireSRWLockExclusive
0x180010969  nop     dword ptr [rax+rax+00h]
0x18001096e  cmp     ebx, 7
0x180010971  ja      short loc_18001097D
0x180010973  mov     eax, 0CCh
0x180010978  bt      eax, ebx
0x18001097b  jb      short loc_18001099D
0x18001097d  lea     eax, [rbx-100h]
0x180010983  cmp     eax, 7Fh
0x180010986  jbe     short loc_18001099D
0x180010988  mov     r9d, r15d
0x18001098b  lea     rcx, [rdi+48h]
0x18001098f  mov     r8d, r14d
0x180010992  mov     edx, ebx
0x180010994  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180010999  mov     bl, al
0x18001099b  jmp     short loc_1800109AE
0x18001099d  mov     r8d, r14d
0x1800109a0  mov     edx, ebx
0x1800109a2  lea     rcx, [rdi+8]
0x1800109a6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800109ab  mov     bl, [rdi+40h]
0x1800109ae  test    rdi, rdi
0x1800109b1  jz      short loc_1800109C2
0x1800109b3  mov     rcx, rdi; SRWLock
0x1800109b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800109bd  nop     dword ptr [rax+rax+00h]
0x1800109c2  test    bl, bl
0x1800109c4  jz      short loc_180010A1E
0x1800109c6  jmp     short loc_1800109D0
0x1800109c8  mov     rcx, rdi; SRWLock
0x1800109cb  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800109d0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800109d7  jnz     short loc_180010A1E
0x1800109d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800109e0  test    rax, rax
0x1800109e3  jz      short loc_1800109EE
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  test    al, al
0x1800109ec  jnz     short loc_180010A1E
0x1800109ee  lea     rbx, [rsi+20h]
0x1800109f2  mov     rcx, rbx; SRWLock
0x1800109f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800109fc  nop     dword ptr [rax+rax+00h]
0x180010a01  mov     rcx, rsi; pv
0x180010a04  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180010a09  test    rbx, rbx
0x180010a0c  jz      short loc_180010A1E
0x180010a0e  mov     rcx, rbx; SRWLock
0x180010a11  call    cs:__imp_ReleaseSRWLockExclusive
0x180010a18  nop     dword ptr [rax+rax+00h]
0x180010a1d  nop
0x180010a1e  add     rsp, 28h
0x180010a22  pop     r15
0x180010a24  pop     r14
0x180010a26  pop     rdi
0x180010a27  pop     rsi
0x180010a28  pop     rbp
0x180010a29  pop     rbx
0x180010a2a  retn
```
