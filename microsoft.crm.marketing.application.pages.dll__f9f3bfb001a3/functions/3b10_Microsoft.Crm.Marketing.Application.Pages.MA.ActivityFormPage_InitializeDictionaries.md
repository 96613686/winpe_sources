# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::InitializeDictionaries

- ea: `0x3b10`
- end: `0x3d32`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::InitializeDictionaries`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3920`

## pseudocode

```c

```

## disassembly

```asm
0x3b10  ldarg.0
0x3b11  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x3b16  ldc.i4   0x1069
0x3b1b  ldstr    a32f14e189a3a45// "{32F14E18-9A3A-4544-8543-8EC73039739B}"
0x3b20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x3b25  ldarg.0
0x3b26  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x3b2b  ldc.i4   0x1072
0x3b30  ldstr    a70d386d583f645// "{70D386D5-83F6-4578-AA42-8340D07279B4}"
0x3b35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x3b3a  ldarg.0
0x3b3b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x3b40  ldc.i4   0x106F
0x3b45  ldstr    aA38a6589695e49// "{A38A6589-695E-490A-BF0A-57284FFCDD4A}"
0x3b4a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x3b4f  ldarg.0
0x3b50  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x3b55  ldc.i4   0x106C
0x3b5a  ldstr    aE5dc7302A39247// "{E5DC7302-A392-4785-B422-ADBD895A267B}"
0x3b5f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x3b64  ldarg.0
0x3b65  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x3b6a  ldc.i4   0x106A
0x3b6f  ldstr    a4fbc42acD18c41// "{4FBC42AC-D18C-4132-9FA7-89F8D0BB0E0C}"
0x3b74  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x3b79  ldarg.0
0x3b7a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3b7f  ldc.i4   0x1069
0x3b84  ldc.i4.6
0x3b85  newarr   [mscorlib]System.String
0x3b8a  dup
0x3b8b  ldc.i4.0
0x3b8c  ldstr    aOrganizer// "organizer"
0x3b91  stelem.ref
0x3b92  dup
0x3b93  ldc.i4.1
0x3b94  ldstr    aOwnerid// "ownerid"
0x3b99  stelem.ref
0x3b9a  dup
0x3b9b  ldc.i4.2
0x3b9c  ldstr    aRegardingobjec// "regardingobjectid"
0x3ba1  stelem.ref
0x3ba2  dup
0x3ba3  ldc.i4.3
0x3ba4  ldstr    aRequiredattend// "requiredattendees"
0x3ba9  stelem.ref
0x3baa  dup
0x3bab  ldc.i4.4
0x3bac  ldstr    aOptionalattend// "optionalattendees"
0x3bb1  stelem.ref
0x3bb2  dup
0x3bb3  ldc.i4.5
0x3bb4  ldstr    aHeaderTabOwner// "header_tab_ownerid"
0x3bb9  stelem.ref
0x3bba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3bbf  ldarg.0
0x3bc0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3bc5  ldc.i4   0x1072
0x3bca  ldc.i4.6
0x3bcb  newarr   [mscorlib]System.String
0x3bd0  dup
0x3bd1  ldc.i4.0
0x3bd2  ldstr    aFrom// "from"
0x3bd7  stelem.ref
0x3bd8  dup
0x3bd9  ldc.i4.1
0x3bda  ldstr    aOwnerid// "ownerid"
0x3bdf  stelem.ref
0x3be0  dup
0x3be1  ldc.i4.2
0x3be2  ldstr    aRegardingobjec// "regardingobjectid"
0x3be7  stelem.ref
0x3be8  dup
0x3be9  ldc.i4.3
0x3bea  ldstr    aTo// "to"
0x3bef  stelem.ref
0x3bf0  dup
0x3bf1  ldc.i4.4
0x3bf2  ldstr    aPhonenumber// "phonenumber"
0x3bf7  stelem.ref
0x3bf8  dup
0x3bf9  ldc.i4.5
0x3bfa  ldstr    aHeaderTabOwner// "header_tab_ownerid"
0x3bff  stelem.ref
0x3c00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3c05  ldarg.0
0x3c06  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3c0b  ldc.i4   0x106F
0x3c10  ldc.i4.6
0x3c11  newarr   [mscorlib]System.String
0x3c16  dup
0x3c17  ldc.i4.0
0x3c18  ldstr    aFrom// "from"
0x3c1d  stelem.ref
0x3c1e  dup
0x3c1f  ldc.i4.1
0x3c20  ldstr    aOwnerid// "ownerid"
0x3c25  stelem.ref
0x3c26  dup
0x3c27  ldc.i4.2
0x3c28  ldstr    aRegardingobjec// "regardingobjectid"
0x3c2d  stelem.ref
0x3c2e  dup
0x3c2f  ldc.i4.3
0x3c30  ldstr    aTo// "to"
0x3c35  stelem.ref
0x3c36  dup
0x3c37  ldc.i4.4
0x3c38  ldstr    aAddress// "address"
0x3c3d  stelem.ref
0x3c3e  dup
0x3c3f  ldc.i4.5
0x3c40  ldstr    aHeaderTabOwner// "header_tab_ownerid"
0x3c45  stelem.ref
0x3c46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3c4b  ldarg.0
0x3c4c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3c51  ldc.i4   0x106C
0x3c56  ldc.i4.6
0x3c57  newarr   [mscorlib]System.String
0x3c5c  dup
0x3c5d  ldc.i4.0
0x3c5e  ldstr    aFrom// "from"
0x3c63  stelem.ref
0x3c64  dup
0x3c65  ldc.i4.1
0x3c66  ldstr    aOwnerid// "ownerid"
0x3c6b  stelem.ref
0x3c6c  dup
0x3c6d  ldc.i4.2
0x3c6e  ldstr    aRegardingobjec// "regardingobjectid"
0x3c73  stelem.ref
0x3c74  dup
0x3c75  ldc.i4.3
0x3c76  ldstr    aTo// "to"
0x3c7b  stelem.ref
0x3c7c  dup
0x3c7d  ldc.i4.4
0x3c7e  ldstr    aFaxnumber// "faxnumber"
0x3c83  stelem.ref
0x3c84  dup
0x3c85  ldc.i4.5
0x3c86  ldstr    aHeaderTabOwner// "header_tab_ownerid"
0x3c8b  stelem.ref
0x3c8c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3c91  ldarg.0
0x3c92  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3c97  ldc.i4   0x106A
0x3c9c  ldc.i4.6
0x3c9d  newarr   [mscorlib]System.String
0x3ca2  dup
0x3ca3  ldc.i4.0
0x3ca4  ldstr    aOwnerid// "ownerid"
0x3ca9  stelem.ref
0x3caa  dup
0x3cab  ldc.i4.1
0x3cac  ldstr    aRegardingobjec// "regardingobjectid"
0x3cb1  stelem.ref
0x3cb2  dup
0x3cb3  ldc.i4.2
0x3cb4  ldstr    aTo// "to"
0x3cb9  stelem.ref
0x3cba  dup
0x3cbb  ldc.i4.3
0x3cbc  ldstr    aCc// "cc"
0x3cc1  stelem.ref
0x3cc2  dup
0x3cc3  ldc.i4.4
0x3cc4  ldstr    aBcc// "bcc"
0x3cc9  stelem.ref
0x3cca  dup
0x3ccb  ldc.i4.5
0x3ccc  ldstr    aHeaderTabOwner// "header_tab_ownerid"
0x3cd1  stelem.ref
0x3cd2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3cd7  ldarg.0
0x3cd8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultDisabledFields
0x3cdd  ldc.i4   0x1072
0x3ce2  ldc.i4.1
0x3ce3  newarr   [mscorlib]System.String
0x3ce8  dup
0x3ce9  ldc.i4.0
0x3cea  ldstr    aDirectioncode// "directioncode"
0x3cef  stelem.ref
0x3cf0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3cf5  ldarg.0
0x3cf6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultDisabledFields
0x3cfb  ldc.i4   0x106F
0x3d00  ldc.i4.1
0x3d01  newarr   [mscorlib]System.String
0x3d06  dup
0x3d07  ldc.i4.0
0x3d08  ldstr    aDirectioncode// "directioncode"
0x3d0d  stelem.ref
0x3d0e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3d13  ldarg.0
0x3d14  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultDisabledFields
0x3d19  ldc.i4   0x106C
0x3d1e  ldc.i4.1
0x3d1f  newarr   [mscorlib]System.String
0x3d24  dup
0x3d25  ldc.i4.0
0x3d26  ldstr    aDirectioncode// "directioncode"
0x3d2b  stelem.ref
0x3d2c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::Add(var<u1>, !!T0)
0x3d31  ret
```
