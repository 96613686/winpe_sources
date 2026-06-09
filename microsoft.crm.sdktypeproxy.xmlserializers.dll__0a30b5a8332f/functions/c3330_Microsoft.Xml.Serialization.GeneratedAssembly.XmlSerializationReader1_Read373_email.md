# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read373_email

- ea: `0xc3330`
- end: `0xc44d0`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read373_email`
- size: `4512`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xef4c0`
- `0x102350`
- `0x152d90`

## callees

- `0x79630`
- `0x79a60`
- `0x90c00`
- `0x91060`
- `0x91320`
- `0x91550`
- `0x91730`
- `0x95710`
- `0x95f10`
- `0x9aa80`
- `0xc3330`
- `0xc44d0`

## string_xrefs

- `0xc3601`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc360f`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc37a4`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc37b2`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc3add`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc3aeb`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc4335`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc4343`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc447b`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:bcc, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:cc, http://schemas.microsoft.com/crm/2007/WebServices:compressed, http://sch`
- `0xc4489`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:bcc, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:cc, http://schemas.microsoft.com/crm/2007/WebServices:compressed, http://sch`

## pseudocode

```c

```

## disassembly

```asm
0xc3330  ldarg.2
0xc3331  brtrue.s loc_C3336
0xc3333  ldnull
0xc3334  br.s     loc_C333C
0xc3336  ldarg.0
0xc3337  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xc333c  stloc.0
0xc333d  ldc.i4.0
0xc333e  stloc.1
0xc333f  ldarg.1
0xc3340  brfalse.s loc_C3349
0xc3342  ldarg.0
0xc3343  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xc3348  stloc.1
0xc3349  ldarg.2
0xc334a  brfalse.s loc_C3379
0xc334c  ldloc.0
0xc334d  ldnull
0xc334e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xc3353  brtrue.s loc_C3379
0xc3355  ldloc.0
0xc3356  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xc335b  ldarg.0
0xc335c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1721_email
0xc3361  bne.un.s loc_C3371
0xc3363  ldloc.0
0xc3364  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xc3369  ldarg.0
0xc336a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc336f  beq.s    loc_C3379
0xc3371  ldarg.0
0xc3372  ldloc.0
0xc3373  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xc3378  throw
0xc3379  ldloc.1
0xc337a  brfalse.s loc_C337E
0xc337c  ldnull
0xc337d  ret
0xc337e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::.ctor()
0xc3383  stloc.2
0xc3384  ldc.i4.s 0x2D
0xc3386  newarr   [mscorlib]System.Boolean
0xc338b  stloc.3
0xc338c  br.s     loc_C33A8
0xc338e  ldarg.0
0xc338f  ldarg.0
0xc3390  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3395  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xc339a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xc339f  brtrue.s loc_C33A8
0xc33a1  ldarg.0
0xc33a2  ldloc.2
0xc33a3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xc33a8  ldarg.0
0xc33a9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33ae  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xc33b3  brtrue.s loc_C338E
0xc33b5  ldarg.0
0xc33b6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33bb  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xc33c0  pop
0xc33c1  ldarg.0
0xc33c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33c7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xc33cc  brfalse.s loc_C33DB
0xc33ce  ldarg.0
0xc33cf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33d4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xc33d9  ldloc.2
0xc33da  ret
0xc33db  ldarg.0
0xc33dc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33e1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xc33e6  ldarg.0
0xc33e7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc33ec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xc33f1  pop
0xc33f2  ldc.i4.0
0xc33f3  stloc.s  4
0xc33f5  ldarg.0
0xc33f6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xc33fb  stloc.s  5
0xc33fd  br       loc_C44A9
0xc3402  ldarg.0
0xc3403  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3408  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc340d  ldc.i4.1
0xc340e  bne.un   loc_C4487
0xc3413  ldloc.3
0xc3414  ldc.i4.0
0xc3415  ldelem.i1
0xc3416  brtrue.s loc_C3455
0xc3418  ldarg.0
0xc3419  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc341e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc3423  ldarg.0
0xc3424  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xc3429  bne.un.s loc_C3455
0xc342b  ldarg.0
0xc342c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3431  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc3436  ldarg.0
0xc3437  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc343c  bne.un.s loc_C3455
0xc343e  ldloc.2
0xc343f  ldarg.0
0xc3440  ldc.i4.0
0xc3441  ldc.i4.1
0xc3442  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xc3447  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xc344c  ldloc.3
0xc344d  ldc.i4.0
0xc344e  ldc.i4.1
0xc344f  stelem.i1
0xc3450  br       loc_C4493
0xc3455  ldloc.3
0xc3456  ldc.i4.1
0xc3457  ldelem.i1
0xc3458  brtrue.s loc_C3497
0xc345a  ldarg.0
0xc345b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3460  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc3465  ldarg.0
0xc3466  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xc346b  bne.un.s loc_C3497
0xc346d  ldarg.0
0xc346e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3473  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc3478  ldarg.0
0xc3479  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc347e  bne.un.s loc_C3497
0xc3480  ldloc.2
0xc3481  ldarg.0
0xc3482  ldc.i4.0
0xc3483  ldc.i4.1
0xc3484  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xc3489  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xc348e  ldloc.3
0xc348f  ldc.i4.1
0xc3490  ldc.i4.1
0xc3491  stelem.i1
0xc3492  br       loc_C4493
0xc3497  ldloc.3
0xc3498  ldc.i4.2
0xc3499  ldelem.i1
0xc349a  brtrue.s loc_C34D9
0xc349c  ldarg.0
0xc349d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc34a2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc34a7  ldarg.0
0xc34a8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xc34ad  bne.un.s loc_C34D9
0xc34af  ldarg.0
0xc34b0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc34b5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc34ba  ldarg.0
0xc34bb  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc34c0  bne.un.s loc_C34D9
0xc34c2  ldloc.2
0xc34c3  ldarg.0
0xc34c4  ldc.i4.0
0xc34c5  ldc.i4.1
0xc34c6  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xc34cb  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xc34d0  ldloc.3
0xc34d1  ldc.i4.2
0xc34d2  ldc.i4.1
0xc34d3  stelem.i1
0xc34d4  br       loc_C4493
0xc34d9  ldloc.3
0xc34da  ldc.i4.3
0xc34db  ldelem.i1
0xc34dc  brtrue.s loc_C351B
0xc34de  ldarg.0
0xc34df  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc34e4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc34e9  ldarg.0
0xc34ea  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xc34ef  bne.un.s loc_C351B
0xc34f1  ldarg.0
0xc34f2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc34f7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc34fc  ldarg.0
0xc34fd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc3502  bne.un.s loc_C351B
0xc3504  ldloc.2
0xc3505  ldarg.0
0xc3506  ldc.i4.0
0xc3507  ldc.i4.1
0xc3508  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xc350d  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.email::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xc3512  ldloc.3
0xc3513  ldc.i4.3
0xc3514  ldc.i4.1
0xc3515  stelem.i1
0xc3516  br       loc_C4493
0xc351b  ldarg.0
0xc351c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3521  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc3526  ldarg.0
0xc3527  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2476_bcc
0xc352c  bne.un   loc_C3679
0xc3531  ldarg.0
0xc3532  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3537  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc353c  ldarg.0
0xc353d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc3542  bne.un   loc_C3679
0xc3547  ldarg.0
0xc3548  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xc354d  brtrue   loc_C4493
0xc3552  ldnull
0xc3553  stloc.s  6
0xc3555  ldc.i4.0
0xc3556  stloc.s  7
0xc3558  ldarg.0
0xc3559  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc355e  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xc3563  brfalse.s loc_C3575
0xc3565  ldarg.0
0xc3566  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc356b  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xc3570  br       loc_C3654
0xc3575  ldarg.0
0xc3576  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc357b  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xc3580  ldarg.0
0xc3581  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3586  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xc358b  pop
0xc358c  ldc.i4.0
0xc358d  stloc.s  8
0xc358f  ldarg.0
0xc3590  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xc3595  stloc.s  9
0xc3597  br       loc_C362F
0xc359c  ldarg.0
0xc359d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc35a2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc35a7  ldc.i4.1
0xc35a8  bne.un.s loc_C360D
0xc35aa  ldarg.0
0xc35ab  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc35b0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc35b5  ldarg.0
0xc35b6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id252_activityparty
0xc35bb  bne.un.s loc_C35FF
0xc35bd  ldarg.0
0xc35be  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc35c3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc35c8  ldarg.0
0xc35c9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc35ce  bne.un.s loc_C35FF
0xc35d0  ldarg.0
0xc35d1  ldloc.s  6
0xc35d3  ldloc.s  7
0xc35d5  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty
0xc35da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc35df  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0xc35e4  castclass class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[]
0xc35e9  stloc.s  6
0xc35eb  ldloc.s  6
0xc35ed  ldloc.s  7
0xc35ef  dup
0xc35f0  ldc.i4.1
0xc35f1  add
0xc35f2  stloc.s  7
0xc35f4  ldarg.0
0xc35f5  ldc.i4.0
0xc35f6  ldc.i4.1
0xc35f7  call     instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read159_activityparty(bool isNullable, bool checkType)
0xc35fc  stelem.ref
0xc35fd  br.s     loc_C3619
0xc35ff  ldarg.0
0xc3600  ldnull
0xc3601  ldstr    aHttpSchemasMic_48// "http://schemas.microsoft.com/crm/2007/W"...
0xc3606  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xc360b  br.s     loc_C3619
0xc360d  ldarg.0
0xc360e  ldnull
0xc360f  ldstr    aHttpSchemasMic_48// "http://schemas.microsoft.com/crm/2007/W"...
0xc3614  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xc3619  ldarg.0
0xc361a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc361f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xc3624  pop
0xc3625  ldarg.0
0xc3626  ldloca.s 8
0xc3628  ldloca.s 9
0xc362a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0xc362f  ldarg.0
0xc3630  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3635  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc363a  ldc.i4.s 0xF
0xc363c  beq.s    loc_C364E
0xc363e  ldarg.0
0xc363f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc3644  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc3649  brtrue   loc_C359C
0xc364e  ldarg.0
  ... truncated ...
```
