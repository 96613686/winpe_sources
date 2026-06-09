# HidpToggleSelSuspWorker

- ea: `0x180038390`
- end: `0x180038455`
- name: `HidpToggleSelSuspWorker`
- size: `197`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c1e4`

## callees

- `0x180038390`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x180038422`
- `ntoskrnl!ZwSetValueKey` at `0x180038422`
- `ntoskrnl!ZwClose` at `0x180038433`
- `ntoskrnl!ZwClose` at `0x180038433`
- `ntoskrnl!IoFreeWorkItem` at `0x180038442`
- `ntoskrnl!IoFreeWorkItem` at `0x180038442`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800383d8`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1800383d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800383f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800383f4`

## pseudocode

```c
void __fastcall HidpToggleSelSuspWorker(PDEVICE_OBJECT DeviceObject, struct _IO_WORKITEM *Context)
{
  PDEVICE_OBJECT *DeviceExtension; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  int Data; // [rsp+50h] [rbp+8h] BYREF
  void *DeviceRegKey; // [rsp+58h] [rbp+10h] BYREF

  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  Data = 0;
  DestinationString = 0;
  DeviceRegKey = 0;
  Data = (*((_DWORD *)DeviceExtension + 447) >> 3) & 1;
  if ( IoOpenDeviceRegistryKey(*DeviceExtension, 1u, 0x1F0000u, &DeviceRegKey) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"SelectiveSuspendOn");
    ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, &Data, 4u);
    ZwClose(DeviceRegKey);
  }
  IoFreeWorkItem(Context);
}

```

## disassembly

```asm
0x180038390  push    rbx
0x180038392  sub     rsp, 40h
0x180038396  mov     rcx, [rcx+40h]
0x18003839a  lea     r9, [rsp+48h+DeviceRegKey]; DeviceRegKey
0x18003839f  mov     [rsp+48h+arg_0], 0
0x1800383a7  xorps   xmm0, xmm0
0x1800383aa  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800383af  mov     [rsp+48h+DeviceRegKey], 0
0x1800383b8  mov     rbx, rdx
0x1800383bb  mov     eax, [rcx+6FCh]
0x1800383c1  mov     edx, 1; DevInstKeyType
0x1800383c6  shr     eax, 3
0x1800383c9  mov     r8d, 1F0000h; DesiredAccess
0x1800383cf  and     eax, edx
0x1800383d1  mov     [rsp+48h+arg_0], eax
0x1800383d5  mov     rcx, [rcx]; DeviceObject
0x1800383d8  call    cs:__imp_IoOpenDeviceRegistryKey
0x1800383df  nop     dword ptr [rax+rax+00h]
0x1800383e4  test    eax, eax
0x1800383e6  js      short loc_18003843F
0x1800383e8  lea     rdx, aSelectivesuspe_0; "SelectiveSuspendOn"
0x1800383ef  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800383f4  call    cs:__imp_RtlInitUnicodeString
0x1800383fb  nop     dword ptr [rax+rax+00h]
0x180038400  mov     rcx, [rsp+48h+DeviceRegKey]; KeyHandle
0x180038405  lea     rax, [rsp+48h+arg_0]
0x18003840a  mov     r9d, 4; Type
0x180038410  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x180038415  mov     [rsp+48h+DataSize], r9d; DataSize
0x18003841a  xor     r8d, r8d; TitleIndex
0x18003841d  mov     [rsp+48h+Data], rax; Data
0x180038422  call    cs:__imp_ZwSetValueKey
0x180038429  nop     dword ptr [rax+rax+00h]
0x18003842e  mov     rcx, [rsp+48h+DeviceRegKey]; Handle
0x180038433  call    cs:__imp_ZwClose
0x18003843a  nop     dword ptr [rax+rax+00h]
0x18003843f  mov     rcx, rbx; IoWorkItem
0x180038442  call    cs:__imp_IoFreeWorkItem
0x180038449  nop     dword ptr [rax+rax+00h]
0x18003844e  add     rsp, 40h
0x180038452  pop     rbx
0x180038453  retn
```
