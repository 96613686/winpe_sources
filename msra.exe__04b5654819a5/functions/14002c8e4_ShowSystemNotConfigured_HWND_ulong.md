# ShowSystemNotConfigured(HWND__ *,ulong)

- ea: `0x14002c8e4`
- end: `0x14002ca1f`
- name: `?ShowSystemNotConfigured@@YAJPEAUHWND__@@K@Z`
- size: `315`
- prototype: `__int64 __fastcall(HWND, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e8b8`

## callees

- `0x14002c8e4`
- `0x140034ce4`

## import_xrefs

- `USER32!MessageBeep` at `0x14002c9af`
- `USER32!MessageBeep` at `0x14002c9af`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c9cb`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14002c9cb`

## string_xrefs

- `0x14002c9df`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002c9e6`: `ShowSystemNotConfigured`

## pseudocode

```c
__int64 __fastcall ShowSystemNotConfigured(HWND a1)
{
  HINSTANCE v1; // rcx
  HRESULT v2; // eax
  CEventLogger *v3; // rcx
  int v5; // [rsp+38h] [rbp-69h] BYREF
  __int64 v6; // [rsp+3Ch] [rbp-65h]
  int v7; // [rsp+44h] [rbp-5Dh]
  __int64 v8; // [rsp+48h] [rbp-59h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+58h] [rbp-49h] BYREF
  int pnRadioButton; // [rsp+108h] [rbp+67h] BYREF
  int v11; // [rsp+10Ch] [rbp+6Bh]
  BOOL pfVerificationFlagChecked; // [rsp+110h] [rbp+6Fh] BYREF
  int pnButton; // [rsp+118h] [rbp+77h] BYREF

  v11 = HIDWORD(a1);
  v6 = 617;
  pnButton = 0;
  pTaskConfig.cxWidth = 0;
  memset(&pTaskConfig.cRadioButtons, 0, 64);
  pfVerificationFlagChecked = 0;
  pnRadioButton = 0;
  v7 = 2;
  v8 = 705;
  v5 = 1080;
  v1 = (HINSTANCE)*((_QWORD *)_AtlModule + 76);
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v5;
  pTaskConfig.hInstance = v1;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)SystemSettingsSayNoCallbackProc;
  pTaskConfig.cbSize = 160;
  pTaskConfig.hwndParent = 0;
  *(_QWORD *)&pTaskConfig.dwFlags = 8;
  pTaskConfig.pszWindowTitle = (PCWSTR)100;
  pTaskConfig.hMainIcon = 0;
  pTaskConfig.pszMainInstruction = (PCWSTR)623;
  pTaskConfig.pszContent = (PCWSTR)680;
  pTaskConfig.cButtons = 2;
  pTaskConfig.nDefaultButton = 1;
  pTaskConfig.lpCallbackData = 0;
  MessageBeep(0xFFFFFFFF);
  v2 = TaskDialogIndirect(&pTaskConfig, &pnButton, &pnRadioButton, &pfVerificationFlagChecked);
  if ( v2 >= 0 )
    return 0;
  CEventLogger::LogError(
    v3,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0xE0Bu,
    L"ShowSystemNotConfigured",
    v2);
  return 2147500037LL;
}

```

## disassembly

```asm
0x14002c8e4  mov     rax, rsp
0x14002c8e7  mov     [rax+20h], rbx
0x14002c8eb  mov     [rax+10h], edx
0x14002c8ee  mov     [rax+8], rcx
0x14002c8f2  push    rbp
0x14002c8f3  lea     rbp, [rax-5Fh]
0x14002c8f7  sub     rsp, 0F0h
0x14002c8fe  xor     ebx, ebx
0x14002c900  mov     [rbp+57h+var_BC], 269h
0x14002c908  xor     eax, eax
0x14002c90a  mov     [rbp+57h+pnButton], ebx
0x14002c90d  mov     [rbp+57h+pTaskConfig.cxWidth], eax
0x14002c910  xorps   xmm0, xmm0
0x14002c913  movups  xmmword ptr [rbp+57h+pTaskConfig.cRadioButtons], xmm0
0x14002c917  mov     [rbp+57h+pfVerificationFlagChecked], ebx
0x14002c91a  lea     edx, [rax+2]
0x14002c91d  mov     [rbp+57h+pnRadioButton], ebx
0x14002c920  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c927  mov     [rbp+57h+var_B4], edx
0x14002c92a  mov     [rbp+57h+var_B0], 2C1h
0x14002c932  mov     [rbp+57h+var_C0], 438h
0x14002c939  mov     rcx, [rax+260h]
0x14002c940  lea     rax, [rbp+57h+var_C0]
0x14002c944  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x14002c948  lea     rax, ?SystemSettingsSayNoCallbackProc@@YAJPEAUHWND__@@I_K_J2@Z; SystemSettingsSayNoCallbackProc(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14002c94f  mov     [rbp+57h+pTaskConfig.hInstance], rcx
0x14002c953  or      ecx, 0FFFFFFFFh; uType
0x14002c956  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x14002c95a  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x14002c961  mov     [rbp+57h+pTaskConfig.hwndParent], rbx
0x14002c965  mov     qword ptr [rbp+57h+pTaskConfig.dwFlags], 8
0x14002c96d  mov     [rbp+57h+pTaskConfig.pszWindowTitle], 64h ; 'd'
0x14002c975  mov     qword ptr [rbp+57h+pTaskConfig.24h], rbx
0x14002c979  mov     [rbp+57h+pTaskConfig.pszMainInstruction], 26Fh
0x14002c981  mov     [rbp+57h+pTaskConfig.pszContent], 2A8h
0x14002c989  mov     [rbp+57h+pTaskConfig.cButtons], edx
0x14002c98c  mov     [rbp+57h+pTaskConfig.nDefaultButton], 1
0x14002c993  mov     [rbp+57h+pTaskConfig.pszVerificationText], rbx
0x14002c997  mov     [rbp+57h+pTaskConfig.pszExpandedInformation], rbx
0x14002c99b  mov     [rbp+57h+pTaskConfig.pszExpandedControlText], rbx
0x14002c99f  mov     [rbp+57h+pTaskConfig.pszCollapsedControlText], rbx
0x14002c9a3  mov     qword ptr [rbp+57h+pTaskConfig.7Ch], rbx
0x14002c9a7  mov     [rbp+57h+pTaskConfig.pszFooter], rbx
0x14002c9ab  mov     [rbp+57h+pTaskConfig.lpCallbackData], rbx
0x14002c9af  call    cs:__imp_MessageBeep
0x14002c9b6  nop     dword ptr [rax+rax+00h]
0x14002c9bb  lea     r9, [rbp+57h+pfVerificationFlagChecked]; pfVerificationFlagChecked
0x14002c9bf  lea     r8, [rbp+57h+pnRadioButton]; pnRadioButton
0x14002c9c3  lea     rdx, [rbp+57h+pnButton]; pnButton
0x14002c9c7  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x14002c9cb  call    cs:__imp_TaskDialogIndirect
0x14002c9d2  nop     dword ptr [rax+rax+00h]
0x14002c9d7  test    eax, eax
0x14002c9d9  jns     short loc_14002CA0B
0x14002c9db  mov     [rsp+28h], eax; unsigned int
0x14002c9df  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002c9e6  lea     rax, aShowsystemnotc; "ShowSystemNotConfigured"
0x14002c9ed  mov     r9d, 0E0Bh; unsigned int
0x14002c9f3  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002c9fa  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x14002c9ff  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002ca04  mov     eax, 80004005h
0x14002ca09  jmp     short loc_14002CA0D
0x14002ca0b  xor     eax, eax
0x14002ca0d  mov     rbx, [rsp+0F0h+arg_18]
0x14002ca15  add     rsp, 0F0h
0x14002ca1c  pop     rbp
0x14002ca1d  retn
```
