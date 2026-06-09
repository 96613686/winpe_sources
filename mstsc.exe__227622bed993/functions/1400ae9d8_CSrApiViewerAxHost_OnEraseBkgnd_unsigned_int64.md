# CSrApiViewerAxHost::OnEraseBkgnd(unsigned __int64)

- ea: `0x1400ae9d8`
- end: `0x1400aefa4`
- name: `?OnEraseBkgnd@CSrApiViewerAxHost@@AEAAJ_K@Z`
- size: `1484`
- prototype: `int(CSrApiViewerAxHost *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400ac5b4`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400ae9d8`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!ScreenToClient` at `0x1400aed2e`
- `USER32!ScreenToClient` at `0x1400aed2e`
- `USER32!GetClientRect` at `0x1400aeae0`
- `USER32!GetClientRect` at `0x1400aec5d`
- `USER32!GetClientRect` at `0x1400aeae0`
- `USER32!GetClientRect` at `0x1400aec5d`
- `USER32!OffsetRect` at `0x1400aed85`
- `USER32!OffsetRect` at `0x1400aed85`
- `USER32!GetWindowRect` at `0x1400aecda`
- `USER32!GetWindowRect` at `0x1400aecda`
- `KERNEL32!GetLastError` at `0x1400aeaea`
- `KERNEL32!GetLastError` at `0x1400aec67`
- `KERNEL32!GetLastError` at `0x1400aece4`
- `KERNEL32!GetLastError` at `0x1400aed38`
- `KERNEL32!GetLastError` at `0x1400aeaea`
- `KERNEL32!GetLastError` at `0x1400aec67`
- `KERNEL32!GetLastError` at `0x1400aece4`
- `KERNEL32!GetLastError` at `0x1400aed38`
- `GDI32!GetStockObject` at `0x1400aeecf`
- `GDI32!GetStockObject` at `0x1400aeecf`
- `GDI32!CombineRgn` at `0x1400aee2e`
- `GDI32!CombineRgn` at `0x1400aee2e`
- `GDI32!DeleteObject` at `0x1400aef6b`
- `GDI32!DeleteObject` at `0x1400aef79`
- `GDI32!DeleteObject` at `0x1400aef6b`
- `GDI32!DeleteObject` at `0x1400aef79`
- `GDI32!FillRgn` at `0x1400aef0e`
- `GDI32!FillRgn` at `0x1400aef0e`
- `GDI32!CreateRectRgn` at `0x1400aeb71`
- `GDI32!CreateRectRgn` at `0x1400aedd7`
- `GDI32!CreateRectRgn` at `0x1400aeb71`
- `GDI32!CreateRectRgn` at `0x1400aedd7`

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
        LastError);
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
0x1400ae9d8  mov     [rsp-28h+arg_10], rbx
0x1400ae9dd  push    rbp
0x1400ae9de  push    rsi
0x1400ae9df  push    rdi
0x1400ae9e0  push    r14
0x1400ae9e2  push    r15
0x1400ae9e4  mov     rbp, rsp
0x1400ae9e7  sub     rsp, 80h
0x1400ae9ee  mov     rax, cs:__security_cookie
0x1400ae9f5  xor     rax, rsp
0x1400ae9f8  mov     [rbp+var_10], rax
0x1400ae9fc  mov     [rbp+hWnd], 0
0x1400aea04  xorps   xmm0, xmm0
0x1400aea07  mov     qword ptr [rbp+Point.x], 0
0x1400aea0f  xorps   xmm1, xmm1
0x1400aea12  mov     rsi, rdx
0x1400aea15  mov     rdi, rcx
0x1400aea18  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1400aea1c  movups  xmmword ptr [rbp+rc.left], xmm1
0x1400aea20  movups  xmmword ptr [rbp+var_20.left], xmm0
0x1400aea24  test    rdx, rdx
0x1400aea27  jnz     short loc_1400AEA7E
0x1400aea29  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aea30  lea     rax, WPP_GLOBAL_Control
0x1400aea37  cmp     rcx, rax
0x1400aea3a  jz      short loc_1400AEA74
0x1400aea3c  test    byte ptr [rcx+1Ch], 8
0x1400aea40  jz      short loc_1400AEA74
0x1400aea42  cmp     byte ptr [rcx+19h], 2
0x1400aea46  jb      short loc_1400AEA74
0x1400aea48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aea4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aea54  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aea5b  mov     edx, 8Bh
0x1400aea60  mov     dword ptr [rsp+80h+var_60], 8000FFFFh
0x1400aea68  mov     r9d, eax
0x1400aea6b  mov     rcx, [rcx+10h]
0x1400aea6f  call    WPP_SF_Dd
0x1400aea74  mov     ebx, 8000FFFFh
0x1400aea79  jmp     loc_1400AEF7F
0x1400aea7e  mov     rcx, [rcx+80h]; hWnd
0x1400aea85  test    rcx, rcx
0x1400aea88  jnz     short loc_1400AEADC
0x1400aea8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aea91  lea     rax, WPP_GLOBAL_Control
0x1400aea98  cmp     rcx, rax
0x1400aea9b  jz      short loc_1400AEAD5
0x1400aea9d  test    byte ptr [rcx+1Ch], 8
0x1400aeaa1  jz      short loc_1400AEAD5
0x1400aeaa3  cmp     byte ptr [rcx+19h], 2
0x1400aeaa7  jb      short loc_1400AEAD5
0x1400aeaa9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aeaae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeab5  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aeabc  mov     edx, 8Ch
0x1400aeac1  mov     dword ptr [rsp+80h+var_60], 0
0x1400aeac9  mov     r9d, eax
0x1400aeacc  mov     rcx, [rcx+10h]
0x1400aead0  call    WPP_SF_Dd
0x1400aead5  xor     ebx, ebx
0x1400aead7  jmp     loc_1400AEF7F
0x1400aeadc  lea     rdx, [rbp+Rect]; lpRect
0x1400aeae0  call    cs:__imp_GetClientRect
0x1400aeae6  test    eax, eax
0x1400aeae8  jnz     short loc_1400AEB55
0x1400aeaea  call    cs:__imp_GetLastError
0x1400aeaf0  mov     ebx, eax
0x1400aeaf2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeaf9  lea     rax, WPP_GLOBAL_Control
0x1400aeb00  cmp     rcx, rax
0x1400aeb03  jz      short loc_1400AEB39
0x1400aeb05  test    byte ptr [rcx+1Ch], 8
0x1400aeb09  jz      short loc_1400AEB39
0x1400aeb0b  cmp     byte ptr [rcx+19h], 2
0x1400aeb0f  jb      short loc_1400AEB39
0x1400aeb11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aeb16  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeb1d  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aeb24  mov     edx, 8Dh
0x1400aeb29  mov     dword ptr [rsp+80h+var_60], ebx
0x1400aeb2d  mov     r9d, eax
0x1400aeb30  mov     rcx, [rcx+10h]
0x1400aeb34  call    WPP_SF_Dd
0x1400aeb39  test    ebx, ebx
0x1400aeb3b  jle     short loc_1400AEB46
0x1400aeb3d  movzx   ebx, bx
0x1400aeb40  or      ebx, 80070000h
0x1400aeb46  test    ebx, ebx
0x1400aeb48  mov     eax, 80004005h
0x1400aeb4d  cmovns  ebx, eax
0x1400aeb50  jmp     loc_1400AEF7F
0x1400aeb55  mov     r9d, [rbp+Rect.bottom]
0x1400aeb59  mov     r8d, [rbp+Rect.right]
0x1400aeb5d  inc     r9d; y2
0x1400aeb60  mov     edx, [rbp+Rect.top]; y1
0x1400aeb63  inc     r8d; x2
0x1400aeb66  mov     ecx, [rbp+Rect.left]; x1
0x1400aeb69  mov     [rbp+Rect.bottom], r9d
0x1400aeb6d  mov     [rbp+Rect.right], r8d
0x1400aeb71  call    cs:__imp_CreateRectRgn
0x1400aeb77  mov     r15, rax
0x1400aeb7a  test    rax, rax
0x1400aeb7d  jnz     short loc_1400AEBD4
0x1400aeb7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeb86  lea     rax, WPP_GLOBAL_Control
0x1400aeb8d  cmp     rcx, rax
0x1400aeb90  jz      short loc_1400AEBCA
0x1400aeb92  test    byte ptr [rcx+1Ch], 8
0x1400aeb96  jz      short loc_1400AEBCA
0x1400aeb98  cmp     byte ptr [rcx+19h], 2
0x1400aeb9c  jb      short loc_1400AEBCA
0x1400aeb9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aeba3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aebaa  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aebb1  mov     edx, 8Eh
0x1400aebb6  mov     dword ptr [rsp+80h+var_60], 80004005h
0x1400aebbe  mov     r9d, eax
0x1400aebc1  mov     rcx, [rcx+10h]
0x1400aebc5  call    WPP_SF_Dd
0x1400aebca  mov     ebx, 80004005h
0x1400aebcf  jmp     loc_1400AEF7F
0x1400aebd4  mov     rcx, [rdi+70h]
0x1400aebd8  lea     rdx, [rbp+hWnd]
0x1400aebdc  xor     r14d, r14d
0x1400aebdf  mov     rax, [rcx]
0x1400aebe2  mov     rax, [rax+18h]
0x1400aebe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400aebeb  mov     ebx, eax
0x1400aebed  test    eax, eax
0x1400aebef  jns     short loc_1400AEC55
0x1400aebf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aebf8  lea     rax, WPP_GLOBAL_Control
0x1400aebff  cmp     rcx, rax
0x1400aec02  jz      loc_1400AEF68
0x1400aec08  test    byte ptr [rcx+1Ch], 8
0x1400aec0c  jz      loc_1400AEF68
0x1400aec12  cmp     byte ptr [rcx+19h], 2
0x1400aec16  jb      loc_1400AEF68
0x1400aec1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aec21  lea     rcx, aMSpoleinplacea; "m_spOleInPlaceActiveObject->GetWindow f"...
0x1400aec28  mov     [rsp+80h+var_58], ebx
0x1400aec2c  mov     [rsp+80h+var_60], rcx
0x1400aec31  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aec38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aec3f  mov     edx, 8Fh
0x1400aec44  mov     r9d, eax
0x1400aec47  mov     rcx, [rcx+10h]
0x1400aec4b  call    WPP_SF_DsD
0x1400aec50  jmp     loc_1400AEF68
0x1400aec55  mov     rcx, [rbp+hWnd]; hWnd
0x1400aec59  lea     rdx, [rbp+rc]; lpRect
0x1400aec5d  call    cs:__imp_GetClientRect
0x1400aec63  test    eax, eax
0x1400aec65  jnz     short loc_1400AECD2
0x1400aec67  call    cs:__imp_GetLastError
0x1400aec6d  mov     ebx, eax
0x1400aec6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aec76  lea     rax, WPP_GLOBAL_Control
0x1400aec7d  cmp     rcx, rax
0x1400aec80  jz      short loc_1400AECB6
0x1400aec82  test    byte ptr [rcx+1Ch], 8
0x1400aec86  jz      short loc_1400AECB6
0x1400aec88  cmp     byte ptr [rcx+19h], 2
0x1400aec8c  jb      short loc_1400AECB6
0x1400aec8e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aec93  mov     edx, 90h
0x1400aec98  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aec9f  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aeca6  mov     r9d, eax
0x1400aeca9  mov     dword ptr [rsp+80h+var_60], ebx
0x1400aecad  mov     rcx, [rcx+10h]
0x1400aecb1  call    WPP_SF_Dd
0x1400aecb6  test    ebx, ebx
0x1400aecb8  jle     short loc_1400AECC3
0x1400aecba  movzx   ebx, bx
0x1400aecbd  or      ebx, 80070000h
0x1400aecc3  test    ebx, ebx
0x1400aecc5  mov     eax, 80004005h
0x1400aecca  cmovns  ebx, eax
0x1400aeccd  jmp     loc_1400AEF68
0x1400aecd2  mov     rcx, [rbp+hWnd]; hWnd
0x1400aecd6  lea     rdx, [rbp+var_20]; lpRect
0x1400aecda  call    cs:__imp_GetWindowRect
0x1400aece0  test    eax, eax
0x1400aece2  jnz     short loc_1400AED17
0x1400aece4  call    cs:__imp_GetLastError
0x1400aecea  mov     ebx, eax
0x1400aecec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aecf3  lea     rax, WPP_GLOBAL_Control
0x1400aecfa  cmp     rcx, rax
0x1400aecfd  jz      short loc_1400AECB6
0x1400aecff  test    byte ptr [rcx+1Ch], 8
0x1400aed03  jz      short loc_1400AECB6
0x1400aed05  cmp     byte ptr [rcx+19h], 2
0x1400aed09  jb      short loc_1400AECB6
0x1400aed0b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aed10  mov     edx, 91h
0x1400aed15  jmp     short loc_1400AEC98
0x1400aed17  mov     eax, [rbp+var_20.left]
0x1400aed1a  lea     rdx, [rbp+Point]; lpPoint
0x1400aed1e  mov     rcx, [rdi+80h]; hWnd
0x1400aed25  mov     [rbp+Point.x], eax
0x1400aed28  mov     eax, [rbp+var_20.top]
0x1400aed2b  mov     [rbp+Point.y], eax
0x1400aed2e  call    cs:__imp_ScreenToClient
0x1400aed34  test    eax, eax
0x1400aed36  jnz     short loc_1400AED7A
0x1400aed38  call    cs:__imp_GetLastError
0x1400aed3e  mov     ebx, eax
0x1400aed40  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aed47  lea     rax, WPP_GLOBAL_Control
0x1400aed4e  cmp     rcx, rax
0x1400aed51  jz      loc_1400AECB6
0x1400aed57  test    byte ptr [rcx+1Ch], 8
0x1400aed5b  jz      loc_1400AECB6
0x1400aed61  cmp     byte ptr [rcx+19h], 2
0x1400aed65  jb      loc_1400AECB6
0x1400aed6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aed70  mov     edx, 92h
0x1400aed75  jmp     loc_1400AEC98
0x1400aed7a  mov     r8d, [rbp+Point.y]; dy
0x1400aed7e  lea     rcx, [rbp+rc]; lprc
0x1400aed82  mov     edx, [rbp+Point.x]; dx
0x1400aed85  call    cs:__imp_OffsetRect
0x1400aed8b  test    eax, eax
0x1400aed8d  jnz     short loc_1400AEDC9
0x1400aed8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aed96  lea     rax, WPP_GLOBAL_Control
0x1400aed9d  cmp     rcx, rax
0x1400aeda0  jz      loc_1400AEF63
0x1400aeda6  test    byte ptr [rcx+1Ch], 8
0x1400aedaa  jz      loc_1400AEF63
0x1400aedb0  cmp     byte ptr [rcx+19h], 2
0x1400aedb4  jb      loc_1400AEF63
0x1400aedba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aedbf  mov     edx, 93h
0x1400aedc4  jmp     loc_1400AEF41
0x1400aedc9  mov     r9d, [rbp+rc.bottom]; y2
0x1400aedcd  mov     r8d, [rbp+rc.right]; x2
0x1400aedd1  mov     edx, [rbp+rc.top]; y1
0x1400aedd4  mov     ecx, [rbp+rc.left]; x1
0x1400aedd7  call    cs:__imp_CreateRectRgn
0x1400aeddd  mov     r14, rax
0x1400aede0  test    rax, rax
0x1400aede3  jnz     short loc_1400AEE1F
0x1400aede5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aedec  lea     rax, WPP_GLOBAL_Control
0x1400aedf3  cmp     rcx, rax
0x1400aedf6  jz      loc_1400AEF63
0x1400aedfc  test    byte ptr [rcx+1Ch], 8
0x1400aee00  jz      loc_1400AEF63
0x1400aee06  cmp     byte ptr [rcx+19h], 2
0x1400aee0a  jb      loc_1400AEF63
0x1400aee10  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aee15  mov     edx, 94h
0x1400aee1a  jmp     loc_1400AEF41
0x1400aee1f  mov     r9d, 3; iMode
0x1400aee25  mov     r8, rax; hrgnSrc2
0x1400aee28  mov     rdx, r15; hrgnSrc1
0x1400aee2b  mov     rcx, r15; hrgnDst
0x1400aee2e  call    cs:__imp_CombineRgn
0x1400aee34  cmp     eax, 1
0x1400aee37  jnz     short loc_1400AEE8B
0x1400aee39  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee40  lea     rax, WPP_GLOBAL_Control
0x1400aee47  cmp     rcx, rax
0x1400aee4a  jz      short loc_1400AEE84
0x1400aee4c  test    byte ptr [rcx+1Ch], 8
0x1400aee50  jz      short loc_1400AEE84
0x1400aee52  cmp     byte ptr [rcx+19h], 2
0x1400aee56  jb      short loc_1400AEE84
0x1400aee58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aee5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee64  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aee6b  mov     edx, 95h
0x1400aee70  mov     dword ptr [rsp+80h+var_60], 0
0x1400aee78  mov     r9d, eax
0x1400aee7b  mov     rcx, [rcx+10h]
0x1400aee7f  call    WPP_SF_Dd
0x1400aee84  xor     ebx, ebx
0x1400aee86  jmp     loc_1400AEF68
0x1400aee8b  add     eax, 0FFFFFFFEh
0x1400aee8e  cmp     eax, 1
0x1400aee91  jbe     short loc_1400AEECA
0x1400aee93  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee9a  lea     rax, WPP_GLOBAL_Control
0x1400aeea1  cmp     rcx, rax
0x1400aeea4  jz      loc_1400AEF63
0x1400aeeaa  test    byte ptr [rcx+1Ch], 8
0x1400aeeae  jz      loc_1400AEF63
0x1400aeeb4  cmp     byte ptr [rcx+19h], 2
0x1400aeeb8  jb      loc_1400AEF63
0x1400aeebe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aeec3  mov     edx, 96h
0x1400aeec8  jmp     short loc_1400AEF41
0x1400aeeca  mov     ecx, 4; i
0x1400aeecf  call    cs:__imp_GetStockObject
0x1400aeed5  test    rax, rax
0x1400aeed8  jnz     short loc_1400AEF05
0x1400aeeda  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
