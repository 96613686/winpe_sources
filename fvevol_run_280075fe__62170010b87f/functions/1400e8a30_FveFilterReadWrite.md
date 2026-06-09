# FveFilterReadWrite

- ea: `0x1400e8a30`
- end: `0x1400e9048`
- name: `FveFilterReadWrite`
- size: `1560`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x140028c84`

## callees

- `0x140008070`
- `0x140008288`
- `0x140008428`
- `0x140008dc0`
- `0x140008f20`
- `0x1400293a0`
- `0x14002c140`
- `0x1400baca0`
- `0x1400cee94`
- `0x1400d330c`
- `0x1400d3820`
- `0x1400d6080`
- `0x1400d89b0`
- `0x1400d9450`
- `0x1400dd088`
- `0x1400dfce8`
- `0x1400e49ec`
- `0x1400e572c`
- `0x1400e8a30`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400e8fd7`
- `ntoskrnl!KfRaiseIrql` at `0x1400e8fd7`
- `ntoskrnl!KeLowerIrql` at `0x1400e9007`
- `ntoskrnl!KeLowerIrql` at `0x1400e9007`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400e8a77`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400e8a77`
- `ntoskrnl!IoGetPagingIoPriority` at `0x1400e8b0c`
- `ntoskrnl!IoGetPagingIoPriority` at `0x1400e8b0c`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x1400e8ad5`
- `ntoskrnl!KeQueryEffectivePriorityThread` at `0x1400e8ad5`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400e8af0`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400e8af0`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8e13`
- `ntoskrnl!KeBugCheckEx` at `0x1400e8e13`

## string_xrefs

- `0x1400e8b2a`: `WRITE`
- `0x1400e8fae`: `WRITE`

## pseudocode

```c
__int64 __fastcall FveFilterReadWrite(__int64 a1, IRP *a2, char a3, unsigned __int64 a4, unsigned int a5)
{
  char v5; // bl
  unsigned int v7; // ebp
  IO_PRIORITY_HINT IoPriorityHint; // r15d
  unsigned int v12; // r13d
  PETHREAD Thread; // rcx
  char PriorityThread; // bp
  char EffectivePriorityThread; // r15
  struct _KTHREAD *v16; // rcx
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  const char *v18; // rdx
  unsigned __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // r8
  bool v22; // zf
  __int64 *v23; // rdx
  KIRQL v24; // bp
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // r8
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  int v31; // r8d
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rbx
  PVOID v36; // r15
  _QWORD *v37; // rax
  __int64 v38; // rax
  char IsPagingRequest; // al
  int v40; // r8d
  const char *v41; // rax
  char PagingIoPriority; // [rsp+60h] [rbp-68h]
  ULONG SortKey; // [rsp+78h] [rbp-50h]
  struct _LIST_ENTRY *Flink; // [rsp+80h] [rbp-48h]
  char v45; // [rsp+D0h] [rbp+8h] BYREF
  IO_PRIORITY_HINT v46; // [rsp+D8h] [rbp+10h]

  Flink = a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
  v5 = (char)Flink;
  v7 = BYTE1(Flink);
  v45 = 0;
  IoPriorityHint = IoGetIoPriorityHint(a2);
  v46 = IoPriorityHint;
  v12 = a5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    Thread = a2->Tail.Overlay.Thread;
    PriorityThread = -1;
    if ( Thread )
      EffectivePriorityThread = KeQueryEffectivePriorityThread(Thread);
    else
      EffectivePriorityThread = -1;
    v16 = a2->Tail.Overlay.Thread;
    if ( v16 )
      PriorityThread = KeQueryPriorityThread(v16);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    PagingIoPriority = IoGetPagingIoPriority(a2);
    v18 = "WRITE";
    if ( !a3 )
      v18 = "READ";
    WPP_SF_qsqiiDdddd(
      (_DWORD)AttachedDevice,
      (_DWORD)v18,
      a4 + v12,
      a1,
      (__int64)v18,
      (char)a2,
      a4,
      a4 + v12,
      v12,
      PriorityThread,
      EffectivePriorityThread,
      v46,
      PagingIoPriority);
    v5 = (char)Flink;
    v7 = BYTE1(Flink);
    IoPriorityHint = v46;
  }
  v19 = *(unsigned int *)(a1 + 1308);
  if ( (((_DWORD)v19 - 1) & (unsigned int)v19) != 0 || !(_DWORD)v19 )
    v20 = v12 % (unsigned int)v19 == 0;
  else
    v20 = (v12 & ((_DWORD)v19 - 1)) == 0;
  if ( v20 )
  {
    v21 = *(unsigned int *)(a1 + 1308);
    if ( ((v19 - 1) & v19) != 0 || !(_DWORD)v19 )
      v22 = a4 % v19 == 0;
    else
      v22 = (a4 & (v19 - 1)) == 0;
    if ( v22 )
    {
      LOBYTE(v21) = a3;
      FveCollectIoStats(a1, a2, v21);
      v23 = FVE_PERF_WRITE_REQUEST_START;
      v24 = 0;
      a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      if ( !a3 )
        v23 = (__int64 *)&FVE_PERF_READ_REQUEST_START;
      FvePerfTraceDevPtr(a1, v23, a2);
      v26 = *(_QWORD *)(a1 + 8);
      if ( !*(_BYTE *)(v26 + 104) || *(_QWORD *)(v26 + 112) )
      {
        if ( a3 )
          _InterlockedIncrement64((volatile signed __int64 *)(a1 + 664));
        else
          _InterlockedIncrement64((volatile signed __int64 *)(a1 + 648));
      }
      if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v25) )
      {
        if ( (*(_DWORD *)(a1 + 808) & 0x19) != 0 )
        {
          v27 = *(_QWORD *)(a1 + 4736);
          if ( v27 )
          {
            if ( *(_DWORD *)(v27 + 88) && *(_QWORD *)(a1 + 1008) )
              goto LABEL_61;
          }
        }
      }
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 9680LL) & 4) == 0 )
      {
        if ( (unsigned __int8)FveShouldTryInlineIceIrp(a1, (_DWORD)a2, a4, v12, a3, 0) )
        {
          LOBYTE(v28) = a3;
          if ( (unsigned __int8)FveTryIssueIceIrp(a1, a2, v28, a4, v12) )
          {
            v29 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            {
              return 259;
            }
            v30 = 68;
LABEL_46:
            WPP_SF_(v29->AttachedDevice, v30, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids);
            return 259;
          }
        }
      }
      if ( FveTryFastPathIo(a1, a2, a3, a4, v12) )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          return 259;
        }
        v30 = 69;
        goto LABEL_46;
      }
      if ( a3 && !(unsigned __int8)FveWriteUsingWorkerQueues(a1, a2->Tail.Overlay.Thread, a4, v12, v5, IoPriorityHint) )
      {
        if ( FveTryInlineWriteEncrypt(a1, a2, a4, v12, &v45) )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids);
          }
          if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v33) )
            return 259;
          v34 = *(_QWORD *)(a1 + 4736);
          if ( !v34 || !*(_DWORD *)(v34 + 88) || (*(_DWORD *)(a1 + 808) & 0x19) == 0 || !*(_QWORD *)(a1 + 1008) && v45 )
            return 259;
LABEL_61:
          KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids);
        }
      }
      LOBYTE(v31) = a3;
      v35 = AcquireRequestResources(a1, (_DWORD)a2, v31, a4, v12);
      if ( v35 )
      {
        v36 = 0;
        SortKey = 0;
        if ( (*(_DWORD *)(a1 + 808) & 0x100) != 0 )
        {
          v37 = *(_QWORD **)(a1 + 736);
          if ( v37 )
          {
            if ( *v37 )
            {
              v36 = a2->Tail.Overlay.DriverContext[3];
              SortKey = a2->Tail.Overlay.DeviceQueueEntry.SortKey;
              a2->Tail.Overlay.DriverContext[3] = 0;
              a2->Tail.Overlay.DriverContext[2] = 0;
            }
          }
        }
        *(_QWORD *)v35 = a2;
        *(_QWORD *)(v35 + 8) = MEMORY[0xFFFFF78000000008];
        *(_QWORD *)(v35 + 16) = 0;
        *(_QWORD *)(v35 + 24) = 0;
        *(_QWORD *)(v35 + 32) = 0;
        *(_QWORD *)(v35 + 40) = 0;
        if ( *(_QWORD *)(a1 + 4736) )
          v38 = 0;
        else
          v38 = FveTestResolveRwStorageRequest(a1, a2, v36);
        *(_QWORD *)(v35 + 192) = v38;
        *(_QWORD *)(v35 + 48) = a1;
        *(_QWORD *)(v35 + 64) = a4;
        *(_DWORD *)(v35 + 72) = v12;
        *(_BYTE *)(v35 + 274) = a3;
        IsPagingRequest = FveIsPagingRequest(a1, a2, a4, v12);
        *(_DWORD *)(v35 + 76) = v46;
        *(_DWORD *)(v35 + 84) = BYTE1(Flink);
        *(_BYTE *)(v35 + 273) = IsPagingRequest;
        *(_BYTE *)(v35 + 80) = (_BYTE)Flink;
        if ( *(_BYTE *)(a1 + 1477) )
          *(_DWORD *)(v35 + 136) = (unsigned __int8)HIBYTE(LODWORD(a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
        *(_DWORD *)(v35 + 88) = SortKey;
        *(_QWORD *)(v35 + 56) = v36;
        if ( IsPagingRequest
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v41 = "WRITE";
          if ( !a3 )
            v41 = "READ";
          WPP_SF_qsq(WPP_GLOBAL_Control->AttachedDevice, 72, v40, a1, (__int64)v41, (char)a2);
        }
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)v35;
        if ( !(_BYTE)Flink )
          v24 = KfRaiseIrql(1u);
        if ( a3 )
          ProcessResourcedWriteRequest(v35);
        else
          ProcessResourcedReadRequest(v35);
        if ( !(_BYTE)Flink )
          KeLowerIrql(v24);
      }
      else
      {
        PutIrpOnResourceWaitQueue(a1, a2);
      }
      return 259;
    }
  }
  return FveFailRundownReadWriteIrp(a1, a2, 3221225485LL, v7);
}

```

## disassembly

```asm
0x1400e8a30  mov     r11, rsp
0x1400e8a33  mov     [r11+18h], rbx
0x1400e8a37  push    rbp
0x1400e8a38  push    rsi
0x1400e8a39  push    rdi
0x1400e8a3a  push    r12
0x1400e8a3c  push    r13
0x1400e8a3e  push    r14
0x1400e8a40  push    r15
0x1400e8a42  sub     rsp, 90h
0x1400e8a49  mov     rbx, [rdx+78h]
0x1400e8a4d  mov     rdi, rcx
0x1400e8a50  mov     rax, rbx
0x1400e8a53  mov     [rsp+0C8h+var_48], rbx
0x1400e8a5b  sar     rax, 8
0x1400e8a5f  mov     rcx, rdx; Irp
0x1400e8a62  movzx   ebp, al
0x1400e8a65  mov     r12, r9
0x1400e8a68  mov     [rsp+0C8h+var_58], ebp
0x1400e8a6c  mov     r14b, r8b
0x1400e8a6f  mov     rsi, rdx
0x1400e8a72  mov     byte ptr [r11+8], 0
0x1400e8a77  call    cs:__imp_IoGetIoPriorityHint
0x1400e8a7e  nop     dword ptr [rax+rax+00h]
0x1400e8a83  mov     r15d, eax
0x1400e8a86  mov     [rsp+0C8h+arg_8], eax
0x1400e8a8d  mov     rdx, cs:WPP_GLOBAL_Control
0x1400e8a94  lea     rax, WPP_GLOBAL_Control
0x1400e8a9b  mov     r13d, [rsp+0C8h+arg_20]
0x1400e8aa3  cmp     rdx, rax
0x1400e8aa6  jz      loc_1400E8B81
0x1400e8aac  mov     ecx, [rdx+2Ch]
0x1400e8aaf  test    cl, cl
0x1400e8ab1  jns     loc_1400E8B81
0x1400e8ab7  cmp     byte ptr [rdx+29h], 4
0x1400e8abb  jb      loc_1400E8B81
0x1400e8ac1  mov     rcx, [rsi+98h]
0x1400e8ac8  or      ebp, 0FFFFFFFFh
0x1400e8acb  test    rcx, rcx
0x1400e8ace  jnz     short loc_1400E8AD5
0x1400e8ad0  mov     r15d, ebp
0x1400e8ad3  jmp     short loc_1400E8AE4
0x1400e8ad5  call    cs:__imp_KeQueryEffectivePriorityThread
0x1400e8adc  nop     dword ptr [rax+rax+00h]
0x1400e8ae1  mov     r15d, eax
0x1400e8ae4  mov     rcx, [rsi+98h]; Thread
0x1400e8aeb  test    rcx, rcx
0x1400e8aee  jz      short loc_1400E8AFE
0x1400e8af0  call    cs:__imp_KeQueryPriorityThread
0x1400e8af7  nop     dword ptr [rax+rax+00h]
0x1400e8afc  mov     ebp, eax
0x1400e8afe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8b05  mov     rbx, [rcx+18h]
0x1400e8b09  mov     rcx, rsi; Irp
0x1400e8b0c  call    cs:__imp_IoGetPagingIoPriority
0x1400e8b13  nop     dword ptr [rax+rax+00h]
0x1400e8b18  mov     dword ptr [rsp+0C8h+var_68], eax
0x1400e8b1c  lea     rcx, aRead_1; "READ"
0x1400e8b23  test    r14b, r14b
0x1400e8b26  lea     r8, [r12+r13]
0x1400e8b2a  lea     rdx, aWrite; "WRITE"
0x1400e8b31  mov     r9, rdi
0x1400e8b34  cmovz   rdx, rcx
0x1400e8b38  mov     ecx, [rsp+0C8h+arg_8]
0x1400e8b3f  mov     [rsp+0C8h+var_70], ecx
0x1400e8b43  mov     rcx, rbx
0x1400e8b46  mov     [rsp+0C8h+var_78], r15d
0x1400e8b4b  mov     [rsp+0C8h+var_80], ebp
0x1400e8b4f  mov     [rsp+0C8h+var_88], r13d
0x1400e8b54  mov     [rsp+0C8h+var_90], r8
0x1400e8b59  mov     [rsp+0C8h+var_98], r12
0x1400e8b5e  mov     [rsp+0C8h+var_A0], rsi
0x1400e8b63  mov     [rsp+0C8h+BugCheckParameter4], rdx
0x1400e8b68  call    WPP_SF_qsqiiDdddd
0x1400e8b6d  mov     rbx, [rsp+0C8h+var_48]
0x1400e8b75  mov     ebp, [rsp+0C8h+var_58]
0x1400e8b79  mov     r15d, [rsp+0C8h+arg_8]
0x1400e8b81  mov     ecx, [rdi+51Ch]
0x1400e8b87  lea     eax, [rcx-1]
0x1400e8b8a  test    ecx, eax
0x1400e8b8c  jnz     short loc_1400E8B97
0x1400e8b8e  test    ecx, ecx
0x1400e8b90  jz      short loc_1400E8B97
0x1400e8b92  and     eax, r13d
0x1400e8b95  jmp     short loc_1400E8BA0
0x1400e8b97  xor     edx, edx
0x1400e8b99  mov     eax, r13d
0x1400e8b9c  div     ecx
0x1400e8b9e  test    edx, edx
0x1400e8ba0  jnz     loc_1400E9018
0x1400e8ba6  lea     rax, [rcx-1]
0x1400e8baa  mov     r8, rcx
0x1400e8bad  test    rcx, rax
0x1400e8bb0  jnz     short loc_1400E8BBB
0x1400e8bb2  test    ecx, ecx
0x1400e8bb4  jz      short loc_1400E8BBB
0x1400e8bb6  and     rax, r12
0x1400e8bb9  jmp     short loc_1400E8BC6
0x1400e8bbb  xor     edx, edx
0x1400e8bbd  mov     rax, r12
0x1400e8bc0  div     r8
0x1400e8bc3  test    rdx, rdx
0x1400e8bc6  jnz     loc_1400E9018
0x1400e8bcc  mov     r8b, r14b
0x1400e8bcf  mov     rdx, rsi
0x1400e8bd2  mov     rcx, rdi
0x1400e8bd5  call    FveCollectIoStats
0x1400e8bda  mov     rax, [rsi+0B8h]
0x1400e8be1  lea     rdx, FVE_PERF_WRITE_REQUEST_START
0x1400e8be8  xor     ebp, ebp
0x1400e8bea  mov     r8, rsi
0x1400e8bed  mov     rcx, rdi
0x1400e8bf0  or      byte ptr [rax+3], 1
0x1400e8bf4  lea     rax, FVE_PERF_READ_REQUEST_START
0x1400e8bfb  test    r14b, r14b
0x1400e8bfe  cmovz   rdx, rax
0x1400e8c02  call    FvePerfTraceDevPtr
0x1400e8c07  mov     rax, [rdi+8]
0x1400e8c0b  cmp     [rax+68h], bpl
0x1400e8c0f  jz      short loc_1400E8C1A
0x1400e8c11  mov     rax, [rax+70h]
0x1400e8c15  test    rax, rax
0x1400e8c18  jz      short loc_1400E8C31
0x1400e8c1a  test    r14b, r14b
0x1400e8c1d  jz      short loc_1400E8C29
0x1400e8c1f  lock inc qword ptr [rdi+298h]
0x1400e8c27  jmp     short loc_1400E8C31
0x1400e8c29  lock inc qword ptr [rdi+288h]
0x1400e8c31  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400e8c36  test    eax, eax
0x1400e8c38  jz      short loc_1400E8C62
0x1400e8c3a  mov     eax, [rdi+328h]
0x1400e8c40  test    al, 19h
0x1400e8c42  jz      short loc_1400E8C62
0x1400e8c44  mov     rax, [rdi+1280h]
0x1400e8c4b  test    rax, rax
0x1400e8c4e  jz      short loc_1400E8C62
0x1400e8c50  cmp     [rax+58h], ebp
0x1400e8c53  jz      short loc_1400E8C62
0x1400e8c55  cmp     [rdi+3F0h], rbp
0x1400e8c5c  jnz     loc_1400E8DFF
0x1400e8c62  mov     rax, [rdi+8]
0x1400e8c66  mov     ecx, [rax+25D0h]
0x1400e8c6c  test    cl, 4
0x1400e8c6f  jnz     short loc_1400E8CD1
0x1400e8c71  mov     byte ptr [rsp+0C8h+var_A0], bpl
0x1400e8c76  mov     r9d, r13d
0x1400e8c79  mov     r8, r12
0x1400e8c7c  mov     byte ptr [rsp+0C8h+BugCheckParameter4], r14b
0x1400e8c81  mov     rdx, rsi
0x1400e8c84  mov     rcx, rdi
0x1400e8c87  call    FveShouldTryInlineIceIrp
0x1400e8c8c  test    al, al
0x1400e8c8e  jz      short loc_1400E8CD1
0x1400e8c90  mov     r9, r12
0x1400e8c93  mov     dword ptr [rsp+0C8h+BugCheckParameter4], r13d
0x1400e8c98  mov     r8b, r14b
0x1400e8c9b  mov     rdx, rsi
0x1400e8c9e  mov     rcx, rdi
0x1400e8ca1  call    FveTryIssueIceIrp
0x1400e8ca6  test    al, al
0x1400e8ca8  jz      short loc_1400E8CD1
0x1400e8caa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8cb1  lea     rax, WPP_GLOBAL_Control
0x1400e8cb8  cmp     rcx, rax
0x1400e8cbb  jz      short loc_1400E8D20
0x1400e8cbd  mov     eax, [rcx+2Ch]
0x1400e8cc0  test    al, al
0x1400e8cc2  jns     short loc_1400E8D20
0x1400e8cc4  cmp     byte ptr [rcx+29h], 5
0x1400e8cc8  jb      short loc_1400E8D20
0x1400e8cca  mov     edx, 44h ; 'D'
0x1400e8ccf  jmp     short loc_1400E8D10
0x1400e8cd1  mov     r9, r12
0x1400e8cd4  mov     dword ptr [rsp+0C8h+BugCheckParameter4], r13d
0x1400e8cd9  mov     r8b, r14b
0x1400e8cdc  mov     rdx, rsi
0x1400e8cdf  mov     rcx, rdi
0x1400e8ce2  call    FveTryFastPathIo
0x1400e8ce7  test    al, al
0x1400e8ce9  jz      short loc_1400E8D2A
0x1400e8ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8cf2  lea     rax, WPP_GLOBAL_Control
0x1400e8cf9  cmp     rcx, rax
0x1400e8cfc  jz      short loc_1400E8D20
0x1400e8cfe  mov     eax, [rcx+2Ch]
0x1400e8d01  test    al, al
0x1400e8d03  jns     short loc_1400E8D20
0x1400e8d05  cmp     byte ptr [rcx+29h], 5
0x1400e8d09  jb      short loc_1400E8D20
0x1400e8d0b  mov     edx, 45h ; 'E'
0x1400e8d10  mov     rcx, [rcx+18h]
0x1400e8d14  lea     r8, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids
0x1400e8d1b  call    WPP_SF_
0x1400e8d20  mov     eax, 103h
0x1400e8d25  jmp     loc_1400E902C
0x1400e8d2a  test    r14b, r14b
0x1400e8d2d  jz      loc_1400E8E55
0x1400e8d33  mov     rdx, [rsi+98h]
0x1400e8d3a  mov     r9d, r13d
0x1400e8d3d  mov     dword ptr [rsp+0C8h+var_A0], r15d
0x1400e8d42  mov     r8, r12
0x1400e8d45  mov     rcx, rdi
0x1400e8d48  mov     byte ptr [rsp+0C8h+BugCheckParameter4], bl
0x1400e8d4c  call    FveWriteUsingWorkerQueues
0x1400e8d51  test    al, al
0x1400e8d53  jnz     loc_1400E8E55
0x1400e8d59  lea     rax, [rsp+0C8h+arg_0]
0x1400e8d61  mov     r9d, r13d
0x1400e8d64  mov     r8, r12
0x1400e8d67  mov     [rsp+0C8h+BugCheckParameter4], rax
0x1400e8d6c  mov     rdx, rsi
0x1400e8d6f  mov     rcx, rdi
0x1400e8d72  call    FveTryInlineWriteEncrypt
0x1400e8d77  test    al, al
0x1400e8d79  jz      loc_1400E8E20
0x1400e8d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8d86  lea     rax, WPP_GLOBAL_Control
0x1400e8d8d  cmp     rcx, rax
0x1400e8d90  jz      short loc_1400E8DB4
0x1400e8d92  mov     eax, [rcx+2Ch]
0x1400e8d95  test    al, al
0x1400e8d97  jns     short loc_1400E8DB4
0x1400e8d99  cmp     byte ptr [rcx+29h], 5
0x1400e8d9d  jb      short loc_1400E8DB4
0x1400e8d9f  mov     rcx, [rcx+18h]
0x1400e8da3  lea     r8, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids
0x1400e8daa  mov     edx, 46h ; 'F'
0x1400e8daf  call    WPP_SF_
0x1400e8db4  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400e8db9  test    eax, eax
0x1400e8dbb  jz      loc_1400E8D20
0x1400e8dc1  mov     rax, [rdi+1280h]
0x1400e8dc8  test    rax, rax
0x1400e8dcb  jz      loc_1400E8D20
0x1400e8dd1  cmp     [rax+58h], ebp
0x1400e8dd4  jz      loc_1400E8D20
0x1400e8dda  mov     eax, [rdi+328h]
0x1400e8de0  test    al, 19h
0x1400e8de2  jz      loc_1400E8D20
0x1400e8de8  cmp     [rdi+3F0h], rbp
0x1400e8def  jnz     short loc_1400E8DFF
0x1400e8df1  cmp     [rsp+0C8h+arg_0], bpl
0x1400e8df9  jnz     loc_1400E8D20
0x1400e8dff  xor     r9d, r9d; BugCheckParameter3
0x1400e8e02  mov     [rsp+0C8h+BugCheckParameter4], rbp; BugCheckParameter4
0x1400e8e07  xor     r8d, r8d; BugCheckParameter2
0x1400e8e0a  mov     ecx, 120h; BugCheckCode
0x1400e8e0f  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400e8e13  call    cs:__imp_KeBugCheckEx
0x1400e8e20  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8e27  lea     rax, WPP_GLOBAL_Control
0x1400e8e2e  cmp     rcx, rax
0x1400e8e31  jz      short loc_1400E8E55
0x1400e8e33  mov     eax, [rcx+2Ch]
0x1400e8e36  test    al, al
0x1400e8e38  jns     short loc_1400E8E55
0x1400e8e3a  cmp     byte ptr [rcx+29h], 5
0x1400e8e3e  jb      short loc_1400E8E55
0x1400e8e40  mov     rcx, [rcx+18h]
0x1400e8e44  lea     r8, WPP_967c1297b27d3b8fbf952ae9e74b6717_Traceguids
0x1400e8e4b  mov     edx, 47h ; 'G'
0x1400e8e50  call    WPP_SF_
0x1400e8e55  mov     r9, r12
0x1400e8e58  mov     dword ptr [rsp+0C8h+BugCheckParameter4], r13d
0x1400e8e5d  mov     r8b, r14b
0x1400e8e60  mov     rdx, rsi
0x1400e8e63  mov     rcx, rdi
0x1400e8e66  call    AcquireRequestResources
0x1400e8e6b  mov     rbx, rax
0x1400e8e6e  test    rax, rax
0x1400e8e71  jnz     short loc_1400E8E83
0x1400e8e73  mov     rdx, rsi
0x1400e8e76  mov     rcx, rdi
0x1400e8e79  call    PutIrpOnResourceWaitQueue
0x1400e8e7e  jmp     loc_1400E8D20
0x1400e8e83  xor     ecx, ecx
0x1400e8e85  test    dword ptr [rdi+328h], 100h
0x1400e8e8f  mov     r15d, ecx
0x1400e8e92  mov     [rsp+0C8h+var_50], ecx
0x1400e8e96  jz      short loc_1400E8EC8
0x1400e8e98  mov     rax, [rdi+2E0h]
0x1400e8e9f  test    rax, rax
0x1400e8ea2  jz      short loc_1400E8EC8
0x1400e8ea4  cmp     [rax], rcx
0x1400e8ea7  jz      short loc_1400E8EC8
0x1400e8ea9  mov     eax, [rsi+88h]
0x1400e8eaf  mov     r15, [rsi+90h]
0x1400e8eb6  mov     [rsp+0C8h+var_50], eax
0x1400e8eba  mov     [rsi+90h], rcx
0x1400e8ec1  mov     [rsi+88h], rcx
0x1400e8ec8  mov     [rbx], rsi
0x1400e8ecb  mov     rax, ds:0FFFFF78000000008h
0x1400e8ed5  mov     [rbx+8], rax
0x1400e8ed9  mov     [rbx+10h], rcx
0x1400e8edd  mov     [rbx+18h], rcx
0x1400e8ee1  mov     [rbx+20h], rcx
0x1400e8ee5  mov     [rbx+28h], rcx
0x1400e8ee9  cmp     [rdi+1280h], rcx
0x1400e8ef0  jnz     short loc_1400E8F02
  ... truncated ...
```
