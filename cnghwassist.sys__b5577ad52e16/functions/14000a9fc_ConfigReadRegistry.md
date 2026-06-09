# ConfigReadRegistry

- ea: `0x14000a9fc`
- end: `0x14000ab07`
- name: `ConfigReadRegistry`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000b1c0`

## callees

- `0x14000a9fc`
- `0x14000ab10`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000aa94`
- `ntoskrnl!ZwClose` at `0x14000aae8`
- `ntoskrnl!ZwClose` at `0x14000aa94`
- `ntoskrnl!ZwClose` at `0x14000aae8`
- `ntoskrnl!ZwOpenKey` at `0x14000aa6d`
- `ntoskrnl!ZwOpenKey` at `0x14000aa6d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000aa34`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000aa34`

## string_xrefs

- `0x14000aa11`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\CngHwAssist\Parameters`

## pseudocode

```c
int ConfigReadRegistry()
{
  void *v0; // rbx
  int result; // eax
  int v2; // edi
  void *v3; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  v0 = 0;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\CngHwAssist\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v2 = result;
  if ( result < 0 )
  {
    v3 = KeyHandle;
  }
  else
  {
    v0 = KeyHandle;
    v3 = 0;
    KeyHandle = 0;
  }
  if ( v3 )
    result = ZwClose(v3);
  if ( v2 >= 0 )
  {
    ConfigReadRegistryOne(v0);
    ConfigReadRegistryOne(v0);
    result = ConfigReadRegistryOne(v0);
  }
  if ( v0 )
    return ZwClose(v0);
  return result;
}

```

## disassembly

```asm
0x14000a9fc  mov     [rsp-8+arg_8], rbx
0x14000aa01  mov     [rsp-8+arg_10], rdi
0x14000aa06  push    rbp
0x14000aa07  mov     rbp, rsp
0x14000aa0a  sub     rsp, 60h
0x14000aa0e  xorps   xmm0, xmm0
0x14000aa11  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14000aa18  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000aa1c  xor     ebx, ebx
0x14000aa1e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000aa22  xor     eax, eax
0x14000aa24  mov     [rbp+KeyHandle], rbx
0x14000aa28  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000aa2c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000aa30  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000aa34  call    cs:__imp_RtlInitUnicodeString
0x14000aa3b  nop     dword ptr [rax+rax+00h]
0x14000aa40  lea     rax, [rbp+DestinationString]
0x14000aa44  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000aa4b  xorps   xmm0, xmm0
0x14000aa4e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000aa52  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000aa56  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x14000aa5a  lea     edx, [rbx+1]; DesiredAccess
0x14000aa5d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000aa64  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000aa68  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000aa6d  call    cs:__imp_ZwOpenKey
0x14000aa74  nop     dword ptr [rax+rax+00h]
0x14000aa79  mov     edi, eax
0x14000aa7b  test    eax, eax
0x14000aa7d  js      short loc_14000AA8B
0x14000aa7f  mov     rbx, [rbp+KeyHandle]
0x14000aa83  xor     ecx, ecx
0x14000aa85  mov     [rbp+KeyHandle], rcx
0x14000aa89  jmp     short loc_14000AA8F
0x14000aa8b  mov     rcx, [rbp+KeyHandle]; Handle
0x14000aa8f  test    rcx, rcx
0x14000aa92  jz      short loc_14000AAA0
0x14000aa94  call    cs:__imp_ZwClose
0x14000aa9b  nop     dword ptr [rax+rax+00h]
0x14000aaa0  test    edi, edi
0x14000aaa2  js      short loc_14000AAE0
0x14000aaa4  xor     r8d, r8d
0x14000aaa7  lea     rdx, qword_140006548
0x14000aaae  mov     rcx, rbx; KeyHandle
0x14000aab1  call    ConfigReadRegistryOne
0x14000aab6  mov     r8d, 1
0x14000aabc  lea     rdx, aLp; "_LP_"
0x14000aac3  mov     rcx, rbx; KeyHandle
0x14000aac6  call    ConfigReadRegistryOne
0x14000aacb  mov     r8d, 2
0x14000aad1  lea     rdx, aVlp; "_VLP_"
0x14000aad8  mov     rcx, rbx; KeyHandle
0x14000aadb  call    ConfigReadRegistryOne
0x14000aae0  test    rbx, rbx
0x14000aae3  jz      short loc_14000AAF4
0x14000aae5  mov     rcx, rbx; Handle
0x14000aae8  call    cs:__imp_ZwClose
0x14000aaef  nop     dword ptr [rax+rax+00h]
0x14000aaf4  lea     r11, [rsp+60h+var_s0]
0x14000aaf9  mov     rbx, [r11+18h]
0x14000aafd  mov     rdi, [r11+20h]
0x14000ab01  mov     rsp, r11
0x14000ab04  pop     rbp
0x14000ab05  retn
```
