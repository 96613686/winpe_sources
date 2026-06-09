# Microsoft.Crm.Application.Forms.DialogForm::GetDefaultButton

- ea: `0x29930`
- end: `0x29b00`
- name: `Microsoft.Crm.Application.Forms.DialogForm::GetDefaultButton`
- size: `464`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x298d0`
- `0x298f0`

## callees

- `0x29570`
- `0x29930`
- `0x29be0`

## string_xrefs

- `0x299da`: `cmdDialogDelete`
- `0x299e0`: `Button_Label_Delete`
- `0x299e6`: `button_delete();`
- `0x29a4f`: `butRemove`
- `0x29a55`: `Button_Label_Remove`
- `0x29a5b`: `if(!Mscrm.Utilities.resetValidationFailedElement()){removeOptimization();}`

## pseudocode

```c

```

## disassembly

```asm
0x29930  ldsfld   string [mscorlib]System.String::Empty
0x29935  stloc.0
0x29936  ldsfld   string [mscorlib]System.String::Empty
0x2993b  stloc.1
0x2993c  ldsfld   string [mscorlib]System.String::Empty
0x29941  stloc.2
0x29942  ldc.i4.0
0x29943  stloc.3
0x29944  ldc.i4.0
0x29945  stloc.s  4
0x29947  ldarg.1
0x29948  ldc.i4   0x200
0x2994d  bgt.s    loc_29998
0x2994f  ldarg.1
0x29950  ldc.i4.s 0x10
0x29952  bgt.s    loc_2997B
0x29954  ldarg.1
0x29955  switch   loc_299D8, loc_29A0A, loc_29A8E, loc_29AE1, loc_29A66
0x2996e  ldarg.1
0x2996f  ldc.i4.s 0x10
0x29971  beq      loc_29A7A
0x29976  br       loc_29AE1
0x2997b  ldarg.1
0x2997c  ldc.i4.s 0x40
0x2997e  beq      loc_29AA2
0x29983  ldarg.1
0x29984  ldc.i4   0x100
0x29989  beq.s    loc_299DA
0x2998b  ldarg.1
0x2998c  ldc.i4   0x200
0x29991  beq.s    loc_299F3
0x29993  br       loc_29AE1
0x29998  ldarg.1
0x29999  ldc.i4   0x1000
0x2999e  bgt.s    loc_299B8
0x299a0  ldarg.1
0x299a1  ldc.i4   0x400
0x299a6  beq.s    loc_29A21
0x299a8  ldarg.1
0x299a9  ldc.i4   0x1000
0x299ae  beq      loc_29AB6
0x299b3  br       loc_29AE1
0x299b8  ldarg.1
0x299b9  ldc.i4   0x4000
0x299be  beq      loc_29ACA
0x299c3  ldarg.1
0x299c4  ldc.i4   0x8000
0x299c9  beq.s    loc_29A38
0x299cb  ldarg.1
0x299cc  ldc.i4   0x10000
0x299d1  beq.s    loc_29A4F
0x299d3  br       loc_29AE1
0x299d8  ldnull
0x299d9  ret
0x299da  ldstr    aCmddialogdelet// "cmdDialogDelete"
0x299df  stloc.0
0x299e0  ldstr    aButtonLabelDel// "Button_Label_Delete"
0x299e5  stloc.1
0x299e6  ldstr    aButtonDelete// "button_delete();"
0x299eb  stloc.2
0x299ec  ldc.i4.0
0x299ed  stloc.3
0x299ee  br       loc_29AEB
0x299f3  ldstr    aCmddialogdeact// "cmdDialogDeactivate"
0x299f8  stloc.0
0x299f9  ldstr    aButtonLabelDea// "Button_Label_Deactivate"
0x299fe  stloc.1
0x299ff  ldstr    aButtonDeactiva// "button_deactivate();"
0x29a04  stloc.2
0x29a05  br       loc_29AEB
0x29a0a  ldstr    aButbegin// "butBegin"
0x29a0f  stloc.0
0x29a10  ldstr    aButtonLabelOk// "Button_Label_OK"
0x29a15  stloc.1
0x29a16  ldstr    aIfMscrmUtiliti// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a1b  stloc.2
0x29a1c  br       loc_29AEB
0x29a21  ldstr    aButbegin// "butBegin"
0x29a26  stloc.0
0x29a27  ldstr    aButtonLabelSav// "Button_Label_Save"
0x29a2c  stloc.1
0x29a2d  ldstr    aIfMscrmUtiliti// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a32  stloc.2
0x29a33  br       loc_29AEB
0x29a38  ldstr    aButoptimize// "butOptimize"
0x29a3d  stloc.0
0x29a3e  ldstr    aDataPerformanc// "Data.Performance.Dashboard.OptimizeButt"...
0x29a43  stloc.1
0x29a44  ldstr    aIfMscrmUtiliti_0// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a49  stloc.2
0x29a4a  br       loc_29AEB
0x29a4f  ldstr    aButremove// "butRemove"
0x29a54  stloc.0
0x29a55  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x29a5a  stloc.1
0x29a5b  ldstr    aIfMscrmUtiliti_1// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a60  stloc.2
0x29a61  br       loc_29AEB
0x29a66  ldstr    aButdialogyes// "butDialogYes"
0x29a6b  stloc.0
0x29a6c  ldstr    aButtonLabelYes// "Button_Label_Yes"
0x29a71  stloc.1
0x29a72  ldstr    aButtonYes// "button_yes();"
0x29a77  stloc.2
0x29a78  br.s     loc_29AEB
0x29a7a  ldstr    aCmddialogno// "cmdDialogNo"
0x29a7f  stloc.0
0x29a80  ldstr    aButtonLabelNo// "Button_Label_No"
0x29a85  stloc.1
0x29a86  ldstr    aButtonNo// "button_no();"
0x29a8b  stloc.2
0x29a8c  br.s     loc_29AEB
0x29a8e  ldstr    aCmddialogcance// "cmdDialogCancel"
0x29a93  stloc.0
0x29a94  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x29a99  stloc.1
0x29a9a  ldstr    aIfMscrmUtiliti_2// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a9f  stloc.2
0x29aa0  br.s     loc_29AEB
0x29aa2  ldstr    aCmddialogapply// "cmdDialogApply"
0x29aa7  stloc.0
0x29aa8  ldstr    aButtonLabelApp// "Button_Label_Apply"
0x29aad  stloc.1
0x29aae  ldstr    aButtonApply// "button_apply();"
0x29ab3  stloc.2
0x29ab4  br.s     loc_29AEB
0x29ab6  ldstr    aCmddialogreset// "cmdDialogReset"
0x29abb  stloc.0
0x29abc  ldstr    aButtonLabelRes// "Button_Label_Reset"
0x29ac1  stloc.1
0x29ac2  ldstr    aButtonReset// "button_reset();"
0x29ac7  stloc.2
0x29ac8  br.s     loc_29AEB
0x29aca  ldstr    aCmddialogerror// "cmdDialogErrorLog"
0x29acf  stloc.0
0x29ad0  ldstr    aDialogSharepoi// "Dialog_SharePoint_Site_Validation_Error"...
0x29ad5  stloc.1
0x29ad6  ldstr    aErrorlogbutton// "errorLogButtonAction();"
0x29adb  stloc.2
0x29adc  ldc.i4.1
0x29add  stloc.s  4
0x29adf  br.s     loc_29AEB
0x29ae1  ldstr    aInvalidButtonS// "Invalid button style"
0x29ae6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Trace::AssertEx(object)
0x29aeb  ldarg.0
0x29aec  ldloc.0
0x29aed  ldloc.1
0x29aee  ldloc.2
0x29aef  ldloc.3
0x29af0  ldarg.1
0x29af1  ldarg.0
0x29af2  call     instance bool Microsoft.Crm.Application.Forms.DialogForm::get_SetAccessKeysForDefaultButtons()
0x29af7  ldarg.2
0x29af8  ldloc.s  4
0x29afa  call     instance class DialogButton Microsoft.Crm.Application.Forms.DialogForm::CreateButton(string id, string resourceId, string onClick, bool disabled, valuetype Microsoft.Crm.Application.Forms.DialogButtonStyles style, bool setAccessKeyFromResource, string tooltip, bool hidden)
0x29aff  ret
```
