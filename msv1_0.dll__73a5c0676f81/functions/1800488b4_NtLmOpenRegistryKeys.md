# NtLmOpenRegistryKeys

- ea: `0x1800488b4`
- end: `0x1800489fe`
- name: `NtLmOpenRegistryKeys`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004a1c0`

## callees

- `0x1800488b4`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004897a`
- `ntdll!NtOpenKey` at `0x1800489e3`
- `ntdll!NtOpenKey` at `0x18004897a`
- `ntdll!NtOpenKey` at `0x1800489e3`
- `ntdll!RtlInitUnicodeString` at `0x180048941`
- `ntdll!RtlInitUnicodeString` at `0x18004899a`
- `ntdll!RtlInitUnicodeString` at `0x180048941`
- `ntdll!RtlInitUnicodeString` at `0x18004899a`

## string_xrefs

- `0x1800488e0`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`
- `0x180048988`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa\Msv1_0`

## pseudocode

```c
NTSTATUS NtLmOpenRegistryKeys()
{
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  NtLmGlobalLmProtocolSupported = 4;
  NtLmGlobalMinimumClientSecurity = 0x20000000;
  NtLmGlobalMinimumServerSecurity = 0x20000000;
  NtLmGlobalLocalSystemUseMachineSecrets = 1;
  DestinationString = 0;
  NtLmGlobalOldPasswordAllowedPeriod = 5;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtLmGlobalRequireNtlm2 = 0;
  NtLmGlobalDatagramUse128BitEncryption = 0;
  NtLmGlobalDatagramUse56BitEncryption = 0;
  NtLmGlobalLsaKey = 0;
  NtLmGlobalLsaMsv1_0Key = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    NtLmGlobalLsaKey = (HKEY)KeyHandle;
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa\\Msv1_0");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = NtOpenKey(&KeyHandle, (dword_180087A84 & 0x20) != 0 ? 131103 : 131097, &ObjectAttributes);
    if ( result >= 0 )
    {
      result = (int)KeyHandle;
      NtLmGlobalLsaMsv1_0Key = (HKEY)KeyHandle;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800488b4  push    rbp
0x1800488b6  mov     rbp, rsp
0x1800488b9  sub     rsp, 60h
0x1800488bd  xorps   xmm1, xmm1
0x1800488c0  mov     [rbp+KeyHandle], 0
0x1800488c8  mov     eax, 20000000h
0x1800488cd  mov     cs:NtLmGlobalLmProtocolSupported, 4
0x1800488d7  xorps   xmm0, xmm0
0x1800488da  mov     cs:NtLmGlobalMinimumClientSecurity, eax
0x1800488e0  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800488e7  mov     cs:NtLmGlobalMinimumServerSecurity, eax
0x1800488ed  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800488f1  mov     cs:NtLmGlobalLocalSystemUseMachineSecrets, 1
0x1800488fb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800488ff  mov     cs:NtLmGlobalOldPasswordAllowedPeriod, 5
0x18004890a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x18004890e  mov     cs:NtLmGlobalRequireNtlm2, 0
0x180048915  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180048919  mov     cs:NtLmGlobalDatagramUse128BitEncryption, 0
0x180048920  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180048924  mov     cs:NtLmGlobalDatagramUse56BitEncryption, 0
0x18004892b  mov     cs:NtLmGlobalLsaKey, 0
0x180048936  mov     cs:NtLmGlobalLsaMsv1_0Key, 0
0x180048941  call    cs:__imp_RtlInitUnicodeString
0x180048947  lea     rax, [rbp+DestinationString]
0x18004894b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180048952  xorps   xmm0, xmm0
0x180048955  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180048959  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004895d  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180048965  mov     edx, 20019h; DesiredAccess
0x18004896a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180048971  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180048975  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004897a  call    cs:__imp_NtOpenKey
0x180048980  test    eax, eax
0x180048982  js      short loc_1800489F8
0x180048984  mov     rax, [rbp+KeyHandle]
0x180048988  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x18004898f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180048993  mov     cs:NtLmGlobalLsaKey, rax
0x18004899a  call    cs:__imp_RtlInitUnicodeString
0x1800489a0  lea     rax, [rbp+DestinationString]
0x1800489a4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800489ab  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800489af  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800489b3  mov     eax, cs:dword_180087A84
0x1800489b9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800489bd  and     al, 20h
0x1800489bf  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800489c7  neg     al
0x1800489c9  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800489d0  xorps   xmm0, xmm0
0x1800489d3  sbb     edx, edx
0x1800489d5  and     edx, 6
0x1800489d8  add     edx, 20019h; DesiredAccess
0x1800489de  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800489e3  call    cs:__imp_NtOpenKey
0x1800489e9  test    eax, eax
0x1800489eb  js      short loc_1800489F8
0x1800489ed  mov     rax, [rbp+KeyHandle]
0x1800489f1  mov     cs:NtLmGlobalLsaMsv1_0Key, rax
0x1800489f8  add     rsp, 60h
0x1800489fc  pop     rbp
0x1800489fd  retn
```
