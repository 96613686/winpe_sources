# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007d94`
- end: `0x180007ea2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000aea0`

## callees

- `0x180005400`
- `0x180005578`
- `0x180007d94`
- `0x180007f14`
- `0x180007f48`
- `0x180007f80`
- `0x180019010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e40`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e8f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e40`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007e8f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007df2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007e79`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007df2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007e79`

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
0x180007d94  push    rbx
0x180007d96  push    rbp
0x180007d97  push    rsi
0x180007d98  push    rdi
0x180007d99  push    r14
0x180007d9b  push    r15
0x180007d9d  sub     rsp, 28h
0x180007da1  cmp     byte ptr [rcx], 0
0x180007da4  mov     r15, r9
0x180007da7  mov     ebx, r8d
0x180007daa  mov     r14d, edx
0x180007dad  mov     rsi, rcx
0x180007db0  jz      loc_180007E95
0x180007db6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007dbb  test    al, al
0x180007dbd  jz      loc_180007E95
0x180007dc3  mov     rdi, [rsi+18h]
0x180007dc7  cmp     ebx, 0FEh
0x180007dcd  jz      short loc_180007E4C
0x180007dcf  cmp     ebx, 0C8h
0x180007dd5  jb      short loc_180007DEF
0x180007dd7  cmp     ebx, 100h
0x180007ddd  jl      loc_180007E95
0x180007de3  cmp     ebx, 200h
0x180007de9  jnb     loc_180007E95
0x180007def  mov     rcx, rdi; SRWLock
0x180007df2  call    cs:__imp_AcquireSRWLockExclusive
0x180007df8  cmp     ebx, 7
0x180007dfb  ja      short loc_180007E07
0x180007dfd  mov     eax, 0CCh
0x180007e02  bt      eax, ebx
0x180007e05  jb      short loc_180007E27
0x180007e07  lea     eax, [rbx-100h]
0x180007e0d  cmp     eax, 7Fh
0x180007e10  jbe     short loc_180007E27
0x180007e12  mov     r9d, r15d
0x180007e15  lea     rcx, [rdi+48h]
0x180007e19  mov     r8d, r14d
0x180007e1c  mov     edx, ebx
0x180007e1e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007e23  mov     bl, al
0x180007e25  jmp     short loc_180007E38
0x180007e27  mov     r8d, r14d
0x180007e2a  lea     rcx, [rdi+8]
0x180007e2e  mov     edx, ebx
0x180007e30  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007e35  mov     bl, [rdi+40h]
0x180007e38  test    rdi, rdi
0x180007e3b  jz      short loc_180007E46
0x180007e3d  mov     rcx, rdi; SRWLock
0x180007e40  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e46  test    bl, bl
0x180007e48  jz      short loc_180007E95
0x180007e4a  jmp     short loc_180007E54
0x180007e4c  mov     rcx, rdi; SRWLock
0x180007e4f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007e54  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007e5b  jnz     short loc_180007E95
0x180007e5d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007e64  test    rax, rax
0x180007e67  jz      short loc_180007E72
0x180007e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6e  test    al, al
0x180007e70  jnz     short loc_180007E95
0x180007e72  lea     rbx, [rsi+20h]
0x180007e76  mov     rcx, rbx; SRWLock
0x180007e79  call    cs:__imp_AcquireSRWLockExclusive
0x180007e7f  mov     rcx, rsi; pv
0x180007e82  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007e87  test    rbx, rbx
0x180007e8a  jz      short loc_180007E95
0x180007e8c  mov     rcx, rbx; SRWLock
0x180007e8f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e95  add     rsp, 28h
0x180007e99  pop     r15
0x180007e9b  pop     r14
0x180007e9d  pop     rdi
0x180007e9e  pop     rsi
0x180007e9f  pop     rbp
0x180007ea0  pop     rbx
0x180007ea1  retn
```
