# KsForwardIrp

- ea: `0x180034790`
- end: `0x180034837`
- name: `KsForwardIrp`
- size: `167`
- prototype: `NTSTATUS __stdcall(PIRP Irp, PFILE_OBJECT FileObject, BOOLEAN ReuseStackLocation)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180034790`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1800347c9`
- `ntoskrnl!IofCallDriver` at `0x1800347c9`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800347b7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1800347b7`
- `ntoskrnl!IofCompleteRequest` at `0x18003481f`
- `ntoskrnl!IofCompleteRequest` at `0x18003481f`

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
0x180034790  push    rbx
0x180034792  sub     rsp, 20h
0x180034796  mov     rbx, rcx
0x180034799  test    r8b, r8b
0x18003479c  jz      short loc_1800347D7
0x18003479e  mov     rax, [rcx+0B8h]
0x1800347a5  mov     [rax+30h], rdx
0x1800347a9  inc     byte ptr [rcx+43h]
0x1800347ac  add     qword ptr [rcx+0B8h], 48h ; 'H'
0x1800347b4  mov     rcx, rdx; FileObject
0x1800347b7  call    cs:__imp_IoGetRelatedDeviceObject
0x1800347be  nop     dword ptr [rax+rax+00h]
0x1800347c3  mov     rcx, rax; DeviceObject
0x1800347c6  mov     rdx, rbx; Irp
0x1800347c9  call    cs:__imp_IofCallDriver
0x1800347d0  nop     dword ptr [rax+rax+00h]
0x1800347d5  jmp     short loc_180034830
0x1800347d7  cmp     byte ptr [rcx+43h], 1
0x1800347db  jle     short loc_180034816
0x1800347dd  mov     rax, [rcx+0B8h]
0x1800347e4  movups  xmm0, xmmword ptr [rax]
0x1800347e7  movups  xmmword ptr [rax-48h], xmm0
0x1800347eb  movups  xmm1, xmmword ptr [rax+10h]
0x1800347ef  movups  xmmword ptr [rax-38h], xmm1
0x1800347f3  movups  xmm0, xmmword ptr [rax+20h]
0x1800347f7  movups  xmmword ptr [rax-28h], xmm0
0x1800347fb  movsd   xmm1, qword ptr [rax+30h]
0x180034800  movsd   qword ptr [rax-18h], xmm1
0x180034805  mov     byte ptr [rax-45h], 0
0x180034809  mov     rax, [rcx+0B8h]
0x180034810  mov     [rax-18h], rdx
0x180034814  jmp     short loc_1800347B4
0x180034816  xor     edx, edx; PriorityBoost
0x180034818  mov     dword ptr [rcx+30h], 0C0000010h
0x18003481f  call    cs:__imp_IofCompleteRequest
0x180034826  nop     dword ptr [rax+rax+00h]
0x18003482b  mov     eax, 0C0000010h
0x180034830  add     rsp, 20h
0x180034834  pop     rbx
0x180034835  retn
```
