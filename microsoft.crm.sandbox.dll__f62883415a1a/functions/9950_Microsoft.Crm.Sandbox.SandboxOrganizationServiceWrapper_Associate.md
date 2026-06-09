# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Associate

- ea: `0x9950`
- end: `0x9989`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Associate`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x5060`
- `0x5080`
- `0x9af0`

## pseudocode

```c

```

## disassembly

```asm
0x9950  ldarg.1
0x9951  ldstr    aEntityname// "entityName"
0x9956  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNullOrEmpty(string argument, string name)
0x995b  ldarg.2
0x995c  ldstr    aEntityid// "entityId"
0x9961  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid argument, string name)
0x9966  ldarg.3
0x9967  ldstr    aRelationship// "relationship"
0x996c  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x9971  ldarg.s  4
0x9973  ldstr    aRelatedentitie// "relatedEntities"
0x9978  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x997d  ldarg.0
0x997e  ldarg.1
0x997f  ldarg.2
0x9980  ldarg.3
0x9981  ldarg.s  4
0x9983  call     instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::AssociateInternal(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection relatedEntities)
0x9988  ret
```
