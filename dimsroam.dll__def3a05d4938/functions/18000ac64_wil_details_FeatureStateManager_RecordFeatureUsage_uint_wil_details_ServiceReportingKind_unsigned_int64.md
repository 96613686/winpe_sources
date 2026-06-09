# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000ac64`
- end: `0x18000ad72`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c560`

## callees

- `0x180009154`
- `0x180009208`
- `0x18000ac64`
- `0x18000adb0`
- `0x18000ade4`
- `0x18000ae1c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad49`

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
0x18000ac64  push    rbx
0x18000ac66  push    rbp
0x18000ac67  push    rsi
0x18000ac68  push    rdi
0x18000ac69  push    r14
0x18000ac6b  push    r15
0x18000ac6d  sub     rsp, 28h
0x18000ac71  cmp     byte ptr [rcx], 0
0x18000ac74  mov     r15, r9
0x18000ac77  mov     ebx, r8d
0x18000ac7a  mov     r14d, edx
0x18000ac7d  mov     rsi, rcx
0x18000ac80  jz      loc_18000AD65
0x18000ac86  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ac8b  test    al, al
0x18000ac8d  jz      loc_18000AD65
0x18000ac93  mov     rdi, [rsi+18h]
0x18000ac97  cmp     ebx, 0FEh
0x18000ac9d  jz      short loc_18000AD1C
0x18000ac9f  cmp     ebx, 0C8h
0x18000aca5  jb      short loc_18000ACBF
0x18000aca7  cmp     ebx, 100h
0x18000acad  jl      loc_18000AD65
0x18000acb3  cmp     ebx, 200h
0x18000acb9  jnb     loc_18000AD65
0x18000acbf  mov     rcx, rdi; SRWLock
0x18000acc2  call    cs:__imp_AcquireSRWLockExclusive
0x18000acc8  cmp     ebx, 7
0x18000accb  ja      short loc_18000ACD7
0x18000accd  mov     eax, 0CCh
0x18000acd2  bt      eax, ebx
0x18000acd5  jb      short loc_18000ACF7
0x18000acd7  lea     eax, [rbx-100h]
0x18000acdd  cmp     eax, 7Fh
0x18000ace0  jbe     short loc_18000ACF7
0x18000ace2  mov     r9d, r15d
0x18000ace5  lea     rcx, [rdi+48h]
0x18000ace9  mov     r8d, r14d
0x18000acec  mov     edx, ebx
0x18000acee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000acf3  mov     bl, al
0x18000acf5  jmp     short loc_18000AD08
0x18000acf7  mov     r8d, r14d
0x18000acfa  lea     rcx, [rdi+8]
0x18000acfe  mov     edx, ebx
0x18000ad00  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ad05  mov     bl, [rdi+40h]
0x18000ad08  test    rdi, rdi
0x18000ad0b  jz      short loc_18000AD16
0x18000ad0d  mov     rcx, rdi; SRWLock
0x18000ad10  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad16  test    bl, bl
0x18000ad18  jz      short loc_18000AD65
0x18000ad1a  jmp     short loc_18000AD24
0x18000ad1c  mov     rcx, rdi; SRWLock
0x18000ad1f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ad24  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ad2b  jnz     short loc_18000AD65
0x18000ad2d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ad34  test    rax, rax
0x18000ad37  jz      short loc_18000AD42
0x18000ad39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad3e  test    al, al
0x18000ad40  jnz     short loc_18000AD65
0x18000ad42  lea     rbx, [rsi+20h]
0x18000ad46  mov     rcx, rbx; SRWLock
0x18000ad49  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad4f  mov     rcx, rsi; pv
0x18000ad52  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000ad57  test    rbx, rbx
0x18000ad5a  jz      short loc_18000AD65
0x18000ad5c  mov     rcx, rbx; SRWLock
0x18000ad5f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad65  add     rsp, 28h
0x18000ad69  pop     r15
0x18000ad6b  pop     r14
0x18000ad6d  pop     rdi
0x18000ad6e  pop     rsi
0x18000ad6f  pop     rbp
0x18000ad70  pop     rbx
0x18000ad71  retn
```
