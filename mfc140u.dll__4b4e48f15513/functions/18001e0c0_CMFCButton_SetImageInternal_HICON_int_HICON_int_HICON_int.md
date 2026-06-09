# CMFCButton::SetImageInternal(HICON__ *,int,HICON__ *,int,HICON__ *,int)

- ea: `0x18001e0c0`
- end: `0x18001e3c9`
- name: `?SetImageInternal@CMFCButton@@IEAAXPEAUHICON__@@H0H0H@Z`
- size: `777`
- prototype: `void __fastcall(CMFCButton *this, HICON__ *hIconCold, int bAutoDestroy, HICON__ *hIconHot, int bChecked, HICON__ *hIconDisabled, int bAlphaBlend)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001dfc0`
- `0x18001e040`
- `0x18001fe90`
- `0x180020040`

## callees

- `0x18001e0c0`
- `0x18001f7f0`
- `0x18006cab0`
- `0x180175270`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802c4640`

## import_xrefs

- `USER32!CopyImage` at `0x18001e1f9`
- `USER32!CopyImage` at `0x18001e1f9`
- `USER32!GetIconInfo` at `0x18001e186`
- `USER32!GetIconInfo` at `0x18001e186`
- `USER32!FillRect` at `0x18001e267`
- `USER32!FillRect` at `0x18001e267`
- `USER32!DestroyIcon` at `0x18001e380`
- `USER32!DestroyIcon` at `0x18001e38e`
- `USER32!DestroyIcon` at `0x18001e39c`
- `USER32!DestroyIcon` at `0x18001e380`
- `USER32!DestroyIcon` at `0x18001e38e`
- `USER32!DestroyIcon` at `0x18001e39c`
- `USER32!DrawIconEx` at `0x18001e2a5`
- `USER32!DrawIconEx` at `0x18001e2a5`
- `GDI32!DeleteDC` at `0x18001e2e9`
- `GDI32!DeleteDC` at `0x18001e2e9`
- `GDI32!DeleteObject` at `0x18001e2c0`
- `GDI32!DeleteObject` at `0x18001e2f8`
- `GDI32!DeleteObject` at `0x18001e302`
- `GDI32!DeleteObject` at `0x18001e2c0`
- `GDI32!DeleteObject` at `0x18001e2f8`
- `GDI32!DeleteObject` at `0x18001e302`
- `GDI32!SelectObject` at `0x18001e212`
- `GDI32!SelectObject` at `0x18001e2b7`
- `GDI32!SelectObject` at `0x18001e212`
- `GDI32!SelectObject` at `0x18001e2b7`
- `GDI32!CreateCompatibleDC` at `0x18001e1d3`
- `GDI32!CreateCompatibleDC` at `0x18001e1d3`
- `GDI32!GetObjectW` at `0x18001e199`
- `GDI32!GetObjectW` at `0x18001e199`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CMFCButton::SetImageInternal(
        CMFCButton *this,
        HICON hIconCold,
        int bAutoDestroy,
        HICON hIconHot,
        int bChecked,
        HICON hIconDisabled,
        int bAlphaBlend)
{
  HICON v7; // r12
  HICON v8; // r15
  CMFCButton *v9; // r13
  int v10; // ebx
  HICON__ *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  CMFCToolBarImages *v14; // r15
  HDC CompatibleDC; // rax
  HANDLE v16; // rax
  void *v17; // r12
  HGDIOBJ v18; // r13
  int cy; // edx
  int cx; // ecx
  HDC v21; // rax
  CDC dcMem; // [rsp+70h] [rbp-71h] BYREF
  HICON__ *v26; // [rsp+90h] [rbp-51h]
  _ICONINFO info; // [rsp+98h] [rbp-49h] BYREF
  tagBITMAP bmp; // [rsp+B8h] [rbp-29h] BYREF
  RECT rc; // [rsp+D8h] [rbp-9h] BYREF

  v7 = hIconHot;
  v26 = hIconHot;
  v8 = hIconCold;
  v9 = this;
  CMFCButton::ClearImages(this, bChecked);
  if ( !v8 )
    return;
  v10 = 0;
  do
  {
    v11 = hIconDisabled;
    if ( v10 == 1 )
      v11 = v7;
    if ( !v10 )
      v11 = v8;
    if ( bChecked )
    {
      if ( !v10 )
      {
        v12 = 1568;
        goto LABEL_16;
      }
      v12 = 2384;
      v13 = 1976;
    }
    else
    {
      if ( !v10 )
      {
        v12 = 344;
        goto LABEL_16;
      }
      v12 = 1160;
      v13 = 752;
    }
    if ( v10 == 1 )
      v12 = v13;
LABEL_16:
    v14 = (CMFCToolBarImages *)((char *)v9 + v12);
    if ( v11 )
    {
      GetIconInfo(v11, &info);
      GetObjectW(info.hbmColor, 32, &bmp);
      v9->m_sizeImage.cx = bmp.bmWidth;
      v9->m_sizeImage.cy = bmp.bmHeight;
      if ( !v10 )
      {
        dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
        memset(&dcMem.m_hDC, 0, 20);
        CompatibleDC = CreateCompatibleDC(0);
        CDC::Attach(&dcMem, CompatibleDC);
        v16 = CopyImage(info.hbmColor, 0, 0, 0, 0x2000u);
        v17 = v16;
        if ( v16 )
        {
          v18 = SelectObject(dcMem.m_hDC, v16);
          if ( !afxGlobalData.m_bInitialized )
          {
            AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
            afxGlobalData.m_bInitialized = 1;
          }
          cy = this->m_sizeImage.cy;
          cx = this->m_sizeImage.cx;
          rc.left = 0;
          rc.top = 0;
          rc.right = cx;
          rc.bottom = cy;
          FillRect(dcMem.m_hDC, &rc, (HBRUSH)afxGlobalData.brBtnFace.m_hObject);
          DrawIconEx(dcMem.m_hDC, 0, 0, v11, this->m_sizeImage.cx, this->m_sizeImage.cy, 0, 0, 3u);
          if ( v18 )
            SelectObject(dcMem.m_hDC, v18);
          DeleteObject(v17);
          v9 = this;
        }
        dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( dcMem.m_hDC )
        {
          v21 = CDC::Detach(&dcMem);
          DeleteDC(v21);
        }
        v7 = v26;
      }
      DeleteObject(info.hbmColor);
      DeleteObject(info.hbmMask);
      v14->m_sizeImage = *(CSize *)&bmp.bmWidth;
      if ( !bAlphaBlend )
      {
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        if ( afxGlobalData.clrBtnFace != v14->m_clrTransparent )
          v14->m_clrTransparent = afxGlobalData.clrBtnFace;
      }
      CMFCToolBarImages::AddIcon(v14, v11, bAlphaBlend);
    }
    ++v10;
    v8 = hIconCold;
  }
  while ( v10 < (hIconDisabled != 0) + 2 );
  if ( bAutoDestroy )
  {
    DestroyIcon(hIconCold);
    if ( v7 )
      DestroyIcon(v7);
    if ( hIconDisabled )
      DestroyIcon(hIconDisabled);
  }
}

```

## disassembly

```asm
0x18001e0c0  mov     [rsp-8+arg_10], rbx
0x18001e0c5  push    rbp
0x18001e0c6  push    rsi
0x18001e0c7  push    rdi
0x18001e0c8  push    r12
0x18001e0ca  push    r13
0x18001e0cc  push    r14
0x18001e0ce  push    r15
0x18001e0d0  lea     rbp, [rsp-0Fh]
0x18001e0d5  sub     rsp, 0F0h
0x18001e0dc  mov     rax, cs:__security_cookie
0x18001e0e3  xor     rax, rsp
0x18001e0e6  mov     [rbp+3Fh+var_38], rax
0x18001e0ea  mov     r12, hIconHot
0x18001e0ed  mov     [rbp+3Fh+var_90], hIconHot
0x18001e0f1  mov     [rsp+120h+var_D0], bAutoDestroy
0x18001e0f6  mov     r15, hIconCold
0x18001e0f9  mov     [rbp+3Fh+hIcon], hIconCold
0x18001e0fd  mov     r13, this
0x18001e100  mov     [rsp+120h+var_C8], this
0x18001e105  mov     r14, [rbp+3Fh+arg_28]
0x18001e109  mov     edx, [rbp+3Fh+arg_20]; bChecked
0x18001e10c  call    ?ClearImages@CMFCButton@@IEAAXH@Z; CMFCButton::ClearImages(int)
0x18001e111  test    r15, r15
0x18001e114  jz      loc_18001E3A2
0x18001e11a  mov     rax, r14
0x18001e11d  neg     rax
0x18001e120  sbb     esi, esi
0x18001e122  neg     esi
0x18001e124  add     esi, 2
0x18001e127  xor     ebx, ebx
0x18001e129  mov     rdi, r14
0x18001e12c  cmp     ebx, 1
0x18001e12f  cmovz   rdi, r12
0x18001e133  test    ebx, ebx
0x18001e135  cmovz   rdi, r15
0x18001e139  cmp     [rbp+3Fh+arg_20], 0
0x18001e13d  jz      short loc_18001E156
0x18001e13f  test    ebx, ebx
0x18001e141  jnz     short loc_18001E14A
0x18001e143  mov     eax, 620h
0x18001e148  jmp     short loc_18001E172
0x18001e14a  mov     eax, 950h
0x18001e14f  mov     ecx, 7B8h
0x18001e154  jmp     short loc_18001E16B
0x18001e156  test    ebx, ebx
0x18001e158  jnz     short loc_18001E161
0x18001e15a  mov     eax, 158h
0x18001e15f  jmp     short loc_18001E172
0x18001e161  mov     eax, 488h
0x18001e166  mov     ecx, 2F0h
0x18001e16b  cmp     ebx, 1
0x18001e16e  cmovz   rax, this
0x18001e172  lea     r15, [rax+r13]
0x18001e176  test    rdi, rdi
0x18001e179  jz      loc_18001E368
0x18001e17f  lea     hIconCold, [rbp+3Fh+info]; piconinfo
0x18001e183  mov     this, rdi; hIcon
0x18001e186  call    cs:__imp_GetIconInfo
0x18001e18c  lea     r8, [rbp+3Fh+bmp]; pv
0x18001e190  mov     edx, 20h ; ' '; c
0x18001e195  mov     this, [rbp+3Fh+info.hbmColor]; h
0x18001e199  call    cs:__imp_GetObjectW
0x18001e19f  mov     eax, [rbp+3Fh+bmp.bmWidth]
0x18001e1a2  mov     [r13+148h], eax
0x18001e1a9  mov     eax, [rbp+3Fh+bmp.bmHeight]
0x18001e1ac  mov     [r13+14Ch], eax
0x18001e1b3  test    ebx, ebx
0x18001e1b5  jnz     loc_18001E2F4
0x18001e1bb  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18001e1c2  mov     [rbp+3Fh+dcMem.__vftable], rax
0x18001e1c6  xorps   xmm0, xmm0
0x18001e1c9  movdqu  xmmword ptr [rbp+3Fh+dcMem.m_hDC], xmm0
0x18001e1ce  and     [rbp+3Fh+dcMem.m_bPrinting], ebx
0x18001e1d1  xor     ecx, ecx; hdc
0x18001e1d3  call    cs:__imp_CreateCompatibleDC
0x18001e1d9  mov     hIconCold, rax; hDC
0x18001e1dc  lea     this, [rbp+3Fh+dcMem]; this
0x18001e1e0  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18001e1e5  mov     [rsp+120h+flags], 2000h; flags
0x18001e1ed  xor     r9d, r9d; cy
0x18001e1f0  xor     bAutoDestroy, bAutoDestroy; cx
0x18001e1f3  xor     edx, edx; type
0x18001e1f5  mov     this, [rbp+3Fh+info.hbmColor]; h
0x18001e1f9  call    cs:__imp_CopyImage
0x18001e1ff  mov     r12, rax
0x18001e202  test    rax, rax
0x18001e205  jz      loc_18001E2CB
0x18001e20b  mov     hIconCold, rax; h
0x18001e20e  mov     this, [rbp+3Fh+dcMem.m_hDC]; hdc
0x18001e212  call    cs:__imp_SelectObject
0x18001e218  mov     r13, rax
0x18001e21b  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x18001e221  jnz     short loc_18001E239
0x18001e223  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18001e22a  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18001e22f  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18001e239  mov     rax, [rsp+120h+var_C8]
0x18001e23e  mov     edx, [rax+14Ch]
0x18001e244  mov     ecx, [rax+148h]
0x18001e24a  and     [rbp+3Fh+rc.left], 0
0x18001e24e  and     [rbp+3Fh+rc.top], 0
0x18001e252  mov     [rbp+3Fh+rc.right], ecx
0x18001e255  mov     [rbp+3Fh+rc.bottom], edx
0x18001e258  mov     r8, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.brBtnFace.m_hObject; hbr
0x18001e25f  lea     hIconCold, [rbp+3Fh+rc]; lprc
0x18001e263  mov     this, [rbp+3Fh+dcMem.m_hDC]; hDC
0x18001e267  call    cs:__imp_FillRect
0x18001e26d  mov     this, [rsp+120h+var_C8]
0x18001e272  mov     eax, [this+14Ch]
0x18001e278  mov     ecx, [this+148h]
0x18001e27e  mov     [rsp+120h+diFlags], 3; diFlags
0x18001e286  and     [rsp+120h+var_E8], 0
0x18001e28c  and     [rsp+120h+var_F0], 0
0x18001e291  mov     [rsp+120h+cyWidth], eax; cyWidth
0x18001e295  mov     [rsp+120h+flags], ecx; cxWidth
0x18001e299  mov     hIconHot, rdi; hIcon
0x18001e29c  xor     bAutoDestroy, bAutoDestroy; yTop
0x18001e29f  xor     edx, edx; xLeft
0x18001e2a1  mov     this, [rbp+3Fh+dcMem.m_hDC]; hdc
0x18001e2a5  call    cs:__imp_DrawIconEx
0x18001e2ab  test    r13, r13
0x18001e2ae  jz      short loc_18001E2BD
0x18001e2b0  mov     hIconCold, r13; h
0x18001e2b3  mov     this, [rbp+3Fh+dcMem.m_hDC]; hdc
0x18001e2b7  call    cs:__imp_SelectObject
0x18001e2bd  mov     this, r12; ho
0x18001e2c0  call    cs:__imp_DeleteObject
0x18001e2c6  mov     r13, [rsp+120h+var_C8]
0x18001e2cb  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18001e2d2  mov     [rbp+3Fh+dcMem.__vftable], rax
0x18001e2d6  cmp     [rbp+3Fh+dcMem.m_hDC], 0
0x18001e2db  jz      short loc_18001E2F0
0x18001e2dd  lea     this, [rbp+3Fh+dcMem]; this
0x18001e2e1  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18001e2e6  mov     this, rax; hdc
0x18001e2e9  call    cs:__imp_DeleteDC
0x18001e2ef  nop
0x18001e2f0  mov     r12, [rbp+3Fh+var_90]
0x18001e2f4  mov     this, [rbp+3Fh+info.hbmColor]; ho
0x18001e2f8  call    cs:__imp_DeleteObject
0x18001e2fe  mov     this, [rbp+3Fh+info.hbmMask]; ho
0x18001e302  call    cs:__imp_DeleteObject
0x18001e308  mov     eax, [rbp+3Fh+bmp.bmWidth]
0x18001e30b  mov     dword ptr [rsp+120h+var_C0], eax
0x18001e30f  mov     eax, [rbp+3Fh+bmp.bmHeight]
0x18001e312  mov     dword ptr [rbp+3Fh+var_C0+4], eax
0x18001e315  mov     rax, [rsp+120h+var_C0]
0x18001e31a  mov     [r15+68h], rax
0x18001e31e  cmp     [rbp+3Fh+arg_30], 0
0x18001e322  jnz     short loc_18001E359
0x18001e324  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18001e32b  jnz     short loc_18001E343
0x18001e32d  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18001e334  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18001e339  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18001e343  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnFace; AFX_GLOBAL_DATA afxGlobalData ...
0x18001e349  cmp     eax, [r15+0D8h]
0x18001e350  jz      short loc_18001E359
0x18001e352  mov     [r15+0D8h], eax
0x18001e359  mov     bAutoDestroy, [rbp+3Fh+arg_30]; bAlphaBlend
0x18001e35d  mov     hIconCold, rdi; hIcon
0x18001e360  mov     this, r15; this
0x18001e363  call    ?AddIcon@CMFCToolBarImages@@QEAAHPEAUHICON__@@H@Z; CMFCToolBarImages::AddIcon(HICON__ *,int)
0x18001e368  inc     ebx
0x18001e36a  cmp     ebx, esi
0x18001e36c  mov     r15, [rbp+3Fh+hIcon]
0x18001e370  jl      loc_18001E129
0x18001e376  cmp     [rsp+120h+var_D0], 0
0x18001e37b  jz      short loc_18001E3A2
0x18001e37d  mov     this, r15; hIcon
0x18001e380  call    cs:__imp_DestroyIcon
0x18001e386  test    r12, r12
0x18001e389  jz      short loc_18001E394
0x18001e38b  mov     this, r12; hIcon
0x18001e38e  call    cs:__imp_DestroyIcon
0x18001e394  test    r14, r14
0x18001e397  jz      short loc_18001E3A2
0x18001e399  mov     this, r14; hIcon
0x18001e39c  call    cs:__imp_DestroyIcon
0x18001e3a2  mov     this, [rbp+3Fh+var_38]
0x18001e3a6  xor     this, rsp; StackCookie
0x18001e3a9  call    __security_check_cookie
0x18001e3ae  mov     rbx, [rsp+120h+arg_10]
0x18001e3b6  add     rsp, 0F0h
0x18001e3bd  pop     r15
0x18001e3bf  pop     r14
0x18001e3c1  pop     r13
0x18001e3c3  pop     r12
0x18001e3c5  pop     rdi
0x18001e3c6  pop     rsi
0x18001e3c7  pop     rbp
0x18001e3c8  retn
```
