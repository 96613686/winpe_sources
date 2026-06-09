# ClassIoBoostPriority

- ea: `0x14001e2f0`
- end: `0x14001e865`
- name: `ClassIoBoostPriority`
- size: `1397`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140029f80`

## callees

- `0x140002d30`
- `0x14000740c`
- `0x1400157d0`
- `0x14001e2f0`
- `0x14001fbf4`
- `0x140029ff4`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001e786`
- `ntoskrnl!ExAllocatePool2` at `0x14001e786`
- `ntoskrnl!IoFreeWorkItem` at `0x14001e7e9`
- `ntoskrnl!IoFreeWorkItem` at `0x14001e7e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e808`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e808`
- `ntoskrnl!IoQueueWorkItem` at `0x14001e7d5`
- `ntoskrnl!IoQueueWorkItem` at `0x14001e7d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e478`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e73c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e478`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e73c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e331`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e331`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001e729`
- `ntoskrnl!IoClearActivityIdThread` at `0x14001e729`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001e62d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001e62d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e549`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e709`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e549`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e709`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e38e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001e38e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e423`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e58f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e854`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e423`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e58f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e854`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14001e64d`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14001e64d`
- `ntoskrnl!IoSizeofWorkItem` at `0x14001e769`
- `ntoskrnl!IoSizeofWorkItem` at `0x14001e769`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001e498`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14001e498`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001e75a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14001e75a`

## pseudocode

```c
void __fastcall ClassIoBoostPriority(__int64 a1, struct _DEVICE_OBJECT *a2, struct _IO_WORKITEM *a3, int a4)
{
  _BYTE *DeviceExtension; // rbp
  KIRQL v8; // di
  volatile signed __int32 **v9; // rbx
  _DWORD **v10; // r8
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 v13; // r15
  char v14; // r14
  KIRQL v15; // al
  KIRQL v16; // r13
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rbx
  _QWORD *v20; // rax
  struct _DEVICE_OBJECT *v21; // rbp
  _DWORD **v22; // r8
  signed __int32 v23; // eax
  signed __int32 v24; // ett
  _QWORD *v25; // rax
  __int64 v26; // r8
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  char v29; // di
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  int v33; // edx
  int v34; // ecx
  PIO_WORKITEM WorkItem; // rdi
  ULONG v36; // eax
  PIO_WORKITEM *Pool2; // rax
  PIO_WORKITEM *v38; // rbx
  signed __int32 v39; // eax
  signed __int32 v40; // ett
  KIRQL CurrentIrql; // [rsp+40h] [rbp-88h]
  __int128 *v43; // [rsp+58h] [rbp-70h] BYREF
  _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+60h] [rbp-68h] BYREF
  __int128 v45; // [rsp+78h] [rbp-50h] BYREF
  __int128 v46; // [rsp+88h] [rbp-40h] BYREF

  DeviceExtension = a2->DeviceExtension;
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  CurrentIrql = KeGetCurrentIrql();
  v8 = CurrentIrql;
  v43 = &v46;
  v45 = 0;
  v46 = 0;
  if ( !DeviceExtension || (DeviceExtension[104] & 2) == 0 )
    return;
  v9 = (volatile signed __int32 **)a2->DeviceExtension;
  if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v9[55] + 2)) )
  {
    _InterlockedIncrement(v9[55]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        WPP_a22cc05f221e30b8049471910da99059_Traceguids,
        *(unsigned int *)v9[55]);
    }
  }
  if ( *((_DWORD *)v9 + 27) )
  {
    v10 = (_DWORD **)a2->DeviceExtension;
    v11 = *v10[55];
    while ( v11 )
    {
      v12 = v11;
      v11 = _InterlockedCompareExchange(v10[55], v11 - 1, v11);
      if ( v12 == v11 )
        return;
    }
LABEL_62:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v10[55] + 2));
    return;
  }
  if ( (DeviceExtension[104] & 1) != 0
    && (v13 = *((_QWORD *)DeviceExtension + 143), (*(_DWORD *)(v13 + 664) & 1) != 0)
    && a4 >= 2 )
  {
    v14 = 0;
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 3672));
    while ( 1 )
    {
      v16 = v15;
      if ( v8 >= 2u )
      {
        if ( !KeQueryDpcWatchdogInformation(&WatchdogInformation) )
        {
          if ( WatchdogInformation.DpcWatchdogLimit
            && 100 * WatchdogInformation.DpcWatchdogCount < 5 * WatchdogInformation.DpcWatchdogLimit )
          {
            v14 = 1;
          }
          if ( WatchdogInformation.DpcTimeLimit
            && 100 * WatchdogInformation.DpcTimeCount < 5 * WatchdogInformation.DpcTimeLimit )
          {
            break;
          }
        }
        if ( v14 )
          break;
      }
      v17 = (_QWORD *)(v13 + 3680);
      v18 = *(_QWORD **)(v13 + 3680);
      if ( v18 == (_QWORD *)(v13 + 3680) )
      {
LABEL_28:
        v20 = *(_QWORD **)(v13 + 3696);
        if ( v20 == (_QWORD *)(v13 + 3696) )
          goto LABEL_31;
        while ( 1 )
        {
          v19 = v20 - 21;
          if ( (struct _IO_WORKITEM *)*(v20 - 2) == a3 )
            break;
          v20 = (_QWORD *)*v20;
          if ( v20 == (_QWORD *)(v13 + 3696) )
            goto LABEL_31;
        }
      }
      else
      {
        while ( 1 )
        {
          v19 = v18 - 21;
          if ( (struct _IO_WORKITEM *)*(v18 - 2) == a3 )
            break;
          v18 = (_QWORD *)*v18;
          if ( v18 == v17 )
            goto LABEL_28;
        }
      }
      if ( !v19 )
      {
LABEL_31:
        v21 = a2;
        goto LABEL_32;
      }
      v25 = v19 + 21;
      v26 = v19[21];
      if ( *(_QWORD **)(v26 + 8) != v19 + 21
        || (v27 = (_QWORD *)v19[22], (_QWORD *)*v27 != v25)
        || (*v27 = v26, *(_QWORD *)(v26 + 8) = v27, v28 = *v17, *(_QWORD **)(*v17 + 8LL) != v17) )
      {
        __fastfail(3u);
      }
      *v25 = v28;
      v29 = 0;
      v19[22] = v17;
      *(_QWORD *)(v28 + 8) = v25;
      *v17 = v25;
      if ( (int)IoGetActivityIdIrp(v19, &v45) >= 0 )
      {
        v29 = 1;
        IoPropagateActivityIdToThread(v19, &v45, &v43);
      }
      if ( ClassPnPETWEnabled )
      {
        if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 2) != 0 )
          McTemplateK0ppqqq_EtwWriteTransfer(
            *(_DWORD *)(*((_QWORD *)DeviceExtension + 143) + 3880LL),
            *(_DWORD *)(*((_QWORD *)DeviceExtension + 143) + 3864LL),
            v32,
            (_DWORD)v19,
            v19[19],
            *(_DWORD *)(*((_QWORD *)DeviceExtension + 143) + 3864LL),
            *(_DWORD *)(*((_QWORD *)DeviceExtension + 143) + 3880LL),
            *((_DWORD *)DeviceExtension + 147));
        if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0 )
        {
          McTemplateK0qdud_EtwWriteTransfer(v31, v30, (unsigned int)&v45, *((_DWORD *)DeviceExtension + 147), 3, 4);
          if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0 )
            McTemplateK0qdud_EtwWriteTransfer(v34, v33, (unsigned int)&v45, *((_DWORD *)DeviceExtension + 147), 1, 2);
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 3672), v16);
      ClasspServiceIdleRequest(DeviceExtension, 0);
      if ( v29 )
        IoClearActivityIdThread(v43);
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 3672));
      v8 = CurrentIrql;
    }
    v21 = a2;
    WorkItem = IoAllocateWorkItem(a2);
    v36 = IoSizeofWorkItem();
    Pool2 = (PIO_WORKITEM *)ExAllocatePool2(64, v36 + 24LL, 1868194643);
    v38 = Pool2;
    if ( WorkItem )
    {
      if ( Pool2 )
      {
        ClassAcquireRemoveLockEx(a2, WorkItem, "minkernel\\storage\\classpnp\\clntirp.c", 0x137u);
        *v38 = WorkItem;
        v38[1] = a3;
        *((_DWORD *)v38 + 4) = a4;
        IoQueueWorkItem(WorkItem, ClasspIoBoostPriorityContext, DelayedWorkQueue, v38);
      }
      else
      {
        IoFreeWorkItem(WorkItem);
      }
    }
    else if ( Pool2 )
    {
      ExFreePoolWithTag(Pool2, 0);
    }
LABEL_32:
    KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 3672), v16);
    v22 = (_DWORD **)v21->DeviceExtension;
    v23 = *v22[55];
    if ( v23 )
    {
      while ( 1 )
      {
        v24 = v23;
        v23 = _InterlockedCompareExchange(v22[55], v23 - 1, v23);
        if ( v24 == v23 )
          break;
        if ( !v23 )
          goto LABEL_35;
      }
    }
    else
    {
LABEL_35:
      ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v22[55] + 2));
    }
  }
  else
  {
    v10 = (_DWORD **)a2->DeviceExtension;
    v39 = *v10[55];
    if ( !v39 )
      goto LABEL_62;
    while ( 1 )
    {
      v40 = v39;
      v39 = _InterlockedCompareExchange(v10[55], v39 - 1, v39);
      if ( v40 == v39 )
        break;
      if ( !v39 )
        goto LABEL_62;
    }
  }
}

```

## disassembly

```asm
0x14001e2f0  push    rbp
0x14001e2f2  push    rsi
0x14001e2f3  push    rdi
0x14001e2f4  push    r12
0x14001e2f6  push    r14
0x14001e2f8  sub     rsp, 0A0h
0x14001e2ff  mov     rax, cs:__security_cookie
0x14001e306  xor     rax, rsp
0x14001e309  mov     [rsp+0C8h+var_30], rax
0x14001e311  mov     rbp, [rdx+40h]
0x14001e315  xorps   xmm0, xmm0
0x14001e318  xor     eax, eax
0x14001e31a  mov     [rsp+0C8h+DeviceObject], rdx
0x14001e31f  movups  xmmword ptr [rsp+0C8h+WatchdogInformation.DpcTimeLimit], xmm0
0x14001e324  mov     [rsp+0C8h+WatchdogInformation.Reserved], eax
0x14001e328  mov     r12d, r9d
0x14001e32b  mov     rsi, r8
0x14001e32e  mov     r14, rdx
0x14001e331  call    cs:__imp_KeGetCurrentIrql
0x14001e338  nop     dword ptr [rax+rax+00h]
0x14001e33d  mov     [rsp+0C8h+var_88], al
0x14001e341  xorps   xmm0, xmm0
0x14001e344  movzx   edi, al
0x14001e347  lea     rax, [rsp+0C8h+var_40]
0x14001e34f  mov     [rsp+0C8h+var_70], rax
0x14001e354  xorps   xmm1, xmm1
0x14001e357  movups  [rsp+0C8h+var_50], xmm0
0x14001e35c  movups  [rsp+0C8h+var_40], xmm1
0x14001e364  test    rbp, rbp
0x14001e367  jz      loc_14001E5B3
0x14001e36d  test    byte ptr [rbp+68h], 2
0x14001e371  jz      loc_14001E5B3
0x14001e377  mov     [rsp+0C8h+arg_0], rbx
0x14001e37f  mov     rbx, [r14+40h]
0x14001e383  mov     rcx, [rbx+1B8h]
0x14001e38a  add     rcx, 8; RunRefCacheAware
0x14001e38e  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14001e395  nop     dword ptr [rax+rax+00h]
0x14001e39a  test    al, al
0x14001e39c  jnz     short loc_14001E3E9
0x14001e39e  mov     rax, [rbx+1B8h]
0x14001e3a5  lock inc dword ptr [rax]
0x14001e3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3af  lea     rax, WPP_GLOBAL_Control
0x14001e3b6  cmp     rcx, rax
0x14001e3b9  jz      short loc_14001E3E9
0x14001e3bb  test    dword ptr [rcx+2Ch], 200h
0x14001e3c2  jz      short loc_14001E3E9
0x14001e3c4  cmp     byte ptr [rcx+29h], 5
0x14001e3c8  jb      short loc_14001E3E9
0x14001e3ca  mov     r9, [rbx+1B8h]
0x14001e3d1  lea     r8, WPP_a22cc05f221e30b8049471910da99059_Traceguids
0x14001e3d8  mov     rcx, [rcx+18h]
0x14001e3dc  mov     edx, 0Eh
0x14001e3e1  mov     r9d, [r9]
0x14001e3e4  call    WPP_SF_d
0x14001e3e9  cmp     dword ptr [rbx+6Ch], 0
0x14001e3ed  jz      short loc_14001E434
0x14001e3ef  mov     r8, [r14+40h]
0x14001e3f3  mov     rax, [r8+1B8h]
0x14001e3fa  mov     eax, [rax]
0x14001e3fc  test    eax, eax
0x14001e3fe  jz      short loc_14001E418
0x14001e400  mov     rcx, [r8+1B8h]
0x14001e407  lea     edx, [rax-1]
0x14001e40a  lock cmpxchg [rcx], edx
0x14001e40e  jz      loc_14001E5AB
0x14001e414  test    eax, eax
0x14001e416  jnz     short loc_14001E400
0x14001e418  mov     rcx, [r8+1B8h]
0x14001e41f  add     rcx, 8; RunRefCacheAware
0x14001e423  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001e42a  nop     dword ptr [rax+rax+00h]
0x14001e42f  jmp     loc_14001E5AB
0x14001e434  test    byte ptr [rbp+68h], 1
0x14001e438  mov     [rsp+0C8h+arg_18], r15
0x14001e440  jz      loc_14001E820
0x14001e446  mov     r15, [rbp+478h]
0x14001e44d  mov     eax, [r15+298h]
0x14001e454  test    al, 1
0x14001e456  jz      loc_14001E820
0x14001e45c  cmp     r12d, 2
0x14001e460  jl      loc_14001E820
0x14001e466  xor     r14b, r14b
0x14001e469  mov     [rsp+0C8h+arg_10], r13
0x14001e471  lea     rcx, [r15+0E58h]; SpinLock
0x14001e478  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e47f  nop     dword ptr [rax+rax+00h]
0x14001e484  mov     ebx, 1
0x14001e489  movzx   r13d, al
0x14001e48d  cmp     dil, 2
0x14001e491  jb      short loc_14001E4E3
0x14001e493  lea     rcx, [rsp+0C8h+WatchdogInformation]; WatchdogInformation
0x14001e498  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14001e49f  nop     dword ptr [rax+rax+00h]
0x14001e4a4  test    eax, eax
0x14001e4a6  jnz     short loc_14001E4DA
0x14001e4a8  mov     eax, [rsp+0C8h+WatchdogInformation.DpcWatchdogLimit]
0x14001e4ac  test    eax, eax
0x14001e4ae  jz      short loc_14001E4C2
0x14001e4b0  imul    ecx, [rsp+0C8h+WatchdogInformation.DpcWatchdogCount], 64h ; 'd'
0x14001e4b5  lea     eax, [rax+rax*4]
0x14001e4b8  movzx   r14d, r14b
0x14001e4bc  cmp     ecx, eax
0x14001e4be  cmovb   r14d, ebx
0x14001e4c2  mov     eax, [rsp+0C8h+WatchdogInformation.DpcTimeLimit]
0x14001e4c6  test    eax, eax
0x14001e4c8  jz      short loc_14001E4DA
0x14001e4ca  imul    ecx, [rsp+0C8h+WatchdogInformation.DpcTimeCount], 64h ; 'd'
0x14001e4cf  lea     eax, [rax+rax*4]
0x14001e4d2  cmp     ecx, eax
0x14001e4d4  jb      loc_14001E752
0x14001e4da  test    r14b, r14b
0x14001e4dd  jnz     loc_14001E752
0x14001e4e3  lea     rdx, [r15+0E60h]
0x14001e4ea  mov     rax, [rdx]
0x14001e4ed  cmp     rax, rdx
0x14001e4f0  jz      short loc_14001E50B
0x14001e4f2  cmp     [rax-10h], rsi
0x14001e4f6  lea     rbx, [rax-0A8h]
0x14001e4fd  jz      loc_14001E5D3
0x14001e503  mov     rax, [rax]
0x14001e506  cmp     rax, rdx
0x14001e509  jnz     short loc_14001E4F2
0x14001e50b  lea     rcx, [r15+0E70h]
0x14001e512  mov     rax, [rcx]
0x14001e515  cmp     rax, rcx
0x14001e518  jz      short loc_14001E539
0x14001e51a  nop     word ptr [rax+rax+00h]
0x14001e520  cmp     [rax-10h], rsi
0x14001e524  lea     rbx, [rax-0A8h]
0x14001e52b  jz      loc_14001E5D3
0x14001e531  mov     rax, [rax]
0x14001e534  cmp     rax, rcx
0x14001e537  jnz     short loc_14001E520
0x14001e539  mov     rbp, [rsp+0C8h+DeviceObject]
0x14001e53e  movzx   edx, r13b; NewIrql
0x14001e542  lea     rcx, [r15+0E58h]; SpinLock
0x14001e549  call    cs:__imp_KeReleaseSpinLock
0x14001e550  nop     dword ptr [rax+rax+00h]
0x14001e555  mov     r8, [rbp+40h]
0x14001e559  mov     rax, [r8+1B8h]
0x14001e560  mov     eax, [rax]
0x14001e562  test    eax, eax
0x14001e564  jz      short loc_14001E584
0x14001e566  nop     word ptr [rax+rax+00000000h]
0x14001e570  mov     rcx, [r8+1B8h]
0x14001e577  lea     edx, [rax-1]
0x14001e57a  lock cmpxchg [rcx], edx
0x14001e57e  jz      short loc_14001E59B
0x14001e580  test    eax, eax
0x14001e582  jnz     short loc_14001E570
0x14001e584  mov     rcx, [r8+1B8h]
0x14001e58b  add     rcx, 8; RunRefCacheAware
0x14001e58f  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14001e596  nop     dword ptr [rax+rax+00h]
0x14001e59b  mov     r13, [rsp+0C8h+arg_10]
0x14001e5a3  mov     r15, [rsp+0C8h+arg_18]
0x14001e5ab  mov     rbx, [rsp+0C8h+arg_0]
0x14001e5b3  mov     rcx, [rsp+0C8h+var_30]
0x14001e5bb  xor     rcx, rsp; StackCookie
0x14001e5be  call    __security_check_cookie
0x14001e5c3  add     rsp, 0A0h
0x14001e5ca  pop     r14
0x14001e5cc  pop     r12
0x14001e5ce  pop     rdi
0x14001e5cf  pop     rsi
0x14001e5d0  pop     rbp
0x14001e5d1  retn
0x14001e5d3  test    rbx, rbx
0x14001e5d6  jz      loc_14001E539
0x14001e5dc  lea     rax, [rbx+0A8h]
0x14001e5e3  mov     r8, [rax]
0x14001e5e6  cmp     [r8+8], rax
0x14001e5ea  jnz     loc_14001E819
0x14001e5f0  mov     rcx, [rbx+0B0h]
0x14001e5f7  cmp     [rcx], rax
0x14001e5fa  jnz     loc_14001E819
0x14001e600  mov     [rcx], r8
0x14001e603  mov     [r8+8], rcx
0x14001e607  mov     rcx, [rdx]
0x14001e60a  cmp     [rcx+8], rdx
0x14001e60e  jnz     loc_14001E819
0x14001e614  mov     [rax], rcx
0x14001e617  xor     dil, dil
0x14001e61a  mov     [rax+8], rdx
0x14001e61e  mov     [rcx+8], rax
0x14001e622  mov     rcx, rbx
0x14001e625  mov     [rdx], rax
0x14001e628  lea     rdx, [rsp+0C8h+var_50]
0x14001e62d  call    cs:__imp_IoGetActivityIdIrp
0x14001e634  nop     dword ptr [rax+rax+00h]
0x14001e639  test    eax, eax
0x14001e63b  js      short loc_14001E659
0x14001e63d  lea     r8, [rsp+0C8h+var_70]
0x14001e642  mov     rcx, rbx
0x14001e645  lea     rdx, [rsp+0C8h+var_50]
0x14001e64a  mov     dil, 1
0x14001e64d  call    cs:__imp_IoPropagateActivityIdToThread
0x14001e654  nop     dword ptr [rax+rax+00h]
0x14001e659  cmp     cs:ClassPnPETWEnabled, 0
0x14001e660  jz      loc_14001E6F9
0x14001e666  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 2
0x14001e66d  jz      short loc_14001E6A8
0x14001e66f  mov     rax, [rbp+478h]
0x14001e676  mov     r9, rbx
0x14001e679  mov     ecx, [rax+0F28h]
0x14001e67f  mov     edx, [rax+0F18h]
0x14001e685  mov     eax, [rbp+24Ch]
0x14001e68b  mov     [rsp+0C8h+var_90], eax
0x14001e68f  mov     rax, [rbx+98h]
0x14001e696  mov     [rsp+0C8h+var_98], ecx
0x14001e69a  mov     [rsp+0C8h+var_A0], edx
0x14001e69e  mov     [rsp+0C8h+var_A8], rax
0x14001e6a3  call    McTemplateK0ppqqq_EtwWriteTransfer
0x14001e6a8  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 40h
0x14001e6af  jz      short loc_14001E6F9
0x14001e6b1  mov     r9d, [rbp+24Ch]
0x14001e6b8  lea     r8, [rsp+0C8h+var_50]
0x14001e6bd  mov     byte ptr [rsp+0C8h+var_A0], 4
0x14001e6c2  mov     dword ptr [rsp+0C8h+var_A8], 3
0x14001e6ca  call    McTemplateK0qdud_EtwWriteTransfer
0x14001e6cf  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 40h
0x14001e6d6  jz      short loc_14001E6F9
0x14001e6d8  mov     r9d, [rbp+24Ch]
0x14001e6df  lea     r8, [rsp+0C8h+var_50]
0x14001e6e4  mov     ebx, 1
0x14001e6e9  mov     byte ptr [rsp+0C8h+var_A0], 2
0x14001e6ee  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x14001e6f2  call    McTemplateK0qdud_EtwWriteTransfer
0x14001e6f7  jmp     short loc_14001E6FE
0x14001e6f9  mov     ebx, 1
0x14001e6fe  movzx   edx, r13b; NewIrql
0x14001e702  lea     rcx, [r15+0E58h]; SpinLock
0x14001e709  call    cs:__imp_KeReleaseSpinLock
0x14001e710  nop     dword ptr [rax+rax+00h]
0x14001e715  xor     edx, edx
0x14001e717  mov     rcx, rbp
0x14001e71a  call    ClasspServiceIdleRequest
0x14001e71f  test    dil, dil
0x14001e722  jz      short loc_14001E735
0x14001e724  mov     rcx, [rsp+0C8h+var_70]
0x14001e729  call    cs:__imp_IoClearActivityIdThread
0x14001e730  nop     dword ptr [rax+rax+00h]
0x14001e735  lea     rcx, [r15+0E58h]; SpinLock
0x14001e73c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001e743  nop     dword ptr [rax+rax+00h]
0x14001e748  movzx   edi, [rsp+0C8h+var_88]
0x14001e74d  jmp     loc_14001E489
0x14001e752  mov     rbp, [rsp+0C8h+DeviceObject]
0x14001e757  mov     rcx, rbp; DeviceObject
0x14001e75a  call    cs:__imp_IoAllocateWorkItem
0x14001e761  nop     dword ptr [rax+rax+00h]
0x14001e766  mov     rdi, rax
0x14001e769  call    cs:__imp_IoSizeofWorkItem
0x14001e770  nop     dword ptr [rax+rax+00h]
0x14001e775  mov     edx, eax
0x14001e777  mov     ecx, 40h ; '@'
0x14001e77c  add     rdx, 18h
0x14001e780  mov     r8d, 6F5A6353h
0x14001e786  call    cs:__imp_ExAllocatePool2
0x14001e78d  nop     dword ptr [rax+rax+00h]
0x14001e792  mov     rbx, rax
0x14001e795  test    rdi, rdi
0x14001e798  jz      short loc_14001E7FA
0x14001e79a  test    rax, rax
0x14001e79d  jz      short loc_14001E7E6
0x14001e79f  mov     r9d, 137h; Line
0x14001e7a5  lea     r8, aMinkernelStora_0; "minkernel\\storage\\classpnp\\clntirp.c"
0x14001e7ac  mov     rdx, rdi; Tag
0x14001e7af  mov     rcx, rbp; DeviceObject
0x14001e7b2  call    ClassAcquireRemoveLockEx
0x14001e7b7  mov     r9, rbx; Context
0x14001e7ba  mov     [rbx], rdi
0x14001e7bd  mov     r8d, 1; QueueType
0x14001e7c3  mov     [rbx+8], rsi
0x14001e7c7  lea     rdx, ClasspIoBoostPriorityContext; WorkerRoutine
0x14001e7ce  mov     [rbx+10h], r12d
0x14001e7d2  mov     rcx, rdi; IoWorkItem
0x14001e7d5  call    cs:__imp_IoQueueWorkItem
0x14001e7dc  nop     dword ptr [rax+rax+00h]
0x14001e7e1  jmp     loc_14001E53E
0x14001e7e6  mov     rcx, rdi; IoWorkItem
0x14001e7e9  call    cs:__imp_IoFreeWorkItem
0x14001e7f0  nop     dword ptr [rax+rax+00h]
0x14001e7f5  jmp     loc_14001E53E
0x14001e7fa  test    rbx, rbx
0x14001e7fd  jz      loc_14001E53E
0x14001e803  xor     edx, edx; Tag
0x14001e805  mov     rcx, rbx; P
0x14001e808  call    cs:__imp_ExFreePoolWithTag
0x14001e80f  nop     dword ptr [rax+rax+00h]
0x14001e814  jmp     loc_14001E53E
0x14001e819  mov     ecx, 3
0x14001e81e  int     29h; Win8: RtlFailFast(ecx)
0x14001e820  mov     r8, [r14+40h]
0x14001e824  mov     rax, [r8+1B8h]
0x14001e82b  mov     eax, [rax]
0x14001e82d  test    eax, eax
0x14001e82f  jz      short loc_14001E849
  ... truncated ...
```
