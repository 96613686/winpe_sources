# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800086f4`
- end: `0x180008802`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000a030`

## callees

- `0x1800059d4`
- `0x180005b54`
- `0x1800086f4`
- `0x180008874`
- `0x1800088a8`
- `0x1800088e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008752`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008752`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800087ef`

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
0x1800086f4  push    rbx
0x1800086f6  push    rbp
0x1800086f7  push    rsi
0x1800086f8  push    rdi
0x1800086f9  push    r14
0x1800086fb  push    r15
0x1800086fd  sub     rsp, 28h
0x180008701  cmp     byte ptr [rcx], 0
0x180008704  mov     r15, r9
0x180008707  mov     ebx, r8d
0x18000870a  mov     r14d, edx
0x18000870d  mov     rsi, rcx
0x180008710  jz      loc_1800087F5
0x180008716  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000871b  test    al, al
0x18000871d  jz      loc_1800087F5
0x180008723  mov     rdi, [rsi+18h]
0x180008727  cmp     ebx, 0FEh
0x18000872d  jz      short loc_1800087AC
0x18000872f  cmp     ebx, 0C8h
0x180008735  jb      short loc_18000874F
0x180008737  cmp     ebx, 100h
0x18000873d  jl      loc_1800087F5
0x180008743  cmp     ebx, 200h
0x180008749  jnb     loc_1800087F5
0x18000874f  mov     rcx, rdi; SRWLock
0x180008752  call    cs:__imp_AcquireSRWLockExclusive
0x180008758  cmp     ebx, 7
0x18000875b  ja      short loc_180008767
0x18000875d  mov     eax, 0CCh
0x180008762  bt      eax, ebx
0x180008765  jb      short loc_180008787
0x180008767  lea     eax, [rbx-100h]
0x18000876d  cmp     eax, 7Fh
0x180008770  jbe     short loc_180008787
0x180008772  mov     r9d, r15d
0x180008775  lea     rcx, [rdi+48h]
0x180008779  mov     r8d, r14d
0x18000877c  mov     edx, ebx
0x18000877e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008783  mov     bl, al
0x180008785  jmp     short loc_180008798
0x180008787  mov     r8d, r14d
0x18000878a  lea     rcx, [rdi+8]
0x18000878e  mov     edx, ebx
0x180008790  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008795  mov     bl, [rdi+40h]
0x180008798  test    rdi, rdi
0x18000879b  jz      short loc_1800087A6
0x18000879d  mov     rcx, rdi; SRWLock
0x1800087a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087a6  test    bl, bl
0x1800087a8  jz      short loc_1800087F5
0x1800087aa  jmp     short loc_1800087B4
0x1800087ac  mov     rcx, rdi; SRWLock
0x1800087af  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800087b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800087bb  jnz     short loc_1800087F5
0x1800087bd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800087c4  test    rax, rax
0x1800087c7  jz      short loc_1800087D2
0x1800087c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ce  test    al, al
0x1800087d0  jnz     short loc_1800087F5
0x1800087d2  lea     rbx, [rsi+20h]
0x1800087d6  mov     rcx, rbx; SRWLock
0x1800087d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800087df  mov     rcx, rsi; pv
0x1800087e2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800087e7  test    rbx, rbx
0x1800087ea  jz      short loc_1800087F5
0x1800087ec  mov     rcx, rbx; SRWLock
0x1800087ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800087f5  add     rsp, 28h
0x1800087f9  pop     r15
0x1800087fb  pop     r14
0x1800087fd  pop     rdi
0x1800087fe  pop     rsi
0x1800087ff  pop     rbp
0x180008800  pop     rbx
0x180008801  retn
```
