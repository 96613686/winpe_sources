# Microsoft.Crm.Application.FormControlClassId::.cctor

- ea: `0x3b0`
- end: `0x9f8`
- name: `Microsoft.Crm.Application.FormControlClassId::.cctor`
- size: `1608`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldstr    a4273edbdAc1d40// "{4273EDBD-AC1D-40D3-9FB2-095C621B552D}"
0x3b5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3ba  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TextBoxControl
0x3bf  ldstr    a1e1fc551F7a843// "{1E1FC551-F7A8-43AF-AC34-A8DC35C7B6D4}"
0x3c4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3c9  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TickerControl
0x3ce  ldstr    a71716b6c711e47// "{71716B6C-711E-476C-8AB8-5D11542BFB47}"
0x3d3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3d8  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::UrlControl
0x3dd  ldstr    a8c10015aB33949// "{8C10015A-B339-4982-9474-A95FE05631A5}"
0x3e2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e7  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PhoneNumberControl
0x3ec  ldstr    aAda2203eB4cd49// "{ADA2203E-B4CD-49BE-9DDF-234642B43B52}"
0x3f1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3f6  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EmailAddressControl
0x3fb  ldstr    a67fac785Cd584f// "{67FAC785-CD58-4F9F-ABB3-4B7DDC6ED5ED}"
0x400  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x405  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RadioControl
0x40a  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x40f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x414  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LookupControl
0x419  ldstr    a5b7738079fb242// "{5B773807-9FB2-42DB-97C3-7A91EFF8ADFF}"
0x41e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x423  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::DateTimeControl
0x428  ldstr    aC6d124ca7eda4a// "{C6D124CA-7EDA-4A60-AEA9-7FB8D318B68F}"
0x42d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x432  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::IntegerControl
0x437  ldstr    a533b9e00756b43// "{533B9E00-756B-4312-95A0-DC888637AC78}"
0x43c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x441  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MoneyControl
0x446  ldstr    a0d2c745aE5a84c// "{0D2C745A-E5A8-4C8F-BA63-C6D3BB604660}"
0x44b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x450  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::FloatControl
0x455  ldstr    aC3efe0c30ec642// "{C3EFE0C3-0EC6-42BE-8349-CBD9079DFD8E}"
0x45a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x45f  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::DecimalControl
0x464  ldstr    aE0dece4b6fc84a// "{E0DECE4B-6FC8-4A8F-A065-082708572369}"
0x469  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x46e  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TextAreaControl
0x473  ldstr    a3ef3998822bb4f// "{3EF39988-22BB-4F0B-BBBE-64B5A3748AEE}"
0x478  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x47d  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistControl
0x482  ldstr    a4aa28ab79c134f// "{4AA28AB7-9C13-4F57-A73D-AD894D048B5F}"
0x487  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x48c  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MultiSelectPicklistControl
0x491  ldstr    a5546e6cd394c4b// "{5546E6CD-394C-4BEE-94A8-4425E17EF6C6}"
0x496  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x49b  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::HiddenInputControl
0x4a0  ldstr    aE7a8127886354d// "{E7A81278-8635-4D9E-8D4D-59480B391C5B}"
0x4a5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4aa  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::GridControl
0x4af  ldstr    a02d4264b47e24b// "{02D4264B-47E2-4B4C-AA95-F439F3F4D458}"
0x4b4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4b9  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ReferencePanelSubgridControl
0x4be  ldstr    aB0c6723a85034f// "{B0C6723A-8503-4FD7-BB28-C8A06AC933C2}"
0x4c3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4c8  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::CheckBoxControl
0x4cd  ldstr    aFd2a7985318744// "{FD2A7985-3187-444E-908D-6624B21F69C0}"
0x4d2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4d7  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::FrameControl
0x4dc  ldstr    a86b9e25e695e4f// "{86B9E25E-695E-4FEF-AC69-F05CFA96739C}"
0x4e1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4e6  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::SocialInsightControl
0x4eb  ldstr    a76b9e25e695e4f// "{76B9E25E-695E-4FEF-AC69-F05CFA96739C}"
0x4f0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4f5  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::OrgInsightsControl
0x4fa  ldstr    aAa987274Ce4e42// "{AA987274-CE4E-4271-A803-66164311A958}"
0x4ff  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x504  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::DurationControl
0x509  ldstr    aF301535044a24a// "{F3015350-44A2-4AA0-97B5-00166532B5E9}"
0x50e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x513  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RegardingControl
0x518  ldstr    aCbfb742c14e74a// "{CBFB742C-14E7-4A17-96BB-1A13F7F64AA2}"
0x51d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x522  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PartyListControl
0x527  ldstr    a06375649C14349// "{06375649-C143-495E-A496-C962E5B4488E}"
0x52c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x531  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::NotesControl
0x536  ldstr    a7c624a0bF59e49// "{7C624A0B-F59E-493D-9583-638D34759266}"
0x53b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x540  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TimeZonePicklistControl
0x545  ldstr    a671a9387Ca5a4d// "{671A9387-CA5A-4D1E-8AB7-06E39DDCF6B5}"
0x54a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x54f  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LanguagePicker
0x554  ldstr    aA62b6fa9169e40// "{A62B6FA9-169E-406C-B1AA-EAB828CB6026}"
0x559  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x55e  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::KBViewerControl
0x563  ldstr    a5d68b98806614d// "{5D68B988-0661-4DB2-BC3E-17598AD3BE6C}"
0x568  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x56d  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistStatusControl
0x572  ldstr    a6f3fb987393b4d// "{6F3FB987-393B-4D2D-859F-9D0F0349B6AD}"
0x577  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x57c  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EmailBodyControl
0x581  ldstr    a2305e33aBad340// "{2305E33A-BAD3-4022-9E15-1856CF218333}"
0x586  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x58b  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistLookupControl
0x590  ldstr    a5f98664259614d// "{5F986642-5961-4D9F-AB5E-643D71E231E9}"
0x595  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x59a  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RelationshipRolePicklist
0x59f  ldstr    a163b90a6Eb6449// "{163B90A6-EB64-49D2-9DF8-3C84A4F0A0F8}"
0x5a4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5a9  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RelatedInformationControl
0x5ae  ldstr    a4168a05cD85746// "{4168A05C-D857-46AF-8457-5BB47EB04EA1}"
0x5b3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5b8  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::CoverPagePicklistControl
0x5bd  ldstr    aB634828eC39044// "{B634828E-C390-444A-AFE6-E07315D9D970}"
0x5c2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5c7  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MailMergeLanguagePicker
0x5cc  ldstr    a3246f9061f7145// "{3246F906-1F71-45F7-B11F-D7BE0F9D04C9}"
0x5d1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5d6  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ConnectionControl
0x5db  ldstr    a821acf1a7e464a// "{821ACF1A-7E46-4A0C-965D-FE14A57D78C7}"
0x5e0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5e5  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ConnectionRoleObjectTypeListControl
0x5ea  ldstr    a62b0df79046447// "{62B0DF79-0464-470F-8AF7-4483CFEA0C7D}"
0x5ef  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5f4  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MapsControl
0x5f9  ldstr    a91dc0675C8b944// "{91DC0675-C8B9-4421-B1E0-261CEBF02BAC}"
0x5fe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x603  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MapLinkControl
0x608  ldstr    a9fdf5f9188b147// "{9FDF5F91-88B1-47F4-AD53-C11EFC01A01D}"
0x60d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x612  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::WebResourceHtmlControl
0x617  ldstr    a587cdf98C1d54b// "{587CDF98-C1D5-4BDE-8473-14A0BC7644A7}"
0x61c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x621  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::WebResourceImageControl
0x626  ldstr    a080677db86ec45// "{080677DB-86EC-4544-AC42-F927E74B491F}"
0x62b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x630  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::WebResourceSilverlightControl
0x635  ldstr    aA28f441b916c48// "{A28F441B-916C-4865-87FD-0C5D53BD59C9}"
0x63a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x63f  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ReportControl
0x644  ldstr    aF02ef97725644b// "{F02EF977-2564-4B9A-B2F0-DF083D8A019B}"
0x649  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x64e  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ArticleContentControl
0x653  ldstr    a06e9f7af1f5446// "{06E9F7AF-1F54-4681-8EEC-1E21A1CEB465}"
0x658  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x65d  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ProcessControl
0x662  ldstr    a6636847dB74d49// "{6636847D-B74D-4994-B55A-A6FAF97ECEA2}"
0x667  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x66c  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ActivitiesWallControl
0x671  ldstr    a69af7dca2e3b4e// "{69AF7DCA-2E3B-4EE7-9201-0DA731DD2413}"
0x676  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x67b  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::QuickFormControl
0x680  ldstr    a5c5600e01d6e42// "{5C5600E0-1D6E-4205-A272-BE80DA87FD42}"
0x685  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x68a  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::QuickFormCollectionControl
0x68f  ldstr    aB68b05f0A46d43// "{B68B05F0-A46D-43F8-843B-917920AF806A}"
0x694  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x699  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ReferencePanelQuickFormCollectionControl
0x69e  ldstr    aDfdf1cde837b4a// "{DFDF1CDE-837B-4AC9-98CF-AC74361FD89D}"
0x6a3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6a8  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LinkControl
0x6ad  ldstr    aDb1284ef9ffc4e// "{DB1284EF-9FFC-4E99-B382-0CC082FE2364}"
0x6b2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6b7  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::CompositionLinkControl
0x6bc  ldstr    aF4c16ecaCa814e// "{F4C16ECA-CA81-4E39-9448-834B8378721E}"
0x6c1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6c6  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ErrorStatusControl
0x6cb  ldstr    aC72511ab84e54f// "{C72511AB-84E5-4FB7-A543-25B4FC01E83E}"
0x6d0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6d5  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ActivitiesContainerControl
0x6da  ldstr    a3f4e2a56F1024b// "{3F4E2A56-F102-4B4D-AB9C-F1574CA5BFDA}"
0x6df  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6e4  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::AccessTeamEntityPickerControl
0x6e9  ldstr    aF93a31b299ac40// "{F93A31B2-99AC-4084-8EC2-D4027C31369A}"
0x6ee  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6f3  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::AccessPrivilegeControl
0x6f8  ldstr    a9c5ca0a1Ab4d47// "{9C5CA0A1-AB4D-4781-BE7E-8DFBE867B87E}"
0x6fd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x702  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TimerControl
0x707  ldstr    a6896f004B17a42// "{6896F004-B17A-4202-861E-8B7EA2080E0B}"
0x70c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x711  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::DynamicPropertyListControl
0x716  ldstr    a00ad73daBd4d49// "{00AD73DA-BD4D-49C6-88A8-2F4F4CAD4A20}"
0x71b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x720  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ButtonControl
0x725  ldstr    aE616a57f20e045// "{E616A57F-20E0-4534-8662-A101B5DDF4E0}"
0x72a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72f  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::SearchWidget
0x734  ldstr    a26e9760f745440// "{26E9760F-7454-40DE-BB07-F6DCCCB82040}"
0x739  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x73e  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EmailRecipientActivityControl
0x743  ldstr    a39354e4a50154d// "{39354E4A-5015-4D74-8031-EA9EB73A1322}"
0x748  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x74d  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LabelControl
0x752  ldstr    aF9a8a302114e46// "{F9A8A302-114E-466A-B582-6771B2AE0D92}"
0x757  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x75c  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::CustomControl
0x761  ldstr    a1479835fF85246// "{1479835F-F852-4679-B864-C6892A2844C9}"
0x766  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x76b  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EditFilterControl
0x770  ldstr    aF94db24f263d44// "{F94DB24F-263D-44A7-B38E-A35E9854812B}"
0x775  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x77a  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RichEditorControl
0x77f  ldstr    a8c54228c1b2549// "{8C54228C-1B25-4909-A12A-F2B968BB0D62}"
0x784  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x789  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PowerBIControl
0x78e  ldstr    aF454228d1d2543// "{F454228D-1D25-4319-E12F-D27968BC0234}"
0x793  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x798  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EmailEngagementActionsControl
0x79d  ldstr    aC8bfbbef685144// "{C8BFBBEF-6851-4401-A0CC-7450062FE085}"
0x7a2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7a7  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ACIControl
0x7ac  ldstr    aD2561f53B29242// "{D2561F53-B292-42D9-B222-478E40FFE29F}"
0x7b1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b6  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::DashboardControl
0x7bb  ldstr    a7ccd14941f7a4e// "{7CCD1494-1F7A-4E3A-8BDE-F32069DAEB9F}"
0x7c0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7c5  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ReferencePanelSearchWidget
0x7ca  ldstr    aFff0e6329d7b4f// "{FFF0E632-9D7B-4F21-BBC1-05D1567AD144}"
0x7cf  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7d4  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::GlobalFilterControl
0x7d9  ldstr    a9c310a73A36042// "{9C310A73-A360-42C5-8943-47A06F1B51EA}"
0x7de  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7e3  stsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::AppliedFiltersControl
0x7e8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::.ctor()
0x7ed  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x7f2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x7f7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LookupControl
0x7fc  ldc.i4.3
0x7fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x802  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x807  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistControl
0x80c  ldc.i4.4
0x80d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x812  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x817  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MultiSelectPicklistControl
0x81c  ldc.i4.s 0xC
0x81e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x823  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x828  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::HiddenInputControl
0x82d  ldc.i4.1
0x82e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x833  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x838  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::GridControl
0x83d  ldc.i4.5
0x83e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x843  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x848  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::ReferencePanelSubgridControl
0x84d  ldc.i4.5
0x84e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x853  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x858  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::FrameControl
0x85d  ldc.i4.2
0x85e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x863  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x868  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RegardingControl
0x86d  ldc.i4.3
0x86e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x873  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x878  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PartyListControl
0x87d  ldc.i4.3
0x87e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x883  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x888  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::LanguagePicker
0x88d  ldc.i4.4
0x88e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x893  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x898  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::KBViewerControl
0x89d  ldc.i4.2
0x89e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8a3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8a8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::NotesControl
0x8ad  ldc.i4.8
0x8ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8b3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8b8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::SearchWidget
0x8bd  ldc.i4.s 9
0x8bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8c4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8c9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::EmailRecipientActivityControl
0x8ce  ldc.i4.s 0xA
0x8d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8d5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8da  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistStatusControl
0x8df  ldc.i4.4
0x8e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8e5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8ea  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::PicklistLookupControl
0x8ef  ldc.i4.4
0x8f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x8f5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x8fa  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RelatedInformationControl
0x8ff  ldc.i4.m1
0x900  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x905  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x90a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::RelationshipRolePicklist
0x90f  ldc.i4.4
0x910  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x915  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x91a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::TimeZonePicklistControl
0x91f  ldc.i4.4
0x920  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x925  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x92a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::CoverPagePicklistControl
0x92f  ldc.i4.4
0x930  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType>::Add(var<u1>, !!T0)
0x935  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Application.SharedObjects.FormControlType> Microsoft.Crm.Application.FormControlClassId::_typeMap
0x93a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.FormControlClassId::MailMergeLanguagePicker
  ... truncated ...
```
