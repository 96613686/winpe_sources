# RxpCheckAndDisableUACCollapsing

- ea: `0x140078e20`
- end: `0x140078f18`
- name: `RxpCheckAndDisableUACCollapsing`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14001d810`
- `0x140083c2c`

## callees

- `0x140025c20`
- `0x140049124`
- `0x140078e20`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140078e6b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140078e6b`
- `ntoskrnl!ZwClose` at `0x140078ef2`
- `ntoskrnl!ZwClose` at `0x140078ef2`
- `ntoskrnl!ZwOpenKey` at `0x140078eae`
- `ntoskrnl!ZwOpenKey` at `0x140078eae`

## string_xrefs

- `0x140078e3e`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Policies\System`
- `0x140078ed0`: `EnableLinkedConnections`

## pseudocode

```c
int RxpCheckAndDisableUACCollapsing()
{
  int result; // eax
  int v1; // [rsp+20h] [rbp-178h]
  ULONG v2; // [rsp+28h] [rbp-170h]
  void *KeyHandle; // [rsp+38h] [rbp-160h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-158h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-128h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RxGetUlongRegistryParameter(KeyHandle, v1, v2);
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x140078e20  push    rbx
0x140078e22  sub     rsp, 190h
0x140078e29  mov     rax, cs:__security_cookie
0x140078e30  xor     rax, rsp
0x140078e33  mov     [rsp+198h+var_18], rax
0x140078e3b  xorps   xmm0, xmm0
0x140078e3e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x140078e45  xor     ebx, ebx
0x140078e47  lea     rcx, [rsp+198h+DestinationString]; DestinationString
0x140078e4c  movups  xmmword ptr [rsp+198h+ObjectAttributes.ObjectName], xmm0
0x140078e51  xor     eax, eax
0x140078e53  mov     [rsp+198h+KeyHandle], rbx
0x140078e58  movups  xmmword ptr [rsp+198h+ObjectAttributes+1Ch], xmm0
0x140078e5d  mov     [rsp+198h+var_168], ebx
0x140078e61  movups  xmmword ptr [rsp+198h+DestinationString.Length], xmm0
0x140078e66  movups  xmmword ptr [rsp+198h+ObjectAttributes.Length], xmm0
0x140078e6b  call    cs:__imp_RtlInitUnicodeString
0x140078e72  nop     dword ptr [rax+rax+00h]
0x140078e77  lea     rax, [rsp+198h+DestinationString]
0x140078e7c  mov     [rsp+198h+ObjectAttributes.Length], 30h ; '0'
0x140078e84  xorps   xmm0, xmm0
0x140078e87  mov     [rsp+198h+ObjectAttributes.ObjectName], rax
0x140078e8c  lea     r8, [rsp+198h+ObjectAttributes]; ObjectAttributes
0x140078e91  mov     [rsp+198h+ObjectAttributes.RootDirectory], rbx
0x140078e96  mov     edx, 20019h; DesiredAccess
0x140078e9b  mov     [rsp+198h+ObjectAttributes.Attributes], 240h
0x140078ea3  lea     rcx, [rsp+198h+KeyHandle]; KeyHandle
0x140078ea8  movdqu  xmmword ptr [rsp+198h+ObjectAttributes.SecurityDescriptor], xmm0
0x140078eae  call    cs:__imp_ZwOpenKey
0x140078eb5  nop     dword ptr [rax+rax+00h]
0x140078eba  test    eax, eax
0x140078ebc  js      short loc_140078EFE
0x140078ebe  mov     rcx, [rsp+198h+KeyHandle]; KeyHandle
0x140078ec3  lea     r9, [rsp+198h+var_118]
0x140078ecb  lea     r8, [rsp+198h+var_168]
0x140078ed0  lea     rdx, aEnablelinkedco; "EnableLinkedConnections"
0x140078ed7  call    RxGetUlongRegistryParameter
0x140078edc  test    eax, eax
0x140078ede  js      short loc_140078EED
0x140078ee0  cmp     [rsp+198h+var_168], ebx
0x140078ee4  jz      short loc_140078EED
0x140078ee6  mov     cs:RxEnableLinkedConnections, 1
0x140078eed  mov     rcx, [rsp+198h+KeyHandle]; Handle
0x140078ef2  call    cs:__imp_ZwClose
0x140078ef9  nop     dword ptr [rax+rax+00h]
0x140078efe  mov     rcx, [rsp+198h+var_18]
0x140078f06  xor     rcx, rsp; StackCookie
0x140078f09  call    __security_check_cookie
0x140078f0e  add     rsp, 190h
0x140078f15  pop     rbx
0x140078f16  retn
```
