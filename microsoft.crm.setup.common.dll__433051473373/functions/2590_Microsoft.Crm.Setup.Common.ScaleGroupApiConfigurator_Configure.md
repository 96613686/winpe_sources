# Microsoft.Crm.Setup.Common.ScaleGroupApiConfigurator::Configure

- ea: `0x2590`
- end: `0x26e3`
- name: `Microsoft.Crm.Setup.Common.ScaleGroupApiConfigurator::Configure`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2590`

## string_xrefs

- `0x25d9`: `Site not found, exiting ScaleGroupApiConfigurator`

## pseudocode

```c

```

## disassembly

```asm
0x2590  newobj   instance void [Microsoft.Web.Administration]Microsoft.Web.Administration.ServerManager::.ctor()
0x2595  stloc.0
0x2596  ldc.i4.1
0x2597  stloc.1
0x2598  ldstr    aMicrosoftDynam// "Microsoft Dynamics CRM"
0x259d  stloc.2
0x259e  ldloc.1
0x259f  ldc.i4.2
0x25a0  blt.s    loc_25B3
0x25a2  ldstr    aMicrosoftDynam// "Microsoft Dynamics CRM"
0x25a7  ldloc.1
0x25a8  box      [mscorlib]System.Int32
0x25ad  call     string [mscorlib]System.String::Concat(object, object)
0x25b2  stloc.2
0x25b3  ldstr    aProcessingSite// "Processing site : "
0x25b8  ldloc.2
0x25b9  call     string [mscorlib]System.String::Concat(string, string)
0x25be  ldc.i4.0
0x25bf  newarr   [mscorlib]System.Object
0x25c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x25c9  ldloc.0
0x25ca  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.SiteCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ServerManager::get_Sites()
0x25cf  ldloc.2
0x25d0  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.Site [Microsoft.Web.Administration]Microsoft.Web.Administration.SiteCollection::get_Item(string)
0x25d5  stloc.3
0x25d6  ldloc.3
0x25d7  brtrue.s loc_25EE
0x25d9  ldstr    aSiteNotFoundEx// "Site not found, exiting ScaleGroupApiCo"...
0x25de  ldc.i4.0
0x25df  newarr   [mscorlib]System.Object
0x25e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x25e9  leave    loc_26E2
0x25ee  ldloc.0
0x25ef  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.Configuration [Microsoft.Web.Administration]Microsoft.Web.Administration.ServerManager::GetApplicationHostConfiguration()
0x25f4  ldstr    aSystemWebserve// "system.webServer/handlers"
0x25f9  ldloc.3
0x25fa  callvirt instance string [Microsoft.Web.Administration]Microsoft.Web.Administration.Site::get_Name()
0x25ff  ldstr    aSg// "/SG"
0x2604  call     string [mscorlib]System.String::Concat(string, string)
0x2609  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection [Microsoft.Web.Administration]Microsoft.Web.Administration.Configuration::GetSection(string, string)
0x260e  stloc.s  4
0x2610  ldstr    aProcessingSect// "Processing section : "
0x2615  ldloc.s  4
0x2617  callvirt instance string [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection::get_SectionPath()
0x261c  call     string [mscorlib]System.String::Concat(string, string)
0x2621  ldc.i4.0
0x2622  newarr   [mscorlib]System.Object
0x2627  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x262c  ldloc.s  4
0x262e  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElementCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::GetCollection()
0x2633  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElementCollectionBase`1<class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement>::GetEnumerator()
0x2638  stloc.s  5
0x263a  br.s     loc_26B2
0x263c  ldloc.s  5
0x263e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement>::get_Current()
0x2643  stloc.s  6
0x2645  ldloc.s  6
0x2647  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::get_Attributes()
0x264c  ldstr    aPath// "path"
0x2651  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection::get_Item(string)
0x2656  callvirt instance object [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute::get_Value()
0x265b  castclass [mscorlib]System.String
0x2660  ldstr    aAspx// "*.aspx"
0x2665  call     bool [mscorlib]System.String::op_Equality(string, string)
0x266a  brfalse.s loc_26B2
0x266c  ldstr    aUpdatingCollec// "Updating collection element : "
0x2671  ldloc.s  6
0x2673  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::get_Attributes()
0x2678  ldstr    aName// "name"
0x267d  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection::get_Item(string)
0x2682  callvirt instance object [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute::get_Value()
0x2687  call     string [mscorlib]System.String::Concat(object, object)
0x268c  ldc.i4.0
0x268d  newarr   [mscorlib]System.Object
0x2692  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x2697  ldloc.s  6
0x2699  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::get_Attributes()
0x269e  ldstr    aVerb// "verb"
0x26a3  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttributeCollection::get_Item(string)
0x26a8  ldstr    asc_1953A// "*"
0x26ad  callvirt instance void [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationAttribute::set_Value(object)
0x26b2  ldloc.s  5
0x26b4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26b9  brtrue.s loc_263C
0x26bb  leave.s  loc_26C9
0x26bd  ldloc.s  5
0x26bf  brfalse.s loc_26C8
0x26c1  ldloc.s  5
0x26c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26c8  endfinally
0x26c9  ldloc.0
0x26ca  callvirt instance void [Microsoft.Web.Administration]Microsoft.Web.Administration.ServerManager::CommitChanges()
0x26cf  ldloc.1
0x26d0  ldc.i4.1
0x26d1  add
0x26d2  stloc.1
0x26d3  br       loc_2598
0x26d8  ldloc.0
0x26d9  brfalse.s loc_26E1
0x26db  ldloc.0
0x26dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26e1  endfinally
0x26e2  ret
```
