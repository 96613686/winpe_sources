# PmFilterInternalDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14000bb00`
- end: `0x14000bbda`
- name: `?PmFilterInternalDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b07c`
- `0x14000bb00`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000bb83`
- `ntoskrnl!IofCallDriver` at `0x14000bb83`
- `ntoskrnl!IofCompleteRequest` at `0x14000bb59`
- `ntoskrnl!IofCompleteRequest` at `0x14000bba5`
- `ntoskrnl!IofCompleteRequest` at `0x14000bb59`
- `ntoskrnl!IofCompleteRequest` at `0x14000bba5`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000bb3f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000bb3f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000bbbe`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000bbbe`

## pseudocode

```c
__int64 __fastcall PmFilterInternalDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  int v6; // eax
  unsigned int v7; // edi
  NTSTATUS Partitions; // eax

  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, File, 1u, 0x20u);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 7356816 )
    {
      Partitions = PmInternalIoctlQueryPartitions(a1, a2);
      a2->IoStatus.Status = Partitions;
      v7 = Partitions;
      IofCompleteRequest(a2, 0);
    }
    else
    {
      ++a2->CurrentLocation;
      ++a2->Tail.Overlay.CurrentStackLocation;
      v7 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
    }
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 120), a2, 0x20u);
  }
  else
  {
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x14000bb00  push    rbx
0x14000bb02  push    rbp
0x14000bb03  push    rsi
0x14000bb04  push    rdi
0x14000bb05  push    r14
0x14000bb07  push    r15
0x14000bb09  sub     rsp, 38h
0x14000bb0d  mov     r14, [rcx+40h]
0x14000bb11  lea     r8, File; File
0x14000bb18  mov     r15, [rdx+0B8h]
0x14000bb1f  mov     rbp, rcx
0x14000bb22  mov     r9d, 1; Line
0x14000bb28  mov     qword ptr [rdx+38h], 0
0x14000bb30  mov     rbx, rdx
0x14000bb33  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000bb3b  lea     rcx, [r14+78h]; RemoveLock
0x14000bb3f  call    cs:__imp_IoAcquireRemoveLockEx
0x14000bb46  nop     dword ptr [rax+rax+00h]
0x14000bb4b  mov     edi, eax
0x14000bb4d  test    eax, eax
0x14000bb4f  jns     short loc_14000BB67
0x14000bb51  xor     edx, edx; PriorityBoost
0x14000bb53  mov     [rbx+30h], eax
0x14000bb56  mov     rcx, rbx; Irp
0x14000bb59  call    cs:__imp_IofCompleteRequest
0x14000bb60  nop     dword ptr [rax+rax+00h]
0x14000bb65  jmp     short loc_14000BBCA
0x14000bb67  cmp     dword ptr [r15+18h], 704190h
0x14000bb6f  mov     rdx, rbx; struct _IRP *
0x14000bb72  jz      short loc_14000BB93
0x14000bb74  inc     byte ptr [rbx+43h]
0x14000bb77  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000bb7f  mov     rcx, [r14+10h]; DeviceObject
0x14000bb83  call    cs:__imp_IofCallDriver
0x14000bb8a  nop     dword ptr [rax+rax+00h]
0x14000bb8f  mov     edi, eax
0x14000bb91  jmp     short loc_14000BBB1
0x14000bb93  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x14000bb96  call    ?PmInternalIoctlQueryPartitions@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PmInternalIoctlQueryPartitions(_DEVICE_OBJECT *,_IRP *)
0x14000bb9b  xor     edx, edx; PriorityBoost
0x14000bb9d  mov     [rbx+30h], eax
0x14000bba0  mov     rcx, rbx; Irp
0x14000bba3  mov     edi, eax
0x14000bba5  call    cs:__imp_IofCompleteRequest
0x14000bbac  nop     dword ptr [rax+rax+00h]
0x14000bbb1  mov     r8d, 20h ; ' '; RemlockSize
0x14000bbb7  lea     rcx, [r14+78h]; RemoveLock
0x14000bbbb  mov     rdx, rbx; Tag
0x14000bbbe  call    cs:__imp_IoReleaseRemoveLockEx
0x14000bbc5  nop     dword ptr [rax+rax+00h]
0x14000bbca  mov     eax, edi
0x14000bbcc  add     rsp, 38h
0x14000bbd0  pop     r15
0x14000bbd2  pop     r14
0x14000bbd4  pop     rdi
0x14000bbd5  pop     rsi
0x14000bbd6  pop     rbp
0x14000bbd7  pop     rbx
0x14000bbd8  retn
```
