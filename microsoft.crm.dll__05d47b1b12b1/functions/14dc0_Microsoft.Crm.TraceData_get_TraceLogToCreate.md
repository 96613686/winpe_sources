# Microsoft.Crm.TraceData::get_TraceLogToCreate

- ea: `0x14dc0`
- end: `0x15020`
- name: `Microsoft.Crm.TraceData::get_TraceLogToCreate`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14ba0`
- `0x14bc0`
- `0x14be0`
- `0x14c00`
- `0x14c20`
- `0x14c40`
- `0x14c60`
- `0x14c80`
- `0x14ca0`
- `0x14cc0`
- `0x14ce0`
- `0x14dc0`
- `0x15020`
- `0x15040`
- `0x15060`

## string_xrefs

- `0x14e46`: `canbedeleted`
- `0x14efe`: `traceparameterxml`
- `0x14f7d`: `traceactionxml`
- `0x14fff`: `tracedetailxml`

## pseudocode

```c

```

## disassembly

```asm
0x14dc0  ldstr    aTracelog// "tracelog"
0x14dc5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x14dca  stloc.0
0x14dcb  ldloc.0
0x14dcc  ldstr    aTracecode// "tracecode"
0x14dd1  ldarg.0
0x14dd2  call     instance int32 Microsoft.Crm.TraceData::get_TraceCode()
0x14dd7  box      [mscorlib]System.Int32
0x14ddc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14de1  ldloc.0
0x14de2  ldstr    aLevel// "level"
0x14de7  ldarg.0
0x14de8  call     instance int32 Microsoft.Crm.TraceData::get_Level()
0x14ded  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x14df2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14df7  ldloc.0
0x14df8  ldstr    aRegardingobjec// "regardingobjectid"
0x14dfd  ldarg.0
0x14dfe  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.TraceData::get_TraceRegarding()
0x14e03  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e08  ldloc.0
0x14e09  ldstr    aIsunique// "isunique"
0x14e0e  ldarg.0
0x14e0f  call     instance bool Microsoft.Crm.TraceData::get_IsUnique()
0x14e14  box      [mscorlib]System.Boolean
0x14e19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e1e  ldloc.0
0x14e1f  ldstr    aParenttracelog// "parenttracelogid"
0x14e24  ldarg.0
0x14e25  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.TraceData::get_ParentTraceLog()
0x14e2a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e2f  ldloc.0
0x14e30  ldstr    aCollationlevel// "collationlevel"
0x14e35  ldarg.0
0x14e36  call     instance int32 Microsoft.Crm.TraceData::get_CollationLevel()
0x14e3b  box      [mscorlib]System.Int32
0x14e40  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e45  ldloc.0
0x14e46  ldstr    aCanbedeleted// "canbedeleted"
0x14e4b  ldarg.0
0x14e4c  call     instance bool Microsoft.Crm.TraceData::get_CanBeDeleted()
0x14e51  box      [mscorlib]System.Boolean
0x14e56  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e5b  ldloc.0
0x14e5c  ldstr    aMachinename// "machinename"
0x14e61  ldarg.0
0x14e62  call     instance string Microsoft.Crm.TraceData::get_MachineName()
0x14e67  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e6c  ldloc.0
0x14e6d  ldstr    aErrortypedispl// "errortypedisplay"
0x14e72  ldarg.0
0x14e73  call     instance string Microsoft.Crm.TraceData::get_ErrorTypeDisplay()
0x14e78  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e7d  ldloc.0
0x14e7e  ldstr    aTracestatus// "tracestatus"
0x14e83  ldarg.0
0x14e84  call     instance bool Microsoft.Crm.TraceData::get_TraceStatus()
0x14e89  box      [mscorlib]System.Boolean
0x14e8e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e93  ldloc.0
0x14e94  ldstr    aErrordetails// "errordetails"
0x14e99  ldarg.0
0x14e9a  call     instance string Microsoft.Crm.TraceData::get_ErrorDetails()
0x14e9f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14ea4  ldarg.0
0x14ea5  call     instance class Microsoft.Crm.TraceParameterSet Microsoft.Crm.TraceData::get_ParameterSet()
0x14eaa  brfalse.s loc_14F1A
0x14eac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14eb1  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x14eb6  stloc.1
0x14eb7  ldloc.1
0x14eb8  ldc.i4.0
0x14eb9  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x14ebe  stloc.2
0x14ebf  ldtoken  Microsoft.Crm.TraceParameterSet
0x14ec4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ec9  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x14ece  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0x14ed3  stloc.3
0x14ed4  ldloc.3
0x14ed5  ldsfld   string [mscorlib]System.String::Empty
0x14eda  ldsfld   string [mscorlib]System.String::Empty
0x14edf  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::Add(string, string)
0x14ee4  ldloc.2
0x14ee5  ldarg.0
0x14ee6  call     instance class Microsoft.Crm.TraceParameterSet Microsoft.Crm.TraceData::get_ParameterSet()
0x14eeb  ldloc.3
0x14eec  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x14ef1  leave.s  loc_14EFD
0x14ef3  ldloc.2
0x14ef4  brfalse.s loc_14EFC
0x14ef6  ldloc.2
0x14ef7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14efc  endfinally
0x14efd  ldloc.0
0x14efe  ldstr    aTraceparameter// "traceparameterxml"
0x14f03  ldloc.1
0x14f04  callvirt instance string [mscorlib]System.Object::ToString()
0x14f09  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14f0e  leave.s  loc_14F1A
0x14f10  ldloc.1
0x14f11  brfalse.s loc_14F19
0x14f13  ldloc.1
0x14f14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f19  endfinally
0x14f1a  ldarg.0
0x14f1b  call     instance class Microsoft.Crm.TraceActionSet Microsoft.Crm.TraceData::get_ActionSet()
0x14f20  brfalse.s loc_14F9C
0x14f22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14f27  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x14f2c  stloc.s  4
0x14f2e  ldloc.s  4
0x14f30  ldc.i4.0
0x14f31  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x14f36  stloc.s  5
0x14f38  ldtoken  Microsoft.Crm.TraceActionSet
0x14f3d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14f42  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x14f47  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0x14f4c  stloc.s  6
0x14f4e  ldloc.s  6
0x14f50  ldsfld   string [mscorlib]System.String::Empty
0x14f55  ldsfld   string [mscorlib]System.String::Empty
0x14f5a  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::Add(string, string)
0x14f5f  ldloc.s  5
0x14f61  ldarg.0
0x14f62  call     instance class Microsoft.Crm.TraceActionSet Microsoft.Crm.TraceData::get_ActionSet()
0x14f67  ldloc.s  6
0x14f69  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x14f6e  leave.s  loc_14F7C
0x14f70  ldloc.s  5
0x14f72  brfalse.s loc_14F7B
0x14f74  ldloc.s  5
0x14f76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f7b  endfinally
0x14f7c  ldloc.0
0x14f7d  ldstr    aTraceactionxml// "traceactionxml"
0x14f82  ldloc.s  4
0x14f84  callvirt instance string [mscorlib]System.Object::ToString()
0x14f89  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14f8e  leave.s  loc_14F9C
0x14f90  ldloc.s  4
0x14f92  brfalse.s loc_14F9B
0x14f94  ldloc.s  4
0x14f96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f9b  endfinally
0x14f9c  ldarg.0
0x14f9d  call     instance class Microsoft.Crm.TraceDetailSet Microsoft.Crm.TraceData::get_DetailSet()
0x14fa2  brfalse.s loc_1501E
0x14fa4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14fa9  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x14fae  stloc.s  7
0x14fb0  ldloc.s  7
0x14fb2  ldc.i4.0
0x14fb3  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x14fb8  stloc.s  8
0x14fba  ldtoken  Microsoft.Crm.TraceDetailSet
0x14fbf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14fc4  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x14fc9  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0x14fce  stloc.s  9
0x14fd0  ldloc.s  9
0x14fd2  ldsfld   string [mscorlib]System.String::Empty
0x14fd7  ldsfld   string [mscorlib]System.String::Empty
0x14fdc  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces::Add(string, string)
0x14fe1  ldloc.s  8
0x14fe3  ldarg.0
0x14fe4  call     instance class Microsoft.Crm.TraceDetailSet Microsoft.Crm.TraceData::get_DetailSet()
0x14fe9  ldloc.s  9
0x14feb  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [System.Xml]System.Xml.XmlWriter, object, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x14ff0  leave.s  loc_14FFE
0x14ff2  ldloc.s  8
0x14ff4  brfalse.s loc_14FFD
0x14ff6  ldloc.s  8
0x14ff8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ffd  endfinally
0x14ffe  ldloc.0
0x14fff  ldstr    aTracedetailxml// "tracedetailxml"
0x15004  ldloc.s  7
0x15006  callvirt instance string [mscorlib]System.Object::ToString()
0x1500b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x15010  leave.s  loc_1501E
0x15012  ldloc.s  7
0x15014  brfalse.s loc_1501D
0x15016  ldloc.s  7
0x15018  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1501d  endfinally
0x1501e  ldloc.0
0x1501f  ret
```
