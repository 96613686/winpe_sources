# DoRotatedStretchBlt

- ea: `0x1801432b0`
- end: `0x18014389d`
- name: `DoRotatedStretchBlt`
- size: `1517`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int hDest, int, __int16, __int16, int, int, __int64, int, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b1afc`

## callees

- `0x1800afb24`
- `0x1800b0ff0`
- `0x1800b1ee8`
- `0x1800b1fa8`
- `0x1800d4f9c`
- `0x1800e9380`
- `0x1801432b0`
- `0x180143e78`
- `0x1801440d0`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180143533`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180143533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014386c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18014386c`
- `GDI32!OffsetViewportOrgEx` at `0x180143651`
- `GDI32!OffsetViewportOrgEx` at `0x180143651`
- `GDI32!CreateDIBitmap` at `0x180143590`
- `GDI32!CreateDIBitmap` at `0x180143606`
- `GDI32!CreateDIBitmap` at `0x180143590`
- `GDI32!CreateDIBitmap` at `0x180143606`
- `GDI32!StretchBlt` at `0x1801436ab`
- `GDI32!StretchBlt` at `0x1801436ab`
- `GDI32!DeleteDC` at `0x180143809`
- `GDI32!DeleteDC` at `0x180143854`
- `GDI32!DeleteDC` at `0x180143809`
- `GDI32!DeleteDC` at `0x180143854`
- `GDI32!SelectObject` at `0x1801435b5`
- `GDI32!SelectObject` at `0x180143626`
- `GDI32!SelectObject` at `0x1801436c7`
- `GDI32!SelectObject` at `0x1801437d3`
- `GDI32!SelectObject` at `0x180143828`
- `GDI32!SelectObject` at `0x1801435b5`
- `GDI32!SelectObject` at `0x180143626`
- `GDI32!SelectObject` at `0x1801436c7`
- `GDI32!SelectObject` at `0x1801437d3`
- `GDI32!SelectObject` at `0x180143828`
- `GDI32!DeleteObject` at `0x1801437ee`
- `GDI32!DeleteObject` at `0x180143840`
- `GDI32!DeleteObject` at `0x1801437ee`
- `GDI32!DeleteObject` at `0x180143840`

## pseudocode

```c
__int64 __fastcall DoRotatedStretchBlt(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int hDest,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        XFORM *a11,
        UINT a12,
        const BITMAPINFO *a13,
        SIZE_T uBytes,
        const void *a15)
{
  int v16; // r15d
  HDC v18; // r14
  int v19; // eax
  int v20; // eax
  int v21; // esi
  int v22; // eax
  int v23; // edi
  int v24; // eax
  int v25; // eax
  int v26; // edi
  int v27; // r12d
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  unsigned int v36; // r15d
  unsigned int v37; // r13d
  SIZE_T v38; // rdx
  BITMAPINFO *v39; // rax
  const BITMAPINFO *pbmi; // r14
  HBITMAP DIBitmap; // rax
  HBITMAP v42; // rax
  BOOL v43; // eax
  HDC v44; // rdx
  __int64 v45; // r8
  HBITMAP v46; // rdi
  unsigned int v47; // eax
  __int64 v48; // r8
  __int16 iUsage; // [rsp+28h] [rbp-D8h]
  int xSrc; // [rsp+30h] [rbp-D0h]
  int ySrc; // [rsp+38h] [rbp-C8h]
  int wSrc; // [rsp+40h] [rbp-C0h]
  __int16 hSrc; // [rsp+48h] [rbp-B8h]
  int v54; // [rsp+60h] [rbp-A0h]
  HDC hdc; // [rsp+68h] [rbp-98h]
  HDC hdca; // [rsp+68h] [rbp-98h]
  HBITMAP ho; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  unsigned int v59; // [rsp+7Ch] [rbp-84h]
  HDC hdcSrc; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+9Ch] [rbp-64h]
  int v65; // [rsp+A0h] [rbp-60h]
  BITMAPINFO *hMem; // [rsp+A8h] [rbp-58h]
  HGDIOBJ h; // [rsp+B8h] [rbp-48h]
  HBITMAP v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+D8h] [rbp-28h] BYREF
  int v70; // [rsp+DCh] [rbp-24h]
  int v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E4h] [rbp-1Ch]
  int v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+ECh] [rbp-14h]
  int v75; // [rsp+F0h] [rbp-10h]
  int v76; // [rsp+F4h] [rbp-Ch]

  v59 = 0;
  if ( *(_DWORD *)(a1 + 484) )
  {
    if ( a6 == 13369376 )
    {
      v16 = 6684742;
    }
    else
    {
      if ( a6 != 15728673 )
      {
        *(_DWORD *)(a1 + 4) |= 0x40000000u;
        return 0;
      }
      v16 = 5898313;
    }
  }
  else
  {
    v16 = a6;
  }
  v70 = a3;
  v65 = a4 + a2;
  v18 = 0;
  v71 = a4 + a2;
  v73 = a4 + a2;
  v72 = a3;
  v69 = a2;
  v75 = a2;
  v58 = v16;
  hdcSrc = 0;
  h = 0;
  v68 = 0;
  hdc = 0;
  ho = 0;
  hMem = 0;
  v64 = a3 + hDest;
  v74 = a3 + hDest;
  v76 = a3 + hDest;
  if ( (unsigned int)bXformWorkhorse(&v69, 4, a1 + 228) )
  {
    v19 = v75;
    if ( v73 < v75 )
      v19 = v73;
    if ( v71 >= v19 )
    {
      v20 = v75;
      if ( v73 < v75 )
        v20 = v73;
    }
    else
    {
      v20 = v71;
    }
    v21 = v69;
    if ( v69 >= v20 )
    {
      v22 = v75;
      if ( v73 < v75 )
        v22 = v73;
      if ( v71 >= v22 )
      {
        v23 = v75;
        if ( v73 < v75 )
          v23 = v73;
        v54 = v23;
      }
      else
      {
        v54 = v71;
      }
    }
    else
    {
      v54 = v69;
    }
    v24 = v76;
    if ( v74 < v76 )
      v24 = v74;
    if ( v72 >= v24 )
    {
      v25 = v76;
      if ( v74 < v76 )
        v25 = v74;
    }
    else
    {
      v25 = v72;
    }
    v26 = v70;
    if ( v70 >= v25 )
    {
      v28 = v76;
      if ( v74 < v76 )
        v28 = v74;
      if ( v72 >= v28 )
      {
        v27 = v76;
        if ( v74 < v76 )
          v27 = v74;
      }
      else
      {
        v27 = v72;
      }
    }
    else
    {
      v27 = v70;
    }
    v29 = v75;
    if ( v73 > v75 )
      v29 = v73;
    if ( v71 <= v29 )
    {
      v30 = v75;
      if ( v73 > v75 )
        v30 = v73;
    }
    else
    {
      v30 = v71;
    }
    if ( v69 <= v30 )
    {
      v31 = v75;
      if ( v73 > v75 )
        v31 = v73;
      if ( v71 <= v31 )
      {
        v21 = v75;
        if ( v73 > v75 )
          v21 = v73;
      }
      else
      {
        v21 = v71;
      }
    }
    v32 = v76;
    if ( v74 > v76 )
      v32 = v74;
    if ( v72 <= v32 )
    {
      v33 = v76;
      if ( v74 > v76 )
        v33 = v74;
    }
    else
    {
      v33 = v72;
    }
    if ( v70 <= v33 )
    {
      v34 = v76;
      if ( v74 > v76 )
        v34 = v74;
      if ( v72 <= v34 )
      {
        v26 = v76;
        if ( v74 > v76 )
          v26 = v74;
      }
      else
      {
        v26 = v72;
      }
    }
    v35 = v16;
    v36 = v16 & 0xCCCC0000;
    v37 = 4 * (v35 & 0xF3330000);
    if ( v36 == v37 )
    {
LABEL_78:
      if ( (unsigned int)DoSaveDC(a1) )
      {
        if ( (unsigned int)DoClipRect(a1, a2, a3, v65, v64, 30) )
        {
          if ( v36 == v37 )
          {
            v47 = bW16Emit9(
                    a1,
                    v58,
                    (unsigned __int16)v54,
                    (unsigned __int16)v27,
                    (unsigned __int16)v21 - (unsigned __int16)v54,
                    (unsigned __int16)v26 - (unsigned __int16)v27,
                    xSrc,
                    ySrc,
                    wSrc,
                    SHIWORD(v58),
                    v58);
            v46 = ho;
          }
          else
          {
            hSrc = v26 - v27;
            iUsage = v26 - v27;
            v46 = ho;
            v47 = bEmitBitmap(
                    a1,
                    ho,
                    v54,
                    v27,
                    (unsigned __int16)v21 - (unsigned __int16)v54,
                    iUsage,
                    0,
                    0,
                    (unsigned __int16)v21 - (unsigned __int16)v54,
                    hSrc,
                    v58);
          }
          v59 = v47;
          DoRestoreDC(a1, 0xFFFFFFFFLL, v48);
LABEL_82:
          v44 = hdc;
          if ( !hdc )
            goto LABEL_91;
          goto LABEL_90;
        }
        DoRestoreDC(a1, 0xFFFFFFFFLL, v45);
      }
      v46 = ho;
      goto LABEL_82;
    }
    hdca = (HDC)hdcMakeCompatibleDC((XFORM *)(a1 + 228));
    v18 = hdca;
    if ( hdca )
    {
      if ( (unsigned int)uBytes < 0x28 )
      {
        v59 = 1;
        goto LABEL_98;
      }
      v38 = 44;
      if ( (unsigned int)uBytes > 0x2C )
        v38 = (unsigned int)uBytes;
      v39 = (BITMAPINFO *)LocalAlloc(0, v38);
      hMem = v39;
      if ( !v39 )
      {
        v18 = hdca;
        goto LABEL_98;
      }
      pbmi = v39;
      memcpy_0(v39, a13, (unsigned int)uBytes);
      pbmi->bmiHeader.biSizeImage = 0;
      pbmi->bmiHeader.biWidth = v21 - v54;
      pbmi->bmiHeader.biHeight = v26 - v27;
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &pbmi->bmiHeader, 2u, 0, pbmi, a12);
      v18 = hdca;
      ho = DIBitmap;
      if ( !DIBitmap )
      {
LABEL_98:
        DeleteDC(v18);
        goto LABEL_99;
      }
      hdc = (HDC)SelectObject(hdca, DIBitmap);
      if ( !hdc )
      {
        v46 = ho;
LABEL_94:
        DeleteObject(v46);
LABEL_95:
        if ( !v18 )
        {
LABEL_99:
          if ( h )
            SelectObject(hdcSrc, h);
          if ( v68 )
            DeleteObject(v68);
          if ( hdcSrc )
            DeleteDC(hdcSrc);
          if ( hMem )
            LocalFree(hMem);
          return v59;
        }
        goto LABEL_98;
      }
      hdcSrc = (HDC)hdcMakeCompatibleDC(a11);
      if ( hdcSrc )
      {
        v42 = CreateDIBitmap(*(HDC *)(a1 + 40), &a13->bmiHeader, 6u, a15, a13, a12);
        v68 = v42;
        if ( v42 )
        {
          h = SelectObject(hdcSrc, v42);
          if ( h )
          {
            OffsetViewportOrgEx(v18, -v54, -v27, 0);
            v43 = StretchBlt(v18, a2, a3, a4, hDest, hdcSrc, a7, a8, a9, a10, 0xCC0020u);
            v44 = hdc;
            if ( !v43 )
            {
LABEL_89:
              v46 = ho;
LABEL_90:
              SelectObject(v18, v44);
LABEL_91:
              if ( !v46 )
                goto LABEL_95;
              goto LABEL_94;
            }
            if ( SelectObject(v18, hdc) )
              goto LABEL_78;
          }
        }
      }
      v44 = hdc;
      goto LABEL_89;
    }
  }
  return v59;
}

```

## disassembly

```asm
0x1801432b0  push    rbp
0x1801432b2  push    rbx
0x1801432b3  push    rsi
0x1801432b4  push    rdi
0x1801432b5  push    r12
0x1801432b7  push    r13
0x1801432b9  push    r14
0x1801432bb  push    r15
0x1801432bd  lea     rbp, [rsp-8]
0x1801432c2  sub     rsp, 108h
0x1801432c9  mov     rax, cs:__security_cookie
0x1801432d0  xor     rax, rsp
0x1801432d3  mov     [rbp+40h+var_48], rax
0x1801432d7  mov     rax, [rbp+40h+arg_50]
0x1801432de  xor     edi, edi
0x1801432e0  mov     rbx, rcx
0x1801432e3  mov     [rbp+40h+lpxf], rax
0x1801432e7  mov     eax, [rbp+40h+arg_58]
0x1801432ed  mov     [rbp+40h+var_C0], eax
0x1801432f0  mov     rax, [rbp+40h+arg_60]
0x1801432f7  mov     [rbp+40h+Src], rax
0x1801432fb  mov     rax, [rbp+40h+arg_70]
0x180143302  mov     [rbp+40h+pjBits], rax
0x180143306  mov     [rbp+40h+wDest], r9d
0x18014330a  mov     [rbp+40h+yDest], r8d
0x18014330e  mov     [rbp+40h+xDest], edx
0x180143311  mov     [rsp+140h+var_C4], edi
0x180143315  cmp     [rcx+1E4h], edi
0x18014331b  jz      short loc_18014334B
0x18014331d  cmp     [rbp+40h+arg_28], 0CC0020h
0x180143324  jnz     short loc_18014332E
0x180143326  mov     r15d, 660046h
0x18014332c  jmp     short loc_18014334F
0x18014332e  cmp     [rbp+40h+arg_28], 0F00021h
0x180143335  jnz     short loc_18014333F
0x180143337  mov     r15d, 5A0049h
0x18014333d  jmp     short loc_18014334F
0x18014333f  bts     dword ptr [rcx+4], 1Eh
0x180143344  xor     eax, eax
0x180143346  jmp     loc_18014387C
0x18014334b  mov     r15d, [rbp+40h+arg_28]
0x18014334f  lea     eax, [r9+rdx]
0x180143353  mov     [rbp+40h+var_64], r8d
0x180143357  mov     [rbp+40h+var_A0], eax
0x18014335a  mov     r14, rdi
0x18014335d  mov     [rbp+40h+var_60], eax
0x180143360  mov     [rbp+40h+var_58], eax
0x180143363  mov     eax, [rbp+40h+hDest]
0x180143366  add     eax, r8d
0x180143369  mov     [rbp+40h+var_5C], r8d
0x18014336d  lea     r8, [rcx+0E4h]
0x180143374  mov     [rbp+40h+var_68], edx
0x180143377  mov     [rbp+40h+var_50], edx
0x18014337a  lea     rcx, [rbp+40h+var_68]
0x18014337e  mov     edx, 4
0x180143383  mov     [rsp+140h+var_C8], r15d
0x180143388  mov     [rbp+40h+hdcSrc], rdi
0x18014338c  mov     [rbp+40h+h], rdi
0x180143390  mov     [rbp+40h+var_80], rdi
0x180143394  mov     [rsp+140h+hdc], rdi
0x180143399  mov     [rsp+140h+ho], rdi
0x18014339e  mov     [rbp+40h+hMem], rdi
0x1801433a2  mov     [rbp+40h+var_A4], eax
0x1801433a5  mov     [rbp+40h+var_54], eax
0x1801433a8  mov     [rbp+40h+var_4C], eax
0x1801433ab  call    bXformWorkhorse
0x1801433b0  test    eax, eax
0x1801433b2  jz      loc_180143878
0x1801433b8  mov     ecx, [rbp+40h+var_50]
0x1801433bb  mov     eax, ecx
0x1801433bd  mov     edx, [rbp+40h+var_58]
0x1801433c0  cmp     edx, ecx
0x1801433c2  mov     r10d, [rbp+40h+var_60]
0x1801433c6  cmovl   eax, edx
0x1801433c9  cmp     r10d, eax
0x1801433cc  jge     short loc_1801433D3
0x1801433ce  mov     eax, r10d
0x1801433d1  jmp     short loc_1801433DA
0x1801433d3  cmp     edx, ecx
0x1801433d5  mov     eax, ecx
0x1801433d7  cmovl   eax, edx
0x1801433da  mov     esi, [rbp+40h+var_68]
0x1801433dd  cmp     esi, eax
0x1801433df  jge     short loc_1801433E7
0x1801433e1  mov     [rsp+140h+var_E0], esi
0x1801433e5  jmp     short loc_180143405
0x1801433e7  cmp     edx, ecx
0x1801433e9  mov     eax, ecx
0x1801433eb  cmovl   eax, edx
0x1801433ee  cmp     r10d, eax
0x1801433f1  jge     short loc_1801433FA
0x1801433f3  mov     [rsp+140h+var_E0], r10d
0x1801433f8  jmp     short loc_180143405
0x1801433fa  cmp     edx, ecx
0x1801433fc  mov     edi, ecx
0x1801433fe  cmovl   edi, edx
0x180143401  mov     [rsp+140h+var_E0], edi
0x180143405  mov     r8d, [rbp+40h+var_4C]
0x180143409  mov     eax, r8d
0x18014340c  mov     r9d, [rbp+40h+var_54]
0x180143410  cmp     r9d, r8d
0x180143413  mov     r11d, [rbp+40h+var_5C]
0x180143417  cmovl   eax, r9d
0x18014341b  cmp     r11d, eax
0x18014341e  jge     short loc_180143425
0x180143420  mov     eax, r11d
0x180143423  jmp     short loc_18014342F
0x180143425  cmp     r9d, r8d
0x180143428  mov     eax, r8d
0x18014342b  cmovl   eax, r9d
0x18014342f  mov     edi, [rbp+40h+var_64]
0x180143432  cmp     edi, eax
0x180143434  jge     short loc_18014343B
0x180143436  mov     r12d, edi
0x180143439  jmp     short loc_180143459
0x18014343b  cmp     r9d, r8d
0x18014343e  mov     eax, r8d
0x180143441  cmovl   eax, r9d
0x180143445  cmp     r11d, eax
0x180143448  jge     short loc_18014344F
0x18014344a  mov     r12d, r11d
0x18014344d  jmp     short loc_180143459
0x18014344f  cmp     r9d, r8d
0x180143452  mov     r12d, r8d
0x180143455  cmovl   r12d, r9d
0x180143459  cmp     edx, ecx
0x18014345b  mov     eax, ecx
0x18014345d  cmovg   eax, edx
0x180143460  cmp     r10d, eax
0x180143463  jle     short loc_18014346A
0x180143465  mov     eax, r10d
0x180143468  jmp     short loc_180143471
0x18014346a  cmp     edx, ecx
0x18014346c  mov     eax, ecx
0x18014346e  cmovg   eax, edx
0x180143471  cmp     esi, eax
0x180143473  jg      short loc_18014348D
0x180143475  cmp     edx, ecx
0x180143477  mov     eax, ecx
0x180143479  cmovg   eax, edx
0x18014347c  cmp     r10d, eax
0x18014347f  jle     short loc_180143486
0x180143481  mov     esi, r10d
0x180143484  jmp     short loc_18014348D
0x180143486  cmp     edx, ecx
0x180143488  mov     esi, ecx
0x18014348a  cmovg   esi, edx
0x18014348d  cmp     r9d, r8d
0x180143490  mov     eax, r8d
0x180143493  cmovg   eax, r9d
0x180143497  cmp     r11d, eax
0x18014349a  jle     short loc_1801434A1
0x18014349c  mov     eax, r11d
0x18014349f  jmp     short loc_1801434AB
0x1801434a1  cmp     r9d, r8d
0x1801434a4  mov     eax, r8d
0x1801434a7  cmovg   eax, r9d
0x1801434ab  cmp     edi, eax
0x1801434ad  jg      short loc_1801434CD
0x1801434af  cmp     r9d, r8d
0x1801434b2  mov     eax, r8d
0x1801434b5  cmovg   eax, r9d
0x1801434b9  cmp     r11d, eax
0x1801434bc  jle     short loc_1801434C3
0x1801434be  mov     edi, r11d
0x1801434c1  jmp     short loc_1801434CD
0x1801434c3  cmp     r9d, r8d
0x1801434c6  mov     edi, r8d
0x1801434c9  cmovg   edi, r9d
0x1801434cd  mov     eax, r15d
0x1801434d0  and     r15d, 0CCCC0000h
0x1801434d7  and     eax, 0F3330000h
0x1801434dc  lea     r13d, ds:0[rax*4]
0x1801434e4  cmp     r15d, r13d
0x1801434e7  jz      loc_1801436DC
0x1801434ed  lea     rcx, [rbx+0E4h]; lpxf
0x1801434f4  call    hdcMakeCompatibleDC
0x1801434f9  mov     [rsp+140h+hdc], rax
0x1801434fe  mov     r14, rax
0x180143501  test    rax, rax
0x180143504  jz      loc_180143878
0x18014350a  mov     eax, dword ptr [rbp+40h+uBytes]
0x180143510  cmp     eax, 28h ; '('
0x180143513  jnb     short loc_180143522
0x180143515  mov     [rsp+140h+var_C4], 1
0x18014351d  jmp     loc_180143806
0x180143522  mov     edx, 2Ch ; ','
0x180143527  mov     r14, rax
0x18014352a  cmp     eax, edx
0x18014352c  jbe     short loc_180143531
0x18014352e  mov     rdx, rax; uBytes
0x180143531  xor     ecx, ecx; uFlags
0x180143533  call    cs:__imp_LocalAlloc
0x18014353a  nop     dword ptr [rax+rax+00h]
0x18014353f  mov     [rbp+40h+hMem], rax
0x180143543  test    rax, rax
0x180143546  jz      loc_180143801
0x18014354c  mov     rdx, [rbp+40h+Src]; Src
0x180143550  mov     r8, r14; Size
0x180143553  mov     rcx, rax; void *
0x180143556  mov     r14, rax
0x180143559  call    memcpy_0
0x18014355e  and     dword ptr [r14+14h], 0
0x180143563  mov     eax, esi
0x180143565  sub     eax, [rsp+140h+var_E0]
0x180143569  xor     r9d, r9d; pjBits
0x18014356c  mov     [r14+4], eax
0x180143570  mov     rdx, r14; pbmih
0x180143573  mov     eax, edi
0x180143575  sub     eax, r12d
0x180143578  mov     [r14+8], eax
0x18014357c  lea     r8d, [r9+2]; flInit
0x180143580  mov     eax, [rbp+40h+var_C0]
0x180143583  mov     rcx, [rbx+28h]; hdc
0x180143587  mov     [rsp+140h+iUsage], eax; iUsage
0x18014358b  mov     [rsp+140h+pbmi], r14; pbmi
0x180143590  call    cs:__imp_CreateDIBitmap
0x180143597  nop     dword ptr [rax+rax+00h]
0x18014359c  mov     r14, [rsp+140h+hdc]
0x1801435a1  mov     [rsp+140h+ho], rax
0x1801435a6  test    rax, rax
0x1801435a9  jz      loc_180143806
0x1801435af  mov     rdx, rax; h
0x1801435b2  mov     rcx, r14; hdc
0x1801435b5  call    cs:__imp_SelectObject
0x1801435bc  nop     dword ptr [rax+rax+00h]
0x1801435c1  mov     [rsp+140h+hdc], rax
0x1801435c6  test    rax, rax
0x1801435c9  jz      loc_1801437E6
0x1801435cf  mov     rcx, [rbp+40h+lpxf]; lpxf
0x1801435d3  call    hdcMakeCompatibleDC
0x1801435d8  mov     [rbp+40h+hdcSrc], rax
0x1801435dc  test    rax, rax
0x1801435df  jz      loc_1801437C6
0x1801435e5  mov     eax, [rbp+40h+var_C0]
0x1801435e8  mov     r8d, 6; flInit
0x1801435ee  mov     r9, [rbp+40h+pjBits]; pjBits
0x1801435f2  mov     rcx, [rbx+28h]; hdc
0x1801435f6  mov     [rsp+140h+iUsage], eax; iUsage
0x1801435fa  mov     rax, [rbp+40h+Src]
0x1801435fe  mov     rdx, rax; pbmih
0x180143601  mov     [rsp+140h+pbmi], rax; pbmi
0x180143606  call    cs:__imp_CreateDIBitmap
0x18014360d  nop     dword ptr [rax+rax+00h]
0x180143612  mov     [rbp+40h+var_80], rax
0x180143616  test    rax, rax
0x180143619  jz      loc_1801437C6
0x18014361f  mov     rcx, [rbp+40h+hdcSrc]; hdc
0x180143623  mov     rdx, rax; h
0x180143626  call    cs:__imp_SelectObject
0x18014362d  nop     dword ptr [rax+rax+00h]
0x180143632  mov     [rbp+40h+h], rax
0x180143636  test    rax, rax
0x180143639  jz      loc_1801437C6
0x18014363f  mov     edx, [rsp+140h+var_E0]
0x180143643  mov     r8d, r12d
0x180143646  neg     r8d; y
0x180143649  neg     edx; x
0x18014364b  xor     r9d, r9d; lppt
0x18014364e  mov     rcx, r14; hdc
0x180143651  call    cs:__imp_OffsetViewportOrgEx
0x180143658  nop     dword ptr [rax+rax+00h]
0x18014365d  mov     eax, [rbp+40h+arg_48]
0x180143663  mov     rcx, r14; hdcDest
0x180143666  mov     r9d, [rbp+40h+wDest]; wDest
0x18014366a  mov     r8d, [rbp+40h+yDest]; yDest
0x18014366e  mov     edx, [rbp+40h+xDest]; xDest
0x180143671  mov     [rsp+140h+rop], 0CC0020h; rop
0x180143679  mov     dword ptr [rsp+140h+hSrc], eax; hSrc
0x18014367d  mov     eax, [rbp+40h+arg_40]
0x180143683  mov     [rsp+140h+wSrc], eax; wSrc
0x180143687  mov     eax, dword ptr [rbp+40h+arg_38]
0x18014368d  mov     [rsp+140h+ySrc], eax; __int16
0x180143691  mov     eax, dword ptr [rbp+40h+arg_30]
0x180143697  mov     [rsp+140h+xSrc], eax; __int16
0x18014369b  mov     rax, [rbp+40h+hdcSrc]
0x18014369f  mov     qword ptr [rsp+140h+iUsage], rax; hdcSrc
0x1801436a4  mov     eax, [rbp+40h+hDest]
0x1801436a7  mov     dword ptr [rsp+140h+pbmi], eax; hDest
0x1801436ab  call    cs:__imp_StretchBlt
0x1801436b2  nop     dword ptr [rax+rax+00h]
0x1801436b7  mov     rdx, [rsp+140h+hdc]; h
0x1801436bc  test    eax, eax
0x1801436be  jz      loc_1801437CB
0x1801436c4  mov     rcx, r14; hdc
0x1801436c7  call    cs:__imp_SelectObject
0x1801436ce  nop     dword ptr [rax+rax+00h]
0x1801436d3  test    rax, rax
0x1801436d6  jz      loc_1801437C6
0x1801436dc  mov     rcx, rbx
0x1801436df  call    DoSaveDC
0x1801436e4  test    eax, eax
0x1801436e6  jz      short loc_180143719
0x1801436e8  mov     eax, [rbp+40h+var_A4]
0x1801436eb  mov     rcx, rbx
0x1801436ee  mov     r9d, [rbp+40h+var_A0]
0x1801436f2  mov     r8d, [rbp+40h+yDest]
0x1801436f6  mov     edx, [rbp+40h+xDest]
0x1801436f9  mov     [rsp+140h+iUsage], 1Eh
0x180143701  mov     dword ptr [rsp+140h+pbmi], eax
  ... truncated ...
```
