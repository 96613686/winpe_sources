# HsmpOpenInstancesRegistryKey

- ea: `0x140042fc4`
- end: `0x1400430e4`
- name: `HsmpOpenInstancesRegistryKey`
- size: `288`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x14001e140`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004302e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004305a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004302e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004305a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043042`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004306e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140043042`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004306e`
- `ntoskrnl!ZwOpenKey` at `0x1400430b3`
- `ntoskrnl!ZwOpenKey` at `0x1400430b3`

## string_xrefs

- `0x140043006`: `\Registry\Machine\System\CurrentControlSet\Services\`

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
0x140042fc4  mov     [rsp-8+arg_10], rbx
0x140042fc9  mov     [rsp-8+arg_18], rdi
0x140042fce  push    rbp
0x140042fcf  lea     rbp, [rsp-0B0h]
0x140042fd7  sub     rsp, 1B0h
0x140042fde  mov     rax, cs:__security_cookie
0x140042fe5  xor     rax, rsp
0x140042fe8  mov     [rbp+0B0h+var_10], rax
0x140042fef  xorps   xmm0, xmm0
0x140042ff2  xor     eax, eax
0x140042ff4  movups  xmmword ptr [rsp+1B0h+Destination.Length], xmm0
0x140042ff9  mov     eax, 140h
0x140042ffe  mov     rdi, rdx
0x140043001  mov     [rsp+1B0h+Destination.MaximumLength], ax
0x140043006  lea     rdx, Source; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004300d  lea     rax, [rsp+1B0h+var_150]
0x140043012  mov     rbx, rcx
0x140043015  movups  xmmword ptr [rsp+1B0h+ObjectAttributes.ObjectName], xmm0
0x14004301a  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004301f  mov     [rsp+1B0h+Destination.Buffer], rax
0x140043024  movups  xmmword ptr [rsp+1B0h+ObjectAttributes.Length], xmm0
0x140043029  movups  xmmword ptr [rsp+1B0h+ObjectAttributes+1Ch], xmm0
0x14004302e  call    cs:__imp_RtlAppendUnicodeToString
0x140043035  nop     dword ptr [rax+rax+00h]
0x14004303a  mov     rdx, rbx; Source
0x14004303d  lea     rcx, [rsp+1B0h+Destination]; Destination
0x140043042  call    cs:__imp_RtlAppendUnicodeStringToString
0x140043049  nop     dword ptr [rax+rax+00h]
0x14004304e  lea     rdx, aInstances; "\\INSTANCES\\"
0x140043055  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004305a  call    cs:__imp_RtlAppendUnicodeToString
0x140043061  nop     dword ptr [rax+rax+00h]
0x140043066  mov     rdx, rbx; Source
0x140043069  lea     rcx, [rsp+1B0h+Destination]; Destination
0x14004306e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140043075  nop     dword ptr [rax+rax+00h]
0x14004307a  lea     rax, [rsp+1B0h+Destination]
0x14004307f  mov     [rsp+1B0h+ObjectAttributes.Length], 30h ; '0'
0x140043087  xorps   xmm0, xmm0
0x14004308a  mov     [rsp+1B0h+ObjectAttributes.ObjectName], rax
0x14004308f  lea     r8, [rsp+1B0h+ObjectAttributes]; ObjectAttributes
0x140043094  mov     [rsp+1B0h+ObjectAttributes.RootDirectory], 0
0x14004309d  mov     edx, 0F003Fh; DesiredAccess
0x1400430a2  mov     [rsp+1B0h+ObjectAttributes.Attributes], 240h
0x1400430aa  mov     rcx, rdi; KeyHandle
0x1400430ad  movdqu  xmmword ptr [rsp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400430b3  call    cs:__imp_ZwOpenKey
0x1400430ba  nop     dword ptr [rax+rax+00h]
0x1400430bf  mov     rcx, [rbp+0B0h+var_10]
0x1400430c6  xor     rcx, rsp; StackCookie
0x1400430c9  call    __security_check_cookie
0x1400430ce  lea     r11, [rsp+1B0h+var_s0]
0x1400430d6  mov     rbx, [r11+20h]
0x1400430da  mov     rdi, [r11+28h]
0x1400430de  mov     rsp, r11
0x1400430e1  pop     rbp
0x1400430e2  retn
```
