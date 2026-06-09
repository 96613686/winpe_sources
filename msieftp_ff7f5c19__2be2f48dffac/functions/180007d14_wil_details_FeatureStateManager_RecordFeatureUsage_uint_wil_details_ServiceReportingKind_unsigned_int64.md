# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007d14`
- end: `0x180007e22`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009e70`

## callees

- `0x180004f34`
- `0x1800050ac`
- `0x180007d14`
- `0x180007e94`
- `0x180007ec8`
- `0x180007f00`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007df9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007d72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007dc0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007e0f`

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
0x180007d14  push    rbx
0x180007d16  push    rbp
0x180007d17  push    rsi
0x180007d18  push    rdi
0x180007d19  push    r14
0x180007d1b  push    r15
0x180007d1d  sub     rsp, 28h
0x180007d21  cmp     byte ptr [rcx], 0
0x180007d24  mov     r15, r9
0x180007d27  mov     ebx, r8d
0x180007d2a  mov     r14d, edx
0x180007d2d  mov     rsi, rcx
0x180007d30  jz      loc_180007E15
0x180007d36  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007d3b  test    al, al
0x180007d3d  jz      loc_180007E15
0x180007d43  mov     rdi, [rsi+18h]
0x180007d47  cmp     ebx, 0FEh
0x180007d4d  jz      short loc_180007DCC
0x180007d4f  cmp     ebx, 0C8h
0x180007d55  jb      short loc_180007D6F
0x180007d57  cmp     ebx, 100h
0x180007d5d  jl      loc_180007E15
0x180007d63  cmp     ebx, 200h
0x180007d69  jnb     loc_180007E15
0x180007d6f  mov     rcx, rdi; SRWLock
0x180007d72  call    cs:__imp_AcquireSRWLockExclusive
0x180007d78  cmp     ebx, 7
0x180007d7b  ja      short loc_180007D87
0x180007d7d  mov     eax, 0CCh
0x180007d82  bt      eax, ebx
0x180007d85  jb      short loc_180007DA7
0x180007d87  lea     eax, [rbx-100h]
0x180007d8d  cmp     eax, 7Fh
0x180007d90  jbe     short loc_180007DA7
0x180007d92  mov     r9d, r15d
0x180007d95  lea     rcx, [rdi+48h]
0x180007d99  mov     r8d, r14d
0x180007d9c  mov     edx, ebx
0x180007d9e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007da3  mov     bl, al
0x180007da5  jmp     short loc_180007DB8
0x180007da7  mov     r8d, r14d
0x180007daa  lea     rcx, [rdi+8]
0x180007dae  mov     edx, ebx
0x180007db0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007db5  mov     bl, [rdi+40h]
0x180007db8  test    rdi, rdi
0x180007dbb  jz      short loc_180007DC6
0x180007dbd  mov     rcx, rdi; SRWLock
0x180007dc0  call    cs:__imp_ReleaseSRWLockExclusive
0x180007dc6  test    bl, bl
0x180007dc8  jz      short loc_180007E15
0x180007dca  jmp     short loc_180007DD4
0x180007dcc  mov     rcx, rdi; SRWLock
0x180007dcf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007dd4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180007ddb  jnz     short loc_180007E15
0x180007ddd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007de4  test    rax, rax
0x180007de7  jz      short loc_180007DF2
0x180007de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dee  test    al, al
0x180007df0  jnz     short loc_180007E15
0x180007df2  lea     rbx, [rsi+20h]
0x180007df6  mov     rcx, rbx; SRWLock
0x180007df9  call    cs:__imp_AcquireSRWLockExclusive
0x180007dff  mov     rcx, rsi; pv
0x180007e02  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007e07  test    rbx, rbx
0x180007e0a  jz      short loc_180007E15
0x180007e0c  mov     rcx, rbx; SRWLock
0x180007e0f  call    cs:__imp_ReleaseSRWLockExclusive
0x180007e15  add     rsp, 28h
0x180007e19  pop     r15
0x180007e1b  pop     r14
0x180007e1d  pop     rdi
0x180007e1e  pop     rsi
0x180007e1f  pop     rbp
0x180007e20  pop     rbx
0x180007e21  retn
```
