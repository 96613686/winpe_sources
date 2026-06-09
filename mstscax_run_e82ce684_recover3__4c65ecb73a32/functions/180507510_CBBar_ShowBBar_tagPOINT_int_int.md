# CBBar::ShowBBar(tagPOINT *,int,int)

- ea: `0x180507510`
- end: `0x180507a8a`
- name: `?ShowBBar@CBBar@@AEAAXPEAUtagPOINT@@HH@Z`
- size: `1402`
- prototype: `void __fastcall(CBBar *__hidden this, struct tagPOINT *, int, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180505940`
- `0x180506d78`
- `0x180507a90`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1800f06c0`
- `0x1800f47c8`
- `0x1800f7748`
- `0x1800f7874`
- `0x18015551c`
- `0x180159c28`
- `0x18050363c`
- `0x180503dec`
- `0x1805044e0`
- `0x1805067e8`
- `0x180506b4c`
- `0x18050701c`
- `0x180507510`
- `0x180508214`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180507a29`
- `KERNEL32!GetLastError` at `0x180507a29`
- `USER32!GetWindowRect` at `0x180507692`
- `USER32!GetWindowRect` at `0x180507692`
- `USER32!ShowWindow` at `0x1805079f3`
- `USER32!ShowWindow` at `0x1805079f3`
- `USER32!SetWindowPos` at `0x18050793a`
- `USER32!SetWindowPos` at `0x18050793a`
- `USER32!IntersectRect` at `0x1805076ac`
- `USER32!IntersectRect` at `0x1805076ac`
- `USER32!EqualRect` at `0x1805076ba`
- `USER32!EqualRect` at `0x18050784d`
- `USER32!EqualRect` at `0x1805076ba`
- `USER32!EqualRect` at `0x18050784d`
- `USER32!CopyRect` at `0x180507702`
- `USER32!CopyRect` at `0x1805079b1`
- `USER32!CopyRect` at `0x180507702`
- `USER32!CopyRect` at `0x1805079b1`
- `USER32!IsRectEmpty` at `0x18050765b`
- `USER32!IsRectEmpty` at `0x1805077c9`
- `USER32!IsRectEmpty` at `0x18050765b`
- `USER32!IsRectEmpty` at `0x1805077c9`
- `USER32!MonitorFromRect` at `0x18050782f`
- `USER32!MonitorFromRect` at `0x18050782f`

## pseudocode

```c
void __fastcall CBBar::ShowBBar(CBBar *this, struct tagPOINT *a2, int a3, int a4)
{
  bool v4; // zf
  LONG v7; // ebx
  LONG v8; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RECT *v10; // rbx
  int v11; // ebx
  int v12; // edi
  int v13; // esi
  int v14; // r14d
  unsigned int v15; // eax
  CHintWnd *v16; // rcx
  unsigned int v17; // eax
  HKEY v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  HMONITOR v22; // rax
  int updated; // edi
  unsigned int v24; // r8d
  unsigned int v25; // eax
  unsigned int v26; // eax
  int v27; // r9d
  int v28; // r8d
  HWND v29; // rcx
  unsigned int v30; // eax
  DWORD LastError; // edi
  unsigned int v32; // eax
  unsigned int v33; // [rsp+20h] [rbp-69h]
  int cy[2]; // [rsp+28h] [rbp-61h]
  unsigned int cya; // [rsp+28h] [rbp-61h]
  int X; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-25h] BYREF
  unsigned int v38; // [rsp+68h] [rbp-21h] BYREF
  int Y; // [rsp+6Ch] [rbp-1Dh] BYREF
  int v40; // [rsp+70h] [rbp-19h]
  int v41; // [rsp+74h] [rbp-15h]
  RECT rc; // [rsp+78h] [rbp-11h] BYREF
  RECT rcSrc2; // [rsp+88h] [rbp-1h] BYREF
  struct tagRECT Rect; // [rsp+98h] [rbp+Fh] BYREF
  struct tagRECT rcDst; // [rsp+A8h] [rbp+1Fh] BYREF

  v4 = *((_DWORD *)this + 394) == 1;
  v40 = a4;
  v41 = a3;
  if ( !v4 )
    return;
  rc = 0;
  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = a2->y;
      v8 = a2->x;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        WPP_64713da2303033df4cd82e061e871de1_Traceguids,
        CurrentThreadActivityIdPrefix,
        v8,
        v7);
    }
    CInfoPanel::GetMonitorRect(this, *a2, &rc);
    v10 = (RECT *)((char *)this + 1520);
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = *((_DWORD *)this + 383);
    v12 = *((_DWORD *)this + 382);
    v13 = *((_DWORD *)this + 381);
    v14 = *((_DWORD *)this + 380);
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      134,
      WPP_64713da2303033df4cd82e061e871de1_Traceguids,
      v15,
      v14,
      v13,
      v12,
      v11);
  }
  v10 = (RECT *)((char *)this + 1520);
  if ( IsRectEmpty((const RECT *)this + 95) )
    goto LABEL_24;
  rcSrc2 = 0;
  Rect = 0;
  rcDst = 0;
  CBBar::GetWindowRect(this, &rcSrc2);
  if ( !GetWindowRect(*((HWND *)this + 9), &Rect) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      cy[0] = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        (unsigned int)WPP_64713da2303033df4cd82e061e871de1_Traceguids,
        v32,
        (__int64)"GetWindowRect failed",
        *(_QWORD *)cy);
    }
    goto LABEL_30;
  }
  IntersectRect(&rcDst, &Rect, &rcSrc2);
  if ( EqualRect(&rcSrc2, &rcDst) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, WPP_64713da2303033df4cd82e061e871de1_Traceguids, v17);
    }
    CopyRect(&rc, (const RECT *)this + 95);
    goto LABEL_30;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
    goto LABEL_29;
  if ( ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      136,
      WPP_64713da2303033df4cd82e061e871de1_Traceguids,
      v19,
      rcSrc2.left,
      rcSrc2.top,
      rcSrc2.right,
      rcSrc2.bottom,
      Rect.left,
      Rect.top,
      Rect.right,
      Rect.bottom);
LABEL_24:
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v18[7] & 1) != 0 && *((_BYTE *)v18 + 25) >= 4u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_64713da2303033df4cd82e061e871de1_Traceguids, v20);
  }
LABEL_29:
  CHintWnd::GetMonitorRect(v16, *((HWND *)this + 9), &rc);
LABEL_30:
  IsRectEmpty(&rc);
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      139,
      WPP_64713da2303033df4cd82e061e871de1_Traceguids,
      v21,
      rc.left,
      rc.top,
      rc.right,
      rc.bottom);
  }
  v22 = MonitorFromRect(&rc, 1u);
  updated = CBBar::UpdateDesktopScaleFactor(this, v22);
  if ( updated || !EqualRect(&rc, v10) )
  {
    v37 = 0;
    v38 = 0;
    X = 0;
    Y = 0;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_64713da2303033df4cd82e061e871de1_Traceguids, v25);
    }
    if ( updated || !*((_QWORD *)this + 38) || !*((_QWORD *)this + 28) )
      CBBar::CreateToolBars(this);
    CBBar::PositionToolBars(this, 0);
    CBBar::GetBBarDimensions(this, &rc, &X, &Y, &v37, &v38, (unsigned int *)this + 388);
    v26 = v38;
    v27 = Y;
    v28 = X;
    cya = v38;
    v33 = v37;
    *((_DWORD *)this + 386) = v37;
    v29 = (HWND)*((_QWORD *)this + 6);
    *((_QWORD *)this + 192) = 0;
    *((_DWORD *)this + 387) = v26;
    SetWindowPos(v29, 0, v28, v27, v33, cya, 0x2414u);
    CBBar::PositionToolBars(this, 1);
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v30 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        WPP_64713da2303033df4cd82e061e871de1_Traceguids,
        v30,
        rc.left,
        rc.top,
        rc.right,
        rc.bottom);
    }
    CopyRect(v10, &rc);
  }
  *((_DWORD *)this + 51) = v40;
  X = 0;
  if ( !v41 || (CBBar::AnimateBBar(this, 1, v24, &X), !X) )
  {
    CBBar::SetBBarTransparency(this);
    ShowWindow(*((HWND *)this + 6), 4);
    CBBar::OnLowerAnimationCompleted(this);
  }
}

```

## disassembly

```asm
0x180507510  mov     [rsp-8+arg_10], rbx
0x180507515  mov     [rsp-8+arg_18], rsi
0x18050751a  push    rbp
0x18050751b  push    rdi
0x18050751c  push    r13
0x18050751e  push    r14
0x180507520  push    r15
0x180507522  lea     rbp, [rsp-37h]
0x180507527  sub     rsp, 0C0h
0x18050752e  mov     rax, cs:__security_cookie
0x180507535  xor     rax, rsp
0x180507538  mov     [rbp+57h+var_28], rax
0x18050753c  cmp     dword ptr [rcx+628h], 1
0x180507543  mov     r14, rdx
0x180507546  mov     [rbp+57h+var_70], r9d
0x18050754a  mov     r15, rcx
0x18050754d  mov     [rbp+57h+var_6C], r8d
0x180507551  jnz     loc_180507A01
0x180507557  xorps   xmm0, xmm0
0x18050755a  mov     edi, 100h
0x18050755f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180507563  test    rdx, rdx
0x180507566  jz      short loc_1805075D6
0x180507568  mov     rax, cs:WPP_GLOBAL_Control
0x18050756f  lea     r13, WPP_GLOBAL_Control
0x180507576  lea     rsi, WPP_64713da2303033df4cd82e061e871de1_Traceguids
0x18050757d  cmp     rax, r13
0x180507580  jz      short loc_1805075BB
0x180507582  test    byte ptr [rax+1Ch], 1
0x180507586  jz      short loc_1805075BB
0x180507588  cmp     byte ptr [rax+19h], 4
0x18050758c  jb      short loc_1805075BB
0x18050758e  mov     ebx, [rdx+4]
0x180507591  mov     edi, [rdx]
0x180507593  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180507598  mov     rcx, cs:WPP_GLOBAL_Control
0x18050759f  mov     edx, 85h
0x1805075a4  mov     [rsp+0E0h+cy], ebx
0x1805075a8  mov     r9d, eax
0x1805075ab  mov     r8, rsi
0x1805075ae  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1805075b2  mov     rcx, [rcx+10h]
0x1805075b6  call    WPP_SF_DLD
0x1805075bb  mov     rdx, [r14]; struct tagPOINT
0x1805075be  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x1805075c2  call    ?GetMonitorRect@CInfoPanel@@AEAAHUtagPOINT@@PEAUtagRECT@@@Z; CInfoPanel::GetMonitorRect(tagPOINT,tagRECT *)
0x1805075c7  xor     r14d, r14d
0x1805075ca  lea     rbx, [r15+5F0h]
0x1805075d1  jmp     loc_1805077C5
0x1805075d6  mov     rax, cs:WPP_GLOBAL_Control
0x1805075dd  lea     r13, WPP_GLOBAL_Control
0x1805075e4  lea     rsi, WPP_64713da2303033df4cd82e061e871de1_Traceguids
0x1805075eb  cmp     rax, r13
0x1805075ee  jz      short loc_180507651
0x1805075f0  test    [rax+1Ch], edi
0x1805075f3  jz      short loc_180507651
0x1805075f5  cmp     byte ptr [rax+19h], 4
0x1805075f9  jb      short loc_180507651
0x1805075fb  mov     ebx, [rcx+5FCh]
0x180507601  mov     edi, [rcx+5F8h]
0x180507607  mov     esi, [rcx+5F4h]
0x18050760d  mov     r14d, [rcx+5F0h]
0x180507614  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180507619  mov     rcx, cs:WPP_GLOBAL_Control
0x180507620  mov     edx, 86h
0x180507625  mov     [rsp+0E0h+var_A8], ebx
0x180507629  mov     r9d, eax
0x18050762c  mov     [rsp+0E0h+uFlags], edi
0x180507630  mov     [rsp+0E0h+cy], esi
0x180507634  lea     rsi, WPP_64713da2303033df4cd82e061e871de1_Traceguids
0x18050763b  mov     rcx, [rcx+10h]
0x18050763f  mov     r8, rsi
0x180507642  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x180507647  call    WPP_SF_Ddddd
0x18050764c  mov     edi, 100h
0x180507651  lea     rbx, [r15+5F0h]
0x180507658  mov     rcx, rbx; lprc
0x18050765b  call    cs:__imp_IsRectEmpty
0x180507661  xor     r14d, r14d
0x180507664  test    eax, eax
0x180507666  jnz     loc_180507780
0x18050766c  xorps   xmm0, xmm0
0x18050766f  lea     rdx, [rbp+57h+rcSrc2]; struct tagRECT *
0x180507673  xorps   xmm1, xmm1
0x180507676  mov     rcx, r15; this
0x180507679  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm0
0x18050767d  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x180507681  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180507685  call    ?GetWindowRect@CBBar@@AEAAXPEAUtagRECT@@@Z; CBBar::GetWindowRect(tagRECT *)
0x18050768a  mov     rcx, [r15+48h]; hWnd
0x18050768e  lea     rdx, [rbp+57h+Rect]; lpRect
0x180507692  call    cs:__imp_GetWindowRect
0x180507698  test    eax, eax
0x18050769a  jz      loc_180507A29
0x1805076a0  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x1805076a4  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x1805076a8  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1805076ac  call    cs:__imp_IntersectRect
0x1805076b2  lea     rdx, [rbp+57h+rcDst]; lprc2
0x1805076b6  lea     rcx, [rbp+57h+rcSrc2]; lprc1
0x1805076ba  call    cs:__imp_EqualRect
0x1805076c0  test    eax, eax
0x1805076c2  jz      short loc_18050770D
0x1805076c4  mov     rax, cs:WPP_GLOBAL_Control
0x1805076cb  cmp     rax, r13
0x1805076ce  jz      short loc_1805076FB
0x1805076d0  test    [rax+1Ch], edi
0x1805076d3  jz      short loc_1805076FB
0x1805076d5  cmp     byte ptr [rax+19h], 4
0x1805076d9  jb      short loc_1805076FB
0x1805076db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805076e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1805076e7  mov     edx, 87h
0x1805076ec  mov     r9d, eax
0x1805076ef  mov     r8, rsi
0x1805076f2  mov     rcx, [rcx+10h]
0x1805076f6  call    WPP_SF_d
0x1805076fb  mov     rdx, rbx; lprcSrc
0x1805076fe  lea     rcx, [rbp+57h+rc]; lprcDst
0x180507702  call    cs:__imp_CopyRect
0x180507708  jmp     loc_1805077C5
0x18050770d  mov     rax, cs:WPP_GLOBAL_Control
0x180507714  cmp     rax, r13
0x180507717  jz      loc_1805077B8
0x18050771d  test    [rax+1Ch], edi
0x180507720  jz      short loc_180507787
0x180507722  cmp     byte ptr [rax+19h], 4
0x180507726  jb      short loc_180507787
0x180507728  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050772d  mov     ecx, [rbp+57h+Rect.bottom]
0x180507730  mov     r9d, eax
0x180507733  mov     eax, [rbp+57h+rcSrc2.left]
0x180507736  mov     edx, 88h
0x18050773b  mov     [rsp+0E0h+var_88], ecx
0x18050773f  mov     r8, rsi
0x180507742  mov     ecx, [rbp+57h+Rect.right]
0x180507745  mov     [rsp+0E0h+var_90], ecx
0x180507749  mov     ecx, [rbp+57h+Rect.top]
0x18050774c  mov     [rsp+0E0h+var_98], ecx
0x180507750  mov     ecx, [rbp+57h+Rect.left]
0x180507753  mov     [rsp+0E0h+var_A0], ecx
0x180507757  mov     ecx, [rbp+57h+rcSrc2.bottom]
0x18050775a  mov     [rsp+0E0h+var_A8], ecx
0x18050775e  mov     ecx, [rbp+57h+rcSrc2.right]
0x180507761  mov     [rsp+0E0h+uFlags], ecx
0x180507765  mov     ecx, [rbp+57h+rcSrc2.top]
0x180507768  mov     [rsp+0E0h+cy], ecx
0x18050776c  mov     rcx, cs:WPP_GLOBAL_Control
0x180507773  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180507777  mov     rcx, [rcx+10h]
0x18050777b  call    WPP_SF_DDDDDDDDD
0x180507780  mov     rax, cs:WPP_GLOBAL_Control
0x180507787  cmp     rax, r13
0x18050778a  jz      short loc_1805077B8
0x18050778c  test    byte ptr [rax+1Ch], 1
0x180507790  jz      short loc_1805077B8
0x180507792  cmp     byte ptr [rax+19h], 4
0x180507796  jb      short loc_1805077B8
0x180507798  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050779d  mov     rcx, cs:WPP_GLOBAL_Control
0x1805077a4  mov     edx, 8Ah
0x1805077a9  mov     r9d, eax
0x1805077ac  mov     r8, rsi
0x1805077af  mov     rcx, [rcx+10h]
0x1805077b3  call    WPP_SF_d
0x1805077b8  mov     rdx, [r15+48h]; HWND
0x1805077bc  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x1805077c0  call    ?GetMonitorRect@CHintWnd@@IEAAHPEAUHWND__@@PEAUtagRECT@@@Z; CHintWnd::GetMonitorRect(HWND__ *,tagRECT *)
0x1805077c5  lea     rcx, [rbp+57h+rc]; lprc
0x1805077c9  call    cs:__imp_IsRectEmpty
0x1805077cf  mov     rax, cs:WPP_GLOBAL_Control
0x1805077d6  cmp     rax, r13
0x1805077d9  jz      short loc_180507826
0x1805077db  test    dword ptr [rax+1Ch], 100h
0x1805077e2  jz      short loc_180507826
0x1805077e4  cmp     byte ptr [rax+19h], 4
0x1805077e8  jb      short loc_180507826
0x1805077ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805077ef  mov     ecx, [rbp+57h+rc.bottom]
0x1805077f2  mov     edx, 8Bh
0x1805077f7  mov     [rsp+0E0h+var_A8], ecx
0x1805077fb  mov     r9d, eax
0x1805077fe  mov     ecx, [rbp+57h+rc.right]
0x180507801  mov     r8, rsi
0x180507804  mov     [rsp+0E0h+uFlags], ecx
0x180507808  mov     ecx, [rbp+57h+rc.top]
0x18050780b  mov     [rsp+0E0h+cy], ecx
0x18050780f  mov     ecx, [rbp+57h+rc.left]
0x180507812  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x180507816  mov     rcx, cs:WPP_GLOBAL_Control
0x18050781d  mov     rcx, [rcx+10h]
0x180507821  call    WPP_SF_Ddddd
0x180507826  mov     edx, 1; dwFlags
0x18050782b  lea     rcx, [rbp+57h+rc]; lprc
0x18050782f  call    cs:__imp_MonitorFromRect
0x180507835  mov     rdx, rax; HMONITOR
0x180507838  mov     rcx, r15; this
0x18050783b  call    ?UpdateDesktopScaleFactor@CBBar@@AEAAHPEAUHMONITOR__@@@Z; CBBar::UpdateDesktopScaleFactor(HMONITOR__ *)
0x180507840  mov     edi, eax
0x180507842  test    eax, eax
0x180507844  jnz     short loc_18050785B
0x180507846  mov     rdx, rbx; lprc2
0x180507849  lea     rcx, [rbp+57h+rc]; lprc1
0x18050784d  call    cs:__imp_EqualRect
0x180507853  test    eax, eax
0x180507855  jnz     loc_1805079B7
0x18050785b  mov     [rbp+57h+var_7C], r14d
0x18050785f  mov     [rbp+57h+var_78], r14d
0x180507863  mov     [rbp+57h+X], r14d
0x180507867  mov     [rbp+57h+Y], r14d
0x18050786b  mov     rax, cs:WPP_GLOBAL_Control
0x180507872  cmp     rax, r13
0x180507875  jz      short loc_1805078A3
0x180507877  test    byte ptr [rax+1Ch], 1
0x18050787b  jz      short loc_1805078A3
0x18050787d  cmp     byte ptr [rax+19h], 4
0x180507881  jb      short loc_1805078A3
0x180507883  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180507888  mov     rcx, cs:WPP_GLOBAL_Control
0x18050788f  mov     edx, 8Ch
0x180507894  mov     r9d, eax
0x180507897  mov     r8, rsi
0x18050789a  mov     rcx, [rcx+10h]
0x18050789e  call    WPP_SF_d
0x1805078a3  test    edi, edi
0x1805078a5  jnz     short loc_1805078B9
0x1805078a7  cmp     [r15+130h], r14
0x1805078ae  jz      short loc_1805078B9
0x1805078b0  cmp     [r15+0E0h], r14
0x1805078b7  jnz     short loc_1805078C1
0x1805078b9  mov     rcx, r15; this
0x1805078bc  call    ?CreateToolBars@CBBar@@AEAAXXZ; CBBar::CreateToolBars(void)
0x1805078c1  xor     edx, edx; int
0x1805078c3  mov     rcx, r15; this
0x1805078c6  call    ?PositionToolBars@CBBar@@AEAAXH@Z; CBBar::PositionToolBars(int)
0x1805078cb  lea     rax, [r15+610h]
0x1805078d2  mov     rcx, r15; this
0x1805078d5  mov     qword ptr [rsp+0E0h+uFlags], rax; unsigned int *
0x1805078da  lea     r9, [rbp+57h+Y]; int *
0x1805078de  lea     rax, [rbp+57h+var_78]
0x1805078e2  mov     qword ptr [rsp+0E0h+cy], rax; unsigned int *
0x1805078e7  lea     r8, [rbp+57h+X]; int *
0x1805078eb  lea     rax, [rbp+57h+var_7C]
0x1805078ef  lea     rdx, [rbp+57h+rc]; lprc
0x1805078f3  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x1805078f8  call    ?GetBBarDimensions@CBBar@@AEAAXPEBUtagRECT@@PEAH1PEAI22@Z; CBBar::GetBBarDimensions(tagRECT const *,int *,int *,uint *,uint *,uint *)
0x1805078fd  mov     ecx, [rbp+57h+var_7C]
0x180507900  xor     edx, edx; hWndInsertAfter
0x180507902  mov     eax, [rbp+57h+var_78]
0x180507905  mov     r9d, [rbp+57h+Y]; Y
0x180507909  mov     r8d, [rbp+57h+X]; X
0x18050790d  mov     [rsp+0E0h+uFlags], 2414h; uFlags
0x180507915  mov     [rsp+0E0h+cy], eax; cy
0x180507919  mov     dword ptr [rsp+0E0h+var_C0], ecx; cx
0x18050791d  mov     [r15+608h], ecx
0x180507924  mov     rcx, [r15+30h]; hWnd
0x180507928  mov     qword ptr [r15+600h], 0
0x180507933  mov     [r15+60Ch], eax
0x18050793a  call    cs:__imp_SetWindowPos
0x180507940  mov     edx, 1; int
0x180507945  mov     rcx, r15; this
0x180507948  call    ?PositionToolBars@CBBar@@AEAAXH@Z; CBBar::PositionToolBars(int)
0x18050794d  mov     rax, cs:WPP_GLOBAL_Control
0x180507954  cmp     rax, r13
0x180507957  jz      short loc_1805079AA
0x180507959  test    dword ptr [rax+1Ch], 100h
0x180507960  jz      short loc_1805079AA
0x180507962  cmp     byte ptr [rax+19h], 4
0x180507966  jb      short loc_1805079AA
0x180507968  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050796d  mov     ecx, [rbp+57h+rc.bottom]
0x180507970  mov     edx, 8Dh
0x180507975  mov     r9d, [rbp+57h+rc.right]
0x180507979  mov     r8, rsi
0x18050797c  mov     [rsp+0E0h+var_A8], ecx
0x180507980  mov     rcx, cs:WPP_GLOBAL_Control
0x180507987  mov     [rsp+0E0h+uFlags], r9d
0x18050798c  mov     r9d, [rbp+57h+rc.top]
0x180507990  mov     [rsp+0E0h+cy], r9d
0x180507995  mov     r9d, [rbp+57h+rc.left]
0x180507999  mov     rcx, [rcx+10h]
0x18050799d  mov     dword ptr [rsp+0E0h+var_C0], r9d
0x1805079a2  mov     r9d, eax
0x1805079a5  call    WPP_SF_Ddddd
0x1805079aa  lea     rdx, [rbp+57h+rc]; lprcSrc
0x1805079ae  mov     rcx, rbx; lprcDst
0x1805079b1  call    cs:__imp_CopyRect
0x1805079b7  mov     eax, [rbp+57h+var_70]
0x1805079ba  mov     [r15+0CCh], eax
0x1805079c1  mov     [rbp+57h+X], r14d
0x1805079c5  cmp     [rbp+57h+var_6C], r14d
0x1805079c9  jz      short loc_1805079E2
0x1805079cb  lea     r9, [rbp+57h+X]; int *
0x1805079cf  mov     edx, 1; int
0x1805079d4  mov     rcx, r15; this
0x1805079d7  call    ?AnimateBBar@CBBar@@AEAAXHKPEAH@Z; CBBar::AnimateBBar(int,ulong,int *)
0x1805079dc  cmp     [rbp+57h+X], r14d
0x1805079e0  jnz     short loc_180507A01
0x1805079e2  mov     rcx, r15; this
0x1805079e5  call    ?SetBBarTransparency@CBBar@@AEAAXXZ; CBBar::SetBBarTransparency(void)
  ... truncated ...
```
