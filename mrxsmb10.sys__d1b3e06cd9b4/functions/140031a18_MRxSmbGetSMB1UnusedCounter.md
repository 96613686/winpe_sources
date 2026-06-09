# MRxSmbGetSMB1UnusedCounter

- ea: `0x140031a18`
- end: `0x140031ad4`
- name: `MRxSmbGetSMB1UnusedCounter`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000bac0`
- `0x14003108c`

## callees

- `0x140031a18`
- `0x140031adc`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140031a89`
- `ntoskrnl!ZwOpenKey` at `0x140031a89`
- `ntoskrnl!ZwClose` at `0x140031ab7`
- `ntoskrnl!ZwClose` at `0x140031ab7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031a4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140031a4e`

## string_xrefs

- `0x140031a28`: `\Registry\Machine\Software\Microsoft\SMB1Uninstall`

## pseudocode

```c
__int64 MRxSmbGetSMB1UnusedCounter()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Microsoft\\SMB1Uninstall");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    MRxSmbGetUlongRegistryParameter(KeyHandle);
    ZwClose(KeyHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x140031a18  mov     [rsp-8+arg_10], rbx
0x140031a1d  push    rbp
0x140031a1e  mov     rbp, rsp
0x140031a21  sub     rsp, 60h
0x140031a25  xorps   xmm0, xmm0
0x140031a28  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x140031a2f  xor     eax, eax
0x140031a31  lea     rcx, [rbp+DestinationString]; DestinationString
0x140031a35  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140031a39  mov     [rbp+KeyHandle], rax
0x140031a3d  xor     ebx, ebx
0x140031a3f  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140031a43  mov     [rbp+arg_0], eax
0x140031a46  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140031a4a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140031a4e  call    cs:__imp_RtlInitUnicodeString
0x140031a55  nop     dword ptr [rax+rax+00h]
0x140031a5a  lea     rax, [rbp+DestinationString]
0x140031a5e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031a65  xorps   xmm0, xmm0
0x140031a68  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140031a6c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140031a70  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x140031a74  mov     edx, 20019h; DesiredAccess
0x140031a79  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140031a80  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140031a84  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140031a89  call    cs:__imp_ZwOpenKey
0x140031a90  nop     dword ptr [rax+rax+00h]
0x140031a95  test    eax, eax
0x140031a97  js      short loc_140031AC3
0x140031a99  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140031a9d  lea     r8, [rbp+arg_0]
0x140031aa1  lea     rdx, aSmb1clientcoun; "SMB1ClientCounter"
0x140031aa8  call    MRxSmbGetUlongRegistryParameter
0x140031aad  mov     rcx, [rbp+KeyHandle]; Handle
0x140031ab1  test    eax, eax
0x140031ab3  cmovns  ebx, [rbp+arg_0]
0x140031ab7  call    cs:__imp_ZwClose
0x140031abe  nop     dword ptr [rax+rax+00h]
0x140031ac3  mov     eax, ebx
0x140031ac5  mov     rbx, [rsp+60h+arg_10]
0x140031acd  add     rsp, 60h
0x140031ad1  pop     rbp
0x140031ad2  retn
```
