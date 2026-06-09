# Microsoft.Crm.Application.Forms.FormDescriptorLoader::GetDefaultFormDescriptor

- ea: `0x31af0`
- end: `0x31ca4`
- name: `Microsoft.Crm.Application.Forms.FormDescriptorLoader::GetDefaultFormDescriptor`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x31890`

## callees

- `0x2fb90`
- `0x2fba0`
- `0x31af0`
- `0x59880`
- `0x5be20`
- `0x6bd50`
- `0x6bdf0`
- `0x6c610`
- `0x6c670`
- `0xa3730`

## string_xrefs

- `0x31b35`: `lastviewedformxml`
- `0x31bcb`: `lastviewedformxml`

## pseudocode

```c

```

## disassembly

```asm
0x31af0  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x31af5  stloc.0
0x31af6  ldloc.0
0x31af7  ldarg.1
0x31af8  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::formId
0x31afd  ldnull
0x31afe  stloc.1
0x31aff  ldsfld   string [mscorlib]System.String::Empty
0x31b04  stloc.2
0x31b05  ldc.i4.m1
0x31b06  stloc.3
0x31b07  ldc.i4.0
0x31b08  stloc.s  4
0x31b0a  ldsfld   string [mscorlib]System.String::Empty
0x31b0f  stloc.s  5
0x31b11  ldstr    aUserentityuise// "userentityuisettings"
0x31b16  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x31b1b  stloc.s  6
0x31b1d  ldloc.s  6
0x31b1f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x31b24  ldstr    aObjecttypecode// "objecttypecode"
0x31b29  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x31b2e  ldloc.s  6
0x31b30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x31b35  ldstr    aLastviewedform// "lastviewedformxml"
0x31b3a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x31b3f  ldloc.s  6
0x31b41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x31b46  ldstr    aOwnerid// "ownerid"
0x31b4b  ldc.i4.0
0x31b4c  ldc.i4.1
0x31b4d  newarr   [mscorlib]System.Object
0x31b52  dup
0x31b53  ldc.i4.0
0x31b54  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x31b59  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x31b5e  box      [mscorlib]System.Guid
0x31b63  stelem.ref
0x31b64  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x31b69  ldloc.s  6
0x31b6b  ldarg.2
0x31b6c  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x31b71  stloc.s  7
0x31b73  ldloc.s  7
0x31b75  brfalse  loc_31C6F
0x31b7a  ldloc.s  7
0x31b7c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x31b81  ldc.i4.0
0x31b82  ble      loc_31C6F
0x31b87  ldloc.s  7
0x31b89  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x31b8e  stloc.s  8
0x31b90  br       loc_31C55
0x31b95  ldloc.s  8
0x31b97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x31b9c  stloc.s  9
0x31b9e  ldloc.s  9
0x31ba0  brfalse  loc_31C55
0x31ba5  ldloc.s  9
0x31ba7  ldstr    aObjecttypecode// "objecttypecode"
0x31bac  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31bb1  brtrue.s loc_31BB6
0x31bb3  ldc.i4.0
0x31bb4  br.s     loc_31BC7
0x31bb6  ldloc.s  9
0x31bb8  ldstr    aObjecttypecode// "objecttypecode"
0x31bbd  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31bc2  unbox.any [mscorlib]System.Int32
0x31bc7  stloc.s  4
0x31bc9  ldloc.s  9
0x31bcb  ldstr    aLastviewedform// "lastviewedformxml"
0x31bd0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x31bd5  castclass [mscorlib]System.String
0x31bda  stloc.s  5
0x31bdc  ldloc.s  5
0x31bde  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31be3  brtrue.s loc_31C55
0x31be5  ldloc.s  5
0x31be7  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Parse(string)
0x31bec  ldstr    aForm_0// "Form"
0x31bf1  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x31bf6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Elements(class [System.Xml.Linq]System.Xml.Linq.XName)
0x31bfb  ldloc.0
0x31bfc  ldfld    class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool> <>c__DisplayClass2_0::<>9__0
0x31c01  dup
0x31c02  brtrue.s loc_31C1C
0x31c04  pop
0x31c05  ldloc.0
0x31c06  ldloc.0
0x31c07  ldftn    instance bool <>c__DisplayClass2_0::<GetDefaultFormDescriptor>b__0(class [System.Xml.Linq]System.Xml.Linq.XElement element)
0x31c0d  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool>::.ctor(object, native int)
0x31c12  dup
0x31c13  stloc.s  0xA
0x31c15  stfld    class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool> <>c__DisplayClass2_0::<>9__0
0x31c1a  ldloc.s  0xA
0x31c1c  call     T0x2B000056
0x31c21  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, string> <>c::<>9__2_1
0x31c26  dup
0x31c27  brtrue.s loc_31C40
0x31c29  pop
0x31c2a  ldsfld   class <>c <>c::<>9
0x31c2f  ldftn    instance string <>c::<GetDefaultFormDescriptor>b__2_1(class [System.Xml.Linq]System.Xml.Linq.XElement element)
0x31c35  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, string>::.ctor(object, native int)
0x31c3a  dup
0x31c3b  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, string> <>c::<>9__2_1
0x31c40  call     T0x2B000057
0x31c45  call     T0x2B000058
0x31c4a  stloc.2
0x31c4b  ldloc.2
0x31c4c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31c51  brtrue.s loc_31C55
0x31c53  leave.s  loc_31C6F
0x31c55  ldloc.s  8
0x31c57  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31c5c  brtrue   loc_31B95
0x31c61  leave.s  loc_31C6F
0x31c63  ldloc.s  8
0x31c65  brfalse.s loc_31C6E
0x31c67  ldloc.s  8
0x31c69  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31c6e  endfinally
0x31c6f  ldloc.2
0x31c70  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31c75  brtrue.s loc_31CA2
0x31c77  ldloc.s  4
0x31c79  ldc.i4.0
0x31c7a  ble.s    loc_31CA2
0x31c7c  ldloc.2
0x31c7d  ldloca.s 3
0x31c7f  call     T0x2B000059
0x31c84  brtrue.s loc_31C88
0x31c86  ldc.i4.m1
0x31c87  stloc.3
0x31c88  newobj   instance void Microsoft.Crm.Application.Platform.FormFilterInformation::.ctor()
0x31c8d  dup
0x31c8e  ldarg.2
0x31c8f  callvirt instance void Microsoft.Crm.Application.Platform.FormFilterInformation::set_Context(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext value)
0x31c94  newobj   instance void Microsoft.Crm.Application.Platform.AppFormFilter::.ctor(class Microsoft.Crm.Application.Platform.FormFilterInformation filterInformation)
0x31c99  ldloc.s  4
0x31c9b  ldloc.3
0x31c9c  callvirt instance class Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Platform.AppFormFilter::GetSingleForm(int32 entityTypeCode, valuetype Microsoft.Crm.Application.FormType formType)
0x31ca1  stloc.1
0x31ca2  ldloc.1
0x31ca3  ret
```
