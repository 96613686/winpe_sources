# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1400095d4`
- end: `0x1400096e3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000c7c0`

## callees

- `0x140006b78`
- `0x140006c2c`
- `0x1400095d4`
- `0x140009724`
- `0x140009758`
- `0x140009790`
- `0x140011010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140009632`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400096b9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009632`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400096b9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009680`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400096cf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009680`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400096cf`

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
0x1400095d4  push    rbx
0x1400095d6  push    rbp
0x1400095d7  push    rsi
0x1400095d8  push    rdi
0x1400095d9  push    r14
0x1400095db  push    r15
0x1400095dd  sub     rsp, 28h
0x1400095e1  mov     r15, r9
0x1400095e4  mov     ebx, r8d
0x1400095e7  mov     r14d, edx
0x1400095ea  mov     rsi, rcx
0x1400095ed  cmp     byte ptr [rcx], 0
0x1400095f0  jz      loc_1400096D6
0x1400095f6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1400095fb  test    al, al
0x1400095fd  jz      loc_1400096D6
0x140009603  mov     rdi, [rsi+18h]
0x140009607  cmp     ebx, 0FEh
0x14000960d  jz      short loc_14000968C
0x14000960f  cmp     ebx, 0C8h
0x140009615  jb      short loc_14000962F
0x140009617  cmp     ebx, 100h
0x14000961d  jl      loc_1400096D6
0x140009623  cmp     ebx, 200h
0x140009629  jnb     loc_1400096D6
0x14000962f  mov     rcx, rdi; SRWLock
0x140009632  call    cs:__imp_AcquireSRWLockExclusive
0x140009638  cmp     ebx, 7
0x14000963b  ja      short loc_140009647
0x14000963d  mov     eax, 0CCh
0x140009642  bt      eax, ebx
0x140009645  jb      short loc_140009667
0x140009647  lea     eax, [rbx-100h]
0x14000964d  cmp     eax, 7Fh
0x140009650  jbe     short loc_140009667
0x140009652  mov     r9d, r15d
0x140009655  lea     rcx, [rdi+48h]
0x140009659  mov     r8d, r14d
0x14000965c  mov     edx, ebx
0x14000965e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140009663  mov     bl, al
0x140009665  jmp     short loc_140009678
0x140009667  mov     r8d, r14d
0x14000966a  mov     edx, ebx
0x14000966c  lea     rcx, [rdi+8]
0x140009670  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140009675  mov     bl, [rdi+40h]
0x140009678  test    rdi, rdi
0x14000967b  jz      short loc_140009686
0x14000967d  mov     rcx, rdi; SRWLock
0x140009680  call    cs:__imp_ReleaseSRWLockExclusive
0x140009686  test    bl, bl
0x140009688  jz      short loc_1400096D6
0x14000968a  jmp     short loc_140009694
0x14000968c  mov     rcx, rdi; SRWLock
0x14000968f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140009694  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000969b  jnz     short loc_1400096D6
0x14000969d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400096a4  test    rax, rax
0x1400096a7  jz      short loc_1400096B2
0x1400096a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096ae  test    al, al
0x1400096b0  jnz     short loc_1400096D6
0x1400096b2  lea     rbx, [rsi+20h]
0x1400096b6  mov     rcx, rbx; SRWLock
0x1400096b9  call    cs:__imp_AcquireSRWLockExclusive
0x1400096bf  mov     rcx, rsi; pv
0x1400096c2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1400096c7  test    rbx, rbx
0x1400096ca  jz      short loc_1400096D6
0x1400096cc  mov     rcx, rbx; SRWLock
0x1400096cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1400096d5  nop
0x1400096d6  add     rsp, 28h
0x1400096da  pop     r15
0x1400096dc  pop     r14
0x1400096de  pop     rdi
0x1400096df  pop     rsi
0x1400096e0  pop     rbp
0x1400096e1  pop     rbx
0x1400096e2  retn
```
