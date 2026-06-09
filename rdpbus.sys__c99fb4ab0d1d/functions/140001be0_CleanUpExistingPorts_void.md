# CleanUpExistingPorts(void)

- ea: `0x140001be0`
- end: `0x140001f06`
- name: `?CleanUpExistingPorts@@YAJXZ`
- size: `806`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x140001460`

## callees

- `0x140001be0`
- `0x1400020b4`
- `0x1400020e4`
- `0x140002180`
- `0x140002520`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140001cb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ceb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001d6d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001db8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001cb0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001ceb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001d6d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001db8`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140001ccb`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x140001ccb`
- `ntoskrnl!ZwDeleteValueKey` at `0x140001dce`
- `ntoskrnl!ZwDeleteValueKey` at `0x140001dce`
- `ntoskrnl!ExFreePool` at `0x140001e6e`
- `ntoskrnl!ExFreePool` at `0x140001e6e`
- `ntoskrnl!ZwQueryValueKey` at `0x140001d9c`
- `ntoskrnl!ZwQueryValueKey` at `0x140001d9c`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140001c45`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140001c45`
- `ntoskrnl!ZwClose` at `0x140001e3c`
- `ntoskrnl!ZwClose` at `0x140001e3c`
- `ntoskrnl!ZwSetValueKey` at `0x140001d55`
- `ntoskrnl!ZwSetValueKey` at `0x140001d55`

## pseudocode

```c
__int64 CleanUpExistingPorts(void)
{
  __int64 v0; // rdx
  unsigned int DeviceInterfaces; // ebx
  __int64 v2; // r8
  WCHAR *v3; // rdi
  __int64 v4; // r14
  unsigned int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  void *DeviceInterfaceRegKey; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD Data[2]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v14; // [rsp+78h] [rbp-88h]
  _BYTE KeyValueInformation[272]; // [rsp+80h] [rbp-80h] BYREF

  SymbolicLinkList = 0;
  DeviceInterfaceRegKey = 0;
  ResultLength = 0;
  DestinationString = 0;
  if ( !RDPDYN_PDO )
  {
    DeviceInterfaces = -1073741823;
    goto LABEL_33;
  }
  DeviceInterfaces = IoGetDeviceInterfaces(&InterfaceClassGuid, RDPDYN_PDO, 1u, &SymbolicLinkList);
  if ( DeviceInterfaces )
  {
LABEL_33:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids,
        DeviceInterfaces);
    return DeviceInterfaces;
  }
  v3 = SymbolicLinkList;
  if ( SymbolicLinkList )
  {
    v4 = -1;
    do
      ++v4;
    while ( SymbolicLinkList[v4] );
    if ( (_DWORD)v4 )
    {
      while ( 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, v0, v2, v3);
        RtlInitUnicodeString(&DestinationString, v3);
        v5 = IoOpenDeviceInterfaceRegistryKey(&DestinationString, 0xF003Fu, &DeviceInterfaceRegKey);
        if ( v5 )
          break;
        RtlInitUnicodeString(&DestinationString, L"Port Description");
        v14 = aInactiveTsPort[16];
        v6 = -1;
        Data[0] = *(_OWORD *)L"Inactive TS Port";
        Data[1] = *(_OWORD *)L" TS Port";
        do
          ++v6;
        while ( *((_WORD *)Data + v6) );
        ZwSetValueKey(DeviceInterfaceRegKey, &DestinationString, 0, 1u, Data, 2 * v6 + 2);
        RtlInitUnicodeString(&DestinationString, L"recyclable");
        if ( ZwQueryValueKey(
               DeviceInterfaceRegKey,
               &DestinationString,
               KeyValueBasicInformation,
               KeyValueInformation,
               0x110u,
               &ResultLength) )
        {
          goto LABEL_19;
        }
        RtlInitUnicodeString(&DestinationString, L"Port Number");
        ZwDeleteValueKey(DeviceInterfaceRegKey, &DestinationString);
LABEL_22:
        if ( DeviceInterfaceRegKey )
          ZwClose(DeviceInterfaceRegKey);
        v7 = (unsigned int)(v4 + 1);
        v4 = -1;
        v3 += v7;
        do
          ++v4;
        while ( v3[v4] );
        if ( !(_DWORD)v4 )
        {
          v3 = SymbolicLinkList;
          goto LABEL_28;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids, v5);
      DeviceInterfaceRegKey = 0;
LABEL_19:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
      goto LABEL_22;
    }
LABEL_28:
    ExFreePool(v3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids);
  }
  return DeviceInterfaces;
}

```

## disassembly

```asm
0x140001be0  push    rbp
0x140001be2  push    rbx
0x140001be3  push    rsi
0x140001be4  push    rdi
0x140001be5  push    r12
0x140001be7  push    r14
0x140001be9  push    r15
0x140001beb  lea     rbp, [rsp-0A0h]
0x140001bf3  sub     rsp, 1A0h
0x140001bfa  mov     rax, cs:__security_cookie
0x140001c01  xor     rax, rsp
0x140001c04  mov     [rbp+0D0h+var_40], rax
0x140001c0b  mov     rdx, cs:?RDPDYN_PDO@@3PEAU_DEVICE_OBJECT@@EA; PhysicalDeviceObject
0x140001c12  xor     r15d, r15d
0x140001c15  mov     [rsp+1D0h+SymbolicLinkList], r15
0x140001c1a  xorps   xmm0, xmm0
0x140001c1d  mov     [rsp+1D0h+DeviceInterfaceRegKey], r15
0x140001c22  mov     [rsp+1D0h+ResultLength], r15d
0x140001c27  movups  xmmword ptr [rsp+1D0h+DestinationString.Length], xmm0
0x140001c2c  test    rdx, rdx
0x140001c2f  jz      loc_140001EAC
0x140001c35  lea     r9, [rsp+1D0h+SymbolicLinkList]; SymbolicLinkList
0x140001c3a  lea     r8d, [r15+1]; Flags
0x140001c3e  lea     rcx, InterfaceClassGuid; InterfaceClassGuid
0x140001c45  call    cs:__imp_IoGetDeviceInterfaces
0x140001c4c  nop     dword ptr [rax+rax+00h]
0x140001c51  mov     ebx, eax
0x140001c53  test    eax, eax
0x140001c55  jnz     loc_140001EB1
0x140001c5b  mov     rdi, [rsp+1D0h+SymbolicLinkList]
0x140001c60  test    rdi, rdi
0x140001c63  jz      loc_140001E7C
0x140001c69  or      r12, 0FFFFFFFFFFFFFFFFh
0x140001c6d  mov     r14, r12
0x140001c70  inc     r14
0x140001c73  cmp     [rdi+r14*2], r15w
0x140001c78  jnz     short loc_140001C70
0x140001c7a  test    r14d, r14d
0x140001c7d  jz      loc_140001E6B
0x140001c83  lea     rsi, WPP_GLOBAL_Control
0x140001c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c91  cmp     rcx, rsi
0x140001c94  jz      short loc_140001CA8
0x140001c96  cmp     byte ptr [rcx+29h], 4
0x140001c9a  jb      short loc_140001CA8
0x140001c9c  mov     rcx, [rcx+18h]
0x140001ca0  mov     r9, rdi
0x140001ca3  call    WPP_SF_S
0x140001ca8  mov     rdx, rdi; SourceString
0x140001cab  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x140001cb0  call    cs:__imp_RtlInitUnicodeString
0x140001cb7  nop     dword ptr [rax+rax+00h]
0x140001cbc  lea     r8, [rsp+1D0h+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x140001cc1  mov     edx, 0F003Fh; DesiredAccess
0x140001cc6  lea     rcx, [rsp+1D0h+DestinationString]; SymbolicLinkName
0x140001ccb  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x140001cd2  nop     dword ptr [rax+rax+00h]
0x140001cd7  test    eax, eax
0x140001cd9  jnz     loc_140001DDC
0x140001cdf  lea     rdx, aPortDescriptio; "Port Description"
0x140001ce6  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x140001ceb  call    cs:__imp_RtlInitUnicodeString
0x140001cf2  nop     dword ptr [rax+rax+00h]
0x140001cf7  movzx   eax, word ptr cs:aInactiveTsPort+20h; ""
0x140001cfe  lea     rcx, [rsp+1D0h+var_178]
0x140001d03  movups  xmm0, xmmword ptr cs:aInactiveTsPort; "Inactive TS Port"
0x140001d0a  mov     [rsp+1D0h+var_158], ax
0x140001d0f  mov     rax, r12
0x140001d12  movups  xmm1, xmmword ptr cs:aInactiveTsPort+10h; " TS Port"
0x140001d19  movups  [rsp+1D0h+var_178], xmm0
0x140001d1e  movups  [rsp+1D0h+var_168], xmm1
0x140001d23  inc     rax
0x140001d26  cmp     [rcx+rax*2], r15w
0x140001d2b  jnz     short loc_140001D23
0x140001d2d  mov     rcx, [rsp+1D0h+DeviceInterfaceRegKey]; KeyHandle
0x140001d32  lea     eax, ds:2[rax*2]
0x140001d39  mov     [rsp+1D0h+DataSize], eax; DataSize
0x140001d3d  lea     rdx, [rsp+1D0h+DestinationString]; ValueName
0x140001d42  lea     rax, [rsp+1D0h+var_178]
0x140001d47  mov     r9d, 1; Type
0x140001d4d  xor     r8d, r8d; TitleIndex
0x140001d50  mov     [rsp+1D0h+Data], rax; Data
0x140001d55  call    cs:__imp_ZwSetValueKey
0x140001d5c  nop     dword ptr [rax+rax+00h]
0x140001d61  lea     rdx, aRecyclable; "recyclable"
0x140001d68  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x140001d6d  call    cs:__imp_RtlInitUnicodeString
0x140001d74  nop     dword ptr [rax+rax+00h]
0x140001d79  mov     rcx, [rsp+1D0h+DeviceInterfaceRegKey]; KeyHandle
0x140001d7e  lea     rax, [rsp+1D0h+ResultLength]
0x140001d83  mov     qword ptr [rsp+1D0h+DataSize], rax; ResultLength
0x140001d88  lea     r9, [rbp+0D0h+KeyValueInformation]; KeyValueInformation
0x140001d8c  xor     r8d, r8d; KeyValueInformationClass
0x140001d8f  mov     dword ptr [rsp+1D0h+Data], 110h; Length
0x140001d97  lea     rdx, [rsp+1D0h+DestinationString]; ValueName
0x140001d9c  call    cs:__imp_ZwQueryValueKey
0x140001da3  nop     dword ptr [rax+rax+00h]
0x140001da8  test    eax, eax
0x140001daa  jnz     short loc_140001E0B
0x140001dac  lea     rdx, aPortNumber; "Port Number"
0x140001db3  lea     rcx, [rsp+1D0h+DestinationString]; DestinationString
0x140001db8  call    cs:__imp_RtlInitUnicodeString
0x140001dbf  nop     dword ptr [rax+rax+00h]
0x140001dc4  mov     rcx, [rsp+1D0h+DeviceInterfaceRegKey]; KeyHandle
0x140001dc9  lea     rdx, [rsp+1D0h+DestinationString]; ValueName
0x140001dce  call    cs:__imp_ZwDeleteValueKey
0x140001dd5  nop     dword ptr [rax+rax+00h]
0x140001dda  jmp     short loc_140001E32
0x140001ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140001de3  cmp     rcx, rsi
0x140001de6  jz      short loc_140001E06
0x140001de8  cmp     byte ptr [rcx+29h], 2
0x140001dec  jb      short loc_140001E06
0x140001dee  mov     rcx, [rcx+18h]
0x140001df2  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001df9  mov     edx, 2Fh ; '/'
0x140001dfe  mov     r9d, eax
0x140001e01  call    WPP_SF_D
0x140001e06  mov     [rsp+1D0h+DeviceInterfaceRegKey], r15
0x140001e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e12  cmp     rcx, rsi
0x140001e15  jz      short loc_140001E32
0x140001e17  cmp     byte ptr [rcx+29h], 2
0x140001e1b  jb      short loc_140001E32
0x140001e1d  mov     rcx, [rcx+18h]
0x140001e21  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001e28  mov     edx, 30h ; '0'
0x140001e2d  call    WPP_SF_
0x140001e32  mov     rcx, [rsp+1D0h+DeviceInterfaceRegKey]; Handle
0x140001e37  test    rcx, rcx
0x140001e3a  jz      short loc_140001E48
0x140001e3c  call    cs:__imp_ZwClose
0x140001e43  nop     dword ptr [rax+rax+00h]
0x140001e48  lea     eax, [r14+1]
0x140001e4c  mov     r14, r12
0x140001e4f  lea     rdi, [rdi+rax*2]
0x140001e53  inc     r14
0x140001e56  cmp     [rdi+r14*2], r15w
0x140001e5b  jnz     short loc_140001E53
0x140001e5d  test    r14d, r14d
0x140001e60  jnz     loc_140001C8A
0x140001e66  mov     rdi, [rsp+1D0h+SymbolicLinkList]
0x140001e6b  mov     rcx, rdi; P
0x140001e6e  call    cs:__imp_ExFreePool
0x140001e75  nop     dword ptr [rax+rax+00h]
0x140001e7a  jmp     short loc_140001EE2
0x140001e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e83  lea     rsi, WPP_GLOBAL_Control
0x140001e8a  cmp     rcx, rsi
0x140001e8d  jz      short loc_140001EE2
0x140001e8f  cmp     byte ptr [rcx+29h], 5
0x140001e93  jb      short loc_140001EE2
0x140001e95  mov     rcx, [rcx+18h]
0x140001e99  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001ea0  mov     edx, 31h ; '1'
0x140001ea5  call    WPP_SF_
0x140001eaa  jmp     short loc_140001EE2
0x140001eac  mov     ebx, 0C0000001h
0x140001eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140001eb8  lea     rsi, WPP_GLOBAL_Control
0x140001ebf  cmp     rcx, rsi
0x140001ec2  jz      short loc_140001EE2
0x140001ec4  cmp     byte ptr [rcx+29h], 4
0x140001ec8  jb      short loc_140001EE2
0x140001eca  mov     rcx, [rcx+18h]
0x140001ece  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x140001ed5  mov     edx, 32h ; '2'
0x140001eda  mov     r9d, ebx
0x140001edd  call    WPP_SF_D
0x140001ee2  mov     eax, ebx
0x140001ee4  mov     rcx, [rbp+0D0h+var_40]
0x140001eeb  xor     rcx, rsp; StackCookie
0x140001eee  call    __security_check_cookie
0x140001ef3  add     rsp, 1A0h
0x140001efa  pop     r15
0x140001efc  pop     r14
0x140001efe  pop     r12
0x140001f00  pop     rdi
0x140001f01  pop     rsi
0x140001f02  pop     rbx
0x140001f03  pop     rbp
0x140001f04  retn
```
