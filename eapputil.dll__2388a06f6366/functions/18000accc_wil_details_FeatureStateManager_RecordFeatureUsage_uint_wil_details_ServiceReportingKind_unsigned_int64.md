# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000accc`
- end: `0x18000addb`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000c0f0`

## callees

- `0x180009d58`
- `0x180009ed0`
- `0x18000accc`
- `0x18000ae24`
- `0x18000ae58`
- `0x18000ae90`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ad78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adc7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000adb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ad2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000adb1`

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
0x18000accc  push    rbx
0x18000acce  push    rbp
0x18000accf  push    rsi
0x18000acd0  push    rdi
0x18000acd1  push    r14
0x18000acd3  push    r15
0x18000acd5  sub     rsp, 28h
0x18000acd9  mov     r15, r9
0x18000acdc  mov     ebx, r8d
0x18000acdf  mov     r14d, edx
0x18000ace2  mov     rsi, rcx
0x18000ace5  cmp     byte ptr [rcx], 0
0x18000ace8  jz      loc_18000ADCE
0x18000acee  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000acf3  test    al, al
0x18000acf5  jz      loc_18000ADCE
0x18000acfb  mov     rdi, [rsi+18h]
0x18000acff  cmp     ebx, 0FEh
0x18000ad05  jz      short loc_18000AD84
0x18000ad07  cmp     ebx, 0C8h
0x18000ad0d  jb      short loc_18000AD27
0x18000ad0f  cmp     ebx, 100h
0x18000ad15  jl      loc_18000ADCE
0x18000ad1b  cmp     ebx, 200h
0x18000ad21  jnb     loc_18000ADCE
0x18000ad27  mov     rcx, rdi; SRWLock
0x18000ad2a  call    cs:__imp_AcquireSRWLockExclusive
0x18000ad30  cmp     ebx, 7
0x18000ad33  ja      short loc_18000AD3F
0x18000ad35  mov     eax, 0CCh
0x18000ad3a  bt      eax, ebx
0x18000ad3d  jb      short loc_18000AD5F
0x18000ad3f  lea     eax, [rbx-100h]
0x18000ad45  cmp     eax, 7Fh
0x18000ad48  jbe     short loc_18000AD5F
0x18000ad4a  mov     r9d, r15d
0x18000ad4d  lea     rcx, [rdi+48h]
0x18000ad51  mov     r8d, r14d
0x18000ad54  mov     edx, ebx
0x18000ad56  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ad5b  mov     bl, al
0x18000ad5d  jmp     short loc_18000AD70
0x18000ad5f  mov     r8d, r14d
0x18000ad62  mov     edx, ebx
0x18000ad64  lea     rcx, [rdi+8]
0x18000ad68  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000ad6d  mov     bl, [rdi+40h]
0x18000ad70  test    rdi, rdi
0x18000ad73  jz      short loc_18000AD7E
0x18000ad75  mov     rcx, rdi; SRWLock
0x18000ad78  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad7e  test    bl, bl
0x18000ad80  jz      short loc_18000ADCE
0x18000ad82  jmp     short loc_18000AD8C
0x18000ad84  mov     rcx, rdi; SRWLock
0x18000ad87  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ad8c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ad93  jnz     short loc_18000ADCE
0x18000ad95  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ad9c  test    rax, rax
0x18000ad9f  jz      short loc_18000ADAA
0x18000ada1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ada6  test    al, al
0x18000ada8  jnz     short loc_18000ADCE
0x18000adaa  lea     rbx, [rsi+20h]
0x18000adae  mov     rcx, rbx; SRWLock
0x18000adb1  call    cs:__imp_AcquireSRWLockExclusive
0x18000adb7  mov     rcx, rsi; pv
0x18000adba  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000adbf  test    rbx, rbx
0x18000adc2  jz      short loc_18000ADCE
0x18000adc4  mov     rcx, rbx; SRWLock
0x18000adc7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000adcd  nop
0x18000adce  add     rsp, 28h
0x18000add2  pop     r15
0x18000add4  pop     r14
0x18000add6  pop     rdi
0x18000add7  pop     rsi
0x18000add8  pop     rbp
0x18000add9  pop     rbx
0x18000adda  retn
```
