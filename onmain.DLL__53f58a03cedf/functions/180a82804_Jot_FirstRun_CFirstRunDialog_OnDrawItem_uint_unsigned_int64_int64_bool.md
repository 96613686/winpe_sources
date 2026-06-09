# Jot::FirstRun::CFirstRunDialog::OnDrawItem(uint,unsigned __int64,__int64,bool *)

- ea: `0x180a82804`
- end: `0x180a82bca`
- name: `?OnDrawItem@CFirstRunDialog@FirstRun@Jot@@AEAA_JI_K_JPEA_N@Z`
- size: `966`
- prototype: `__int64 __usercall@<rax>(Jot::FirstRun::CFirstRunDialog *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180779300`

## callees

- `0x18005ccc0`
- `0x180078ec0`
- `0x180094440`
- `0x1802e2190`
- `0x1802e5170`
- `0x1803d3890`
- `0x1803d3ab4`
- `0x1803d3ae8`
- `0x180a82804`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180a82a12`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180a82a12`
- `GDI32!CreateSolidBrush` at `0x180a8291f`
- `GDI32!CreateSolidBrush` at `0x180a82af7`
- `GDI32!CreateSolidBrush` at `0x180a8291f`
- `GDI32!CreateSolidBrush` at `0x180a82af7`
- `GDI32!SelectObject` at `0x180a82958`
- `GDI32!SelectObject` at `0x180a82958`
- `GDI32!CreatePen` at `0x180a82937`
- `GDI32!CreatePen` at `0x180a82937`
- `GDI32!DeleteObject` at `0x180a82ab0`
- `GDI32!DeleteObject` at `0x180a82aba`
- `GDI32!DeleteObject` at `0x180a82b21`
- `GDI32!DeleteObject` at `0x180a82ab0`
- `GDI32!DeleteObject` at `0x180a82aba`
- `GDI32!DeleteObject` at `0x180a82b21`
- `GDI32!SetTextColor` at `0x180a829e5`
- `GDI32!SetTextColor` at `0x180a829e5`
- `GDI32!SetBkMode` at `0x180a829f3`
- `GDI32!SetBkMode` at `0x180a82b18`
- `GDI32!SetBkMode` at `0x180a829f3`
- `GDI32!SetBkMode` at `0x180a82b18`
- `GDI32!MoveToEx` at `0x180a8296b`
- `GDI32!MoveToEx` at `0x180a8296b`
- `GDI32!LineTo` at `0x180a8297d`
- `GDI32!LineTo` at `0x180a82992`
- `GDI32!LineTo` at `0x180a829a5`
- `GDI32!LineTo` at `0x180a829b5`
- `GDI32!LineTo` at `0x180a8297d`
- `GDI32!LineTo` at `0x180a82992`
- `GDI32!LineTo` at `0x180a829a5`
- `GDI32!LineTo` at `0x180a829b5`
- `USER32!GetSysColor` at `0x180a828f1`
- `USER32!GetSysColor` at `0x180a82914`
- `USER32!GetSysColor` at `0x180a82aef`
- `USER32!GetSysColor` at `0x180a828f1`
- `USER32!GetSysColor` at `0x180a82914`
- `USER32!GetSysColor` at `0x180a82aef`
- `USER32!DrawTextW` at `0x180a82aa6`
- `USER32!DrawTextW` at `0x180a82aa6`
- `USER32!DrawFocusRect` at `0x180a829d7`
- `USER32!DrawFocusRect` at `0x180a829d7`
- `USER32!InflateRect` at `0x180a829ca`
- `USER32!InflateRect` at `0x180a829ca`
- `USER32!FillRect` at `0x180a8294b`
- `USER32!FillRect` at `0x180a82b0a`
- `USER32!FillRect` at `0x180a8294b`
- `USER32!FillRect` at `0x180a82b0a`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x180a82b96`
- `mso40uiWin32Client!__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z` at `0x180a82b96`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x180a82ad3`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x180a82ad3`

## pseudocode

```c
__int64 __fastcall Jot::FirstRun::CFirstRunDialog::OnDrawItem(
        Jot::FirstRun::CFirstRunDialog *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  char *v7; // r15
  HDC v8; // rdi
  int v9; // r12d
  bool v10; // zf
  COLORREF v11; // ebx
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rdx
  HDC v18; // rdi
  COLORREF SysColor; // eax
  HBRUSH SolidBrush; // rbx
  _QWORD *v21; // rax
  int v22; // edi
  int v23; // r15d
  int MenuControlButtonHeight; // ebx
  int MenuControlButtonWidth; // eax
  int v27; // [rsp+38h] [rbp-59h]
  bool v28; // [rsp+48h] [rbp-49h]
  COLORREF color; // [rsp+50h] [rbp-41h] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-39h]
  HGDIOBJ ho; // [rsp+60h] [rbp-31h]
  _BYTE v32[16]; // [rsp+68h] [rbp-29h] BYREF
  RECT rc; // [rsp+78h] [rbp-19h] BYREF
  LPCWSTR lpchText[2]; // [rsp+88h] [rbp-9h] BYREF
  int cchText; // [rsp+98h] [rbp+7h]
  unsigned __int64 v36; // [rsp+A0h] [rbp+Fh]

  *a5 = 0;
  if ( a4 && *(_QWORD *)(a4 + 24) )
  {
    v7 = (char *)this + 552;
    if ( *(_QWORD *)(a4 + 24) == *(_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](
                                              (char *)this + 552,
                                              10)
      || *(_QWORD *)(a4 + 24) == *(_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](
                                              v7,
                                              11) )
    {
      if ( *(_DWORD *)a4 == 5 && MsoFCbvHighContrast() )
      {
        v18 = *(HDC *)(a4 + 32);
        rc = *(RECT *)(a4 + 40);
        SysColor = GetSysColor(17);
        SolidBrush = CreateSolidBrush(SysColor);
        FillRect(v18, &rc, SolidBrush);
        SetBkMode(v18, 1);
        DeleteObject(SolidBrush);
      }
      v21 = (_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](v7, 10);
      v22 = 175;
      v23 = 0;
      if ( *(_QWORD *)(a4 + 24) != *v21 )
        v22 = 191;
      if ( *((_BYTE *)this + 609) || *((_BYTE *)this + 610) )
        v23 = 1;
      MenuControlButtonHeight = Jot::FirstRun::CFirstRunDialog::GetMenuControlButtonHeight(this);
      MenuControlButtonWidth = Jot::FirstRun::CFirstRunDialog::GetMenuControlButtonWidth(this);
      LOBYTE(v27) = -1;
      NetUI::RenderSmartBitmap(
        *(NetUI **)(a4 + 32),
        0,
        0,
        MenuControlButtonWidth,
        MenuControlButtonHeight,
        v22,
        v23,
        v27,
        0,
        v28);
      goto LABEL_31;
    }
    if ( *(_QWORD *)(a4 + 24) == *(_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](
                                              v7,
                                              9)
      || *(_QWORD *)(a4 + 24) == *(_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](
                                              v7,
                                              8) )
    {
      if ( *(_DWORD *)a4 != 4 )
      {
LABEL_31:
        *a5 = 1;
        return 0;
      }
      v8 = *(HDC *)(a4 + 32);
      v9 = *(_DWORD *)(a4 + 16) & 0x10;
      v10 = (*(_BYTE *)(a4 + 16) & 1) == 0;
      rc = *(RECT *)(a4 + 40);
      if ( !v10 || v9 )
      {
        v11 = 13924352;
        v12 = 8;
      }
      else
      {
        if ( (*(_BYTE *)(a4 + 16) & 4) == 0 )
        {
          v11 = 13924352;
          color = 13924352;
LABEL_15:
          ho = CreateSolidBrush(v11);
          h = CreatePen(0, 1, color);
          FillRect(v8, &rc, (HBRUSH)ho);
          SelectObject(v8, h);
          MoveToEx(v8, rc.left, rc.top, 0);
          LineTo(v8, rc.right - 1, rc.top);
          LineTo(v8, rc.right - 1, rc.bottom - 1);
          LineTo(v8, rc.left, rc.bottom - 1);
          LineTo(v8, rc.left, rc.top);
          if ( v9 )
          {
            InflateRect(&rc, -1, -1);
            DrawFocusRect(v8, &rc);
          }
          SetTextColor(v8, 0xFFFFFFu);
          SetBkMode(v8, 1);
          v13 = *((_QWORD *)this + 68);
          if ( !v13 )
            _invoke_watson(0, 0, 0, 0, 0);
          v14 = *(_QWORD *)(*((_QWORD *)this + 65)
                          + 8 * ((*((_QWORD *)this + 66) - 1LL) & (*((_QWORD *)this + 67) - 1LL + v13)));
          color = 9
                - (*(_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](v7, 9) != *(_QWORD *)(a4 + 24));
          v15 = (_QWORD *)std::map<enum Jot::FirstRun::CFirstRunDialog::ControlId,Jot::FirstRun::CFirstRunDialog::SControlState>::_Try_emplace<enum Jot::FirstRun::CFirstRunDialog::ControlId,>(
                            v14,
                            v32,
                            &color);
          v16 = Jot::CWzInBuffer::operator wchar_t *(*v15 + 40LL);
          std::wstring::wstring(lpchText, v16);
          v17 = (const WCHAR *)lpchText;
          if ( v36 > 7 )
            v17 = lpchText[0];
          DrawTextW(v8, v17, cchText, &rc, 0x25u);
          DeleteObject(ho);
          DeleteObject(h);
          std::wstring::~wstring(lpchText);
          goto LABEL_31;
        }
        v11 = GetSysColor(17);
        v12 = 17;
      }
      color = GetSysColor(v12);
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180a82804  mov     [rsp-8+arg_8], rbx
0x180a82809  push    rbp
0x180a8280a  push    rsi
0x180a8280b  push    rdi
0x180a8280c  push    r12
0x180a8280e  push    r13
0x180a82810  push    r14
0x180a82812  push    r15
0x180a82814  lea     rbp, [rsp-1Fh]
0x180a82819  sub     rsp, 0B0h
0x180a82820  mov     rax, cs:__security_cookie
0x180a82827  xor     rax, rsp
0x180a8282a  mov     [rbp+4Fh+var_38], rax
0x180a8282e  mov     r13, [rbp+4Fh+arg_20]
0x180a82832  xor     r12d, r12d
0x180a82835  mov     rsi, r9
0x180a82838  mov     r14, rcx
0x180a8283b  mov     [r13+0], r12b
0x180a8283f  test    r9, r9
0x180a82842  jz      loc_180A82BA1
0x180a82848  cmp     [r9+18h], r12
0x180a8284c  jz      loc_180A82BA1
0x180a82852  lea     r15, [rcx+228h]
0x180a82859  mov     rcx, r15
0x180a8285c  lea     edx, [r12+0Ah]
0x180a82861  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a82866  mov     rcx, [rax]
0x180a82869  cmp     [rsi+18h], rcx
0x180a8286d  jz      loc_180A82ACE
0x180a82873  lea     edx, [r12+0Bh]
0x180a82878  mov     rcx, r15
0x180a8287b  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a82880  mov     rcx, [rax]
0x180a82883  cmp     [rsi+18h], rcx
0x180a82887  jz      loc_180A82ACE
0x180a8288d  lea     edx, [r12+9]
0x180a82892  mov     rcx, r15
0x180a82895  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a8289a  mov     rcx, [rax]
0x180a8289d  cmp     [rsi+18h], rcx
0x180a828a1  jz      short loc_180A828BD
0x180a828a3  lea     edx, [r12+8]
0x180a828a8  mov     rcx, r15
0x180a828ab  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a828b0  mov     rcx, [rax]
0x180a828b3  cmp     [rsi+18h], rcx
0x180a828b7  jnz     loc_180A82BA1
0x180a828bd  cmp     dword ptr [rsi], 4
0x180a828c0  jnz     loc_180A82B9C
0x180a828c6  mov     r12d, [rsi+10h]
0x180a828ca  movups  xmm0, xmmword ptr [rsi+28h]
0x180a828ce  mov     rdi, [rsi+20h]
0x180a828d2  and     r12d, 10h
0x180a828d6  test    byte ptr [rsi+10h], 1
0x180a828da  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x180a828df  jnz     short loc_180A8290A
0x180a828e1  test    r12d, r12d
0x180a828e4  jnz     short loc_180A8290A
0x180a828e6  test    byte ptr [rsi+10h], 4
0x180a828ea  jz      short loc_180A82900
0x180a828ec  lea     ecx, [r12+11h]; nIndex
0x180a828f1  call    cs:__imp_GetSysColor
0x180a828f7  mov     ebx, eax
0x180a828f9  lea     ecx, [r12+11h]
0x180a828fe  jmp     short loc_180A82914
0x180a82900  mov     ebx, 0D47800h
0x180a82905  mov     [rbp+4Fh+color], ebx
0x180a82908  jmp     short loc_180A8291D
0x180a8290a  mov     ebx, 0D47800h
0x180a8290f  mov     ecx, 8; nIndex
0x180a82914  call    cs:__imp_GetSysColor
0x180a8291a  mov     [rbp+4Fh+color], eax
0x180a8291d  mov     ecx, ebx; color
0x180a8291f  call    cs:__imp_CreateSolidBrush
0x180a82925  mov     r8d, [rbp+4Fh+color]; color
0x180a82929  mov     edx, 1; cWidth
0x180a8292e  xor     ecx, ecx; iStyle
0x180a82930  mov     [rbp+4Fh+ho], rax
0x180a82934  mov     rbx, rax
0x180a82937  call    cs:__imp_CreatePen
0x180a8293d  mov     r8, rbx; hbr
0x180a82940  lea     rdx, [rbp+4Fh+rc]; lprc
0x180a82944  mov     rcx, rdi; hDC
0x180a82947  mov     [rbp+4Fh+h], rax
0x180a8294b  call    cs:__imp_FillRect
0x180a82951  mov     rdx, [rbp+4Fh+h]; h
0x180a82955  mov     rcx, rdi; hdc
0x180a82958  call    cs:__imp_SelectObject
0x180a8295e  mov     r8d, [rbp+4Fh+rc.top]; y
0x180a82962  xor     r9d, r9d; lppt
0x180a82965  mov     edx, [rbp+4Fh+rc.left]; x
0x180a82968  mov     rcx, rdi; hdc
0x180a8296b  call    cs:__imp_MoveToEx
0x180a82971  mov     edx, [rbp+4Fh+rc.right]
0x180a82974  mov     rcx, rdi; hdc
0x180a82977  mov     r8d, [rbp+4Fh+rc.top]; y
0x180a8297b  dec     edx; x
0x180a8297d  call    cs:__imp_LineTo
0x180a82983  mov     r8d, [rbp+4Fh+rc.bottom]
0x180a82987  mov     rcx, rdi; hdc
0x180a8298a  mov     edx, [rbp+4Fh+rc.right]
0x180a8298d  dec     r8d; y
0x180a82990  dec     edx; x
0x180a82992  call    cs:__imp_LineTo
0x180a82998  mov     r8d, [rbp+4Fh+rc.bottom]
0x180a8299c  mov     rcx, rdi; hdc
0x180a8299f  mov     edx, [rbp+4Fh+rc.left]; x
0x180a829a2  dec     r8d; y
0x180a829a5  call    cs:__imp_LineTo
0x180a829ab  mov     r8d, [rbp+4Fh+rc.top]; y
0x180a829af  mov     rcx, rdi; hdc
0x180a829b2  mov     edx, [rbp+4Fh+rc.left]; x
0x180a829b5  call    cs:__imp_LineTo
0x180a829bb  test    r12d, r12d
0x180a829be  jz      short loc_180A829DD
0x180a829c0  or      edx, 0FFFFFFFFh; dx
0x180a829c3  lea     rcx, [rbp+4Fh+rc]; lprc
0x180a829c7  mov     r8d, edx; dy
0x180a829ca  call    cs:__imp_InflateRect
0x180a829d0  lea     rdx, [rbp+4Fh+rc]; lprc
0x180a829d4  mov     rcx, rdi; hDC
0x180a829d7  call    cs:__imp_DrawFocusRect
0x180a829dd  mov     edx, 0FFFFFFh; color
0x180a829e2  mov     rcx, rdi; hdc
0x180a829e5  call    cs:__imp_SetTextColor
0x180a829eb  mov     edx, 1; mode
0x180a829f0  mov     rcx, rdi; hdc
0x180a829f3  call    cs:__imp_SetBkMode
0x180a829f9  mov     rcx, [r14+220h]; Expression
0x180a82a00  test    rcx, rcx
0x180a82a03  jnz     short loc_180A82A19
0x180a82a05  xor     r9d, r9d; LineNo
0x180a82a08  mov     [rsp+0E0h+Reserved], rcx; Reserved
0x180a82a0d  xor     r8d, r8d; FileName
0x180a82a10  xor     edx, edx; FunctionName
0x180a82a12  call    cs:__imp__invoke_watson
0x180a82a19  mov     rax, [r14+218h]
0x180a82a20  mov     edx, 9
0x180a82a25  dec     rax
0x180a82a28  add     rcx, rax
0x180a82a2b  mov     rax, [r14+210h]
0x180a82a32  dec     rax
0x180a82a35  and     rcx, rax
0x180a82a38  mov     rax, [r14+208h]
0x180a82a3f  mov     rbx, [rax+rcx*8]
0x180a82a43  mov     rcx, r15
0x180a82a46  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a82a4b  mov     rcx, [rsi+18h]
0x180a82a4f  lea     r8, [rbp+4Fh+color]
0x180a82a53  lea     rdx, [rbp+4Fh+var_78]
0x180a82a57  sub     rcx, [rax]
0x180a82a5a  neg     rcx
0x180a82a5d  mov     rcx, rbx
0x180a82a60  sbb     eax, eax
0x180a82a62  add     eax, 9
0x180a82a65  mov     [rbp+4Fh+color], eax
0x180a82a68  call    ??$_Try_emplace@W4ControlId@CFirstRunDialog@FirstRun@Jot@@$$V@?$map@W4ControlId@CFirstRunDialog@FirstRun@Jot@@USControlState@234@U?$less@W4ControlId@CFirstRunDialog@FirstRun@Jot@@@std@@V?$allocator@U?$pair@$$CBW4ControlId@CFirstRunDialog@FirstRun@Jot@@USControlState@234@@std@@@7@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ControlId@CFirstRunDialog@FirstRun@Jot@@USControlState@234@@std@@PEAX@std@@_N@1@$$QEAW4ControlId@CFirstRunDialog@FirstRun@Jot@@@Z; std::map<Jot::FirstRun::CFirstRunDialog::ControlId,Jot::FirstRun::CFirstRunDialog::SControlState>::_Try_emplace<Jot::FirstRun::CFirstRunDialog::ControlId,>(Jot::FirstRun::CFirstRunDialog::ControlId &&)
0x180a82a6d  mov     rcx, [rax]
0x180a82a70  add     rcx, 28h ; '('
0x180a82a74  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x180a82a79  mov     rdx, rax
0x180a82a7c  lea     rcx, [rbp+4Fh+lpchText]
0x180a82a80  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180a82a85  cmp     [rbp+4Fh+var_40], 7
0x180a82a8a  lea     rdx, [rbp+4Fh+lpchText]
0x180a82a8e  mov     r8d, [rbp+4Fh+cchText]; cchText
0x180a82a92  lea     r9, [rbp+4Fh+rc]; lprc
0x180a82a96  cmova   rdx, [rbp+4Fh+lpchText]; lpchText
0x180a82a9b  mov     rcx, rdi; hdc
0x180a82a9e  mov     dword ptr [rsp+0E0h+Reserved], 25h ; '%'; format
0x180a82aa6  call    cs:__imp_DrawTextW
0x180a82aac  mov     rcx, [rbp+4Fh+ho]; ho
0x180a82ab0  call    cs:__imp_DeleteObject
0x180a82ab6  mov     rcx, [rbp+4Fh+h]; ho
0x180a82aba  call    cs:__imp_DeleteObject
0x180a82ac0  lea     rcx, [rbp+4Fh+lpchText]; void *
0x180a82ac4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180a82ac9  jmp     loc_180A82B9C
0x180a82ace  cmp     dword ptr [rsi], 5
0x180a82ad1  jnz     short loc_180A82B27
0x180a82ad3  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x180a82ad9  test    eax, eax
0x180a82adb  jz      short loc_180A82B27
0x180a82add  movups  xmm0, xmmword ptr [rsi+28h]
0x180a82ae1  mov     rdi, [rsi+20h]
0x180a82ae5  mov     ecx, 11h; nIndex
0x180a82aea  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x180a82aef  call    cs:__imp_GetSysColor
0x180a82af5  mov     ecx, eax; color
0x180a82af7  call    cs:__imp_CreateSolidBrush
0x180a82afd  lea     rdx, [rbp+4Fh+rc]; lprc
0x180a82b01  mov     rcx, rdi; hDC
0x180a82b04  mov     r8, rax; hbr
0x180a82b07  mov     rbx, rax
0x180a82b0a  call    cs:__imp_FillRect
0x180a82b10  mov     edx, 1; mode
0x180a82b15  mov     rcx, rdi; hdc
0x180a82b18  call    cs:__imp_SetBkMode
0x180a82b1e  mov     rcx, rbx; ho
0x180a82b21  call    cs:__imp_DeleteObject
0x180a82b27  mov     edx, 0Ah
0x180a82b2c  mov     rcx, r15
0x180a82b2f  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180a82b34  mov     edi, 0AFh
0x180a82b39  mov     r15d, r12d
0x180a82b3c  mov     rax, [rax]
0x180a82b3f  cmp     [rsi+18h], rax
0x180a82b43  lea     ecx, [rdi+10h]
0x180a82b46  cmovnz  edi, ecx
0x180a82b49  cmp     [r14+261h], r12b
0x180a82b50  jnz     short loc_180A82B5B
0x180a82b52  cmp     [r14+262h], r12b
0x180a82b59  jz      short loc_180A82B61
0x180a82b5b  mov     r15d, 1
0x180a82b61  mov     rcx, r14; this
0x180a82b64  call    ?GetMenuControlButtonHeight@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetMenuControlButtonHeight(void)
0x180a82b69  mov     rcx, r14; this
0x180a82b6c  mov     ebx, eax
0x180a82b6e  call    ?GetMenuControlButtonWidth@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetMenuControlButtonWidth(void)
0x180a82b73  mov     rcx, [rsi+20h]
0x180a82b77  mov     r9d, eax
0x180a82b7a  mov     [rsp+0E0h+var_A0], r12b
0x180a82b7f  xor     r8d, r8d
0x180a82b82  mov     [rsp+0E0h+var_A8], 0FFh
0x180a82b87  xor     edx, edx
0x180a82b89  mov     [rsp+0E0h+var_B0], r15d
0x180a82b8e  mov     [rsp+0E0h+var_B8], edi
0x180a82b92  mov     dword ptr [rsp+0E0h+Reserved], ebx
0x180a82b96  call    cs:__imp_?RenderSmartBitmap@NetUI@@YAXPEAUHDC__@@HHHHHHE_N@Z; NetUI::RenderSmartBitmap(HDC__ *,int,int,int,int,int,int,uchar,bool)
0x180a82b9c  mov     byte ptr [r13+0], 1
0x180a82ba1  xor     eax, eax
0x180a82ba3  mov     rcx, [rbp+4Fh+var_38]
0x180a82ba7  xor     rcx, rsp; StackCookie
0x180a82baa  call    __security_check_cookie
0x180a82baf  mov     rbx, [rsp+0E0h+arg_8]
0x180a82bb7  add     rsp, 0B0h
0x180a82bbe  pop     r15
0x180a82bc0  pop     r14
0x180a82bc2  pop     r13
0x180a82bc4  pop     r12
0x180a82bc6  pop     rdi
0x180a82bc7  pop     rsi
0x180a82bc8  pop     rbp
0x180a82bc9  retn
```
