# KsDefaultDispatchPnp

- ea: `0x180049460`
- end: `0x180049529`
- name: `KsDefaultDispatchPnp`
- size: `201`
- prototype: `DRIVER_DISPATCH`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800481d0`

## callees

- `0x180047f70`
- `0x180049460`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1800494d6`
- `ntoskrnl!IofCallDriver` at `0x1800494d6`
- `ntoskrnl!IoDetachDevice` at `0x1800494ed`
- `ntoskrnl!IoDetachDevice` at `0x1800494ed`
- `ntoskrnl!IoDeleteDevice` at `0x1800494fc`
- `ntoskrnl!IoDeleteDevice` at `0x1800494fc`

## pseudocode

```c
NTSTATUS __stdcall KsDefaultDispatchPnp(struct _DEVICE_OBJECT *DeviceObject, struct _IRP *Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  UCHAR MinorFunction; // si
  _QWORD *v6; // rcx
  struct _DEVICE_OBJECT *v7; // rdi
  NTSTATUS v8; // ebx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v6 = *(_QWORD **)CurrentStackLocation->DeviceObject->DeviceExtension;
  v7 = (struct _DEVICE_OBJECT *)v6[15];
  if ( !MinorFunction || CurrentStackLocation->MinorFunction == 1 )
    goto LABEL_13;
  if ( CurrentStackLocation->MinorFunction == 2 )
  {
    KsFreeDeviceHeader(v6);
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
LABEL_13:
    Irp->IoStatus.Status = 0;
    goto LABEL_9;
  }
  if ( CurrentStackLocation->MinorFunction == 3
    || CurrentStackLocation->MinorFunction == 4
    || CurrentStackLocation->MinorFunction == 5
    || CurrentStackLocation->MinorFunction == 6
    || CurrentStackLocation->MinorFunction == 23 )
  {
    goto LABEL_13;
  }
LABEL_9:
  ++Irp->CurrentLocation;
  Irp->Tail.Overlay.CurrentStackLocation = CurrentStackLocation + 1;
  v8 = IofCallDriver(v7, Irp);
  if ( MinorFunction == 2 )
  {
    IoDetachDevice(v7);
    IoDeleteDevice(DeviceObject);
  }
  return v8;
}

```

## disassembly

```asm
0x180049460  push    rbx
0x180049462  push    rbp
0x180049463  push    rsi
0x180049464  push    rdi
0x180049465  sub     rsp, 28h
0x180049469  mov     rbx, rdx
0x18004946c  mov     rbp, rcx
0x18004946f  mov     rdx, [rdx+0B8h]
0x180049476  movzx   esi, byte ptr [rdx+1]
0x18004947a  mov     rax, [rdx+28h]
0x18004947e  mov     r8, [rax+40h]
0x180049482  mov     rcx, [r8]; Header
0x180049485  mov     r8d, esi
0x180049488  mov     rdi, [rcx+78h]
0x18004948c  test    esi, esi
0x18004948e  jz      loc_180049520
0x180049494  sub     r8d, 1
0x180049498  jz      loc_180049520
0x18004949e  sub     r8d, 1
0x1800494a2  jz      short loc_180049514
0x1800494a4  sub     r8d, 1
0x1800494a8  jz      short loc_180049520
0x1800494aa  sub     r8d, 1
0x1800494ae  jz      short loc_180049520
0x1800494b0  sub     r8d, 1
0x1800494b4  jz      short loc_180049520
0x1800494b6  sub     r8d, 1
0x1800494ba  jz      short loc_180049520
0x1800494bc  cmp     r8d, 11h
0x1800494c0  jz      short loc_180049520
0x1800494c2  inc     byte ptr [rbx+43h]
0x1800494c5  lea     rax, [rdx+48h]
0x1800494c9  mov     rdx, rbx; Irp
0x1800494cc  mov     [rbx+0B8h], rax
0x1800494d3  mov     rcx, rdi; DeviceObject
0x1800494d6  call    cs:__imp_IofCallDriver
0x1800494dd  nop     dword ptr [rax+rax+00h]
0x1800494e2  mov     ebx, eax
0x1800494e4  cmp     sil, 2
0x1800494e8  jnz     short loc_180049508
0x1800494ea  mov     rcx, rdi; TargetDevice
0x1800494ed  call    cs:__imp_IoDetachDevice
0x1800494f4  nop     dword ptr [rax+rax+00h]
0x1800494f9  mov     rcx, rbp; DeviceObject
0x1800494fc  call    cs:__imp_IoDeleteDevice
0x180049503  nop     dword ptr [rax+rax+00h]
0x180049508  mov     eax, ebx
0x18004950a  add     rsp, 28h
0x18004950e  pop     rdi
0x18004950f  pop     rsi
0x180049510  pop     rbp
0x180049511  pop     rbx
0x180049512  retn
0x180049514  call    KsFreeDeviceHeader
0x180049519  mov     rdx, [rbx+0B8h]
0x180049520  mov     dword ptr [rbx+30h], 0
0x180049527  jmp     short loc_1800494C2
```
