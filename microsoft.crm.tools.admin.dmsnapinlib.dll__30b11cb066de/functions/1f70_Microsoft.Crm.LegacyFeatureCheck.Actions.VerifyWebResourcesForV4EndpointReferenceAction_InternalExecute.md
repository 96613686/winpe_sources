# Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyWebResourcesForV4EndpointReferenceAction::InternalExecute

- ea: `0x1f70`
- end: `0x2022`
- name: `Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyWebResourcesForV4EndpointReferenceAction::InternalExecute`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1110`
- `0x11b0`
- `0x1860`
- `0x1880`
- `0x1be0`
- `0x1c00`
- `0x1f70`

## string_xrefs

- `0x1fbc`: `crmservice.asmx`
- `0x1fd2`: `Web resource {0} contains a reference to the 2007 web service endpoint`
- `0x2011`: `Did not find any web resources that contain calls to the 2007 web service endpoint`

## pseudocode

```c

```

## disassembly

```asm
0x1f70  ldarg.1
0x1f71  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.WebResource> Microsoft.Crm.LegacyFeatureCheck.Organization::GetWebResources()
0x1f76  stloc.0
0x1f77  ldarg.0
0x1f78  ldarg.1
0x1f79  ldc.i4.3
0x1f7a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f7f  ldstr    aChecking0WebRe// "Checking {0} web resources"
0x1f84  ldc.i4.1
0x1f85  newarr   [mscorlib]System.Object
0x1f8a  dup
0x1f8b  ldc.i4.0
0x1f8c  ldloc.0
0x1f8d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.WebResource>::get_Count()
0x1f92  box      [mscorlib]System.Int32
0x1f97  stelem.ref
0x1f98  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x1f9d  ldc.i4.0
0x1f9e  stloc.1
0x1f9f  ldloc.0
0x1fa0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.WebResource>::GetEnumerator()
0x1fa5  stloc.2
0x1fa6  br.s     loc_1FED
0x1fa8  ldloca.s 2
0x1faa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.WebResource>::get_Current()
0x1faf  stloc.3
0x1fb0  ldarg.1
0x1fb1  ldloc.3
0x1fb2  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.Organization::GetWebResourceContent(class Microsoft.Crm.LegacyFeatureCheck.WebResource resource)
0x1fb7  stloc.s  4
0x1fb9  ldc.i4.m1
0x1fba  ldloc.s  4
0x1fbc  ldstr    aCrmserviceAsmx// "crmservice.asmx"
0x1fc1  ldc.i4.5
0x1fc2  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1fc7  beq.s    loc_1FED
0x1fc9  ldarg.0
0x1fca  ldarg.1
0x1fcb  ldc.i4.3
0x1fcc  ldloc.3
0x1fcd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.LegacyFeatureCheck.WebResource::get_Id()
0x1fd2  ldstr    aWebResource0Co// "Web resource {0} contains a reference t"...
0x1fd7  ldc.i4.1
0x1fd8  newarr   [mscorlib]System.Object
0x1fdd  dup
0x1fde  ldc.i4.0
0x1fdf  ldloc.3
0x1fe0  callvirt instance string Microsoft.Crm.LegacyFeatureCheck.WebResource::get_Name()
0x1fe5  stelem.ref
0x1fe6  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x1feb  ldc.i4.1
0x1fec  stloc.1
0x1fed  ldloca.s 2
0x1fef  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.WebResource>::MoveNext()
0x1ff4  brtrue.s loc_1FA8
0x1ff6  leave.s  loc_2006
0x1ff8  ldloca.s 2
0x1ffa  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.LegacyFeatureCheck.WebResource>
0x2000  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2005  endfinally
0x2006  ldloc.1
0x2007  brtrue.s loc_2021
0x2009  ldarg.0
0x200a  ldarg.1
0x200b  ldc.i4.3
0x200c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2011  ldstr    aDidNotFindAnyW// "Did not find any web resources that con"...
0x2016  ldc.i4.0
0x2017  newarr   [mscorlib]System.Object
0x201c  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.OrganizationVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.Organization organization, valuetype Microsoft.Crm.LegacyFeatureCheck.Common.ComponentName component, valuetype [mscorlib]System.Guid componentId, string messageFormat, object[] values)
0x2021  ret
```
