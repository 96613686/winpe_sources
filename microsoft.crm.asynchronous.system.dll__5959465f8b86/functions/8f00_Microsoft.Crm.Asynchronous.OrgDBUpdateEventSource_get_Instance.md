# Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::get_Instance

- ea: `0x8f00`
- end: `0x8f0b`
- name: `Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xced0`
- `0xd020`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource> Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::lazyInstance
0x8f05  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource>::get_Value()
0x8f0a  ret
```
