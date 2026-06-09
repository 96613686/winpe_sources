# CSNOCplCore::OnStartNetprofmDlg(void)

- ea: `0x18000e564`
- end: `0x18000e70e`
- name: `?OnStartNetprofmDlg@CSNOCplCore@@AEAAXXZ`
- size: `426`
- prototype: `void __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d2e4`

## callees

- `0x180002c2c`
- `0x1800090f4`
- `0x18000ae44`
- `0x18000e564`
- `0x1800126b0`
- `0x18001b77c`
- `0x18001e7c4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e6d3`

## pseudocode

```c
void __fastcall CSNOCplCore::OnStartNetprofmDlg(CSNOCplCore *this, __int64 a2, __int64 a3)
{
  signed int v4; // ebx
  HWND ParentWindow; // rax
  void *v6; // rsi
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // r15
  HWND v9; // rax
  const struct _GUID *v10; // rdx
  const struct _GUID *v11; // r8
  HWND v12; // rax
  int v13; // [rsp+30h] [rbp-89h] BYREF
  __int64 v14; // [rsp+34h] [rbp-85h]
  unsigned __int16 *v15; // [rsp+40h] [rbp-79h] BYREF
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-69h] BYREF
  int pnButton; // [rsp+128h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+130h] [rbp+77h] BYREF
  unsigned __int16 *v19; // [rsp+138h] [rbp+7Fh] BYREF

  pv = 0;
  v19 = 0;
  v15 = 0;
  v4 = HrFormatTaskDlgMessage((unsigned __int16 *)this, a2, a3, &pv, &v19, &v15);
  if ( v4 < 0 )
    goto LABEL_8;
  memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
  pTaskConfig.cbSize = 160;
  ParentWindow = CSNOCplCore::GetParentWindow(this);
  v6 = pv;
  v7 = v19;
  v8 = v15;
  pTaskConfig.hwndParent = ParentWindow;
  pTaskConfig.hInstance = g_hinst;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)NetprofmDialogCallback;
  pTaskConfig.dwFlags = 8;
  pTaskConfig.dwCommonButtons = 8;
  pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v13;
  pTaskConfig.pszWindowTitle = (PCWSTR)pv;
  pTaskConfig.pszMainInstruction = v19;
  pTaskConfig.pszContent = v15;
  pTaskConfig.cxWidth = 200;
  v13 = 501;
  v14 = 58;
  pTaskConfig.cButtons = 1;
  pnButton = 0;
  v4 = TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
  if ( v4 >= 0 && pnButton == 501 )
  {
    pv = 0;
    v9 = CSNOCplCore::GetParentWindow(this);
    v4 = CoCreateInstanceAsAdmin(v9, v10, v11, &pv);
    if ( v4 >= 0 )
    {
      if ( pv )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)pv + 56LL))(pv);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
      }
    }
  }
  CoTaskMemFree(v6);
  CoTaskMemFree(v7);
  CoTaskMemFree(v8);
  if ( v4 < 0 )
  {
LABEL_8:
    if ( v4 != -2147023673 )
    {
      v12 = CSNOCplCore::GetParentWindow(this);
      ThrowErrorBox(v12, v4);
    }
  }
}

```

## disassembly

```asm
0x18000e564  mov     [rsp-8+arg_0], rbx
0x18000e569  push    rbp
0x18000e56a  push    rsi
0x18000e56b  push    rdi
0x18000e56c  push    r14
0x18000e56e  push    r15
0x18000e570  lea     rbp, [rsp-37h]
0x18000e575  sub     rsp, 0F0h
0x18000e57c  lea     rax, [rbp+57h+var_D0]
0x18000e580  mov     [rbp+57h+pv], 0
0x18000e588  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x18000e58d  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x18000e591  lea     rax, [rbp+57h+arg_18]
0x18000e595  mov     [rbp+57h+arg_18], 0
0x18000e59d  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x18000e5a2  mov     rdi, rcx
0x18000e5a5  mov     [rbp+57h+var_D0], 0
0x18000e5ad  call    ?HrFormatTaskDlgMessage@@YAJQEAUHINSTANCE__@@IIPEAPEAG11@Z; HrFormatTaskDlgMessage(HINSTANCE__ * const,uint,uint,ushort * *,ushort * *,ushort * *)
0x18000e5b2  mov     ebx, eax
0x18000e5b4  test    eax, eax
0x18000e5b6  js      loc_18000E6DD
0x18000e5bc  xor     edx, edx; Val
0x18000e5be  lea     rcx, [rbp+57h+pTaskConfig.hwndParent]; void *
0x18000e5c2  mov     r8d, 9Ch; Size
0x18000e5c8  call    memset_0
0x18000e5cd  xor     eax, eax
0x18000e5cf  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x18000e5d6  mov     rcx, rdi; this
0x18000e5d9  mov     [rsp+110h+var_E0], rax
0x18000e5de  mov     [rsp+110h+var_D8], eax
0x18000e5e2  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000e5e7  mov     rsi, [rbp+57h+pv]
0x18000e5eb  lea     rdx, [rbp+57h+pnButton]; pnButton
0x18000e5ef  mov     r14, [rbp+57h+arg_18]
0x18000e5f3  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x18000e5f7  mov     r15, [rbp+57h+var_D0]
0x18000e5fb  xor     r9d, r9d; pfVerificationFlagChecked
0x18000e5fe  mov     [rbp+57h+pTaskConfig.hwndParent], rax
0x18000e602  xor     r8d, r8d; pnRadioButton
0x18000e605  mov     rax, cs:g_hinst
0x18000e60c  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x18000e610  lea     rax, ?NetprofmDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z; NetprofmDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x18000e617  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x18000e61b  mov     eax, 8
0x18000e620  mov     [rbp+57h+pTaskConfig.dwFlags], eax
0x18000e623  mov     [rbp+57h+pTaskConfig.dwCommonButtons], eax
0x18000e626  lea     rax, [rsp+110h+var_E0]
0x18000e62b  mov     [rbp+57h+pTaskConfig.pButtons], rax
0x18000e62f  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rsi
0x18000e633  mov     [rbp+57h+pTaskConfig.pszMainInstruction], r14
0x18000e637  mov     [rbp+57h+pTaskConfig.pszContent], r15
0x18000e63b  mov     [rbp+57h+pTaskConfig.cxWidth], 0C8h
0x18000e642  mov     dword ptr [rsp+110h+var_E0], 1F5h
0x18000e64a  mov     [rsp+110h+var_E0+4], 3Ah ; ':'
0x18000e653  mov     [rbp+57h+pTaskConfig.cButtons], 1
0x18000e65a  mov     [rbp+57h+pnButton], 0
0x18000e661  call    TaskDialogIndirect
0x18000e666  mov     ebx, eax
0x18000e668  test    eax, eax
0x18000e66a  js      short loc_18000E6BE
0x18000e66c  cmp     [rbp+57h+pnButton], 1F5h
0x18000e673  jnz     short loc_18000E6BE
0x18000e675  mov     rcx, rdi; this
0x18000e678  mov     [rbp+57h+pv], 0
0x18000e680  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000e685  lea     r9, [rbp+57h+pv]; void **
0x18000e689  mov     rcx, rax; HWND
0x18000e68c  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000e691  mov     ebx, eax
0x18000e693  test    eax, eax
0x18000e695  js      short loc_18000E6BE
0x18000e697  mov     rcx, [rbp+57h+pv]
0x18000e69b  test    rcx, rcx
0x18000e69e  jz      short loc_18000E6BE
0x18000e6a0  mov     rax, [rcx]
0x18000e6a3  mov     rax, [rax+38h]
0x18000e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ac  mov     rcx, [rbp+57h+pv]
0x18000e6b0  mov     ebx, eax
0x18000e6b2  mov     rax, [rcx]
0x18000e6b5  mov     rax, [rax+10h]
0x18000e6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6be  mov     rcx, rsi; pv
0x18000e6c1  call    cs:__imp_CoTaskMemFree
0x18000e6c7  mov     rcx, r14; pv
0x18000e6ca  call    cs:__imp_CoTaskMemFree
0x18000e6d0  mov     rcx, r15; pv
0x18000e6d3  call    cs:__imp_CoTaskMemFree
0x18000e6d9  test    ebx, ebx
0x18000e6db  jns     short loc_18000E6F7
0x18000e6dd  cmp     ebx, 800704C7h
0x18000e6e3  jz      short loc_18000E6F7
0x18000e6e5  mov     rcx, rdi; this
0x18000e6e8  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000e6ed  mov     rcx, rax; hWnd
0x18000e6f0  mov     edx, ebx; dwMessageId
0x18000e6f2  call    ?ThrowErrorBox@@YAXQEAUHWND__@@J@Z; ThrowErrorBox(HWND__ * const,long)
0x18000e6f7  mov     rbx, [rsp+110h+arg_0]
0x18000e6ff  add     rsp, 0F0h
0x18000e706  pop     r15
0x18000e708  pop     r14
0x18000e70a  pop     rdi
0x18000e70b  pop     rsi
0x18000e70c  pop     rbp
0x18000e70d  retn
```
