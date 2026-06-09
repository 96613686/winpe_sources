# KoDriverInitialize

- ea: `0x180039d40`
- end: `0x180039e04`
- name: `KoDriverInitialize`
- size: `196`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPathName, KoCreateObjectHandler CreateObjectHandler)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180039d40`
- `0x180062150`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180039d6f`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x180039d6f`

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
0x180039d40  mov     rax, rsp
0x180039d43  mov     [rax+8], rbx
0x180039d47  mov     [rax+10h], rsi
0x180039d4b  push    rdi
0x180039d4c  sub     rsp, 20h
0x180039d50  mov     rsi, r8
0x180039d53  mov     qword ptr [rax+20h], 0
0x180039d5b  mov     r8d, 8; DriverObjectExtensionSize
0x180039d61  lea     r9, [rax+20h]; DriverObjectExtension
0x180039d65  lea     rdx, KoDriverInitialize; ClientIdentificationAddress
0x180039d6c  mov     rbx, rcx
0x180039d6f  call    cs:__imp_IoAllocateDriverObjectExtension
0x180039d76  nop     dword ptr [rax+rax+00h]
0x180039d7b  mov     edi, eax
0x180039d7d  test    eax, eax
0x180039d7f  js      short loc_180039DF1
0x180039d81  mov     rdx, [rsp+28h+arg_18]
0x180039d86  lea     rax, KsDefaultDispatchPnp
0x180039d8d  mov     [rdx], rsi
0x180039d90  xor     edx, edx; MajorFunction
0x180039d92  mov     rcx, [rbx+30h]
0x180039d96  mov     [rbx+148h], rax
0x180039d9d  lea     rax, KsDefaultDispatchPower
0x180039da4  mov     [rbx+120h], rax
0x180039dab  lea     rax, KsDefaultForwardIrp
0x180039db2  mov     [rbx+128h], rax
0x180039db9  lea     rax, PnpAddDevice
0x180039dc0  mov     [rcx+8], rax
0x180039dc4  lea     rax, KsNullDriverUnload
0x180039dcb  mov     rcx, rbx; DriverObject
0x180039dce  mov     [rbx+68h], rax
0x180039dd2  call    KsSetMajorFunctionHandler
0x180039dd7  mov     edx, 2; MajorFunction
0x180039ddc  mov     rcx, rbx; DriverObject
0x180039ddf  call    KsSetMajorFunctionHandler
0x180039de4  mov     edx, 0Eh; MajorFunction
0x180039de9  mov     rcx, rbx; DriverObject
0x180039dec  call    KsSetMajorFunctionHandler
0x180039df1  mov     rbx, [rsp+28h+arg_0]
0x180039df6  mov     eax, edi
0x180039df8  mov     rsi, [rsp+28h+arg_8]
0x180039dfd  add     rsp, 20h
0x180039e01  pop     rdi
0x180039e02  retn
```
