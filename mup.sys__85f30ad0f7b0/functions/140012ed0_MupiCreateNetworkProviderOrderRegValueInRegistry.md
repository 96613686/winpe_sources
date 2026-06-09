# MupiCreateNetworkProviderOrderRegValueInRegistry

- ea: `0x140012ed0`
- end: `0x140012fb3`
- name: `MupiCreateNetworkProviderOrderRegValueInRegistry`
- size: `227`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003b80`

## callees

- `0x140012ed0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140012f11`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012f11`
- `ntoskrnl!ZwClose` at `0x140012f92`
- `ntoskrnl!ZwClose` at `0x140012f92`
- `ntoskrnl!ZwOpenKey` at `0x140012f50`
- `ntoskrnl!ZwOpenKey` at `0x140012f50`
- `ntoskrnl!ZwSetValueKey` at `0x140012f80`
- `ntoskrnl!ZwSetValueKey` at `0x140012f80`

## string_xrefs

- `0x140012ef4`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

## pseudocode

```c
__int64 __fastcall MupiCreateNetworkProviderOrderRegValueInRegistry(PUNICODE_STRING ValueName, int a2)
{
  NTSTATUS v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int Data; // [rsp+88h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  Data = a2;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Networkprovider\\ProviderOrder");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes);
  if ( v3 >= 0 )
  {
    v3 = ZwSetValueKey(KeyHandle, ValueName, 0, 4u, &Data, 4u);
    ZwClose(KeyHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140012ed0  mov     [rsp-8+arg_0], rbx
0x140012ed5  mov     [rsp-8+arg_18], rdi
0x140012eda  mov     [rsp-8+arg_8], edx
0x140012ede  push    rbp
0x140012edf  mov     rbp, rsp
0x140012ee2  sub     rsp, 70h
0x140012ee6  xorps   xmm0, xmm0
0x140012ee9  mov     [rbp+KeyHandle], 0
0x140012ef1  mov     rdi, rcx
0x140012ef4  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012efb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012eff  xor     eax, eax
0x140012f01  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012f05  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012f09  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012f0d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012f11  call    cs:__imp_RtlInitUnicodeString
0x140012f18  nop     dword ptr [rax+rax+00h]
0x140012f1d  lea     rax, [rbp+DestinationString]
0x140012f21  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012f28  xorps   xmm0, xmm0
0x140012f2b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012f2f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012f33  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012f3b  mov     edx, 2; DesiredAccess
0x140012f40  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012f47  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140012f4b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012f50  call    cs:__imp_ZwOpenKey
0x140012f57  nop     dword ptr [rax+rax+00h]
0x140012f5c  mov     ebx, eax
0x140012f5e  test    eax, eax
0x140012f60  js      short loc_140012F9E
0x140012f62  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140012f66  lea     rax, [rbp+arg_8]
0x140012f6a  mov     r9d, 4; Type
0x140012f70  xor     r8d, r8d; TitleIndex
0x140012f73  mov     [rsp+70h+DataSize], r9d; DataSize
0x140012f78  mov     rdx, rdi; ValueName
0x140012f7b  mov     [rsp+70h+Data], rax; Data
0x140012f80  call    cs:__imp_ZwSetValueKey
0x140012f87  nop     dword ptr [rax+rax+00h]
0x140012f8c  mov     rcx, [rbp+KeyHandle]; Handle
0x140012f90  mov     ebx, eax
0x140012f92  call    cs:__imp_ZwClose
0x140012f99  nop     dword ptr [rax+rax+00h]
0x140012f9e  lea     r11, [rsp+70h+var_s0]
0x140012fa3  mov     eax, ebx
0x140012fa5  mov     rbx, [r11+10h]
0x140012fa9  mov     rdi, [r11+28h]
0x140012fad  mov     rsp, r11
0x140012fb0  pop     rbp
0x140012fb1  retn
```
