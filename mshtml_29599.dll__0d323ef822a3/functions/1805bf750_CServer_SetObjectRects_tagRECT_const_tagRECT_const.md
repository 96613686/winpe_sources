# CServer::SetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x1805bf750`
- end: `0x1805bfa12`
- name: `?SetObjectRects@CServer@@UEAAJPEBUtagRECT@@0@Z`
- size: `706`
- prototype: `int(CServer *__hidden this, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1805bf580`

## callees

- `0x1805bf750`
- `0x1805bfa18`
- `0x1810c2d60`

## import_xrefs

- `GDI32!DeleteObject` at `0x1805bf934`
- `GDI32!DeleteObject` at `0x1805bf976`
- `GDI32!DeleteObject` at `0x1805bf934`
- `GDI32!DeleteObject` at `0x1805bf976`
- `GDI32!CreateRectRgnIndirect` at `0x1805bf89f`
- `GDI32!CreateRectRgnIndirect` at `0x1805bf8c3`
- `GDI32!CreateRectRgnIndirect` at `0x1805bf89f`
- `GDI32!CreateRectRgnIndirect` at `0x1805bf8c3`
- `USER32!ValidateRgn` at `0x1805bf9fd`
- `USER32!ValidateRgn` at `0x1805bf9fd`
- `USER32!CopyRect` at `0x1805bf7ca`
- `USER32!CopyRect` at `0x1805bf7f5`
- `USER32!CopyRect` at `0x1805bf830`
- `USER32!CopyRect` at `0x1805bf7ca`
- `USER32!CopyRect` at `0x1805bf7f5`
- `USER32!CopyRect` at `0x1805bf830`
- `USER32!InflateRect` at `0x1805bf9b5`
- `USER32!InflateRect` at `0x1805bf9b5`
- `USER32!GetUpdateRgn` at `0x1805bf969`
- `USER32!GetUpdateRgn` at `0x1805bf969`
- `USER32!InvalidateRgn` at `0x1805bf92b`
- `USER32!InvalidateRgn` at `0x1805bf92b`
- `USER32!SetWindowPos` at `0x1805bf906`
- `USER32!SetWindowPos` at `0x1805bf906`
- `USER32!IntersectRect` at `0x1805bf859`
- `USER32!IntersectRect` at `0x1805bf859`
- `USER32!OffsetRect` at `0x1805bf7e4`
- `USER32!OffsetRect` at `0x1805bf80f`
- `USER32!OffsetRect` at `0x1805bf895`
- `USER32!OffsetRect` at `0x1805bf7e4`
- `USER32!OffsetRect` at `0x1805bf80f`
- `USER32!OffsetRect` at `0x1805bf895`
- `USER32!EqualRect` at `0x1805bf867`
- `USER32!EqualRect` at `0x1805bf867`
- `USER32!SetWindowRgn` at `0x1805bf8b6`
- `USER32!SetWindowRgn` at `0x1805bf9d9`
- `USER32!SetWindowRgn` at `0x1805bf8b6`
- `USER32!SetWindowRgn` at `0x1805bf9d9`

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
0x1805bf750  mov     [rsp-18h+arg_18], rbx
0x1805bf755  push    rbp
0x1805bf756  push    rsi
0x1805bf757  push    rdi
0x1805bf758  mov     rbp, rsp
0x1805bf75b  sub     rsp, 70h
0x1805bf75f  mov     rax, cs:__security_cookie
0x1805bf766  xor     rax, rsp
0x1805bf769  mov     [rbp+var_10], rax
0x1805bf76d  mov     rdi, rdx
0x1805bf770  mov     rbx, rcx
0x1805bf773  test    rdx, rdx
0x1805bf776  jz      loc_1805BF983
0x1805bf77c  mov     eax, [rcx+0B8h]
0x1805bf782  shl     eax, 1Ch
0x1805bf785  cmp     eax, 30000000h
0x1805bf78a  jl      loc_1805BFA08
0x1805bf790  mov     rcx, [rcx+60h]
0x1805bf794  test    rcx, rcx
0x1805bf797  jz      loc_1805BFA08
0x1805bf79d  test    r8, r8
0x1805bf7a0  mov     rsi, rdx
0x1805bf7a3  cmovnz  rsi, r8
0x1805bf7a7  cmp     dword ptr [rbx+48h], 0
0x1805bf7ab  jz      loc_1805BF98A
0x1805bf7b1  cmp     dword ptr [rbx+4Ch], 0
0x1805bf7b5  jz      loc_1805BF996
0x1805bf7bb  mov     rax, [rdx]
0x1805bf7be  mov     [rcx+8], rax
0x1805bf7c2  mov     rcx, [rbx+60h]
0x1805bf7c6  add     rcx, 10h; lprcDst
0x1805bf7ca  call    cs:__imp_CopyRect
0x1805bf7d0  mov     rcx, [rbx+60h]
0x1805bf7d4  mov     r8d, [rcx+0Ch]
0x1805bf7d8  mov     edx, [rcx+8]
0x1805bf7db  neg     r8d; dy
0x1805bf7de  neg     edx; dx
0x1805bf7e0  add     rcx, 10h; lprc
0x1805bf7e4  call    cs:__imp_OffsetRect
0x1805bf7ea  mov     rcx, [rbx+60h]
0x1805bf7ee  mov     rdx, rsi; lprcSrc
0x1805bf7f1  add     rcx, 20h ; ' '; lprcDst
0x1805bf7f5  call    cs:__imp_CopyRect
0x1805bf7fb  mov     rcx, [rbx+60h]
0x1805bf7ff  mov     r8d, [rcx+0Ch]
0x1805bf803  mov     edx, [rcx+8]
0x1805bf806  neg     r8d; dy
0x1805bf809  neg     edx; dx
0x1805bf80b  add     rcx, 20h ; ' '; lprc
0x1805bf80f  call    cs:__imp_OffsetRect
0x1805bf815  cmp     byte ptr [rbx+0C7h], 0
0x1805bf81c  jnz     loc_1805BF93A
0x1805bf822  xorps   xmm0, xmm0
0x1805bf825  lea     rcx, [rbp+rcDst]; lprcDst
0x1805bf829  mov     rdx, rdi; lprcSrc
0x1805bf82c  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1805bf830  call    cs:__imp_CopyRect
0x1805bf836  mov     rax, [rbx+60h]
0x1805bf83a  cmp     byte ptr [rax+9Dh], 0
0x1805bf841  jnz     loc_1805BF9A9
0x1805bf847  xorps   xmm0, xmm0
0x1805bf84a  lea     rdx, [rbp+rcDst]; lprcSrc1
0x1805bf84e  mov     r8, rsi; lprcSrc2
0x1805bf851  lea     rcx, [rbp+rc1]; lprcDst
0x1805bf855  movups  xmmword ptr [rbp+rc1.left], xmm0
0x1805bf859  call    cs:__imp_IntersectRect
0x1805bf85f  lea     rdx, [rbp+rcDst]; lprc2
0x1805bf863  lea     rcx, [rbp+rc1]; lprc1
0x1805bf867  call    cs:__imp_EqualRect
0x1805bf86d  mov     rcx, [rbx+60h]
0x1805bf871  mov     esi, 1
0x1805bf876  test    eax, eax
0x1805bf878  jnz     loc_1805BF9C0
0x1805bf87e  mov     [rcx+0A1h], sil
0x1805bf885  lea     rcx, [rbp+rc1]; lprc
0x1805bf889  mov     r8d, [rbp+rcDst.top]
0x1805bf88d  mov     edx, [rbp+rcDst.left]
0x1805bf890  neg     r8d; dy
0x1805bf893  neg     edx; dx
0x1805bf895  call    cs:__imp_OffsetRect
0x1805bf89b  lea     rcx, [rbp+rc1]; lprect
0x1805bf89f  call    cs:__imp_CreateRectRgnIndirect
0x1805bf8a5  mov     rcx, [rbx+60h]
0x1805bf8a9  mov     r8d, esi; bRedraw
0x1805bf8ac  mov     rdx, rax; hRgn
0x1805bf8af  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf8b6  call    cs:__imp_SetWindowRgn
0x1805bf8bc  lea     rcx, ?g_Zero@@3TZERO_STRUCTS@@B; lprect
0x1805bf8c3  call    cs:__imp_CreateRectRgnIndirect
0x1805bf8c9  mov     rdi, rax
0x1805bf8cc  test    rax, rax
0x1805bf8cf  jnz     loc_1805BF958
0x1805bf8d5  mov     edx, [rbp+rcDst.bottom]
0x1805bf8d8  mov     rcx, [rbx+60h]
0x1805bf8dc  mov     r9d, [rbp+rcDst.top]; Y
0x1805bf8e0  sub     edx, r9d
0x1805bf8e3  mov     eax, [rbp+rcDst.right]
0x1805bf8e6  mov     r8d, [rbp+rcDst.left]; X
0x1805bf8ea  sub     eax, r8d
0x1805bf8ed  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf8f4  mov     [rsp+70h+uFlags], 14h; uFlags
0x1805bf8fc  mov     [rsp+70h+cy], edx; cy
0x1805bf900  xor     edx, edx; hWndInsertAfter
0x1805bf902  mov     [rsp+70h+var_50], eax; cx
0x1805bf906  call    cs:__imp_SetWindowPos
0x1805bf90c  test    rdi, rdi
0x1805bf90f  jz      short loc_1805BF93A
0x1805bf911  mov     rcx, [rbx+60h]; struct CInPlace *
0x1805bf915  call    ?IsInPlaceActive@CInPlace@@SA_NPEBV1@@Z; CInPlace::IsInPlaceActive(CInPlace const *)
0x1805bf91a  test    al, al
0x1805bf91c  jz      short loc_1805BF931
0x1805bf91e  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf925  xor     r8d, r8d; bErase
0x1805bf928  mov     rdx, rdi; hRgn
0x1805bf92b  call    cs:__imp_InvalidateRgn
0x1805bf931  mov     rcx, rdi; ho
0x1805bf934  call    cs:__imp_DeleteObject
0x1805bf93a  xor     eax, eax
0x1805bf93c  mov     rcx, [rbp+var_10]
0x1805bf940  xor     rcx, rsp; StackCookie
0x1805bf943  call    __security_check_cookie
0x1805bf948  mov     rbx, [rsp+70h+arg_18]
0x1805bf950  add     rsp, 70h
0x1805bf954  pop     rdi
0x1805bf955  pop     rsi
0x1805bf956  pop     rbp
0x1805bf957  retn
0x1805bf958  mov     rcx, [rbx+60h]
0x1805bf95c  xor     r8d, r8d; bErase
0x1805bf95f  mov     rdx, rdi; hRgn
0x1805bf962  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf969  call    cs:__imp_GetUpdateRgn
0x1805bf96f  cmp     eax, esi
0x1805bf971  ja      short loc_1805BF9EF
0x1805bf973  mov     rcx, rdi; ho
0x1805bf976  call    cs:__imp_DeleteObject
0x1805bf97c  xor     edi, edi
0x1805bf97e  jmp     loc_1805BF8D5
0x1805bf983  mov     eax, 80070057h
0x1805bf988  jmp     short loc_1805BF93C
0x1805bf98a  mov     eax, [rdx+8]
0x1805bf98d  cmp     eax, [rdx]
0x1805bf98f  jnz     short loc_1805BF9A2
0x1805bf991  jmp     loc_1805BF7B1
0x1805bf996  mov     eax, [rdx+0Ch]
0x1805bf999  cmp     eax, [rdx+4]
0x1805bf99c  jz      loc_1805BF7BB
0x1805bf9a2  mov     eax, 80004005h
0x1805bf9a7  jmp     short loc_1805BF93C
0x1805bf9a9  mov     edx, 4; dx
0x1805bf9ae  lea     rcx, [rbp+rcDst]; lprc
0x1805bf9b2  mov     r8d, edx; dy
0x1805bf9b5  call    cs:__imp_InflateRect
0x1805bf9bb  jmp     loc_1805BF847
0x1805bf9c0  cmp     byte ptr [rcx+0A1h], 0
0x1805bf9c7  jz      loc_1805BF8BC
0x1805bf9cd  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf9d4  mov     r8d, esi; bRedraw
0x1805bf9d7  xor     edx, edx; hRgn
0x1805bf9d9  call    cs:__imp_SetWindowRgn
0x1805bf9df  mov     rax, [rbx+60h]
0x1805bf9e3  mov     byte ptr [rax+0A1h], 0
0x1805bf9ea  jmp     loc_1805BF8BC
0x1805bf9ef  mov     rcx, [rbx+60h]
0x1805bf9f3  mov     rdx, rdi; hRgn
0x1805bf9f6  mov     rcx, [rcx+0A8h]; hWnd
0x1805bf9fd  call    cs:__imp_ValidateRgn
0x1805bfa03  jmp     loc_1805BF8D5
0x1805bfa08  mov     eax, 8000FFFFh
0x1805bfa0d  jmp     loc_1805BF93C
```
