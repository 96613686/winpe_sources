# CWizard::OnInitDialog(HWND__ *)

- ea: `0x1400328fc`
- end: `0x140032be8`
- name: `?OnInitDialog@CWizard@@QEAAJPEAUHWND__@@@Z`
- size: `748`
- prototype: `int(CWizard *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140034200`

## callees

- `0x140026c48`
- `0x1400328fc`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `GDI32!GetTextMetricsW` at `0x14003296a`
- `GDI32!GetTextMetricsW` at `0x14003296a`
- `USER32!ShowWindow` at `0x140032ae7`
- `USER32!ShowWindow` at `0x140032ae7`
- `USER32!GetDlgItem` at `0x1400329cb`
- `USER32!GetDlgItem` at `0x140032a0c`
- `USER32!GetDlgItem` at `0x140032a6f`
- `USER32!GetDlgItem` at `0x1400329cb`
- `USER32!GetDlgItem` at `0x140032a0c`
- `USER32!GetDlgItem` at `0x140032a6f`
- `USER32!MapWindowPoints` at `0x140032a9d`
- `USER32!MapWindowPoints` at `0x140032a9d`
- `USER32!SetScrollInfo` at `0x140032bb5`
- `USER32!SetScrollInfo` at `0x140032bb5`
- `USER32!SetWindowLongPtrW` at `0x140032b15`
- `USER32!SetWindowLongPtrW` at `0x140032b15`
- `USER32!ReleaseDC` at `0x140032988`
- `USER32!ReleaseDC` at `0x140032988`
- `USER32!GetDC` at `0x140032941`
- `USER32!GetDC` at `0x140032941`
- `USER32!GetWindowRect` at `0x140032a82`
- `USER32!GetWindowRect` at `0x140032b4f`
- `USER32!GetWindowRect` at `0x140032a82`
- `USER32!GetWindowRect` at `0x140032b4f`
- `USER32!UpdateWindow` at `0x140032af6`
- `USER32!UpdateWindow` at `0x140032af6`
- `USER32!SetWindowPos` at `0x140032b3c`
- `USER32!SetWindowPos` at `0x140032b3c`
- `USER32!MoveWindow` at `0x140032ad3`
- `USER32!MoveWindow` at `0x140032ad3`

## pseudocode

```c
__int64 __fastcall CWizard::OnInitDialog(struct IRaContactControl **this, HWND a2)
{
  unsigned int v4; // edi
  HDC DC; // rbx
  HWND DlgItem; // rbx
  signed int RAContactControl; // eax
  CEventLogger *v8; // rcx
  unsigned int v9; // r9d
  int v10; // edx
  HWND v11; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-39h] BYREF
  SCROLLINFO v14; // [rsp+50h] [rbp-29h] BYREF
  struct tagTEXTMETRICW tm; // [rsp+70h] [rbp-9h] BYREF

  memset(&v14, 0, sizeof(v14));
  v4 = 0;
  Rect = 0;
  DC = GetDC(a2);
  memset(&tm, 0, sizeof(tm));
  GetTextMetricsW(DC, &tm);
  dword_140064238 = tm.tmExternalLeading + tm.tmHeight;
  ReleaseDC(a2, DC);
  switch ( *(_DWORD *)this )
  {
    case 0x6B:
    case 0x6C:
    case 0x7D9:
      SetWindowLongPtrW(a2, -16, 1075838976);
      SetWindowPos(a2, 0, 0, 0, 0, 0, 0x41u);
      GetWindowRect(a2, &Rect);
      Rect.bottom -= Rect.top;
      v14.cbSize = 28;
      *(_QWORD *)&v14.fMask = 3;
      v14.nPage = Rect.bottom / dword_140064238;
      v14.nMax = (int)((double)Rect.bottom * 1.7 / (double)dword_140064238);
      SetScrollInfo(a2, 1, &v14, 1);
      return v4;
    case 0x7DC:
      DlgItem = GetDlgItem(a2, 1076);
      RAContactControl = CreateRAContactControl(DlgItem, 1u, ContactSelectedCb, this + 2);
      v4 = RAContactControl;
      if ( RAContactControl < 0 )
      {
        v9 = 134;
        goto LABEL_11;
      }
      v10 = 1016;
LABEL_13:
      v11 = GetDlgItem(a2, v10);
      GetWindowRect(v11, &Rect);
      MapWindowPoints(0, a2, (LPPOINT)&Rect, 2u);
      Rect.right -= Rect.left;
      Rect.bottom -= Rect.top;
      MoveWindow(DlgItem, Rect.left, Rect.top, Rect.right, Rect.bottom, 1);
      ShowWindow(DlgItem, 5);
      UpdateWindow(DlgItem);
      return v4;
    case 0x7DD:
      DlgItem = GetDlgItem(a2, 1077);
      RAContactControl = CreateRAContactControl(DlgItem, 0, ContactSelectedCb, this + 3);
      v4 = RAContactControl;
      if ( RAContactControl < 0 )
      {
        v9 = 166;
LABEL_11:
        CEventLogger::LogError(
          v8,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\wizard.cpp",
          v9,
          L"CWizard::OnInitDialog",
          RAContactControl);
        return v4;
      }
      v10 = 1017;
      goto LABEL_13;
  }
  return v4;
}

```

## disassembly

```asm
0x1400328fc  mov     [rsp-8+arg_10], rbx
0x140032901  mov     [rsp-8+arg_18], rsi
0x140032906  push    rbp
0x140032907  push    rdi
0x140032908  push    r14
0x14003290a  lea     rbp, [rsp-47h]
0x14003290f  sub     rsp, 0C0h
0x140032916  mov     rax, cs:__security_cookie
0x14003291d  xor     rax, rsp
0x140032920  mov     [rbp+57h+var_20], rax
0x140032924  xorps   xmm1, xmm1
0x140032927  mov     r14, rcx
0x14003292a  xorps   xmm0, xmm0
0x14003292d  mov     rcx, rdx; hWnd
0x140032930  movups  xmmword ptr [rbp+57h+var_80.cbSize], xmm1
0x140032934  mov     rsi, rdx
0x140032937  xor     edi, edi
0x140032939  movups  xmmword ptr [rbp+57h+var_80.nMax], xmm1
0x14003293d  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x140032941  call    cs:__imp_GetDC
0x140032948  nop     dword ptr [rax+rax+00h]
0x14003294d  xorps   xmm0, xmm0
0x140032950  lea     rdx, [rbp+57h+tm]; lptm
0x140032954  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x140032958  mov     rcx, rax; hdc
0x14003295b  mov     rbx, rax
0x14003295e  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x140032962  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x140032966  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x14003296a  call    cs:__imp_GetTextMetricsW
0x140032971  nop     dword ptr [rax+rax+00h]
0x140032976  mov     ecx, [rbp+57h+tm.tmHeight]
0x140032979  mov     rdx, rbx; hDC
0x14003297c  add     ecx, [rbp+57h+tm.tmExternalLeading]
0x14003297f  mov     cs:dword_140064238, ecx
0x140032985  mov     rcx, rsi; hWnd
0x140032988  call    cs:__imp_ReleaseDC
0x14003298f  nop     dword ptr [rax+rax+00h]
0x140032994  mov     ecx, [r14]
0x140032997  sub     ecx, 6Bh ; 'k'
0x14003299a  jz      loc_140032B07
0x1400329a0  sub     ecx, 1
0x1400329a3  jz      loc_140032B07
0x1400329a9  sub     ecx, 76Dh
0x1400329af  jz      loc_140032B07
0x1400329b5  sub     ecx, 3
0x1400329b8  jz      short loc_140032A04
0x1400329ba  cmp     ecx, 1
0x1400329bd  jnz     loc_140032BC1
0x1400329c3  mov     edx, 435h; nIDDlgItem
0x1400329c8  mov     rcx, rsi; hDlg
0x1400329cb  call    cs:__imp_GetDlgItem
0x1400329d2  nop     dword ptr [rax+rax+00h]
0x1400329d7  lea     r9, [r14+18h]; struct IRaContactControl **
0x1400329db  xor     edx, edx; int
0x1400329dd  mov     rcx, rax; hWnd
0x1400329e0  lea     r8, ?ContactSelectedCb@@YAXPEAGH@Z; void (*)(unsigned __int16 *, int)
0x1400329e7  mov     rbx, rax
0x1400329ea  call    ?CreateRAContactControl@@YAJPEAUHWND__@@HP6AXPEAGH@ZPEAPEAUIRaContactControl@@@Z; CreateRAContactControl(HWND__ *,int,void (*)(ushort *,int),IRaContactControl * *)
0x1400329ef  mov     edi, eax
0x1400329f1  test    eax, eax
0x1400329f3  jns     short loc_1400329FD
0x1400329f5  mov     r9d, 0A6h
0x1400329fb  jmp     short loc_140032A3F
0x1400329fd  mov     edx, 3F9h
0x140032a02  jmp     short loc_140032A6C
0x140032a04  mov     edx, 434h; nIDDlgItem
0x140032a09  mov     rcx, rsi; hDlg
0x140032a0c  call    cs:__imp_GetDlgItem
0x140032a13  nop     dword ptr [rax+rax+00h]
0x140032a18  lea     r9, [r14+10h]; struct IRaContactControl **
0x140032a1c  mov     edx, 1; int
0x140032a21  mov     rcx, rax; hWnd
0x140032a24  lea     r8, ?ContactSelectedCb@@YAXPEAGH@Z; void (*)(unsigned __int16 *, int)
0x140032a2b  mov     rbx, rax
0x140032a2e  call    ?CreateRAContactControl@@YAJPEAUHWND__@@HP6AXPEAGH@ZPEAPEAUIRaContactControl@@@Z; CreateRAContactControl(HWND__ *,int,void (*)(ushort *,int),IRaContactControl * *)
0x140032a33  mov     edi, eax
0x140032a35  test    eax, eax
0x140032a37  jns     short loc_140032A67
0x140032a39  mov     r9d, 86h; unsigned int
0x140032a3f  mov     [rsp+0D0h+bRepaint], eax; unsigned int
0x140032a43  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140032a4a  lea     rax, aCwizardOninitd; "CWizard::OnInitDialog"
0x140032a51  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140032a58  mov     qword ptr [rsp+0D0h+nHeight], rax; unsigned __int16 *
0x140032a5d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140032a62  jmp     loc_140032BC1
0x140032a67  mov     edx, 3F8h; nIDDlgItem
0x140032a6c  mov     rcx, rsi; hDlg
0x140032a6f  call    cs:__imp_GetDlgItem
0x140032a76  nop     dword ptr [rax+rax+00h]
0x140032a7b  mov     rcx, rax; hWnd
0x140032a7e  lea     rdx, [rbp+57h+Rect]; lpRect
0x140032a82  call    cs:__imp_GetWindowRect
0x140032a89  nop     dword ptr [rax+rax+00h]
0x140032a8e  mov     r9d, 2; cPoints
0x140032a94  lea     r8, [rbp+57h+Rect]; lpPoints
0x140032a98  mov     rdx, rsi; hWndTo
0x140032a9b  xor     ecx, ecx; hWndFrom
0x140032a9d  call    cs:__imp_MapWindowPoints
0x140032aa4  nop     dword ptr [rax+rax+00h]
0x140032aa9  mov     r9d, [rbp+57h+Rect.right]
0x140032aad  mov     rcx, rbx; hWnd
0x140032ab0  mov     eax, [rbp+57h+Rect.bottom]
0x140032ab3  mov     edx, [rbp+57h+Rect.left]; X
0x140032ab6  sub     r9d, edx; nWidth
0x140032ab9  mov     r8d, [rbp+57h+Rect.top]; Y
0x140032abd  sub     eax, r8d
0x140032ac0  mov     [rsp+0D0h+bRepaint], 1; bRepaint
0x140032ac8  mov     [rbp+57h+Rect.right], r9d
0x140032acc  mov     [rbp+57h+Rect.bottom], eax
0x140032acf  mov     [rsp+0D0h+nHeight], eax; nHeight
0x140032ad3  call    cs:__imp_MoveWindow
0x140032ada  nop     dword ptr [rax+rax+00h]
0x140032adf  mov     edx, 5; nCmdShow
0x140032ae4  mov     rcx, rbx; hWnd
0x140032ae7  call    cs:__imp_ShowWindow
0x140032aee  nop     dword ptr [rax+rax+00h]
0x140032af3  mov     rcx, rbx; hWnd
0x140032af6  call    cs:__imp_UpdateWindow
0x140032afd  nop     dword ptr [rax+rax+00h]
0x140032b02  jmp     loc_140032BC1
0x140032b07  mov     edx, 0FFFFFFF0h; nIndex
0x140032b0c  mov     r8d, 40200000h; dwNewLong
0x140032b12  mov     rcx, rsi; hWnd
0x140032b15  call    cs:__imp_SetWindowLongPtrW
0x140032b1c  nop     dword ptr [rax+rax+00h]
0x140032b21  mov     [rsp+0D0h+uFlags], 41h ; 'A'; uFlags
0x140032b29  xor     r9d, r9d; Y
0x140032b2c  mov     [rsp+0D0h+bRepaint], edi; cy
0x140032b30  xor     r8d, r8d; X
0x140032b33  xor     edx, edx; hWndInsertAfter
0x140032b35  mov     [rsp+0D0h+nHeight], edi; cx
0x140032b39  mov     rcx, rsi; hWnd
0x140032b3c  call    cs:__imp_SetWindowPos
0x140032b43  nop     dword ptr [rax+rax+00h]
0x140032b48  lea     rdx, [rbp+57h+Rect]; lpRect
0x140032b4c  mov     rcx, rsi; hWnd
0x140032b4f  call    cs:__imp_GetWindowRect
0x140032b56  nop     dword ptr [rax+rax+00h]
0x140032b5b  mov     r8d, cs:dword_140064238
0x140032b62  mov     r9d, 1; redraw
0x140032b68  mov     eax, [rbp+57h+Rect.bottom]
0x140032b6b  sub     eax, [rbp+57h+Rect.top]
0x140032b6e  mov     [rbp+57h+Rect.bottom], eax
0x140032b71  movd    xmm0, r8d
0x140032b76  cvtdq2pd xmm0, xmm0
0x140032b7a  mov     [rbp+57h+var_80.cbSize], 1Ch
0x140032b81  mov     qword ptr [rbp+57h+var_80.fMask], 3
0x140032b89  movd    xmm1, eax
0x140032b8d  cdq
0x140032b8e  idiv    r8d
0x140032b91  cvtdq2pd xmm1, xmm1
0x140032b95  lea     r8, [rbp+57h+var_80]; lpsi
0x140032b99  mov     [rbp+57h+var_80.nPage], eax
0x140032b9c  mov     edx, r9d; nBar
0x140032b9f  mulsd   xmm1, cs:__real@3ffb333333333333
0x140032ba7  divsd   xmm1, xmm0
0x140032bab  cvttsd2si ecx, xmm1
0x140032baf  mov     [rbp+57h+var_80.nMax], ecx
0x140032bb2  mov     rcx, rsi; hwnd
0x140032bb5  call    cs:__imp_SetScrollInfo
0x140032bbc  nop     dword ptr [rax+rax+00h]
0x140032bc1  mov     eax, edi
0x140032bc3  mov     rcx, [rbp+57h+var_20]
0x140032bc7  xor     rcx, rsp; StackCookie
0x140032bca  call    __security_check_cookie
0x140032bcf  lea     r11, [rsp+0D0h+var_10]
0x140032bd7  mov     rbx, [r11+30h]
0x140032bdb  mov     rsi, [r11+38h]
0x140032bdf  mov     rsp, r11
0x140032be2  pop     r14
0x140032be4  pop     rdi
0x140032be5  pop     rbp
0x140032be6  retn
```
