# MF_AnyDIBits

- ea: `0x18005a5b4`
- end: `0x18005ac22`
- name: `MF_AnyDIBits`
- size: `1646`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int@<r8d>, __int16, int, int, unsigned int, unsigned int, unsigned int, UINT cLines, void *, BITMAPINFOHEADER *pbmih, UINT, unsigned int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18001f090`
- `0x1800772b0`

## callees

- `0x18001ede0`
- `0x1800200a0`
- `0x18002841c`
- `0x1800286b0`
- `0x18002c048`
- `0x180035af0`
- `0x1800462a4`
- `0x18004cde8`
- `0x18005a5b4`
- `0x18005ac28`
- `0x18005ad04`
- `0x18006c314`
- `0x18007f800`
- `0x180090c50`
- `0x180091148`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005a83a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005a83a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a947`
- `GDI32!DeleteDC` at `0x18005a91f`
- `GDI32!DeleteDC` at `0x18005a91f`
- `GDI32!pldcGet` at `0x18005a9c5`
- `GDI32!pldcGet` at `0x18005ab0b`
- `GDI32!pldcGet` at `0x18005a9c5`
- `GDI32!pldcGet` at `0x18005ab0b`
- `GDI32!GdiSetLastError` at `0x18005abf3`
- `GDI32!GdiSetLastError` at `0x18005abf3`
- `GDI32!DeleteObject` at `0x18005a933`
- `GDI32!DeleteObject` at `0x18005a933`

## pseudocode

```c
__int64 __fastcall MF_AnyDIBits(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        UINT cLines,
        char *a12,
        BITMAPINFO *pbmih,
        UINT ColorUse,
        int a15,
        int a16)
{
  int v16; // r10d
  int v17; // esi
  int v18; // r11d
  int v20; // r8d
  UINT v21; // r15d
  unsigned int v22; // r12d
  DWORD biYPelsPerMeter; // eax
  HLOCAL v24; // r15
  HDC CompatibleDC; // r13
  HBITMAP DIBitmap; // rax
  HBITMAP v27; // r12
  LONG biHeight; // r9d
  LONG v29; // edx
  LONG v30; // ecx
  int v31; // ebx
  LONG v32; // r9d
  unsigned int v33; // ebx
  __int64 v35; // r14
  MDC *v36; // rdi
  MRSTRETCHDIBITS *v37; // r11
  int biBitCount; // r8d
  int biPlanes; // edx
  LONG biWidth; // ecx
  unsigned __int64 v41; // rcx
  char *v42; // rdx
  MRSETDIBITSTODEVICE *v43; // rax
  size_t v44; // [rsp+58h] [rbp-C8h]
  size_t Size; // [rsp+68h] [rbp-B8h]
  SIZE_T uBytes; // [rsp+A0h] [rbp-80h] BYREF
  int v47; // [rsp+A8h] [rbp-78h]
  int v48; // [rsp+ACh] [rbp-74h]
  UINT start; // [rsp+B0h] [rbp-70h] BYREF
  int v50; // [rsp+B4h] [rbp-6Ch]
  void *v51; // [rsp+B8h] [rbp-68h]
  void *lpBits; // [rsp+C0h] [rbp-60h]
  struct tagBITMAPINFO bmi; // [rsp+C8h] [rbp-58h] BYREF

  v16 = a3;
  v17 = cLines;
  v18 = a2;
  v47 = a3;
  v20 = a15;
  v21 = 0;
  v50 = a4;
  v22 = 0;
  v48 = a2;
  lpBits = a12;
  start = 0;
  uBytes = 0;
  v51 = 0;
  if ( ((a15 ^ (4 * a15)) & 0xCCCC0000) != 0 )
  {
    if ( !a12
      || (a16 == 80 || a16 == 3379) && !cLines
      || !(unsigned int)bMetaGetDIBInfo(a1, 0, pbmih, &start, &uBytes, ColorUse, cLines, 0) )
    {
      return 0;
    }
    if ( pbmih->bmiHeader.biSize == 124
      && *(_DWORD *)&pbmih[1].bmiHeader.biPlanes == 1296188740
      && pbmih[2].bmiHeader.biXPelsPerMeter )
    {
      biYPelsPerMeter = pbmih[2].bmiHeader.biYPelsPerMeter;
      v51 = (char *)pbmih + (unsigned int)pbmih[2].bmiHeader.biXPelsPerMeter;
      HIDWORD(uBytes) = biYPelsPerMeter;
    }
    a4 = v50;
    v18 = v48;
    v16 = v47;
    v20 = a15;
    v22 = uBytes;
    v21 = start;
  }
  if ( a16 == 80 )
  {
    v35 = pldcGet(a1);
    if ( v35 && (a1 & 0x7F0000) != 0x660000 )
    {
      LODWORD(uBytes) = 0;
      if ( !(unsigned int)MRSETDIBITSTODEVICE::bComputeSize(v21, v22, HIDWORD(uBytes), (unsigned int *)&uBytes) )
        return 0;
      v36 = *(MDC **)(v35 + 16);
      v43 = (MRSETDIBITSTODEVICE *)MDC::pvNewRecord(v36, uBytes);
      if ( !v43 )
        return 0;
      MRSETDIBITSTODEVICE::vInit(
        v43,
        v36,
        v48,
        v47,
        a6,
        a7,
        a8,
        a9,
        a10,
        cLines,
        v22,
        a12,
        v21,
        pbmih,
        HIDWORD(uBytes),
        v51,
        ColorUse);
LABEL_61:
      *((_DWORD *)v36 + 8) |= 4u;
      *(_DWORD *)(v35 + 8) |= 0x20000000u;
      return 1;
    }
LABEL_63:
    GdiSetLastError(6);
    return 0;
  }
  if ( a16 == 81 )
  {
    v35 = pldcGet(a1);
    if ( v35 && (a1 & 0x7F0000) != 0x660000 )
    {
      LODWORD(uBytes) = 0;
      if ( !MRSTRETCHDIBITS::bComputeSize(v21, v22, HIDWORD(uBytes), (unsigned int *)&uBytes) )
        return 0;
      v36 = *(MDC **)(v35 + 16);
      v37 = (MRSTRETCHDIBITS *)MDC::pvNewRecord(v36, uBytes);
      if ( !v37 )
        return 0;
      if ( cLines )
      {
        biBitCount = pbmih->bmiHeader.biBitCount;
        biPlanes = pbmih->bmiHeader.biPlanes;
        biWidth = pbmih->bmiHeader.biWidth;
        LODWORD(uBytes) = 0;
        if ( !(unsigned int)SignedCJSCAN(biWidth, biPlanes, biBitCount, (unsigned int *)&uBytes) )
          return 0;
        v41 = a10 * (unsigned __int64)(unsigned int)uBytes;
        if ( v41 > 0xFFFFFFFF )
          return 0;
        v42 = &a12[(unsigned int)v41];
        if ( v42 < a12 )
          return 0;
      }
      else
      {
        v42 = a12;
      }
      MRSTRETCHDIBITS::vInit(
        v37,
        v36,
        v48,
        v47,
        v50,
        a5,
        a6,
        a7 - a10,
        a8,
        a9,
        cLines,
        v22,
        v42,
        v21,
        pbmih,
        ColorUse,
        HIDWORD(uBytes),
        v51,
        a15);
      goto LABEL_61;
    }
    goto LABEL_63;
  }
  if ( a16 != 3379 && a16 != 3907 )
    return 1;
  if ( !v21 )
    goto LABEL_44;
  if ( ColorUse == 2 )
    return 0;
  if ( pbmih->bmiHeader.biSize != 40
    || pbmih->bmiHeader.biPlanes == 1 && (v17 = cLines, ((pbmih->bmiHeader.biBitCount - 16) & 0xFFEF) != 0) )
  {
LABEL_44:
    LODWORD(Size) = v21;
    LODWORD(v44) = v22;
    return MF16_RecordDIBits(a1, v18, v16, a4, a5, a6, a7, a8, a9, a10, v17, v44, a12, Size, pbmih, ColorUse, v20, a16);
  }
  LODWORD(uBytes) = 0;
  memset(&bmi, 0, sizeof(bmi));
  if ( ColorUse == 1 )
    return 0;
  HIDWORD(uBytes) = 0;
  v24 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  DIBitmap = CreateDIBitmap(CompatibleDC, &pbmih->bmiHeader, 2u, 0, pbmih, 0);
  v27 = DIBitmap;
  if ( !DIBitmap )
  {
LABEL_36:
    v33 = 0;
    goto LABEL_37;
  }
  biHeight = v17;
  if ( !v17 )
    biHeight = pbmih->bmiHeader.biHeight;
  start = v17 != 0 ? a10 : 0;
  if ( SetDIBits(CompatibleDC, DIBitmap, start, biHeight, lpBits, pbmih, ColorUse) )
  {
    v29 = pbmih->bmiHeader.biHeight;
    v30 = pbmih->bmiHeader.biWidth;
    bmi.bmiHeader.biSize = pbmih->bmiHeader.biSize;
    *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = *(_QWORD *)&pbmih->bmiHeader.biXPelsPerMeter;
    bmi.bmiHeader.biHeight = v29;
    if ( v17 )
      v29 = v17;
    bmi.bmiHeader.biSizeImage = 0;
    *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
    bmi.bmiHeader.biWidth = v30;
    *(_QWORD *)&bmi.bmiHeader.biPlanes = 1572865;
    if ( (unsigned int)CBImage(v30, v29, 1, 24, (__int64)&uBytes) )
    {
      v31 = uBytes;
      v24 = LocalAlloc(0, (unsigned int)uBytes);
      if ( !v24 )
        goto LABEL_34;
      v32 = bmi.bmiHeader.biHeight;
      if ( v17 )
        v32 = v17;
      if ( GetDIBits(CompatibleDC, v27, start, v32, v24, &bmi, 0) )
      {
        LODWORD(Size) = 40;
        LODWORD(v44) = v31;
        v33 = MF16_RecordDIBits(a1, v48, v47, v50, a5, a6, a7, a8, a9, a10, v17, v44, v24, Size, &bmi, 0, a15, a16);
      }
      else
      {
LABEL_34:
        v33 = HIDWORD(uBytes);
      }
      goto LABEL_37;
    }
    goto LABEL_36;
  }
  v33 = 0;
LABEL_37:
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v27 )
    DeleteObject(v27);
  if ( v24 )
    LocalFree(v24);
  return v33;
}

```

## disassembly

```asm
0x18005a5b4  push    rbp
0x18005a5b6  push    rbx
0x18005a5b7  push    rsi
0x18005a5b8  push    rdi
0x18005a5b9  push    r12
0x18005a5bb  push    r13
0x18005a5bd  push    r14
0x18005a5bf  push    r15
0x18005a5c1  lea     rbp, [rsp+18h]
0x18005a5c6  sub     rsp, 108h
0x18005a5cd  mov     rax, cs:__security_cookie
0x18005a5d4  xor     rax, rsp
0x18005a5d7  mov     [rbp+20h+var_48], rax
0x18005a5db  mov     r13, [rbp+20h+arg_58]
0x18005a5e2  xor     r14d, r14d
0x18005a5e5  mov     rbx, [rbp+20h+pbmih]
0x18005a5ec  mov     r10d, r8d
0x18005a5ef  mov     esi, [rbp+20h+cLines]
0x18005a5f5  mov     r11d, edx
0x18005a5f8  mov     [rbp+20h+var_98], r8d
0x18005a5fc  mov     rdi, rcx
0x18005a5ff  mov     r8d, [rbp+20h+arg_70]
0x18005a606  mov     r15d, r14d
0x18005a609  mov     [rbp+20h+var_8C], r9d
0x18005a60d  mov     r12d, r14d
0x18005a610  mov     [rbp+20h+var_94], edx
0x18005a613  mov     [rbp+20h+lpBits], r13
0x18005a617  lea     eax, ds:0[r8*4]
0x18005a61f  mov     [rbp+20h+start], r14d
0x18005a623  xor     eax, r8d
0x18005a626  mov     dword ptr [rbp+20h+uBytes], r14d
0x18005a62a  mov     dword ptr [rbp+20h+uBytes+4], r14d
0x18005a62e  mov     [rbp+20h+var_88], r14
0x18005a632  test    eax, 0CCCC0000h
0x18005a637  jz      loc_18005A6D1
0x18005a63d  test    r13, r13
0x18005a640  jz      loc_18005ABFF
0x18005a646  mov     eax, [rbp+20h+arg_78]
0x18005a64c  cmp     eax, 50h ; 'P'
0x18005a64f  jz      short loc_18005A658
0x18005a651  cmp     eax, 0D33h
0x18005a656  jnz     short loc_18005A660
0x18005a658  test    esi, esi
0x18005a65a  jz      loc_18005ABFF
0x18005a660  mov     eax, [rbp+20h+arg_68]
0x18005a666  lea     r9, [rbp+20h+start]
0x18005a66a  mov     [rsp+140h+var_108], r14d
0x18005a66f  mov     r8, rbx
0x18005a672  mov     [rsp+140h+ColorUse], esi
0x18005a676  xor     edx, edx
0x18005a678  mov     [rsp+140h+iUsage], eax
0x18005a67c  lea     rax, [rbp+20h+uBytes]
0x18005a680  mov     [rsp+140h+pbmi], rax
0x18005a685  call    bMetaGetDIBInfo
0x18005a68a  test    eax, eax
0x18005a68c  jz      loc_18005ABFF
0x18005a692  cmp     dword ptr [rbx], 7Ch ; '|'
0x18005a695  jnz     short loc_18005A6B6
0x18005a697  cmp     dword ptr [rbx+38h], 4D424544h
0x18005a69e  jnz     short loc_18005A6B6
0x18005a6a0  cmp     [rbx+70h], r14d
0x18005a6a4  jz      short loc_18005A6B6
0x18005a6a6  mov     edx, [rbx+70h]
0x18005a6a9  mov     eax, [rbx+74h]
0x18005a6ac  add     rdx, rbx
0x18005a6af  mov     [rbp+20h+var_88], rdx
0x18005a6b3  mov     dword ptr [rbp+20h+uBytes+4], eax
0x18005a6b6  mov     r9d, [rbp+20h+var_8C]; int
0x18005a6ba  mov     r11d, [rbp+20h+var_94]
0x18005a6be  mov     r10d, [rbp+20h+var_98]
0x18005a6c2  mov     r8d, [rbp+20h+arg_70]
0x18005a6c9  mov     r12d, dword ptr [rbp+20h+uBytes]
0x18005a6cd  mov     r15d, [rbp+20h+start]
0x18005a6d1  mov     ecx, [rbp+20h+arg_78]
0x18005a6d7  mov     eax, ecx
0x18005a6d9  sub     eax, 50h ; 'P'
0x18005a6dc  jz      loc_18005AB08
0x18005a6e2  sub     eax, 1
0x18005a6e5  jz      loc_18005A9C2
0x18005a6eb  sub     eax, 0CE2h
0x18005a6f0  jz      short loc_18005A6FD
0x18005a6f2  cmp     eax, 210h
0x18005a6f7  jnz     loc_18005ABE7
0x18005a6fd  mov     edx, [rbp+20h+arg_68]
0x18005a703  test    r15d, r15d
0x18005a706  jz      loc_18005A95A
0x18005a70c  cmp     edx, 2
0x18005a70f  jz      loc_18005ABFF
0x18005a715  cmp     dword ptr [rbx], 28h ; '('
0x18005a718  jnz     loc_18005A95A
0x18005a71e  mov     r14d, 1
0x18005a724  cmp     [rbx+0Ch], r14w
0x18005a729  jnz     short loc_18005A747
0x18005a72b  movzx   eax, word ptr [rbx+0Eh]
0x18005a72f  mov     esi, 0FFEFh
0x18005a734  sub     ax, 10h
0x18005a738  test    si, ax
0x18005a73b  mov     esi, [rbp+20h+cLines]
0x18005a741  jnz     loc_18005A95A
0x18005a747  xorps   xmm0, xmm0
0x18005a74a  xor     r12d, r12d
0x18005a74d  mov     dword ptr [rbp+20h+uBytes], r12d
0x18005a751  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biCompression], xmm0
0x18005a755  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biYPelsPerMeter], xmm0
0x18005a759  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biSize], xmm0
0x18005a75d  cmp     edx, r14d
0x18005a760  jz      loc_18005ABFF
0x18005a766  xor     ecx, ecx; hdc
0x18005a768  mov     dword ptr [rbp+20h+uBytes+4], r12d
0x18005a76c  mov     r15d, r12d
0x18005a76f  call    CreateCompatibleDC
0x18005a774  xor     r9d, r9d; pjBits
0x18005a777  mov     [rsp+140h+iUsage], r12d; iUsage
0x18005a77c  lea     r8d, [r12+2]; flInit
0x18005a781  mov     [rsp+140h+pbmi], rbx; pbmi
0x18005a786  mov     rdx, rbx; pbmih
0x18005a789  mov     rcx, rax; hdc
0x18005a78c  mov     r13, rax
0x18005a78f  call    CreateDIBitmap
0x18005a794  mov     r12, rax
0x18005a797  test    rax, rax
0x18005a79a  jz      loc_18005A914
0x18005a7a0  mov     r9d, esi
0x18005a7a3  test    esi, esi
0x18005a7a5  jnz     short loc_18005A7AB
0x18005a7a7  mov     r9d, [rbx+8]; cLines
0x18005a7ab  mov     eax, esi
0x18005a7ad  mov     rdx, r12; hbm
0x18005a7b0  neg     eax
0x18005a7b2  mov     eax, [rbp+20h+arg_68]
0x18005a7b8  mov     [rsp+140h+ColorUse], eax; ColorUse
0x18005a7bc  sbb     ecx, ecx
0x18005a7be  and     ecx, [rbp+20h+arg_48]
0x18005a7c1  mov     rax, [rbp+20h+lpBits]
0x18005a7c5  mov     r8d, ecx; start
0x18005a7c8  mov     [rbp+20h+start], ecx
0x18005a7cb  mov     rcx, r13; hdc
0x18005a7ce  mov     qword ptr [rsp+140h+iUsage], rbx; lpbmi
0x18005a7d3  mov     [rsp+140h+pbmi], rax; lpBits
0x18005a7d8  call    SetDIBits
0x18005a7dd  xor     r8d, r8d
0x18005a7e0  test    eax, eax
0x18005a7e2  jz      loc_18005A90F
0x18005a7e8  mov     edx, [rbx+8]
0x18005a7eb  lea     r9d, [r8+18h]
0x18005a7ef  mov     eax, [rbx]
0x18005a7f1  test    esi, esi
0x18005a7f3  mov     ecx, [rbx+4]
0x18005a7f6  mov     [rbp+20h+bmi.bmiHeader.biSize], eax
0x18005a7f9  mov     rax, [rbx+18h]
0x18005a7fd  mov     qword ptr [rbp+20h+bmi.bmiHeader.biXPelsPerMeter], rax
0x18005a801  lea     rax, [rbp+20h+uBytes]
0x18005a805  mov     [rbp+20h+bmi.bmiHeader.biHeight], edx
0x18005a808  cmovnz  edx, esi
0x18005a80b  mov     [rbp+20h+bmi.bmiHeader.biSizeImage], r8d
0x18005a80f  mov     qword ptr [rbp+20h+bmi.bmiHeader.biClrUsed], r8
0x18005a813  mov     r8d, r14d
0x18005a816  mov     [rsp+140h+pbmi], rax
0x18005a81b  mov     [rbp+20h+bmi.bmiHeader.biWidth], ecx
0x18005a81e  mov     qword ptr [rbp+20h+bmi.bmiHeader.biPlanes], 180001h
0x18005a826  call    CBImage
0x18005a82b  test    eax, eax
0x18005a82d  jz      loc_18005A914
0x18005a833  mov     ebx, dword ptr [rbp+20h+uBytes]
0x18005a836  xor     ecx, ecx; uFlags
0x18005a838  mov     edx, ebx; uBytes
0x18005a83a  call    cs:__imp_LocalAlloc
0x18005a841  nop     dword ptr [rax+rax+00h]
0x18005a846  mov     r15, rax
0x18005a849  test    rax, rax
0x18005a84c  jz      loc_18005A90A
0x18005a852  mov     r9d, [rbp+20h+bmi.bmiHeader.biHeight]
0x18005a856  lea     rax, [rbp+20h+bmi]
0x18005a85a  mov     r8d, [rbp+20h+start]; start
0x18005a85e  test    esi, esi
0x18005a860  mov     [rsp+140h+ColorUse], 0; usage
0x18005a868  mov     rdx, r12; hbm
0x18005a86b  mov     qword ptr [rsp+140h+iUsage], rax; lpbmi
0x18005a870  cmovnz  r9d, esi; cLines
0x18005a874  mov     rcx, r13; hdc
0x18005a877  mov     [rsp+140h+pbmi], r15; lpvBits
0x18005a87c  call    GetDIBits
0x18005a881  test    eax, eax
0x18005a883  jz      loc_18005A90A
0x18005a889  mov     eax, [rbp+20h+arg_78]
0x18005a88f  mov     rcx, rdi; int
0x18005a892  mov     r9d, [rbp+20h+var_8C]; int
0x18005a896  mov     r8d, [rbp+20h+var_98]; int
0x18005a89a  mov     edx, [rbp+20h+var_94]; int
0x18005a89d  mov     dword ptr [rsp+140h+var_B8], eax; int
0x18005a8a4  mov     eax, [rbp+20h+arg_70]
0x18005a8aa  mov     [rsp+140h+var_C0], eax; int
0x18005a8b1  lea     rax, [rbp+20h+bmi]
0x18005a8b5  mov     dword ptr [rsp+140h+var_C8], 0; int
0x18005a8bd  mov     [rsp+140h+Src], rax; Src
0x18005a8c2  mov     eax, [rbp+20h+arg_48]
0x18005a8c5  mov     dword ptr [rsp+140h+Size], 28h ; '('; Size
0x18005a8cd  mov     [rsp+140h+var_E0], r15; void *
0x18005a8d2  mov     dword ptr [rsp+140h+var_E8], ebx; size_t
0x18005a8d6  mov     [rsp+140h+var_F0], esi; int
0x18005a8da  mov     [rsp+140h+var_F8], eax; __int16
0x18005a8de  mov     eax, [rbp+20h+arg_40]
0x18005a8e1  mov     [rsp+140h+var_100], eax; int
0x18005a8e5  mov     eax, [rbp+20h+arg_38]
0x18005a8e8  mov     [rsp+140h+var_108], eax; int
0x18005a8ec  mov     eax, [rbp+20h+arg_30]
0x18005a8ef  mov     [rsp+140h+ColorUse], eax; int
0x18005a8f3  mov     eax, [rbp+20h+arg_28]
0x18005a8f6  mov     [rsp+140h+iUsage], eax; int
0x18005a8fa  mov     eax, dword ptr [rbp+20h+arg_20]
0x18005a8fd  mov     dword ptr [rsp+140h+pbmi], eax; __int16
0x18005a901  call    MF16_RecordDIBits
0x18005a906  mov     ebx, eax
0x18005a908  jmp     short loc_18005A917
0x18005a90a  mov     ebx, dword ptr [rbp+20h+uBytes+4]
0x18005a90d  jmp     short loc_18005A917
0x18005a90f  mov     ebx, r8d
0x18005a912  jmp     short loc_18005A917
0x18005a914  mov     ebx, r15d
0x18005a917  test    r13, r13
0x18005a91a  jz      short loc_18005A92B
0x18005a91c  mov     rcx, r13; hdc
0x18005a91f  call    cs:__imp_DeleteDC
0x18005a926  nop     dword ptr [rax+rax+00h]
0x18005a92b  test    r12, r12
0x18005a92e  jz      short loc_18005A93F
0x18005a930  mov     rcx, r12; ho
0x18005a933  call    cs:__imp_DeleteObject
0x18005a93a  nop     dword ptr [rax+rax+00h]
0x18005a93f  test    r15, r15
0x18005a942  jz      short loc_18005A953
0x18005a944  mov     rcx, r15; hMem
0x18005a947  call    cs:__imp_LocalFree
0x18005a94e  nop     dword ptr [rax+rax+00h]
0x18005a953  mov     eax, ebx
0x18005a955  jmp     loc_18005AC01
0x18005a95a  mov     eax, [rbp+20h+arg_48]
0x18005a95d  mov     dword ptr [rsp+140h+var_B8], ecx; int
0x18005a964  mov     rcx, rdi; int
0x18005a967  mov     [rsp+140h+var_C0], r8d; int
0x18005a96f  mov     r8d, r10d; int
0x18005a972  mov     dword ptr [rsp+140h+var_C8], edx; int
0x18005a976  mov     edx, r11d; int
0x18005a979  mov     [rsp+140h+Src], rbx; Src
0x18005a97e  mov     dword ptr [rsp+140h+Size], r15d; Size
0x18005a983  mov     [rsp+140h+var_E0], r13; void *
0x18005a988  mov     dword ptr [rsp+140h+var_E8], r12d; size_t
0x18005a98d  mov     [rsp+140h+var_F0], esi; int
0x18005a991  mov     [rsp+140h+var_F8], eax; __int16
0x18005a995  mov     eax, [rbp+20h+arg_40]
0x18005a998  mov     [rsp+140h+var_100], eax; int
0x18005a99c  mov     eax, [rbp+20h+arg_38]
0x18005a99f  mov     [rsp+140h+var_108], eax; int
0x18005a9a3  mov     eax, [rbp+20h+arg_30]
0x18005a9a6  mov     [rsp+140h+ColorUse], eax; int
0x18005a9aa  mov     eax, [rbp+20h+arg_28]
0x18005a9ad  mov     [rsp+140h+iUsage], eax; int
0x18005a9b1  mov     eax, dword ptr [rbp+20h+arg_20]
0x18005a9b4  mov     dword ptr [rsp+140h+pbmi], eax; __int16
0x18005a9b8  call    MF16_RecordDIBits
0x18005a9bd  jmp     loc_18005AC01
0x18005a9c2  mov     rcx, rdi
0x18005a9c5  call    cs:__imp_pldcGet
0x18005a9cc  nop     dword ptr [rax+rax+00h]
0x18005a9d1  mov     r14, rax
0x18005a9d4  test    rax, rax
0x18005a9d7  jz      loc_18005ABEE
0x18005a9dd  and     edi, 7F0000h
0x18005a9e3  cmp     edi, 660000h
0x18005a9e9  jz      loc_18005ABEE
0x18005a9ef  mov     r8d, dword ptr [rbp+20h+uBytes+4]; unsigned int
0x18005a9f3  lea     r9, [rbp+20h+uBytes]; unsigned int *
0x18005a9f7  mov     edx, r12d; unsigned int
0x18005a9fa  mov     dword ptr [rbp+20h+uBytes], 0
0x18005aa01  mov     ecx, r15d; unsigned int
0x18005aa04  call    ?bComputeSize@MRSTRETCHDIBITS@@SAHKKKPEAK@Z; MRSTRETCHDIBITS::bComputeSize(ulong,ulong,ulong,ulong *)
0x18005aa09  test    eax, eax
0x18005aa0b  jz      loc_18005ABFF
0x18005aa11  mov     rdi, [r14+10h]
0x18005aa15  mov     edx, dword ptr [rbp+20h+uBytes]; unsigned int
0x18005aa18  mov     rcx, rdi; this
0x18005aa1b  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x18005aa20  mov     r11, rax
0x18005aa23  test    rax, rax
0x18005aa26  jz      loc_18005ABFF
0x18005aa2c  test    esi, esi
0x18005aa2e  jz      short loc_18005AA7B
0x18005aa30  movzx   r8d, word ptr [rbx+0Eh]; int
0x18005aa35  lea     r9, [rbp+20h+uBytes]; unsigned int *
0x18005aa39  movzx   edx, word ptr [rbx+0Ch]; int
0x18005aa3d  mov     ecx, [rbx+4]; int
0x18005aa40  mov     dword ptr [rbp+20h+uBytes], 0
0x18005aa47  call    ?SignedCJSCAN@@YAHJJJPEAK@Z; SignedCJSCAN(long,long,long,ulong *)
0x18005aa4c  test    eax, eax
0x18005aa4e  jz      loc_18005ABFF
0x18005aa54  mov     eax, [rbp+20h+arg_48]
0x18005aa57  mov     ecx, dword ptr [rbp+20h+uBytes]
0x18005aa5a  imul    rcx, rax
0x18005aa5e  mov     eax, 0FFFFFFFFh
0x18005aa63  cmp     rcx, rax
  ... truncated ...
```
