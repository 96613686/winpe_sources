# CSrApiViewerAxHost::OnEraseBkgnd(unsigned __int64)

- ea: `0x1400b0b48`
- end: `0x1400b1114`
- name: `?OnEraseBkgnd@CSrApiViewerAxHost@@AEAAJ_K@Z`
- size: `1484`
- prototype: `int(CSrApiViewerAxHost *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400ae724`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400b0b48`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!ScreenToClient` at `0x1400b0e9e`
- `USER32!ScreenToClient` at `0x1400b0e9e`
- `USER32!GetClientRect` at `0x1400b0c50`
- `USER32!GetClientRect` at `0x1400b0dcd`
- `USER32!GetClientRect` at `0x1400b0c50`
- `USER32!GetClientRect` at `0x1400b0dcd`
- `USER32!OffsetRect` at `0x1400b0ef5`
- `USER32!OffsetRect` at `0x1400b0ef5`
- `USER32!GetWindowRect` at `0x1400b0e4a`
- `USER32!GetWindowRect` at `0x1400b0e4a`
- `KERNEL32!GetLastError` at `0x1400b0c5a`
- `KERNEL32!GetLastError` at `0x1400b0dd7`
- `KERNEL32!GetLastError` at `0x1400b0e54`
- `KERNEL32!GetLastError` at `0x1400b0ea8`
- `KERNEL32!GetLastError` at `0x1400b0c5a`
- `KERNEL32!GetLastError` at `0x1400b0dd7`
- `KERNEL32!GetLastError` at `0x1400b0e54`
- `KERNEL32!GetLastError` at `0x1400b0ea8`
- `GDI32!GetStockObject` at `0x1400b103f`
- `GDI32!GetStockObject` at `0x1400b103f`
- `GDI32!CombineRgn` at `0x1400b0f9e`
- `GDI32!CombineRgn` at `0x1400b0f9e`
- `GDI32!DeleteObject` at `0x1400b10db`
- `GDI32!DeleteObject` at `0x1400b10e9`
- `GDI32!DeleteObject` at `0x1400b10db`
- `GDI32!DeleteObject` at `0x1400b10e9`
- `GDI32!FillRgn` at `0x1400b107e`
- `GDI32!FillRgn` at `0x1400b107e`
- `GDI32!CreateRectRgn` at `0x1400b0ce1`
- `GDI32!CreateRectRgn` at `0x1400b0f47`
- `GDI32!CreateRectRgn` at `0x1400b0ce1`
- `GDI32!CreateRectRgn` at `0x1400b0f47`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::OnEraseBkgnd(CSrApiViewerAxHost *this, HDC a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // ebx
  HWND v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // eax
  HRGN RectRgn; // r15
  unsigned int v10; // eax
  HRGN v11; // r14
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  HWND v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rdx
  HRGN v18; // rax
  int v19; // eax
  unsigned int v20; // eax
  HBRUSH StockObject; // rax
  struct tagPOINT Point; // [rsp+30h] [rbp-50h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-48h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT rc; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT v27; // [rsp+60h] [rbp-20h] BYREF

  hWnd = 0;
  Point = 0;
  Rect = 0;
  rc = 0;
  v27 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    return (unsigned int)-2147418113;
  }
  v6 = (HWND)*((_QWORD *)this + 16);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v7, 0);
    }
    return 0;
  }
  if ( !GetClientRect(v6, &Rect) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v8,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  RectRgn = CreateRectRgn(Rect.left, Rect.top, ++Rect.right, ++Rect.bottom);
  if ( !RectRgn )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v10,
        -2147467259);
    }
    return (unsigned int)-2147467259;
  }
  v11 = 0;
  LastError = (*(__int64 (__fastcall **)(_QWORD, HWND *))(**((_QWORD **)this + 14) + 24LL))(
                *((_QWORD *)this + 14),
                &hWnd);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        143,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v12,
        (__int64)"m_spOleInPlaceActiveObject->GetWindow failed",
        LastError,
        Point,
        hWnd);
    }
    goto LABEL_88;
  }
  if ( !GetClientRect(hWnd, &rc) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 144;
LABEL_39:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v13,
      LastError);
LABEL_40:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_88;
  }
  if ( !GetWindowRect(hWnd, &v27) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 145;
    goto LABEL_39;
  }
  v15 = (HWND)*((_QWORD *)this + 16);
  Point.x = v27.left;
  Point.y = v27.top;
  if ( !ScreenToClient(v15, &Point) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 146;
    goto LABEL_39;
  }
  if ( !OffsetRect(&rc, Point.x, Point.y) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_87;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 147;
    goto LABEL_86;
  }
  v18 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
  v11 = v18;
  if ( !v18 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_87;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 148;
    goto LABEL_86;
  }
  v19 = CombineRgn(RectRgn, RectRgn, v18, 3);
  if ( v19 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v20, 0);
    }
    LastError = 0;
    goto LABEL_88;
  }
  if ( (unsigned int)(v19 - 2) > 1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_87;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 150;
    goto LABEL_86;
  }
  StockObject = (HBRUSH)GetStockObject(4);
  if ( !StockObject )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_87;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 151;
    goto LABEL_86;
  }
  if ( FillRgn(a2, RectRgn, StockObject) )
    goto LABEL_88;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 152;
LABEL_86:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v16,
      -2147467259);
  }
LABEL_87:
  LastError = -2147467259;
LABEL_88:
  DeleteObject(RectRgn);
  if ( v11 )
    DeleteObject(v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400b0b48  mov     [rsp-28h+arg_10], rbx
0x1400b0b4d  push    rbp
0x1400b0b4e  push    rsi
0x1400b0b4f  push    rdi
0x1400b0b50  push    r14
0x1400b0b52  push    r15
0x1400b0b54  mov     rbp, rsp
0x1400b0b57  sub     rsp, 80h
0x1400b0b5e  mov     rax, cs:__security_cookie
0x1400b0b65  xor     rax, rsp
0x1400b0b68  mov     [rbp+var_10], rax
0x1400b0b6c  mov     [rbp+hWnd], 0
0x1400b0b74  xorps   xmm0, xmm0
0x1400b0b77  mov     qword ptr [rbp+Point.x], 0
0x1400b0b7f  xorps   xmm1, xmm1
0x1400b0b82  mov     rsi, rdx
0x1400b0b85  mov     rdi, rcx
0x1400b0b88  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1400b0b8c  movups  xmmword ptr [rbp+rc.left], xmm1
0x1400b0b90  movups  xmmword ptr [rbp+var_20.left], xmm0
0x1400b0b94  test    rdx, rdx
0x1400b0b97  jnz     short loc_1400B0BEE
0x1400b0b99  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0ba0  lea     rax, WPP_GLOBAL_Control
0x1400b0ba7  cmp     rcx, rax
0x1400b0baa  jz      short loc_1400B0BE4
0x1400b0bac  test    byte ptr [rcx+1Ch], 8
0x1400b0bb0  jz      short loc_1400B0BE4
0x1400b0bb2  cmp     byte ptr [rcx+19h], 2
0x1400b0bb6  jb      short loc_1400B0BE4
0x1400b0bb8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0bc4  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0bcb  mov     edx, 8Bh
0x1400b0bd0  mov     dword ptr [rsp+80h+var_60], 8000FFFFh
0x1400b0bd8  mov     r9d, eax
0x1400b0bdb  mov     rcx, [rcx+10h]
0x1400b0bdf  call    WPP_SF_Dd
0x1400b0be4  mov     ebx, 8000FFFFh
0x1400b0be9  jmp     loc_1400B10EF
0x1400b0bee  mov     rcx, [rcx+80h]; hWnd
0x1400b0bf5  test    rcx, rcx
0x1400b0bf8  jnz     short loc_1400B0C4C
0x1400b0bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0c01  lea     rax, WPP_GLOBAL_Control
0x1400b0c08  cmp     rcx, rax
0x1400b0c0b  jz      short loc_1400B0C45
0x1400b0c0d  test    byte ptr [rcx+1Ch], 8
0x1400b0c11  jz      short loc_1400B0C45
0x1400b0c13  cmp     byte ptr [rcx+19h], 2
0x1400b0c17  jb      short loc_1400B0C45
0x1400b0c19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0c25  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0c2c  mov     edx, 8Ch
0x1400b0c31  mov     dword ptr [rsp+80h+var_60], 0
0x1400b0c39  mov     r9d, eax
0x1400b0c3c  mov     rcx, [rcx+10h]
0x1400b0c40  call    WPP_SF_Dd
0x1400b0c45  xor     ebx, ebx
0x1400b0c47  jmp     loc_1400B10EF
0x1400b0c4c  lea     rdx, [rbp+Rect]; lpRect
0x1400b0c50  call    cs:__imp_GetClientRect
0x1400b0c56  test    eax, eax
0x1400b0c58  jnz     short loc_1400B0CC5
0x1400b0c5a  call    cs:__imp_GetLastError
0x1400b0c60  mov     ebx, eax
0x1400b0c62  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0c69  lea     rax, WPP_GLOBAL_Control
0x1400b0c70  cmp     rcx, rax
0x1400b0c73  jz      short loc_1400B0CA9
0x1400b0c75  test    byte ptr [rcx+1Ch], 8
0x1400b0c79  jz      short loc_1400B0CA9
0x1400b0c7b  cmp     byte ptr [rcx+19h], 2
0x1400b0c7f  jb      short loc_1400B0CA9
0x1400b0c81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0c86  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0c8d  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0c94  mov     edx, 8Dh
0x1400b0c99  mov     dword ptr [rsp+80h+var_60], ebx
0x1400b0c9d  mov     r9d, eax
0x1400b0ca0  mov     rcx, [rcx+10h]
0x1400b0ca4  call    WPP_SF_Dd
0x1400b0ca9  test    ebx, ebx
0x1400b0cab  jle     short loc_1400B0CB6
0x1400b0cad  movzx   ebx, bx
0x1400b0cb0  or      ebx, 80070000h
0x1400b0cb6  test    ebx, ebx
0x1400b0cb8  mov     eax, 80004005h
0x1400b0cbd  cmovns  ebx, eax
0x1400b0cc0  jmp     loc_1400B10EF
0x1400b0cc5  mov     r9d, [rbp+Rect.bottom]
0x1400b0cc9  mov     r8d, [rbp+Rect.right]
0x1400b0ccd  inc     r9d; y2
0x1400b0cd0  mov     edx, [rbp+Rect.top]; y1
0x1400b0cd3  inc     r8d; x2
0x1400b0cd6  mov     ecx, [rbp+Rect.left]; x1
0x1400b0cd9  mov     [rbp+Rect.bottom], r9d
0x1400b0cdd  mov     [rbp+Rect.right], r8d
0x1400b0ce1  call    cs:__imp_CreateRectRgn
0x1400b0ce7  mov     r15, rax
0x1400b0cea  test    rax, rax
0x1400b0ced  jnz     short loc_1400B0D44
0x1400b0cef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0cf6  lea     rax, WPP_GLOBAL_Control
0x1400b0cfd  cmp     rcx, rax
0x1400b0d00  jz      short loc_1400B0D3A
0x1400b0d02  test    byte ptr [rcx+1Ch], 8
0x1400b0d06  jz      short loc_1400B0D3A
0x1400b0d08  cmp     byte ptr [rcx+19h], 2
0x1400b0d0c  jb      short loc_1400B0D3A
0x1400b0d0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0d13  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0d1a  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0d21  mov     edx, 8Eh
0x1400b0d26  mov     dword ptr [rsp+80h+var_60], 80004005h
0x1400b0d2e  mov     r9d, eax
0x1400b0d31  mov     rcx, [rcx+10h]
0x1400b0d35  call    WPP_SF_Dd
0x1400b0d3a  mov     ebx, 80004005h
0x1400b0d3f  jmp     loc_1400B10EF
0x1400b0d44  mov     rcx, [rdi+70h]
0x1400b0d48  lea     rdx, [rbp+hWnd]
0x1400b0d4c  xor     r14d, r14d
0x1400b0d4f  mov     rax, [rcx]
0x1400b0d52  mov     rax, [rax+18h]
0x1400b0d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b0d5b  mov     ebx, eax
0x1400b0d5d  test    eax, eax
0x1400b0d5f  jns     short loc_1400B0DC5
0x1400b0d61  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0d68  lea     rax, WPP_GLOBAL_Control
0x1400b0d6f  cmp     rcx, rax
0x1400b0d72  jz      loc_1400B10D8
0x1400b0d78  test    byte ptr [rcx+1Ch], 8
0x1400b0d7c  jz      loc_1400B10D8
0x1400b0d82  cmp     byte ptr [rcx+19h], 2
0x1400b0d86  jb      loc_1400B10D8
0x1400b0d8c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0d91  lea     rcx, aMSpoleinplacea; "m_spOleInPlaceActiveObject->GetWindow f"...
0x1400b0d98  mov     [rsp+80h+var_58], ebx
0x1400b0d9c  mov     [rsp+80h+var_60], rcx
0x1400b0da1  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0da8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0daf  mov     edx, 8Fh
0x1400b0db4  mov     r9d, eax
0x1400b0db7  mov     rcx, [rcx+10h]
0x1400b0dbb  call    WPP_SF_DsD
0x1400b0dc0  jmp     loc_1400B10D8
0x1400b0dc5  mov     rcx, [rbp+hWnd]; hWnd
0x1400b0dc9  lea     rdx, [rbp+rc]; lpRect
0x1400b0dcd  call    cs:__imp_GetClientRect
0x1400b0dd3  test    eax, eax
0x1400b0dd5  jnz     short loc_1400B0E42
0x1400b0dd7  call    cs:__imp_GetLastError
0x1400b0ddd  mov     ebx, eax
0x1400b0ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0de6  lea     rax, WPP_GLOBAL_Control
0x1400b0ded  cmp     rcx, rax
0x1400b0df0  jz      short loc_1400B0E26
0x1400b0df2  test    byte ptr [rcx+1Ch], 8
0x1400b0df6  jz      short loc_1400B0E26
0x1400b0df8  cmp     byte ptr [rcx+19h], 2
0x1400b0dfc  jb      short loc_1400B0E26
0x1400b0dfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0e03  mov     edx, 90h
0x1400b0e08  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0e0f  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0e16  mov     r9d, eax
0x1400b0e19  mov     dword ptr [rsp+80h+var_60], ebx
0x1400b0e1d  mov     rcx, [rcx+10h]
0x1400b0e21  call    WPP_SF_Dd
0x1400b0e26  test    ebx, ebx
0x1400b0e28  jle     short loc_1400B0E33
0x1400b0e2a  movzx   ebx, bx
0x1400b0e2d  or      ebx, 80070000h
0x1400b0e33  test    ebx, ebx
0x1400b0e35  mov     eax, 80004005h
0x1400b0e3a  cmovns  ebx, eax
0x1400b0e3d  jmp     loc_1400B10D8
0x1400b0e42  mov     rcx, [rbp+hWnd]; hWnd
0x1400b0e46  lea     rdx, [rbp+var_20]; lpRect
0x1400b0e4a  call    cs:__imp_GetWindowRect
0x1400b0e50  test    eax, eax
0x1400b0e52  jnz     short loc_1400B0E87
0x1400b0e54  call    cs:__imp_GetLastError
0x1400b0e5a  mov     ebx, eax
0x1400b0e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0e63  lea     rax, WPP_GLOBAL_Control
0x1400b0e6a  cmp     rcx, rax
0x1400b0e6d  jz      short loc_1400B0E26
0x1400b0e6f  test    byte ptr [rcx+1Ch], 8
0x1400b0e73  jz      short loc_1400B0E26
0x1400b0e75  cmp     byte ptr [rcx+19h], 2
0x1400b0e79  jb      short loc_1400B0E26
0x1400b0e7b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0e80  mov     edx, 91h
0x1400b0e85  jmp     short loc_1400B0E08
0x1400b0e87  mov     eax, [rbp+var_20.left]
0x1400b0e8a  lea     rdx, [rbp+Point]; lpPoint
0x1400b0e8e  mov     rcx, [rdi+80h]; hWnd
0x1400b0e95  mov     [rbp+Point.x], eax
0x1400b0e98  mov     eax, [rbp+var_20.top]
0x1400b0e9b  mov     [rbp+Point.y], eax
0x1400b0e9e  call    cs:__imp_ScreenToClient
0x1400b0ea4  test    eax, eax
0x1400b0ea6  jnz     short loc_1400B0EEA
0x1400b0ea8  call    cs:__imp_GetLastError
0x1400b0eae  mov     ebx, eax
0x1400b0eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0eb7  lea     rax, WPP_GLOBAL_Control
0x1400b0ebe  cmp     rcx, rax
0x1400b0ec1  jz      loc_1400B0E26
0x1400b0ec7  test    byte ptr [rcx+1Ch], 8
0x1400b0ecb  jz      loc_1400B0E26
0x1400b0ed1  cmp     byte ptr [rcx+19h], 2
0x1400b0ed5  jb      loc_1400B0E26
0x1400b0edb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0ee0  mov     edx, 92h
0x1400b0ee5  jmp     loc_1400B0E08
0x1400b0eea  mov     r8d, [rbp+Point.y]; dy
0x1400b0eee  lea     rcx, [rbp+rc]; lprc
0x1400b0ef2  mov     edx, [rbp+Point.x]; dx
0x1400b0ef5  call    cs:__imp_OffsetRect
0x1400b0efb  test    eax, eax
0x1400b0efd  jnz     short loc_1400B0F39
0x1400b0eff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0f06  lea     rax, WPP_GLOBAL_Control
0x1400b0f0d  cmp     rcx, rax
0x1400b0f10  jz      loc_1400B10D3
0x1400b0f16  test    byte ptr [rcx+1Ch], 8
0x1400b0f1a  jz      loc_1400B10D3
0x1400b0f20  cmp     byte ptr [rcx+19h], 2
0x1400b0f24  jb      loc_1400B10D3
0x1400b0f2a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0f2f  mov     edx, 93h
0x1400b0f34  jmp     loc_1400B10B1
0x1400b0f39  mov     r9d, [rbp+rc.bottom]; y2
0x1400b0f3d  mov     r8d, [rbp+rc.right]; x2
0x1400b0f41  mov     edx, [rbp+rc.top]; y1
0x1400b0f44  mov     ecx, [rbp+rc.left]; x1
0x1400b0f47  call    cs:__imp_CreateRectRgn
0x1400b0f4d  mov     r14, rax
0x1400b0f50  test    rax, rax
0x1400b0f53  jnz     short loc_1400B0F8F
0x1400b0f55  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0f5c  lea     rax, WPP_GLOBAL_Control
0x1400b0f63  cmp     rcx, rax
0x1400b0f66  jz      loc_1400B10D3
0x1400b0f6c  test    byte ptr [rcx+1Ch], 8
0x1400b0f70  jz      loc_1400B10D3
0x1400b0f76  cmp     byte ptr [rcx+19h], 2
0x1400b0f7a  jb      loc_1400B10D3
0x1400b0f80  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0f85  mov     edx, 94h
0x1400b0f8a  jmp     loc_1400B10B1
0x1400b0f8f  mov     r9d, 3; iMode
0x1400b0f95  mov     r8, rax; hrgnSrc2
0x1400b0f98  mov     rdx, r15; hrgnSrc1
0x1400b0f9b  mov     rcx, r15; hrgnDst
0x1400b0f9e  call    cs:__imp_CombineRgn
0x1400b0fa4  cmp     eax, 1
0x1400b0fa7  jnz     short loc_1400B0FFB
0x1400b0fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0fb0  lea     rax, WPP_GLOBAL_Control
0x1400b0fb7  cmp     rcx, rax
0x1400b0fba  jz      short loc_1400B0FF4
0x1400b0fbc  test    byte ptr [rcx+1Ch], 8
0x1400b0fc0  jz      short loc_1400B0FF4
0x1400b0fc2  cmp     byte ptr [rcx+19h], 2
0x1400b0fc6  jb      short loc_1400B0FF4
0x1400b0fc8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0fd4  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0fdb  mov     edx, 95h
0x1400b0fe0  mov     dword ptr [rsp+80h+var_60], 0
0x1400b0fe8  mov     r9d, eax
0x1400b0feb  mov     rcx, [rcx+10h]
0x1400b0fef  call    WPP_SF_Dd
0x1400b0ff4  xor     ebx, ebx
0x1400b0ff6  jmp     loc_1400B10D8
0x1400b0ffb  add     eax, 0FFFFFFFEh
0x1400b0ffe  cmp     eax, 1
0x1400b1001  jbe     short loc_1400B103A
0x1400b1003  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b100a  lea     rax, WPP_GLOBAL_Control
0x1400b1011  cmp     rcx, rax
0x1400b1014  jz      loc_1400B10D3
0x1400b101a  test    byte ptr [rcx+1Ch], 8
0x1400b101e  jz      loc_1400B10D3
0x1400b1024  cmp     byte ptr [rcx+19h], 2
0x1400b1028  jb      loc_1400B10D3
0x1400b102e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1033  mov     edx, 96h
0x1400b1038  jmp     short loc_1400B10B1
0x1400b103a  mov     ecx, 4; i
0x1400b103f  call    cs:__imp_GetStockObject
0x1400b1045  test    rax, rax
0x1400b1048  jnz     short loc_1400B1075
0x1400b104a  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
