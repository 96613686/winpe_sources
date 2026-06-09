# HsmFltPreLOCK_CONTROL

- ea: `0x14004bbf0`
- end: `0x14004be4b`
- name: `HsmFltPreLOCK_CONTROL`
- size: `603`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x140009300`
- `0x1400130d8`
- `0x14004bbf0`
- `0x14004c0c0`

## import_xrefs

- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14004bd6b`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14004bd6b`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x14004bdb0`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x14004bdb0`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004be3a`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004be3a`
- `FLTMGR!FltIsOperationSynchronous` at `0x14004bd0d`
- `FLTMGR!FltIsOperationSynchronous` at `0x14004bd0d`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004bc22`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004bc22`
- `FLTMGR!FltDeleteContext` at `0x14004bd43`
- `FLTMGR!FltDeleteContext` at `0x14004bd43`
- `FLTMGR!FltGetRequestorProcess` at `0x14004bc5c`
- `FLTMGR!FltGetRequestorProcess` at `0x14004bc5c`
- `FLTMGR!FltReleaseContext` at `0x14004bc7d`
- `FLTMGR!FltReleaseContext` at `0x14004bcb3`
- `FLTMGR!FltReleaseContext` at `0x14004bc7d`
- `FLTMGR!FltReleaseContext` at `0x14004bcb3`

## pseudocode

```c
__int64 __fastcall HsmFltPreLOCK_CONTROL(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  struct _FLT_INSTANCE *TargetInstance; // rdi
  int v7; // r8d
  __int64 *v8; // rbx
  __int64 v9; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_CONTEXT v11; // rcx
  unsigned int v12; // edi
  int v13; // ebp
  struct _FLT_DEFERRED_IO_WORKITEM *DeferredIoWorkItem; // rsi
  unsigned int v16; // eax
  bool IsRealTimeThread; // al
  PFLT_CONTEXT Context; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  Iopb = CallbackData->Iopb;
  Context = 0;
  TargetInstance = Iopb->TargetInstance;
  FltGetStreamHandleContext(TargetInstance, Iopb->TargetFileObject, &Context);
  v8 = (__int64 *)Context;
  if ( Context )
  {
    v9 = *((_QWORD *)Context + 2);
    if ( (*(_DWORD *)(v9 + 28) & 1) != 0 )
    {
      if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*(_QWORD *)(v9 + 16) + 16LL) + 32LL) != TargetInstance )
      {
        v11 = Context;
        goto LABEL_6;
      }
      RequestorProcess = FltGetRequestorProcess(CallbackData);
      if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
      {
        v8 = (__int64 *)Context;
        goto LABEL_7;
      }
    }
    else
    {
      if ( !Context )
        goto LABEL_7;
      FltDeleteContext(Context);
    }
    v11 = Context;
LABEL_6:
    FltReleaseContext(v11);
    v8 = 0;
    Context = 0;
  }
LABEL_7:
  if ( !v8 || (*(_DWORD *)(v8[2] + 28) & 2) != 0 )
  {
    v12 = 1;
    if ( !v8 )
      return v12;
    v13 = 0;
  }
  else
  {
    LOBYTE(v7) = 1;
    HsmpTracePreCallbackEnter((_DWORD)CallbackData, 0, v7, (_DWORD)v8, v8[2]);
    if ( FltIsOperationSynchronous(CallbackData) )
    {
      v13 = 0;
      DeferredIoWorkItem = 0;
      HsmPreLockControlSynchronous(0, CallbackData, a3);
      v12 = v16;
      goto LABEL_11;
    }
    v12 = 2;
    DeferredIoWorkItem = FltAllocateDeferredIoWorkItem();
    if ( !DeferredIoWorkItem )
    {
      v13 = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      goto LABEL_11;
    }
    IsRealTimeThread = HsmOsIsRealTimeThread();
    v13 = FltQueueDeferredIoWorkItem(
            DeferredIoWorkItem,
            CallbackData,
            (PFLT_DEFERRED_IO_WORKITEM_ROUTINE)HsmPreLockControlSynchronous,
            (WORK_QUEUE_TYPE)!IsRealTimeThread,
            0);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_05674a74ef883615dbe7db7578a33db5_Traceguids,
          CallbackData->Iopb->TargetFileObject,
          CallbackData,
          v13);
      }
      goto LABEL_11;
    }
  }
  DeferredIoWorkItem = 0;
LABEL_11:
  FltReleaseContext(v8);
  if ( v13 < 0 )
  {
    CallbackData->IoStatus.Status = v13;
    v12 = 4;
    CallbackData->IoStatus.Information = 0;
  }
  if ( DeferredIoWorkItem )
    FltFreeDeferredIoWorkItem(DeferredIoWorkItem);
  return v12;
}

```

## disassembly

```asm
0x14004bbf0  push    rbx
0x14004bbf2  push    rdi
0x14004bbf3  push    r12
0x14004bbf5  push    r14
0x14004bbf7  push    r15
0x14004bbf9  sub     rsp, 30h
0x14004bbfd  xor     r12d, r12d
0x14004bc00  mov     r14, r8
0x14004bc03  mov     [r8], r12
0x14004bc06  mov     r15, rcx
0x14004bc09  mov     rdx, [rcx+10h]
0x14004bc0d  lea     r8, [rsp+58h+Context]; Context
0x14004bc12  mov     [rsp+58h+Context], r12
0x14004bc17  mov     rdi, [rdx+10h]
0x14004bc1b  mov     rdx, [rdx+8]; FileObject
0x14004bc1f  mov     rcx, rdi; Instance
0x14004bc22  call    cs:__imp_FltGetStreamHandleContext
0x14004bc29  nop     dword ptr [rax+rax+00h]
0x14004bc2e  mov     rbx, [rsp+58h+Context]
0x14004bc33  test    rbx, rbx
0x14004bc36  jz      short loc_14004BC91
0x14004bc38  mov     rcx, [rbx+10h]
0x14004bc3c  mov     eax, [rcx+1Ch]
0x14004bc3f  test    al, 1
0x14004bc41  jz      loc_14004BD37
0x14004bc47  mov     rax, [rcx+10h]
0x14004bc4b  mov     rcx, [rax+10h]
0x14004bc4f  cmp     [rcx+20h], rdi
0x14004bc53  jnz     loc_14004BD54
0x14004bc59  mov     rcx, r15; CallbackData
0x14004bc5c  call    cs:__imp_FltGetRequestorProcess
0x14004bc63  nop     dword ptr [rax+rax+00h]
0x14004bc68  mov     rcx, rax
0x14004bc6b  call    HsmOsIsPassThroughModeEnabled
0x14004bc70  test    al, al
0x14004bc72  jz      loc_14004BD5C
0x14004bc78  mov     rcx, [rsp+58h+Context]; Context
0x14004bc7d  call    cs:__imp_FltReleaseContext
0x14004bc84  nop     dword ptr [rax+rax+00h]
0x14004bc89  mov     rbx, r12
0x14004bc8c  mov     [rsp+58h+Context], rbx
0x14004bc91  mov     [rsp+58h+arg_8], rbp
0x14004bc96  mov     [rsp+58h+arg_10], rsi
0x14004bc9b  test    rbx, rbx
0x14004bc9e  jnz     short loc_14004BCEA
0x14004bca0  mov     edi, 1
0x14004bca5  test    rbx, rbx
0x14004bca8  jz      short loc_14004BCD0
0x14004bcaa  mov     ebp, r12d
0x14004bcad  mov     rsi, r12
0x14004bcb0  mov     rcx, rbx; Context
0x14004bcb3  call    cs:__imp_FltReleaseContext
0x14004bcba  nop     dword ptr [rax+rax+00h]
0x14004bcbf  test    ebp, ebp
0x14004bcc1  js      loc_14004BE25
0x14004bcc7  test    rsi, rsi
0x14004bcca  jnz     loc_14004BE37
0x14004bcd0  mov     rsi, [rsp+58h+arg_10]
0x14004bcd5  mov     eax, edi
0x14004bcd7  mov     rbp, [rsp+58h+arg_8]
0x14004bcdc  add     rsp, 30h
0x14004bce0  pop     r15
0x14004bce2  pop     r14
0x14004bce4  pop     r12
0x14004bce6  pop     rdi
0x14004bce7  pop     rbx
0x14004bce8  retn
0x14004bcea  mov     rcx, [rbx+10h]
0x14004bcee  mov     eax, [rcx+1Ch]
0x14004bcf1  test    al, 2
0x14004bcf3  jnz     short loc_14004BCA0
0x14004bcf5  mov     [rsp+58h+var_38], rcx
0x14004bcfa  mov     r9, rbx
0x14004bcfd  mov     rcx, r15
0x14004bd00  mov     r8b, 1
0x14004bd03  xor     edx, edx
0x14004bd05  call    HsmpTracePreCallbackEnter
0x14004bd0a  mov     rcx, r15; CallbackData
0x14004bd0d  call    cs:__imp_FltIsOperationSynchronous
0x14004bd14  nop     dword ptr [rax+rax+00h]
0x14004bd19  test    al, al
0x14004bd1b  jz      short loc_14004BD66
0x14004bd1d  mov     r8, r14; Context
0x14004bd20  mov     rdx, r15; CallbackData
0x14004bd23  xor     ecx, ecx; FltWorkItem
0x14004bd25  mov     ebp, r12d
0x14004bd28  mov     rsi, r12
0x14004bd2b  call    HsmPreLockControlSynchronous
0x14004bd30  mov     edi, eax
0x14004bd32  jmp     loc_14004BCB0
0x14004bd37  test    rbx, rbx
0x14004bd3a  jz      loc_14004BC91
0x14004bd40  mov     rcx, rbx; Context
0x14004bd43  call    cs:__imp_FltDeleteContext
0x14004bd4a  nop     dword ptr [rax+rax+00h]
0x14004bd4f  jmp     loc_14004BC78
0x14004bd54  mov     rcx, rbx
0x14004bd57  jmp     loc_14004BC7D
0x14004bd5c  mov     rbx, [rsp+58h+Context]
0x14004bd61  jmp     loc_14004BC91
0x14004bd66  mov     edi, 2
0x14004bd6b  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x14004bd72  nop     dword ptr [rax+rax+00h]
0x14004bd77  mov     rsi, rax
0x14004bd7a  test    rax, rax
0x14004bd7d  jnz     short loc_14004BD90
0x14004bd7f  mov     ebp, 0C000009Ah
0x14004bd84  mov     ecx, ebp
0x14004bd86  call    HsmDbgBreakOnStatus
0x14004bd8b  jmp     loc_14004BCB0
0x14004bd90  call    HsmOsIsRealTimeThread
0x14004bd95  test    al, al
0x14004bd97  mov     [rsp+58h+var_38], r12; Context
0x14004bd9c  mov     r9d, r12d
0x14004bd9f  lea     r8, HsmPreLockControlSynchronous; WorkerRoutine
0x14004bda6  setz    r9b; QueueType
0x14004bdaa  mov     rdx, r15; Data
0x14004bdad  mov     rcx, rsi; FltWorkItem
0x14004bdb0  call    cs:__imp_FltQueueDeferredIoWorkItem
0x14004bdb7  nop     dword ptr [rax+rax+00h]
0x14004bdbc  mov     ecx, eax
0x14004bdbe  mov     ebp, eax
0x14004bdc0  call    HsmDbgBreakOnStatus
0x14004bdc5  test    ebp, ebp
0x14004bdc7  jns     loc_14004BCAD
0x14004bdcd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bdd4  lea     rax, WPP_GLOBAL_Control
0x14004bddb  cmp     rcx, rax
0x14004bdde  jz      loc_14004BCB0
0x14004bde4  mov     edx, [rcx+2Ch]
0x14004bde7  test    dl, 1
0x14004bdea  jz      loc_14004BCB0
0x14004bdf0  cmp     [rcx+29h], dil
0x14004bdf4  jb      loc_14004BCB0
0x14004bdfa  mov     r9, [r15+10h]
0x14004bdfe  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004be05  mov     rcx, [rcx+18h]
0x14004be09  mov     edx, 11h
0x14004be0e  mov     [rsp+58h+var_30], ebp
0x14004be12  mov     [rsp+58h+var_38], r15
0x14004be17  mov     r9, [r9+8]
0x14004be1b  call    WPP_SF_qqd
0x14004be20  jmp     loc_14004BCB0
0x14004be25  mov     [r15+18h], ebp
0x14004be29  mov     edi, 4
0x14004be2e  mov     [r15+20h], r12
0x14004be32  jmp     loc_14004BCC7
0x14004be37  mov     rcx, rsi; FltWorkItem
0x14004be3a  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14004be41  nop     dword ptr [rax+rax+00h]
0x14004be46  jmp     loc_14004BCD0
```
