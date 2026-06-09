# CMenuBar::OnCustomDraw(tagNMHDR *,__int64 *)

- ea: `0x14003b240`
- end: `0x14003b518`
- name: `?OnCustomDraw@CMenuBar@@IEAAXPEAUtagNMHDR@@PEA_J@Z`
- size: `728`
- prototype: `void __fastcall(CMenuBar *__hidden this, struct tagNMHDR *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14003b240`
- `0x1400575d8`
- `0x14006623c`
- `0x1400c1344`
- `0x1400c13f4`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `GDI32!GetTextColor` at `0x14003b467`
- `GDI32!GetTextColor` at `0x14003b467`
- `GDI32!GetLayout` at `0x14003b366`
- `GDI32!GetLayout` at `0x14003b366`
- `GDI32!SetLayout` at `0x14003b37e`
- `GDI32!SetLayout` at `0x14003b3c6`
- `GDI32!SetLayout` at `0x14003b37e`
- `GDI32!SetLayout` at `0x14003b3c6`
- `GDI32!GetBkColor` at `0x14003b47e`
- `GDI32!GetBkColor` at `0x14003b47e`
- `GDI32!RoundRect` at `0x14003b43b`
- `GDI32!RoundRect` at `0x14003b43b`
- `USER32!DrawIconEx` at `0x14003b3b6`
- `USER32!DrawIconEx` at `0x14003b3b6`
- `USER32!CopyRect` at `0x14003b322`
- `USER32!CopyRect` at `0x14003b3ff`
- `USER32!CopyRect` at `0x14003b322`
- `USER32!CopyRect` at `0x14003b3ff`
- `USER32!GetSystemMetrics` at `0x14003b333`
- `USER32!GetSystemMetrics` at `0x14003b34f`
- `USER32!GetSystemMetrics` at `0x14003b333`
- `USER32!GetSystemMetrics` at `0x14003b34f`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14003b4ba`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14003b4ba`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x14003b3e0`
- `MFC42u!__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z` at `0x14003b3e0`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x14003b27f`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x14003b27f`
- `MFC42u!__imp_?MDIGetActive@CMDIFrameWnd@@QEBAPEAVCMDIChildWnd@@PEAH@Z` at `0x14003b2fc`
- `MFC42u!__imp_?MDIGetActive@CMDIFrameWnd@@QEBAPEAVCMDIChildWnd@@PEAH@Z` at `0x14003b2fc`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x14003b40f`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x14003b4c6`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x14003b40f`
- `MFC42u!__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z` at `0x14003b4c6`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14003b489`
- `MFC42u!__imp_?SetBkMode@CDC@@QEAAHH@Z` at `0x14003b489`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMenuBar::OnCustomDraw(CMenuBar *this, struct tagNMHDR *a2, __int64 *a3)
{
  struct CWnd *v6; // rax
  int v7; // ebx
  int v8; // esi
  int v9; // ebx
  int v10; // r13d
  DWORD Layout; // eax
  DWORD v12; // ebx
  int v13; // edi
  HDC *v14; // r13
  struct CPen *v15; // rsi
  __int64 v16; // rdi
  void (__fastcall *v17)(HDC *, _QWORD); // rbx
  COLORREF TextColor; // eax
  COLORREF BkColor; // eax
  const struct CString *MenuItemText; // rax
  struct tagRECT rcDst; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT v22; // [rsp+60h] [rbp-20h] BYREF

  if ( a2 )
  {
    if ( CWnd::FromHandle(a2->hwndFrom) == this )
    {
      if ( LODWORD(a2[1].hwndFrom) == 1 )
      {
        *a3 = 32;
      }
      else if ( LODWORD(a2[1].hwndFrom) == 65537 )
      {
        if ( a2[2].idFrom == 21508 )
        {
          if ( *((_BYTE *)this + 354) )
          {
            v6 = CMDIFrameWnd::MDIGetActive(*((CMDIFrameWnd **)this + 32), 0);
            CMenuBar::GetMaxedChildIcon(this, v6);
          }
          if ( *((_QWORD *)this + 43) )
          {
            CopyRect(&rcDst, (const RECT *)&a2[1].code);
            v7 = rcDst.right - rcDst.left;
            v8 = (v7 - GetSystemMetrics(49)) / 2;
            v9 = rcDst.bottom - rcDst.top;
            v10 = (v9 - GetSystemMetrics(50) + 1) / 2;
            Layout = GetLayout((HDC)a2[1].idFrom);
            v12 = Layout;
            v13 = Layout & 1;
            if ( (Layout & 1) != 0 )
              SetLayout((HDC)a2[1].idFrom, Layout | 8);
            DrawIconEx((HDC)a2[1].idFrom, v8 + rcDst.left, v10 + rcDst.top, *((HICON *)this + 43), 0, 0, 0, 0, 3u);
            if ( v13 )
              SetLayout((HDC)a2[1].idFrom, v12);
          }
        }
        if ( (a2[2].code & 0x40) != 0
          && *((_BYTE *)this + 408)
          && (v14 = (HDC *)CDC::FromHandle((HDC)a2[1].idFrom)) != 0 )
        {
          CopyRect(&v22, (const RECT *)&a2[1].code);
          v15 = CDC::SelectObject((CDC *)v14, (CMenuBar *)((char *)this + 376));
          RoundRect(v14[1], v22.left, v22.top, v22.right, v22.bottom, 6, 6);
          v16 = (*((__int64 (__fastcall **)(HDC *, char *))*v14 + 12))(v14, (char *)this + 392);
          v17 = (void (__fastcall *)(HDC *, _QWORD))*((_QWORD *)*v14 + 14);
          TextColor = GetTextColor(v14[2]);
          v17(v14, TextColor);
          BkColor = GetBkColor(v14[2]);
          CDC::SetBkMode((CDC *)v14, BkColor);
          MenuItemText = (const struct CString *)CMenuBar::GetMenuItemText(this, &rcDst, LODWORD(a2[2].idFrom));
          CDC::DrawTextW((CDC *)v14, MenuItemText, &v22, 0x25u);
          CString::~CString(&rcDst);
          CDC::SelectObject((CDC *)v14, v15);
          (*((void (__fastcall **)(HDC *, __int64))*v14 + 12))(v14, v16);
          *a3 = 4;
        }
        else
        {
          *a3 = 0;
        }
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_7a02f1ec600930346f410dec2780ba23_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14003b240  test    rdx, rdx
0x14003b243  jz      locret_14003B517
0x14003b249  mov     [rsp-38h+arg_18], rbx
0x14003b24e  push    rbp
0x14003b24f  push    rsi
0x14003b250  push    rdi
0x14003b251  push    r12
0x14003b253  push    r13
0x14003b255  push    r14
0x14003b257  push    r15
0x14003b259  mov     rbp, rsp
0x14003b25c  sub     rsp, 80h
0x14003b263  mov     rax, cs:__security_cookie
0x14003b26a  xor     rax, rsp
0x14003b26d  mov     [rbp+var_10], rax
0x14003b271  mov     r12, r8
0x14003b274  mov     r14, rdx
0x14003b277  mov     r15, rcx
0x14003b27a  xor     esi, esi
0x14003b27c  mov     rcx, [rdx]
0x14003b27f  call    cs:__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x14003b285  cmp     rax, r15
0x14003b288  jz      short loc_14003B2C3
0x14003b28a  lea     rax, WPP_GLOBAL_Control
0x14003b291  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b298  cmp     rcx, rax
0x14003b29b  jz      loc_14003B4F1
0x14003b2a1  cmp     byte ptr [rcx+19h], 2
0x14003b2a5  jb      loc_14003B4F1
0x14003b2ab  lea     edx, [rsi+0Ah]
0x14003b2ae  lea     r8, WPP_7a02f1ec600930346f410dec2780ba23_Traceguids
0x14003b2b5  mov     rcx, [rcx+10h]
0x14003b2b9  call    WPP_SF_
0x14003b2be  jmp     loc_14003B4F1
0x14003b2c3  mov     ecx, [r14+18h]
0x14003b2c7  sub     ecx, 1
0x14003b2ca  jz      loc_14003B4E9
0x14003b2d0  cmp     ecx, 10000h
0x14003b2d6  jnz     loc_14003B4F1
0x14003b2dc  cmp     qword ptr [r14+38h], 5404h
0x14003b2e4  jnz     loc_14003B3CC
0x14003b2ea  cmp     [r15+162h], sil
0x14003b2f1  jz      short loc_14003B30D
0x14003b2f3  xor     edx, edx
0x14003b2f5  mov     rcx, [r15+100h]
0x14003b2fc  call    cs:__imp_?MDIGetActive@CMDIFrameWnd@@QEBAPEAVCMDIChildWnd@@PEAH@Z; CMDIFrameWnd::MDIGetActive(int *)
0x14003b302  mov     rdx, rax; struct CWnd *
0x14003b305  mov     rcx, r15; this
0x14003b308  call    ?GetMaxedChildIcon@CMenuBar@@IEAAXPEAVCWnd@@@Z; CMenuBar::GetMaxedChildIcon(CWnd *)
0x14003b30d  cmp     [r15+158h], rsi
0x14003b314  jz      loc_14003B3CC
0x14003b31a  lea     rdx, [r14+28h]; lprcSrc
0x14003b31e  lea     rcx, [rbp+rcDst]; lprcDst
0x14003b322  call    cs:__imp_CopyRect
0x14003b328  mov     ebx, [rbp+rcDst.right]
0x14003b32b  sub     ebx, [rbp+rcDst.left]
0x14003b32e  mov     ecx, 31h ; '1'; nIndex
0x14003b333  call    cs:__imp_GetSystemMetrics
0x14003b339  sub     ebx, eax
0x14003b33b  mov     eax, ebx
0x14003b33d  cdq
0x14003b33e  sub     eax, edx
0x14003b340  sar     eax, 1
0x14003b342  mov     esi, eax
0x14003b344  mov     ebx, [rbp+rcDst.bottom]
0x14003b347  sub     ebx, [rbp+rcDst.top]
0x14003b34a  mov     ecx, 32h ; '2'; nIndex
0x14003b34f  call    cs:__imp_GetSystemMetrics
0x14003b355  sub     ebx, eax
0x14003b357  lea     eax, [rbx+1]
0x14003b35a  cdq
0x14003b35b  sub     eax, edx
0x14003b35d  sar     eax, 1
0x14003b35f  mov     r13d, eax
0x14003b362  mov     rcx, [r14+20h]; hdc
0x14003b366  call    cs:__imp_GetLayout
0x14003b36c  mov     ebx, eax
0x14003b36e  mov     edi, eax
0x14003b370  and     edi, 1
0x14003b373  jz      short loc_14003B384
0x14003b375  mov     edx, eax
0x14003b377  or      edx, 8; l
0x14003b37a  mov     rcx, [r14+20h]; hdc
0x14003b37e  call    cs:__imp_SetLayout
0x14003b384  mov     r8d, [rbp+rcDst.top]
0x14003b388  add     r8d, r13d; yTop
0x14003b38b  mov     edx, [rbp+rcDst.left]
0x14003b38e  add     edx, esi; xLeft
0x14003b390  mov     [rsp+80h+diFlags], 3; diFlags
0x14003b398  xor     esi, esi
0x14003b39a  mov     [rsp+80h+hbrFlickerFreeDraw], rsi; hbrFlickerFreeDraw
0x14003b39f  mov     [rsp+80h+istepIfAniCur], esi; istepIfAniCur
0x14003b3a3  mov     [rsp+80h+cyWidth], esi; cyWidth
0x14003b3a7  mov     [rsp+80h+cxWidth], esi; cxWidth
0x14003b3ab  mov     r9, [r15+158h]; hIcon
0x14003b3b2  mov     rcx, [r14+20h]; hdc
0x14003b3b6  call    cs:__imp_DrawIconEx
0x14003b3bc  test    edi, edi
0x14003b3be  jz      short loc_14003B3CC
0x14003b3c0  mov     edx, ebx; l
0x14003b3c2  mov     rcx, [r14+20h]; hdc
0x14003b3c6  call    cs:__imp_SetLayout
0x14003b3cc  test    byte ptr [r14+40h], 40h
0x14003b3d1  jz      short loc_14003B3EE
0x14003b3d3  cmp     [r15+198h], sil
0x14003b3da  jz      short loc_14003B3EE
0x14003b3dc  mov     rcx, [r14+20h]
0x14003b3e0  call    cs:__imp_?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x14003b3e6  mov     r13, rax
0x14003b3e9  test    rax, rax
0x14003b3ec  jnz     short loc_14003B3F7
0x14003b3ee  mov     [r12], rsi
0x14003b3f2  jmp     loc_14003B4F1
0x14003b3f7  lea     rdx, [r14+28h]; lprcSrc
0x14003b3fb  lea     rcx, [rbp+var_20]; lprcDst
0x14003b3ff  call    cs:__imp_CopyRect
0x14003b405  lea     rdx, [r15+178h]
0x14003b40c  mov     rcx, r13
0x14003b40f  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x14003b415  mov     rsi, rax
0x14003b418  mov     eax, 6
0x14003b41d  mov     [rsp+80h+istepIfAniCur], eax; height
0x14003b421  mov     [rsp+80h+cyWidth], eax; width
0x14003b425  mov     ecx, [rbp+var_20.bottom]
0x14003b428  mov     [rsp+80h+cxWidth], ecx; bottom
0x14003b42c  mov     r9d, [rbp+var_20.right]; right
0x14003b430  mov     r8d, [rbp+var_20.top]; top
0x14003b434  mov     edx, [rbp+var_20.left]; left
0x14003b437  mov     rcx, [r13+8]; hdc
0x14003b43b  call    cs:__imp_RoundRect
0x14003b441  mov     rcx, [r13+0]
0x14003b445  lea     rdx, [r15+188h]
0x14003b44c  mov     rax, [rcx+60h]
0x14003b450  mov     rcx, r13
0x14003b453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b458  mov     rdi, rax
0x14003b45b  mov     rcx, [r13+0]
0x14003b45f  mov     rbx, [rcx+70h]
0x14003b463  mov     rcx, [r13+10h]; hdc
0x14003b467  call    cs:__imp_GetTextColor
0x14003b46d  mov     edx, eax
0x14003b46f  mov     rcx, r13
0x14003b472  mov     rax, rbx
0x14003b475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b47a  mov     rcx, [r13+10h]; hdc
0x14003b47e  call    cs:__imp_GetBkColor
0x14003b484  mov     edx, eax
0x14003b486  mov     rcx, r13
0x14003b489  call    cs:__imp_?SetBkMode@CDC@@QEAAHH@Z; CDC::SetBkMode(int)
0x14003b48f  mov     r8d, [r14+38h]
0x14003b493  lea     rdx, [rbp+rcDst]
0x14003b497  mov     rcx, r15
0x14003b49a  call    ?GetMenuItemText@CMenuBar@@IEAA?AVCString@@K@Z; CMenuBar::GetMenuItemText(ulong)
0x14003b49f  nop
0x14003b4a0  mov     r9d, 25h ; '%'; unsigned int
0x14003b4a6  lea     r8, [rbp+var_20]; struct tagRECT *
0x14003b4aa  mov     rdx, rax; struct CString *
0x14003b4ad  mov     rcx, r13; this
0x14003b4b0  call    ?DrawTextW@CDC@@QEAAHAEBVCString@@PEAUtagRECT@@I@Z; CDC::DrawTextW(CString const &,tagRECT *,uint)
0x14003b4b5  nop
0x14003b4b6  lea     rcx, [rbp+rcDst]
0x14003b4ba  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14003b4c0  mov     rdx, rsi
0x14003b4c3  mov     rcx, r13
0x14003b4c6  call    cs:__imp_?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x14003b4cc  mov     rax, [r13+0]
0x14003b4d0  mov     rdx, rdi
0x14003b4d3  mov     rcx, r13
0x14003b4d6  mov     rax, [rax+60h]
0x14003b4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b4df  mov     qword ptr [r12], 4
0x14003b4e7  jmp     short loc_14003B4F1
0x14003b4e9  mov     qword ptr [r12], 20h ; ' '
0x14003b4f1  mov     rcx, [rbp+var_10]
0x14003b4f5  xor     rcx, rsp; StackCookie
0x14003b4f8  call    __security_check_cookie
0x14003b4fd  mov     rbx, [rsp+80h+arg_18]
0x14003b505  add     rsp, 80h
0x14003b50c  pop     r15
0x14003b50e  pop     r14
0x14003b510  pop     r13
0x14003b512  pop     r12
0x14003b514  pop     rdi
0x14003b515  pop     rsi
0x14003b516  pop     rbp
0x14003b517  retn
```
