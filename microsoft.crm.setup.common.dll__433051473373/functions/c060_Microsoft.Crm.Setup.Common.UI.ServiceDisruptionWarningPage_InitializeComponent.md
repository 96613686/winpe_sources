# Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::InitializeComponent

- ea: `0xc060`
- end: `0xc22b`
- name: `Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::InitializeComponent`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbd50`

## string_xrefs

- `0xc16b`: `_serviceList`
- `0xc17b`: `_serviceList`
- `0xc1f7`: `ServiceDisruptionWarningPage`

## pseudocode

```c

```

## disassembly

```asm
0xc060  ldtoken  Microsoft.Crm.Setup.Common.ServiceDisruptionWarningPage
0xc065  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc06a  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(class [mscorlib]System.Type)
0xc06f  ldarg.0
0xc070  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xc075  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc07a  ldarg.0
0xc07b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xc080  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_messageLabel
0xc085  ldarg.0
0xc086  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xc08b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_serviceList
0xc090  ldarg.0
0xc091  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xc096  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xc09b  ldarg.0
0xc09c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0xc0a1  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc0a6  ldarg.0
0xc0a7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc0ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xc0b1  ldarg.0
0xc0b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc0b7  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0xc0bc  ldarg.0
0xc0bd  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xc0c2  dup
0xc0c3  ldarg.0
0xc0c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc0c9  ldstr    aTablelayoutpan// "_tableLayoutPanel"
0xc0ce  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc0d3  ldarg.0
0xc0d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc0d9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xc0de  ldarg.0
0xc0df  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_messageLabel
0xc0e4  ldc.i4.1
0xc0e5  ldc.i4.0
0xc0e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xc0eb  ldarg.0
0xc0ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc0f1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xc0f6  ldarg.0
0xc0f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_serviceList
0xc0fc  ldc.i4.1
0xc0fd  ldc.i4.1
0xc0fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xc103  ldarg.0
0xc104  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc109  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xc10e  ldarg.0
0xc10f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xc114  ldc.i4.1
0xc115  ldc.i4.2
0xc116  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xc11b  ldarg.0
0xc11c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc121  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xc126  ldarg.0
0xc127  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc12c  ldc.i4.0
0xc12d  ldc.i4.0
0xc12e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xc133  ldarg.0
0xc134  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc139  ldstr    aTablelayoutpan// "_tableLayoutPanel"
0xc13e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc143  dup
0xc144  ldarg.0
0xc145  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_messageLabel
0xc14a  ldstr    aMessagelabel// "_messageLabel"
0xc14f  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc154  ldarg.0
0xc155  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_messageLabel
0xc15a  ldstr    aMessagelabel// "_messageLabel"
0xc15f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc164  dup
0xc165  ldarg.0
0xc166  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_serviceList
0xc16b  ldstr    aServicelist// "_serviceList"
0xc170  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc175  ldarg.0
0xc176  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_serviceList
0xc17b  ldstr    aServicelist// "_serviceList"
0xc180  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc185  dup
0xc186  ldarg.0
0xc187  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xc18c  ldstr    aInstructionlab// "_instructionLabel"
0xc191  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc196  ldarg.0
0xc197  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xc19c  ldstr    aInstructionlab// "_instructionLabel"
0xc1a1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc1a6  dup
0xc1a7  ldarg.0
0xc1a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc1ad  ldstr    aAlerticon// "_alertIcon"
0xc1b2  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc1b7  ldarg.0
0xc1b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc1bd  ldstr    aAlerticon// "_alertIcon"
0xc1c2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc1c7  ldarg.0
0xc1c8  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc1cd  ldc.i4.0
0xc1ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0xc1d3  ldarg.0
0xc1d4  ldstr    aThis// "$this"
0xc1d9  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xc1de  ldarg.0
0xc1df  ldc.i4.1
0xc1e0  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0xc1e5  ldarg.0
0xc1e6  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xc1eb  ldarg.0
0xc1ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc1f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xc1f6  ldarg.0
0xc1f7  ldstr    aServicedisrupt_4// "ServiceDisruptionWarningPage"
0xc1fc  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc201  ldarg.0
0xc202  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc207  ldc.i4.0
0xc208  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0xc20d  ldarg.0
0xc20e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_tableLayoutPanel
0xc213  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0xc218  ldarg.0
0xc219  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_alertIcon
0xc21e  callvirt instance void [System]System.ComponentModel.ISupportInitialize::EndInit()
0xc223  ldarg.0
0xc224  ldc.i4.0
0xc225  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0xc22a  ret
```
