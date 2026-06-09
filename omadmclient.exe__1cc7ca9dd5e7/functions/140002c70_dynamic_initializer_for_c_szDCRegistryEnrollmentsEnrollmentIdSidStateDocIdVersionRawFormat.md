# _dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateDocIdVersionRawFormat__

- ea: `0x140002c70`
- end: `0x140002ca1`
- name: `_dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateDocIdVersionRawFormat__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002c74`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140002c74`

## string_xrefs

- `0x140002c82`: `Software\Microsoft\DeclaredConfiguration\HostOS\Config\enrollments\%s\%s\state\%s\%s\raw`
- `0x140002c89`: `OSData\Software\Microsoft\DeclaredConfiguration\HostOS\Config\enrollments\%s\%s\state\%s\%s\raw`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateDocIdVersionRawFormat__(
        __int64 a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Config\\enrollments\\%s\\%s\\state\\%s\\%s\\raw";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Config\\enrollments\\%s\\%s\\state\\%s\\%s\\raw";
  qword_140085180 = (__int64)v2;
  return result;
}

```

## disassembly

```asm
0x140002c70  sub     rsp, 28h
0x140002c74  call    cs:__imp_RtlIsStateSeparationEnabled
0x140002c7b  nop     dword ptr [rax+rax+00h]
0x140002c80  test    al, al
0x140002c82  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\DeclaredConfigurat"...
0x140002c89  lea     rcx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140002c90  cmovz   rcx, rdx
0x140002c94  mov     cs:qword_140085180, rcx
0x140002c9b  add     rsp, 28h
0x140002c9f  retn
```
