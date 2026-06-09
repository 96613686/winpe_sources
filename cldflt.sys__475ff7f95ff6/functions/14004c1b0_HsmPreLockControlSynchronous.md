# HsmPreLockControlSynchronous

- ea: `0x14004c1b0`
- end: `0x14004c6a8`
- name: `HsmPreLockControlSynchronous`
- size: `1272`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14004bce0`

## callees

- `0x140001910`
- `0x140001b00`
- `0x140003c50`
- `0x1400044f0`
- `0x14000abb8`
- `0x14001af00`
- `0x14004c1b0`
- `0x14004c6b0`
- `0x14004c6d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14004c5b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004c5b5`
- `ntoskrnl!KeInitializeEvent` at `0x14004c27a`
- `ntoskrnl!KeInitializeEvent` at `0x14004c27a`
- `FLTMGR!FltAllocateFileLock` at `0x14004c49e`
- `FLTMGR!FltAllocateFileLock` at `0x14004c49e`
- `FLTMGR!FltProcessFileLock` at `0x14004c2a9`
- `FLTMGR!FltProcessFileLock` at `0x14004c2a9`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004c4f8`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004c4f8`
- `FLTMGR!FltFreeFileLock` at `0x14004c550`
- `FLTMGR!FltFreeFileLock` at `0x14004c550`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004c56b`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004c56b`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14004c484`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14004c484`
- `FLTMGR!FltCancelIo` at `0x14004c593`
- `FLTMGR!FltCancelIo` at `0x14004c593`
- `FLTMGR!FltReleaseContext` at `0x14004c403`
- `FLTMGR!FltReleaseContext` at `0x14004c403`

## pseudocode

```c
void __fastcall HsmPreLockControlSynchronous(
        PFLT_DEFERRED_IO_WORKITEM FltWorkItem,
        PFLT_CALLBACK_DATA CallbackData,
        _QWORD *Context)
{
  void *v3; // r14
  __int64 StreamHandleContext; // rax
  _QWORD *v6; // r12
  int v7; // edx
  __int64 v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  NTSTATUS Status; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  FILE_LOCK *v15; // rax
  FLT_PREOP_CALLBACK_STATUS v16; // eax
  int v17; // r15d
  FLT_PREOP_CALLBACK_STATUS v18; // esi
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  int v20; // r9d
  FILE_LOCK *FileLock; // rax
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  struct _KEVENT Event; // [rsp+50h] [rbp-58h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+20h]

  v3 = 0;
  memset(&Event, 0, sizeof(Event));
  if ( FltWorkItem )
    FltFreeDeferredIoWorkItem(FltWorkItem);
  StreamHandleContext = HsmpGetStreamHandleContext(
                          CallbackData,
                          CallbackData->Iopb->TargetInstance,
                          CallbackData->Iopb->TargetFileObject);
  v6 = (_QWORD *)StreamHandleContext;
  if ( !StreamHandleContext || (v7 = *(_DWORD *)(*(_QWORD *)(StreamHandleContext + 16) + 28LL), (v7 & 2) != 0) )
  {
    v18 = FLT_PREOP_SUCCESS_NO_CALLBACK;
LABEL_24:
    if ( !v6 )
      goto LABEL_25;
    goto LABEL_32;
  }
  LOBYTE(v7) = 1;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, v7, 0, 0, 0);
  v8 = v6[2];
  v9 = *(_QWORD *)(v8 + 16);
  v27 = v9;
  if ( !HsmpGetFileLock(v8, v10, v11) )
  {
    FileLock = FltAllocateFileLock((PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE)HsmiCompleteLockCallbackDataRoutine, 0);
    if ( !FileLock )
    {
      Status = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_12;
      }
      v23 = 10;
      goto LABEL_43;
    }
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)(*(_QWORD *)(v8 + 160) + 32LL),
           (signed __int64)FileLock,
           0) )
    {
      FltFreeFileLock(FileLock);
    }
  }
  Status = 0;
  if ( CallbackData->Iopb->MinorFunction != 1 )
    goto LABEL_19;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    Iopb = CallbackData->Iopb;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqiqiiD)(
      WPP_GLOBAL_Control->AttachedDevice,
      Iopb->Parameters.WMI.ProviderId,
      Iopb,
      CallbackData,
      v8,
      *(_QWORD *)(v9 + 32),
      Iopb->TargetFileObject,
      (LARGE_INTEGER)Iopb->Parameters.Read.ByteOffset.QuadPart,
      Iopb->Parameters.Create.SecurityContext->SecurityQos,
      Iopb->Parameters.Create.Options,
      *(_QWORD *)&Event.Header.Lock,
      Event.Header.WaitListHead.Flink,
      Event.Header.WaitListHead.Blink);
  }
  v15 = (FILE_LOCK *)HsmpGetFileLock(v8, v13, v14);
  v16 = FltProcessFileLock(v15, CallbackData, &Event);
  v17 = v16;
  if ( v16 == FLT_PREOP_PENDING )
  {
    Status = FltCancellableWaitForSingleObject(&Event, 0, CallbackData);
    HsmDbgBreakOnStatus(Status);
    if ( Status == -1073741749 || Status == -1073741536 )
    {
      FltCancelIo(CallbackData);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    if ( Status >= 0 )
    {
      v17 = 4;
LABEL_10:
      Status = CallbackData->IoStatus.Status;
      HsmDbgBreakOnStatus(Status);
      if ( Status < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqiDd(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
            CallbackData,
            v8,
            *(_QWORD *)(v9 + 32),
            v17,
            Status);
        }
        goto LABEL_12;
      }
      goto LABEL_15;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
LABEL_12:
      v3 = 0;
      CallbackData->IoStatus.Status = Status;
      v18 = FLT_PREOP_COMPLETE;
      CallbackData->IoStatus.Information = 0;
      goto LABEL_24;
    }
    v23 = 12;
LABEL_43:
    WPP_SF_qqqd(
      v22->AttachedDevice,
      v23,
      WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
      CallbackData,
      v8,
      *(_QWORD *)(v9 + 32),
      Status);
    goto LABEL_12;
  }
  if ( v16 == FLT_PREOP_COMPLETE )
    goto LABEL_10;
  v18 = FLT_PREOP_DISALLOW_FASTIO;
  if ( v16 != FLT_PREOP_DISALLOW_FASTIO )
  {
    v9 = v27;
LABEL_15:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_23:
      v18 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
      v3 = v6;
      v6 = 0;
      goto LABEL_24;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
        CallbackData,
        v8,
        *(_QWORD *)(v9 + 32),
        Status);
LABEL_19:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
        CallbackData,
        v8,
        *(_QWORD *)(v9 + 32),
        Status);
    }
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqiDd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
      CallbackData,
      v8,
      *(_QWORD *)(v27 + 32),
      3,
      0);
  }
  v3 = 0;
LABEL_32:
  FltReleaseContext(v6);
  LOBYTE(v20) = 1;
  HsmpTracePreCallbackExit(v18, (_DWORD)CallbackData, (_DWORD)v3, v20, 0);
LABEL_25:
  if ( FltWorkItem )
    FltCompletePendedPreOperation(CallbackData, v18, v3);
  else
    *Context = v3;
}

```

## disassembly

```asm
0x14004c1b0  mov     [rsp+arg_10], r8
0x14004c1b5  mov     [rsp+arg_0], rcx
0x14004c1ba  push    rbx
0x14004c1bb  push    rsi
0x14004c1bc  push    rdi
0x14004c1bd  push    r12
0x14004c1bf  push    r13
0x14004c1c1  push    r14
0x14004c1c3  push    r15
0x14004c1c5  sub     rsp, 70h
0x14004c1c9  mov     rax, rcx
0x14004c1cc  xor     r14d, r14d
0x14004c1cf  xor     ecx, ecx
0x14004c1d1  mov     [rsp+0A8h+Context], r14
0x14004c1d9  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rcx
0x14004c1de  xorps   xmm0, xmm0
0x14004c1e1  mov     rdi, rdx
0x14004c1e4  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14004c1e9  test    rax, rax
0x14004c1ec  jnz     loc_14004C4F5
0x14004c1f2  mov     rdx, [rdi+10h]
0x14004c1f6  mov     rcx, rdi; CallbackData
0x14004c1f9  mov     r8, [rdx+8]; FileObject
0x14004c1fd  mov     rdx, [rdx+10h]; Instance
0x14004c201  call    HsmpGetStreamHandleContext
0x14004c206  mov     r12, rax
0x14004c209  test    rax, rax
0x14004c20c  jz      loc_14004C472
0x14004c212  mov     rcx, [rax+10h]
0x14004c216  mov     edx, [rcx+1Ch]
0x14004c219  test    dl, 2
0x14004c21c  jnz     loc_14004C472
0x14004c222  xor     r9d, r9d
0x14004c225  mov     [rsp+0A8h+Timeout], r14
0x14004c22a  xor     r8d, r8d
0x14004c22d  mov     dl, 1
0x14004c22f  mov     rcx, rdi
0x14004c232  call    HsmpTracePreCallbackEnter
0x14004c237  mov     r13, [r12+10h]
0x14004c23c  mov     rcx, r13
0x14004c23f  mov     rsi, [r13+10h]
0x14004c243  mov     [rsp+0A8h+arg_18], rsi
0x14004c24b  call    HsmpGetFileLock
0x14004c250  test    rax, rax
0x14004c253  jz      loc_14004C495
0x14004c259  mov     rax, [rdi+10h]
0x14004c25d  lea     r14, WPP_GLOBAL_Control
0x14004c264  xor     ebx, ebx
0x14004c266  cmp     byte ptr [rax+5], 1
0x14004c26a  jnz     loc_14004C330
0x14004c270  xor     r8d, r8d; State
0x14004c273  lea     rcx, [rsp+0A8h+Event]; Event
0x14004c278  xor     edx, edx; Type
0x14004c27a  call    cs:__imp_KeInitializeEvent
0x14004c281  nop     dword ptr [rax+rax+00h]
0x14004c286  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c28d  cmp     rcx, r14
0x14004c290  jnz     loc_14004C38F
0x14004c296  mov     rcx, r13
0x14004c299  call    HsmpGetFileLock
0x14004c29e  mov     rcx, rax; FileLock
0x14004c2a1  lea     r8, [rsp+0A8h+Event]; Context
0x14004c2a6  mov     rdx, rdi; CallbackData
0x14004c2a9  call    cs:__imp_FltProcessFileLock
0x14004c2b0  nop     dword ptr [rax+rax+00h]
0x14004c2b5  mov     r15d, eax
0x14004c2b8  cmp     eax, 2
0x14004c2bb  jz      loc_14004C561
0x14004c2c1  cmp     eax, 4
0x14004c2c4  jnz     short loc_14004C2FE
0x14004c2c6  mov     ebx, [rdi+18h]
0x14004c2c9  mov     ecx, ebx
0x14004c2cb  call    HsmDbgBreakOnStatus
0x14004c2d0  test    ebx, ebx
0x14004c2d2  jns     short loc_14004C313
0x14004c2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c2db  cmp     rcx, r14
0x14004c2de  jnz     loc_14004C429
0x14004c2e4  mov     r14, [rsp+0A8h+Context]
0x14004c2ec  mov     [rdi+18h], ebx
0x14004c2ef  mov     esi, 4
0x14004c2f4  mov     qword ptr [rdi+20h], 0
0x14004c2fc  jmp     short loc_14004C359
0x14004c2fe  mov     esi, 3
0x14004c303  cmp     eax, esi
0x14004c305  jz      loc_14004C3ED
0x14004c30b  mov     rsi, [rsp+0A8h+arg_18]
0x14004c313  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c31a  cmp     rcx, r14
0x14004c31d  jz      short loc_14004C34D
0x14004c31f  mov     eax, [rcx+2Ch]
0x14004c322  test    al, 1
0x14004c324  jz      short loc_14004C330
0x14004c326  cmp     byte ptr [rcx+29h], 4
0x14004c32a  jnb     loc_14004C64A
0x14004c330  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c337  cmp     rcx, r14
0x14004c33a  jz      short loc_14004C34D
0x14004c33c  mov     eax, [rcx+2Ch]
0x14004c33f  test    al, 1
0x14004c341  jz      short loc_14004C34D
0x14004c343  cmp     byte ptr [rcx+29h], 4
0x14004c347  jnb     loc_14004C679
0x14004c34d  xor     esi, esi
0x14004c34f  mov     r14, r12
0x14004c352  xor     r12d, r12d
0x14004c355  test    ebx, ebx
0x14004c357  js      short loc_14004C2EC
0x14004c359  test    r12, r12
0x14004c35c  jnz     loc_14004C400
0x14004c362  cmp     [rsp+0A8h+arg_0], 0
0x14004c36b  jnz     loc_14004C47C
0x14004c371  mov     rax, [rsp+0A8h+arg_10]
0x14004c379  mov     [rax], r14
0x14004c37c  mov     eax, esi
0x14004c37e  add     rsp, 70h
0x14004c382  pop     r15
0x14004c384  pop     r14
0x14004c386  pop     r13
0x14004c388  pop     r12
0x14004c38a  pop     rdi
0x14004c38b  pop     rsi
0x14004c38c  pop     rbx
0x14004c38d  retn
0x14004c38f  mov     eax, [rcx+2Ch]
0x14004c392  test    al, 1
0x14004c394  jz      loc_14004C296
0x14004c39a  cmp     byte ptr [rcx+29h], 4
0x14004c39e  jb      loc_14004C296
0x14004c3a4  mov     r8, [rdi+10h]
0x14004c3a8  mov     r9, rdi
0x14004c3ab  mov     rcx, [rcx+18h]
0x14004c3af  mov     eax, [r8+20h]
0x14004c3b3  mov     rdx, [r8+18h]
0x14004c3b7  mov     [rsp+0A8h+var_60], eax
0x14004c3bb  mov     rax, [rdx]
0x14004c3be  mov     [rsp+0A8h+var_68], rax
0x14004c3c3  mov     rax, [r8+28h]
0x14004c3c7  mov     [rsp+0A8h+var_70], rax
0x14004c3cc  mov     rax, [r8+8]
0x14004c3d0  mov     [rsp+0A8h+var_78], rax
0x14004c3d5  mov     rax, [rsi+20h]
0x14004c3d9  mov     [rsp+0A8h+var_80], rax
0x14004c3de  mov     [rsp+0A8h+Timeout], r13
0x14004c3e3  call    WPP_SF_qqiqiiD
0x14004c3e8  jmp     loc_14004C296
0x14004c3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c3f4  cmp     rcx, r14
0x14004c3f7  jnz     loc_14004C5FA
0x14004c3fd  mov     r14, rbx
0x14004c400  mov     rcx, r12; Context
0x14004c403  call    cs:__imp_FltReleaseContext
0x14004c40a  nop     dword ptr [rax+rax+00h]
0x14004c40f  mov     r9b, 1
0x14004c412  mov     byte ptr [rsp+0A8h+Timeout], 0
0x14004c417  mov     r8, r14
0x14004c41a  mov     rdx, rdi
0x14004c41d  mov     ecx, esi
0x14004c41f  call    HsmpTracePreCallbackExit
0x14004c424  jmp     loc_14004C362
0x14004c429  mov     eax, [rcx+2Ch]
0x14004c42c  test    al, 1
0x14004c42e  jz      loc_14004C2E4
0x14004c434  cmp     byte ptr [rcx+29h], 2
0x14004c438  jb      loc_14004C2E4
0x14004c43e  mov     rax, [rsi+20h]
0x14004c442  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c449  mov     rcx, [rcx+18h]
0x14004c44d  mov     edx, 0Eh
0x14004c452  mov     dword ptr [rsp+0A8h+var_70], ebx
0x14004c456  mov     r9, rdi
0x14004c459  mov     dword ptr [rsp+0A8h+var_78], r15d
0x14004c45e  mov     [rsp+0A8h+var_80], rax
0x14004c463  mov     [rsp+0A8h+Timeout], r13
0x14004c468  call    WPP_SF_qqiDd
0x14004c46d  jmp     loc_14004C2E4
0x14004c472  mov     esi, 1
0x14004c477  jmp     loc_14004C359
0x14004c47c  mov     r8, r14; Context
0x14004c47f  mov     edx, esi; CallbackStatus
0x14004c481  mov     rcx, rdi; CallbackData
0x14004c484  call    cs:__imp_FltCompletePendedPreOperation
0x14004c48b  nop     dword ptr [rax+rax+00h]
0x14004c490  jmp     loc_14004C37C
0x14004c495  xor     edx, edx; UnlockRoutine
0x14004c497  lea     rcx, HsmiCompleteLockCallbackDataRoutine; CompleteLockCallbackDataRoutine
0x14004c49e  call    cs:__imp_FltAllocateFileLock
0x14004c4a5  nop     dword ptr [rax+rax+00h]
0x14004c4aa  mov     rdx, rax
0x14004c4ad  test    rax, rax
0x14004c4b0  jnz     loc_14004C538
0x14004c4b6  mov     ebx, 0C000009Ah
0x14004c4bb  mov     ecx, ebx
0x14004c4bd  call    HsmDbgBreakOnStatus
0x14004c4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c4c9  lea     r14, WPP_GLOBAL_Control
0x14004c4d0  cmp     rcx, r14
0x14004c4d3  jz      loc_14004C2E4
0x14004c4d9  mov     eax, [rcx+2Ch]
0x14004c4dc  test    al, 1
0x14004c4de  jz      loc_14004C2E4
0x14004c4e4  cmp     byte ptr [rcx+29h], 2
0x14004c4e8  jb      loc_14004C2E4
0x14004c4ee  mov     edx, 0Ah
0x14004c4f3  jmp     short loc_14004C50E
0x14004c4f5  mov     rcx, rax; FltWorkItem
0x14004c4f8  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14004c4ff  nop     dword ptr [rax+rax+00h]
0x14004c504  jmp     loc_14004C1F2
0x14004c509  mov     edx, 0Ch
0x14004c50e  mov     rax, [rsi+20h]
0x14004c512  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c519  mov     rcx, [rcx+18h]
0x14004c51d  mov     r9, rdi
0x14004c520  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c524  mov     [rsp+0A8h+var_80], rax
0x14004c529  mov     [rsp+0A8h+Timeout], r13
0x14004c52e  call    WPP_SF_qqqd
0x14004c533  jmp     loc_14004C2E4
0x14004c538  mov     rcx, [r13+0A0h]
0x14004c53f  xor     eax, eax
0x14004c541  lock cmpxchg [rcx+20h], rdx
0x14004c547  jz      loc_14004C259
0x14004c54d  mov     rcx, rdx; FileLock
0x14004c550  call    cs:__imp_FltFreeFileLock
0x14004c557  nop     dword ptr [rax+rax+00h]
0x14004c55c  jmp     loc_14004C259
0x14004c561  mov     r8, rdi; CallbackData
0x14004c564  lea     rcx, [rsp+0A8h+Event]; Object
0x14004c569  xor     edx, edx; Timeout
0x14004c56b  call    cs:__imp_FltCancellableWaitForSingleObject
0x14004c572  nop     dword ptr [rax+rax+00h]
0x14004c577  mov     ecx, eax
0x14004c579  mov     ebx, eax
0x14004c57b  call    HsmDbgBreakOnStatus
0x14004c580  cmp     ebx, 0C000004Bh
0x14004c586  jz      short loc_14004C590
0x14004c588  cmp     ebx, 0C0000120h
0x14004c58e  jnz     short loc_14004C5C1
0x14004c590  mov     rcx, rdi; CallbackData
0x14004c593  call    cs:__imp_FltCancelIo
0x14004c59a  nop     dword ptr [rax+rax+00h]
0x14004c59f  xor     r9d, r9d; Alertable
0x14004c5a2  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14004c5ab  xor     r8d, r8d; WaitMode
0x14004c5ae  lea     rcx, [rsp+0A8h+Event]; Object
0x14004c5b3  xor     edx, edx; WaitReason
0x14004c5b5  call    cs:__imp_KeWaitForSingleObject
0x14004c5bc  nop     dword ptr [rax+rax+00h]
0x14004c5c1  test    ebx, ebx
0x14004c5c3  jns     short loc_14004C5EF
0x14004c5c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c5cc  cmp     rcx, r14
0x14004c5cf  jz      loc_14004C2E4
0x14004c5d5  mov     eax, [rcx+2Ch]
0x14004c5d8  test    al, 1
0x14004c5da  jz      loc_14004C2E4
0x14004c5e0  cmp     byte ptr [rcx+29h], 2
0x14004c5e4  jb      loc_14004C2E4
0x14004c5ea  jmp     loc_14004C509
0x14004c5ef  mov     r15d, 4
0x14004c5f5  jmp     loc_14004C2C6
0x14004c5fa  mov     eax, [rcx+2Ch]
0x14004c5fd  test    al, 1
0x14004c5ff  jz      loc_14004C3FD
0x14004c605  cmp     byte ptr [rcx+29h], 2
0x14004c609  jb      loc_14004C3FD
0x14004c60f  mov     rax, [rsp+0A8h+arg_18]
0x14004c617  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c61e  mov     rcx, [rcx+18h]
0x14004c622  mov     edx, 0Dh
0x14004c627  mov     dword ptr [rsp+0A8h+var_70], ebx
0x14004c62b  mov     r9, rdi
0x14004c62e  mov     dword ptr [rsp+0A8h+var_78], esi
0x14004c632  mov     rax, [rax+20h]
0x14004c636  mov     [rsp+0A8h+var_80], rax
0x14004c63b  mov     [rsp+0A8h+Timeout], r13
0x14004c640  call    WPP_SF_qqiDd
0x14004c645  jmp     loc_14004C3FD
0x14004c64a  mov     rax, [rsi+20h]
0x14004c64e  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c655  mov     rcx, [rcx+18h]
0x14004c659  mov     edx, 0Fh
0x14004c65e  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c662  mov     r9, rdi
0x14004c665  mov     [rsp+0A8h+var_80], rax
0x14004c66a  mov     [rsp+0A8h+Timeout], r13
0x14004c66f  call    WPP_SF_qqqd
0x14004c674  jmp     loc_14004C330
0x14004c679  mov     rax, [rsi+20h]
0x14004c67d  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c684  mov     rcx, [rcx+18h]
0x14004c688  mov     edx, 10h
0x14004c68d  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c691  mov     r9, rdi
0x14004c694  mov     [rsp+0A8h+var_80], rax
0x14004c699  mov     [rsp+0A8h+Timeout], r13
0x14004c69e  call    WPP_SF_qqqd
0x14004c6a3  jmp     loc_14004C34D
```
