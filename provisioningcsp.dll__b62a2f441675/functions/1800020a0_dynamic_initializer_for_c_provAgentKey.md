# _dynamic_initializer_for__c_provAgentKey__

- ea: `0x1800020a0`
- end: `0x1800020ca`
- name: `_dynamic_initializer_for__c_provAgentKey__`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000882c`

## string_xrefs

- `0x1800020b2`: `OSData\Software\Microsoft\Provisioning\Agent`
- `0x1800020ab`: `Software\Microsoft\Provisioning\Agent`

## pseudocode

```c
char dynamic_initializer_for__c_provAgentKey__()
{
  char result; // al
  const WCHAR *v1; // rcx

  result = MVIsStateSeparationEnabled();
  v1 = L"OSData\\Software\\Microsoft\\Provisioning\\Agent";
  if ( !result )
    v1 = L"Software\\Microsoft\\Provisioning\\Agent";
  c_provAgentKey = v1;
  return result;
}

```

## disassembly

```asm
0x1800020a0  sub     rsp, 28h
0x1800020a4  call    ?MVIsStateSeparationEnabled@@YA_NXZ; MVIsStateSeparationEnabled(void)
0x1800020a9  test    al, al
0x1800020ab  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Provisioning\\Agen"...
0x1800020b2  lea     rcx, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800020b9  cmovz   rcx, rdx
0x1800020bd  mov     cs:?c_provAgentKey@@3PEBGEB, rcx; ushort const * const c_provAgentKey
0x1800020c4  add     rsp, 28h
0x1800020c8  retn
```
