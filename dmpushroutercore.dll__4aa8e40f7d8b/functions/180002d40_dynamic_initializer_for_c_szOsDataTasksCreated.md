# _dynamic_initializer_for__c_szOsDataTasksCreated__

- ea: `0x180002d40`
- end: `0x180002d6a`
- name: `_dynamic_initializer_for__c_szOsDataTasksCreated__`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180002d44`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180002d44`

## string_xrefs

- `0x180002d53`: `OSData\Software\Microsoft\Enrollments\OSDataTasksCreated`
- `0x180002d4c`: `Software\Microsoft\Enrollments\OSDataTasksCreated`

## pseudocode

```c
__int64 __fastcall dynamic_initializer_for__c_szOsDataTasksCreated__(__int64 a1)
{
  __int64 result; // rax
  const WCHAR *v2; // rcx

  result = RtlIsStateSeparationEnabled(a1);
  v2 = L"OSData\\Software\\Microsoft\\Enrollments\\OSDataTasksCreated";
  if ( !(_BYTE)result )
    v2 = L"Software\\Microsoft\\Enrollments\\OSDataTasksCreated";
  lpSubKey = v2;
  return result;
}

```

## disassembly

```asm
0x180002d40  sub     rsp, 28h
0x180002d44  call    cs:__imp_RtlIsStateSeparationEnabled
0x180002d4a  test    al, al
0x180002d4c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments\\OSDat"...
0x180002d53  lea     rcx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Enrollment"...
0x180002d5a  cmovz   rcx, rdx
0x180002d5e  mov     cs:lpSubKey, rcx
0x180002d65  add     rsp, 28h
0x180002d69  retn
```
