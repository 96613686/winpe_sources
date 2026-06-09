# CContainerWnd::LeaveFullScreen(void)

- ea: `0x140015778`
- end: `0x140015a13`
- name: `?LeaveFullScreen@CContainerWnd@@AEAAXXZ`
- size: `667`
- prototype: `void __fastcall(CContainerWnd *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140017538`
- `0x1400225b0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x1400155ec`
- `0x1400156f8`
- `0x140015778`
- `0x140019304`
- `0x1400a0ba4`
- `0x140113390`

## import_xrefs

- `USER32!SetWindowRgn` at `0x14001593b`
- `USER32!SetWindowRgn` at `0x14001593b`
- `USER32!SetWindowLongW` at `0x14001592b`
- `USER32!SetWindowLongW` at `0x14001592b`
- `USER32!LockWindowUpdate` at `0x140015825`
- `USER32!LockWindowUpdate` at `0x140015994`
- `USER32!LockWindowUpdate` at `0x140015825`
- `USER32!LockWindowUpdate` at `0x140015994`
- `USER32!ShowWindow` at `0x14001598c`
- `USER32!ShowWindow` at `0x14001598c`
- `USER32!SetWindowPlacement` at `0x1400158da`
- `USER32!SetWindowPlacement` at `0x1400158f8`
- `USER32!SetWindowPlacement` at `0x1400158da`
- `USER32!SetWindowPlacement` at `0x1400158f8`
- `USER32!GetWindowLongW` at `0x140015917`
- `USER32!GetWindowLongW` at `0x140015917`
- `USER32!SetWindowPos` at `0x140015973`
- `USER32!SetWindowPos` at `0x140015973`
- `USER32!GetWindowRect` at `0x140015906`
- `USER32!GetWindowRect` at `0x140015906`

## pseudocode

```c
void __fastcall CContainerWnd::LeaveFullScreen(CContainerWnd *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v3; // rax
  __int128 *v4; // rcx
  __int128 v5; // xmm2
  RECT v6; // xmm1
  unsigned int v7; // r8d
  unsigned int v8; // edx
  unsigned int v9; // r9d
  int v10; // edi
  LONG WindowLongW; // eax
  unsigned int v12; // eax
  struct tagRECT Rect; // [rsp+40h] [rbp-19h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+50h] [rbp-9h] BYREF

  Rect = 0;
  memset(&wndpl, 0, sizeof(wndpl));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      210,
      &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  ++*((_DWORD *)this + 185);
  if ( (unsigned int)CContainerWnd::IsRemoteResMatchMonitorSize(this) )
    *(_DWORD *)(*((_QWORD *)this + 95) + 201344LL) = 0;
  if ( *((_DWORD *)this + 28) )
  {
    LockWindowUpdate(*((HWND *)this + 1));
    v3 = *((_QWORD *)this + 95);
    *((_DWORD *)this + 28) = 0;
    *((_DWORD *)this + 471) = 0;
    v4 = (__int128 *)(v3 + 64);
    if ( v3 != -64 )
    {
      v5 = *v4;
      *(_OWORD *)&wndpl.length = *v4;
      *(_OWORD *)&wndpl.ptMinPosition.y = *(_OWORD *)(v3 + 80);
      v6 = *(RECT *)(v3 + 92);
      wndpl.rcNormalPosition = v6;
      if ( *(_DWORD *)(v3 + 46160) )
        goto LABEL_16;
      v7 = *((_DWORD *)this + 48);
      v8 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v6, 8)) - wndpl.rcNormalPosition.left;
      if ( v8 > v7 )
        wndpl.rcNormalPosition.right = v7 + wndpl.rcNormalPosition.left;
      v9 = *((_DWORD *)this + 49);
      if ( wndpl.rcNormalPosition.bottom - wndpl.rcNormalPosition.top <= v9 )
      {
        if ( v8 <= v7 )
          goto LABEL_16;
      }
      else
      {
        wndpl.rcNormalPosition.bottom = v9 + wndpl.rcNormalPosition.top;
      }
      *v4 = v5;
      *(_OWORD *)(v3 + 80) = *(_OWORD *)&wndpl.ptMinPosition.y;
      *(RECT *)(v3 + 92) = wndpl.rcNormalPosition;
LABEL_16:
      v10 = *((_DWORD *)this + 485);
      if ( SetWindowPlacement(*((HWND *)this + 1), &wndpl) )
      {
        if ( v10 != *((_DWORD *)this + 485) )
          SetWindowPlacement(*((HWND *)this + 1), &wndpl);
        GetWindowRect(*((HWND *)this + 1), &Rect);
        WindowLongW = GetWindowLongW(*((HWND *)this + 1), -16);
        SetWindowLongW(*((HWND *)this + 1), -16, WindowLongW | 0xC50000);
        SetWindowRgn(*((HWND *)this + 1), 0, 1);
        CContainerWnd::RecalcMaxWindowSize(this);
        SetWindowPos(
          *((HWND *)this + 1),
          (HWND)0xFFFFFFFFFFFFFFFELL,
          0,
          0,
          Rect.right - Rect.left,
          Rect.bottom - Rect.top,
          0x32u);
        if ( (unsigned int)CContainerWnd::IsRemoteResMatchMonitorSize(this) )
          ShowWindow(*((HWND *)this + 1), 1);
        LockWindowUpdate(0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v12);
        }
        CClientUtilsWin32::NotifyShellOfFullScreen(
          *((HWND *)this + 1),
          0,
          (struct ITaskbarList2 **)this + 229,
          (int *)this + 460);
      }
    }
  }
  CContainerWnd::LeaveEventHandler(this);
}

```

## disassembly

```asm
0x140015778  push    rbp
0x14001577a  push    rbx
0x14001577b  push    rdi
0x14001577c  push    r15
0x14001577e  lea     rbp, [rsp-3Fh]
0x140015783  sub     rsp, 98h
0x14001578a  mov     rax, cs:__security_cookie
0x140015791  xor     rax, rsp
0x140015794  mov     [rbp+57h+var_30], rax
0x140015798  xorps   xmm1, xmm1
0x14001579b  xorps   xmm0, xmm0
0x14001579e  movups  xmmword ptr [rbp+57h+wndpl.ptMinPosition.y], xmm1
0x1400157a2  mov     rbx, rcx
0x1400157a5  movups  xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left], xmm1
0x1400157a9  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1400157ad  movups  xmmword ptr [rbp+57h+wndpl.length], xmm1
0x1400157b1  mov     rax, cs:WPP_GLOBAL_Control
0x1400157b8  lea     r15, WPP_GLOBAL_Control
0x1400157bf  cmp     rax, r15
0x1400157c2  jz      short loc_1400157F4
0x1400157c4  test    byte ptr [rax+1Ch], 1
0x1400157c8  jz      short loc_1400157F4
0x1400157ca  cmp     byte ptr [rax+19h], 4
0x1400157ce  jb      short loc_1400157F4
0x1400157d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400157d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157dc  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400157e3  mov     edx, 0D2h
0x1400157e8  mov     r9d, eax
0x1400157eb  mov     rcx, [rcx+10h]
0x1400157ef  call    WPP_SF_d
0x1400157f4  inc     dword ptr [rbx+2E4h]
0x1400157fa  mov     rcx, rbx; this
0x1400157fd  call    ?IsRemoteResMatchMonitorSize@CContainerWnd@@AEAAHXZ; CContainerWnd::IsRemoteResMatchMonitorSize(void)
0x140015802  test    eax, eax
0x140015804  jz      short loc_140015817
0x140015806  mov     rax, [rbx+2F8h]
0x14001580d  mov     dword ptr [rax+31280h], 0
0x140015817  cmp     dword ptr [rbx+70h], 0
0x14001581b  jz      loc_1400159F2
0x140015821  mov     rcx, [rbx+8]; hWndLock
0x140015825  call    cs:__imp_LockWindowUpdate
0x14001582b  mov     rax, [rbx+2F8h]
0x140015832  mov     dword ptr [rbx+70h], 0
0x140015839  mov     dword ptr [rbx+75Ch], 0
0x140015843  lea     rcx, [rax+40h]
0x140015847  test    rcx, rcx
0x14001584a  jz      loc_1400159F2
0x140015850  movups  xmm2, xmmword ptr [rcx]
0x140015853  movups  xmmword ptr [rbp+57h+wndpl.length], xmm2
0x140015857  movups  xmm0, xmmword ptr [rcx+10h]
0x14001585b  movups  xmmword ptr [rbp+57h+wndpl.ptMinPosition.y], xmm0
0x14001585f  movups  xmm1, xmmword ptr [rcx+1Ch]
0x140015863  movups  xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left], xmm1
0x140015867  cmp     dword ptr [rax+0B450h], 0
0x14001586e  jnz     short loc_1400158CC
0x140015870  mov     rax, qword ptr [rbp+57h+wndpl.ptMaxPosition.y]
0x140015874  mov     r8d, [rbx+0C0h]
0x14001587b  shr     rax, 20h
0x14001587f  psrldq  xmm1, 8
0x140015884  movd    edx, xmm1
0x140015888  sub     edx, eax
0x14001588a  cmp     edx, r8d
0x14001588d  jbe     short loc_140015895
0x14001588f  add     eax, r8d
0x140015892  mov     [rbp+57h+wndpl.rcNormalPosition.right], eax
0x140015895  mov     eax, [rbp+57h+wndpl.rcNormalPosition.bottom]
0x140015898  mov     r10d, [rbp+57h+wndpl.rcNormalPosition.top]
0x14001589c  sub     eax, r10d
0x14001589f  mov     r9d, [rbx+0C4h]
0x1400158a6  cmp     eax, r9d
0x1400158a9  jbe     short loc_1400158B4
0x1400158ab  lea     eax, [r9+r10]
0x1400158af  mov     [rbp+57h+wndpl.rcNormalPosition.bottom], eax
0x1400158b2  jmp     short loc_1400158B9
0x1400158b4  cmp     edx, r8d
0x1400158b7  jbe     short loc_1400158CC
0x1400158b9  movups  xmmword ptr [rcx], xmm2
0x1400158bc  movups  xmm0, xmmword ptr [rbp+57h+wndpl.ptMinPosition.y]
0x1400158c0  movups  xmmword ptr [rcx+10h], xmm0
0x1400158c4  movups  xmm1, xmmword ptr [rbp+57h+wndpl.rcNormalPosition.left]
0x1400158c8  movups  xmmword ptr [rcx+1Ch], xmm1
0x1400158cc  mov     rcx, [rbx+8]; hWnd
0x1400158d0  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x1400158d4  mov     edi, [rbx+794h]
0x1400158da  call    cs:__imp_SetWindowPlacement
0x1400158e0  test    eax, eax
0x1400158e2  jz      loc_1400159F2
0x1400158e8  cmp     edi, [rbx+794h]
0x1400158ee  jz      short loc_1400158FE
0x1400158f0  mov     rcx, [rbx+8]; hWnd
0x1400158f4  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x1400158f8  call    cs:__imp_SetWindowPlacement
0x1400158fe  mov     rcx, [rbx+8]; hWnd
0x140015902  lea     rdx, [rbp+57h+Rect]; lpRect
0x140015906  call    cs:__imp_GetWindowRect
0x14001590c  mov     rcx, [rbx+8]; hWnd
0x140015910  mov     edi, 0FFFFFFF0h
0x140015915  mov     edx, edi; nIndex
0x140015917  call    cs:__imp_GetWindowLongW
0x14001591d  mov     rcx, [rbx+8]; hWnd
0x140015921  mov     edx, edi; nIndex
0x140015923  or      eax, 0C50000h
0x140015928  mov     r8d, eax; dwNewLong
0x14001592b  call    cs:__imp_SetWindowLongW
0x140015931  mov     rcx, [rbx+8]; hWnd
0x140015935  lea     r8d, [rdi+11h]; bRedraw
0x140015939  xor     edx, edx; hRgn
0x14001593b  call    cs:__imp_SetWindowRgn
0x140015941  mov     rcx, rbx; this
0x140015944  call    ?RecalcMaxWindowSize@CContainerWnd@@AEAAXXZ; CContainerWnd::RecalcMaxWindowSize(void)
0x140015949  mov     ecx, [rbp+57h+Rect.bottom]
0x14001594c  xor     r9d, r9d; Y
0x14001594f  sub     ecx, [rbp+57h+Rect.top]
0x140015952  xor     r8d, r8d; X
0x140015955  mov     eax, [rbp+57h+Rect.right]
0x140015958  sub     eax, [rbp+57h+Rect.left]
0x14001595b  mov     [rsp+0B0h+uFlags], 32h ; '2'; uFlags
0x140015963  lea     rdx, [r9-2]; hWndInsertAfter
0x140015967  mov     [rsp+0B0h+cy], ecx; cy
0x14001596b  mov     rcx, [rbx+8]; hWnd
0x14001596f  mov     [rsp+0B0h+var_90], eax; cx
0x140015973  call    cs:__imp_SetWindowPos
0x140015979  mov     rcx, rbx; this
0x14001597c  call    ?IsRemoteResMatchMonitorSize@CContainerWnd@@AEAAHXZ; CContainerWnd::IsRemoteResMatchMonitorSize(void)
0x140015981  test    eax, eax
0x140015983  jz      short loc_140015992
0x140015985  mov     rcx, [rbx+8]; hWnd
0x140015989  lea     edx, [rdi+11h]; nCmdShow
0x14001598c  call    cs:__imp_ShowWindow
0x140015992  xor     ecx, ecx; hWndLock
0x140015994  call    cs:__imp_LockWindowUpdate
0x14001599a  mov     rax, cs:WPP_GLOBAL_Control
0x1400159a1  cmp     rax, r15
0x1400159a4  jz      short loc_1400159D9
0x1400159a6  test    dword ptr [rax+1Ch], 100h
0x1400159ad  jz      short loc_1400159D9
0x1400159af  cmp     byte ptr [rax+19h], 5
0x1400159b3  jb      short loc_1400159D9
0x1400159b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400159ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400159c1  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400159c8  mov     edx, 0D3h
0x1400159cd  mov     r9d, eax
0x1400159d0  mov     rcx, [rcx+10h]
0x1400159d4  call    WPP_SF_d
0x1400159d9  mov     rcx, [rbx+8]; HWND
0x1400159dd  lea     r9, [rbx+730h]; int *
0x1400159e4  lea     r8, [rbx+728h]; struct ITaskbarList2 **
0x1400159eb  xor     edx, edx; int
0x1400159ed  call    ?NotifyShellOfFullScreen@CClientUtilsWin32@@SAHPEAUHWND__@@HPEAPEAUITaskbarList2@@PEAH@Z; CClientUtilsWin32::NotifyShellOfFullScreen(HWND__ *,int,ITaskbarList2 * *,int *)
0x1400159f2  mov     rcx, rbx; this
0x1400159f5  call    ?LeaveEventHandler@CContainerWnd@@QEAAJXZ; CContainerWnd::LeaveEventHandler(void)
0x1400159fa  mov     rcx, [rbp+57h+var_30]
0x1400159fe  xor     rcx, rsp; StackCookie
0x140015a01  call    __security_check_cookie
0x140015a06  add     rsp, 98h
0x140015a0d  pop     r15
0x140015a0f  pop     rdi
0x140015a10  pop     rbx
0x140015a11  pop     rbp
0x140015a12  retn
```
