# FltpOpenServiceRootRegistryKey

- ea: `0x18006b1c0`
- end: `0x18006b2aa`
- name: `FltpOpenServiceRootRegistryKey`
- size: `234`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004e100`
- `0x18005224c`
- `0x18006aef0`

## callees

- `0x180024800`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006b21e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18006b21e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006b237`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006b237`
- `ntoskrnl!ZwOpenKey` at `0x18006b27c`
- `ntoskrnl!ZwOpenKey` at `0x18006b27c`

## string_xrefs

- `0x18006b1f6`: `\Registry\Machine\System\ControlSet001\Services\`

## pseudocode

```c
NTSTATUS __fastcall FltpOpenServiceRootRegistryKey(__int64 a1, void **a2)
{
  UNICODE_STRING Destination; // [rsp+20h] [rbp-198h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-188h] BYREF
  char v7; // [rsp+60h] [rbp-158h] BYREF

  *(_QWORD *)&Destination.Length = 20971520;
  Destination.Buffer = (wchar_t *)&v7;
  memset(&ObjectAttributes, 0, 44);
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\ControlSet001\\Services\\");
  RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 48) + 24LL));
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(a2, 0x20019u, &ObjectAttributes);
}

```

## disassembly

```asm
0x18006b1c0  mov     [rsp+arg_10], rbx
0x18006b1c5  push    rdi
0x18006b1c6  sub     rsp, 1B0h
0x18006b1cd  mov     rax, cs:__security_cookie
0x18006b1d4  xor     rax, rsp
0x18006b1d7  mov     [rsp+1B8h+var_18], rax
0x18006b1df  xorps   xmm0, xmm0
0x18006b1e2  xor     eax, eax
0x18006b1e4  movups  xmmword ptr [rsp+1B8h+Destination.Length], xmm0
0x18006b1e9  mov     eax, 140h
0x18006b1ee  mov     rdi, rdx
0x18006b1f1  mov     [rsp+1B8h+Destination.MaximumLength], ax
0x18006b1f6  lea     rdx, FltpServicesRegistryPathDesktop; "\\Registry\\Machine\\System\\ControlSet"...
0x18006b1fd  lea     rax, [rsp+1B8h+var_158]
0x18006b202  mov     rbx, rcx
0x18006b205  movups  xmmword ptr [rsp+1B8h+ObjectAttributes.ObjectName], xmm0
0x18006b20a  lea     rcx, [rsp+1B8h+Destination]; Destination
0x18006b20f  mov     [rsp+1B8h+Destination.Buffer], rax
0x18006b214  movups  xmmword ptr [rsp+1B8h+ObjectAttributes.Length], xmm0
0x18006b219  movups  xmmword ptr [rsp+1B8h+ObjectAttributes+1Ch], xmm0
0x18006b21e  call    cs:__imp_RtlAppendUnicodeToString
0x18006b225  nop     dword ptr [rax+rax+00h]
0x18006b22a  mov     rdx, [rbx+30h]
0x18006b22e  lea     rcx, [rsp+1B8h+Destination]; Destination
0x18006b233  add     rdx, 18h; Source
0x18006b237  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006b23e  nop     dword ptr [rax+rax+00h]
0x18006b243  lea     rax, [rsp+1B8h+Destination]
0x18006b248  mov     [rsp+1B8h+ObjectAttributes.Length], 30h ; '0'
0x18006b250  xorps   xmm0, xmm0
0x18006b253  mov     [rsp+1B8h+ObjectAttributes.ObjectName], rax
0x18006b258  lea     r8, [rsp+1B8h+ObjectAttributes]; ObjectAttributes
0x18006b25d  mov     [rsp+1B8h+ObjectAttributes.RootDirectory], 0
0x18006b266  mov     edx, 20019h; DesiredAccess
0x18006b26b  mov     [rsp+1B8h+ObjectAttributes.Attributes], 240h
0x18006b273  mov     rcx, rdi; KeyHandle
0x18006b276  movdqu  xmmword ptr [rsp+1B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006b27c  call    cs:__imp_ZwOpenKey
0x18006b283  nop     dword ptr [rax+rax+00h]
0x18006b288  mov     rcx, [rsp+1B8h+var_18]
0x18006b290  xor     rcx, rsp; StackCookie
0x18006b293  call    __security_check_cookie
0x18006b298  mov     rbx, [rsp+1B8h+arg_10]
0x18006b2a0  add     rsp, 1B0h
0x18006b2a7  pop     rdi
0x18006b2a8  retn
```
