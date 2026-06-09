# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b40c`
- end: `0x18000b51b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000f7e0`

## callees

- `0x180009bf4`
- `0x180009d6c`
- `0x18000b40c`
- `0x18000b564`
- `0x18000b598`
- `0x18000b5d0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b507`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b507`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b46a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b46a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b4f1`

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
0x18000b40c  push    rbx
0x18000b40e  push    rbp
0x18000b40f  push    rsi
0x18000b410  push    rdi
0x18000b411  push    r14
0x18000b413  push    r15
0x18000b415  sub     rsp, 28h
0x18000b419  mov     r15, r9
0x18000b41c  mov     ebx, r8d
0x18000b41f  mov     r14d, edx
0x18000b422  mov     rsi, rcx
0x18000b425  cmp     byte ptr [rcx], 0
0x18000b428  jz      loc_18000B50E
0x18000b42e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b433  test    al, al
0x18000b435  jz      loc_18000B50E
0x18000b43b  mov     rdi, [rsi+18h]
0x18000b43f  cmp     ebx, 0FEh
0x18000b445  jz      short loc_18000B4C4
0x18000b447  cmp     ebx, 0C8h
0x18000b44d  jb      short loc_18000B467
0x18000b44f  cmp     ebx, 100h
0x18000b455  jl      loc_18000B50E
0x18000b45b  cmp     ebx, 200h
0x18000b461  jnb     loc_18000B50E
0x18000b467  mov     rcx, rdi; SRWLock
0x18000b46a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b470  cmp     ebx, 7
0x18000b473  ja      short loc_18000B47F
0x18000b475  mov     eax, 0CCh
0x18000b47a  bt      eax, ebx
0x18000b47d  jb      short loc_18000B49F
0x18000b47f  lea     eax, [rbx-100h]
0x18000b485  cmp     eax, 7Fh
0x18000b488  jbe     short loc_18000B49F
0x18000b48a  mov     r9d, r15d
0x18000b48d  lea     rcx, [rdi+48h]
0x18000b491  mov     r8d, r14d
0x18000b494  mov     edx, ebx
0x18000b496  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b49b  mov     bl, al
0x18000b49d  jmp     short loc_18000B4B0
0x18000b49f  mov     r8d, r14d
0x18000b4a2  mov     edx, ebx
0x18000b4a4  lea     rcx, [rdi+8]
0x18000b4a8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b4ad  mov     bl, [rdi+40h]
0x18000b4b0  test    rdi, rdi
0x18000b4b3  jz      short loc_18000B4BE
0x18000b4b5  mov     rcx, rdi; SRWLock
0x18000b4b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b4be  test    bl, bl
0x18000b4c0  jz      short loc_18000B50E
0x18000b4c2  jmp     short loc_18000B4CC
0x18000b4c4  mov     rcx, rdi; SRWLock
0x18000b4c7  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b4cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b4d3  jnz     short loc_18000B50E
0x18000b4d5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b4dc  test    rax, rax
0x18000b4df  jz      short loc_18000B4EA
0x18000b4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e6  test    al, al
0x18000b4e8  jnz     short loc_18000B50E
0x18000b4ea  lea     rbx, [rsi+20h]
0x18000b4ee  mov     rcx, rbx; SRWLock
0x18000b4f1  call    cs:__imp_AcquireSRWLockExclusive
0x18000b4f7  mov     rcx, rsi; pv
0x18000b4fa  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000b4ff  test    rbx, rbx
0x18000b502  jz      short loc_18000B50E
0x18000b504  mov     rcx, rbx; SRWLock
0x18000b507  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b50d  nop
0x18000b50e  add     rsp, 28h
0x18000b512  pop     r15
0x18000b514  pop     r14
0x18000b516  pop     rdi
0x18000b517  pop     rsi
0x18000b518  pop     rbp
0x18000b519  pop     rbx
0x18000b51a  retn
```
