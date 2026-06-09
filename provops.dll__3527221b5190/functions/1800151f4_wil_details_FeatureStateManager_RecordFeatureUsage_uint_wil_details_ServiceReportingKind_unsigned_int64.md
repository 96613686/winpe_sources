# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800151f4`
- end: `0x180015303`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001b830`

## callees

- `0x1800123f8`
- `0x180012570`
- `0x1800151f4`
- `0x180015344`
- `0x180015378`
- `0x1800153b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015252`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800152d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015252`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800152d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800152a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800152ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800152a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800152ef`

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
0x1800151f4  push    rbx
0x1800151f6  push    rbp
0x1800151f7  push    rsi
0x1800151f8  push    rdi
0x1800151f9  push    r14
0x1800151fb  push    r15
0x1800151fd  sub     rsp, 28h
0x180015201  mov     r15, r9
0x180015204  mov     ebx, r8d
0x180015207  mov     r14d, edx
0x18001520a  mov     rsi, rcx
0x18001520d  cmp     byte ptr [rcx], 0
0x180015210  jz      loc_1800152F6
0x180015216  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001521b  test    al, al
0x18001521d  jz      loc_1800152F6
0x180015223  mov     rdi, [rsi+18h]
0x180015227  cmp     ebx, 0FEh
0x18001522d  jz      short loc_1800152AC
0x18001522f  cmp     ebx, 0C8h
0x180015235  jb      short loc_18001524F
0x180015237  cmp     ebx, 100h
0x18001523d  jl      loc_1800152F6
0x180015243  cmp     ebx, 200h
0x180015249  jnb     loc_1800152F6
0x18001524f  mov     rcx, rdi; SRWLock
0x180015252  call    cs:__imp_AcquireSRWLockExclusive
0x180015258  cmp     ebx, 7
0x18001525b  ja      short loc_180015267
0x18001525d  mov     eax, 0CCh
0x180015262  bt      eax, ebx
0x180015265  jb      short loc_180015287
0x180015267  lea     eax, [rbx-100h]
0x18001526d  cmp     eax, 7Fh
0x180015270  jbe     short loc_180015287
0x180015272  mov     r9d, r15d
0x180015275  lea     rcx, [rdi+48h]
0x180015279  mov     r8d, r14d
0x18001527c  mov     edx, ebx
0x18001527e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015283  mov     bl, al
0x180015285  jmp     short loc_180015298
0x180015287  mov     r8d, r14d
0x18001528a  mov     edx, ebx
0x18001528c  lea     rcx, [rdi+8]
0x180015290  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015295  mov     bl, [rdi+40h]
0x180015298  test    rdi, rdi
0x18001529b  jz      short loc_1800152A6
0x18001529d  mov     rcx, rdi; SRWLock
0x1800152a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800152a6  test    bl, bl
0x1800152a8  jz      short loc_1800152F6
0x1800152aa  jmp     short loc_1800152B4
0x1800152ac  mov     rcx, rdi; SRWLock
0x1800152af  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800152b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800152bb  jnz     short loc_1800152F6
0x1800152bd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800152c4  test    rax, rax
0x1800152c7  jz      short loc_1800152D2
0x1800152c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152ce  test    al, al
0x1800152d0  jnz     short loc_1800152F6
0x1800152d2  lea     rbx, [rsi+20h]
0x1800152d6  mov     rcx, rbx; SRWLock
0x1800152d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800152df  mov     rcx, rsi; pv
0x1800152e2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800152e7  test    rbx, rbx
0x1800152ea  jz      short loc_1800152F6
0x1800152ec  mov     rcx, rbx; SRWLock
0x1800152ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800152f5  nop
0x1800152f6  add     rsp, 28h
0x1800152fa  pop     r15
0x1800152fc  pop     r14
0x1800152fe  pop     rdi
0x1800152ff  pop     rsi
0x180015300  pop     rbp
0x180015301  pop     rbx
0x180015302  retn
```
