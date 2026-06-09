# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007284`
- end: `0x1400073b0`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140009880`

## callees

- `0x140004cbc`
- `0x140004e64`
- `0x140007284`
- `0x140007434`
- `0x14000746c`
- `0x1400074a4`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007379`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400072e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007379`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000733a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007395`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000733a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007395`

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
0x140007284  push    rbx
0x140007286  push    rbp
0x140007287  push    rsi
0x140007288  push    rdi
0x140007289  push    r14
0x14000728b  push    r15
0x14000728d  sub     rsp, 28h
0x140007291  mov     r15, r9
0x140007294  mov     ebx, r8d
0x140007297  mov     r14d, edx
0x14000729a  mov     rsi, rcx
0x14000729d  cmp     byte ptr [rcx], 0
0x1400072a0  jz      loc_1400073A2
0x1400072a6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400072ab  test    al, al
0x1400072ad  jz      loc_1400073A2
0x1400072b3  mov     rdi, [rsi+18h]
0x1400072b7  cmp     ebx, 0FEh
0x1400072bd  jz      loc_14000734C
0x1400072c3  cmp     ebx, 0C8h
0x1400072c9  jb      short loc_1400072E3
0x1400072cb  cmp     ebx, 100h
0x1400072d1  jl      loc_1400073A2
0x1400072d7  cmp     ebx, 200h
0x1400072dd  jnb     loc_1400073A2
0x1400072e3  mov     rcx, rdi; SRWLock
0x1400072e6  call    cs:__imp_AcquireSRWLockExclusive
0x1400072ed  nop     dword ptr [rax+rax+00h]
0x1400072f2  cmp     ebx, 7
0x1400072f5  ja      short loc_140007301
0x1400072f7  mov     eax, 0CCh
0x1400072fc  bt      eax, ebx
0x1400072ff  jb      short loc_140007321
0x140007301  lea     eax, [rbx-100h]
0x140007307  cmp     eax, 7Fh
0x14000730a  jbe     short loc_140007321
0x14000730c  mov     r9d, r15d
0x14000730f  lea     rcx, [rdi+48h]
0x140007313  mov     r8d, r14d
0x140007316  mov     edx, ebx
0x140007318  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000731d  mov     bl, al
0x14000731f  jmp     short loc_140007332
0x140007321  mov     r8d, r14d
0x140007324  mov     edx, ebx
0x140007326  lea     rcx, [rdi+8]
0x14000732a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000732f  mov     bl, [rdi+40h]
0x140007332  test    rdi, rdi
0x140007335  jz      short loc_140007346
0x140007337  mov     rcx, rdi; SRWLock
0x14000733a  call    cs:__imp_ReleaseSRWLockExclusive
0x140007341  nop     dword ptr [rax+rax+00h]
0x140007346  test    bl, bl
0x140007348  jz      short loc_1400073A2
0x14000734a  jmp     short loc_140007354
0x14000734c  mov     rcx, rdi; SRWLock
0x14000734f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140007354  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000735b  jnz     short loc_1400073A2
0x14000735d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007364  test    rax, rax
0x140007367  jz      short loc_140007372
0x140007369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000736e  test    al, al
0x140007370  jnz     short loc_1400073A2
0x140007372  lea     rbx, [rsi+20h]
0x140007376  mov     rcx, rbx; SRWLock
0x140007379  call    cs:__imp_AcquireSRWLockExclusive
0x140007380  nop     dword ptr [rax+rax+00h]
0x140007385  mov     rcx, rsi; pv
0x140007388  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000738d  test    rbx, rbx
0x140007390  jz      short loc_1400073A2
0x140007392  mov     rcx, rbx; SRWLock
0x140007395  call    cs:__imp_ReleaseSRWLockExclusive
0x14000739c  nop     dword ptr [rax+rax+00h]
0x1400073a1  nop
0x1400073a2  add     rsp, 28h
0x1400073a6  pop     r15
0x1400073a8  pop     r14
0x1400073aa  pop     rdi
0x1400073ab  pop     rsi
0x1400073ac  pop     rbp
0x1400073ad  pop     rbx
0x1400073ae  retn
```
