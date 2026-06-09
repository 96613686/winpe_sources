# Microsoft.Crm.Common.Application.Platform.EntityAttributeMapBaseFactory::Microsoft.Crm.Application.Commands.IMapEntityFactory.RetrieveMapEntity

- ea: `0x3f20`
- end: `0x3fa6`
- name: `Microsoft.Crm.Common.Application.Platform.EntityAttributeMapBaseFactory::Microsoft.Crm.Application.Commands.IMapEntityFactory.RetrieveMapEntity`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8b0`
- `0x950`
- `0xc60`
- `0x3f20`

## pseudocode

```c

```

## disassembly

```asm
0x3f20  ldarg.1
0x3f21  ldc.i4.1
0x3f22  sub
0x3f23  switch   loc_3F4A, loc_3F4A, loc_3F4A, loc_3F54, loc_3F6D, loc_3F86, loc_3F4A, loc_3F4A
0x3f48  br.s     loc_3F9F
0x3f4a  ldarg.2
0x3f4b  ldarg.3
0x3f4c  ldarg.s  4
0x3f4e  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string additionalPropertyToSet)
0x3f53  ret
0x3f54  ldarg.3
0x3f55  brfalse.s loc_3F61
0x3f57  ldarg.2
0x3f58  ldarg.3
0x3f59  ldarg.s  4
0x3f5b  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string additionalPropertyToSet)
0x3f60  ret
0x3f61  ldarg.2
0x3f62  ldstr    aFaxnumber// "faxnumber"
0x3f67  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string contactPropertyName)
0x3f6c  ret
0x3f6d  ldarg.3
0x3f6e  brfalse.s loc_3F7A
0x3f70  ldarg.2
0x3f71  ldarg.3
0x3f72  ldarg.s  4
0x3f74  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string additionalPropertyToSet)
0x3f79  ret
0x3f7a  ldarg.2
0x3f7b  ldstr    aAddress// "address"
0x3f80  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string contactPropertyName)
0x3f85  ret
0x3f86  ldarg.3
0x3f87  brfalse.s loc_3F93
0x3f89  ldarg.2
0x3f8a  ldarg.3
0x3f8b  ldarg.s  4
0x3f8d  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string partyParticipationTypeName, string additionalPropertyToSet)
0x3f92  ret
0x3f93  ldarg.2
0x3f94  ldstr    aPhonenumber// "phonenumber"
0x3f99  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityContactInformationMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType, string contactPropertyName)
0x3f9e  ret
0x3f9f  ldarg.2
0x3fa0  newobj   instance void Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType targetEntityType)
0x3fa5  ret
```
