# _dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateFormat__

- ea: `0x140002cb0`
- end: `0x140002ce1`
- name: `_dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateFormat__`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x140002cb4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140002cb4`

## string_xrefs

- `0x140002cc9`: `OSData\Software\Microsoft\DeclaredConfiguration\HostOS\Config\enrollments\%s\%s\state`
- `0x140002cc2`: `Software\Microsoft\DeclaredConfiguration\HostOS\Config\enrollments\%s\%s\state`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdSidStateFormat__(__int64 a1)
{
  __int64 result; // rax
  const wchar_t *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Config\\enrollments\\%s\\%s\\state";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\DeclaredConfiguration\\HostOS\\Config\\enrollments\\%s\\%s\\state";
  qword_140085168 = (__int64)v2;
  return result;
}

```

## disassembly

```asm
0x140002cb0  sub     rsp, 28h
0x140002cb4  call    cs:__imp_RtlIsStateSeparationEnabled
0x140002cbb  nop     dword ptr [rax+rax+00h]
0x140002cc0  test    al, al
0x140002cc2  lea     rdx, aSoftwareMicros_18; "Software\\Microsoft\\DeclaredConfigurat"...
0x140002cc9  lea     rcx, aOsdataSoftware_5; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x140002cd0  cmovz   rcx, rdx
0x140002cd4  mov     cs:qword_140085168, rcx
0x140002cdb  add     rsp, 28h
0x140002cdf  retn
```
