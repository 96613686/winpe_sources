# DrawStatusTextEx

- ea: `0x180021848`
- end: `0x180021c3f`
- name: `DrawStatusTextEx`
- size: `1015`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800217b0`
- `0x180021c50`
- `0x180021f10`

## callees

- `0x1800115f0`
- `0x180019614`
- `0x180021848`

## import_xrefs

- `GDI32!SelectObject` at `0x1800219c2`
- `GDI32!SelectObject` at `0x1800219ff`
- `GDI32!SelectObject` at `0x1800219c2`
- `GDI32!SelectObject` at `0x1800219ff`
- `GDI32!DeleteObject` at `0x180021c19`
- `GDI32!DeleteObject` at `0x180021c19`
- `GDI32!ExtTextOutW` at `0x180021bb0`
- `GDI32!ExtTextOutW` at `0x180021bb0`
- `GDI32!SetBkMode` at `0x180021929`
- `GDI32!SetBkMode` at `0x180021c0b`
- `GDI32!SetBkMode` at `0x180021929`
- `GDI32!SetBkMode` at `0x180021c0b`
- `GDI32!SetBkColor` at `0x180021961`
- `GDI32!SetBkColor` at `0x180021bff`
- `GDI32!SetBkColor` at `0x180021961`
- `GDI32!SetBkColor` at `0x180021bff`
- `GDI32!SetTextColor` at `0x18002193b`
- `GDI32!SetTextColor` at `0x180021bf3`
- `GDI32!SetTextColor` at `0x18002193b`
- `GDI32!SetTextColor` at `0x180021bf3`
- `GDI32!GetTextAlign` at `0x1800218bb`
- `GDI32!GetTextAlign` at `0x1800218bb`
- `GDI32!SetTextAlign` at `0x1800218cd`
- `GDI32!SetTextAlign` at `0x180021be7`
- `GDI32!SetTextAlign` at `0x1800218cd`
- `GDI32!SetTextAlign` at `0x180021be7`
- `GDI32!GetNearestColor` at `0x1800218ea`
- `GDI32!GetNearestColor` at `0x1800218ea`
- `GDI32!CreateSolidBrush` at `0x1800218fa`
- `GDI32!CreateSolidBrush` at `0x1800218fa`
- `GDI32!PatBlt` at `0x1800219f3`
- `GDI32!PatBlt` at `0x1800219f3`
- `USER32!InflateRect` at `0x1800219b1`
- `USER32!InflateRect` at `0x1800219b1`
- `USER32!DrawEdge` at `0x180021993`
- `USER32!DrawEdge` at `0x180021993`
- `USER32!DrawIconEx` at `0x180021b38`
- `USER32!DrawIconEx` at `0x180021b38`

## pseudocode

```c
int __fastcall DrawStatusTextEx(__int64 a1, HDC a2, struct tagRECT *a3, const WCHAR *a4, __int64 a5, __int16 a6)
{
  int v6; // r12d
  struct tagRECT v8; // xmm0
  HGDIOBJ v11; // r15
  const WCHAR *v12; // rdi
  int v13; // edx
  COLORREF v14; // edx
  HGDIOBJ v15; // rsi
  __int64 v16; // r15
  int v17; // esi
  const WCHAR *v18; // r14
  int v19; // r10d
  LONG v20; // r11d
  HICON v21; // r9
  LONG left; // ecx
  HGDIOBJ v23; // r15
  int result; // eax
  UINT options; // [rsp+54h] [rbp-55h]
  int v26; // [rsp+58h] [rbp-51h]
  int v27; // [rsp+5Ch] [rbp-4Dh] BYREF
  int v28; // [rsp+60h] [rbp-49h]
  UINT align; // [rsp+64h] [rbp-45h]
  COLORREF v30; // [rsp+68h] [rbp-41h]
  int mode; // [rsp+6Ch] [rbp-3Dh]
  __int64 v32; // [rsp+70h] [rbp-39h]
  int v33; // [rsp+78h] [rbp-31h]
  COLORREF color; // [rsp+7Ch] [rbp-2Dh]
  struct tagRECT *v35; // [rsp+80h] [rbp-29h]
  HGDIOBJ ho; // [rsp+88h] [rbp-21h]
  UINT c[2]; // [rsp+90h] [rbp-19h]
  struct tagRECT qrc; // [rsp+98h] [rbp-11h] BYREF

  v6 = 0;
  v8 = *a3;
  v32 = a5;
  v35 = a3;
  v33 = a6 & 0x400;
  v27 = 0;
  v11 = 0;
  ho = 0;
  align = 0;
  v26 = 0;
  qrc = v8;
  if ( (a6 & 0x400) != 0 )
  {
    align = GetTextAlign(a2);
    SetTextAlign(a2, align | 0x100);
  }
  v12 = &c_szNULL;
  if ( a4 )
    v12 = a4;
  if ( GetNearestColor(a2, g_clrBtnFace) == g_clrBtnFace || (ho = CreateSolidBrush(g_clrBtnFace), (v11 = ho) == 0) )
  {
    options = 6;
    v13 = 2;
  }
  else
  {
    options = 4;
    v13 = 1;
  }
  mode = SetBkMode(a2, v13);
  color = SetTextColor(a2, g_clrBtnText);
  if ( !a1 || (v14 = *(_DWORD *)(a1 + 164), v14 == -16777216) )
    v14 = g_clrBtnFace;
  v30 = SetBkColor(a2, v14);
  if ( (a6 & 0x100) != 0 )
    InflateRect(&qrc, -g_cxBorder, -g_cyBorder);
  else
    DrawEdge(a2, &qrc, (a6 & 0x200) != 0 ? 4 : 2, 0x200Fu);
  if ( v11 )
  {
    v15 = SelectObject(a2, v11);
    if ( v15 )
    {
      PatBlt(a2, qrc.left, qrc.top, qrc.right - qrc.left, qrc.bottom - qrc.top, 0xF00021u);
      SelectObject(a2, v15);
    }
  }
  v16 = v32;
  v28 = 0;
  do
  {
    if ( (a6 & 0x800) == 0 && *v12 == 9 && (unsigned int)v6 <= 1 )
      goto LABEL_49;
    v17 = 0;
    v18 = v12;
    if ( *v12 )
    {
      while ( (a6 & 0x800) != 0 || *v18 != 9 )
      {
        if ( !*++v18 )
          goto LABEL_26;
      }
    }
    else
    {
LABEL_26:
      v28 = 1;
    }
    *(_QWORD *)c = v18 - v12;
    MGetTextExtent(a2, v12, c[0], (__int64)&v27);
    if ( v16 && *(_QWORD *)(v16 + 16) && !v26 )
    {
      v26 = 1;
      v17 = *(_DWORD *)(v16 + 24) + 2 * g_cxEdge;
    }
    if ( v6 )
    {
      if ( v6 == 1 )
        v19 = (v35->left + v35->right - v17) / 2;
      else
        v19 = v35->right - v17 - g_cxEdge;
    }
    else
    {
      v19 = g_cxEdge + v35->left;
    }
    v20 = v19 + v17;
    LODWORD(v32) = v19 + v17;
    if ( v16 )
    {
      if ( v17 )
      {
        if ( v19 > v35->left )
        {
          v21 = *(HICON *)(v16 + 16);
          if ( v21 )
          {
            DrawIconEx(
              a2,
              v19,
              qrc.top + (qrc.bottom - *(_DWORD *)(v16 + 28) - qrc.top) / 2,
              v21,
              *(_DWORD *)(v16 + 24),
              *(_DWORD *)(v16 + 28),
              0,
              0,
              3u);
            v20 = v32;
          }
        }
        left = v20;
        qrc.left = v20;
      }
      else
      {
        left = qrc.left;
      }
      *(_DWORD *)(v16 + 40) = !*v12 && v17 || qrc.right - left <= 0;
    }
    ExtTextOutW(a2, v20, (qrc.bottom + qrc.top - v27) / 2, options, &qrc, v12, c[0], 0);
    if ( v28 )
      break;
    options = 4;
    v12 = v18;
LABEL_49:
    ++v6;
    ++v12;
  }
  while ( v6 < 3 );
  v23 = ho;
  if ( v33 )
    SetTextAlign(a2, align);
  SetTextColor(a2, color);
  SetBkColor(a2, v30);
  result = SetBkMode(a2, mode);
  if ( v23 )
    return DeleteObject(v23);
  return result;
}

```

## disassembly

```asm
0x180021848  push    rbp
0x18002184a  push    rbx
0x18002184b  push    rsi
0x18002184c  push    rdi
0x18002184d  push    r12
0x18002184f  push    r13
0x180021851  push    r14
0x180021853  push    r15
0x180021855  lea     rbp, [rsp-0Fh]
0x18002185a  sub     rsp, 0B8h
0x180021861  mov     rax, cs:__security_cookie
0x180021868  xor     rax, rsp
0x18002186b  mov     [rbp+47h+var_48], rax
0x18002186f  mov     rax, [rbp+47h+arg_20]
0x180021873  xor     r12d, r12d
0x180021876  mov     r13d, [rbp+47h+arg_28]
0x18002187a  mov     rsi, r9
0x18002187d  movups  xmm0, xmmword ptr [r8]
0x180021881  mov     [rbp+47h+var_80], rax
0x180021885  mov     rbx, rdx
0x180021888  mov     eax, r13d
0x18002188b  mov     [rbp+47h+var_70], r8
0x18002188f  and     eax, 400h
0x180021894  mov     [rbp+47h+var_A0], r12d
0x180021898  mov     [rbp+47h+var_78], eax
0x18002189b  mov     r14, rcx
0x18002189e  mov     dword ptr [rbp+47h+var_94], r12d
0x1800218a2  mov     r15d, r12d
0x1800218a5  mov     [rbp+47h+ho], r12
0x1800218a9  mov     [rbp+47h+align], r12d
0x1800218ad  mov     [rbp+47h+var_98], r12d
0x1800218b1  movdqu  xmmword ptr [rbp+47h+qrc.left], xmm0
0x1800218b6  jz      short loc_1800218D3
0x1800218b8  mov     rcx, rdx; hdc
0x1800218bb  call    cs:__imp_GetTextAlign
0x1800218c1  mov     edx, eax
0x1800218c3  mov     [rbp+47h+align], eax
0x1800218c6  bts     edx, 8; align
0x1800218ca  mov     rcx, rbx; hdc
0x1800218cd  call    cs:__imp_SetTextAlign
0x1800218d3  mov     edx, cs:g_clrBtnFace; color
0x1800218d9  lea     rdi, c_szNULL
0x1800218e0  test    rsi, rsi
0x1800218e3  mov     rcx, rbx; hdc
0x1800218e6  cmovnz  rdi, rsi
0x1800218ea  call    cs:__imp_GetNearestColor
0x1800218f0  mov     ecx, cs:g_clrBtnFace; color
0x1800218f6  cmp     eax, ecx
0x1800218f8  jz      short loc_18002191A
0x1800218fa  call    cs:__imp_CreateSolidBrush
0x180021900  mov     [rbp+47h+ho], rax
0x180021904  mov     r15, rax
0x180021907  test    rax, rax
0x18002190a  jz      short loc_18002191A
0x18002190c  mov     [rbp+47h+options], 4
0x180021913  mov     edx, 1
0x180021918  jmp     short loc_180021926
0x18002191a  mov     [rbp+47h+options], 6
0x180021921  mov     edx, 2; mode
0x180021926  mov     rcx, rbx; hdc
0x180021929  call    cs:__imp_SetBkMode
0x18002192f  mov     edx, cs:g_clrBtnText; color
0x180021935  mov     rcx, rbx; hdc
0x180021938  mov     [rbp+47h+mode], eax
0x18002193b  call    cs:__imp_SetTextColor
0x180021941  mov     [rbp+47h+color], eax
0x180021944  test    r14, r14
0x180021947  jz      short loc_180021958
0x180021949  mov     edx, [r14+0A4h]
0x180021950  cmp     edx, 0FF000000h
0x180021956  jnz     short loc_18002195E
0x180021958  mov     edx, cs:g_clrBtnFace; color
0x18002195e  mov     rcx, rbx; hdc
0x180021961  call    cs:__imp_SetBkColor
0x180021967  mov     [rbp+47h+var_88], eax
0x18002196a  bt      r13d, 8
0x18002196f  jb      short loc_18002199B
0x180021971  mov     eax, r13d
0x180021974  lea     rdx, [rbp+47h+qrc]; qrc
0x180021978  and     eax, 200h
0x18002197d  mov     r9d, 200Fh; grfFlags
0x180021983  neg     eax
0x180021985  mov     rcx, rbx; hdc
0x180021988  sbb     r8d, r8d
0x18002198b  and     r8d, 2
0x18002198f  add     r8d, 2; edge
0x180021993  call    cs:__imp_DrawEdge
0x180021999  jmp     short loc_1800219B7
0x18002199b  mov     r8d, cs:g_cyBorder
0x1800219a2  lea     rcx, [rbp+47h+qrc]; lprc
0x1800219a6  mov     edx, cs:g_cxBorder
0x1800219ac  neg     r8d; dy
0x1800219af  neg     edx; dx
0x1800219b1  call    cs:__imp_InflateRect
0x1800219b7  test    r15, r15
0x1800219ba  jz      short loc_180021A05
0x1800219bc  mov     rdx, r15; h
0x1800219bf  mov     rcx, rbx; hdc
0x1800219c2  call    cs:__imp_SelectObject
0x1800219c8  mov     rsi, rax
0x1800219cb  test    rax, rax
0x1800219ce  jz      short loc_180021A05
0x1800219d0  mov     ecx, [rbp+47h+qrc.bottom]
0x1800219d3  mov     r8d, [rbp+47h+qrc.top]; y
0x1800219d7  sub     ecx, r8d
0x1800219da  mov     r9d, [rbp+47h+qrc.right]
0x1800219de  mov     edx, [rbp+47h+qrc.left]; x
0x1800219e1  sub     r9d, edx; w
0x1800219e4  mov     [rsp+0F0h+rop], 0F00021h; rop
0x1800219ec  mov     [rsp+0F0h+h], ecx; h
0x1800219f0  mov     rcx, rbx; hdc
0x1800219f3  call    cs:__imp_PatBlt
0x1800219f9  mov     rdx, rsi; h
0x1800219fc  mov     rcx, rbx; hdc
0x1800219ff  call    cs:__imp_SelectObject
0x180021a05  mov     r15, [rbp+47h+var_80]
0x180021a09  xor     eax, eax
0x180021a0b  mov     dword ptr [rbp+47h+var_94+4], eax
0x180021a0e  and     r13d, 800h
0x180021a15  test    r13d, r13d
0x180021a18  jnz     short loc_180021A2A
0x180021a1a  cmp     word ptr [rdi], 9
0x180021a1e  jnz     short loc_180021A2A
0x180021a20  cmp     r12d, 1
0x180021a24  jbe     loc_180021BC7
0x180021a2a  mov     esi, eax
0x180021a2c  mov     r14, rdi
0x180021a2f  cmp     [rdi], ax
0x180021a32  jz      short loc_180021A4A
0x180021a34  test    r13d, r13d
0x180021a37  jnz     short loc_180021A40
0x180021a39  cmp     word ptr [r14], 9
0x180021a3e  jz      short loc_180021A51
0x180021a40  add     r14, 2
0x180021a44  cmp     [r14], ax
0x180021a48  jnz     short loc_180021A34
0x180021a4a  mov     dword ptr [rbp+47h+var_94+4], 1
0x180021a51  lea     rcx, [rbp+47h+var_94]
0x180021a55  mov     rax, r14
0x180021a58  sub     rax, rdi
0x180021a5b  mov     qword ptr [rsp+0F0h+h], rcx; __int64
0x180021a60  sar     rax, 1
0x180021a63  lea     r9, [rbp+47h+var_A0]
0x180021a67  mov     r8d, eax; c
0x180021a6a  mov     qword ptr [rbp+47h+c], rax
0x180021a6e  mov     rdx, rdi; lpString
0x180021a71  mov     rcx, rbx; hdc
0x180021a74  call    MGetTextExtent
0x180021a79  mov     edx, cs:g_cxEdge
0x180021a7f  xor     r8d, r8d
0x180021a82  test    r15, r15
0x180021a85  jz      short loc_180021AA1
0x180021a87  cmp     [r15+10h], r8
0x180021a8b  jz      short loc_180021AA1
0x180021a8d  cmp     [rbp+47h+var_98], r8d
0x180021a91  jnz     short loc_180021AA1
0x180021a93  mov     eax, [r15+18h]
0x180021a97  mov     [rbp+47h+var_98], 1
0x180021a9e  lea     esi, [rax+rdx*2]
0x180021aa1  mov     rcx, [rbp+47h+var_70]
0x180021aa5  test    r12d, r12d
0x180021aa8  jz      short loc_180021AD4
0x180021aaa  cmp     r12d, 1
0x180021aae  jz      short loc_180021AC0
0x180021ab0  mov     r10d, [rcx+8]
0x180021ab4  sub     r10d, esi
0x180021ab7  sub     r10d, edx
0x180021aba  sub     r10d, [rbp+47h+var_A0]
0x180021abe  jmp     short loc_180021ADA
0x180021ac0  mov     eax, [rcx+8]
0x180021ac3  sub     eax, esi
0x180021ac5  sub     eax, [rbp+47h+var_A0]
0x180021ac8  add     eax, [rcx]
0x180021aca  cdq
0x180021acb  sub     eax, edx
0x180021acd  sar     eax, 1
0x180021acf  mov     r10d, eax
0x180021ad2  jmp     short loc_180021ADA
0x180021ad4  mov     r10d, [rcx]
0x180021ad7  add     r10d, edx
0x180021ada  lea     r11d, [r10+rsi]
0x180021ade  mov     dword ptr [rbp+47h+var_80], r11d
0x180021ae2  test    r15, r15
0x180021ae5  jz      loc_180021B76
0x180021aeb  test    esi, esi
0x180021aed  jz      short loc_180021B4D
0x180021aef  cmp     r10d, [rcx]
0x180021af2  jle     short loc_180021B45
0x180021af4  mov     r9, [r15+10h]; hIcon
0x180021af8  test    r9, r9
0x180021afb  jz      short loc_180021B45
0x180021afd  mov     ecx, [r15+1Ch]
0x180021b01  mov     eax, [rbp+47h+qrc.bottom]
0x180021b04  sub     eax, ecx
0x180021b06  mov     [rsp+0F0h+diFlags], 3; diFlags
0x180021b0e  sub     eax, [rbp+47h+qrc.top]
0x180021b11  cdq
0x180021b12  mov     [rsp+0F0h+hbrFlickerFreeDraw], r8; hbrFlickerFreeDraw
0x180021b17  sub     eax, edx
0x180021b19  mov     [rsp+0F0h+istepIfAniCur], r8d; istepIfAniCur
0x180021b1e  mov     [rsp+0F0h+rop], ecx; cyWidth
0x180021b22  mov     edx, r10d; xLeft
0x180021b25  mov     ecx, [r15+18h]
0x180021b29  sar     eax, 1
0x180021b2b  add     eax, [rbp+47h+qrc.top]
0x180021b2e  mov     [rsp+0F0h+h], ecx; cxWidth
0x180021b32  mov     r8d, eax; yTop
0x180021b35  mov     rcx, rbx; hdc
0x180021b38  call    cs:__imp_DrawIconEx
0x180021b3e  mov     r11d, dword ptr [rbp+47h+var_80]
0x180021b42  xor     r8d, r8d
0x180021b45  mov     ecx, r11d
0x180021b48  mov     [rbp+47h+qrc.left], ecx
0x180021b4b  jmp     short loc_180021B50
0x180021b4d  mov     ecx, [rbp+47h+qrc.left]
0x180021b50  cmp     [rdi], r8w
0x180021b54  jnz     short loc_180021B64
0x180021b56  test    esi, esi
0x180021b58  jz      short loc_180021B64
0x180021b5a  mov     dword ptr [r15+28h], 1
0x180021b62  jmp     short loc_180021B76
0x180021b64  mov     eax, [rbp+47h+qrc.right]
0x180021b67  sub     eax, ecx
0x180021b69  mov     ecx, r8d
0x180021b6c  cmp     [rbp+47h+var_A0], eax
0x180021b6f  setnl   cl
0x180021b72  mov     [r15+28h], ecx
0x180021b76  mov     eax, [rbp+47h+qrc.top]
0x180021b79  mov     rcx, rbx; hdc
0x180021b7c  sub     eax, dword ptr [rbp+47h+var_94]
0x180021b7f  add     eax, [rbp+47h+qrc.bottom]
0x180021b82  mov     r9d, [rbp+47h+options]; options
0x180021b86  cdq
0x180021b87  sub     eax, edx
0x180021b89  mov     [rsp+0F0h+hbrFlickerFreeDraw], 0; lpDx
0x180021b92  sar     eax, 1
0x180021b94  mov     edx, r11d; x
0x180021b97  mov     r8d, eax; y
0x180021b9a  mov     rax, qword ptr [rbp+47h+c]
0x180021b9e  mov     [rsp+0F0h+istepIfAniCur], eax; c
0x180021ba2  lea     rax, [rbp+47h+qrc]
0x180021ba6  mov     qword ptr [rsp+0F0h+rop], rdi; lpString
0x180021bab  mov     qword ptr [rsp+0F0h+h], rax; lprect
0x180021bb0  call    cs:__imp_ExtTextOutW
0x180021bb6  xor     eax, eax
0x180021bb8  cmp     dword ptr [rbp+47h+var_94+4], eax
0x180021bbb  jnz     short loc_180021BD8
0x180021bbd  mov     [rbp+47h+options], 4
0x180021bc4  mov     rdi, r14
0x180021bc7  inc     r12d
0x180021bca  add     rdi, 2
0x180021bce  cmp     r12d, 3
0x180021bd2  jl      loc_180021A15
0x180021bd8  mov     r15, [rbp+47h+ho]
0x180021bdc  cmp     [rbp+47h+var_78], eax
0x180021bdf  jz      short loc_180021BED
0x180021be1  mov     edx, [rbp+47h+align]; align
0x180021be4  mov     rcx, rbx; hdc
0x180021be7  call    cs:__imp_SetTextAlign
0x180021bed  mov     edx, [rbp+47h+color]; color
0x180021bf0  mov     rcx, rbx; hdc
0x180021bf3  call    cs:__imp_SetTextColor
0x180021bf9  mov     edx, [rbp+47h+var_88]; color
0x180021bfc  mov     rcx, rbx; hdc
0x180021bff  call    cs:__imp_SetBkColor
0x180021c05  mov     edx, [rbp+47h+mode]; mode
0x180021c08  mov     rcx, rbx; hdc
0x180021c0b  call    cs:__imp_SetBkMode
0x180021c11  test    r15, r15
0x180021c14  jz      short loc_180021C1F
0x180021c16  mov     rcx, r15; ho
0x180021c19  call    cs:__imp_DeleteObject
0x180021c1f  mov     rcx, [rbp+47h+var_48]
0x180021c23  xor     rcx, rsp; StackCookie
0x180021c26  call    __security_check_cookie
0x180021c2b  add     rsp, 0B8h
0x180021c32  pop     r15
0x180021c34  pop     r14
0x180021c36  pop     r13
0x180021c38  pop     r12
0x180021c3a  pop     rdi
0x180021c3b  pop     rsi
0x180021c3c  pop     rbx
0x180021c3d  pop     rbp
0x180021c3e  retn
```
