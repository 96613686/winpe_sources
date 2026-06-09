# ClassGetDeviceParameter

- ea: `0x14005f690`
- end: `0x14005f7f4`
- name: `ClassGetDeviceParameter`
- size: `356`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PWSTR SubkeyName, PWSTR ParameterName, PULONG ParameterValue)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140017c2c`
- `0x14001f978`
- `0x14005479c`
- `0x1400579b4`
- `0x1400597c0`

## callees

- `0x14003e470`
- `0x14003e940`
- `0x14005bef0`
- `0x14005f690`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14005f755`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061c60`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061d0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061dc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f755`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061c60`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061d0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140061dc4`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005f6f2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005f719`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005f6f2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14005f719`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140061d42`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140061df9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140061d1e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140061dd5`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140061d1e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140061dd5`
- `ntoskrnl!ZwClose` at `0x14005f7ab`
- `ntoskrnl!ZwClose` at `0x14005f7bd`
- `ntoskrnl!ZwClose` at `0x140061cb2`
- `ntoskrnl!ZwClose` at `0x140061d69`
- `ntoskrnl!ZwClose` at `0x140061e31`
- `ntoskrnl!ZwClose` at `0x14005f7ab`
- `ntoskrnl!ZwClose` at `0x14005f7bd`
- `ntoskrnl!ZwClose` at `0x140061cb2`
- `ntoskrnl!ZwClose` at `0x140061d69`
- `ntoskrnl!ZwClose` at `0x140061e31`
- `ntoskrnl!ZwOpenKey` at `0x14005f793`
- `ntoskrnl!ZwOpenKey` at `0x140061c9e`
- `ntoskrnl!ZwOpenKey` at `0x14005f793`
- `ntoskrnl!ZwOpenKey` at `0x140061c9e`

## string_xrefs

- `0x140061cc8`: `RtlQueryRegistryValuesEx`
- `0x140061d7f`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __stdcall ClassGetDeviceParameter(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        PWSTR SubkeyName,
        PWSTR ParameterName,
        PULONG ParameterValue)
{
  struct _DEVICE_OBJECT *LowerPdo; // rcx
  void *v9; // rbx
  ULONG v10; // r15d
  PVOID v11; // rax
  int v12; // ebx
  void *v13; // rbx
  ULONG v14; // r15d
  PVOID SystemRoutineAddress; // rax
  void *KeyHandle; // [rsp+30h] [rbp-89h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-81h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v19[14]; // [rsp+80h] [rbp-39h] BYREF
  void *DeviceRegKey; // [rsp+120h] [rbp+67h] BYREF

  memset(v19, 0, sizeof(v19));
  LowerPdo = FdoExtension->LowerPdo;
  DeviceRegKey = 0;
  KeyHandle = 0;
  if ( IoOpenDeviceRegistryKey(LowerPdo, 1u, 0x20019u, &DeviceRegKey) < 0 )
  {
LABEL_2:
    if ( IoOpenDeviceRegistryKey(FdoExtension->LowerPdo, 2u, 0x20019u, &DeviceRegKey) >= 0 )
    {
      if ( !SubkeyName )
        goto LABEL_20;
      DestinationString = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      RtlInitUnicodeString(&DestinationString, SubkeyName);
      ObjectAttributes.RootDirectory = DeviceRegKey;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
LABEL_20:
        v13 = DeviceRegKey;
        v14 = *ParameterValue;
        LODWORD(v19[1]) = 292;
        v19[2] = ParameterName;
        v19[3] = ParameterValue;
        if ( SubkeyName )
          v13 = KeyHandle;
        LODWORD(v19[4]) = 0x4000000;
        v19[5] = 0;
        LODWORD(v19[6]) = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
        SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
        if ( !SystemRoutineAddress )
          SystemRoutineAddress = RtlQueryRegistryValues;
        if ( ((int (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
               0x40000000,
               v13,
               v19,
               0,
               0) < 0 )
          *ParameterValue = v14;
        else
          ClassSetDeviceParameter(FdoExtension, SubkeyName, ParameterName, *ParameterValue);
        if ( SubkeyName )
          ZwClose(KeyHandle);
      }
      ZwClose(DeviceRegKey);
    }
    return;
  }
  if ( SubkeyName )
  {
    DestinationString = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    RtlInitUnicodeString(&DestinationString, SubkeyName);
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    {
      ZwClose(DeviceRegKey);
      goto LABEL_2;
    }
  }
  v9 = DeviceRegKey;
  v10 = *ParameterValue;
  LODWORD(v19[1]) = 292;
  v19[2] = ParameterName;
  v19[3] = ParameterValue;
  if ( SubkeyName )
    v9 = KeyHandle;
  LODWORD(v19[4]) = 0x4000000;
  v19[5] = 0;
  LODWORD(v19[6]) = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  v11 = MmGetSystemRoutineAddress(&DestinationString);
  if ( !v11 )
    v11 = RtlQueryRegistryValues;
  v12 = ((__int64 (__fastcall *)(__int64, void *, _QWORD *, _QWORD, _QWORD))v11)(0x40000000, v9, v19, 0, 0);
  if ( v12 < 0 )
    *ParameterValue = v10;
  if ( SubkeyName )
    ZwClose(KeyHandle);
  ZwClose(DeviceRegKey);
  if ( v12 < 0 )
    goto LABEL_2;
}

```

## disassembly

```asm
0x14005f690  mov     [rsp-8+arg_8], rbx
0x14005f695  mov     [rsp-8+arg_10], rsi
0x14005f69a  push    rbp
0x14005f69b  push    rdi
0x14005f69c  push    r12
0x14005f69e  push    r14
0x14005f6a0  push    r15
0x14005f6a2  lea     rbp, [rsp-37h]
0x14005f6a7  sub     rsp, 0F0h
0x14005f6ae  mov     rdi, rdx
0x14005f6b1  mov     r12, r8
0x14005f6b4  xor     edx, edx; Val
0x14005f6b6  mov     r14, rcx
0x14005f6b9  lea     rcx, [rbp+57h+var_90]; void *
0x14005f6bd  mov     rsi, r9
0x14005f6c0  lea     r8d, [rdx+70h]; Size
0x14005f6c4  call    memset
0x14005f6c9  mov     rcx, [r14+200h]; DeviceObject
0x14005f6d0  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x14005f6d4  mov     ebx, 20019h
0x14005f6d9  mov     [rbp+57h+DeviceRegKey], 0
0x14005f6e1  mov     r8d, ebx; DesiredAccess
0x14005f6e4  mov     [rsp+110h+KeyHandle], 0
0x14005f6ed  mov     edx, 1; DevInstKeyType
0x14005f6f2  call    cs:__imp_IoOpenDeviceRegistryKey
0x14005f6f9  nop     dword ptr [rax+rax+00h]
0x14005f6fe  test    eax, eax
0x14005f700  jns     loc_140061C38
0x14005f706  mov     rcx, [r14+200h]; DeviceObject
0x14005f70d  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x14005f711  mov     r8d, ebx; DesiredAccess
0x14005f714  mov     edx, 2; DevInstKeyType
0x14005f719  call    cs:__imp_IoOpenDeviceRegistryKey
0x14005f720  nop     dword ptr [rax+rax+00h]
0x14005f725  test    eax, eax
0x14005f727  js      loc_14005F7CD
0x14005f72d  test    rdi, rdi
0x14005f730  jz      loc_140061D7B
0x14005f736  xorps   xmm1, xmm1
0x14005f739  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x14005f73e  xorps   xmm0, xmm0
0x14005f741  mov     rdx, rdi; SourceString
0x14005f744  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x14005f749  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14005f74d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14005f751  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14005f755  call    cs:__imp_RtlInitUnicodeString
0x14005f75c  nop     dword ptr [rax+rax+00h]
0x14005f761  mov     rax, [rbp+57h+DeviceRegKey]
0x14005f765  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14005f769  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14005f76d  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x14005f772  lea     rax, [rsp+110h+DestinationString]
0x14005f777  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14005f77e  xorps   xmm0, xmm0
0x14005f781  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14005f785  mov     edx, ebx; DesiredAccess
0x14005f787  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14005f78e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005f793  call    cs:__imp_ZwOpenKey
0x14005f79a  nop     dword ptr [rax+rax+00h]
0x14005f79f  test    eax, eax
0x14005f7a1  jns     loc_140061D7B
0x14005f7a7  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x14005f7ab  call    cs:__imp_ZwClose
0x14005f7b2  nop     dword ptr [rax+rax+00h]
0x14005f7b7  jmp     short loc_14005F7CD
0x14005f7b9  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x14005f7bd  call    cs:__imp_ZwClose
0x14005f7c4  nop     dword ptr [rax+rax+00h]
0x14005f7c9  test    ebx, ebx
0x14005f7cb  js      short loc_14005F7EA
0x14005f7cd  lea     r11, [rsp+110h+var_20]
0x14005f7d5  mov     rbx, [r11+38h]
0x14005f7d9  mov     rsi, [r11+40h]
0x14005f7dd  mov     rsp, r11
0x14005f7e0  pop     r15
0x14005f7e2  pop     r14
0x14005f7e4  pop     r12
0x14005f7e6  pop     rdi
0x14005f7e7  pop     rbp
0x14005f7e8  retn
0x14005f7ea  mov     ebx, 20019h
0x14005f7ef  jmp     loc_14005F706
0x140061c38  test    rdi, rdi
0x140061c3b  jz      loc_140061CC4
0x140061c41  xorps   xmm1, xmm1
0x140061c44  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140061c49  xorps   xmm0, xmm0
0x140061c4c  mov     rdx, rdi; SourceString
0x140061c4f  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x140061c54  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x140061c58  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x140061c5c  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x140061c60  call    cs:__imp_RtlInitUnicodeString
0x140061c67  nop     dword ptr [rax+rax+00h]
0x140061c6c  mov     rax, [rbp+57h+DeviceRegKey]
0x140061c70  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140061c74  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140061c78  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x140061c7d  lea     rax, [rsp+110h+DestinationString]
0x140061c82  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140061c89  xorps   xmm0, xmm0
0x140061c8c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140061c90  mov     edx, ebx; DesiredAccess
0x140061c92  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140061c99  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140061c9e  call    cs:__imp_ZwOpenKey
0x140061ca5  nop     dword ptr [rax+rax+00h]
0x140061caa  test    eax, eax
0x140061cac  jns     short loc_140061CC4
0x140061cae  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x140061cb2  call    cs:__imp_ZwClose
0x140061cb9  nop     dword ptr [rax+rax+00h]
0x140061cbe  nop
0x140061cbf  jmp     loc_14005F706
0x140061cc4  mov     rbx, [rbp+57h+DeviceRegKey]
0x140061cc8  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140061ccf  mov     r15d, [rsi]
0x140061cd2  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140061cd7  xorps   xmm0, xmm0
0x140061cda  mov     [rbp+57h+var_88], 124h
0x140061ce1  test    rdi, rdi
0x140061ce4  mov     [rbp+57h+var_80], r12
0x140061ce8  mov     [rbp+57h+var_78], rsi
0x140061cec  cmovnz  rbx, [rsp+110h+KeyHandle]
0x140061cf2  mov     [rbp+57h+var_70], 4000000h
0x140061cf9  mov     [rbp+57h+var_68], 0
0x140061d01  mov     [rbp+57h+var_60], 0
0x140061d08  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x140061d0d  call    cs:__imp_RtlInitUnicodeString
0x140061d14  nop     dword ptr [rax+rax+00h]
0x140061d19  lea     rcx, [rsp+110h+DestinationString]; SystemRoutineName
0x140061d1e  call    cs:__imp_MmGetSystemRoutineAddress
0x140061d25  nop     dword ptr [rax+rax+00h]
0x140061d2a  lea     r8, [rbp+57h+var_90]
0x140061d2e  mov     [rsp+110h+var_F0], 0
0x140061d37  test    rax, rax
0x140061d3a  mov     rdx, rbx
0x140061d3d  mov     ecx, 40000000h
0x140061d42  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140061d4a  xor     r9d, r9d
0x140061d4d  call    _guard_dispatch_icall
0x140061d52  mov     ebx, eax
0x140061d54  test    eax, eax
0x140061d56  jns     short loc_140061D5B
0x140061d58  mov     [rsi], r15d
0x140061d5b  test    rdi, rdi
0x140061d5e  jz      loc_14005F7B9
0x140061d64  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x140061d69  call    cs:__imp_ZwClose
0x140061d70  nop     dword ptr [rax+rax+00h]
0x140061d75  nop
0x140061d76  jmp     loc_14005F7B9
0x140061d7b  mov     rbx, [rbp+57h+DeviceRegKey]
0x140061d7f  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x140061d86  mov     r15d, [rsi]
0x140061d89  lea     rcx, [rsp+110h+DestinationString]; DestinationString
0x140061d8e  xorps   xmm0, xmm0
0x140061d91  mov     [rbp+57h+var_88], 124h
0x140061d98  test    rdi, rdi
0x140061d9b  mov     [rbp+57h+var_80], r12
0x140061d9f  mov     [rbp+57h+var_78], rsi
0x140061da3  cmovnz  rbx, [rsp+110h+KeyHandle]
0x140061da9  mov     [rbp+57h+var_70], 4000000h
0x140061db0  mov     [rbp+57h+var_68], 0
0x140061db8  mov     [rbp+57h+var_60], 0
0x140061dbf  movups  xmmword ptr [rsp+110h+DestinationString.Length], xmm0
0x140061dc4  call    cs:__imp_RtlInitUnicodeString
0x140061dcb  nop     dword ptr [rax+rax+00h]
0x140061dd0  lea     rcx, [rsp+110h+DestinationString]; SystemRoutineName
0x140061dd5  call    cs:__imp_MmGetSystemRoutineAddress
0x140061ddc  nop     dword ptr [rax+rax+00h]
0x140061de1  lea     r8, [rbp+57h+var_90]
0x140061de5  mov     [rsp+110h+var_F0], 0
0x140061dee  test    rax, rax
0x140061df1  mov     rdx, rbx
0x140061df4  mov     ecx, 40000000h
0x140061df9  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140061e01  xor     r9d, r9d
0x140061e04  call    _guard_dispatch_icall
0x140061e09  test    eax, eax
0x140061e0b  js      short loc_140061E20
0x140061e0d  mov     r9d, [rsi]; ParameterValue
0x140061e10  mov     r8, r12; ParameterName
0x140061e13  mov     rdx, rdi; SubkeyName
0x140061e16  mov     rcx, r14; FdoExtension
0x140061e19  call    ClassSetDeviceParameter
0x140061e1e  jmp     short loc_140061E23
0x140061e20  mov     [rsi], r15d
0x140061e23  test    rdi, rdi
0x140061e26  jz      loc_14005F7A7
0x140061e2c  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x140061e31  call    cs:__imp_ZwClose
0x140061e38  nop     dword ptr [rax+rax+00h]
0x140061e3d  nop
0x140061e3e  jmp     loc_14005F7A7
```
