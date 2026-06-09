# _dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__

- ea: `0x140002d30`
- end: `0x140002d61`
- name: `_dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002d34`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140002d34`

## string_xrefs

- `0x140002d42`: `Software\Microsoft\DeclaredConfiguration\HostOS\Results\Containers\%s\Config\enrollments\%s\%s\state\%s\%s`
- `0x140002d49`: `OSData\Software\Microsoft\DeclaredConfiguration\HostOS\Results\Containers\%s\Config\enrollments\%s\%s\state\%s\%s`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__(
        __int64 a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Containers\\%s\\Config\\enrollments\\%s\\%s\\state\\%s\\%s";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Containers\\%s\\Config\\enrollments\\%s\\%s\\state\\%s\\%s";
  qword_140085170 = (__int64)v2;
  return result;
}

```

## disassembly

```asm
0x140002d30  sub     rsp, 28h
0x140002d34  call    cs:__imp_RtlIsStateSeparationEnabled
0x140002d3b  nop     dword ptr [rax+rax+00h]
0x140002d40  test    al, al
0x140002d42  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\DeclaredConfigurat"...
0x140002d49  lea     rcx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140002d50  cmovz   rcx, rdx
0x140002d54  mov     cs:qword_140085170, rcx
0x140002d5b  add     rsp, 28h
0x140002d5f  retn
```
