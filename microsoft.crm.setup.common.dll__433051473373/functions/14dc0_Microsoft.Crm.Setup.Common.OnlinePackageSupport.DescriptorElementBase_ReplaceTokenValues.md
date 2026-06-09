# Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::ReplaceTokenValues

- ea: `0x14dc0`
- end: `0x14e9d`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::ReplaceTokenValues`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14830`

## callees

- `0x14dc0`
- `0x14ed0`
- `0x16c50`

## pseudocode

```c

```

## disassembly

```asm
0x14dc0  ldarg.0
0x14dc1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14dc6  callvirt instance class [mscorlib]System.Reflection.PropertyInfo[] [mscorlib]System.Type::GetProperties()
0x14dcb  stloc.0
0x14dcc  ldc.i4.0
0x14dcd  stloc.1
0x14dce  br       loc_14E93
0x14dd3  ldloc.0
0x14dd4  ldloc.1
0x14dd5  ldelem.ref
0x14dd6  stloc.2
0x14dd7  ldloc.2
0x14dd8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x14ddd  stloc.3
0x14dde  ldloc.2
0x14ddf  ldarg.0
0x14de0  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x14de5  stloc.s  4
0x14de7  ldloc.3
0x14de8  ldtoken  [mscorlib]System.String
0x14ded  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14df2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x14df7  brfalse.s loc_14E26
0x14df9  ldloc.2
0x14dfa  ldtoken  [System.Xml]System.Xml.Serialization.XmlAttributeAttribute
0x14dff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14e04  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Attribute> [mscorlib]System.Reflection.CustomAttributeExtensions::GetCustomAttributes(class [mscorlib]System.Reflection.MemberInfo, class [mscorlib]System.Type)
0x14e09  call     T0x2B000018
0x14e0e  brfalse.s loc_14E8F
0x14e10  ldloc.2
0x14e11  ldarg.0
0x14e12  ldarg.1
0x14e13  ldloc.s  4
0x14e15  castclass [mscorlib]System.String
0x14e1a  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::ReplaceTokens(string template)
0x14e1f  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0x14e24  br.s     loc_14E8F
0x14e26  ldloc.s  4
0x14e28  isinst   Microsoft.Crm.Setup.Common.OnlinePackageSupport.IDescriptorElement
0x14e2d  stloc.s  5
0x14e2f  ldloc.s  5
0x14e31  brfalse.s loc_14E3D
0x14e33  ldloc.s  5
0x14e35  ldarg.1
0x14e36  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.IDescriptorElement::ReplaceTokenValues(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap tokenMap)
0x14e3b  br.s     loc_14E8F
0x14e3d  ldloc.s  4
0x14e3f  isinst   [mscorlib]System.Collections.IEnumerable
0x14e44  stloc.s  6
0x14e46  ldloc.s  6
0x14e48  brfalse.s loc_14E8F
0x14e4a  ldloc.s  6
0x14e4c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x14e51  stloc.s  7
0x14e53  br.s     loc_14E6F
0x14e55  ldloc.s  7
0x14e57  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x14e5c  isinst   Microsoft.Crm.Setup.Common.OnlinePackageSupport.IDescriptorElement
0x14e61  stloc.s  5
0x14e63  ldloc.s  5
0x14e65  brfalse.s loc_14E6F
0x14e67  ldloc.s  5
0x14e69  ldarg.1
0x14e6a  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.IDescriptorElement::ReplaceTokenValues(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap tokenMap)
0x14e6f  ldloc.s  7
0x14e71  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x14e76  brtrue.s loc_14E55
0x14e78  leave.s  loc_14E8F
0x14e7a  ldloc.s  7
0x14e7c  isinst   [mscorlib]System.IDisposable
0x14e81  stloc.s  8
0x14e83  ldloc.s  8
0x14e85  brfalse.s loc_14E8E
0x14e87  ldloc.s  8
0x14e89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14e8e  endfinally
0x14e8f  ldloc.1
0x14e90  ldc.i4.1
0x14e91  add
0x14e92  stloc.1
0x14e93  ldloc.1
0x14e94  ldloc.0
0x14e95  ldlen
0x14e96  conv.i4
0x14e97  blt      loc_14DD3
0x14e9c  ret
```
