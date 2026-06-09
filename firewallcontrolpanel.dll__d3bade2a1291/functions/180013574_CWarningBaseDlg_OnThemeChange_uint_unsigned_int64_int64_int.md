# CWarningBaseDlg::OnThemeChange(uint,unsigned __int64,__int64,int &)

- ea: `0x180013574`
- end: `0x1800136ba`
- name: `?OnThemeChange@CWarningBaseDlg@@QEAA_JI_K_JAEAH@Z`
- size: `326`
- prototype: `__int64 __usercall@<rax>(CWarningBaseDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180013960`

## callees

- `0x180011650`
- `0x180012c08`
- `0x180012f38`
- `0x180013574`
- `0x180013d4c`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x180013608`
- `USER32!SendMessageW` at `0x18001367d`
- `USER32!SendMessageW` at `0x180013608`
- `USER32!SendMessageW` at `0x18001367d`
- `USER32!GetDC` at `0x1800135e5`
- `USER32!GetDC` at `0x1800135e5`
- `GDI32!GetObjectW` at `0x180013633`
- `GDI32!GetObjectW` at `0x180013633`
- `GDI32!CreateFontIndirectW` at `0x18001364a`
- `GDI32!CreateFontIndirectW` at `0x18001364a`
- `UxTheme!IsThemeActive` at `0x1800135c4`
- `UxTheme!IsThemeActive` at `0x1800135c4`
- `UxTheme!OpenThemeData` at `0x1800135d8`
- `UxTheme!OpenThemeData` at `0x1800135d8`
- `UxTheme!CloseThemeData` at `0x1800135b2`
- `UxTheme!CloseThemeData` at `0x1800135b2`

## string_xrefs

- `0x1800135d1`: `TASKDIALOG`

## pseudocode

```c
__int64 __fastcall CWarningBaseDlg::OnThemeChange(CWarningBaseDlg *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
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
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v18, 12201);
    SendMessageW(*DlgItem, 0x30u, v15, 0);
    CWarningBaseDlg::AdjustTitlePosition(this);
  }
  CWarningBaseDlg::UpdateBackground(this);
  return 0;
}

```

## disassembly

```asm
0x180013574  mov     [rsp+arg_8], rbx
0x180013579  mov     [rsp+arg_10], rsi
0x18001357e  push    rdi
0x18001357f  sub     rsp, 0B0h
0x180013586  mov     rax, cs:__security_cookie
0x18001358d  xor     rax, rsp
0x180013590  mov     [rsp+0B8h+var_18], rax
0x180013598  mov     rax, [rsp+0B8h+arg_20]
0x1800135a0  mov     rbx, rcx
0x1800135a3  mov     dword ptr [rax], 0
0x1800135a9  mov     rcx, [rcx+60h]; hTheme
0x1800135ad  test    rcx, rcx
0x1800135b0  jz      short loc_1800135C0
0x1800135b2  call    cs:__imp_CloseThemeData
0x1800135b8  mov     qword ptr [rbx+60h], 0
0x1800135c0  lea     rsi, [rbx+8]
0x1800135c4  call    cs:__imp_IsThemeActive
0x1800135ca  mov     rcx, [rsi]; hWnd
0x1800135cd  test    eax, eax
0x1800135cf  jz      short loc_1800135FE
0x1800135d1  lea     rdx, pszClassList; "TASKDIALOG"
0x1800135d8  call    cs:__imp_OpenThemeData
0x1800135de  mov     rcx, [rsi]; hWnd
0x1800135e1  mov     [rbx+60h], rax
0x1800135e5  call    cs:__imp_GetDC
0x1800135eb  test    rax, rax
0x1800135ee  jz      short loc_180013654
0x1800135f0  mov     rdx, [rbx+60h]; void *
0x1800135f4  mov     r8, rax; HDC
0x1800135f7  call    ?CreateSecurityFont@CBaseDlg@@IEAAPEAUHFONT__@@PEAXPEAUHDC__@@HH@Z; CBaseDlg::CreateSecurityFont(void *,HDC__ *,int,int)
0x1800135fc  jmp     short loc_180013650
0x1800135fe  xor     r9d, r9d; lParam
0x180013601  xor     r8d, r8d; wParam
0x180013604  lea     edx, [r9+31h]; Msg
0x180013608  call    cs:__imp_SendMessageW
0x18001360e  mov     rdi, rax
0x180013611  test    rax, rax
0x180013614  jz      short loc_180013654
0x180013616  xor     edx, edx; Val
0x180013618  lea     rcx, [rsp+0B8h+pv]; void *
0x18001361d  lea     r8d, [rdx+5Ch]; Size
0x180013621  call    memset_0
0x180013626  lea     r8, [rsp+0B8h+pv]; pv
0x18001362b  mov     edx, 5Ch ; '\'; c
0x180013630  mov     rcx, rdi; h
0x180013633  call    cs:__imp_GetObjectW
0x180013639  test    eax, eax
0x18001363b  jz      short loc_180013654
0x18001363d  lea     rcx, [rsp+0B8h+pv]; lplf
0x180013642  mov     [rsp+0B8h+var_68], 2BCh
0x18001364a  call    cs:__imp_CreateFontIndirectW
0x180013650  mov     [rbx+50h], rax
0x180013654  mov     rdi, [rbx+50h]
0x180013658  test    rdi, rdi
0x18001365b  jz      short loc_18001368B
0x18001365d  mov     r8d, 2FA9h
0x180013663  lea     rdx, [rsp+0B8h+var_88]
0x180013668  mov     rcx, rsi
0x18001366b  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180013670  xor     r9d, r9d; lParam
0x180013673  mov     r8, rdi; wParam
0x180013676  mov     rcx, [rax]; hWnd
0x180013679  lea     edx, [r9+30h]; Msg
0x18001367d  call    cs:__imp_SendMessageW
0x180013683  mov     rcx, rbx; this
0x180013686  call    ?AdjustTitlePosition@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::AdjustTitlePosition(void)
0x18001368b  mov     rcx, rbx; this
0x18001368e  call    ?UpdateBackground@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::UpdateBackground(void)
0x180013693  xor     eax, eax
0x180013695  mov     rcx, [rsp+0B8h+var_18]
0x18001369d  xor     rcx, rsp; StackCookie
0x1800136a0  call    __security_check_cookie
0x1800136a5  lea     r11, [rsp+0B8h+var_8]
0x1800136ad  mov     rbx, [r11+18h]
0x1800136b1  mov     rsi, [r11+20h]
0x1800136b5  mov     rsp, r11
0x1800136b8  pop     rdi
0x1800136b9  retn
```
