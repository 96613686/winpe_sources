# CInfoPanel::ShowInfoPanel(tagPOINT *,int,int)

- ea: `0x18050c530`
- end: `0x18050c8da`
- name: `?ShowInfoPanel@CInfoPanel@@AEAAXPEAUtagPOINT@@HH@Z`
- size: `938`
- prototype: `void __fastcall(CInfoPanel *__hidden this, struct tagPOINT *, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x18050ba74`
- `0x18050c8e0`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800f06c0`
- `0x1800f7748`
- `0x180508d38`
- `0x18050a1b4`
- `0x18050a510`
- `0x18050b8b4`
- `0x18050b960`
- `0x18050c530`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `USER32!GetWindowRect` at `0x18050c621`
- `USER32!GetWindowRect` at `0x18050c621`
- `USER32!ShowWindow` at `0x18050c844`
- `USER32!ShowWindow` at `0x18050c844`
- `USER32!SetWindowPos` at `0x18050c79d`
- `USER32!SetWindowPos` at `0x18050c79d`
- `USER32!IntersectRect` at `0x18050c633`
- `USER32!IntersectRect` at `0x18050c633`
- `USER32!EqualRect` at `0x18050c641`
- `USER32!EqualRect` at `0x18050c6e6`
- `USER32!EqualRect` at `0x18050c641`
- `USER32!EqualRect` at `0x18050c6e6`
- `USER32!CopyRect` at `0x18050c652`
- `USER32!CopyRect` at `0x18050c81b`
- `USER32!CopyRect` at `0x18050c652`
- `USER32!CopyRect` at `0x18050c81b`
- `USER32!IsRectEmpty` at `0x18050c5f1`
- `USER32!IsRectEmpty` at `0x18050c6d9`
- `USER32!IsRectEmpty` at `0x18050c5f1`
- `USER32!IsRectEmpty` at `0x18050c6d9`
- `USER32!MonitorFromWindow` at `0x18050c6ad`
- `USER32!MonitorFromWindow` at `0x18050c6ad`
- `USER32!GetMonitorInfoW` at `0x18050c6c6`
- `USER32!GetMonitorInfoW` at `0x18050c6c6`

## pseudocode

```c
void __fastcall CInfoPanel::ShowInfoPanel(CInfoPanel *this, struct tagPOINT *a2, int a3)
{
  LONG v6; // ebx
  LONG v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  RECT *v9; // rbx
  unsigned int v10; // eax
  HWND v11; // rcx
  HMONITOR v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // r9d
  int v16; // r8d
  HWND v17; // rcx
  unsigned int v18; // r9d
  unsigned int v19; // r9d
  unsigned int v20; // r9d
  unsigned int v21; // r9d
  unsigned int v22; // r9d
  __int64 v23; // rcx
  int v24; // ebx
  unsigned int v25; // eax
  unsigned int v26; // [rsp+20h] [rbp-69h]
  unsigned int v27; // [rsp+20h] [rbp-69h]
  unsigned int v28; // [rsp+20h] [rbp-69h]
  unsigned int v29; // [rsp+20h] [rbp-69h]
  unsigned int v30; // [rsp+20h] [rbp-69h]
  unsigned int v31; // [rsp+20h] [rbp-69h]
  unsigned int cy; // [rsp+28h] [rbp-61h]
  unsigned int v33; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-45h] BYREF
  int Y; // [rsp+48h] [rbp-41h] BYREF
  int X; // [rsp+4Ch] [rbp-3Dh] BYREF
  RECT rc; // [rsp+50h] [rbp-39h] BYREF
  RECT rcSrc2; // [rsp+60h] [rbp-29h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-19h] BYREF
  struct tagRECT rcDst; // [rsp+80h] [rbp-9h] BYREF
  struct tagMONITORINFO mi; // [rsp+90h] [rbp+7h] BYREF

  if ( !*((_DWORD *)this + 793) )
  {
    rc = 0;
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v6 = a2->y;
        v7 = a2->x;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DLD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids,
          CurrentThreadActivityIdPrefix,
          v7,
          v6);
      }
      CInfoPanel::GetMonitorRect(this, *a2, &rc);
      v9 = (RECT *)((char *)this + 3140);
    }
    else
    {
      v9 = (RECT *)((char *)this + 3140);
      if ( IsRectEmpty((const RECT *)((char *)this + 3140))
        || (rcSrc2 = 0,
            Rect = 0,
            rcDst = 0,
            CInfoPanel::GetWindowRect(this, &rcSrc2),
            GetWindowRect(*((HWND *)this + 9), &Rect),
            IntersectRect(&rcDst, &Rect, &rcSrc2),
            !EqualRect(&rcSrc2, &rcDst)) )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v10 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids, v10);
        }
        v11 = (HWND)*((_QWORD *)this + 9);
        memset(&mi, 0, sizeof(mi));
        v12 = MonitorFromWindow(v11, 0);
        if ( v12 )
        {
          mi.cbSize = 40;
          GetMonitorInfoW(v12, &mi);
          rc = mi.rcMonitor;
        }
      }
      else
      {
        CopyRect(&rc, v9);
      }
    }
    IsRectEmpty(&rc);
    if ( !EqualRect(&rc, v9) )
    {
      v33 = 0;
      v34 = 0;
      X = 0;
      Y = 0;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids, v13);
      }
      CInfoPanel::GetInfoPanelDimensions(this, &rc, &X, &Y, &v33, &v34);
      v14 = v34;
      v15 = Y;
      v16 = X;
      cy = v34;
      v26 = v33;
      *((_DWORD *)this + 791) = v33;
      v17 = (HWND)*((_QWORD *)this + 6);
      *(_QWORD *)((char *)this + 3156) = 0;
      *((_DWORD *)this + 792) = v14;
      SetWindowPos(v17, 0, v16, v15, v26, cy, 0x2414u);
      CInfoPanel::PositionControl(this, *((HWND *)this + 357), 8u, v18, v27);
      CInfoPanel::PositionControl(this, *((HWND *)this + 358), 9u, v19, v28);
      CInfoPanel::PositionControl(this, *((HWND *)this + 361), 0xEu, v20, v29);
      CInfoPanel::PositionControl(this, *((HWND *)this + 359), 0xFu, v21, v30);
      CInfoPanel::PositionControl(this, *((HWND *)this + 360), 0x10u, v22, v31);
      CInfoPanel::PositionWinCtrlsToolBar(this);
      CopyRect(v9, &rc);
    }
    if ( a3 )
      CInfoPanel::AnimateInfoPanel(this, 1, 0xDCu);
    else
      ShowWindow(*((HWND *)this + 6), 4);
    v23 = *((_QWORD *)this + 13);
    *((_DWORD *)this + 793) = 1;
    v24 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v23 + 32LL))(
            v23,
            "ShowSessionDiagnostics",
            1);
    if ( v24 < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids, v25, v24);
    }
  }
}

```

## disassembly

```asm
0x18050c530  mov     [rsp-8+arg_10], rbx
0x18050c535  push    rbp
0x18050c536  push    rsi
0x18050c537  push    rdi
0x18050c538  push    r14
0x18050c53a  push    r15
0x18050c53c  lea     rbp, [rsp-37h]
0x18050c541  sub     rsp, 0C0h
0x18050c548  mov     rax, cs:__security_cookie
0x18050c54f  xor     rax, rsp
0x18050c552  mov     [rbp+57h+var_28], rax
0x18050c556  cmp     dword ptr [rcx+0C64h], 0
0x18050c55d  mov     r15d, r8d
0x18050c560  mov     r14, rdx
0x18050c563  mov     rsi, rcx
0x18050c566  jnz     loc_18050C8B7
0x18050c56c  lea     rdi, WPP_GLOBAL_Control
0x18050c573  xorps   xmm0, xmm0
0x18050c576  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x18050c57a  test    rdx, rdx
0x18050c57d  jz      short loc_18050C5E7
0x18050c57f  mov     rax, cs:WPP_GLOBAL_Control
0x18050c586  cmp     rax, rdi
0x18050c589  jz      short loc_18050C5CF
0x18050c58b  test    byte ptr [rax+1Ch], 1
0x18050c58f  jz      short loc_18050C5CF
0x18050c591  cmp     byte ptr [rax+19h], 4
0x18050c595  jb      short loc_18050C5CF
0x18050c597  mov     ebx, [rdx+4]
0x18050c59a  mov     edi, [rdx]
0x18050c59c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050c5a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18050c5a8  lea     r8, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids
0x18050c5af  mov     edx, 5Ah ; 'Z'
0x18050c5b4  mov     [rsp+0E0h+cy], ebx
0x18050c5b8  mov     r9d, eax
0x18050c5bb  mov     dword ptr [rsp+0E0h+var_C0], edi
0x18050c5bf  mov     rcx, [rcx+10h]
0x18050c5c3  call    WPP_SF_DLD
0x18050c5c8  lea     rdi, WPP_GLOBAL_Control
0x18050c5cf  mov     rdx, [r14]; struct tagPOINT
0x18050c5d2  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x18050c5d6  call    ?GetMonitorRect@CInfoPanel@@AEAAHUtagPOINT@@PEAUtagRECT@@@Z; CInfoPanel::GetMonitorRect(tagPOINT,tagRECT *)
0x18050c5db  lea     rbx, [rsi+0C44h]
0x18050c5e2  jmp     loc_18050C6D5
0x18050c5e7  lea     rbx, [rcx+0C44h]
0x18050c5ee  mov     rcx, rbx; lprc
0x18050c5f1  call    cs:__imp_IsRectEmpty
0x18050c5f7  test    eax, eax
0x18050c5f9  jnz     short loc_18050C65A
0x18050c5fb  xorps   xmm0, xmm0
0x18050c5fe  lea     rdx, [rbp+57h+rcSrc2]; struct tagRECT *
0x18050c602  xorps   xmm1, xmm1
0x18050c605  mov     rcx, rsi; this
0x18050c608  movups  xmmword ptr [rbp+57h+rcSrc2.left], xmm0
0x18050c60c  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x18050c610  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18050c614  call    ?GetWindowRect@CInfoPanel@@AEAAXPEAUtagRECT@@@Z; CInfoPanel::GetWindowRect(tagRECT *)
0x18050c619  mov     rcx, [rsi+48h]; hWnd
0x18050c61d  lea     rdx, [rbp+57h+Rect]; lpRect
0x18050c621  call    cs:__imp_GetWindowRect
0x18050c627  lea     r8, [rbp+57h+rcSrc2]; lprcSrc2
0x18050c62b  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x18050c62f  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18050c633  call    cs:__imp_IntersectRect
0x18050c639  lea     rdx, [rbp+57h+rcDst]; lprc2
0x18050c63d  lea     rcx, [rbp+57h+rcSrc2]; lprc1
0x18050c641  call    cs:__imp_EqualRect
0x18050c647  test    eax, eax
0x18050c649  jz      short loc_18050C65A
0x18050c64b  mov     rdx, rbx; lprcSrc
0x18050c64e  lea     rcx, [rbp+57h+rc]; lprcDst
0x18050c652  call    cs:__imp_CopyRect
0x18050c658  jmp     short loc_18050C6D5
0x18050c65a  mov     rax, cs:WPP_GLOBAL_Control
0x18050c661  cmp     rax, rdi
0x18050c664  jz      short loc_18050C696
0x18050c666  test    byte ptr [rax+1Ch], 1
0x18050c66a  jz      short loc_18050C696
0x18050c66c  cmp     byte ptr [rax+19h], 4
0x18050c670  jb      short loc_18050C696
0x18050c672  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050c677  mov     rcx, cs:WPP_GLOBAL_Control
0x18050c67e  lea     r8, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids
0x18050c685  mov     edx, 5Bh ; '['
0x18050c68a  mov     r9d, eax
0x18050c68d  mov     rcx, [rcx+10h]
0x18050c691  call    WPP_SF_d
0x18050c696  mov     rcx, [rsi+48h]; hwnd
0x18050c69a  xorps   xmm0, xmm0
0x18050c69d  xor     eax, eax
0x18050c69f  xor     edx, edx; dwFlags
0x18050c6a1  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x18050c6a5  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x18050c6a9  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x18050c6ad  call    cs:__imp_MonitorFromWindow
0x18050c6b3  test    rax, rax
0x18050c6b6  jz      short loc_18050C6D5
0x18050c6b8  lea     rdx, [rbp+57h+mi]; lpmi
0x18050c6bc  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x18050c6c3  mov     rcx, rax; hMonitor
0x18050c6c6  call    cs:__imp_GetMonitorInfoW
0x18050c6cc  movups  xmm0, xmmword ptr [rbp+57h+mi.rcMonitor.left]
0x18050c6d0  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x18050c6d5  lea     rcx, [rbp+57h+rc]; lprc
0x18050c6d9  call    cs:__imp_IsRectEmpty
0x18050c6df  mov     rdx, rbx; lprc2
0x18050c6e2  lea     rcx, [rbp+57h+rc]; lprc1
0x18050c6e6  call    cs:__imp_EqualRect
0x18050c6ec  test    eax, eax
0x18050c6ee  jnz     loc_18050C821
0x18050c6f4  mov     [rbp+57h+var_A0], eax
0x18050c6f7  mov     [rbp+57h+var_9C], eax
0x18050c6fa  mov     [rbp+57h+X], eax
0x18050c6fd  mov     [rbp+57h+Y], eax
0x18050c700  mov     rax, cs:WPP_GLOBAL_Control
0x18050c707  cmp     rax, rdi
0x18050c70a  jz      short loc_18050C73C
0x18050c70c  test    byte ptr [rax+1Ch], 1
0x18050c710  jz      short loc_18050C73C
0x18050c712  cmp     byte ptr [rax+19h], 4
0x18050c716  jb      short loc_18050C73C
0x18050c718  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050c71d  mov     rcx, cs:WPP_GLOBAL_Control
0x18050c724  lea     r8, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids
0x18050c72b  mov     edx, 5Ch ; '\'
0x18050c730  mov     r9d, eax
0x18050c733  mov     rcx, [rcx+10h]
0x18050c737  call    WPP_SF_d
0x18050c73c  lea     rax, [rbp+57h+var_9C]
0x18050c740  mov     rcx, rsi; this
0x18050c743  mov     qword ptr [rsp+0E0h+cy], rax; unsigned int *
0x18050c748  lea     r9, [rbp+57h+Y]; int *
0x18050c74c  lea     rax, [rbp+57h+var_A0]
0x18050c750  lea     r8, [rbp+57h+X]; int *
0x18050c754  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x18050c759  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18050c75d  call    ?GetInfoPanelDimensions@CInfoPanel@@AEAAXPEBUtagRECT@@PEAH1PEAI2@Z; CInfoPanel::GetInfoPanelDimensions(tagRECT const *,int *,int *,uint *,uint *)
0x18050c762  mov     eax, [rbp+57h+var_9C]
0x18050c765  xor     edx, edx; hWndInsertAfter
0x18050c767  mov     ecx, [rbp+57h+var_A0]
0x18050c76a  mov     r9d, [rbp+57h+Y]; Y
0x18050c76e  mov     r8d, [rbp+57h+X]; X
0x18050c772  mov     [rsp+0E0h+uFlags], 2414h; uFlags
0x18050c77a  mov     [rsp+0E0h+cy], eax; cy
0x18050c77e  mov     dword ptr [rsp+0E0h+var_C0], ecx; unsigned int
0x18050c782  mov     [rsi+0C5Ch], ecx
0x18050c788  mov     rcx, [rsi+30h]; hWnd
0x18050c78c  mov     qword ptr [rsi+0C54h], 0
0x18050c797  mov     [rsi+0C60h], eax
0x18050c79d  call    cs:__imp_SetWindowPos
0x18050c7a3  mov     rdx, [rsi+0B28h]; hWnd
0x18050c7aa  mov     r8d, 8; unsigned int
0x18050c7b0  mov     rcx, rsi; this
0x18050c7b3  call    ?PositionControl@CInfoPanel@@AEAAXPEAUHWND__@@KKK@Z; CInfoPanel::PositionControl(HWND__ *,ulong,ulong,ulong)
0x18050c7b8  mov     rdx, [rsi+0B30h]; hWnd
0x18050c7bf  mov     r8d, 9; unsigned int
0x18050c7c5  mov     rcx, rsi; this
0x18050c7c8  call    ?PositionControl@CInfoPanel@@AEAAXPEAUHWND__@@KKK@Z; CInfoPanel::PositionControl(HWND__ *,ulong,ulong,ulong)
0x18050c7cd  mov     rdx, [rsi+0B48h]; hWnd
0x18050c7d4  mov     r8d, 0Eh; unsigned int
0x18050c7da  mov     rcx, rsi; this
0x18050c7dd  call    ?PositionControl@CInfoPanel@@AEAAXPEAUHWND__@@KKK@Z; CInfoPanel::PositionControl(HWND__ *,ulong,ulong,ulong)
0x18050c7e2  mov     rdx, [rsi+0B38h]; hWnd
0x18050c7e9  mov     r8d, 0Fh; unsigned int
0x18050c7ef  mov     rcx, rsi; this
0x18050c7f2  call    ?PositionControl@CInfoPanel@@AEAAXPEAUHWND__@@KKK@Z; CInfoPanel::PositionControl(HWND__ *,ulong,ulong,ulong)
0x18050c7f7  mov     rdx, [rsi+0B40h]; hWnd
0x18050c7fe  mov     r8d, 10h; unsigned int
0x18050c804  mov     rcx, rsi; this
0x18050c807  call    ?PositionControl@CInfoPanel@@AEAAXPEAUHWND__@@KKK@Z; CInfoPanel::PositionControl(HWND__ *,ulong,ulong,ulong)
0x18050c80c  mov     rcx, rsi; this
0x18050c80f  call    ?PositionWinCtrlsToolBar@CInfoPanel@@AEAAXXZ; CInfoPanel::PositionWinCtrlsToolBar(void)
0x18050c814  lea     rdx, [rbp+57h+rc]; lprcSrc
0x18050c818  mov     rcx, rbx; lprcDst
0x18050c81b  call    cs:__imp_CopyRect
0x18050c821  test    r15d, r15d
0x18050c824  jz      short loc_18050C83B
0x18050c826  mov     edx, 1; int
0x18050c82b  mov     r8d, 0DCh; unsigned int
0x18050c831  mov     rcx, rsi; this
0x18050c834  call    ?AnimateInfoPanel@CInfoPanel@@AEAAXHK@Z; CInfoPanel::AnimateInfoPanel(int,ulong)
0x18050c839  jmp     short loc_18050C84A
0x18050c83b  mov     rcx, [rsi+30h]; hWnd
0x18050c83f  mov     edx, 4; nCmdShow
0x18050c844  call    cs:__imp_ShowWindow
0x18050c84a  mov     rcx, [rsi+68h]
0x18050c84e  lea     rdx, aShowsessiondia_0; "ShowSessionDiagnostics"
0x18050c855  mov     dword ptr [rsi+0C64h], 1
0x18050c85f  mov     r8d, 1
0x18050c865  mov     rax, [rcx]
0x18050c868  mov     rax, [rax+20h]
0x18050c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18050c871  mov     ebx, eax
0x18050c873  test    eax, eax
0x18050c875  jns     short loc_18050C8B7
0x18050c877  mov     rcx, cs:WPP_GLOBAL_Control
0x18050c87e  cmp     rcx, rdi
0x18050c881  jz      short loc_18050C8B7
0x18050c883  test    byte ptr [rcx+1Ch], 8
0x18050c887  jz      short loc_18050C8B7
0x18050c889  cmp     byte ptr [rcx+19h], 2
0x18050c88d  jb      short loc_18050C8B7
0x18050c88f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18050c894  mov     rcx, cs:WPP_GLOBAL_Control
0x18050c89b  lea     r8, WPP_ef1ef0a411af31a3dd1fff7fb6868a58_Traceguids
0x18050c8a2  mov     edx, 5Dh ; ']'
0x18050c8a7  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18050c8ab  mov     r9d, eax
0x18050c8ae  mov     rcx, [rcx+10h]
0x18050c8b2  call    WPP_SF_Dd
0x18050c8b7  mov     rcx, [rbp+57h+var_28]
0x18050c8bb  xor     rcx, rsp; StackCookie
0x18050c8be  call    __security_check_cookie
0x18050c8c3  mov     rbx, [rsp+0E0h+arg_10]
0x18050c8cb  add     rsp, 0C0h
0x18050c8d2  pop     r15
0x18050c8d4  pop     r14
0x18050c8d6  pop     rdi
0x18050c8d7  pop     rsi
0x18050c8d8  pop     rbp
0x18050c8d9  retn
```
