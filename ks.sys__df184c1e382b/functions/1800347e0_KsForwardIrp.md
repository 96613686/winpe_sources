# KsForwardIrp

- ea: `0x1800347e0`
- end: `0x180034887`
- name: `KsForwardIrp`
- size: `167`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PFILE_OBJECT FileObject, BOOLEAN ReuseStackLocation)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800347e0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x180034819`
- `ntoskrnl!IofCallDriver` at `0x180034819`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180034807`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180034807`
- `ntoskrnl!IofCompleteRequest` at `0x18003486f`
- `ntoskrnl!IofCompleteRequest` at `0x18003486f`

## pseudocode

```c
NTSTATUS __stdcall KsForwardIrp(PIRP Irp, PFILE_OBJECT FileObject, BOOLEAN ReuseStackLocation)
{
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  if ( ReuseStackLocation )
  {
    Irp->Tail.Overlay.CurrentStackLocation->FileObject = FileObject;
    ++Irp->CurrentLocation;
    ++Irp->Tail.Overlay.CurrentStackLocation;
LABEL_3:
    RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
    return IofCallDriver(RelatedDeviceObject, Irp);
  }
  if ( Irp->CurrentLocation > 1 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    Irp->Tail.Overlay.CurrentStackLocation[-1].FileObject = FileObject;
    goto LABEL_3;
  }
  Irp->IoStatus.Status = -1073741808;
  IofCompleteRequest(Irp, 0);
  return -1073741808;
}

```

## disassembly

```asm
0x1800347e0  push    rbx
0x1800347e2  sub     rsp, 20h
0x1800347e6  mov     rbx, rcx
0x1800347e9  test    r8b, r8b
0x1800347ec  jz      short loc_180034827
0x1800347ee  mov     rax, [rcx+0B8h]
0x1800347f5  mov     [rax+30h], rdx
0x1800347f9  inc     byte ptr [rcx+43h]
0x1800347fc  add     qword ptr [rcx+0B8h], 48h ; 'H'
0x180034804  mov     rcx, rdx; FileObject
0x180034807  call    cs:__imp_IoGetRelatedDeviceObject
0x18003480e  nop     dword ptr [rax+rax+00h]
0x180034813  mov     rcx, rax; DeviceObject
0x180034816  mov     rdx, rbx; Irp
0x180034819  call    cs:__imp_IofCallDriver
0x180034820  nop     dword ptr [rax+rax+00h]
0x180034825  jmp     short loc_180034880
0x180034827  cmp     byte ptr [rcx+43h], 1
0x18003482b  jle     short loc_180034866
0x18003482d  mov     rax, [rcx+0B8h]
0x180034834  movups  xmm0, xmmword ptr [rax]
0x180034837  movups  xmmword ptr [rax-48h], xmm0
0x18003483b  movups  xmm1, xmmword ptr [rax+10h]
0x18003483f  movups  xmmword ptr [rax-38h], xmm1
0x180034843  movups  xmm0, xmmword ptr [rax+20h]
0x180034847  movups  xmmword ptr [rax-28h], xmm0
0x18003484b  movsd   xmm1, qword ptr [rax+30h]
0x180034850  movsd   qword ptr [rax-18h], xmm1
0x180034855  mov     byte ptr [rax-45h], 0
0x180034859  mov     rax, [rcx+0B8h]
0x180034860  mov     [rax-18h], rdx
0x180034864  jmp     short loc_180034804
0x180034866  xor     edx, edx; PriorityBoost
0x180034868  mov     dword ptr [rcx+30h], 0C0000010h
0x18003486f  call    cs:__imp_IofCompleteRequest
0x180034876  nop     dword ptr [rax+rax+00h]
0x18003487b  mov     eax, 0C0000010h
0x180034880  add     rsp, 20h
0x180034884  pop     rbx
0x180034885  retn
```
