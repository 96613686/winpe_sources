# KbdHid_PresenceNotificationCompleted

- ea: `0x1400053c0`
- end: `0x140005484`
- name: `KbdHid_PresenceNotificationCompleted`
- size: `196`
- prototype: `IO_COMPLETION_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001d30`
- `0x1400053c0`
- `0x140005d88`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140005462`
- `ntoskrnl!IoFreeIrp` at `0x140005462`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005453`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005453`

## pseudocode

```c
__int64 __fastcall KbdHid_PresenceNotificationCompleted(PDEVICE_OBJECT DeviceObject, PIRP Irp, char *Context)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      25,
      (__int64)WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
      *(_QWORD *)Context,
      (char)Irp,
      Irp->IoStatus.Status);
  if ( !Irp->IoStatus.Status )
    KbdHid_CancelAutoRepeatTimer(Context);
  *((_QWORD *)Context + 99) = 0;
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 152), Irp, 0x20u);
  IoFreeIrp(Irp);
  return 3221225494LL;
}

```

## disassembly

```asm
0x1400053c0  mov     [rsp+arg_0], rbx
0x1400053c5  mov     [rsp+arg_8], rsi
0x1400053ca  push    rdi
0x1400053cb  sub     rsp, 40h
0x1400053cf  mov     rsi, r8
0x1400053d2  mov     rdi, rdx
0x1400053d5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400053dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400053e3  jz      short loc_140005425
0x1400053e5  mov     eax, [rdx+30h]
0x1400053e8  mov     r9d, 19h
0x1400053ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053f5  mov     [rsp+48h+var_10], eax
0x1400053f9  mov     rax, [r8]
0x1400053fc  mov     r8d, 4
0x140005402  mov     [rsp+48h+var_18], rdx
0x140005407  movzx   edx, r8b
0x14000540b  mov     rcx, [rcx+40h]
0x14000540f  mov     [rsp+48h+var_20], rax
0x140005414  lea     rax, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x14000541b  mov     [rsp+48h+var_28], rax
0x140005420  call    WPP_RECORDER_SF_qqd
0x140005425  cmp     dword ptr [rdi+30h], 0
0x140005429  jnz     short loc_140005438
0x14000542b  mov     edx, 5
0x140005430  mov     rcx, rsi; Context
0x140005433  call    KbdHid_CancelAutoRepeatTimer
0x140005438  lea     rcx, [rsi+98h]; RemoveLock
0x14000543f  mov     qword ptr [rsi+318h], 0
0x14000544a  mov     r8d, 20h ; ' '; RemlockSize
0x140005450  mov     rdx, rdi; Tag
0x140005453  call    cs:__imp_IoReleaseRemoveLockEx
0x14000545a  nop     dword ptr [rax+rax+00h]
0x14000545f  mov     rcx, rdi; Irp
0x140005462  call    cs:__imp_IoFreeIrp
0x140005469  nop     dword ptr [rax+rax+00h]
0x14000546e  mov     rbx, [rsp+48h+arg_0]
0x140005473  mov     eax, 0C0000016h
0x140005478  mov     rsi, [rsp+48h+arg_8]
0x14000547d  add     rsp, 40h
0x140005481  pop     rdi
0x140005482  retn
```
