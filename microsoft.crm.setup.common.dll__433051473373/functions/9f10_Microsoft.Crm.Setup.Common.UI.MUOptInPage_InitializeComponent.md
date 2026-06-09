# Microsoft.Crm.Setup.Common.UI.MUOptInPage::InitializeComponent

- ea: `0x9f10`
- end: `0xa447`
- name: `Microsoft.Crm.Setup.Common.UI.MUOptInPage::InitializeComponent`
- size: `1335`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9d70`

## callees

- `0x10ac0`
- `0x10be0`
- `0x111c0`

## string_xrefs

- `0xa0f4`: `_linkLayoutPanel`
- `0xa104`: `_linkLayoutPanel`
- `0xa115`: `_linkMUFaq`
- `0xa125`: `_linkMUFaq`
- `0xa159`: `_linkPrivacyStatement`
- `0xa169`: `_linkPrivacyStatement`
- `0xa2a9`: `_useUpdatesIcon`
- `0xa2b9`: `_useUpdatesIcon`
- `0xa2d6`: `_useMicrosoftUpdate`
- `0xa2e6`: `_useMicrosoftUpdate`
- `0xa326`: `_dontUseUpdatesIcon`
- `0xa336`: `_dontUseUpdatesIcon`
- `0xa353`: `_dontUseMicrosoftUpdate`
- `0xa363`: `_dontUseMicrosoftUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x9f10  ldtoken  Microsoft.Crm.Setup.Common.MUOptInPage
0x9f15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9f1a  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(class [mscorlib]System.Type)
0x9f1f  ldarg.0
0x9f20  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x9f25  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0x9f2a  ldarg.0
0x9f2b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x9f30  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0x9f35  ldarg.0
0x9f36  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9f3b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionText
0x9f40  ldarg.0
0x9f41  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x9f46  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0x9f4b  ldarg.0
0x9f4c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x9f51  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0x9f56  ldarg.0
0x9f57  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x9f5c  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0x9f61  ldarg.0
0x9f62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x9f67  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0x9f6c  ldarg.0
0x9f6d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x9f72  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0x9f77  ldarg.0
0x9f78  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x9f7d  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0x9f82  ldarg.0
0x9f83  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x9f88  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0x9f8d  ldarg.0
0x9f8e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x9f93  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseUpdatesIcon
0x9f98  ldarg.0
0x9f99  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x9f9e  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseMicrosoftUpdate
0x9fa3  ldarg.0
0x9fa4  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0x9fa9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9fae  ldarg.0
0x9faf  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0x9fb4  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x9fb9  ldarg.0
0x9fba  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0x9fbf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9fc4  ldarg.0
0x9fc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0x9fca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9fcf  ldarg.0
0x9fd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0x9fd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9fda  ldarg.0
0x9fdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0x9fe0  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x9fe5  ldarg.0
0x9fe6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseUpdatesIcon
0x9feb  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x9ff0  ldarg.0
0x9ff1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9ff6  ldarg.0
0x9ff7  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0x9ffc  ldc.i4.1
0x9ffd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa002  ldarg.0
0xa003  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa008  ldc.i4.0
0xa009  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xa00e  ldarg.0
0xa00f  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa014  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa019  ldarg.0
0xa01a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0xa01f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa024  ldarg.0
0xa025  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa02a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa02f  ldarg.0
0xa030  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionText
0xa035  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa03a  dup
0xa03b  ldarg.0
0xa03c  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa041  ldstr    aDescriptionlay// "_descriptionLayoutPanel"
0xa046  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa04b  ldarg.0
0xa04c  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa051  ldstr    aDescriptionlay// "_descriptionLayoutPanel"
0xa056  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa05b  dup
0xa05c  ldarg.0
0xa05d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0xa062  ldstr    aSysicon// "_sysIcon"
0xa067  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa06c  ldarg.0
0xa06d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0xa072  ldstr    aSysicon// "_sysIcon"
0xa077  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa07c  ldarg.0
0xa07d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_sysIcon
0xa082  ldc.i4.0
0xa083  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0xa088  dup
0xa089  ldarg.0
0xa08a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionText
0xa08f  ldstr    aDescriptiontex// "_descriptionText"
0xa094  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa099  ldarg.0
0xa09a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionText
0xa09f  ldstr    aDescriptiontex// "_descriptionText"
0xa0a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa0a9  ldarg.0
0xa0aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa0af  ldc.i4.1
0xa0b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa0b5  ldarg.0
0xa0b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa0bb  ldc.i4.0
0xa0bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xa0c1  ldarg.0
0xa0c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa0c7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa0cc  ldarg.0
0xa0cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0xa0d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa0d7  ldarg.0
0xa0d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa0dd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa0e2  ldarg.0
0xa0e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0xa0e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa0ed  dup
0xa0ee  ldarg.0
0xa0ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa0f4  ldstr    aLinklayoutpane// "_linkLayoutPanel"
0xa0f9  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa0fe  ldarg.0
0xa0ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa104  ldstr    aLinklayoutpane// "_linkLayoutPanel"
0xa109  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa10e  dup
0xa10f  ldarg.0
0xa110  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0xa115  ldstr    aLinkmufaq// "_linkMUFaq"
0xa11a  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa11f  ldarg.0
0xa120  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0xa125  ldstr    aLinkmufaq// "_linkMUFaq"
0xa12a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa12f  ldarg.0
0xa130  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0xa135  ldc.i4.1
0xa136  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0xa13b  ldarg.0
0xa13c  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkMUFaq
0xa141  ldarg.0
0xa142  ldftn    instance void Microsoft.Crm.Setup.Common.UI.MUOptInPage::MUFaq_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0xa148  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0xa14d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0xa152  dup
0xa153  ldarg.0
0xa154  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0xa159  ldstr    aLinkprivacysta// "_linkPrivacyStatement"
0xa15e  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa163  ldarg.0
0xa164  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0xa169  ldstr    aLinkprivacysta// "_linkPrivacyStatement"
0xa16e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa173  ldarg.0
0xa174  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0xa179  ldc.i4.1
0xa17a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0xa17f  ldarg.0
0xa180  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkPrivacyStatement
0xa185  ldarg.0
0xa186  ldftn    instance void Microsoft.Crm.Setup.Common.UI.MUOptInPage::PrivacyStatement_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0xa18c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0xa191  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0xa196  ldarg.0
0xa197  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa19c  ldc.i4.1
0xa19d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa1a2  ldarg.0
0xa1a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa1a8  ldc.i4.0
0xa1a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xa1ae  dup
0xa1af  ldarg.0
0xa1b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa1b5  ldstr    aPagelayoutpane// "_pageLayoutPanel"
0xa1ba  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa1bf  ldarg.0
0xa1c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa1c5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa1ca  ldarg.0
0xa1cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_descriptionLayoutPanel
0xa1d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa1d5  ldarg.0
0xa1d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa1db  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa1e0  ldarg.0
0xa1e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa1e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa1eb  ldarg.0
0xa1ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa1f1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa1f6  ldarg.0
0xa1f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_linkLayoutPanel
0xa1fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa201  ldarg.0
0xa202  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_pageLayoutPanel
0xa207  ldstr    aPagelayoutpane// "_pageLayoutPanel"
0xa20c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa211  ldarg.0
0xa212  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa217  ldc.i4.1
0xa218  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa21d  ldarg.0
0xa21e  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa223  ldc.i4.0
0xa224  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xa229  ldarg.0
0xa22a  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa22f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa234  ldarg.0
0xa235  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0xa23a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa23f  ldarg.0
0xa240  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa245  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa24a  ldarg.0
0xa24b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa250  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa255  ldarg.0
0xa256  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa25b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa260  ldarg.0
0xa261  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseUpdatesIcon
0xa266  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa26b  ldarg.0
0xa26c  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa271  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xa276  ldarg.0
0xa277  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseMicrosoftUpdate
0xa27c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xa281  dup
0xa282  ldarg.0
0xa283  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa288  ldstr    aOptionlayoutpa// "_optionLayoutPanel"
0xa28d  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa292  ldarg.0
0xa293  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.MUOptInPage::_optionLayoutPanel
0xa298  ldstr    aOptionlayoutpa// "_optionLayoutPanel"
0xa29d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa2a2  dup
0xa2a3  ldarg.0
0xa2a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0xa2a9  ldstr    aUseupdatesicon// "_useUpdatesIcon"
0xa2ae  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa2b3  ldarg.0
0xa2b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0xa2b9  ldstr    aUseupdatesicon// "_useUpdatesIcon"
0xa2be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa2c3  ldarg.0
0xa2c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useUpdatesIcon
0xa2c9  ldc.i4.0
0xa2ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0xa2cf  dup
0xa2d0  ldarg.0
0xa2d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa2d6  ldstr    aUsemicrosoftup// "_useMicrosoftUpdate"
0xa2db  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa2e0  ldarg.0
0xa2e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa2e6  ldstr    aUsemicrosoftup// "_useMicrosoftUpdate"
0xa2eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa2f0  ldarg.0
0xa2f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa2f6  ldc.i4.1
0xa2f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0xa2fc  ldarg.0
0xa2fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa302  ldc.i4.1
0xa303  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0xa308  ldarg.0
0xa309  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Crm.Setup.Common.UI.MUOptInPage::_useMicrosoftUpdate
0xa30e  ldarg.0
0xa30f  ldftn    instance void Microsoft.Crm.Setup.Common.UI.MUOptInPage::radio_Click(object sender, class [mscorlib]System.EventArgs e)
0xa315  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa31a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0xa31f  dup
0xa320  ldarg.0
0xa321  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseUpdatesIcon
0xa326  ldstr    aDontuseupdates// "_dontUseUpdatesIcon"
0xa32b  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0xa330  ldarg.0
0xa331  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.MUOptInPage::_dontUseUpdatesIcon
0xa336  ldstr    aDontuseupdates// "_dontUseUpdatesIcon"
  ... truncated ...
```
