# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006a44`
- end: `0x180006b52`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180008960`

## callees

- `0x180004564`
- `0x1800046dc`
- `0x180006a44`
- `0x180006bc4`
- `0x180006bf8`
- `0x180006c30`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006aa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006aa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006af0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006af0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006b3f`

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
0x180006a44  push    rbx
0x180006a46  push    rbp
0x180006a47  push    rsi
0x180006a48  push    rdi
0x180006a49  push    r14
0x180006a4b  push    r15
0x180006a4d  sub     rsp, 28h
0x180006a51  cmp     byte ptr [rcx], 0
0x180006a54  mov     r15, r9
0x180006a57  mov     ebx, r8d
0x180006a5a  mov     r14d, edx
0x180006a5d  mov     rsi, rcx
0x180006a60  jz      loc_180006B45
0x180006a66  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006a6b  test    al, al
0x180006a6d  jz      loc_180006B45
0x180006a73  mov     rdi, [rsi+18h]
0x180006a77  cmp     ebx, 0FEh
0x180006a7d  jz      short loc_180006AFC
0x180006a7f  cmp     ebx, 0C8h
0x180006a85  jb      short loc_180006A9F
0x180006a87  cmp     ebx, 100h
0x180006a8d  jl      loc_180006B45
0x180006a93  cmp     ebx, 200h
0x180006a99  jnb     loc_180006B45
0x180006a9f  mov     rcx, rdi; SRWLock
0x180006aa2  call    cs:__imp_AcquireSRWLockExclusive
0x180006aa8  cmp     ebx, 7
0x180006aab  ja      short loc_180006AB7
0x180006aad  mov     eax, 0CCh
0x180006ab2  bt      eax, ebx
0x180006ab5  jb      short loc_180006AD7
0x180006ab7  lea     eax, [rbx-100h]
0x180006abd  cmp     eax, 7Fh
0x180006ac0  jbe     short loc_180006AD7
0x180006ac2  mov     r9d, r15d
0x180006ac5  lea     rcx, [rdi+48h]
0x180006ac9  mov     r8d, r14d
0x180006acc  mov     edx, ebx
0x180006ace  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006ad3  mov     bl, al
0x180006ad5  jmp     short loc_180006AE8
0x180006ad7  mov     r8d, r14d
0x180006ada  lea     rcx, [rdi+8]
0x180006ade  mov     edx, ebx
0x180006ae0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006ae5  mov     bl, [rdi+40h]
0x180006ae8  test    rdi, rdi
0x180006aeb  jz      short loc_180006AF6
0x180006aed  mov     rcx, rdi; SRWLock
0x180006af0  call    cs:__imp_ReleaseSRWLockExclusive
0x180006af6  test    bl, bl
0x180006af8  jz      short loc_180006B45
0x180006afa  jmp     short loc_180006B04
0x180006afc  mov     rcx, rdi; SRWLock
0x180006aff  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006b04  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006b0b  jnz     short loc_180006B45
0x180006b0d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006b14  test    rax, rax
0x180006b17  jz      short loc_180006B22
0x180006b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1e  test    al, al
0x180006b20  jnz     short loc_180006B45
0x180006b22  lea     rbx, [rsi+20h]
0x180006b26  mov     rcx, rbx; SRWLock
0x180006b29  call    cs:__imp_AcquireSRWLockExclusive
0x180006b2f  mov     rcx, rsi; pv
0x180006b32  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006b37  test    rbx, rbx
0x180006b3a  jz      short loc_180006B45
0x180006b3c  mov     rcx, rbx; SRWLock
0x180006b3f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006b45  add     rsp, 28h
0x180006b49  pop     r15
0x180006b4b  pop     r14
0x180006b4d  pop     rdi
0x180006b4e  pop     rsi
0x180006b4f  pop     rbp
0x180006b50  pop     rbx
0x180006b51  retn
```
