# Microsoft.Crm.Setup.Common.UI.PathSpaceControl::InitializeComponent

- ea: `0xb4d0`
- end: `0xb72e`
- name: `Microsoft.Crm.Setup.Common.UI.PathSpaceControl::InitializeComponent`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb450`

## callees

- `0xb430`

## string_xrefs

- `0xb70a`: `PathSpaceControl`

## pseudocode

```c

```

## disassembly

```asm
0xb4d0  ldtoken  Microsoft.Crm.Setup.Common.PathSpaceControl
0xb4d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb4da  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(class [mscorlib]System.Type)
0xb4df  ldarg.0
0xb4e0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xb4e5  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb4ea  ldarg.0
0xb4eb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb4f0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb4f5  ldarg.0
0xb4f6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb4fb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb500  ldarg.0
0xb501  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb506  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb50b  ldarg.0
0xb50c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xb511  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb516  ldarg.0
0xb517  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xb51c  ldarg.0
0xb51d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb522  ldc.i4.0
0xb523  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xb528  ldarg.0
0xb529  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb52e  ldstr    aTextspaceavail// "textSpaceAvailable"
0xb533  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb538  ldarg.0
0xb539  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb53e  ldc.i4   0x12C
0xb543  ldc.i4.s 0x17
0xb545  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xb54a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xb54f  ldarg.0
0xb550  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb555  ldc.i4.s 0x11
0xb557  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xb55c  ldarg.0
0xb55d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb562  ldc.i4.0
0xb563  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xb568  ldarg.0
0xb569  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb56e  ldstr    aTextspacerequi// "textSpaceRequired"
0xb573  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb578  ldarg.0
0xb579  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb57e  ldc.i4   0x12C
0xb583  ldc.i4.s 0x17
0xb585  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xb58a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xb58f  ldarg.0
0xb590  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb595  ldc.i4.s 0x10
0xb597  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xb59c  ldarg.0
0xb59d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb5a2  ldc.i4.1
0xb5a3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xb5a8  ldarg.0
0xb5a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb5ae  ldc.i4.0
0xb5af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xb5b4  ldarg.0
0xb5b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb5ba  ldstr    aLabelspaceavai// "labelSpaceAvailable"
0xb5bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb5c4  ldarg.0
0xb5c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb5ca  ldc.i4.0
0xb5cb  ldc.i4.s 0x10
0xb5cd  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xb5d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xb5d7  ldarg.0
0xb5d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb5dd  ldc.i4.s 0xF
0xb5df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xb5e4  ldarg.0
0xb5e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb5ea  ldc.i4.1
0xb5eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xb5f0  ldarg.0
0xb5f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb5f6  ldc.i4.0
0xb5f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xb5fc  ldarg.0
0xb5fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb602  ldstr    aLabelspacerequ// "labelSpaceRequired"
0xb607  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb60c  ldarg.0
0xb60d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb612  ldc.i4.0
0xb613  ldc.i4.s 0x10
0xb615  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0xb61a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xb61f  ldarg.0
0xb620  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb625  ldc.i4.s 0xE
0xb627  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xb62c  dup
0xb62d  ldarg.0
0xb62e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb633  ldstr    aTablelayout// "tableLayout"
0xb638  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb63d  ldarg.0
0xb63e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb643  ldc.i4.0
0xb644  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_CellBorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelCellBorderStyle)
0xb649  ldarg.0
0xb64a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb64f  ldc.i4.2
0xb650  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_ColumnCount(int32)
0xb655  ldarg.0
0xb656  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb65b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xb660  ldc.i4.0
0xb661  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType)
0xb666  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xb66b  pop
0xb66c  ldarg.0
0xb66d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb672  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xb677  ldc.i4.0
0xb678  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType)
0xb67d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xb682  pop
0xb683  ldarg.0
0xb684  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb689  ldc.i4.2
0xb68a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_RowCount(int32)
0xb68f  ldarg.0
0xb690  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb695  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xb69a  ldarg.0
0xb69b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb6a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6a5  ldarg.0
0xb6a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb6ab  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xb6b0  ldarg.0
0xb6b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb6b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6bb  ldarg.0
0xb6bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb6c1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xb6c6  ldarg.0
0xb6c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb6cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6d1  ldarg.0
0xb6d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb6d7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xb6dc  ldarg.0
0xb6dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb6e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6e7  ldarg.0
0xb6e8  call     instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::SetLayoutPanelDocking()
0xb6ed  ldarg.0
0xb6ee  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xb6f3  ldarg.0
0xb6f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.PathSpaceControl::tableLayout
0xb6f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6fe  ldarg.0
0xb6ff  ldstr    aThis// "$this"
0xb704  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xb709  ldarg.0
0xb70a  ldstr    aPathspacecontr// "PathSpaceControl"
0xb70f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xb714  ldarg.0
0xb715  ldarg.0
0xb716  ldftn    instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::OnRightToLeftChanged(object sender, class [mscorlib]System.EventArgs e)
0xb71c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xb721  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::add_RightToLeftChanged(class [mscorlib]System.EventHandler)
0xb726  ldarg.0
0xb727  ldc.i4.0
0xb728  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0xb72d  ret
```
