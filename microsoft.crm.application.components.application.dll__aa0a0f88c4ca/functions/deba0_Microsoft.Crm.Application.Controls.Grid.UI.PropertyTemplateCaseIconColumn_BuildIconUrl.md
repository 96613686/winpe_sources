# Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplateCaseIconColumn::BuildIconUrl

- ea: `0xdeba0`
- end: `0xdecef`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplateCaseIconColumn::BuildIconUrl`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xdeb70`

## callees

- `0xdac00`
- `0xdeba0`
- `0xdfc40`

## string_xrefs

- `0xdebfc`: `/WebResources/Service/_imgs/Incident/Incident_origincode_icon{0}.png`
- `0xdec2a`: `/WebResources/Service/_imgs/Incident/Incident_origincode_icon{0}.png`
- `0xdec58`: `/WebResources/Service/_imgs/Incident/Incident_origincode_icon{0}.png`
- `0xdec83`: `/WebResources/Service/_imgs/Incident/Incident_origincode_icon{0}.png`
- `0xdecd0`: `/WebResources/Service/_imgs/Incident/Incident_origincode_custom.png`

## pseudocode

```c

```

## disassembly

```asm
0xdeba0  ldnull
0xdeba1  stloc.0
0xdeba2  ldarg.1
0xdeba3  ldarg.0
0xdeba4  ldfld    string Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplateCaseIconColumn::caseOriginCodeColumnName
0xdeba9  callvirt instance object Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource::GetRawValue(string columnName)
0xdebae  stloc.1
0xdebaf  ldc.i4.m1
0xdebb0  stloc.2
0xdebb1  ldloc.1
0xdebb2  brfalse.s loc_DEBC6
0xdebb4  ldloc.1
0xdebb5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xdebba  beq.s    loc_DEBC4
0xdebbc  ldloc.1
0xdebbd  unbox.any [mscorlib]System.Int32
0xdebc2  br.s     loc_DEBC5
0xdebc4  ldc.i4.m1
0xdebc5  stloc.2
0xdebc6  ldloc.2
0xdebc7  ldc.i4.m1
0xdebc8  sub
0xdebc9  switch   loc_DEC7E, loc_DECA8, loc_DEBF7, loc_DEBF7, loc_DEBF7
0xdebe2  ldloc.2
0xdebe3  ldc.i4   0x9B3
0xdebe8  beq.s    loc_DEC25
0xdebea  ldloc.2
0xdebeb  ldc.i4   0xF92
0xdebf0  beq.s    loc_DEC53
0xdebf2  br       loc_DECA8
0xdebf7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdebfc  ldstr    aWebresourcesSe// "/WebResources/Service/_imgs/Incident/In"...
0xdec01  ldc.i4.1
0xdec02  newarr   [mscorlib]System.Object
0xdec07  dup
0xdec08  ldc.i4.0
0xdec09  ldloc.2
0xdec0a  box      [mscorlib]System.Int32
0xdec0f  stelem.ref
0xdec10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdec15  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdec1a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdec1f  stloc.0
0xdec20  br       loc_DECED
0xdec25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdec2a  ldstr    aWebresourcesSe// "/WebResources/Service/_imgs/Incident/In"...
0xdec2f  ldc.i4.1
0xdec30  newarr   [mscorlib]System.Object
0xdec35  dup
0xdec36  ldc.i4.0
0xdec37  ldc.i4.4
0xdec38  box      [mscorlib]System.Int32
0xdec3d  stelem.ref
0xdec3e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdec43  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdec48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdec4d  stloc.0
0xdec4e  br       loc_DECED
0xdec53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdec58  ldstr    aWebresourcesSe// "/WebResources/Service/_imgs/Incident/In"...
0xdec5d  ldc.i4.1
0xdec5e  newarr   [mscorlib]System.Object
0xdec63  dup
0xdec64  ldc.i4.0
0xdec65  ldc.i4.5
0xdec66  box      [mscorlib]System.Int32
0xdec6b  stelem.ref
0xdec6c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdec71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdec76  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdec7b  stloc.0
0xdec7c  br.s     loc_DECED
0xdec7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdec83  ldstr    aWebresourcesSe// "/WebResources/Service/_imgs/Incident/In"...
0xdec88  ldc.i4.1
0xdec89  newarr   [mscorlib]System.Object
0xdec8e  dup
0xdec8f  ldc.i4.0
0xdec90  ldsfld   string [mscorlib]System.String::Empty
0xdec95  stelem.ref
0xdec96  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdec9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdeca0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdeca5  stloc.0
0xdeca6  br.s     loc_DECED
0xdeca8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdecad  ldstr    aNewIncidentOri// "new_incident_origincode_icon{0}.png"
0xdecb2  ldc.i4.1
0xdecb3  newarr   [mscorlib]System.Object
0xdecb8  dup
0xdecb9  ldc.i4.0
0xdecba  ldloc.2
0xdecbb  box      [mscorlib]System.Int32
0xdecc0  stelem.ref
0xdecc1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdecc6  stloc.3
0xdecc7  ldarg.0
0xdecc8  ldloc.3
0xdecc9  call     instance bool Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplate::IsWebResourceExists(string webResourceName)
0xdecce  brtrue.s loc_DECE1
0xdecd0  ldstr    aWebresourcesSe_0// "/WebResources/Service/_imgs/Incident/In"...
0xdecd5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdecda  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdecdf  br.s     loc_DECEC
0xdece1  ldloc.3
0xdece2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xdece7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetSystemWebResourceIconUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdecec  stloc.0
0xdeced  ldloc.0
0xdecee  ret
```
