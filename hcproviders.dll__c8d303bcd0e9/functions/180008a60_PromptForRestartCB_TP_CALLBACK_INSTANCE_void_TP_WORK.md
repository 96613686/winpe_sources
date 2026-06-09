# PromptForRestartCB(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180008a60`
- end: `0x180008be3`
- name: `?PromptForRestartCB@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `387`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004fbc`
- `0x180008a60`
- `0x180008dc4`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b67`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008a7e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008a7e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008b91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008b91`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x180008b21`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x180008b21`
- `USER32!ExitWindowsEx` at `0x180008b57`
- `USER32!ExitWindowsEx` at `0x180008b57`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180008bbd`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180008bbd`

## pseudocode

```c
void __fastcall PromptForRestartCB(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  const unsigned __int16 *v4; // rcx
  int v5; // ebx
  int v6; // esi
  const unsigned __int16 *v7; // rcx
  signed int LastError; // eax
  int v9; // [rsp+30h] [rbp-79h] BYREF
  __int64 v10; // [rsp+34h] [rbp-75h]
  int v11; // [rsp+3Ch] [rbp-6Dh]
  __int64 v12; // [rsp+40h] [rbp-69h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-59h] BYREF
  int pnButton; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned int v15; // [rsp+128h] [rbp+7Fh] BYREF

  if ( CoInitializeEx(0, 6u) < 0 )
    goto LABEL_10;
  v10 = 200;
  v9 = 1;
  v11 = 2;
  v12 = 201;
  pTaskConfig.cbSize = 160;
  memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
  pTaskConfig.hwndParent = *(HWND *)Context;
  pTaskConfig.hInstance = g_hinst;
  pTaskConfig.dwFlags = 8;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v9;
  pTaskConfig.pszMainInstruction = (PCWSTR)*((_QWORD *)Context + 1);
  pTaskConfig.cButtons = 2;
  pTaskConfig.nDefaultButton = 1;
  pTaskConfig.pszWindowTitle = (PCWSTR)202;
  pTaskConfig.pszContent = (PCWSTR)205;
  pnButton = 0;
  v5 = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
  if ( v5 >= 0 && pnButton == 1 )
  {
    v15 = 0;
    v6 = SetPrivilegeAttribute(v4, 2u, &v15);
    if ( !ExitWindowsEx(0x42u, 0x20004u) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( !v6 )
      SetPrivilegeAttribute(v7, v15, 0);
  }
  CoUninitialize();
  if ( v5 < 0 )
LABEL_10:
    ShellMessageBoxW(g_hinst, *(HWND *)Context, (LPCWSTR)0xCE, (LPCWSTR)0xCA, 0x10u);
  operator delete(Context);
}

```

## disassembly

```asm
0x180008a60  mov     [rsp-8+arg_0], rbx
0x180008a65  push    rbp
0x180008a66  push    rsi
0x180008a67  push    rdi
0x180008a68  lea     rbp, [rsp-47h]
0x180008a6d  sub     rsp, 0F0h
0x180008a74  mov     rdi, rdx
0x180008a77  xor     ecx, ecx; pvReserved
0x180008a79  mov     edx, 6; dwCoInit
0x180008a7e  call    cs:__imp_CoInitializeEx
0x180008a85  nop     dword ptr [rax+rax+00h]
0x180008a8a  test    eax, eax
0x180008a8c  js      loc_180008BA1
0x180008a92  mov     esi, 1
0x180008a97  mov     [rbp+57h+var_CC], 0C8h
0x180008a9f  xor     edx, edx; Val
0x180008aa1  mov     [rbp+57h+var_D0], esi
0x180008aa4  mov     r8d, 9Ch; Size
0x180008aaa  mov     [rbp+57h+var_C4], 2
0x180008ab1  lea     rcx, [rbp+57h+pTaskConfig.hwndParent]; void *
0x180008ab5  mov     [rbp+57h+var_C0], 0C9h
0x180008abd  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x180008ac4  call    memset_0
0x180008ac9  mov     rax, [rdi]
0x180008acc  lea     rdx, [rbp+57h+pnButton]; pnButton
0x180008ad0  mov     [rbp+57h+pTaskConfig.hwndParent], rax
0x180008ad4  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x180008ad8  mov     rax, cs:g_hinst
0x180008adf  xor     r9d, r9d; pfVerificationFlagChecked
0x180008ae2  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x180008ae6  xor     r8d, r8d; pnRadioButton
0x180008ae9  lea     rax, [rbp+57h+var_D0]
0x180008aed  mov     [rbp+57h+pTaskConfig.dwFlags], 8
0x180008af4  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x180008af8  mov     rax, [rdi+8]
0x180008afc  mov     [rbp+57h+pTaskConfig.pszMainInstruction], rax
0x180008b00  mov     [rbp+57h+pTaskConfig.cButtons], 2
0x180008b07  mov     [rbp+57h+pTaskConfig.nDefaultButton], esi
0x180008b0a  mov     [rbp+57h+pTaskConfig.pszWindowTitle], 0CAh
0x180008b12  mov     [rbp+57h+pTaskConfig.pszContent], 0CDh
0x180008b1a  mov     [rbp+57h+pnButton], 0
0x180008b21  call    cs:__imp_TaskDialogIndirect
0x180008b28  nop     dword ptr [rax+rax+00h]
0x180008b2d  mov     ebx, eax
0x180008b2f  test    eax, eax
0x180008b31  js      short loc_180008B91
0x180008b33  cmp     [rbp+57h+pnButton], esi
0x180008b36  jnz     short loc_180008B91
0x180008b38  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x180008b3c  mov     [rbp+57h+arg_18], 0
0x180008b43  lea     edx, [rsi+1]; unsigned int
0x180008b46  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x180008b4b  mov     edx, 20004h; dwReason
0x180008b50  mov     ecx, 42h ; 'B'; uFlags
0x180008b55  mov     esi, eax
0x180008b57  call    cs:__imp_ExitWindowsEx
0x180008b5e  nop     dword ptr [rax+rax+00h]
0x180008b63  test    eax, eax
0x180008b65  jnz     short loc_180008B82
0x180008b67  call    cs:__imp_GetLastError
0x180008b6e  nop     dword ptr [rax+rax+00h]
0x180008b73  mov     ebx, eax
0x180008b75  test    eax, eax
0x180008b77  jle     short loc_180008B82
0x180008b79  movzx   ebx, ax
0x180008b7c  or      ebx, 80070000h
0x180008b82  test    esi, esi
0x180008b84  jnz     short loc_180008B91
0x180008b86  mov     edx, [rbp+57h+arg_18]; unsigned int
0x180008b89  xor     r8d, r8d; unsigned int *
0x180008b8c  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x180008b91  call    cs:__imp_CoUninitialize
0x180008b98  nop     dword ptr [rax+rax+00h]
0x180008b9d  test    ebx, ebx
0x180008b9f  jns     short loc_180008BC9
0x180008ba1  mov     rdx, [rdi]; hWnd
0x180008ba4  mov     r9d, 0CAh; lpcTitle
0x180008baa  mov     rcx, cs:g_hinst; hAppInst
0x180008bb1  mov     [rsp+100h+fuStyle], 10h; fuStyle
0x180008bb9  lea     r8d, [r9+4]; lpcText
0x180008bbd  call    cs:__imp_ShellMessageBoxW
0x180008bc4  nop     dword ptr [rax+rax+00h]
0x180008bc9  mov     rcx, rdi; Block
0x180008bcc  mov     rbx, [rsp+100h+arg_0]
0x180008bd4  add     rsp, 0F0h
0x180008bdb  pop     rdi
0x180008bdc  pop     rsi
0x180008bdd  pop     rbp
0x180008bde  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
