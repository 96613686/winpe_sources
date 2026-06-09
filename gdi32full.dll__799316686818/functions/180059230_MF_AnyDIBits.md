# MF_AnyDIBits

- ea: `0x180059230`
- end: `0x1800598ab`
- name: `MF_AnyDIBits`
- size: `1659`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int@<r8d>, __int16, int, int, unsigned int, unsigned int, unsigned int, UINT cLines, void *, BITMAPINFOHEADER *pbmih, UINT, unsigned int, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001f310`
- `0x180072b80`

## callees

- `0x18001ec70`
- `0x18001f0a0`
- `0x18001fe20`
- `0x180023110`
- `0x18003a744`
- `0x180041510`
- `0x180059230`
- `0x1800598b4`
- `0x18005ce70`
- `0x18005d100`
- `0x180067b78`
- `0x18007ac50`
- `0x18008b4e4`
- `0x18008b9c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800594b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800595a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800595a7`
- `GDI32!DeleteDC` at `0x18005958b`
- `GDI32!DeleteDC` at `0x18005958b`
- `GDI32!pldcGet` at `0x180059623`
- `GDI32!pldcGet` at `0x1800597a1`
- `GDI32!pldcGet` at `0x180059623`
- `GDI32!pldcGet` at `0x1800597a1`
- `GDI32!GdiSetLastError` at `0x180059883`
- `GDI32!GdiSetLastError` at `0x180059883`
- `GDI32!DeleteObject` at `0x180059599`
- `GDI32!DeleteObject` at `0x180059599`

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
        unsigned int a15,
        int a16)
{
  void *v16; // r14
  unsigned int v17; // esi
  unsigned int v18; // r13d
  int v19; // r10d
  DWORD biYPelsPerMeter; // r12d
  int v21; // r8d
  int v22; // r11d
  HLOCAL v24; // rsi
  HDC CompatibleDC; // r13
  HBITMAP DIBitmap; // rax
  HBITMAP v27; // r12
  LONG biHeight; // r9d
  UINT v29; // edx
  LONG v30; // ecx
  int v31; // ebx
  LONG v32; // r9d
  unsigned int v33; // ebx
  _QWORD *v35; // rax
  unsigned int v36; // edx
  unsigned int v37; // ecx
  unsigned int v38; // edx
  MDC *v39; // rdi
  MRSTRETCHDIBITS *v40; // r11
  int biBitCount; // r8d
  int biPlanes; // edx
  LONG biWidth; // ecx
  unsigned __int64 v44; // rcx
  char *v45; // rdx
  _DWORD *v46; // rax
  __int64 v47; // r14
  MDC *v48; // rdi
  MRSETDIBITSTODEVICE *v49; // rax
  size_t v50; // [rsp+58h] [rbp-C8h]
  size_t Size; // [rsp+68h] [rbp-B8h]
  SIZE_T uBytes; // [rsp+A0h] [rbp-80h] BYREF
  int v53; // [rsp+A8h] [rbp-78h]
  int v54; // [rsp+ACh] [rbp-74h]
  int v55; // [rsp+B0h] [rbp-70h]
  UINT start[2]; // [rsp+B8h] [rbp-68h]
  void *lpBits; // [rsp+C0h] [rbp-60h]
  struct tagBITMAPINFO bmi; // [rsp+C8h] [rbp-58h] BYREF

  v16 = a12;
  v17 = 0;
  v18 = 0;
  v19 = a3;
  v53 = a3;
  biYPelsPerMeter = 0;
  v21 = a15;
  v22 = a2;
  v55 = a4;
  v54 = a2;
  lpBits = a12;
  uBytes = 0;
  *(_QWORD *)start = 0;
  if ( ((a15 ^ (4 * a15)) & 0xCCCC0000) != 0 )
  {
    if ( !a12
      || (a16 == 80 || a16 == 3379) && !cLines
      || !(unsigned int)bMetaGetDIBInfo(a1, 0, pbmih, (char *)&uBytes + 4, &uBytes, ColorUse, cLines, 0) )
    {
      return 0;
    }
    if ( pbmih->bmiHeader.biSize == 124
      && *(_DWORD *)&pbmih[1].bmiHeader.biPlanes == 1296188740
      && pbmih[2].bmiHeader.biXPelsPerMeter )
    {
      biYPelsPerMeter = pbmih[2].bmiHeader.biYPelsPerMeter;
      *(_QWORD *)start = (char *)pbmih + (unsigned int)pbmih[2].bmiHeader.biXPelsPerMeter;
    }
    a4 = v55;
    v22 = v54;
    v19 = v53;
    v21 = a15;
    v18 = uBytes;
    v17 = HIDWORD(uBytes);
  }
  if ( a16 == 80 )
  {
    v47 = pldcGet(a1);
    if ( v47 && (a1 & 0x7F0000) != 0x660000 )
    {
      LODWORD(uBytes) = 0;
      if ( !(unsigned int)MRSETDIBITSTODEVICE::bComputeSize(v17, v18, biYPelsPerMeter, (unsigned int *)&uBytes) )
        return 0;
      v48 = *(MDC **)(v47 + 16);
      v49 = (MRSETDIBITSTODEVICE *)MDC::pvNewRecord(v48, uBytes);
      if ( !v49 )
        return 0;
      MRSETDIBITSTODEVICE::vInit(
        v49,
        v48,
        v54,
        v53,
        a6,
        a7,
        a8,
        a9,
        a10,
        cLines,
        v18,
        lpBits,
        v17,
        pbmih,
        biYPelsPerMeter,
        *(const void **)start,
        ColorUse);
      *((_DWORD *)v48 + 8) |= 4u;
      *(_DWORD *)(v47 + 8) |= 0x20000000u;
      return 1;
    }
LABEL_67:
    GdiSetLastError(6);
    return 0;
  }
  if ( a16 == 81 )
  {
    v35 = (_QWORD *)pldcGet(a1);
    lpBits = v35;
    if ( v35 && (a1 & 0x7F0000) != 0x660000 )
    {
      if ( v17 > 0xFFFFFFFC )
        return 0;
      if ( v18 > 0xFFFFFFFC )
        return 0;
      if ( biYPelsPerMeter > 0xFFFFFFFC )
        return 0;
      v36 = ((v17 + 3) & 0xFFFFFFFC) + 80;
      if ( ((v17 + 3) & 0xFFFFFFFC) >= 0xFFFFFFB0 )
        return 0;
      v37 = v36 + ((v18 + 3) & 0xFFFFFFFC);
      if ( v37 < v36 )
        return 0;
      v38 = v37 + ((biYPelsPerMeter + 3) & 0xFFFFFFFC);
      if ( v38 < v37 )
        return 0;
      v39 = (MDC *)v35[2];
      v40 = (MRSTRETCHDIBITS *)MDC::pvNewRecord(v39, v38);
      if ( !v40 )
        return 0;
      if ( cLines )
      {
        biBitCount = pbmih->bmiHeader.biBitCount;
        biPlanes = pbmih->bmiHeader.biPlanes;
        biWidth = pbmih->bmiHeader.biWidth;
        LODWORD(uBytes) = 0;
        if ( !(unsigned int)SignedCJSCAN(biWidth, biPlanes, biBitCount, (unsigned int *)&uBytes) )
          return 0;
        v44 = a10 * (unsigned __int64)(unsigned int)uBytes;
        if ( v44 > 0xFFFFFFFF )
          return 0;
        v45 = &a12[(unsigned int)v44];
        if ( v45 < a12 )
          return 0;
      }
      else
      {
        v45 = a12;
      }
      MRSTRETCHDIBITS::vInit(
        v40,
        v39,
        v54,
        v53,
        v55,
        a5,
        a6,
        a7 - a10,
        a8,
        a9,
        cLines,
        v18,
        v45,
        v17,
        pbmih,
        ColorUse,
        biYPelsPerMeter,
        *(const void **)start,
        a15);
      v46 = lpBits;
      *((_DWORD *)v39 + 8) |= 4u;
      v46[2] |= 0x20000000u;
      return 1;
    }
    goto LABEL_67;
  }
  if ( a16 != 3379 && a16 != 3907 )
    return 1;
  if ( !v17 )
    goto LABEL_44;
  if ( ColorUse == 2 )
    return 0;
  if ( pbmih->bmiHeader.biSize != 40 )
  {
LABEL_44:
    LODWORD(Size) = v17;
    LODWORD(v50) = v18;
    return MF16_RecordDIBits(
             a1,
             v22,
             v19,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9,
             a10,
             cLines,
             v50,
             v16,
             Size,
             pbmih,
             ColorUse,
             v21,
             a16);
  }
  if ( pbmih->bmiHeader.biPlanes == 1 && ((pbmih->bmiHeader.biBitCount - 16) & 0xFFEF) != 0 )
  {
    v16 = lpBits;
    goto LABEL_44;
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
    goto LABEL_35;
  biHeight = cLines;
  if ( !cLines )
    biHeight = pbmih->bmiHeader.biHeight;
  start[0] = cLines != 0 ? a10 : 0;
  if ( !SetDIBits(CompatibleDC, DIBitmap, start[0], biHeight, lpBits, pbmih, ColorUse) )
    goto LABEL_35;
  v29 = pbmih->bmiHeader.biHeight;
  v30 = pbmih->bmiHeader.biWidth;
  bmi.bmiHeader.biSize = pbmih->bmiHeader.biSize;
  *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = *(_QWORD *)&pbmih->bmiHeader.biXPelsPerMeter;
  bmi.bmiHeader.biHeight = v29;
  if ( cLines )
    v29 = cLines;
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
    if ( cLines )
      v32 = cLines;
    if ( GetDIBits(CompatibleDC, v27, start[0], v32, v24, &bmi, 0) )
    {
      LODWORD(Size) = 40;
      LODWORD(v50) = v31;
      v33 = MF16_RecordDIBits(a1, v54, v53, v55, a5, a6, a7, a8, a9, a10, cLines, v50, v24, Size, &bmi, 0, a15, a16);
    }
    else
    {
LABEL_34:
      v33 = HIDWORD(uBytes);
    }
  }
  else
  {
LABEL_35:
    v33 = 0;
  }
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
0x180059230  push    rbp
0x180059232  push    rbx
0x180059233  push    rsi
0x180059234  push    rdi
0x180059235  push    r12
0x180059237  push    r13
0x180059239  push    r14
0x18005923b  push    r15
0x18005923d  lea     rbp, [rsp+18h]
0x180059242  sub     rsp, 108h
0x180059249  mov     rax, cs:__security_cookie
0x180059250  xor     rax, rsp
0x180059253  mov     [rbp+20h+var_48], rax
0x180059257  mov     r14, [rbp+20h+arg_58]
0x18005925e  xor     esi, esi
0x180059260  mov     rbx, [rbp+20h+pbmih]
0x180059267  xor     r13d, r13d
0x18005926a  mov     r15d, [rbp+20h+cLines]
0x180059271  mov     r10d, r8d
0x180059274  mov     [rbp+20h+var_98], r8d
0x180059278  xor     r12d, r12d
0x18005927b  mov     r8d, [rbp+20h+arg_70]
0x180059282  mov     r11d, edx
0x180059285  mov     [rbp+20h+var_90], r9d
0x180059289  mov     rdi, rcx
0x18005928c  mov     [rbp+20h+var_94], edx
0x18005928f  mov     [rbp+20h+lpBits], r14
0x180059293  lea     eax, ds:0[r8*4]
0x18005929b  mov     dword ptr [rbp+20h+uBytes+4], esi
0x18005929e  xor     eax, r8d
0x1800592a1  mov     dword ptr [rbp+20h+uBytes], r13d
0x1800592a5  mov     qword ptr [rbp+20h+start], rsi
0x1800592a9  test    eax, 0CCCC0000h
0x1800592ae  jz      loc_180059348
0x1800592b4  test    r14, r14
0x1800592b7  jz      loc_180059889
0x1800592bd  mov     eax, [rbp+20h+arg_78]
0x1800592c3  cmp     eax, 50h ; 'P'
0x1800592c6  jz      short loc_1800592CF
0x1800592c8  cmp     eax, 0D33h
0x1800592cd  jnz     short loc_1800592D8
0x1800592cf  test    r15d, r15d
0x1800592d2  jz      loc_180059889
0x1800592d8  mov     ecx, [rbp+20h+arg_68]
0x1800592de  lea     rax, [rbp+20h+uBytes]
0x1800592e2  mov     [rsp+140h+var_108], esi
0x1800592e6  lea     r9, [rbp+20h+uBytes+4]
0x1800592ea  mov     [rsp+140h+ColorUse], r15d
0x1800592ef  mov     r8, rbx
0x1800592f2  mov     [rsp+140h+iUsage], ecx
0x1800592f6  xor     edx, edx
0x1800592f8  mov     rcx, rdi
0x1800592fb  mov     [rsp+140h+pbmi], rax
0x180059300  call    bMetaGetDIBInfo
0x180059305  test    eax, eax
0x180059307  jz      loc_180059889
0x18005930d  cmp     dword ptr [rbx], 7Ch ; '|'
0x180059310  jnz     short loc_18005932E
0x180059312  cmp     dword ptr [rbx+38h], 4D424544h
0x180059319  jnz     short loc_18005932E
0x18005931b  cmp     [rbx+70h], esi
0x18005931e  jz      short loc_18005932E
0x180059320  mov     edx, [rbx+70h]
0x180059323  mov     r12d, [rbx+74h]
0x180059327  add     rdx, rbx
0x18005932a  mov     qword ptr [rbp+20h+start], rdx
0x18005932e  mov     r9d, [rbp+20h+var_90]; int
0x180059332  mov     r11d, [rbp+20h+var_94]
0x180059336  mov     r10d, [rbp+20h+var_98]
0x18005933a  mov     r8d, [rbp+20h+arg_70]
0x180059341  mov     r13d, dword ptr [rbp+20h+uBytes]
0x180059345  mov     esi, dword ptr [rbp+20h+uBytes+4]
0x180059348  mov     ecx, [rbp+20h+arg_78]
0x18005934e  mov     eax, ecx
0x180059350  sub     eax, 50h ; 'P'
0x180059353  jz      loc_18005979E
0x180059359  sub     eax, 1
0x18005935c  jz      loc_180059620
0x180059362  sub     eax, 0CE2h
0x180059367  jz      short loc_180059374
0x180059369  cmp     eax, 210h
0x18005936e  jnz     loc_180059877
0x180059374  mov     edx, [rbp+20h+arg_68]
0x18005937a  test    esi, esi
0x18005937c  jz      loc_1800595B8
0x180059382  cmp     edx, 2
0x180059385  jz      loc_180059889
0x18005938b  cmp     dword ptr [rbx], 28h ; '('
0x18005938e  jnz     loc_1800595B8
0x180059394  mov     r14d, 1
0x18005939a  cmp     [rbx+0Ch], r14w
0x18005939f  jnz     short loc_1800593B9
0x1800593a1  movzx   eax, word ptr [rbx+0Eh]
0x1800593a5  mov     r12d, 0FFEFh
0x1800593ab  sub     ax, 10h
0x1800593af  test    r12w, ax
0x1800593b3  jnz     loc_1800595B4
0x1800593b9  xorps   xmm0, xmm0
0x1800593bc  xor     r12d, r12d
0x1800593bf  mov     dword ptr [rbp+20h+uBytes], r12d
0x1800593c3  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biCompression], xmm0
0x1800593c7  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biYPelsPerMeter], xmm0
0x1800593cb  movups  xmmword ptr [rbp+20h+bmi.bmiHeader.biSize], xmm0
0x1800593cf  cmp     edx, r14d
0x1800593d2  jz      loc_180059889
0x1800593d8  xor     ecx, ecx; hdc
0x1800593da  mov     dword ptr [rbp+20h+uBytes+4], r12d
0x1800593de  mov     esi, r12d
0x1800593e1  call    CreateCompatibleDC
0x1800593e6  xor     r9d, r9d; pjBits
0x1800593e9  mov     [rsp+140h+iUsage], r12d; iUsage
0x1800593ee  lea     r8d, [r12+2]; flInit
0x1800593f3  mov     [rsp+140h+pbmi], rbx; pbmi
0x1800593f8  mov     rdx, rbx; pbmih
0x1800593fb  mov     rcx, rax; hdc
0x1800593fe  mov     r13, rax
0x180059401  call    CreateDIBitmap
0x180059406  mov     r12, rax
0x180059409  test    rax, rax
0x18005940c  jz      loc_180059581
0x180059412  mov     r9d, r15d
0x180059415  test    r15d, r15d
0x180059418  jnz     short loc_18005941E
0x18005941a  mov     r9d, [rbx+8]; cLines
0x18005941e  mov     ecx, [rbp+20h+arg_68]
0x180059424  mov     eax, r15d
0x180059427  mov     [rsp+140h+ColorUse], ecx; ColorUse
0x18005942b  neg     eax
0x18005942d  mov     rcx, [rbp+20h+lpBits]
0x180059431  mov     rdx, r12; hbm
0x180059434  sbb     eax, eax
0x180059436  mov     qword ptr [rsp+140h+iUsage], rbx; lpbmi
0x18005943b  and     eax, [rbp+20h+arg_48]
0x18005943e  mov     [rsp+140h+pbmi], rcx; lpBits
0x180059443  mov     r8d, eax; start
0x180059446  mov     rcx, r13; hdc
0x180059449  mov     [rbp+20h+start], eax
0x18005944c  call    SetDIBits
0x180059451  xor     r8d, r8d
0x180059454  test    eax, eax
0x180059456  jz      loc_180059581
0x18005945c  mov     edx, [rbx+8]
0x18005945f  lea     r9d, [r8+18h]
0x180059463  mov     eax, [rbx]
0x180059465  test    r15d, r15d
0x180059468  mov     ecx, [rbx+4]
0x18005946b  mov     [rbp+20h+bmi.bmiHeader.biSize], eax
0x18005946e  mov     rax, [rbx+18h]
0x180059472  mov     qword ptr [rbp+20h+bmi.bmiHeader.biXPelsPerMeter], rax
0x180059476  lea     rax, [rbp+20h+uBytes]
0x18005947a  mov     [rbp+20h+bmi.bmiHeader.biHeight], edx
0x18005947d  cmovnz  edx, r15d
0x180059481  mov     [rbp+20h+bmi.bmiHeader.biSizeImage], r8d
0x180059485  mov     qword ptr [rbp+20h+bmi.bmiHeader.biClrUsed], r8
0x180059489  mov     r8d, r14d
0x18005948c  mov     [rsp+140h+pbmi], rax
0x180059491  mov     [rbp+20h+bmi.bmiHeader.biWidth], ecx
0x180059494  mov     qword ptr [rbp+20h+bmi.bmiHeader.biPlanes], 180001h
0x18005949c  call    CBImage
0x1800594a1  test    eax, eax
0x1800594a3  jz      loc_180059581
0x1800594a9  mov     ebx, dword ptr [rbp+20h+uBytes]
0x1800594ac  xor     ecx, ecx; uFlags
0x1800594ae  mov     edx, ebx; uBytes
0x1800594b0  call    cs:__imp_LocalAlloc
0x1800594b6  mov     rsi, rax
0x1800594b9  test    rax, rax
0x1800594bc  jz      loc_18005957C
0x1800594c2  mov     r9d, [rbp+20h+bmi.bmiHeader.biHeight]
0x1800594c6  lea     rax, [rbp+20h+bmi]
0x1800594ca  mov     r8d, [rbp+20h+start]; start
0x1800594ce  test    r15d, r15d
0x1800594d1  mov     [rsp+140h+ColorUse], 0; usage
0x1800594d9  mov     rdx, r12; hbm
0x1800594dc  mov     qword ptr [rsp+140h+iUsage], rax; lpbmi
0x1800594e1  cmovnz  r9d, r15d; cLines
0x1800594e5  mov     rcx, r13; hdc
0x1800594e8  mov     [rsp+140h+pbmi], rsi; lpvBits
0x1800594ed  call    GetDIBits
0x1800594f2  test    eax, eax
0x1800594f4  jz      loc_18005957C
0x1800594fa  mov     eax, [rbp+20h+arg_78]
0x180059500  mov     rcx, rdi; int
0x180059503  mov     r9d, [rbp+20h+var_90]; int
0x180059507  mov     r8d, [rbp+20h+var_98]; int
0x18005950b  mov     edx, [rbp+20h+var_94]; int
0x18005950e  mov     dword ptr [rsp+140h+var_B8], eax; int
0x180059515  mov     eax, [rbp+20h+arg_70]
0x18005951b  mov     [rsp+140h+var_C0], eax; int
0x180059522  lea     rax, [rbp+20h+bmi]
0x180059526  mov     dword ptr [rsp+140h+var_C8], 0; int
0x18005952e  mov     [rsp+140h+Src], rax; Src
0x180059533  mov     eax, [rbp+20h+arg_48]
0x180059536  mov     dword ptr [rsp+140h+Size], 28h ; '('; Size
0x18005953e  mov     [rsp+140h+var_E0], rsi; void *
0x180059543  mov     dword ptr [rsp+140h+var_E8], ebx; size_t
0x180059547  mov     [rsp+140h+var_F0], r15d; int
0x18005954c  mov     [rsp+140h+var_F8], eax; __int16
0x180059550  mov     eax, [rbp+20h+arg_40]
0x180059553  mov     [rsp+140h+var_100], eax; int
0x180059557  mov     eax, [rbp+20h+arg_38]
0x18005955a  mov     [rsp+140h+var_108], eax; int
0x18005955e  mov     eax, [rbp+20h+arg_30]
0x180059561  mov     [rsp+140h+ColorUse], eax; int
0x180059565  mov     eax, [rbp+20h+arg_28]
0x180059568  mov     [rsp+140h+iUsage], eax; int
0x18005956c  mov     eax, dword ptr [rbp+20h+arg_20]
0x18005956f  mov     dword ptr [rsp+140h+pbmi], eax; __int16
0x180059573  call    MF16_RecordDIBits
0x180059578  mov     ebx, eax
0x18005957a  jmp     short loc_180059583
0x18005957c  mov     ebx, dword ptr [rbp+20h+uBytes+4]
0x18005957f  jmp     short loc_180059583
0x180059581  mov     ebx, esi
0x180059583  test    r13, r13
0x180059586  jz      short loc_180059591
0x180059588  mov     rcx, r13; hdc
0x18005958b  call    cs:__imp_DeleteDC
0x180059591  test    r12, r12
0x180059594  jz      short loc_18005959F
0x180059596  mov     rcx, r12; ho
0x180059599  call    cs:__imp_DeleteObject
0x18005959f  test    rsi, rsi
0x1800595a2  jz      short loc_1800595AD
0x1800595a4  mov     rcx, rsi; hMem
0x1800595a7  call    cs:__imp_LocalFree
0x1800595ad  mov     eax, ebx
0x1800595af  jmp     loc_18005988B
0x1800595b4  mov     r14, [rbp+20h+lpBits]
0x1800595b8  mov     eax, [rbp+20h+arg_48]
0x1800595bb  mov     dword ptr [rsp+140h+var_B8], ecx; int
0x1800595c2  mov     rcx, rdi; int
0x1800595c5  mov     [rsp+140h+var_C0], r8d; int
0x1800595cd  mov     r8d, r10d; int
0x1800595d0  mov     dword ptr [rsp+140h+var_C8], edx; int
0x1800595d4  mov     edx, r11d; int
0x1800595d7  mov     [rsp+140h+Src], rbx; Src
0x1800595dc  mov     dword ptr [rsp+140h+Size], esi; Size
0x1800595e0  mov     [rsp+140h+var_E0], r14; void *
0x1800595e5  mov     dword ptr [rsp+140h+var_E8], r13d; size_t
0x1800595ea  mov     [rsp+140h+var_F0], r15d; int
0x1800595ef  mov     [rsp+140h+var_F8], eax; __int16
0x1800595f3  mov     eax, [rbp+20h+arg_40]
0x1800595f6  mov     [rsp+140h+var_100], eax; int
0x1800595fa  mov     eax, [rbp+20h+arg_38]
0x1800595fd  mov     [rsp+140h+var_108], eax; int
0x180059601  mov     eax, [rbp+20h+arg_30]
0x180059604  mov     [rsp+140h+ColorUse], eax; int
0x180059608  mov     eax, [rbp+20h+arg_28]
0x18005960b  mov     [rsp+140h+iUsage], eax; int
0x18005960f  mov     eax, dword ptr [rbp+20h+arg_20]
0x180059612  mov     dword ptr [rsp+140h+pbmi], eax; __int16
0x180059616  call    MF16_RecordDIBits
0x18005961b  jmp     loc_18005988B
0x180059620  mov     rcx, rdi
0x180059623  call    cs:__imp_pldcGet
0x180059629  mov     [rbp+20h+lpBits], rax
0x18005962d  test    rax, rax
0x180059630  jz      loc_18005987E
0x180059636  and     edi, 7F0000h
0x18005963c  cmp     edi, 660000h
0x180059642  jz      loc_18005987E
0x180059648  mov     r9d, 0FFFFFFFCh
0x18005964e  cmp     esi, r9d
0x180059651  ja      loc_180059889
0x180059657  cmp     r13d, r9d
0x18005965a  ja      loc_180059889
0x180059660  cmp     r12d, r9d
0x180059663  ja      loc_180059889
0x180059669  lea     edx, [rsi+3]
0x18005966c  and     edx, r9d
0x18005966f  add     edx, 50h ; 'P'
0x180059672  cmp     edx, 50h ; 'P'
0x180059675  jb      loc_180059889
0x18005967b  lea     ecx, [r13+3]
0x18005967f  and     ecx, r9d
0x180059682  add     ecx, edx
0x180059684  cmp     ecx, edx
0x180059686  jb      loc_180059889
0x18005968c  lea     edx, [r12+3]
0x180059691  and     edx, r9d
0x180059694  add     edx, ecx; unsigned int
0x180059696  cmp     edx, ecx
0x180059698  jb      loc_180059889
0x18005969e  mov     rdi, [rax+10h]
0x1800596a2  mov     rcx, rdi; this
0x1800596a5  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x1800596aa  mov     r11, rax
0x1800596ad  test    rax, rax
0x1800596b0  jz      loc_180059889
0x1800596b6  test    r15d, r15d
0x1800596b9  jz      short loc_180059706
0x1800596bb  movzx   r8d, word ptr [rbx+0Eh]; int
0x1800596c0  lea     r9, [rbp+20h+uBytes]; unsigned int *
0x1800596c4  movzx   edx, word ptr [rbx+0Ch]; int
0x1800596c8  mov     ecx, [rbx+4]; int
0x1800596cb  mov     dword ptr [rbp+20h+uBytes], 0
0x1800596d2  call    ?SignedCJSCAN@@YAHJJJPEAK@Z; SignedCJSCAN(long,long,long,ulong *)
0x1800596d7  test    eax, eax
0x1800596d9  jz      loc_180059889
  ... truncated ...
```
