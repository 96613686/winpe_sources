# Microsoft.Xrm.CrmLicenseData::AddAppCommonLicenses

- ea: `0x70`
- end: `0x4211`
- name: `Microsoft.Xrm.CrmLicenseData::AddAppCommonLicenses`
- size: `16801`
- prototype: ``
- caller_count: `0`
- callee_count: `284`
- tags: `broker_com_uri`

## callees

- `0xc690`
- `0xcd60`
- `0xcd70`
- `0xcd80`
- `0xcd90`
- `0xcda0`
- `0xcdb0`
- `0xcdc0`
- `0xcdd0`
- `0xcde0`
- `0xcdf0`
- `0xce00`
- `0xce10`
- `0xce20`
- `0xce30`
- `0xce40`
- `0xce50`
- `0xce60`
- `0xce70`
- `0xce80`
- `0xce90`
- `0xcea0`
- `0xceb0`
- `0xcec0`
- `0xced0`
- `0xcee0`
- `0xcef0`
- `0xcf00`
- `0xcf10`
- `0xcf20`
- `0xcf30`
- `0xcf40`
- `0xcf50`
- `0xcf60`
- `0xcf70`
- `0xcf80`
- `0xcf90`
- `0xcfa0`
- `0xcfb0`
- `0xcfc0`
- `0xcfd0`
- `0xcfe0`
- `0xcff0`
- `0xd000`
- `0xd010`
- `0xd020`
- `0xd030`
- `0xd040`
- `0xd050`
- `0xd060`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldsfld   class Microsoft.Xrm.LicensesPrivileges Microsoft.Xrm.CrmLicenseData::licensesPrivileges
0x75  ldstr    a0999196858354f// "{09991968-5835-4fb6-B552-D9FF0632AB3D}"
0x7a  ldc.i4   0xA9
0x7f  newarr   Microsoft.Xrm.PrivilegeDefinition
0x84  dup
0x85  ldc.i4.0
0x86  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateAdvancedSimilarityRule()
0x8b  stelem.ref
0x8c  dup
0x8d  ldc.i4.1
0x8e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadAdvancedSimilarityRule()
0x93  stelem.ref
0x94  dup
0x95  ldc.i4.2
0x96  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteAdvancedSimilarityRule()
0x9b  stelem.ref
0x9c  dup
0x9d  ldc.i4.3
0x9e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteAdvancedSimilarityRule()
0xa3  stelem.ref
0xa4  dup
0xa5  ldc.i4.4
0xa6  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendAdvancedSimilarityRule()
0xab  stelem.ref
0xac  dup
0xad  ldc.i4.5
0xae  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToAdvancedSimilarityRule()
0xb3  stelem.ref
0xb4  dup
0xb5  ldc.i4.6
0xb6  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadCalendar()
0xbb  stelem.ref
0xbc  dup
0xbd  ldc.i4.7
0xbe  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteCalendar()
0xc3  stelem.ref
0xc4  dup
0xc5  ldc.i4.8
0xc6  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateChannelPropertyGroup()
0xcb  stelem.ref
0xcc  dup
0xcd  ldc.i4.s 9
0xcf  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadChannelPropertyGroup()
0xd4  stelem.ref
0xd5  dup
0xd6  ldc.i4.s 0xA
0xd8  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteChannelPropertyGroup()
0xdd  stelem.ref
0xde  dup
0xdf  ldc.i4.s 0xB
0xe1  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteChannelPropertyGroup()
0xe6  stelem.ref
0xe7  dup
0xe8  ldc.i4.s 0xC
0xea  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendChannelPropertyGroup()
0xef  stelem.ref
0xf0  dup
0xf1  ldc.i4.s 0xD
0xf3  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToChannelPropertyGroup()
0xf8  stelem.ref
0xf9  dup
0xfa  ldc.i4.s 0xE
0xfc  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateConnectionRole()
0x101  stelem.ref
0x102  dup
0x103  ldc.i4.s 0xF
0x105  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadConnectionRole()
0x10a  stelem.ref
0x10b  dup
0x10c  ldc.i4.s 0x10
0x10e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteConnectionRole()
0x113  stelem.ref
0x114  dup
0x115  ldc.i4.s 0x11
0x117  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteConnectionRole()
0x11c  stelem.ref
0x11d  dup
0x11e  ldc.i4.s 0x12
0x120  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendConnectionRole()
0x125  stelem.ref
0x126  dup
0x127  ldc.i4.s 0x13
0x129  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToConnectionRole()
0x12e  stelem.ref
0x12f  dup
0x130  ldc.i4.s 0x14
0x132  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateConvertRule()
0x137  stelem.ref
0x138  dup
0x139  ldc.i4.s 0x15
0x13b  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadConvertRule()
0x140  stelem.ref
0x141  dup
0x142  ldc.i4.s 0x16
0x144  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteConvertRule()
0x149  stelem.ref
0x14a  dup
0x14b  ldc.i4.s 0x17
0x14d  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendConvertRule()
0x152  stelem.ref
0x153  dup
0x154  ldc.i4.s 0x18
0x156  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToConvertRule()
0x15b  stelem.ref
0x15c  dup
0x15d  ldc.i4.s 0x19
0x15f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteConvertRule()
0x164  stelem.ref
0x165  dup
0x166  ldc.i4.s 0x1A
0x168  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareConvertRule()
0x16d  stelem.ref
0x16e  dup
0x16f  ldc.i4.s 0x1B
0x171  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignConvertRule()
0x176  stelem.ref
0x177  dup
0x178  ldc.i4.s 0x1C
0x17a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateEmailServerProfile()
0x17f  stelem.ref
0x180  dup
0x181  ldc.i4.s 0x1D
0x183  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadEmailServerProfile()
0x188  stelem.ref
0x189  dup
0x18a  ldc.i4.s 0x1E
0x18c  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteEmailServerProfile()
0x191  stelem.ref
0x192  dup
0x193  ldc.i4.s 0x1F
0x195  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteEmailServerProfile()
0x19a  stelem.ref
0x19b  dup
0x19c  ldc.i4.s 0x20
0x19e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendEmailServerProfile()
0x1a3  stelem.ref
0x1a4  dup
0x1a5  ldc.i4.s 0x21
0x1a7  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToEmailServerProfile()
0x1ac  stelem.ref
0x1ad  dup
0x1ae  ldc.i4.s 0x22
0x1b0  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareEmailServerProfile()
0x1b5  stelem.ref
0x1b6  dup
0x1b7  ldc.i4.s 0x23
0x1b9  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignEmailServerProfile()
0x1be  stelem.ref
0x1bf  dup
0x1c0  ldc.i4.s 0x24
0x1c2  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateEmailSignature()
0x1c7  stelem.ref
0x1c8  dup
0x1c9  ldc.i4.s 0x25
0x1cb  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadEmailSignature()
0x1d0  stelem.ref
0x1d1  dup
0x1d2  ldc.i4.s 0x26
0x1d4  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteEmailSignature()
0x1d9  stelem.ref
0x1da  dup
0x1db  ldc.i4.s 0x27
0x1dd  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteEmailSignature()
0x1e2  stelem.ref
0x1e3  dup
0x1e4  ldc.i4.s 0x28
0x1e6  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignEmailSignature()
0x1eb  stelem.ref
0x1ec  dup
0x1ed  ldc.i4.s 0x29
0x1ef  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateExchangeSyncIdMapping()
0x1f4  stelem.ref
0x1f5  dup
0x1f6  ldc.i4.s 0x2A
0x1f8  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadExchangeSyncIdMapping()
0x1fd  stelem.ref
0x1fe  dup
0x1ff  ldc.i4.s 0x2B
0x201  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteExchangeSyncIdMapping()
0x206  stelem.ref
0x207  dup
0x208  ldc.i4.s 0x2C
0x20a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteExchangeSyncIdMapping()
0x20f  stelem.ref
0x210  dup
0x211  ldc.i4.s 0x2D
0x213  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateExpiredProcess()
0x218  stelem.ref
0x219  dup
0x21a  ldc.i4.s 0x2E
0x21c  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadExpiredProcess()
0x221  stelem.ref
0x222  dup
0x223  ldc.i4.s 0x2F
0x225  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteExpiredProcess()
0x22a  stelem.ref
0x22b  dup
0x22c  ldc.i4.s 0x30
0x22e  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteExpiredProcess()
0x233  stelem.ref
0x234  dup
0x235  ldc.i4.s 0x31
0x237  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendExpiredProcess()
0x23c  stelem.ref
0x23d  dup
0x23e  ldc.i4.s 0x32
0x240  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToExpiredProcess()
0x245  stelem.ref
0x246  dup
0x247  ldc.i4.s 0x33
0x249  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateFeedback()
0x24e  stelem.ref
0x24f  dup
0x250  ldc.i4.s 0x34
0x252  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadFeedback()
0x257  stelem.ref
0x258  dup
0x259  ldc.i4.s 0x35
0x25b  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteFeedback()
0x260  stelem.ref
0x261  dup
0x262  ldc.i4.s 0x36
0x264  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteFeedback()
0x269  stelem.ref
0x26a  dup
0x26b  ldc.i4.s 0x37
0x26d  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ShareFeedback()
0x272  stelem.ref
0x273  dup
0x274  ldc.i4.s 0x38
0x276  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AssignFeedback()
0x27b  stelem.ref
0x27c  dup
0x27d  ldc.i4.s 0x39
0x27f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendFeedback()
0x284  stelem.ref
0x285  dup
0x286  ldc.i4.s 0x3A
0x288  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToFeedback()
0x28d  stelem.ref
0x28e  dup
0x28f  ldc.i4.s 0x3B
0x291  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateArticle()
0x296  stelem.ref
0x297  dup
0x298  ldc.i4.s 0x3C
0x29a  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadArticle()
0x29f  stelem.ref
0x2a0  dup
0x2a1  ldc.i4.s 0x3D
0x2a3  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteArticle()
0x2a8  stelem.ref
0x2a9  dup
0x2aa  ldc.i4.s 0x3E
0x2ac  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteArticle()
0x2b1  stelem.ref
0x2b2  dup
0x2b3  ldc.i4.s 0x3F
0x2b5  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_PublishArticle()
0x2ba  stelem.ref
0x2bb  dup
0x2bc  ldc.i4.s 0x40
0x2be  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToArticle()
0x2c3  stelem.ref
0x2c4  dup
0x2c5  ldc.i4.s 0x41
0x2c7  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendArticle()
0x2cc  stelem.ref
0x2cd  dup
0x2ce  ldc.i4.s 0x42
0x2d0  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateArticleTemplate()
0x2d5  stelem.ref
0x2d6  dup
0x2d7  ldc.i4.s 0x43
0x2d9  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadArticleTemplate()
0x2de  stelem.ref
0x2df  dup
0x2e0  ldc.i4.s 0x44
0x2e2  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteArticleTemplate()
0x2e7  stelem.ref
0x2e8  dup
0x2e9  ldc.i4.s 0x45
0x2eb  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_DeleteArticleTemplate()
0x2f0  stelem.ref
0x2f1  dup
0x2f2  ldc.i4.s 0x46
0x2f4  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_AppendToArticleTemplate()
0x2f9  stelem.ref
0x2fa  dup
0x2fb  ldc.i4.s 0x47
0x2fd  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_CreateKnowledgeBaseRecord()
0x302  stelem.ref
0x303  dup
0x304  ldc.i4.s 0x48
0x306  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_ReadKnowledgeBaseRecord()
0x30b  stelem.ref
0x30c  dup
0x30d  ldc.i4.s 0x49
0x30f  call     class Microsoft.Xrm.PrivilegeDefinition Microsoft.Xrm.Privileges::get_WriteKnowledgeBaseRecord()
0x314  stelem.ref
  ... truncated ...
```
