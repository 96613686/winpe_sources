# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Disassociate

- ea: `0x9990`
- end: `0x99c9`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::Disassociate`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5040`
- `0x5060`
- `0x5080`
- `0x9b20`

## pseudocode

```c

```

## disassembly

```asm
0x9990  ldarg.1
0x9991  ldstr    aEntityname// "entityName"
0x9996  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNullOrEmpty(string argument, string name)
0x999b  ldarg.2
0x999c  ldstr    aEntityid// "entityId"
0x99a1  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid argument, string name)
0x99a6  ldarg.3
0x99a7  ldstr    aRelationship// "relationship"
0x99ac  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x99b1  ldarg.s  4
0x99b3  ldstr    aRelatedentitie// "relatedEntities"
0x99b8  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x99bd  ldarg.0
0x99be  ldarg.1
0x99bf  ldarg.2
0x99c0  ldarg.3
0x99c1  ldarg.s  4
0x99c3  call     instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::DisassociateInternal(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection relatedEntities)
0x99c8  ret
```
