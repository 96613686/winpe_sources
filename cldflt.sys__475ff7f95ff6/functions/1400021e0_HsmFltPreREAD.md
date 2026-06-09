# HsmFltPreREAD

- ea: `0x1400021e0`
- end: `0x140002ae4`
- name: `HsmFltPreREAD`
- size: `2308`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140001a00`
- `0x140001a88`
- `0x140001b00`
- `0x140001ba0`
- `0x1400021e0`
- `0x140002aec`
- `0x140003c50`
- `0x1400044f0`
- `0x140007ddc`
- `0x14000c9f4`
- `0x14000cd0c`
- `0x140011cc0`
- `0x14001b350`
- `0x14001b3f0`
- `0x14004ba24`
- `0x14004c6b0`
- `0x14004c6d0`
- `0x140055370`
- `0x140058ddc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140002359`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002492`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024ba`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024d0`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024e5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002865`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002359`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002492`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024ba`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024d0`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400024e5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002865`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000236a`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000236a`
- `ntoskrnl!FsRtlIsPagingFile` at `0x140002207`
- `ntoskrnl!FsRtlIsPagingFile` at `0x140002207`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002311`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140002311`
- `FLTMGR!FltCheckLockForReadAccess` at `0x1400023e3`
- `FLTMGR!FltCheckLockForReadAccess` at `0x1400023e3`
- `FLTMGR!FltIsOperationSynchronous` at `0x140002a79`
- `FLTMGR!FltIsOperationSynchronous` at `0x140002a79`
- `FLTMGR!FltReferenceContext` at `0x140002328`
- `FLTMGR!FltReferenceContext` at `0x140002328`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140002667`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140002667`
- `FLTMGR!FltGetRequestorProcess` at `0x1400022bb`
- `FLTMGR!FltGetRequestorProcess` at `0x1400027a5`
- `FLTMGR!FltGetRequestorProcess` at `0x1400022bb`
- `FLTMGR!FltGetRequestorProcess` at `0x1400027a5`
- `FLTMGR!FltReleaseContext` at `0x14000251f`
- `FLTMGR!FltReleaseContext` at `0x140002636`
- `FLTMGR!FltReleaseContext` at `0x14000251f`
- `FLTMGR!FltReleaseContext` at `0x140002636`

## string_xrefs

- `0x14000295d`: `Recursive Read during compression when file not FullyValidated`

## pseudocode

```c
__int64 __fastcall HsmFltPreREAD(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 *a3)
{
  struct _FILE_OBJECT *v4; // rbp
  struct _FLT_INSTANCE *v6; // rdi
  ULONG Length; // ebx
  char v8; // r12
  __int64 v9; // rbx
  int v10; // r8d
  void *v11; // rsi
  __int64 v12; // rcx
  PEPROCESS RequestorProcess; // rax
  unsigned int v14; // edi
  struct _EX_RUNDOWN_REF *v15; // rcx
  unsigned int i; // eax
  int v17; // ecx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  FILE_LOCK *FileLock; // rax
  char v24; // al
  NTSTATUS v25; // r14d
  __int64 v26; // r10
  int v27; // r12d
  __int64 StreamContext; // rax
  int v30; // r8d
  unsigned int v31; // eax
  NTSTATUS Status; // ecx
  ULONG_PTR Information; // r8
  int v34; // r14d
  PEPROCESS v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  char StreamSize; // al
  __int64 v39; // r10
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _DEVICE_OBJECT *AttachedDevice; // r12
  PFILE_OBJECT TargetFileObject; // rsi
  ULONG v43; // ebp
  char v44; // r15
  LARGE_INTEGER ByteOffset; // r14
  char v46; // di
  BOOLEAN IsOperationSynchronous; // al
  __int64 v48; // [rsp+60h] [rbp-68h]
  __int64 v49; // [rsp+68h] [rbp-60h]
  struct _EX_RUNDOWN_REF *v50; // [rsp+70h] [rbp-58h]
  ULONG_PTR Count; // [rsp+78h] [rbp-50h]
  __int64 StreamHandleContext; // [rsp+80h] [rbp-48h]
  union _LARGE_INTEGER Timeout; // [rsp+88h] [rbp-40h] BYREF
  unsigned int v54; // [rsp+D0h] [rbp+8h]
  int v55; // [rsp+D0h] [rbp+8h]
  NTSTATUS v56; // [rsp+D8h] [rbp+10h]
  int v57; // [rsp+E8h] [rbp+20h]

  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Length = CallbackData->Iopb->Parameters.Read.Length;
  if ( FsRtlIsPagingFile(v4) )
    return 1;
  v8 = 0;
  if ( (CallbackData->Iopb->IrpFlags & 2) != 0 && IoGetTopLevelIrp() )
  {
    v11 = 0;
    StreamHandleContext = 0;
    LOBYTE(v48) = 0;
    if ( IoGetTopLevelIrp() == (PIRP)2 || IoGetTopLevelIrp() == (PIRP)1 || (v9 = 0, IoGetTopLevelIrp() == (PIRP)7) )
    {
      StreamContext = HsmpGetStreamContext(CallbackData, v6, v4);
      v9 = StreamContext;
      if ( StreamContext )
      {
        LOBYTE(v30) = 1;
        HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, v30, 0, StreamContext);
        if ( (*(_DWORD *)(v9 + 28) & 0x100) == 0 )
        {
          v55 = -1073688822;
          HsmDbgBreakOnStatus(-1073688822);
          v14 = 4;
          v25 = -1073688822;
          v57 = 4;
          goto LABEL_90;
        }
      }
    }
    v14 = 1;
    LOBYTE(v55) = 0;
    v57 = 1;
    v27 = 0;
    goto LABEL_32;
  }
  if ( !Length )
    return 1;
  v9 = HsmpGetStreamContext(CallbackData, v6, v4);
  if ( !v9 )
    return 1;
  StreamHandleContext = HsmpGetStreamHandleContext(CallbackData, v6, v4);
  LOBYTE(v10) = 1;
  v11 = (void *)StreamHandleContext;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, v10, StreamHandleContext, v9);
  v12 = *(_QWORD *)(v9 + 16);
  v48 = *(_QWORD *)(v12 + 32);
  v49 = *(_QWORD *)(v12 + 16);
  if ( (*(_DWORD *)(v9 + 28) & 0x20000) != 0
    && *(struct _KTHREAD **)(v9 + 152) == KeGetCurrentThread()
    && IoGetTopLevelIrp() )
  {
    v37 = *(unsigned int *)(v9 + 28);
    if ( (v37 & 0x100) != 0 )
    {
      v55 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qqiqqLq(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          v37,
          v6,
          v4,
          v48,
          CallbackData,
          v9,
          v37,
          *(_QWORD *)(v9 + 152));
      }
    }
    else
    {
      v55 = -1073741595;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiqqLqd(
          WPP_GLOBAL_Control->AttachedDevice,
          v36,
          v37,
          v6,
          v4,
          v48,
          CallbackData,
          v9,
          v37,
          *(_QWORD *)(v9 + 152));
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Recursive Read during compression when file not FullyValidated");
    }
    v25 = v55;
    v14 = 1;
    v57 = 1;
    if ( v55 < 0 )
    {
      v14 = 4;
      v57 = 4;
      goto LABEL_90;
    }
    goto LABEL_91;
  }
  RequestorProcess = FltGetRequestorProcess(CallbackData);
  v14 = 4;
  v57 = 4;
  HsmiOsSetPebCloudFileFlags(RequestorProcess, 4);
  v15 = *(struct _EX_RUNDOWN_REF **)(v9 + 16);
  v56 = 0;
  v50 = v15;
  Count = v15[4].Count;
  for ( i = 0; ; i = v54 + 1 )
  {
    v54 = i;
    if ( i > 5 )
    {
      v55 = -1073688801;
      v34 = -1073688801;
      HsmDbgBreakOnStatus(-1073688801);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqiDd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
          CallbackData,
          Count,
          v9,
          *(_DWORD *)(v9 + 28),
          -1073688801);
      }
      HsmDbgBreakOnStatus(-1073688801);
      goto LABEL_84;
    }
    if ( ExAcquireRundownProtection(v15 + 7) )
    {
      FltReferenceContext((PFLT_CONTEXT)v9);
      goto LABEL_10;
    }
    Timeout.QuadPart = -600000000;
    v56 = FltCancellableWaitForSingleObject(&v50[8], &Timeout, CallbackData);
    HsmDbgBreakOnStatus(v56);
    v17 = v56;
    if ( v56 == 258 )
      break;
    if ( v56 < 0 )
      goto LABEL_56;
    v15 = v50;
  }
  v56 = -1073688801;
  HsmDbgBreakOnStatus(-1073688801);
  v17 = -1073688801;
LABEL_56:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqiDd(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids,
      CallbackData,
      Count,
      v9,
      *(_DWORD *)(v9 + 28),
      v17);
LABEL_10:
    v17 = v56;
  }
  v55 = v17;
  HsmDbgBreakOnStatus(v17);
  if ( v56 < 0 )
  {
    v34 = v56;
LABEL_84:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v9);
      WPP_SF_qqLiqiqd(
        *(_QWORD *)(v39 + 24),
        13,
        (unsigned int)WPP_2f77a96d61d535b9e067d50c2392dcbb_Traceguids,
        v49,
        v9,
        *(_DWORD *)(v9 + 28),
        StreamSize,
        (char)v4,
        v48,
        CallbackData,
        v34);
    }
LABEL_88:
    v25 = v55;
    goto LABEL_90;
  }
  v8 = 1;
  if ( !IoGetTopLevelIrp()
    && !KeAreAllApcsDisabled()
    && !*(_BYTE *)(v49 + 24)
    && *((_QWORD *)&_Config + 1)
    && !*(_DWORD *)(v9 + 36) )
  {
    if ( StreamHandleContext )
    {
      if ( (*(_DWORD *)(StreamHandleContext + 40) & 8) == 0 )
        goto LABEL_19;
    }
    else
    {
      v35 = FltGetRequestorProcess(CallbackData);
      if ( (unsigned int)HsmiOsGetProcessSessionIdFromEprocess(v35) )
LABEL_19:
        HsmpUpdateLastAccessTime(CallbackData);
    }
  }
  if ( (CallbackData->Iopb->IrpFlags & 2) != 0
    || !HsmpGetFileLock(v9, v18, v19)
    || (FileLock = (FILE_LOCK *)HsmpGetFileLock(v21, v20, v22), FltCheckLockForReadAccess(FileLock, CallbackData)) )
  {
    v31 = HsmpRecallInitiateHydrationEx(
            StreamHandleContext,
            v9,
            (int)CallbackData->Iopb->TargetFileObject,
            1,
            CallbackData,
            CallbackData->Iopb->Parameters.Read.ByteOffset.QuadPart,
            CallbackData->Iopb->Parameters.Read.Length,
            0,
            0);
    v57 = v31;
    v14 = v31;
    if ( !v31 )
    {
      *a3 = v9;
      goto LABEL_41;
    }
    if ( v31 != 2 )
      goto LABEL_91;
    goto LABEL_66;
  }
  v55 = -1073741740;
  HsmDbgBreakOnStatus(-1073741740);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v24 = HsmpGetStreamSize(v9);
      v25 = -1073741740;
      WPP_SF_qqLiqiqd(
        *(_QWORD *)(v26 + 24),
        14,
        (unsigned int)WPP_2f77a96d61d535b9e067d50c2392dcbb_Traceguids,
        v49,
        v9,
        *(_DWORD *)(v9 + 28),
        v24,
        (char)v4,
        v48,
        CallbackData,
        -1073741740);
      goto LABEL_90;
    }
    goto LABEL_88;
  }
  v25 = -1073741740;
LABEL_90:
  CallbackData->IoStatus.Status = v25;
  CallbackData->IoStatus.Information = 0;
LABEL_91:
  if ( v8 )
    HsmpReleaseUserRequestRundownProtection((PFLT_CONTEXT)v9);
  v27 = v55;
LABEL_32:
  if ( v9 )
  {
    if ( v27 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      Iopb = CallbackData->Iopb;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      TargetFileObject = Iopb->TargetFileObject;
      v43 = Iopb->Parameters.Read.Length;
      v44 = (Iopb->IrpFlags & 1) == 0;
      ByteOffset = Iopb->Parameters.Read.ByteOffset;
      v46 = (Iopb->IrpFlags & 2) != 0;
      IsOperationSynchronous = FltIsOperationSynchronous(CallbackData);
      WPP_SF_qiDcccqid(
        (_DWORD)AttachedDevice,
        15,
        (unsigned int)WPP_2f77a96d61d535b9e067d50c2392dcbb_Traceguids,
        (_DWORD)CallbackData,
        ByteOffset.QuadPart,
        v43,
        IsOperationSynchronous,
        v44,
        v46,
        (char)TargetFileObject,
        v48,
        v55);
      v14 = v57;
      v11 = (void *)StreamHandleContext;
    }
    if ( v14 != 2 )
    {
LABEL_41:
      Status = CallbackData->IoStatus.Status;
      Information = CallbackData->IoStatus.Information;
      goto LABEL_42;
    }
LABEL_66:
    Status = 259;
    Information = 0;
LABEL_42:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qldPq(WPP_GLOBAL_Control->AttachedDevice, 38, Information, CallbackData, v14, Status, Information, 0);
    }
    FltReleaseContext((PFLT_CONTEXT)v9);
  }
  if ( v11 )
    FltReleaseContext(v11);
  return v14;
}

```

## disassembly

```asm
0x1400021e0  push    rbx
0x1400021e2  push    rbp
0x1400021e3  push    rdi
0x1400021e4  push    r13
0x1400021e6  push    r14
0x1400021e8  sub     rsp, 0A0h
0x1400021ef  mov     rax, [rcx+10h]
0x1400021f3  mov     r13, rcx
0x1400021f6  mov     rbp, [rdx+20h]
0x1400021fa  mov     r14, r8
0x1400021fd  mov     rdi, [rdx+18h]
0x140002201  mov     rcx, rbp; FileObject
0x140002204  mov     ebx, [rax+18h]
0x140002207  call    cs:__imp_FsRtlIsPagingFile
0x14000220e  nop     dword ptr [rax+rax+00h]
0x140002213  test    eax, eax
0x140002215  jnz     loc_14000283B
0x14000221b  mov     rax, [r13+10h]
0x14000221f  mov     [rsp+0C8h+arg_10], rsi
0x140002227  mov     [rsp+0C8h+var_30], r12
0x14000222f  xor     r12b, r12b
0x140002232  mov     [rsp+0C8h+var_38], r15
0x14000223a  mov     ecx, [rax]
0x14000223c  test    cl, 2
0x14000223f  jnz     loc_140002492
0x140002245  test    ebx, ebx
0x140002247  jz      loc_140002845
0x14000224d  mov     r8, rbp; FileObject
0x140002250  mov     rdx, rdi; Instance
0x140002253  mov     rcx, r13; CallbackData
0x140002256  call    HsmpGetStreamContext
0x14000225b  mov     rbx, rax
0x14000225e  test    rax, rax
0x140002261  jz      loc_140002845
0x140002267  mov     r8, rbp; FileObject
0x14000226a  mov     rdx, rdi; Instance
0x14000226d  mov     rcx, r13; CallbackData
0x140002270  call    HsmpGetStreamHandleContext
0x140002275  mov     r9, rax
0x140002278  mov     [rsp+0C8h+var_48], rax
0x140002280  mov     r8b, 1
0x140002283  mov     [rsp+0C8h+CallbackData], rbx
0x140002288  xor     edx, edx
0x14000228a  mov     rcx, r13
0x14000228d  mov     rsi, rax
0x140002290  call    HsmpTracePreCallbackEnter
0x140002295  test    dword ptr [rbx+1Ch], 20000h
0x14000229c  mov     rcx, [rbx+10h]
0x1400022a0  mov     rax, [rcx+20h]
0x1400022a4  mov     [rsp+0C8h+var_68], rax
0x1400022a9  mov     rax, [rcx+10h]
0x1400022ad  mov     [rsp+0C8h+var_60], rax
0x1400022b2  jnz     loc_14000284F
0x1400022b8  mov     rcx, r13; CallbackData
0x1400022bb  call    cs:__imp_FltGetRequestorProcess
0x1400022c2  nop     dword ptr [rax+rax+00h]
0x1400022c7  mov     edi, 4
0x1400022cc  mov     rcx, rax
0x1400022cf  mov     edx, edi
0x1400022d1  mov     [rsp+0C8h+arg_18], edi
0x1400022d8  call    HsmiOsSetPebCloudFileFlags
0x1400022dd  mov     rcx, [rbx+10h]
0x1400022e1  xor     r15d, r15d
0x1400022e4  mov     [rsp+0C8h+arg_8], r15d
0x1400022ec  mov     [rsp+0C8h+var_58], rcx
0x1400022f1  mov     rax, [rcx+20h]
0x1400022f5  mov     [rsp+0C8h+var_50], rax
0x1400022fa  mov     eax, r15d
0x1400022fd  mov     [rsp+0C8h+arg_0], eax
0x140002304  cmp     eax, 5
0x140002307  ja      loc_1400026AF
0x14000230d  add     rcx, 38h ; '8'; RunRef
0x140002311  call    cs:__imp_ExAcquireRundownProtection
0x140002318  nop     dword ptr [rax+rax+00h]
0x14000231d  test    al, al
0x14000231f  jz      loc_140002647
0x140002325  mov     rcx, rbx; Context
0x140002328  call    cs:__imp_FltReferenceContext
0x14000232f  nop     dword ptr [rax+rax+00h]
0x140002334  mov     ecx, [rsp+0C8h+arg_8]
0x14000233b  mov     [rsp+0C8h+arg_0], ecx
0x140002342  call    HsmDbgBreakOnStatus
0x140002347  mov     eax, [rsp+0C8h+arg_8]
0x14000234e  test    eax, eax
0x140002350  js      loc_14000297C
0x140002356  mov     r12b, 1
0x140002359  call    cs:__imp_IoGetTopLevelIrp
0x140002360  nop     dword ptr [rax+rax+00h]
0x140002365  test    rax, rax
0x140002368  jnz     short loc_1400023B8
0x14000236a  call    cs:__imp_KeAreAllApcsDisabled
0x140002371  nop     dword ptr [rax+rax+00h]
0x140002376  test    al, al
0x140002378  jnz     short loc_1400023B8
0x14000237a  mov     rax, [rsp+0C8h+var_60]
0x14000237f  movzx   eax, byte ptr [rax+18h]
0x140002383  test    al, al
0x140002385  jnz     short loc_1400023B8
0x140002387  cmp     qword ptr cs:__Config+8, r15
0x14000238e  jz      short loc_1400023B8
0x140002390  mov     eax, [rbx+24h]
0x140002393  test    eax, eax
0x140002395  jnz     short loc_1400023B8
0x140002397  test    rsi, rsi
0x14000239a  jz      loc_1400027A2
0x1400023a0  mov     eax, [rsi+28h]
0x1400023a3  test    al, 8
0x1400023a5  jnz     short loc_1400023B8
0x1400023a7  mov     r9, rbp
0x1400023aa  mov     r8, rsi
0x1400023ad  mov     rdx, rbx
0x1400023b0  mov     rcx, r13; CallbackData
0x1400023b3  call    HsmpUpdateLastAccessTime
0x1400023b8  mov     rax, [r13+10h]
0x1400023bc  mov     ecx, [rax]
0x1400023be  test    cl, 2
0x1400023c1  jnz     loc_1400025B7
0x1400023c7  mov     rcx, rbx
0x1400023ca  call    HsmpGetFileLock
0x1400023cf  test    rax, rax
0x1400023d2  jz      loc_1400025B7
0x1400023d8  call    HsmpGetFileLock
0x1400023dd  mov     rcx, rax; FileLock
0x1400023e0  mov     rdx, r13; CallbackData
0x1400023e3  call    cs:__imp_FltCheckLockForReadAccess
0x1400023ea  nop     dword ptr [rax+rax+00h]
0x1400023ef  test    al, al
0x1400023f1  jnz     loc_1400025B7
0x1400023f7  mov     eax, 0C0000054h
0x1400023fc  mov     ecx, eax
0x1400023fe  mov     [rsp+0C8h+arg_0], eax
0x140002405  call    HsmDbgBreakOnStatus
0x14000240a  mov     r10, cs:WPP_GLOBAL_Control
0x140002411  lea     rax, WPP_GLOBAL_Control
0x140002418  cmp     r10, rax
0x14000241b  jz      loc_1400029F7
0x140002421  mov     eax, [r10+2Ch]
0x140002425  test    r12b, al
0x140002428  jz      loc_1400029ED
0x14000242e  cmp     byte ptr [r10+29h], 2
0x140002433  jb      loc_1400029ED
0x140002439  mov     rcx, rbx
0x14000243c  call    HsmpGetStreamSize
0x140002441  mov     rcx, [rsp+0C8h+var_68]
0x140002446  lea     r8, WPP_2f77a96d61d535b9e067d50c2392dcbb_Traceguids
0x14000244d  mov     r14d, [rsp+0C8h+arg_0]
0x140002455  mov     edx, 0Eh
0x14000245a  mov     r9, [rsp+0C8h+var_60]
0x14000245f  mov     dword ptr [rsp+0C8h+var_78], r14d
0x140002464  mov     [rsp+0C8h+var_80], r13
0x140002469  mov     [rsp+0C8h+var_88], rcx
0x14000246e  mov     rcx, [r10+18h]
0x140002472  mov     qword ptr [rsp+0C8h+var_90], rbp
0x140002477  mov     [rsp+0C8h+var_98], rax
0x14000247c  mov     eax, [rbx+1Ch]
0x14000247f  mov     dword ptr [rsp+0C8h+var_A0], eax
0x140002483  mov     [rsp+0C8h+CallbackData], rbx
0x140002488  call    WPP_SF_qqLiqiqd
0x14000248d  jmp     loc_1400029FD
0x140002492  call    cs:__imp_IoGetTopLevelIrp
0x140002499  nop     dword ptr [rax+rax+00h]
0x14000249e  test    rax, rax
0x1400024a1  jz      loc_140002245
0x1400024a7  xor     r15d, r15d
0x1400024aa  mov     esi, r15d
0x1400024ad  mov     [rsp+0C8h+var_48], r15
0x1400024b5  mov     [rsp+0C8h+var_68], r15
0x1400024ba  call    cs:__imp_IoGetTopLevelIrp
0x1400024c1  nop     dword ptr [rax+rax+00h]
0x1400024c6  cmp     rax, 2
0x1400024ca  jz      loc_140002555
0x1400024d0  call    cs:__imp_IoGetTopLevelIrp
0x1400024d7  nop     dword ptr [rax+rax+00h]
0x1400024dc  cmp     rax, 1
0x1400024e0  jz      short loc_140002555
0x1400024e2  mov     ebx, r15d
0x1400024e5  call    cs:__imp_IoGetTopLevelIrp
0x1400024ec  nop     dword ptr [rax+rax+00h]
0x1400024f1  cmp     rax, 7
0x1400024f5  jz      short loc_140002555
0x1400024f7  mov     edi, 1
0x1400024fc  mov     [rsp+0C8h+arg_0], r15d
0x140002504  mov     [rsp+0C8h+arg_18], edi
0x14000250b  mov     r12d, r15d
0x14000250e  test    rbx, rbx
0x140002511  jnz     loc_14000281C
0x140002517  test    rsi, rsi
0x14000251a  jz      short loc_14000252B
0x14000251c  mov     rcx, rsi; Context
0x14000251f  call    cs:__imp_FltReleaseContext
0x140002526  nop     dword ptr [rax+rax+00h]
0x14000252b  mov     eax, edi
0x14000252d  mov     r12, [rsp+0C8h+var_30]
0x140002535  mov     rsi, [rsp+0C8h+arg_10]
0x14000253d  mov     r15, [rsp+0C8h+var_38]
0x140002545  add     rsp, 0A0h
0x14000254c  pop     r14
0x14000254e  pop     r13
0x140002550  pop     rdi
0x140002551  pop     rbp
0x140002552  pop     rbx
0x140002553  retn
0x140002555  mov     r8, rbp; FileObject
0x140002558  mov     rdx, rdi; Instance
0x14000255b  mov     rcx, r13; CallbackData
0x14000255e  call    HsmpGetStreamContext
0x140002563  mov     rbx, rax
0x140002566  test    rax, rax
0x140002569  jz      short loc_1400024F7
0x14000256b  xor     r9d, r9d
0x14000256e  mov     [rsp+0C8h+CallbackData], rax
0x140002573  mov     r8b, 1
0x140002576  xor     edx, edx
0x140002578  mov     rcx, r13
0x14000257b  call    HsmpTracePreCallbackEnter
0x140002580  test    dword ptr [rbx+1Ch], 100h
0x140002587  jnz     loc_1400024F7
0x14000258d  mov     eax, 0C000CF0Ah
0x140002592  mov     ecx, eax
0x140002594  mov     [rsp+0C8h+arg_0], eax
0x14000259b  call    HsmDbgBreakOnStatus
0x1400025a0  mov     edi, 4
0x1400025a5  mov     r14d, 0C000CF0Ah
0x1400025ab  mov     [rsp+0C8h+arg_18], edi
0x1400025b2  jmp     loc_1400029FD
0x1400025b7  mov     r8, [r13+10h]
0x1400025bb  mov     r9d, 1; int
0x1400025c1  mov     [rsp+0C8h+var_88], r15; __int64
0x1400025c6  mov     rdx, rbx; int
0x1400025c9  mov     qword ptr [rsp+0C8h+var_90], r15; int
0x1400025ce  mov     rcx, rsi; int
0x1400025d1  mov     eax, [r8+18h]
0x1400025d5  mov     [rsp+0C8h+var_98], rax; __int64
0x1400025da  mov     rax, [r8+28h]
0x1400025de  mov     r8, [r8+8]; int
0x1400025e2  mov     [rsp+0C8h+var_A0], rax; __int64
0x1400025e7  mov     [rsp+0C8h+CallbackData], r13; CallbackData
0x1400025ec  call    HsmpRecallInitiateHydrationEx
0x1400025f1  mov     [rsp+0C8h+arg_18], eax
0x1400025f8  mov     edi, eax
0x1400025fa  test    eax, eax
0x1400025fc  jnz     loc_14000296E
0x140002602  mov     [r14], rbx
0x140002605  mov     ecx, [r13+18h]
0x140002609  mov     r8, [r13+20h]
0x14000260d  mov     r10, cs:WPP_GLOBAL_Control
0x140002614  lea     rax, WPP_GLOBAL_Control
0x14000261b  cmp     r10, rax
0x14000261e  jz      short loc_140002633
0x140002620  mov     eax, [r10+2Ch]
0x140002624  test    al, 4
0x140002626  jz      short loc_140002633
0x140002628  cmp     byte ptr [r10+29h], 4
0x14000262d  jnb     loc_1400027C6
0x140002633  mov     rcx, rbx; Context
0x140002636  call    cs:__imp_FltReleaseContext
0x14000263d  nop     dword ptr [rax+rax+00h]
0x140002642  jmp     loc_140002517
0x140002647  mov     rcx, [rsp+0C8h+var_58]
0x14000264c  lea     rdx, [rsp+0C8h+Timeout]; Timeout
0x140002654  add     rcx, 40h ; '@'; Object
0x140002658  mov     qword ptr [rsp+0C8h+Timeout], 0FFFFFFFFDC3CBA00h
0x140002664  mov     r8, r13; CallbackData
0x140002667  call    cs:__imp_FltCancellableWaitForSingleObject
0x14000266e  nop     dword ptr [rax+rax+00h]
0x140002673  mov     ecx, eax
0x140002675  mov     [rsp+0C8h+arg_8], eax
0x14000267c  call    HsmDbgBreakOnStatus
0x140002681  mov     ecx, [rsp+0C8h+arg_8]
0x140002688  cmp     ecx, 102h
0x14000268e  jz      loc_140002725
0x140002694  test    ecx, ecx
0x140002696  js      loc_14000273D
0x14000269c  mov     eax, [rsp+0C8h+arg_0]
0x1400026a3  mov     rcx, [rsp+0C8h+var_58]
0x1400026a8  inc     eax
0x1400026aa  jmp     loc_1400022FD
0x1400026af  mov     eax, 0C000CF1Fh
0x1400026b4  mov     ecx, eax
0x1400026b6  mov     [rsp+0C8h+arg_0], eax
0x1400026bd  mov     r14d, eax
0x1400026c0  call    HsmDbgBreakOnStatus
0x1400026c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026cc  lea     rax, WPP_GLOBAL_Control
0x1400026d3  cmp     rcx, rax
0x1400026d6  jz      short loc_140002718
0x1400026d8  mov     eax, [rcx+2Ch]
0x1400026db  test    al, 1
0x1400026dd  jz      short loc_140002718
0x1400026df  cmp     byte ptr [rcx+29h], 2
0x1400026e3  jb      short loc_140002718
0x1400026e5  mov     eax, [rbx+1Ch]
0x1400026e8  lea     r8, WPP_8f31b92a248035cb366e8e2533e4f911_Traceguids
0x1400026ef  mov     rcx, [rcx+18h]
0x1400026f3  mov     edx, 0Ah
0x1400026f8  mov     [rsp+0C8h+var_90], r14d
0x1400026fd  mov     r9, r13
0x140002700  mov     dword ptr [rsp+0C8h+var_98], eax
0x140002704  mov     rax, [rsp+0C8h+var_50]
0x140002709  mov     [rsp+0C8h+var_A0], rbx
  ... truncated ...
```
