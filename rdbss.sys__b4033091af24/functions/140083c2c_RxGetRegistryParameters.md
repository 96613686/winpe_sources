# RxGetRegistryParameters

- ea: `0x140083c2c`
- end: `0x140083e02`
- name: `RxGetRegistryParameters`
- size: `470`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008321c`

## callees

- `0x140025c20`
- `0x140049124`
- `0x140078e20`
- `0x140083c2c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140083cdd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140083cdd`
- `ntoskrnl!ZwClose` at `0x140083dc4`
- `ntoskrnl!ZwClose` at `0x140083dd5`
- `ntoskrnl!ZwClose` at `0x140083dc4`
- `ntoskrnl!ZwClose` at `0x140083dd5`
- `ntoskrnl!ZwOpenKey` at `0x140083cbd`
- `ntoskrnl!ZwOpenKey` at `0x140083d22`
- `ntoskrnl!ZwOpenKey` at `0x140083cbd`
- `ntoskrnl!ZwOpenKey` at `0x140083d22`

## pseudocode

```c
int __fastcall RxGetRegistryParameters(UNICODE_STRING *a1)
{
  int result; // eax
  int v3; // [rsp+20h] [rbp-E0h]
  int v4; // [rsp+20h] [rbp-E0h]
  ULONG v5; // [rsp+28h] [rbp-D8h]
  ULONG v6; // [rsp+28h] [rbp-D8h]
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RxpCheckAndDisableUACCollapsing();
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Parameters");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) < 0 )
      return ZwClose(KeyHandle);
    RxGetUlongRegistryParameter(Handle, v3, v5);
    if ( (unsigned int)FspPerDeviceThreshold < 8 )
      goto LABEL_7;
    if ( (unsigned int)FspPerDeviceThreshold > 0x7FFFFFFF )
    {
      FspPerDeviceThreshold = 0x7FFFFFFF;
      goto LABEL_8;
    }
    if ( (unsigned int)FspPerDeviceThreshold < 8 )
LABEL_7:
      FspPerDeviceThreshold = 8;
LABEL_8:
    RxGetUlongRegistryParameter(Handle, v4, v6);
    if ( LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) >= 4 )
    {
      if ( LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) > 0x7FFFFFFF )
      {
        LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 0x7FFFFFFF;
LABEL_13:
        ZwClose(Handle);
        return ZwClose(KeyHandle);
      }
      if ( LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) >= 4 )
        goto LABEL_13;
    }
    LODWORD(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = 4;
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x140083c2c  mov     [rsp-8+arg_8], rbx
0x140083c31  push    rbp
0x140083c32  lea     rbp, [rsp-90h]
0x140083c3a  sub     rsp, 190h
0x140083c41  mov     rax, cs:__security_cookie
0x140083c48  xor     rax, rsp
0x140083c4b  mov     [rbp+90h+var_10], rax
0x140083c52  xorps   xmm0, xmm0
0x140083c55  mov     [rsp+190h+KeyHandle], 0
0x140083c5e  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x140083c63  xor     eax, eax
0x140083c65  mov     [rsp+190h+Handle], 0
0x140083c6e  movups  xmmword ptr [rsp+190h+ObjectAttributes+1Ch], xmm0
0x140083c73  mov     rbx, rcx
0x140083c76  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x140083c7b  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x140083c80  call    RxpCheckAndDisableUACCollapsing
0x140083c85  mov     [rsp+190h+ObjectAttributes.ObjectName], rbx
0x140083c8a  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x140083c8f  xorps   xmm0, xmm0
0x140083c92  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x140083c9a  mov     ebx, 20019h
0x140083c9f  mov     [rsp+190h+ObjectAttributes.RootDirectory], 0
0x140083ca8  mov     edx, ebx; DesiredAccess
0x140083caa  mov     [rsp+190h+ObjectAttributes.Attributes], 240h
0x140083cb2  lea     rcx, [rsp+190h+KeyHandle]; KeyHandle
0x140083cb7  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x140083cbd  call    cs:__imp_ZwOpenKey
0x140083cc4  nop     dword ptr [rax+rax+00h]
0x140083cc9  test    eax, eax
0x140083ccb  js      loc_140083DE1
0x140083cd1  lea     rdx, aParameters; "Parameters"
0x140083cd8  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x140083cdd  call    cs:__imp_RtlInitUnicodeString
0x140083ce4  nop     dword ptr [rax+rax+00h]
0x140083ce9  mov     rax, [rsp+190h+KeyHandle]
0x140083cee  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x140083cf3  mov     [rsp+190h+ObjectAttributes.RootDirectory], rax
0x140083cf8  lea     rcx, [rsp+190h+Handle]; KeyHandle
0x140083cfd  lea     rax, [rsp+190h+DestinationString]
0x140083d02  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x140083d0a  xorps   xmm0, xmm0
0x140083d0d  mov     [rsp+190h+ObjectAttributes.ObjectName], rax
0x140083d12  mov     edx, ebx; DesiredAccess
0x140083d14  mov     [rsp+190h+ObjectAttributes.Attributes], 240h
0x140083d1c  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x140083d22  call    cs:__imp_ZwOpenKey
0x140083d29  nop     dword ptr [rax+rax+00h]
0x140083d2e  test    eax, eax
0x140083d30  js      loc_140083DD0
0x140083d36  mov     rcx, [rsp+190h+Handle]; KeyHandle
0x140083d3b  lea     r9, [rbp+90h+var_110]
0x140083d3f  lea     r8, FspPerDeviceThreshold
0x140083d46  lea     rdx, aFspperdeviceth; "FspPerDeviceThreshold"
0x140083d4d  call    RxGetUlongRegistryParameter
0x140083d52  mov     eax, cs:FspPerDeviceThreshold
0x140083d58  mov     ebx, 7FFFFFFFh
0x140083d5d  cmp     eax, 8
0x140083d60  jb      short loc_140083D73
0x140083d62  cmp     eax, ebx
0x140083d64  jbe     short loc_140083D6E
0x140083d66  mov     cs:FspPerDeviceThreshold, ebx
0x140083d6c  jmp     short loc_140083D7D
0x140083d6e  cmp     eax, 8
0x140083d71  jnb     short loc_140083D7D
0x140083d73  mov     cs:FspPerDeviceThreshold, 8
0x140083d7d  mov     rcx, [rsp+190h+Handle]; KeyHandle
0x140083d82  lea     r9, [rbp+90h+var_110]
0x140083d86  lea     r8, WPP_MAIN_CB.DeviceQueue.DeviceListHead
0x140083d8d  lea     rdx, aFspperfcbthres; "FspPerFcbThreshold"
0x140083d94  call    RxGetUlongRegistryParameter
0x140083d99  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140083d9f  cmp     eax, 4
0x140083da2  jb      short loc_140083DB5
0x140083da4  cmp     eax, ebx
0x140083da6  jbe     short loc_140083DB0
0x140083da8  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, ebx
0x140083dae  jmp     short loc_140083DBF
0x140083db0  cmp     eax, 4
0x140083db3  jnb     short loc_140083DBF
0x140083db5  mov     dword ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, 4
0x140083dbf  mov     rcx, [rsp+190h+Handle]; Handle
0x140083dc4  call    cs:__imp_ZwClose
0x140083dcb  nop     dword ptr [rax+rax+00h]
0x140083dd0  mov     rcx, [rsp+190h+KeyHandle]; Handle
0x140083dd5  call    cs:__imp_ZwClose
0x140083ddc  nop     dword ptr [rax+rax+00h]
0x140083de1  mov     rcx, [rbp+90h+var_10]
0x140083de8  xor     rcx, rsp; StackCookie
0x140083deb  call    __security_check_cookie
0x140083df0  mov     rbx, [rsp+190h+arg_8]
0x140083df8  add     rsp, 190h
0x140083dff  pop     rbp
0x140083e00  retn
```
