# RegLinkExists(HKEY__ *,ushort const *)

- ea: `0x18004c2a8`
- end: `0x18004c38b`
- name: `?RegLinkExists@@YAHPEAUHKEY__@@PEBG@Z`
- size: `227`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c554`

## callees

- `0x1800272ec`
- `0x18004c2a8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004c314`
- `ntdll!NtOpenKey` at `0x18004c314`
- `ntdll!RtlInitUnicodeString` at `0x18004c2d9`
- `ntdll!RtlInitUnicodeString` at `0x18004c330`
- `ntdll!RtlInitUnicodeString` at `0x18004c2d9`
- `ntdll!RtlInitUnicodeString` at `0x18004c330`
- `ntdll!NtQueryValueKey` at `0x18004c355`
- `ntdll!NtQueryValueKey` at `0x18004c355`

## string_xrefs

- `0x18004c321`: `SymbolicLinkValue`

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
0x18004c2a8  mov     [rsp-8+arg_10], rbx
0x18004c2ad  mov     [rsp-8+arg_18], rdi
0x18004c2b2  mov     [rsp-8+arg_8], rdx
0x18004c2b7  push    rbp
0x18004c2b8  mov     rbp, rsp
0x18004c2bb  sub     rsp, 80h
0x18004c2c2  mov     rbx, rcx
0x18004c2c5  lea     rdx, aSoftwareClasse; "Software\\Classes\\"
0x18004c2cc  xorps   xmm0, xmm0
0x18004c2cf  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c2d3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004c2d7  xor     edi, edi
0x18004c2d9  call    cs:__imp_RtlInitUnicodeString
0x18004c2df  lea     rax, [rbp+DestinationString]
0x18004c2e3  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004c2eb  xorps   xmm0, xmm0
0x18004c2ee  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004c2f2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004c2f6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 140h
0x18004c2fe  mov     edx, 2000000h; DesiredAccess
0x18004c303  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18004c307  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c30b  mov     [rbp+KeyHandle], rdi
0x18004c30f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004c314  call    cs:__imp_NtOpenKey
0x18004c31a  test    eax, eax
0x18004c31c  js      short loc_18004C36B
0x18004c31e  xorps   xmm0, xmm0
0x18004c321  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x18004c328  lea     rcx, [rbp+ValueName]; DestinationString
0x18004c32c  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18004c330  call    cs:__imp_RtlInitUnicodeString
0x18004c336  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004c33a  lea     rax, [rbp+arg_8]
0x18004c33e  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18004c343  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18004c347  xor     r9d, r9d; KeyValueInformation
0x18004c34a  mov     [rsp+80h+Length], edi; Length
0x18004c34e  lea     rdx, [rbp+ValueName]; ValueName
0x18004c352  mov     dword ptr [rbp+arg_8], edi
0x18004c355  call    cs:__imp_NtQueryValueKey
0x18004c35b  cmp     eax, 0C0000034h
0x18004c360  jz      short loc_18004C36B
0x18004c362  cmp     dword ptr [rbp+arg_8], edi
0x18004c365  lea     eax, [rdi+1]
0x18004c368  cmova   edi, eax
0x18004c36b  lea     rcx, [rbp+KeyHandle]
0x18004c36f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c374  lea     r11, [rsp+80h+var_s0]
0x18004c37c  mov     eax, edi
0x18004c37e  mov     rbx, [r11+20h]
0x18004c382  mov     rdi, [r11+28h]
0x18004c386  mov     rsp, r11
0x18004c389  pop     rbp
0x18004c38a  retn
```
