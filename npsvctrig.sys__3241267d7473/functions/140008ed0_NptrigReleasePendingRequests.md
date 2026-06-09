# NptrigReleasePendingRequests

- ea: `0x140008ed0`
- end: `0x140009063`
- name: `NptrigReleasePendingRequests`
- size: `403`
- prototype: `PFLT_CALLBACK_DATA __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008410`
- `0x140008cb0`
- `0x14000a190`

## callees

- `0x140001220`
- `0x140001500`
- `0x1400015f0`
- `0x1400017b0`
- `0x140008330`
- `0x140008ed0`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140008f93`
- `ntoskrnl!KeCancelTimer` at `0x140008f93`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140008fd6`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140008fd6`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140008f4a`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009032`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140008f4a`
- `FLTMGR!FltCbdqRemoveNextIo` at `0x140009032`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140009017`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140009017`

## pseudocode

```c
PFLT_CALLBACK_DATA __fastcall NptrigReleasePendingRequests(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS v4; // ebp
  void *v7; // rsi
  PFLT_CALLBACK_DATA result; // rax
  __int64 v9; // r8
  struct _FLT_CALLBACK_DATA *i; // rbx
  _QWORD *v11; // r14
  __int64 v12; // r8
  __int64 v13; // r8

  v4 = a3;
  if ( (WPP_MAIN_CB.DeviceType & 1) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (REGHANDLE *)&SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
      (const EVENT_DESCRIPTOR *)ServiceTriggerPerfServiceArrived,
      a3,
      a4,
      *(const char **)(a1 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 28, a3, a1, v4);
  v7 = (void *)(a1 + 16);
  result = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(a2 + 24), (PVOID)(a1 + 16));
  for ( i = result; result; i = result )
  {
    v11 = i->QueueContext[0];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, v9, i->QueueContext[0]);
    if ( KeCancelTimer((PKTIMER)(v11 + 15)) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, v12, v11);
      NptrigReleaseRequestRef(v11);
      FltFreeGenericWorkItem((PFLT_GENERIC_WORKITEM)v11[24]);
    }
    NptrigAlterIoStatus(i, v4, v12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 31, v13, *v11, v4);
    FltCompletePendedPostOperation(i);
    NptrigReleaseRequestRef(v11);
    result = FltCbdqRemoveNextIo((PFLT_CALLBACK_DATA_QUEUE)(a2 + 24), v7);
  }
  return result;
}

```

## disassembly

```asm
0x140008ed0  mov     [rsp+arg_8], rbx
0x140008ed5  mov     [rsp+arg_10], rbp
0x140008eda  push    rsi
0x140008edb  push    rdi
0x140008edc  push    r15
0x140008ede  sub     rsp, 30h
0x140008ee2  test    byte ptr cs:WPP_MAIN_CB.DeviceType, 1
0x140008ee9  mov     ebp, r8d
0x140008eec  mov     rdi, rdx
0x140008eef  mov     rbx, rcx
0x140008ef2  jz      short loc_140008F10
0x140008ef4  mov     rax, [rcx+18h]
0x140008ef8  lea     rdx, ServiceTriggerPerfServiceArrived
0x140008eff  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context; int
0x140008f06  mov     [rsp+48h+var_28], rax; __int64
0x140008f0b  call    McTemplateK0zz_EtwWriteTransfer
0x140008f10  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f17  lea     r15, WPP_GLOBAL_Control
0x140008f1e  cmp     rcx, r15
0x140008f21  jz      short loc_140008F3F
0x140008f23  mov     eax, [rcx+2Ch]
0x140008f26  test    al, 4
0x140008f28  jz      short loc_140008F3F
0x140008f2a  mov     rcx, [rcx+18h]
0x140008f2e  mov     edx, 1Ch
0x140008f33  mov     r9, rbx
0x140008f36  mov     dword ptr [rsp+48h+var_28], ebp
0x140008f3a  call    WPP_SF_qd
0x140008f3f  lea     rsi, [rbx+10h]
0x140008f43  mov     rdx, rsi; PeekContext
0x140008f46  lea     rcx, [rdi+18h]; Cbdq
0x140008f4a  call    cs:__imp_FltCbdqRemoveNextIo
0x140008f51  nop     dword ptr [rax+rax+00h]
0x140008f56  mov     rbx, rax
0x140008f59  test    rax, rax
0x140008f5c  jz      loc_14000904F
0x140008f62  mov     [rsp+48h+arg_0], r14
0x140008f67  mov     r14, [rbx+40h]
0x140008f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f72  cmp     rcx, r15
0x140008f75  jz      short loc_140008F8F
0x140008f77  mov     eax, [rcx+2Ch]
0x140008f7a  test    al, 4
0x140008f7c  jz      short loc_140008F8F
0x140008f7e  mov     rcx, [rcx+18h]
0x140008f82  mov     edx, 1Dh
0x140008f87  mov     r9, r14
0x140008f8a  call    WPP_SF_q
0x140008f8f  lea     rcx, [r14+78h]; PKTIMER
0x140008f93  call    cs:__imp_KeCancelTimer
0x140008f9a  nop     dword ptr [rax+rax+00h]
0x140008f9f  test    al, al
0x140008fa1  jz      short loc_140008FE2
0x140008fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140008faa  cmp     rcx, r15
0x140008fad  jz      short loc_140008FC7
0x140008faf  mov     eax, [rcx+2Ch]
0x140008fb2  test    al, 4
0x140008fb4  jz      short loc_140008FC7
0x140008fb6  mov     rcx, [rcx+18h]
0x140008fba  mov     edx, 1Eh
0x140008fbf  mov     r9, r14
0x140008fc2  call    WPP_SF_q
0x140008fc7  mov     rcx, r14; P
0x140008fca  call    NptrigReleaseRequestRef
0x140008fcf  mov     rcx, [r14+0C0h]; FltWorkItem
0x140008fd6  call    cs:__imp_FltFreeGenericWorkItem
0x140008fdd  nop     dword ptr [rax+rax+00h]
0x140008fe2  mov     edx, ebp
0x140008fe4  mov     rcx, rbx; Data
0x140008fe7  call    NptrigAlterIoStatus
0x140008fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ff3  cmp     rcx, r15
0x140008ff6  jz      short loc_140009014
0x140008ff8  mov     eax, [rcx+2Ch]
0x140008ffb  test    al, 4
0x140008ffd  jz      short loc_140009014
0x140008fff  mov     r9, [r14]
0x140009002  mov     edx, 1Fh
0x140009007  mov     rcx, [rcx+18h]
0x14000900b  mov     dword ptr [rsp+48h+var_28], ebp
0x14000900f  call    WPP_SF_qd
0x140009014  mov     rcx, rbx; CallbackData
0x140009017  call    cs:__imp_FltCompletePendedPostOperation
0x14000901e  nop     dword ptr [rax+rax+00h]
0x140009023  mov     rcx, r14; P
0x140009026  call    NptrigReleaseRequestRef
0x14000902b  mov     rdx, rsi; PeekContext
0x14000902e  lea     rcx, [rdi+18h]; Cbdq
0x140009032  call    cs:__imp_FltCbdqRemoveNextIo
0x140009039  nop     dword ptr [rax+rax+00h]
0x14000903e  mov     rbx, rax
0x140009041  test    rax, rax
0x140009044  jnz     loc_140008F67
0x14000904a  mov     r14, [rsp+48h+arg_0]
0x14000904f  mov     rbx, [rsp+48h+arg_8]
0x140009054  mov     rbp, [rsp+48h+arg_10]
0x140009059  add     rsp, 30h
0x14000905d  pop     r15
0x14000905f  pop     rdi
0x140009060  pop     rsi
0x140009061  retn
```
