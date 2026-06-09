# Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::.cctor

- ea: `0x71870`
- end: `0x71c02`
- name: `Microsoft.Crm.Web.Tools.EmailRouterMigration.MainWizardPage::.cctor`
- size: `914`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x718cc`: `LOCID_INCOMPLETE_ROUTER_FILES`
- `0x718d4`: `MW_MSG_IncompleteRouter_Files`
- `0x718fe`: `LOCID_MW_INCOMING_SERVER_TYPE`
- `0x71906`: `MigrationWizard.Incoming_Server_Type`
- `0x71930`: `LOCID_MW_INCOMING_SERVER_LOC`
- `0x71938`: `MigrationWizard.Incoming_Server_Loc`
- `0x71b85`: `LOCID_MW_PROFILES_CREATE_MSG`
- `0x71b8d`: `MigrationWizard.ServerProfilesCreated.Description`
- `0x71b9f`: `LOCID_MW_FWMAILBOX_CREATE_MSG`
- `0x71ba7`: `MigrationWizard.ForwardMailboxesCreated.Description`
- `0x71bb9`: `LOCID_MW_USERQUEUE_UPDATE_MSG`
- `0x71bc1`: `MigrationWizard.UserQueueUpdated.Description`

## pseudocode

```c

```

## disassembly

```asm
0x71870  ldc.i4.s 0x23
0x71872  newarr   string[]
0x71877  dup
0x71878  ldc.i4.0
0x71879  ldc.i4.2
0x7187a  newarr   [mscorlib]System.String
0x7187f  dup
0x71880  ldc.i4.0
0x71881  ldstr    aLocidMigration// "LOCID_MIGRATION_INVALID_FILE"
0x71886  stelem.ref
0x71887  dup
0x71888  ldc.i4.1
0x71889  ldstr    aMwMsgInvalidFi// "MW_MSG_Invalid_File"
0x7188e  stelem.ref
0x7188f  stelem.ref
0x71890  dup
0x71891  ldc.i4.1
0x71892  ldc.i4.2
0x71893  newarr   [mscorlib]System.String
0x71898  dup
0x71899  ldc.i4.0
0x7189a  ldstr    aLocidMwFilepro// "LOCID_MW_FILEPROCESS_PROGRESS"
0x7189f  stelem.ref
0x718a0  dup
0x718a1  ldc.i4.1
0x718a2  ldstr    aMwMsgFileproce// "MW_MSG_FileProcess_Progress"
0x718a7  stelem.ref
0x718a8  stelem.ref
0x718a9  dup
0x718aa  ldc.i4.2
0x718ab  ldc.i4.2
0x718ac  newarr   [mscorlib]System.String
0x718b1  dup
0x718b2  ldc.i4.0
0x718b3  ldstr    aLocidMwEmailRo// "LOCID_MW_EMAIL_ROUTER_FILE_COUNT"
0x718b8  stelem.ref
0x718b9  dup
0x718ba  ldc.i4.1
0x718bb  ldstr    aMigrationwizar_2// "MigrationWizard.ProcessFilePage.EmailRo"...
0x718c0  stelem.ref
0x718c1  stelem.ref
0x718c2  dup
0x718c3  ldc.i4.3
0x718c4  ldc.i4.2
0x718c5  newarr   [mscorlib]System.String
0x718ca  dup
0x718cb  ldc.i4.0
0x718cc  ldstr    aLocidIncomplet// "LOCID_INCOMPLETE_ROUTER_FILES"
0x718d1  stelem.ref
0x718d2  dup
0x718d3  ldc.i4.1
0x718d4  ldstr    aMwMsgIncomplet// "MW_MSG_IncompleteRouter_Files"
0x718d9  stelem.ref
0x718da  stelem.ref
0x718db  dup
0x718dc  ldc.i4.4
0x718dd  ldc.i4.2
0x718de  newarr   [mscorlib]System.String
0x718e3  dup
0x718e4  ldc.i4.0
0x718e5  ldstr    aLocidMwEmailSe// "LOCID_MW_EMAIL_SERVER_MSG"
0x718ea  stelem.ref
0x718eb  dup
0x718ec  ldc.i4.1
0x718ed  ldstr    aMigrationwizar_3// "MigrationWizard.Email_Server_Msg"
0x718f2  stelem.ref
0x718f3  stelem.ref
0x718f4  dup
0x718f5  ldc.i4.5
0x718f6  ldc.i4.2
0x718f7  newarr   [mscorlib]System.String
0x718fc  dup
0x718fd  ldc.i4.0
0x718fe  ldstr    aLocidMwIncomin// "LOCID_MW_INCOMING_SERVER_TYPE"
0x71903  stelem.ref
0x71904  dup
0x71905  ldc.i4.1
0x71906  ldstr    aMigrationwizar_4// "MigrationWizard.Incoming_Server_Type"
0x7190b  stelem.ref
0x7190c  stelem.ref
0x7190d  dup
0x7190e  ldc.i4.6
0x7190f  ldc.i4.2
0x71910  newarr   [mscorlib]System.String
0x71915  dup
0x71916  ldc.i4.0
0x71917  ldstr    aLocidMwOutgoin// "LOCID_MW_OUTGOING_SERVER_TYPE"
0x7191c  stelem.ref
0x7191d  dup
0x7191e  ldc.i4.1
0x7191f  ldstr    aMigrationwizar_5// "MigrationWizard.Outgoing_Server_Type"
0x71924  stelem.ref
0x71925  stelem.ref
0x71926  dup
0x71927  ldc.i4.7
0x71928  ldc.i4.2
0x71929  newarr   [mscorlib]System.String
0x7192e  dup
0x7192f  ldc.i4.0
0x71930  ldstr    aLocidMwIncomin_0// "LOCID_MW_INCOMING_SERVER_LOC"
0x71935  stelem.ref
0x71936  dup
0x71937  ldc.i4.1
0x71938  ldstr    aMigrationwizar_6// "MigrationWizard.Incoming_Server_Loc"
0x7193d  stelem.ref
0x7193e  stelem.ref
0x7193f  dup
0x71940  ldc.i4.8
0x71941  ldc.i4.2
0x71942  newarr   [mscorlib]System.String
0x71947  dup
0x71948  ldc.i4.0
0x71949  ldstr    aLocidMwOutgoin_0// "LOCID_MW_OUTGOING_SERVER_LOC"
0x7194e  stelem.ref
0x7194f  dup
0x71950  ldc.i4.1
0x71951  ldstr    aMigrationwizar_7// "MigrationWizard.Outgoing_Server_Loc"
0x71956  stelem.ref
0x71957  stelem.ref
0x71958  dup
0x71959  ldc.i4.s 9
0x7195b  ldc.i4.2
0x7195c  newarr   [mscorlib]System.String
0x71961  dup
0x71962  ldc.i4.0
0x71963  ldstr    aLocidMwNewProf// "LOCID_MW_NEW_PROFILE_MSG"
0x71968  stelem.ref
0x71969  dup
0x7196a  ldc.i4.1
0x7196b  ldstr    aMigrationwizar_8// "MigrationWizard.New_Profile_Msg"
0x71970  stelem.ref
0x71971  stelem.ref
0x71972  dup
0x71973  ldc.i4.s 0xA
0x71975  ldc.i4.2
0x71976  newarr   [mscorlib]System.String
0x7197b  dup
0x7197c  ldc.i4.0
0x7197d  ldstr    aLocidMwServerP// "LOCID_MW_SERVER_PROFILE_NAME"
0x71982  stelem.ref
0x71983  dup
0x71984  ldc.i4.1
0x71985  ldstr    aMigrationwizar_9// "MigrationWizard.Server_Profile_Name"
0x7198a  stelem.ref
0x7198b  stelem.ref
0x7198c  dup
0x7198d  ldc.i4.s 0xB
0x7198f  ldc.i4.2
0x71990  newarr   [mscorlib]System.String
0x71995  dup
0x71996  ldc.i4.0
0x71997  ldstr    aLocidMwEmailSe_0// "LOCID_MW_EMAIL_SERVER_TYPE"
0x7199c  stelem.ref
0x7199d  dup
0x7199e  ldc.i4.1
0x7199f  ldstr    aMigrationwizar_10// "MigrationWizard.Email_Server_Type"
0x719a4  stelem.ref
0x719a5  stelem.ref
0x719a6  dup
0x719a7  ldc.i4.s 0xC
0x719a9  ldc.i4.2
0x719aa  newarr   [mscorlib]System.String
0x719af  dup
0x719b0  ldc.i4.0
0x719b1  ldstr    aLocidMwMigrate// "LOCID_MW_MIGRATE_PROFILES"
0x719b6  stelem.ref
0x719b7  dup
0x719b8  ldc.i4.1
0x719b9  ldstr    aMigrationwizar_11// "MigrationWizard.Migrate_Profiles_Title"
0x719be  stelem.ref
0x719bf  stelem.ref
0x719c0  dup
0x719c1  ldc.i4.s 0xD
0x719c3  ldc.i4.2
0x719c4  newarr   [mscorlib]System.String
0x719c9  dup
0x719ca  ldc.i4.0
0x719cb  ldstr    aLocidMwPop3Exc// "LOCID_MW_POP3_EXCHANGE_MSG"
0x719d0  stelem.ref
0x719d1  dup
0x719d2  ldc.i4.1
0x719d3  ldstr    aMigrationwizar_12// "MigrationWizard.Pop3_Exchange_Warning_M"...
0x719d8  stelem.ref
0x719d9  stelem.ref
0x719da  dup
0x719db  ldc.i4.s 0xE
0x719dd  ldc.i4.2
0x719de  newarr   [mscorlib]System.String
0x719e3  dup
0x719e4  ldc.i4.0
0x719e5  ldstr    aLocidMwExchang// "LOCID_MW_EXCHANGE_SMTP_MSG"
0x719ea  stelem.ref
0x719eb  dup
0x719ec  ldc.i4.1
0x719ed  ldstr    aMigrationwizar_13// "MigrationWizard.Exchange_Smtp_Warning_M"...
0x719f2  stelem.ref
0x719f3  stelem.ref
0x719f4  dup
0x719f5  ldc.i4.s 0xF
0x719f7  ldc.i4.2
0x719f8  newarr   [mscorlib]System.String
0x719fd  dup
0x719fe  ldc.i4.0
0x719ff  ldstr    aLocidMwExchang_0// "LOCID_MW_EXCHANGE_WEBDAV_MSG"
0x71a04  stelem.ref
0x71a05  dup
0x71a06  ldc.i4.1
0x71a07  ldstr    aMigrationwizar_14// "MigrationWizard.Exchange_WebDav_Warning"...
0x71a0c  stelem.ref
0x71a0d  stelem.ref
0x71a0e  dup
0x71a0f  ldc.i4.s 0x10
0x71a11  ldc.i4.2
0x71a12  newarr   [mscorlib]System.String
0x71a17  dup
0x71a18  ldc.i4.0
0x71a19  ldstr    aLocidMwCustomP// "LOCID_MW_CUSTOM_PROFILE_MSG"
0x71a1e  stelem.ref
0x71a1f  dup
0x71a20  ldc.i4.1
0x71a21  ldstr    aMigrationwizar_15// "MigrationWizard.Custom_Profile_Warning_"...
0x71a26  stelem.ref
0x71a27  stelem.ref
0x71a28  dup
0x71a29  ldc.i4.s 0x11
0x71a2b  ldc.i4.2
0x71a2c  newarr   [mscorlib]System.String
0x71a31  dup
0x71a32  ldc.i4.0
0x71a33  ldstr    aLocidMwNonSslP// "LOCID_MW_NON_SSL_PROFILE_MSG"
0x71a38  stelem.ref
0x71a39  dup
0x71a3a  ldc.i4.1
0x71a3b  ldstr    aMigrationwizar_16// "MigrationWizard.NonSSL_Profile_Warning_"...
0x71a40  stelem.ref
0x71a41  stelem.ref
0x71a42  dup
0x71a43  ldc.i4.s 0x12
0x71a45  ldc.i4.2
0x71a46  newarr   [mscorlib]System.String
0x71a4b  dup
0x71a4c  ldc.i4.0
0x71a4d  ldstr    aLocidMwYesMsg// "LOCID_MW_YES_MSG"
0x71a52  stelem.ref
0x71a53  dup
0x71a54  ldc.i4.1
0x71a55  ldstr    aMigrationwizar_17// "MigrationWizard.YES_MSG"
0x71a5a  stelem.ref
0x71a5b  stelem.ref
0x71a5c  dup
0x71a5d  ldc.i4.s 0x13
0x71a5f  ldc.i4.2
0x71a60  newarr   [mscorlib]System.String
0x71a65  dup
0x71a66  ldc.i4.0
0x71a67  ldstr    aLocidMwNoMsg// "LOCID_MW_NO_MSG"
0x71a6c  stelem.ref
0x71a6d  dup
0x71a6e  ldc.i4.1
0x71a6f  ldstr    aMigrationwizar_18// "MigrationWizard.NO_MSG"
0x71a74  stelem.ref
0x71a75  stelem.ref
0x71a76  dup
0x71a77  ldc.i4.s 0x14
0x71a79  ldc.i4.2
0x71a7a  newarr   [mscorlib]System.String
0x71a7f  dup
0x71a80  ldc.i4.0
0x71a81  ldstr    aLocidConfirmCa// "LOCID_CONFIRM_CANCEL_MIGRATION"
0x71a86  stelem.ref
0x71a87  dup
0x71a88  ldc.i4.1
0x71a89  ldstr    aMigrationwizar_19// "MigrationWizard.Confirm_Cancellation"
0x71a8e  stelem.ref
0x71a8f  stelem.ref
0x71a90  dup
0x71a91  ldc.i4.s 0x15
0x71a93  ldc.i4.2
0x71a94  newarr   [mscorlib]System.String
0x71a99  dup
0x71a9a  ldc.i4.0
0x71a9b  ldstr    aLocidReviewSum// "LOCID_REVIEW_SUMMARY_TITLE"
0x71aa0  stelem.ref
0x71aa1  dup
0x71aa2  ldc.i4.1
0x71aa3  ldstr    aMigrationwizar_20// "MigrationWizard.Summary.Title"
0x71aa8  stelem.ref
0x71aa9  stelem.ref
0x71aaa  dup
0x71aab  ldc.i4.s 0x16
0x71aad  ldc.i4.2
0x71aae  newarr   [mscorlib]System.String
0x71ab3  dup
0x71ab4  ldc.i4.0
0x71ab5  ldstr    aLocidServerPro// "LOCID_SERVER_PROFILE_COUNT"
0x71aba  stelem.ref
0x71abb  dup
0x71abc  ldc.i4.1
0x71abd  ldstr    aMigrationwizar_21// "MigrationWizard.EmailServerProfileCount"...
0x71ac2  stelem.ref
  ... truncated ...
```
