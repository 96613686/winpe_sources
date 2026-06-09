# Microsoft.Crm.Common.Web.Activities.CreateDialog::AddActivityItems

- ea: `0xb670`
- end: `0xb826`
- name: `Microsoft.Crm.Common.Web.Activities.CreateDialog::AddActivityItems`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb5f0`

## callees

- `0xb670`
- `0xb830`

## pseudocode

```c

```

## disassembly

```asm
0xb670  ldstr    aUl// "ul"
0xb675  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xb67a  stloc.0
0xb67b  ldloc.0
0xb67c  ldstr    aTblitems// "tblItems"
0xb681  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xb686  ldloc.0
0xb687  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xb68c  ldstr    aClass// "class"
0xb691  ldstr    aMsCrmDialogLis// "ms-crm-Dialog-List"
0xb696  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xb69b  ldloc.0
0xb69c  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xb6a1  ldc.i4.s 0xB
0xb6a3  ldstr    a100// "100%"
0xb6a8  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(valuetype [System.Web]System.Web.UI.HtmlTextWriterStyle, string)
0xb6ad  ldarg.0
0xb6ae  ldfld    class [System.Web]System.Web.UI.WebControls.PlaceHolder Microsoft.Crm.Common.Web.Activities.CreateDialog::activitiesList
0xb6b3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xb6b8  ldloc.0
0xb6b9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xb6be  ldarg.0
0xb6bf  ldloc.0
0xb6c0  ldc.i4   0x1074
0xb6c5  ldc.i4.1
0xb6c6  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb6cb  dup
0xb6cc  ldc.i4.0
0xb6cd  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb6d2  stelem.ref
0xb6d3  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb6d8  ldarg.0
0xb6d9  ldloc.0
0xb6da  ldc.i4   0x106C
0xb6df  ldc.i4.1
0xb6e0  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb6e5  dup
0xb6e6  ldc.i4.0
0xb6e7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb6ec  stelem.ref
0xb6ed  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb6f2  ldarg.0
0xb6f3  ldloc.0
0xb6f4  ldc.i4   0x1072
0xb6f9  ldc.i4.1
0xb6fa  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb6ff  dup
0xb700  ldc.i4.0
0xb701  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb706  stelem.ref
0xb707  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb70c  ldarg.0
0xb70d  ldloc.0
0xb70e  ldc.i4   0x106A
0xb713  ldc.i4.1
0xb714  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb719  dup
0xb71a  ldc.i4.0
0xb71b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb720  stelem.ref
0xb721  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb726  ldarg.0
0xb727  ldloc.0
0xb728  ldc.i4   0x106F
0xb72d  ldc.i4.1
0xb72e  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb733  dup
0xb734  ldc.i4.0
0xb735  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb73a  stelem.ref
0xb73b  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb740  ldarg.0
0xb741  ldloc.0
0xb742  ldc.i4   0x1069
0xb747  ldc.i4.1
0xb748  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb74d  dup
0xb74e  ldc.i4.0
0xb74f  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb754  stelem.ref
0xb755  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb75a  ldarg.0
0xb75b  ldloc.0
0xb75c  ldc.i4   0x1076
0xb761  ldc.i4.3
0xb762  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb767  dup
0xb768  ldc.i4.0
0xb769  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb76e  stelem.ref
0xb76f  dup
0xb770  ldc.i4.1
0xb771  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadService()
0xb776  stelem.ref
0xb777  dup
0xb778  ldc.i4.2
0xb779  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToService()
0xb77e  stelem.ref
0xb77f  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb784  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToCampaign()
0xb789  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb78e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb793  brtrue.s loc_B7A6
0xb795  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendToActivity()
0xb79a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb79f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb7a4  brfalse.s loc_B7C8
0xb7a6  ldarg.0
0xb7a7  ldloc.0
0xb7a8  ldc.i4   0x1131
0xb7ad  ldc.i4.2
0xb7ae  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb7b3  dup
0xb7b4  ldc.i4.0
0xb7b5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb7ba  stelem.ref
0xb7bb  dup
0xb7bc  ldc.i4.1
0xb7bd  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_AppendActivity()
0xb7c2  stelem.ref
0xb7c3  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb7c8  ldarg.0
0xb7c9  ldloc.0
0xb7ca  ldc.i4   0x109B
0xb7cf  ldc.i4.1
0xb7d0  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb7d5  dup
0xb7d6  ldc.i4.0
0xb7d7  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb7dc  stelem.ref
0xb7dd  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb7e2  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::get_CustomActivitiesByName()
0xb7e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::GetEnumerator()
0xb7ec  stloc.1
0xb7ed  br.s     loc_B811
0xb7ef  ldloc.1
0xb7f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Current()
0xb7f5  stloc.2
0xb7f6  ldarg.0
0xb7f7  ldloc.0
0xb7f8  ldloc.2
0xb7f9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xb7fe  ldc.i4.1
0xb7ff  newarr   [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition
0xb804  dup
0xb805  ldc.i4.0
0xb806  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateActivity()
0xb80b  stelem.ref
0xb80c  call     instance void Microsoft.Crm.Common.Web.Activities.CreateDialog::AddListItem(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl listControl, int32 objectTypeCode, class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition[] privileges)
0xb811  ldloc.1
0xb812  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb817  brtrue.s loc_B7EF
0xb819  leave.s  loc_B825
0xb81b  ldloc.1
0xb81c  brfalse.s loc_B824
0xb81e  ldloc.1
0xb81f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb824  endfinally
0xb825  ret
```
