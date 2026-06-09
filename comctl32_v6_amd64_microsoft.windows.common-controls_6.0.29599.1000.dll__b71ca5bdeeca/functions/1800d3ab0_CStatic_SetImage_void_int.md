# CStatic::SetImage(void *,int)

- ea: `0x1800d3ab0`
- end: `0x1800d3e67`
- name: `?SetImage@CStatic@@AEAAPEAXPEAXH@Z`
- size: `951`
- prototype: `void *(CStatic *__hidden this, void *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180055550`
- `0x1800565f4`

## callees

- `0x180010000`
- `0x18007b714`
- `0x1800b00fc`
- `0x1800d3ab0`
- `0x1800d3e70`
- `0x1800d3f14`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800d3c9c`
- `GDI32!DeleteObject` at `0x1800d3cb4`
- `GDI32!DeleteObject` at `0x1800d3c9c`
- `GDI32!DeleteObject` at `0x1800d3cb4`
- `GDI32!GetObjectW` at `0x1800d3b8d`
- `GDI32!GetObjectW` at `0x1800d3b8d`
- `GDI32!SelectObject` at `0x1800d3c04`
- `GDI32!SelectObject` at `0x1800d3c13`
- `GDI32!SelectObject` at `0x1800d3c59`
- `GDI32!SelectObject` at `0x1800d3c66`
- `GDI32!SelectObject` at `0x1800d3c04`
- `GDI32!SelectObject` at `0x1800d3c13`
- `GDI32!SelectObject` at `0x1800d3c59`
- `GDI32!SelectObject` at `0x1800d3c66`
- `GDI32!DeleteDC` at `0x1800d3c70`
- `GDI32!DeleteDC` at `0x1800d3cbd`
- `GDI32!DeleteDC` at `0x1800d3c70`
- `GDI32!DeleteDC` at `0x1800d3cbd`
- `GDI32!CreateCompatibleDC` at `0x1800d3bb3`
- `GDI32!CreateCompatibleDC` at `0x1800d3beb`
- `GDI32!CreateCompatibleDC` at `0x1800d3bb3`
- `GDI32!CreateCompatibleDC` at `0x1800d3beb`
- `GDI32!BitBlt` at `0x1800d3c4d`
- `GDI32!BitBlt` at `0x1800d3c4d`
- `USER32!AdjustWindowRectEx` at `0x1800d3d25`
- `USER32!AdjustWindowRectEx` at `0x1800d3d25`
- `USER32!IsWindowVisible` at `0x1800d3d61`
- `USER32!IsWindowVisible` at `0x1800d3d61`
- `USER32!SetWindowPos` at `0x1800d3d58`
- `USER32!SetWindowPos` at `0x1800d3d58`
- `USER32!SetTimer` at `0x1800d3ddb`
- `USER32!SetTimer` at `0x1800d3ddb`
- `USER32!KillTimer` at `0x1800d3b21`
- `USER32!KillTimer` at `0x1800d3b21`
- `USER32!GetClientRect` at `0x1800d3af6`
- `USER32!GetClientRect` at `0x1800d3af6`
- `USER32!UpdateWindow` at `0x1800d3d7d`
- `USER32!UpdateWindow` at `0x1800d3d7d`
- `USER32!InvalidateRect` at `0x1800d3d74`
- `USER32!InvalidateRect` at `0x1800d3d74`
- `USER32!GetCursorFrameInfo` at `0x1800d3dac`
- `USER32!GetCursorFrameInfo` at `0x1800d3e46`
- `USER32!GetCursorFrameInfo` at `0x1800d3dac`
- `USER32!GetCursorFrameInfo` at `0x1800d3e46`

## pseudocode

```c
struct tagPOINT __fastcall CStatic::SetImage(CStatic *this, void *a2, int a3)
{
  HWND v5; // rcx
  UINT v6; // edi
  DWORD v8; // r12d
  struct tagPOINT v9; // r15
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r15
  void *v12; // r12
  HDC v13; // rax
  HGDIOBJ v14; // rdi
  HGDIOBJ v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r8
  HWND v18; // rcx
  LONG right; // ecx
  LONG bottom; // eax
  __int64 v21; // r8
  __int64 v22; // rcx
  HWND v23; // rcx
  UINT v24; // edx
  bool v26; // zf
  bool v27; // sf
  bool v28; // of
  HDC hdc; // [rsp+50h] [rbp-49h] BYREF
  __int128 pv; // [rsp+58h] [rbp-41h] BYREF
  __int128 v31; // [rsp+68h] [rbp-31h]
  struct tagRGBQUAD *v32; // [rsp+78h] [rbp-21h] BYREF
  UINT v33; // [rsp+80h] [rbp-19h] BYREF
  DWORD v34; // [rsp+84h] [rbp-15h] BYREF
  struct tagRECT v35; // [rsp+88h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+98h] [rbp-1h] BYREF
  struct tagPOINT Point[2]; // [rsp+A8h] [rbp+Fh] BYREF

  v5 = *(HWND *)this;
  v6 = 0;
  v33 = 0;
  Rect = 0;
  GetClientRect(v5, &Rect);
  v34 = *(_DWORD *)(*((_QWORD *)this + 6) + 12LL);
  v8 = v34;
  if ( (v34 & 0x1F) == 3 && *((int *)this + 6) > 1 )
    KillTimer(*(HWND *)this, 0xFFFDu);
  v9 = (struct tagPOINT)*((_QWORD *)this + 2);
  Point[0] = v9;
  *(_QWORD *)&v35.left = 0;
  *(_QWORD *)&v35.right = 0;
  if ( a2 )
  {
    switch ( v34 & 0x1F )
    {
      case 3u:
        hdc = 0;
        GetIconSize(a2, &hdc);
        *(_QWORD *)&v35.right = hdc;
        *((_QWORD *)this + 3) = 0;
        v34 = 0;
        v33 = 0;
        if ( GetCursorFrameInfo(a2, 0, 0, &v34, &v33) )
        {
          v28 = __OFSUB__(v33, 1);
          v26 = v33 == 1;
          v27 = (int)(v33 - 1) < 0;
          *((_DWORD *)this + 6) = v33;
          LOBYTE(v6) = !(v27 ^ v28 | v26);
        }
        break;
      case 0xEu:
        *((_DWORD *)this + 8) &= ~4u;
        pv = 0;
        v31 = 0;
        if ( GetObjectW(a2, 32, &pv) )
        {
          *(_QWORD *)&v35.right = *(_QWORD *)((char *)&pv + 4);
          if ( WORD1(v31) == 32 )
          {
            CompatibleDC = CreateCompatibleDC(0);
            hdcSrc = CompatibleDC;
            if ( CompatibleDC )
            {
              v32 = 0;
              v12 = (void *)CreateDIB(CompatibleDC, DWORD1(pv), DWORD2(pv), &v32);
              if ( v12 )
              {
                v13 = CreateCompatibleDC(hdcSrc);
                hdc = v13;
                if ( v13
                  && (v14 = SelectObject(v13, v12),
                      v15 = SelectObject(hdcSrc, a2),
                      BitBlt(hdc, 0, 0, SDWORD1(pv), SDWORD2(pv), hdcSrc, 0, 0, 0xCC0020u),
                      SelectObject(hdcSrc, v15),
                      SelectObject(hdc, v14),
                      DeleteDC(hdc),
                      (unsigned int)DIBSectionUtil::HasAlpha(DWORD1(pv), DWORD2(pv), v32)) )
                {
                  PreProcessDIB(v16, DWORD2(pv), v17, 0);
                  if ( a3 )
                    DeleteObject(a2);
                  *((_DWORD *)this + 8) |= 4u;
                  a2 = v12;
                  a3 = 1;
                }
                else
                {
                  DeleteObject(v12);
                }
              }
              DeleteDC(hdcSrc);
              v6 = v33;
              v8 = v34;
            }
            v9 = Point[0];
          }
        }
        break;
      case 0xFu:
        v35.right = Rect.right - Rect.left;
        v35.bottom = Rect.bottom - Rect.top;
        break;
    }
  }
  *((_QWORD *)this + 2) = a2;
  *((_DWORD *)this + 8) = a3 ^ (*((_DWORD *)this + 8) ^ a3) & 0xFFFFFFFE;
  if ( (v8 & 0x240) == 0 )
  {
    v18 = *(HWND *)this;
    *(_OWORD *)&Point[0].x = 0;
    GetRectInParent(v18, Point);
    right = v35.right;
    bottom = v35.bottom;
    *(_QWORD *)&v35.left = 0;
    if ( v35.right && v35.bottom )
    {
      AdjustWindowRectEx(&v35, v8, 0, *(_DWORD *)(*((_QWORD *)this + 6) + 8LL));
      right = v35.right - v35.left;
      bottom = v35.bottom - v35.top;
      v35.bottom -= v35.top;
      v35.right -= v35.left;
    }
    SetWindowPos(*(HWND *)this, 0, 0, 0, right, bottom, 0x16u);
  }
  if ( IsWindowVisible(*(HWND *)this) )
  {
    InvalidateRect(*(HWND *)this, 0, 1);
    UpdateWindow(*(HWND *)this);
  }
  if ( v6 )
  {
    v21 = *((unsigned int *)this + 7);
    v22 = *((_QWORD *)this + 2);
    v33 = 0;
    v34 = 0;
    GetCursorFrameInfo(v22, 0, v21, &v33, &v34);
    v23 = *(HWND *)this;
    v24 = 100 * v33 / 6;
    if ( v24 < 0xC8 )
      v24 = 200;
    v33 = v24;
    SetTimer(v23, 0xFFFDu, v24, 0);
  }
  return v9;
}

```

## disassembly

```asm
0x1800d3ab0  mov     [rsp-8+arg_10], rbx
0x1800d3ab5  push    rbp
0x1800d3ab6  push    rsi
0x1800d3ab7  push    rdi
0x1800d3ab8  push    r12
0x1800d3aba  push    r13
0x1800d3abc  push    r14
0x1800d3abe  push    r15
0x1800d3ac0  lea     rbp, [rsp-27h]
0x1800d3ac5  sub     rsp, 0C0h
0x1800d3acc  mov     rax, cs:__security_cookie
0x1800d3ad3  xor     rax, rsp
0x1800d3ad6  mov     [rbp+57h+var_38], rax
0x1800d3ada  mov     r14, rdx
0x1800d3add  mov     rsi, rcx
0x1800d3ae0  mov     rcx, [rcx]; hWnd
0x1800d3ae3  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800d3ae7  xorps   xmm0, xmm0
0x1800d3aea  xor     edi, edi
0x1800d3aec  mov     [rbp+57h+var_70], edi
0x1800d3aef  mov     r13d, r8d
0x1800d3af2  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800d3af6  call    cs:__imp_GetClientRect
0x1800d3afc  mov     rax, [rsi+30h]
0x1800d3b00  mov     r12d, [rax+0Ch]
0x1800d3b04  mov     ebx, r12d
0x1800d3b07  and     ebx, 1Fh
0x1800d3b0a  mov     [rbp+57h+var_6C], r12d
0x1800d3b0e  cmp     ebx, 3
0x1800d3b11  jnz     short loc_1800D3B27
0x1800d3b13  cmp     dword ptr [rsi+18h], 1
0x1800d3b17  jle     short loc_1800D3B27
0x1800d3b19  mov     rcx, [rsi]; hWnd
0x1800d3b1c  mov     edx, 0FFFDh; uIDEvent
0x1800d3b21  call    cs:__imp_KillTimer
0x1800d3b27  mov     r15, [rsi+10h]
0x1800d3b2b  xor     eax, eax
0x1800d3b2d  mov     qword ptr [rbp+57h+Point.x], r15
0x1800d3b31  mov     qword ptr [rbp+57h+var_68.left], rax
0x1800d3b35  mov     qword ptr [rbp+57h+var_68.right], rax
0x1800d3b39  test    r14, r14
0x1800d3b3c  jz      loc_1800D3CCE
0x1800d3b42  sub     ebx, 3
0x1800d3b45  jz      loc_1800D3E0B
0x1800d3b4b  sub     ebx, 0Bh
0x1800d3b4e  jz      short loc_1800D3B70
0x1800d3b50  cmp     ebx, 1
0x1800d3b53  jnz     loc_1800D3CCE
0x1800d3b59  mov     eax, [rbp+57h+Rect.right]
0x1800d3b5c  sub     eax, [rbp+57h+Rect.left]
0x1800d3b5f  mov     [rbp+57h+var_68.right], eax
0x1800d3b62  mov     eax, [rbp+57h+Rect.bottom]
0x1800d3b65  sub     eax, [rbp+57h+Rect.top]
0x1800d3b68  mov     [rbp+57h+var_68.bottom], eax
0x1800d3b6b  jmp     loc_1800D3CCE
0x1800d3b70  and     dword ptr [rsi+20h], 0FFFFFFFBh
0x1800d3b74  lea     r8, [rbp+57h+pv]; pv
0x1800d3b78  xorps   xmm0, xmm0
0x1800d3b7b  mov     ebx, 20h ; ' '
0x1800d3b80  mov     edx, ebx; c
0x1800d3b82  mov     rcx, r14; h
0x1800d3b85  movups  [rbp+57h+pv], xmm0
0x1800d3b89  movups  [rbp+57h+var_88], xmm0
0x1800d3b8d  call    cs:__imp_GetObjectW
0x1800d3b93  test    eax, eax
0x1800d3b95  jz      loc_1800D3CCE
0x1800d3b9b  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800d3b9e  mov     [rbp+57h+var_68.right], eax
0x1800d3ba1  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800d3ba4  mov     [rbp+57h+var_68.bottom], eax
0x1800d3ba7  cmp     word ptr [rbp+57h+var_88+2], bx
0x1800d3bab  jnz     loc_1800D3CCE
0x1800d3bb1  xor     ecx, ecx; hdc
0x1800d3bb3  call    cs:__imp_CreateCompatibleDC
0x1800d3bb9  mov     r15, rax
0x1800d3bbc  test    rax, rax
0x1800d3bbf  jz      loc_1800D3CCA
0x1800d3bc5  mov     r8d, dword ptr [rbp+57h+pv+8]
0x1800d3bc9  lea     r9, [rbp+57h+var_78]
0x1800d3bcd  mov     edx, dword ptr [rbp+57h+pv+4]
0x1800d3bd0  mov     rcx, rax
0x1800d3bd3  mov     [rbp+57h+var_78], rdi
0x1800d3bd7  call    CreateDIB
0x1800d3bdc  mov     r12, rax
0x1800d3bdf  test    rax, rax
0x1800d3be2  jz      loc_1800D3CBA
0x1800d3be8  mov     rcx, r15; hdc
0x1800d3beb  call    cs:__imp_CreateCompatibleDC
0x1800d3bf1  mov     [rbp+57h+hdc], rax
0x1800d3bf5  test    rax, rax
0x1800d3bf8  jz      loc_1800D3CB1
0x1800d3bfe  mov     rdx, r12; h
0x1800d3c01  mov     rcx, rax; hdc
0x1800d3c04  call    cs:__imp_SelectObject
0x1800d3c0a  mov     rdx, r14; h
0x1800d3c0d  mov     rcx, r15; hdc
0x1800d3c10  mov     rdi, rax
0x1800d3c13  call    cs:__imp_SelectObject
0x1800d3c19  mov     ecx, dword ptr [rbp+57h+pv+8]
0x1800d3c1c  xor     r8d, r8d; y
0x1800d3c1f  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x1800d3c23  xor     edx, edx; x
0x1800d3c25  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1800d3c2d  mov     rbx, rax
0x1800d3c30  mov     [rsp+0F0h+y1], 0; y1
0x1800d3c38  mov     [rsp+0F0h+x1], 0; x1
0x1800d3c40  mov     [rsp+0F0h+hdcSrc], r15; hdcSrc
0x1800d3c45  mov     [rsp+0F0h+cy], ecx; cy
0x1800d3c49  mov     rcx, [rbp+57h+hdc]; hdc
0x1800d3c4d  call    cs:__imp_BitBlt
0x1800d3c53  mov     rdx, rbx; h
0x1800d3c56  mov     rcx, r15; hdc
0x1800d3c59  call    cs:__imp_SelectObject
0x1800d3c5f  mov     rcx, [rbp+57h+hdc]; hdc
0x1800d3c63  mov     rdx, rdi; h
0x1800d3c66  call    cs:__imp_SelectObject
0x1800d3c6c  mov     rcx, [rbp+57h+hdc]; hdc
0x1800d3c70  call    cs:__imp_DeleteDC
0x1800d3c76  mov     r8, [rbp+57h+var_78]; struct tagRGBQUAD *
0x1800d3c7a  mov     edx, dword ptr [rbp+57h+pv+8]; unsigned int
0x1800d3c7d  mov     ecx, dword ptr [rbp+57h+pv+4]; unsigned int
0x1800d3c80  call    ?HasAlpha@DIBSectionUtil@@SAHIIPEBUtagRGBQUAD@@@Z; DIBSectionUtil::HasAlpha(uint,uint,tagRGBQUAD const *)
0x1800d3c85  test    eax, eax
0x1800d3c87  jz      short loc_1800D3CB1
0x1800d3c89  mov     edx, dword ptr [rbp+57h+pv+8]
0x1800d3c8c  xor     r9d, r9d
0x1800d3c8f  call    PreProcessDIB
0x1800d3c94  test    r13d, r13d
0x1800d3c97  jz      short loc_1800D3CA2
0x1800d3c99  mov     rcx, r14; ho
0x1800d3c9c  call    cs:__imp_DeleteObject
0x1800d3ca2  or      dword ptr [rsi+20h], 4
0x1800d3ca6  mov     r14, r12
0x1800d3ca9  mov     r13d, 1
0x1800d3caf  jmp     short loc_1800D3CBA
0x1800d3cb1  mov     rcx, r12; ho
0x1800d3cb4  call    cs:__imp_DeleteObject
0x1800d3cba  mov     rcx, r15; hdc
0x1800d3cbd  call    cs:__imp_DeleteDC
0x1800d3cc3  mov     edi, [rbp+57h+var_70]
0x1800d3cc6  mov     r12d, [rbp+57h+var_6C]
0x1800d3cca  mov     r15, qword ptr [rbp+57h+Point.x]
0x1800d3cce  mov     eax, r13d
0x1800d3cd1  mov     [rsi+10h], r14
0x1800d3cd5  xor     eax, [rsi+20h]
0x1800d3cd8  and     eax, 0FFFFFFFEh
0x1800d3cdb  xor     eax, r13d
0x1800d3cde  mov     [rsi+20h], eax
0x1800d3ce1  test    r12d, 240h
0x1800d3ce8  jnz     short loc_1800D3D5E
0x1800d3cea  mov     rcx, [rsi]; hWnd
0x1800d3ced  lea     rdx, [rbp+57h+Point]; lpPoint
0x1800d3cf1  xorps   xmm0, xmm0
0x1800d3cf4  movups  xmmword ptr [rbp+57h+Point.x], xmm0
0x1800d3cf8  call    ?GetRectInParent@@YAXPEAUHWND__@@PEAUtagRECT@@@Z; GetRectInParent(HWND__ *,tagRECT *)
0x1800d3cfd  mov     ecx, [rbp+57h+var_68.right]
0x1800d3d00  mov     eax, [rbp+57h+var_68.bottom]
0x1800d3d03  mov     qword ptr [rbp+57h+var_68.left], 0
0x1800d3d0b  test    ecx, ecx
0x1800d3d0d  jz      short loc_1800D3D3D
0x1800d3d0f  test    eax, eax
0x1800d3d11  jz      short loc_1800D3D3D
0x1800d3d13  mov     r9, [rsi+30h]
0x1800d3d17  lea     rcx, [rbp+57h+var_68]; lpRect
0x1800d3d1b  xor     r8d, r8d; bMenu
0x1800d3d1e  mov     edx, r12d; dwStyle
0x1800d3d21  mov     r9d, [r9+8]; dwExStyle
0x1800d3d25  call    cs:__imp_AdjustWindowRectEx
0x1800d3d2b  mov     ecx, [rbp+57h+var_68.right]
0x1800d3d2e  sub     ecx, [rbp+57h+var_68.left]
0x1800d3d31  mov     eax, [rbp+57h+var_68.bottom]
0x1800d3d34  sub     eax, [rbp+57h+var_68.top]
0x1800d3d37  mov     [rbp+57h+var_68.bottom], eax
0x1800d3d3a  mov     [rbp+57h+var_68.right], ecx
0x1800d3d3d  mov     [rsp+0F0h+x1], 16h; uFlags
0x1800d3d45  xor     r9d, r9d; Y
0x1800d3d48  mov     dword ptr [rsp+0F0h+hdcSrc], eax; cy
0x1800d3d4c  xor     r8d, r8d; X
0x1800d3d4f  mov     [rsp+0F0h+cy], ecx; cx
0x1800d3d53  xor     edx, edx; hWndInsertAfter
0x1800d3d55  mov     rcx, [rsi]; hWnd
0x1800d3d58  call    cs:__imp_SetWindowPos
0x1800d3d5e  mov     rcx, [rsi]; hWnd
0x1800d3d61  call    cs:__imp_IsWindowVisible
0x1800d3d67  test    eax, eax
0x1800d3d69  jz      short loc_1800D3D83
0x1800d3d6b  mov     rcx, [rsi]; hWnd
0x1800d3d6e  xor     edx, edx; lpRect
0x1800d3d70  lea     r8d, [rdx+1]; bErase
0x1800d3d74  call    cs:__imp_InvalidateRect
0x1800d3d7a  mov     rcx, [rsi]; hWnd
0x1800d3d7d  call    cs:__imp_UpdateWindow
0x1800d3d83  test    edi, edi
0x1800d3d85  jz      short loc_1800D3DE1
0x1800d3d87  mov     r8d, [rsi+1Ch]
0x1800d3d8b  lea     rax, [rbp+57h+var_6C]
0x1800d3d8f  mov     rcx, [rsi+10h]
0x1800d3d93  lea     r9, [rbp+57h+var_70]
0x1800d3d97  xor     edx, edx
0x1800d3d99  mov     qword ptr [rsp+0F0h+cy], rax
0x1800d3d9e  mov     [rbp+57h+var_70], 0
0x1800d3da5  mov     [rbp+57h+var_6C], 0
0x1800d3dac  call    cs:__imp_GetCursorFrameInfo
0x1800d3db2  imul    ecx, [rbp+57h+var_70], 64h ; 'd'
0x1800d3db6  mov     eax, 0AAAAAAABh
0x1800d3dbb  mul     ecx
0x1800d3dbd  mov     rcx, [rsi]; hWnd
0x1800d3dc0  mov     eax, 0C8h
0x1800d3dc5  shr     edx, 2
0x1800d3dc8  cmp     edx, eax
0x1800d3dca  cmovb   edx, eax
0x1800d3dcd  xor     r9d, r9d; lpTimerFunc
0x1800d3dd0  mov     [rbp+57h+var_70], edx
0x1800d3dd3  mov     r8d, edx; uElapse
0x1800d3dd6  mov     edx, 0FFFDh; nIDEvent
0x1800d3ddb  call    cs:__imp_SetTimer
0x1800d3de1  mov     rax, r15
0x1800d3de4  mov     rcx, [rbp+57h+var_38]
0x1800d3de8  xor     rcx, rsp; StackCookie
0x1800d3deb  call    __security_check_cookie
0x1800d3df0  mov     rbx, [rsp+0F0h+arg_10]
0x1800d3df8  add     rsp, 0C0h
0x1800d3dff  pop     r15
0x1800d3e01  pop     r14
0x1800d3e03  pop     r13
0x1800d3e05  pop     r12
0x1800d3e07  pop     rdi
0x1800d3e08  pop     rsi
0x1800d3e09  pop     rbp
0x1800d3e0a  retn
0x1800d3e0b  lea     rdx, [rbp+57h+hdc]
0x1800d3e0f  mov     [rbp+57h+hdc], rax
0x1800d3e13  mov     rcx, r14
0x1800d3e16  call    GetIconSize
0x1800d3e1b  mov     eax, dword ptr [rbp+57h+hdc]
0x1800d3e1e  lea     r9, [rbp+57h+var_6C]
0x1800d3e22  mov     [rbp+57h+var_68.right], eax
0x1800d3e25  xor     r8d, r8d
0x1800d3e28  mov     eax, dword ptr [rbp+57h+hdc+4]
0x1800d3e2b  xor     edx, edx
0x1800d3e2d  mov     [rbp+57h+var_68.bottom], eax
0x1800d3e30  mov     rcx, r14
0x1800d3e33  lea     rax, [rbp+57h+var_70]
0x1800d3e37  mov     [rsi+18h], rdi
0x1800d3e3b  mov     qword ptr [rsp+0F0h+cy], rax
0x1800d3e40  mov     [rbp+57h+var_6C], edi
0x1800d3e43  mov     [rbp+57h+var_70], edi
0x1800d3e46  call    cs:__imp_GetCursorFrameInfo
0x1800d3e4c  test    rax, rax
0x1800d3e4f  jz      loc_1800D3CCE
0x1800d3e55  mov     eax, [rbp+57h+var_70]
0x1800d3e58  cmp     eax, 1
0x1800d3e5b  mov     [rsi+18h], eax
0x1800d3e5e  setnle  dil
0x1800d3e62  jmp     loc_1800D3CCE
```
