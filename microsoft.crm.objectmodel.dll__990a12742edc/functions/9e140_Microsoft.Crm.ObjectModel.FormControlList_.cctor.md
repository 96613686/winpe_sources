# Microsoft.Crm.ObjectModel.FormControlList::.cctor

- ea: `0x9e140`
- end: `0x9f2ce`
- name: `Microsoft.Crm.ObjectModel.FormControlList::.cctor`
- size: `4494`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x9df20`
- `0x9e0c0`
- `0x9e0e0`
- `0x9e100`

## string_xrefs

- `0x9e4e7`: `ComboBox`
- `0x9e520`: `ComboBox`
- `0x9e6e8`: `ComboBox`
- `0x9e721`: `ComboBox`
- `0x9e680`: `PartyListRead`
- `0x9e685`: `PartyListRead`
- `0x9ed90`: `PartyListRead`
- `0x9ed95`: `PartyListRead`

## pseudocode

```c

```

## disassembly

```asm
0x9e140  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::.ctor()
0x9e145  dup
0x9e146  ldstr    a06375649C14349_0// "{06375649-c143-495e-a496-c962e5b4488e}"
0x9e14b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e150  stloc.0
0x9e151  ldloca.s 0
0x9e153  constrained. [mscorlib]System.Guid
0x9e159  callvirt instance string [mscorlib]System.Object::ToString()
0x9e15e  ldc.i4.s 0x13
0x9e160  ldstr    aLabel// "label"
0x9e165  ldstr    aLabel_0// "Label"
0x9e16a  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e16f  ldstr    aLabel_0// "Label"
0x9e174  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e179  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e17e  dup
0x9e17f  ldstr    a537de92a7ee648// "{537DE92A-7EE6-4843-B6E2-1EB0326F55C7}"
0x9e184  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e189  stloc.0
0x9e18a  ldloca.s 0
0x9e18c  constrained. [mscorlib]System.Guid
0x9e192  callvirt instance string [mscorlib]System.Object::ToString()
0x9e197  ldc.i4.s 0x19
0x9e199  ldstr    aLabel// "label"
0x9e19e  ldstr    aLabel_0// "Label"
0x9e1a3  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e1a8  ldstr    aLabel_0// "Label"
0x9e1ad  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e1b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e1b7  dup
0x9e1b8  ldstr    a5c5600e01d6e42// "{5C5600E0-1D6E-4205-A272-BE80DA87FD42}"
0x9e1bd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e1c2  stloc.0
0x9e1c3  ldloca.s 0
0x9e1c5  constrained. [mscorlib]System.Guid
0x9e1cb  callvirt instance string [mscorlib]System.Object::ToString()
0x9e1d0  ldc.i4.s 0x14
0x9e1d2  ldstr    aLabel// "label"
0x9e1d7  ldstr    aLabel_0// "Label"
0x9e1dc  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e1e1  ldstr    aLabel_0// "Label"
0x9e1e6  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e1eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e1f0  dup
0x9e1f1  ldstr    aE7a8127886354d_0// "{E7A81278-8635-4d9e-8D4D-59480B391C5B}"
0x9e1f6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e1fb  stloc.0
0x9e1fc  ldloca.s 0
0x9e1fe  constrained. [mscorlib]System.Guid
0x9e204  callvirt instance string [mscorlib]System.Object::ToString()
0x9e209  ldc.i4.s 0x12
0x9e20b  ldstr    aLabel// "label"
0x9e210  ldstr    aLabel_0// "Label"
0x9e215  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e21a  ldstr    aLabel_0// "Label"
0x9e21f  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e224  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e229  dup
0x9e22a  ldstr    a00000000000000// "{00000000-0000-0000-0000-000000000000}"
0x9e22f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e234  stloc.0
0x9e235  ldloca.s 0
0x9e237  constrained. [mscorlib]System.Guid
0x9e23d  callvirt instance string [mscorlib]System.Object::ToString()
0x9e242  ldc.i4.0
0x9e243  ldstr    aLabel// "label"
0x9e248  ldstr    aLabel_0// "Label"
0x9e24d  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e252  ldstr    aLabel_0// "Label"
0x9e257  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e25c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e261  dup
0x9e262  ldstr    aAa987274Ce4e42// "{AA987274-CE4E-4271-A803-66164311A958}"
0x9e267  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e26c  stloc.0
0x9e26d  ldloca.s 0
0x9e26f  constrained. [mscorlib]System.Guid
0x9e275  callvirt instance string [mscorlib]System.Object::ToString()
0x9e27a  ldc.i4.2
0x9e27b  ldstr    aDurationscroll// "DurationScroller"
0x9e280  ldstr    aDurationscroll// "DurationScroller"
0x9e285  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e28a  ldstr    aLabel_0// "Label"
0x9e28f  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e294  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e299  dup
0x9e29a  ldstr    a270bd3dbD9af47// "{270BD3DB-D9AF-4782-9025-509E298DEC0A}"
0x9e29f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e2a4  stloc.0
0x9e2a5  ldloca.s 0
0x9e2a7  constrained. [mscorlib]System.Guid
0x9e2ad  callvirt instance string [mscorlib]System.Object::ToString()
0x9e2b2  ldc.i4.1
0x9e2b3  ldstr    aLookup// "Lookup"
0x9e2b8  ldstr    aLookupviewmode// "LookupViewModel"
0x9e2bd  ldstr    aFieldbutton// "FieldButton"
0x9e2c2  ldstr    aNavigationbutt// "NavigationButton"
0x9e2c7  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e2cc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e2d1  dup
0x9e2d2  ldstr    a18673f53962140// "{18673F53-9621-408B-BAFD-BAC975849E96}"
0x9e2d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e2dc  stloc.0
0x9e2dd  ldloca.s 0
0x9e2df  constrained. [mscorlib]System.Guid
0x9e2e5  callvirt instance string [mscorlib]System.Object::ToString()
0x9e2ea  ldc.i4.s 0x3B
0x9e2ec  ldstr    aInteractioncen_6// "InteractionCentricLookup"
0x9e2f1  ldstr    aInteractioncen_5// "InteractionCentricLookupViewModel"
0x9e2f6  ldstr    aFieldbutton// "FieldButton"
0x9e2fb  ldstr    aNavigationbutt// "NavigationButton"
0x9e300  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e305  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e30a  dup
0x9e30b  ldstr    aC6d124ca7eda4a_0// "{C6D124CA-7EDA-4a60-AEA9-7FB8D318B68F}"
0x9e310  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e315  stloc.0
0x9e316  ldloca.s 0
0x9e318  constrained. [mscorlib]System.Guid
0x9e31e  callvirt instance string [mscorlib]System.Object::ToString()
0x9e323  ldc.i4.3
0x9e324  ldstr    aInteger_0// "Integer"
0x9e329  ldstr    aInteger_0// "Integer"
0x9e32e  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e333  ldstr    aLabel_0// "Label"
0x9e338  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e33d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e342  dup
0x9e343  ldstr    a0d2c745aE5a84c_0// "{0D2C745A-E5A8-4c8f-BA63-C6D3BB604660}"
0x9e348  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e34d  stloc.0
0x9e34e  ldloca.s 0
0x9e350  constrained. [mscorlib]System.Guid
0x9e356  callvirt instance string [mscorlib]System.Object::ToString()
0x9e35b  ldc.i4.5
0x9e35c  ldstr    aReal// "Real"
0x9e361  ldstr    aReal// "Real"
0x9e366  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e36b  ldstr    aLabel_0// "Label"
0x9e370  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e375  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e37a  dup
0x9e37b  ldstr    aC3efe0c30ec642_0// "{C3EFE0C3-0EC6-42be-8349-CBD9079DFD8E}"
0x9e380  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e385  stloc.0
0x9e386  ldloca.s 0
0x9e388  constrained. [mscorlib]System.Guid
0x9e38e  callvirt instance string [mscorlib]System.Object::ToString()
0x9e393  ldc.i4.6
0x9e394  ldstr    aDecimal// "Decimal"
0x9e399  ldstr    aDecimal// "Decimal"
0x9e39e  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e3a3  ldstr    aLabel_0// "Label"
0x9e3a8  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e3ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e3b2  dup
0x9e3b3  ldstr    a533b9e00756b43// "{533B9E00-756B-4312-95A0-DC888637AC78}"
0x9e3b8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e3bd  stloc.0
0x9e3be  ldloca.s 0
0x9e3c0  constrained. [mscorlib]System.Guid
0x9e3c6  callvirt instance string [mscorlib]System.Object::ToString()
0x9e3cb  ldc.i4.4
0x9e3cc  ldstr    aMoney_0// "Money"
0x9e3d1  ldstr    aMoney_0// "Money"
0x9e3d6  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e3db  ldstr    aLabel_0// "Label"
0x9e3e0  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e3e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e3ea  dup
0x9e3eb  ldstr    aAda2203eB4cd49_0// "{ADA2203E-B4CD-49be-9DDF-234642B43B52}"
0x9e3f0  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e3f5  stloc.0
0x9e3f6  ldloca.s 0
0x9e3f8  constrained. [mscorlib]System.Guid
0x9e3fe  callvirt instance string [mscorlib]System.Object::ToString()
0x9e403  ldc.i4.7
0x9e404  ldstr    aString// "String"
0x9e409  ldstr    aString// "String"
0x9e40e  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e413  ldstr    aLabel_0// "Label"
0x9e418  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e41d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e422  dup
0x9e423  ldstr    a4273edbdAc1d40_0// "{4273EDBD-AC1D-40d3-9FB2-095C621B552D}"
0x9e428  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e42d  stloc.0
0x9e42e  ldloca.s 0
0x9e430  constrained. [mscorlib]System.Guid
0x9e436  callvirt instance string [mscorlib]System.Object::ToString()
0x9e43b  ldc.i4.8
0x9e43c  ldstr    aString// "String"
0x9e441  ldstr    aString// "String"
0x9e446  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e44b  ldstr    aLabel_0// "Label"
0x9e450  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e455  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e45a  dup
0x9e45b  ldstr    aE0dece4b6fc84a_0// "{E0DECE4B-6FC8-4a8f-A065-082708572369}"
0x9e460  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e465  stloc.0
0x9e466  ldloca.s 0
0x9e468  constrained. [mscorlib]System.Guid
0x9e46e  callvirt instance string [mscorlib]System.Object::ToString()
0x9e473  ldc.i4.s 9
0x9e475  ldstr    aMultilinestrin// "MultilineString"
0x9e47a  ldstr    aString// "String"
0x9e47f  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e484  ldstr    aLabel_0// "Label"
0x9e489  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e48e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e493  dup
0x9e494  ldstr    a71716b6c711e47_0// "{71716B6C-711E-476c-8AB8-5D11542BFB47}"
0x9e499  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e49e  stloc.0
0x9e49f  ldloca.s 0
0x9e4a1  constrained. [mscorlib]System.Guid
0x9e4a7  callvirt instance string [mscorlib]System.Object::ToString()
0x9e4ac  ldc.i4.s 0xA
0x9e4ae  ldstr    aString// "String"
0x9e4b3  ldstr    aString// "String"
0x9e4b8  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e4bd  ldstr    aLabel_0// "Label"
0x9e4c2  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e4c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e4cc  dup
0x9e4cd  ldstr    a3ef3998822bb4f_0// "{3EF39988-22BB-4f0b-BBBE-64B5A3748AEE}"
0x9e4d2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e4d7  stloc.0
0x9e4d8  ldloca.s 0
0x9e4da  constrained. [mscorlib]System.Guid
0x9e4e0  callvirt instance string [mscorlib]System.Object::ToString()
0x9e4e5  ldc.i4.s 0xB
0x9e4e7  ldstr    aCombobox// "ComboBox"
0x9e4ec  ldstr    aOptionsetviewm// "OptionSetViewModel"
0x9e4f1  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e4f6  ldstr    aLabel_0// "Label"
0x9e4fb  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e500  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e505  dup
0x9e506  ldstr    a5d68b98806614d_0// "{5D68B988-0661-4db2-BC3E-17598AD3BE6C}"
0x9e50b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e510  stloc.0
0x9e511  ldloca.s 0
0x9e513  constrained. [mscorlib]System.Guid
0x9e519  callvirt instance string [mscorlib]System.Object::ToString()
0x9e51e  ldc.i4.s 0xC
0x9e520  ldstr    aCombobox// "ComboBox"
0x9e525  ldstr    aStatusoptionse// "StatusOptionSetViewModel"
0x9e52a  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e52f  ldstr    aLabel_0// "Label"
0x9e534  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e539  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e53e  dup
0x9e53f  ldstr    a5b7738079fb242_0// "{5B773807-9FB2-42db-97C3-7A91EFF8ADFF}"
0x9e544  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e549  stloc.0
0x9e54a  ldloca.s 0
0x9e54c  constrained. [mscorlib]System.Guid
0x9e552  callvirt instance string [mscorlib]System.Object::ToString()
0x9e557  ldc.i4.s 0x11
0x9e559  ldstr    aDatetimescroll// "DateTimeScroller"
0x9e55e  ldstr    aDatetimescroll// "DateTimeScroller"
0x9e563  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e568  ldstr    aLabel_0// "Label"
0x9e56d  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e572  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e577  dup
0x9e578  ldstr    a67fac785Cd584f_0// "{67FAC785-CD58-4f9f-ABB3-4B7DDC6ED5ED}"
0x9e57d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e582  stloc.0
0x9e583  ldloca.s 0
0x9e585  constrained. [mscorlib]System.Guid
0x9e58b  callvirt instance string [mscorlib]System.Object::ToString()
0x9e590  ldc.i4.s 0xD
0x9e592  ldstr    aTogglecontrol// "ToggleControl"
0x9e597  ldstr    aToggleviewmode// "ToggleViewModel"
0x9e59c  ldstr    aDefaultvaluela// "DefaultValueLabel"
0x9e5a1  ldstr    aLabel_0// "Label"
0x9e5a6  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e5ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e5b0  dup
0x9e5b1  ldstr    aF301535044a24a_0// "{F3015350-44A2-4aa0-97B5-00166532B5E9}"
0x9e5b6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e5bb  stloc.0
0x9e5bc  ldloca.s 0
0x9e5be  constrained. [mscorlib]System.Guid
0x9e5c4  callvirt instance string [mscorlib]System.Object::ToString()
0x9e5c9  ldc.i4.s 0xE
0x9e5cb  ldstr    aMultiplesource// "MultipleSourceLookup"
0x9e5d0  ldstr    aMultiplesource// "MultipleSourceLookup"
0x9e5d5  ldstr    aFieldbutton// "FieldButton"
0x9e5da  ldstr    aNavigationbutt// "NavigationButton"
0x9e5df  newobj   instance void Microsoft.Crm.ObjectModel.FormControl::.ctor(string id, valuetype Microsoft.Crm.ObjectModel.ControlType type, [opt] string editName, [opt] string editViewModelName, [opt] string readOnlyName, [opt] string readOnlyViewModelName)
0x9e5e4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.FormControl>::Add(var<u1>)
0x9e5e9  dup
0x9e5ea  ldstr    a6f3fb987393b4d// "{6F3FB987-393B-4d2d-859F-9D0F0349B6AD}"
0x9e5ef  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9e5f4  stloc.0
0x9e5f5  ldloca.s 0
  ... truncated ...
```
