# HsmPreLockControlSynchronous

- ea: `0x14004c0c0`
- end: `0x14004c5b8`
- name: `HsmPreLockControlSynchronous`
- size: `1272`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14004bbf0`

## callees

- `0x140001910`
- `0x140001b00`
- `0x140003c50`
- `0x1400044f0`
- `0x14000abb8`
- `0x14001ae80`
- `0x14004c0c0`
- `0x14004c5c0`
- `0x14004c5e0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14004c4c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004c4c5`
- `ntoskrnl!KeInitializeEvent` at `0x14004c18a`
- `ntoskrnl!KeInitializeEvent` at `0x14004c18a`
- `FLTMGR!FltAllocateFileLock` at `0x14004c3ae`
- `FLTMGR!FltAllocateFileLock` at `0x14004c3ae`
- `FLTMGR!FltProcessFileLock` at `0x14004c1b9`
- `FLTMGR!FltProcessFileLock` at `0x14004c1b9`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004c408`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004c408`
- `FLTMGR!FltFreeFileLock` at `0x14004c460`
- `FLTMGR!FltFreeFileLock` at `0x14004c460`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004c47b`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x14004c47b`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14004c394`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14004c394`
- `FLTMGR!FltCancelIo` at `0x14004c4a3`
- `FLTMGR!FltCancelIo` at `0x14004c4a3`
- `FLTMGR!FltReleaseContext` at `0x14004c313`
- `FLTMGR!FltReleaseContext` at `0x14004c313`

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
  int Status; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  FILE_LOCK *v15; // rax
  FLT_PREOP_CALLBACK_STATUS v16; // eax
  FLT_PREOP_CALLBACK_STATUS v17; // esi
  PFLT_IO_PARAMETER_BLOCK Iopb; // r8
  int v19; // r9d
  FILE_LOCK *FileLock; // rax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  struct _KEVENT Event; // [rsp+50h] [rbp-58h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+20h]

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
    v17 = FLT_PREOP_SUCCESS_NO_CALLBACK;
LABEL_24:
    if ( !v6 )
      goto LABEL_25;
    goto LABEL_32;
  }
  LOBYTE(v7) = 1;
  HsmpTracePreCallbackEnter((_DWORD)CallbackData, v7, 0, 0, 0);
  v8 = v6[2];
  v9 = *(_QWORD *)(v8 + 16);
  v26 = v9;
  if ( !HsmpGetFileLock(v8, v10, v11) )
  {
    FileLock = FltAllocateFileLock(HsmiCompleteLockCallbackDataRoutine, 0);
    if ( !FileLock )
    {
      Status = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_12;
      }
      v22 = 10;
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
  if ( v16 == FLT_PREOP_PENDING )
  {
    Status = FltCancellableWaitForSingleObject(&Event, 0, CallbackData);
    HsmDbgBreakOnStatus((unsigned int)Status);
    if ( Status == -1073741749 || Status == -1073741536 )
    {
      FltCancelIo(CallbackData);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    if ( Status >= 0 )
    {
LABEL_10:
      Status = CallbackData->IoStatus.Status;
      HsmDbgBreakOnStatus((unsigned int)Status);
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
            *(_QWORD *)(v9 + 32));
        }
        goto LABEL_12;
      }
      goto LABEL_15;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
LABEL_12:
      v3 = 0;
      CallbackData->IoStatus.Status = Status;
      v17 = FLT_PREOP_COMPLETE;
      CallbackData->IoStatus.Information = 0;
      goto LABEL_24;
    }
    v22 = 12;
LABEL_43:
    WPP_SF_qqqd(
      v21->AttachedDevice,
      v22,
      WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
      CallbackData,
      v8,
      *(_QWORD *)(v9 + 32),
      Status);
    goto LABEL_12;
  }
  if ( v16 == FLT_PREOP_COMPLETE )
    goto LABEL_10;
  v17 = FLT_PREOP_DISALLOW_FASTIO;
  if ( v16 != FLT_PREOP_DISALLOW_FASTIO )
  {
    v9 = v26;
LABEL_15:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_23:
      v17 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
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
      *(_QWORD *)(v26 + 32));
  }
  v3 = 0;
LABEL_32:
  FltReleaseContext(v6);
  LOBYTE(v19) = 1;
  HsmpTracePreCallbackExit(v17, (_DWORD)CallbackData, (_DWORD)v3, v19, 0);
LABEL_25:
  if ( FltWorkItem )
    FltCompletePendedPreOperation(CallbackData, v17, v3);
  else
    *Context = v3;
}

```

## disassembly

```asm
0x14004c0c0  mov     [rsp+arg_10], r8
0x14004c0c5  mov     [rsp+arg_0], rcx
0x14004c0ca  push    rbx
0x14004c0cb  push    rsi
0x14004c0cc  push    rdi
0x14004c0cd  push    r12
0x14004c0cf  push    r13
0x14004c0d1  push    r14
0x14004c0d3  push    r15
0x14004c0d5  sub     rsp, 70h
0x14004c0d9  mov     rax, rcx
0x14004c0dc  xor     r14d, r14d
0x14004c0df  xor     ecx, ecx
0x14004c0e1  mov     [rsp+0A8h+Context], r14
0x14004c0e9  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rcx
0x14004c0ee  xorps   xmm0, xmm0
0x14004c0f1  mov     rdi, rdx
0x14004c0f4  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14004c0f9  test    rax, rax
0x14004c0fc  jnz     loc_14004C405
0x14004c102  mov     rdx, [rdi+10h]
0x14004c106  mov     rcx, rdi; CallbackData
0x14004c109  mov     r8, [rdx+8]; FileObject
0x14004c10d  mov     rdx, [rdx+10h]; Instance
0x14004c111  call    HsmpGetStreamHandleContext
0x14004c116  mov     r12, rax
0x14004c119  test    rax, rax
0x14004c11c  jz      loc_14004C382
0x14004c122  mov     rcx, [rax+10h]
0x14004c126  mov     edx, [rcx+1Ch]
0x14004c129  test    dl, 2
0x14004c12c  jnz     loc_14004C382
0x14004c132  xor     r9d, r9d
0x14004c135  mov     [rsp+0A8h+Timeout], r14
0x14004c13a  xor     r8d, r8d
0x14004c13d  mov     dl, 1
0x14004c13f  mov     rcx, rdi
0x14004c142  call    HsmpTracePreCallbackEnter
0x14004c147  mov     r13, [r12+10h]
0x14004c14c  mov     rcx, r13
0x14004c14f  mov     rsi, [r13+10h]
0x14004c153  mov     [rsp+0A8h+arg_18], rsi
0x14004c15b  call    HsmpGetFileLock
0x14004c160  test    rax, rax
0x14004c163  jz      loc_14004C3A5
0x14004c169  mov     rax, [rdi+10h]
0x14004c16d  lea     r14, WPP_GLOBAL_Control
0x14004c174  xor     ebx, ebx
0x14004c176  cmp     byte ptr [rax+5], 1
0x14004c17a  jnz     loc_14004C240
0x14004c180  xor     r8d, r8d; State
0x14004c183  lea     rcx, [rsp+0A8h+Event]; Event
0x14004c188  xor     edx, edx; Type
0x14004c18a  call    cs:__imp_KeInitializeEvent
0x14004c191  nop     dword ptr [rax+rax+00h]
0x14004c196  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c19d  cmp     rcx, r14
0x14004c1a0  jnz     loc_14004C29F
0x14004c1a6  mov     rcx, r13
0x14004c1a9  call    HsmpGetFileLock
0x14004c1ae  mov     rcx, rax; FileLock
0x14004c1b1  lea     r8, [rsp+0A8h+Event]; Context
0x14004c1b6  mov     rdx, rdi; CallbackData
0x14004c1b9  call    cs:__imp_FltProcessFileLock
0x14004c1c0  nop     dword ptr [rax+rax+00h]
0x14004c1c5  mov     r15d, eax
0x14004c1c8  cmp     eax, 2
0x14004c1cb  jz      loc_14004C471
0x14004c1d1  cmp     eax, 4
0x14004c1d4  jnz     short loc_14004C20E
0x14004c1d6  mov     ebx, [rdi+18h]
0x14004c1d9  mov     ecx, ebx
0x14004c1db  call    HsmDbgBreakOnStatus
0x14004c1e0  test    ebx, ebx
0x14004c1e2  jns     short loc_14004C223
0x14004c1e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c1eb  cmp     rcx, r14
0x14004c1ee  jnz     loc_14004C339
0x14004c1f4  mov     r14, [rsp+0A8h+Context]
0x14004c1fc  mov     [rdi+18h], ebx
0x14004c1ff  mov     esi, 4
0x14004c204  mov     qword ptr [rdi+20h], 0
0x14004c20c  jmp     short loc_14004C269
0x14004c20e  mov     esi, 3
0x14004c213  cmp     eax, esi
0x14004c215  jz      loc_14004C2FD
0x14004c21b  mov     rsi, [rsp+0A8h+arg_18]
0x14004c223  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c22a  cmp     rcx, r14
0x14004c22d  jz      short loc_14004C25D
0x14004c22f  mov     eax, [rcx+2Ch]
0x14004c232  test    al, 1
0x14004c234  jz      short loc_14004C240
0x14004c236  cmp     byte ptr [rcx+29h], 4
0x14004c23a  jnb     loc_14004C55A
0x14004c240  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c247  cmp     rcx, r14
0x14004c24a  jz      short loc_14004C25D
0x14004c24c  mov     eax, [rcx+2Ch]
0x14004c24f  test    al, 1
0x14004c251  jz      short loc_14004C25D
0x14004c253  cmp     byte ptr [rcx+29h], 4
0x14004c257  jnb     loc_14004C589
0x14004c25d  xor     esi, esi
0x14004c25f  mov     r14, r12
0x14004c262  xor     r12d, r12d
0x14004c265  test    ebx, ebx
0x14004c267  js      short loc_14004C1FC
0x14004c269  test    r12, r12
0x14004c26c  jnz     loc_14004C310
0x14004c272  cmp     [rsp+0A8h+arg_0], 0
0x14004c27b  jnz     loc_14004C38C
0x14004c281  mov     rax, [rsp+0A8h+arg_10]
0x14004c289  mov     [rax], r14
0x14004c28c  mov     eax, esi
0x14004c28e  add     rsp, 70h
0x14004c292  pop     r15
0x14004c294  pop     r14
0x14004c296  pop     r13
0x14004c298  pop     r12
0x14004c29a  pop     rdi
0x14004c29b  pop     rsi
0x14004c29c  pop     rbx
0x14004c29d  retn
0x14004c29f  mov     eax, [rcx+2Ch]
0x14004c2a2  test    al, 1
0x14004c2a4  jz      loc_14004C1A6
0x14004c2aa  cmp     byte ptr [rcx+29h], 4
0x14004c2ae  jb      loc_14004C1A6
0x14004c2b4  mov     r8, [rdi+10h]
0x14004c2b8  mov     r9, rdi
0x14004c2bb  mov     rcx, [rcx+18h]
0x14004c2bf  mov     eax, [r8+20h]
0x14004c2c3  mov     rdx, [r8+18h]
0x14004c2c7  mov     [rsp+0A8h+var_60], eax
0x14004c2cb  mov     rax, [rdx]
0x14004c2ce  mov     [rsp+0A8h+var_68], rax
0x14004c2d3  mov     rax, [r8+28h]
0x14004c2d7  mov     [rsp+0A8h+var_70], rax
0x14004c2dc  mov     rax, [r8+8]
0x14004c2e0  mov     [rsp+0A8h+var_78], rax
0x14004c2e5  mov     rax, [rsi+20h]
0x14004c2e9  mov     [rsp+0A8h+var_80], rax
0x14004c2ee  mov     [rsp+0A8h+Timeout], r13
0x14004c2f3  call    WPP_SF_qqiqiiD
0x14004c2f8  jmp     loc_14004C1A6
0x14004c2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c304  cmp     rcx, r14
0x14004c307  jnz     loc_14004C50A
0x14004c30d  mov     r14, rbx
0x14004c310  mov     rcx, r12; Context
0x14004c313  call    cs:__imp_FltReleaseContext
0x14004c31a  nop     dword ptr [rax+rax+00h]
0x14004c31f  mov     r9b, 1
0x14004c322  mov     byte ptr [rsp+0A8h+Timeout], 0
0x14004c327  mov     r8, r14
0x14004c32a  mov     rdx, rdi
0x14004c32d  mov     ecx, esi
0x14004c32f  call    HsmpTracePreCallbackExit
0x14004c334  jmp     loc_14004C272
0x14004c339  mov     eax, [rcx+2Ch]
0x14004c33c  test    al, 1
0x14004c33e  jz      loc_14004C1F4
0x14004c344  cmp     byte ptr [rcx+29h], 2
0x14004c348  jb      loc_14004C1F4
0x14004c34e  mov     rax, [rsi+20h]
0x14004c352  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c359  mov     rcx, [rcx+18h]
0x14004c35d  mov     edx, 0Eh
0x14004c362  mov     dword ptr [rsp+0A8h+var_70], ebx
0x14004c366  mov     r9, rdi
0x14004c369  mov     dword ptr [rsp+0A8h+var_78], r15d
0x14004c36e  mov     [rsp+0A8h+var_80], rax
0x14004c373  mov     [rsp+0A8h+Timeout], r13
0x14004c378  call    WPP_SF_qqiDd
0x14004c37d  jmp     loc_14004C1F4
0x14004c382  mov     esi, 1
0x14004c387  jmp     loc_14004C269
0x14004c38c  mov     r8, r14; Context
0x14004c38f  mov     edx, esi; CallbackStatus
0x14004c391  mov     rcx, rdi; CallbackData
0x14004c394  call    cs:__imp_FltCompletePendedPreOperation
0x14004c39b  nop     dword ptr [rax+rax+00h]
0x14004c3a0  jmp     loc_14004C28C
0x14004c3a5  xor     edx, edx; UnlockRoutine
0x14004c3a7  lea     rcx, HsmiCompleteLockCallbackDataRoutine; CompleteLockCallbackDataRoutine
0x14004c3ae  call    cs:__imp_FltAllocateFileLock
0x14004c3b5  nop     dword ptr [rax+rax+00h]
0x14004c3ba  mov     rdx, rax
0x14004c3bd  test    rax, rax
0x14004c3c0  jnz     loc_14004C448
0x14004c3c6  mov     ebx, 0C000009Ah
0x14004c3cb  mov     ecx, ebx
0x14004c3cd  call    HsmDbgBreakOnStatus
0x14004c3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c3d9  lea     r14, WPP_GLOBAL_Control
0x14004c3e0  cmp     rcx, r14
0x14004c3e3  jz      loc_14004C1F4
0x14004c3e9  mov     eax, [rcx+2Ch]
0x14004c3ec  test    al, 1
0x14004c3ee  jz      loc_14004C1F4
0x14004c3f4  cmp     byte ptr [rcx+29h], 2
0x14004c3f8  jb      loc_14004C1F4
0x14004c3fe  mov     edx, 0Ah
0x14004c403  jmp     short loc_14004C41E
0x14004c405  mov     rcx, rax; FltWorkItem
0x14004c408  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14004c40f  nop     dword ptr [rax+rax+00h]
0x14004c414  jmp     loc_14004C102
0x14004c419  mov     edx, 0Ch
0x14004c41e  mov     rax, [rsi+20h]
0x14004c422  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c429  mov     rcx, [rcx+18h]
0x14004c42d  mov     r9, rdi
0x14004c430  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c434  mov     [rsp+0A8h+var_80], rax
0x14004c439  mov     [rsp+0A8h+Timeout], r13
0x14004c43e  call    WPP_SF_qqqd
0x14004c443  jmp     loc_14004C1F4
0x14004c448  mov     rcx, [r13+0A0h]
0x14004c44f  xor     eax, eax
0x14004c451  lock cmpxchg [rcx+20h], rdx
0x14004c457  jz      loc_14004C169
0x14004c45d  mov     rcx, rdx; FileLock
0x14004c460  call    cs:__imp_FltFreeFileLock
0x14004c467  nop     dword ptr [rax+rax+00h]
0x14004c46c  jmp     loc_14004C169
0x14004c471  mov     r8, rdi; CallbackData
0x14004c474  lea     rcx, [rsp+0A8h+Event]; Object
0x14004c479  xor     edx, edx; Timeout
0x14004c47b  call    cs:__imp_FltCancellableWaitForSingleObject
0x14004c482  nop     dword ptr [rax+rax+00h]
0x14004c487  mov     ecx, eax
0x14004c489  mov     ebx, eax
0x14004c48b  call    HsmDbgBreakOnStatus
0x14004c490  cmp     ebx, 0C000004Bh
0x14004c496  jz      short loc_14004C4A0
0x14004c498  cmp     ebx, 0C0000120h
0x14004c49e  jnz     short loc_14004C4D1
0x14004c4a0  mov     rcx, rdi; CallbackData
0x14004c4a3  call    cs:__imp_FltCancelIo
0x14004c4aa  nop     dword ptr [rax+rax+00h]
0x14004c4af  xor     r9d, r9d; Alertable
0x14004c4b2  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14004c4bb  xor     r8d, r8d; WaitMode
0x14004c4be  lea     rcx, [rsp+0A8h+Event]; Object
0x14004c4c3  xor     edx, edx; WaitReason
0x14004c4c5  call    cs:__imp_KeWaitForSingleObject
0x14004c4cc  nop     dword ptr [rax+rax+00h]
0x14004c4d1  test    ebx, ebx
0x14004c4d3  jns     short loc_14004C4FF
0x14004c4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c4dc  cmp     rcx, r14
0x14004c4df  jz      loc_14004C1F4
0x14004c4e5  mov     eax, [rcx+2Ch]
0x14004c4e8  test    al, 1
0x14004c4ea  jz      loc_14004C1F4
0x14004c4f0  cmp     byte ptr [rcx+29h], 2
0x14004c4f4  jb      loc_14004C1F4
0x14004c4fa  jmp     loc_14004C419
0x14004c4ff  mov     r15d, 4
0x14004c505  jmp     loc_14004C1D6
0x14004c50a  mov     eax, [rcx+2Ch]
0x14004c50d  test    al, 1
0x14004c50f  jz      loc_14004C30D
0x14004c515  cmp     byte ptr [rcx+29h], 2
0x14004c519  jb      loc_14004C30D
0x14004c51f  mov     rax, [rsp+0A8h+arg_18]
0x14004c527  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c52e  mov     rcx, [rcx+18h]
0x14004c532  mov     edx, 0Dh
0x14004c537  mov     dword ptr [rsp+0A8h+var_70], ebx
0x14004c53b  mov     r9, rdi
0x14004c53e  mov     dword ptr [rsp+0A8h+var_78], esi
0x14004c542  mov     rax, [rax+20h]
0x14004c546  mov     [rsp+0A8h+var_80], rax
0x14004c54b  mov     [rsp+0A8h+Timeout], r13
0x14004c550  call    WPP_SF_qqiDd
0x14004c555  jmp     loc_14004C30D
0x14004c55a  mov     rax, [rsi+20h]
0x14004c55e  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c565  mov     rcx, [rcx+18h]
0x14004c569  mov     edx, 0Fh
0x14004c56e  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c572  mov     r9, rdi
0x14004c575  mov     [rsp+0A8h+var_80], rax
0x14004c57a  mov     [rsp+0A8h+Timeout], r13
0x14004c57f  call    WPP_SF_qqqd
0x14004c584  jmp     loc_14004C240
0x14004c589  mov     rax, [rsi+20h]
0x14004c58d  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004c594  mov     rcx, [rcx+18h]
0x14004c598  mov     edx, 10h
0x14004c59d  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004c5a1  mov     r9, rdi
0x14004c5a4  mov     [rsp+0A8h+var_80], rax
0x14004c5a9  mov     [rsp+0A8h+Timeout], r13
0x14004c5ae  call    WPP_SF_qqqd
0x14004c5b3  jmp     loc_14004C25D
```
