# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetAttributeMapSectionHtml

- ea: `0x5750`
- end: `0x57da`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetAttributeMapSectionHtml`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x5750`
- `0x7d50`
- `0x7e60`
- `0x9100`

## pseudocode

```c

```

## disassembly

```asm
0x5750  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5755  stloc.0
0x5756  ldloc.0
0x5757  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x575c  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x5761  stloc.1
0x5762  ldloc.1
0x5763  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x5768  stloc.2
0x5769  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView
0x576e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5773  ldarg.2
0x5774  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x5779  unbox.any [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView
0x577e  stloc.3
0x577f  ldnull
0x5780  stloc.s  4
0x5782  ldarg.3
0x5783  ldarg.1
0x5784  ldc.i4.0
0x5785  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x578a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::.ctor(string, string, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x578f  ldarg.1
0x5790  ldloc.3
0x5791  newobj   instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity targetEntity, string inputFileId, valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView view)
0x5796  stloc.s  4
0x5798  ldloc.s  4
0x579a  ldloc.2
0x579b  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Render(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x57a0  leave.s  loc_57B9
0x57a2  stloc.s  5
0x57a4  ldarg.0
0x57a5  ldloc.s  5
0x57a7  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x57ac  throw
0x57ad  ldloc.s  4
0x57af  brfalse.s loc_57B8
0x57b1  ldloc.s  4
0x57b3  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::Dispose()
0x57b8  endfinally
0x57b9  ldloc.0
0x57ba  callvirt instance string [mscorlib]System.Object::ToString()
0x57bf  stloc.s  6
0x57c1  leave.s  loc_57D7
0x57c3  ldloc.2
0x57c4  brfalse.s loc_57CC
0x57c6  ldloc.2
0x57c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57cc  endfinally
0x57cd  ldloc.1
0x57ce  brfalse.s loc_57D6
0x57d0  ldloc.1
0x57d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57d6  endfinally
0x57d7  ldloc.s  6
0x57d9  ret
```
