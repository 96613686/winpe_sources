# SplashWindow::ButtonWndProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x140044cb0`
- end: `0x140044e91`
- name: `?ButtonWndProc@SplashWindow@@CA_JPEAUHWND__@@I_K_J11@Z`
- size: `481`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001020`
- `0x140044bc4`
- `0x140044cb0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x140044dd7`
- `KERNEL32!MulDiv` at `0x140044def`
- `KERNEL32!MulDiv` at `0x140044e0e`
- `KERNEL32!MulDiv` at `0x140044e2e`
- `KERNEL32!MulDiv` at `0x140044dd7`
- `KERNEL32!MulDiv` at `0x140044def`
- `KERNEL32!MulDiv` at `0x140044e0e`
- `KERNEL32!MulDiv` at `0x140044e2e`
- `USER32!GetClientRect` at `0x140044d21`
- `USER32!GetClientRect` at `0x140044d21`
- `USER32!MapWindowPoints` at `0x140044d37`
- `USER32!MapWindowPoints` at `0x140044d37`
- `USER32!RedrawWindow` at `0x140044d5e`
- `USER32!RedrawWindow` at `0x140044d5e`
- `USER32!BeginPaint` at `0x140044d84`
- `USER32!BeginPaint` at `0x140044d84`
- `USER32!FillRect` at `0x140044db2`
- `USER32!FillRect` at `0x140044db2`
- `USER32!EndPaint` at `0x140044e4a`
- `USER32!EndPaint` at `0x140044e4a`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x140044e5e`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x140044e5e`
- `COMCTL32!__imp_DefSubclassProc` at `0x140044e6f`
- `COMCTL32!__imp_DefSubclassProc` at `0x140044e6f`
- `GDI32!CreateSolidBrush` at `0x140044d9f`
- `GDI32!CreateSolidBrush` at `0x140044d9f`
- `GDI32!DeleteObject` at `0x140044dbb`
- `GDI32!DeleteObject` at `0x140044dbb`

## pseudocode

```c
LRESULT __fastcall SplashWindow::ButtonWndProc(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam)
{
  SplashWindow *v8; // rbx
  HWND v9; // rbx
  HDC v10; // rax
  SplashWindow *v11; // rdx
  HDC v12; // r14
  HBRUSH SolidBrush; // rbx
  LONG v14; // edi
  LONG v15; // ebx
  LONG v16; // eax
  struct tagRECT Rect; // [rsp+20h] [rbp-69h] BYREF
  RECT rcUpdate; // [rsp+30h] [rbp-59h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-49h] BYREF

  if ( uMsg == 2 )
  {
    RemoveWindowSubclass(hWnd, SplashWindow::ButtonWndProc, 0);
    return DefSubclassProc(hWnd, uMsg, wParam, lParam);
  }
  if ( uMsg != 15 )
  {
    if ( uMsg == 512 )
    {
      v8 = SplashWindow::sm_pThis;
      if ( *((_BYTE *)SplashWindow::sm_pThis + 40) )
        return DefSubclassProc(hWnd, uMsg, wParam, lParam);
      *((_BYTE *)SplashWindow::sm_pThis + 40) = 1;
    }
    else
    {
      if ( uMsg != 675 )
        return DefSubclassProc(hWnd, uMsg, wParam, lParam);
      v8 = SplashWindow::sm_pThis;
      if ( !*((_BYTE *)SplashWindow::sm_pThis + 40) )
        return DefSubclassProc(hWnd, uMsg, wParam, lParam);
      *((_BYTE *)SplashWindow::sm_pThis + 40) = 0;
    }
    v9 = (HWND)*((_QWORD *)v8 + 1);
    GetClientRect(hWnd, &Rect);
    MapWindowPoints(hWnd, v9, (LPPOINT)&Rect, 2u);
    rcUpdate = Rect;
    RedrawWindow(*((HWND *)SplashWindow::sm_pThis + 1), &rcUpdate, 0, 5u);
    return DefSubclassProc(hWnd, uMsg, wParam, lParam);
  }
  v10 = BeginPaint(hWnd, &Paint);
  v11 = SplashWindow::sm_pThis;
  v12 = v10;
  if ( *((_BYTE *)SplashWindow::sm_pThis + 40) )
  {
    SolidBrush = CreateSolidBrush(0x1C2BC4u);
    FillRect(v12, &Paint.rcPaint, SolidBrush);
    DeleteObject(SolidBrush);
    v11 = SplashWindow::sm_pThis;
  }
  v14 = MulDiv(8, *((_DWORD *)v11 + 16), 96);
  v15 = MulDiv(8, *((_DWORD *)SplashWindow::sm_pThis + 17), 96);
  v16 = MulDiv(20, *((_DWORD *)SplashWindow::sm_pThis + 16), 96);
  Rect.left = v14;
  Rect.top = v15;
  Rect.right = v16;
  Rect.bottom = MulDiv(20, *((_DWORD *)SplashWindow::sm_pThis + 17), 96);
  DrawX(v12, &Rect);
  EndPaint(hWnd, &Paint);
  return 0;
}

```

## disassembly

```asm
0x140044cb0  push    rbp
0x140044cb2  push    rbx
0x140044cb3  push    rsi
0x140044cb4  push    rdi
0x140044cb5  push    r14
0x140044cb7  push    r15
0x140044cb9  lea     rbp, [rsp-1Fh]
0x140044cbe  sub     rsp, 0A8h
0x140044cc5  mov     rax, cs:__security_cookie
0x140044ccc  xor     rax, rsp
0x140044ccf  mov     [rbp+47h+var_40], rax
0x140044cd3  mov     r15, r9
0x140044cd6  mov     r14, r8
0x140044cd9  mov     edi, edx
0x140044cdb  mov     rsi, rcx
0x140044cde  cmp     edx, 2
0x140044ce1  jz      loc_140044E54
0x140044ce7  cmp     edx, 0Fh
0x140044cea  jz      loc_140044D80
0x140044cf0  cmp     edx, 200h
0x140044cf6  jz      short loc_140044D69
0x140044cf8  cmp     edx, 2A3h
0x140044cfe  jnz     loc_140044E64
0x140044d04  mov     rbx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044d0b  cmp     byte ptr [rbx+28h], 0
0x140044d0f  jz      loc_140044E64
0x140044d15  mov     byte ptr [rbx+28h], 0
0x140044d19  mov     rbx, [rbx+8]
0x140044d1d  lea     rdx, [rbp+47h+Rect]; lpRect
0x140044d21  call    cs:__imp_GetClientRect
0x140044d27  mov     r9d, 2; cPoints
0x140044d2d  lea     r8, [rbp+47h+Rect]; lpPoints
0x140044d31  mov     rdx, rbx; hWndTo
0x140044d34  mov     rcx, rsi; hWndFrom
0x140044d37  call    cs:__imp_MapWindowPoints
0x140044d3d  mov     rcx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044d44  lea     rdx, [rbp+47h+rcUpdate]; lprcUpdate
0x140044d48  movaps  xmm0, xmmword ptr [rbp+47h+Rect.left]
0x140044d4c  mov     r9d, 5; flags
0x140044d52  movdqa  xmmword ptr [rbp+47h+rcUpdate.left], xmm0
0x140044d57  xor     r8d, r8d; hrgnUpdate
0x140044d5a  mov     rcx, [rcx+8]; hWnd
0x140044d5e  call    cs:__imp_RedrawWindow
0x140044d64  jmp     loc_140044E64
0x140044d69  mov     rbx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044d70  cmp     byte ptr [rbx+28h], 0
0x140044d74  jnz     loc_140044E64
0x140044d7a  mov     byte ptr [rbx+28h], 1
0x140044d7e  jmp     short loc_140044D19
0x140044d80  lea     rdx, [rbp+47h+Paint]; lpPaint
0x140044d84  call    cs:__imp_BeginPaint
0x140044d8a  mov     rdx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044d91  mov     r14, rax
0x140044d94  cmp     byte ptr [rdx+28h], 0
0x140044d98  jz      short loc_140044DC8
0x140044d9a  mov     ecx, 1C2BC4h; color
0x140044d9f  call    cs:__imp_CreateSolidBrush
0x140044da5  lea     rdx, [rbp+47h+Paint.rcPaint]; lprc
0x140044da9  mov     rcx, r14; hDC
0x140044dac  mov     r8, rax; hbr
0x140044daf  mov     rbx, rax
0x140044db2  call    cs:__imp_FillRect
0x140044db8  mov     rcx, rbx; ho
0x140044dbb  call    cs:__imp_DeleteObject
0x140044dc1  mov     rdx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044dc8  mov     edx, [rdx+40h]; nNumerator
0x140044dcb  mov     r8d, 60h ; '`'; nDenominator
0x140044dd1  lea     ebx, [r8-58h]
0x140044dd5  mov     ecx, ebx; nNumber
0x140044dd7  call    cs:__imp_MulDiv
0x140044ddd  mov     rdx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044de4  lea     r8d, [rbx+58h]; nDenominator
0x140044de8  mov     ecx, ebx; nNumber
0x140044dea  mov     edi, eax
0x140044dec  mov     edx, [rdx+44h]; nNumerator
0x140044def  call    cs:__imp_MulDiv
0x140044df5  mov     rdx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044dfc  mov     r8d, 60h ; '`'; nDenominator
0x140044e02  mov     ebx, eax
0x140044e04  mov     edx, [rdx+40h]; nNumerator
0x140044e07  lea     r15d, [r8-4Ch]
0x140044e0b  mov     ecx, r15d; nNumber
0x140044e0e  call    cs:__imp_MulDiv
0x140044e14  mov     rdx, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x140044e1b  lea     r8d, [r15+4Ch]; nDenominator
0x140044e1f  mov     ecx, r15d; nNumber
0x140044e22  mov     [rbp+47h+Rect.left], edi
0x140044e25  mov     [rbp+47h+Rect.top], ebx
0x140044e28  mov     [rbp+47h+Rect.right], eax
0x140044e2b  mov     edx, [rdx+44h]; nNumerator
0x140044e2e  call    cs:__imp_MulDiv
0x140044e34  lea     rdx, [rbp+47h+Rect]; struct tagRECT
0x140044e38  mov     rcx, r14; HDC
0x140044e3b  mov     [rbp+47h+Rect.bottom], eax
0x140044e3e  call    ?DrawX@@YAXPEAUHDC__@@UtagRECT@@@Z; DrawX(HDC__ *,tagRECT)
0x140044e43  lea     rdx, [rbp+47h+Paint]; lpPaint
0x140044e47  mov     rcx, rsi; hWnd
0x140044e4a  call    cs:__imp_EndPaint
0x140044e50  xor     eax, eax
0x140044e52  jmp     short loc_140044E75
0x140044e54  xor     r8d, r8d; uIdSubclass
0x140044e57  lea     rdx, ?ButtonWndProc@SplashWindow@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x140044e5e  call    cs:__imp_RemoveWindowSubclass
0x140044e64  mov     r9, r15; lParam
0x140044e67  mov     r8, r14; wParam
0x140044e6a  mov     edx, edi; uMsg
0x140044e6c  mov     rcx, rsi; hWnd
0x140044e6f  call    cs:__imp_DefSubclassProc
0x140044e75  mov     rcx, [rbp+47h+var_40]
0x140044e79  xor     rcx, rsp; StackCookie
0x140044e7c  call    __security_check_cookie
0x140044e81  add     rsp, 0A8h
0x140044e88  pop     r15
0x140044e8a  pop     r14
0x140044e8c  pop     rdi
0x140044e8d  pop     rsi
0x140044e8e  pop     rbx
0x140044e8f  pop     rbp
0x140044e90  retn
```
