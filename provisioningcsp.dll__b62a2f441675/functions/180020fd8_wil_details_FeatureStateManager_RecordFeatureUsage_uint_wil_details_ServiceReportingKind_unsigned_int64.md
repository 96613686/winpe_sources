# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180020fd8`
- end: `0x180021104`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180022630`

## callees

- `0x180016c58`
- `0x180016d24`
- `0x180020fd8`
- `0x18002110c`
- `0x180021144`
- `0x18002117c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002103a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800210cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002103a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800210cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002108e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800210e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002108e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800210e9`

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
0x180020fd8  push    rbx
0x180020fda  push    rbp
0x180020fdb  push    rsi
0x180020fdc  push    rdi
0x180020fdd  push    r14
0x180020fdf  push    r15
0x180020fe1  sub     rsp, 28h
0x180020fe5  mov     r15, r9
0x180020fe8  mov     ebx, r8d
0x180020feb  mov     r14d, edx
0x180020fee  mov     rsi, rcx
0x180020ff1  cmp     byte ptr [rcx], 0
0x180020ff4  jz      loc_1800210F6
0x180020ffa  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180020fff  test    al, al
0x180021001  jz      loc_1800210F6
0x180021007  mov     rdi, [rsi+18h]
0x18002100b  cmp     ebx, 0FEh
0x180021011  jz      loc_1800210A0
0x180021017  cmp     ebx, 0C8h
0x18002101d  jb      short loc_180021037
0x18002101f  cmp     ebx, 100h
0x180021025  jl      loc_1800210F6
0x18002102b  cmp     ebx, 200h
0x180021031  jnb     loc_1800210F6
0x180021037  mov     rcx, rdi; SRWLock
0x18002103a  call    cs:__imp_AcquireSRWLockExclusive
0x180021041  nop     dword ptr [rax+rax+00h]
0x180021046  cmp     ebx, 7
0x180021049  ja      short loc_180021055
0x18002104b  mov     eax, 0CCh
0x180021050  bt      eax, ebx
0x180021053  jb      short loc_180021075
0x180021055  lea     eax, [rbx-100h]
0x18002105b  cmp     eax, 7Fh
0x18002105e  jbe     short loc_180021075
0x180021060  mov     r9d, r15d
0x180021063  lea     rcx, [rdi+48h]
0x180021067  mov     r8d, r14d
0x18002106a  mov     edx, ebx
0x18002106c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180021071  mov     bl, al
0x180021073  jmp     short loc_180021086
0x180021075  mov     r8d, r14d
0x180021078  mov     edx, ebx
0x18002107a  lea     rcx, [rdi+8]
0x18002107e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180021083  mov     bl, [rdi+40h]
0x180021086  test    rdi, rdi
0x180021089  jz      short loc_18002109A
0x18002108b  mov     rcx, rdi; SRWLock
0x18002108e  call    cs:__imp_ReleaseSRWLockExclusive
0x180021095  nop     dword ptr [rax+rax+00h]
0x18002109a  test    bl, bl
0x18002109c  jz      short loc_1800210F6
0x18002109e  jmp     short loc_1800210A8
0x1800210a0  mov     rcx, rdi; SRWLock
0x1800210a3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800210a8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800210af  jnz     short loc_1800210F6
0x1800210b1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800210b8  test    rax, rax
0x1800210bb  jz      short loc_1800210C6
0x1800210bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210c2  test    al, al
0x1800210c4  jnz     short loc_1800210F6
0x1800210c6  lea     rbx, [rsi+20h]
0x1800210ca  mov     rcx, rbx; SRWLock
0x1800210cd  call    cs:__imp_AcquireSRWLockExclusive
0x1800210d4  nop     dword ptr [rax+rax+00h]
0x1800210d9  mov     rcx, rsi; pv
0x1800210dc  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800210e1  test    rbx, rbx
0x1800210e4  jz      short loc_1800210F6
0x1800210e6  mov     rcx, rbx; SRWLock
0x1800210e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800210f0  nop     dword ptr [rax+rax+00h]
0x1800210f5  nop
0x1800210f6  add     rsp, 28h
0x1800210fa  pop     r15
0x1800210fc  pop     r14
0x1800210fe  pop     rdi
0x1800210ff  pop     rsi
0x180021100  pop     rbp
0x180021101  pop     rbx
0x180021102  retn
```
