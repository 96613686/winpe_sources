# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DurationControl::CreateDurationOptions

- ea: `0xab90`
- end: `0xaf76`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.DurationControl::CreateDurationOptions`
- size: `998`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa450`
- `0x131a0`

## pseudocode

```c

```

## disassembly

```asm
0xab90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xab95  stloc.0
0xab96  ldloc.0
0xab97  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xab9c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaba1  ldstr    aAppdurationcon// "AppDurationControl_Minute"
0xaba6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xabab  ldc.i4.1
0xabac  newarr   [mscorlib]System.Object
0xabb1  dup
0xabb2  ldc.i4.0
0xabb3  ldstr    a1_0// "1"
0xabb8  stelem.ref
0xabb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xabbe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xabc3  ldloc.0
0xabc4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xabc9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xabce  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xabd3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xabd8  ldc.i4.1
0xabd9  newarr   [mscorlib]System.Object
0xabde  dup
0xabdf  ldc.i4.0
0xabe0  ldstr    a15// "15"
0xabe5  stelem.ref
0xabe6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xabeb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xabf0  ldloc.0
0xabf1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xabf6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xabfb  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xac00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac05  ldc.i4.1
0xac06  newarr   [mscorlib]System.Object
0xac0b  dup
0xac0c  ldc.i4.0
0xac0d  ldstr    a30// "30"
0xac12  stelem.ref
0xac13  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac18  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac1d  ldloc.0
0xac1e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xac28  ldstr    aAppdurationcon_0// "AppDurationControl_Minutes"
0xac2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac32  ldc.i4.1
0xac33  newarr   [mscorlib]System.Object
0xac38  dup
0xac39  ldc.i4.0
0xac3a  ldstr    a45// "45"
0xac3f  stelem.ref
0xac40  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac45  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac4a  ldloc.0
0xac4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac50  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xac55  ldstr    aAppdurationcon_1// "AppDurationControl_Hour"
0xac5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac5f  ldc.i4.1
0xac60  newarr   [mscorlib]System.Object
0xac65  dup
0xac66  ldc.i4.0
0xac67  ldstr    a1_0// "1"
0xac6c  stelem.ref
0xac6d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xac77  ldloc.0
0xac78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xac7d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xac82  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xac87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xac8c  ldc.i4.1
0xac8d  newarr   [mscorlib]System.Object
0xac92  dup
0xac93  ldc.i4.0
0xac94  ldstr    a15_0// "1.5"
0xac99  stelem.ref
0xac9a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xac9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaca4  ldloc.0
0xaca5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xacaa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xacaf  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xacb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xacb9  ldc.i4.1
0xacba  newarr   [mscorlib]System.Object
0xacbf  dup
0xacc0  ldc.i4.0
0xacc1  ldstr    a2// "2"
0xacc6  stelem.ref
0xacc7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaccc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xacd1  ldloc.0
0xacd2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xacd7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xacdc  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xace1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xace6  ldc.i4.1
0xace7  newarr   [mscorlib]System.Object
0xacec  dup
0xaced  ldc.i4.0
0xacee  ldstr    a25// "2.5"
0xacf3  stelem.ref
0xacf4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xacf9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xacfe  ldloc.0
0xacff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad09  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xad0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad13  ldc.i4.1
0xad14  newarr   [mscorlib]System.Object
0xad19  dup
0xad1a  ldc.i4.0
0xad1b  ldstr    a3// "3"
0xad20  stelem.ref
0xad21  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xad2b  ldloc.0
0xad2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad36  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xad3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad40  ldc.i4.1
0xad41  newarr   [mscorlib]System.Object
0xad46  dup
0xad47  ldc.i4.0
0xad48  ldstr    a35// "3.5"
0xad4d  stelem.ref
0xad4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xad58  ldloc.0
0xad59  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad5e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad63  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xad68  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad6d  ldc.i4.1
0xad6e  newarr   [mscorlib]System.Object
0xad73  dup
0xad74  ldc.i4.0
0xad75  ldstr    a4// "4"
0xad7a  stelem.ref
0xad7b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xad80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xad85  ldloc.0
0xad86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xad8b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xad90  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xad95  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xad9a  ldc.i4.1
0xad9b  newarr   [mscorlib]System.Object
0xada0  dup
0xada1  ldc.i4.0
0xada2  ldstr    a45_0// "4.5"
0xada7  stelem.ref
0xada8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xadad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xadb2  ldloc.0
0xadb3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xadb8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xadbd  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xadc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadc7  ldc.i4.1
0xadc8  newarr   [mscorlib]System.Object
0xadcd  dup
0xadce  ldc.i4.0
0xadcf  ldstr    a5// "5"
0xadd4  stelem.ref
0xadd5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xadda  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaddf  ldloc.0
0xade0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xade5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xadea  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xadef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadf4  ldc.i4.1
0xadf5  newarr   [mscorlib]System.Object
0xadfa  dup
0xadfb  ldc.i4.0
0xadfc  ldstr    a55// "5.5"
0xae01  stelem.ref
0xae02  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xae0c  ldloc.0
0xae0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae12  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xae17  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xae1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae21  ldc.i4.1
0xae22  newarr   [mscorlib]System.Object
0xae27  dup
0xae28  ldc.i4.0
0xae29  ldstr    a6// "6"
0xae2e  stelem.ref
0xae2f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae34  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xae39  ldloc.0
0xae3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae3f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xae44  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xae49  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae4e  ldc.i4.1
0xae4f  newarr   [mscorlib]System.Object
0xae54  dup
0xae55  ldc.i4.0
0xae56  ldstr    a65// "6.5"
0xae5b  stelem.ref
0xae5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xae66  ldloc.0
0xae67  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae6c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xae71  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xae76  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xae7b  ldc.i4.1
0xae7c  newarr   [mscorlib]System.Object
0xae81  dup
0xae82  ldc.i4.0
0xae83  ldstr    a7// "7"
0xae88  stelem.ref
0xae89  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xae8e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xae93  ldloc.0
0xae94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xae99  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xae9e  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xaea3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaea8  ldc.i4.1
0xaea9  newarr   [mscorlib]System.Object
0xaeae  dup
0xaeaf  ldc.i4.0
0xaeb0  ldstr    a75// "7.5"
0xaeb5  stelem.ref
0xaeb6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaebb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaec0  ldloc.0
0xaec1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaec6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaecb  ldstr    aAppdurationcon_2// "AppDurationControl_Hours"
0xaed0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaed5  ldc.i4.1
0xaed6  newarr   [mscorlib]System.Object
0xaedb  dup
0xaedc  ldc.i4.0
0xaedd  ldstr    a8// "8"
0xaee2  stelem.ref
0xaee3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaee8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaeed  ldloc.0
0xaeee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaef3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaef8  ldstr    aAppdurationcon_3// "AppDurationControl_Day"
0xaefd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaf02  ldc.i4.1
0xaf03  newarr   [mscorlib]System.Object
0xaf08  dup
0xaf09  ldc.i4.0
0xaf0a  ldstr    a1_0// "1"
0xaf0f  stelem.ref
0xaf10  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaf15  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaf1a  ldloc.0
0xaf1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf20  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaf25  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0xaf2a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaf2f  ldc.i4.1
0xaf30  newarr   [mscorlib]System.Object
0xaf35  dup
0xaf36  ldc.i4.0
0xaf37  ldstr    a2// "2"
0xaf3c  stelem.ref
0xaf3d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaf42  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaf47  ldloc.0
0xaf48  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaf4d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaf52  ldstr    aAppdurationcon_4// "AppDurationControl_Days"
0xaf57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaf5c  ldc.i4.1
0xaf5d  newarr   [mscorlib]System.Object
0xaf62  dup
0xaf63  ldc.i4.0
0xaf64  ldstr    a3// "3"
0xaf69  stelem.ref
0xaf6a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xaf6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xaf74  ldloc.0
0xaf75  ret
```
