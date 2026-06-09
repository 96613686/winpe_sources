# _dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateFormat__

- ea: `0x140002db0`
- end: `0x140002de1`
- name: `_dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateFormat__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002db4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140002db4`

## string_xrefs

- `0x140002dc9`: `OSData\Software\Microsoft\DeclaredConfiguration\HostOS\Results\Config\enrollments\%s\%s\state`
- `0x140002dc2`: `Software\Microsoft\DeclaredConfiguration\HostOS\Results\Config\enrollments\%s\%s\state`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateFormat__(__int64 a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Config\\enrollments\\%s\\%s\\state";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Results\\Config\\enrollments\\%s\\%s\\state";
  qword_140085160 = (__int64)v2;
  return result;
}

```

## disassembly

```asm
0x140002db0  sub     rsp, 28h
0x140002db4  call    cs:__imp_RtlIsStateSeparationEnabled
0x140002dbb  nop     dword ptr [rax+rax+00h]
0x140002dc0  test    al, al
0x140002dc2  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\DeclaredConfigurat"...
0x140002dc9  lea     rcx, aOsdataSoftware_14; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140002dd0  cmovz   rcx, rdx
0x140002dd4  mov     cs:qword_140085160, rcx
0x140002ddb  add     rsp, 28h
0x140002ddf  retn
```
