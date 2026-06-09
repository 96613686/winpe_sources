# RegLinkExists(HKEY__ *,ushort const *)

- ea: `0x18004f288`
- end: `0x18004f384`
- name: `?RegLinkExists@@YAHPEAUHKEY__@@PEBG@Z`
- size: `252`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f564`

## callees

- `0x1800292fc`
- `0x18004f288`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004f2fa`
- `ntdll!NtOpenKey` at `0x18004f2fa`
- `ntdll!RtlInitUnicodeString` at `0x18004f2b9`
- `ntdll!RtlInitUnicodeString` at `0x18004f31c`
- `ntdll!RtlInitUnicodeString` at `0x18004f2b9`
- `ntdll!RtlInitUnicodeString` at `0x18004f31c`
- `ntdll!NtQueryValueKey` at `0x18004f347`
- `ntdll!NtQueryValueKey` at `0x18004f347`

## string_xrefs

- `0x18004f30d`: `SymbolicLinkValue`

## pseudocode

```c
_BOOL8 __fastcall RegLinkExists(HKEY a1, const unsigned __int16 *a2)
{
  BOOL v3; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+10h] BYREF
  const unsigned __int16 *ResultLength; // [rsp+98h] [rbp+18h] BYREF

  ResultLength = a2;
  DestinationString = 0;
  v3 = 0;
  RtlInitUnicodeString(&DestinationString, L"Software\\Classes\\");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 320;
  ObjectAttributes.RootDirectory = a1;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes) >= 0 )
  {
    ValueName = 0;
    RtlInitUnicodeString(&ValueName, L"SymbolicLinkValue");
    LODWORD(ResultLength) = 0;
    if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, 0, (PULONG)&ResultLength) != -1073741772 )
      v3 = (_DWORD)ResultLength != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x18004f288  mov     [rsp-8+arg_10], rbx
0x18004f28d  mov     [rsp-8+arg_18], rdi
0x18004f292  mov     [rsp-8+arg_8], rdx
0x18004f297  push    rbp
0x18004f298  mov     rbp, rsp
0x18004f29b  sub     rsp, 80h
0x18004f2a2  mov     rbx, rcx
0x18004f2a5  lea     rdx, SourceString; "Software\\Classes\\"
0x18004f2ac  xorps   xmm0, xmm0
0x18004f2af  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004f2b3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004f2b7  xor     edi, edi
0x18004f2b9  call    cs:__imp_RtlInitUnicodeString
0x18004f2c0  nop     dword ptr [rax+rax+00h]
0x18004f2c5  lea     rax, [rbp+DestinationString]
0x18004f2c9  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004f2d1  xorps   xmm0, xmm0
0x18004f2d4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004f2d8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004f2dc  mov     qword ptr [rbp+ObjectAttributes.Attributes], 140h
0x18004f2e4  mov     edx, 2000000h; DesiredAccess
0x18004f2e9  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18004f2ed  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004f2f1  mov     [rbp+KeyHandle], rdi
0x18004f2f5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004f2fa  call    cs:__imp_NtOpenKey
0x18004f301  nop     dword ptr [rax+rax+00h]
0x18004f306  test    eax, eax
0x18004f308  js      short loc_18004F363
0x18004f30a  xorps   xmm0, xmm0
0x18004f30d  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x18004f314  lea     rcx, [rbp+ValueName]; DestinationString
0x18004f318  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18004f31c  call    cs:__imp_RtlInitUnicodeString
0x18004f323  nop     dword ptr [rax+rax+00h]
0x18004f328  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004f32c  lea     rax, [rbp+arg_8]
0x18004f330  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18004f335  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18004f339  xor     r9d, r9d; KeyValueInformation
0x18004f33c  mov     [rsp+80h+Length], edi; Length
0x18004f340  lea     rdx, [rbp+ValueName]; ValueName
0x18004f344  mov     dword ptr [rbp+arg_8], edi
0x18004f347  call    cs:__imp_NtQueryValueKey
0x18004f34e  nop     dword ptr [rax+rax+00h]
0x18004f353  cmp     eax, 0C0000034h
0x18004f358  jz      short loc_18004F363
0x18004f35a  cmp     dword ptr [rbp+arg_8], edi
0x18004f35d  lea     eax, [rdi+1]
0x18004f360  cmova   edi, eax
0x18004f363  lea     rcx, [rbp+KeyHandle]
0x18004f367  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f36c  lea     r11, [rsp+80h+var_s0]
0x18004f374  mov     eax, edi
0x18004f376  mov     rbx, [r11+20h]
0x18004f37a  mov     rdi, [r11+28h]
0x18004f37e  mov     rsp, r11
0x18004f381  pop     rbp
0x18004f382  retn
```
