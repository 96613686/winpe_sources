# HandlePendingIrps

- ea: `0x18000f900`
- end: `0x18000fd59`
- name: `HandlePendingIrps`
- size: `1113`
- prototype: `__int64 __fastcall(PVOID InsertContext)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800230d0`
- `0x180024330`
- `0x180024910`
- `0x180025e00`

## callees

- `0x180001fa0`
- `0x1800075c4`
- `0x180007ba8`
- `0x18000ded4`
- `0x18000f900`
- `0x18000fe80`
- `0x1800263a0`
- `0x180026430`
- `0x180026710`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f9c5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f9c5`
- `ntoskrnl!IofCompleteRequest` at `0x18000fa1d`
- `ntoskrnl!IofCompleteRequest` at `0x18000fa1d`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fb8e`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fc54`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fb8e`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fc54`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000fab2`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000fab2`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fbbd`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fc85`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fbbd`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fc85`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18000f933`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18000f933`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18000f949`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18000f949`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f962`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000fa0c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000fa35`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f962`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000fa0c`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000fa35`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fa8a`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fb0b`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fd16`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fa8a`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fb0b`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fd16`
- `ntoskrnl!NtFreeVirtualMemory` at `0x18000fd41`
- `ntoskrnl!NtFreeVirtualMemory` at `0x18000fd41`

## pseudocode

```c
void __fastcall HandlePendingIrps(char *InsertContext)
{
  struct _FAST_MUTEX *v2; // rbx
  PIRP v3; // rax
  IRP *v4; // r13
  PMDL MdlAddress; // rcx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  PVOID *MappedSystemVa; // r12
  ULONG_PTR *v9; // r15
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  ULONG_PTR v13; // rdi
  char *v14; // rax
  __int64 v15; // r8
  int v16; // eax
  ULONG_PTR v17; // rsi
  PVOID v18; // rdi
  __int64 v19; // rbx
  __int64 CurrentProcess; // rax
  char *v21; // rbx
  __int64 v22; // rcx
  ULONG_PTR v23; // rax
  ULONG_PTR **v24; // rax
  PVOID v25; // rbx
  __int64 v26; // rax
  volatile signed __int64 *v27; // rdx
  volatile signed __int64 *v28; // roff
  void *v29; // rcx
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-58h]
  ULONG Priority; // [rsp+28h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-38h] BYREF
  ULONG_PTR *v33; // [rsp+48h] [rbp-30h]
  ULONG_PTR *v34; // [rsp+50h] [rbp-28h]
  char *v35; // [rsp+58h] [rbp-20h]
  volatile signed __int64 *CurrentAsyncPerfCounterSet; // [rsp+60h] [rbp-18h]
  int v37; // [rsp+C0h] [rbp+48h] BYREF
  ULONG_PTR RegionSize; // [rsp+C8h] [rbp+50h] BYREF
  ULONG_PTR v39; // [rsp+D0h] [rbp+58h] BYREF
  char *v40; // [rsp+D8h] [rbp+60h]

  if ( *((char **)InsertContext + 21) == InsertContext + 168 || *((char **)InsertContext + 11) == InsertContext + 88 )
    return;
  v2 = (struct _FAST_MUTEX *)(InsertContext + 104);
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(InsertContext + 104));
  v3 = IoCsqRemoveNextIrp((PIO_CSQ)(InsertContext + 24), InsertContext);
  v4 = v3;
  if ( !v3 )
  {
    KeReleaseGuardedMutex(v2);
    return;
  }
  MdlAddress = v3->MdlAddress;
  if ( MdlAddress->ByteCount < 8 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v7 = 11;
LABEL_15:
      WPP_SF_(v6[3], v7, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = (PVOID *)MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = (PVOID *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v7 = 12;
      goto LABEL_15;
    }
LABEL_16:
    v4->IoStatus.Status = -1073741811;
    KeReleaseGuardedMutex(v2);
    goto LABEL_17;
  }
  *MappedSystemVa = 0;
  KeReleaseGuardedMutex(v2);
  CurrentAsyncPerfCounterSet = (volatile signed __int64 *)KsecGetCurrentAsyncPerfCounterSet(InsertContext);
  RegionSize = 0;
  v9 = (ULONG_PTR *)PendingCallPullBatch(&RegionSize, InsertContext);
  v34 = v9;
  _InterlockedAdd64(CurrentAsyncPerfCounterSet + 4, RegionSize);
  RegionSize += 4LL;
  if ( !v9 )
  {
    IoCsqInsertIrpEx((PIO_CSQ)(InsertContext + 24), v4, 0, InsertContext);
    return;
  }
  v10 = ZwAllocateVirtualMemory(*((HANDLE *)InsertContext + 1), MappedSystemVa, 0, &RegionSize, 0x1000u, 4u);
  v12 = (unsigned int)v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 3));
    HandlePendingCallList(InsertContext, v9, 3221225626LL);
    IoCsqInsertIrpEx((PIO_CSQ)(InsertContext + 24), v4, 0, InsertContext);
    goto LABEL_25;
  }
  v13 = 0;
  v35 = (char *)*MappedSystemVa;
  v14 = v35 + 4;
  RegionSize -= 4LL;
  v4->IoStatus.Information = 4;
  v4->IoStatus.Status = 0;
  v32 = 0;
  v37 = 0;
  v40 = v14;
  v39 = 0;
  do
  {
    v33 = (ULONG_PTR *)*v9;
    if ( RegionSize < *(unsigned int *)(v9[2] + 40) )
    {
      v15 = 3221225626LL;
LABEL_31:
      PendingCallFailure(InsertContext, v9, v15);
      goto LABEL_38;
    }
    v16 = CallInProgressStarted(v9, v11, v12);
    if ( v16 < 0 )
    {
      v15 = (unsigned int)v16;
      goto LABEL_31;
    }
    v17 = v9[2];
    v18 = *(PVOID *)InsertContext;
    v19 = *(unsigned int *)(v17 + 40);
    CurrentProcess = PsGetCurrentProcess();
    LOBYTE(Priority) = 0;
    *(_QWORD *)BugCheckOnFailure = v19;
    v21 = v40;
    if ( (int)MmCopyVirtualMemory(CurrentProcess, v17, v18, v40, *(_QWORD *)BugCheckOnFailure, Priority, &v32) >= 0 )
    {
      v13 = v39;
      v22 = *(unsigned int *)(v9[2] + 40);
      RegionSize -= v22;
      v23 = v9[2];
      v40 = &v21[v22];
      v4->IoStatus.Information += *(unsigned int *)(v23 + 40);
      ++v37;
      if ( v13 )
      {
        v24 = *(ULONG_PTR ***)(v13 + 8);
        if ( *v24 != (ULONG_PTR *)v13 )
          __fastfail(3u);
        *v9 = v13;
        v9[1] = (ULONG_PTR)v24;
        *v24 = v9;
        *(_QWORD *)(v13 + 8) = v9;
      }
      else
      {
        v13 = (ULONG_PTR)v9;
        v39 = (ULONG_PTR)v9;
        v9[1] = (ULONG_PTR)v9;
        *v9 = (ULONG_PTR)v9;
      }
    }
    else
    {
      PendingCallFailure(InsertContext, v9, 3221225626LL);
      v13 = v39;
    }
LABEL_38:
    v9 = v33;
  }
  while ( v33 != v34 );
  if ( v37 <= 0 )
    goto LABEL_17;
  v25 = *(PVOID *)InsertContext;
  v26 = PsGetCurrentProcess();
  LOBYTE(Priority) = 0;
  if ( (int)MmCopyVirtualMemory(v26, &v37, v25, v35, 4, Priority, &v32) < 0 )
  {
    HandlePendingCallList(InsertContext, v13, 3221225626LL);
    IoCsqInsertIrpEx((PIO_CSQ)(InsertContext + 24), v4, 0, InsertContext);
    if ( !*MappedSystemVa )
      return;
    v29 = (void *)*((_QWORD *)InsertContext + 1);
    v39 = 0;
    NtFreeVirtualMemory(v29, MappedSystemVa, &v39, 0x8000u);
LABEL_25:
    *MappedSystemVa = 0;
    return;
  }
  HandlePendingCallList(InsertContext, v13, 0);
  v27 = CurrentAsyncPerfCounterSet;
  v28 = CurrentAsyncPerfCounterSet;
  _InterlockedAdd64(CurrentAsyncPerfCounterSet, -v37);
  _InterlockedAdd64(v28 + 2, v37);
  _InterlockedAdd64(v27 + 3, v37);
  _InterlockedIncrement64(v27 + 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, &WPP_f9740104427135617d8c60794f45a901_Traceguids, v4);
LABEL_17:
  IofCompleteRequest(v4, 0);
}

```

## disassembly

```asm
0x18000f900  push    rbp
0x18000f902  push    rbx
0x18000f903  push    rsi
0x18000f904  push    rdi
0x18000f905  push    r12
0x18000f907  push    r13
0x18000f909  push    r14
0x18000f90b  push    r15
0x18000f90d  mov     rbp, rsp
0x18000f910  sub     rsp, 78h
0x18000f914  lea     rax, [rcx+0A8h]
0x18000f91b  mov     r14, rcx
0x18000f91e  cmp     [rax], rax
0x18000f921  jz      short loc_18000F96E
0x18000f923  lea     rax, [rcx+58h]
0x18000f927  cmp     [rax], rax
0x18000f92a  jz      short loc_18000F96E
0x18000f92c  lea     rbx, [rcx+68h]
0x18000f930  mov     rcx, rbx; Mutex
0x18000f933  call    cs:__imp_KeAcquireGuardedMutex
0x18000f93a  nop     dword ptr [rax+rax+00h]
0x18000f93f  lea     rdi, [r14+18h]
0x18000f943  mov     rdx, r14; PeekContext
0x18000f946  mov     rcx, rdi; Csq
0x18000f949  call    cs:__imp_IoCsqRemoveNextIrp
0x18000f950  nop     dword ptr [rax+rax+00h]
0x18000f955  xor     esi, esi
0x18000f957  mov     r13, rax
0x18000f95a  test    rax, rax
0x18000f95d  jnz     short loc_18000F980
0x18000f95f  mov     rcx, rbx; Mutex
0x18000f962  call    cs:__imp_KeReleaseGuardedMutex
0x18000f969  nop     dword ptr [rax+rax+00h]
0x18000f96e  add     rsp, 78h
0x18000f972  pop     r15
0x18000f974  pop     r14
0x18000f976  pop     r13
0x18000f978  pop     r12
0x18000f97a  pop     rdi
0x18000f97b  pop     rsi
0x18000f97c  pop     rbx
0x18000f97d  pop     rbp
0x18000f97e  retn
0x18000f980  mov     rcx, [rax+8]; MemoryDescriptorList
0x18000f984  cmp     dword ptr [rcx+28h], 8
0x18000f988  jnb     short loc_18000F9A4
0x18000f98a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f991  lea     rax, WPP_GLOBAL_Control
0x18000f998  cmp     rcx, rax
0x18000f99b  jz      short loc_18000FA01
0x18000f99d  mov     edx, 0Bh
0x18000f9a2  jmp     short loc_18000F9F1
0x18000f9a4  test    byte ptr [rcx+0Ah], 5
0x18000f9a8  jz      short loc_18000F9B0
0x18000f9aa  mov     r12, [rcx+18h]
0x18000f9ae  jmp     short loc_18000F9D4
0x18000f9b0  xor     r9d, r9d; RequestedAddress
0x18000f9b3  mov     [rsp+78h+Priority], 40000010h; Priority
0x18000f9bb  xor     edx, edx; AccessMode
0x18000f9bd  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x18000f9c1  lea     r8d, [r9+1]; CacheType
0x18000f9c5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000f9cc  nop     dword ptr [rax+rax+00h]
0x18000f9d1  mov     r12, rax
0x18000f9d4  test    r12, r12
0x18000f9d7  jnz     short loc_18000FA2E
0x18000f9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9e0  lea     rax, WPP_GLOBAL_Control
0x18000f9e7  cmp     rcx, rax
0x18000f9ea  jz      short loc_18000FA01
0x18000f9ec  lea     edx, [r12+0Ch]
0x18000f9f1  mov     rcx, [rcx+18h]
0x18000f9f5  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000f9fc  call    WPP_SF_
0x18000fa01  mov     rcx, rbx; Mutex
0x18000fa04  mov     dword ptr [r13+30h], 0C000000Dh
0x18000fa0c  call    cs:__imp_KeReleaseGuardedMutex
0x18000fa13  nop     dword ptr [rax+rax+00h]
0x18000fa18  xor     edx, edx; PriorityBoost
0x18000fa1a  mov     rcx, r13; Irp
0x18000fa1d  call    cs:__imp_IofCompleteRequest
0x18000fa24  nop     dword ptr [rax+rax+00h]
0x18000fa29  jmp     loc_18000F96E
0x18000fa2e  mov     rcx, rbx; Mutex
0x18000fa31  mov     [r12], rsi
0x18000fa35  call    cs:__imp_KeReleaseGuardedMutex
0x18000fa3c  nop     dword ptr [rax+rax+00h]
0x18000fa41  mov     rcx, r14
0x18000fa44  call    KsecGetCurrentAsyncPerfCounterSet
0x18000fa49  mov     rdx, r14
0x18000fa4c  mov     [rbp+var_18], rax
0x18000fa50  lea     rcx, [rbp+RegionSize]
0x18000fa54  mov     [rbp+RegionSize], rsi
0x18000fa58  mov     rbx, rax
0x18000fa5b  call    PendingCallPullBatch
0x18000fa60  mov     rdx, [rbp+RegionSize]
0x18000fa64  mov     r15, rax
0x18000fa67  mov     [rbp+var_28], rax
0x18000fa6b  lock add [rbx+20h], rdx
0x18000fa70  mov     ebx, 4
0x18000fa75  xor     r8d, r8d; ZeroBits
0x18000fa78  add     [rbp+RegionSize], rbx
0x18000fa7c  test    rax, rax
0x18000fa7f  jnz     short loc_18000FA9B
0x18000fa81  mov     r9, r14; InsertContext
0x18000fa84  mov     rdx, r13; Irp
0x18000fa87  mov     rcx, rdi; Csq
0x18000fa8a  call    cs:__imp_IoCsqInsertIrpEx
0x18000fa91  nop     dword ptr [rax+rax+00h]
0x18000fa96  jmp     loc_18000F96E
0x18000fa9b  mov     rcx, [r14+8]; ProcessHandle
0x18000fa9f  lea     r9, [rbp+RegionSize]; RegionSize
0x18000faa3  mov     [rsp+78h+Priority], ebx; Protect
0x18000faa7  mov     rdx, r12; BaseAddress
0x18000faaa  mov     [rsp+78h+BugCheckOnFailure], 1000h; AllocationType
0x18000fab2  call    cs:__imp_ZwAllocateVirtualMemory
0x18000fab9  nop     dword ptr [rax+rax+00h]
0x18000fabe  mov     r8d, eax
0x18000fac1  test    eax, eax
0x18000fac3  jns     short loc_18000FB20
0x18000fac5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000facc  lea     rax, WPP_GLOBAL_Control
0x18000fad3  cmp     rcx, rax
0x18000fad6  jz      short loc_18000FAEE
0x18000fad8  mov     edx, [rcx+2Ch]
0x18000fadb  test    dl, 1
0x18000fade  jz      short loc_18000FAEE
0x18000fae0  mov     rcx, [rcx+18h]
0x18000fae4  mov     [rsp+78h+BugCheckOnFailure], r8d
0x18000fae9  call    WPP_SF_sD
0x18000faee  mov     r8d, 0C000009Ah
0x18000faf4  mov     rdx, r15
0x18000faf7  mov     rcx, r14
0x18000fafa  call    HandlePendingCallList
0x18000faff  mov     r9, r14; InsertContext
0x18000fb02  xor     r8d, r8d; Context
0x18000fb05  mov     rdx, r13; Irp
0x18000fb08  mov     rcx, rdi; Csq
0x18000fb0b  call    cs:__imp_IoCsqInsertIrpEx
0x18000fb12  nop     dword ptr [rax+rax+00h]
0x18000fb17  mov     [r12], rsi
0x18000fb1b  jmp     loc_18000F96E
0x18000fb20  mov     rax, [r12]
0x18000fb24  mov     rdi, rsi
0x18000fb27  mov     [rbp+var_20], rax
0x18000fb2b  add     rax, rbx
0x18000fb2e  sub     [rbp+RegionSize], rbx
0x18000fb32  mov     [r13+38h], rbx
0x18000fb36  mov     [r13+30h], esi
0x18000fb3a  mov     [rbp+var_38], rsi
0x18000fb3e  mov     [rbp+arg_0], esi
0x18000fb41  mov     [rbp+arg_18], rax
0x18000fb45  mov     [rbp+arg_10], rsi
0x18000fb49  mov     rax, [r15]
0x18000fb4c  mov     [rbp+var_30], rax
0x18000fb50  mov     rax, [r15+10h]
0x18000fb54  mov     ecx, [rax+28h]
0x18000fb57  cmp     [rbp+RegionSize], rcx
0x18000fb5b  jnb     short loc_18000FB65
0x18000fb5d  mov     r8d, 0C000009Ah
0x18000fb63  jmp     short loc_18000FB74
0x18000fb65  mov     rcx, r15
0x18000fb68  call    CallInProgressStarted
0x18000fb6d  test    eax, eax
0x18000fb6f  jns     short loc_18000FB84
0x18000fb71  mov     r8d, eax
0x18000fb74  mov     rdx, r15
0x18000fb77  mov     rcx, r14
0x18000fb7a  call    PendingCallFailure
0x18000fb7f  jmp     loc_18000FC3A
0x18000fb84  mov     rsi, [r15+10h]
0x18000fb88  mov     rdi, [r14]
0x18000fb8b  mov     ebx, [rsi+28h]
0x18000fb8e  call    cs:__imp_PsGetCurrentProcess
0x18000fb95  nop     dword ptr [rax+rax+00h]
0x18000fb9a  lea     rcx, [rbp+var_38]
0x18000fb9e  mov     r8, rdi
0x18000fba1  mov     [rsp+78h+var_48], rcx
0x18000fba6  mov     rdx, rsi
0x18000fba9  mov     byte ptr [rsp+78h+Priority], 0
0x18000fbae  mov     rcx, rax
0x18000fbb1  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbx
0x18000fbb6  mov     rbx, [rbp+arg_18]
0x18000fbba  mov     r9, rbx
0x18000fbbd  call    cs:__imp_MmCopyVirtualMemory
0x18000fbc4  nop     dword ptr [rax+rax+00h]
0x18000fbc9  xor     esi, esi
0x18000fbcb  test    eax, eax
0x18000fbcd  jns     short loc_18000FBE6
0x18000fbcf  mov     r8d, 0C000009Ah
0x18000fbd5  mov     rdx, r15
0x18000fbd8  mov     rcx, r14
0x18000fbdb  call    PendingCallFailure
0x18000fbe0  mov     rdi, [rbp+arg_10]
0x18000fbe4  jmp     short loc_18000FC3A
0x18000fbe6  mov     rax, [r15+10h]
0x18000fbea  mov     rdi, [rbp+arg_10]
0x18000fbee  mov     ecx, [rax+28h]
0x18000fbf1  sub     [rbp+RegionSize], rcx
0x18000fbf5  add     rbx, rcx
0x18000fbf8  mov     rax, [r15+10h]
0x18000fbfc  mov     [rbp+arg_18], rbx
0x18000fc00  mov     ecx, [rax+28h]
0x18000fc03  add     [r13+38h], rcx
0x18000fc07  inc     [rbp+arg_0]
0x18000fc0a  test    rdi, rdi
0x18000fc0d  jnz     short loc_18000FC1F
0x18000fc0f  mov     rdi, r15
0x18000fc12  mov     [rbp+arg_10], r15
0x18000fc16  mov     [r15+8], r15
0x18000fc1a  mov     [r15], r15
0x18000fc1d  jmp     short loc_18000FC3A
0x18000fc1f  mov     rax, [rdi+8]
0x18000fc23  cmp     [rax], rdi
0x18000fc26  jnz     loc_18000FD52
0x18000fc2c  mov     [r15], rdi
0x18000fc2f  mov     [r15+8], rax
0x18000fc33  mov     [rax], r15
0x18000fc36  mov     [rdi+8], r15
0x18000fc3a  mov     r15, [rbp+var_30]
0x18000fc3e  cmp     r15, [rbp+var_28]
0x18000fc42  jnz     loc_18000FB49
0x18000fc48  cmp     [rbp+arg_0], esi
0x18000fc4b  jle     loc_18000FA18
0x18000fc51  mov     rbx, [r14]
0x18000fc54  call    cs:__imp_PsGetCurrentProcess
0x18000fc5b  nop     dword ptr [rax+rax+00h]
0x18000fc60  mov     r9, [rbp+var_20]
0x18000fc64  lea     rcx, [rbp+var_38]
0x18000fc68  mov     [rsp+78h+var_48], rcx
0x18000fc6d  lea     rdx, [rbp+arg_0]
0x18000fc71  mov     byte ptr [rsp+78h+Priority], sil
0x18000fc76  mov     rcx, rax
0x18000fc79  mov     r8, rbx
0x18000fc7c  mov     qword ptr [rsp+78h+BugCheckOnFailure], 4
0x18000fc85  call    cs:__imp_MmCopyVirtualMemory
0x18000fc8c  nop     dword ptr [rax+rax+00h]
0x18000fc91  mov     rdx, rdi
0x18000fc94  mov     rcx, r14
0x18000fc97  test    eax, eax
0x18000fc99  js      short loc_18000FCFE
0x18000fc9b  xor     r8d, r8d
0x18000fc9e  call    HandlePendingCallList
0x18000fca3  mov     eax, [rbp+arg_0]
0x18000fca6  mov     rdx, [rbp+var_18]
0x18000fcaa  neg     eax
0x18000fcac  movsxd  rcx, eax
0x18000fcaf  lock add [rdx], rcx
0x18000fcb3  movsxd  rax, [rbp+arg_0]
0x18000fcb7  lock add [rdx+10h], rax
0x18000fcbc  movsxd  rax, [rbp+arg_0]
0x18000fcc0  lock add [rdx+18h], rax
0x18000fcc5  lock inc qword ptr [rdx+8]
0x18000fcca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcd1  lea     rax, WPP_GLOBAL_Control
0x18000fcd8  cmp     rcx, rax
0x18000fcdb  jz      loc_18000FA18
0x18000fce1  mov     rcx, [rcx+18h]
0x18000fce5  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000fcec  mov     edx, 0Eh
0x18000fcf1  mov     r9, r13
0x18000fcf4  call    WPP_SF_q
0x18000fcf9  jmp     loc_18000FA18
0x18000fcfe  mov     r8d, 0C000009Ah
0x18000fd04  call    HandlePendingCallList
0x18000fd09  mov     r9, r14; InsertContext
0x18000fd0c  lea     rcx, [r14+18h]; Csq
0x18000fd10  xor     r8d, r8d; Context
0x18000fd13  mov     rdx, r13; Irp
0x18000fd16  call    cs:__imp_IoCsqInsertIrpEx
0x18000fd1d  nop     dword ptr [rax+rax+00h]
0x18000fd22  cmp     [r12], rsi
0x18000fd26  jz      loc_18000F96E
0x18000fd2c  mov     rcx, [r14+8]; ProcessHandle
0x18000fd30  lea     r8, [rbp+arg_10]; RegionSize
0x18000fd34  mov     r9d, 8000h; FreeType
0x18000fd3a  mov     [rbp+arg_10], rsi
0x18000fd3e  mov     rdx, r12; BaseAddress
0x18000fd41  call    cs:__imp_NtFreeVirtualMemory
0x18000fd48  nop     dword ptr [rax+rax+00h]
0x18000fd4d  jmp     loc_18000FB17
0x18000fd52  mov     ecx, 3
0x18000fd57  int     29h; Win8: RtlFailFast(ecx)
```
