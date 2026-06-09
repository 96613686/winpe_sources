# _Header_DrawBitmap

- ea: `0x1800628ec`
- end: `0x180062bf6`
- name: `_Header_DrawBitmap`
- size: `778`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, HIMAGELIST himl@<rdx>, int, char, LPRECT lprc, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005ec54`

## callees

- `0x1800115f0`
- `0x1800628ec`
- `0x180085ba0`
- `0x180085eb0`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800629e8`
- `GDI32!CreateCompatibleDC` at `0x1800629e8`
- `GDI32!SelectObject` at `0x180062a01`
- `GDI32!SelectObject` at `0x180062b8c`
- `GDI32!SelectObject` at `0x180062a01`
- `GDI32!SelectObject` at `0x180062b8c`
- `GDI32!BitBlt` at `0x180062b7e`
- `GDI32!BitBlt` at `0x180062b7e`
- `GDI32!GetObjectW` at `0x1800629d6`
- `GDI32!GetObjectW` at `0x1800629d6`
- `GDI32!DeleteDC` at `0x180062b95`
- `GDI32!DeleteDC` at `0x180062b95`
- `USER32!SetRectEmpty` at `0x180062954`
- `USER32!SetRectEmpty` at `0x180062954`
- `USER32!IsRectEmpty` at `0x18006295d`
- `USER32!IsRectEmpty` at `0x18006295d`
- `USER32!OffsetRect` at `0x180062a40`
- `USER32!OffsetRect` at `0x180062a40`

## pseudocode

```c
__int64 __fastcall Header_DrawBitmap(
        HDC hdc,
        HIMAGELIST himl,
        __int64 a3,
        const RECT *a4,
        int a5,
        char a6,
        LPRECT lprc,
        int a8)
{
  __int64 result; // rax
  struct tagRECT v13; // xmm0
  HDC hdcSrc; // r15
  LONG top; // ebx
  LONG right; // esi
  HDC CompatibleDC; // rax
  int x1; // r12d
  LONG left; // edi
  int v20; // ecx
  LONG v21; // r14d
  int v22; // eax
  int y1; // r8d
  struct tagRECT v24; // xmm1
  struct tagRECT *v25; // rdx
  int v26; // eax
  __m128i v27; // xmm0
  unsigned int v28; // ecx
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  HDC hdca; // [rsp+60h] [rbp-A0h]
  HGDIOBJ h; // [rsp+68h] [rbp-98h]
  struct _IMAGELIST *v34; // [rsp+70h] [rbp-90h]
  struct tagRECT *v35; // [rsp+78h] [rbp-88h]
  IMAGELISTDRAWPARAMS pimldp; // [rsp+80h] [rbp-80h] BYREF
  struct tagRECT pv[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct tagRECT rc; // [rsp+100h] [rbp+0h] BYREF

  hdca = hdc;
  v34 = himl;
  v35 = lprc;
  v29 = 0;
  rc = 0;
  memset(pv, 0, sizeof(pv));
  SetRectEmpty(lprc);
  if ( IsRectEmpty(a4) )
    return (unsigned int)a4->left;
  v13 = *a4;
  rc = v13;
  rc.right = v13.right - a8;
  result = (unsigned int)(a8 + _mm_cvtsi128_si32((__m128i)v13));
  rc.left = result;
  if ( (int)result < v13.right - a8 )
  {
    v31 = *(_DWORD *)(a3 + 28) & 0x800;
    if ( v31 )
    {
      h = 0;
      hdcSrc = 0;
      ImageList_GetIconSize(himl, (int *)&v29, (int *)&v29 + 1);
      top = v29;
      right = HIDWORD(v29);
    }
    else
    {
      if ( GetObjectW(*(HANDLE *)(a3 + 16), 32, pv) != 32 )
        return (unsigned int)rc.left;
      CompatibleDC = CreateCompatibleDC(hdc);
      hdcSrc = CompatibleDC;
      if ( !CompatibleDC )
        return (unsigned int)rc.left;
      h = SelectObject(CompatibleDC, *(HGDIOBJ *)(a3 + 16));
      if ( !h )
        return (unsigned int)rc.left;
      top = pv[0].top;
      right = pv[0].right;
      v29 = *(_QWORD *)&pv[0].top;
    }
    x1 = 0;
    if ( (a6 & 0x20) != 0 )
    {
      OffsetRect(&rc, g_cxBorder, g_cyBorder);
      top = v29;
      right = HIDWORD(v29);
    }
    left = rc.left;
    v20 = rc.right - rc.left;
    if ( a5 )
    {
      if ( a5 != 2 )
      {
        if ( top <= v20 )
        {
          left = rc.right - top;
          rc.left = rc.right - top;
          goto LABEL_23;
        }
        x1 = top - v20;
        goto LABEL_21;
      }
      if ( top > v20 )
      {
        x1 = (top - v20) / 2;
LABEL_21:
        top = rc.right - rc.left;
        LODWORD(v29) = rc.right - rc.left;
        goto LABEL_23;
      }
      left = (rc.left + rc.right - top) / 2;
      rc.left = left;
    }
    else if ( top > v20 )
    {
      goto LABEL_21;
    }
LABEL_23:
    v21 = rc.top;
    if ( right <= rc.bottom - rc.top )
    {
      y1 = 0;
      v30 = 0;
      v21 = (rc.bottom - rc.top - right) / 2;
      rc.top = v21;
    }
    else
    {
      HIDWORD(v29) = rc.bottom - rc.top;
      v22 = right + rc.top - rc.bottom;
      right = rc.bottom - rc.top;
      y1 = v22 / 2;
      v30 = v22 / 2;
    }
    if ( v31 )
    {
      memset(&pimldp, 0, sizeof(pimldp));
      pimldp.himl = v34;
      pimldp.i = *(_DWORD *)(a3 + 40);
      pimldp.yBitmap = v30;
      pimldp.hdcDst = hdca;
      pimldp.rgbBk = -16777216;
      pimldp.rgbFg = -16777216;
      pimldp.cbSize = 88;
      pimldp.x = left;
      pimldp.y = v21;
      pimldp.cx = top;
      pimldp.cy = right;
      pimldp.xBitmap = x1;
      pimldp.fStyle = 0;
      ImageList_DrawIndirect(&pimldp);
    }
    else
    {
      BitBlt(hdca, left, v21, top, right, hdcSrc, x1, y1, 0xCC0020u);
      SelectObject(hdcSrc, h);
      DeleteDC(hdcSrc);
    }
    v24 = rc;
    v25 = v35;
    v26 = v29;
    v27 = _mm_srli_si128((__m128i)rc, 4);
    *v35 = rc;
    v25->bottom = HIDWORD(v29) + _mm_cvtsi128_si32(v27);
    v28 = _mm_cvtsi128_si32((__m128i)v24);
    result = v28 + v26;
    v25->right = result;
    if ( (*(_BYTE *)(a3 + 28) & 1) != 0 )
      return v28;
  }
  return result;
}

```

## disassembly

```asm
0x1800628ec  push    rbp
0x1800628ee  push    rbx
0x1800628ef  push    rsi
0x1800628f0  push    rdi
0x1800628f1  push    r12
0x1800628f3  push    r13
0x1800628f5  push    r14
0x1800628f7  push    r15
0x1800628f9  lea     rbp, [rsp-28h]
0x1800628fe  sub     rsp, 128h
0x180062905  mov     rax, cs:__security_cookie
0x18006290c  xor     rax, rsp
0x18006290f  mov     [rbp+60h+var_50], rax
0x180062913  mov     rax, [rbp+60h+lprc]
0x18006291a  xorps   xmm0, xmm0
0x18006291d  mov     rdi, rcx
0x180062920  mov     [rsp+160h+hdc], rcx
0x180062925  xor     r14d, r14d
0x180062928  mov     [rsp+160h+var_F0], rdx
0x18006292d  mov     rcx, rax; lprc
0x180062930  mov     [rsp+160h+var_E8], rax
0x180062935  mov     rbx, r9
0x180062938  mov     dword ptr [rsp+160h+var_110], r14d
0x18006293d  mov     r13, r8
0x180062940  mov     dword ptr [rsp+160h+var_110+4], r14d
0x180062945  mov     rsi, rdx
0x180062948  movups  xmmword ptr [rbp+60h+rc.left], xmm0
0x18006294c  movups  [rbp+60h+pv], xmm0
0x180062950  movups  [rbp+60h+var_70], xmm0
0x180062954  call    cs:__imp_SetRectEmpty
0x18006295a  mov     rcx, rbx; lprc
0x18006295d  call    cs:__imp_IsRectEmpty
0x180062963  test    eax, eax
0x180062965  jz      short loc_18006296E
0x180062967  mov     eax, [rbx]
0x180062969  jmp     loc_180062BD6
0x18006296e  movups  xmm0, xmmword ptr [rbx]
0x180062971  movups  xmmword ptr [rbp+60h+rc.left], xmm0
0x180062975  mov     ecx, [rbp+60h+rc.right]
0x180062978  sub     ecx, [rbp+60h+arg_38]
0x18006297e  movd    eax, xmm0
0x180062982  mov     [rbp+60h+rc.right], ecx
0x180062985  add     eax, [rbp+60h+arg_38]
0x18006298b  mov     [rbp+60h+rc.left], eax
0x18006298e  cmp     eax, ecx
0x180062990  jge     loc_180062BD6
0x180062996  mov     eax, [r13+1Ch]
0x18006299a  and     eax, 800h
0x18006299f  mov     [rsp+160h+var_104], eax
0x1800629a3  jz      short loc_1800629C9
0x1800629a5  lea     r8, [rsp+160h+var_110+4]; cy
0x1800629aa  mov     [rsp+160h+h], r14
0x1800629af  lea     rdx, [rsp+160h+var_110]; cx
0x1800629b4  mov     rcx, rsi; himl
0x1800629b7  mov     r15, r14
0x1800629ba  call    ImageList_GetIconSize
0x1800629bf  mov     ebx, dword ptr [rsp+160h+var_110]
0x1800629c3  mov     esi, dword ptr [rsp+160h+var_110+4]
0x1800629c7  jmp     short loc_180062A23
0x1800629c9  mov     rcx, [r13+10h]; h
0x1800629cd  lea     r8, [rbp+60h+pv]; pv
0x1800629d1  mov     edx, 20h ; ' '; c
0x1800629d6  call    cs:__imp_GetObjectW
0x1800629dc  cmp     eax, 20h ; ' '
0x1800629df  jnz     loc_180062BD3
0x1800629e5  mov     rcx, rdi; hdc
0x1800629e8  call    cs:__imp_CreateCompatibleDC
0x1800629ee  mov     r15, rax
0x1800629f1  test    rax, rax
0x1800629f4  jz      loc_180062BD3
0x1800629fa  mov     rdx, [r13+10h]; h
0x1800629fe  mov     rcx, rax; hdc
0x180062a01  call    cs:__imp_SelectObject
0x180062a07  mov     [rsp+160h+h], rax
0x180062a0c  test    rax, rax
0x180062a0f  jz      loc_180062BD3
0x180062a15  mov     ebx, dword ptr [rbp+60h+pv+4]
0x180062a18  mov     esi, dword ptr [rbp+60h+pv+8]
0x180062a1b  mov     dword ptr [rsp+160h+var_110], ebx
0x180062a1f  mov     dword ptr [rsp+160h+var_110+4], esi
0x180062a23  test    [rbp+60h+arg_28], 20h
0x180062a2a  mov     r12d, r14d
0x180062a2d  jz      short loc_180062A4E
0x180062a2f  mov     r8d, cs:g_cyBorder; dy
0x180062a36  lea     rcx, [rbp+60h+rc]; lprc
0x180062a3a  mov     edx, cs:g_cxBorder; dx
0x180062a40  call    cs:__imp_OffsetRect
0x180062a46  mov     ebx, dword ptr [rsp+160h+var_110]
0x180062a4a  mov     esi, dword ptr [rsp+160h+var_110+4]
0x180062a4e  mov     eax, [rbp+60h+rc.right]
0x180062a51  mov     ecx, eax
0x180062a53  mov     edi, [rbp+60h+rc.left]
0x180062a56  sub     ecx, edi
0x180062a58  mov     edx, [rbp+60h+arg_20]
0x180062a5e  test    edx, edx
0x180062a60  jnz     short loc_180062A68
0x180062a62  cmp     ebx, ecx
0x180062a64  jle     short loc_180062AA8
0x180062a66  jmp     short loc_180062A99
0x180062a68  cmp     edx, 2
0x180062a6b  jnz     short loc_180062A8F
0x180062a6d  cmp     ebx, ecx
0x180062a6f  jle     short loc_180062A7F
0x180062a71  sub     ebx, ecx
0x180062a73  mov     eax, ebx
0x180062a75  cdq
0x180062a76  sub     eax, edx
0x180062a78  sar     eax, 1
0x180062a7a  mov     r12d, eax
0x180062a7d  jmp     short loc_180062A99
0x180062a7f  sub     eax, ebx
0x180062a81  add     eax, edi
0x180062a83  cdq
0x180062a84  sub     eax, edx
0x180062a86  sar     eax, 1
0x180062a88  mov     edi, eax
0x180062a8a  mov     [rbp+60h+rc.left], eax
0x180062a8d  jmp     short loc_180062AA8
0x180062a8f  cmp     ebx, ecx
0x180062a91  jle     short loc_180062AA1
0x180062a93  mov     r12d, ebx
0x180062a96  sub     r12d, ecx
0x180062a99  mov     ebx, ecx
0x180062a9b  mov     dword ptr [rsp+160h+var_110], ecx
0x180062a9f  jmp     short loc_180062AA8
0x180062aa1  mov     edi, eax
0x180062aa3  sub     edi, ebx
0x180062aa5  mov     [rbp+60h+rc.left], edi
0x180062aa8  mov     ecx, [rbp+60h+rc.bottom]
0x180062aab  mov     r14d, [rbp+60h+rc.top]
0x180062aaf  sub     ecx, r14d
0x180062ab2  cmp     esi, ecx
0x180062ab4  jle     short loc_180062AD2
0x180062ab6  mov     eax, r14d
0x180062ab9  mov     dword ptr [rsp+160h+var_110+4], ecx
0x180062abd  sub     eax, [rbp+60h+rc.bottom]
0x180062ac0  add     eax, esi
0x180062ac2  mov     esi, ecx
0x180062ac4  cdq
0x180062ac5  sub     eax, edx
0x180062ac7  sar     eax, 1
0x180062ac9  mov     r8d, eax
0x180062acc  mov     [rsp+160h+var_108], eax
0x180062ad0  jmp     short loc_180062AE9
0x180062ad2  sub     ecx, esi
0x180062ad4  xor     r8d, r8d
0x180062ad7  mov     eax, ecx
0x180062ad9  mov     [rsp+160h+var_108], r8d
0x180062ade  cdq
0x180062adf  sub     eax, edx
0x180062ae1  sar     eax, 1
0x180062ae3  mov     r14d, eax
0x180062ae6  mov     [rbp+60h+rc.top], eax
0x180062ae9  cmp     [rsp+160h+var_104], 0
0x180062aee  jz      short loc_180062B56
0x180062af0  mov     r15d, 58h ; 'X'
0x180062af6  lea     rcx, [rbp+60h+pimldp]; void *
0x180062afa  mov     r8d, r15d; Size
0x180062afd  xor     edx, edx; Val
0x180062aff  call    memset
0x180062b04  mov     rax, [rsp+160h+var_F0]
0x180062b09  mov     rcx, [rsp+160h+hdc]
0x180062b0e  mov     [rbp+60h+pimldp.himl], rax
0x180062b12  mov     eax, [r13+28h]
0x180062b16  mov     [rbp+60h+pimldp.i], eax
0x180062b19  mov     eax, [rsp+160h+var_108]
0x180062b1d  mov     [rbp+60h+pimldp.yBitmap], eax
0x180062b20  mov     eax, 0FF000000h
0x180062b25  mov     [rbp+60h+pimldp.hdcDst], rcx
0x180062b29  lea     rcx, [rbp+60h+pimldp]; pimldp
0x180062b2d  mov     [rbp+60h+pimldp.rgbBk], eax
0x180062b30  mov     [rbp+60h+pimldp.rgbFg], eax
0x180062b33  mov     [rbp+60h+pimldp.cbSize], r15d
0x180062b37  mov     [rbp+60h+pimldp.x], edi
0x180062b3a  mov     [rbp+60h+pimldp.y], r14d
0x180062b3e  mov     [rbp+60h+pimldp.cx], ebx
0x180062b41  mov     [rbp+60h+pimldp.cy], esi
0x180062b44  mov     [rbp+60h+pimldp.xBitmap], r12d
0x180062b48  mov     [rbp+60h+pimldp.fStyle], 0
0x180062b4f  call    ImageList_DrawIndirect
0x180062b54  jmp     short loc_180062B9B
0x180062b56  mov     rcx, [rsp+160h+hdc]; hdc
0x180062b5b  mov     r9d, ebx; cx
0x180062b5e  mov     [rsp+160h+rop], 0CC0020h; rop
0x180062b66  mov     edx, edi; x
0x180062b68  mov     [rsp+160h+y1], r8d; y1
0x180062b6d  mov     r8d, r14d; y
0x180062b70  mov     [rsp+160h+x1], r12d; x1
0x180062b75  mov     [rsp+160h+hdcSrc], r15; hdcSrc
0x180062b7a  mov     [rsp+160h+var_140], esi; cy
0x180062b7e  call    cs:__imp_BitBlt
0x180062b84  mov     rdx, [rsp+160h+h]; h
0x180062b89  mov     rcx, r15; hdc
0x180062b8c  call    cs:__imp_SelectObject
0x180062b92  mov     rcx, r15; hdc
0x180062b95  call    cs:__imp_DeleteDC
0x180062b9b  movups  xmm1, xmmword ptr [rbp+60h+rc.left]
0x180062b9f  mov     rdx, [rsp+160h+var_E8]
0x180062ba4  mov     eax, dword ptr [rsp+160h+var_110]
0x180062ba8  movdqa  xmm0, xmm1
0x180062bac  psrldq  xmm0, 4
0x180062bb1  movdqu  xmmword ptr [rdx], xmm1
0x180062bb5  movd    ecx, xmm0
0x180062bb9  add     ecx, dword ptr [rsp+160h+var_110+4]
0x180062bbd  mov     [rdx+0Ch], ecx
0x180062bc0  movd    ecx, xmm1
0x180062bc4  add     eax, ecx
0x180062bc6  mov     [rdx+8], eax
0x180062bc9  test    byte ptr [r13+1Ch], 1
0x180062bce  cmovnz  eax, ecx
0x180062bd1  jmp     short loc_180062BD6
0x180062bd3  mov     eax, [rbp+60h+rc.left]
0x180062bd6  mov     rcx, [rbp+60h+var_50]
0x180062bda  xor     rcx, rsp; StackCookie
0x180062bdd  call    __security_check_cookie
0x180062be2  add     rsp, 128h
0x180062be9  pop     r15
0x180062beb  pop     r14
0x180062bed  pop     r13
0x180062bef  pop     r12
0x180062bf1  pop     rdi
0x180062bf2  pop     rsi
0x180062bf3  pop     rbx
0x180062bf4  pop     rbp
0x180062bf5  retn
```
