# HsmFltPreLOCK_CONTROL

- ea: `0x14004bce0`
- end: `0x14004bf3b`
- name: `HsmFltPreLOCK_CONTROL`
- size: `603`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003c50`
- `0x1400044f0`
- `0x140006f40`
- `0x140009300`
- `0x140013158`
- `0x14004bce0`
- `0x14004c1b0`

## import_xrefs

- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14004be5b`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14004be5b`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x14004bea0`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x14004bea0`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004bf2a`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14004bf2a`
- `FLTMGR!FltIsOperationSynchronous` at `0x14004bdfd`
- `FLTMGR!FltIsOperationSynchronous` at `0x14004bdfd`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004bd12`
- `FLTMGR!FltGetStreamHandleContext` at `0x14004bd12`
- `FLTMGR!FltDeleteContext` at `0x14004be33`
- `FLTMGR!FltDeleteContext` at `0x14004be33`
- `FLTMGR!FltGetRequestorProcess` at `0x14004bd4c`
- `FLTMGR!FltGetRequestorProcess` at `0x14004bd4c`
- `FLTMGR!FltReleaseContext` at `0x14004bd6d`
- `FLTMGR!FltReleaseContext` at `0x14004bda3`
- `FLTMGR!FltReleaseContext` at `0x14004bd6d`
- `FLTMGR!FltReleaseContext` at `0x14004bda3`

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
  NTSTATUS v13; // ebp
  struct _FLT_DEFERRED_IO_WORKITEM *DeferredIoWorkItem; // rsi
  unsigned int v16; // eax
  char IsRealTimeThread; // al
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
      HsmDbgBreakOnStatus(-1073741670);
      goto LABEL_11;
    }
    IsRealTimeThread = HsmOsIsRealTimeThread();
    v13 = FltQueueDeferredIoWorkItem(
            DeferredIoWorkItem,
            CallbackData,
            HsmPreLockControlSynchronous,
            (WORK_QUEUE_TYPE)(IsRealTimeThread == 0),
            0);
    HsmDbgBreakOnStatus(v13);
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
0x14004bce0  push    rbx
0x14004bce2  push    rdi
0x14004bce3  push    r12
0x14004bce5  push    r14
0x14004bce7  push    r15
0x14004bce9  sub     rsp, 30h
0x14004bced  xor     r12d, r12d
0x14004bcf0  mov     r14, r8
0x14004bcf3  mov     [r8], r12
0x14004bcf6  mov     r15, rcx
0x14004bcf9  mov     rdx, [rcx+10h]
0x14004bcfd  lea     r8, [rsp+58h+Context]; Context
0x14004bd02  mov     [rsp+58h+Context], r12
0x14004bd07  mov     rdi, [rdx+10h]
0x14004bd0b  mov     rdx, [rdx+8]; FileObject
0x14004bd0f  mov     rcx, rdi; Instance
0x14004bd12  call    cs:__imp_FltGetStreamHandleContext
0x14004bd19  nop     dword ptr [rax+rax+00h]
0x14004bd1e  mov     rbx, [rsp+58h+Context]
0x14004bd23  test    rbx, rbx
0x14004bd26  jz      short loc_14004BD81
0x14004bd28  mov     rcx, [rbx+10h]
0x14004bd2c  mov     eax, [rcx+1Ch]
0x14004bd2f  test    al, 1
0x14004bd31  jz      loc_14004BE27
0x14004bd37  mov     rax, [rcx+10h]
0x14004bd3b  mov     rcx, [rax+10h]
0x14004bd3f  cmp     [rcx+20h], rdi
0x14004bd43  jnz     loc_14004BE44
0x14004bd49  mov     rcx, r15; CallbackData
0x14004bd4c  call    cs:__imp_FltGetRequestorProcess
0x14004bd53  nop     dword ptr [rax+rax+00h]
0x14004bd58  mov     rcx, rax
0x14004bd5b  call    HsmOsIsPassThroughModeEnabled
0x14004bd60  test    al, al
0x14004bd62  jz      loc_14004BE4C
0x14004bd68  mov     rcx, [rsp+58h+Context]; Context
0x14004bd6d  call    cs:__imp_FltReleaseContext
0x14004bd74  nop     dword ptr [rax+rax+00h]
0x14004bd79  mov     rbx, r12
0x14004bd7c  mov     [rsp+58h+Context], rbx
0x14004bd81  mov     [rsp+58h+arg_8], rbp
0x14004bd86  mov     [rsp+58h+arg_10], rsi
0x14004bd8b  test    rbx, rbx
0x14004bd8e  jnz     short loc_14004BDDA
0x14004bd90  mov     edi, 1
0x14004bd95  test    rbx, rbx
0x14004bd98  jz      short loc_14004BDC0
0x14004bd9a  mov     ebp, r12d
0x14004bd9d  mov     rsi, r12
0x14004bda0  mov     rcx, rbx; Context
0x14004bda3  call    cs:__imp_FltReleaseContext
0x14004bdaa  nop     dword ptr [rax+rax+00h]
0x14004bdaf  test    ebp, ebp
0x14004bdb1  js      loc_14004BF15
0x14004bdb7  test    rsi, rsi
0x14004bdba  jnz     loc_14004BF27
0x14004bdc0  mov     rsi, [rsp+58h+arg_10]
0x14004bdc5  mov     eax, edi
0x14004bdc7  mov     rbp, [rsp+58h+arg_8]
0x14004bdcc  add     rsp, 30h
0x14004bdd0  pop     r15
0x14004bdd2  pop     r14
0x14004bdd4  pop     r12
0x14004bdd6  pop     rdi
0x14004bdd7  pop     rbx
0x14004bdd8  retn
0x14004bdda  mov     rcx, [rbx+10h]
0x14004bdde  mov     eax, [rcx+1Ch]
0x14004bde1  test    al, 2
0x14004bde3  jnz     short loc_14004BD90
0x14004bde5  mov     [rsp+58h+var_38], rcx
0x14004bdea  mov     r9, rbx
0x14004bded  mov     rcx, r15
0x14004bdf0  mov     r8b, 1
0x14004bdf3  xor     edx, edx
0x14004bdf5  call    HsmpTracePreCallbackEnter
0x14004bdfa  mov     rcx, r15; CallbackData
0x14004bdfd  call    cs:__imp_FltIsOperationSynchronous
0x14004be04  nop     dword ptr [rax+rax+00h]
0x14004be09  test    al, al
0x14004be0b  jz      short loc_14004BE56
0x14004be0d  mov     r8, r14; Context
0x14004be10  mov     rdx, r15; CallbackData
0x14004be13  xor     ecx, ecx; FltWorkItem
0x14004be15  mov     ebp, r12d
0x14004be18  mov     rsi, r12
0x14004be1b  call    HsmPreLockControlSynchronous
0x14004be20  mov     edi, eax
0x14004be22  jmp     loc_14004BDA0
0x14004be27  test    rbx, rbx
0x14004be2a  jz      loc_14004BD81
0x14004be30  mov     rcx, rbx; Context
0x14004be33  call    cs:__imp_FltDeleteContext
0x14004be3a  nop     dword ptr [rax+rax+00h]
0x14004be3f  jmp     loc_14004BD68
0x14004be44  mov     rcx, rbx
0x14004be47  jmp     loc_14004BD6D
0x14004be4c  mov     rbx, [rsp+58h+Context]
0x14004be51  jmp     loc_14004BD81
0x14004be56  mov     edi, 2
0x14004be5b  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x14004be62  nop     dword ptr [rax+rax+00h]
0x14004be67  mov     rsi, rax
0x14004be6a  test    rax, rax
0x14004be6d  jnz     short loc_14004BE80
0x14004be6f  mov     ebp, 0C000009Ah
0x14004be74  mov     ecx, ebp
0x14004be76  call    HsmDbgBreakOnStatus
0x14004be7b  jmp     loc_14004BDA0
0x14004be80  call    HsmOsIsRealTimeThread
0x14004be85  test    al, al
0x14004be87  mov     [rsp+58h+var_38], r12; Context
0x14004be8c  mov     r9d, r12d
0x14004be8f  lea     r8, HsmPreLockControlSynchronous; WorkerRoutine
0x14004be96  setz    r9b; QueueType
0x14004be9a  mov     rdx, r15; Data
0x14004be9d  mov     rcx, rsi; FltWorkItem
0x14004bea0  call    cs:__imp_FltQueueDeferredIoWorkItem
0x14004bea7  nop     dword ptr [rax+rax+00h]
0x14004beac  mov     ecx, eax
0x14004beae  mov     ebp, eax
0x14004beb0  call    HsmDbgBreakOnStatus
0x14004beb5  test    ebp, ebp
0x14004beb7  jns     loc_14004BD9D
0x14004bebd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bec4  lea     rax, WPP_GLOBAL_Control
0x14004becb  cmp     rcx, rax
0x14004bece  jz      loc_14004BDA0
0x14004bed4  mov     edx, [rcx+2Ch]
0x14004bed7  test    dl, 1
0x14004beda  jz      loc_14004BDA0
0x14004bee0  cmp     [rcx+29h], dil
0x14004bee4  jb      loc_14004BDA0
0x14004beea  mov     r9, [r15+10h]
0x14004beee  lea     r8, WPP_05674a74ef883615dbe7db7578a33db5_Traceguids
0x14004bef5  mov     rcx, [rcx+18h]
0x14004bef9  mov     edx, 11h
0x14004befe  mov     [rsp+58h+var_30], ebp
0x14004bf02  mov     [rsp+58h+var_38], r15
0x14004bf07  mov     r9, [r9+8]
0x14004bf0b  call    WPP_SF_qqd
0x14004bf10  jmp     loc_14004BDA0
0x14004bf15  mov     [r15+18h], ebp
0x14004bf19  mov     edi, 4
0x14004bf1e  mov     [r15+20h], r12
0x14004bf22  jmp     loc_14004BDB7
0x14004bf27  mov     rcx, rsi; FltWorkItem
0x14004bf2a  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14004bf31  nop     dword ptr [rax+rax+00h]
0x14004bf36  jmp     loc_14004BDC0
```
