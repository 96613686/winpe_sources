# DoRotatedStretchBlt

- ea: `0x1801497ec`
- end: `0x180149dfa`
- name: `DoRotatedStretchBlt`
- size: `1550`
- prototype: `__int64 __fastcall(int, int, int, int, int hDest, int, int, int, int, int, __int64, int, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800c6990`

## callees

- `0x1800c5db4`
- `0x1800c790c`
- `0x1800c7a84`
- `0x1800c87fc`
- `0x1800c8944`
- `0x1800f294c`
- `0x180105d40`
- `0x1801497ec`
- `0x18014a120`
- `0x180171428`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180149a8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180149a8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180149dc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180149dc9`
- `GDI32!OffsetViewportOrgEx` at `0x180149baa`
- `GDI32!OffsetViewportOrgEx` at `0x180149baa`
- `GDI32!CreateDIBitmap` at `0x180149aef`
- `GDI32!CreateDIBitmap` at `0x180149b60`
- `GDI32!CreateDIBitmap` at `0x180149aef`
- `GDI32!CreateDIBitmap` at `0x180149b60`
- `GDI32!StretchBlt` at `0x180149c04`
- `GDI32!StretchBlt` at `0x180149c04`
- `GDI32!DeleteDC` at `0x180149d66`
- `GDI32!DeleteDC` at `0x180149db1`
- `GDI32!DeleteDC` at `0x180149d66`
- `GDI32!DeleteDC` at `0x180149db1`
- `GDI32!SelectObject` at `0x180149b0f`
- `GDI32!SelectObject` at `0x180149b80`
- `GDI32!SelectObject` at `0x180149c20`
- `GDI32!SelectObject` at `0x180149d37`
- `GDI32!SelectObject` at `0x180149d85`
- `GDI32!SelectObject` at `0x180149b0f`
- `GDI32!SelectObject` at `0x180149b80`
- `GDI32!SelectObject` at `0x180149c20`
- `GDI32!SelectObject` at `0x180149d37`
- `GDI32!SelectObject` at `0x180149d85`
- `GDI32!DeleteObject` at `0x180149d52`
- `GDI32!DeleteObject` at `0x180149d9d`
- `GDI32!DeleteObject` at `0x180149d52`
- `GDI32!DeleteObject` at `0x180149d9d`

## pseudocode

```c
__int64 __fastcall DoRotatedStretchBlt(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int hDest,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        XFORM *a11,
        UINT a12,
        const BITMAPINFO *pbmi,
        SIZE_T uBytes,
        const void *a15)
{
  int v16; // r14d
  HDC CompatibleDC; // r13
  signed int v19; // eax
  signed int *v20; // rax
  signed int v21; // esi
  unsigned int v22; // r15d
  signed int v23; // eax
  signed int v24; // eax
  signed int *v25; // rax
  signed int v26; // edi
  unsigned int v27; // r12d
  signed int v28; // eax
  signed int v29; // eax
  signed int *v30; // rax
  signed int v31; // eax
  signed int v32; // eax
  signed int *v33; // rax
  signed int v34; // eax
  int v35; // eax
  unsigned int v36; // r14d
  SIZE_T v37; // rdx
  BITMAPINFO *v38; // rax
  HBITMAP DIBitmap; // rax
  HBITMAP v40; // rax
  BOOL v41; // eax
  void *v42; // rdx
  HBITMAP v43; // rdi
  unsigned int v44; // eax
  unsigned int iUsage; // [rsp+28h] [rbp-D8h]
  int xSrc; // [rsp+30h] [rbp-D0h]
  int ySrc; // [rsp+38h] [rbp-C8h]
  int wSrc; // [rsp+40h] [rbp-C0h]
  int hSrc; // [rsp+48h] [rbp-B8h]
  unsigned int v50; // [rsp+60h] [rbp-A0h]
  HBITMAP ho; // [rsp+68h] [rbp-98h]
  unsigned int v52; // [rsp+70h] [rbp-90h]
  HGDIOBJ h; // [rsp+78h] [rbp-88h]
  signed int v54; // [rsp+80h] [rbp-80h]
  HDC hdc; // [rsp+90h] [rbp-70h]
  int v59; // [rsp+9Ch] [rbp-64h]
  unsigned int v60; // [rsp+A0h] [rbp-60h]
  unsigned int v61; // [rsp+A4h] [rbp-5Ch]
  BITMAPINFO *hMem; // [rsp+A8h] [rbp-58h]
  HGDIOBJ v63; // [rsp+B8h] [rbp-48h]
  HBITMAP v64; // [rsp+C0h] [rbp-40h]
  signed int v65; // [rsp+D8h] [rbp-28h] BYREF
  signed int v66; // [rsp+DCh] [rbp-24h]
  signed int v67; // [rsp+E0h] [rbp-20h] BYREF
  signed int v68; // [rsp+E4h] [rbp-1Ch] BYREF
  signed int v69; // [rsp+E8h] [rbp-18h] BYREF
  signed int v70; // [rsp+ECh] [rbp-14h] BYREF
  signed int v71; // [rsp+F0h] [rbp-10h] BYREF
  signed int v72; // [rsp+F4h] [rbp-Ch] BYREF

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
  v65 = a2;
  v60 = a4 + a2;
  v67 = a4 + a2;
  v69 = a4 + a2;
  v66 = a3;
  v59 = a3 + hDest;
  v70 = a3 + hDest;
  v72 = a3 + hDest;
  v68 = a3;
  v71 = a2;
  v50 = v16;
  v52 = 0;
  if ( (unsigned int)bXformWorkhorse(&v65, 4, a1 + 228) )
  {
    CompatibleDC = 0;
    v19 = v71;
    hdc = 0;
    if ( v69 < v71 )
      v19 = v69;
    v63 = 0;
    v64 = 0;
    h = 0;
    ho = 0;
    hMem = 0;
    if ( v67 >= v19 )
    {
      v20 = &v69;
      if ( v69 >= v71 )
        v20 = &v71;
    }
    else
    {
      v20 = &v67;
    }
    v21 = v65;
    if ( v65 >= *v20 )
    {
      v23 = v71;
      if ( v69 < v71 )
        v23 = v69;
      if ( v67 >= v23 )
      {
        v22 = v71;
        if ( v69 < v71 )
          v22 = v69;
        v54 = v22;
      }
      else
      {
        v22 = v67;
        v54 = v67;
      }
    }
    else
    {
      v22 = v65;
      v54 = v65;
    }
    v24 = v72;
    if ( v70 < v72 )
      v24 = v70;
    if ( v68 >= v24 )
    {
      v25 = &v70;
      if ( v70 >= v72 )
        v25 = &v72;
    }
    else
    {
      v25 = &v68;
    }
    v26 = v66;
    if ( v66 >= *v25 )
    {
      v28 = v72;
      if ( v70 < v72 )
        v28 = v70;
      if ( v68 >= v28 )
      {
        v27 = v72;
        if ( v70 < v72 )
          v27 = v70;
      }
      else
      {
        v27 = v68;
      }
    }
    else
    {
      v27 = v66;
    }
    v29 = v71;
    if ( v69 > v71 )
      v29 = v69;
    if ( v67 <= v29 )
    {
      v30 = &v69;
      if ( v69 <= v71 )
        v30 = &v71;
    }
    else
    {
      v30 = &v67;
    }
    if ( v65 <= *v30 )
    {
      v31 = v71;
      if ( v69 > v71 )
        v31 = v69;
      if ( v67 <= v31 )
      {
        v21 = v71;
        if ( v69 > v71 )
          v21 = v69;
      }
      else
      {
        v21 = v67;
      }
    }
    v32 = v72;
    if ( v70 > v72 )
      v32 = v70;
    if ( v68 <= v32 )
    {
      v33 = &v70;
      if ( v70 <= v72 )
        v33 = &v72;
    }
    else
    {
      v33 = &v68;
    }
    if ( v66 <= *v33 )
    {
      v34 = v72;
      if ( v70 > v72 )
        v34 = v70;
      if ( v68 <= v34 )
      {
        v26 = v72;
        if ( v70 > v72 )
          v26 = v70;
      }
      else
      {
        v26 = v68;
      }
    }
    v35 = v16;
    v36 = v16 & 0xCCCC0000;
    v61 = 4 * (v35 & 0xF3330000);
    if ( v36 == v61 )
    {
LABEL_78:
      if ( (unsigned int)DoSaveDC(a1) )
      {
        if ( (unsigned int)DoClipRect(a1, a2, a3, v60, v59, 30) )
        {
          if ( v36 == v61 )
          {
            v44 = bW16Emit9(
                    a1,
                    HIWORD(v50),
                    (unsigned __int16)v22,
                    (unsigned __int16)v27,
                    (unsigned __int16)v21 - (unsigned __int16)v22,
                    (unsigned __int16)v26 - (unsigned __int16)v27,
                    xSrc,
                    ySrc,
                    wSrc,
                    SHIWORD(v50),
                    v50);
            v43 = ho;
          }
          else
          {
            hSrc = v26 - v27;
            iUsage = v26 - v27;
            v43 = ho;
            v44 = bEmitBitmap(a1, ho, v22, v27, v21 - v22, iUsage, 0, 0, v21 - v22, hSrc, v50);
          }
          v52 = v44;
          DoRestoreDC(a1, 0xFFFFFFFFLL);
LABEL_82:
          v42 = h;
          if ( !h )
            goto LABEL_91;
          goto LABEL_90;
        }
        DoRestoreDC(a1, 0xFFFFFFFFLL);
      }
      v43 = ho;
      goto LABEL_82;
    }
    CompatibleDC = (HDC)hdcMakeCompatibleDC((XFORM *)(a1 + 228));
    if ( CompatibleDC )
    {
      if ( (unsigned int)uBytes < 0x28 )
      {
        v52 = 1;
        goto LABEL_96;
      }
      v37 = 44;
      if ( (unsigned int)uBytes > 0x2C )
        v37 = (unsigned int)uBytes;
      v38 = (BITMAPINFO *)LocalAlloc(0, v37);
      hMem = v38;
      if ( !v38 )
        goto LABEL_96;
      memcpy_0(v38, pbmi, (unsigned int)uBytes);
      v22 = v54;
      hMem->bmiHeader.biWidth = v21 - v54;
      hMem->bmiHeader.biSizeImage = 0;
      hMem->bmiHeader.biHeight = v26 - v27;
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &hMem->bmiHeader, 2u, 0, hMem, a12);
      ho = DIBitmap;
      if ( !DIBitmap )
        goto LABEL_96;
      h = SelectObject(CompatibleDC, DIBitmap);
      if ( !h )
      {
        v43 = ho;
LABEL_94:
        DeleteObject(v43);
LABEL_95:
        if ( !CompatibleDC )
        {
LABEL_97:
          if ( v63 )
            SelectObject(hdc, v63);
          if ( v64 )
            DeleteObject(v64);
          if ( hdc )
            DeleteDC(hdc);
          if ( hMem )
            LocalFree(hMem);
          return v52;
        }
LABEL_96:
        DeleteDC(CompatibleDC);
        goto LABEL_97;
      }
      hdc = (HDC)hdcMakeCompatibleDC(a11);
      if ( hdc )
      {
        v40 = CreateDIBitmap(*(HDC *)(a1 + 40), &pbmi->bmiHeader, 6u, a15, pbmi, a12);
        v64 = v40;
        if ( v40 )
        {
          v63 = SelectObject(hdc, v40);
          if ( v63 )
          {
            OffsetViewportOrgEx(CompatibleDC, -v54, -v27, 0);
            v41 = StretchBlt(CompatibleDC, a2, a3, a4, hDest, hdc, a7, a8, a9, a10, 0xCC0020u);
            v42 = h;
            if ( !v41 )
            {
LABEL_89:
              v43 = ho;
LABEL_90:
              SelectObject(CompatibleDC, v42);
LABEL_91:
              if ( !v43 )
                goto LABEL_95;
              goto LABEL_94;
            }
            if ( SelectObject(CompatibleDC, h) )
              goto LABEL_78;
          }
        }
      }
      v42 = h;
      goto LABEL_89;
    }
  }
  return v52;
}

```

## disassembly

```asm
0x1801497ec  push    rbp
0x1801497ee  push    rbx
0x1801497ef  push    rsi
0x1801497f0  push    rdi
0x1801497f1  push    r12
0x1801497f3  push    r13
0x1801497f5  push    r14
0x1801497f7  push    r15
0x1801497f9  lea     rbp, [rsp-8]
0x1801497fe  sub     rsp, 108h
0x180149805  mov     rax, cs:__security_cookie
0x18014980c  xor     rax, rsp
0x18014980f  mov     [rbp+40h+var_48], rax
0x180149813  mov     rbx, rcx
0x180149816  mov     [rbp+40h+wDest], r9d
0x18014981a  mov     rcx, [rbp+40h+arg_50]
0x180149821  xor     edi, edi
0x180149823  mov     [rbp+40h+lpxf], rcx
0x180149827  mov     ecx, [rbp+40h+arg_58]
0x18014982d  mov     [rbp+40h+var_BC], ecx
0x180149830  mov     rcx, [rbp+40h+arg_60]
0x180149837  mov     [rbp+40h+Src], rcx
0x18014983b  mov     rcx, [rbp+40h+arg_70]
0x180149842  mov     [rbp+40h+pjBits], rcx
0x180149846  mov     [rbp+40h+yDest], r8d
0x18014984a  mov     [rbp+40h+xDest], edx
0x18014984d  cmp     [rbx+1E4h], edi
0x180149853  jz      short loc_180149883
0x180149855  cmp     [rbp+40h+arg_28], 0CC0020h
0x18014985c  jnz     short loc_180149866
0x18014985e  mov     r14d, 660046h
0x180149864  jmp     short loc_180149887
0x180149866  cmp     [rbp+40h+arg_28], 0F00021h
0x18014986d  jnz     short loc_180149877
0x18014986f  mov     r14d, 5A0049h
0x180149875  jmp     short loc_180149887
0x180149877  bts     dword ptr [rbx+4], 1Eh
0x18014987c  xor     eax, eax
0x18014987e  jmp     loc_180149DD9
0x180149883  mov     r14d, [rbp+40h+arg_28]
0x180149887  lea     ecx, [r9+rdx]
0x18014988b  mov     [rbp+40h+var_68], edx
0x18014988e  mov     [rbp+40h+var_A0], ecx
0x180149891  mov     [rbp+40h+var_60], ecx
0x180149894  mov     [rbp+40h+var_58], ecx
0x180149897  mov     ecx, [rbp+40h+hDest]
0x18014989a  add     ecx, r8d
0x18014989d  mov     [rbp+40h+var_64], r8d
0x1801498a1  mov     [rbp+40h+var_A4], ecx
0x1801498a4  mov     [rbp+40h+var_54], ecx
0x1801498a7  mov     [rbp+40h+var_4C], ecx
0x1801498aa  lea     rcx, [rbp+40h+var_68]
0x1801498ae  mov     [rbp+40h+var_5C], r8d
0x1801498b2  lea     r8, [rbx+0E4h]
0x1801498b9  mov     [rbp+40h+var_50], edx
0x1801498bc  mov     edx, 4
0x1801498c1  mov     [rsp+140h+var_E0], r14d
0x1801498c6  mov     [rsp+140h+var_D0], edi
0x1801498ca  call    bXformWorkhorse
0x1801498cf  test    eax, eax
0x1801498d1  jz      loc_180149DD5
0x1801498d7  mov     ecx, [rbp+40h+var_50]
0x1801498da  mov     r13, rdi
0x1801498dd  mov     edx, [rbp+40h+var_58]
0x1801498e0  mov     eax, ecx
0x1801498e2  mov     r10d, [rbp+40h+var_60]
0x1801498e6  cmp     edx, ecx
0x1801498e8  mov     [rbp+40h+hdc], rdi
0x1801498ec  cmovl   eax, edx
0x1801498ef  mov     [rbp+40h+var_88], rdi
0x1801498f3  mov     [rbp+40h+var_80], rdi
0x1801498f7  mov     [rsp+140h+h], rdi
0x1801498fc  mov     [rsp+140h+ho], rdi
0x180149901  mov     [rbp+40h+hMem], rdi
0x180149905  cmp     r10d, eax
0x180149908  jge     short loc_180149910
0x18014990a  lea     rax, [rbp+40h+var_60]
0x18014990e  jmp     short loc_18014991E
0x180149910  cmp     edx, ecx
0x180149912  lea     rax, [rbp+40h+var_58]
0x180149916  lea     r8, [rbp+40h+var_50]
0x18014991a  cmovge  rax, r8
0x18014991e  mov     esi, [rbp+40h+var_68]
0x180149921  cmp     esi, [rax]
0x180149923  jge     short loc_18014992D
0x180149925  mov     r15d, esi
0x180149928  mov     [rbp+40h+var_C0], esi
0x18014992b  jmp     short loc_18014994F
0x18014992d  cmp     edx, ecx
0x18014992f  mov     eax, ecx
0x180149931  cmovl   eax, edx
0x180149934  cmp     r10d, eax
0x180149937  jge     short loc_180149942
0x180149939  mov     r15d, r10d
0x18014993c  mov     [rbp+40h+var_C0], r10d
0x180149940  jmp     short loc_18014994F
0x180149942  cmp     edx, ecx
0x180149944  mov     r15d, ecx
0x180149947  cmovl   r15d, edx
0x18014994b  mov     [rbp+40h+var_C0], r15d
0x18014994f  mov     r8d, [rbp+40h+var_4C]
0x180149953  mov     eax, r8d
0x180149956  mov     r9d, [rbp+40h+var_54]
0x18014995a  cmp     r9d, r8d
0x18014995d  mov     r11d, [rbp+40h+var_5C]
0x180149961  cmovl   eax, r9d
0x180149965  cmp     r11d, eax
0x180149968  jge     short loc_180149970
0x18014996a  lea     rax, [rbp+40h+var_5C]
0x18014996e  jmp     short loc_18014997F
0x180149970  cmp     r9d, r8d
0x180149973  lea     rax, [rbp+40h+var_54]
0x180149977  lea     rdi, [rbp+40h+var_4C]
0x18014997b  cmovge  rax, rdi
0x18014997f  mov     edi, [rbp+40h+var_64]
0x180149982  cmp     edi, [rax]
0x180149984  jge     short loc_18014998B
0x180149986  mov     r12d, edi
0x180149989  jmp     short loc_1801499A9
0x18014998b  cmp     r9d, r8d
0x18014998e  mov     eax, r8d
0x180149991  cmovl   eax, r9d
0x180149995  cmp     r11d, eax
0x180149998  jge     short loc_18014999F
0x18014999a  mov     r12d, r11d
0x18014999d  jmp     short loc_1801499A9
0x18014999f  cmp     r9d, r8d
0x1801499a2  mov     r12d, r8d
0x1801499a5  cmovl   r12d, r9d
0x1801499a9  cmp     edx, ecx
0x1801499ab  mov     eax, ecx
0x1801499ad  cmovg   eax, edx
0x1801499b0  cmp     r10d, eax
0x1801499b3  jle     short loc_1801499BB
0x1801499b5  lea     rax, [rbp+40h+var_60]
0x1801499b9  jmp     short loc_1801499CE
0x1801499bb  lea     r14, [rbp+40h+var_50]
0x1801499bf  cmp     edx, ecx
0x1801499c1  lea     rax, [rbp+40h+var_58]
0x1801499c5  cmovle  rax, r14
0x1801499c9  mov     r14d, [rsp+140h+var_E0]
0x1801499ce  cmp     esi, [rax]
0x1801499d0  jg      short loc_1801499EA
0x1801499d2  cmp     edx, ecx
0x1801499d4  mov     eax, ecx
0x1801499d6  cmovg   eax, edx
0x1801499d9  cmp     r10d, eax
0x1801499dc  jle     short loc_1801499E3
0x1801499de  mov     esi, r10d
0x1801499e1  jmp     short loc_1801499EA
0x1801499e3  cmp     edx, ecx
0x1801499e5  mov     esi, ecx
0x1801499e7  cmovg   esi, edx
0x1801499ea  cmp     r9d, r8d
0x1801499ed  mov     eax, r8d
0x1801499f0  cmovg   eax, r9d
0x1801499f4  cmp     r11d, eax
0x1801499f7  jle     short loc_1801499FF
0x1801499f9  lea     rax, [rbp+40h+var_5C]
0x1801499fd  jmp     short loc_180149A0E
0x1801499ff  cmp     r9d, r8d
0x180149a02  lea     rax, [rbp+40h+var_54]
0x180149a06  lea     rcx, [rbp+40h+var_4C]
0x180149a0a  cmovle  rax, rcx
0x180149a0e  cmp     edi, [rax]
0x180149a10  jg      short loc_180149A30
0x180149a12  cmp     r9d, r8d
0x180149a15  mov     eax, r8d
0x180149a18  cmovg   eax, r9d
0x180149a1c  cmp     r11d, eax
0x180149a1f  jle     short loc_180149A26
0x180149a21  mov     edi, r11d
0x180149a24  jmp     short loc_180149A30
0x180149a26  cmp     r9d, r8d
0x180149a29  mov     edi, r8d
0x180149a2c  cmovg   edi, r9d
0x180149a30  mov     eax, r14d
0x180149a33  and     r14d, 0CCCC0000h
0x180149a3a  and     eax, 0F3330000h
0x180149a3f  shl     eax, 2
0x180149a42  mov     [rbp+40h+var_9C], eax
0x180149a45  cmp     r14d, eax
0x180149a48  jz      loc_180149C35
0x180149a4e  lea     rcx, [rbx+0E4h]; lpxf
0x180149a55  call    hdcMakeCompatibleDC
0x180149a5a  mov     r13, rax
0x180149a5d  test    rax, rax
0x180149a60  jz      loc_180149DD5
0x180149a66  mov     eax, dword ptr [rbp+40h+uBytes]
0x180149a6c  cmp     eax, 28h ; '('
0x180149a6f  jnb     short loc_180149A7E
0x180149a71  mov     [rsp+140h+var_D0], 1
0x180149a79  jmp     loc_180149D63
0x180149a7e  mov     edx, 2Ch ; ','
0x180149a83  mov     r15, rax
0x180149a86  cmp     eax, edx
0x180149a88  cmova   rdx, rax; uBytes
0x180149a8c  xor     ecx, ecx; uFlags
0x180149a8e  call    cs:__imp_LocalAlloc
0x180149a95  nop     dword ptr [rax+rax+00h]
0x180149a9a  mov     [rbp+40h+hMem], rax
0x180149a9e  test    rax, rax
0x180149aa1  jz      loc_180149D63
0x180149aa7  mov     rdx, [rbp+40h+Src]; Src
0x180149aab  mov     r8, r15; Size
0x180149aae  mov     rcx, rax; void *
0x180149ab1  call    memcpy_0
0x180149ab6  mov     rcx, [rbp+40h+hMem]
0x180149aba  mov     eax, esi
0x180149abc  mov     r15d, [rbp+40h+var_C0]
0x180149ac0  xor     r9d, r9d; pjBits
0x180149ac3  sub     eax, r15d
0x180149ac6  mov     rdx, rcx; pbmih
0x180149ac9  mov     [rcx+4], eax
0x180149acc  mov     eax, edi
0x180149ace  sub     eax, r12d
0x180149ad1  mov     dword ptr [rcx+14h], 0
0x180149ad8  mov     [rcx+8], eax
0x180149adb  lea     r8d, [r9+2]; flInit
0x180149adf  mov     eax, [rbp+40h+var_BC]
0x180149ae2  mov     [rsp+140h+iUsage], eax; iUsage
0x180149ae6  mov     [rsp+140h+pbmi], rcx; pbmi
0x180149aeb  mov     rcx, [rbx+28h]; hdc
0x180149aef  call    cs:__imp_CreateDIBitmap
0x180149af6  nop     dword ptr [rax+rax+00h]
0x180149afb  mov     [rsp+140h+ho], rax
0x180149b00  test    rax, rax
0x180149b03  jz      loc_180149D63
0x180149b09  mov     rdx, rax; h
0x180149b0c  mov     rcx, r13; hdc
0x180149b0f  call    cs:__imp_SelectObject
0x180149b16  nop     dword ptr [rax+rax+00h]
0x180149b1b  mov     [rsp+140h+h], rax
0x180149b20  test    rax, rax
0x180149b23  jz      loc_180149D4A
0x180149b29  mov     rcx, [rbp+40h+lpxf]; lpxf
0x180149b2d  call    hdcMakeCompatibleDC
0x180149b32  mov     [rbp+40h+hdc], rax
0x180149b36  test    rax, rax
0x180149b39  jz      loc_180149D2A
0x180149b3f  mov     eax, [rbp+40h+var_BC]
0x180149b42  mov     r8d, 6; flInit
0x180149b48  mov     r9, [rbp+40h+pjBits]; pjBits
0x180149b4c  mov     rcx, [rbx+28h]; hdc
0x180149b50  mov     [rsp+140h+iUsage], eax; iUsage
0x180149b54  mov     rax, [rbp+40h+Src]
0x180149b58  mov     rdx, rax; pbmih
0x180149b5b  mov     [rsp+140h+pbmi], rax; pbmi
0x180149b60  call    cs:__imp_CreateDIBitmap
0x180149b67  nop     dword ptr [rax+rax+00h]
0x180149b6c  mov     [rbp+40h+var_80], rax
0x180149b70  test    rax, rax
0x180149b73  jz      loc_180149D2A
0x180149b79  mov     rcx, [rbp+40h+hdc]; hdc
0x180149b7d  mov     rdx, rax; h
0x180149b80  call    cs:__imp_SelectObject
0x180149b87  nop     dword ptr [rax+rax+00h]
0x180149b8c  mov     [rbp+40h+var_88], rax
0x180149b90  test    rax, rax
0x180149b93  jz      loc_180149D2A
0x180149b99  mov     r8d, r12d
0x180149b9c  mov     edx, r15d
0x180149b9f  neg     r8d; y
0x180149ba2  neg     edx; x
0x180149ba4  xor     r9d, r9d; lppt
0x180149ba7  mov     rcx, r13; hdc
0x180149baa  call    cs:__imp_OffsetViewportOrgEx
0x180149bb1  nop     dword ptr [rax+rax+00h]
0x180149bb6  mov     eax, [rbp+40h+arg_40]
0x180149bbc  mov     ecx, [rbp+40h+arg_48]
0x180149bc2  mov     r9d, [rbp+40h+wDest]; wDest
0x180149bc6  mov     r8d, [rbp+40h+yDest]; yDest
0x180149bca  mov     edx, [rbp+40h+xDest]; xDest
0x180149bcd  mov     [rsp+140h+rop], 0CC0020h; rop
0x180149bd5  mov     [rsp+140h+hSrc], ecx; hSrc
0x180149bd9  mov     rcx, r13; hdcDest
0x180149bdc  mov     [rsp+140h+wSrc], eax; wSrc
0x180149be0  mov     eax, [rbp+40h+arg_38]
0x180149be6  mov     [rsp+140h+ySrc], eax; ySrc
0x180149bea  mov     eax, [rbp+40h+arg_30]
0x180149bf0  mov     [rsp+140h+xSrc], eax; xSrc
0x180149bf4  mov     rax, [rbp+40h+hdc]
0x180149bf8  mov     qword ptr [rsp+140h+iUsage], rax; hdcSrc
0x180149bfd  mov     eax, [rbp+40h+hDest]
0x180149c00  mov     dword ptr [rsp+140h+pbmi], eax; hDest
0x180149c04  call    cs:__imp_StretchBlt
0x180149c0b  nop     dword ptr [rax+rax+00h]
0x180149c10  mov     rdx, [rsp+140h+h]; h
0x180149c15  test    eax, eax
0x180149c17  jz      loc_180149D2F
0x180149c1d  mov     rcx, r13; hdc
0x180149c20  call    cs:__imp_SelectObject
0x180149c27  nop     dword ptr [rax+rax+00h]
0x180149c2c  test    rax, rax
0x180149c2f  jz      loc_180149D2A
0x180149c35  mov     rcx, rbx
0x180149c38  call    DoSaveDC
0x180149c3d  test    eax, eax
0x180149c3f  jz      short loc_180149C72
0x180149c41  mov     eax, [rbp+40h+var_A4]
  ... truncated ...
```
