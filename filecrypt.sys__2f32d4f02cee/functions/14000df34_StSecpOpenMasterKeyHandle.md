# StSecpOpenMasterKeyHandle

- ea: `0x14000df34`
- end: `0x14000dff1`
- name: `StSecpOpenMasterKeyHandle`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e104`
- `0x14000e280`

## callees

- `0x14000df34`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000df6d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000df6d`
- `ntoskrnl!ZwOpenKey` at `0x14000dfac`
- `ntoskrnl!ZwOpenKey` at `0x14000dfac`
- `ntoskrnl!ZwClose` at `0x14000dfd0`
- `ntoskrnl!ZwClose` at `0x14000dfd0`

## string_xrefs

- `0x14000df49`: `\REGISTRY\MACHINE\Software\Microsoft\StorageSec\Encrypt`

## pseudocode

```c
__int64 __fastcall StSecpOpenMasterKeyHandle(void **a1)
{
  NTSTATUS v2; // eax
  void *v3; // rcx
  unsigned int v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\Software\\Microsoft\\StorageSec\\Encrypt");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  v3 = KeyHandle;
  v4 = v2;
  if ( v2 >= 0 )
  {
    *a1 = KeyHandle;
    v3 = 0;
    KeyHandle = 0;
  }
  if ( v3 )
    ZwClose(v3);
  return v4;
}

```

## disassembly

```asm
0x14000df34  mov     [rsp-8+arg_0], rbx
0x14000df39  mov     [rsp-8+arg_10], rdi
0x14000df3e  push    rbp
0x14000df3f  mov     rbp, rsp
0x14000df42  sub     rsp, 60h
0x14000df46  xorps   xmm0, xmm0
0x14000df49  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\Software\\Microsof"...
0x14000df50  mov     rdi, rcx
0x14000df53  xor     eax, eax
0x14000df55  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000df59  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000df5d  mov     [rbp+KeyHandle], rax
0x14000df61  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000df65  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000df69  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000df6d  call    cs:__imp_RtlInitUnicodeString
0x14000df74  nop     dword ptr [rax+rax+00h]
0x14000df79  lea     rax, [rbp+DestinationString]
0x14000df7d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000df84  xorps   xmm0, xmm0
0x14000df87  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000df8b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000df8f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000df97  mov     edx, 0F003Fh; DesiredAccess
0x14000df9c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000dfa3  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000dfa7  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000dfac  call    cs:__imp_ZwOpenKey
0x14000dfb3  nop     dword ptr [rax+rax+00h]
0x14000dfb8  mov     rcx, [rbp+KeyHandle]
0x14000dfbc  mov     ebx, eax
0x14000dfbe  test    eax, eax
0x14000dfc0  js      short loc_14000DFCB
0x14000dfc2  mov     [rdi], rcx
0x14000dfc5  xor     ecx, ecx; Handle
0x14000dfc7  mov     [rbp+KeyHandle], rcx
0x14000dfcb  test    rcx, rcx
0x14000dfce  jz      short loc_14000DFDC
0x14000dfd0  call    cs:__imp_ZwClose
0x14000dfd7  nop     dword ptr [rax+rax+00h]
0x14000dfdc  lea     r11, [rsp+60h+var_s0]
0x14000dfe1  mov     eax, ebx
0x14000dfe3  mov     rbx, [r11+10h]
0x14000dfe7  mov     rdi, [r11+20h]
0x14000dfeb  mov     rsp, r11
0x14000dfee  pop     rbp
0x14000dfef  retn
```
