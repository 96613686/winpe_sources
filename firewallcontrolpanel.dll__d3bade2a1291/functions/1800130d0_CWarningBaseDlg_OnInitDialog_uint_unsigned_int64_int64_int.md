# CWarningBaseDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x1800130d0`
- end: `0x180013269`
- name: `?OnInitDialog@CWarningBaseDlg@@QEAA_JI_K_JAEAH@Z`
- size: `409`
- prototype: `__int64 __usercall@<rax>(CWarningBaseDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013960`

## callees

- `0x180011650`
- `0x180012c08`
- `0x180012f38`
- `0x1800130d0`
- `0x18001563c`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!SendMessageW` at `0x180013142`
- `USER32!SendMessageW` at `0x1800131b7`
- `USER32!SendMessageW` at `0x180013142`
- `USER32!SendMessageW` at `0x1800131b7`
- `USER32!GetDC` at `0x18001311f`
- `USER32!GetDC` at `0x18001311f`
- `USER32!GetSysColor` at `0x1800131d4`
- `USER32!GetSysColor` at `0x180013230`
- `USER32!GetSysColor` at `0x1800131d4`
- `USER32!GetSysColor` at `0x180013230`
- `GDI32!GetObjectW` at `0x18001316d`
- `GDI32!GetObjectW` at `0x18001316d`
- `GDI32!CreateFontIndirectW` at `0x180013184`
- `GDI32!CreateFontIndirectW` at `0x180013184`
- `GDI32!CreateSolidBrush` at `0x1800131dc`
- `GDI32!CreateSolidBrush` at `0x180013238`
- `GDI32!CreateSolidBrush` at `0x1800131dc`
- `GDI32!CreateSolidBrush` at `0x180013238`
- `UxTheme!GetThemeColor` at `0x18001321b`
- `UxTheme!GetThemeColor` at `0x18001321b`
- `UxTheme!IsThemeActive` at `0x1800130fe`
- `UxTheme!IsThemeActive` at `0x1800131ee`
- `UxTheme!IsThemeActive` at `0x1800130fe`
- `UxTheme!IsThemeActive` at `0x1800131ee`
- `UxTheme!OpenThemeData` at `0x180013112`
- `UxTheme!OpenThemeData` at `0x180013112`

## string_xrefs

- `0x18001310b`: `TASKDIALOG`

## pseudocode

```c
__int64 __fastcall CWarningBaseDlg::OnInitDialog(CWarningBaseDlg *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HWND *v5; // rsi
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
  COLORREF SysColor; // eax
  void *v18; // rcx
  COLORREF v19; // ecx
  __int64 result; // rax
  COLORREF pColor; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v22[8]; // [rsp+38h] [rbp-A0h] BYREF
  LOGFONTW pv; // [rsp+40h] [rbp-98h] BYREF

  v5 = (HWND *)((char *)this + 8);
  v7 = IsThemeActive();
  v8 = *v5;
  if ( v7 )
  {
    v9 = OpenThemeData(v8, L"TASKDIALOG");
    v10 = *v5;
    *((_QWORD *)this + 12) = v9;
    DC = GetDC(v10);
    if ( !DC )
      goto LABEL_8;
    SecurityFont = CBaseDlg::CreateSecurityFont(v12, *((void **)this + 12), DC);
    goto LABEL_7;
  }
  v14 = (void *)SendMessageW(v8, 0x31u, 0, 0);
  if ( v14 )
  {
    memset_0(&pv, 0, sizeof(pv));
    if ( GetObjectW(v14, 92, &pv) )
    {
      pv.lfWeight = 700;
      SecurityFont = CreateFontIndirectW(&pv);
LABEL_7:
      *((_QWORD *)this + 10) = SecurityFont;
    }
  }
LABEL_8:
  v15 = *((_QWORD *)this + 10);
  if ( v15 )
  {
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem(v5, v22, 12201);
    SendMessageW(*DlgItem, 0x30u, v15, 0);
    CWarningBaseDlg::AdjustTitlePosition(this);
  }
  *((_DWORD *)this + 22) = IsUIHighContrast(0);
  SysColor = GetSysColor(15);
  *((_QWORD *)this + 8) = CreateSolidBrush(SysColor);
  pColor = 0;
  if ( IsThemeActive() && (v18 = (void *)*((_QWORD *)this + 12)) != 0 && GetThemeColor(v18, 1, 0, 3802, &pColor) >= 0 )
    v19 = pColor;
  else
    v19 = GetSysColor(5);
  *((_QWORD *)this + 9) = CreateSolidBrush(v19);
  result = 1;
  *a5 = 0;
  return result;
}

```

## disassembly

```asm
0x1800130d0  push    rbx
0x1800130d2  push    rsi
0x1800130d3  push    rdi
0x1800130d4  push    r14
0x1800130d6  sub     rsp, 0B8h
0x1800130dd  mov     rax, cs:__security_cookie
0x1800130e4  xor     rax, rsp
0x1800130e7  mov     [rsp+0D8h+var_38], rax
0x1800130ef  mov     r14, [rsp+0D8h+arg_20]
0x1800130f7  lea     rsi, [rcx+8]
0x1800130fb  mov     rbx, rcx
0x1800130fe  call    cs:__imp_IsThemeActive
0x180013104  mov     rcx, [rsi]; hWnd
0x180013107  test    eax, eax
0x180013109  jz      short loc_180013138
0x18001310b  lea     rdx, pszClassList; "TASKDIALOG"
0x180013112  call    cs:__imp_OpenThemeData
0x180013118  mov     rcx, [rsi]; hWnd
0x18001311b  mov     [rbx+60h], rax
0x18001311f  call    cs:__imp_GetDC
0x180013125  test    rax, rax
0x180013128  jz      short loc_18001318E
0x18001312a  mov     rdx, [rbx+60h]; void *
0x18001312e  mov     r8, rax; HDC
0x180013131  call    ?CreateSecurityFont@CBaseDlg@@IEAAPEAUHFONT__@@PEAXPEAUHDC__@@HH@Z; CBaseDlg::CreateSecurityFont(void *,HDC__ *,int,int)
0x180013136  jmp     short loc_18001318A
0x180013138  xor     r9d, r9d; lParam
0x18001313b  xor     r8d, r8d; wParam
0x18001313e  lea     edx, [r9+31h]; Msg
0x180013142  call    cs:__imp_SendMessageW
0x180013148  mov     rdi, rax
0x18001314b  test    rax, rax
0x18001314e  jz      short loc_18001318E
0x180013150  xor     edx, edx; Val
0x180013152  lea     rcx, [rsp+0D8h+pv]; void *
0x180013157  lea     r8d, [rdx+5Ch]; Size
0x18001315b  call    memset_0
0x180013160  lea     r8, [rsp+0D8h+pv]; pv
0x180013165  mov     edx, 5Ch ; '\'; c
0x18001316a  mov     rcx, rdi; h
0x18001316d  call    cs:__imp_GetObjectW
0x180013173  test    eax, eax
0x180013175  jz      short loc_18001318E
0x180013177  lea     rcx, [rsp+0D8h+pv]; lplf
0x18001317c  mov     [rsp+0D8h+var_88], 2BCh
0x180013184  call    cs:__imp_CreateFontIndirectW
0x18001318a  mov     [rbx+50h], rax
0x18001318e  mov     rdi, [rbx+50h]
0x180013192  test    rdi, rdi
0x180013195  jz      short loc_1800131C5
0x180013197  mov     r8d, 2FA9h
0x18001319d  lea     rdx, [rsp+0D8h+var_A0]
0x1800131a2  mov     rcx, rsi
0x1800131a5  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800131aa  xor     r9d, r9d; lParam
0x1800131ad  mov     r8, rdi; wParam
0x1800131b0  mov     rcx, [rax]; hWnd
0x1800131b3  lea     edx, [r9+30h]; Msg
0x1800131b7  call    cs:__imp_SendMessageW
0x1800131bd  mov     rcx, rbx; this
0x1800131c0  call    ?AdjustTitlePosition@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::AdjustTitlePosition(void)
0x1800131c5  xor     ecx, ecx; int *
0x1800131c7  call    ?IsUIHighContrast@@YAHPEAH@Z; IsUIHighContrast(int *)
0x1800131cc  mov     ecx, 0Fh; nIndex
0x1800131d1  mov     [rbx+58h], eax
0x1800131d4  call    cs:__imp_GetSysColor
0x1800131da  mov     ecx, eax; color
0x1800131dc  call    cs:__imp_CreateSolidBrush
0x1800131e2  mov     [rbx+40h], rax
0x1800131e6  mov     [rsp+0D8h+var_A8], 0
0x1800131ee  call    cs:__imp_IsThemeActive
0x1800131f4  mov     edi, 1
0x1800131f9  test    eax, eax
0x1800131fb  jz      short loc_18001322B
0x1800131fd  mov     rcx, [rbx+60h]; hTheme
0x180013201  test    rcx, rcx
0x180013204  jz      short loc_18001322B
0x180013206  lea     rax, [rsp+0D8h+var_A8]
0x18001320b  mov     r9d, 0EDAh; iPropId
0x180013211  xor     r8d, r8d; iStateId
0x180013214  mov     [rsp+0D8h+pColor], rax; pColor
0x180013219  mov     edx, edi; iPartId
0x18001321b  call    cs:__imp_GetThemeColor
0x180013221  test    eax, eax
0x180013223  js      short loc_18001322B
0x180013225  mov     ecx, [rsp+0D8h+var_A8]
0x180013229  jmp     short loc_180013238
0x18001322b  mov     ecx, 5; nIndex
0x180013230  call    cs:__imp_GetSysColor
0x180013236  mov     ecx, eax; color
0x180013238  call    cs:__imp_CreateSolidBrush
0x18001323e  mov     [rbx+48h], rax
0x180013242  mov     rax, rdi
0x180013245  mov     dword ptr [r14], 0
0x18001324c  mov     rcx, [rsp+0D8h+var_38]
0x180013254  xor     rcx, rsp; StackCookie
0x180013257  call    __security_check_cookie
0x18001325c  add     rsp, 0B8h
0x180013263  pop     r14
0x180013265  pop     rdi
0x180013266  pop     rsi
0x180013267  pop     rbx
0x180013268  retn
```
