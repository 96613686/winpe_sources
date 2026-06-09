# CHtmlHelpControl::SetObjectRects(tagRECT const *,tagRECT const *)

- ea: `0x180033390`
- end: `0x1800334f7`
- name: `?SetObjectRects@CHtmlHelpControl@@UEAAJPEBUtagRECT@@0@Z`
- size: `359`
- prototype: `int(CHtmlHelpControl *__hidden this, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180033390`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!CopyRect` at `0x18003349a`
- `USER32!CopyRect` at `0x1800334da`
- `USER32!CopyRect` at `0x18003349a`
- `USER32!CopyRect` at `0x1800334da`
- `USER32!IntersectRect` at `0x1800333d9`
- `USER32!IntersectRect` at `0x1800333d9`
- `USER32!EqualRect` at `0x1800333eb`
- `USER32!EqualRect` at `0x1800333eb`
- `USER32!OffsetRect` at `0x180033405`
- `USER32!OffsetRect` at `0x180033405`
- `USER32!SetWindowRgn` at `0x180033426`
- `USER32!SetWindowRgn` at `0x180033446`
- `USER32!SetWindowRgn` at `0x180033426`
- `USER32!SetWindowRgn` at `0x180033446`
- `USER32!SetWindowPos` at `0x18003348a`
- `USER32!SetWindowPos` at `0x18003348a`
- `GDI32!CreateRectRgnIndirect` at `0x180033410`
- `GDI32!CreateRectRgnIndirect` at `0x180033410`

## pseudocode

```c
__int64 __fastcall CHtmlHelpControl::SetObjectRects(
        CHtmlHelpControl *this,
        const struct tagRECT *a2,
        const struct tagRECT *a3)
{
  int v5; // esi
  HRGN v6; // rax
  int v7; // ecx
  int cy; // eax
  __int64 v9; // rcx
  struct tagRECT rcDst; // [rsp+40h] [rbp-38h] BYREF

  if ( !*((_QWORD *)this + 20) )
  {
    CopyRect((LPRECT)this + 9, a2);
    return 0;
  }
  v5 = (*((_DWORD *)this + 53) >> 4) & 1;
  if ( a3 && (rcDst = 0, IntersectRect(&rcDst, a2, a3)) && !EqualRect(&rcDst, a2) )
  {
    OffsetRect(&rcDst, -a2->left, -a2->top);
    v6 = CreateRectRgnIndirect(&rcDst);
    SetWindowRgn(*((HWND *)this + 20), v6, 1);
    *((_DWORD *)this + 53) |= 0x10u;
  }
  else if ( v5 )
  {
    SetWindowRgn(*((HWND *)this + 20), 0, 1);
    *((_DWORD *)this + 53) &= ~0x10u;
  }
  v7 = a2->right - a2->left;
  *((_DWORD *)this + 34) = v7;
  cy = a2->bottom - a2->top;
  *((_DWORD *)this + 35) = cy;
  SetWindowPos(*((HWND *)this + 20), 0, a2->left, a2->top, v7, cy, 0x14u);
  CopyRect((LPRECT)this + 9, a2);
  if ( *((_DWORD *)this + 74) == 2 )
  {
    v9 = *((_QWORD *)this + 67);
  }
  else
  {
    if ( *((_DWORD *)this + 74) != 3 )
      return 0;
    v9 = *((_QWORD *)this + 68);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  return 0;
}

```

## disassembly

```asm
0x180033390  push    rbx
0x180033392  push    rsi
0x180033393  push    rdi
0x180033394  sub     rsp, 60h
0x180033398  mov     rax, cs:__security_cookie
0x18003339f  xor     rax, rsp
0x1800333a2  mov     [rsp+78h+var_28], rax
0x1800333a7  cmp     qword ptr [rcx+0A0h], 0
0x1800333af  mov     rdi, rdx
0x1800333b2  mov     rbx, rcx
0x1800333b5  jz      loc_1800334D3
0x1800333bb  mov     esi, [rcx+0D4h]
0x1800333c1  shr     esi, 4
0x1800333c4  and     esi, 1
0x1800333c7  test    r8, r8
0x1800333ca  jz      short loc_180033435
0x1800333cc  xorps   xmm0, xmm0
0x1800333cf  lea     rcx, [rsp+78h+rcDst]; lprcDst
0x1800333d4  movups  xmmword ptr [rsp+78h+rcDst.left], xmm0
0x1800333d9  call    cs:__imp_IntersectRect
0x1800333df  test    eax, eax
0x1800333e1  jz      short loc_180033435
0x1800333e3  mov     rdx, rdi; lprc2
0x1800333e6  lea     rcx, [rsp+78h+rcDst]; lprc1
0x1800333eb  call    cs:__imp_EqualRect
0x1800333f1  test    eax, eax
0x1800333f3  jnz     short loc_180033435
0x1800333f5  mov     r8d, [rdi+4]
0x1800333f9  lea     rcx, [rsp+78h+rcDst]; lprc
0x1800333fe  mov     edx, [rdi]
0x180033400  neg     r8d; dy
0x180033403  neg     edx; dx
0x180033405  call    cs:__imp_OffsetRect
0x18003340b  lea     rcx, [rsp+78h+rcDst]; lprect
0x180033410  call    cs:__imp_CreateRectRgnIndirect
0x180033416  mov     rcx, [rbx+0A0h]; hWnd
0x18003341d  mov     r8d, 1; bRedraw
0x180033423  mov     rdx, rax; hRgn
0x180033426  call    cs:__imp_SetWindowRgn
0x18003342c  or      dword ptr [rbx+0D4h], 10h
0x180033433  jmp     short loc_180033453
0x180033435  test    esi, esi
0x180033437  jz      short loc_180033453
0x180033439  mov     rcx, [rbx+0A0h]; hWnd
0x180033440  xor     edx, edx; hRgn
0x180033442  lea     r8d, [rdx+1]; bRedraw
0x180033446  call    cs:__imp_SetWindowRgn
0x18003344c  and     dword ptr [rbx+0D4h], 0FFFFFFEFh
0x180033453  mov     ecx, [rdi+8]
0x180033456  xor     edx, edx; hWndInsertAfter
0x180033458  sub     ecx, [rdi]
0x18003345a  mov     [rbx+88h], ecx
0x180033460  mov     eax, [rdi+0Ch]
0x180033463  sub     eax, [rdi+4]
0x180033466  mov     [rbx+8Ch], eax
0x18003346c  mov     r9d, [rdi+4]; Y
0x180033470  mov     r8d, [rdi]; X
0x180033473  mov     [rsp+78h+uFlags], 14h; uFlags
0x18003347b  mov     [rsp+78h+cy], eax; cy
0x18003347f  mov     [rsp+78h+var_58], ecx; cx
0x180033483  mov     rcx, [rbx+0A0h]; hWnd
0x18003348a  call    cs:__imp_SetWindowPos
0x180033490  lea     rcx, [rbx+90h]; lprcDst
0x180033497  mov     rdx, rdi; lprcSrc
0x18003349a  call    cs:__imp_CopyRect
0x1800334a0  mov     ecx, [rbx+128h]
0x1800334a6  sub     ecx, 2
0x1800334a9  jz      short loc_1800334B9
0x1800334ab  cmp     ecx, 1
0x1800334ae  jnz     short loc_1800334E0
0x1800334b0  mov     rcx, [rbx+220h]
0x1800334b7  jmp     short loc_1800334C0
0x1800334b9  mov     rcx, [rbx+218h]
0x1800334c0  test    rcx, rcx
0x1800334c3  jz      short loc_1800334E0
0x1800334c5  mov     rax, [rcx]
0x1800334c8  mov     rax, [rax+18h]
0x1800334cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334d1  jmp     short loc_1800334E0
0x1800334d3  add     rcx, 90h; lprcDst
0x1800334da  call    cs:__imp_CopyRect
0x1800334e0  xor     eax, eax
0x1800334e2  mov     rcx, [rsp+78h+var_28]
0x1800334e7  xor     rcx, rsp; StackCookie
0x1800334ea  call    __security_check_cookie
0x1800334ef  add     rsp, 60h
0x1800334f3  pop     rdi
0x1800334f4  pop     rsi
0x1800334f5  pop     rbx
0x1800334f6  retn
```
