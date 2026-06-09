# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180017f40`
- end: `0x18001804e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001c9a0`

## callees

- `0x1800170f4`
- `0x1800171a8`
- `0x180017f40`
- `0x180018054`
- `0x180018088`
- `0x1800180c0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018025`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017f9e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018025`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001803b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001803b`

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
0x180017f40  push    rbx
0x180017f42  push    rbp
0x180017f43  push    rsi
0x180017f44  push    rdi
0x180017f45  push    r14
0x180017f47  push    r15
0x180017f49  sub     rsp, 28h
0x180017f4d  cmp     byte ptr [rcx], 0
0x180017f50  mov     r15, r9
0x180017f53  mov     ebx, r8d
0x180017f56  mov     r14d, edx
0x180017f59  mov     rsi, rcx
0x180017f5c  jz      loc_180018041
0x180017f62  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180017f67  test    al, al
0x180017f69  jz      loc_180018041
0x180017f6f  mov     rdi, [rsi+18h]
0x180017f73  cmp     ebx, 0FEh
0x180017f79  jz      short loc_180017FF8
0x180017f7b  cmp     ebx, 0C8h
0x180017f81  jb      short loc_180017F9B
0x180017f83  cmp     ebx, 100h
0x180017f89  jl      loc_180018041
0x180017f8f  cmp     ebx, 200h
0x180017f95  jnb     loc_180018041
0x180017f9b  mov     rcx, rdi; SRWLock
0x180017f9e  call    cs:__imp_AcquireSRWLockExclusive
0x180017fa4  cmp     ebx, 7
0x180017fa7  ja      short loc_180017FB3
0x180017fa9  mov     eax, 0CCh
0x180017fae  bt      eax, ebx
0x180017fb1  jb      short loc_180017FD3
0x180017fb3  lea     eax, [rbx-100h]
0x180017fb9  cmp     eax, 7Fh
0x180017fbc  jbe     short loc_180017FD3
0x180017fbe  mov     r9d, r15d
0x180017fc1  lea     rcx, [rdi+48h]
0x180017fc5  mov     r8d, r14d
0x180017fc8  mov     edx, ebx
0x180017fca  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180017fcf  mov     bl, al
0x180017fd1  jmp     short loc_180017FE4
0x180017fd3  mov     r8d, r14d
0x180017fd6  lea     rcx, [rdi+8]
0x180017fda  mov     edx, ebx
0x180017fdc  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180017fe1  mov     bl, [rdi+40h]
0x180017fe4  test    rdi, rdi
0x180017fe7  jz      short loc_180017FF2
0x180017fe9  mov     rcx, rdi; SRWLock
0x180017fec  call    cs:__imp_ReleaseSRWLockExclusive
0x180017ff2  test    bl, bl
0x180017ff4  jz      short loc_180018041
0x180017ff6  jmp     short loc_180018000
0x180017ff8  mov     rcx, rdi; SRWLock
0x180017ffb  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180018000  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180018007  jnz     short loc_180018041
0x180018009  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180018010  test    rax, rax
0x180018013  jz      short loc_18001801E
0x180018015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001801a  test    al, al
0x18001801c  jnz     short loc_180018041
0x18001801e  lea     rbx, [rsi+20h]
0x180018022  mov     rcx, rbx; SRWLock
0x180018025  call    cs:__imp_AcquireSRWLockExclusive
0x18001802b  mov     rcx, rsi; pv
0x18001802e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180018033  test    rbx, rbx
0x180018036  jz      short loc_180018041
0x180018038  mov     rcx, rbx; SRWLock
0x18001803b  call    cs:__imp_ReleaseSRWLockExclusive
0x180018041  add     rsp, 28h
0x180018045  pop     r15
0x180018047  pop     r14
0x180018049  pop     rdi
0x18001804a  pop     rsi
0x18001804b  pop     rbp
0x18001804c  pop     rbx
0x18001804d  retn
```
