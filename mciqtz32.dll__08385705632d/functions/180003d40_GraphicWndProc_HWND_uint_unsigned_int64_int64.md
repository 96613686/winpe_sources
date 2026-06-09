# GraphicWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180003d40`
- end: `0x180004156`
- name: `?GraphicWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1046`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001460`
- `0x180001d22`
- `0x180003408`
- `0x180003c8c`
- `0x180003d40`
- `0x180004f9c`
- `0x180007010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180004128`
- `KERNEL32!SetEvent` at `0x180004128`
- `USER32!SetWindowLongPtrW` at `0x180003f7c`
- `USER32!SetWindowLongPtrW` at `0x180003f7c`
- `USER32!BeginPaint` at `0x180003def`
- `USER32!BeginPaint` at `0x180003def`
- `USER32!IsIconic` at `0x180003dda`
- `USER32!IsIconic` at `0x180003dda`
- `USER32!GetClientRect` at `0x180003e56`
- `USER32!GetClientRect` at `0x180003f0c`
- `USER32!GetClientRect` at `0x180003e56`
- `USER32!GetClientRect` at `0x180003f0c`
- `USER32!DefWindowProcW` at `0x180003fad`
- `USER32!DefWindowProcW` at `0x18000409b`
- `USER32!DefWindowProcW` at `0x180003fad`
- `USER32!DefWindowProcW` at `0x18000409b`
- `USER32!DestroyWindow` at `0x180003ffe`
- `USER32!DestroyWindow` at `0x180003ffe`
- `USER32!EndPaint` at `0x180003ee5`
- `USER32!EndPaint` at `0x180003ee5`
- `USER32!GetSystemMetrics` at `0x180004145`
- `USER32!GetSystemMetrics` at `0x180004145`
- `USER32!GetWindowLongPtrW` at `0x180003d72`
- `USER32!GetWindowLongPtrW` at `0x180003d72`
- `USER32!ShowWindow` at `0x180003fcb`
- `USER32!ShowWindow` at `0x180003fcb`
- `GDI32!DeleteObject` at `0x180003ed8`
- `GDI32!DeleteObject` at `0x180003ed8`
- `GDI32!SelectPalette` at `0x180003e3d`
- `GDI32!SelectPalette` at `0x180003ecf`
- `GDI32!SelectPalette` at `0x180003e3d`
- `GDI32!SelectPalette` at `0x180003ecf`
- `GDI32!StretchDIBits` at `0x180003eb8`
- `GDI32!StretchDIBits` at `0x180003eb8`
- `GDI32!RealizePalette` at `0x180003e49`
- `GDI32!RealizePalette` at `0x180003e49`
- `GDI32!SetStretchBltMode` at `0x180003e1d`
- `GDI32!SetStretchBltMode` at `0x180003e1d`

## pseudocode

```c
__int64 __fastcall GraphicWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  unsigned int v9; // edx
  LONG_PTR v10; // rbx
  HDC v11; // rax
  HDC v12; // rdi
  BITMAPINFO *lpbmi; // r13
  HPALETTE v14; // r15
  HPALETTE PaletteFromDIB; // rax
  HPALETTE v16; // r14
  HWND v17; // rcx
  __int64 result; // rax
  __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // rcx
  unsigned int v22; // edx
  int v23; // [rsp+70h] [rbp-69h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp-61h] BYREF
  struct tagRECT v25; // [rsp+88h] [rbp-51h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+A0h] [rbp-39h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(hWnd, 0);
  v10 = WindowLongPtrW;
  if ( Msg > 0x1B )
  {
    if ( Msg != 28 )
    {
      if ( Msg == 36 )
      {
        *(_DWORD *)(lParam + 24) = 2 * GetSystemMetrics(30);
        return DefWindowProcW(hWnd, Msg, wParam, lParam);
      }
      if ( Msg != 126 )
      {
        switch ( Msg )
        {
          case 0x101u:
            if ( wParam != 27 )
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            break;
          case 0x112u:
            goto LABEL_23;
          case 0x202u:
            break;
          default:
            if ( Msg != 783 && Msg - 784 > 1 )
              return DefWindowProcW(hWnd, Msg, wParam, lParam);
            goto LABEL_44;
        }
        v20 = *(_DWORD *)(WindowLongPtrW + 288) == 526;
        v23 = 0;
        if ( v20 )
        {
          v21 = *(_QWORD *)(WindowLongPtrW + 176);
          if ( v21 )
          {
            if ( !(*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 280LL))(v21, &v23) && v23 == -1 )
            {
              DeviceStop((struct _MCIGRAPHIC *)v10, v22);
              (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v10 + 176) + 288LL))(*(_QWORD *)(v10 + 176), 0);
              SetEvent(*(HANDLE *)(v10 + 264));
              GraphicDelayedNotify(v10, 1);
            }
          }
        }
        return DefWindowProcW(hWnd, Msg, wParam, lParam);
      }
    }
LABEL_44:
    if ( WindowLongPtrW )
    {
      v19 = *(_QWORD *)(WindowLongPtrW + 176);
      if ( v19 )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, WPARAM, LPARAM))(*(_QWORD *)v19 + 304LL))(
          v19,
          *(_QWORD *)(WindowLongPtrW + 296),
          Msg,
          wParam,
          lParam);
    }
    return DefWindowProcW(hWnd, Msg, wParam, lParam);
  }
  if ( Msg == 27 )
    goto LABEL_44;
  if ( Msg <= 0x10 )
  {
    if ( Msg == 16 )
    {
      DeviceStop((struct _MCIGRAPHIC *)WindowLongPtrW, v9);
      ShowWindow(hWnd, 0);
      return 0;
    }
    if ( Msg != 1 )
    {
      if ( Msg == 2 )
      {
        DeviceStop((struct _MCIGRAPHIC *)WindowLongPtrW, v9);
        if ( *(_QWORD *)(v10 + 296) == *(_QWORD *)(v10 + 48) )
          *(_QWORD *)(v10 + 296) = 0;
        *(_QWORD *)(v10 + 48) = 0;
        return DefWindowProcW(hWnd, Msg, wParam, lParam);
      }
      if ( Msg != 3 )
      {
        if ( Msg == 5 )
        {
          v17 = *(HWND *)(WindowLongPtrW + 296);
          v25 = 0;
          if ( *(HWND *)(WindowLongPtrW + 48) == v17 )
          {
            GetClientRect(v17, &v25);
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int))(**(_QWORD **)(v10 + 176) + 312LL))(
              *(_QWORD *)(v10 + 176),
              0,
              0,
              (unsigned int)(v25.right - v25.left),
              v25.bottom - v25.top);
          }
        }
        else if ( Msg == 15 )
        {
          memset_0(&Paint, 0, sizeof(Paint));
          if ( !IsIconic(hWnd) )
          {
            v11 = BeginPaint(hWnd, &Paint);
            v12 = v11;
            if ( *(_DWORD *)(v10 + 592) )
            {
              lpbmi = *(BITMAPINFO **)(v10 + 600);
              v14 = 0;
              Rect = 0;
              SetStretchBltMode(v11, 3);
              PaletteFromDIB = GetPaletteFromDIB(&lpbmi->bmiHeader);
              v16 = PaletteFromDIB;
              if ( PaletteFromDIB )
              {
                v14 = SelectPalette(v12, PaletteFromDIB, 1);
                RealizePalette(v12);
              }
              GetClientRect(hWnd, &Rect);
              StretchDIBits(
                v12,
                Rect.left,
                Rect.top,
                Rect.right - Rect.left,
                Rect.bottom - Rect.top,
                0,
                0,
                lpbmi->bmiHeader.biWidth,
                lpbmi->bmiHeader.biHeight,
                *(const void **)(v10 + 608),
                lpbmi,
                0,
                0xCC0020u);
              if ( v16 )
              {
                SelectPalette(v12, v14, 1);
                DeleteObject(v16);
              }
            }
            EndPaint(hWnd, &Paint);
            return 0;
          }
        }
        return DefWindowProcW(hWnd, Msg, wParam, lParam);
      }
      goto LABEL_44;
    }
    SetWindowLongPtrW(hWnd, 0, **(_QWORD **)lParam);
LABEL_23:
    if ( (wParam & 0xFFF0) == 0xF090 || (wParam & 0xFFF0) == 0xF100 )
    {
      ++gfEvil;
      result = DefWindowProcW(hWnd, Msg, wParam, lParam);
      --gfEvil;
      return result;
    }
    return DefWindowProcW(hWnd, Msg, wParam, lParam);
  }
  if ( Msg != 17 )
  {
    if ( Msg == 20 )
      return 1;
    if ( Msg != 21 )
    {
      if ( Msg == 22 && wParam )
        DestroyWindow(hWnd);
      return DefWindowProcW(hWnd, Msg, wParam, lParam);
    }
    goto LABEL_44;
  }
  DeviceStop((struct _MCIGRAPHIC *)WindowLongPtrW, v9);
  return DefWindowProcW(hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x180003d40  push    rbp
0x180003d42  push    rbx
0x180003d43  push    rsi
0x180003d44  push    rdi
0x180003d45  push    r13
0x180003d47  push    r14
0x180003d49  push    r15
0x180003d4b  lea     rbp, [rsp-27h]
0x180003d50  sub     rsp, 100h
0x180003d57  mov     rax, cs:__security_cookie
0x180003d5e  xor     rax, rsp
0x180003d61  mov     [rbp+57h+var_40], rax
0x180003d65  mov     edi, edx
0x180003d67  mov     r15, r9
0x180003d6a  xor     edx, edx; nIndex
0x180003d6c  mov     r14, r8
0x180003d6f  mov     rsi, rcx
0x180003d72  call    cs:__imp_GetWindowLongPtrW
0x180003d78  mov     rbx, rax
0x180003d7b  cmp     edi, 1Bh
0x180003d7e  ja      loc_18000401D
0x180003d84  jz      loc_18000405E
0x180003d8a  cmp     edi, 10h
0x180003d8d  ja      loc_180003FD8
0x180003d93  jz      loc_180003FBE
0x180003d99  mov     eax, edi
0x180003d9b  sub     eax, 1
0x180003d9e  jz      loc_180003F71
0x180003da4  sub     eax, 1
0x180003da7  jz      loc_180003F44
0x180003dad  sub     eax, 1
0x180003db0  jz      loc_18000405E
0x180003db6  sub     eax, 2
0x180003db9  jz      loc_180003EF0
0x180003dbf  cmp     eax, 0Ah
0x180003dc2  jnz     loc_180004090
0x180003dc8  xor     edx, edx; Val
0x180003dca  lea     r8d, [rax+3Eh]; Size
0x180003dce  lea     rcx, [rbp+57h+Paint]; void *
0x180003dd2  call    memset_0
0x180003dd7  mov     rcx, rsi; hWnd
0x180003dda  call    cs:__imp_IsIconic
0x180003de0  test    eax, eax
0x180003de2  jnz     loc_180004090
0x180003de8  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180003dec  mov     rcx, rsi; hWnd
0x180003def  call    cs:__imp_BeginPaint
0x180003df5  cmp     dword ptr [rbx+250h], 0
0x180003dfc  mov     rdi, rax
0x180003dff  jz      loc_180003EDE
0x180003e05  mov     r13, [rbx+258h]
0x180003e0c  xorps   xmm0, xmm0
0x180003e0f  xor     r15d, r15d
0x180003e12  mov     rcx, rax; hdc
0x180003e15  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180003e19  lea     edx, [r15+3]; mode
0x180003e1d  call    cs:__imp_SetStretchBltMode
0x180003e23  mov     rcx, r13; struct tagBITMAPINFOHEADER *
0x180003e26  call    ?GetPaletteFromDIB@@YAPEAUHPALETTE__@@PEAUtagBITMAPINFOHEADER@@@Z; GetPaletteFromDIB(tagBITMAPINFOHEADER *)
0x180003e2b  mov     r14, rax
0x180003e2e  test    rax, rax
0x180003e31  jz      short loc_180003E4F
0x180003e33  lea     r8d, [r15+1]; bForceBkgd
0x180003e37  mov     rdx, rax; hPal
0x180003e3a  mov     rcx, rdi; hdc
0x180003e3d  call    cs:__imp_SelectPalette
0x180003e43  mov     rcx, rdi; hdc
0x180003e46  mov     r15, rax
0x180003e49  call    cs:__imp_RealizePalette
0x180003e4f  lea     rdx, [rbp+57h+Rect]; lpRect
0x180003e53  mov     rcx, rsi; hWnd
0x180003e56  call    cs:__imp_GetClientRect
0x180003e5c  mov     rax, [rbx+260h]
0x180003e63  mov     ecx, [rbp+57h+Rect.bottom]
0x180003e66  mov     r8d, [rbp+57h+Rect.top]; yDest
0x180003e6a  sub     ecx, r8d
0x180003e6d  mov     r9d, [rbp+57h+Rect.right]
0x180003e71  mov     edx, [rbp+57h+Rect.left]; xDest
0x180003e74  sub     r9d, edx; DestWidth
0x180003e77  mov     [rsp+130h+rop], 0CC0020h; rop
0x180003e7f  mov     [rsp+130h+iUsage], 0; iUsage
0x180003e87  mov     [rsp+130h+lpbmi], r13; lpbmi
0x180003e8c  mov     [rsp+130h+lpBits], rax; lpBits
0x180003e91  mov     eax, [r13+8]
0x180003e95  mov     [rsp+130h+SrcHeight], eax; SrcHeight
0x180003e99  mov     eax, [r13+4]
0x180003e9d  mov     [rsp+130h+SrcWidth], eax; SrcWidth
0x180003ea1  mov     [rsp+130h+ySrc], 0; ySrc
0x180003ea9  mov     [rsp+130h+xSrc], 0; xSrc
0x180003eb1  mov     [rsp+130h+DestHeight], ecx; DestHeight
0x180003eb5  mov     rcx, rdi; hdc
0x180003eb8  call    cs:__imp_StretchDIBits
0x180003ebe  test    r14, r14
0x180003ec1  jz      short loc_180003EDE
0x180003ec3  mov     r8d, 1; bForceBkgd
0x180003ec9  mov     rdx, r15; hPal
0x180003ecc  mov     rcx, rdi; hdc
0x180003ecf  call    cs:__imp_SelectPalette
0x180003ed5  mov     rcx, r14; ho
0x180003ed8  call    cs:__imp_DeleteObject
0x180003ede  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180003ee2  mov     rcx, rsi; hWnd
0x180003ee5  call    cs:__imp_EndPaint
0x180003eeb  jmp     loc_180003FD1
0x180003ef0  mov     rcx, [rbx+128h]; hWnd
0x180003ef7  xorps   xmm0, xmm0
0x180003efa  movups  xmmword ptr [rbp+57h+var_A8.left], xmm0
0x180003efe  cmp     [rbx+30h], rcx
0x180003f02  jnz     loc_180004090
0x180003f08  lea     rdx, [rbp+57h+var_A8]; lpRect
0x180003f0c  call    cs:__imp_GetClientRect
0x180003f12  mov     rcx, [rbx+0B0h]
0x180003f19  xor     r8d, r8d
0x180003f1c  mov     edx, [rbp+57h+var_A8.bottom]
0x180003f1f  sub     edx, [rbp+57h+var_A8.top]
0x180003f22  mov     r9d, [rbp+57h+var_A8.right]
0x180003f26  mov     rax, [rcx]
0x180003f29  sub     r9d, [rbp+57h+var_A8.left]
0x180003f2d  mov     [rsp+130h+DestHeight], edx
0x180003f31  xor     edx, edx
0x180003f33  mov     rax, [rax+138h]
0x180003f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f3f  jmp     loc_180004090
0x180003f44  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180003f47  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x180003f4c  mov     rax, [rbx+30h]
0x180003f50  cmp     [rbx+128h], rax
0x180003f57  jnz     short loc_180003F64
0x180003f59  mov     qword ptr [rbx+128h], 0
0x180003f64  mov     qword ptr [rbx+30h], 0
0x180003f6c  jmp     loc_180004090
0x180003f71  mov     r8, [r15]
0x180003f74  xor     edx, edx; nIndex
0x180003f76  mov     rcx, rsi; hWnd
0x180003f79  mov     r8, [r8]; dwNewLong
0x180003f7c  call    cs:__imp_SetWindowLongPtrW
0x180003f82  mov     rax, r14
0x180003f85  and     eax, 0FFF0h
0x180003f8a  sub     rax, 0F090h
0x180003f90  jz      short loc_180003F9C
0x180003f92  cmp     rax, 70h ; 'p'
0x180003f96  jnz     loc_180004090
0x180003f9c  inc     cs:?gfEvil@@3HA; int gfEvil
0x180003fa2  mov     r9, r15; lParam
0x180003fa5  mov     r8, r14; wParam
0x180003fa8  mov     edx, edi; Msg
0x180003faa  mov     rcx, rsi; hWnd
0x180003fad  call    cs:__imp_DefWindowProcW
0x180003fb3  dec     cs:?gfEvil@@3HA; int gfEvil
0x180003fb9  jmp     loc_1800040A1
0x180003fbe  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180003fc1  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x180003fc6  xor     edx, edx; nCmdShow
0x180003fc8  mov     rcx, rsi; hWnd
0x180003fcb  call    cs:__imp_ShowWindow
0x180003fd1  xor     eax, eax
0x180003fd3  jmp     loc_1800040A1
0x180003fd8  mov     eax, edi
0x180003fda  sub     eax, 11h
0x180003fdd  jz      short loc_180004013
0x180003fdf  sub     eax, 3
0x180003fe2  jz      short loc_180004009
0x180003fe4  sub     eax, 1
0x180003fe7  jz      short loc_18000405E
0x180003fe9  cmp     eax, 1
0x180003fec  jnz     loc_180004090
0x180003ff2  test    r14, r14
0x180003ff5  jz      loc_180004090
0x180003ffb  mov     rcx, rsi; hWnd
0x180003ffe  call    cs:__imp_DestroyWindow
0x180004004  jmp     loc_180004090
0x180004009  mov     eax, 1
0x18000400e  jmp     loc_1800040A1
0x180004013  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004016  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x18000401b  jmp     short loc_180004090
0x18000401d  mov     eax, edi
0x18000401f  sub     eax, 1Ch
0x180004022  jz      short loc_18000405E
0x180004024  sub     eax, 8
0x180004027  jz      loc_180004140
0x18000402d  sub     eax, 5Ah ; 'Z'
0x180004030  jz      short loc_18000405E
0x180004032  sub     eax, 83h
0x180004037  jz      loc_1800040BF
0x18000403d  sub     eax, 11h
0x180004040  jz      loc_180003F82
0x180004046  sub     eax, 0F0h
0x18000404b  jz      short loc_1800040C5
0x18000404d  sub     eax, 10Dh
0x180004052  jz      short loc_18000405E
0x180004054  sub     eax, 1
0x180004057  jz      short loc_18000405E
0x180004059  cmp     eax, 1
0x18000405c  jnz     short loc_180004090
0x18000405e  test    rbx, rbx
0x180004061  jz      short loc_180004090
0x180004063  mov     rcx, [rbx+0B0h]
0x18000406a  test    rcx, rcx
0x18000406d  jz      short loc_180004090
0x18000406f  mov     rax, [rcx]
0x180004072  mov     r9, r14
0x180004075  mov     rdx, [rbx+128h]
0x18000407c  mov     r8d, edi
0x18000407f  mov     qword ptr [rsp+130h+DestHeight], r15
0x180004084  mov     rax, [rax+130h]
0x18000408b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004090  mov     r9, r15; lParam
0x180004093  mov     r8, r14; wParam
0x180004096  mov     edx, edi; Msg
0x180004098  mov     rcx, rsi; hWnd
0x18000409b  call    cs:__imp_DefWindowProcW
0x1800040a1  mov     rcx, [rbp+57h+var_40]
0x1800040a5  xor     rcx, rsp; StackCookie
0x1800040a8  call    __security_check_cookie
0x1800040ad  add     rsp, 100h
0x1800040b4  pop     r15
0x1800040b6  pop     r14
0x1800040b8  pop     r13
0x1800040ba  pop     rdi
0x1800040bb  pop     rsi
0x1800040bc  pop     rbx
0x1800040bd  pop     rbp
0x1800040be  retn
0x1800040bf  cmp     r14, 1Bh
0x1800040c3  jnz     short loc_180004090
0x1800040c5  cmp     dword ptr [rbx+120h], 20Eh
0x1800040cf  mov     [rbp+57h+var_C0], 0
0x1800040d6  jnz     short loc_180004090
0x1800040d8  mov     rcx, [rbx+0B0h]
0x1800040df  test    rcx, rcx
0x1800040e2  jz      short loc_180004090
0x1800040e4  mov     rax, [rcx]
0x1800040e7  lea     rdx, [rbp+57h+var_C0]
0x1800040eb  mov     rax, [rax+118h]
0x1800040f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f7  test    eax, eax
0x1800040f9  jnz     short loc_180004090
0x1800040fb  cmp     [rbp+57h+var_C0], 0FFFFFFFFh
0x1800040ff  jnz     short loc_180004090
0x180004101  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004104  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x180004109  mov     rcx, [rbx+0B0h]
0x180004110  xor     edx, edx
0x180004112  mov     rax, [rcx]
0x180004115  mov     rax, [rax+120h]
0x18000411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004121  mov     rcx, [rbx+108h]; hEvent
0x180004128  call    cs:__imp_SetEvent
0x18000412e  mov     edx, 1
0x180004133  mov     rcx, rbx
0x180004136  call    GraphicDelayedNotify
0x18000413b  jmp     loc_180004090
0x180004140  mov     ecx, 1Eh; nIndex
0x180004145  call    cs:__imp_GetSystemMetrics
0x18000414b  add     eax, eax
0x18000414d  mov     [r15+18h], eax
0x180004151  jmp     loc_180004090
```
