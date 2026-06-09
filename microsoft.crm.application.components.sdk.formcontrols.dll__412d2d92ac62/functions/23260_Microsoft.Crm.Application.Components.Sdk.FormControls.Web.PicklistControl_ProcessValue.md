# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::ProcessValue

- ea: `0x23260`
- end: `0x234ec`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::ProcessValue`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x23500`

## callees

- `0x182d0`
- `0x23240`
- `0x23260`

## pseudocode

```c

```

## disassembly

```asm
0x23260  ldarg.1
0x23261  isinst   [mscorlib]System.String
0x23266  brfalse.s loc_232A9
0x23268  ldarg.0
0x23269  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2326e  brfalse.s loc_232A9
0x23270  ldarg.0
0x23271  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23276  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x2327b  ldstr    aStatecode// "statecode"
0x23280  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23285  brfalse.s loc_232A9
0x23287  ldarg.0
0x23288  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2328d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x23292  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x23297  ldarg.1
0x23298  castclass [mscorlib]System.String
0x2329d  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x232a2  box      [mscorlib]System.Int32
0x232a7  starg.s  1
0x232a9  ldarg.1
0x232aa  brfalse.s loc_232EF
0x232ac  ldarg.1
0x232ad  isinst   [mscorlib]System.Int32
0x232b2  brtrue.s loc_232EF
0x232b4  ldarg.1
0x232b5  isinst   [mscorlib]System.Int32
0x232ba  brtrue.s loc_232EF
0x232bc  ldarg.1
0x232bd  isinst   [mscorlib]System.Boolean
0x232c2  brtrue.s loc_232EF
0x232c4  ldarg.1
0x232c5  isinst   [mscorlib]System.String
0x232ca  brfalse.s loc_232D4
0x232cc  ldarg.0
0x232cd  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::get_AllowStringValues()
0x232d2  brtrue.s loc_232EF
0x232d4  ldstr    aWrongValueType// "Wrong value type is passed to the contr"...
0x232d9  ldarg.0
0x232da  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x232df  ldstr    aThisControlOnl_8// ". This control only accepts strings,int"...
0x232e4  call     string [mscorlib]System.String::Concat(string, string, string)
0x232e9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x232ee  throw
0x232ef  ldarg.1
0x232f0  brfalse.s loc_2330D
0x232f2  ldarg.1
0x232f3  isinst   [mscorlib]System.Boolean
0x232f8  brfalse.s loc_2330D
0x232fa  ldarg.1
0x232fb  unbox.any [mscorlib]System.Boolean
0x23300  brtrue.s loc_23305
0x23302  ldc.i4.0
0x23303  br.s     loc_23306
0x23305  ldc.i4.1
0x23306  box      [mscorlib]System.Int32
0x2330b  starg.s  1
0x2330d  ldarg.1
0x2330e  brfalse.s loc_23321
0x23310  ldarg.1
0x23311  isinst   [mscorlib]System.Int32
0x23316  brfalse.s loc_23380
0x23318  ldarg.1
0x23319  unbox.any [mscorlib]System.Int32
0x2331e  ldc.i4.m1
0x2331f  bne.un.s loc_23380
0x23321  ldarg.0
0x23322  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x23327  ldarg.0
0x23328  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2332d  brfalse.s loc_23361
0x2332f  ldarg.0
0x23330  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23335  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x2333a  brfalse.s loc_23371
0x2333c  ldarg.0
0x2333d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23342  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x23347  isinst   [mscorlib]System.Int32
0x2334c  brfalse.s loc_23361
0x2334e  ldarg.0
0x2334f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23354  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x23359  unbox.any [mscorlib]System.Int32
0x2335e  ldc.i4.m1
0x2335f  beq.s    loc_23371
0x23361  ldc.i4.m1
0x23362  stloc.0
0x23363  ldloca.s 0
0x23365  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2336a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2336f  br.s     loc_23376
0x23371  ldsfld   string [mscorlib]System.String::Empty
0x23376  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x2337b  br       loc_234EA
0x23380  ldarg.0
0x23381  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23386  brfalse.s loc_233C0
0x23388  ldarg.0
0x23389  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x2338e  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x23393  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x23398  ldarg.1
0x23399  unbox.any [mscorlib]System.Int32
0x2339e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::ContainsKey(var<u1>)
0x233a3  brtrue.s loc_233C0
0x233a5  ldarg.0
0x233a6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x233ab  ldarg.1
0x233ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x233b1  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x233b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x233bb  br       loc_234EA
0x233c0  ldarg.0
0x233c1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x233c6  ldc.i4.m1
0x233c7  stloc.0
0x233c8  ldloca.s 0
0x233ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x233cf  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x233d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x233d9  ldarg.0
0x233da  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x233df  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x233e4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x233e9  stloc.1
0x233ea  br       loc_234C9
0x233ef  ldloc.1
0x233f0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x233f5  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x233fa  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::get_Options()
0x233ff  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x23404  stloc.2
0x23405  br       loc_234A8
0x2340a  ldloc.2
0x2340b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x23410  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option
0x23415  stloc.3
0x23416  ldarg.0
0x23417  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::get_AllowStringValues()
0x2341c  brtrue.s loc_2345B
0x2341e  ldloc.3
0x2341f  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x23424  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23429  brtrue.s loc_2345B
0x2342b  ldloc.3
0x2342c  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x23431  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23436  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x2343b  ldarg.1
0x2343c  unbox.any [mscorlib]System.Int32
0x23441  bne.un.s loc_2345B
0x23443  ldarg.0
0x23444  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x23449  ldarg.1
0x2344a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2344f  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x23454  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x23459  leave.s  loc_234C9
0x2345b  ldarg.1
0x2345c  isinst   [mscorlib]System.String
0x23461  brfalse.s loc_234A8
0x23463  ldarg.0
0x23464  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::get_AllowStringValues()
0x23469  brfalse.s loc_234A8
0x2346b  ldloc.3
0x2346c  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x23471  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x23476  brtrue.s loc_234A8
0x23478  ldloc.3
0x23479  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Option::get_Value()
0x2347e  ldarg.1
0x2347f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23484  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x23489  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2348e  brfalse.s loc_234A8
0x23490  ldarg.0
0x23491  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::_innerSelect
0x23496  ldarg.1
0x23497  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2349c  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x234a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x234a6  leave.s  loc_234C9
0x234a8  ldloc.2
0x234a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x234ae  brtrue   loc_2340A
0x234b3  leave.s  loc_234C9
0x234b5  ldloc.2
0x234b6  isinst   [mscorlib]System.IDisposable
0x234bb  stloc.s  4
0x234bd  ldloc.s  4
0x234bf  brfalse.s loc_234C8
0x234c1  ldloc.s  4
0x234c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x234c8  endfinally
0x234c9  ldloc.1
0x234ca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x234cf  brtrue   loc_233EF
0x234d4  leave.s  loc_234EA
0x234d6  ldloc.1
0x234d7  isinst   [mscorlib]System.IDisposable
0x234dc  stloc.s  4
0x234de  ldloc.s  4
0x234e0  brfalse.s loc_234E9
0x234e2  ldloc.s  4
0x234e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x234e9  endfinally
0x234ea  ldarg.1
0x234eb  ret
```
