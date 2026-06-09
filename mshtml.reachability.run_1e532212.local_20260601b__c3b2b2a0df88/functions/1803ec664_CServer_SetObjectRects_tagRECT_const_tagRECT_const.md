# CServer::SetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x1803ec664`
- end: `0x1803ec99d`
- name: `?SetObjectRects@CServer@@UEAAJPEBUtagRECT@@0@Z`
- size: `825`
- prototype: `int(CServer *__hidden this, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1803ec490`

## callees

- `0x1803ec664`
- `0x1803ec9a4`
- `0x1810f65c0`

## import_xrefs

- `GDI32!DeleteObject` at `0x1803ec896`
- `GDI32!DeleteObject` at `0x1803ec8e9`
- `GDI32!DeleteObject` at `0x1803ec896`
- `GDI32!DeleteObject` at `0x1803ec8e9`
- `GDI32!CreateRectRgnIndirect` at `0x1803ec7e3`
- `GDI32!CreateRectRgnIndirect` at `0x1803ec813`
- `GDI32!CreateRectRgnIndirect` at `0x1803ec7e3`
- `GDI32!CreateRectRgnIndirect` at `0x1803ec813`
- `USER32!ValidateRgn` at `0x1803ec982`
- `USER32!ValidateRgn` at `0x1803ec982`
- `USER32!CopyRect` at `0x1803ec6de`
- `USER32!CopyRect` at `0x1803ec715`
- `USER32!CopyRect` at `0x1803ec75c`
- `USER32!CopyRect` at `0x1803ec6de`
- `USER32!CopyRect` at `0x1803ec715`
- `USER32!CopyRect` at `0x1803ec75c`
- `USER32!InflateRect` at `0x1803ec92e`
- `USER32!InflateRect` at `0x1803ec92e`
- `USER32!GetUpdateRgn` at `0x1803ec8d2`
- `USER32!GetUpdateRgn` at `0x1803ec8d2`
- `USER32!InvalidateRgn` at `0x1803ec887`
- `USER32!InvalidateRgn` at `0x1803ec887`
- `USER32!SetWindowPos` at `0x1803ec85c`
- `USER32!SetWindowPos` at `0x1803ec85c`
- `USER32!IntersectRect` at `0x1803ec78b`
- `USER32!IntersectRect` at `0x1803ec78b`
- `USER32!OffsetRect` at `0x1803ec6fe`
- `USER32!OffsetRect` at `0x1803ec735`
- `USER32!OffsetRect` at `0x1803ec7d3`
- `USER32!OffsetRect` at `0x1803ec6fe`
- `USER32!OffsetRect` at `0x1803ec735`
- `USER32!OffsetRect` at `0x1803ec7d3`
- `USER32!EqualRect` at `0x1803ec79f`
- `USER32!EqualRect` at `0x1803ec79f`
- `USER32!SetWindowRgn` at `0x1803ec800`
- `USER32!SetWindowRgn` at `0x1803ec958`
- `USER32!SetWindowRgn` at `0x1803ec800`
- `USER32!SetWindowRgn` at `0x1803ec958`

## pseudocode

```c
__int64 __fastcall CServer::SetObjectRects(CServer *this, const struct tagRECT *a2, const struct tagRECT *a3)
{
  __int64 v5; // rcx
  const RECT *v6; // rsi
  BOOL v7; // eax
  __int64 v8; // rcx
  HRGN v9; // rax
  HRGN RectRgnIndirect; // rax
  HRGN v11; // rdi
  __int64 v12; // rcx
  struct tagRECT rcDst; // [rsp+40h] [rbp-30h] BYREF
  RECT rc1; // [rsp+50h] [rbp-20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  if ( (int)(*((_DWORD *)this + 46) << 28) < 805306368 )
    return 2147549183LL;
  v5 = *((_QWORD *)this + 12);
  if ( !v5 )
    return 2147549183LL;
  v6 = a2;
  if ( a3 )
    v6 = a3;
  if ( !*((_DWORD *)this + 18) && a2->right != a2->left || !*((_DWORD *)this + 19) && a2->bottom != a2->top )
    return 2147500037LL;
  *(_QWORD *)(v5 + 8) = *(_QWORD *)&a2->left;
  CopyRect((LPRECT)(*((_QWORD *)this + 12) + 16LL), a2);
  OffsetRect(
    (LPRECT)(*((_QWORD *)this + 12) + 16LL),
    -*(_DWORD *)(*((_QWORD *)this + 12) + 8LL),
    -*(_DWORD *)(*((_QWORD *)this + 12) + 12LL));
  CopyRect((LPRECT)(*((_QWORD *)this + 12) + 32LL), v6);
  OffsetRect(
    (LPRECT)(*((_QWORD *)this + 12) + 32LL),
    -*(_DWORD *)(*((_QWORD *)this + 12) + 8LL),
    -*(_DWORD *)(*((_QWORD *)this + 12) + 12LL));
  if ( !*((_BYTE *)this + 199) )
  {
    rcDst = 0;
    CopyRect(&rcDst, a2);
    if ( *(_BYTE *)(*((_QWORD *)this + 12) + 157LL) )
      InflateRect(&rcDst, 4, 4);
    rc1 = 0;
    IntersectRect(&rc1, &rcDst, v6);
    v7 = EqualRect(&rc1, &rcDst);
    v8 = *((_QWORD *)this + 12);
    if ( v7 )
    {
      if ( *(_BYTE *)(v8 + 161) )
      {
        SetWindowRgn(*(HWND *)(v8 + 168), 0, 1);
        *(_BYTE *)(*((_QWORD *)this + 12) + 161LL) = 0;
      }
    }
    else
    {
      *(_BYTE *)(v8 + 161) = 1;
      OffsetRect(&rc1, -rcDst.left, -rcDst.top);
      v9 = CreateRectRgnIndirect(&rc1);
      SetWindowRgn(*(HWND *)(*((_QWORD *)this + 12) + 168LL), v9, 1);
    }
    RectRgnIndirect = CreateRectRgnIndirect(&g_Zero);
    v11 = RectRgnIndirect;
    if ( RectRgnIndirect )
    {
      if ( (unsigned int)GetUpdateRgn(*(HWND *)(*((_QWORD *)this + 12) + 168LL), RectRgnIndirect, 0) > 1 )
      {
        ValidateRgn(*(HWND *)(*((_QWORD *)this + 12) + 168LL), v11);
      }
      else
      {
        DeleteObject(v11);
        v11 = 0;
      }
    }
    SetWindowPos(
      *(HWND *)(*((_QWORD *)this + 12) + 168LL),
      0,
      rcDst.left,
      rcDst.top,
      rcDst.right - rcDst.left,
      rcDst.bottom - rcDst.top,
      0x14u);
    if ( v11 )
    {
      if ( CInPlace::IsInPlaceActive(*((const struct CInPlace **)this + 12)) )
        InvalidateRgn(*(HWND *)(v12 + 168), v11, 0);
      DeleteObject(v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1803ec664  mov     [rsp-18h+arg_18], rbx
0x1803ec669  push    rbp
0x1803ec66a  push    rsi
0x1803ec66b  push    rdi
0x1803ec66c  mov     rbp, rsp
0x1803ec66f  sub     rsp, 70h
0x1803ec673  mov     rax, cs:__security_cookie
0x1803ec67a  xor     rax, rsp
0x1803ec67d  mov     [rbp+var_10], rax
0x1803ec681  mov     rdi, rdx
0x1803ec684  mov     rbx, rcx
0x1803ec687  test    rdx, rdx
0x1803ec68a  jz      loc_1803EC8FC
0x1803ec690  mov     eax, [rcx+0B8h]
0x1803ec696  shl     eax, 1Ch
0x1803ec699  cmp     eax, 30000000h
0x1803ec69e  jl      loc_1803EC993
0x1803ec6a4  mov     rcx, [rcx+60h]
0x1803ec6a8  test    rcx, rcx
0x1803ec6ab  jz      loc_1803EC993
0x1803ec6b1  test    r8, r8
0x1803ec6b4  mov     rsi, rdx
0x1803ec6b7  cmovnz  rsi, r8
0x1803ec6bb  cmp     dword ptr [rbx+48h], 0
0x1803ec6bf  jz      loc_1803EC903
0x1803ec6c5  cmp     dword ptr [rbx+4Ch], 0
0x1803ec6c9  jz      loc_1803EC90F
0x1803ec6cf  mov     rax, [rdx]
0x1803ec6d2  mov     [rcx+8], rax
0x1803ec6d6  mov     rcx, [rbx+60h]
0x1803ec6da  add     rcx, 10h; lprcDst
0x1803ec6de  call    cs:__imp_CopyRect
0x1803ec6e5  nop     dword ptr [rax+rax+00h]
0x1803ec6ea  mov     rcx, [rbx+60h]
0x1803ec6ee  mov     r8d, [rcx+0Ch]
0x1803ec6f2  mov     edx, [rcx+8]
0x1803ec6f5  neg     r8d; dy
0x1803ec6f8  neg     edx; dx
0x1803ec6fa  add     rcx, 10h; lprc
0x1803ec6fe  call    cs:__imp_OffsetRect
0x1803ec705  nop     dword ptr [rax+rax+00h]
0x1803ec70a  mov     rcx, [rbx+60h]
0x1803ec70e  mov     rdx, rsi; lprcSrc
0x1803ec711  add     rcx, 20h ; ' '; lprcDst
0x1803ec715  call    cs:__imp_CopyRect
0x1803ec71c  nop     dword ptr [rax+rax+00h]
0x1803ec721  mov     rcx, [rbx+60h]
0x1803ec725  mov     r8d, [rcx+0Ch]
0x1803ec729  mov     edx, [rcx+8]
0x1803ec72c  neg     r8d; dy
0x1803ec72f  neg     edx; dx
0x1803ec731  add     rcx, 20h ; ' '; lprc
0x1803ec735  call    cs:__imp_OffsetRect
0x1803ec73c  nop     dword ptr [rax+rax+00h]
0x1803ec741  cmp     byte ptr [rbx+0C7h], 0
0x1803ec748  jnz     loc_1803EC8A2
0x1803ec74e  xorps   xmm0, xmm0
0x1803ec751  lea     rcx, [rbp+rcDst]; lprcDst
0x1803ec755  mov     rdx, rdi; lprcSrc
0x1803ec758  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1803ec75c  call    cs:__imp_CopyRect
0x1803ec763  nop     dword ptr [rax+rax+00h]
0x1803ec768  mov     rax, [rbx+60h]
0x1803ec76c  cmp     byte ptr [rax+9Dh], 0
0x1803ec773  jnz     loc_1803EC922
0x1803ec779  xorps   xmm0, xmm0
0x1803ec77c  lea     rdx, [rbp+rcDst]; lprcSrc1
0x1803ec780  mov     r8, rsi; lprcSrc2
0x1803ec783  lea     rcx, [rbp+rc1]; lprcDst
0x1803ec787  movups  xmmword ptr [rbp+rc1.left], xmm0
0x1803ec78b  call    cs:__imp_IntersectRect
0x1803ec792  nop     dword ptr [rax+rax+00h]
0x1803ec797  lea     rdx, [rbp+rcDst]; lprc2
0x1803ec79b  lea     rcx, [rbp+rc1]; lprc1
0x1803ec79f  call    cs:__imp_EqualRect
0x1803ec7a6  nop     dword ptr [rax+rax+00h]
0x1803ec7ab  mov     rcx, [rbx+60h]
0x1803ec7af  mov     esi, 1
0x1803ec7b4  test    eax, eax
0x1803ec7b6  jnz     loc_1803EC93F
0x1803ec7bc  mov     [rcx+0A1h], sil
0x1803ec7c3  lea     rcx, [rbp+rc1]; lprc
0x1803ec7c7  mov     r8d, [rbp+rcDst.top]
0x1803ec7cb  mov     edx, [rbp+rcDst.left]
0x1803ec7ce  neg     r8d; dy
0x1803ec7d1  neg     edx; dx
0x1803ec7d3  call    cs:__imp_OffsetRect
0x1803ec7da  nop     dword ptr [rax+rax+00h]
0x1803ec7df  lea     rcx, [rbp+rc1]; lprect
0x1803ec7e3  call    cs:__imp_CreateRectRgnIndirect
0x1803ec7ea  nop     dword ptr [rax+rax+00h]
0x1803ec7ef  mov     rcx, [rbx+60h]
0x1803ec7f3  mov     r8d, esi; bRedraw
0x1803ec7f6  mov     rdx, rax; hRgn
0x1803ec7f9  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec800  call    cs:__imp_SetWindowRgn
0x1803ec807  nop     dword ptr [rax+rax+00h]
0x1803ec80c  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x1803ec813  call    cs:__imp_CreateRectRgnIndirect
0x1803ec81a  nop     dword ptr [rax+rax+00h]
0x1803ec81f  mov     rdi, rax
0x1803ec822  test    rax, rax
0x1803ec825  jnz     loc_1803EC8C1
0x1803ec82b  mov     edx, [rbp+rcDst.bottom]
0x1803ec82e  mov     rcx, [rbx+60h]
0x1803ec832  mov     r9d, [rbp+rcDst.top]; Y
0x1803ec836  sub     edx, r9d
0x1803ec839  mov     eax, [rbp+rcDst.right]
0x1803ec83c  mov     r8d, [rbp+rcDst.left]; X
0x1803ec840  sub     eax, r8d
0x1803ec843  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec84a  mov     [rsp+70h+uFlags], 14h; uFlags
0x1803ec852  mov     [rsp+70h+cy], edx; cy
0x1803ec856  xor     edx, edx; hWndInsertAfter
0x1803ec858  mov     [rsp+70h+var_50], eax; cx
0x1803ec85c  call    cs:__imp_SetWindowPos
0x1803ec863  nop     dword ptr [rax+rax+00h]
0x1803ec868  test    rdi, rdi
0x1803ec86b  jz      short loc_1803EC8A2
0x1803ec86d  mov     rcx, [rbx+60h]; struct CInPlace *
0x1803ec871  call    ?IsInPlaceActive@CInPlace@@SA_NPEBV1@@Z; CInPlace::IsInPlaceActive(CInPlace const *)
0x1803ec876  test    al, al
0x1803ec878  jz      short loc_1803EC893
0x1803ec87a  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec881  xor     r8d, r8d; bErase
0x1803ec884  mov     rdx, rdi; hRgn
0x1803ec887  call    cs:__imp_InvalidateRgn
0x1803ec88e  nop     dword ptr [rax+rax+00h]
0x1803ec893  mov     rcx, rdi; ho
0x1803ec896  call    cs:__imp_DeleteObject
0x1803ec89d  nop     dword ptr [rax+rax+00h]
0x1803ec8a2  xor     eax, eax
0x1803ec8a4  mov     rcx, [rbp+var_10]
0x1803ec8a8  xor     rcx, rsp; StackCookie
0x1803ec8ab  call    __security_check_cookie
0x1803ec8b0  mov     rbx, [rsp+70h+arg_18]
0x1803ec8b8  add     rsp, 70h
0x1803ec8bc  pop     rdi
0x1803ec8bd  pop     rsi
0x1803ec8be  pop     rbp
0x1803ec8bf  retn
0x1803ec8c1  mov     rcx, [rbx+60h]
0x1803ec8c5  xor     r8d, r8d; bErase
0x1803ec8c8  mov     rdx, rdi; hRgn
0x1803ec8cb  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec8d2  call    cs:__imp_GetUpdateRgn
0x1803ec8d9  nop     dword ptr [rax+rax+00h]
0x1803ec8de  cmp     eax, esi
0x1803ec8e0  ja      loc_1803EC974
0x1803ec8e6  mov     rcx, rdi; ho
0x1803ec8e9  call    cs:__imp_DeleteObject
0x1803ec8f0  nop     dword ptr [rax+rax+00h]
0x1803ec8f5  xor     edi, edi
0x1803ec8f7  jmp     loc_1803EC82B
0x1803ec8fc  mov     eax, 80070057h
0x1803ec901  jmp     short loc_1803EC8A4
0x1803ec903  mov     eax, [rdx+8]
0x1803ec906  cmp     eax, [rdx]
0x1803ec908  jnz     short loc_1803EC91B
0x1803ec90a  jmp     loc_1803EC6C5
0x1803ec90f  mov     eax, [rdx+0Ch]
0x1803ec912  cmp     eax, [rdx+4]
0x1803ec915  jz      loc_1803EC6CF
0x1803ec91b  mov     eax, 80004005h
0x1803ec920  jmp     short loc_1803EC8A4
0x1803ec922  mov     edx, 4; dx
0x1803ec927  lea     rcx, [rbp+rcDst]; lprc
0x1803ec92b  mov     r8d, edx; dy
0x1803ec92e  call    cs:__imp_InflateRect
0x1803ec935  nop     dword ptr [rax+rax+00h]
0x1803ec93a  jmp     loc_1803EC779
0x1803ec93f  cmp     byte ptr [rcx+0A1h], 0
0x1803ec946  jz      loc_1803EC80C
0x1803ec94c  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec953  mov     r8d, esi; bRedraw
0x1803ec956  xor     edx, edx; hRgn
0x1803ec958  call    cs:__imp_SetWindowRgn
0x1803ec95f  nop     dword ptr [rax+rax+00h]
0x1803ec964  mov     rax, [rbx+60h]
0x1803ec968  mov     byte ptr [rax+0A1h], 0
0x1803ec96f  jmp     loc_1803EC80C
0x1803ec974  mov     rcx, [rbx+60h]
0x1803ec978  mov     rdx, rdi; hRgn
0x1803ec97b  mov     rcx, [rcx+0A8h]; hWnd
0x1803ec982  call    cs:__imp_ValidateRgn
0x1803ec989  nop     dword ptr [rax+rax+00h]
0x1803ec98e  jmp     loc_1803EC82B
0x1803ec993  mov     eax, 8000FFFFh
0x1803ec998  jmp     loc_1803EC8A4
```
