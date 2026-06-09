# HandlePendingIrps

- ea: `0x18000f898`
- end: `0x18000fcf1`
- name: `HandlePendingIrps`
- size: `1113`
- prototype: `__int64 __fastcall(PVOID InsertContext)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180023080`
- `0x1800242e0`
- `0x1800248c0`
- `0x180025db0`

## callees

- `0x180001fa0`
- `0x1800075c4`
- `0x180007ba8`
- `0x18000ded4`
- `0x18000f898`
- `0x18000fe20`
- `0x180026350`
- `0x1800263e0`
- `0x1800266c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f95d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000f95d`
- `ntoskrnl!IofCompleteRequest` at `0x18000f9b5`
- `ntoskrnl!IofCompleteRequest` at `0x18000f9b5`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fb26`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fbec`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fb26`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000fbec`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000fa4a`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x18000fa4a`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fb55`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fc1d`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fb55`
- `ntoskrnl!MmCopyVirtualMemory` at `0x18000fc1d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18000f8cb`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x18000f8cb`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18000f8e1`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x18000f8e1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f8fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f9a4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f9cd`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f8fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f9a4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x18000f9cd`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fa22`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000faa3`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fcae`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fa22`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000faa3`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x18000fcae`
- `ntoskrnl!NtFreeVirtualMemory` at `0x18000fcd9`
- `ntoskrnl!NtFreeVirtualMemory` at `0x18000fcd9`

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
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r9
  ULONG_PTR v23; // rsi
  PVOID v24; // rdi
  __int64 v25; // rbx
  __int64 CurrentProcess; // rax
  char *v27; // rbx
  __int64 v28; // rcx
  ULONG_PTR v29; // rax
  ULONG_PTR **v30; // rax
  PVOID v31; // rbx
  __int64 v32; // rax
  volatile signed __int64 *v33; // rdx
  volatile signed __int64 *v34; // roff
  void *v35; // rcx
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-58h]
  ULONG Priority; // [rsp+28h] [rbp-50h]
  __int64 v38; // [rsp+40h] [rbp-38h] BYREF
  ULONG_PTR *v39; // [rsp+48h] [rbp-30h]
  ULONG_PTR *v40; // [rsp+50h] [rbp-28h]
  char *v41; // [rsp+58h] [rbp-20h]
  volatile signed __int64 *CurrentAsyncPerfCounterSet; // [rsp+60h] [rbp-18h]
  int v43; // [rsp+C0h] [rbp+48h] BYREF
  ULONG_PTR RegionSize; // [rsp+C8h] [rbp+50h] BYREF
  ULONG_PTR v45; // [rsp+D0h] [rbp+58h] BYREF
  char *v46; // [rsp+D8h] [rbp+60h]

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
      WPP_SF_(v6[3], v7, WPP_f9740104427135617d8c60794f45a901_Traceguids);
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
  v40 = v9;
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
  v41 = (char *)*MappedSystemVa;
  v14 = v41 + 4;
  RegionSize -= 4LL;
  v4->IoStatus.Information = 4;
  v4->IoStatus.Status = 0;
  v38 = 0;
  v43 = 0;
  v46 = v14;
  v45 = 0;
  do
  {
    v39 = (ULONG_PTR *)*v9;
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
    v23 = v9[2];
    v24 = *(PVOID *)InsertContext;
    v25 = *(unsigned int *)(v23 + 40);
    CurrentProcess = PsGetCurrentProcess(v18, v17, v19, v20);
    LOBYTE(Priority) = 0;
    *(_QWORD *)BugCheckOnFailure = v25;
    v27 = v46;
    if ( (int)MmCopyVirtualMemory(CurrentProcess, v23, v24, v46, *(_QWORD *)BugCheckOnFailure, Priority, &v38) >= 0 )
    {
      v13 = v45;
      v28 = *(unsigned int *)(v9[2] + 40);
      RegionSize -= v28;
      v29 = v9[2];
      v46 = &v27[v28];
      v21 = *(unsigned int *)(v29 + 40);
      v4->IoStatus.Information += v21;
      ++v43;
      if ( v13 )
      {
        v30 = *(ULONG_PTR ***)(v13 + 8);
        if ( *v30 != (ULONG_PTR *)v13 )
          __fastfail(3u);
        *v9 = v13;
        v9[1] = (ULONG_PTR)v30;
        *v30 = v9;
        *(_QWORD *)(v13 + 8) = v9;
      }
      else
      {
        v13 = (ULONG_PTR)v9;
        v45 = (ULONG_PTR)v9;
        v9[1] = (ULONG_PTR)v9;
        *v9 = (ULONG_PTR)v9;
      }
    }
    else
    {
      PendingCallFailure(InsertContext, v9, 3221225626LL);
      v13 = v45;
    }
LABEL_38:
    v9 = v39;
  }
  while ( v39 != v40 );
  if ( v43 <= 0 )
    goto LABEL_17;
  v31 = *(PVOID *)InsertContext;
  v32 = PsGetCurrentProcess(v21, v11, v12, v22);
  LOBYTE(Priority) = 0;
  if ( (int)MmCopyVirtualMemory(v32, &v43, v31, v41, 4, Priority, &v38) < 0 )
  {
    HandlePendingCallList(InsertContext, v13, 3221225626LL);
    IoCsqInsertIrpEx((PIO_CSQ)(InsertContext + 24), v4, 0, InsertContext);
    if ( !*MappedSystemVa )
      return;
    v35 = (void *)*((_QWORD *)InsertContext + 1);
    v45 = 0;
    NtFreeVirtualMemory(v35, MappedSystemVa, &v45, 0x8000u);
LABEL_25:
    *MappedSystemVa = 0;
    return;
  }
  HandlePendingCallList(InsertContext, v13, 0);
  v33 = CurrentAsyncPerfCounterSet;
  v34 = CurrentAsyncPerfCounterSet;
  _InterlockedAdd64(CurrentAsyncPerfCounterSet, -v43);
  _InterlockedAdd64(v34 + 2, v43);
  _InterlockedAdd64(v33 + 3, v43);
  _InterlockedIncrement64(v33 + 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, WPP_f9740104427135617d8c60794f45a901_Traceguids, v4);
LABEL_17:
  IofCompleteRequest(v4, 0);
}

```

## disassembly

```asm
0x18000f898  push    rbp
0x18000f89a  push    rbx
0x18000f89b  push    rsi
0x18000f89c  push    rdi
0x18000f89d  push    r12
0x18000f89f  push    r13
0x18000f8a1  push    r14
0x18000f8a3  push    r15
0x18000f8a5  mov     rbp, rsp
0x18000f8a8  sub     rsp, 78h
0x18000f8ac  lea     rax, [rcx+0A8h]
0x18000f8b3  mov     r14, rcx
0x18000f8b6  cmp     [rax], rax
0x18000f8b9  jz      short loc_18000F906
0x18000f8bb  lea     rax, [rcx+58h]
0x18000f8bf  cmp     [rax], rax
0x18000f8c2  jz      short loc_18000F906
0x18000f8c4  lea     rbx, [rcx+68h]
0x18000f8c8  mov     rcx, rbx; Mutex
0x18000f8cb  call    cs:__imp_KeAcquireGuardedMutex
0x18000f8d2  nop     dword ptr [rax+rax+00h]
0x18000f8d7  lea     rdi, [r14+18h]
0x18000f8db  mov     rdx, r14; PeekContext
0x18000f8de  mov     rcx, rdi; Csq
0x18000f8e1  call    cs:__imp_IoCsqRemoveNextIrp
0x18000f8e8  nop     dword ptr [rax+rax+00h]
0x18000f8ed  xor     esi, esi
0x18000f8ef  mov     r13, rax
0x18000f8f2  test    rax, rax
0x18000f8f5  jnz     short loc_18000F918
0x18000f8f7  mov     rcx, rbx; Mutex
0x18000f8fa  call    cs:__imp_KeReleaseGuardedMutex
0x18000f901  nop     dword ptr [rax+rax+00h]
0x18000f906  add     rsp, 78h
0x18000f90a  pop     r15
0x18000f90c  pop     r14
0x18000f90e  pop     r13
0x18000f910  pop     r12
0x18000f912  pop     rdi
0x18000f913  pop     rsi
0x18000f914  pop     rbx
0x18000f915  pop     rbp
0x18000f916  retn
0x18000f918  mov     rcx, [rax+8]; MemoryDescriptorList
0x18000f91c  cmp     dword ptr [rcx+28h], 8
0x18000f920  jnb     short loc_18000F93C
0x18000f922  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f929  lea     rax, WPP_GLOBAL_Control
0x18000f930  cmp     rcx, rax
0x18000f933  jz      short loc_18000F999
0x18000f935  mov     edx, 0Bh
0x18000f93a  jmp     short loc_18000F989
0x18000f93c  test    byte ptr [rcx+0Ah], 5
0x18000f940  jz      short loc_18000F948
0x18000f942  mov     r12, [rcx+18h]
0x18000f946  jmp     short loc_18000F96C
0x18000f948  xor     r9d, r9d; RequestedAddress
0x18000f94b  mov     [rsp+78h+Priority], 40000010h; Priority
0x18000f953  xor     edx, edx; AccessMode
0x18000f955  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x18000f959  lea     r8d, [r9+1]; CacheType
0x18000f95d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000f964  nop     dword ptr [rax+rax+00h]
0x18000f969  mov     r12, rax
0x18000f96c  test    r12, r12
0x18000f96f  jnz     short loc_18000F9C6
0x18000f971  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f978  lea     rax, WPP_GLOBAL_Control
0x18000f97f  cmp     rcx, rax
0x18000f982  jz      short loc_18000F999
0x18000f984  lea     edx, [r12+0Ch]
0x18000f989  mov     rcx, [rcx+18h]
0x18000f98d  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000f994  call    WPP_SF_
0x18000f999  mov     rcx, rbx; Mutex
0x18000f99c  mov     dword ptr [r13+30h], 0C000000Dh
0x18000f9a4  call    cs:__imp_KeReleaseGuardedMutex
0x18000f9ab  nop     dword ptr [rax+rax+00h]
0x18000f9b0  xor     edx, edx; PriorityBoost
0x18000f9b2  mov     rcx, r13; Irp
0x18000f9b5  call    cs:__imp_IofCompleteRequest
0x18000f9bc  nop     dword ptr [rax+rax+00h]
0x18000f9c1  jmp     loc_18000F906
0x18000f9c6  mov     rcx, rbx; Mutex
0x18000f9c9  mov     [r12], rsi
0x18000f9cd  call    cs:__imp_KeReleaseGuardedMutex
0x18000f9d4  nop     dword ptr [rax+rax+00h]
0x18000f9d9  mov     rcx, r14
0x18000f9dc  call    KsecGetCurrentAsyncPerfCounterSet
0x18000f9e1  mov     rdx, r14
0x18000f9e4  mov     [rbp+var_18], rax
0x18000f9e8  lea     rcx, [rbp+RegionSize]
0x18000f9ec  mov     [rbp+RegionSize], rsi
0x18000f9f0  mov     rbx, rax
0x18000f9f3  call    PendingCallPullBatch
0x18000f9f8  mov     rdx, [rbp+RegionSize]
0x18000f9fc  mov     r15, rax
0x18000f9ff  mov     [rbp+var_28], rax
0x18000fa03  lock add [rbx+20h], rdx
0x18000fa08  mov     ebx, 4
0x18000fa0d  xor     r8d, r8d; ZeroBits
0x18000fa10  add     [rbp+RegionSize], rbx
0x18000fa14  test    rax, rax
0x18000fa17  jnz     short loc_18000FA33
0x18000fa19  mov     r9, r14; InsertContext
0x18000fa1c  mov     rdx, r13; Irp
0x18000fa1f  mov     rcx, rdi; Csq
0x18000fa22  call    cs:__imp_IoCsqInsertIrpEx
0x18000fa29  nop     dword ptr [rax+rax+00h]
0x18000fa2e  jmp     loc_18000F906
0x18000fa33  mov     rcx, [r14+8]; ProcessHandle
0x18000fa37  lea     r9, [rbp+RegionSize]; RegionSize
0x18000fa3b  mov     [rsp+78h+Priority], ebx; Protect
0x18000fa3f  mov     rdx, r12; BaseAddress
0x18000fa42  mov     [rsp+78h+BugCheckOnFailure], 1000h; AllocationType
0x18000fa4a  call    cs:__imp_ZwAllocateVirtualMemory
0x18000fa51  nop     dword ptr [rax+rax+00h]
0x18000fa56  mov     r8d, eax
0x18000fa59  test    eax, eax
0x18000fa5b  jns     short loc_18000FAB8
0x18000fa5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa64  lea     rax, WPP_GLOBAL_Control
0x18000fa6b  cmp     rcx, rax
0x18000fa6e  jz      short loc_18000FA86
0x18000fa70  mov     edx, [rcx+2Ch]
0x18000fa73  test    dl, 1
0x18000fa76  jz      short loc_18000FA86
0x18000fa78  mov     rcx, [rcx+18h]
0x18000fa7c  mov     [rsp+78h+BugCheckOnFailure], r8d
0x18000fa81  call    WPP_SF_sD
0x18000fa86  mov     r8d, 0C000009Ah
0x18000fa8c  mov     rdx, r15
0x18000fa8f  mov     rcx, r14
0x18000fa92  call    HandlePendingCallList
0x18000fa97  mov     r9, r14; InsertContext
0x18000fa9a  xor     r8d, r8d; Context
0x18000fa9d  mov     rdx, r13; Irp
0x18000faa0  mov     rcx, rdi; Csq
0x18000faa3  call    cs:__imp_IoCsqInsertIrpEx
0x18000faaa  nop     dword ptr [rax+rax+00h]
0x18000faaf  mov     [r12], rsi
0x18000fab3  jmp     loc_18000F906
0x18000fab8  mov     rax, [r12]
0x18000fabc  mov     rdi, rsi
0x18000fabf  mov     [rbp+var_20], rax
0x18000fac3  add     rax, rbx
0x18000fac6  sub     [rbp+RegionSize], rbx
0x18000faca  mov     [r13+38h], rbx
0x18000face  mov     [r13+30h], esi
0x18000fad2  mov     [rbp+var_38], rsi
0x18000fad6  mov     [rbp+arg_0], esi
0x18000fad9  mov     [rbp+arg_18], rax
0x18000fadd  mov     [rbp+arg_10], rsi
0x18000fae1  mov     rax, [r15]
0x18000fae4  mov     [rbp+var_30], rax
0x18000fae8  mov     rax, [r15+10h]
0x18000faec  mov     ecx, [rax+28h]
0x18000faef  cmp     [rbp+RegionSize], rcx
0x18000faf3  jnb     short loc_18000FAFD
0x18000faf5  mov     r8d, 0C000009Ah
0x18000fafb  jmp     short loc_18000FB0C
0x18000fafd  mov     rcx, r15
0x18000fb00  call    CallInProgressStarted
0x18000fb05  test    eax, eax
0x18000fb07  jns     short loc_18000FB1C
0x18000fb09  mov     r8d, eax
0x18000fb0c  mov     rdx, r15
0x18000fb0f  mov     rcx, r14
0x18000fb12  call    PendingCallFailure
0x18000fb17  jmp     loc_18000FBD2
0x18000fb1c  mov     rsi, [r15+10h]
0x18000fb20  mov     rdi, [r14]
0x18000fb23  mov     ebx, [rsi+28h]
0x18000fb26  call    cs:__imp_PsGetCurrentProcess
0x18000fb2d  nop     dword ptr [rax+rax+00h]
0x18000fb32  lea     rcx, [rbp+var_38]
0x18000fb36  mov     r8, rdi
0x18000fb39  mov     [rsp+78h+var_48], rcx
0x18000fb3e  mov     rdx, rsi
0x18000fb41  mov     byte ptr [rsp+78h+Priority], 0
0x18000fb46  mov     rcx, rax
0x18000fb49  mov     qword ptr [rsp+78h+BugCheckOnFailure], rbx
0x18000fb4e  mov     rbx, [rbp+arg_18]
0x18000fb52  mov     r9, rbx
0x18000fb55  call    cs:__imp_MmCopyVirtualMemory
0x18000fb5c  nop     dword ptr [rax+rax+00h]
0x18000fb61  xor     esi, esi
0x18000fb63  test    eax, eax
0x18000fb65  jns     short loc_18000FB7E
0x18000fb67  mov     r8d, 0C000009Ah
0x18000fb6d  mov     rdx, r15
0x18000fb70  mov     rcx, r14
0x18000fb73  call    PendingCallFailure
0x18000fb78  mov     rdi, [rbp+arg_10]
0x18000fb7c  jmp     short loc_18000FBD2
0x18000fb7e  mov     rax, [r15+10h]
0x18000fb82  mov     rdi, [rbp+arg_10]
0x18000fb86  mov     ecx, [rax+28h]
0x18000fb89  sub     [rbp+RegionSize], rcx
0x18000fb8d  add     rbx, rcx
0x18000fb90  mov     rax, [r15+10h]
0x18000fb94  mov     [rbp+arg_18], rbx
0x18000fb98  mov     ecx, [rax+28h]
0x18000fb9b  add     [r13+38h], rcx
0x18000fb9f  inc     [rbp+arg_0]
0x18000fba2  test    rdi, rdi
0x18000fba5  jnz     short loc_18000FBB7
0x18000fba7  mov     rdi, r15
0x18000fbaa  mov     [rbp+arg_10], r15
0x18000fbae  mov     [r15+8], r15
0x18000fbb2  mov     [r15], r15
0x18000fbb5  jmp     short loc_18000FBD2
0x18000fbb7  mov     rax, [rdi+8]
0x18000fbbb  cmp     [rax], rdi
0x18000fbbe  jnz     loc_18000FCEA
0x18000fbc4  mov     [r15], rdi
0x18000fbc7  mov     [r15+8], rax
0x18000fbcb  mov     [rax], r15
0x18000fbce  mov     [rdi+8], r15
0x18000fbd2  mov     r15, [rbp+var_30]
0x18000fbd6  cmp     r15, [rbp+var_28]
0x18000fbda  jnz     loc_18000FAE1
0x18000fbe0  cmp     [rbp+arg_0], esi
0x18000fbe3  jle     loc_18000F9B0
0x18000fbe9  mov     rbx, [r14]
0x18000fbec  call    cs:__imp_PsGetCurrentProcess
0x18000fbf3  nop     dword ptr [rax+rax+00h]
0x18000fbf8  mov     r9, [rbp+var_20]
0x18000fbfc  lea     rcx, [rbp+var_38]
0x18000fc00  mov     [rsp+78h+var_48], rcx
0x18000fc05  lea     rdx, [rbp+arg_0]
0x18000fc09  mov     byte ptr [rsp+78h+Priority], sil
0x18000fc0e  mov     rcx, rax
0x18000fc11  mov     r8, rbx
0x18000fc14  mov     qword ptr [rsp+78h+BugCheckOnFailure], 4
0x18000fc1d  call    cs:__imp_MmCopyVirtualMemory
0x18000fc24  nop     dword ptr [rax+rax+00h]
0x18000fc29  mov     rdx, rdi
0x18000fc2c  mov     rcx, r14
0x18000fc2f  test    eax, eax
0x18000fc31  js      short loc_18000FC96
0x18000fc33  xor     r8d, r8d
0x18000fc36  call    HandlePendingCallList
0x18000fc3b  mov     eax, [rbp+arg_0]
0x18000fc3e  mov     rdx, [rbp+var_18]
0x18000fc42  neg     eax
0x18000fc44  movsxd  rcx, eax
0x18000fc47  lock add [rdx], rcx
0x18000fc4b  movsxd  rax, [rbp+arg_0]
0x18000fc4f  lock add [rdx+10h], rax
0x18000fc54  movsxd  rax, [rbp+arg_0]
0x18000fc58  lock add [rdx+18h], rax
0x18000fc5d  lock inc qword ptr [rdx+8]
0x18000fc62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc69  lea     rax, WPP_GLOBAL_Control
0x18000fc70  cmp     rcx, rax
0x18000fc73  jz      loc_18000F9B0
0x18000fc79  mov     rcx, [rcx+18h]
0x18000fc7d  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x18000fc84  mov     edx, 0Eh
0x18000fc89  mov     r9, r13
0x18000fc8c  call    WPP_SF_q
0x18000fc91  jmp     loc_18000F9B0
0x18000fc96  mov     r8d, 0C000009Ah
0x18000fc9c  call    HandlePendingCallList
0x18000fca1  mov     r9, r14; InsertContext
0x18000fca4  lea     rcx, [r14+18h]; Csq
0x18000fca8  xor     r8d, r8d; Context
0x18000fcab  mov     rdx, r13; Irp
0x18000fcae  call    cs:__imp_IoCsqInsertIrpEx
0x18000fcb5  nop     dword ptr [rax+rax+00h]
0x18000fcba  cmp     [r12], rsi
0x18000fcbe  jz      loc_18000F906
0x18000fcc4  mov     rcx, [r14+8]; ProcessHandle
0x18000fcc8  lea     r8, [rbp+arg_10]; RegionSize
0x18000fccc  mov     r9d, 8000h; FreeType
0x18000fcd2  mov     [rbp+arg_10], rsi
0x18000fcd6  mov     rdx, r12; BaseAddress
0x18000fcd9  call    cs:__imp_NtFreeVirtualMemory
0x18000fce0  nop     dword ptr [rax+rax+00h]
0x18000fce5  jmp     loc_18000FAAF
0x18000fcea  mov     ecx, 3
0x18000fcef  int     29h; Win8: RtlFailFast(ecx)
```
