# ListView_RecalcRegion

- ea: `0x18005a314`
- end: `0x18005a9dc`
- name: `ListView_RecalcRegion`
- size: `1736`
- prototype: `__int64 __fastcall(int)`
- caller_count: `10`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800529fc`
- `0x180055608`
- `0x180056c24`
- `0x180058f1c`
- `0x180059798`
- `0x1800598d8`
- `0x18005a9e4`
- `0x1800733e0`
- `0x180075c34`
- `0x180076674`

## callees

- `0x1800115f0`
- `0x180052cf8`
- `0x180054598`
- `0x180055de0`
- `0x18005a314`
- `0x180085a10`
- `0x180085eb0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18005a491`
- `GDI32!CreateCompatibleDC` at `0x18005a491`
- `GDI32!SelectObject` at `0x18005a538`
- `GDI32!SelectObject` at `0x18005a98d`
- `GDI32!SelectObject` at `0x18005a538`
- `GDI32!SelectObject` at `0x18005a98d`
- `GDI32!DeleteObject` at `0x18005a3e0`
- `GDI32!DeleteObject` at `0x18005a604`
- `GDI32!DeleteObject` at `0x18005a677`
- `GDI32!DeleteObject` at `0x18005a8b0`
- `GDI32!DeleteObject` at `0x18005a904`
- `GDI32!DeleteObject` at `0x18005a956`
- `GDI32!DeleteObject` at `0x18005a964`
- `GDI32!DeleteObject` at `0x18005a996`
- `GDI32!DeleteObject` at `0x18005a3e0`
- `GDI32!DeleteObject` at `0x18005a604`
- `GDI32!DeleteObject` at `0x18005a677`
- `GDI32!DeleteObject` at `0x18005a8b0`
- `GDI32!DeleteObject` at `0x18005a904`
- `GDI32!DeleteObject` at `0x18005a956`
- `GDI32!DeleteObject` at `0x18005a964`
- `GDI32!DeleteObject` at `0x18005a996`
- `GDI32!CreateRectRgn` at `0x18005a573`
- `GDI32!CreateRectRgn` at `0x18005a882`
- `GDI32!CreateRectRgn` at `0x18005a573`
- `GDI32!CreateRectRgn` at `0x18005a882`
- `GDI32!GetObjectW` at `0x18005a4e2`
- `GDI32!GetObjectW` at `0x18005a4e2`
- `GDI32!DeleteDC` at `0x18005a99f`
- `GDI32!DeleteDC` at `0x18005a99f`
- `GDI32!PatBlt` at `0x18005a563`
- `GDI32!PatBlt` at `0x18005a563`
- `GDI32!CreateBitmap` at `0x18005a4be`
- `GDI32!CreateBitmap` at `0x18005a4be`
- `GDI32!GetBitmapBits` at `0x18005a780`
- `GDI32!GetBitmapBits` at `0x18005a780`
- `GDI32!CombineRgn` at `0x18005a66c`
- `GDI32!CombineRgn` at `0x18005a8a4`
- `GDI32!CombineRgn` at `0x18005a925`
- `GDI32!CombineRgn` at `0x18005a66c`
- `GDI32!CombineRgn` at `0x18005a8a4`
- `GDI32!CombineRgn` at `0x18005a925`
- `GDI32!CreateRectRgnIndirect` at `0x18005a64b`
- `GDI32!CreateRectRgnIndirect` at `0x18005a6ec`
- `GDI32!CreateRectRgnIndirect` at `0x18005a861`
- `GDI32!CreateRectRgnIndirect` at `0x18005a64b`
- `GDI32!CreateRectRgnIndirect` at `0x18005a6ec`
- `GDI32!CreateRectRgnIndirect` at `0x18005a861`
- `GDI32!OffsetRgn` at `0x18005a6b7`
- `GDI32!OffsetRgn` at `0x18005a6b7`
- `KERNEL32!GlobalAlloc` at `0x18005a51e`
- `KERNEL32!GlobalAlloc` at `0x18005a51e`
- `KERNEL32!GlobalFree` at `0x18005a97c`
- `KERNEL32!GlobalFree` at `0x18005a97c`
- `USER32!CopyRect` at `0x18005a695`
- `USER32!CopyRect` at `0x18005a695`
- `USER32!InflateRect` at `0x18005a6e2`
- `USER32!InflateRect` at `0x18005a6e2`
- `USER32!EqualRect` at `0x18005a421`
- `USER32!EqualRect` at `0x18005a421`
- `USER32!OffsetRect` at `0x18005a857`
- `USER32!OffsetRect` at `0x18005a857`
- `USER32!SetWindowRgn` at `0x18005a9b1`
- `USER32!SetWindowRgn` at `0x18005a9b1`

## pseudocode

```c
void __fastcall ListView_RecalcRegion(__int64 a1, int a2)
{
  bool v2; // zf
  int v4; // ecx
  HGDIOBJ v5; // r15
  HRGN v6; // r13
  int v7; // esi
  __int64 v8; // rbx
  void **v9; // r14
  void *v10; // rcx
  int v11; // ebx
  int v12; // esi
  HDC v13; // r12
  HBITMAP Bitmap; // rax
  HBITMAP v15; // r14
  unsigned __int64 v16; // rdx
  int v17; // r12d
  __int64 v18; // rsi
  char *v19; // rcx
  RECT *p_rc2; // rcx
  HRGN RectRgnIndirect; // rax
  HRGN v22; // r14
  int v23; // ebx
  HRGN v24; // rcx
  HRGN v25; // rdx
  HRGN v26; // rbx
  int v27; // r15d
  int v28; // eax
  LONG v29; // r13d
  int v30; // r10d
  int v31; // r8d
  LONG v32; // r14d
  int v33; // edx
  __int64 v34; // rax
  LONG v35; // eax
  LONG v36; // r8d
  int v37; // edx
  HRGN v38; // r15
  int v39; // r12d
  char *v40; // rcx
  int nWidth; // [rsp+30h] [rbp-D0h] BYREF
  int cy; // [rsp+34h] [rbp-CCh] BYREF
  int v43; // [rsp+38h] [rbp-C8h]
  int v44; // [rsp+3Ch] [rbp-C4h]
  int v45; // [rsp+40h] [rbp-C0h]
  HRGN RectRgn; // [rsp+48h] [rbp-B8h]
  HDC hdcDst; // [rsp+50h] [rbp-B0h]
  LPVOID lpvBits; // [rsp+58h] [rbp-A8h]
  HGDIOBJ v49; // [rsp+60h] [rbp-A0h]
  HBITMAP hbit; // [rsp+68h] [rbp-98h]
  LONG cb[2]; // [rsp+70h] [rbp-90h]
  _OWORD pv[2]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v53[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h]
  __int128 v55; // [rsp+A8h] [rbp-58h]
  __int128 v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  RECT rc2; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+E0h] [rbp-20h] BYREF

  v2 = (*(_DWORD *)(a1 + 76) & 0x200) == 0;
  rc2 = 0;
  rc = 0;
  memset(pv, 0, sizeof(pv));
  if ( v2 )
    return;
  v4 = *(_DWORD *)(a1 + 72);
  if ( (v4 & 0x10012) != 0x12 )
    return;
  v5 = 0;
  v6 = 0;
  *(_DWORD *)(a1 + 72) = v4 | 0x10000;
  if ( *(int *)(a1 + 512) > 0 )
  {
    nWidth = 0;
    cy = 0;
    if ( !a2 )
    {
      v7 = 0;
      while ( 1 )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) + 8LL * v7);
        v9 = (void **)(v8 + 40);
        if ( !(unsigned int)ListView_IsItemVisible(a1, (unsigned int)v7) )
        {
          v10 = *v9;
          if ( (char *)*v9 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
            goto LABEL_13;
          *(_DWORD *)(v8 + 48) = 0x7FFFFFFF;
          *(_DWORD *)(v8 + 52) = 0x7FFFFFFF;
          DeleteObject(v10);
          *v9 = 0;
        }
        ListView_GetRects(a1, v7, 0, (int)&rc2, 0, 0);
        if ( *(_DWORD *)(v8 + 8) != *(_DWORD *)(v8 + 48)
          || *(_DWORD *)(v8 + 12) != *(_DWORD *)(v8 + 52)
          || !*v9
          || !EqualRect((const RECT *)(v8 + 56), &rc2) )
        {
          break;
        }
LABEL_13:
        if ( ++v7 >= *(_DWORD *)(a1 + 512) )
          goto LABEL_79;
      }
    }
    ListView_GetRects(a1, 0, (int)&rc, 0, 0, 0);
    ImageList_GetIconSize(*(HIMAGELIST *)(a1 + 272), &nWidth, &cy);
    v11 = rc.right - rc.left - nWidth;
    v12 = rc.bottom - rc.top - cy;
    nWidth = rc.right - rc.left;
    cy = rc.bottom - rc.top;
    hdcDst = CreateCompatibleDC(0);
    v13 = hdcDst;
    if ( hdcDst )
    {
      Bitmap = CreateBitmap(nWidth, cy, 1u, 1u, 0);
      hbit = Bitmap;
      v15 = Bitmap;
      if ( !Bitmap )
      {
LABEL_77:
        DeleteDC(v13);
        goto LABEL_78;
      }
      GetObjectW(Bitmap, 32, pv);
      if ( pv[0] < 0
        || SDWORD2(pv[0]) < 0
        || (v16 = HIDWORD(pv[0]) * (unsigned __int64)DWORD2(pv[0]), *(_QWORD *)cb = v16, v16 > 0xFFFFFFFF)
        || (lpvBits = GlobalAlloc(0x40u, (unsigned int)v16)) == 0 )
      {
LABEL_76:
        SelectObject(v13, v5);
        DeleteObject(v15);
        goto LABEL_77;
      }
      v5 = SelectObject(v13, v15);
      v49 = v5;
      PatBlt(v13, 0, 0, nWidth, cy, 0xFF0062u);
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v6 = RectRgn;
      if ( !RectRgn )
      {
LABEL_75:
        GlobalFree(lpvBits);
        v15 = hbit;
        goto LABEL_76;
      }
      v17 = 0;
      v45 = 0;
      v43 = v11 / 2;
      v44 = v12 / 2;
      if ( *(int *)(a1 + 512) <= 0 )
      {
LABEL_74:
        v13 = hdcDst;
        goto LABEL_75;
      }
      while ( 1 )
      {
        v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) + 8LL * v17);
        if ( *(_DWORD *)(v18 + 12) == 0x7FFFFFFF )
          goto LABEL_67;
        if ( !(unsigned int)ListView_IsItemVisible(a1, (unsigned int)v17) )
        {
          v19 = *(char **)(v18 + 40);
          if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            *(_DWORD *)(v18 + 48) = 0x7FFFFFFF;
            *(_DWORD *)(v18 + 52) = 0x7FFFFFFF;
            DeleteObject(v19);
            *(_QWORD *)(v18 + 40) = -1;
          }
          goto LABEL_67;
        }
        ListView_GetRects(a1, v17, (int)&rc, (int)&rc2, 0, 0);
        p_rc2 = &rc2;
        if ( v17 == *(_DWORD *)(a1 + 336) )
          p_rc2 = (RECT *)(v18 + 56);
        RectRgnIndirect = CreateRectRgnIndirect(p_rc2);
        v22 = RectRgnIndirect;
        if ( !RectRgnIndirect || (v23 = CombineRgn(v6, RectRgnIndirect, v6, 2), DeleteObject(v22), !v23) )
        {
LABEL_72:
          DeleteObject(v6);
          v6 = 0;
          goto LABEL_73;
        }
        if ( *(_DWORD *)(a1 + 336) != v17 )
          CopyRect((LPRECT)(v18 + 56), &rc2);
        v24 = *(HRGN *)(v18 + 40);
        if ( (unsigned __int64)v24 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          OffsetRgn(v24, *(_DWORD *)(v18 + 8) - *(_DWORD *)(v18 + 48), *(_DWORD *)(v18 + 12) - *(_DWORD *)(v18 + 52));
          v25 = *(HRGN *)(v18 + 40);
          goto LABEL_66;
        }
        if ( g_fSlowMachine )
        {
          rc.bottom = rc2.top;
          InflateRect(&rc, -v43, 0);
          v26 = CreateRectRgnIndirect(&rc);
          goto LABEL_62;
        }
        v27 = 0;
        v26 = 0;
        if ( *(_WORD *)(v18 + 16) == 0xFFFF )
        {
          v57 = 0;
          v53[1] = v17;
          v54 = 0;
          v56 = 0;
          v53[0] = 2;
          v55 = 0xFFFFu;
          LODWORD(v56) = 0;
          ListView_OnGetItem(a1, v53);
        }
        ImageList_Draw(
          *(HIMAGELIST *)(a1 + 272),
          *(__int16 *)(v18 + 16),
          hdcDst,
          0,
          0,
          *(_WORD *)(v18 + 28) & 0xF00 | 0x10);
        GetBitmapBits(hbit, cb[0], lpvBits);
        v28 = cy;
        v29 = 0;
        if ( cy <= 0 )
          goto LABEL_67;
        v30 = HIDWORD(pv[0]);
        v31 = nWidth;
        do
        {
          v32 = 0;
          if ( v31 > 0 )
          {
            while ( 1 )
            {
              v33 = 128 >> (v32 % 8);
              v34 = v32 / 8 + v30 * v29;
              if ( v27 )
              {
                if ( ((unsigned __int8)v33 & *((_BYTE *)lpvBits + v34)) == 0 )
                  goto LABEL_58;
              }
              else
              {
                if ( ((unsigned __int8)v33 & *((_BYTE *)lpvBits + v34)) != 0 )
                  goto LABEL_58;
                rc2.left = v32;
                rc2.bottom = v29 + 1;
                rc2.top = v29;
                if ( v32 != v31 - 1 )
                {
                  v27 = 1;
                  goto LABEL_58;
                }
                ++v32;
              }
              v2 = (*(_DWORD *)(a1 + 32) & 0x400000) == 0;
              rc2.right = v32;
              if ( v2 )
              {
                v37 = v43 + rc.left;
              }
              else
              {
                v35 = v31 - v32 - 1;
                v36 = v31 - rc2.left - 1;
                v37 = rc.left - v43;
                rc2.left = v35;
                rc2.right = v36;
              }
              OffsetRect(&rc2, v37, v44 + rc.top);
              v38 = CreateRectRgnIndirect(&rc2);
              if ( !v38
                || (v26 || (v26 = CreateRectRgn(0, 0, 0, 0)) != 0 ? (v39 = CombineRgn(v26, v38, v26, 2)) : (v39 = 0),
                    DeleteObject(v38),
                    !v39) )
              {
                if ( v26 )
                  DeleteObject(v26);
                v6 = RectRgn;
                goto LABEL_72;
              }
              v30 = HIDWORD(pv[0]);
              v27 = 0;
              v31 = nWidth;
LABEL_58:
              if ( ++v32 >= v31 )
              {
                v28 = cy;
                break;
              }
            }
          }
          ++v29;
        }
        while ( v29 < v28 );
        v17 = v45;
        v6 = RectRgn;
LABEL_62:
        if ( v26 )
        {
          v40 = *(char **)(v18 + 40);
          if ( (unsigned __int64)(v40 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            DeleteObject(v40);
          *(_QWORD *)(v18 + 40) = v26;
          v25 = v26;
LABEL_66:
          *(_QWORD *)(v18 + 48) = *(_QWORD *)(v18 + 8);
          if ( !CombineRgn(v6, v25, v6, 2) )
            goto LABEL_72;
        }
LABEL_67:
        v6 = RectRgn;
        v45 = ++v17;
        if ( v17 >= *(_DWORD *)(a1 + 512) )
        {
LABEL_73:
          v5 = v49;
          goto LABEL_74;
        }
      }
    }
  }
LABEL_78:
  SetWindowRgn(*(HWND *)a1, v6, 1);
LABEL_79:
  *(_DWORD *)(a1 + 72) &= ~0x10000u;
}

```

## disassembly

```asm
0x18005a314  push    rbp
0x18005a316  push    rbx
0x18005a317  push    rsi
0x18005a318  push    rdi
0x18005a319  push    r12
0x18005a31b  push    r13
0x18005a31d  push    r14
0x18005a31f  push    r15
0x18005a321  lea     rbp, [rsp-8]
0x18005a326  sub     rsp, 108h
0x18005a32d  mov     rax, cs:__security_cookie
0x18005a334  xor     rax, rsp
0x18005a337  mov     [rbp+40h+var_50], rax
0x18005a33b  test    dword ptr [rcx+4Ch], 200h
0x18005a342  xorps   xmm0, xmm0
0x18005a345  xorps   xmm1, xmm1
0x18005a348  mov     rdi, rcx
0x18005a34b  movups  xmmword ptr [rbp+40h+rc2.left], xmm0
0x18005a34f  movups  xmmword ptr [rbp+40h+rc.left], xmm1
0x18005a353  movups  [rsp+140h+pv], xmm0
0x18005a358  movups  [rbp+40h+var_B8], xmm0
0x18005a35c  jz      loc_18005A9BC
0x18005a362  mov     ecx, [rcx+48h]
0x18005a365  mov     eax, ecx
0x18005a367  and     eax, 10012h
0x18005a36c  cmp     eax, 12h
0x18005a36f  jnz     loc_18005A9BC
0x18005a375  xor     r15d, r15d
0x18005a378  bts     ecx, 10h
0x18005a37c  mov     r13d, r15d
0x18005a37f  mov     [rdi+48h], ecx
0x18005a382  cmp     [rdi+200h], r15d
0x18005a389  jle     loc_18005A9A5
0x18005a38f  mov     [rsp+140h+nWidth], r15d
0x18005a394  mov     r12d, 7FFFFFFFh
0x18005a39a  mov     [rsp+140h+cy], r15d
0x18005a39f  test    edx, edx
0x18005a3a1  jnz     loc_18005A43E
0x18005a3a7  mov     esi, r15d
0x18005a3aa  mov     rax, [rdi+40h]
0x18005a3ae  movsxd  rdx, esi
0x18005a3b1  mov     rcx, [rax+8]
0x18005a3b5  mov     rbx, [rcx+rdx*8]
0x18005a3b9  mov     edx, esi
0x18005a3bb  mov     rcx, rdi
0x18005a3be  lea     r14, [rbx+28h]
0x18005a3c2  call    ListView_IsItemVisible
0x18005a3c7  test    eax, eax
0x18005a3c9  jnz     short loc_18005A3E9
0x18005a3cb  mov     rcx, [r14]; ho
0x18005a3ce  lea     rax, [rcx-1]
0x18005a3d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a3d6  ja      short loc_18005A42B
0x18005a3d8  mov     [rbx+30h], r12d
0x18005a3dc  mov     [rbx+34h], r12d
0x18005a3e0  call    cs:__imp_DeleteObject
0x18005a3e6  mov     [r14], r15
0x18005a3e9  mov     qword ptr [rsp+140h+rop], r15; LPRECT
0x18005a3ee  lea     r9, [rbp+40h+rc2]; int
0x18005a3f2  xor     r8d, r8d; int
0x18005a3f5  mov     [rsp+140h+lpBits], r15; lprcDst
0x18005a3fa  mov     edx, esi; int
0x18005a3fc  mov     rcx, rdi; int
0x18005a3ff  call    ListView_GetRects
0x18005a404  mov     eax, [rbx+30h]
0x18005a407  cmp     [rbx+8], eax
0x18005a40a  jnz     short loc_18005A43E
0x18005a40c  mov     eax, [rbx+34h]
0x18005a40f  cmp     [rbx+0Ch], eax
0x18005a412  jnz     short loc_18005A43E
0x18005a414  cmp     [r14], r15
0x18005a417  jz      short loc_18005A43E
0x18005a419  lea     rcx, [rbx+38h]; lprc1
0x18005a41d  lea     rdx, [rbp+40h+rc2]; lprc2
0x18005a421  call    cs:__imp_EqualRect
0x18005a427  test    eax, eax
0x18005a429  jz      short loc_18005A43E
0x18005a42b  inc     esi
0x18005a42d  cmp     esi, [rdi+200h]
0x18005a433  jl      loc_18005A3AA
0x18005a439  jmp     loc_18005A9B7
0x18005a43e  mov     qword ptr [rsp+140h+rop], r15; LPRECT
0x18005a443  lea     r8, [rbp+40h+rc]; int
0x18005a447  xor     r9d, r9d; int
0x18005a44a  mov     [rsp+140h+lpBits], r15; lprcDst
0x18005a44f  xor     edx, edx; int
0x18005a451  mov     rcx, rdi; int
0x18005a454  call    ListView_GetRects
0x18005a459  mov     rcx, [rdi+110h]; himl
0x18005a460  lea     r8, [rsp+140h+cy]; cy
0x18005a465  lea     rdx, [rsp+140h+nWidth]; cx
0x18005a46a  call    ImageList_GetIconSize
0x18005a46f  mov     ecx, [rbp+40h+rc.right]
0x18005a472  sub     ecx, [rbp+40h+rc.left]
0x18005a475  mov     eax, [rbp+40h+rc.bottom]
0x18005a478  mov     ebx, ecx
0x18005a47a  sub     eax, [rbp+40h+rc.top]
0x18005a47d  sub     ebx, [rsp+140h+nWidth]
0x18005a481  mov     esi, eax
0x18005a483  sub     esi, [rsp+140h+cy]
0x18005a487  mov     [rsp+140h+nWidth], ecx
0x18005a48b  xor     ecx, ecx; hdc
0x18005a48d  mov     [rsp+140h+cy], eax
0x18005a491  call    cs:__imp_CreateCompatibleDC
0x18005a497  mov     [rsp+140h+hdcDst], rax
0x18005a49c  mov     r12, rax
0x18005a49f  test    rax, rax
0x18005a4a2  jz      loc_18005A9A5
0x18005a4a8  mov     edx, [rsp+140h+cy]; nHeight
0x18005a4ac  mov     r9d, 1; nBitCount
0x18005a4b2  mov     ecx, [rsp+140h+nWidth]; nWidth
0x18005a4b6  mov     r8d, r9d; nPlanes
0x18005a4b9  mov     [rsp+140h+lpBits], r15; lpBits
0x18005a4be  call    cs:__imp_CreateBitmap
0x18005a4c4  mov     [rsp+140h+hbit], rax
0x18005a4c9  mov     r14, rax
0x18005a4cc  test    rax, rax
0x18005a4cf  jz      loc_18005A99C
0x18005a4d5  lea     r8, [rsp+140h+pv]; pv
0x18005a4da  mov     edx, 20h ; ' '; c
0x18005a4df  mov     rcx, rax; h
0x18005a4e2  call    cs:__imp_GetObjectW
0x18005a4e8  mov     ecx, dword ptr [rbp+40h+pv+0Ch]
0x18005a4eb  test    ecx, ecx
0x18005a4ed  js      loc_18005A987
0x18005a4f3  mov     eax, dword ptr [rbp+40h+pv+8]
0x18005a4f6  test    eax, eax
0x18005a4f8  js      loc_18005A987
0x18005a4fe  mov     edx, eax
0x18005a500  mov     eax, 0FFFFFFFFh
0x18005a505  imul    rdx, rcx
0x18005a509  mov     qword ptr [rsp+140h+cb], rdx
0x18005a50e  cmp     rdx, rax
0x18005a511  ja      loc_18005A987
0x18005a517  mov     edx, edx; dwBytes
0x18005a519  mov     ecx, 40h ; '@'; uFlags
0x18005a51e  call    cs:__imp_GlobalAlloc
0x18005a524  mov     [rsp+140h+lpvBits], rax
0x18005a529  test    rax, rax
0x18005a52c  jz      loc_18005A987
0x18005a532  mov     rdx, r14; h
0x18005a535  mov     rcx, r12; hdc
0x18005a538  call    cs:__imp_SelectObject
0x18005a53e  mov     r9d, [rsp+140h+nWidth]; w
0x18005a543  xor     r8d, r8d; y
0x18005a546  mov     r15, rax
0x18005a549  mov     [rsp+140h+var_E0], rax
0x18005a54e  mov     eax, [rsp+140h+cy]
0x18005a552  xor     edx, edx; x
0x18005a554  mov     [rsp+140h+rop], 0FF0062h; rop
0x18005a55c  mov     rcx, r12; hdc
0x18005a55f  mov     dword ptr [rsp+140h+lpBits], eax; h
0x18005a563  call    cs:__imp_PatBlt
0x18005a569  xor     r9d, r9d; y2
0x18005a56c  xor     r8d, r8d; x2
0x18005a56f  xor     edx, edx; y1
0x18005a571  xor     ecx, ecx; x1
0x18005a573  call    cs:__imp_CreateRectRgn
0x18005a579  mov     [rsp+140h+var_F8], rax
0x18005a57e  mov     r13, rax
0x18005a581  test    rax, rax
0x18005a584  jz      loc_18005A977
0x18005a58a  xor     r12d, r12d
0x18005a58d  mov     eax, ebx
0x18005a58f  cdq
0x18005a590  mov     [rsp+140h+var_100], r12d
0x18005a595  sub     eax, edx
0x18005a597  sar     eax, 1
0x18005a599  mov     [rsp+140h+var_108], eax
0x18005a59d  mov     eax, esi
0x18005a59f  cdq
0x18005a5a0  sub     eax, edx
0x18005a5a2  sar     eax, 1
0x18005a5a4  mov     [rsp+140h+var_104], eax
0x18005a5a8  cmp     [rdi+200h], r12d
0x18005a5af  jle     loc_18005A972
0x18005a5b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005a5b9  mov     rcx, [rdi+40h]
0x18005a5bd  movsxd  r8, r12d
0x18005a5c0  mov     rdx, [rcx+8]
0x18005a5c4  mov     rsi, [rdx+r8*8]
0x18005a5c8  cmp     dword ptr [rsi+0Ch], 7FFFFFFFh
0x18005a5cf  jz      loc_18005A933
0x18005a5d5  mov     edx, r12d
0x18005a5d8  mov     rcx, rdi
0x18005a5db  call    ListView_IsItemVisible
0x18005a5e0  test    eax, eax
0x18005a5e2  jnz     short loc_18005A613
0x18005a5e4  mov     rcx, [rsi+28h]; ho
0x18005a5e8  lea     rax, [rcx-1]
0x18005a5ec  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a5f0  ja      loc_18005A933
0x18005a5f6  mov     dword ptr [rsi+30h], 7FFFFFFFh
0x18005a5fd  mov     dword ptr [rsi+34h], 7FFFFFFFh
0x18005a604  call    cs:__imp_DeleteObject
0x18005a60a  mov     [rsi+28h], rbx
0x18005a60e  jmp     loc_18005A933
0x18005a613  mov     qword ptr [rsp+140h+rop], 0; LPRECT
0x18005a61c  lea     r9, [rbp+40h+rc2]; int
0x18005a620  lea     r8, [rbp+40h+rc]; int
0x18005a624  mov     [rsp+140h+lpBits], 0; lprcDst
0x18005a62d  mov     edx, r12d; int
0x18005a630  mov     rcx, rdi; int
0x18005a633  call    ListView_GetRects
0x18005a638  cmp     r12d, [rdi+150h]
0x18005a63f  lea     r15, [rsi+38h]
0x18005a643  lea     rcx, [rbp+40h+rc2]
0x18005a647  cmovz   rcx, r15; lprect
0x18005a64b  call    cs:__imp_CreateRectRgnIndirect
0x18005a651  mov     r14, rax
0x18005a654  test    rax, rax
0x18005a657  jz      loc_18005A961
0x18005a65d  mov     r9d, 2; iMode
0x18005a663  mov     r8, r13; hrgnSrc2
0x18005a666  mov     rdx, rax; hrgnSrc1
0x18005a669  mov     rcx, r13; hrgnDst
0x18005a66c  call    cs:__imp_CombineRgn
0x18005a672  mov     rcx, r14; ho
0x18005a675  mov     ebx, eax
0x18005a677  call    cs:__imp_DeleteObject
0x18005a67d  test    ebx, ebx
0x18005a67f  jz      loc_18005A961
0x18005a685  cmp     [rdi+150h], r12d
0x18005a68c  jz      short loc_18005A69B
0x18005a68e  lea     rdx, [rbp+40h+rc2]; lprcSrc
0x18005a692  mov     rcx, r15; lprcDst
0x18005a695  call    cs:__imp_CopyRect
0x18005a69b  mov     rcx, [rsi+28h]; hrgn
0x18005a69f  lea     rax, [rcx-1]
0x18005a6a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a6a7  ja      short loc_18005A6C6
0x18005a6a9  mov     r8d, [rsi+0Ch]
0x18005a6ad  mov     edx, [rsi+8]
0x18005a6b0  sub     r8d, [rsi+34h]; y
0x18005a6b4  sub     edx, [rsi+30h]; x
0x18005a6b7  call    cs:__imp_OffsetRgn
0x18005a6bd  mov     rdx, [rsi+28h]
0x18005a6c1  jmp     loc_18005A911
0x18005a6c6  cmp     cs:g_fSlowMachine, 0
0x18005a6cd  jz      short loc_18005A6FA
0x18005a6cf  mov     edx, [rsp+140h+var_108]
0x18005a6d3  lea     rcx, [rbp+40h+rc]; lprc
0x18005a6d7  mov     eax, [rbp+40h+rc2.top]
0x18005a6da  neg     edx; dx
0x18005a6dc  xor     r8d, r8d; dy
0x18005a6df  mov     [rbp+40h+rc.bottom], eax
0x18005a6e2  call    cs:__imp_InflateRect
0x18005a6e8  lea     rcx, [rbp+40h+rc]; lprect
0x18005a6ec  call    cs:__imp_CreateRectRgnIndirect
0x18005a6f2  mov     rbx, rax
0x18005a6f5  jmp     loc_18005A8F1
0x18005a6fa  xor     r15d, r15d
0x18005a6fd  xor     ebx, ebx
0x18005a6ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005a703  cmp     [rsi+10h], ax
0x18005a707  jnz     short loc_18005A746
0x18005a709  xor     eax, eax
0x18005a70b  lea     rdx, [rbp+40h+var_A8]
0x18005a70f  xorps   xmm0, xmm0
0x18005a712  mov     [rbp+40h+var_78], rax
0x18005a716  movups  [rbp+40h+var_A8], xmm0
0x18005a71a  mov     rcx, rdi
0x18005a71d  mov     dword ptr [rbp+40h+var_A8+4], r12d
0x18005a721  movups  [rbp+40h+var_98], xmm0
0x18005a725  mov     dword ptr [rbp+40h+var_A8+8], eax
0x18005a728  movups  [rbp+40h+var_88], xmm0
0x18005a72c  mov     dword ptr [rbp+40h+var_A8], 2
0x18005a733  mov     dword ptr [rbp+40h+var_98], 0FFFFh
0x18005a73a  mov     qword ptr [rbp+40h+var_98+8], rax
0x18005a73e  mov     dword ptr [rbp+40h+var_88], eax
0x18005a741  call    ListView_OnGetItem
0x18005a746  movzx   eax, word ptr [rsi+1Ch]
0x18005a74a  xor     r9d, r9d; x
0x18005a74d  movsx   edx, word ptr [rsi+10h]; i
0x18005a751  and     eax, 0F00h
0x18005a756  mov     r8, [rsp+140h+hdcDst]; hdcDst
0x18005a75b  or      eax, 10h
0x18005a75e  mov     rcx, [rdi+110h]; himl
0x18005a765  mov     [rsp+140h+rop], eax; fStyle
0x18005a769  mov     dword ptr [rsp+140h+lpBits], ebx; y
0x18005a76d  call    ImageList_Draw
0x18005a772  mov     r8, [rsp+140h+lpvBits]; lpvBits
0x18005a777  mov     edx, [rsp+140h+cb]; cb
0x18005a77b  mov     rcx, [rsp+140h+hbit]; hbit
0x18005a780  call    cs:__imp_GetBitmapBits
0x18005a786  mov     eax, [rsp+140h+cy]
0x18005a78a  xor     r13d, r13d
0x18005a78d  test    eax, eax
0x18005a78f  jle     loc_18005A92F
0x18005a795  mov     r10d, dword ptr [rbp+40h+pv+0Ch]
0x18005a799  mov     r8d, [rsp+140h+nWidth]
0x18005a79e  xor     r14d, r14d
0x18005a7a1  test    r8d, r8d
0x18005a7a4  jle     loc_18005A8DB
0x18005a7aa  mov     eax, r14d
0x18005a7ad  cdq
0x18005a7ae  and     edx, 7
0x18005a7b1  add     eax, edx
0x18005a7b3  mov     r9d, eax
0x18005a7b6  and     eax, 7
  ... truncated ...
```
