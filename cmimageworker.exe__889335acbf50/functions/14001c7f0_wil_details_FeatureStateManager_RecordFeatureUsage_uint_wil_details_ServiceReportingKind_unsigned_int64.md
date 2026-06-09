# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14001c7f0`
- end: `0x14001c91c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14001edd0`

## callees

- `0x1400194d0`
- `0x14001967c`
- `0x14001c7f0`
- `0x14001c924`
- `0x14001c95c`
- `0x14001c994`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c8a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c901`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c8a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c901`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c852`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c8e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c852`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001c8e5`

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
0x14001c7f0  push    rbx
0x14001c7f2  push    rbp
0x14001c7f3  push    rsi
0x14001c7f4  push    rdi
0x14001c7f5  push    r14
0x14001c7f7  push    r15
0x14001c7f9  sub     rsp, 28h
0x14001c7fd  mov     r15, r9
0x14001c800  mov     ebx, r8d
0x14001c803  mov     r14d, edx
0x14001c806  mov     rsi, rcx
0x14001c809  cmp     byte ptr [rcx], 0
0x14001c80c  jz      loc_14001C90E
0x14001c812  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14001c817  test    al, al
0x14001c819  jz      loc_14001C90E
0x14001c81f  mov     rdi, [rsi+18h]
0x14001c823  cmp     ebx, 0FEh
0x14001c829  jz      loc_14001C8B8
0x14001c82f  cmp     ebx, 0C8h
0x14001c835  jb      short loc_14001C84F
0x14001c837  cmp     ebx, 100h
0x14001c83d  jl      loc_14001C90E
0x14001c843  cmp     ebx, 200h
0x14001c849  jnb     loc_14001C90E
0x14001c84f  mov     rcx, rdi; SRWLock
0x14001c852  call    cs:__imp_AcquireSRWLockExclusive
0x14001c859  nop     dword ptr [rax+rax+00h]
0x14001c85e  cmp     ebx, 7
0x14001c861  ja      short loc_14001C86D
0x14001c863  mov     eax, 0CCh
0x14001c868  bt      eax, ebx
0x14001c86b  jb      short loc_14001C88D
0x14001c86d  lea     eax, [rbx-100h]
0x14001c873  cmp     eax, 7Fh
0x14001c876  jbe     short loc_14001C88D
0x14001c878  mov     r9d, r15d
0x14001c87b  lea     rcx, [rdi+48h]
0x14001c87f  mov     r8d, r14d
0x14001c882  mov     edx, ebx
0x14001c884  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14001c889  mov     bl, al
0x14001c88b  jmp     short loc_14001C89E
0x14001c88d  mov     r8d, r14d
0x14001c890  mov     edx, ebx
0x14001c892  lea     rcx, [rdi+8]
0x14001c896  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14001c89b  mov     bl, [rdi+40h]
0x14001c89e  test    rdi, rdi
0x14001c8a1  jz      short loc_14001C8B2
0x14001c8a3  mov     rcx, rdi; SRWLock
0x14001c8a6  call    cs:__imp_ReleaseSRWLockExclusive
0x14001c8ad  nop     dword ptr [rax+rax+00h]
0x14001c8b2  test    bl, bl
0x14001c8b4  jz      short loc_14001C90E
0x14001c8b6  jmp     short loc_14001C8C0
0x14001c8b8  mov     rcx, rdi; SRWLock
0x14001c8bb  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14001c8c0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14001c8c7  jnz     short loc_14001C90E
0x14001c8c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001c8d0  test    rax, rax
0x14001c8d3  jz      short loc_14001C8DE
0x14001c8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8da  test    al, al
0x14001c8dc  jnz     short loc_14001C90E
0x14001c8de  lea     rbx, [rsi+20h]
0x14001c8e2  mov     rcx, rbx; SRWLock
0x14001c8e5  call    cs:__imp_AcquireSRWLockExclusive
0x14001c8ec  nop     dword ptr [rax+rax+00h]
0x14001c8f1  mov     rcx, rsi; pv
0x14001c8f4  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14001c8f9  test    rbx, rbx
0x14001c8fc  jz      short loc_14001C90E
0x14001c8fe  mov     rcx, rbx; SRWLock
0x14001c901  call    cs:__imp_ReleaseSRWLockExclusive
0x14001c908  nop     dword ptr [rax+rax+00h]
0x14001c90d  nop
0x14001c90e  add     rsp, 28h
0x14001c912  pop     r15
0x14001c914  pop     r14
0x14001c916  pop     rdi
0x14001c917  pop     rsi
0x14001c918  pop     rbp
0x14001c919  pop     rbx
0x14001c91a  retn
```
