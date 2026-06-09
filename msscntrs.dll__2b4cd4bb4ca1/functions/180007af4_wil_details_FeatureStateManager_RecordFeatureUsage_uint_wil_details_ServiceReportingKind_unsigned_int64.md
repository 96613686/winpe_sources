# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007af4`
- end: `0x180007c03`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009e80`

## callees

- `0x180005b64`
- `0x180005cdc`
- `0x180007af4`
- `0x180007c84`
- `0x180007cb8`
- `0x180007cf0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007bd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007b52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007bd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ba0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007ba0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007bef`

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
0x180007af4  push    rbx
0x180007af6  push    rbp
0x180007af7  push    rsi
0x180007af8  push    rdi
0x180007af9  push    r14
0x180007afb  push    r15
0x180007afd  sub     rsp, 28h
0x180007b01  mov     r15, r9
0x180007b04  mov     ebx, r8d
0x180007b07  mov     r14d, edx
0x180007b0a  mov     rsi, rcx
0x180007b0d  cmp     byte ptr [rcx], 0
0x180007b10  jz      loc_180007BF6
0x180007b16  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007b1b  test    al, al
0x180007b1d  jz      loc_180007BF6
0x180007b23  mov     rdi, [rsi+18h]
0x180007b27  cmp     ebx, 0FEh
0x180007b2d  jz      short loc_180007BAC
0x180007b2f  cmp     ebx, 0C8h
0x180007b35  jb      short loc_180007B4F
0x180007b37  cmp     ebx, 100h
0x180007b3d  jl      loc_180007BF6
0x180007b43  cmp     ebx, 200h
0x180007b49  jnb     loc_180007BF6
0x180007b4f  mov     rcx, rdi; SRWLock
0x180007b52  call    cs:__imp_AcquireSRWLockExclusive
0x180007b58  cmp     ebx, 7
0x180007b5b  ja      short loc_180007B67
0x180007b5d  mov     eax, 0CCh
0x180007b62  bt      eax, ebx
0x180007b65  jb      short loc_180007B87
0x180007b67  lea     eax, [rbx-100h]
0x180007b6d  cmp     eax, 7Fh
0x180007b70  jbe     short loc_180007B87
0x180007b72  mov     r9d, r15d
0x180007b75  lea     rcx, [rdi+48h]
0x180007b79  mov     r8d, r14d
0x180007b7c  mov     edx, ebx
0x180007b7e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b83  mov     bl, al
0x180007b85  jmp     short loc_180007B98
0x180007b87  mov     r8d, r14d
0x180007b8a  mov     edx, ebx
0x180007b8c  lea     rcx, [rdi+8]
0x180007b90  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007b95  mov     bl, [rdi+40h]
0x180007b98  test    rdi, rdi
0x180007b9b  jz      short loc_180007BA6
0x180007b9d  mov     rcx, rdi; SRWLock
0x180007ba0  call    cs:__imp_ReleaseSRWLockExclusive
0x180007ba6  test    bl, bl
0x180007ba8  jz      short loc_180007BF6
0x180007baa  jmp     short loc_180007BB4
0x180007bac  mov     rcx, rdi; SRWLock
0x180007baf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007bb4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007bbb  jnz     short loc_180007BF6
0x180007bbd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007bc4  test    rax, rax
0x180007bc7  jz      short loc_180007BD2
0x180007bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bce  test    al, al
0x180007bd0  jnz     short loc_180007BF6
0x180007bd2  lea     rbx, [rsi+20h]
0x180007bd6  mov     rcx, rbx; SRWLock
0x180007bd9  call    cs:__imp_AcquireSRWLockExclusive
0x180007bdf  mov     rcx, rsi; pv
0x180007be2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007be7  test    rbx, rbx
0x180007bea  jz      short loc_180007BF6
0x180007bec  mov     rcx, rbx; SRWLock
0x180007bef  call    cs:__imp_ReleaseSRWLockExclusive
0x180007bf5  nop
0x180007bf6  add     rsp, 28h
0x180007bfa  pop     r15
0x180007bfc  pop     r14
0x180007bfe  pop     rdi
0x180007bff  pop     rsi
0x180007c00  pop     rbp
0x180007c01  pop     rbx
0x180007c02  retn
```
