# Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::.cctor

- ea: `0xf4f80`
- end: `0xf5205`
- name: `Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::.cctor`
- size: `645`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## string_xrefs

- `0xf4f88`: `/_common/styles/jquery/jQuery.UI.core.css`
- `0xf4f90`: `/_common/styles/jquery/jQuery.UI.theme.css`
- `0xf5084`: `LOCID_TRACE_DELETE_TOOLTIP`
- `0xf508c`: `Web.Wall_DeleteTraceToolTip`
- `0xf5106`: `LOCID_MAIN_WALL_DELETE_CONFIRM`
- `0xf510e`: `Web.Wall_MainWallPageDeleteConfirmMessage`
- `0xf5120`: `LOCID_RECORD_WALL_DELETE_CONFIRM`
- `0xf5128`: `Web.Wall_RecordWallPageDeleteConfirmMessage`
- `0xf513a`: `LOCID_TRACE_PRIVILEGE_ERROR`
- `0xf5142`: `Web.Wall_PrivilegeError`
- `0xf516e`: `LOCID_DELETE_ALL_CONFIRM`
- `0xf5176`: `Web.Wall_DeleteAllConfirm`
- `0xf5188`: `LOCID_DELETE_ALL_FAIL_MESSAGE`
- `0xf51a2`: `LOCID_TRACE_SHOWERROR_COMMAND`
- `0xf51aa`: `Web.Wall_ShowErrorTraceCommand`
- `0xf51d6`: `LOCID_TRACE_HIDEERROR_COMMAND`
- `0xf51de`: `Web.Wall_HideErrorTraceCommand`

## pseudocode

```c

```

## disassembly

```asm
0xf4f80  ldc.i4.4
0xf4f81  newarr   [mscorlib]System.String
0xf4f86  dup
0xf4f87  ldc.i4.0
0xf4f88  ldstr    aCommonStylesJq_2// "/_common/styles/jquery/jQuery.UI.core.c"...
0xf4f8d  stelem.ref
0xf4f8e  dup
0xf4f8f  ldc.i4.1
0xf4f90  ldstr    aCommonStylesJq_3// "/_common/styles/jquery/jQuery.UI.theme."...
0xf4f95  stelem.ref
0xf4f96  dup
0xf4f97  ldc.i4.2
0xf4f98  ldstr    aControlsWallco// "/_controls/wallcontrol/WallContent.css."...
0xf4f9d  stelem.ref
0xf4f9e  dup
0xf4f9f  ldc.i4.3
0xf4fa0  ldstr    aControlsWallco_0// "/_controls/wallcontrol/UserWall.css"
0xf4fa5  stelem.ref
0xf4fa6  stsfld   string[] Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::styleSheets
0xf4fab  ldc.i4.s 0x17
0xf4fad  newarr   string[]
0xf4fb2  dup
0xf4fb3  ldc.i4.0
0xf4fb4  ldc.i4.2
0xf4fb5  newarr   [mscorlib]System.String
0xf4fba  dup
0xf4fbb  ldc.i4.0
0xf4fbc  ldstr    aLocidTraceAll// "LOCID_TRACE_ALL"
0xf4fc1  stelem.ref
0xf4fc2  dup
0xf4fc3  ldc.i4.1
0xf4fc4  ldstr    aWebWallAlltrac// "Web.Wall_AllTraces"
0xf4fc9  stelem.ref
0xf4fca  stelem.ref
0xf4fcb  dup
0xf4fcc  ldc.i4.1
0xf4fcd  ldc.i4.2
0xf4fce  newarr   [mscorlib]System.String
0xf4fd3  dup
0xf4fd4  ldc.i4.0
0xf4fd5  ldstr    aLocidTraceErro// "LOCID_TRACE_ERROR"
0xf4fda  stelem.ref
0xf4fdb  dup
0xf4fdc  ldc.i4.1
0xf4fdd  ldstr    aWebWallErrortr// "Web.Wall_ErrorTraces"
0xf4fe2  stelem.ref
0xf4fe3  stelem.ref
0xf4fe4  dup
0xf4fe5  ldc.i4.2
0xf4fe6  ldc.i4.2
0xf4fe7  newarr   [mscorlib]System.String
0xf4fec  dup
0xf4fed  ldc.i4.0
0xf4fee  ldstr    aLocidTraceWarn// "LOCID_TRACE_WARNING"
0xf4ff3  stelem.ref
0xf4ff4  dup
0xf4ff5  ldc.i4.1
0xf4ff6  ldstr    aWebWallWarning// "Web.Wall_WarningTraces"
0xf4ffb  stelem.ref
0xf4ffc  stelem.ref
0xf4ffd  dup
0xf4ffe  ldc.i4.3
0xf4fff  ldc.i4.2
0xf5000  newarr   [mscorlib]System.String
0xf5005  dup
0xf5006  ldc.i4.0
0xf5007  ldstr    aLocidTraceInfo// "LOCID_TRACE_INFORMATION"
0xf500c  stelem.ref
0xf500d  dup
0xf500e  ldc.i4.1
0xf500f  ldstr    aWebWallInforma// "Web.Wall_InformationTraces"
0xf5014  stelem.ref
0xf5015  stelem.ref
0xf5016  dup
0xf5017  ldc.i4.4
0xf5018  ldc.i4.2
0xf5019  newarr   [mscorlib]System.String
0xf501e  dup
0xf501f  ldc.i4.0
0xf5020  ldstr    aLocidTraceAllF// "LOCID_TRACE_ALL_FILTER_TOOLTIP"
0xf5025  stelem.ref
0xf5026  dup
0xf5027  ldc.i4.1
0xf5028  ldstr    aWebWallAlltrac_0// "Web.Wall_AllTraceToolTip"
0xf502d  stelem.ref
0xf502e  stelem.ref
0xf502f  dup
0xf5030  ldc.i4.5
0xf5031  ldc.i4.2
0xf5032  newarr   [mscorlib]System.String
0xf5037  dup
0xf5038  ldc.i4.0
0xf5039  ldstr    aLocidTraceErrF// "LOCID_TRACE_ERR_FILTER_TOOLTIP"
0xf503e  stelem.ref
0xf503f  dup
0xf5040  ldc.i4.1
0xf5041  ldstr    aWebWallErrorfi// "Web.Wall_ErrorFilterToolTip"
0xf5046  stelem.ref
0xf5047  stelem.ref
0xf5048  dup
0xf5049  ldc.i4.6
0xf504a  ldc.i4.2
0xf504b  newarr   [mscorlib]System.String
0xf5050  dup
0xf5051  ldc.i4.0
0xf5052  ldstr    aLocidTraceWarn_0// "LOCID_TRACE_WARN_FILTER_TOOLTIP"
0xf5057  stelem.ref
0xf5058  dup
0xf5059  ldc.i4.1
0xf505a  ldstr    aWebWallWarning_0// "Web.Wall_WarningFilterToolTip"
0xf505f  stelem.ref
0xf5060  stelem.ref
0xf5061  dup
0xf5062  ldc.i4.7
0xf5063  ldc.i4.2
0xf5064  newarr   [mscorlib]System.String
0xf5069  dup
0xf506a  ldc.i4.0
0xf506b  ldstr    aLocidTraceInfo_0// "LOCID_TRACE_INFO_FILTER_TOOLTIP"
0xf5070  stelem.ref
0xf5071  dup
0xf5072  ldc.i4.1
0xf5073  ldstr    aWebWallInforma_0// "Web.Wall_InformationFilterToolTip"
0xf5078  stelem.ref
0xf5079  stelem.ref
0xf507a  dup
0xf507b  ldc.i4.8
0xf507c  ldc.i4.2
0xf507d  newarr   [mscorlib]System.String
0xf5082  dup
0xf5083  ldc.i4.0
0xf5084  ldstr    aLocidTraceDele// "LOCID_TRACE_DELETE_TOOLTIP"
0xf5089  stelem.ref
0xf508a  dup
0xf508b  ldc.i4.1
0xf508c  ldstr    aWebWallDeletet// "Web.Wall_DeleteTraceToolTip"
0xf5091  stelem.ref
0xf5092  stelem.ref
0xf5093  dup
0xf5094  ldc.i4.s 9
0xf5096  ldc.i4.2
0xf5097  newarr   [mscorlib]System.String
0xf509c  dup
0xf509d  ldc.i4.0
0xf509e  ldstr    aLocidTraceExCo// "LOCID_TRACE_EX_CONFIRMTOOLTIP"
0xf50a3  stelem.ref
0xf50a4  dup
0xf50a5  ldc.i4.1
0xf50a6  ldstr    aWebWallExchang// "Web.Wall_ExchangeSyncConfirmActionToolT"...
0xf50ab  stelem.ref
0xf50ac  stelem.ref
0xf50ad  dup
0xf50ae  ldc.i4.s 0xA
0xf50b0  ldc.i4.2
0xf50b1  newarr   [mscorlib]System.String
0xf50b6  dup
0xf50b7  ldc.i4.0
0xf50b8  ldstr    aLocidTraceExDe// "LOCID_TRACE_EX_DENYTOOLTIP"
0xf50bd  stelem.ref
0xf50be  dup
0xf50bf  ldc.i4.1
0xf50c0  ldstr    aWebWallExchang_0// "Web.Wall_ExchangeSyncDenyActionToolTip"
0xf50c5  stelem.ref
0xf50c6  stelem.ref
0xf50c7  dup
0xf50c8  ldc.i4.s 0xB
0xf50ca  ldc.i4.2
0xf50cb  newarr   [mscorlib]System.String
0xf50d0  dup
0xf50d1  ldc.i4.0
0xf50d2  ldstr    aLocidTraceExCo_0// "LOCID_TRACE_EX_CONFIRMBUTTONTEXT"
0xf50d7  stelem.ref
0xf50d8  dup
0xf50d9  ldc.i4.1
0xf50da  ldstr    aWebWallExchang_1// "Web.Wall_ExchangeSyncConfirmActionButto"...
0xf50df  stelem.ref
0xf50e0  stelem.ref
0xf50e1  dup
0xf50e2  ldc.i4.s 0xC
0xf50e4  ldc.i4.2
0xf50e5  newarr   [mscorlib]System.String
0xf50ea  dup
0xf50eb  ldc.i4.0
0xf50ec  ldstr    aLocidTraceExDe_0// "LOCID_TRACE_EX_DENYBUTTONTEXT"
0xf50f1  stelem.ref
0xf50f2  dup
0xf50f3  ldc.i4.1
0xf50f4  ldstr    aWebWallExchang_2// "Web.Wall_ExchangeSyncDenyActionButtonTe"...
0xf50f9  stelem.ref
0xf50fa  stelem.ref
0xf50fb  dup
0xf50fc  ldc.i4.s 0xD
0xf50fe  ldc.i4.2
0xf50ff  newarr   [mscorlib]System.String
0xf5104  dup
0xf5105  ldc.i4.0
0xf5106  ldstr    aLocidMainWallD// "LOCID_MAIN_WALL_DELETE_CONFIRM"
0xf510b  stelem.ref
0xf510c  dup
0xf510d  ldc.i4.1
0xf510e  ldstr    aWebWallMainwal// "Web.Wall_MainWallPageDeleteConfirmMessa"...
0xf5113  stelem.ref
0xf5114  stelem.ref
0xf5115  dup
0xf5116  ldc.i4.s 0xE
0xf5118  ldc.i4.2
0xf5119  newarr   [mscorlib]System.String
0xf511e  dup
0xf511f  ldc.i4.0
0xf5120  ldstr    aLocidRecordWal// "LOCID_RECORD_WALL_DELETE_CONFIRM"
0xf5125  stelem.ref
0xf5126  dup
0xf5127  ldc.i4.1
0xf5128  ldstr    aWebWallRecordw// "Web.Wall_RecordWallPageDeleteConfirmMes"...
0xf512d  stelem.ref
0xf512e  stelem.ref
0xf512f  dup
0xf5130  ldc.i4.s 0xF
0xf5132  ldc.i4.2
0xf5133  newarr   [mscorlib]System.String
0xf5138  dup
0xf5139  ldc.i4.0
0xf513a  ldstr    aLocidTracePriv// "LOCID_TRACE_PRIVILEGE_ERROR"
0xf513f  stelem.ref
0xf5140  dup
0xf5141  ldc.i4.1
0xf5142  ldstr    aWebWallPrivile// "Web.Wall_PrivilegeError"
0xf5147  stelem.ref
0xf5148  stelem.ref
0xf5149  dup
0xf514a  ldc.i4.s 0x10
0xf514c  ldc.i4.2
0xf514d  newarr   [mscorlib]System.String
0xf5152  dup
0xf5153  ldc.i4.0
0xf5154  ldstr    aLocidTraceErro_0// "LOCID_TRACE_ERROR_MESSAGE"
0xf5159  stelem.ref
0xf515a  dup
0xf515b  ldc.i4.1
0xf515c  ldstr    aWebWallErrorme// "Web.Wall_ErrorMessage"
0xf5161  stelem.ref
0xf5162  stelem.ref
0xf5163  dup
0xf5164  ldc.i4.s 0x11
0xf5166  ldc.i4.2
0xf5167  newarr   [mscorlib]System.String
0xf516c  dup
0xf516d  ldc.i4.0
0xf516e  ldstr    aLocidDeleteAll// "LOCID_DELETE_ALL_CONFIRM"
0xf5173  stelem.ref
0xf5174  dup
0xf5175  ldc.i4.1
0xf5176  ldstr    aWebWallDeletea// "Web.Wall_DeleteAllConfirm"
0xf517b  stelem.ref
0xf517c  stelem.ref
0xf517d  dup
0xf517e  ldc.i4.s 0x12
0xf5180  ldc.i4.2
0xf5181  newarr   [mscorlib]System.String
0xf5186  dup
0xf5187  ldc.i4.0
0xf5188  ldstr    aLocidDeleteAll_0// "LOCID_DELETE_ALL_FAIL_MESSAGE"
0xf518d  stelem.ref
0xf518e  dup
0xf518f  ldc.i4.1
0xf5190  ldstr    aErrorMessageAc_2// "Error_Message_Action_MultipleErrorsFoun"...
0xf5195  stelem.ref
0xf5196  stelem.ref
0xf5197  dup
0xf5198  ldc.i4.s 0x13
0xf519a  ldc.i4.2
0xf519b  newarr   [mscorlib]System.String
0xf51a0  dup
0xf51a1  ldc.i4.0
0xf51a2  ldstr    aLocidTraceShow// "LOCID_TRACE_SHOWERROR_COMMAND"
0xf51a7  stelem.ref
0xf51a8  dup
0xf51a9  ldc.i4.1
0xf51aa  ldstr    aWebWallShowerr// "Web.Wall_ShowErrorTraceCommand"
0xf51af  stelem.ref
0xf51b0  stelem.ref
0xf51b1  dup
0xf51b2  ldc.i4.s 0x14
0xf51b4  ldc.i4.2
0xf51b5  newarr   [mscorlib]System.String
0xf51ba  dup
0xf51bb  ldc.i4.0
0xf51bc  ldstr    aLocidTraceShow_0// "LOCID_TRACE_SHOWERROR_TOOLTIP"
0xf51c1  stelem.ref
0xf51c2  dup
0xf51c3  ldc.i4.1
0xf51c4  ldstr    aWebWallShowerr_0// "Web.Wall_ShowErrorTraceToolTip"
0xf51c9  stelem.ref
0xf51ca  stelem.ref
0xf51cb  dup
0xf51cc  ldc.i4.s 0x15
0xf51ce  ldc.i4.2
0xf51cf  newarr   [mscorlib]System.String
0xf51d4  dup
0xf51d5  ldc.i4.0
  ... truncated ...
```
