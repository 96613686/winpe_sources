# NpCreateDevice

- ea: `0x14001655c`
- end: `0x1400165ff`
- name: `NpCreateDevice`
- size: `163`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000bcc4`
- `0x140018080`

## callees

- `0x14000bdc8`
- `0x14001655c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016585`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016585`
- `ntoskrnl!IoCreateDevice` at `0x1400165bf`
- `ntoskrnl!IoCreateDevice` at `0x1400165bf`

## pseudocode

```c
NTSTATUS __fastcall NpCreateDevice(PDEVICE_OBJECT *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v3; // ebx
  struct _UNICODE_STRING DeviceName; // [rsp+40h] [rbp-18h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+68h] [rbp+10h] BYREF

  DeviceObject = 0;
  DeviceName = 0;
  RtlInitUnicodeString(&DeviceName, L"\\Device\\NamedPipe");
  result = IoCreateDevice(NpfsDriverObject, 0x1D8u, &DeviceName, 0x11u, 0x20000u, 0, &DeviceObject);
  v3 = result;
  if ( result >= 0 )
  {
    DeviceObject->Flags |= 0x200u;
    NpInitializeVcb(DeviceObject->DeviceExtension);
    *a1 = DeviceObject;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x14001655c  mov     rax, rsp
0x14001655f  mov     [rax+8], rbx
0x140016563  push    rdi
0x140016564  sub     rsp, 50h
0x140016568  mov     rdi, rcx
0x14001656b  mov     qword ptr [rax+10h], 0
0x140016573  xorps   xmm0, xmm0
0x140016576  lea     rcx, [rax-18h]; DestinationString
0x14001657a  lea     rdx, SourceString; "\\Device\\NamedPipe"
0x140016581  movups  xmmword ptr [rax-18h], xmm0
0x140016585  call    cs:__imp_RtlInitUnicodeString
0x14001658c  nop     dword ptr [rax+rax+00h]
0x140016591  mov     rcx, cs:NpfsDriverObject; DriverObject
0x140016598  lea     rax, [rsp+58h+arg_8]
0x14001659d  mov     [rsp+58h+DeviceObject], rax; DeviceObject
0x1400165a2  lea     r8, [rsp+58h+DeviceName]; DeviceName
0x1400165a7  mov     [rsp+58h+Exclusive], 0; Exclusive
0x1400165ac  mov     r9d, 11h; DeviceType
0x1400165b2  mov     edx, 1D8h; DeviceExtensionSize
0x1400165b7  mov     [rsp+58h+DeviceCharacteristics], 20000h; DeviceCharacteristics
0x1400165bf  call    cs:__imp_IoCreateDevice
0x1400165c6  nop     dword ptr [rax+rax+00h]
0x1400165cb  mov     ebx, eax
0x1400165cd  test    eax, eax
0x1400165cf  js      short loc_1400165F3
0x1400165d1  mov     rax, [rsp+58h+arg_8]
0x1400165d6  bts     dword ptr [rax+30h], 9
0x1400165db  mov     rcx, [rsp+58h+arg_8]
0x1400165e0  mov     rcx, [rcx+40h]
0x1400165e4  call    NpInitializeVcb
0x1400165e9  mov     rax, [rsp+58h+arg_8]
0x1400165ee  mov     [rdi], rax
0x1400165f1  mov     eax, ebx
0x1400165f3  mov     rbx, [rsp+58h+arg_0]
0x1400165f8  add     rsp, 50h
0x1400165fc  pop     rdi
0x1400165fd  retn
```
