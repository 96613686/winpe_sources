# ClassGetDriverExtension

- ea: `0x140022fe0`
- end: `0x140022ffd`
- name: `ClassGetDriverExtension`
- size: `29`
- prototype: `PCLASS_DRIVER_EXTENSION __stdcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400543e0`
- `0x140058974`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140022feb`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140022feb`

## pseudocode

```c
PCLASS_DRIVER_EXTENSION __stdcall ClassGetDriverExtension(PDRIVER_OBJECT DriverObject)
{
  return (PCLASS_DRIVER_EXTENSION)IoGetDriverObjectExtension(DriverObject, ClassInitialize);
}

```

## disassembly

```asm
0x140022fe0  sub     rsp, 28h
0x140022fe4  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140022feb  call    cs:__imp_IoGetDriverObjectExtension
0x140022ff2  nop     dword ptr [rax+rax+00h]
0x140022ff7  add     rsp, 28h
0x140022ffb  retn
```
