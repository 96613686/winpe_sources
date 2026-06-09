# _Header_DrawBitmap(HDC__ *,_IMAGELIST *,_HD_ITEMW *,tagRECT const *,int,uint,tagRECT *,int,DPISCALEINFO *)

- ea: `0x1800cb060`
- end: `0x1800cb3ad`
- name: `?_Header_DrawBitmap@@YAHPEAUHDC__@@PEAU_IMAGELIST@@PEAU_HD_ITEMW@@PEBUtagRECT@@HIPEAU4@HPEAUDPISCALEINFO@@@Z`
- size: `845`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, HIMAGELIST himl@<rdx>, struct _HD_ITEMW *@<r8>, const struct tagRECT *@<r9>, int, char, struct tagRECT *, int, struct DPISCALEINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009d9c`

## callees

- `0x1800199c0`
- `0x180019b30`
- `0x1800cb060`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!GetObjectW` at `0x1800cb26d`
- `GDI32!GetObjectW` at `0x1800cb26d`
- `GDI32!SelectObject` at `0x1800cb298`
- `GDI32!SelectObject` at `0x1800cb391`
- `GDI32!SelectObject` at `0x1800cb298`
- `GDI32!SelectObject` at `0x1800cb391`
- `GDI32!DeleteDC` at `0x1800cb39a`
- `GDI32!DeleteDC` at `0x1800cb39a`
- `GDI32!CreateCompatibleDC` at `0x1800cb27f`
- `GDI32!CreateCompatibleDC` at `0x1800cb27f`
- `GDI32!BitBlt` at `0x1800cb385`
- `GDI32!BitBlt` at `0x1800cb385`
- `USER32!SetRectEmpty` at `0x1800cb0dc`
- `USER32!SetRectEmpty` at `0x1800cb0dc`
- `USER32!OffsetRect` at `0x1800cb345`
- `USER32!OffsetRect` at `0x1800cb345`
- `USER32!IsRectEmpty` at `0x1800cb0e5`
- `USER32!IsRectEmpty` at `0x1800cb0e5`
- `USER32!GetSystemMetrics` at `0x1800cb329`
- `USER32!GetSystemMetrics` at `0x1800cb336`
- `USER32!GetSystemMetrics` at `0x1800cb329`
- `USER32!GetSystemMetrics` at `0x1800cb336`

## pseudocode

```c
__int64 __fastcall _Header_DrawBitmap(
        HDC hdc,
        HIMAGELIST himl,
        struct _HD_ITEMW *a3,
        const struct tagRECT *a4,
        int a5,
        char a6,
        LPRECT lprc,
        int a8)
{
  struct tagRECT v12; // xmm0
  __int64 result; // rax
  int v14; // r15d
  HGDIOBJ v15; // r13
  HDC hdcSrc; // rdi
  int v17; // r9d
  int v18; // r8d
  int x1; // esi
  LONG left; // r10d
  int v21; // ecx
  LONG top; // ecx
  int y1; // r12d
  struct tagRECT v24; // xmm1
  int v25; // eax
  __m128i v26; // xmm0
  unsigned int v27; // ecx
  HDC CompatibleDC; // rax
  int v29; // eax
  int SystemMetrics; // ebx
  int v31; // eax
  IMAGELISTDRAWPARAMS pimldp; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT rc; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD pv[2]; // [rsp+E8h] [rbp-18h] BYREF

  v35 = 0;
  rc = 0;
  memset_0(&pimldp, 0, sizeof(pimldp));
  memset(pv, 0, sizeof(pv));
  SetRectEmpty(lprc);
  if ( IsRectEmpty(a4) )
    return (unsigned int)a4->left;
  v12 = *a4;
  rc = v12;
  rc.right = v12.right - a8;
  result = (unsigned int)(a8 + _mm_cvtsi128_si32((__m128i)v12));
  rc.left = result;
  if ( (int)result < v12.right - a8 )
  {
    v14 = a3->fmt & 0x800;
    if ( v14 )
    {
      v15 = 0;
      hdcSrc = 0;
      ImageList_GetIconSize(himl, (int *)&v35, (int *)&v35 + 1);
      v17 = v35;
      v18 = HIDWORD(v35);
    }
    else
    {
      if ( GetObjectW(a3->hbm, 32, pv) != 32 )
        return (unsigned int)rc.left;
      CompatibleDC = CreateCompatibleDC(hdc);
      hdcSrc = CompatibleDC;
      if ( !CompatibleDC )
        return (unsigned int)rc.left;
      v15 = SelectObject(CompatibleDC, a3->hbm);
      if ( !v15 )
        return (unsigned int)rc.left;
      v17 = DWORD1(pv[0]);
      v18 = DWORD2(pv[0]);
      v35 = *(_QWORD *)((char *)pv + 4);
    }
    x1 = 0;
    left = rc.left;
    v21 = rc.right - rc.left;
    if ( a5 )
    {
      if ( a5 == 2 )
      {
        if ( v17 <= v21 )
        {
          left = (rc.left + rc.right - v17) / 2;
          rc.left = left;
          goto LABEL_8;
        }
        x1 = (v17 - v21) / 2;
      }
      else
      {
        if ( v17 <= v21 )
        {
          left = rc.right - v17;
          rc.left = rc.right - v17;
          goto LABEL_8;
        }
        x1 = v17 - v21;
      }
    }
    else if ( v17 <= v21 )
    {
LABEL_8:
      top = rc.top;
      if ( v18 > rc.bottom - rc.top )
      {
        HIDWORD(v35) = rc.bottom - rc.top;
        v29 = v18 + rc.top - rc.bottom;
        v18 = rc.bottom - rc.top;
        y1 = v29 / 2;
      }
      else
      {
        y1 = 0;
        top = (rc.bottom - rc.top - v18) / 2;
        rc.top = top;
      }
      if ( (a6 & 0x20) != 0 )
      {
        SystemMetrics = GetSystemMetrics(6);
        v31 = GetSystemMetrics(5);
        OffsetRect(&rc, v31, SystemMetrics);
        top = rc.top;
        left = rc.left;
        v17 = v35;
        v18 = HIDWORD(v35);
      }
      if ( v14 )
      {
        pimldp.himl = himl;
        pimldp.hdcDst = hdc;
        pimldp.i = a3->iImage;
        pimldp.y = top;
        pimldp.rgbBk = -16777216;
        pimldp.rgbFg = -16777216;
        pimldp.cbSize = 88;
        pimldp.x = left;
        pimldp.cx = v17;
        pimldp.cy = v18;
        pimldp.xBitmap = x1;
        pimldp.yBitmap = y1;
        pimldp.fStyle = 0;
        pimldp.fState = 0;
        ImageList_DrawIndirect(&pimldp);
      }
      else
      {
        BitBlt(hdc, left, top, v17, v18, hdcSrc, x1, y1, 0xCC0020u);
        SelectObject(hdcSrc, v15);
        DeleteDC(hdcSrc);
      }
      v24 = rc;
      v25 = v35;
      v26 = _mm_srli_si128((__m128i)rc, 4);
      *lprc = rc;
      lprc->bottom = HIDWORD(v35) + _mm_cvtsi128_si32(v26);
      v27 = _mm_cvtsi128_si32((__m128i)v24);
      result = v27 + v25;
      lprc->right = result;
      if ( (a3->fmt & 1) != 0 )
        return v27;
      return result;
    }
    v17 = rc.right - rc.left;
    LODWORD(v35) = rc.right - rc.left;
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x1800cb060  push    rbp
0x1800cb062  push    rbx
0x1800cb063  push    rsi
0x1800cb064  push    rdi
0x1800cb065  push    r12
0x1800cb067  push    r13
0x1800cb069  push    r14
0x1800cb06b  push    r15
0x1800cb06d  lea     rbp, [rsp-18h]
0x1800cb072  sub     rsp, 118h
0x1800cb079  mov     rax, cs:__security_cookie
0x1800cb080  xor     rax, rsp
0x1800cb083  mov     [rbp+50h+var_48], rax
0x1800cb087  mov     rdi, [rbp+50h+lprc]
0x1800cb08e  mov     r12, rdx
0x1800cb091  mov     [rsp+150h+var_F8], rdx
0x1800cb096  mov     r14, r8
0x1800cb099  xor     edx, edx; Val
0x1800cb09b  mov     [rsp+150h+hdc], rcx
0x1800cb0a0  mov     rsi, rcx
0x1800cb0a3  mov     [rsp+150h+var_F0], rdi
0x1800cb0a8  xorps   xmm0, xmm0
0x1800cb0ab  mov     dword ptr [rbp+50h+var_80], 0
0x1800cb0b2  lea     rcx, [rsp+150h+pimldp]; void *
0x1800cb0b7  mov     dword ptr [rbp+50h+var_80+4], 0
0x1800cb0be  lea     r8d, [rdx+58h]; Size
0x1800cb0c2  mov     rbx, r9
0x1800cb0c5  movups  xmmword ptr [rbp+50h+rc.left], xmm0
0x1800cb0c9  call    memset_0
0x1800cb0ce  xorps   xmm0, xmm0
0x1800cb0d1  mov     rcx, rdi; lprc
0x1800cb0d4  movups  [rbp+50h+pv], xmm0
0x1800cb0d8  movups  [rbp+50h+var_58], xmm0
0x1800cb0dc  call    cs:__imp_SetRectEmpty
0x1800cb0e2  mov     rcx, rbx; lprc
0x1800cb0e5  call    cs:__imp_IsRectEmpty
0x1800cb0eb  test    eax, eax
0x1800cb0ed  jnz     loc_1800CB25C
0x1800cb0f3  movups  xmm0, xmmword ptr [rbx]
0x1800cb0f6  movups  xmmword ptr [rbp+50h+rc.left], xmm0
0x1800cb0fa  mov     ecx, [rbp+50h+rc.right]
0x1800cb0fd  sub     ecx, [rbp+50h+arg_38]
0x1800cb103  movd    eax, xmm0
0x1800cb107  mov     [rbp+50h+rc.right], ecx
0x1800cb10a  add     eax, [rbp+50h+arg_38]
0x1800cb110  mov     [rbp+50h+rc.left], eax
0x1800cb113  cmp     eax, ecx
0x1800cb115  jge     loc_1800CB23C
0x1800cb11b  mov     r15d, [r14+1Ch]
0x1800cb11f  and     r15d, 800h
0x1800cb126  jz      loc_1800CB260
0x1800cb12c  xor     r13d, r13d
0x1800cb12f  lea     r8, [rbp+50h+var_80+4]; cy
0x1800cb133  xor     edi, edi
0x1800cb135  lea     rdx, [rbp+50h+var_80]; cx
0x1800cb139  mov     rcx, r12; himl
0x1800cb13c  call    ImageList_GetIconSize
0x1800cb141  mov     r9d, dword ptr [rbp+50h+var_80]
0x1800cb145  mov     r8d, dword ptr [rbp+50h+var_80+4]
0x1800cb149  mov     eax, [rbp+50h+rc.right]
0x1800cb14c  xor     esi, esi
0x1800cb14e  mov     r10d, [rbp+50h+rc.left]
0x1800cb152  mov     ecx, eax
0x1800cb154  mov     edx, [rbp+50h+arg_20]
0x1800cb15a  sub     ecx, r10d
0x1800cb15d  lea     ebx, [rsi+2]
0x1800cb160  test    edx, edx
0x1800cb162  jnz     loc_1800CB2BF
0x1800cb168  cmp     r9d, ecx
0x1800cb16b  jle     short loc_1800CB173
0x1800cb16d  mov     r9d, ecx; cx
0x1800cb170  mov     dword ptr [rbp+50h+var_80], ecx
0x1800cb173  mov     r11d, [rbp+50h+rc.bottom]
0x1800cb177  mov     ecx, [rbp+50h+rc.top]
0x1800cb17a  sub     r11d, ecx
0x1800cb17d  cmp     r8d, r11d
0x1800cb180  jg      loc_1800CB30A
0x1800cb186  sub     r11d, r8d
0x1800cb189  xor     r12d, r12d
0x1800cb18c  mov     eax, r11d
0x1800cb18f  cdq
0x1800cb190  idiv    ebx
0x1800cb192  mov     ecx, eax
0x1800cb194  mov     [rbp+50h+rc.top], eax
0x1800cb197  test    [rbp+50h+arg_28], 20h
0x1800cb19e  jnz     loc_1800CB324
0x1800cb1a4  test    r15d, r15d
0x1800cb1a7  jz      loc_1800CB35F
0x1800cb1ad  mov     rax, [rsp+150h+var_F8]
0x1800cb1b2  mov     [rsp+150h+pimldp.himl], rax
0x1800cb1b7  mov     rax, [rsp+150h+hdc]
0x1800cb1bc  mov     [rbp+50h+pimldp.hdcDst], rax
0x1800cb1c0  mov     eax, [r14+28h]
0x1800cb1c4  mov     [rbp+50h+pimldp.i], eax
0x1800cb1c7  mov     eax, 0FF000000h
0x1800cb1cc  mov     [rbp+50h+pimldp.y], ecx
0x1800cb1cf  lea     rcx, [rsp+150h+pimldp]; pimldp
0x1800cb1d4  mov     [rbp+50h+pimldp.rgbBk], eax
0x1800cb1d7  mov     [rbp+50h+pimldp.rgbFg], eax
0x1800cb1da  mov     [rsp+150h+pimldp.cbSize], 58h ; 'X'
0x1800cb1e2  mov     [rbp+50h+pimldp.x], r10d
0x1800cb1e6  mov     [rbp+50h+pimldp.cx], r9d
0x1800cb1ea  mov     [rbp+50h+pimldp.cy], r8d
0x1800cb1ee  mov     [rbp+50h+pimldp.xBitmap], esi
0x1800cb1f1  mov     [rbp+50h+pimldp.yBitmap], r12d
0x1800cb1f5  mov     [rbp+50h+pimldp.fStyle], 0
0x1800cb1fc  mov     [rbp+50h+pimldp.fState], 0
0x1800cb203  call    ImageList_DrawIndirect
0x1800cb208  movups  xmm1, xmmword ptr [rbp+50h+rc.left]
0x1800cb20c  mov     rdx, [rsp+150h+var_F0]
0x1800cb211  mov     eax, dword ptr [rbp+50h+var_80]
0x1800cb214  movdqa  xmm0, xmm1
0x1800cb218  psrldq  xmm0, 4
0x1800cb21d  movdqu  xmmword ptr [rdx], xmm1
0x1800cb221  movd    ecx, xmm0
0x1800cb225  add     ecx, dword ptr [rbp+50h+var_80+4]
0x1800cb228  mov     [rdx+0Ch], ecx
0x1800cb22b  movd    ecx, xmm1
0x1800cb22f  add     eax, ecx
0x1800cb231  mov     [rdx+8], eax
0x1800cb234  test    byte ptr [r14+1Ch], 1
0x1800cb239  cmovnz  eax, ecx
0x1800cb23c  mov     rcx, [rbp+50h+var_48]
0x1800cb240  xor     rcx, rsp; StackCookie
0x1800cb243  call    __security_check_cookie
0x1800cb248  add     rsp, 118h
0x1800cb24f  pop     r15
0x1800cb251  pop     r14
0x1800cb253  pop     r13
0x1800cb255  pop     r12
0x1800cb257  pop     rdi
0x1800cb258  pop     rsi
0x1800cb259  pop     rbx
0x1800cb25a  pop     rbp
0x1800cb25b  retn
0x1800cb25c  mov     eax, [rbx]
0x1800cb25e  jmp     short loc_1800CB23C
0x1800cb260  mov     rcx, [r14+10h]; h
0x1800cb264  lea     r8, [rbp+50h+pv]; pv
0x1800cb268  mov     edx, 20h ; ' '; c
0x1800cb26d  call    cs:__imp_GetObjectW
0x1800cb273  cmp     eax, 20h ; ' '
0x1800cb276  jnz     loc_1800CB3A5
0x1800cb27c  mov     rcx, rsi; hdc
0x1800cb27f  call    cs:__imp_CreateCompatibleDC
0x1800cb285  mov     rdi, rax
0x1800cb288  test    rax, rax
0x1800cb28b  jz      loc_1800CB3A5
0x1800cb291  mov     rdx, [r14+10h]; h
0x1800cb295  mov     rcx, rax; hdc
0x1800cb298  call    cs:__imp_SelectObject
0x1800cb29e  mov     r13, rax
0x1800cb2a1  test    rax, rax
0x1800cb2a4  jz      loc_1800CB3A5
0x1800cb2aa  mov     r9d, dword ptr [rbp+50h+pv+4]
0x1800cb2ae  mov     r8d, dword ptr [rbp+50h+pv+8]
0x1800cb2b2  mov     dword ptr [rbp+50h+var_80], r9d
0x1800cb2b6  mov     dword ptr [rbp+50h+var_80+4], r8d
0x1800cb2ba  jmp     loc_1800CB149
0x1800cb2bf  cmp     edx, ebx
0x1800cb2c1  jnz     short loc_1800CB2EC
0x1800cb2c3  cmp     r9d, ecx
0x1800cb2c6  jle     short loc_1800CB2D8
0x1800cb2c8  sub     r9d, ecx
0x1800cb2cb  mov     eax, r9d
0x1800cb2ce  cdq
0x1800cb2cf  idiv    ebx
0x1800cb2d1  mov     esi, eax
0x1800cb2d3  jmp     loc_1800CB16D
0x1800cb2d8  sub     eax, r9d
0x1800cb2db  add     eax, r10d
0x1800cb2de  cdq
0x1800cb2df  idiv    ebx
0x1800cb2e1  mov     r10d, eax
0x1800cb2e4  mov     [rbp+50h+rc.left], eax
0x1800cb2e7  jmp     loc_1800CB173
0x1800cb2ec  cmp     r9d, ecx
0x1800cb2ef  jle     short loc_1800CB2FB
0x1800cb2f1  mov     esi, r9d
0x1800cb2f4  sub     esi, ecx
0x1800cb2f6  jmp     loc_1800CB16D
0x1800cb2fb  mov     r10d, eax
0x1800cb2fe  sub     r10d, r9d
0x1800cb301  mov     [rbp+50h+rc.left], r10d
0x1800cb305  jmp     loc_1800CB173
0x1800cb30a  mov     eax, ecx
0x1800cb30c  mov     dword ptr [rbp+50h+var_80+4], r11d
0x1800cb310  sub     eax, [rbp+50h+rc.bottom]
0x1800cb313  add     eax, r8d
0x1800cb316  mov     r8d, r11d
0x1800cb319  cdq
0x1800cb31a  idiv    ebx
0x1800cb31c  mov     r12d, eax
0x1800cb31f  jmp     loc_1800CB197
0x1800cb324  mov     ecx, 6; nIndex
0x1800cb329  call    cs:__imp_GetSystemMetrics
0x1800cb32f  mov     ecx, 5; nIndex
0x1800cb334  mov     ebx, eax
0x1800cb336  call    cs:__imp_GetSystemMetrics
0x1800cb33c  mov     r8d, ebx; dy
0x1800cb33f  lea     rcx, [rbp+50h+rc]; lprc
0x1800cb343  mov     edx, eax; dx
0x1800cb345  call    cs:__imp_OffsetRect
0x1800cb34b  mov     ecx, [rbp+50h+rc.top]
0x1800cb34e  mov     r10d, [rbp+50h+rc.left]
0x1800cb352  mov     r9d, dword ptr [rbp+50h+var_80]
0x1800cb356  mov     r8d, dword ptr [rbp+50h+var_80+4]
0x1800cb35a  jmp     loc_1800CB1A4
0x1800cb35f  mov     [rsp+150h+rop], 0CC0020h; rop
0x1800cb367  mov     edx, r10d; x
0x1800cb36a  mov     [rsp+150h+y1], r12d; y1
0x1800cb36f  mov     [rsp+150h+x1], esi; x1
0x1800cb373  mov     [rsp+150h+hdcSrc], rdi; hdcSrc
0x1800cb378  mov     [rsp+150h+var_130], r8d; cy
0x1800cb37d  mov     r8d, ecx; y
0x1800cb380  mov     rcx, [rsp+150h+hdc]; hdc
0x1800cb385  call    cs:__imp_BitBlt
0x1800cb38b  mov     rdx, r13; h
0x1800cb38e  mov     rcx, rdi; hdc
0x1800cb391  call    cs:__imp_SelectObject
0x1800cb397  mov     rcx, rdi; hdc
0x1800cb39a  call    cs:__imp_DeleteDC
0x1800cb3a0  jmp     loc_1800CB208
0x1800cb3a5  mov     eax, [rbp+50h+rc.left]
0x1800cb3a8  jmp     loc_1800CB23C
```
