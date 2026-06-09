# Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOfWeekOptions

- ea: `0xaf0`
- end: `0xcc7`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::GetDayOfWeekOptions`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xaa0`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  ldc.i4.8
0xaf1  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption
0xaf6  dup
0xaf7  ldc.i4.0
0xaf8  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xafd  stelem.ref
0xafe  dup
0xaff  ldc.i4.0
0xb00  ldelem.ref
0xb01  ldstr    aMicrosoftCrmTr_37// "Microsoft.Crm.Transformations.AddToCurr"...
0xb06  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb0b  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xb10  dup
0xb11  ldc.i4.0
0xb12  ldelem.ref
0xb13  ldstr    aMicrosoftCrmTr_38// "Microsoft.Crm.Transformations.AddToCurr"...
0xb18  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb1d  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xb22  dup
0xb23  ldc.i4.0
0xb24  ldelem.ref
0xb25  ldc.i4.m1
0xb26  box      [mscorlib]System.Int32
0xb2b  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xb30  dup
0xb31  ldc.i4.1
0xb32  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xb37  stelem.ref
0xb38  dup
0xb39  ldc.i4.1
0xb3a  ldelem.ref
0xb3b  ldstr    aMicrosoftCrmTr_39// "Microsoft.Crm.Transformations.AddToCurr"...
0xb40  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb45  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xb4a  dup
0xb4b  ldc.i4.1
0xb4c  ldelem.ref
0xb4d  ldstr    aMicrosoftCrmTr_40// "Microsoft.Crm.Transformations.AddToCurr"...
0xb52  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb57  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xb5c  dup
0xb5d  ldc.i4.1
0xb5e  ldelem.ref
0xb5f  ldc.i4.0
0xb60  box      [mscorlib]System.Int32
0xb65  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xb6a  dup
0xb6b  ldc.i4.2
0xb6c  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xb71  stelem.ref
0xb72  dup
0xb73  ldc.i4.2
0xb74  ldelem.ref
0xb75  ldstr    aMicrosoftCrmTr_41// "Microsoft.Crm.Transformations.AddToCurr"...
0xb7a  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb7f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xb84  dup
0xb85  ldc.i4.2
0xb86  ldelem.ref
0xb87  ldstr    aMicrosoftCrmTr_42// "Microsoft.Crm.Transformations.AddToCurr"...
0xb8c  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xb91  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xb96  dup
0xb97  ldc.i4.2
0xb98  ldelem.ref
0xb99  ldc.i4.1
0xb9a  box      [mscorlib]System.Int32
0xb9f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xba4  dup
0xba5  ldc.i4.3
0xba6  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xbab  stelem.ref
0xbac  dup
0xbad  ldc.i4.3
0xbae  ldelem.ref
0xbaf  ldstr    aMicrosoftCrmTr_43// "Microsoft.Crm.Transformations.AddToCurr"...
0xbb4  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xbb9  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xbbe  dup
0xbbf  ldc.i4.3
0xbc0  ldelem.ref
0xbc1  ldstr    aMicrosoftCrmTr_44// "Microsoft.Crm.Transformations.AddToCurr"...
0xbc6  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xbcb  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xbd0  dup
0xbd1  ldc.i4.3
0xbd2  ldelem.ref
0xbd3  ldc.i4.2
0xbd4  box      [mscorlib]System.Int32
0xbd9  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xbde  dup
0xbdf  ldc.i4.4
0xbe0  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xbe5  stelem.ref
0xbe6  dup
0xbe7  ldc.i4.4
0xbe8  ldelem.ref
0xbe9  ldstr    aMicrosoftCrmTr_45// "Microsoft.Crm.Transformations.AddToCurr"...
0xbee  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xbf3  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xbf8  dup
0xbf9  ldc.i4.4
0xbfa  ldelem.ref
0xbfb  ldstr    aMicrosoftCrmTr_46// "Microsoft.Crm.Transformations.AddToCurr"...
0xc00  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xc05  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xc0a  dup
0xc0b  ldc.i4.4
0xc0c  ldelem.ref
0xc0d  ldc.i4.3
0xc0e  box      [mscorlib]System.Int32
0xc13  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xc18  dup
0xc19  ldc.i4.5
0xc1a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xc1f  stelem.ref
0xc20  dup
0xc21  ldc.i4.5
0xc22  ldelem.ref
0xc23  ldstr    aMicrosoftCrmTr_47// "Microsoft.Crm.Transformations.AddToCurr"...
0xc28  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xc2d  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xc32  dup
0xc33  ldc.i4.5
0xc34  ldelem.ref
0xc35  ldstr    aMicrosoftCrmTr_48// "Microsoft.Crm.Transformations.AddToCurr"...
0xc3a  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xc3f  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xc44  dup
0xc45  ldc.i4.5
0xc46  ldelem.ref
0xc47  ldc.i4.4
0xc48  box      [mscorlib]System.Int32
0xc4d  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xc52  dup
0xc53  ldc.i4.6
0xc54  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xc59  stelem.ref
0xc5a  dup
0xc5b  ldc.i4.6
0xc5c  ldelem.ref
0xc5d  ldstr    aMicrosoftCrmTr_49// "Microsoft.Crm.Transformations.AddToCurr"...
0xc62  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xc67  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xc6c  dup
0xc6d  ldc.i4.6
0xc6e  ldelem.ref
0xc6f  ldstr    aMicrosoftCrmTr_50// "Microsoft.Crm.Transformations.AddToCurr"...
0xc74  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xc79  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xc7e  dup
0xc7f  ldc.i4.6
0xc80  ldelem.ref
0xc81  ldc.i4.5
0xc82  box      [mscorlib]System.Int32
0xc87  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xc8c  dup
0xc8d  ldc.i4.7
0xc8e  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0xc93  stelem.ref
0xc94  dup
0xc95  ldc.i4.7
0xc96  ldelem.ref
0xc97  ldstr    aMicrosoftCrmTr_51// "Microsoft.Crm.Transformations.AddToCurr"...
0xc9c  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xca1  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0xca6  dup
0xca7  ldc.i4.7
0xca8  ldelem.ref
0xca9  ldstr    aMicrosoftCrmTr_52// "Microsoft.Crm.Transformations.AddToCurr"...
0xcae  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0xcb3  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0xcb8  dup
0xcb9  ldc.i4.7
0xcba  ldelem.ref
0xcbb  ldc.i4.6
0xcbc  box      [mscorlib]System.Int32
0xcc1  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0xcc6  ret
```
