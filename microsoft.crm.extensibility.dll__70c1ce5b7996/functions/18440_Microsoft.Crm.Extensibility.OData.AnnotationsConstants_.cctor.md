# Microsoft.Crm.Extensibility.OData.AnnotationsConstants::.cctor

- ea: `0x18440`
- end: `0x184bf`
- name: `Microsoft.Crm.Extensibility.OData.AnnotationsConstants::.cctor`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1847c`: `OData.Community.Display.V1`

## pseudocode

```c

```

## disassembly

```asm
0x18440  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18445  ldstr    a01_0// "{0}.{1}"
0x1844a  ldc.i4.2
0x1844b  newarr   [mscorlib]System.Object
0x18450  dup
0x18451  ldc.i4.0
0x18452  ldstr    aMicrosoftDynam_0// "Microsoft.Dynamics.CRM"
0x18457  stelem.ref
0x18458  dup
0x18459  ldc.i4.1
0x1845a  ldstr    aLookuplogicaln// "lookuplogicalname"
0x1845f  stelem.ref
0x18460  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18465  stsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityLogicalNameAnnotation
0x1846a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1846f  ldstr    a01_0// "{0}.{1}"
0x18474  ldc.i4.2
0x18475  newarr   [mscorlib]System.Object
0x1847a  dup
0x1847b  ldc.i4.0
0x1847c  ldstr    aOdataCommunity_1// "OData.Community.Display.V1"
0x18481  stelem.ref
0x18482  dup
0x18483  ldc.i4.1
0x18484  ldstr    aFormattedvalue// "FormattedValue"
0x18489  stelem.ref
0x1848a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1848f  stsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityDisplayNameAnnotation
0x18494  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18499  ldstr    a01_0// "{0}.{1}"
0x1849e  ldc.i4.2
0x1849f  newarr   [mscorlib]System.Object
0x184a4  dup
0x184a5  ldc.i4.0
0x184a6  ldstr    aMicrosoftDynam_0// "Microsoft.Dynamics.CRM"
0x184ab  stelem.ref
0x184ac  dup
0x184ad  ldc.i4.1
0x184ae  ldstr    aAssociatednavi// "associatednavigationproperty"
0x184b3  stelem.ref
0x184b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x184b9  stsfld   string Microsoft.Crm.Extensibility.OData.AnnotationsConstants::LookupEntityAssociatedNavigationPropertyAnnotation
0x184be  ret
```
