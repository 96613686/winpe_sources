# HsmpOpenInstancesRegistryKey

- ea: `0x1400430b4`
- end: `0x1400431d4`
- name: `HsmpOpenInstancesRegistryKey`
- size: `288`
- prototype: `NTSTATUS __fastcall(PCUNICODE_STRING Source, PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004311e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004314a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004311e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004314a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043132`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004315e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043132`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004315e`
- `ntoskrnl!ZwOpenKey` at `0x1400431a3`
- `ntoskrnl!ZwOpenKey` at `0x1400431a3`

## string_xrefs

- `0x1400430f6`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
NTSTATUS __fastcall HsmpOpenInstancesRegistryKey(PCUNICODE_STRING Source, PHANDLE KeyHandle)
{
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-E0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-D0h] BYREF
  char v7; // [rsp+60h] [rbp-A0h] BYREF

  *(_QWORD *)&Destination.Length = 20971520;
  Destination.Buffer = (PWSTR)&v7;
  memset(&ObjectAttributes, 0, 44);
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
  RtlAppendUnicodeStringToString(&Destination, Source);
  RtlAppendUnicodeToString(&Destination, L"\\INSTANCES\\");
  RtlAppendUnicodeStringToString(&Destination, Source);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(KeyHandle, 0xF003Fu, &ObjectAttributes);
}

```

## disassembly

```asm
0x1400430b4  mov     [rsp-8+arg_10], rbx
0x1400430b9  mov     [rsp-8+arg_18], rdi
0x1400430be  push    rbp
0x1400430bf  lea     rbp, [rsp-0B0h]
0x1400430c7  sub     rsp, 1B0h
0x1400430ce  mov     rax, cs:__security_cookie
0x1400430d5  xor     rax, rsp
0x1400430d8  mov     [rbp+0B0h+var_10], rax
0x1400430df  xorps   xmm0, xmm0
0x1400430e2  xor     eax, eax
0x1400430e4  movups  xmmword ptr [rsp+1B0h+Destination.Length], xmm0
0x1400430e9  mov     eax, 140h
0x1400430ee  mov     rdi, rdx
0x1400430f1  mov     [rsp+1B0h+Destination.MaximumLength], ax
0x1400430f6  lea     rdx, Source; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400430fd  lea     rax, [rsp+1B0h+var_150]
0x140043102  mov     rbx, rcx
0x140043105  movups  xmmword ptr [rsp+1B0h+ObjectAttributes.ObjectName], xmm0
0x14004310a  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004310f  mov     [rsp+1B0h+Destination.Buffer], rax
0x140043114  movups  xmmword ptr [rsp+1B0h+ObjectAttributes.Length], xmm0
0x140043119  movups  xmmword ptr [rsp+1B0h+ObjectAttributes+1Ch], xmm0
0x14004311e  call    cs:__imp_RtlAppendUnicodeToString
0x140043125  nop     dword ptr [rax+rax+00h]
0x14004312a  mov     rdx, rbx; Source
0x14004312d  lea     rcx, [rsp+1B0h+Destination]; Destination
0x140043132  call    cs:__imp_RtlAppendUnicodeStringToString
0x140043139  nop     dword ptr [rax+rax+00h]
0x14004313e  lea     rdx, aInstances; "\\INSTANCES\\"
0x140043145  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004314a  call    cs:__imp_RtlAppendUnicodeToString
0x140043151  nop     dword ptr [rax+rax+00h]
0x140043156  mov     rdx, rbx; Source
0x140043159  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004315e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140043165  nop     dword ptr [rax+rax+00h]
0x14004316a  lea     rax, [rsp+1B0h+Destination]
0x14004316f  mov     [rsp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x140043177  xorps   xmm0, xmm0
0x14004317a  mov     [rsp+1B0h+ObjectAttributes.ObjectName], rax
0x14004317f  lea     r8, [rsp+1B0h+ObjectAttributes]; ObjectAttributes
0x140043184  mov     [rsp+1B0h+ObjectAttributes.RootDirectory], 0
0x14004318d  mov     edx, 0F003Fh; DesiredAccess
0x140043192  mov     [rsp+1B0h+ObjectAttributes.Attributes], 240h
0x14004319a  mov     rcx, rdi; KeyHandle
0x14004319d  movdqu  xmmword ptr [rsp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400431a3  call    cs:__imp_ZwOpenKey
0x1400431aa  nop     dword ptr [rax+rax+00h]
0x1400431af  mov     rcx, [rbp+0B0h+var_10]
0x1400431b6  xor     rcx, rsp; StackCookie
0x1400431b9  call    __security_check_cookie
0x1400431be  lea     r11, [rsp+1B0h+var_s0]
0x1400431c6  mov     rbx, [r11+20h]
0x1400431ca  mov     rdi, [r11+28h]
0x1400431ce  mov     rsp, r11
0x1400431d1  pop     rbp
0x1400431d2  retn
```
