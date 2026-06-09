# ClfsRegistryQueryMiniNT

- ea: `0x14004e324`
- end: `0x14004e3cd`
- name: `ClfsRegistryQueryMiniNT`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004d968`

## callees

- `0x14004e324`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004e3ad`
- `ntoskrnl!ZwClose` at `0x14004e3ad`
- `ntoskrnl!ZwOpenKey` at `0x14004e396`
- `ntoskrnl!ZwOpenKey` at `0x14004e396`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e357`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e357`

## string_xrefs

- `0x14004e33c`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
bool ClfsRegistryQueryMiniNT()
{
  NTSTATUS v0; // ebx
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v0 >= 0;
}

```

## disassembly

```asm
0x14004e324  mov     [rsp-8+arg_8], rbx
0x14004e329  push    rbp
0x14004e32a  mov     rbp, rsp
0x14004e32d  sub     rsp, 60h
0x14004e331  xorps   xmm0, xmm0
0x14004e334  mov     [rbp+KeyHandle], 0
0x14004e33c  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004e343  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004e347  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14004e34b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14004e34f  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e353  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004e357  call    cs:__imp_RtlInitUnicodeString
0x14004e35e  nop     dword ptr [rax+rax+00h]
0x14004e363  lea     rax, [rbp+DestinationString]
0x14004e367  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14004e36e  xorps   xmm0, xmm0
0x14004e371  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14004e375  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004e379  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14004e381  mov     edx, 20019h; DesiredAccess
0x14004e386  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14004e38d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14004e391  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e396  call    cs:__imp_ZwOpenKey
0x14004e39d  nop     dword ptr [rax+rax+00h]
0x14004e3a2  mov     rcx, [rbp+KeyHandle]; Handle
0x14004e3a6  mov     ebx, eax
0x14004e3a8  test    rcx, rcx
0x14004e3ab  jz      short loc_14004E3B9
0x14004e3ad  call    cs:__imp_ZwClose
0x14004e3b4  nop     dword ptr [rax+rax+00h]
0x14004e3b9  shr     ebx, 1Fh
0x14004e3bc  xor     bl, 1
0x14004e3bf  mov     al, bl
0x14004e3c1  mov     rbx, [rsp+60h+arg_8]
0x14004e3c6  add     rsp, 60h
0x14004e3ca  pop     rbp
0x14004e3cb  retn
```
