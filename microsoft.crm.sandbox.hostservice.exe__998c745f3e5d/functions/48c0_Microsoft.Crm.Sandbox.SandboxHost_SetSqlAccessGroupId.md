# Microsoft.Crm.Sandbox.SandboxHost::SetSqlAccessGroupId

- ea: `0x48c0`
- end: `0x48da`
- name: `Microsoft.Crm.Sandbox.SandboxHost::SetSqlAccessGroupId`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140`

## callees

- `0x48c0`
- `0x4e60`

## pseudocode

```c

```

## disassembly

```asm
0x48c0  ldarg.0
0x48c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x48c6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x48cb  brfalse.s loc_48CE
0x48cd  ret
0x48ce  ldarg.0
0x48cf  call     unsigned int8[] [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetSidFromAD(valuetype [mscorlib]System.Guid)
0x48d4  call     void Microsoft.Crm.Sandbox.SandboxHost::set_SqlAccessGroupSid(unsigned int8[] value)
0x48d9  ret
```
