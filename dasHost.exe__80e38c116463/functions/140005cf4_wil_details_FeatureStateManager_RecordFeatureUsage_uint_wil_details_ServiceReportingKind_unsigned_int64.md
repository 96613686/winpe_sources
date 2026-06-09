# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140005cf4`
- end: `0x140005e03`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140007ed0`

## callees

- `0x140004484`
- `0x140004538`
- `0x140005cf4`
- `0x140005e44`
- `0x140005e78`
- `0x140005eb0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005d52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005dd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005d52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005dd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005da0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005def`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005da0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005def`

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
0x140005cf4  push    rbx
0x140005cf6  push    rbp
0x140005cf7  push    rsi
0x140005cf8  push    rdi
0x140005cf9  push    r14
0x140005cfb  push    r15
0x140005cfd  sub     rsp, 28h
0x140005d01  mov     r15, r9
0x140005d04  mov     ebx, r8d
0x140005d07  mov     r14d, edx
0x140005d0a  mov     rsi, rcx
0x140005d0d  cmp     byte ptr [rcx], 0
0x140005d10  jz      loc_140005DF6
0x140005d16  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140005d1b  test    al, al
0x140005d1d  jz      loc_140005DF6
0x140005d23  mov     rdi, [rsi+18h]
0x140005d27  cmp     ebx, 0FEh
0x140005d2d  jz      short loc_140005DAC
0x140005d2f  cmp     ebx, 0C8h
0x140005d35  jb      short loc_140005D4F
0x140005d37  cmp     ebx, 100h
0x140005d3d  jl      loc_140005DF6
0x140005d43  cmp     ebx, 200h
0x140005d49  jnb     loc_140005DF6
0x140005d4f  mov     rcx, rdi; SRWLock
0x140005d52  call    cs:__imp_AcquireSRWLockExclusive
0x140005d58  cmp     ebx, 7
0x140005d5b  ja      short loc_140005D67
0x140005d5d  mov     eax, 0CCh
0x140005d62  bt      eax, ebx
0x140005d65  jb      short loc_140005D87
0x140005d67  lea     eax, [rbx-100h]
0x140005d6d  cmp     eax, 7Fh
0x140005d70  jbe     short loc_140005D87
0x140005d72  mov     r9d, r15d
0x140005d75  lea     rcx, [rdi+48h]
0x140005d79  mov     r8d, r14d
0x140005d7c  mov     edx, ebx
0x140005d7e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140005d83  mov     bl, al
0x140005d85  jmp     short loc_140005D98
0x140005d87  mov     r8d, r14d
0x140005d8a  mov     edx, ebx
0x140005d8c  lea     rcx, [rdi+8]
0x140005d90  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140005d95  mov     bl, [rdi+40h]
0x140005d98  test    rdi, rdi
0x140005d9b  jz      short loc_140005DA6
0x140005d9d  mov     rcx, rdi; SRWLock
0x140005da0  call    cs:__imp_ReleaseSRWLockExclusive
0x140005da6  test    bl, bl
0x140005da8  jz      short loc_140005DF6
0x140005daa  jmp     short loc_140005DB4
0x140005dac  mov     rcx, rdi; SRWLock
0x140005daf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140005db4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140005dbb  jnz     short loc_140005DF6
0x140005dbd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005dc4  test    rax, rax
0x140005dc7  jz      short loc_140005DD2
0x140005dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dce  test    al, al
0x140005dd0  jnz     short loc_140005DF6
0x140005dd2  lea     rbx, [rsi+20h]
0x140005dd6  mov     rcx, rbx; SRWLock
0x140005dd9  call    cs:__imp_AcquireSRWLockExclusive
0x140005ddf  mov     rcx, rsi; pv
0x140005de2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140005de7  test    rbx, rbx
0x140005dea  jz      short loc_140005DF6
0x140005dec  mov     rcx, rbx; SRWLock
0x140005def  call    cs:__imp_ReleaseSRWLockExclusive
0x140005df5  nop
0x140005df6  add     rsp, 28h
0x140005dfa  pop     r15
0x140005dfc  pop     r14
0x140005dfe  pop     rdi
0x140005dff  pop     rsi
0x140005e00  pop     rbp
0x140005e01  pop     rbx
0x140005e02  retn
```
