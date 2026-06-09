# MRxSmbEvaluateRegistryRoutingParameters

- ea: `0x140091d40`
- end: `0x140091df7`
- name: `MRxSmbEvaluateRegistryRoutingParameters`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140028fec`

## callees

- `0x140091d40`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140091dba`
- `ntoskrnl!ZwOpenKey` at `0x140091dba`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091d77`
- `ntoskrnl!RtlInitUnicodeString` at `0x140091d77`
- `ntoskrnl!ZwClose` at `0x140091de4`
- `ntoskrnl!ZwClose` at `0x140091de4`

## pseudocode

```c
int __fastcall MRxSmbEvaluateRegistryRoutingParameters(void *a1)
{
  int result; // eax
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+8h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Routing");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    byte_14007D240 = 1;
    return ZwClose(KeyHandle);
  }
  else
  {
    byte_14007D240 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140091d40  push    rbx
0x140091d42  sub     rsp, 60h
0x140091d46  xorps   xmm0, xmm0
0x140091d49  mov     [rsp+68h+KeyHandle], 0
0x140091d52  mov     rbx, rcx
0x140091d55  lea     rdx, aRouting; "Routing"
0x140091d5c  movups  xmmword ptr [rsp+68h+ObjectAttributes.ObjectName], xmm0
0x140091d61  xor     eax, eax
0x140091d63  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140091d68  movups  xmmword ptr [rsp+68h+ObjectAttributes+1Ch], xmm0
0x140091d6d  movups  xmmword ptr [rsp+68h+ObjectAttributes.Length], xmm0
0x140091d72  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140091d77  call    cs:__imp_RtlInitUnicodeString
0x140091d7e  nop     dword ptr [rax+rax+00h]
0x140091d83  lea     rax, [rsp+68h+DestinationString]
0x140091d88  mov     [rsp+68h+ObjectAttributes.Length], 30h ; '0'
0x140091d90  xorps   xmm0, xmm0
0x140091d93  mov     [rsp+68h+ObjectAttributes.ObjectName], rax
0x140091d98  lea     r8, [rsp+68h+ObjectAttributes]; ObjectAttributes
0x140091d9d  mov     [rsp+68h+ObjectAttributes.RootDirectory], rbx
0x140091da2  mov     edx, 20019h; DesiredAccess
0x140091da7  mov     [rsp+68h+ObjectAttributes.Attributes], 240h
0x140091daf  lea     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x140091db4  movdqu  xmmword ptr [rsp+68h+ObjectAttributes.SecurityDescriptor], xmm0
0x140091dba  call    cs:__imp_ZwOpenKey
0x140091dc1  nop     dword ptr [rax+rax+00h]
0x140091dc6  test    eax, eax
0x140091dc8  jns     short loc_140091DD8
0x140091dca  mov     cs:byte_14007D240, 0
0x140091dd1  add     rsp, 60h
0x140091dd5  pop     rbx
0x140091dd6  retn
0x140091dd8  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x140091ddd  mov     cs:byte_14007D240, 1
0x140091de4  call    cs:__imp_ZwClose
0x140091deb  nop     dword ptr [rax+rax+00h]
0x140091df0  add     rsp, 60h
0x140091df4  pop     rbx
0x140091df5  retn
```
