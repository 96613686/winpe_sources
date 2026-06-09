# CKernelFilterDevice::~CKernelFilterDevice(void)

- ea: `0x14000a2ec`
- end: `0x14000a310`
- name: `??1CKernelFilterDevice@@UEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CKernelFilterDevice *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001260`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000a2fe`
- `ntoskrnl!IoDeleteDevice` at `0x14000a2fe`

## pseudocode

```c
void __fastcall CKernelFilterDevice::~CKernelFilterDevice(PDEVICE_OBJECT *this)
{
  *this = (PDEVICE_OBJECT)&CKernelFilterDevice::`vftable';
  IoDeleteDevice(this[5]);
}

```

## disassembly

```asm
0x14000a2ec  sub     rsp, 28h
0x14000a2f0  lea     rax, ??_7CKernelFilterDevice@@6B@; const CKernelFilterDevice::`vftable'
0x14000a2f7  mov     [rcx], rax
0x14000a2fa  mov     rcx, [rcx+28h]; DeviceObject
0x14000a2fe  call    cs:__imp_IoDeleteDevice
0x14000a305  nop     dword ptr [rax+rax+00h]
0x14000a30a  add     rsp, 28h
0x14000a30e  retn
```
