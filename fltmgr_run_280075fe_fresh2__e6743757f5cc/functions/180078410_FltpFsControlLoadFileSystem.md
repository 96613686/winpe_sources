# FltpFsControlLoadFileSystem

- ea: `0x180078410`
- end: `0x180078597`
- name: `FltpFsControlLoadFileSystem`
- size: `391`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006ee20`

## callees

- `0x180003380`
- `0x180009f20`
- `0x18001cd80`
- `0x18001fd80`
- `0x180020a00`
- `0x1800682b0`
- `0x180078410`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x180078470`
- `ntoskrnl!KeInitializeEvent` at `0x180078470`
- `ntoskrnl!IoAttachDeviceToDeviceStackSafe` at `0x180078552`
- `ntoskrnl!IoAttachDeviceToDeviceStackSafe` at `0x180078552`
- `ntoskrnl!IoDetachDevice` at `0x1800784cb`
- `ntoskrnl!IoDetachDevice` at `0x1800784cb`
- `ntoskrnl!IofCompleteRequest` at `0x18007857d`
- `ntoskrnl!IofCompleteRequest` at `0x18007857d`

## pseudocode

```c
__int64 __fastcall FltpFsControlLoadFileSystem(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  unsigned __int16 *DeviceExtension; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r8d
  unsigned int Status; // ebx
  int v12; // [rsp+20h] [rbp-68h]
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  DeviceExtension = (unsigned __int16 *)DeviceObject->DeviceExtension;
  memset(&Event, 0, sizeof(Event));
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0spw_EtwWriteTransfer(
      (_DWORD)DeviceObject,
      (unsigned int)fltmgr_c7670,
      (unsigned int)"FltpFsControlLoadFileSystem",
      (_DWORD)DeviceObject,
      DeviceExtension[24] >> 1,
      *((_QWORD *)DeviceExtension + 7));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v6 = Irp->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FltpFsControlCompletion;
  v6[-1].Context = &Event;
  v6[-1].Control = -32;
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 1));
  if ( (unsigned int)FltpCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp) == 259 )
    FltpCancellableWaitForIo(&Event, Irp);
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0sppwd_EtwWriteTransfer(
      DeviceExtension[24] >> 1,
      v7,
      v8,
      (_DWORD)DeviceObject,
      v12,
      DeviceExtension[24] >> 1,
      *((_QWORD *)DeviceExtension + 7),
      Irp->IoStatus.Status);
  if ( (int)FltpDbgStatus((unsigned int)Irp->IoStatus.Status, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 7733, 0) >= 0
    || Irp->IoStatus.Status == -1073741554 )
  {
    *((_QWORD *)DeviceExtension + 1) = 0;
    FltpCleanupDeviceObject(DeviceObject, 8, v9);
  }
  else
  {
    IoAttachDeviceToDeviceStackSafe(
      DeviceObject,
      *((PDEVICE_OBJECT *)DeviceExtension + 1),
      (PDEVICE_OBJECT *)DeviceExtension + 1);
  }
  Status = Irp->IoStatus.Status;
  IofCompleteRequest(Irp, 0);
  return Status;
}

```

## disassembly

```asm
0x180078410  push    rbx
0x180078412  push    rbp
0x180078413  push    rsi
0x180078414  push    rdi
0x180078415  push    r14
0x180078417  sub     rsp, 60h
0x18007841b  mov     rbp, [rcx+40h]
0x18007841f  xor     eax, eax
0x180078421  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x180078428  xorps   xmm0, xmm0
0x18007842b  mov     rdi, rdx
0x18007842e  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x180078433  mov     rsi, rcx
0x180078436  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x18007843b  jz      short loc_180078466
0x18007843d  movzx   edx, word ptr [rbp+30h]
0x180078441  lea     r8, aFltpfscontroll; "FltpFsControlLoadFileSystem"
0x180078448  mov     rax, [rbp+38h]
0x18007844c  mov     r9, rcx
0x18007844f  shr     edx, 1
0x180078451  mov     [rsp+88h+var_60], rax
0x180078456  mov     [rsp+88h+var_68], edx
0x18007845a  lea     rdx, fltmgr_c7670
0x180078461  call    McTemplateU0spw_EtwWriteTransfer
0x180078466  xor     r8d, r8d; State
0x180078469  lea     rcx, [rsp+88h+Event]; Event
0x18007846e  xor     edx, edx; Type
0x180078470  call    cs:__imp_KeInitializeEvent
0x180078477  nop     dword ptr [rax+rax+00h]
0x18007847c  mov     rax, [rdi+0B8h]
0x180078483  lea     rcx, FltpFsControlCompletion
0x18007848a  movups  xmm0, xmmword ptr [rax]
0x18007848d  movups  xmmword ptr [rax-48h], xmm0
0x180078491  movups  xmm1, xmmword ptr [rax+10h]
0x180078495  movups  xmmword ptr [rax-38h], xmm1
0x180078499  movups  xmm0, xmmword ptr [rax+20h]
0x18007849d  movups  xmmword ptr [rax-28h], xmm0
0x1800784a1  movsd   xmm1, qword ptr [rax+30h]
0x1800784a6  movsd   qword ptr [rax-18h], xmm1
0x1800784ab  mov     byte ptr [rax-45h], 0
0x1800784af  mov     rax, [rdi+0B8h]
0x1800784b6  mov     [rax-10h], rcx
0x1800784ba  lea     rcx, [rsp+88h+Event]
0x1800784bf  mov     [rax-8], rcx
0x1800784c3  mov     byte ptr [rax-45h], 0E0h
0x1800784c7  mov     rcx, [rbp+8]; TargetDevice
0x1800784cb  call    cs:__imp_IoDetachDevice
0x1800784d2  nop     dword ptr [rax+rax+00h]
0x1800784d7  mov     rcx, [rbp+8]; DeviceObject
0x1800784db  mov     rdx, rdi; Irp
0x1800784de  call    FltpCallDriver
0x1800784e3  cmp     eax, 103h
0x1800784e8  jnz     short loc_1800784F7
0x1800784ea  mov     rdx, rdi; Irp
0x1800784ed  lea     rcx, [rsp+88h+Event]; Object
0x1800784f2  call    FltpCancellableWaitForIo
0x1800784f7  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800784fe  jz      short loc_180078522
0x180078500  mov     eax, [rdi+30h]
0x180078503  mov     r9, rsi
0x180078506  movzx   ecx, word ptr [rbp+30h]
0x18007850a  mov     [rsp+88h+var_50], eax
0x18007850e  mov     rax, [rbp+38h]
0x180078512  shr     ecx, 1
0x180078514  mov     [rsp+88h+var_58], rax
0x180078519  mov     dword ptr [rsp+88h+var_60], ecx
0x18007851d  call    McTemplateU0sppwd_EtwWriteTransfer
0x180078522  mov     ecx, [rdi+30h]
0x180078525  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x18007852c  mov     r8d, 1E35h
0x180078532  xor     r9d, r9d
0x180078535  call    FltpDbgStatus
0x18007853a  test    eax, eax
0x18007853c  jns     short loc_180078560
0x18007853e  cmp     dword ptr [rdi+30h], 0C000010Eh
0x180078545  jz      short loc_180078560
0x180078547  mov     rdx, [rbp+8]; TargetDevice
0x18007854b  lea     r8, [rbp+8]; AttachedToDeviceObject
0x18007854f  mov     rcx, rsi; SourceDevice
0x180078552  call    cs:__imp_IoAttachDeviceToDeviceStackSafe
0x180078559  nop     dword ptr [rax+rax+00h]
0x18007855e  jmp     short loc_180078575
0x180078560  mov     edx, 8
0x180078565  mov     qword ptr [rbp+8], 0
0x18007856d  mov     rcx, rsi; DeviceObject
0x180078570  call    FltpCleanupDeviceObject
0x180078575  mov     ebx, [rdi+30h]
0x180078578  xor     edx, edx; PriorityBoost
0x18007857a  mov     rcx, rdi; Irp
0x18007857d  call    cs:__imp_IofCompleteRequest
0x180078584  nop     dword ptr [rax+rax+00h]
0x180078589  mov     eax, ebx
0x18007858b  add     rsp, 60h
0x18007858f  pop     r14
0x180078591  pop     rdi
0x180078592  pop     rsi
0x180078593  pop     rbp
0x180078594  pop     rbx
0x180078595  retn
```
