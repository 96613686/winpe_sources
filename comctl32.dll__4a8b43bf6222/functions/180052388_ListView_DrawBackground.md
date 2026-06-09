# ListView_DrawBackground

- ea: `0x180052388`
- end: `0x1800526a2`
- name: `ListView_DrawBackground`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180055bf8`

## callees

- `0x1800115f0`
- `0x180052388`
- `0x18005a274`
- `0x180090020`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800523f3`
- `GDI32!DeleteObject` at `0x180052654`
- `GDI32!DeleteObject` at `0x1800523f3`
- `GDI32!DeleteObject` at `0x180052654`
- `GDI32!RectVisible` at `0x1800525c5`
- `GDI32!RectVisible` at `0x18005260a`
- `GDI32!RectVisible` at `0x1800525c5`
- `GDI32!RectVisible` at `0x18005260a`
- `GDI32!IntersectClipRect` at `0x180052415`
- `GDI32!IntersectClipRect` at `0x180052415`
- `GDI32!GetClipBox` at `0x180052422`
- `GDI32!GetClipBox` at `0x180052422`
- `GDI32!SelectClipRgn` at `0x180052646`
- `GDI32!SelectClipRgn` at `0x180052646`
- `GDI32!CreateRectRgnIndirect` at `0x1800523d2`
- `GDI32!CreateRectRgnIndirect` at `0x1800523d2`
- `GDI32!GetClipRgn` at `0x1800523e6`
- `GDI32!GetClipRgn` at `0x1800523e6`
- `GDI32!ExcludeClipRect` at `0x1800525fe`
- `GDI32!ExcludeClipRect` at `0x1800525fe`
- `USER32!GetClientRect` at `0x180052532`
- `USER32!GetClientRect` at `0x180052532`
- `USER32!SendMessageW` at `0x18005263a`
- `USER32!SendMessageW` at `0x180052682`
- `USER32!SendMessageW` at `0x18005263a`
- `USER32!SendMessageW` at `0x180052682`
- `USER32!FillRect` at `0x180052624`
- `USER32!FillRect` at `0x18005266c`
- `USER32!FillRect` at `0x180052624`
- `USER32!FillRect` at `0x18005266c`

## pseudocode

```c
int __fastcall ListView_DrawBackground(__int64 a1, HDC a2, const RECT *a3)
{
  bool v3; // zf
  HRGN RectRgnIndirect; // rax
  HRGN v8; // r14
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 *v13; // rcx
  __int64 v14; // rax
  LONG bottom; // eax
  LONG right; // r9d
  LONG top; // r8d
  int left; // edx
  HWND v19; // rcx
  int v20; // eax
  LONG v21; // r8d
  LONG v22; // r9d
  int v23; // edx
  int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  LONG v27; // eax
  LONG v28; // ecx
  int result; // eax
  int v30; // [rsp+30h] [rbp-50h] BYREF
  int v31; // [rsp+34h] [rbp-4Ch]
  __int64 v32; // [rsp+38h] [rbp-48h] BYREF
  int v33; // [rsp+40h] [rbp-40h] BYREF
  RECT v34; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT rect; // [rsp+68h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a1 + 560) == 0;
  rect = 0;
  if ( v3 || (*(_BYTE *)(a1 + 56) & 0x20) == 0 )
  {
    if ( *(_DWORD *)(a1 + 96) == -1 )
      return SendMessageW(*(HWND *)(a1 + 8), 0x14u, (WPARAM)a2, 0);
    else
      return FillRect(a2, a3, *(HBRUSH *)(a1 + 112));
  }
  RectRgnIndirect = CreateRectRgnIndirect(a3);
  v8 = RectRgnIndirect;
  if ( RectRgnIndirect && GetClipRgn(a2, RectRgnIndirect) <= 0 )
  {
    DeleteObject(v8);
    v8 = 0;
  }
  if ( a3 )
    IntersectClipRect(a2, a3->left, a3->top, a3->right, a3->bottom);
  GetClipBox(a2, &rect);
  if ( !*(_QWORD *)(a1 + 560) || (*(_BYTE *)(a1 + 56) & 0x20) == 0 )
    goto LABEL_26;
  v9 = *(_DWORD *)(a1 + 16) & 3;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  Rect = 0;
  v10 = v9 - 1;
  if ( !v10 )
  {
    v30 = -*(_DWORD *)(a1 + 456);
    v11 = *(_DWORD *)(a1 + 448) - *(_DWORD *)(a1 + 460);
    goto LABEL_15;
  }
  if ( v10 != 2 )
  {
    v30 = -*(_DWORD *)(a1 + 296);
    v11 = -*(_DWORD *)(a1 + 300);
LABEL_15:
    v31 = v11;
    goto LABEL_16;
  }
  v12 = -*(_DWORD *)(a1 + 248);
  v31 = 0;
  v30 = v12;
LABEL_16:
  ListView_Realize(a1, a2, 1);
  v13 = *(__int64 **)(a1 + 560);
  v14 = *v13;
  if ( (*(_BYTE *)(a1 + 568) & 0x10) != 0 )
  {
    (*(void (__fastcall **)(__int64 *, HDC, int *, const RECT *, _QWORD))(v14 + 88))(v13, a2, &v30, a3, 0);
    bottom = a3->bottom;
    right = a3->right;
    top = a3->top;
    left = a3->left;
  }
  else
  {
    (*(void (__fastcall **)(__int64 *, int *, __int64 *, _QWORD))(v14 + 64))(v13, &v33, &v32, 0);
    v19 = *(HWND *)a1;
    *(_QWORD *)&v34.right = v32;
    *(_QWORD *)&v34.left = 0;
    GetClientRect(v19, &Rect);
    v20 = *(_DWORD *)(a1 + 592);
    v21 = v34.left;
    v22 = v34.right;
    if ( v20 )
    {
      v23 = v20 * (Rect.right - (int)v32) / 100;
      v21 = v23 + v34.left;
      v22 = v23 + v34.right;
    }
    v24 = *(_DWORD *)(a1 + 596);
    if ( v24 )
    {
      v25 = (int)((unsigned __int64)(1374389535LL * v24 * (Rect.bottom - HIDWORD(v32))) >> 32) >> 5;
      v26 = (v25 >> 31) + v25;
      v27 = v26 + v34.top;
      v28 = v26 + v34.bottom;
    }
    else
    {
      v28 = v34.bottom;
      v27 = v34.top;
    }
    v34.bottom = v31 + v28;
    v34.left = v30 + v21;
    v34.top = v31 + v27;
    v34.right = v30 + v22;
    if ( !RectVisible(a2, &v34) )
      goto LABEL_26;
    (*(void (__fastcall **)(_QWORD, HDC, RECT *))(**(_QWORD **)(a1 + 560) + 80LL))(*(_QWORD *)(a1 + 560), a2, &v34);
    bottom = v34.bottom;
    right = v34.right;
    top = v34.top;
    left = v34.left;
  }
  ExcludeClipRect(a2, left, top, right, bottom);
LABEL_26:
  if ( RectVisible(a2, a3) )
  {
    if ( *(_DWORD *)(a1 + 96) == -1 )
      SendMessageW(*(HWND *)(a1 + 8), 0x14u, (WPARAM)a2, 0);
    else
      FillRect(a2, a3, *(HBRUSH *)(a1 + 112));
  }
  result = SelectClipRgn(a2, v8);
  if ( v8 )
    return DeleteObject(v8);
  return result;
}

```

## disassembly

```asm
0x180052388  push    rbp
0x18005238a  push    rbx
0x18005238b  push    rsi
0x18005238c  push    rdi
0x18005238d  push    r14
0x18005238f  mov     rbp, rsp
0x180052392  sub     rsp, 80h
0x180052399  mov     rax, cs:__security_cookie
0x1800523a0  xor     rax, rsp
0x1800523a3  mov     [rbp+var_8], rax
0x1800523a7  cmp     qword ptr [rcx+230h], 0
0x1800523af  xorps   xmm0, xmm0
0x1800523b2  movups  xmmword ptr [rbp+rect.left], xmm0
0x1800523b6  mov     rsi, r8
0x1800523b9  mov     rdi, rdx
0x1800523bc  mov     rbx, rcx
0x1800523bf  jz      loc_18005265C
0x1800523c5  test    byte ptr [rcx+38h], 20h
0x1800523c9  jz      loc_18005265C
0x1800523cf  mov     rcx, r8; lprect
0x1800523d2  call    cs:__imp_CreateRectRgnIndirect
0x1800523d8  mov     r14, rax
0x1800523db  test    rax, rax
0x1800523de  jz      short loc_1800523FC
0x1800523e0  mov     rdx, rax; hrgn
0x1800523e3  mov     rcx, rdi; hdc
0x1800523e6  call    cs:__imp_GetClipRgn
0x1800523ec  test    eax, eax
0x1800523ee  jg      short loc_1800523FC
0x1800523f0  mov     rcx, r14; ho
0x1800523f3  call    cs:__imp_DeleteObject
0x1800523f9  xor     r14d, r14d
0x1800523fc  test    rsi, rsi
0x1800523ff  jz      short loc_18005241B
0x180052401  mov     eax, [rsi+0Ch]
0x180052404  mov     rcx, rdi; hdc
0x180052407  mov     r9d, [rsi+8]; right
0x18005240b  mov     r8d, [rsi+4]; top
0x18005240f  mov     edx, [rsi]; left
0x180052411  mov     [rsp+80h+bottom], eax; bottom
0x180052415  call    cs:__imp_IntersectClipRect
0x18005241b  lea     rdx, [rbp+rect]; lprect
0x18005241f  mov     rcx, rdi; hdc
0x180052422  call    cs:__imp_GetClipBox
0x180052428  cmp     qword ptr [rbx+230h], 0
0x180052430  jz      loc_180052604
0x180052436  test    byte ptr [rbx+38h], 20h
0x18005243a  jz      loc_180052604
0x180052440  mov     eax, [rbx+10h]
0x180052443  xorps   xmm0, xmm0
0x180052446  and     eax, 3
0x180052449  mov     [rbp+var_40], 0
0x180052450  mov     [rbp+var_48], 0
0x180052458  xorps   xmm1, xmm1
0x18005245b  movups  xmmword ptr [rbp+var_38.left], xmm0
0x18005245f  movups  xmmword ptr [rbp+Rect.left], xmm1
0x180052463  sub     eax, 1
0x180052466  jz      short loc_180052496
0x180052468  cmp     eax, 2
0x18005246b  jz      short loc_180052482
0x18005246d  mov     eax, [rbx+128h]
0x180052473  neg     eax
0x180052475  mov     [rbp+var_50], eax
0x180052478  mov     eax, [rbx+12Ch]
0x18005247e  neg     eax
0x180052480  jmp     short loc_1800524AD
0x180052482  mov     eax, [rbx+0F8h]
0x180052488  neg     eax
0x18005248a  mov     [rbp+var_4C], 0
0x180052491  mov     [rbp+var_50], eax
0x180052494  jmp     short loc_1800524B0
0x180052496  mov     eax, [rbx+1C8h]
0x18005249c  neg     eax
0x18005249e  mov     [rbp+var_50], eax
0x1800524a1  mov     eax, [rbx+1C0h]
0x1800524a7  sub     eax, [rbx+1CCh]
0x1800524ad  mov     [rbp+var_4C], eax
0x1800524b0  xor     r9d, r9d
0x1800524b3  mov     rdx, rdi
0x1800524b6  mov     rcx, rbx
0x1800524b9  lea     r8d, [r9+1]
0x1800524bd  call    ListView_Realize
0x1800524c2  test    byte ptr [rbx+238h], 10h
0x1800524c9  mov     rcx, [rbx+230h]
0x1800524d0  mov     rax, [rcx]
0x1800524d3  jz      short loc_180052503
0x1800524d5  mov     rax, [rax+58h]
0x1800524d9  lea     r8, [rbp+var_50]
0x1800524dd  mov     r9, rsi
0x1800524e0  mov     qword ptr [rsp+80h+bottom], 0
0x1800524e9  mov     rdx, rdi
0x1800524ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524f1  mov     eax, [rsi+0Ch]
0x1800524f4  mov     r9d, [rsi+8]
0x1800524f8  mov     r8d, [rsi+4]
0x1800524fc  mov     edx, [rsi]
0x1800524fe  jmp     loc_1800525F7
0x180052503  mov     rax, [rax+40h]
0x180052507  lea     r8, [rbp+var_48]
0x18005250b  xor     r9d, r9d
0x18005250e  lea     rdx, [rbp+var_40]
0x180052512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052517  mov     eax, dword ptr [rbp+var_48]
0x18005251a  lea     rdx, [rbp+Rect]; lpRect
0x18005251e  mov     rcx, [rbx]; hWnd
0x180052521  mov     [rbp+var_38.right], eax
0x180052524  mov     eax, dword ptr [rbp+var_48+4]
0x180052527  mov     [rbp+var_38.bottom], eax
0x18005252a  mov     qword ptr [rbp+var_38.left], 0
0x180052532  call    cs:__imp_GetClientRect
0x180052538  mov     eax, [rbx+250h]
0x18005253e  mov     r10d, 51EB851Fh
0x180052544  mov     r8d, [rbp+var_38.left]
0x180052548  mov     r9d, [rbp+var_38.right]
0x18005254c  test    eax, eax
0x18005254e  jz      short loc_18005256E
0x180052550  mov     ecx, [rbp+Rect.right]
0x180052553  sub     ecx, dword ptr [rbp+var_48]
0x180052556  imul    ecx, eax
0x180052559  mov     eax, r10d
0x18005255c  imul    ecx
0x18005255e  sar     edx, 5
0x180052561  mov     eax, edx
0x180052563  shr     eax, 1Fh
0x180052566  add     edx, eax
0x180052568  add     r8d, edx
0x18005256b  add     r9d, edx
0x18005256e  mov     edx, [rbx+254h]
0x180052574  test    edx, edx
0x180052576  jz      short loc_18005259C
0x180052578  mov     ecx, [rbp+Rect.bottom]
0x18005257b  mov     eax, r10d
0x18005257e  sub     ecx, dword ptr [rbp+var_48+4]
0x180052581  imul    ecx, edx
0x180052584  imul    ecx
0x180052586  mov     ecx, [rbp+var_38.bottom]
0x180052589  sar     edx, 5
0x18005258c  mov     eax, edx
0x18005258e  shr     eax, 1Fh
0x180052591  add     edx, eax
0x180052593  mov     eax, [rbp+var_38.top]
0x180052596  add     eax, edx
0x180052598  add     ecx, edx
0x18005259a  jmp     short loc_1800525A2
0x18005259c  mov     ecx, [rbp+var_38.bottom]
0x18005259f  mov     eax, [rbp+var_38.top]
0x1800525a2  add     ecx, [rbp+var_4C]
0x1800525a5  lea     rdx, [rbp+var_38]; lprect
0x1800525a9  add     r8d, [rbp+var_50]
0x1800525ad  add     eax, [rbp+var_4C]
0x1800525b0  add     r9d, [rbp+var_50]
0x1800525b4  mov     [rbp+var_38.bottom], ecx
0x1800525b7  mov     rcx, rdi; hdc
0x1800525ba  mov     [rbp+var_38.left], r8d
0x1800525be  mov     [rbp+var_38.top], eax
0x1800525c1  mov     [rbp+var_38.right], r9d
0x1800525c5  call    cs:__imp_RectVisible
0x1800525cb  test    eax, eax
0x1800525cd  jz      short loc_180052604
0x1800525cf  mov     rcx, [rbx+230h]
0x1800525d6  lea     r8, [rbp+var_38]
0x1800525da  mov     rdx, rdi
0x1800525dd  mov     rax, [rcx]
0x1800525e0  mov     rax, [rax+50h]
0x1800525e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800525e9  mov     eax, [rbp+var_38.bottom]
0x1800525ec  mov     r9d, [rbp+var_38.right]; right
0x1800525f0  mov     r8d, [rbp+var_38.top]; top
0x1800525f4  mov     edx, [rbp+var_38.left]; left
0x1800525f7  mov     rcx, rdi; hdc
0x1800525fa  mov     [rsp+80h+bottom], eax; bottom
0x1800525fe  call    cs:__imp_ExcludeClipRect
0x180052604  mov     rdx, rsi; lprect
0x180052607  mov     rcx, rdi; hdc
0x18005260a  call    cs:__imp_RectVisible
0x180052610  test    eax, eax
0x180052612  jz      short loc_180052640
0x180052614  cmp     dword ptr [rbx+60h], 0FFFFFFFFh
0x180052618  jz      short loc_18005262C
0x18005261a  mov     r8, [rbx+70h]; hbr
0x18005261e  mov     rdx, rsi; lprc
0x180052621  mov     rcx, rdi; hDC
0x180052624  call    cs:__imp_FillRect
0x18005262a  jmp     short loc_180052640
0x18005262c  mov     rcx, [rbx+8]; hWnd
0x180052630  xor     r9d, r9d; lParam
0x180052633  mov     r8, rdi; wParam
0x180052636  lea     edx, [r9+14h]; Msg
0x18005263a  call    cs:__imp_SendMessageW
0x180052640  mov     rdx, r14; hrgn
0x180052643  mov     rcx, rdi; hdc
0x180052646  call    cs:__imp_SelectClipRgn
0x18005264c  test    r14, r14
0x18005264f  jz      short loc_180052688
0x180052651  mov     rcx, r14; ho
0x180052654  call    cs:__imp_DeleteObject
0x18005265a  jmp     short loc_180052688
0x18005265c  cmp     dword ptr [rcx+60h], 0FFFFFFFFh
0x180052660  jz      short loc_180052674
0x180052662  mov     r8, [rcx+70h]; hbr
0x180052666  mov     rdx, rsi; lprc
0x180052669  mov     rcx, rdi; hDC
0x18005266c  call    cs:__imp_FillRect
0x180052672  jmp     short loc_180052688
0x180052674  mov     rcx, [rcx+8]; hWnd
0x180052678  xor     r9d, r9d; lParam
0x18005267b  mov     r8, rdi; wParam
0x18005267e  lea     edx, [r9+14h]; Msg
0x180052682  call    cs:__imp_SendMessageW
0x180052688  mov     rcx, [rbp+var_8]
0x18005268c  xor     rcx, rsp; StackCookie
0x18005268f  call    __security_check_cookie
0x180052694  add     rsp, 80h
0x18005269b  pop     r14
0x18005269d  pop     rdi
0x18005269e  pop     rsi
0x18005269f  pop     rbx
0x1800526a0  pop     rbp
0x1800526a1  retn
```
