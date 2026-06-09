# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180005c44`
- end: `0x180005d53`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180007a10`

## callees

- `0x1800041e4`
- `0x180004298`
- `0x180005c44`
- `0x180005d94`
- `0x180005dc8`
- `0x180005e00`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ca2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005ca2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005d29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005d3f`

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
0x180005c44  push    rbx
0x180005c46  push    rbp
0x180005c47  push    rsi
0x180005c48  push    rdi
0x180005c49  push    r14
0x180005c4b  push    r15
0x180005c4d  sub     rsp, 28h
0x180005c51  mov     r15, r9
0x180005c54  mov     ebx, r8d
0x180005c57  mov     r14d, edx
0x180005c5a  mov     rsi, rcx
0x180005c5d  cmp     byte ptr [rcx], 0
0x180005c60  jz      loc_180005D46
0x180005c66  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180005c6b  test    al, al
0x180005c6d  jz      loc_180005D46
0x180005c73  mov     rdi, [rsi+18h]
0x180005c77  cmp     ebx, 0FEh
0x180005c7d  jz      short loc_180005CFC
0x180005c7f  cmp     ebx, 0C8h
0x180005c85  jb      short loc_180005C9F
0x180005c87  cmp     ebx, 100h
0x180005c8d  jl      loc_180005D46
0x180005c93  cmp     ebx, 200h
0x180005c99  jnb     loc_180005D46
0x180005c9f  mov     rcx, rdi; SRWLock
0x180005ca2  call    cs:__imp_AcquireSRWLockExclusive
0x180005ca8  cmp     ebx, 7
0x180005cab  ja      short loc_180005CB7
0x180005cad  mov     eax, 0CCh
0x180005cb2  bt      eax, ebx
0x180005cb5  jb      short loc_180005CD7
0x180005cb7  lea     eax, [rbx-100h]
0x180005cbd  cmp     eax, 7Fh
0x180005cc0  jbe     short loc_180005CD7
0x180005cc2  mov     r9d, r15d
0x180005cc5  lea     rcx, [rdi+48h]
0x180005cc9  mov     r8d, r14d
0x180005ccc  mov     edx, ebx
0x180005cce  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005cd3  mov     bl, al
0x180005cd5  jmp     short loc_180005CE8
0x180005cd7  mov     r8d, r14d
0x180005cda  mov     edx, ebx
0x180005cdc  lea     rcx, [rdi+8]
0x180005ce0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180005ce5  mov     bl, [rdi+40h]
0x180005ce8  test    rdi, rdi
0x180005ceb  jz      short loc_180005CF6
0x180005ced  mov     rcx, rdi; SRWLock
0x180005cf0  call    cs:__imp_ReleaseSRWLockExclusive
0x180005cf6  test    bl, bl
0x180005cf8  jz      short loc_180005D46
0x180005cfa  jmp     short loc_180005D04
0x180005cfc  mov     rcx, rdi; SRWLock
0x180005cff  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180005d04  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005d0b  jnz     short loc_180005D46
0x180005d0d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005d14  test    rax, rax
0x180005d17  jz      short loc_180005D22
0x180005d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d1e  test    al, al
0x180005d20  jnz     short loc_180005D46
0x180005d22  lea     rbx, [rsi+20h]
0x180005d26  mov     rcx, rbx; SRWLock
0x180005d29  call    cs:__imp_AcquireSRWLockExclusive
0x180005d2f  mov     rcx, rsi; pv
0x180005d32  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180005d37  test    rbx, rbx
0x180005d3a  jz      short loc_180005D46
0x180005d3c  mov     rcx, rbx; SRWLock
0x180005d3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d45  nop
0x180005d46  add     rsp, 28h
0x180005d4a  pop     r15
0x180005d4c  pop     r14
0x180005d4e  pop     rdi
0x180005d4f  pop     rsi
0x180005d50  pop     rbp
0x180005d51  pop     rbx
0x180005d52  retn
```
