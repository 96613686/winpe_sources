# HidpSetRegistryValue

- ea: `0x18001e490`
- end: `0x18001e530`
- name: `HidpSetRegistryValue`
- size: `160`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003a590`

## callees

- `0x18001e490`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x18001e503`
- `ntoskrnl!ZwSetValueKey` at `0x18001e503`
- `ntoskrnl!ZwClose` at `0x18001e516`
- `ntoskrnl!ZwClose` at `0x18001e516`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18001e4d4`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x18001e4d4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001e4b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001e4b5`

## pseudocode

```c
__int64 __fastcall HidpSetRegistryValue(PDEVICE_OBJECT DeviceObject, const WCHAR *a2, __int64 a3, void *a4)
{
  NTSTATUS v6; // ebx
  void *DeviceRegKey; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-20h] BYREF

  DeviceRegKey = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v6 = IoOpenDeviceRegistryKey(DeviceObject, 1u, 0x1F0000u, &DeviceRegKey);
  if ( v6 >= 0 )
  {
    v6 = ZwSetValueKey(DeviceRegKey, &ValueName, 0, 4u, a4, 4u);
    ZwClose(DeviceRegKey);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e490  mov     rax, rsp
0x18001e493  mov     [rax+8], rbx
0x18001e497  push    rdi
0x18001e498  sub     rsp, 50h
0x18001e49c  mov     rbx, rcx
0x18001e49f  mov     qword ptr [rax-28h], 0
0x18001e4a7  xorps   xmm0, xmm0
0x18001e4aa  lea     rcx, [rax-20h]; DestinationString
0x18001e4ae  movups  xmmword ptr [rax-20h], xmm0
0x18001e4b2  mov     rdi, r9
0x18001e4b5  call    cs:__imp_RtlInitUnicodeString
0x18001e4bc  nop     dword ptr [rax+rax+00h]
0x18001e4c1  lea     r9, [rsp+58h+DeviceRegKey]; DeviceRegKey
0x18001e4c6  mov     edx, 1; DevInstKeyType
0x18001e4cb  mov     r8d, 1F0000h; DesiredAccess
0x18001e4d1  mov     rcx, rbx; DeviceObject
0x18001e4d4  call    cs:__imp_IoOpenDeviceRegistryKey
0x18001e4db  nop     dword ptr [rax+rax+00h]
0x18001e4e0  mov     ebx, eax
0x18001e4e2  test    eax, eax
0x18001e4e4  js      short loc_18001E522
0x18001e4e6  mov     rcx, [rsp+58h+DeviceRegKey]; KeyHandle
0x18001e4eb  lea     rdx, [rsp+58h+ValueName]; ValueName
0x18001e4f0  mov     r9d, 4; Type
0x18001e4f6  xor     r8d, r8d; TitleIndex
0x18001e4f9  mov     [rsp+58h+DataSize], r9d; DataSize
0x18001e4fe  mov     [rsp+58h+Data], rdi; Data
0x18001e503  call    cs:__imp_ZwSetValueKey
0x18001e50a  nop     dword ptr [rax+rax+00h]
0x18001e50f  mov     rcx, [rsp+58h+DeviceRegKey]; Handle
0x18001e514  mov     ebx, eax
0x18001e516  call    cs:__imp_ZwClose
0x18001e51d  nop     dword ptr [rax+rax+00h]
0x18001e522  mov     eax, ebx
0x18001e524  mov     rbx, [rsp+58h+arg_0]
0x18001e529  add     rsp, 50h
0x18001e52d  pop     rdi
0x18001e52e  retn
```
