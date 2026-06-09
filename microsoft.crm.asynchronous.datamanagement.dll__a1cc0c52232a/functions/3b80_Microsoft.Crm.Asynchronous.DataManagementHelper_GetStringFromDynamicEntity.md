# Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity

- ea: `0x3b80`
- end: `0x3baa`
- name: `Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity`
- size: `42`
- prototype: ``
- caller_count: `78`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x62b0`
- `0x6520`
- `0x65d0`
- `0x6690`
- `0x6a40`
- `0x6c10`
- `0x6c80`
- `0x6e60`
- `0x71a0`
- `0x75e0`
- `0x77b0`
- `0x82e0`
- `0x8be0`
- `0x8c30`
- `0x8fd0`
- `0x9380`
- `0x98a0`
- `0x9c10`
- `0x9d80`
- `0xa070`
- `0xa600`
- `0xafb0`
- `0xc8e0`
- `0xd1c0`
- `0xd3d0`
- `0xd4b0`
- `0xd5a0`
- `0xe010`
- `0xe550`
- `0xf190`
- `0xfd90`
- `0xfe70`
- `0x10b00`
- `0x10ec0`
- `0x12170`
- `0x13670`
- `0x13f50`
- `0x14370`
- `0x14940`
- `0x14bc0`
- `0x14cb0`
- `0x15220`
- `0x156f0`
- `0x15b80`
- `0x15d20`
- `0x16690`
- `0x16bf0`
- `0x16f30`
- `0x17080`
- `0x17130`

## callees

- `0x3b80`

## pseudocode

```c

```

## disassembly

```asm
0x3b80  ldarg.0
0x3b81  brfalse.s loc_3B8B
0x3b83  ldarg.1
0x3b84  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b89  brfalse.s loc_3B8D
0x3b8b  ldnull
0x3b8c  ret
0x3b8d  ldarg.0
0x3b8e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3b93  ldarg.1
0x3b94  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3b99  brtrue.s loc_3B9D
0x3b9b  ldnull
0x3b9c  ret
0x3b9d  ldarg.0
0x3b9e  ldarg.1
0x3b9f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3ba4  castclass [mscorlib]System.String
0x3ba9  ret
```
