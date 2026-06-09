# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000aa74`
- end: `0x18000ab83`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ce50`

## callees

- `0x1800089a4`
- `0x180008b1c`
- `0x18000aa74`
- `0x18000ac04`
- `0x18000ac38`
- `0x18000ac70`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ab6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000aad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab59`

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
0x18000aa74  push    rbx
0x18000aa76  push    rbp
0x18000aa77  push    rsi
0x18000aa78  push    rdi
0x18000aa79  push    r14
0x18000aa7b  push    r15
0x18000aa7d  sub     rsp, 28h
0x18000aa81  mov     r15, r9
0x18000aa84  mov     ebx, r8d
0x18000aa87  mov     r14d, edx
0x18000aa8a  mov     rsi, rcx
0x18000aa8d  cmp     byte ptr [rcx], 0
0x18000aa90  jz      loc_18000AB76
0x18000aa96  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aa9b  test    al, al
0x18000aa9d  jz      loc_18000AB76
0x18000aaa3  mov     rdi, [rsi+18h]
0x18000aaa7  cmp     ebx, 0FEh
0x18000aaad  jz      short loc_18000AB2C
0x18000aaaf  cmp     ebx, 0C8h
0x18000aab5  jb      short loc_18000AACF
0x18000aab7  cmp     ebx, 100h
0x18000aabd  jl      loc_18000AB76
0x18000aac3  cmp     ebx, 200h
0x18000aac9  jnb     loc_18000AB76
0x18000aacf  mov     rcx, rdi; SRWLock
0x18000aad2  call    cs:__imp_AcquireSRWLockExclusive
0x18000aad8  cmp     ebx, 7
0x18000aadb  ja      short loc_18000AAE7
0x18000aadd  mov     eax, 0CCh
0x18000aae2  bt      eax, ebx
0x18000aae5  jb      short loc_18000AB07
0x18000aae7  lea     eax, [rbx-100h]
0x18000aaed  cmp     eax, 7Fh
0x18000aaf0  jbe     short loc_18000AB07
0x18000aaf2  mov     r9d, r15d
0x18000aaf5  lea     rcx, [rdi+48h]
0x18000aaf9  mov     r8d, r14d
0x18000aafc  mov     edx, ebx
0x18000aafe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ab03  mov     bl, al
0x18000ab05  jmp     short loc_18000AB18
0x18000ab07  mov     r8d, r14d
0x18000ab0a  mov     edx, ebx
0x18000ab0c  lea     rcx, [rdi+8]
0x18000ab10  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ab15  mov     bl, [rdi+40h]
0x18000ab18  test    rdi, rdi
0x18000ab1b  jz      short loc_18000AB26
0x18000ab1d  mov     rcx, rdi; SRWLock
0x18000ab20  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab26  test    bl, bl
0x18000ab28  jz      short loc_18000AB76
0x18000ab2a  jmp     short loc_18000AB34
0x18000ab2c  mov     rcx, rdi; SRWLock
0x18000ab2f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ab34  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ab3b  jnz     short loc_18000AB76
0x18000ab3d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ab44  test    rax, rax
0x18000ab47  jz      short loc_18000AB52
0x18000ab49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab4e  test    al, al
0x18000ab50  jnz     short loc_18000AB76
0x18000ab52  lea     rbx, [rsi+20h]
0x18000ab56  mov     rcx, rbx; SRWLock
0x18000ab59  call    cs:__imp_AcquireSRWLockExclusive
0x18000ab5f  mov     rcx, rsi; pv
0x18000ab62  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000ab67  test    rbx, rbx
0x18000ab6a  jz      short loc_18000AB76
0x18000ab6c  mov     rcx, rbx; SRWLock
0x18000ab6f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ab75  nop
0x18000ab76  add     rsp, 28h
0x18000ab7a  pop     r15
0x18000ab7c  pop     r14
0x18000ab7e  pop     rdi
0x18000ab7f  pop     rsi
0x18000ab80  pop     rbp
0x18000ab81  pop     rbx
0x18000ab82  retn
```
