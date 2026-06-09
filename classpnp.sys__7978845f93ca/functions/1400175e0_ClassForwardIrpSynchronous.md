# ClassForwardIrpSynchronous

- ea: `0x1400175e0`
- end: `0x14001761f`
- name: `ClassForwardIrpSynchronous`
- size: `63`
- prototype: `NTSTATUS __stdcall(PCOMMON_DEVICE_EXTENSION CommonExtension, PIRP Irp)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013000`
- `0x140014418`
- `0x14001e86c`
- `0x14001ecc0`
- `0x140030338`
- `0x14005fe50`

## callees

- `0x140017630`

## pseudocode

```c
NTSTATUS __stdcall ClassForwardIrpSynchronous(PCOMMON_DEVICE_EXTENSION CommonExtension, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  return ClassSendIrpSynchronous(CommonExtension->LowerDeviceObject, Irp);
}

```

## disassembly

```asm
0x1400175e0  sub     rsp, 28h
0x1400175e4  mov     rax, [rdx+0B8h]
0x1400175eb  movups  xmm0, xmmword ptr [rax]
0x1400175ee  movups  xmmword ptr [rax-48h], xmm0
0x1400175f2  movups  xmm1, xmmword ptr [rax+10h]
0x1400175f6  movups  xmmword ptr [rax-38h], xmm1
0x1400175fa  movups  xmm0, xmmword ptr [rax+20h]
0x1400175fe  movups  xmmword ptr [rax-28h], xmm0
0x140017602  movsd   xmm1, qword ptr [rax+30h]
0x140017607  movsd   qword ptr [rax-18h], xmm1
0x14001760c  mov     byte ptr [rax-45h], 0
0x140017610  mov     rcx, [rcx+10h]; TargetDeviceObject
0x140017614  call    ClassSendIrpSynchronous
0x140017619  add     rsp, 28h
0x14001761d  retn
```
