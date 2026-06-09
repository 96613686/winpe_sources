# Microsoft.Crm.Application.Controls.NotesDataControl::RenderNotesCreator

- ea: `0xa8420`
- end: `0xa86bd`
- name: `Microsoft.Crm.Application.Controls.NotesDataControl::RenderNotesCreator`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa88e0`

## callees

- `0xa8420`

## string_xrefs

- `0xa84b6`: `<textarea id="noteTextInput-create" class="ms-crm-Note-Text-create" tabIndex="0" unselectable="true" contenteditable="true" `
- `0xa8556`: `<Button class="noteAttachButton" id="noteAttachButton" accessKey="A" `
- `0xa8562`: ` onclick="var c=$find('{0}'); if (!IsNull(c)) c.createNote(new Sys.UI.DomEvent(event));" `
- `0xa8619`: ` onclick="var c=$find('{0}'); if (!IsNull(c)) c.createNote(new Sys.UI.DomEvent(event));" `
- `0xa856f`: ` onmouseover="var c=$find('{0}'); if (!IsNull(c)) c.setPreventCreateButtonHide(true);" `
- `0xa8626`: ` onmouseover="var c=$find('{0}'); if (!IsNull(c)) c.setPreventCreateButtonHide(true);" `
- `0xa857c`: ` onmouseout="var c=$find('{0}'); if (!IsNull(c)) c.setPreventCreateButtonHide(false);" `
- `0xa8633`: ` onmouseout="var c=$find('{0}'); if (!IsNull(c)) c.setPreventCreateButtonHide(false);" `
- `0xa860d`: `<Button class="noteDoneButton" id="noteDoneButton" accessKey="D" `

## pseudocode

```c

```

## disassembly

```asm
0xa8420  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateNote()
0xa8425  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa842a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa842f  brtrue.s loc_A8432
0xa8431  ret
0xa8432  ldarg.3
0xa8433  brfalse.s loc_A8439
0xa8435  ldarg.3
0xa8436  ldc.i4.0
0xa8437  ble.s    loc_A8446
0xa8439  ldarg.0
0xa843a  ldstr    aDivClassNotest// "<div class=\"notesTextBoxDiv\" id=\"not"...
0xa843f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8444  br.s     loc_A8499
0xa8446  ldarg.0
0xa8447  ldstr    aDivClassNotest_0// "<div class=\"notesTextBoxDiv\" id=\"not"...
0xa844c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8451  ldarg.0
0xa8452  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8457  ldstr    aBClassNotchSty// "<b class=\"notch\" style=\"left: {0}px;"...
0xa845c  ldc.i4.1
0xa845d  newarr   [mscorlib]System.Object
0xa8462  dup
0xa8463  ldc.i4.0
0xa8464  ldarg.3
0xa8465  box      [mscorlib]System.Int32
0xa846a  stelem.ref
0xa846b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8470  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8475  ldarg.0
0xa8476  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa847b  ldstr    aBClassNotchBor// "<b class=\"notch border-notch\" style="...
0xa8480  ldc.i4.1
0xa8481  newarr   [mscorlib]System.Object
0xa8486  dup
0xa8487  ldc.i4.0
0xa8488  ldarg.3
0xa8489  box      [mscorlib]System.Int32
0xa848e  stelem.ref
0xa848f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8494  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8499  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa849e  stloc.0
0xa849f  ldarg.0
0xa84a0  ldstr    aDivClassNotest_1// "<div class=\"notesTextBoxSpacer\">"
0xa84a5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa84aa  ldarg.1
0xa84ab  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xa84b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xa84b5  stloc.1
0xa84b6  ldstr    aTextareaIdNote// "<textarea id=\"noteTextInput-create\" c"...
0xa84bb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xa84c0  stloc.2
0xa84c1  ldloc.2
0xa84c2  ldstr    aOnkeydownVarCF// " onkeydown=\"var c=$find('{0}');if (!Is"...
0xa84c7  ldloc.1
0xa84c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa84cd  pop
0xa84ce  ldloc.2
0xa84cf  ldstr    aOnfocusVarCFin// " onfocus=\"var c=$find('{0}'); if (!IsN"...
0xa84d4  ldloc.1
0xa84d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa84da  pop
0xa84db  ldloc.2
0xa84dc  ldstr    aOnblurVarCFind// " onblur=\"var c=$find('{0}'); if (!IsNu"...
0xa84e1  ldloc.1
0xa84e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa84e7  pop
0xa84e8  ldloc.2
0xa84e9  ldstr    aOnkeyupVarCFin// " onkeyup=\"var c=$find('{0}'); if (!IsN"...
0xa84ee  ldloc.1
0xa84ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa84f4  pop
0xa84f5  ldloc.2
0xa84f6  ldstr    asc_111CB6// ">"
0xa84fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8500  pop
0xa8501  ldloc.2
0xa8502  ldloc.0
0xa8503  ldstr    aNewnotehinttex// "NewNoteHintText"
0xa8508  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa850d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8512  pop
0xa8513  ldloc.2
0xa8514  ldstr    aTextarea_0// "</textarea>"
0xa8519  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa851e  pop
0xa851f  ldloc.2
0xa8520  ldstr    aDiv_1// "</div>"
0xa8525  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa852a  pop
0xa852b  ldarg.0
0xa852c  ldloc.2
0xa852d  callvirt instance string [mscorlib]System.Object::ToString()
0xa8532  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8537  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xa853c  stloc.3
0xa853d  ldloc.3
0xa853e  ldstr    aDivClassNotest_2// "<div class=\"notesTextBoxActionsDiv\" i"...
0xa8543  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8548  pop
0xa8549  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa854e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8553  brtrue.s loc_A85BE
0xa8555  ldloc.3
0xa8556  ldstr    aButtonClassNot// "<Button class=\"noteAttachButton\" id="...
0xa855b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8560  pop
0xa8561  ldloc.3
0xa8562  ldstr    aOnclickVarCFin// " onclick=\"var c=$find('{0}'); if (!IsN"...
0xa8567  ldloc.1
0xa8568  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa856d  pop
0xa856e  ldloc.3
0xa856f  ldstr    aOnmouseoverVar// " onmouseover=\"var c=$find('{0}'); if ("...
0xa8574  ldloc.1
0xa8575  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa857a  pop
0xa857b  ldloc.3
0xa857c  ldstr    aOnmouseoutVarC// " onmouseout=\"var c=$find('{0}'); if (!"...
0xa8581  ldloc.1
0xa8582  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa8587  pop
0xa8588  ldloc.3
0xa8589  ldstr    aOnkeydownVarCF// " onkeydown=\"var c=$find('{0}');if (!Is"...
0xa858e  ldloc.1
0xa858f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa8594  pop
0xa8595  ldloc.3
0xa8596  ldstr    aOnblurVarCFind// " onblur=\"var c=$find('{0}'); if (!IsNu"...
0xa859b  ldloc.1
0xa859c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa85a1  pop
0xa85a2  ldloc.3
0xa85a3  ldstr    aTypeButtonTitl// "type=\"button\" title=\"{0}\" value=\"{"...
0xa85a8  ldloc.0
0xa85a9  ldstr    aMscrmFormEmail// "Mscrm_Form_email_MainTab_Actions_Attach"...
0xa85ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa85b3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa85b8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa85bd  pop
0xa85be  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa85c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0xa85c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa85cd  stloc.s  4
0xa85cf  ldloc.s  4
0xa85d1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa85d6  ldarg.2
0xa85d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xa85dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xa85e1  ldloc.s  4
0xa85e3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa85e8  stloc.s  5
0xa85ea  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa85ef  ldloc.0
0xa85f0  ldstr    aRibbonTooltipA// "Ribbon.Tooltip.AddNote"
0xa85f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa85fa  ldc.i4.1
0xa85fb  newarr   [mscorlib]System.Object
0xa8600  dup
0xa8601  ldc.i4.0
0xa8602  ldloc.s  5
0xa8604  stelem.ref
0xa8605  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa860a  stloc.s  6
0xa860c  ldloc.3
0xa860d  ldstr    aButtonClassNot_0// "<Button class=\"noteDoneButton\" id=\"n"...
0xa8612  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa8617  pop
0xa8618  ldloc.3
0xa8619  ldstr    aOnclickVarCFin// " onclick=\"var c=$find('{0}'); if (!IsN"...
0xa861e  ldloc.1
0xa861f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa8624  pop
0xa8625  ldloc.3
0xa8626  ldstr    aOnmouseoverVar// " onmouseover=\"var c=$find('{0}'); if ("...
0xa862b  ldloc.1
0xa862c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa8631  pop
0xa8632  ldloc.3
0xa8633  ldstr    aOnmouseoutVarC// " onmouseout=\"var c=$find('{0}'); if (!"...
0xa8638  ldloc.1
0xa8639  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa863e  pop
0xa863f  ldloc.3
0xa8640  ldstr    aOnkeydownVarCF// " onkeydown=\"var c=$find('{0}');if (!Is"...
0xa8645  ldloc.1
0xa8646  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa864b  pop
0xa864c  ldloc.3
0xa864d  ldstr    aOnblurVarCFind// " onblur=\"var c=$find('{0}'); if (!IsNu"...
0xa8652  ldloc.1
0xa8653  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa8658  pop
0xa8659  ldloc.3
0xa865a  ldstr    aTitle0// " title=\"{0}\""
0xa865f  ldloc.s  6
0xa8661  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xa8666  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xa866b  pop
0xa866c  ldloc.3
0xa866d  ldstr    aTypeButtonValu// " type=\"button\" value=\"{0}\">{1}</But"...
0xa8672  ldloc.0
0xa8673  ldstr    aNewnotebuttont// "NewNoteButtonText"
0xa8678  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa867d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xa8682  ldloc.0
0xa8683  ldstr    aNewnotebuttont// "NewNoteButtonText"
0xa8688  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa868d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa8692  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0xa8697  pop
0xa8698  ldloc.3
0xa8699  ldstr    aDiv_1// "</div>"
0xa869e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa86a3  pop
0xa86a4  ldloc.3
0xa86a5  ldstr    aDiv_1// "</div>"
0xa86aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa86af  pop
0xa86b0  ldarg.0
0xa86b1  ldloc.3
0xa86b2  callvirt instance string [mscorlib]System.Object::ToString()
0xa86b7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa86bc  ret
```
