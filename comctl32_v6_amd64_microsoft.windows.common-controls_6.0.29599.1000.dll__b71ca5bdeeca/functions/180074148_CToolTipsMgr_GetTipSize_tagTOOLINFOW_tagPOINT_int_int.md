# CToolTipsMgr::GetTipSize(tagTOOLINFOW *,tagPOINT *,int *,int *)

- ea: `0x180074148`
- end: `0x1800745e5`
- name: `?GetTipSize@CToolTipsMgr@@AEAAXPEAUtagTOOLINFOW@@PEAUtagPOINT@@PEAH2@Z`
- size: `1181`
- prototype: `void __usercall(CToolTipsMgr *__hidden this@<rcx>, struct tagTOOLINFOW *@<rdx>, struct tagPOINT *@<r8>, int *@<r9>, int *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18006fd80`
- `0x18007370c`
- `0x1800c0854`

## callees

- `0x180019b30`
- `0x18004f420`
- `0x1800725b4`
- `0x180073340`
- `0x180074148`
- `0x180074a40`
- `0x180074c1c`
- `0x1800d7d2c`
- `0x180114520`
- `0x180114ebc`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074287`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074545`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074287`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180074545`
- `GDI32!SelectObject` at `0x1800741d9`
- `GDI32!SelectObject` at `0x18007438d`
- `GDI32!SelectObject` at `0x1800741d9`
- `GDI32!SelectObject` at `0x18007438d`
- `GDI32!DeleteDC` at `0x180074396`
- `GDI32!DeleteDC` at `0x180074396`
- `GDI32!CreateCompatibleDC` at `0x1800741a9`
- `GDI32!CreateCompatibleDC` at `0x1800741a9`
- `USER32!GetMonitorInfoW` at `0x18007446c`
- `USER32!GetMonitorInfoW` at `0x18007446c`
- `USER32!GetMessagePos` at `0x18007442d`
- `USER32!GetMessagePos` at `0x18007442d`
- `USER32!GetDC` at `0x180074194`
- `USER32!GetDC` at `0x180074194`
- `USER32!GetSystemMetrics` at `0x1800744ef`
- `USER32!GetSystemMetrics` at `0x1800744fe`
- `USER32!GetSystemMetrics` at `0x1800744ef`
- `USER32!GetSystemMetrics` at `0x1800744fe`
- `USER32!SetRect` at `0x18007422a`
- `USER32!SetRect` at `0x1800744ab`
- `USER32!SetRect` at `0x18007422a`
- `USER32!SetRect` at `0x1800744ab`
- `USER32!ReleaseDC` at `0x1800741b9`
- `USER32!ReleaseDC` at `0x1800741b9`
- `USER32!MonitorFromPoint` at `0x180074458`
- `USER32!MonitorFromPoint` at `0x180074458`

## pseudocode

```c
void __fastcall CToolTipsMgr::GetTipSize(
        CToolTipsMgr *this,
        struct tagTOOLINFOW *a2,
        struct tagPOINT *a3,
        int *a4,
        int *a5)
{
  HDC DC; // rax
  HDC v9; // rdi
  HDC CompatibleDC; // rsi
  void *v11; // rdx
  LONG v12; // edi
  int *v13; // r14
  int v14; // ecx
  int x; // r15d
  struct IControlMarkup *v16; // rax
  int v17; // r15d
  HWND hwnd; // rcx
  UINT v19; // eax
  char v20; // r14
  struct IControlMarkup *CurToolBestMarkup; // rax
  __int64 v22; // rax
  DWORD MessagePos; // eax
  LONG v24; // ecx
  LONG y; // eax
  HMONITOR v26; // rax
  int v27; // r9d
  struct _IMAGELIST *v28; // rcx
  int v29; // ecx
  struct IControlMarkup *v30; // rax
  HGDIOBJ h; // [rsp+38h] [rbp-A9h]
  _QWORD v34[2]; // [rsp+50h] [rbp-91h] BYREF
  int v35; // [rsp+60h] [rbp-81h]
  int v36; // [rsp+68h] [rbp-79h]
  HDC v37; // [rsp+70h] [rbp-71h]
  struct tagRECT rc; // [rsp+78h] [rbp-69h] BYREF
  unsigned int v39; // [rsp+A0h] [rbp-41h]
  POINT pt; // [rsp+B0h] [rbp-31h] BYREF
  tagMONITORINFO mi; // [rsp+B8h] [rbp-29h] BYREF

  *a4 = 0;
  *a5 = 0;
  DC = GetDC(*((HWND *)this + 1));
  v9 = DC;
  if ( !DC )
    return;
  CompatibleDC = CreateCompatibleDC(DC);
  ReleaseDC(*((HWND *)this + 1), v9);
  if ( !CompatibleDC )
    return;
  v11 = (void *)*((_QWORD *)this + 14);
  h = 0;
  if ( v11 )
    h = SelectObject(CompatibleDC, v11);
  memset_0(v34, 0, 0x58u);
  v34[0] = *((_QWORD *)this + 1);
  v34[1] = a2->uId;
  v35 = -12;
  v37 = CompatibleDC;
  v36 = 1;
  SetRect(&rc, 0, 0, 0, 0);
  v12 = (*((_BYTE *)this + 24) & 2) << 10;
  if ( (unsigned int)CToolTipsMgr::IsRTL(this) )
    v12 |= 0x20000u;
  if ( (a2->uFlags & 0x800) != 0 )
    v12 |= 2u;
  v13 = (int *)((char *)this + 284);
  if ( *((_DWORD *)this + 43) )
  {
    v28 = (struct _IMAGELIST *)*((_QWORD *)this + 24);
    pt.x = 0;
    if ( ImageList_GetIconSize(v28, (int *)this + 71, (int *)&pt) )
      *v13 = MulDiv(*v13, *((_DWORD *)this + 15), 96);
    *v13 += 5;
  }
  else
  {
    *v13 = 0;
  }
  v14 = *((_DWORD *)this + 59);
  if ( v14 == -1 )
  {
    x = v12 | 0x20;
    CToolTipsMgr::SetThemeRenderFlags(this, v12 | 0x20);
    CurToolBestMarkup = CToolTipsMgr::GetCurToolBestMarkup(this);
    (*(void (__fastcall **)(struct IControlMarkup *, HDC, __int64, struct tagRECT *))(*(_QWORD *)CurToolBestMarkup
                                                                                    + 160LL))(
      CurToolBestMarkup,
      CompatibleDC,
      1,
      &rc);
    v22 = *((_QWORD *)this + 13);
    if ( v22 && (*(_BYTE *)(v22 + 4) & 0x20) != 0 )
    {
      pt.x = a3->x;
      y = a3->y;
    }
    else
    {
      MessagePos = GetMessagePos();
      v24 = (__int16)MessagePos;
      y = SHIWORD(MessagePos);
      pt.x = v24;
    }
    pt.y = y;
    memset(&mi, 0, sizeof(mi));
    v26 = MonitorFromPoint(pt, 2u);
    mi.cbSize = 40;
    GetMonitorInfoW(v26, &mi);
    v27 = mi.rcWork.right - *((_DWORD *)this + 63) - *((_DWORD *)this + 61) - *v13 - mi.rcWork.left;
    if ( rc.right - rc.left > v27 )
    {
      SetRect(&rc, 0, 0, v27, 0);
      pt.x = v12;
      CToolTipsMgr::CalcTextSize(this, CompatibleDC, &rc, (unsigned int *)&pt, 1);
      x = pt.x;
    }
  }
  else
  {
    x = v12 | 0x250;
    rc.right = MulDiv(v14, *((_DWORD *)this + 15), 96);
    CToolTipsMgr::SetThemeRenderFlags(this, v12 | 0x250);
    v16 = CToolTipsMgr::GetCurToolBestMarkup(this);
    (*(void (__fastcall **)(struct IControlMarkup *, HDC, __int64, struct tagRECT *))(*(_QWORD *)v16 + 160LL))(
      v16,
      CompatibleDC,
      1,
      &rc);
  }
  *a4 = rc.right;
  *a5 = rc.bottom;
  *((_DWORD *)this + 60) = x;
  v17 = x | 0x400;
  hwnd = a2->hwnd;
  v19 = (a2->uFlags >> 6) & 1;
  v39 = v17;
  v20 = SendNotifyEx(hwnd, -1, 0, v34, v19);
  if ( (v20 & 4) == 0 && !(unsigned int)CToolTipsMgr::RenderTitledTip(this, CompatibleDC, &rc, v17) )
  {
    if ( (v20 & 2) != 0 || v39 != v17 )
    {
      CToolTipsMgr::SetThemeRenderFlags(this, v39);
      v30 = CToolTipsMgr::GetCurToolBestMarkup(this);
      (*(void (__fastcall **)(struct IControlMarkup *, HDC, __int64, struct tagRECT *))(*(_QWORD *)v30 + 160LL))(
        v30,
        CompatibleDC,
        1,
        &rc);
      *a4 = rc.right - rc.left;
      *a5 = rc.bottom - rc.top;
    }
    else if ( rc.right - rc.left != *a4 || rc.bottom - rc.top != *a5 )
    {
      v29 = rc.bottom - rc.top;
      *a4 = rc.right - rc.left;
      *a5 = v29;
    }
    goto LABEL_19;
  }
  *a4 = rc.right - rc.left;
  *a5 = rc.bottom - rc.top;
  if ( (v20 & 4) == 0 )
  {
LABEL_19:
    if ( (v20 & 0x10) != 0 )
    {
      v36 = 2;
      SendNotifyEx(a2->hwnd, -1, 0, v34, (a2->uFlags >> 6) & 1);
    }
  }
  if ( *((_QWORD *)this + 14) )
    SelectObject(CompatibleDC, h);
  DeleteDC(CompatibleDC);
  if ( (v20 & 4) == 0 )
  {
    *a4 += GetSystemMetrics(45);
    *a5 += GetSystemMetrics(46);
  }
}

```

## disassembly

```asm
0x180074148  push    rbp
0x18007414a  push    rbx
0x18007414b  push    rsi
0x18007414c  push    rdi
0x18007414d  push    r12
0x18007414f  push    r13
0x180074151  push    r14
0x180074153  push    r15
0x180074155  lea     rbp, [rsp-17h]
0x18007415a  sub     rsp, 0F8h
0x180074161  mov     rax, cs:__security_cookie
0x180074168  xor     rax, rsp
0x18007416b  mov     [rbp+4Fh+var_50], rax
0x18007416f  mov     r13, [rbp+4Fh+arg_20]
0x180074173  xor     r15d, r15d
0x180074176  mov     [r9], r15d
0x180074179  mov     rbx, rcx
0x18007417c  mov     r12, r9
0x18007417f  mov     [rsp+130h+var_F0], r8
0x180074184  mov     r14, rdx
0x180074187  mov     [rsp+130h+var_100], rdx
0x18007418c  mov     [r13+0], r15d
0x180074190  mov     rcx, [rcx+8]; hWnd
0x180074194  call    cs:__imp_GetDC
0x18007419a  mov     rdi, rax
0x18007419d  test    rax, rax
0x1800741a0  jz      loc_1800743A4
0x1800741a6  mov     rcx, rax; hdc
0x1800741a9  call    cs:__imp_CreateCompatibleDC
0x1800741af  mov     rcx, [rbx+8]; hWnd
0x1800741b3  mov     rdx, rdi; hDC
0x1800741b6  mov     rsi, rax
0x1800741b9  call    cs:__imp_ReleaseDC
0x1800741bf  test    rsi, rsi
0x1800741c2  jz      loc_1800743A4
0x1800741c8  mov     rdx, [rbx+70h]; h
0x1800741cc  mov     [rsp+130h+h], r15
0x1800741d1  test    rdx, rdx
0x1800741d4  jz      short loc_1800741E4
0x1800741d6  mov     rcx, rsi; hdc
0x1800741d9  call    cs:__imp_SelectObject
0x1800741df  mov     [rsp+130h+h], rax
0x1800741e4  xor     edx, edx; Val
0x1800741e6  lea     rcx, [rsp+130h+var_E0]; void *
0x1800741eb  lea     r8d, [rdx+58h]; Size
0x1800741ef  call    memset_0
0x1800741f4  mov     rcx, [rbx+8]
0x1800741f8  xor     r9d, r9d; xRight
0x1800741fb  mov     [rsp+130h+var_E0], rcx
0x180074200  xor     r8d, r8d; yTop
0x180074203  mov     rcx, [r14+10h]
0x180074207  xor     edx, edx; xLeft
0x180074209  mov     [rsp+130h+var_D8], rcx
0x18007420e  lea     rcx, [rbp+4Fh+rc]; lprc
0x180074212  mov     [rsp+130h+var_D0], 0FFFFFFF4h
0x18007421a  mov     [rbp+4Fh+var_C0], rsi
0x18007421e  mov     [rbp+4Fh+var_C8], 1
0x180074225  mov     [rsp+130h+yBottom], r15d; yBottom
0x18007422a  call    cs:__imp_SetRect
0x180074230  movzx   edi, byte ptr [rbx+18h]
0x180074234  mov     rcx, rbx; this
0x180074237  and     edi, 2
0x18007423a  shl     edi, 0Ah
0x18007423d  call    ?IsRTL@CToolTipsMgr@@AEBAHXZ; CToolTipsMgr::IsRTL(void)
0x180074242  test    eax, eax
0x180074244  jnz     loc_18007450D
0x18007424a  test    dword ptr [r14+4], 800h
0x180074252  jnz     loc_180074516
0x180074258  lea     r14, [rbx+11Ch]
0x18007425f  cmp     [rbx+0ACh], r15d
0x180074266  jnz     loc_18007451E
0x18007426c  mov     [r14], r15d
0x18007426f  mov     ecx, [rbx+0ECh]; nNumber
0x180074275  cmp     ecx, 0FFFFFFFFh
0x180074278  jz      loc_1800743DE
0x18007427e  mov     edx, [rbx+3Ch]; nNumerator
0x180074281  mov     r8d, 60h ; '`'; nDenominator
0x180074287  call    cs:__imp_MulDiv
0x18007428d  mov     r15d, edi
0x180074290  mov     rcx, rbx; this
0x180074293  or      r15d, 250h
0x18007429a  mov     [rbp+4Fh+rc.right], eax
0x18007429d  mov     edx, r15d; unsigned int
0x1800742a0  call    ?SetThemeRenderFlags@CToolTipsMgr@@AEAAXK@Z; CToolTipsMgr::SetThemeRenderFlags(ulong)
0x1800742a5  mov     rcx, rbx; this
0x1800742a8  call    ?GetCurToolBestMarkup@CToolTipsMgr@@AEAAPEAUIControlMarkup@@XZ; CToolTipsMgr::GetCurToolBestMarkup(void)
0x1800742ad  mov     r10, rax
0x1800742b0  lea     r9, [rbp+4Fh+rc]
0x1800742b4  mov     r8d, 1
0x1800742ba  mov     rdx, rsi
0x1800742bd  mov     rcx, [rax]
0x1800742c0  mov     rax, [rcx+0A0h]
0x1800742c7  mov     rcx, r10
0x1800742ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742cf  mov     eax, [rbp+4Fh+rc.right]
0x1800742d2  lea     r9, [rsp+130h+var_E0]
0x1800742d7  mov     rcx, [rsp+130h+var_100]
0x1800742dc  xor     r8d, r8d
0x1800742df  mov     [r12], eax
0x1800742e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800742e7  mov     eax, [rbp+4Fh+rc.bottom]
0x1800742ea  mov     [r13+0], eax
0x1800742ee  mov     [rbx+0F0h], r15d
0x1800742f5  bts     r15d, 0Ah
0x1800742fa  mov     eax, [rcx+4]
0x1800742fd  mov     rcx, [rcx+8]
0x180074301  shr     eax, 6
0x180074304  and     eax, 1
0x180074307  mov     [rbp+4Fh+var_90], r15d
0x18007430b  mov     [rsp+130h+yBottom], eax
0x18007430f  call    SendNotifyEx
0x180074314  mov     edi, eax
0x180074316  mov     r14, rax
0x180074319  and     edi, 4
0x18007431c  jnz     loc_1800743C4
0x180074322  mov     r9d, r15d; unsigned int
0x180074325  lea     r8, [rbp+4Fh+rc]; struct tagRECT *
0x180074329  mov     rdx, rsi; HDC
0x18007432c  mov     rcx, rbx; this
0x18007432f  call    ?RenderTitledTip@CToolTipsMgr@@AEAAHPEAUHDC__@@PEAUtagRECT@@I@Z; CToolTipsMgr::RenderTitledTip(HDC__ *,tagRECT *,uint)
0x180074334  test    eax, eax
0x180074336  jnz     loc_1800743C4
0x18007433c  mov     edx, [rbp+4Fh+var_90]; unsigned int
0x18007433f  test    r14b, 2
0x180074343  jnz     loc_180074567
0x180074349  cmp     edx, r15d
0x18007434c  jnz     loc_180074567
0x180074352  mov     edx, [rbp+4Fh+rc.right]
0x180074355  sub     edx, [rbp+4Fh+rc.left]
0x180074358  mov     ecx, [rbp+4Fh+rc.bottom]
0x18007435b  cmp     edx, [r12]
0x18007435f  jnz     loc_180074557
0x180074365  mov     eax, ecx
0x180074367  sub     eax, [rbp+4Fh+rc.top]
0x18007436a  cmp     eax, [r13+0]
0x18007436e  jnz     loc_180074557
0x180074374  test    r14b, 10h
0x180074378  jnz     loc_1800745B2
0x18007437e  cmp     qword ptr [rbx+70h], 0
0x180074383  jz      short loc_180074393
0x180074385  mov     rdx, [rsp+130h+h]; h
0x18007438a  mov     rcx, rsi; hdc
0x18007438d  call    cs:__imp_SelectObject
0x180074393  mov     rcx, rsi; hdc
0x180074396  call    cs:__imp_DeleteDC
0x18007439c  test    edi, edi
0x18007439e  jz      loc_1800744EA
0x1800743a4  mov     rcx, [rbp+4Fh+var_50]
0x1800743a8  xor     rcx, rsp; StackCookie
0x1800743ab  call    __security_check_cookie
0x1800743b0  add     rsp, 0F8h
0x1800743b7  pop     r15
0x1800743b9  pop     r14
0x1800743bb  pop     r13
0x1800743bd  pop     r12
0x1800743bf  pop     rdi
0x1800743c0  pop     rsi
0x1800743c1  pop     rbx
0x1800743c2  pop     rbp
0x1800743c3  retn
0x1800743c4  mov     eax, [rbp+4Fh+rc.right]
0x1800743c7  sub     eax, [rbp+4Fh+rc.left]
0x1800743ca  mov     [r12], eax
0x1800743ce  mov     eax, [rbp+4Fh+rc.bottom]
0x1800743d1  sub     eax, [rbp+4Fh+rc.top]
0x1800743d4  mov     [r13+0], eax
0x1800743d8  test    edi, edi
0x1800743da  jnz     short loc_18007437E
0x1800743dc  jmp     short loc_180074374
0x1800743de  mov     r15d, edi
0x1800743e1  mov     rcx, rbx; this
0x1800743e4  or      r15d, 20h
0x1800743e8  mov     edx, r15d; unsigned int
0x1800743eb  call    ?SetThemeRenderFlags@CToolTipsMgr@@AEAAXK@Z; CToolTipsMgr::SetThemeRenderFlags(ulong)
0x1800743f0  mov     rcx, rbx; this
0x1800743f3  call    ?GetCurToolBestMarkup@CToolTipsMgr@@AEAAPEAUIControlMarkup@@XZ; CToolTipsMgr::GetCurToolBestMarkup(void)
0x1800743f8  mov     r10, rax
0x1800743fb  lea     r9, [rbp+4Fh+rc]
0x1800743ff  mov     r8d, 1
0x180074405  mov     rdx, rsi
0x180074408  mov     rcx, [rax]
0x18007440b  mov     rax, [rcx+0A0h]
0x180074412  mov     rcx, r10
0x180074415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007441a  mov     rax, [rbx+68h]
0x18007441e  test    rax, rax
0x180074421  jz      short loc_18007442D
0x180074423  test    byte ptr [rax+4], 20h
0x180074427  jnz     loc_1800744D8
0x18007442d  call    cs:__imp_GetMessagePos
0x180074433  movsx   ecx, ax
0x180074436  shr     eax, 10h
0x180074439  cwde
0x18007443a  mov     [rbp+4Fh+pt.x], ecx
0x18007443d  mov     [rbp+4Fh+pt.y], eax
0x180074440  xorps   xmm0, xmm0
0x180074443  mov     rcx, qword ptr [rbp+4Fh+pt.x]; pt
0x180074447  xor     eax, eax
0x180074449  movups  xmmword ptr [rbp+4Fh+mi.cbSize], xmm0
0x18007444d  mov     qword ptr [rbp+4Fh+mi.rcWork.bottom], rax
0x180074451  movups  xmmword ptr [rbp+4Fh+mi.rcMonitor.bottom], xmm0
0x180074455  lea     edx, [rax+2]; dwFlags
0x180074458  call    cs:__imp_MonitorFromPoint
0x18007445e  lea     rdx, [rbp+4Fh+mi]; lpmi
0x180074462  mov     [rbp+4Fh+mi.cbSize], 28h ; '('
0x180074469  mov     rcx, rax; hMonitor
0x18007446c  call    cs:__imp_GetMonitorInfoW
0x180074472  mov     r9d, [rbp+4Fh+mi.rcWork.right]
0x180074476  sub     r9d, [rbx+0FCh]
0x18007447d  sub     r9d, [rbx+0F4h]
0x180074484  sub     r9d, [r14]
0x180074487  mov     eax, [rbp+4Fh+rc.right]
0x18007448a  sub     r9d, [rbp+4Fh+mi.rcWork.left]; xRight
0x18007448e  sub     eax, [rbp+4Fh+rc.left]
0x180074491  cmp     eax, r9d
0x180074494  jle     loc_1800742CF
0x18007449a  xor     r8d, r8d; yTop
0x18007449d  mov     [rsp+130h+yBottom], 0; yBottom
0x1800744a5  xor     edx, edx; xLeft
0x1800744a7  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800744ab  call    cs:__imp_SetRect
0x1800744b1  lea     r9, [rbp+4Fh+pt]; unsigned int *
0x1800744b5  mov     [rbp+4Fh+pt.x], edi
0x1800744b8  lea     r8, [rbp+4Fh+rc]; struct tagRECT *
0x1800744bc  mov     [rsp+130h+yBottom], 1; int
0x1800744c4  mov     rdx, rsi; HDC
0x1800744c7  mov     rcx, rbx; this
0x1800744ca  call    ?CalcTextSize@CToolTipsMgr@@AEAAXPEAUHDC__@@PEAUtagRECT@@PEAIH@Z; CToolTipsMgr::CalcTextSize(HDC__ *,tagRECT *,uint *,int)
0x1800744cf  mov     r15d, [rbp+4Fh+pt.x]
0x1800744d3  jmp     loc_1800742CF
0x1800744d8  mov     rcx, [rsp+130h+var_F0]
0x1800744dd  mov     eax, [rcx]
0x1800744df  mov     [rbp+4Fh+pt.x], eax
0x1800744e2  mov     eax, [rcx+4]
0x1800744e5  jmp     loc_18007443D
0x1800744ea  mov     ecx, 2Dh ; '-'; nIndex
0x1800744ef  call    cs:__imp_GetSystemMetrics
0x1800744f5  add     [r12], eax
0x1800744f9  mov     ecx, 2Eh ; '.'; nIndex
0x1800744fe  call    cs:__imp_GetSystemMetrics
0x180074504  add     [r13+0], eax
0x180074508  jmp     loc_1800743A4
0x18007450d  bts     edi, 11h
0x180074511  jmp     loc_18007424A
0x180074516  or      edi, 2
0x180074519  jmp     loc_180074258
0x18007451e  mov     rcx, [rbx+0C0h]; himl
0x180074525  lea     r8, [rbp+4Fh+pt]; cy
0x180074529  mov     rdx, r14; cx
0x18007452c  mov     [rbp+4Fh+pt.x], r15d
0x180074530  call    ImageList_GetIconSize
0x180074535  test    eax, eax
0x180074537  jz      short loc_18007454E
0x180074539  mov     edx, [rbx+3Ch]; nNumerator
0x18007453c  mov     r8d, 60h ; '`'; nDenominator
0x180074542  mov     ecx, [r14]; nNumber
0x180074545  call    cs:__imp_MulDiv
0x18007454b  mov     [r14], eax
0x18007454e  add     dword ptr [r14], 5
0x180074552  jmp     loc_18007426F
0x180074557  sub     ecx, [rbp+4Fh+rc.top]
0x18007455a  mov     [r12], edx
0x18007455e  mov     [r13+0], ecx
0x180074562  jmp     loc_180074374
0x180074567  mov     rcx, rbx; this
0x18007456a  call    ?SetThemeRenderFlags@CToolTipsMgr@@AEAAXK@Z; CToolTipsMgr::SetThemeRenderFlags(ulong)
0x18007456f  mov     rcx, rbx; this
0x180074572  call    ?GetCurToolBestMarkup@CToolTipsMgr@@AEAAPEAUIControlMarkup@@XZ; CToolTipsMgr::GetCurToolBestMarkup(void)
0x180074577  mov     r10, rax
0x18007457a  lea     r9, [rbp+4Fh+rc]
0x18007457e  mov     r8d, 1
0x180074584  mov     rdx, rsi
0x180074587  mov     rcx, [rax]
0x18007458a  mov     rax, [rcx+0A0h]
0x180074591  mov     rcx, r10
0x180074594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074599  mov     eax, [rbp+4Fh+rc.right]
0x18007459c  sub     eax, [rbp+4Fh+rc.left]
0x18007459f  mov     [r12], eax
0x1800745a3  mov     eax, [rbp+4Fh+rc.bottom]
0x1800745a6  sub     eax, [rbp+4Fh+rc.top]
0x1800745a9  mov     [r13+0], eax
0x1800745ad  jmp     loc_180074374
0x1800745b2  mov     rcx, [rsp+130h+var_100]
0x1800745b7  lea     r9, [rsp+130h+var_E0]
0x1800745bc  xor     r8d, r8d
0x1800745bf  mov     [rbp+4Fh+var_C8], 2
0x1800745c6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800745ca  mov     eax, [rcx+4]
0x1800745cd  mov     rcx, [rcx+8]
0x1800745d1  shr     eax, 6
0x1800745d4  and     eax, 1
0x1800745d7  mov     [rsp+130h+yBottom], eax
0x1800745db  call    SendNotifyEx
0x1800745e0  jmp     loc_18007437E
```
