# CKernelFilterDriver::Initialize(void)

- ea: `0x14000a254`
- end: `0x14000a2e3`
- name: `?Initialize@CKernelFilterDriver@@QEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(CKernelFilterDriver *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x14000d078`

## callees

- `0x14000a254`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14000a283`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x14000a283`

## pseudocode

```c
__int64 __fastcall CKernelFilterDriver::Initialize(PDRIVER_OBJECT *this)
{
  NTSTATUS v2; // r8d
  __int64 v3; // rdx
  PVOID DriverObjectExtension; // [rsp+30h] [rbp+8h] BYREF

  DriverObjectExtension = 0;
  v2 = IoAllocateDriverObjectExtension(this[1], CKernelFilterDriver::AddDevice, 8u, &DriverObjectExtension);
  if ( v2 >= 0 )
  {
    v3 = 0;
    *(_QWORD *)DriverObjectExtension = this;
    do
      this[1]->MajorFunction[v3++] = (PDRIVER_DISPATCH)CKernelFilterDevice::DispatchIrpBridge;
    while ( v3 != 28 );
    this[1]->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)CKernelFilterDriver::AddDevice;
    this[1]->DriverUnload = (PDRIVER_UNLOAD)CKernelFilterDriver::DriverUnload;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000a254  mov     [rsp+arg_8], rbx
0x14000a259  push    rdi
0x14000a25a  sub     rsp, 20h
0x14000a25e  mov     rbx, rcx
0x14000a261  mov     [rsp+28h+DriverObjectExtension], 0
0x14000a26a  mov     rcx, [rcx+8]; DriverObject
0x14000a26e  lea     rdi, ?AddDevice@CKernelFilterDriver@@CAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; CKernelFilterDriver::AddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x14000a275  mov     rdx, rdi; ClientIdentificationAddress
0x14000a278  lea     r9, [rsp+28h+DriverObjectExtension]; DriverObjectExtension
0x14000a27d  mov     r8d, 8; DriverObjectExtensionSize
0x14000a283  call    cs:__imp_IoAllocateDriverObjectExtension
0x14000a28a  nop     dword ptr [rax+rax+00h]
0x14000a28f  mov     r8d, eax
0x14000a292  test    eax, eax
0x14000a294  js      short loc_14000A2D4
0x14000a296  mov     rcx, [rsp+28h+DriverObjectExtension]
0x14000a29b  xor     edx, edx
0x14000a29d  mov     [rcx], rbx
0x14000a2a0  mov     rcx, [rbx+8]
0x14000a2a4  lea     rax, ?DispatchIrpBridge@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKernelFilterDevice::DispatchIrpBridge(_DEVICE_OBJECT *,_IRP *)
0x14000a2ab  mov     [rcx+rdx*8+70h], rax
0x14000a2b0  inc     rdx
0x14000a2b3  cmp     rdx, 1Ch
0x14000a2b7  jnz     short loc_14000A2A0
0x14000a2b9  mov     rax, [rbx+8]
0x14000a2bd  mov     rcx, [rax+30h]
0x14000a2c1  mov     [rcx+8], rdi
0x14000a2c5  lea     rcx, ?DriverUnload@CKernelFilterDriver@@CAXPEAU_DRIVER_OBJECT@@@Z; CKernelFilterDriver::DriverUnload(_DRIVER_OBJECT *)
0x14000a2cc  mov     rax, [rbx+8]
0x14000a2d0  mov     [rax+68h], rcx
0x14000a2d4  mov     rbx, [rsp+28h+arg_8]
0x14000a2d9  mov     eax, r8d
0x14000a2dc  add     rsp, 20h
0x14000a2e0  pop     rdi
0x14000a2e1  retn
```
