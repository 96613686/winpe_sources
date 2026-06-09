# Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetSCInitializedRow

- ea: `0xb8710`
- end: `0xb8951`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::GetSCInitializedRow`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xbb2e0`

## callees

- `0xb8620`
- `0xb8710`

## string_xrefs

- `0xb8786`: `componenttype`
- `0xb87fc`: `componenttype`
- `0xb8807`: `componenttype`
- `0xb87a9`: `solutioncomponentid`
- `0xb87bc`: `solutioncomponentid`
- `0xb87c7`: `solutioncomponentid`
- `0xb87e5`: `solutioncomponentid`

## pseudocode

```c

```

## disassembly

```asm
0xb8710  ldnull
0xb8711  stloc.0
0xb8712  ldarg.0
0xb8713  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::InitializeSolutionComponentColumnSet()
0xb8718  ldarg.0
0xb8719  ldfld    string[] Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::returnColumnSet
0xb871e  ldlen
0xb871f  conv.i4
0xb8720  newarr   [mscorlib]System.String
0xb8725  stloc.0
0xb8726  ldloc.0
0xb8727  ldarg.0
0xb8728  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb872d  ldstr    aOid// "oid"
0xb8732  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8737  ldarg.1
0xb8738  ldstr    aObjectid// "objectid"
0xb873d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8742  unbox.any [mscorlib]System.Guid
0xb8747  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xb874c  stelem.ref
0xb874d  ldloc.0
0xb874e  ldarg.0
0xb874f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8754  ldstr    aSolutionid// "solutionid"
0xb8759  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb875e  ldarg.1
0xb875f  ldstr    aSolutionid// "solutionid"
0xb8764  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8769  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xb876e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xb8773  stelem.ref
0xb8774  ldloc.0
0xb8775  ldarg.0
0xb8776  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb877b  ldstr    aMoid// "moid"
0xb8780  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8785  ldarg.1
0xb8786  ldstr    aComponenttype// "componenttype"
0xb878b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8790  unbox.any [mscorlib]System.Int32
0xb8795  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjectTypeCode(int32)
0xb879a  stloc.1
0xb879b  ldloca.s 1
0xb879d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb87a2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb87a7  stelem.ref
0xb87a8  ldarg.1
0xb87a9  ldstr    aSolutioncompon_0// "solutioncomponentid"
0xb87ae  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb87b3  brfalse.s loc_B87DE
0xb87b5  ldloc.0
0xb87b6  ldarg.0
0xb87b7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb87bc  ldstr    aSolutioncompon_0// "solutioncomponentid"
0xb87c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb87c6  ldarg.1
0xb87c7  ldstr    aSolutioncompon_0// "solutioncomponentid"
0xb87cc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb87d1  unbox.any [mscorlib]System.Guid
0xb87d6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xb87db  stelem.ref
0xb87dc  br.s     loc_B87F5
0xb87de  ldloc.0
0xb87df  ldarg.0
0xb87e0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb87e5  ldstr    aSolutioncompon_0// "solutioncomponentid"
0xb87ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb87ef  ldsfld   string [mscorlib]System.String::Empty
0xb87f4  stelem.ref
0xb87f5  ldloc.0
0xb87f6  ldarg.0
0xb87f7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb87fc  ldstr    aComponenttype// "componenttype"
0xb8801  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8806  ldarg.1
0xb8807  ldstr    aComponenttype// "componenttype"
0xb880c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xb8811  unbox.any [mscorlib]System.Int32
0xb8816  stloc.1
0xb8817  ldloca.s 1
0xb8819  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb881e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb8823  stelem.ref
0xb8824  ldloc.0
0xb8825  ldarg.0
0xb8826  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb882b  ldstr    aSubtype// "subtype"
0xb8830  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8835  ldsfld   string [mscorlib]System.String::Empty
0xb883a  stelem.ref
0xb883b  ldloc.0
0xb883c  ldarg.0
0xb883d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8842  ldstr    aDisplayname// "displayname"
0xb8847  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb884c  ldsfld   string [mscorlib]System.String::Empty
0xb8851  stelem.ref
0xb8852  ldloc.0
0xb8853  ldarg.0
0xb8854  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8859  ldstr    aName// "name"
0xb885e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8863  ldsfld   string [mscorlib]System.String::Empty
0xb8868  stelem.ref
0xb8869  ldloc.0
0xb886a  ldarg.0
0xb886b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8870  ldstr    aType// "type"
0xb8875  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb887a  ldsfld   string [mscorlib]System.String::Empty
0xb887f  stelem.ref
0xb8880  ldloc.0
0xb8881  ldarg.0
0xb8882  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8887  ldstr    aDescription// "description"
0xb888c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8891  ldsfld   string [mscorlib]System.String::Empty
0xb8896  stelem.ref
0xb8897  ldloc.0
0xb8898  ldarg.0
0xb8899  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb889e  ldstr    aSolutionname// "solutionname"
0xb88a3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb88a8  ldsfld   string [mscorlib]System.String::Empty
0xb88ad  stelem.ref
0xb88ae  ldloc.0
0xb88af  ldarg.0
0xb88b0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb88b5  ldstr    aOtc// "otc"
0xb88ba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb88bf  ldsfld   string [mscorlib]System.String::Empty
0xb88c4  stelem.ref
0xb88c5  ldloc.0
0xb88c6  ldarg.0
0xb88c7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb88cc  ldstr    aParententity_0// "parententity"
0xb88d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb88d6  ldsfld   string [mscorlib]System.String::Empty
0xb88db  stelem.ref
0xb88dc  ldloc.0
0xb88dd  ldarg.0
0xb88de  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb88e3  ldstr    aDependencytype// "dependencytype"
0xb88e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb88ed  ldsfld   string [mscorlib]System.String::Empty
0xb88f2  stelem.ref
0xb88f3  ldloc.0
0xb88f4  ldarg.0
0xb88f5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb88fa  ldstr    aParententityid// "parententityid"
0xb88ff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8904  ldsfld   string [mscorlib]System.String::Empty
0xb8909  stelem.ref
0xb890a  ldloc.0
0xb890b  ldarg.0
0xb890c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8911  ldstr    aParenttype_1// "parenttype"
0xb8916  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb891b  ldsfld   string [mscorlib]System.String::Empty
0xb8920  stelem.ref
0xb8921  ldloc.0
0xb8922  ldarg.0
0xb8923  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb8928  ldstr    aDependencytype_0// "dependencytypename"
0xb892d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8932  ldsfld   string [mscorlib]System.String::Empty
0xb8937  stelem.ref
0xb8938  ldloc.0
0xb8939  ldarg.0
0xb893a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Application.Controls.SystemCustomization.ComponentDependencyBaseDataProvider::columnIndex
0xb893f  ldstr    aTypename_0// "typename"
0xb8944  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0xb8949  ldsfld   string [mscorlib]System.String::Empty
0xb894e  stelem.ref
0xb894f  ldloc.0
0xb8950  ret
```
