# NatDispatch

- ea: `0x140002260`
- end: `0x1400027bd`
- name: `NatDispatch`
- size: `1373`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002260`
- `0x140002b38`
- `0x1400051e8`
- `0x14000c8b0`
- `0x14000fe9c`
- `0x140010df4`
- `0x140017718`
- `0x14001d490`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400023d6`
- `ntoskrnl!IofCompleteRequest` at `0x140002762`
- `ntoskrnl!IofCompleteRequest` at `0x1400023d6`
- `ntoskrnl!IofCompleteRequest` at `0x140002762`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002621`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140002621`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002563`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000272f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002563`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000272f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000253e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002637`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000253e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002637`

## pseudocode

```c
__int64 __fastcall NatDispatch(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  __int64 *v4; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int v6; // esi
  char v7; // r15
  UCHAR MajorFunction; // al
  unsigned int v9; // eax
  __int64 v10; // r9
  struct _IRP *MasterIrp; // rsi
  KIRQL v12; // al
  HANDLE CurrentProcessId; // r14
  KIRQL v14; // r12
  unsigned int v16; // [rsp+90h] [rbp+18h] BYREF

  v4 = WPP_bf6394432411365576a648e5337212b4_Traceguids;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_bf6394432411365576a648e5337212b4_Traceguids);
    v4 = WPP_bf6394432411365576a648e5337212b4_Traceguids;
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v16 = 0;
  v6 = 0;
  Irp->IoStatus.Status = 0;
  v7 = 1;
  Irp->IoStatus.Information = 0;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( !CurrentStackLocation->MajorFunction )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_bf6394432411365576a648e5337212b4_Traceguids,
        *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
    }
    if ( Irp->RequestorMode != 1 && (CurrentStackLocation->Flags & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_bf6394432411365576a648e5337212b4_Traceguids);
      }
      CurrentStackLocation->FileObject->FsContext = 0;
      goto LABEL_83;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_bf6394432411365576a648e5337212b4_Traceguids,
        *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
    }
    CurrentProcessId = PsGetCurrentProcessId();
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
    if ( *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy || Irp->RequestorMode != 1 )
    {
      if ( CurrentProcessId != (HANDLE)WPP_MAIN_CB.DeviceQueue.Lock )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bf6394432411365576a648e5337212b4_Traceguids);
        }
        v6 = -1073741790;
        goto LABEL_80;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_bf6394432411365576a648e5337212b4_Traceguids);
      }
      ++*(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_bf6394432411365576a648e5337212b4_Traceguids);
      }
      WPP_MAIN_CB.DeviceQueue.Lock = (KSPIN_LOCK)CurrentProcessId;
      *(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy = 1;
    }
    CurrentStackLocation->FileObject->FsContext = (PVOID)1;
LABEL_80:
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v14);
    goto LABEL_81;
  }
  if ( MajorFunction == 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_bf6394432411365576a648e5337212b4_Traceguids,
        *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
    }
    if ( CurrentStackLocation->FileObject->FsContext == (PVOID)1 )
    {
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
      if ( !--*(_DWORD *)&WPP_MAIN_CB.DeviceQueue.Busy )
        WPP_MAIN_CB.DeviceQueue.Lock = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink, v12);
    }
    goto LABEL_83;
  }
  if ( MajorFunction != 14 )
  {
    if ( MajorFunction == 18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_bf6394432411365576a648e5337212b4_Traceguids,
          *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
      }
      NatDeleteAnyAssociatedInterface(CurrentStackLocation->FileObject, Irp, v4);
      NatCleanupAnyAssociatedRedirect(CurrentStackLocation->FileObject);
      NatCleanupAnyAssociatedNotification(CurrentStackLocation->FileObject);
      NatDeleteAnyAssociatedDynamicTicket(CurrentStackLocation->FileObject);
      goto LABEL_83;
    }
    if ( MajorFunction != 23 )
    {
LABEL_83:
      Irp->IoStatus.Information = v16;
      Irp->IoStatus.Status = v6;
      IofCompleteRequest(Irp, 0);
      goto LABEL_84;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_bf6394432411365576a648e5337212b4_Traceguids,
        *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
    }
    v9 = NatExecuteSystemControl(DeviceObject, Irp);
    v6 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_23:
        v7 = 0;
        IofCompleteRequest(Irp, 0);
        goto LABEL_81;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_bf6394432411365576a648e5337212b4_Traceguids, v9);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      LOBYTE(v10) = 1;
      WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_bf6394432411365576a648e5337212b4_Traceguids, v10);
    }
    goto LABEL_23;
  }
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      WPP_bf6394432411365576a648e5337212b4_Traceguids,
      *(unsigned int *)&WPP_MAIN_CB.DeviceQueue.Busy);
  }
  v6 = NatpExecuteIoDeviceControl(
         Irp,
         CurrentStackLocation->FileObject,
         (unsigned int)Irp->RequestorMode,
         MasterIrp,
         CurrentStackLocation->Parameters.Create.Options,
         MasterIrp,
         CurrentStackLocation->Parameters.Read.Length,
         CurrentStackLocation->Parameters.Read.ByteOffset.LowPart,
         &v16);
  if ( v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_bf6394432411365576a648e5337212b4_Traceguids, v6);
  }
LABEL_81:
  if ( v6 != 259 && v7 )
    goto LABEL_83;
LABEL_84:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_bf6394432411365576a648e5337212b4_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140002260  mov     [rsp+arg_0], rbp
0x140002265  mov     [rsp+arg_18], rsi
0x14000226a  push    rdi
0x14000226b  push    r12
0x14000226d  push    r13
0x14000226f  push    r14
0x140002271  push    r15
0x140002273  sub     rsp, 50h
0x140002277  mov     rbp, rdx
0x14000227a  mov     r14, rcx
0x14000227d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002284  lea     r12, WPP_GLOBAL_Control
0x14000228b  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002292  mov     r13d, 1
0x140002298  cmp     rcx, r12
0x14000229b  jz      short loc_1400022BF
0x14000229d  mov     eax, [rcx+2Ch]
0x1400022a0  test    r13b, al
0x1400022a3  jz      short loc_1400022BF
0x1400022a5  cmp     byte ptr [rcx+29h], 6
0x1400022a9  jb      short loc_1400022BF
0x1400022ab  mov     rcx, [rcx+18h]
0x1400022af  lea     edx, [r13+9]
0x1400022b3  call    WPP_SF_
0x1400022b8  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x1400022bf  mov     rdi, [rbp+0B8h]
0x1400022c6  xor     ecx, ecx
0x1400022c8  mov     [rsp+78h+arg_10], ecx
0x1400022cf  mov     esi, ecx
0x1400022d1  mov     [rbp+30h], ecx
0x1400022d4  mov     r15b, r13b
0x1400022d7  mov     [rbp+38h], rcx
0x1400022db  mov     al, [rdi]
0x1400022dd  mov     [rsp+78h+arg_8], r13b
0x1400022e5  test    al, al
0x1400022e7  jz      loc_140002574
0x1400022ed  cmp     al, 2
0x1400022ef  jz      loc_1400024FA
0x1400022f5  cmp     al, 0Eh
0x1400022f7  jz      loc_14000243F
0x1400022fd  cmp     al, 12h
0x1400022ff  jz      loc_1400023E7
0x140002305  cmp     al, 17h
0x140002307  jnz     loc_14000274F
0x14000230d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002314  cmp     rcx, r12
0x140002317  jz      short loc_14000233C
0x140002319  mov     eax, [rcx+2Ch]
0x14000231c  test    r13b, al
0x14000231f  jz      short loc_14000233C
0x140002321  cmp     byte ptr [rcx+29h], 5
0x140002325  jb      short loc_14000233C
0x140002327  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000232e  mov     edx, 15h
0x140002333  mov     rcx, [rcx+18h]
0x140002337  call    WPP_SF_d
0x14000233c  lea     r8, [rsp+78h+arg_8]
0x140002344  mov     rdx, rbp; Irp
0x140002347  mov     rcx, r14; DeviceObject
0x14000234a  call    NatExecuteSystemControl
0x14000234f  mov     r15b, [rsp+78h+arg_8]
0x140002357  mov     esi, eax
0x140002359  test    eax, eax
0x14000235b  jz      short loc_14000238F
0x14000235d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002364  cmp     rcx, r12
0x140002367  jz      short loc_1400023C5
0x140002369  mov     edx, [rcx+2Ch]
0x14000236c  test    r13b, dl
0x14000236f  jz      short loc_14000238F
0x140002371  cmp     byte ptr [rcx+29h], 2
0x140002375  jb      short loc_14000238F
0x140002377  mov     rcx, [rcx+18h]
0x14000237b  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002382  mov     edx, 16h
0x140002387  mov     r9d, eax
0x14000238a  call    WPP_SF_d
0x14000238f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002396  cmp     rcx, r12
0x140002399  jz      short loc_1400023C5
0x14000239b  mov     eax, [rcx+2Ch]
0x14000239e  test    r13b, al
0x1400023a1  jz      short loc_1400023C5
0x1400023a3  cmp     byte ptr [rcx+29h], 5
0x1400023a7  jb      short loc_1400023C5
0x1400023a9  mov     rcx, [rcx+18h]
0x1400023ad  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x1400023b4  test    r15b, r15b
0x1400023b7  mov     edx, 17h
0x1400023bc  setnz   r9b
0x1400023c0  call    WPP_SF_c
0x1400023c5  test    r15b, r15b
0x1400023c8  jz      loc_140002742
0x1400023ce  xor     r15b, r15b
0x1400023d1  xor     edx, edx; PriorityBoost
0x1400023d3  mov     rcx, rbp; Irp
0x1400023d6  call    cs:__imp_IofCompleteRequest
0x1400023dd  nop     dword ptr [rax+rax+00h]
0x1400023e2  jmp     loc_140002742
0x1400023e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023ee  cmp     rcx, r12
0x1400023f1  jz      short loc_140002416
0x1400023f3  mov     eax, [rcx+2Ch]
0x1400023f6  test    r13b, al
0x1400023f9  jz      short loc_140002416
0x1400023fb  cmp     byte ptr [rcx+29h], 5
0x1400023ff  jb      short loc_140002416
0x140002401  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x140002408  mov     edx, 11h
0x14000240d  mov     rcx, [rcx+18h]
0x140002411  call    WPP_SF_d
0x140002416  mov     rcx, [rdi+30h]
0x14000241a  call    NatDeleteAnyAssociatedInterface
0x14000241f  mov     rcx, [rdi+30h]
0x140002423  call    NatCleanupAnyAssociatedRedirect
0x140002428  mov     rcx, [rdi+30h]
0x14000242c  call    NatCleanupAnyAssociatedNotification
0x140002431  mov     rcx, [rdi+30h]
0x140002435  call    NatDeleteAnyAssociatedDynamicTicket
0x14000243a  jmp     loc_14000274F
0x14000243f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002446  mov     rsi, [rbp+18h]
0x14000244a  cmp     rcx, r12
0x14000244d  jz      short loc_140002472
0x14000244f  mov     eax, [rcx+2Ch]
0x140002452  test    r13b, al
0x140002455  jz      short loc_140002472
0x140002457  cmp     byte ptr [rcx+29h], 5
0x14000245b  jb      short loc_140002472
0x14000245d  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x140002464  mov     edx, 13h
0x140002469  mov     rcx, [rcx+18h]
0x14000246d  call    WPP_SF_d
0x140002472  movsx   r8d, byte ptr [rbp+40h]
0x140002477  lea     rax, [rsp+78h+arg_10]
0x14000247f  mov     rdx, [rdi+30h]
0x140002483  mov     r9, rsi
0x140002486  mov     [rsp+78h+var_38], rax
0x14000248b  mov     rcx, rbp
0x14000248e  mov     eax, [rdi+18h]
0x140002491  mov     [rsp+78h+var_40], eax
0x140002495  mov     eax, [rdi+8]
0x140002498  mov     [rsp+78h+var_48], eax
0x14000249c  mov     eax, [rdi+10h]
0x14000249f  mov     [rsp+78h+var_50], rsi
0x1400024a4  mov     [rsp+78h+var_58], eax
0x1400024a8  call    NatpExecuteIoDeviceControl
0x1400024ad  mov     esi, eax
0x1400024af  test    eax, eax
0x1400024b1  jz      loc_140002742
0x1400024b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400024be  cmp     rcx, r12
0x1400024c1  jz      loc_140002742
0x1400024c7  mov     eax, [rcx+2Ch]
0x1400024ca  test    r13b, al
0x1400024cd  jz      loc_140002742
0x1400024d3  cmp     byte ptr [rcx+29h], 2
0x1400024d7  jb      loc_140002742
0x1400024dd  mov     rcx, [rcx+18h]
0x1400024e1  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x1400024e8  mov     edx, 14h
0x1400024ed  mov     r9d, esi
0x1400024f0  call    WPP_SF_d
0x1400024f5  jmp     loc_140002742
0x1400024fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002501  cmp     rcx, r12
0x140002504  jz      short loc_140002529
0x140002506  mov     eax, [rcx+2Ch]
0x140002509  test    r13b, al
0x14000250c  jz      short loc_140002529
0x14000250e  cmp     byte ptr [rcx+29h], 5
0x140002512  jb      short loc_140002529
0x140002514  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000251b  mov     edx, 12h
0x140002520  mov     rcx, [rcx+18h]
0x140002524  call    WPP_SF_d
0x140002529  mov     rax, [rdi+30h]
0x14000252d  cmp     [rax+18h], r13
0x140002531  jnz     loc_14000274F
0x140002537  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000253e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002545  nop     dword ptr [rax+rax+00h]
0x14000254a  add     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0FFFFFFFFh
0x140002551  jnz     short loc_14000255A
0x140002553  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, rsi
0x14000255a  mov     dl, al; NewIrql
0x14000255c  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x140002563  call    cs:__imp_KeReleaseSpinLock
0x14000256a  nop     dword ptr [rax+rax+00h]
0x14000256f  jmp     loc_14000274F
0x140002574  mov     rcx, cs:WPP_GLOBAL_Control
0x14000257b  cmp     rcx, r12
0x14000257e  jz      short loc_1400025A3
0x140002580  mov     eax, [rcx+2Ch]
0x140002583  test    r13b, al
0x140002586  jz      short loc_1400025A3
0x140002588  cmp     byte ptr [rcx+29h], 5
0x14000258c  jb      short loc_1400025A3
0x14000258e  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x140002595  mov     edx, 0Bh
0x14000259a  mov     rcx, [rcx+18h]
0x14000259e  call    WPP_SF_d
0x1400025a3  cmp     [rbp+40h], r13b
0x1400025a7  jz      short loc_1400025EB
0x1400025a9  test    [rdi+2], r13b
0x1400025ad  jnz     short loc_1400025EB
0x1400025af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025b6  cmp     rcx, r12
0x1400025b9  jz      short loc_1400025DE
0x1400025bb  mov     eax, [rcx+2Ch]
0x1400025be  test    r13b, al
0x1400025c1  jz      short loc_1400025DE
0x1400025c3  cmp     byte ptr [rcx+29h], 5
0x1400025c7  jb      short loc_1400025DE
0x1400025c9  mov     rcx, [rcx+18h]
0x1400025cd  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x1400025d4  mov     edx, 10h
0x1400025d9  call    WPP_SF_
0x1400025de  mov     rax, [rdi+30h]
0x1400025e2  mov     [rax+18h], rsi
0x1400025e6  jmp     loc_14000274F
0x1400025eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025f2  cmp     rcx, r12
0x1400025f5  jz      short loc_140002621
0x1400025f7  mov     eax, [rcx+2Ch]
0x1400025fa  test    r13b, al
0x1400025fd  jz      short loc_140002621
0x1400025ff  cmp     byte ptr [rcx+29h], 5
0x140002603  jb      short loc_140002621
0x140002605  mov     r9d, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14000260c  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002613  mov     rcx, [rcx+18h]
0x140002617  mov     edx, 0Ch
0x14000261c  call    WPP_SF_d
0x140002621  call    cs:__imp_PsGetCurrentProcessId
0x140002628  nop     dword ptr [rax+rax+00h]
0x14000262d  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x140002634  mov     r14, rax
0x140002637  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000263e  nop     dword ptr [rax+rax+00h]
0x140002643  cmp     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, esi
0x140002649  mov     r12b, al
0x14000264c  jnz     short loc_14000269A
0x14000264e  cmp     [rbp+40h], r13b
0x140002652  jnz     short loc_14000269A
0x140002654  mov     rcx, cs:WPP_GLOBAL_Control
0x14000265b  lea     rax, WPP_GLOBAL_Control
0x140002662  cmp     rcx, rax
0x140002665  jz      short loc_14000268A
0x140002667  mov     edx, [rcx+2Ch]
0x14000266a  test    r13b, dl
0x14000266d  jz      short loc_14000268A
0x14000266f  cmp     byte ptr [rcx+29h], 5
0x140002673  jb      short loc_14000268A
0x140002675  mov     rcx, [rcx+18h]
0x140002679  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002680  mov     edx, 0Dh
0x140002685  call    WPP_SF_
0x14000268a  mov     cs:WPP_MAIN_CB.DeviceQueue.Lock, r14
0x140002691  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, r13d
0x140002698  jmp     short loc_1400026E0
0x14000269a  cmp     r14, cs:WPP_MAIN_CB.DeviceQueue.Lock
0x1400026a1  jnz     short loc_1400026EA
0x1400026a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026aa  lea     rax, WPP_GLOBAL_Control
0x1400026b1  cmp     rcx, rax
0x1400026b4  jz      short loc_1400026D9
0x1400026b6  mov     eax, [rcx+2Ch]
0x1400026b9  test    r13b, al
0x1400026bc  jz      short loc_1400026D9
0x1400026be  cmp     byte ptr [rcx+29h], 5
0x1400026c2  jb      short loc_1400026D9
0x1400026c4  mov     rcx, [rcx+18h]
0x1400026c8  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x1400026cf  mov     edx, 0Eh
0x1400026d4  call    WPP_SF_
0x1400026d9  add     dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, r13d
0x1400026e0  mov     rax, [rdi+30h]
0x1400026e4  mov     [rax+18h], r13
0x1400026e8  jmp     short loc_140002725
0x1400026ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026f1  lea     rax, WPP_GLOBAL_Control
0x1400026f8  cmp     rcx, rax
0x1400026fb  jz      short loc_140002720
0x1400026fd  mov     eax, [rcx+2Ch]
0x140002700  test    r13b, al
0x140002703  jz      short loc_140002720
0x140002705  cmp     byte ptr [rcx+29h], 5
0x140002709  jb      short loc_140002720
0x14000270b  mov     rcx, [rcx+18h]
0x14000270f  lea     r8, WPP_bf6394432411365576a648e5337212b4_Traceguids
0x140002716  mov     edx, 0Fh
0x14000271b  call    WPP_SF_
0x140002720  mov     esi, 0C0000022h
0x140002725  mov     dl, r12b; NewIrql
0x140002728  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink; SpinLock
0x14000272f  call    cs:__imp_KeReleaseSpinLock
0x140002736  nop     dword ptr [rax+rax+00h]
0x14000273b  lea     r12, WPP_GLOBAL_Control
0x140002742  cmp     esi, 103h
  ... truncated ...
```
