# I8xCompletePendedRequest

- ea: `0x140007f30`
- end: `0x140007ff0`
- name: `I8xCompletePendedRequest`
- size: `192`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007c20`
- `0x1400090c0`
- `0x1400092d0`

## callees

- `0x140007f30`
- `0x140008d80`

## import_xrefs

- `ntoskrnl!IoFreeController` at `0x140007fa9`
- `ntoskrnl!IoFreeController` at `0x140007fa9`
- `ntoskrnl!IofCompleteRequest` at `0x140007f92`
- `ntoskrnl!IofCompleteRequest` at `0x140007f92`
- `ntoskrnl!IoStartNextPacket` at `0x140007fba`
- `ntoskrnl!IoStartNextPacket` at `0x140007fba`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007fd3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140007fd3`

## pseudocode

```c
void __fastcall I8xCompletePendedRequest(PDEVICE_OBJECT DeviceObject, _QWORD *Tag, int a3, int a4)
{
  char *DeviceExtension; // rsi

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  Tag[7] = 0;
  *((_DWORD *)Tag + 12) = a4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDD(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)Tag, a3, a4);
  IofCompleteRequest((PIRP)Tag, 6);
  IoFreeController(*(PCONTROLLER_OBJECT *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 8LL));
  IoStartNextPacket(DeviceObject, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), Tag, 0x20u);
}

```

## disassembly

```asm
0x140007f30  mov     [rsp+arg_0], rbx
0x140007f35  mov     [rsp+arg_8], rsi
0x140007f3a  push    rdi
0x140007f3b  sub     rsp, 40h
0x140007f3f  mov     rsi, [rcx+40h]
0x140007f43  mov     rbx, rdx
0x140007f46  mov     qword ptr [rdx+38h], 0
0x140007f4e  mov     rdi, rcx
0x140007f51  mov     [rdx+30h], r9d
0x140007f55  lea     rax, WPP_RECORDER_INITIALIZED
0x140007f5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007f63  jz      short loc_140007F8D
0x140007f65  mov     rax, [rdx+0B8h]
0x140007f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007f73  mov     [rsp+48h+var_10], r9d
0x140007f78  mov     eax, [rax+18h]
0x140007f7b  mov     rcx, [rcx+40h]
0x140007f7f  mov     [rsp+48h+var_18], eax
0x140007f83  mov     [rsp+48h+var_20], rdx
0x140007f88  call    WPP_RECORDER_SF_qDD
0x140007f8d  mov     dl, 6; PriorityBoost
0x140007f8f  mov     rcx, rbx; Irp
0x140007f92  call    cs:__imp_IofCompleteRequest
0x140007f99  nop     dword ptr [rax+rax+00h]
0x140007f9e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x140007fa5  mov     rcx, [rcx+8]; ControllerObject
0x140007fa9  call    cs:__imp_IoFreeController
0x140007fb0  nop     dword ptr [rax+rax+00h]
0x140007fb5  xor     edx, edx; Cancelable
0x140007fb7  mov     rcx, rdi; DeviceObject
0x140007fba  call    cs:__imp_IoStartNextPacket
0x140007fc1  nop     dword ptr [rax+rax+00h]
0x140007fc6  lea     rcx, [rsi+28h]; RemoveLock
0x140007fca  mov     r8d, 20h ; ' '; RemlockSize
0x140007fd0  mov     rdx, rbx; Tag
0x140007fd3  call    cs:__imp_IoReleaseRemoveLockEx
0x140007fda  nop     dword ptr [rax+rax+00h]
0x140007fdf  mov     rbx, [rsp+48h+arg_0]
0x140007fe4  mov     rsi, [rsp+48h+arg_8]
0x140007fe9  add     rsp, 40h
0x140007fed  pop     rdi
0x140007fee  retn
```
