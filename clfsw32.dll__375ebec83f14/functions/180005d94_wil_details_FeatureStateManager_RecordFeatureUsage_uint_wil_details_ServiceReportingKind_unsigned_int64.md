# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005d94`
- end: `0x180005ebf`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800079d0`

## callees

- `0x18000419c`
- `0x180004268`
- `0x180005d94`
- `0x180005f08`
- `0x180005f40`
- `0x180005f78`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ea5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005ea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005df6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005df6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e89`

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
0x180005d94  push    rbx
0x180005d96  push    rbp
0x180005d97  push    rsi
0x180005d98  push    rdi
0x180005d99  push    r14
0x180005d9b  push    r15
0x180005d9d  sub     rsp, 28h
0x180005da1  cmp     byte ptr [rcx], 0
0x180005da4  mov     r15, r9
0x180005da7  mov     ebx, r8d
0x180005daa  mov     r14d, edx
0x180005dad  mov     rsi, rcx
0x180005db0  jz      loc_180005EB1
0x180005db6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005dbb  test    al, al
0x180005dbd  jz      loc_180005EB1
0x180005dc3  mov     rdi, [rsi+18h]
0x180005dc7  cmp     ebx, 0FEh
0x180005dcd  jz      loc_180005E5C
0x180005dd3  cmp     ebx, 0C8h
0x180005dd9  jb      short loc_180005DF3
0x180005ddb  cmp     ebx, 100h
0x180005de1  jl      loc_180005EB1
0x180005de7  cmp     ebx, 200h
0x180005ded  jnb     loc_180005EB1
0x180005df3  mov     rcx, rdi; SRWLock
0x180005df6  call    cs:__imp_AcquireSRWLockExclusive
0x180005dfd  nop     dword ptr [rax+rax+00h]
0x180005e02  cmp     ebx, 7
0x180005e05  ja      short loc_180005E11
0x180005e07  mov     eax, 0CCh
0x180005e0c  bt      eax, ebx
0x180005e0f  jb      short loc_180005E31
0x180005e11  lea     eax, [rbx-100h]
0x180005e17  cmp     eax, 7Fh
0x180005e1a  jbe     short loc_180005E31
0x180005e1c  mov     r9d, r15d
0x180005e1f  lea     rcx, [rdi+48h]
0x180005e23  mov     r8d, r14d
0x180005e26  mov     edx, ebx
0x180005e28  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005e2d  mov     bl, al
0x180005e2f  jmp     short loc_180005E42
0x180005e31  mov     r8d, r14d
0x180005e34  lea     rcx, [rdi+8]
0x180005e38  mov     edx, ebx
0x180005e3a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005e3f  mov     bl, [rdi+40h]
0x180005e42  test    rdi, rdi
0x180005e45  jz      short loc_180005E56
0x180005e47  mov     rcx, rdi; SRWLock
0x180005e4a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e51  nop     dword ptr [rax+rax+00h]
0x180005e56  test    bl, bl
0x180005e58  jz      short loc_180005EB1
0x180005e5a  jmp     short loc_180005E64
0x180005e5c  mov     rcx, rdi; SRWLock
0x180005e5f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005e64  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005e6b  jnz     short loc_180005EB1
0x180005e6d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005e74  test    rax, rax
0x180005e77  jz      short loc_180005E82
0x180005e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7e  test    al, al
0x180005e80  jnz     short loc_180005EB1
0x180005e82  lea     rbx, [rsi+20h]
0x180005e86  mov     rcx, rbx; SRWLock
0x180005e89  call    cs:__imp_AcquireSRWLockExclusive
0x180005e90  nop     dword ptr [rax+rax+00h]
0x180005e95  mov     rcx, rsi; pv
0x180005e98  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005e9d  test    rbx, rbx
0x180005ea0  jz      short loc_180005EB1
0x180005ea2  mov     rcx, rbx; SRWLock
0x180005ea5  call    cs:__imp_ReleaseSRWLockExclusive
0x180005eac  nop     dword ptr [rax+rax+00h]
0x180005eb1  add     rsp, 28h
0x180005eb5  pop     r15
0x180005eb7  pop     r14
0x180005eb9  pop     rdi
0x180005eba  pop     rsi
0x180005ebb  pop     rbp
0x180005ebc  pop     rbx
0x180005ebd  retn
```
