# MoreOptionsDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x14000de50`
- end: `0x14000e05b`
- name: `?MoreOptionsDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `523`
- prototype: `__int64 __fastcall(HWND hDlg, int, __int16, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x14000c678`
- `0x14000de50`
- `0x14000e0ec`

## import_xrefs

- `USER32!ShowWindow` at `0x14000dffd`
- `USER32!ShowWindow` at `0x14000dffd`
- `USER32!LoadStringW` at `0x14000deed`
- `USER32!LoadStringW` at `0x14000deed`
- `USER32!EnableWindow` at `0x14000dfe4`
- `USER32!EnableWindow` at `0x14000e016`
- `USER32!EnableWindow` at `0x14000e02f`
- `USER32!EnableWindow` at `0x14000dfe4`
- `USER32!EnableWindow` at `0x14000e016`
- `USER32!EnableWindow` at `0x14000e02f`
- `USER32!GetDlgItem` at `0x14000dfd9`
- `USER32!GetDlgItem` at `0x14000dff2`
- `USER32!GetDlgItem` at `0x14000e00b`
- `USER32!GetDlgItem` at `0x14000e024`
- `USER32!GetDlgItem` at `0x14000dfd9`
- `USER32!GetDlgItem` at `0x14000dff2`
- `USER32!GetDlgItem` at `0x14000e00b`
- `USER32!GetDlgItem` at `0x14000e024`
- `USER32!SetWindowLongPtrW` at `0x14000dfa6`
- `USER32!SetWindowLongPtrW` at `0x14000dfa6`
- `USER32!GetWindowLongPtrW` at `0x14000deac`
- `USER32!GetWindowLongPtrW` at `0x14000deac`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14000df68`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14000df68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000dfbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000dfbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000dfc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000dfc9`

## string_xrefs

- `0x14000dfae`: `srclient.dll`

## pseudocode

```c
__int64 __fastcall MoreOptionsDlgProc(HWND hDlg, int a2, __int16 a3, __int64 a4)
{
  int v5; // edx
  LONG_PTR WindowLongPtrW; // rdi
  LONG_PTR v7; // r8
  HMODULE Library; // rax
  HWND DlgItem; // rax
  HWND v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  int pnButton; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR *v16; // [rsp+2Ch] [rbp-D4h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[40]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = a2 - 272;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      if ( a3 == 1025 )
      {
        OpenProgramsAndFeaturesCPL();
      }
      else if ( a3 == 1030 )
      {
        WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
        if ( WindowLongPtrW )
        {
          pnButton = 0;
          memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
          LoadStringW(g_hInstance, 0x1Au, Buffer, 40);
          v15 = 1;
          v16 = Buffer;
          pTaskConfig.hInstance = g_hInstance;
          pTaskConfig.cbSize = 160;
          pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v15;
          pTaskConfig.hwndParent = hDlg;
          pTaskConfig.dwCommonButtons = 8;
          pTaskConfig.pszWindowTitle = (PCWSTR)22;
          pTaskConfig.pszMainInstruction = (PCWSTR)24;
          pTaskConfig.pszContent = (PCWSTR)25;
          pTaskConfig.cButtons = 1;
          pTaskConfig.nDefaultButton = 1;
          TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
          if ( pnButton == 1 )
            DeleteSystemRestorePoints((LPCWSTR)(WindowLongPtrW + 16));
        }
      }
      return 1;
    }
    return 0;
  }
  v7 = *(_QWORD *)(a4 + 48);
  if ( !v7 )
    return 0;
  SetWindowLongPtrW(hDlg, 16, v7);
  Library = LoadLibraryExW(L"srclient.dll", 0, 0x801u);
  if ( Library )
  {
    FreeLibrary(Library);
  }
  else
  {
    DlgItem = GetDlgItem(hDlg, 1027);
    EnableWindow(DlgItem, 0);
    v11 = GetDlgItem(hDlg, 1028);
    ShowWindow(v11, 0);
    v12 = GetDlgItem(hDlg, 1029);
    EnableWindow(v12, 0);
    v13 = GetDlgItem(hDlg, 1030);
    EnableWindow(v13, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x14000de50  mov     [rsp-8+arg_8], rbx
0x14000de55  mov     [rsp-8+arg_10], rdi
0x14000de5a  push    rbp
0x14000de5b  lea     rbp, [rsp-40h]
0x14000de60  sub     rsp, 140h
0x14000de67  mov     rax, cs:__security_cookie
0x14000de6e  xor     rax, rsp
0x14000de71  mov     [rbp+40h+var_10], rax
0x14000de75  mov     rbx, rcx
0x14000de78  sub     edx, 110h
0x14000de7e  jz      loc_14000DF91
0x14000de84  cmp     edx, 1
0x14000de87  jnz     loc_14000DF9A
0x14000de8d  movzx   ecx, r8w
0x14000de91  sub     ecx, 401h
0x14000de97  jz      loc_14000DF87
0x14000de9d  cmp     ecx, 5
0x14000dea0  jnz     loc_14000E035
0x14000dea6  lea     edx, [rcx+0Bh]; nIndex
0x14000dea9  mov     rcx, rbx; hWnd
0x14000deac  call    cs:__imp_GetWindowLongPtrW
0x14000deb2  mov     rdi, rax
0x14000deb5  test    rax, rax
0x14000deb8  jz      loc_14000E035
0x14000debe  xor     edx, edx; Val
0x14000dec0  mov     [rsp+140h+pnButton], 0
0x14000dec8  mov     r8d, 0A0h; Size
0x14000dece  lea     rcx, [rsp+140h+pTaskConfig]; void *
0x14000ded3  call    memset_0
0x14000ded8  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14000dedf  lea     r8, [rbp+40h+Buffer]; lpBuffer
0x14000dee3  mov     r9d, 28h ; '('; cchBufferMax
0x14000dee9  lea     edx, [r9-0Eh]; uID
0x14000deed  call    cs:__imp_LoadStringW
0x14000def3  lea     rax, [rbp+40h+Buffer]
0x14000def7  mov     [rsp+140h+var_118], 1
0x14000deff  mov     [rsp+140h+var_114], rax
0x14000df04  lea     rdx, [rsp+140h+pnButton]; pnButton
0x14000df09  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14000df10  lea     rcx, [rsp+140h+pTaskConfig]; pTaskConfig
0x14000df15  mov     [rsp+140h+pTaskConfig.hInstance], rax
0x14000df1a  xor     r9d, r9d; pfVerificationFlagChecked
0x14000df1d  lea     rax, [rsp+140h+var_118]
0x14000df22  mov     [rsp+140h+pTaskConfig.cbSize], 0A0h
0x14000df2a  xor     r8d, r8d; pnRadioButton
0x14000df2d  mov     [rbp+40h+pTaskConfig.pButtons], rax
0x14000df31  mov     [rsp+140h+pTaskConfig.hwndParent], rbx
0x14000df36  mov     [rsp+140h+pTaskConfig.dwCommonButtons], 8
0x14000df3e  mov     [rsp+140h+pTaskConfig.pszWindowTitle], 16h
0x14000df47  mov     [rsp+140h+pTaskConfig.pszMainInstruction], 18h
0x14000df50  mov     [rsp+140h+pTaskConfig.pszContent], 19h
0x14000df59  mov     [rsp+140h+pTaskConfig.cButtons], 1
0x14000df61  mov     [rbp+40h+pTaskConfig.nDefaultButton], 1
0x14000df68  call    cs:__imp_TaskDialogIndirect
0x14000df6e  cmp     [rsp+140h+pnButton], 1
0x14000df73  jnz     loc_14000E035
0x14000df79  lea     rcx, [rdi+10h]; lpszVolumeMountPoint
0x14000df7d  call    ?DeleteSystemRestorePoints@@YAXPEBG@Z; DeleteSystemRestorePoints(ushort const *)
0x14000df82  jmp     loc_14000E035
0x14000df87  call    ?OpenProgramsAndFeaturesCPL@@YAXXZ; OpenProgramsAndFeaturesCPL(void)
0x14000df8c  jmp     loc_14000E035
0x14000df91  mov     r8, [r9+30h]; dwNewLong
0x14000df95  test    r8, r8
0x14000df98  jnz     short loc_14000DFA1
0x14000df9a  xor     eax, eax
0x14000df9c  jmp     loc_14000E03A
0x14000dfa1  mov     edx, 10h; nIndex
0x14000dfa6  call    cs:__imp_SetWindowLongPtrW
0x14000dfac  xor     edx, edx; hFile
0x14000dfae  lea     rcx, LibFileName; "srclient.dll"
0x14000dfb5  mov     r8d, 801h; dwFlags
0x14000dfbb  call    cs:__imp_LoadLibraryExW
0x14000dfc1  test    rax, rax
0x14000dfc4  jz      short loc_14000DFD1
0x14000dfc6  mov     rcx, rax; hLibModule
0x14000dfc9  call    cs:__imp_FreeLibrary
0x14000dfcf  jmp     short loc_14000E035
0x14000dfd1  mov     edx, 403h; nIDDlgItem
0x14000dfd6  mov     rcx, rbx; hDlg
0x14000dfd9  call    cs:__imp_GetDlgItem
0x14000dfdf  mov     rcx, rax; hWnd
0x14000dfe2  xor     edx, edx; bEnable
0x14000dfe4  call    cs:__imp_EnableWindow
0x14000dfea  mov     edx, 404h; nIDDlgItem
0x14000dfef  mov     rcx, rbx; hDlg
0x14000dff2  call    cs:__imp_GetDlgItem
0x14000dff8  mov     rcx, rax; hWnd
0x14000dffb  xor     edx, edx; nCmdShow
0x14000dffd  call    cs:__imp_ShowWindow
0x14000e003  mov     edx, 405h; nIDDlgItem
0x14000e008  mov     rcx, rbx; hDlg
0x14000e00b  call    cs:__imp_GetDlgItem
0x14000e011  mov     rcx, rax; hWnd
0x14000e014  xor     edx, edx; bEnable
0x14000e016  call    cs:__imp_EnableWindow
0x14000e01c  mov     edx, 406h; nIDDlgItem
0x14000e021  mov     rcx, rbx; hDlg
0x14000e024  call    cs:__imp_GetDlgItem
0x14000e02a  mov     rcx, rax; hWnd
0x14000e02d  xor     edx, edx; bEnable
0x14000e02f  call    cs:__imp_EnableWindow
0x14000e035  mov     eax, 1
0x14000e03a  mov     rcx, [rbp+40h+var_10]
0x14000e03e  xor     rcx, rsp; StackCookie
0x14000e041  call    __security_check_cookie
0x14000e046  lea     r11, [rsp+140h+var_s0]
0x14000e04e  mov     rbx, [r11+18h]
0x14000e052  mov     rdi, [r11+20h]
0x14000e056  mov     rsp, r11
0x14000e059  pop     rbp
0x14000e05a  retn
```
