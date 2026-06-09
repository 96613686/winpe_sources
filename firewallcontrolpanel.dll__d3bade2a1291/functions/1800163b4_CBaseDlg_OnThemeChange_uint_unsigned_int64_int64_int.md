# CBaseDlg::OnThemeChange(uint,unsigned __int64,__int64,int &)

- ea: `0x1800163b4`
- end: `0x1800164fa`
- name: `?OnThemeChange@CBaseDlg@@QEAA_JI_K_JAEAH@Z`
- size: `326`
- prototype: `__int64 __usercall@<rax>(CBaseDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012030`

## callees

- `0x180011650`
- `0x180012f38`
- `0x180013d4c`
- `0x180015f24`
- `0x1800163b4`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x180016448`
- `USER32!SendMessageW` at `0x1800164bd`
- `USER32!SendMessageW` at `0x180016448`
- `USER32!SendMessageW` at `0x1800164bd`
- `USER32!GetDC` at `0x180016425`
- `USER32!GetDC` at `0x180016425`
- `GDI32!GetObjectW` at `0x180016473`
- `GDI32!GetObjectW` at `0x180016473`
- `GDI32!CreateFontIndirectW` at `0x18001648a`
- `GDI32!CreateFontIndirectW` at `0x18001648a`
- `UxTheme!IsThemeActive` at `0x180016404`
- `UxTheme!IsThemeActive` at `0x180016404`
- `UxTheme!OpenThemeData` at `0x180016418`
- `UxTheme!OpenThemeData` at `0x180016418`
- `UxTheme!CloseThemeData` at `0x1800163f2`
- `UxTheme!CloseThemeData` at `0x1800163f2`

## string_xrefs

- `0x180016411`: `TASKDIALOG`

## pseudocode

```c
__int64 __fastcall CBaseDlg::OnThemeChange(CBaseDlg *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  void *v6; // rcx
  BOOL v7; // eax
  HWND v8; // rcx
  HTHEME v9; // rax
  HWND v10; // rcx
  HDC DC; // rax
  CBaseDlg *v12; // rcx
  HFONT SecurityFont; // rax
  void *v14; // rdi
  WPARAM v15; // rdi
  HWND *DlgItem; // rax
  _BYTE v18[16]; // [rsp+30h] [rbp-88h] BYREF
  LOGFONTW pv; // [rsp+40h] [rbp-78h] BYREF

  *a5 = 0;
  v6 = (void *)*((_QWORD *)this + 12);
  if ( v6 )
  {
    CloseThemeData(v6);
    *((_QWORD *)this + 12) = 0;
  }
  v7 = IsThemeActive();
  v8 = (HWND)*((_QWORD *)this + 1);
  if ( v7 )
  {
    v9 = OpenThemeData(v8, L"TASKDIALOG");
    v10 = (HWND)*((_QWORD *)this + 1);
    *((_QWORD *)this + 12) = v9;
    DC = GetDC(v10);
    if ( !DC )
      goto LABEL_10;
    SecurityFont = CBaseDlg::CreateSecurityFont(v12, *((void **)this + 12), DC);
    goto LABEL_9;
  }
  v14 = (void *)SendMessageW(v8, 0x31u, 0, 0);
  if ( v14 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(v14, 92, &pv) )
    {
      pv.lfWeight = 700;
      SecurityFont = CreateFontIndirectW(&pv);
LABEL_9:
      *((_QWORD *)this + 10) = SecurityFont;
    }
  }
LABEL_10:
  v15 = *((_QWORD *)this + 10);
  if ( v15 )
  {
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v18, 1600);
    SendMessageW(*DlgItem, 0x30u, v15, 0);
    CBaseDlg::AdjustTitlePosition(this);
  }
  CWarningBaseDlg::UpdateBackground(this);
  return 0;
}

```

## disassembly

```asm
0x1800163b4  mov     [rsp+arg_8], rbx
0x1800163b9  mov     [rsp+arg_10], rsi
0x1800163be  push    rdi
0x1800163bf  sub     rsp, 0B0h
0x1800163c6  mov     rax, cs:__security_cookie
0x1800163cd  xor     rax, rsp
0x1800163d0  mov     [rsp+0B8h+var_18], rax
0x1800163d8  mov     rax, [rsp+0B8h+arg_20]
0x1800163e0  mov     rbx, rcx
0x1800163e3  mov     dword ptr [rax], 0
0x1800163e9  mov     rcx, [rcx+60h]; hTheme
0x1800163ed  test    rcx, rcx
0x1800163f0  jz      short loc_180016400
0x1800163f2  call    cs:__imp_CloseThemeData
0x1800163f8  mov     qword ptr [rbx+60h], 0
0x180016400  lea     rsi, [rbx+8]
0x180016404  call    cs:__imp_IsThemeActive
0x18001640a  mov     rcx, [rsi]; hWnd
0x18001640d  test    eax, eax
0x18001640f  jz      short loc_18001643E
0x180016411  lea     rdx, pszClassList; "TASKDIALOG"
0x180016418  call    cs:__imp_OpenThemeData
0x18001641e  mov     rcx, [rsi]; hWnd
0x180016421  mov     [rbx+60h], rax
0x180016425  call    cs:__imp_GetDC
0x18001642b  test    rax, rax
0x18001642e  jz      short loc_180016494
0x180016430  mov     rdx, [rbx+60h]; void *
0x180016434  mov     r8, rax; HDC
0x180016437  call    ?CreateSecurityFont@CBaseDlg@@IEAAPEAUHFONT__@@PEAXPEAUHDC__@@HH@Z; CBaseDlg::CreateSecurityFont(void *,HDC__ *,int,int)
0x18001643c  jmp     short loc_180016490
0x18001643e  xor     r9d, r9d; lParam
0x180016441  xor     r8d, r8d; wParam
0x180016444  lea     edx, [r9+31h]; Msg
0x180016448  call    cs:__imp_SendMessageW
0x18001644e  mov     rdi, rax
0x180016451  test    rax, rax
0x180016454  jz      short loc_180016494
0x180016456  xor     edx, edx; Val
0x180016458  lea     rcx, [rsp+0B8h+pv]; void *
0x18001645d  lea     r8d, [rdx+5Ch]; Size
0x180016461  call    memset_0
0x180016466  lea     r8, [rsp+0B8h+pv]; pv
0x18001646b  mov     edx, 5Ch ; '\'; c
0x180016470  mov     rcx, rdi; h
0x180016473  call    cs:__imp_GetObjectW
0x180016479  test    eax, eax
0x18001647b  jz      short loc_180016494
0x18001647d  lea     rcx, [rsp+0B8h+pv]; lplf
0x180016482  mov     [rsp+0B8h+var_68], 2BCh
0x18001648a  call    cs:__imp_CreateFontIndirectW
0x180016490  mov     [rbx+50h], rax
0x180016494  mov     rdi, [rbx+50h]
0x180016498  test    rdi, rdi
0x18001649b  jz      short loc_1800164CB
0x18001649d  mov     r8d, 640h
0x1800164a3  lea     rdx, [rsp+0B8h+var_88]
0x1800164a8  mov     rcx, rsi
0x1800164ab  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800164b0  xor     r9d, r9d; lParam
0x1800164b3  mov     r8, rdi; wParam
0x1800164b6  mov     rcx, [rax]; hWnd
0x1800164b9  lea     edx, [r9+30h]; Msg
0x1800164bd  call    cs:__imp_SendMessageW
0x1800164c3  mov     rcx, rbx; this
0x1800164c6  call    ?AdjustTitlePosition@CBaseDlg@@IEAAXXZ; CBaseDlg::AdjustTitlePosition(void)
0x1800164cb  mov     rcx, rbx; this
0x1800164ce  call    ?UpdateBackground@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::UpdateBackground(void)
0x1800164d3  xor     eax, eax
0x1800164d5  mov     rcx, [rsp+0B8h+var_18]
0x1800164dd  xor     rcx, rsp; StackCookie
0x1800164e0  call    __security_check_cookie
0x1800164e5  lea     r11, [rsp+0B8h+var_8]
0x1800164ed  mov     rbx, [r11+18h]
0x1800164f1  mov     rsi, [r11+20h]
0x1800164f5  mov     rsp, r11
0x1800164f8  pop     rdi
0x1800164f9  retn
```
