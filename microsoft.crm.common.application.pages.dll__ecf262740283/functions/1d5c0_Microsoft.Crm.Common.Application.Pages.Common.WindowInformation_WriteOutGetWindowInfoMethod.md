# Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteOutGetWindowInfoMethod

- ea: `0x1d5c0`
- end: `0x1d690`
- name: `Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteOutGetWindowInfoMethod`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1d540`

## callees

- `0x1d5a0`
- `0x1d5c0`
- `0x1d690`
- `0x1d710`

## string_xrefs

- `0x1d5cc`: `function CRMWindowInfo(sUrl, iXOffset, iYOffset)\n{\n	this.Width	= parseInt(iXOffset, 10);\n	this.Height	= parseInt(iYOffset, 10);\n	this.Url	= Mscrm.CrmUri.create(sUrl);\n}`

## pseudocode

```c

```

## disassembly

```asm
0x1d5c0  ldc.i4   0x808
0x1d5c5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1d5ca  stloc.0
0x1d5cb  ldloc.0
0x1d5cc  ldstr    aFunctionCrmwin// "function CRMWindowInfo(sUrl, iXOffset, "...
0x1d5d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d5d6  pop
0x1d5d7  ldloc.0
0x1d5d8  ldstr    aTypeRegisterna_0// "Type.registerNamespace('Mscrm');"
0x1d5dd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1d5e2  pop
0x1d5e3  ldloc.0
0x1d5e4  ldstr    aTypeRegisterna_1// "Type.registerNamespace('Mscrm.Imported'"...
0x1d5e9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1d5ee  pop
0x1d5ef  ldloc.0
0x1d5f0  ldstr    aIfMscrmImporte// "if(!Mscrm.Imported.WindowInformationImp"...
0x1d5f5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1d5fa  pop
0x1d5fb  ldloc.0
0x1d5fc  ldstr    aMscrmImportedW// "Mscrm.Imported.WindowInformationImpleme"...
0x1d601  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1d606  pop
0x1d607  ldloc.0
0x1d608  ldstr    aSwitchParseint// "switch (parseInt(iObjectType, 10)) {"
0x1d60d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d612  pop
0x1d613  ldarg.0
0x1d614  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::get_CurrentWindowInformation()
0x1d619  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<int32, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WindowInformation::get_ObjectUrls()
0x1d61e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, string>::get_Keys()
0x1d623  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x1d628  stloc.1
0x1d629  br.s     loc_1D63A
0x1d62b  ldloc.1
0x1d62c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x1d631  stloc.2
0x1d632  ldarg.0
0x1d633  ldloc.0
0x1d634  ldloc.2
0x1d635  call     instance void Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteCaseForObject(class [mscorlib]System.Text.StringBuilder stringBuilder, int32 objectType)
0x1d63a  ldloc.1
0x1d63b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1d640  brtrue.s loc_1D62B
0x1d642  leave.s  loc_1D64E
0x1d644  ldloc.1
0x1d645  brfalse.s loc_1D64D
0x1d647  ldloc.1
0x1d648  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d64d  endfinally
0x1d64e  ldarg.0
0x1d64f  ldloc.0
0x1d650  call     instance void Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::WriteCaseForByPassObject(class [mscorlib]System.Text.StringBuilder stringBuilder)
0x1d655  ldloc.0
0x1d656  ldstr    aDefaultReturnN// "default: return new CRMWindowInfo(\"/us"...
0x1d65b  ldarg.0
0x1d65c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1d661  ldstr    aUserdefinedEdi_0// "userdefined/edit.aspx_WINDOW_WIDTH"
0x1d666  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1d66b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x1d670  pop
0x1d671  ldloc.0
0x1d672  ldstr    asc_23888// "}"
0x1d677  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d67c  pop
0x1d67d  ldloc.0
0x1d67e  ldstr    asc_23888// "}"
0x1d683  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1d688  pop
0x1d689  ldloc.0
0x1d68a  callvirt instance string [mscorlib]System.Object::ToString()
0x1d68f  ret
```
