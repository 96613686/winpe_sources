# Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::<InitializeLifetimeService>b__3_0

- ea: `0x2400`
- end: `0x2421`
- name: `Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::<InitializeLifetimeService>b__3_0`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2400`: `SandboxMarshalByRefObject.InitializeLifetimeService: Initializing {0} with lease time {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2400  ldstr    aSandboxmarshal// "SandboxMarshalByRefObject.InitializeLif"...
0x2405  ldarg.0
0x2406  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x240b  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2410  ldarg.0
0x2411  ldfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x2416  box      [mscorlib]System.Int32
0x241b  call     string [mscorlib]System.String::Format(string, object, object)
0x2420  ret
```
