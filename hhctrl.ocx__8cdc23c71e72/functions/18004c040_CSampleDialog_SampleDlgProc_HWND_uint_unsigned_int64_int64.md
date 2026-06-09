# CSampleDialog::SampleDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004c040`
- end: `0x18004c95a`
- name: `?SampleDlgProc@CSampleDialog@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `2330`
- prototype: `__int64 __fastcall(CSampleDialog *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004bfc0`

## callees

- `0x180005a4c`
- `0x1800095c8`
- `0x18000f460`
- `0x180012b38`
- `0x180012c04`
- `0x1800439a0`
- `0x1800439ec`
- `0x1800496ac`
- `0x1800498dc`
- `0x18004a7d0`
- `0x18004c040`
- `0x18004cba0`
- `0x18004e6a8`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x18004c692`
- `KERNEL32!DeleteFileA` at `0x18004c704`
- `KERNEL32!DeleteFileA` at `0x18004c692`
- `KERNEL32!DeleteFileA` at `0x18004c704`
- `KERNEL32!GetTempPath2A` at `0x18004c4e3`
- `KERNEL32!GetTempPath2A` at `0x18004c4e3`
- `KERNEL32!CopyFileA` at `0x18004c762`
- `KERNEL32!CopyFileA` at `0x18004c762`
- `KERNEL32!WinExec` at `0x18004c793`
- `KERNEL32!WinExec` at `0x18004c793`
- `USER32!SendDlgItemMessageA` at `0x18004c161`
- `USER32!SendDlgItemMessageA` at `0x18004c7d8`
- `USER32!SendDlgItemMessageA` at `0x18004c810`
- `USER32!SendDlgItemMessageA` at `0x18004c83f`
- `USER32!SendDlgItemMessageA` at `0x18004c859`
- `USER32!SendDlgItemMessageA` at `0x18004c161`
- `USER32!SendDlgItemMessageA` at `0x18004c7d8`
- `USER32!SendDlgItemMessageA` at `0x18004c810`
- `USER32!SendDlgItemMessageA` at `0x18004c83f`
- `USER32!SendDlgItemMessageA` at `0x18004c859`
- `USER32!LoadStringA` at `0x18004c281`
- `USER32!LoadStringA` at `0x18004c328`
- `USER32!LoadStringA` at `0x18004c34b`
- `USER32!LoadStringA` at `0x18004c57e`
- `USER32!LoadStringA` at `0x18004c5a1`
- `USER32!LoadStringA` at `0x18004c72e`
- `USER32!LoadStringA` at `0x18004c74e`
- `USER32!LoadStringA` at `0x18004c281`
- `USER32!LoadStringA` at `0x18004c328`
- `USER32!LoadStringA` at `0x18004c34b`
- `USER32!LoadStringA` at `0x18004c57e`
- `USER32!LoadStringA` at `0x18004c5a1`
- `USER32!LoadStringA` at `0x18004c72e`
- `USER32!LoadStringA` at `0x18004c74e`
- `USER32!MessageBoxA` at `0x18004c365`
- `USER32!MessageBoxA` at `0x18004c5bb`
- `USER32!MessageBoxA` at `0x18004c365`
- `USER32!MessageBoxA` at `0x18004c5bb`
- `USER32!ShowScrollBar` at `0x18004c8ba`
- `USER32!ShowScrollBar` at `0x18004c8ba`
- `USER32!LoadStringW` at `0x18004c252`
- `USER32!LoadStringW` at `0x18004c2c9`
- `USER32!LoadStringW` at `0x18004c2ec`
- `USER32!LoadStringW` at `0x18004c533`
- `USER32!LoadStringW` at `0x18004c556`
- `USER32!LoadStringW` at `0x18004c6bc`
- `USER32!LoadStringW` at `0x18004c6dc`
- `USER32!LoadStringW` at `0x18004c252`
- `USER32!LoadStringW` at `0x18004c2c9`
- `USER32!LoadStringW` at `0x18004c2ec`
- `USER32!LoadStringW` at `0x18004c533`
- `USER32!LoadStringW` at `0x18004c556`
- `USER32!LoadStringW` at `0x18004c6bc`
- `USER32!LoadStringW` at `0x18004c6dc`
- `USER32!EndDialog` at `0x18004c7a3`
- `USER32!EndDialog` at `0x18004c7a3`
- `USER32!ReleaseDC` at `0x18004c8c6`
- `USER32!ReleaseDC` at `0x18004c8c6`
- `USER32!GetDC` at `0x18004c7f1`
- `USER32!GetDC` at `0x18004c7f1`
- `USER32!CharNextA` at `0x18004c636`
- `USER32!CharNextA` at `0x18004c636`
- `USER32!SetCursor` at `0x18004c90e`
- `USER32!SetCursor` at `0x18004c90e`
- `USER32!GetWindowRect` at `0x18004c7e8`
- `USER32!GetWindowRect` at `0x18004c7e8`
- `USER32!EnableWindow` at `0x18004c42e`
- `USER32!EnableWindow` at `0x18004c459`
- `USER32!EnableWindow` at `0x18004c8df`
- `USER32!EnableWindow` at `0x18004c8f8`
- `USER32!EnableWindow` at `0x18004c42e`
- `USER32!EnableWindow` at `0x18004c459`
- `USER32!EnableWindow` at `0x18004c8df`
- `USER32!EnableWindow` at `0x18004c8f8`
- `USER32!SendMessageA` at `0x18004c127`
- `USER32!SendMessageA` at `0x18004c178`
- `USER32!SendMessageA` at `0x18004c3b5`
- `USER32!SendMessageA` at `0x18004c3e1`
- `USER32!SendMessageA` at `0x18004c3f5`
- `USER32!SendMessageA` at `0x18004c4a5`
- `USER32!SendMessageA` at `0x18004c4d1`
- `USER32!SendMessageA` at `0x18004c4f7`
- `USER32!SendMessageA` at `0x18004c5d4`
- `USER32!SendMessageA` at `0x18004c8ad`
- `USER32!SendMessageA` at `0x18004c127`
- `USER32!SendMessageA` at `0x18004c178`
- `USER32!SendMessageA` at `0x18004c3b5`
- `USER32!SendMessageA` at `0x18004c3e1`
- `USER32!SendMessageA` at `0x18004c3f5`
- `USER32!SendMessageA` at `0x18004c4a5`
- `USER32!SendMessageA` at `0x18004c4d1`
- `USER32!SendMessageA` at `0x18004c4f7`
- `USER32!SendMessageA` at `0x18004c5d4`
- `USER32!SendMessageA` at `0x18004c8ad`
- `USER32!GetDlgItem` at `0x18004c093`
- `USER32!GetDlgItem` at `0x18004c40f`
- `USER32!GetDlgItem` at `0x18004c423`
- `USER32!GetDlgItem` at `0x18004c44e`
- `USER32!GetDlgItem` at `0x18004c464`
- `USER32!GetDlgItem` at `0x18004c8d4`
- `USER32!GetDlgItem` at `0x18004c8ed`
- `USER32!GetDlgItem` at `0x18004c093`
- `USER32!GetDlgItem` at `0x18004c40f`
- `USER32!GetDlgItem` at `0x18004c423`
- `USER32!GetDlgItem` at `0x18004c44e`
- `USER32!GetDlgItem` at `0x18004c464`
- `USER32!GetDlgItem` at `0x18004c8d4`
- `USER32!GetDlgItem` at `0x18004c8ed`
- `USER32!MessageBoxW` at `0x18004c306`
- `USER32!MessageBoxW` at `0x18004c6f9`
- `USER32!MessageBoxW` at `0x18004c306`
- `USER32!MessageBoxW` at `0x18004c6f9`
- `USER32!PostMessageA` at `0x18004c925`
- `USER32!PostMessageA` at `0x18004c925`
- `USER32!LoadCursorA` at `0x18004c905`
- `USER32!LoadCursorA` at `0x18004c905`
- `GDI32!GetTextExtentPoint32A` at `0x18004c877`
- `GDI32!GetTextExtentPoint32A` at `0x18004c877`

## pseudocode

```c
__int64 __fastcall CSampleDialog::SampleDlgProc(CSampleDialog *this, HWND a2, int a3, unsigned __int64 a4)
{
  CSampleDialog *v5; // r13
  HWND DlgItem; // rax
  CSampleDialog *v9; // rcx
  HWND v10; // r14
  int v11; // ebx
  int v12; // ebx
  int v14; // r12d
  unsigned int j; // r15d
  LRESULT v16; // rdi
  int v17; // eax
  HINSTANCE v18; // rax
  __int64 v19; // rax
  HINSTANCE v20; // rax
  __int64 v21; // rdi
  HINSTANCE v22; // rax
  HINSTANCE v23; // rax
  UINT v24; // edx
  HINSTANCE v25; // rax
  HINSTANCE v26; // rax
  UINT v27; // edx
  HINSTANCE v28; // rax
  HINSTANCE v29; // rax
  unsigned __int64 v30; // rdi
  signed int OneSel; // eax
  WPARAM v32; // rbx
  HWND v33; // rax
  BOOL v34; // edx
  HWND v35; // rax
  BOOL v36; // edx
  signed int v37; // eax
  WPARAM v38; // rbx
  int v39; // eax
  HINSTANCE ResourceInstance; // rax
  HINSTANCE v41; // rax
  UINT v42; // r9d
  HINSTANCE v43; // rax
  HINSTANCE v44; // rax
  UINT v45; // r9d
  const char **v46; // rbx
  const char *v47; // rbx
  LPSTR v48; // rcx
  CHAR i; // dl
  LPSTR v50; // rax
  HINSTANCE v51; // rax
  HINSTANCE v52; // rax
  HINSTANCE v53; // rax
  HINSTANCE v54; // rax
  int cx; // ebx
  HDC DC; // r15
  LPARAM *lParam; // rdi
  int v58; // eax
  const CHAR *v59; // rdx
  __int64 v60; // r8
  HWND v61; // rax
  HWND v62; // rax
  HCURSOR CursorA; // rax
  struct tagSIZE psizl; // [rsp+38h] [rbp-C8h] BYREF
  CSampleDialog *v65; // [rsp+40h] [rbp-C0h]
  LPARAM v66[257]; // [rsp+50h] [rbp-B0h] BYREF
  char v67; // [rsp+858h] [rbp+758h]
  struct tagRECT Rect; // [rsp+870h] [rbp+770h] BYREF
  CHAR Caption[272]; // [rsp+880h] [rbp+780h] BYREF
  CHAR v70[256]; // [rsp+990h] [rbp+890h] BYREF
  CHAR ExistingFileName[256]; // [rsp+A90h] [rbp+990h] BYREF
  WCHAR Text[256]; // [rsp+B90h] [rbp+A90h] BYREF
  WCHAR Buffer[264]; // [rsp+D90h] [rbp+C90h] BYREF
  CHAR CmdLine[272]; // [rsp+FA0h] [rbp+EA0h] BYREF

  v65 = this;
  v5 = this;
  DlgItem = GetDlgItem(a2, 201);
  psizl = 0;
  v10 = DlgItem;
  Rect = 0;
  v11 = a3 - 16;
  if ( !v11 )
  {
    PostMessageA(a2, 0x111u, 2u, 0);
    return 1;
  }
  v12 = v11 - 256;
  if ( !v12 )
  {
    cx = 0;
    CSampleDialog::SetAllFonts(v9, a2);
    SendDlgItemMessageA(a2, 201, 0x30u, *(_QWORD *)(*((_QWORD *)v5 + 615) + 1216LL), 0);
    GetWindowRect(v10, &Rect);
    DC = GetDC(v10);
    SendDlgItemMessageA(a2, 201, 0x184u, 0, 0);
    lParam = (LPARAM *)*((_QWORD *)v5 + 210);
    while ( lParam )
    {
      v58 = SendDlgItemMessageA(a2, 201, 0x180u, 0, *lParam);
      SendDlgItemMessageA(a2, 201, 0x19Au, v58, (LPARAM)lParam);
      v59 = (const CHAR *)*lParam;
      v60 = -1;
      do
        ++v60;
      while ( v59[v60] );
      GetTextExtentPoint32A(DC, v59, v60, &psizl);
      lParam = (LPARAM *)lParam[3];
      if ( psizl.cx > cx )
        cx = psizl.cx;
    }
    if ( Rect.right - Rect.left > cx )
      ShowScrollBar(v10, 0, 0);
    else
      SendMessageA(v10, 0x194u, cx, 0);
    ReleaseDC(v10, DC);
    v61 = GetDlgItem(a2, 204);
    EnableWindow(v61, 0);
    v62 = GetDlgItem(a2, 205);
    EnableWindow(v62, 0);
    CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
    SetCursor(CursorA);
    return 1;
  }
  if ( v12 != 1 )
    return 0;
  switch ( (unsigned __int16)a4 )
  {
    case 1u:
    case 2u:
      EndDialog(a2, 0);
      return 1;
    case 0xC9u:
      v30 = a4 >> 16;
      if ( (_WORD)v30 == 1 )
      {
        OneSel = GetOneSel(DlgItem, 0);
        if ( OneSel == -1 )
          goto LABEL_36;
        v32 = OneSel;
        if ( (unsigned int)SendMessageA(v10, 0x18Au, OneSel, (LPARAM)Caption) >= 0x104 )
          return 1;
        SendMessageA(v10, 0x189u, v32, (LPARAM)Caption);
        if ( (*(_BYTE *)(SendMessageA(v10, 0x199u, v32, 0) + 20) & 2) == 0 )
        {
LABEL_36:
          v33 = GetDlgItem(a2, 204);
          v34 = 0;
        }
        else
        {
          v33 = GetDlgItem(a2, 204);
          v34 = 1;
        }
        EnableWindow(v33, v34);
        if ( GetOneSel(v10, 1) == -1 )
        {
          v35 = GetDlgItem(a2, 205);
          v36 = 0;
        }
        else
        {
          v35 = GetDlgItem(a2, 205);
          v36 = 1;
        }
        EnableWindow(v35, v36);
        return 1;
      }
      if ( (_WORD)v30 != 2 )
        return 1;
      goto LABEL_42;
    case 0xCBu:
      *((_DWORD *)v5 + 550) = 1;
      goto LABEL_13;
    case 0xCCu:
LABEL_42:
      v37 = GetOneSel(DlgItem, 0);
      if ( v37 != -1 )
      {
        v38 = v37;
        if ( (unsigned int)SendMessageA(v10, 0x18Au, v37, (LPARAM)Caption) >= 0x104 )
          return 1;
        SendMessageA(v10, 0x189u, v38, (LPARAM)Caption);
      }
      GetTempPath2A(260, Caption);
      v39 = SendMessageA(v10, 0x188u, 0, 0);
      if ( v39 == -1 )
      {
        if ( g_bWinNT5 )
        {
          ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(ResourceInstance, 0x192u, Buffer, 260);
          v41 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(v41, 0x191u, Text, 256);
          v42 = 0;
LABEL_61:
          MessageBoxW(a2, Text, Buffer, v42);
          return 1;
        }
        v43 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v43, 0x192u, Caption, 260);
        v44 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v44, 0x191u, v70, 256);
        v45 = 0;
        goto LABEL_49;
      }
      v46 = (const char **)SendMessageA(v10, 0x199u, v39, 0);
      StringCchCopyA(ExistingFileName, 0x100u, (const char *)v5 + 4292);
      CatPath(ExistingFileName, *v46, 0x100u);
      if ( *((_DWORD *)v5 + 551) )
        BackSlashToSlash(ExistingFileName);
      v47 = *v46;
      v48 = (LPSTR)v47;
      for ( i = *v47; i; i = *v48 )
      {
        v50 = v48 + 1;
        if ( i != 92 )
          v50 = (LPSTR)v47;
        v47 = v50;
        v48 = CharNextA(v48);
      }
      CatPath(Caption, v47, 0x104u);
      if ( *((_DWORD *)v5 + 551) )
      {
        if ( (int)DownloadURL(ExistingFileName, Caption) < 0 )
        {
          if ( g_bWinNT5 )
          {
            DeleteFileA(Caption);
            v51 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringW(v51, 0x192u, Buffer, 260);
            v52 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
            LoadStringW(v52, 0x191u, Text, 256);
            v42 = 48;
            goto LABEL_61;
          }
          DeleteFileA(Caption);
          v53 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringA(v53, 0x192u, Caption, 260);
          v54 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringA(v54, 0x191u, v70, 256);
          v45 = 48;
LABEL_49:
          MessageBoxA(a2, v70, Caption, v45);
          return 1;
        }
      }
      else
      {
        CopyFileA(ExistingFileName, Caption, 0);
      }
      StringCchPrintfA(CmdLine, 0x104u, "notepad %s", Caption);
      WinExec(CmdLine, 5u);
      return 1;
  }
  if ( (unsigned __int16)a4 != 205 )
    return 1;
LABEL_13:
  v14 = SendMessageA(DlgItem, 0x18Bu, 0, 0);
  if ( v14 > 0 )
  {
    for ( j = 0; (int)j < v14; ++j )
    {
      v16 = SendDlgItemMessageA(a2, 201, 0x199u, j, 0);
      v17 = SendMessageA(v10, 0x187u, j, 0);
      *(_DWORD *)(v16 + 12) = (unsigned __int64)(v17 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL;
    }
    v5 = v65;
  }
  v67 = 0;
  v66[0] = (LPARAM)&CLockOut::`vftable';
  CLockOut::LockOut((LPARAM)v66, a2);
  if ( g_bWinNT5 )
  {
    v18 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v19 = IsolationAwareDialogBoxParamW(v18, (LPCWSTR)0x12C, a2, (DLGPROC)SampleCopyProcStub, (LPARAM)v5);
  }
  else
  {
    v20 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v19 = IsolationAwareDialogBoxParamA(v20, (LPCSTR)0x12C, a2, (DLGPROC)SampleCopyProcStub, (LPARAM)v5);
  }
  v21 = v19;
  CLockOut::Unlock((CLockOut *)v66);
  if ( v21 == 2 )
  {
    if ( g_bWinNT5 )
    {
      v22 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
      LoadStringW(v22, 0x192u, Buffer, 260);
      v23 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
      v24 = 401;
LABEL_27:
      LoadStringW(v23, v24, Text, 256);
      MessageBoxW(a2, Text, Buffer, 0);
      goto LABEL_30;
    }
    v25 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    LoadStringA(v25, 0x192u, Caption, 260);
    v26 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v27 = 401;
    goto LABEL_29;
  }
  if ( v21 == 1 )
  {
    if ( g_bWinNT5 )
    {
      v28 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
      LoadStringW(v28, 0x192u, Buffer, 260);
      v23 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
      v24 = 400;
      goto LABEL_27;
    }
    v29 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    LoadStringA(v29, 0x192u, Caption, 260);
    v26 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v27 = 400;
LABEL_29:
    LoadStringA(v26, v27, v70, 256);
    MessageBoxA(a2, v70, Caption, 0);
  }
LABEL_30:
  v66[0] = (LPARAM)&CLockOut::`vftable';
  CLockOut::Unlock((CLockOut *)v66);
  return 1;
}

```

## disassembly

```asm
0x18004c040  mov     [rsp-8+arg_10], rbx
0x18004c045  push    rbp
0x18004c046  push    rsi
0x18004c047  push    rdi
0x18004c048  push    r12
0x18004c04a  push    r13
0x18004c04c  push    r14
0x18004c04e  push    r15
0x18004c050  lea     rbp, [rsp-0FC0h]
0x18004c058  mov     eax, 10C0h
0x18004c05d  call    _alloca_probe
0x18004c062  sub     rsp, rax
0x18004c065  mov     rax, cs:__security_cookie
0x18004c06c  xor     rax, rsp
0x18004c06f  mov     [rbp+0FF0h+var_40], rax
0x18004c076  mov     rsi, rdx
0x18004c079  mov     [rsp+10F0h+var_10B0], rcx
0x18004c07e  mov     r13, rcx
0x18004c081  mov     r15d, 0C9h
0x18004c087  mov     edx, r15d; nIDDlgItem
0x18004c08a  mov     rcx, rsi; hDlg
0x18004c08d  mov     rdi, r9
0x18004c090  mov     ebx, r8d
0x18004c093  call    cs:__imp_GetDlgItem
0x18004c099  xor     r12d, r12d
0x18004c09c  xorps   xmm0, xmm0
0x18004c09f  mov     qword ptr [rsp+10F0h+psizl.cx], r12
0x18004c0a4  mov     r14, rax
0x18004c0a7  movups  xmmword ptr [rbp+0FF0h+Rect.left], xmm0
0x18004c0ae  sub     ebx, 10h
0x18004c0b1  jz      loc_18004C916
0x18004c0b7  sub     ebx, 100h
0x18004c0bd  jz      loc_18004C7AE
0x18004c0c3  cmp     ebx, 1
0x18004c0c6  jz      short loc_18004C0CF
0x18004c0c8  xor     eax, eax
0x18004c0ca  jmp     loc_18004C930
0x18004c0cf  movzx   ecx, di
0x18004c0d2  sub     ecx, 1
0x18004c0d5  jz      loc_18004C79E
0x18004c0db  sub     ecx, 1
0x18004c0de  jz      loc_18004C79E
0x18004c0e4  sub     ecx, 0C7h
0x18004c0ea  jz      loc_18004C37F
0x18004c0f0  mov     r15d, 2
0x18004c0f6  sub     ecx, r15d
0x18004c0f9  jz      short loc_18004C10E
0x18004c0fb  sub     ecx, 1
0x18004c0fe  jz      loc_18004C481
0x18004c104  cmp     ecx, 1
0x18004c107  jz      short loc_18004C119
0x18004c109  jmp     loc_18004C92B
0x18004c10e  mov     dword ptr [r13+898h], 1
0x18004c119  xor     r9d, r9d; lParam
0x18004c11c  xor     r8d, r8d; wParam
0x18004c11f  mov     edx, 18Bh; Msg
0x18004c124  mov     rcx, r14; hWnd
0x18004c127  call    cs:__imp_SendMessageA
0x18004c12d  mov     dword ptr [rsp+10F0h+wParam], 0
0x18004c135  mov     r12, rax
0x18004c138  test    eax, eax
0x18004c13a  jle     short loc_18004C1A3
0x18004c13c  mov     r15d, dword ptr [rsp+10F0h+wParam]
0x18004c141  mov     r13d, 1
0x18004c147  mov     r9d, r15d; wParam
0x18004c14a  mov     edx, 0C9h; nIDDlgItem
0x18004c14f  mov     r8d, 199h; Msg
0x18004c155  mov     [rsp+10F0h+lParam], 0; lParam
0x18004c15e  mov     rcx, rsi; hDlg
0x18004c161  call    cs:__imp_SendDlgItemMessageA
0x18004c167  xor     r9d, r9d; lParam
0x18004c16a  mov     r8d, r15d; wParam
0x18004c16d  mov     edx, 187h; Msg
0x18004c172  mov     rcx, r14; hWnd
0x18004c175  mov     rdi, rax
0x18004c178  call    cs:__imp_SendMessageA
0x18004c17e  xor     edx, edx
0x18004c180  movsxd  rcx, eax
0x18004c183  sub     rcx, r13
0x18004c186  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18004c18a  setbe   dl
0x18004c18d  add     r15d, r13d
0x18004c190  mov     [rdi+0Ch], edx
0x18004c193  cmp     r15d, r12d
0x18004c196  jl      short loc_18004C147
0x18004c198  mov     r13, [rsp+10F0h+var_10B0]
0x18004c19d  mov     r15d, 2
0x18004c1a3  lea     r14, ??_7CLockOut@@6B@; const CLockOut::`vftable'
0x18004c1aa  mov     [rbp+0FF0h+var_898], 0
0x18004c1b1  mov     rdx, rsi; hWnd
0x18004c1b4  mov     [rsp+10F0h+var_10A0], r14
0x18004c1b9  lea     rcx, [rsp+10F0h+var_10A0]; lParam
0x18004c1be  call    ?LockOut@CLockOut@@QEAAXPEAUHWND__@@@Z; CLockOut::LockOut(HWND__ *)
0x18004c1c3  cmp     cs:?g_bWinNT5@@3HA, 0; int g_bWinNT5
0x18004c1ca  lea     rbx, ?_Module@@3VCHtmlHelpModule@@A; CHtmlHelpModule _Module
0x18004c1d1  mov     rcx, rbx; this
0x18004c1d4  jz      short loc_18004C1F9
0x18004c1d6  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c1db  mov     rcx, rax; hInstance
0x18004c1de  mov     [rsp+10F0h+lParam], r13; LPARAM
0x18004c1e3  lea     r9, ?SampleCopyProcStub@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18004c1ea  mov     r8, rsi; hWndParent
0x18004c1ed  mov     edx, 12Ch; lpTemplateName
0x18004c1f2  call    IsolationAwareDialogBoxParamW
0x18004c1f7  jmp     short loc_18004C21A
0x18004c1f9  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c1fe  mov     rcx, rax; hInstance
0x18004c201  mov     [rsp+10F0h+lParam], r13; LPARAM
0x18004c206  lea     r9, ?SampleCopyProcStub@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18004c20d  mov     r8, rsi; hWndParent
0x18004c210  mov     edx, 12Ch; lpTemplateName
0x18004c215  call    IsolationAwareDialogBoxParamA
0x18004c21a  lea     rcx, [rsp+10F0h+var_10A0]; this
0x18004c21f  mov     rdi, rax
0x18004c222  call    ?Unlock@CLockOut@@QEAAXXZ; CLockOut::Unlock(void)
0x18004c227  cmp     rdi, r15
0x18004c22a  jnz     short loc_18004C299
0x18004c22c  cmp     cs:?g_bWinNT5@@3HA, 0; int g_bWinNT5
0x18004c233  mov     rcx, rbx; this
0x18004c236  jz      short loc_18004C267
0x18004c238  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c23d  mov     rcx, rax; hInstance
0x18004c240  lea     r8, [rbp+0FF0h+Buffer]; lpBuffer
0x18004c247  mov     r9d, 104h; cchBufferMax
0x18004c24d  mov     edx, 192h; uID
0x18004c252  call    cs:__imp_LoadStringW
0x18004c258  mov     rcx, rbx; this
0x18004c25b  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c260  mov     edx, 191h
0x18004c265  jmp     short loc_18004C2DC
0x18004c267  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c26c  mov     rcx, rax; hInstance
0x18004c26f  lea     r8, [rbp+0FF0h+Caption]; lpBuffer
0x18004c276  mov     r9d, 104h; cchBufferMax
0x18004c27c  mov     edx, 192h; uID
0x18004c281  call    cs:__imp_LoadStringA
0x18004c287  mov     rcx, rbx; this
0x18004c28a  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c28f  mov     edx, 191h
0x18004c294  jmp     loc_18004C33B
0x18004c299  cmp     rdi, 1
0x18004c29d  jnz     loc_18004C36B
0x18004c2a3  cmp     cs:?g_bWinNT5@@3HA, 0; int g_bWinNT5
0x18004c2aa  mov     rcx, rbx; this
0x18004c2ad  jz      short loc_18004C30E
0x18004c2af  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c2b4  mov     rcx, rax; hInstance
0x18004c2b7  lea     r8, [rbp+0FF0h+Buffer]; lpBuffer
0x18004c2be  mov     r9d, 104h; cchBufferMax
0x18004c2c4  mov     edx, 192h; uID
0x18004c2c9  call    cs:__imp_LoadStringW
0x18004c2cf  mov     rcx, rbx; this
0x18004c2d2  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c2d7  mov     edx, 190h; uID
0x18004c2dc  lea     r8, [rbp+0FF0h+Text]; lpBuffer
0x18004c2e3  mov     r9d, 100h; cchBufferMax
0x18004c2e9  mov     rcx, rax; hInstance
0x18004c2ec  call    cs:__imp_LoadStringW
0x18004c2f2  xor     r9d, r9d; uType
0x18004c2f5  lea     r8, [rbp+0FF0h+Buffer]; lpCaption
0x18004c2fc  lea     rdx, [rbp+0FF0h+Text]; lpText
0x18004c303  mov     rcx, rsi; hWnd
0x18004c306  call    cs:__imp_MessageBoxW
0x18004c30c  jmp     short loc_18004C36B
0x18004c30e  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c313  mov     rcx, rax; hInstance
0x18004c316  lea     r8, [rbp+0FF0h+Caption]; lpBuffer
0x18004c31d  mov     r9d, 104h; cchBufferMax
0x18004c323  mov     edx, 192h; uID
0x18004c328  call    cs:__imp_LoadStringA
0x18004c32e  mov     rcx, rbx; this
0x18004c331  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c336  mov     edx, 190h; uID
0x18004c33b  mov     r9d, 100h; cchBufferMax
0x18004c341  lea     r8, [rbp+0FF0h+var_760]; lpBuffer
0x18004c348  mov     rcx, rax; hInstance
0x18004c34b  call    cs:__imp_LoadStringA
0x18004c351  xor     r9d, r9d; uType
0x18004c354  lea     r8, [rbp+0FF0h+Caption]; lpCaption
0x18004c35b  lea     rdx, [rbp+0FF0h+var_760]; lpText
0x18004c362  mov     rcx, rsi; hWnd
0x18004c365  call    cs:__imp_MessageBoxA
0x18004c36b  lea     rcx, [rsp+10F0h+var_10A0]; this
0x18004c370  mov     [rsp+10F0h+var_10A0], r14
0x18004c375  call    ?Unlock@CLockOut@@QEAAXXZ; CLockOut::Unlock(void)
0x18004c37a  jmp     loc_18004C92B
0x18004c37f  shr     rdi, 10h
0x18004c383  mov     eax, 1
0x18004c388  cmp     di, ax
0x18004c38b  jnz     loc_18004C471
0x18004c391  xor     edx, edx; int
0x18004c393  mov     rcx, r14; hWnd
0x18004c396  call    ?GetOneSel@@YAIPEAUHWND__@@H@Z; GetOneSel(HWND__ *,int)
0x18004c39b  cmp     eax, 0FFFFFFFFh
0x18004c39e  jz      short loc_18004C41B
0x18004c3a0  movsxd  rbx, eax
0x18004c3a3  lea     r9, [rbp+0FF0h+Caption]; lParam
0x18004c3aa  mov     r8, rbx; wParam
0x18004c3ad  mov     edx, 18Ah; Msg
0x18004c3b2  mov     rcx, r14; hWnd
0x18004c3b5  call    cs:__imp_SendMessageA
0x18004c3bb  cmp     eax, 0FFFFFFFFh
0x18004c3be  jz      loc_18004C92B
0x18004c3c4  cmp     eax, 104h
0x18004c3c9  jnb     loc_18004C92B
0x18004c3cf  lea     r9, [rbp+0FF0h+Caption]; lParam
0x18004c3d6  mov     r8, rbx; wParam
0x18004c3d9  mov     edx, 189h; Msg
0x18004c3de  mov     rcx, r14; hWnd
0x18004c3e1  call    cs:__imp_SendMessageA
0x18004c3e7  xor     r9d, r9d; lParam
0x18004c3ea  mov     r8, rbx; wParam
0x18004c3ed  mov     edx, 199h; Msg
0x18004c3f2  mov     rcx, r14; hWnd
0x18004c3f5  call    cs:__imp_SendMessageA
0x18004c3fb  mov     r15d, 2
0x18004c401  test    [rax+14h], r15b
0x18004c405  jz      short loc_18004C41B
0x18004c407  mov     edx, 0CCh; nIDDlgItem
0x18004c40c  mov     rcx, rsi; hDlg
0x18004c40f  call    cs:__imp_GetDlgItem
0x18004c415  lea     edx, [r15-1]
0x18004c419  jmp     short loc_18004C42B
0x18004c41b  mov     edx, 0CCh; nIDDlgItem
0x18004c420  mov     rcx, rsi; hDlg
0x18004c423  call    cs:__imp_GetDlgItem
0x18004c429  xor     edx, edx; bEnable
0x18004c42b  mov     rcx, rax; hWnd
0x18004c42e  call    cs:__imp_EnableWindow
0x18004c434  mov     edx, 1; int
0x18004c439  mov     rcx, r14; hWnd
0x18004c43c  call    ?GetOneSel@@YAIPEAUHWND__@@H@Z; GetOneSel(HWND__ *,int)
0x18004c441  mov     edx, 0CDh; nIDDlgItem
0x18004c446  mov     rcx, rsi; hDlg
0x18004c449  cmp     eax, 0FFFFFFFFh
0x18004c44c  jnz     short loc_18004C464
0x18004c44e  call    cs:__imp_GetDlgItem
0x18004c454  xor     edx, edx; bEnable
0x18004c456  mov     rcx, rax; hWnd
0x18004c459  call    cs:__imp_EnableWindow
0x18004c45f  jmp     loc_18004C92B
0x18004c464  call    cs:__imp_GetDlgItem
0x18004c46a  mov     edx, 1
0x18004c46f  jmp     short loc_18004C456
0x18004c471  mov     r15d, 2
0x18004c477  cmp     di, r15w
0x18004c47b  jnz     loc_18004C92B
0x18004c481  xor     edx, edx; int
0x18004c483  mov     rcx, r14; hWnd
0x18004c486  call    ?GetOneSel@@YAIPEAUHWND__@@H@Z; GetOneSel(HWND__ *,int)
0x18004c48b  cmp     eax, 0FFFFFFFFh
0x18004c48e  jz      short loc_18004C4D7
0x18004c490  movsxd  rbx, eax
0x18004c493  lea     r9, [rbp+0FF0h+Caption]; lParam
0x18004c49a  mov     r8, rbx; wParam
0x18004c49d  mov     edx, 18Ah; Msg
0x18004c4a2  mov     rcx, r14; hWnd
0x18004c4a5  call    cs:__imp_SendMessageA
0x18004c4ab  cmp     eax, 0FFFFFFFFh
0x18004c4ae  jz      loc_18004C92B
0x18004c4b4  cmp     eax, 104h
0x18004c4b9  jnb     loc_18004C92B
0x18004c4bf  lea     r9, [rbp+0FF0h+Caption]; lParam
0x18004c4c6  mov     r8, rbx; wParam
0x18004c4c9  mov     edx, 189h; Msg
0x18004c4ce  mov     rcx, r14; hWnd
0x18004c4d1  call    cs:__imp_SendMessageA
0x18004c4d7  lea     rdx, [rbp+0FF0h+Caption]
0x18004c4de  mov     ecx, 104h
0x18004c4e3  call    cs:__imp_GetTempPath2A
0x18004c4e9  xor     r9d, r9d; lParam
0x18004c4ec  xor     r8d, r8d; wParam
0x18004c4ef  mov     edx, 188h; Msg
0x18004c4f4  mov     rcx, r14; hWnd
0x18004c4f7  call    cs:__imp_SendMessageA
0x18004c4fd  cmp     eax, 0FFFFFFFFh
0x18004c500  jnz     loc_18004C5C6
0x18004c506  cmp     cs:?g_bWinNT5@@3HA, r12d; int g_bWinNT5
0x18004c50d  lea     rbx, ?_Module@@3VCHtmlHelpModule@@A; CHtmlHelpModule _Module
0x18004c514  mov     rcx, rbx; this
0x18004c517  jz      short loc_18004C564
0x18004c519  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c51e  mov     rcx, rax; hInstance
0x18004c521  lea     r8, [rbp+0FF0h+Buffer]; lpBuffer
0x18004c528  mov     r9d, 104h; cchBufferMax
0x18004c52e  mov     edx, 192h; uID
0x18004c533  call    cs:__imp_LoadStringW
0x18004c539  mov     rcx, rbx; this
0x18004c53c  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c541  mov     rcx, rax; hInstance
0x18004c544  lea     r8, [rbp+0FF0h+Text]; lpBuffer
0x18004c54b  mov     r9d, 100h; cchBufferMax
0x18004c551  mov     edx, 191h; uID
0x18004c556  call    cs:__imp_LoadStringW
0x18004c55c  xor     r9d, r9d
0x18004c55f  jmp     loc_18004C6E8
0x18004c564  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004c569  mov     rcx, rax; hInstance
0x18004c56c  lea     r8, [rbp+0FF0h+Caption]; lpBuffer
0x18004c573  mov     r9d, 104h; cchBufferMax
  ... truncated ...
```
