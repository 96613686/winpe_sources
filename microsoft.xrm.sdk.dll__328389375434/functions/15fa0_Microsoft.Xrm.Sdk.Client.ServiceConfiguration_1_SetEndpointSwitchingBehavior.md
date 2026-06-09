# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::SetEndpointSwitchingBehavior

- ea: `0x15fa0`
- end: `0x16062`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::SetEndpointSwitchingBehavior`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15c60`
- `0x15fa0`
- `0x17660`
- `0x17680`
- `0x176a0`
- `0x19c70`

## pseudocode

```c

```

## disassembly

```asm
0x15fa0  ldarg.0
0x15fa1  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x15fa6  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x15fab  brtrue.s loc_15FAE
0x15fad  ret
0x15fae  ldarg.0
0x15faf  ldarg.0
0x15fb0  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x15fb5  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x15fba  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_PrimaryEndpoint()
0x15fbf  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_PrimaryEndpoint(class [System]System.Uri)
0x15fc4  ldc.i4.0
0x15fc5  stloc.0
0x15fc6  ldc.i4.1
0x15fc7  stloc.1
0x15fc8  ldarg.0
0x15fc9  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x15fce  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x15fd3  callvirt instance bool Microsoft.Xrm.Sdk.Client.ServiceUrls::get_GeneratedFromAlternate()
0x15fd8  brtrue.s loc_1603D
0x15fda  ldarg.0
0x15fdb  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x15fe0  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x15fe5  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x15fea  callvirt T0x2B00005D
0x15fef  stloc.2
0x15ff0  ldloc.2
0x15ff1  brfalse.s loc_1603F
0x15ff3  ldloc.2
0x15ff4  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x15ff9  ldstr    aFailoveravaila// "FailoverAvailable"
0x15ffe  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x16003  brfalse.s loc_1603F
0x16005  ldloc.2
0x16006  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x1600b  ldstr    aFailoveravaila// "FailoverAvailable"
0x16010  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x16015  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1601a  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x1601f  stloc.0
0x16020  ldloc.2
0x16021  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x16026  ldstr    aEndpointenable// "EndpointEnabled"
0x1602b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x16030  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16035  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x1603a  stloc.1
0x1603b  br.s     loc_1603F
0x1603d  ldc.i4.1
0x1603e  stloc.0
0x1603f  ldloc.0
0x16040  brfalse.s loc_16061
0x16042  ldarg.0
0x16043  ldarg.0
0x16044  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpointMetadata()
0x16049  callvirt instance class Microsoft.Xrm.Sdk.Client.ServiceUrls Microsoft.Xrm.Sdk.Client.ServiceEndpointMetadata::get_ServiceUrls()
0x1604e  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.ServiceUrls::get_AlternateEndpoint()
0x16053  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_AlternateEndpoint(class [System]System.Uri)
0x16058  ldloc.1
0x16059  brtrue.s loc_16061
0x1605b  ldarg.0
0x1605c  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::SwitchEndpoint()
0x16061  ret
```
