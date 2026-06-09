# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008e24`
- end: `0x180008f50`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b8c0`

## callees

- `0x18000691c`
- `0x1800069e8`
- `0x180008e24`
- `0x180008f98`
- `0x180008fd0`
- `0x180009008`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008eda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f19`

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
0x180008e24  push    rbx
0x180008e26  push    rbp
0x180008e27  push    rsi
0x180008e28  push    rdi
0x180008e29  push    r14
0x180008e2b  push    r15
0x180008e2d  sub     rsp, 28h
0x180008e31  mov     r15, r9
0x180008e34  mov     ebx, r8d
0x180008e37  mov     r14d, edx
0x180008e3a  mov     rsi, rcx
0x180008e3d  cmp     byte ptr [rcx], 0
0x180008e40  jz      loc_180008F42
0x180008e46  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008e4b  test    al, al
0x180008e4d  jz      loc_180008F42
0x180008e53  mov     rdi, [rsi+18h]
0x180008e57  cmp     ebx, 0FEh
0x180008e5d  jz      loc_180008EEC
0x180008e63  cmp     ebx, 0C8h
0x180008e69  jb      short loc_180008E83
0x180008e6b  cmp     ebx, 100h
0x180008e71  jl      loc_180008F42
0x180008e77  cmp     ebx, 200h
0x180008e7d  jnb     loc_180008F42
0x180008e83  mov     rcx, rdi; SRWLock
0x180008e86  call    cs:__imp_AcquireSRWLockExclusive
0x180008e8d  nop     dword ptr [rax+rax+00h]
0x180008e92  cmp     ebx, 7
0x180008e95  ja      short loc_180008EA1
0x180008e97  mov     eax, 0CCh
0x180008e9c  bt      eax, ebx
0x180008e9f  jb      short loc_180008EC1
0x180008ea1  lea     eax, [rbx-100h]
0x180008ea7  cmp     eax, 7Fh
0x180008eaa  jbe     short loc_180008EC1
0x180008eac  mov     r9d, r15d
0x180008eaf  lea     rcx, [rdi+48h]
0x180008eb3  mov     r8d, r14d
0x180008eb6  mov     edx, ebx
0x180008eb8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008ebd  mov     bl, al
0x180008ebf  jmp     short loc_180008ED2
0x180008ec1  mov     r8d, r14d
0x180008ec4  mov     edx, ebx
0x180008ec6  lea     rcx, [rdi+8]
0x180008eca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008ecf  mov     bl, [rdi+40h]
0x180008ed2  test    rdi, rdi
0x180008ed5  jz      short loc_180008EE6
0x180008ed7  mov     rcx, rdi; SRWLock
0x180008eda  call    cs:__imp_ReleaseSRWLockExclusive
0x180008ee1  nop     dword ptr [rax+rax+00h]
0x180008ee6  test    bl, bl
0x180008ee8  jz      short loc_180008F42
0x180008eea  jmp     short loc_180008EF4
0x180008eec  mov     rcx, rdi; SRWLock
0x180008eef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008ef4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008efb  jnz     short loc_180008F42
0x180008efd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008f04  test    rax, rax
0x180008f07  jz      short loc_180008F12
0x180008f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0e  test    al, al
0x180008f10  jnz     short loc_180008F42
0x180008f12  lea     rbx, [rsi+20h]
0x180008f16  mov     rcx, rbx; SRWLock
0x180008f19  call    cs:__imp_AcquireSRWLockExclusive
0x180008f20  nop     dword ptr [rax+rax+00h]
0x180008f25  mov     rcx, rsi; pv
0x180008f28  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008f2d  test    rbx, rbx
0x180008f30  jz      short loc_180008F42
0x180008f32  mov     rcx, rbx; SRWLock
0x180008f35  call    cs:__imp_ReleaseSRWLockExclusive
0x180008f3c  nop     dword ptr [rax+rax+00h]
0x180008f41  nop
0x180008f42  add     rsp, 28h
0x180008f46  pop     r15
0x180008f48  pop     r14
0x180008f4a  pop     rdi
0x180008f4b  pop     rsi
0x180008f4c  pop     rbp
0x180008f4d  pop     rbx
0x180008f4e  retn
```
