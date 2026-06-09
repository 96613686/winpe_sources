# KoDriverInitialize

- ea: `0x180039cf0`
- end: `0x180039db4`
- name: `KoDriverInitialize`
- size: `196`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPathName, KoCreateObjectHandler CreateObjectHandler)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180039cf0`
- `0x180061fb0`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180039d1f`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180039d1f`

## pseudocode

```c
NTSTATUS __stdcall KoDriverInitialize(
        PDRIVER_OBJECT DriverObject,
        PUNICODE_STRING RegistryPathName,
        KoCreateObjectHandler CreateObjectHandler)
{
  int DriverObjectExtension; // edi
  PDRIVER_EXTENSION DriverExtension; // rcx
  KoCreateObjectHandler *v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  DriverObjectExtension = IoAllocateDriverObjectExtension(DriverObject, KoDriverInitialize, 8u, (PVOID *)&v8);
  if ( DriverObjectExtension >= 0 )
  {
    *v8 = CreateObjectHandler;
    DriverExtension = DriverObject->DriverExtension;
    DriverObject->MajorFunction[27] = KsDefaultDispatchPnp;
    DriverObject->MajorFunction[22] = KsDefaultDispatchPower;
    DriverObject->MajorFunction[23] = KsDefaultForwardIrp;
    DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)PnpAddDevice;
    DriverObject->DriverUnload = KsNullDriverUnload;
    KsSetMajorFunctionHandler(DriverObject, 0);
    KsSetMajorFunctionHandler(DriverObject, 2u);
    KsSetMajorFunctionHandler(DriverObject, 0xEu);
  }
  return DriverObjectExtension;
}

```

## disassembly

```asm
0x180039cf0  mov     rax, rsp
0x180039cf3  mov     [rax+8], rbx
0x180039cf7  mov     [rax+10h], rsi
0x180039cfb  push    rdi
0x180039cfc  sub     rsp, 20h
0x180039d00  mov     rsi, r8
0x180039d03  mov     qword ptr [rax+20h], 0
0x180039d0b  mov     r8d, 8; DriverObjectExtensionSize
0x180039d11  lea     r9, [rax+20h]; DriverObjectExtension
0x180039d15  lea     rdx, KoDriverInitialize; ClientIdentificationAddress
0x180039d1c  mov     rbx, rcx
0x180039d1f  call    cs:__imp_IoAllocateDriverObjectExtension
0x180039d26  nop     dword ptr [rax+rax+00h]
0x180039d2b  mov     edi, eax
0x180039d2d  test    eax, eax
0x180039d2f  js      short loc_180039DA1
0x180039d31  mov     rdx, [rsp+28h+arg_18]
0x180039d36  lea     rax, KsDefaultDispatchPnp
0x180039d3d  mov     [rdx], rsi
0x180039d40  xor     edx, edx; MajorFunction
0x180039d42  mov     rcx, [rbx+30h]
0x180039d46  mov     [rbx+148h], rax
0x180039d4d  lea     rax, KsDefaultDispatchPower
0x180039d54  mov     [rbx+120h], rax
0x180039d5b  lea     rax, KsDefaultForwardIrp
0x180039d62  mov     [rbx+128h], rax
0x180039d69  lea     rax, PnpAddDevice
0x180039d70  mov     [rcx+8], rax
0x180039d74  lea     rax, KsNullDriverUnload
0x180039d7b  mov     rcx, rbx; DriverObject
0x180039d7e  mov     [rbx+68h], rax
0x180039d82  call    KsSetMajorFunctionHandler
0x180039d87  mov     edx, 2; MajorFunction
0x180039d8c  mov     rcx, rbx; DriverObject
0x180039d8f  call    KsSetMajorFunctionHandler
0x180039d94  mov     edx, 0Eh; MajorFunction
0x180039d99  mov     rcx, rbx; DriverObject
0x180039d9c  call    KsSetMajorFunctionHandler
0x180039da1  mov     rbx, [rsp+28h+arg_0]
0x180039da6  mov     eax, edi
0x180039da8  mov     rsi, [rsp+28h+arg_8]
0x180039dad  add     rsp, 20h
0x180039db1  pop     rdi
0x180039db2  retn
```
