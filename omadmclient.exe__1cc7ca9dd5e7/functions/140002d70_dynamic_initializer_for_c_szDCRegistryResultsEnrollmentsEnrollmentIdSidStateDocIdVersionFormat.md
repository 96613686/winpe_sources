# _dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__

- ea: `0x140002d70`
- end: `0x140002da1`
- name: `_dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002d74`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140002d74`

## string_xrefs

- `0x140002d89`: `OSData\Software\Microsoft\DeclaredConfiguration\HostOS\Results\Config\enrollments\%s\%s\state\%s\%s`
- `0x140002d82`: `Software\Microsoft\DeclaredConfiguration\HostOS\Results\Config\enrollments\%s\%s\state\%s\%s`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__(
        __int64 a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Config\\enrollments\\%s\\%s\\state\\%s\\%s";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Config\\enrollments\\%s\\%s\\state\\%s\\%s";
  qword_140085178 = (__int64)v2;
  return result;
}

```

## disassembly

```asm
0x140002d70  sub     rsp, 28h
0x140002d74  call    cs:__imp_RtlIsStateSeparationEnabled
0x140002d7b  nop     dword ptr [rax+rax+00h]
0x140002d80  test    al, al
0x140002d82  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\DeclaredConfigurat"...
0x140002d89  lea     rcx, aOsdataSoftware_10; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140002d90  cmovz   rcx, rdx
0x140002d94  mov     cs:qword_140085178, rcx
0x140002d9b  add     rsp, 28h
0x140002d9f  retn
```
