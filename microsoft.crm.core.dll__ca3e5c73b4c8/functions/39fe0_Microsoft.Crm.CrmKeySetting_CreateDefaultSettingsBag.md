# Microsoft.Crm.CrmKeySetting::CreateDefaultSettingsBag

- ea: `0x39fe0`
- end: `0x3a3e3`
- name: `Microsoft.Crm.CrmKeySetting::CreateDefaultSettingsBag`
- size: `1027`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39b30`

## callees

- `0x1b5d0`
- `0x39710`
- `0x39850`
- `0x39fe0`
- `0x44400`
- `0x44510`

## string_xrefs

- `0x3a069`: `CreatedOn`
- `0x3a047`: `IsConfigurationRow`

## pseudocode

```c

```

## disassembly

```asm
0x39fe0  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x39fe5  stloc.0
0x39fe6  ldloc.0
0x39fe7  ldstr    aId// "Id"
0x39fec  ldarg.0
0x39fed  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x39ff2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::GetKeySettingGuid(valuetype Microsoft.Crm.CrmKeyType keyType)
0x39ff7  box      [mscorlib]System.Guid
0x39ffc  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a001  ldloc.0
0x3a002  ldstr    aKeytype// "KeyType"
0x3a007  ldarg.0
0x3a008  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x3a00d  stloc.1
0x3a00e  ldloca.s 1
0x3a010  constrained. Microsoft.Crm.CrmKeyType
0x3a016  callvirt instance string [mscorlib]System.Object::ToString()
0x3a01b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a020  ldloc.0
0x3a021  ldstr    aArchivelength// "ArchiveLength"
0x3a026  ldc.i4.1
0x3a027  box      [mscorlib]System.Int32
0x3a02c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a031  ldloc.0
0x3a032  ldstr    aActivekeyid_1// "ActiveKeyId"
0x3a037  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3a03c  box      [mscorlib]System.Guid
0x3a041  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a046  ldloc.0
0x3a047  ldstr    aIsconfiguratio// "IsConfigurationRow"
0x3a04c  ldc.i4.1
0x3a04d  box      [mscorlib]System.Boolean
0x3a052  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a057  ldloc.0
0x3a058  ldstr    aEnabled// "Enabled"
0x3a05d  ldc.i4.1
0x3a05e  box      [mscorlib]System.Boolean
0x3a063  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a068  ldloc.0
0x3a069  ldstr    aCreatedon// "CreatedOn"
0x3a06e  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x3a073  box      [mscorlib]System.DateTime
0x3a078  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a07d  ldarg.0
0x3a07e  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x3a083  stloc.1
0x3a084  ldloc.1
0x3a085  ldc.i4.1
0x3a086  sub
0x3a087  switch   loc_3A0BD, loc_3A133, loc_3A184, loc_3A223, loc_3A2C8, loc_3A31C, loc_3A31C, loc_3A223, loc_3A1D5, loc_3A274, loc_3A36D
0x3a0b8  br       loc_3A3B8
0x3a0bd  ldarg.1
0x3a0be  ldc.i4.2
0x3a0bf  bne.un.s loc_3A0E5
0x3a0c1  ldloc.0
0x3a0c2  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a0c7  ldc.i4.1
0x3a0c8  box      [mscorlib]System.Int32
0x3a0cd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a0d2  ldloc.0
0x3a0d3  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a0d8  ldc.i4.2
0x3a0d9  box      [mscorlib]System.Int32
0x3a0de  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a0e3  br.s     loc_3A109
0x3a0e5  ldloc.0
0x3a0e6  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a0eb  ldc.i4.s 0x18
0x3a0ed  box      [mscorlib]System.Int32
0x3a0f2  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a0f7  ldloc.0
0x3a0f8  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a0fd  ldc.i4.s 0x18
0x3a0ff  box      [mscorlib]System.Int32
0x3a104  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a109  ldloc.0
0x3a10a  ldstr    aAlgorithm// "Algorithm"
0x3a10f  ldstr    aHmacsha256// "HMACSHA256"
0x3a114  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a119  ldloc.0
0x3a11a  ldstr    aKeylength// "KeyLength"
0x3a11f  ldc.i4   0x80
0x3a124  box      [mscorlib]System.Int32
0x3a129  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a12e  br       loc_3A3E1
0x3a133  ldloc.0
0x3a134  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a139  ldc.i4   0x2D0
0x3a13e  box      [mscorlib]System.Int32
0x3a143  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a148  ldloc.0
0x3a149  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a14e  ldc.i4.s 0x48
0x3a150  box      [mscorlib]System.Int32
0x3a155  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a15a  ldloc.0
0x3a15b  ldstr    aAlgorithm// "Algorithm"
0x3a160  ldstr    aHmacsha256// "HMACSHA256"
0x3a165  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a16a  ldloc.0
0x3a16b  ldstr    aKeylength// "KeyLength"
0x3a170  ldc.i4   0x80
0x3a175  box      [mscorlib]System.Int32
0x3a17a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a17f  br       loc_3A3E1
0x3a184  ldloc.0
0x3a185  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a18a  ldc.i4   0xFFFF
0x3a18f  box      [mscorlib]System.Int32
0x3a194  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a199  ldloc.0
0x3a19a  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a19f  ldc.i4   0xFFFF
0x3a1a4  box      [mscorlib]System.Int32
0x3a1a9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a1ae  ldloc.0
0x3a1af  ldstr    aAlgorithm// "Algorithm"
0x3a1b4  ldstr    aRijndael// "Rijndael"
0x3a1b9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a1be  ldloc.0
0x3a1bf  ldstr    aKeylength// "KeyLength"
0x3a1c4  ldc.i4.s 0x20
0x3a1c6  box      [mscorlib]System.Int32
0x3a1cb  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a1d0  br       loc_3A3E1
0x3a1d5  ldloc.0
0x3a1d6  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a1db  ldc.i4.s 0x18
0x3a1dd  box      [mscorlib]System.Int32
0x3a1e2  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a1e7  ldloc.0
0x3a1e8  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a1ed  ldc.i4.s 0x18
0x3a1ef  box      [mscorlib]System.Int32
0x3a1f4  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a1f9  ldloc.0
0x3a1fa  ldstr    aAlgorithm// "Algorithm"
0x3a1ff  ldstr    aHmacsha256// "HMACSHA256"
0x3a204  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a209  ldloc.0
0x3a20a  ldstr    aKeylength// "KeyLength"
0x3a20f  ldc.i4   0x80
0x3a214  box      [mscorlib]System.Int32
0x3a219  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a21e  br       loc_3A3E1
0x3a223  ldloc.0
0x3a224  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a229  ldc.i4   0x2D0
0x3a22e  box      [mscorlib]System.Int32
0x3a233  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a238  ldloc.0
0x3a239  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a23e  ldc.i4   0x2238
0x3a243  box      [mscorlib]System.Int32
0x3a248  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a24d  ldloc.0
0x3a24e  ldstr    aAlgorithm// "Algorithm"
0x3a253  ldstr    aRijndael// "Rijndael"
0x3a258  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a25d  ldloc.0
0x3a25e  ldstr    aKeylength// "KeyLength"
0x3a263  ldc.i4.s 0x20
0x3a265  box      [mscorlib]System.Int32
0x3a26a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a26f  br       loc_3A3E1
0x3a274  ldloc.0
0x3a275  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a27a  ldc.i4   0x2D0
0x3a27f  box      [mscorlib]System.Int32
0x3a284  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a289  ldloc.0
0x3a28a  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a28f  ldc.i4   0x2238
0x3a294  box      [mscorlib]System.Int32
0x3a299  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a29e  ldloc.0
0x3a29f  ldstr    aAlgorithm// "Algorithm"
0x3a2a4  ldstr    aHmacsha256// "HMACSHA256"
0x3a2a9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a2ae  ldloc.0
0x3a2af  ldstr    aKeylength// "KeyLength"
0x3a2b4  ldc.i4   0x80
0x3a2b9  box      [mscorlib]System.Int32
0x3a2be  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a2c3  br       loc_3A3E1
0x3a2c8  ldloc.0
0x3a2c9  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a2ce  ldc.i4   0x2D0
0x3a2d3  box      [mscorlib]System.Int32
0x3a2d8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a2dd  ldloc.0
0x3a2de  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a2e3  ldc.i4   0xFFFF
0x3a2e8  box      [mscorlib]System.Int32
0x3a2ed  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a2f2  ldloc.0
0x3a2f3  ldstr    aAlgorithm// "Algorithm"
0x3a2f8  ldstr    aHmacsha256// "HMACSHA256"
0x3a2fd  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a302  ldloc.0
0x3a303  ldstr    aKeylength// "KeyLength"
0x3a308  ldc.i4   0x80
0x3a30d  box      [mscorlib]System.Int32
0x3a312  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a317  br       loc_3A3E1
0x3a31c  ldloc.0
0x3a31d  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a322  ldc.i4   0x2D0
0x3a327  box      [mscorlib]System.Int32
0x3a32c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a331  ldloc.0
0x3a332  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a337  ldc.i4   0x2D0
0x3a33c  box      [mscorlib]System.Int32
0x3a341  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a346  ldloc.0
0x3a347  ldstr    aAlgorithm// "Algorithm"
0x3a34c  ldstr    aHmacsha256// "HMACSHA256"
0x3a351  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a356  ldloc.0
0x3a357  ldstr    aKeylength// "KeyLength"
0x3a35c  ldc.i4   0x80
0x3a361  box      [mscorlib]System.Int32
0x3a366  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a36b  br.s     loc_3A3E1
0x3a36d  ldloc.0
0x3a36e  ldstr    aKeygenerationi_0// "KeyGenerationInterval"
0x3a373  ldc.i4.s 0x30
0x3a375  box      [mscorlib]System.Int32
0x3a37a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a37f  ldloc.0
0x3a380  ldstr    aCryptotimetoli// "CryptoTimeToLive"
0x3a385  ldc.i4.s 0x18
0x3a387  box      [mscorlib]System.Int32
0x3a38c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a391  ldloc.0
0x3a392  ldstr    aAlgorithm// "Algorithm"
0x3a397  ldstr    aHmacsha256// "HMACSHA256"
0x3a39c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a3a1  ldloc.0
0x3a3a2  ldstr    aKeylength// "KeyLength"
0x3a3a7  ldc.i4   0x80
0x3a3ac  box      [mscorlib]System.Int32
0x3a3b1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x3a3b6  br.s     loc_3A3E1
0x3a3b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a3bd  ldstr    aUnknownKeyType// "Unknown key type.  No default settings "...
0x3a3c2  ldc.i4.1
0x3a3c3  newarr   [mscorlib]System.Object
0x3a3c8  dup
0x3a3c9  ldc.i4.0
0x3a3ca  ldarg.0
0x3a3cb  call     instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKeySetting::get_KeyType()
0x3a3d0  box      Microsoft.Crm.CrmKeyType
0x3a3d5  stelem.ref
0x3a3d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a3db  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x3a3e0  throw
0x3a3e1  ldloc.0
0x3a3e2  ret
```
