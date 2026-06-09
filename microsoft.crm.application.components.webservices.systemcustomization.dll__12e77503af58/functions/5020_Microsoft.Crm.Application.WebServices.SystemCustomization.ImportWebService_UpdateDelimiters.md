# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateDelimiters

- ea: `0x5020`
- end: `0x52ff`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateDelimiters`
- size: `735`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x5020`
- `0xbfb0`
- `0xbfc0`
- `0xbfd0`
- `0xbfe0`
- `0xbff0`

## pseudocode

```c

```

## disassembly

```asm
0x5020  ldarg.1
0x5021  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5026  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x502b  stloc.0
0x502c  ldstr    aImportfile// "importfile"
0x5031  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5036  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x503b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x5040  ldloc.0
0x5041  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x5046  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::RetrieveImportFiles(valuetype [mscorlib]System.Guid)
0x504b  ldc.i4.1
0x504c  stloc.1
0x504d  dup
0x504e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x5053  ldc.i4.1
0x5054  beq.s    loc_5059
0x5056  ldc.i4.0
0x5057  br.s     loc_505A
0x5059  ldc.i4.1
0x505a  stloc.2
0x505b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5060  stloc.3
0x5061  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x5066  stloc.s  4
0x5068  br       loc_51BE
0x506d  ldloc.s  4
0x506f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x5074  stloc.s  5
0x5076  ldloc.s  5
0x5078  ldstr    aFielddelimiter// "fielddelimitercode"
0x507d  ldloc.0
0x507e  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_FieldDelimiter()
0x5083  box      [mscorlib]System.Int32
0x5088  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x508d  ldloc.s  5
0x508f  ldstr    aDatadelimiterc// "datadelimitercode"
0x5094  ldloc.0
0x5095  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_DataDelimiter()
0x509a  box      [mscorlib]System.Int32
0x509f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x50a4  ldloc.s  5
0x50a6  ldstr    aIsfirstrowhead// "isfirstrowheader"
0x50ab  ldloc.0
0x50ac  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportWizardState::get_IsFirstRowHeader()
0x50b1  box      [mscorlib]System.Boolean
0x50b6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x50bb  ldloc.2
0x50bc  brfalse.s loc_50CF
0x50be  ldloc.s  5
0x50c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x50c5  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50ca  br       loc_518D
0x50cf  nop
0x50d0  ldloc.s  5
0x50d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x50d7  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50dc  leave    loc_518D
0x50e1  stloc.s  6
0x50e3  ldloc.s  6
0x50e5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x50ea  ldc.i4   0x80040337
0x50ef  beq.s    loc_5145
0x50f1  ldloc.s  6
0x50f3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x50f8  ldc.i4   0x80040368
0x50fd  beq.s    loc_5145
0x50ff  ldloc.s  6
0x5101  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5106  ldc.i4   0x80040365
0x510b  beq.s    loc_5145
0x510d  ldloc.s  6
0x510f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5114  ldc.i4   0x80040366
0x5119  beq.s    loc_5145
0x511b  ldloc.s  6
0x511d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5122  ldc.i4   0x80040350
0x5127  beq.s    loc_5145
0x5129  ldloc.s  6
0x512b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5130  ldc.i4   0x80040338
0x5135  beq.s    loc_5145
0x5137  ldloc.s  6
0x5139  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x513e  ldc.i4   0x80040348
0x5143  bne.un.s loc_518B
0x5145  ldloc.s  6
0x5147  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x514c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5151  stloc.s  7
0x5153  newobj   instance void ImportFileErrorInfo::.ctor()
0x5158  stloc.s  8
0x515a  ldloc.s  8
0x515c  ldloc.s  5
0x515e  ldstr    aSource// "source"
0x5163  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5168  castclass [mscorlib]System.String
0x516d  callvirt instance void ImportFileErrorInfo::set_FileName(string value)
0x5172  ldloc.s  8
0x5174  ldloc.s  7
0x5176  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_DisplayText()
0x517b  callvirt instance void ImportFileErrorInfo::set_ErrorMessage(string value)
0x5180  ldloc.3
0x5181  ldloc.s  8
0x5183  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x5188  pop
0x5189  leave.s  loc_51BE
0x518b  rethrow
0x518d  ldstr    aImportfile// "importfile"
0x5192  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5197  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x519c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x51a1  ldloc.s  5
0x51a3  ldstr    aImportfileid// "importfileid"
0x51a8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x51ad  unbox.any [mscorlib]System.Guid
0x51b2  callvirt instance string[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportFile::RetrieveHeaders(valuetype [mscorlib]System.Guid)
0x51b7  ldlen
0x51b8  conv.i4
0x51b9  ldc.i4.1
0x51ba  bne.un.s loc_51BE
0x51bc  ldc.i4.0
0x51bd  stloc.1
0x51be  ldloc.s  4
0x51c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x51c5  brtrue   loc_506D
0x51ca  leave.s  loc_51D8
0x51cc  ldloc.s  4
0x51ce  brfalse.s loc_51D7
0x51d0  ldloc.s  4
0x51d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x51d7  endfinally
0x51d8  ldloc.3
0x51d9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x51de  ldc.i4.0
0x51df  ble      loc_52EC
0x51e4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x51e9  stloc.s  9
0x51eb  ldloc.s  9
0x51ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x51f2  ldstr    aImportwizardEr// "ImportWizard.ErrorHandling.Header"
0x51f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5201  pop
0x5202  ldloc.s  9
0x5204  ldstr    aBrTableBorder1// "<br><table border=\"1\">"
0x5209  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x520e  pop
0x520f  ldloc.s  9
0x5211  ldstr    aTrTdWidth200px// "<tr><td width=\"200px\"><b>"
0x5216  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x521b  pop
0x521c  ldloc.s  9
0x521e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5223  ldstr    aImportwizardEr_0// "ImportWizard.ErrorHandling.FileName"
0x5228  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x522d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5232  pop
0x5233  ldloc.s  9
0x5235  ldstr    aBTdTdB// "</b></td><td><b>"
0x523a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x523f  pop
0x5240  ldloc.s  9
0x5242  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5247  ldstr    aImportwizardEr_1// "ImportWizard.ErrorHandling.Error"
0x524c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5251  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5256  pop
0x5257  ldloc.s  9
0x5259  ldstr    aBTdTr// "</b></td></tr>"
0x525e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5263  pop
0x5264  ldc.i4.0
0x5265  stloc.s  0xA
0x5267  br.s     loc_52C3
0x5269  ldloc.3
0x526a  ldloc.s  0xA
0x526c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x5271  castclass ImportFileErrorInfo
0x5276  stloc.s  0xB
0x5278  ldloc.s  9
0x527a  ldstr    aTrTdWidth200px_0// "<tr><td width=\"200px\">"
0x527f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5284  pop
0x5285  ldloc.s  9
0x5287  ldloc.s  0xB
0x5289  callvirt instance string ImportFileErrorInfo::get_FileName()
0x528e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5293  pop
0x5294  ldloc.s  9
0x5296  ldstr    aTdTd// "</td><td>"
0x529b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x52a0  pop
0x52a1  ldloc.s  9
0x52a3  ldloc.s  0xB
0x52a5  callvirt instance string ImportFileErrorInfo::get_ErrorMessage()
0x52aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x52af  pop
0x52b0  ldloc.s  9
0x52b2  ldstr    aTdTr// "</td></tr>"
0x52b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x52bc  pop
0x52bd  ldloc.s  0xA
0x52bf  ldc.i4.1
0x52c0  add
0x52c1  stloc.s  0xA
0x52c3  ldloc.s  0xA
0x52c5  ldloc.3
0x52c6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x52cb  blt.s    loc_5269
0x52cd  ldloc.s  9
0x52cf  ldstr    aTable// "</table>"
0x52d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x52d9  pop
0x52da  ldloc.s  9
0x52dc  callvirt instance string [mscorlib]System.Object::ToString()
0x52e1  ldc.i4   0x8004034A
0x52e6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x52eb  throw
0x52ec  ldloc.1
0x52ed  stloc.s  0xC
0x52ef  leave.s  loc_52FC
0x52f1  stloc.s  0xD
0x52f3  ldarg.0
0x52f4  ldloc.s  0xD
0x52f6  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x52fb  throw
0x52fc  ldloc.s  0xC
0x52fe  ret
```
