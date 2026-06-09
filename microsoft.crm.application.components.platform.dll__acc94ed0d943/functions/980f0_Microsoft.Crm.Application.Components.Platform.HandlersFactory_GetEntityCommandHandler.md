# Microsoft.Crm.Application.Components.Platform.HandlersFactory::GetEntityCommandHandler

- ea: `0x980f0`
- end: `0x98270`
- name: `Microsoft.Crm.Application.Components.Platform.HandlersFactory::GetEntityCommandHandler`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6a2e0`
- `0x980d0`
- `0x980f0`

## string_xrefs

- `0x981f0`: `Microsoft.Crm.Sales.Application.WebServices`
- `0x981f5`: `Microsoft.Crm.Sales.Application.WebServices.InlineEdit.SalesEntityCommandHandlerFactory`
- `0x98210`: `Microsoft.Crm.Common.Application.WebServices`
- `0x98215`: `Microsoft.Crm.Common.Application.WebServices.InlineEdit.CommonEntityCommandHandlerFactory`
- `0x98230`: `Microsoft.Crm.Service.Application.Components.WebServices.Core`
- `0x98235`: `Microsoft.Crm.Service.Application.WebServices.InlineEdit.ServiceEntityCommandHandlerFactory`
- `0x98250`: `Microsoft.Crm.Core.Application.Components.WebServices.Core`
- `0x98255`: `Microsoft.Crm.Core.Application.WebServices.InlineEdit.EntityCommandHandlerFactory`

## pseudocode

```c

```

## disassembly

```asm
0x980f0  ldarg.0
0x980f1  callvirt instance int32 Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x980f6  stloc.0
0x980f7  ldloc.0
0x980f8  ldc.i4   0x443
0x980fd  bgt      loc_98185
0x98102  ldloc.0
0x98103  ldc.i4.s 0x70
0x98105  bgt.s    loc_98122
0x98107  ldloc.0
0x98108  ldc.i4.3
0x98109  beq      loc_981F0
0x9810e  ldloc.0
0x9810f  ldc.i4.4
0x98110  beq      loc_98210
0x98115  ldloc.0
0x98116  ldc.i4.s 0x70
0x98118  beq      loc_98230
0x9811d  br       loc_98250
0x98122  ldloc.0
0x98123  ldc.i4   0x3F3
0x98128  bgt.s    loc_98145
0x9812a  ldloc.0
0x9812b  ldc.i4   0x3F2
0x98130  beq      loc_981F0
0x98135  ldloc.0
0x98136  ldc.i4   0x3F3
0x9813b  beq      loc_98230
0x98140  br       loc_98250
0x98145  ldloc.0
0x98146  ldc.i4   0x400
0x9814b  beq      loc_98210
0x98150  ldloc.0
0x98151  ldc.i4   0x43B
0x98156  sub
0x98157  switch   loc_981F0, loc_981F0, loc_981F0, loc_98250, loc_98250, loc_981F0, loc_981F0, loc_981F0, loc_981F0
0x98180  br       loc_98250
0x98185  ldloc.0
0x98186  ldc.i4   0x2007
0x9818b  bgt.s    loc_981AD
0x9818d  ldloc.0
0x9818e  ldc.i4   0x106A
0x98193  beq.s    loc_98210
0x98195  ldloc.0
0x98196  ldc.i4   0x106C
0x9819b  beq.s    loc_98210
0x9819d  ldloc.0
0x9819e  ldc.i4   0x2007
0x981a3  beq      loc_98230
0x981a8  br       loc_98250
0x981ad  ldloc.0
0x981ae  ldc.i4   0x24B9
0x981b3  bgt.s    loc_981CA
0x981b5  ldloc.0
0x981b6  ldc.i4   0x2455
0x981bb  beq.s    loc_98230
0x981bd  ldloc.0
0x981be  ldc.i4   0x24B9
0x981c3  beq.s    loc_98230
0x981c5  br       loc_98250
0x981ca  ldloc.0
0x981cb  ldc.i4   0x25E4
0x981d0  sub
0x981d1  switch   loc_98230, loc_98230, loc_98250, loc_98230
0x981e6  ldloc.0
0x981e7  ldc.i4   0x2617
0x981ec  beq.s    loc_98230
0x981ee  br.s     loc_98250
0x981f0  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sales.Application.WebServ"...
0x981f5  ldstr    aMicrosoftCrmSa_0// "Microsoft.Crm.Sales.Application.WebServ"...
0x981fa  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x981ff  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x98204  castclass Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory
0x98209  ldarg.0
0x9820a  callvirt instance class Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory::GetEntityCommandHandler(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x9820f  ret
0x98210  ldstr    aMicrosoftCrmCo// "Microsoft.Crm.Common.Application.WebSer"...
0x98215  ldstr    aMicrosoftCrmCo_0// "Microsoft.Crm.Common.Application.WebSer"...
0x9821a  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x9821f  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x98224  castclass Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory
0x98229  ldarg.0
0x9822a  callvirt instance class Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory::GetEntityCommandHandler(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x9822f  ret
0x98230  ldstr    aMicrosoftCrmSe_5// "Microsoft.Crm.Service.Application.Compo"...
0x98235  ldstr    aMicrosoftCrmSe_6// "Microsoft.Crm.Service.Application.WebSe"...
0x9823a  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x9823f  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x98244  castclass Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory
0x98249  ldarg.0
0x9824a  callvirt instance class Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory::GetEntityCommandHandler(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x9824f  ret
0x98250  ldstr    aMicrosoftCrmCo_1// "Microsoft.Crm.Core.Application.Componen"...
0x98255  ldstr    aMicrosoftCrmCo_2// "Microsoft.Crm.Core.Application.WebServi"...
0x9825a  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x9825f  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x98264  castclass Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory
0x98269  ldarg.0
0x9826a  callvirt instance class Microsoft.Crm.Application.Components.Platform.IEntityCommandHandler Microsoft.Crm.Application.Components.Platform.IEntityCommandHandlerFactory::GetEntityCommandHandler(class Microsoft.Crm.Application.Platform.EntityType entityType)
0x9826f  ret
```
