# NptrigWaitNamedPipeTimeoutWorkItem

- ea: `0x140009fa0`
- end: `0x14000a0ed`
- name: `NptrigWaitNamedPipeTimeoutWorkItem`
- size: `333`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, IO_CSQ_IRP_CONTEXT *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001500`
- `0x1400015f0`
- `0x140001928`
- `0x140008330`
- `0x140009fa0`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x14000a0c8`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14000a0c8`
- `FLTMGR!FltCbdqRemoveIo` at `0x140009ff7`
- `FLTMGR!FltCbdqRemoveIo` at `0x140009ff7`
- `FLTMGR!FltCompletePendedPostOperation` at `0x14000a0b1`
- `FLTMGR!FltCompletePendedPostOperation` at `0x14000a0b1`

## pseudocode

```c
void __fastcall NptrigWaitNamedPipeTimeoutWorkItem(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        IO_CSQ_IRP_CONTEXT *Context)
{
  __int64 v5; // r8
  __int64 v6; // r9
  NTSTATUS v7; // edx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 33, Context, Context, *(_QWORD *)&Context->Type);
  if ( FltCbdqRemoveIo((PFLT_CALLBACK_DATA_QUEUE)&Context[8].Irp->AssociatedIrp, Context + 3) )
  {
    if ( (WPP_MAIN_CB.DeviceType & 1) != 0 )
      McTemplateK0zz_EtwWriteTransfer(
        (REGHANDLE *)&SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
        (const EVENT_DESCRIPTOR *)ServiceTriggerPerfServiceTimedOut,
        v5,
        v6,
        (const char *)Context[4].Irp);
    v7 = -1073741643;
    if ( LODWORD(Context[7].Csq) )
      v7 = -1073741772;
    NptrigAlterIoStatus(*(PFLT_CALLBACK_DATA *)&Context->Type, v7, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 35, v8, Context, *(_QWORD *)&Context->Type);
    FltCompletePendedPostOperation(*(PFLT_CALLBACK_DATA *)&Context->Type);
    NptrigReleaseRequestRef((volatile signed __int32 *)Context, v9, v10);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 34, v5, Context, *(_QWORD *)&Context->Type);
  }
  FltFreeGenericWorkItem(FltWorkItem);
  NptrigReleaseRequestRef((volatile signed __int32 *)Context, v11, v12);
}

```

## disassembly

```asm
0x140009fa0  mov     [rsp+arg_0], rbx
0x140009fa5  mov     [rsp+arg_8], rsi
0x140009faa  push    rdi
0x140009fab  sub     rsp, 30h
0x140009faf  mov     rbx, r8
0x140009fb2  mov     rdi, rcx
0x140009fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fbc  lea     rsi, WPP_GLOBAL_Control
0x140009fc3  cmp     rcx, rsi
0x140009fc6  jz      short loc_140009FE8
0x140009fc8  mov     eax, [rcx+2Ch]
0x140009fcb  test    al, 4
0x140009fcd  jz      short loc_140009FE8
0x140009fcf  mov     rax, [r8]
0x140009fd2  mov     edx, 21h ; '!'
0x140009fd7  mov     rcx, [rcx+18h]
0x140009fdb  mov     r9, rbx
0x140009fde  mov     [rsp+38h+var_18], rax
0x140009fe3  call    WPP_SF_qq
0x140009fe8  mov     rcx, [rbx+0C8h]
0x140009fef  lea     rdx, [rbx+48h]; Context
0x140009ff3  add     rcx, 18h; Cbdq
0x140009ff7  call    cs:__imp_FltCbdqRemoveIo
0x140009ffe  nop     dword ptr [rax+rax+00h]
0x14000a003  test    rax, rax
0x14000a006  jnz     short loc_14000A041
0x14000a008  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a00f  cmp     rcx, rsi
0x14000a012  jz      loc_14000A0C5
0x14000a018  mov     eax, [rcx+2Ch]
0x14000a01b  test    al, 4
0x14000a01d  jz      loc_14000A0C5
0x14000a023  mov     rax, [rbx]
0x14000a026  mov     edx, 22h ; '"'
0x14000a02b  mov     rcx, [rcx+18h]
0x14000a02f  mov     r9, rbx
0x14000a032  mov     [rsp+38h+var_18], rax
0x14000a037  call    WPP_SF_qq
0x14000a03c  jmp     loc_14000A0C5
0x14000a041  test    byte ptr cs:WPP_MAIN_CB.DeviceType, 1
0x14000a048  jz      short loc_14000A066
0x14000a04a  mov     rax, [rbx+68h]
0x14000a04e  lea     rdx, ServiceTriggerPerfServiceTimedOut
0x14000a055  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context; int
0x14000a05c  mov     [rsp+38h+var_18], rax; __int64
0x14000a061  call    McTemplateK0zz_EtwWriteTransfer
0x14000a066  cmp     dword ptr [rbx+0B8h], 0
0x14000a06d  mov     edx, 0C00000B5h
0x14000a072  mov     rcx, [rbx]; Data
0x14000a075  mov     eax, 0C0000034h
0x14000a07a  cmovnz  edx, eax
0x14000a07d  call    NptrigAlterIoStatus
0x14000a082  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a089  cmp     rcx, rsi
0x14000a08c  jz      short loc_14000A0AE
0x14000a08e  mov     eax, [rcx+2Ch]
0x14000a091  test    al, 4
0x14000a093  jz      short loc_14000A0AE
0x14000a095  mov     rax, [rbx]
0x14000a098  mov     edx, 23h ; '#'
0x14000a09d  mov     rcx, [rcx+18h]
0x14000a0a1  mov     r9, rbx
0x14000a0a4  mov     [rsp+38h+var_18], rax
0x14000a0a9  call    WPP_SF_qq
0x14000a0ae  mov     rcx, [rbx]; CallbackData
0x14000a0b1  call    cs:__imp_FltCompletePendedPostOperation
0x14000a0b8  nop     dword ptr [rax+rax+00h]
0x14000a0bd  mov     rcx, rbx; P
0x14000a0c0  call    NptrigReleaseRequestRef
0x14000a0c5  mov     rcx, rdi; FltWorkItem
0x14000a0c8  call    cs:__imp_FltFreeGenericWorkItem
0x14000a0cf  nop     dword ptr [rax+rax+00h]
0x14000a0d4  mov     rcx, rbx; P
0x14000a0d7  call    NptrigReleaseRequestRef
0x14000a0dc  mov     rbx, [rsp+38h+arg_0]
0x14000a0e1  mov     rsi, [rsp+38h+arg_8]
0x14000a0e6  add     rsp, 30h
0x14000a0ea  pop     rdi
0x14000a0eb  retn
```
