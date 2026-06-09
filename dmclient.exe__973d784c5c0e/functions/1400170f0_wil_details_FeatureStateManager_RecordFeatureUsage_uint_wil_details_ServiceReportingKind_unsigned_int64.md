# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1400170f0`
- end: `0x14001721c`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140018430`

## callees

- `0x1400163bc`
- `0x140016488`
- `0x1400170f0`
- `0x140017224`
- `0x14001725c`
- `0x140017294`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017152`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400171e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140017152`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400171e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400171a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017201`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400171a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140017201`

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
0x1400170f0  push    rbx
0x1400170f2  push    rbp
0x1400170f3  push    rsi
0x1400170f4  push    rdi
0x1400170f5  push    r14
0x1400170f7  push    r15
0x1400170f9  sub     rsp, 28h
0x1400170fd  mov     r15, r9
0x140017100  mov     ebx, r8d
0x140017103  mov     r14d, edx
0x140017106  mov     rsi, rcx
0x140017109  cmp     byte ptr [rcx], 0
0x14001710c  jz      loc_14001720E
0x140017112  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140017117  test    al, al
0x140017119  jz      loc_14001720E
0x14001711f  mov     rdi, [rsi+18h]
0x140017123  cmp     ebx, 0FEh
0x140017129  jz      loc_1400171B8
0x14001712f  cmp     ebx, 0C8h
0x140017135  jb      short loc_14001714F
0x140017137  cmp     ebx, 100h
0x14001713d  jl      loc_14001720E
0x140017143  cmp     ebx, 200h
0x140017149  jnb     loc_14001720E
0x14001714f  mov     rcx, rdi; SRWLock
0x140017152  call    cs:__imp_AcquireSRWLockExclusive
0x140017159  nop     dword ptr [rax+rax+00h]
0x14001715e  cmp     ebx, 7
0x140017161  ja      short loc_14001716D
0x140017163  mov     eax, 0CCh
0x140017168  bt      eax, ebx
0x14001716b  jb      short loc_14001718D
0x14001716d  lea     eax, [rbx-100h]
0x140017173  cmp     eax, 7Fh
0x140017176  jbe     short loc_14001718D
0x140017178  mov     r9d, r15d
0x14001717b  lea     rcx, [rdi+48h]
0x14001717f  mov     r8d, r14d
0x140017182  mov     edx, ebx
0x140017184  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140017189  mov     bl, al
0x14001718b  jmp     short loc_14001719E
0x14001718d  mov     r8d, r14d
0x140017190  mov     edx, ebx
0x140017192  lea     rcx, [rdi+8]
0x140017196  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14001719b  mov     bl, [rdi+40h]
0x14001719e  test    rdi, rdi
0x1400171a1  jz      short loc_1400171B2
0x1400171a3  mov     rcx, rdi; SRWLock
0x1400171a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1400171ad  nop     dword ptr [rax+rax+00h]
0x1400171b2  test    bl, bl
0x1400171b4  jz      short loc_14001720E
0x1400171b6  jmp     short loc_1400171C0
0x1400171b8  mov     rcx, rdi; SRWLock
0x1400171bb  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400171c0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400171c7  jnz     short loc_14001720E
0x1400171c9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400171d0  test    rax, rax
0x1400171d3  jz      short loc_1400171DE
0x1400171d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400171da  test    al, al
0x1400171dc  jnz     short loc_14001720E
0x1400171de  lea     rbx, [rsi+20h]
0x1400171e2  mov     rcx, rbx; SRWLock
0x1400171e5  call    cs:__imp_AcquireSRWLockExclusive
0x1400171ec  nop     dword ptr [rax+rax+00h]
0x1400171f1  mov     rcx, rsi; pv
0x1400171f4  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1400171f9  test    rbx, rbx
0x1400171fc  jz      short loc_14001720E
0x1400171fe  mov     rcx, rbx; SRWLock
0x140017201  call    cs:__imp_ReleaseSRWLockExclusive
0x140017208  nop     dword ptr [rax+rax+00h]
0x14001720d  nop
0x14001720e  add     rsp, 28h
0x140017212  pop     r15
0x140017214  pop     r14
0x140017216  pop     rdi
0x140017217  pop     rsi
0x140017218  pop     rbp
0x140017219  pop     rbx
0x14001721a  retn
```
