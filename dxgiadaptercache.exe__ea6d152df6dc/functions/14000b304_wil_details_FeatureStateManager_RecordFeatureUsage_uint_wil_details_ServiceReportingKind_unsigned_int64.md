# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000b304`
- end: `0x14000b413`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000f6f0`

## callees

- `0x1400083cc`
- `0x140008480`
- `0x14000b304`
- `0x14000b454`
- `0x14000b488`
- `0x14000b4c0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b362`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b3e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b362`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b3e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b3b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b3ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b3b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b3ff`

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
0x14000b304  push    rbx
0x14000b306  push    rbp
0x14000b307  push    rsi
0x14000b308  push    rdi
0x14000b309  push    r14
0x14000b30b  push    r15
0x14000b30d  sub     rsp, 28h
0x14000b311  mov     r15, r9
0x14000b314  mov     ebx, r8d
0x14000b317  mov     r14d, edx
0x14000b31a  mov     rsi, rcx
0x14000b31d  cmp     byte ptr [rcx], 0
0x14000b320  jz      loc_14000B406
0x14000b326  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000b32b  test    al, al
0x14000b32d  jz      loc_14000B406
0x14000b333  mov     rdi, [rsi+18h]
0x14000b337  cmp     ebx, 0FEh
0x14000b33d  jz      short loc_14000B3BC
0x14000b33f  cmp     ebx, 0C8h
0x14000b345  jb      short loc_14000B35F
0x14000b347  cmp     ebx, 100h
0x14000b34d  jl      loc_14000B406
0x14000b353  cmp     ebx, 200h
0x14000b359  jnb     loc_14000B406
0x14000b35f  mov     rcx, rdi; SRWLock
0x14000b362  call    cs:__imp_AcquireSRWLockExclusive
0x14000b368  cmp     ebx, 7
0x14000b36b  ja      short loc_14000B377
0x14000b36d  mov     eax, 0CCh
0x14000b372  bt      eax, ebx
0x14000b375  jb      short loc_14000B397
0x14000b377  lea     eax, [rbx-100h]
0x14000b37d  cmp     eax, 7Fh
0x14000b380  jbe     short loc_14000B397
0x14000b382  mov     r9d, r15d
0x14000b385  lea     rcx, [rdi+48h]
0x14000b389  mov     r8d, r14d
0x14000b38c  mov     edx, ebx
0x14000b38e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b393  mov     bl, al
0x14000b395  jmp     short loc_14000B3A8
0x14000b397  mov     r8d, r14d
0x14000b39a  mov     edx, ebx
0x14000b39c  lea     rcx, [rdi+8]
0x14000b3a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b3a5  mov     bl, [rdi+40h]
0x14000b3a8  test    rdi, rdi
0x14000b3ab  jz      short loc_14000B3B6
0x14000b3ad  mov     rcx, rdi; SRWLock
0x14000b3b0  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b3b6  test    bl, bl
0x14000b3b8  jz      short loc_14000B406
0x14000b3ba  jmp     short loc_14000B3C4
0x14000b3bc  mov     rcx, rdi; SRWLock
0x14000b3bf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b3c4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000b3cb  jnz     short loc_14000B406
0x14000b3cd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000b3d4  test    rax, rax
0x14000b3d7  jz      short loc_14000B3E2
0x14000b3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b3de  test    al, al
0x14000b3e0  jnz     short loc_14000B406
0x14000b3e2  lea     rbx, [rsi+20h]
0x14000b3e6  mov     rcx, rbx; SRWLock
0x14000b3e9  call    cs:__imp_AcquireSRWLockExclusive
0x14000b3ef  mov     rcx, rsi; pv
0x14000b3f2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000b3f7  test    rbx, rbx
0x14000b3fa  jz      short loc_14000B406
0x14000b3fc  mov     rcx, rbx; SRWLock
0x14000b3ff  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b405  nop
0x14000b406  add     rsp, 28h
0x14000b40a  pop     r15
0x14000b40c  pop     r14
0x14000b40e  pop     rdi
0x14000b40f  pop     rsi
0x14000b410  pop     rbp
0x14000b411  pop     rbx
0x14000b412  retn
```
