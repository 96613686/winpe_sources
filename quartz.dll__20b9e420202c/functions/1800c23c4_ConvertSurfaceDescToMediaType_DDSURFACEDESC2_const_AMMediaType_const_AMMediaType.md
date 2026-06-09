# ConvertSurfaceDescToMediaType(_DDSURFACEDESC2 * const,_AMMediaType const *,_AMMediaType * *)

- ea: `0x1800c23c4`
- end: `0x1800c286e`
- name: `?ConvertSurfaceDescToMediaType@@YAJQEAU_DDSURFACEDESC2@@PEBU_AMMediaType@@PEAPEAU2@@Z`
- size: `1194`
- prototype: `int(struct _DDSURFACEDESC2 *const, const struct _AMMediaType *, struct _AMMediaType **)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800abe54`
- `0x1800ae3d8`
- `0x1800b01d0`
- `0x1800b5a48`

## callees

- `0x180026424`
- `0x18002f03c`
- `0x1800c1fcc`
- `0x1800c23c4`
- `0x1800c2b70`
- `0x180144134`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800c273f`
- `USER32!IsRectEmpty` at `0x1800c2770`
- `USER32!IsRectEmpty` at `0x1800c27fe`
- `USER32!IsRectEmpty` at `0x1800c282f`
- `USER32!IsRectEmpty` at `0x1800c273f`
- `USER32!IsRectEmpty` at `0x1800c2770`
- `USER32!IsRectEmpty` at `0x1800c27fe`
- `USER32!IsRectEmpty` at `0x1800c282f`

## pseudocode

```c
__int64 __fastcall ConvertSurfaceDescToMediaType(
        struct _DDSURFACEDESC2 *const a1,
        struct _AMMediaType *a2,
        struct _AMMediaType **a3)
{
  __int64 v5; // rax
  __int64 v7; // rax
  __int64 result; // rax
  const struct _AMMediaType *v9; // rdx
  unsigned int v10; // r15d
  struct tagBITMAPINFOHEADER *v11; // rax
  const struct _AMMediaType *v12; // rdx
  struct _AMMediaType *v13; // rcx
  struct tagBITMAPINFOHEADER *v14; // r10
  DWORD *p_dwFourCC; // r9
  LONG lPitch; // r8d
  signed int dwRGBBitCount; // eax
  int v18; // ecx
  DWORD dwWidth; // eax
  signed int v20; // ebp
  WORD v21; // r11
  DWORD v22; // r9d
  struct tagBITMAPINFOHEADER *v23; // rax
  __int64 *v24; // rcx
  bool v25; // zf
  unsigned int v26; // eax
  unsigned int *BitMasks; // rax
  __int64 v28; // r10
  DWORD dwFlags; // ecx
  __int16 v30; // ax
  GUID v31; // xmm0
  _QWORD *v32; // rbx
  __int64 v33; // rax
  BYTE *v34; // rsi
  const RECT *v35; // rbx
  int *v36; // rdi
  int right; // ecx
  int v38; // eax
  int top; // ecx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  __int64 v45; // rax
  BYTE *pbFormat; // rsi
  int *v47; // rdi
  int left; // ecx
  int v49; // eax
  int bottom; // ecx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  char v55[72]; // [rsp+20h] [rbp-48h] BYREF

  *a3 = 0;
  v5 = *(_QWORD *)&a2->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v5 )
    v5 = *(_QWORD *)a2->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( v5 || a2->cbFormat < 0x58 )
  {
    v7 = *(_QWORD *)&a2->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)a2->formattype.Data4 - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v7 || a2->cbFormat < 0x70 )
      return 2147942487LL;
  }
  result = VMR9::AllocVideoMediaType((VMR9 *)a2, (const struct _AMMediaType *)a3, a3);
  v10 = result;
  if ( (int)result >= 0 )
  {
    v11 = VMR9::GetbmiHeader((VMR9 *)*a3, v9);
    v14 = v11;
    if ( !v11 )
    {
      FreeMediaType(v13);
      return 2147500037LL;
    }
    v11->biSize = 40;
    p_dwFourCC = &a1->ddpfPixelFormat.dwFourCC;
    if ( (a1->dwFlags & 8) != 0 )
    {
      lPitch = a1->lPitch;
      v11->biWidth = lPitch;
      if ( *p_dwFourCC == 808530000 || *p_dwFourCC == 909193296 )
      {
        v18 = 2;
      }
      else
      {
        dwRGBBitCount = a1->ddpfPixelFormat.dwRGBBitCount;
        if ( ((dwRGBBitCount - 8) & 0xFFFFFFE7) != 0 )
        {
LABEL_22:
          v20 = -a1->dwHeight;
          v14->biPlanes = 1;
          v14->biHeight = v20;
          v21 = *((_WORD *)&a1->dwFVF + 6);
          v14->biBitCount = v21;
          v22 = *p_dwFourCC;
          v14->biCompression = v22;
          *(_QWORD *)&v14->biClrUsed = 0;
          if ( v22 )
            goto LABEL_38;
          v23 = VMR9::GetbmiHeader((VMR9 *)a2, v12);
          v24 = qword_1801A2450;
          if ( v23 )
            v24 = (__int64 *)v23;
          if ( ((v21 - 16) & 0xFFEF) != 0 )
            goto LABEL_38;
          if ( *((_DWORD *)v24 + 4) == v22 + 3 )
            goto LABEL_37;
          if ( v21 == 32 )
          {
            if ( a1->ddpfPixelFormat.dwRBitMask == 16711680 && a1->ddpfPixelFormat.dwGBitMask == 65280 )
            {
              v25 = a1->ddpfPixelFormat.dwBBitMask == 255;
              goto LABEL_31;
            }
          }
          else
          {
            if ( v21 != 16 )
              goto LABEL_38;
            if ( a1->ddpfPixelFormat.dwRBitMask == 31744 && a1->ddpfPixelFormat.dwGBitMask == 992 )
            {
              v25 = a1->ddpfPixelFormat.dwBBitMask == 31;
LABEL_31:
              if ( v25 )
                goto LABEL_40;
            }
          }
LABEL_37:
          v14->biCompression = v22 + 3;
          v22 += 3;
LABEL_38:
          if ( v21 <= 8u )
            v14->biClrUsed = 1 << v21;
LABEL_40:
          v26 = -(v20 * (((v14->biWidth * (unsigned int)v21 + 31) >> 3) & 0x1FFFFFFC));
          if ( v20 >= 0 )
            v26 = v20 * (((v14->biWidth * (unsigned int)v21 + 31) >> 3) & 0x1FFFFFFC);
          v14->biSizeImage = v26;
          if ( v22 && v21 > 8u )
          {
            BitMasks = (unsigned int *)GetBitMasks(v14);
            *BitMasks = a1->ddpfPixelFormat.dwRBitMask;
            BitMasks[1] = a1->ddpfPixelFormat.dwGBitMask;
            BitMasks[2] = a1->ddpfPixelFormat.dwBBitMask;
          }
          (*a3)->subtype = *(GUID *)GetBitmapSubtype(v55, v14);
          dwFlags = a1->ddpfPixelFormat.dwFlags;
          if ( (a1->ddsCaps.dwCaps & 0x2000) != 0 )
          {
            if ( (dwFlags & 0x40) == 0 )
              goto LABEL_72;
            v30 = *(_WORD *)(v28 + 14);
            if ( (dwFlags & 1) != 0 )
            {
              if ( v30 == 16 )
              {
                if ( a1->ddpfPixelFormat.dwRGBAlphaBitMask == 0x8000 )
                {
                  v31 = MEDIASUBTYPE_ARGB1555_D3D_DX7_RT;
                }
                else
                {
                  if ( a1->ddpfPixelFormat.dwRGBAlphaBitMask != 61440 )
                    goto LABEL_72;
                  v31 = MEDIASUBTYPE_ARGB4444_D3D_DX7_RT;
                }
              }
              else
              {
                if ( v30 != 32 )
                  goto LABEL_72;
                v31 = MEDIASUBTYPE_ARGB32_D3D_DX7_RT;
              }
            }
            else if ( v30 == 16 )
            {
              v31 = MEDIASUBTYPE_RGB16_D3D_DX7_RT;
            }
            else
            {
              if ( v30 != 32 )
                goto LABEL_72;
              v31 = MEDIASUBTYPE_RGB32_D3D_DX7_RT;
            }
          }
          else
          {
            if ( (dwFlags & 1) == 0 )
              goto LABEL_72;
            if ( (dwFlags & 0x40) != 0 )
            {
              if ( *(_WORD *)(v28 + 14) == 16 )
              {
                if ( a1->ddpfPixelFormat.dwRGBAlphaBitMask == 0x8000 )
                {
                  v31 = MEDIASUBTYPE_ARGB1555;
                }
                else
                {
                  if ( a1->ddpfPixelFormat.dwRGBAlphaBitMask != 61440 )
                    goto LABEL_72;
                  v31 = MEDIASUBTYPE_ARGB4444;
                }
              }
              else
              {
                if ( *(_WORD *)(v28 + 14) != 32 )
                  goto LABEL_72;
                v31 = MEDIASUBTYPE_ARGB32;
              }
            }
            else
            {
              if ( (dwFlags & 4) == 0 || *(_WORD *)(v28 + 14) != 32 )
              {
LABEL_72:
                (*a3)->lSampleSize = *(_DWORD *)(v28 + 20);
                v32 = *a3;
                v33 = *(_QWORD *)&(*a3)->formattype.Data1 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
                if ( !v33 )
                  v33 = *(_QWORD *)((char *)v32 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
                if ( v33 )
                {
                  v45 = *(_QWORD *)((char *)v32 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
                  if ( !v45 )
                    v45 = *(_QWORD *)((char *)v32 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
                  if ( v45 )
                    return v10;
                  pbFormat = a2->pbFormat;
                  v35 = (const RECT *)v32[10];
                  v47 = (int *)(pbFormat + 76);
                  left = -v35[5].left;
                  if ( v35[5].left > 0 )
                    left = v35[5].left;
                  v49 = -*((_DWORD *)pbFormat + 20);
                  if ( *((int *)pbFormat + 20) > 0 )
                    v49 = *((_DWORD *)pbFormat + 20);
                  if ( left == v49 )
                  {
                    bottom = -v35[4].bottom;
                    if ( v35[4].bottom > 0 )
                      bottom = v35[4].bottom;
                    v51 = -*v47;
                    if ( *v47 > 0 )
                      v51 = *v47;
                    if ( bottom == v51 )
                      return v10;
                  }
                  if ( IsRectEmpty(v35) )
                  {
                    *(_QWORD *)&v35->left = 0;
                    v52 = -*v47;
                    if ( *v47 > 0 )
                      v52 = *v47;
                    v35->right = v52;
                    v53 = -*((_DWORD *)pbFormat + 20);
                    if ( *((int *)pbFormat + 20) > 0 )
                      v53 = *((_DWORD *)pbFormat + 20);
                    v35->bottom = v53;
                  }
                  if ( !IsRectEmpty(v35 + 1) )
                    return v10;
                  *(_QWORD *)&v35[1].left = 0;
                  v54 = -*v47;
                  if ( *v47 > 0 )
                    v54 = *v47;
                  v35[1].right = v54;
                  v44 = -*((_DWORD *)pbFormat + 20);
                  if ( *((int *)pbFormat + 20) > 0 )
                    v44 = *((_DWORD *)pbFormat + 20);
                }
                else
                {
                  v34 = a2->pbFormat;
                  v35 = (const RECT *)v32[10];
                  v36 = (int *)(v34 + 52);
                  right = -v35[3].right;
                  if ( v35[3].right > 0 )
                    right = v35[3].right;
                  v38 = -*((_DWORD *)v34 + 14);
                  if ( *((int *)v34 + 14) > 0 )
                    v38 = *((_DWORD *)v34 + 14);
                  if ( right == v38 )
                  {
                    top = -v35[3].top;
                    if ( v35[3].top > 0 )
                      top = v35[3].top;
                    v40 = -*v36;
                    if ( *v36 > 0 )
                      v40 = *v36;
                    if ( top == v40 )
                      return v10;
                  }
                  if ( IsRectEmpty(v35) )
                  {
                    *(_QWORD *)&v35->left = 0;
                    v41 = -*v36;
                    if ( *v36 > 0 )
                      v41 = *v36;
                    v35->right = v41;
                    v42 = -*((_DWORD *)v34 + 14);
                    if ( *((int *)v34 + 14) > 0 )
                      v42 = *((_DWORD *)v34 + 14);
                    v35->bottom = v42;
                  }
                  if ( !IsRectEmpty(v35 + 1) )
                    return v10;
                  *(_QWORD *)&v35[1].left = 0;
                  v43 = -*v36;
                  if ( *v36 > 0 )
                    v43 = *v36;
                  v35[1].right = v43;
                  v44 = -*((_DWORD *)v34 + 14);
                  if ( *((int *)v34 + 14) > 0 )
                    v44 = *((_DWORD *)v34 + 14);
                }
                v35[1].bottom = v44;
                return v10;
              }
              v31 = MEDIASUBTYPE_AYUV;
            }
          }
          (*a3)->subtype = v31;
          goto LABEL_72;
        }
        v18 = dwRGBBitCount / 8;
      }
      v12 = (const struct _AMMediaType *)(unsigned int)(lPitch >> 31);
      LODWORD(v12) = lPitch % v18;
      dwWidth = lPitch / v18;
    }
    else
    {
      dwWidth = a1->dwWidth;
    }
    v14->biWidth = dwWidth;
    goto LABEL_22;
  }
  return result;
}

```

## disassembly

```asm
0x1800c23c4  push    rbx
0x1800c23c6  push    rbp
0x1800c23c7  push    rsi
0x1800c23c8  push    rdi
0x1800c23c9  push    r14
0x1800c23cb  push    r15
0x1800c23cd  sub     rsp, 38h
0x1800c23d1  mov     qword ptr [r8], 0
0x1800c23d8  mov     rdi, r8
0x1800c23db  mov     rax, [rdx+2Ch]
0x1800c23df  mov     rsi, rdx
0x1800c23e2  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800c23e9  mov     rbx, rcx
0x1800c23ec  jnz     short loc_1800C23F9
0x1800c23ee  mov     rax, [rdx+34h]
0x1800c23f2  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800c23f9  test    rax, rax
0x1800c23fc  jnz     short loc_1800C2404
0x1800c23fe  cmp     dword ptr [rdx+48h], 58h ; 'X'
0x1800c2402  jnb     short loc_1800C2431
0x1800c2404  mov     rax, [rdx+2Ch]
0x1800c2408  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800c240f  jnz     short loc_1800C241C
0x1800c2411  mov     rax, [rdx+34h]
0x1800c2415  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800c241c  test    rax, rax
0x1800c241f  jnz     short loc_1800C2427
0x1800c2421  cmp     dword ptr [rdx+48h], 70h ; 'p'
0x1800c2425  jnb     short loc_1800C2431
0x1800c2427  mov     eax, 80070057h
0x1800c242c  jmp     loc_1800C2860
0x1800c2431  mov     rdx, rdi; struct _AMMediaType *
0x1800c2434  mov     rcx, rsi; this
0x1800c2437  call    ?AllocVideoMediaType@VMR9@@YAJPEBU_AMMediaType@@PEAPEAU2@@Z; VMR9::AllocVideoMediaType(_AMMediaType const *,_AMMediaType * *)
0x1800c243c  mov     r15d, eax
0x1800c243f  test    eax, eax
0x1800c2441  js      loc_1800C2860
0x1800c2447  mov     rcx, [rdi]; this
0x1800c244a  call    ?GetbmiHeader@VMR9@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; VMR9::GetbmiHeader(_AMMediaType const *)
0x1800c244f  mov     r10, rax
0x1800c2452  test    rax, rax
0x1800c2455  jnz     short loc_1800C2466
0x1800c2457  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800c245c  mov     eax, 80004005h
0x1800c2461  jmp     loc_1800C2860
0x1800c2466  mov     r11d, 8
0x1800c246c  mov     dword ptr [rax], 28h ; '('
0x1800c2472  lea     r9, [rbx+58h]
0x1800c2476  test    [rbx+4], r11b
0x1800c247a  jz      short loc_1800C24B9
0x1800c247c  mov     r8d, [rbx+10h]
0x1800c2480  mov     [rax+4], r8d
0x1800c2484  cmp     dword ptr [r9], 30313050h
0x1800c248b  jz      short loc_1800C24B2
0x1800c248d  cmp     dword ptr [r9], 36313050h
0x1800c2494  jz      short loc_1800C24B2
0x1800c2496  mov     eax, [rbx+5Ch]
0x1800c2499  lea     ecx, [rax-8]
0x1800c249c  test    ecx, 0FFFFFFE7h
0x1800c24a2  jnz     short loc_1800C24C0
0x1800c24a4  cdq
0x1800c24a5  idiv    r11d
0x1800c24a8  mov     ecx, eax
0x1800c24aa  mov     eax, r8d
0x1800c24ad  cdq
0x1800c24ae  idiv    ecx
0x1800c24b0  jmp     short loc_1800C24BC
0x1800c24b2  mov     ecx, 2
0x1800c24b7  jmp     short loc_1800C24AA
0x1800c24b9  mov     eax, [rbx+0Ch]
0x1800c24bc  mov     [r10+4], eax
0x1800c24c0  mov     ebp, [rbx+8]
0x1800c24c3  mov     eax, 1
0x1800c24c8  neg     ebp
0x1800c24ca  mov     [r10+0Ch], ax
0x1800c24cf  mov     [r10+8], ebp
0x1800c24d3  mov     r14w, 20h ; ' '
0x1800c24d8  movzx   r11d, word ptr [rbx+5Ch]
0x1800c24dd  mov     [r10+0Eh], r11w
0x1800c24e2  mov     r9d, [r9]
0x1800c24e5  mov     [r10+10h], r9d
0x1800c24e9  mov     qword ptr [r10+20h], 0
0x1800c24f1  test    r9d, r9d
0x1800c24f4  jnz     loc_1800C257A
0x1800c24fa  mov     rcx, rsi; this
0x1800c24fd  call    ?GetbmiHeader@VMR9@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; VMR9::GetbmiHeader(_AMMediaType const *)
0x1800c2502  test    rax, rax
0x1800c2505  lea     rcx, qword_1801A2450
0x1800c250c  mov     edx, 0FFEFh
0x1800c2511  cmovnz  rcx, rax
0x1800c2515  lea     eax, [r11-10h]
0x1800c2519  test    dx, ax
0x1800c251c  jnz     short loc_1800C2575
0x1800c251e  lea     eax, [r9+3]
0x1800c2522  cmp     [rcx+10h], eax
0x1800c2525  jz      short loc_1800C256E
0x1800c2527  cmp     r11w, r14w
0x1800c252b  jnz     short loc_1800C254F
0x1800c252d  cmp     dword ptr [rbx+60h], 0FF0000h
0x1800c2534  jnz     short loc_1800C256E
0x1800c2536  cmp     dword ptr [rbx+64h], 0FF00h
0x1800c253d  jnz     short loc_1800C256E
0x1800c253f  cmp     dword ptr [rbx+68h], 0FFh
0x1800c2546  jnz     short loc_1800C256E
0x1800c2548  mov     edx, 8
0x1800c254d  jmp     short loc_1800C258E
0x1800c254f  cmp     r11w, 10h
0x1800c2554  jnz     short loc_1800C2575
0x1800c2556  cmp     dword ptr [rbx+60h], 7C00h
0x1800c255d  jnz     short loc_1800C256E
0x1800c255f  cmp     dword ptr [rbx+64h], 3E0h
0x1800c2566  jnz     short loc_1800C256E
0x1800c2568  cmp     dword ptr [rbx+68h], 1Fh
0x1800c256c  jmp     short loc_1800C2546
0x1800c256e  mov     [r10+10h], eax
0x1800c2572  mov     r9d, eax
0x1800c2575  mov     eax, 1
0x1800c257a  mov     edx, 8
0x1800c257f  cmp     r11w, dx
0x1800c2583  ja      short loc_1800C258E
0x1800c2585  mov     ecx, r11d
0x1800c2588  shl     eax, cl
0x1800c258a  mov     [r10+20h], eax
0x1800c258e  movzx   ecx, r11w
0x1800c2592  imul    ecx, [r10+4]
0x1800c2597  add     ecx, 1Fh
0x1800c259a  shr     ecx, 3
0x1800c259d  and     ecx, 1FFFFFFCh
0x1800c25a3  imul    ecx, ebp
0x1800c25a6  mov     eax, ecx
0x1800c25a8  neg     eax
0x1800c25aa  test    ebp, ebp
0x1800c25ac  cmovns  eax, ecx
0x1800c25af  mov     [r10+14h], eax
0x1800c25b3  test    r9d, r9d
0x1800c25b6  jz      short loc_1800C25D7
0x1800c25b8  cmp     r11w, dx
0x1800c25bc  jbe     short loc_1800C25D7
0x1800c25be  mov     rcx, r10; struct tagBITMAPINFOHEADER *
0x1800c25c1  call    ?GetBitMasks@@YAPEBKPEBUtagBITMAPINFOHEADER@@@Z; GetBitMasks(tagBITMAPINFOHEADER const *)
0x1800c25c6  mov     ecx, [rbx+60h]
0x1800c25c9  mov     [rax], ecx
0x1800c25cb  mov     ecx, [rbx+64h]
0x1800c25ce  mov     [rax+4], ecx
0x1800c25d1  mov     ecx, [rbx+68h]
0x1800c25d4  mov     [rax+8], ecx
0x1800c25d7  mov     rdx, r10
0x1800c25da  lea     rcx, [rsp+68h+var_48]
0x1800c25df  call    GetBitmapSubtype
0x1800c25e4  movups  xmm1, xmmword ptr [rax]
0x1800c25e7  mov     rax, [rdi]
0x1800c25ea  movdqu  xmmword ptr [rax+10h], xmm1
0x1800c25ef  test    dword ptr [rbx+70h], 2000h
0x1800c25f6  mov     ecx, [rbx+54h]
0x1800c25f9  jz      short loc_1800C2673
0x1800c25fb  test    cl, 40h
0x1800c25fe  jz      loc_1800C26D4
0x1800c2604  movzx   eax, word ptr [r10+0Eh]
0x1800c2609  test    cl, 1
0x1800c260c  jz      short loc_1800C2655
0x1800c260e  cmp     ax, 10h
0x1800c2612  jz      short loc_1800C262A
0x1800c2614  cmp     ax, r14w
0x1800c2618  jnz     loc_1800C26D4
0x1800c261e  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB32_D3D_DX7_RT.Data1
0x1800c2625  jmp     loc_1800C26CC
0x1800c262a  cmp     dword ptr [rbx+6Ch], 8000h
0x1800c2631  jz      short loc_1800C264C
0x1800c2633  cmp     dword ptr [rbx+6Ch], 0F000h
0x1800c263a  jnz     loc_1800C26D4
0x1800c2640  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB4444_D3D_DX7_RT.Data1
0x1800c2647  jmp     loc_1800C26CC
0x1800c264c  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB1555_D3D_DX7_RT.Data1
0x1800c2653  jmp     short loc_1800C26CC
0x1800c2655  cmp     ax, 10h
0x1800c2659  jz      short loc_1800C266A
0x1800c265b  cmp     ax, r14w
0x1800c265f  jnz     short loc_1800C26D4
0x1800c2661  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_RGB32_D3D_DX7_RT.Data1
0x1800c2668  jmp     short loc_1800C26CC
0x1800c266a  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_RGB16_D3D_DX7_RT.Data1
0x1800c2671  jmp     short loc_1800C26CC
0x1800c2673  test    cl, 1
0x1800c2676  jz      short loc_1800C26D4
0x1800c2678  test    cl, 40h
0x1800c267b  jz      short loc_1800C26B9
0x1800c267d  cmp     word ptr [r10+0Eh], 10h
0x1800c2683  jz      short loc_1800C2695
0x1800c2685  cmp     [r10+0Eh], r14w
0x1800c268a  jnz     short loc_1800C26D4
0x1800c268c  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB32.Data1
0x1800c2693  jmp     short loc_1800C26CC
0x1800c2695  cmp     dword ptr [rbx+6Ch], 8000h
0x1800c269c  jz      short loc_1800C26B0
0x1800c269e  cmp     dword ptr [rbx+6Ch], 0F000h
0x1800c26a5  jnz     short loc_1800C26D4
0x1800c26a7  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB4444.Data1
0x1800c26ae  jmp     short loc_1800C26CC
0x1800c26b0  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB1555.Data1
0x1800c26b7  jmp     short loc_1800C26CC
0x1800c26b9  test    cl, 4
0x1800c26bc  jz      short loc_1800C26D4
0x1800c26be  cmp     [r10+0Eh], r14w
0x1800c26c3  jnz     short loc_1800C26D4
0x1800c26c5  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_AYUV.Data1
0x1800c26cc  mov     rax, [rdi]
0x1800c26cf  movdqu  xmmword ptr [rax+10h], xmm0
0x1800c26d4  mov     eax, [r10+14h]
0x1800c26d8  mov     rcx, [rdi]
0x1800c26db  mov     [rcx+28h], eax
0x1800c26de  mov     rbx, [rdi]
0x1800c26e1  mov     rax, [rbx+2Ch]
0x1800c26e5  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800c26ec  jnz     short loc_1800C26F9
0x1800c26ee  mov     rax, [rbx+34h]
0x1800c26f2  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800c26f9  test    rax, rax
0x1800c26fc  jnz     loc_1800C27A4
0x1800c2702  mov     rsi, [rsi+50h]
0x1800c2706  mov     rbx, [rbx+50h]
0x1800c270a  mov     eax, [rsi+38h]
0x1800c270d  lea     rdi, [rsi+34h]
0x1800c2711  mov     ecx, [rbx+38h]
0x1800c2714  neg     ecx
0x1800c2716  cmovs   ecx, [rbx+38h]
0x1800c271a  neg     eax
0x1800c271c  cmovs   eax, [rsi+38h]
0x1800c2720  cmp     ecx, eax
0x1800c2722  jnz     short loc_1800C273C
0x1800c2724  mov     ecx, [rbx+34h]
0x1800c2727  mov     eax, [rdi]
0x1800c2729  neg     ecx
0x1800c272b  cmovs   ecx, [rbx+34h]
0x1800c272f  neg     eax
0x1800c2731  cmovs   eax, [rdi]
0x1800c2734  cmp     ecx, eax
0x1800c2736  jz      loc_1800C285D
0x1800c273c  mov     rcx, rbx; lprc
0x1800c273f  call    cs:__imp_IsRectEmpty
0x1800c2746  nop     dword ptr [rax+rax+00h]
0x1800c274b  test    eax, eax
0x1800c274d  jz      short loc_1800C276C
0x1800c274f  mov     qword ptr [rbx], 0
0x1800c2756  mov     eax, [rdi]
0x1800c2758  neg     eax
0x1800c275a  cmovs   eax, [rdi]
0x1800c275d  mov     [rbx+8], eax
0x1800c2760  mov     eax, [rsi+38h]
0x1800c2763  neg     eax
0x1800c2765  cmovs   eax, [rsi+38h]
0x1800c2769  mov     [rbx+0Ch], eax
0x1800c276c  lea     rcx, [rbx+10h]; lprc
0x1800c2770  call    cs:__imp_IsRectEmpty
0x1800c2777  nop     dword ptr [rax+rax+00h]
0x1800c277c  test    eax, eax
0x1800c277e  jz      loc_1800C285D
0x1800c2784  mov     qword ptr [rbx+10h], 0
0x1800c278c  mov     eax, [rdi]
0x1800c278e  neg     eax
0x1800c2790  cmovs   eax, [rdi]
0x1800c2793  mov     [rbx+18h], eax
0x1800c2796  mov     eax, [rsi+38h]
0x1800c2799  neg     eax
0x1800c279b  cmovs   eax, [rsi+38h]
0x1800c279f  jmp     loc_1800C285A
0x1800c27a4  mov     rax, [rbx+2Ch]
0x1800c27a8  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800c27af  jnz     short loc_1800C27BC
0x1800c27b1  mov     rax, [rbx+34h]
0x1800c27b5  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800c27bc  test    rax, rax
0x1800c27bf  jnz     loc_1800C285D
0x1800c27c5  mov     rsi, [rsi+50h]
0x1800c27c9  mov     rbx, [rbx+50h]
0x1800c27cd  mov     eax, [rsi+50h]
0x1800c27d0  lea     rdi, [rsi+4Ch]
0x1800c27d4  mov     ecx, [rbx+50h]
0x1800c27d7  neg     ecx
0x1800c27d9  cmovs   ecx, [rbx+50h]
0x1800c27dd  neg     eax
0x1800c27df  cmovs   eax, [rsi+50h]
0x1800c27e3  cmp     ecx, eax
0x1800c27e5  jnz     short loc_1800C27FB
0x1800c27e7  mov     ecx, [rbx+4Ch]
0x1800c27ea  mov     eax, [rdi]
0x1800c27ec  neg     ecx
0x1800c27ee  cmovs   ecx, [rbx+4Ch]
0x1800c27f2  neg     eax
0x1800c27f4  cmovs   eax, [rdi]
0x1800c27f7  cmp     ecx, eax
0x1800c27f9  jz      short loc_1800C285D
0x1800c27fb  mov     rcx, rbx; lprc
0x1800c27fe  call    cs:__imp_IsRectEmpty
0x1800c2805  nop     dword ptr [rax+rax+00h]
0x1800c280a  test    eax, eax
0x1800c280c  jz      short loc_1800C282B
0x1800c280e  mov     qword ptr [rbx], 0
0x1800c2815  mov     eax, [rdi]
0x1800c2817  neg     eax
0x1800c2819  cmovs   eax, [rdi]
  ... truncated ...
```
