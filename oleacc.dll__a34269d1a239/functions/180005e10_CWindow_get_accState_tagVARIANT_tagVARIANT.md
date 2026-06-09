# CWindow::get_accState(tagVARIANT,tagVARIANT *)

- ea: `0x180005e10`
- end: `0x180006125`
- name: `?get_accState@CWindow@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CWindow *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002ebf0`

## callees

- `0x180005e10`
- `0x18000612c`
- `0x18000630c`
- `0x180008870`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180005f4b`
- `USER32!SetRectEmpty` at `0x180005f4b`
- `USER32!GetParent` at `0x180006084`
- `USER32!GetParent` at `0x180006084`
- `USER32!IsWindow` at `0x180005e8e`
- `USER32!IsWindow` at `0x180006050`
- `USER32!IsWindow` at `0x180005e8e`
- `USER32!IsWindow` at `0x180006050`
- `USER32!GetDesktopWindow` at `0x180005f73`
- `USER32!GetDesktopWindow` at `0x18000605e`
- `USER32!GetDesktopWindow` at `0x180005f73`
- `USER32!GetDesktopWindow` at `0x18000605e`
- `USER32!GetWindowLongW` at `0x180006018`
- `USER32!GetWindowLongW` at `0x180006029`
- `USER32!GetWindowLongW` at `0x180006075`
- `USER32!GetWindowLongW` at `0x180006018`
- `USER32!GetWindowLongW` at `0x180006029`
- `USER32!GetWindowLongW` at `0x180006075`
- `USER32!MapWindowPoints` at `0x180005f6d`
- `USER32!MapWindowPoints` at `0x18000600a`
- `USER32!MapWindowPoints` at `0x180005f6d`
- `USER32!MapWindowPoints` at `0x18000600a`
- `USER32!GetWindowRect` at `0x180005fe8`
- `USER32!GetWindowRect` at `0x180005fe8`
- `USER32!GetWindow` at `0x180006094`
- `USER32!GetWindow` at `0x180006094`
- `USER32!GetClientRect` at `0x180005f58`
- `USER32!GetClientRect` at `0x180005ff5`
- `USER32!GetClientRect` at `0x180005f58`
- `USER32!GetClientRect` at `0x180005ff5`

## pseudocode

```c
__int64 __fastcall CWindow::get_accState(struct HWND__ **this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  LONG lVal; // r9d
  struct HWND__ *v7; // rbx
  HWND v8; // rcx
  DWORD dwStyle; // ecx
  LONG v10; // eax
  HWND v11; // rbx
  struct HWND__ *v12; // rbx
  HWND Ancestor; // rax
  HWND v14; // rbx
  DWORD v15; // edx
  __int64 result; // rax
  unsigned int v17; // edx
  unsigned int v18; // ecx
  HWND v19; // r8
  __int64 v20; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 (__fastcall *v22)(__int64, __int128 *, struct tagVARIANT *); // rax
  unsigned int v23; // ebx
  __int128 v24; // [rsp+30h] [rbp-49h] BYREF
  IRecordInfo *v25; // [rsp+40h] [rbp-39h]
  struct tagRECT rc; // [rsp+50h] [rbp-29h] BYREF
  struct tagWINDOWINFO Rect; // [rsp+60h] [rbp-19h] BYREF

  a3->vt = 0;
  if ( !(*((unsigned int (__fastcall **)(struct HWND__ **))*this + 30))(this) )
    return 2147942487LL;
  lVal = a2->lVal;
  a3->vt = 3;
  a3->lVal = 0;
  v7 = this[10];
  if ( !lVal )
  {
    v8 = this[10];
    memset(&Rect, 0, sizeof(Rect));
    rc = 0;
    if ( IsWindow(v8) )
    {
      if ( lpfnWindowInfo )
      {
        Rect.cbSize = 60;
        if ( !lpfnWindowInfo(v7, &Rect) )
          goto LABEL_24;
      }
      else
      {
        GetWindowRect(v7, &Rect.rcWindow);
        GetClientRect(v7, &Rect.rcClient);
        MapWindowPoints(v7, 0, (LPPOINT)&Rect.rcClient, 2u);
        Rect.dwStyle = GetWindowLongW(v7, -16);
        Rect.dwExStyle = GetWindowLongW(v7, -20);
        *(_QWORD *)&Rect.dwWindowStatus = 0;
        *(_QWORD *)&Rect.cyWindowBorders = 0;
      }
      dwStyle = Rect.dwStyle;
      if ( (Rect.dwStyle & 0x10000000) == 0 )
        a3->lVal |= 0x8000u;
      v10 = a3->lVal;
      if ( (dwStyle & 0x8000000) != 0 )
      {
        v10 |= 1u;
        a3->lVal = v10;
      }
      if ( (dwStyle & 0x40000) != 0 )
      {
        v10 |= 0x20000u;
        a3->lVal = v10;
      }
      if ( (dwStyle & 0xC00000) == 0xC00000 )
        a3->lVal = v10 | 0x140000;
      v11 = this[10];
      if ( MyGetFocus() == v11 )
        a3->lVal |= 4u;
      a3->lVal |= 0x100000u;
      v12 = this[10];
      if ( lpfnGetAncestor )
      {
        Ancestor = lpfnGetAncestor(v12, 1u);
      }
      else
      {
        if ( !IsWindow(v12) || v12 == GetDesktopWindow() )
          return 0;
        if ( (GetWindowLongW(v12, -16) & 0x40000000) != 0 )
          Ancestor = GetParent(v12);
        else
          Ancestor = GetWindow(v12, 4u);
      }
      v14 = Ancestor;
      if ( !Ancestor )
        return 0;
      SetRectEmpty(&rc);
      GetClientRect(v14, &rc);
      MapWindowPoints(v14, 0, (LPPOINT)&rc, 2u);
      if ( v14 != GetDesktopWindow() )
      {
        if ( Rect.rcWindow.right <= rc.left
          || Rect.rcWindow.bottom <= rc.top
          || Rect.rcWindow.left >= rc.right
          || Rect.rcWindow.top >= rc.bottom )
        {
          a3->lVal |= 0x18000u;
        }
        return 0;
      }
      if ( xMonitorFromRect(&Rect.rcWindow, v15) )
        return 0;
    }
LABEL_24:
    a3->lVal |= 0x8000u;
    return 0;
  }
  v17 = *((_DWORD *)this + 17);
  v18 = *((_DWORD *)this + 25);
  v19 = this[10];
  *(_QWORD *)&rc.left = 0;
  result = AccessibleObjectFromWindowTimeout(v18, v17, v19, lVal, &IID_IAccessible, (void **)&rc);
  if ( (int)result >= 0 )
  {
    v20 = *(_QWORD *)&rc.left;
    if ( *(_QWORD *)&rc.left )
    {
      a2->lVal = 0;
      pRecInfo = a2->pRecInfo;
      v22 = *(__int64 (__fastcall **)(__int64, __int128 *, struct tagVARIANT *))(*(_QWORD *)v20 + 112LL);
      v24 = *(_OWORD *)&a2->vt;
      v25 = pRecInfo;
      v23 = v22(v20, &v24, a3);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rc.left + 16LL))(*(_QWORD *)&rc.left);
      return v23;
    }
    goto LABEL_24;
  }
  return result;
}

```

## disassembly

```asm
0x180005e10  push    rbp
0x180005e12  push    rbx
0x180005e13  push    rsi
0x180005e14  push    rdi
0x180005e15  push    r14
0x180005e17  lea     rbp, [rsp-37h]
0x180005e1c  sub     rsp, 0B0h
0x180005e23  mov     rax, cs:__security_cookie
0x180005e2a  xor     rax, rsp
0x180005e2d  mov     [rbp+57h+var_30], rax
0x180005e31  xor     eax, eax
0x180005e33  mov     rdi, r8
0x180005e36  mov     [r8], ax
0x180005e3a  mov     rsi, rdx
0x180005e3d  mov     rax, [rcx]
0x180005e40  mov     r14, rcx
0x180005e43  mov     rax, [rax+0F0h]
0x180005e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4f  test    eax, eax
0x180005e51  jz      loc_180005FB3
0x180005e57  mov     r9d, [rsi+8]
0x180005e5b  mov     word ptr [rdi], 3
0x180005e60  mov     dword ptr [rdi+8], 0
0x180005e67  mov     rbx, [r14+50h]
0x180005e6b  test    r9d, r9d
0x180005e6e  jnz     loc_18000609F
0x180005e74  xorps   xmm0, xmm0
0x180005e77  mov     rcx, rbx; hWnd
0x180005e7a  movups  [rbp+57h+var_50], xmm0
0x180005e7e  movups  [rbp+57h+var_50+0Ch], xmm0
0x180005e82  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180005e86  movups  xmmword ptr [rbp+57h+var_60.left], xmm0
0x180005e8a  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180005e8e  call    cs:__imp_IsWindow
0x180005e94  test    eax, eax
0x180005e96  jz      loc_180005FA9
0x180005e9c  mov     rax, cs:?lpfnWindowInfo@@3P6AHPEAUHWND__@@PEAUtagWINDOWINFO@@@ZEA; int (*lpfnWindowInfo)(HWND__ *,tagWINDOWINFO *)
0x180005ea3  mov     rcx, rbx; hWnd
0x180005ea6  test    rax, rax
0x180005ea9  jz      loc_180005FE4
0x180005eaf  lea     rdx, [rbp+57h+Rect]
0x180005eb3  mov     [rbp+57h+Rect.left], 3Ch ; '<'
0x180005eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ebf  test    eax, eax
0x180005ec1  jz      loc_180005FA9
0x180005ec7  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x180005eca  mov     esi, 8000h
0x180005ecf  bt      ecx, 1Ch
0x180005ed3  jb      short loc_180005ED8
0x180005ed5  or      [rdi+8], esi
0x180005ed8  mov     eax, [rdi+8]
0x180005edb  bt      ecx, 1Bh
0x180005edf  jnb     short loc_180005EE7
0x180005ee1  or      eax, 1
0x180005ee4  mov     [rdi+8], eax
0x180005ee7  bt      ecx, 12h
0x180005eeb  jnb     short loc_180005EF4
0x180005eed  bts     eax, 11h
0x180005ef1  mov     [rdi+8], eax
0x180005ef4  mov     edx, 0C00000h
0x180005ef9  and     ecx, edx
0x180005efb  cmp     ecx, edx
0x180005efd  jnz     short loc_180005F07
0x180005eff  or      eax, 140000h
0x180005f04  mov     [rdi+8], eax
0x180005f07  mov     rbx, [r14+50h]
0x180005f0b  call    ?MyGetFocus@@YAPEAUHWND__@@XZ; MyGetFocus(void)
0x180005f10  cmp     rax, rbx
0x180005f13  jz      loc_180006047
0x180005f19  bts     dword ptr [rdi+8], 14h
0x180005f1e  mov     rax, cs:?lpfnGetAncestor@@3P6APEAUHWND__@@PEAU1@I@ZEA; HWND__ * (*lpfnGetAncestor)(HWND__ *,uint)
0x180005f25  mov     rbx, [r14+50h]
0x180005f29  mov     rcx, rbx; hWnd
0x180005f2c  test    rax, rax
0x180005f2f  jz      loc_180006050
0x180005f35  mov     edx, 1
0x180005f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3f  mov     rbx, rax
0x180005f42  test    rax, rax
0x180005f45  jz      short loc_180005F8D
0x180005f47  lea     rcx, [rbp+57h+rc]; lprc
0x180005f4b  call    cs:__imp_SetRectEmpty
0x180005f51  lea     rdx, [rbp+57h+rc]; lpRect
0x180005f55  mov     rcx, rbx; hWnd
0x180005f58  call    cs:__imp_GetClientRect
0x180005f5e  mov     r9d, 2; cPoints
0x180005f64  lea     r8, [rbp+57h+rc]; lpPoints
0x180005f68  xor     edx, edx; hWndTo
0x180005f6a  mov     rcx, rbx; hWndFrom
0x180005f6d  call    cs:__imp_MapWindowPoints
0x180005f73  call    cs:__imp_GetDesktopWindow
0x180005f79  cmp     rbx, rax
0x180005f7c  jz      short loc_180005FBA
0x180005f7e  mov     eax, [rbp+57h+rc.left]
0x180005f81  cmp     [rbp+57h+Rect.bottom], eax
0x180005f84  jg      short loc_180005FCA
0x180005f86  or      dword ptr [rdi+8], 18000h
0x180005f8d  xor     eax, eax
0x180005f8f  mov     rcx, [rbp+57h+var_30]
0x180005f93  xor     rcx, rsp; StackCookie
0x180005f96  call    __security_check_cookie
0x180005f9b  add     rsp, 0B0h
0x180005fa2  pop     r14
0x180005fa4  pop     rdi
0x180005fa5  pop     rsi
0x180005fa6  pop     rbx
0x180005fa7  pop     rbp
0x180005fa8  retn
0x180005fa9  mov     esi, 8000h
0x180005fae  or      [rdi+8], esi
0x180005fb1  jmp     short loc_180005F8D
0x180005fb3  mov     eax, 80070057h
0x180005fb8  jmp     short loc_180005F8F
0x180005fba  lea     rcx, [rbp+57h+Rect.top]; LPCRECT
0x180005fbe  call    xMonitorFromRect
0x180005fc3  test    rax, rax
0x180005fc6  jnz     short loc_180005F8D
0x180005fc8  jmp     short loc_180005FAE
0x180005fca  mov     eax, [rbp+57h+rc.top]
0x180005fcd  cmp     [rbp+57h+var_60.left], eax
0x180005fd0  jle     short loc_180005F86
0x180005fd2  mov     eax, [rbp+57h+rc.right]
0x180005fd5  cmp     [rbp+57h+Rect.top], eax
0x180005fd8  jge     short loc_180005F86
0x180005fda  mov     eax, [rbp+57h+rc.bottom]
0x180005fdd  cmp     [rbp+57h+Rect.right], eax
0x180005fe0  jge     short loc_180005F86
0x180005fe2  jmp     short loc_180005F8D
0x180005fe4  lea     rdx, [rbp+57h+Rect.top]; lpRect
0x180005fe8  call    cs:__imp_GetWindowRect
0x180005fee  lea     rdx, [rbp+57h+var_60.top]; lpRect
0x180005ff2  mov     rcx, rbx; hWnd
0x180005ff5  call    cs:__imp_GetClientRect
0x180005ffb  mov     r9d, 2; cPoints
0x180006001  lea     r8, [rbp+57h+var_60.top]; lpPoints
0x180006005  xor     edx, edx; hWndTo
0x180006007  mov     rcx, rbx; hWndFrom
0x18000600a  call    cs:__imp_MapWindowPoints
0x180006010  mov     edx, 0FFFFFFF0h; nIndex
0x180006015  mov     rcx, rbx; hWnd
0x180006018  call    cs:__imp_GetWindowLongW
0x18000601e  mov     edx, 0FFFFFFECh; nIndex
0x180006023  mov     rcx, rbx; hWnd
0x180006026  mov     dword ptr [rbp+57h+var_50+4], eax
0x180006029  call    cs:__imp_GetWindowLongW
0x18000602f  mov     dword ptr [rbp+57h+var_50+8], eax
0x180006032  mov     qword ptr [rbp+57h+var_50+0Ch], 0
0x18000603a  mov     [rbp+57h+var_3C], 0
0x180006042  jmp     loc_180005EC7
0x180006047  or      dword ptr [rdi+8], 4
0x18000604b  jmp     loc_180005F19
0x180006050  call    cs:__imp_IsWindow
0x180006056  test    eax, eax
0x180006058  jz      loc_180005F8D
0x18000605e  call    cs:__imp_GetDesktopWindow
0x180006064  cmp     rbx, rax
0x180006067  jz      loc_180005F8D
0x18000606d  mov     edx, 0FFFFFFF0h; nIndex
0x180006072  mov     rcx, rbx; hWnd
0x180006075  call    cs:__imp_GetWindowLongW
0x18000607b  mov     rcx, rbx; hWnd
0x18000607e  bt      eax, 1Eh
0x180006082  jnb     short loc_18000608F
0x180006084  call    cs:__imp_GetParent
0x18000608a  jmp     loc_180005F3F
0x18000608f  mov     edx, 4; uCmd
0x180006094  call    cs:__imp_GetWindow
0x18000609a  jmp     loc_180005F3F
0x18000609f  mov     edx, [r14+44h]
0x1800060a3  lea     rax, [rbp+57h+rc]
0x1800060a7  mov     ecx, [r14+64h]
0x1800060ab  mov     r8, rbx
0x1800060ae  mov     [rsp+0D0h+var_A8], rax
0x1800060b3  lea     rax, IID_IAccessible
0x1800060ba  mov     [rsp+0D0h+var_B0], rax
0x1800060bf  mov     qword ptr [rbp+57h+rc.left], 0
0x1800060c7  call    AccessibleObjectFromWindowTimeout
0x1800060cc  test    eax, eax
0x1800060ce  js      loc_180005F8F
0x1800060d4  mov     rcx, qword ptr [rbp+57h+rc.left]
0x1800060d8  test    rcx, rcx
0x1800060db  jz      loc_180005FA9
0x1800060e1  mov     dword ptr [rsi+8], 0
0x1800060e8  lea     rdx, [rbp+57h+var_A0]
0x1800060ec  mov     rax, [rcx]
0x1800060ef  mov     r8, rdi
0x1800060f2  movups  xmm0, xmmword ptr [rsi]
0x1800060f5  movsd   xmm1, qword ptr [rsi+10h]
0x1800060fa  mov     rax, [rax+70h]
0x1800060fe  movaps  [rbp+57h+var_A0], xmm0
0x180006102  movsd   [rbp+57h+var_90], xmm1
0x180006107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610c  mov     rcx, qword ptr [rbp+57h+rc.left]
0x180006110  mov     ebx, eax
0x180006112  mov     rdx, [rcx]
0x180006115  mov     rax, [rdx+10h]
0x180006119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611e  mov     eax, ebx
0x180006120  jmp     loc_180005F8F
```
