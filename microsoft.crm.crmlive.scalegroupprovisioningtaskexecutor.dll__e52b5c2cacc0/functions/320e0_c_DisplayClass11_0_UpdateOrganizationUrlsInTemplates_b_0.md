# <>c__DisplayClass11_0::<UpdateOrganizationUrlsInTemplates>b__0

- ea: `0x320e0`
- end: `0x32264`
- name: `<>c__DisplayClass11_0::<UpdateOrganizationUrlsInTemplates>b__0`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x320e0`

## string_xrefs

- `0x320e6`: `Template`
- `0x32108`: `presentationxml`
- `0x321e8`: `presentationxml`
- `0x3221d`: `presentationxml`
- `0x32118`: `templatetypecode`
- `0x32184`: `templatetypecode`

## pseudocode

```c

```

## disassembly

```asm
0x320e0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.TemplateService::.ctor()
0x320e5  stloc.0
0x320e6  ldstr    aTemplate// "Template"
0x320eb  ldarg.1
0x320ec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x320f1  stloc.1
0x320f2  ldloc.1
0x320f3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x320f8  ldstr    aBody// "body"
0x320fd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x32102  ldloc.1
0x32103  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x32108  ldstr    aPresentationxm// "presentationxml"
0x3210d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x32112  ldloc.1
0x32113  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x32118  ldstr    aTemplatetypeco// "templatetypecode"
0x3211d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x32122  ldloc.0
0x32123  ldloc.1
0x32124  ldarg.1
0x32125  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3212a  ldarg.0
0x3212b  ldfld    string <>c__DisplayClass11_0::newFullDomain
0x32130  ldarg.0
0x32131  ldfld    string <>c__DisplayClass11_0::newFullDomain
0x32136  ldc.i4.s 0x2E
0x32138  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x3213d  ldc.i4.1
0x3213e  add
0x3213f  callvirt instance string [mscorlib]System.String::Substring(int32)
0x32144  stloc.2
0x32145  ldstr    aHttps// "https://"
0x3214a  ldarg.0
0x3214b  ldfld    string <>c__DisplayClass11_0::newFullDomain
0x32150  call     string [mscorlib]System.String::Concat(string, string)
0x32155  stloc.3
0x32156  ldstr    aHttpsW// "https://([\\w\\-]*)\\."
0x3215b  ldloc.2
0x3215c  call     string [System]System.Text.RegularExpressions.Regex::Escape(string)
0x32161  call     string [mscorlib]System.String::Concat(string, string)
0x32166  stloc.s  4
0x32168  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3216d  stloc.s  5
0x3216f  br       loc_32240
0x32174  ldloc.s  5
0x32176  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3217b  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x32180  stloc.s  6
0x32182  ldloc.s  6
0x32184  ldstr    aTemplatetypeco// "templatetypecode"
0x32189  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3218e  unbox.any [mscorlib]System.Int32
0x32193  ldc.i4   0x125C
0x32198  bne.un   loc_32240
0x3219d  ldc.i4.0
0x3219e  stloc.s  7
0x321a0  ldloc.s  6
0x321a2  ldstr    aBody// "body"
0x321a7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x321ac  castclass [mscorlib]System.String
0x321b1  stloc.s  8
0x321b3  ldloc.s  8
0x321b5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x321ba  brtrue.s loc_321E6
0x321bc  ldloc.s  8
0x321be  ldloc.s  4
0x321c0  ldloc.3
0x321c1  ldc.i4.1
0x321c2  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x321c7  stloc.s  0xA
0x321c9  ldloc.s  0xA
0x321cb  ldloc.s  8
0x321cd  ldc.i4.5
0x321ce  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x321d3  brtrue.s loc_321E6
0x321d5  ldloc.s  6
0x321d7  ldstr    aBody// "body"
0x321dc  ldloc.s  0xA
0x321de  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x321e3  ldc.i4.1
0x321e4  stloc.s  7
0x321e6  ldloc.s  6
0x321e8  ldstr    aPresentationxm// "presentationxml"
0x321ed  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x321f2  castclass [mscorlib]System.String
0x321f7  stloc.s  9
0x321f9  ldloc.s  9
0x321fb  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x32200  brtrue.s loc_3222C
0x32202  ldloc.s  9
0x32204  ldloc.s  4
0x32206  ldloc.3
0x32207  ldc.i4.1
0x32208  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3220d  stloc.s  0xB
0x3220f  ldloc.s  0xB
0x32211  ldloc.s  9
0x32213  ldc.i4.5
0x32214  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x32219  brtrue.s loc_3222C
0x3221b  ldloc.s  6
0x3221d  ldstr    aPresentationxm// "presentationxml"
0x32222  ldloc.s  0xB
0x32224  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x32229  ldc.i4.1
0x3222a  stloc.s  7
0x3222c  ldloc.s  7
0x3222e  brfalse.s loc_32240
0x32230  ldarg.0
0x32231  ldc.i4.1
0x32232  stfld    bool <>c__DisplayClass11_0::anyTemplateUpdated
0x32237  ldloc.0
0x32238  ldloc.s  6
0x3223a  ldarg.1
0x3223b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32240  ldloc.s  5
0x32242  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32247  brtrue   loc_32174
0x3224c  leave.s  loc_32263
0x3224e  ldloc.s  5
0x32250  isinst   [mscorlib]System.IDisposable
0x32255  stloc.s  0xC
0x32257  ldloc.s  0xC
0x32259  brfalse.s loc_32262
0x3225b  ldloc.s  0xC
0x3225d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32262  endfinally
0x32263  ret
```
