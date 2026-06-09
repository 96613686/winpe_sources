# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006fa4`
- end: `0x1800070b3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009bf0`

## callees

- `0x180004ee4`
- `0x18000505c`
- `0x180006fa4`
- `0x180007134`
- `0x180007168`
- `0x1800071a0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000709f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007050`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000709f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007002`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007089`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007002`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007089`

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
0x180006fa4  push    rbx
0x180006fa6  push    rbp
0x180006fa7  push    rsi
0x180006fa8  push    rdi
0x180006fa9  push    r14
0x180006fab  push    r15
0x180006fad  sub     rsp, 28h
0x180006fb1  mov     r15, r9
0x180006fb4  mov     ebx, r8d
0x180006fb7  mov     r14d, edx
0x180006fba  mov     rsi, rcx
0x180006fbd  cmp     byte ptr [rcx], 0
0x180006fc0  jz      loc_1800070A6
0x180006fc6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006fcb  test    al, al
0x180006fcd  jz      loc_1800070A6
0x180006fd3  mov     rdi, [rsi+18h]
0x180006fd7  cmp     ebx, 0FEh
0x180006fdd  jz      short loc_18000705C
0x180006fdf  cmp     ebx, 0C8h
0x180006fe5  jb      short loc_180006FFF
0x180006fe7  cmp     ebx, 100h
0x180006fed  jl      loc_1800070A6
0x180006ff3  cmp     ebx, 200h
0x180006ff9  jnb     loc_1800070A6
0x180006fff  mov     rcx, rdi; SRWLock
0x180007002  call    cs:__imp_AcquireSRWLockExclusive
0x180007008  cmp     ebx, 7
0x18000700b  ja      short loc_180007017
0x18000700d  mov     eax, 0CCh
0x180007012  bt      eax, ebx
0x180007015  jb      short loc_180007037
0x180007017  lea     eax, [rbx-100h]
0x18000701d  cmp     eax, 7Fh
0x180007020  jbe     short loc_180007037
0x180007022  mov     r9d, r15d
0x180007025  lea     rcx, [rdi+48h]
0x180007029  mov     r8d, r14d
0x18000702c  mov     edx, ebx
0x18000702e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007033  mov     bl, al
0x180007035  jmp     short loc_180007048
0x180007037  mov     r8d, r14d
0x18000703a  mov     edx, ebx
0x18000703c  lea     rcx, [rdi+8]
0x180007040  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007045  mov     bl, [rdi+40h]
0x180007048  test    rdi, rdi
0x18000704b  jz      short loc_180007056
0x18000704d  mov     rcx, rdi; SRWLock
0x180007050  call    cs:__imp_ReleaseSRWLockExclusive
0x180007056  test    bl, bl
0x180007058  jz      short loc_1800070A6
0x18000705a  jmp     short loc_180007064
0x18000705c  mov     rcx, rdi; SRWLock
0x18000705f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007064  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000706b  jnz     short loc_1800070A6
0x18000706d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007074  test    rax, rax
0x180007077  jz      short loc_180007082
0x180007079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000707e  test    al, al
0x180007080  jnz     short loc_1800070A6
0x180007082  lea     rbx, [rsi+20h]
0x180007086  mov     rcx, rbx; SRWLock
0x180007089  call    cs:__imp_AcquireSRWLockExclusive
0x18000708f  mov     rcx, rsi; pv
0x180007092  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180007097  test    rbx, rbx
0x18000709a  jz      short loc_1800070A6
0x18000709c  mov     rcx, rbx; SRWLock
0x18000709f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800070a5  nop
0x1800070a6  add     rsp, 28h
0x1800070aa  pop     r15
0x1800070ac  pop     r14
0x1800070ae  pop     rdi
0x1800070af  pop     rsi
0x1800070b0  pop     rbp
0x1800070b1  pop     rbx
0x1800070b2  retn
```
