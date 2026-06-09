# MupiCreateNetworkProviderOrderRegValueInRegistry

- ea: `0x140012e80`
- end: `0x140012f63`
- name: `MupiCreateNetworkProviderOrderRegValueInRegistry`
- size: `227`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140003b80`

## callees

- `0x140012e80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140012ec1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012ec1`
- `ntoskrnl!ZwClose` at `0x140012f42`
- `ntoskrnl!ZwClose` at `0x140012f42`
- `ntoskrnl!ZwOpenKey` at `0x140012f00`
- `ntoskrnl!ZwOpenKey` at `0x140012f00`
- `ntoskrnl!ZwSetValueKey` at `0x140012f30`
- `ntoskrnl!ZwSetValueKey` at `0x140012f30`

## string_xrefs

- `0x140012ea4`: `\Registry\Machine\System\CurrentControlSet\Control\Networkprovider\ProviderOrder`

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
0x140012e80  mov     [rsp-8+arg_0], rbx
0x140012e85  mov     [rsp-8+arg_18], rdi
0x140012e8a  mov     [rsp-8+arg_8], edx
0x140012e8e  push    rbp
0x140012e8f  mov     rbp, rsp
0x140012e92  sub     rsp, 70h
0x140012e96  xorps   xmm0, xmm0
0x140012e99  mov     [rbp+KeyHandle], 0
0x140012ea1  mov     rdi, rcx
0x140012ea4  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012eab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012eaf  xor     eax, eax
0x140012eb1  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012eb5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012eb9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140012ebd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012ec1  call    cs:__imp_RtlInitUnicodeString
0x140012ec8  nop     dword ptr [rax+rax+00h]
0x140012ecd  lea     rax, [rbp+DestinationString]
0x140012ed1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012ed8  xorps   xmm0, xmm0
0x140012edb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012edf  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012ee3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012eeb  mov     edx, 2; DesiredAccess
0x140012ef0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140012ef7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140012efb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012f00  call    cs:__imp_ZwOpenKey
0x140012f07  nop     dword ptr [rax+rax+00h]
0x140012f0c  mov     ebx, eax
0x140012f0e  test    eax, eax
0x140012f10  js      short loc_140012F4E
0x140012f12  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140012f16  lea     rax, [rbp+arg_8]
0x140012f1a  mov     r9d, 4; Type
0x140012f20  xor     r8d, r8d; TitleIndex
0x140012f23  mov     [rsp+70h+DataSize], r9d; DataSize
0x140012f28  mov     rdx, rdi; ValueName
0x140012f2b  mov     [rsp+70h+Data], rax; Data
0x140012f30  call    cs:__imp_ZwSetValueKey
0x140012f37  nop     dword ptr [rax+rax+00h]
0x140012f3c  mov     rcx, [rbp+KeyHandle]; Handle
0x140012f40  mov     ebx, eax
0x140012f42  call    cs:__imp_ZwClose
0x140012f49  nop     dword ptr [rax+rax+00h]
0x140012f4e  lea     r11, [rsp+70h+var_s0]
0x140012f53  mov     eax, ebx
0x140012f55  mov     rbx, [r11+10h]
0x140012f59  mov     rdi, [r11+28h]
0x140012f5d  mov     rsp, r11
0x140012f60  pop     rbp
0x140012f61  retn
```
