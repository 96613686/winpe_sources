# SetPortDescrToDisabled

- ea: `0x14001b8d0`
- end: `0x14001ba0a`
- name: `SetPortDescrToDisabled`
- size: `314`
- prototype: `__int64 __fastcall(PUNICODE_STRING SymbolicLinkName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x14000268c`

## callees

- `0x14000327c`
- `0x1400035a0`
- `0x14001b8d0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001b974`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001b974`
- `ntoskrnl!ZwClose` at `0x14001b9f0`
- `ntoskrnl!ZwClose` at `0x14001b9f0`
- `ntoskrnl!ZwSetValueKey` at `0x14001b9a9`
- `ntoskrnl!ZwSetValueKey` at `0x14001b9a9`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x14001b92c`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x14001b92c`

## pseudocode

```c
__int64 __fastcall SetPortDescrToDisabled(PUNICODE_STRING SymbolicLinkName)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  void *DeviceInterfaceRegKey; // [rsp+58h] [rbp+10h] BYREF

  DeviceInterfaceRegKey = (void *)-1LL;
  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids, SymbolicLinkName);
  v2 = IoOpenDeviceInterfaceRegistryKey(SymbolicLinkName, 0xF003Fu, &DeviceInterfaceRegKey);
  v3 = v2;
  if ( v2 < 0 )
  {
    DeviceInterfaceRegKey = (void *)-1LL;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return v3;
    v5 = 34;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"Port Description");
  v2 = ZwSetValueKey(
         DeviceInterfaceRegKey,
         &DestinationString,
         0,
         1u,
         &DisabledPortDescription,
         *(ULONG *)&WPP_MAIN_CB.DeviceQueue.Busy);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v5 = 35;
LABEL_12:
      WPP_SF_d(v4->AttachedDevice, v5, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids, (unsigned int)v2);
    }
  }
  if ( DeviceInterfaceRegKey != (void *)-1LL )
    ZwClose(DeviceInterfaceRegKey);
  return v3;
}

```

## disassembly

```asm
0x14001b8d0  mov     [rsp+arg_0], rbx
0x14001b8d5  push    rdi
0x14001b8d6  sub     rsp, 40h
0x14001b8da  xorps   xmm0, xmm0
0x14001b8dd  mov     [rsp+48h+DeviceInterfaceRegKey], 0FFFFFFFFFFFFFFFFh
0x14001b8e6  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001b8eb  mov     rbx, rcx
0x14001b8ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8f5  lea     rdi, WPP_GLOBAL_Control
0x14001b8fc  cmp     rcx, rdi
0x14001b8ff  jz      short loc_14001B91F
0x14001b901  cmp     byte ptr [rcx+29h], 4
0x14001b905  jb      short loc_14001B91F
0x14001b907  mov     rcx, [rcx+18h]
0x14001b90b  lea     r8, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids
0x14001b912  mov     edx, 21h ; '!'
0x14001b917  mov     r9, rbx
0x14001b91a  call    WPP_SF_Z
0x14001b91f  lea     r8, [rsp+48h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x14001b924  mov     edx, 0F003Fh; DesiredAccess
0x14001b929  mov     rcx, rbx; SymbolicLinkName
0x14001b92c  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x14001b933  nop     dword ptr [rax+rax+00h]
0x14001b938  mov     ebx, eax
0x14001b93a  test    eax, eax
0x14001b93c  jns     short loc_14001B968
0x14001b93e  mov     [rsp+48h+DeviceInterfaceRegKey], 0FFFFFFFFFFFFFFFFh
0x14001b947  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b94e  cmp     rcx, rdi
0x14001b951  jz      loc_14001B9FC
0x14001b957  cmp     byte ptr [rcx+29h], 2
0x14001b95b  jb      loc_14001B9FC
0x14001b961  mov     edx, 22h ; '"'
0x14001b966  jmp     short loc_14001B9D2
0x14001b968  lea     rdx, aPortDescriptio; "Port Description"
0x14001b96f  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001b974  call    cs:__imp_RtlInitUnicodeString
0x14001b97b  nop     dword ptr [rax+rax+00h]
0x14001b980  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x14001b986  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x14001b98b  mov     rcx, [rsp+48h+DeviceInterfaceRegKey]; KeyHandle
0x14001b990  mov     r9d, 1; Type
0x14001b996  mov     [rsp+48h+DataSize], eax; DataSize
0x14001b99a  xor     r8d, r8d; TitleIndex
0x14001b99d  lea     rax, ?DisabledPortDescription@@3PAGA; "Inactive TS Port"
0x14001b9a4  mov     [rsp+48h+Data], rax; Data
0x14001b9a9  call    cs:__imp_ZwSetValueKey
0x14001b9b0  nop     dword ptr [rax+rax+00h]
0x14001b9b5  mov     ebx, eax
0x14001b9b7  test    eax, eax
0x14001b9b9  jns     short loc_14001B9E5
0x14001b9bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9c2  cmp     rcx, rdi
0x14001b9c5  jz      short loc_14001B9E5
0x14001b9c7  cmp     byte ptr [rcx+29h], 2
0x14001b9cb  jb      short loc_14001B9E5
0x14001b9cd  mov     edx, 23h ; '#'
0x14001b9d2  mov     rcx, [rcx+18h]
0x14001b9d6  lea     r8, WPP_40b7fc8c890d3cf5321c7b1086dc23d2_Traceguids
0x14001b9dd  mov     r9d, eax
0x14001b9e0  call    WPP_SF_d
0x14001b9e5  mov     rcx, [rsp+48h+DeviceInterfaceRegKey]; Handle
0x14001b9ea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14001b9ee  jz      short loc_14001B9FC
0x14001b9f0  call    cs:__imp_ZwClose
0x14001b9f7  nop     dword ptr [rax+rax+00h]
0x14001b9fc  mov     eax, ebx
0x14001b9fe  mov     rbx, [rsp+48h+arg_0]
0x14001ba03  add     rsp, 40h
0x14001ba07  pop     rdi
0x14001ba08  retn
```
