# Microsoft.Crm.Transformations.AddToCurrentDate::PerformParameterValidations

- ea: `0x7c0`
- end: `0x911`
- name: `Microsoft.Crm.Transformations.AddToCurrentDate::PerformParameterValidations`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d0`

## callees

- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  ldarg.1
0x7c1  ldc.i4.0
0x7c2  ldelem.ref
0x7c3  brfalse.s loc_7F0
0x7c5  ldarg.1
0x7c6  ldc.i4.0
0x7c7  ldelem.ref
0x7c8  isinst   [mscorlib]System.Int32
0x7cd  brtrue.s loc_7F0
0x7cf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d4  ldstr    aInvalidInputTr// "Invalid input transformation parameter "...
0x7d9  ldc.i4.1
0x7da  newarr   [mscorlib]System.Object
0x7df  dup
0x7e0  ldc.i4.0
0x7e1  ldarg.1
0x7e2  ldc.i4.0
0x7e3  ldelem.ref
0x7e4  stelem.ref
0x7e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7ea  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x7ef  throw
0x7f0  ldarg.1
0x7f1  ldc.i4.1
0x7f2  ldelem.ref
0x7f3  brfalse.s loc_820
0x7f5  ldarg.1
0x7f6  ldc.i4.1
0x7f7  ldelem.ref
0x7f8  isinst   [mscorlib]System.Int32
0x7fd  brtrue.s loc_820
0x7ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x804  ldstr    aInvalidInputTr_0// "Invalid input transformation parameter "...
0x809  ldc.i4.1
0x80a  newarr   [mscorlib]System.Object
0x80f  dup
0x810  ldc.i4.0
0x811  ldarg.1
0x812  ldc.i4.1
0x813  ldelem.ref
0x814  stelem.ref
0x815  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x81a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x81f  throw
0x820  ldarg.1
0x821  ldc.i4.2
0x822  ldelem.ref
0x823  brfalse.s loc_850
0x825  ldarg.1
0x826  ldc.i4.2
0x827  ldelem.ref
0x828  isinst   [mscorlib]System.Int32
0x82d  brtrue.s loc_850
0x82f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x834  ldstr    aInvalidInputTr_1// "Invalid input transformation parameter "...
0x839  ldc.i4.1
0x83a  newarr   [mscorlib]System.Object
0x83f  dup
0x840  ldc.i4.0
0x841  ldarg.1
0x842  ldc.i4.2
0x843  ldelem.ref
0x844  stelem.ref
0x845  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x84a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x84f  throw
0x850  ldarg.1
0x851  ldc.i4.3
0x852  ldelem.ref
0x853  brfalse.s loc_880
0x855  ldarg.1
0x856  ldc.i4.3
0x857  ldelem.ref
0x858  isinst   [mscorlib]System.Int32
0x85d  brtrue.s loc_880
0x85f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x864  ldstr    aInvalidInputTr_2// "Invalid input transformation parameter "...
0x869  ldc.i4.1
0x86a  newarr   [mscorlib]System.Object
0x86f  dup
0x870  ldc.i4.0
0x871  ldarg.1
0x872  ldc.i4.3
0x873  ldelem.ref
0x874  stelem.ref
0x875  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x87f  throw
0x880  ldarg.1
0x881  ldc.i4.4
0x882  ldelem.ref
0x883  brfalse.s loc_8B0
0x885  ldarg.1
0x886  ldc.i4.4
0x887  ldelem.ref
0x888  isinst   [mscorlib]System.Int32
0x88d  brtrue.s loc_8B0
0x88f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x894  ldstr    aInvalidInputTr_3// "Invalid input transformation parameter "...
0x899  ldc.i4.1
0x89a  newarr   [mscorlib]System.Object
0x89f  dup
0x8a0  ldc.i4.0
0x8a1  ldarg.1
0x8a2  ldc.i4.4
0x8a3  ldelem.ref
0x8a4  stelem.ref
0x8a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8aa  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x8af  throw
0x8b0  ldarg.1
0x8b1  ldc.i4.5
0x8b2  ldelem.ref
0x8b3  brfalse.s loc_8E0
0x8b5  ldarg.1
0x8b6  ldc.i4.5
0x8b7  ldelem.ref
0x8b8  isinst   [mscorlib]System.Int32
0x8bd  brtrue.s loc_8E0
0x8bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c4  ldstr    aInvalidInputTr_4// "Invalid input transformation parameter "...
0x8c9  ldc.i4.1
0x8ca  newarr   [mscorlib]System.Object
0x8cf  dup
0x8d0  ldc.i4.0
0x8d1  ldarg.1
0x8d2  ldc.i4.5
0x8d3  ldelem.ref
0x8d4  stelem.ref
0x8d5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8da  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x8df  throw
0x8e0  ldarg.1
0x8e1  ldc.i4.6
0x8e2  ldelem.ref
0x8e3  brfalse.s loc_910
0x8e5  ldarg.1
0x8e6  ldc.i4.6
0x8e7  ldelem.ref
0x8e8  isinst   [mscorlib]System.Int32
0x8ed  brtrue.s loc_910
0x8ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f4  ldstr    aInvalidInputTr_5// "Invalid input transformation parameter "...
0x8f9  ldc.i4.1
0x8fa  newarr   [mscorlib]System.Object
0x8ff  dup
0x900  ldc.i4.0
0x901  ldarg.1
0x902  ldc.i4.6
0x903  ldelem.ref
0x904  stelem.ref
0x905  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x90a  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.TransformationParameterException::.ctor(string)
0x90f  throw
0x910  ret
```
