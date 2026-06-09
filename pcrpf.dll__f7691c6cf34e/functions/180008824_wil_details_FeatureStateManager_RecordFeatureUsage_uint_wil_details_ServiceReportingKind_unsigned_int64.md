# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008824`
- end: `0x180008950`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b050`

## callees

- `0x18000643c`
- `0x1800065ec`
- `0x180008824`
- `0x1800089d4`
- `0x180008a0c`
- `0x180008a44`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008886`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008919`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008886`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008919`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800088da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008935`

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
0x180008824  push    rbx
0x180008826  push    rbp
0x180008827  push    rsi
0x180008828  push    rdi
0x180008829  push    r14
0x18000882b  push    r15
0x18000882d  sub     rsp, 28h
0x180008831  mov     r15, r9
0x180008834  mov     ebx, r8d
0x180008837  mov     r14d, edx
0x18000883a  mov     rsi, rcx
0x18000883d  cmp     byte ptr [rcx], 0
0x180008840  jz      loc_180008942
0x180008846  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000884b  test    al, al
0x18000884d  jz      loc_180008942
0x180008853  mov     rdi, [rsi+18h]
0x180008857  cmp     ebx, 0FEh
0x18000885d  jz      loc_1800088EC
0x180008863  cmp     ebx, 0C8h
0x180008869  jb      short loc_180008883
0x18000886b  cmp     ebx, 100h
0x180008871  jl      loc_180008942
0x180008877  cmp     ebx, 200h
0x18000887d  jnb     loc_180008942
0x180008883  mov     rcx, rdi; SRWLock
0x180008886  call    cs:__imp_AcquireSRWLockExclusive
0x18000888d  nop     dword ptr [rax+rax+00h]
0x180008892  cmp     ebx, 7
0x180008895  ja      short loc_1800088A1
0x180008897  mov     eax, 0CCh
0x18000889c  bt      eax, ebx
0x18000889f  jb      short loc_1800088C1
0x1800088a1  lea     eax, [rbx-100h]
0x1800088a7  cmp     eax, 7Fh
0x1800088aa  jbe     short loc_1800088C1
0x1800088ac  mov     r9d, r15d
0x1800088af  lea     rcx, [rdi+48h]
0x1800088b3  mov     r8d, r14d
0x1800088b6  mov     edx, ebx
0x1800088b8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800088bd  mov     bl, al
0x1800088bf  jmp     short loc_1800088D2
0x1800088c1  mov     r8d, r14d
0x1800088c4  mov     edx, ebx
0x1800088c6  lea     rcx, [rdi+8]
0x1800088ca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800088cf  mov     bl, [rdi+40h]
0x1800088d2  test    rdi, rdi
0x1800088d5  jz      short loc_1800088E6
0x1800088d7  mov     rcx, rdi; SRWLock
0x1800088da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800088e1  nop     dword ptr [rax+rax+00h]
0x1800088e6  test    bl, bl
0x1800088e8  jz      short loc_180008942
0x1800088ea  jmp     short loc_1800088F4
0x1800088ec  mov     rcx, rdi; SRWLock
0x1800088ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800088f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800088fb  jnz     short loc_180008942
0x1800088fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008904  test    rax, rax
0x180008907  jz      short loc_180008912
0x180008909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890e  test    al, al
0x180008910  jnz     short loc_180008942
0x180008912  lea     rbx, [rsi+20h]
0x180008916  mov     rcx, rbx; SRWLock
0x180008919  call    cs:__imp_AcquireSRWLockExclusive
0x180008920  nop     dword ptr [rax+rax+00h]
0x180008925  mov     rcx, rsi; pv
0x180008928  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000892d  test    rbx, rbx
0x180008930  jz      short loc_180008942
0x180008932  mov     rcx, rbx; SRWLock
0x180008935  call    cs:__imp_ReleaseSRWLockExclusive
0x18000893c  nop     dword ptr [rax+rax+00h]
0x180008941  nop
0x180008942  add     rsp, 28h
0x180008946  pop     r15
0x180008948  pop     r14
0x18000894a  pop     rdi
0x18000894b  pop     rsi
0x18000894c  pop     rbp
0x18000894d  pop     rbx
0x18000894e  retn
```
