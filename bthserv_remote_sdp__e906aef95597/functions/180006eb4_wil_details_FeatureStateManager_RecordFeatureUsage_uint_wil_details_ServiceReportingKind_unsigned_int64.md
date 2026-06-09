# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006eb4`
- end: `0x180006ff7`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800094a0`

## callees

- `0x180004dd4`
- `0x180004f94`
- `0x180006eb4`
- `0x180007074`
- `0x1800070ac`
- `0x1800070e4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006fd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006f75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006fd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006fb4`

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
0x180006eb4  mov     [rsp+arg_0], rbx
0x180006eb9  mov     [rsp+arg_8], rbp
0x180006ebe  mov     [rsp+arg_10], rsi
0x180006ec3  push    rdi
0x180006ec4  push    r14
0x180006ec6  push    r15
0x180006ec8  sub     rsp, 20h
0x180006ecc  mov     r15, r9
0x180006ecf  mov     ebx, r8d
0x180006ed2  mov     r14d, edx
0x180006ed5  mov     rsi, rcx
0x180006ed8  cmp     byte ptr [rcx], 0
0x180006edb  jz      loc_180006FDD
0x180006ee1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006ee6  test    al, al
0x180006ee8  jz      loc_180006FDD
0x180006eee  mov     rdi, [rsi+18h]
0x180006ef2  cmp     ebx, 0FEh
0x180006ef8  jz      loc_180006F87
0x180006efe  cmp     ebx, 0C8h
0x180006f04  jb      short loc_180006F1E
0x180006f06  cmp     ebx, 100h
0x180006f0c  jl      loc_180006FDD
0x180006f12  cmp     ebx, 200h
0x180006f18  jnb     loc_180006FDD
0x180006f1e  mov     rcx, rdi; SRWLock
0x180006f21  call    cs:__imp_AcquireSRWLockExclusive
0x180006f28  nop     dword ptr [rax+rax+00h]
0x180006f2d  cmp     ebx, 7
0x180006f30  ja      short loc_180006F3C
0x180006f32  mov     eax, 0CCh
0x180006f37  bt      eax, ebx
0x180006f3a  jb      short loc_180006F5C
0x180006f3c  lea     eax, [rbx-100h]
0x180006f42  cmp     eax, 7Fh
0x180006f45  jbe     short loc_180006F5C
0x180006f47  lea     rcx, [rdi+48h]
0x180006f4b  mov     r9d, r15d
0x180006f4e  mov     r8d, r14d
0x180006f51  mov     edx, ebx
0x180006f53  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006f58  mov     bl, al
0x180006f5a  jmp     short loc_180006F6D
0x180006f5c  mov     r8d, r14d
0x180006f5f  mov     edx, ebx
0x180006f61  lea     rcx, [rdi+8]
0x180006f65  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006f6a  mov     bl, [rdi+40h]
0x180006f6d  test    rdi, rdi
0x180006f70  jz      short loc_180006F81
0x180006f72  mov     rcx, rdi; SRWLock
0x180006f75  call    cs:__imp_ReleaseSRWLockExclusive
0x180006f7c  nop     dword ptr [rax+rax+00h]
0x180006f81  test    bl, bl
0x180006f83  jz      short loc_180006FDD
0x180006f85  jmp     short loc_180006F8F
0x180006f87  mov     rcx, rdi; SRWLock
0x180006f8a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006f8f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006f96  jnz     short loc_180006FDD
0x180006f98  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006f9f  test    rax, rax
0x180006fa2  jz      short loc_180006FAD
0x180006fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa9  test    al, al
0x180006fab  jnz     short loc_180006FDD
0x180006fad  lea     rbx, [rsi+20h]
0x180006fb1  mov     rcx, rbx; SRWLock
0x180006fb4  call    cs:__imp_AcquireSRWLockExclusive
0x180006fbb  nop     dword ptr [rax+rax+00h]
0x180006fc0  mov     rcx, rsi; pv
0x180006fc3  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006fc8  test    rbx, rbx
0x180006fcb  jz      short loc_180006FDD
0x180006fcd  mov     rcx, rbx; SRWLock
0x180006fd0  call    cs:__imp_ReleaseSRWLockExclusive
0x180006fd7  nop     dword ptr [rax+rax+00h]
0x180006fdc  nop
0x180006fdd  mov     rbx, [rsp+38h+arg_0]
0x180006fe2  mov     rbp, [rsp+38h+arg_8]
0x180006fe7  mov     rsi, [rsp+38h+arg_10]
0x180006fec  add     rsp, 20h
0x180006ff0  pop     r15
0x180006ff2  pop     r14
0x180006ff4  pop     rdi
0x180006ff5  retn
```
