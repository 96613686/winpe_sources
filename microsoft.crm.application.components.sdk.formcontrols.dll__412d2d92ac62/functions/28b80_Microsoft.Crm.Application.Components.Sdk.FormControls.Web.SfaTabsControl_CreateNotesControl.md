# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateNotesControl

- ea: `0x28b80`
- end: `0x28bfc`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::CreateNotesControl`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x28820`

## callees

- `0x20f40`
- `0x216b0`
- `0x216d0`
- `0x216f0`
- `0x28640`
- `0x28b80`
- `0x290e0`
- `0x29e70`
- `0x29e90`
- `0x29eb0`
- `0x29f00`
- `0x29f60`

## pseudocode

```c

```

## disassembly

```asm
0x28b80  ldarg.1
0x28b81  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_HasNotes()
0x28b86  brfalse.s loc_28BFB
0x28b88  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::.ctor()
0x28b8d  dup
0x28b8e  ldstr    aNotesv2control// "notesv2control_"
0x28b93  ldarg.0
0x28b94  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28b99  call     string [mscorlib]System.String::Concat(string, string)
0x28b9e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x28ba3  dup
0x28ba4  ldarg.0
0x28ba5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x28baa  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::set_MasterComponentId(string value)
0x28baf  dup
0x28bb0  ldarg.1
0x28bb1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x28bb6  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::set_ParentLogicalName(string value)
0x28bbb  dup
0x28bbc  ldarg.0
0x28bbd  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::get_IsControlReadOnly()
0x28bc2  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::set_IsControlReadOnly(bool value)
0x28bc7  stloc.0
0x28bc8  ldarg.0
0x28bc9  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabsControl::get_Items()
0x28bce  newobj   instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::.ctor()
0x28bd3  dup
0x28bd4  ldstr    aNotestab// "NotesTab"
0x28bd9  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabId(string value)
0x28bde  dup
0x28bdf  ldloc.0
0x28be0  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_Control(class [System.Web]System.Web.UI.Control value)
0x28be5  dup
0x28be6  ldarg.0
0x28be7  ldstr    aAnnotation// "annotation"
0x28bec  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SfaTabsControl::GetTabName(string entityTypeName)
0x28bf1  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer::set_TabName(string value)
0x28bf6  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TabDataContainer>::Add(var<u1>)
0x28bfb  ret
```
