# NsippDeleteDevice

- ea: `0x140005bb8`
- end: `0x140005c36`
- name: `NsippDeleteDevice`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000d180`

## callees

- `0x140005bb8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140005bd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005bd0`
- `ntoskrnl!IoDeleteDevice` at `0x140005bf4`
- `ntoskrnl!IoDeleteDevice` at `0x140005bf4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140005be1`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140005be1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c19`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005c19`

## pseudocode

```c
void NsippDeleteDevice()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\??\\Nsi");
  IoDeleteSymbolicLink(&DestinationString);
  IoDeleteDevice(NsiProxyDeviceObject);
  NsiProxyDeviceObject = 0;
  if ( NsiServiceSecurityDescriptor )
    ExFreePoolWithTag(NsiServiceSecurityDescriptor, 0);
  NsiServiceSecurityDescriptor = 0;
}

```

## disassembly

```asm
0x140005bb8  sub     rsp, 38h
0x140005bbc  xorps   xmm0, xmm0
0x140005bbf  lea     rdx, aNsi; "\\??\\Nsi"
0x140005bc6  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140005bcb  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140005bd0  call    cs:__imp_RtlInitUnicodeString
0x140005bd7  nop     dword ptr [rax+rax+00h]
0x140005bdc  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x140005be1  call    cs:__imp_IoDeleteSymbolicLink
0x140005be8  nop     dword ptr [rax+rax+00h]
0x140005bed  mov     rcx, cs:NsiProxyDeviceObject; DeviceObject
0x140005bf4  call    cs:__imp_IoDeleteDevice
0x140005bfb  nop     dword ptr [rax+rax+00h]
0x140005c00  mov     rcx, cs:NsiServiceSecurityDescriptor; P
0x140005c07  mov     cs:NsiProxyDeviceObject, 0
0x140005c12  test    rcx, rcx
0x140005c15  jz      short loc_140005C25
0x140005c17  xor     edx, edx; Tag
0x140005c19  call    cs:__imp_ExFreePoolWithTag
0x140005c20  nop     dword ptr [rax+rax+00h]
0x140005c25  mov     cs:NsiServiceSecurityDescriptor, 0
0x140005c30  add     rsp, 38h
0x140005c34  retn
```
