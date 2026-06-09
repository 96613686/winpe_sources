# OnViewerConnectionFailedProc(uchar)

- ea: `0x14001d894`
- end: `0x14001da52`
- name: `?OnViewerConnectionFailedProc@@YAXE@Z`
- size: `446`
- prototype: `void __fastcall(unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001c340`
- `0x14001da60`

## callees

- `0x140002463`
- `0x14001d894`
- `0x14001e68c`
- `0x14001ec30`
- `0x140037e08`

## import_xrefs

- `KERNEL32!MulDiv` at `0x14001d9dc`
- `KERNEL32!MulDiv` at `0x14001d9dc`
- `KERNEL32!GetModuleHandleW` at `0x14001d93d`
- `KERNEL32!GetModuleHandleW` at `0x14001d93d`
- `USER32!GetDialogBaseUnits` at `0x14001d9c2`
- `USER32!GetDialogBaseUnits` at `0x14001d9c2`
- `USER32!KillTimer` at `0x14001d8c5`
- `USER32!KillTimer` at `0x14001d8c5`
- `USER32!PostMessageW` at `0x14001da30`
- `USER32!PostMessageW` at `0x14001da30`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14001d9f9`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14001d9f9`

## pseudocode

```c
void __fastcall OnViewerConnectionFailedProc()
{
  CEventLogger *v0; // rbx
  HWND v1; // rdi
  HMODULE ModuleHandleW; // rax
  unsigned __int16 DialogBaseUnits; // ax
  UINT v4; // edx
  LPARAM v5; // r9
  int v6; // [rsp+28h] [rbp-59h] BYREF
  __int64 v7; // [rsp+2Ch] [rbp-55h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+38h] [rbp-49h] BYREF
  int pnButton; // [rsp+E8h] [rbp+67h] BYREF

  pnButton = 0;
  KillTimer(*((HWND *)_AtlModule + 10), 1u);
  CExpInterDlg::UpdateStatusPanel((CEventLogger *)((char *)_AtlModule + 72), CTRL_LEVEL_MIN);
  CExpInterDlg::SetStatusText((CEventLogger *)((char *)_AtlModule + 72), 0);
  v0 = _AtlModule;
  v1 = (HWND)*((_QWORD *)_AtlModule + 10);
  memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
  CSqmManager::RecordError((CEventLogger *)((char *)v0 + 496), 0x223u, 0);
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = v1;
  ModuleHandleW = GetModuleHandleW(0);
  pTaskConfig.pszContent = (PCWSTR)547;
  pTaskConfig.hInstance = ModuleHandleW;
  pTaskConfig.dwFlags = 8;
  pTaskConfig.dwCommonButtons = 8;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v6;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = (HICON)65534;
  pTaskConfig.pszMainInstruction = (PCWSTR)659;
  v6 = 40962;
  v7 = 560;
  pTaskConfig.cButtons = 1;
  pTaskConfig.nDefaultButton = 0;
  pTaskConfig.pszVerificationText = 0;
  memset(&pTaskConfig.hFooterIcon, 0, 32);
  DialogBaseUnits = GetDialogBaseUnits();
  pTaskConfig.cxWidth = MulDiv(518, 4, DialogBaseUnits);
  if ( TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0) >= 0 && pnButton == 40962 )
  {
    v4 = 32798;
    v5 = 3;
  }
  else
  {
    v5 = 0;
    v4 = 16;
  }
  PostMessageW(*((HWND *)_AtlModule + 10), v4, 0, v5);
}

```

## disassembly

```asm
0x14001d894  mov     rax, rsp
0x14001d897  mov     [rax+10h], rbx
0x14001d89b  mov     [rax+18h], rdi
0x14001d89f  mov     [rax+8], cl
0x14001d8a2  push    rbp
0x14001d8a3  lea     rbp, [rax-5Fh]
0x14001d8a7  sub     rsp, 0D0h
0x14001d8ae  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001d8b5  mov     edx, 1; uIDEvent
0x14001d8ba  mov     [rbp+57h+pnButton], 0
0x14001d8c1  mov     rcx, [rcx+50h]; hWnd
0x14001d8c5  call    cs:__imp_KillTimer
0x14001d8cc  nop     dword ptr [rax+rax+00h]
0x14001d8d1  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001d8d8  xor     edx, edx; enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001
0x14001d8da  add     rcx, 48h ; 'H'; this
0x14001d8de  call    ?UpdateStatusPanel@CExpInterDlg@@QEAAJW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@@Z; CExpInterDlg::UpdateStatusPanel(__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001)
0x14001d8e3  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001d8ea  xor     edx, edx; unsigned int
0x14001d8ec  add     rcx, 48h ; 'H'; this
0x14001d8f0  call    ?SetStatusText@CExpInterDlg@@QEAAJI@Z; CExpInterDlg::SetStatusText(uint)
0x14001d8f5  mov     rbx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001d8fc  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x14001d900  xor     edx, edx; Val
0x14001d902  mov     r8d, 0A0h; Size
0x14001d908  mov     rdi, [rbx+50h]
0x14001d90c  call    memset_0
0x14001d911  xor     eax, eax
0x14001d913  lea     rcx, [rbx+1F0h]; this
0x14001d91a  mov     ebx, 223h
0x14001d91f  mov     [rbp+57h+var_B0], rax
0x14001d923  mov     edx, ebx; unsigned int
0x14001d925  mov     [rbp+57h+var_A8], eax
0x14001d928  xor     r8d, r8d; unsigned int
0x14001d92b  call    ?RecordError@CSqmManager@@QEAAXKK@Z; CSqmManager::RecordError(ulong,ulong)
0x14001d930  xor     ecx, ecx; lpModuleName
0x14001d932  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x14001d939  mov     [rbp+57h+pTaskConfig.hwndParent], rdi
0x14001d93d  call    cs:__imp_GetModuleHandleW
0x14001d944  nop     dword ptr [rax+rax+00h]
0x14001d949  mov     [rbp+57h+pTaskConfig.pszContent], rbx
0x14001d94d  mov     ebx, 0A002h
0x14001d952  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x14001d956  mov     eax, 8
0x14001d95b  mov     [rbp+57h+pTaskConfig.dwFlags], eax
0x14001d95e  mov     [rbp+57h+pTaskConfig.dwCommonButtons], eax
0x14001d961  lea     rax, [rbp+57h+var_B0]
0x14001d965  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x14001d969  mov     [rbp+57h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14001d971  mov     qword ptr [rbp+57h+pTaskConfig.24h], 0FFFEh
0x14001d979  mov     [rbp+57h+pTaskConfig.pszMainInstruction], 293h
0x14001d981  mov     dword ptr [rbp+57h+var_B0], ebx
0x14001d984  mov     [rbp+57h+var_B0+4], 230h
0x14001d98c  mov     [rbp+57h+pTaskConfig.cButtons], 1
0x14001d993  mov     [rbp+57h+pTaskConfig.nDefaultButton], 0
0x14001d99a  mov     [rbp+57h+pTaskConfig.pszVerificationText], 0
0x14001d9a2  mov     qword ptr [rbp+57h+pTaskConfig.7Ch], 0
0x14001d9aa  mov     [rbp+57h+pTaskConfig.pszFooter], 0
0x14001d9b2  mov     [rbp+57h+pTaskConfig.pfCallback], 0
0x14001d9ba  mov     [rbp+57h+pTaskConfig.lpCallbackData], 0
0x14001d9c2  call    cs:__imp_GetDialogBaseUnits
0x14001d9c9  nop     dword ptr [rax+rax+00h]
0x14001d9ce  movzx   r8d, ax; nDenominator
0x14001d9d2  mov     edx, 4; nNumerator
0x14001d9d7  mov     ecx, 206h; nNumber
0x14001d9dc  call    cs:__imp_MulDiv
0x14001d9e3  nop     dword ptr [rax+rax+00h]
0x14001d9e8  xor     r9d, r9d; pfVerificationFlagChecked
0x14001d9eb  lea     rdx, [rbp+57h+pnButton]; pnButton
0x14001d9ef  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x14001d9f3  mov     [rbp+57h+pTaskConfig.cxWidth], eax
0x14001d9f6  xor     r8d, r8d; pnRadioButton
0x14001d9f9  call    cs:__imp_TaskDialogIndirect
0x14001da00  nop     dword ptr [rax+rax+00h]
0x14001da05  test    eax, eax
0x14001da07  js      short loc_14001DA1B
0x14001da09  cmp     [rbp+57h+pnButton], ebx
0x14001da0c  jnz     short loc_14001DA1B
0x14001da0e  mov     edx, 801Eh
0x14001da13  mov     r9d, 3
0x14001da19  jmp     short loc_14001DA22
0x14001da1b  xor     r9d, r9d; lParam
0x14001da1e  lea     edx, [r9+10h]; Msg
0x14001da22  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001da29  xor     r8d, r8d; wParam
0x14001da2c  mov     rcx, [rcx+50h]; hWnd
0x14001da30  call    cs:__imp_PostMessageW
0x14001da37  nop     dword ptr [rax+rax+00h]
0x14001da3c  lea     r11, [rsp+0D0h+var_s0]
0x14001da44  mov     rbx, [r11+18h]
0x14001da48  mov     rdi, [r11+20h]
0x14001da4c  mov     rsp, r11
0x14001da4f  pop     rbp
0x14001da50  retn
```
