# CContainerWnd::OnRemoteDesktopSizeNotify(long,long)

- ea: `0x140017538`
- end: `0x14001785c`
- name: `?OnRemoteDesktopSizeNotify@CContainerWnd@@QEAAXJJ@Z`
- size: `804`
- prototype: `void __fastcall(CContainerWnd *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x140019ff8`
- `0x14002d28c`

## callees

- `0x14000b7d8`
- `0x1400132fc`
- `0x140014794`
- `0x140015390`
- `0x1400156f8`
- `0x140015778`
- `0x140017538`
- `0x140019304`
- `0x14001dec0`
- `0x14001df1c`
- `0x14001e158`
- `0x14001e404`
- `0x14001e6d4`
- `0x14001e8dc`
- `0x140113390`

## import_xrefs

- `USER32!MoveWindow` at `0x140017763`
- `USER32!MoveWindow` at `0x140017763`
- `USER32!GetWindowLongW` at `0x140017632`
- `USER32!GetWindowLongW` at `0x140017643`
- `USER32!GetWindowLongW` at `0x140017632`
- `USER32!GetWindowLongW` at `0x140017643`
- `USER32!CopyRect` at `0x1400176e1`
- `USER32!CopyRect` at `0x1400176e1`
- `USER32!IntersectRect` at `0x1400176fb`
- `USER32!IntersectRect` at `0x1400176fb`
- `USER32!GetWindowRect` at `0x140017623`
- `USER32!GetWindowRect` at `0x140017623`
- `USER32!GetWindowPlacement` at `0x1400177a8`
- `USER32!GetWindowPlacement` at `0x1400177a8`
- `USER32!IsIconic` at `0x14001777a`
- `USER32!IsIconic` at `0x14001777a`

## pseudocode

```c
void __fastcall CContainerWnd::OnRemoteDesktopSizeNotify(CContainerWnd *this, int a2, int a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND v7; // rcx
  LONG WindowLongW; // ebx
  LONG v9; // eax
  int v10; // r9d
  int v11; // ebx
  int v12; // eax
  int v13; // ebx
  int SystemMetrics; // eax
  HWND v15; // rcx
  HMONITOR v16; // rax
  __int64 v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // rdx
  HWND v20; // rcx
  __int64 v21; // rax
  unsigned int v22; // [rsp+30h] [rbp-49h] BYREF
  RECT rcSrc1; // [rsp+38h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-31h] BYREF
  struct tagRECT v25; // [rsp+58h] [rbp-21h] BYREF
  WINDOWPLACEMENT v26; // [rsp+68h] [rbp-11h] BYREF
  struct tagRECT rcDst; // [rsp+98h] [rbp+1Fh] BYREF

  ++*((_DWORD *)this + 185);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      221,
      &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      a2,
      a3);
  }
  *((_DWORD *)this + 50) = a2;
  *((_DWORD *)this + 51) = a3;
  CContainerWnd::RecalcMaxWindowSize(this);
  if ( *((_DWORD *)this + 28) )
  {
    if ( (unsigned int)CContainerWnd::IsConnected(this) )
    {
      CContainerWnd::LeaveFullScreen(this);
      CContainerWnd::EnterFullScreen(this);
    }
  }
  else
  {
    v22 = 0;
    rcSrc1 = 0;
    rcDst = 0;
    Rect = 0;
    v25 = 0;
    CContainerWnd::GetZoomLevel(this, &v22);
    v7 = (HWND)*((_QWORD *)this + 1);
    rcSrc1.right = v22 * a2 / 0x64;
    rcSrc1.bottom = v22 * a3 / 0x64;
    GetWindowRect(v7, &Rect);
    WindowLongW = GetWindowLongW(*((HWND *)this + 1), -20);
    v9 = GetWindowLongW(*((HWND *)this + 1), -16);
    CContainerWnd::_AdjustWindowRectEx(this, &rcSrc1, v9, v10, WindowLongW);
    v11 = Rect.left - rcSrc1.left;
    v12 = v11 + CContainerWnd::_GetSystemMetrics(this, 20);
    v13 = Rect.top - rcSrc1.top;
    rcSrc1.right += v12;
    SystemMetrics = CContainerWnd::_GetSystemMetrics(this, 3);
    v15 = (HWND)*((_QWORD *)this + 1);
    rcSrc1.bottom += v13 + SystemMetrics;
    rcSrc1.left = Rect.left;
    rcSrc1.top = Rect.top;
    memset(&v26, 0, 40);
    v26.length = 40;
    v16 = xMonitorFromWindow(v15, 2u);
    if ( v16 && xGetMonitorInfo(v16, (LPMONITORINFO)&v26) && CopyRect(&rcDst, (const RECT *)&v26.ptMaxPosition) )
    {
      if ( IntersectRect(&v25, &rcSrc1, &rcDst) )
      {
        MoveWindow(*((HWND *)this + 1), v25.left, v25.top, v25.right - v25.left, v25.bottom - v25.top, 0);
        if ( *((_DWORD *)this + 323) )
        {
          if ( !IsIconic(*((HWND *)this + 1)) )
          {
            v20 = (HWND)*((_QWORD *)this + 1);
            v26.length = 44;
            memset(&v26.flags, 0, 40);
            if ( GetWindowPlacement(v20, &v26) )
            {
              v21 = *((_QWORD *)this + 95);
              *(_OWORD *)(v21 + 64) = *(_OWORD *)&v26.length;
              *(_OWORD *)(v21 + 80) = *(_OWORD *)&v26.ptMinPosition.y;
              *(RECT *)(v21 + 92) = v26.rcNormalPosition;
            }
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = *((_QWORD *)this + 1);
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 223;
LABEL_22:
        WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v18, v17);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = *((_QWORD *)this + 1);
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      v19 = 222;
      goto LABEL_22;
    }
  }
  CContainerWnd::LeaveEventHandler(this);
}

```

## disassembly

```asm
0x140017538  push    rbp
0x14001753a  push    rbx
0x14001753b  push    rsi
0x14001753c  push    rdi
0x14001753d  push    r15
0x14001753f  lea     rbp, [rsp-37h]
0x140017544  sub     rsp, 0B0h
0x14001754b  mov     rax, cs:__security_cookie
0x140017552  xor     rax, rsp
0x140017555  mov     [rbp+57h+var_28], rax
0x140017559  inc     dword ptr [rcx+2E4h]
0x14001755f  mov     esi, r8d
0x140017562  mov     ebx, edx
0x140017564  mov     rdi, rcx
0x140017567  mov     rax, cs:WPP_GLOBAL_Control
0x14001756e  lea     r15, WPP_GLOBAL_Control
0x140017575  cmp     rax, r15
0x140017578  jz      short loc_1400175B2
0x14001757a  test    byte ptr [rax+1Ch], 1
0x14001757e  jz      short loc_1400175B2
0x140017580  cmp     byte ptr [rax+19h], 4
0x140017584  jb      short loc_1400175B2
0x140017586  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001758b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017592  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140017599  mov     edx, 0DDh
0x14001759e  mov     [rsp+0D0h+bRepaint], esi
0x1400175a2  mov     r9d, eax
0x1400175a5  mov     [rsp+0D0h+nHeight], ebx
0x1400175a9  mov     rcx, [rcx+10h]
0x1400175ad  call    WPP_SF_DLD
0x1400175b2  mov     rcx, rdi; this
0x1400175b5  mov     [rdi+0C8h], ebx
0x1400175bb  mov     [rdi+0CCh], esi
0x1400175c1  call    ?RecalcMaxWindowSize@CContainerWnd@@AEAAXXZ; CContainerWnd::RecalcMaxWindowSize(void)
0x1400175c6  cmp     dword ptr [rdi+70h], 0
0x1400175ca  mov     rcx, rdi; this
0x1400175cd  jnz     loc_140017821
0x1400175d3  xorps   xmm0, xmm0
0x1400175d6  mov     [rbp+57h+var_A0], 0
0x1400175dd  xorps   xmm1, xmm1
0x1400175e0  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x1400175e4  movdqu  xmmword ptr [rbp+57h+rcSrc1.left], xmm0
0x1400175e9  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1400175ed  movups  xmmword ptr [rbp+57h+Rect.left], xmm1
0x1400175f1  movups  xmmword ptr [rbp+57h+var_78.left], xmm0
0x1400175f5  call    ?GetZoomLevel@CContainerWnd@@AEAAXPEAK@Z; CContainerWnd::GetZoomLevel(ulong *)
0x1400175fa  imul    ebx, [rbp+57h+var_A0]
0x1400175fe  mov     ecx, 51EB851Fh
0x140017603  imul    esi, [rbp+57h+var_A0]
0x140017607  mov     eax, ecx
0x140017609  mul     ebx
0x14001760b  mov     eax, ecx
0x14001760d  mov     rcx, [rdi+8]; hWnd
0x140017611  shr     edx, 5
0x140017614  mov     [rbp+57h+rcSrc1.right], edx
0x140017617  mul     esi
0x140017619  shr     edx, 5
0x14001761c  mov     [rbp+57h+rcSrc1.bottom], edx
0x14001761f  lea     rdx, [rbp+57h+Rect]; lpRect
0x140017623  call    cs:__imp_GetWindowRect
0x140017629  mov     rcx, [rdi+8]; hWnd
0x14001762d  mov     edx, 0FFFFFFECh; nIndex
0x140017632  call    cs:__imp_GetWindowLongW
0x140017638  mov     rcx, [rdi+8]; hWnd
0x14001763c  mov     edx, 0FFFFFFF0h; nIndex
0x140017641  mov     ebx, eax
0x140017643  call    cs:__imp_GetWindowLongW
0x140017649  lea     rdx, [rbp+57h+rcSrc1]; struct tagRECT *
0x14001764d  mov     [rsp+0D0h+nHeight], ebx; unsigned int
0x140017651  mov     r8d, eax; unsigned int
0x140017654  mov     rcx, rdi; this
0x140017657  call    ?_AdjustWindowRectEx@CContainerWnd@@IEAAHPEAUtagRECT@@KHK@Z; CContainerWnd::_AdjustWindowRectEx(tagRECT *,ulong,int,ulong)
0x14001765c  mov     ebx, [rbp+57h+Rect.left]
0x14001765f  mov     edx, 14h; int
0x140017664  sub     ebx, [rbp+57h+rcSrc1.left]
0x140017667  mov     rcx, rdi; this
0x14001766a  call    ?_GetSystemMetrics@CContainerWnd@@IEAAHH@Z; CContainerWnd::_GetSystemMetrics(int)
0x14001766f  add     eax, ebx
0x140017671  mov     edx, 3; int
0x140017676  mov     ebx, [rbp+57h+Rect.top]
0x140017679  mov     rcx, rdi; this
0x14001767c  sub     ebx, [rbp+57h+rcSrc1.top]
0x14001767f  add     [rbp+57h+rcSrc1.right], eax
0x140017682  call    ?_GetSystemMetrics@CContainerWnd@@IEAAHH@Z; CContainerWnd::_GetSystemMetrics(int)
0x140017687  mov     rcx, [rdi+8]; HWND
0x14001768b  add     eax, ebx
0x14001768d  add     [rbp+57h+rcSrc1.bottom], eax
0x140017690  xorps   xmm0, xmm0
0x140017693  mov     eax, [rbp+57h+Rect.left]
0x140017696  mov     [rbp+57h+rcSrc1.left], eax
0x140017699  mov     eax, [rbp+57h+Rect.top]
0x14001769c  mov     [rbp+57h+rcSrc1.top], eax
0x14001769f  xor     eax, eax
0x1400176a1  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x1400176a5  mov     qword ptr [rbp+57h+var_68.rcWork.bottom], rax
0x1400176a9  movups  xmmword ptr [rbp+57h+var_68.rcMonitor.bottom], xmm0
0x1400176ad  lea     edx, [rax+2]; DWORD
0x1400176b0  mov     [rbp+57h+var_68.cbSize], 28h ; '('
0x1400176b7  call    xMonitorFromWindow
0x1400176bc  test    rax, rax
0x1400176bf  jz      loc_1400177D7
0x1400176c5  lea     rdx, [rbp+57h+var_68]; LPMONITORINFO
0x1400176c9  mov     rcx, rax; HMONITOR
0x1400176cc  call    xGetMonitorInfo
0x1400176d1  test    eax, eax
0x1400176d3  jz      loc_1400177D7
0x1400176d9  lea     rdx, [rbp+57h+var_68.rcWork]; lprcSrc
0x1400176dd  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1400176e1  call    cs:__imp_CopyRect
0x1400176e7  test    eax, eax
0x1400176e9  jz      loc_1400177D7
0x1400176ef  lea     r8, [rbp+57h+rcDst]; lprcSrc2
0x1400176f3  lea     rdx, [rbp+57h+rcSrc1]; lprcSrc1
0x1400176f7  lea     rcx, [rbp+57h+var_78]; lprcDst
0x1400176fb  call    cs:__imp_IntersectRect
0x140017701  test    eax, eax
0x140017703  jnz     short loc_14001773F
0x140017705  mov     rax, cs:WPP_GLOBAL_Control
0x14001770c  cmp     rax, r15
0x14001770f  jz      loc_14001783A
0x140017715  test    dword ptr [rax+1Ch], 100h
0x14001771c  jz      loc_14001783A
0x140017722  cmp     byte ptr [rax+19h], 2
0x140017726  jb      loc_14001783A
0x14001772c  mov     rbx, [rdi+8]
0x140017730  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140017735  mov     edx, 0DFh
0x14001773a  jmp     loc_140017800
0x14001773f  mov     eax, [rbp+57h+var_78.bottom]
0x140017742  mov     r8d, [rbp+57h+var_78.top]; Y
0x140017746  sub     eax, r8d
0x140017749  mov     r9d, [rbp+57h+var_78.right]
0x14001774d  mov     edx, [rbp+57h+var_78.left]; X
0x140017750  sub     r9d, edx; nWidth
0x140017753  mov     rcx, [rdi+8]; hWnd
0x140017757  mov     [rsp+0D0h+bRepaint], 0; bRepaint
0x14001775f  mov     [rsp+0D0h+nHeight], eax; nHeight
0x140017763  call    cs:__imp_MoveWindow
0x140017769  cmp     dword ptr [rdi+50Ch], 0
0x140017770  jz      loc_14001783A
0x140017776  mov     rcx, [rdi+8]; hWnd
0x14001777a  call    cs:__imp_IsIconic
0x140017780  test    eax, eax
0x140017782  jnz     loc_14001783A
0x140017788  mov     rcx, [rdi+8]; hWnd
0x14001778c  lea     rdx, [rbp+57h+var_68]; lpwndpl
0x140017790  xorps   xmm0, xmm0
0x140017793  mov     [rbp+57h+var_68.cbSize], 2Ch ; ','
0x14001779a  xor     eax, eax
0x14001779c  movups  xmmword ptr [rbp+57h+var_68.rcMonitor.left], xmm0
0x1400177a0  mov     qword ptr [rbp+57h+var_68.dwFlags], rax
0x1400177a4  movups  xmmword ptr [rbp+57h+var_68.rcWork.left], xmm0
0x1400177a8  call    cs:__imp_GetWindowPlacement
0x1400177ae  test    eax, eax
0x1400177b0  jz      loc_14001783A
0x1400177b6  movups  xmm0, xmmword ptr [rbp+57h+var_68.cbSize]
0x1400177ba  mov     rax, [rdi+2F8h]
0x1400177c1  movups  xmmword ptr [rax+40h], xmm0
0x1400177c5  movups  xmm1, xmmword ptr [rbp+57h+var_68.rcMonitor.bottom]
0x1400177c9  movups  xmmword ptr [rax+50h], xmm1
0x1400177cd  movups  xmm0, xmmword ptr [rbp+57h+var_68.rcWork.right]
0x1400177d1  movups  xmmword ptr [rax+5Ch], xmm0
0x1400177d5  jmp     short loc_14001783A
0x1400177d7  mov     rax, cs:WPP_GLOBAL_Control
0x1400177de  cmp     rax, r15
0x1400177e1  jz      short loc_14001783A
0x1400177e3  test    dword ptr [rax+1Ch], 100h
0x1400177ea  jz      short loc_14001783A
0x1400177ec  cmp     byte ptr [rax+19h], 2
0x1400177f0  jb      short loc_14001783A
0x1400177f2  mov     rbx, [rdi+8]
0x1400177f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400177fb  mov     edx, 0DEh
0x140017800  mov     rcx, cs:WPP_GLOBAL_Control
0x140017807  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x14001780e  mov     r9d, eax
0x140017811  mov     qword ptr [rsp+0D0h+nHeight], rbx
0x140017816  mov     rcx, [rcx+10h]
0x14001781a  call    WPP_SF_Dq
0x14001781f  jmp     short loc_14001783A
0x140017821  call    ?IsConnected@CContainerWnd@@QEAAHXZ; CContainerWnd::IsConnected(void)
0x140017826  test    eax, eax
0x140017828  jz      short loc_14001783A
0x14001782a  mov     rcx, rdi; this
0x14001782d  call    ?LeaveFullScreen@CContainerWnd@@AEAAXXZ; CContainerWnd::LeaveFullScreen(void)
0x140017832  mov     rcx, rdi; this
0x140017835  call    ?EnterFullScreen@CContainerWnd@@AEAAXXZ; CContainerWnd::EnterFullScreen(void)
0x14001783a  mov     rcx, rdi; this
0x14001783d  call    ?LeaveEventHandler@CContainerWnd@@QEAAJXZ; CContainerWnd::LeaveEventHandler(void)
0x140017842  mov     rcx, [rbp+57h+var_28]
0x140017846  xor     rcx, rsp; StackCookie
0x140017849  call    __security_check_cookie
0x14001784e  add     rsp, 0B0h
0x140017855  pop     r15
0x140017857  pop     rdi
0x140017858  pop     rsi
0x140017859  pop     rbx
0x14001785a  pop     rbp
0x14001785b  retn
```
