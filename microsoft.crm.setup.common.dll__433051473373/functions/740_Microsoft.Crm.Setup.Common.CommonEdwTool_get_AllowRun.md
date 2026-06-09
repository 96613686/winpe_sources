# Microsoft.Crm.Setup.Common.CommonEdwTool::get_AllowRun

- ea: `0x740`
- end: `0x7cc`
- name: `Microsoft.Crm.Setup.Common.CommonEdwTool::get_AllowRun`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2740`
- `0x50a0`

## callees

- `0x730`
- `0x740`

## pseudocode

```c

```

## disassembly

```asm
0x740  ldc.i4.0
0x741  stloc.0
0x742  ldarg.0
0x743  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool::get_Results()
0x748  callvirt instance class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.GroupCollection [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWToolResults::GetFailedGroups()
0x74d  stloc.1
0x74e  ldloc.1
0x74f  brfalse.s loc_759
0x751  ldloc.1
0x752  callvirt instance int32 [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.GroupCollection::get_Count()
0x757  brtrue.s loc_75D
0x759  ldc.i4.1
0x75a  stloc.0
0x75b  br.s     loc_7CA
0x75d  ldarg.0
0x75e  callvirt instance string Microsoft.Crm.Setup.Common.CommonEdwTool::get_ComponentRegistryKeyName()
0x763  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x768  brtrue.s loc_7CA
0x76a  ldnull
0x76b  stloc.2
0x76c  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x771  ldarg.0
0x772  callvirt instance string Microsoft.Crm.Setup.Common.CommonEdwTool::get_ComponentRegistryKeyName()
0x777  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x77c  stloc.3
0x77d  ldloc.3
0x77e  brfalse.s loc_792
0x780  ldloc.3
0x781  ldstr    aIgnorechecks// "IgnoreChecks"
0x786  ldc.i4.0
0x787  box      [mscorlib]System.Int32
0x78c  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x791  stloc.2
0x792  leave.s  loc_79E
0x794  ldloc.3
0x795  brfalse.s loc_79D
0x797  ldloc.3
0x798  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79d  endfinally
0x79e  ldloc.2
0x79f  brfalse.s loc_7CA
0x7a1  ldloc.2
0x7a2  ldc.i4.1
0x7a3  box      [mscorlib]System.Int32
0x7a8  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7ad  brfalse.s loc_7CA
0x7af  ldstr    aIgnorechecksSp// "IgnoreChecks specified in {0}, Allowing"...
0x7b4  ldc.i4.1
0x7b5  newarr   [mscorlib]System.Object
0x7ba  dup
0x7bb  ldc.i4.0
0x7bc  ldarg.0
0x7bd  callvirt instance string Microsoft.Crm.Setup.Common.CommonEdwTool::get_ComponentRegistryKeyName()
0x7c2  stelem.ref
0x7c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x7c8  ldc.i4.1
0x7c9  stloc.0
0x7ca  ldloc.0
0x7cb  ret
```
