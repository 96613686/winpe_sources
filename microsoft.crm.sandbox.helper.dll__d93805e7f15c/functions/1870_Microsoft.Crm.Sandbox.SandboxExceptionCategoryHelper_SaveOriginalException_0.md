# Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException_0

- ea: `0x1870`
- end: `0x18c0`
- name: `Microsoft.Crm.Sandbox.SandboxExceptionCategoryHelper::SaveOriginalException_0`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1850`

## callees

- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1870  ldarg.0
0x1871  brfalse.s loc_18BF
0x1873  ldarg.0
0x1874  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1879  brfalse.s loc_18BF
0x187b  ldarg.1
0x187c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1881  brtrue.s loc_18BF
0x1883  ldarg.0
0x1884  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1889  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_ExceptionSource()
0x188e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1893  brfalse.s loc_18BF
0x1895  ldarg.0
0x1896  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x189b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::get_OriginalException()
0x18a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18a5  brfalse.s loc_18BF
0x18a7  ldarg.0
0x18a8  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x18ad  ldarg.1
0x18ae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_OriginalException(string)
0x18b3  ldarg.0
0x18b4  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x18b9  ldarg.2
0x18ba  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault::set_ExceptionSource(string)
0x18bf  ret
```
