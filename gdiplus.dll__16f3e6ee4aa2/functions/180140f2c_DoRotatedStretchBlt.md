# DoRotatedStretchBlt

- ea: `0x180140f2c`
- end: `0x1801414df`
- name: `DoRotatedStretchBlt`
- size: `1459`
- prototype: `__int64 __fastcall(int, int, int, int, int hDest, int, int, int, int, int, __int64, int, __int64, SIZE_T uBytes, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800c2ce4`

## callees

- `0x1800c2194`
- `0x1800c3bb8`
- `0x1800c3d1c`
- `0x1800c49e8`
- `0x1800c4b24`
- `0x1800eb850`
- `0x1800fe680`
- `0x180140f2c`
- `0x1801417e0`
- `0x180168478`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801411ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801411ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801414b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801414b5`
- `GDI32!OffsetViewportOrgEx` at `0x1801412cc`
- `GDI32!OffsetViewportOrgEx` at `0x1801412cc`
- `GDI32!CreateDIBitmap` at `0x180141229`
- `GDI32!CreateDIBitmap` at `0x18014128e`
- `GDI32!CreateDIBitmap` at `0x180141229`
- `GDI32!CreateDIBitmap` at `0x18014128e`
- `GDI32!StretchBlt` at `0x180141320`
- `GDI32!StretchBlt` at `0x180141320`
- `GDI32!DeleteDC` at `0x18014146a`
- `GDI32!DeleteDC` at `0x1801414a3`
- `GDI32!DeleteDC` at `0x18014146a`
- `GDI32!DeleteDC` at `0x1801414a3`
- `GDI32!SelectObject` at `0x180141243`
- `GDI32!SelectObject` at `0x1801412a8`
- `GDI32!SelectObject` at `0x180141336`
- `GDI32!SelectObject` at `0x180141447`
- `GDI32!SelectObject` at `0x180141483`
- `GDI32!SelectObject` at `0x180141243`
- `GDI32!SelectObject` at `0x1801412a8`
- `GDI32!SelectObject` at `0x180141336`
- `GDI32!SelectObject` at `0x180141447`
- `GDI32!SelectObject` at `0x180141483`
- `GDI32!DeleteObject` at `0x18014145c`
- `GDI32!DeleteObject` at `0x180141495`
- `GDI32!DeleteObject` at `0x18014145c`
- `GDI32!DeleteObject` at `0x180141495`

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
0x180140f2c  push    rbp
0x180140f2e  push    rbx
0x180140f2f  push    rsi
0x180140f30  push    rdi
0x180140f31  push    r12
0x180140f33  push    r13
0x180140f35  push    r14
0x180140f37  push    r15
0x180140f39  lea     rbp, [rsp-8]
0x180140f3e  sub     rsp, 108h
0x180140f45  mov     rax, cs:__security_cookie
0x180140f4c  xor     rax, rsp
0x180140f4f  mov     [rbp+40h+var_48], rax
0x180140f53  mov     rbx, rcx
0x180140f56  mov     [rbp+40h+wDest], r9d
0x180140f5a  mov     rcx, [rbp+40h+arg_50]
0x180140f61  xor     edi, edi
0x180140f63  mov     [rbp+40h+lpxf], rcx
0x180140f67  mov     ecx, [rbp+40h+arg_58]
0x180140f6d  mov     [rbp+40h+var_BC], ecx
0x180140f70  mov     rcx, [rbp+40h+arg_60]
0x180140f77  mov     [rbp+40h+Src], rcx
0x180140f7b  mov     rcx, [rbp+40h+arg_70]
0x180140f82  mov     [rbp+40h+pjBits], rcx
0x180140f86  mov     [rbp+40h+yDest], r8d
0x180140f8a  mov     [rbp+40h+xDest], edx
0x180140f8d  cmp     [rbx+1E4h], edi
0x180140f93  jz      short loc_180140FC3
0x180140f95  cmp     [rbp+40h+arg_28], 0CC0020h
0x180140f9c  jnz     short loc_180140FA6
0x180140f9e  mov     r14d, 660046h
0x180140fa4  jmp     short loc_180140FC7
0x180140fa6  cmp     [rbp+40h+arg_28], 0F00021h
0x180140fad  jnz     short loc_180140FB7
0x180140faf  mov     r14d, 5A0049h
0x180140fb5  jmp     short loc_180140FC7
0x180140fb7  bts     dword ptr [rbx+4], 1Eh
0x180140fbc  xor     eax, eax
0x180140fbe  jmp     loc_1801414BF
0x180140fc3  mov     r14d, [rbp+40h+arg_28]
0x180140fc7  lea     ecx, [r9+rdx]
0x180140fcb  mov     [rbp+40h+var_68], edx
0x180140fce  mov     [rbp+40h+var_A0], ecx
0x180140fd1  mov     [rbp+40h+var_60], ecx
0x180140fd4  mov     [rbp+40h+var_58], ecx
0x180140fd7  mov     ecx, [rbp+40h+hDest]
0x180140fda  add     ecx, r8d
0x180140fdd  mov     [rbp+40h+var_64], r8d
0x180140fe1  mov     [rbp+40h+var_A4], ecx
0x180140fe4  mov     [rbp+40h+var_54], ecx
0x180140fe7  mov     [rbp+40h+var_4C], ecx
0x180140fea  lea     rcx, [rbp+40h+var_68]
0x180140fee  mov     [rbp+40h+var_5C], r8d
0x180140ff2  lea     r8, [rbx+0E4h]
0x180140ff9  mov     [rbp+40h+var_50], edx
0x180140ffc  mov     edx, 4
0x180141001  mov     [rsp+140h+var_E0], r14d
0x180141006  mov     [rsp+140h+var_D0], edi
0x18014100a  call    bXformWorkhorse
0x18014100f  test    eax, eax
0x180141011  jz      loc_1801414BB
0x180141017  mov     ecx, [rbp+40h+var_50]
0x18014101a  mov     r13, rdi
0x18014101d  mov     edx, [rbp+40h+var_58]
0x180141020  mov     eax, ecx
0x180141022  mov     r10d, [rbp+40h+var_60]
0x180141026  cmp     edx, ecx
0x180141028  mov     [rbp+40h+hdc], rdi
0x18014102c  cmovl   eax, edx
0x18014102f  mov     [rbp+40h+var_88], rdi
0x180141033  mov     [rbp+40h+var_80], rdi
0x180141037  mov     [rsp+140h+h], rdi
0x18014103c  mov     [rsp+140h+ho], rdi
0x180141041  mov     [rbp+40h+hMem], rdi
0x180141045  cmp     r10d, eax
0x180141048  jge     short loc_180141050
0x18014104a  lea     rax, [rbp+40h+var_60]
0x18014104e  jmp     short loc_18014105E
0x180141050  cmp     edx, ecx
0x180141052  lea     rax, [rbp+40h+var_58]
0x180141056  lea     r8, [rbp+40h+var_50]
0x18014105a  cmovge  rax, r8
0x18014105e  mov     esi, [rbp+40h+var_68]
0x180141061  cmp     esi, [rax]
0x180141063  jge     short loc_18014106D
0x180141065  mov     r15d, esi
0x180141068  mov     [rbp+40h+var_C0], esi
0x18014106b  jmp     short loc_18014108F
0x18014106d  cmp     edx, ecx
0x18014106f  mov     eax, ecx
0x180141071  cmovl   eax, edx
0x180141074  cmp     r10d, eax
0x180141077  jge     short loc_180141082
0x180141079  mov     r15d, r10d
0x18014107c  mov     [rbp+40h+var_C0], r10d
0x180141080  jmp     short loc_18014108F
0x180141082  cmp     edx, ecx
0x180141084  mov     r15d, ecx
0x180141087  cmovl   r15d, edx
0x18014108b  mov     [rbp+40h+var_C0], r15d
0x18014108f  mov     r8d, [rbp+40h+var_4C]
0x180141093  mov     eax, r8d
0x180141096  mov     r9d, [rbp+40h+var_54]
0x18014109a  cmp     r9d, r8d
0x18014109d  mov     r11d, [rbp+40h+var_5C]
0x1801410a1  cmovl   eax, r9d
0x1801410a5  cmp     r11d, eax
0x1801410a8  jge     short loc_1801410B0
0x1801410aa  lea     rax, [rbp+40h+var_5C]
0x1801410ae  jmp     short loc_1801410BF
0x1801410b0  cmp     r9d, r8d
0x1801410b3  lea     rax, [rbp+40h+var_54]
0x1801410b7  lea     rdi, [rbp+40h+var_4C]
0x1801410bb  cmovge  rax, rdi
0x1801410bf  mov     edi, [rbp+40h+var_64]
0x1801410c2  cmp     edi, [rax]
0x1801410c4  jge     short loc_1801410CB
0x1801410c6  mov     r12d, edi
0x1801410c9  jmp     short loc_1801410E9
0x1801410cb  cmp     r9d, r8d
0x1801410ce  mov     eax, r8d
0x1801410d1  cmovl   eax, r9d
0x1801410d5  cmp     r11d, eax
0x1801410d8  jge     short loc_1801410DF
0x1801410da  mov     r12d, r11d
0x1801410dd  jmp     short loc_1801410E9
0x1801410df  cmp     r9d, r8d
0x1801410e2  mov     r12d, r8d
0x1801410e5  cmovl   r12d, r9d
0x1801410e9  cmp     edx, ecx
0x1801410eb  mov     eax, ecx
0x1801410ed  cmovg   eax, edx
0x1801410f0  cmp     r10d, eax
0x1801410f3  jle     short loc_1801410FB
0x1801410f5  lea     rax, [rbp+40h+var_60]
0x1801410f9  jmp     short loc_18014110E
0x1801410fb  lea     r14, [rbp+40h+var_50]
0x1801410ff  cmp     edx, ecx
0x180141101  lea     rax, [rbp+40h+var_58]
0x180141105  cmovle  rax, r14
0x180141109  mov     r14d, [rsp+140h+var_E0]
0x18014110e  cmp     esi, [rax]
0x180141110  jg      short loc_18014112A
0x180141112  cmp     edx, ecx
0x180141114  mov     eax, ecx
0x180141116  cmovg   eax, edx
0x180141119  cmp     r10d, eax
0x18014111c  jle     short loc_180141123
0x18014111e  mov     esi, r10d
0x180141121  jmp     short loc_18014112A
0x180141123  cmp     edx, ecx
0x180141125  mov     esi, ecx
0x180141127  cmovg   esi, edx
0x18014112a  cmp     r9d, r8d
0x18014112d  mov     eax, r8d
0x180141130  cmovg   eax, r9d
0x180141134  cmp     r11d, eax
0x180141137  jle     short loc_18014113F
0x180141139  lea     rax, [rbp+40h+var_5C]
0x18014113d  jmp     short loc_18014114E
0x18014113f  cmp     r9d, r8d
0x180141142  lea     rax, [rbp+40h+var_54]
0x180141146  lea     rcx, [rbp+40h+var_4C]
0x18014114a  cmovle  rax, rcx
0x18014114e  cmp     edi, [rax]
0x180141150  jg      short loc_180141170
0x180141152  cmp     r9d, r8d
0x180141155  mov     eax, r8d
0x180141158  cmovg   eax, r9d
0x18014115c  cmp     r11d, eax
0x18014115f  jle     short loc_180141166
0x180141161  mov     edi, r11d
0x180141164  jmp     short loc_180141170
0x180141166  cmp     r9d, r8d
0x180141169  mov     edi, r8d
0x18014116c  cmovg   edi, r9d
0x180141170  mov     eax, r14d
0x180141173  and     r14d, 0CCCC0000h
0x18014117a  and     eax, 0F3330000h
0x18014117f  shl     eax, 2
0x180141182  mov     [rbp+40h+var_9C], eax
0x180141185  cmp     r14d, eax
0x180141188  jz      loc_180141345
0x18014118e  lea     rcx, [rbx+0E4h]; lpxf
0x180141195  call    hdcMakeCompatibleDC
0x18014119a  mov     r13, rax
0x18014119d  test    rax, rax
0x1801411a0  jz      loc_1801414BB
0x1801411a6  mov     eax, dword ptr [rbp+40h+uBytes]
0x1801411ac  cmp     eax, 28h ; '('
0x1801411af  jnb     short loc_1801411BE
0x1801411b1  mov     [rsp+140h+var_D0], 1
0x1801411b9  jmp     loc_180141467
0x1801411be  mov     edx, 2Ch ; ','
0x1801411c3  mov     r15, rax
0x1801411c6  cmp     eax, edx
0x1801411c8  cmova   rdx, rax; uBytes
0x1801411cc  xor     ecx, ecx; uFlags
0x1801411ce  call    cs:__imp_LocalAlloc
0x1801411d4  mov     [rbp+40h+hMem], rax
0x1801411d8  test    rax, rax
0x1801411db  jz      loc_180141467
0x1801411e1  mov     rdx, [rbp+40h+Src]; Src
0x1801411e5  mov     r8, r15; Size
0x1801411e8  mov     rcx, rax; void *
0x1801411eb  call    memcpy_0
0x1801411f0  mov     rcx, [rbp+40h+hMem]
0x1801411f4  mov     eax, esi
0x1801411f6  mov     r15d, [rbp+40h+var_C0]
0x1801411fa  xor     r9d, r9d; pjBits
0x1801411fd  sub     eax, r15d
0x180141200  mov     rdx, rcx; pbmih
0x180141203  mov     [rcx+4], eax
0x180141206  mov     eax, edi
0x180141208  sub     eax, r12d
0x18014120b  mov     dword ptr [rcx+14h], 0
0x180141212  mov     [rcx+8], eax
0x180141215  lea     r8d, [r9+2]; flInit
0x180141219  mov     eax, [rbp+40h+var_BC]
0x18014121c  mov     [rsp+140h+iUsage], eax; iUsage
0x180141220  mov     [rsp+140h+pbmi], rcx; pbmi
0x180141225  mov     rcx, [rbx+28h]; hdc
0x180141229  call    cs:__imp_CreateDIBitmap
0x18014122f  mov     [rsp+140h+ho], rax
0x180141234  test    rax, rax
0x180141237  jz      loc_180141467
0x18014123d  mov     rdx, rax; h
0x180141240  mov     rcx, r13; hdc
0x180141243  call    cs:__imp_SelectObject
0x180141249  mov     [rsp+140h+h], rax
0x18014124e  test    rax, rax
0x180141251  jz      loc_180141454
0x180141257  mov     rcx, [rbp+40h+lpxf]; lpxf
0x18014125b  call    hdcMakeCompatibleDC
0x180141260  mov     [rbp+40h+hdc], rax
0x180141264  test    rax, rax
0x180141267  jz      loc_18014143A
0x18014126d  mov     eax, [rbp+40h+var_BC]
0x180141270  mov     r8d, 6; flInit
0x180141276  mov     r9, [rbp+40h+pjBits]; pjBits
0x18014127a  mov     rcx, [rbx+28h]; hdc
0x18014127e  mov     [rsp+140h+iUsage], eax; iUsage
0x180141282  mov     rax, [rbp+40h+Src]
0x180141286  mov     rdx, rax; pbmih
0x180141289  mov     [rsp+140h+pbmi], rax; pbmi
0x18014128e  call    cs:__imp_CreateDIBitmap
0x180141294  mov     [rbp+40h+var_80], rax
0x180141298  test    rax, rax
0x18014129b  jz      loc_18014143A
0x1801412a1  mov     rcx, [rbp+40h+hdc]; hdc
0x1801412a5  mov     rdx, rax; h
0x1801412a8  call    cs:__imp_SelectObject
0x1801412ae  mov     [rbp+40h+var_88], rax
0x1801412b2  test    rax, rax
0x1801412b5  jz      loc_18014143A
0x1801412bb  mov     r8d, r12d
0x1801412be  mov     edx, r15d
0x1801412c1  neg     r8d; y
0x1801412c4  neg     edx; x
0x1801412c6  xor     r9d, r9d; lppt
0x1801412c9  mov     rcx, r13; hdc
0x1801412cc  call    cs:__imp_OffsetViewportOrgEx
0x1801412d2  mov     eax, [rbp+40h+arg_40]
0x1801412d8  mov     ecx, [rbp+40h+arg_48]
0x1801412de  mov     r9d, [rbp+40h+wDest]; wDest
0x1801412e2  mov     r8d, [rbp+40h+yDest]; yDest
0x1801412e6  mov     edx, [rbp+40h+xDest]; xDest
0x1801412e9  mov     [rsp+140h+rop], 0CC0020h; rop
0x1801412f1  mov     [rsp+140h+hSrc], ecx; hSrc
0x1801412f5  mov     rcx, r13; hdcDest
0x1801412f8  mov     [rsp+140h+wSrc], eax; wSrc
0x1801412fc  mov     eax, [rbp+40h+arg_38]
0x180141302  mov     [rsp+140h+ySrc], eax; ySrc
0x180141306  mov     eax, [rbp+40h+arg_30]
0x18014130c  mov     [rsp+140h+xSrc], eax; xSrc
0x180141310  mov     rax, [rbp+40h+hdc]
0x180141314  mov     qword ptr [rsp+140h+iUsage], rax; hdcSrc
0x180141319  mov     eax, [rbp+40h+hDest]
0x18014131c  mov     dword ptr [rsp+140h+pbmi], eax; hDest
0x180141320  call    cs:__imp_StretchBlt
0x180141326  mov     rdx, [rsp+140h+h]; h
0x18014132b  test    eax, eax
0x18014132d  jz      loc_18014143F
0x180141333  mov     rcx, r13; hdc
0x180141336  call    cs:__imp_SelectObject
0x18014133c  test    rax, rax
0x18014133f  jz      loc_18014143A
0x180141345  mov     rcx, rbx
0x180141348  call    DoSaveDC
0x18014134d  test    eax, eax
0x18014134f  jz      short loc_180141382
0x180141351  mov     eax, [rbp+40h+var_A4]
0x180141354  mov     rcx, rbx
0x180141357  mov     r9d, [rbp+40h+var_A0]
0x18014135b  mov     r8d, [rbp+40h+yDest]
0x18014135f  mov     edx, [rbp+40h+xDest]
0x180141362  mov     [rsp+140h+iUsage], 1Eh
0x18014136a  mov     dword ptr [rsp+140h+pbmi], eax
0x18014136e  call    DoClipRect
0x180141373  test    eax, eax
  ... truncated ...
```
