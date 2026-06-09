# ScriptTextOut

- ea: `0x180020a90`
- end: `0x18002141f`
- name: `ScriptTextOut`
- size: `2447`
- prototype: `HRESULT __stdcall(const HDC hdc, SCRIPT_CACHE *psc, int x, int y, UINT fuOptions, const RECT *lprc, const SCRIPT_ANALYSIS *psa, const WCHAR *pwcReserved, int iReserved, const WORD *pwGlyphs, int cGlyphs, const int *piAdvance, const int *piJustify, const GOFFSET *pGoffset)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800202a8`
- `0x180024610`

## callees

- `0x180006978`
- `0x180006a28`
- `0x180006e00`
- `0x180009460`
- `0x180009760`
- `0x18000a900`
- `0x18000d040`
- `0x18000d200`
- `0x1800136a0`
- `0x18001b2d0`
- `0x18001b4f0`
- `0x1800200a0`
- `0x180020224`
- `0x1800209d0`
- `0x180020a90`
- `0x1800215b0`
- `0x180021e50`
- `0x180022950`
- `0x180022b20`
- `0x18002ade0`
- `0x180032f20`
- `0x180049730`
- `0x180061010`
- `0x180061180`
- `0x1800653e0`
- `0x180072d30`
- `0x18007f800`
- `0x18009e220`
- `0x18009e530`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020c3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020c15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020c15`
- `GDI32!DeleteDC` at `0x1800211ca`
- `GDI32!DeleteDC` at `0x1800211ca`
- `GDI32!ExtTextOutW` at `0x180020e43`
- `GDI32!ExtTextOutW` at `0x180020fd3`
- `GDI32!ExtTextOutW` at `0x1800211a3`
- `GDI32!ExtTextOutW` at `0x180020e43`
- `GDI32!ExtTextOutW` at `0x180020fd3`
- `GDI32!ExtTextOutW` at `0x1800211a3`
- `GDI32!MoveToEx` at `0x180020dfb`
- `GDI32!MoveToEx` at `0x180020e72`
- `GDI32!MoveToEx` at `0x180021162`
- `GDI32!MoveToEx` at `0x180020dfb`
- `GDI32!MoveToEx` at `0x180020e72`
- `GDI32!MoveToEx` at `0x180021162`
- `GDI32!SelectObject` at `0x180021103`
- `GDI32!SelectObject` at `0x1800213d5`
- `GDI32!SelectObject` at `0x1800213fe`
- `GDI32!SelectObject` at `0x180021103`
- `GDI32!SelectObject` at `0x1800213d5`
- `GDI32!SelectObject` at `0x1800213fe`
- `GDI32!SetBkMode` at `0x180020de4`
- `GDI32!SetBkMode` at `0x180020e99`
- `GDI32!SetBkMode` at `0x18002114a`
- `GDI32!SetBkMode` at `0x180020de4`
- `GDI32!SetBkMode` at `0x180020e99`
- `GDI32!SetBkMode` at `0x18002114a`
- `GDI32!SetTextAlign` at `0x180020dd0`
- `GDI32!SetTextAlign` at `0x180020e83`
- `GDI32!SetTextAlign` at `0x180021135`
- `GDI32!SetTextAlign` at `0x180020dd0`
- `GDI32!SetTextAlign` at `0x180020e83`
- `GDI32!SetTextAlign` at `0x180021135`
- `GDI32!DeleteObject` at `0x1800213e5`
- `GDI32!DeleteObject` at `0x18002140e`
- `GDI32!DeleteObject` at `0x1800213e5`
- `GDI32!DeleteObject` at `0x18002140e`
- `TextShaping!ShapingDrawGlyphs` at `0x180020f2c`
- `TextShaping!ShapingDrawGlyphs` at `0x180020f2c`

## pseudocode

```c
HRESULT __stdcall ScriptTextOut(
        const HDC hdc,
        SCRIPT_CACHE *psc,
        int x,
        int y,
        UINT fuOptions,
        const RECT *lprc,
        const SCRIPT_ANALYSIS *psa,
        const WCHAR *pwcReserved,
        int iReserved,
        const WORD *pwGlyphs,
        int cGlyphs,
        const int *piAdvance,
        const int *piJustify,
        const GOFFSET *pGoffset)
{
  WORD *v14; // r15
  struct _ABC *v16; // rsi
  const WORD *lpString; // r13
  const int *lpDx; // r12
  __int64 v19; // r8
  char *v20; // rdx
  const int *p_abcA; // rax
  const GOFFSET *v23; // r8
  const GOFFSET *v24; // r11
  UINT v25; // edi
  __int64 v26; // rsi
  __int64 v27; // rdx
  int v28; // edx
  HDC v29; // rsi
  unsigned __int64 v30; // r9
  __int64 v31; // r10
  int v32; // r8d
  __int64 v33; // rdx
  int v34; // eax
  __int16 v35; // cx
  int v36; // edx
  unsigned int v37; // eax
  UINT TextAlign; // esi
  int BkMode; // ebx
  HRESULT v40; // ebx
  int v41; // eax
  HDC CompatibleDC; // rax
  UINT v43; // eax
  char *v44; // rax
  unsigned __int64 v45; // rcx
  HRESULT v46; // r15d
  __int64 v47; // r8
  HGDIOBJ v48; // r9
  const int *v49; // r10
  struct _ABC *i; // r11
  unsigned __int64 v51; // rcx
  __int64 k; // r9
  unsigned __int64 v53; // rdx
  GOFFSET *v54; // rcx
  struct _ABC *v55; // r9
  int v56; // r10d
  signed int v57; // r8d
  __m128i v58; // xmm2
  __m128i v59; // xmm1
  __int64 v60; // rax
  __m128i v61; // xmm1
  __m128i v62; // xmm1
  __int64 v63; // rax
  __int64 j; // r8
  INT ya; // [rsp+90h] [rbp-80h] BYREF
  HDC hdca; // [rsp+98h] [rbp-78h]
  UINT c; // [rsp+A0h] [rbp-70h]
  int v68; // [rsp+A4h] [rbp-6Ch] BYREF
  struct tagPOINT pt; // [rsp+A8h] [rbp-68h] BYREF
  struct _ABC *v70; // [rsp+B0h] [rbp-60h]
  const GOFFSET *v71; // [rsp+B8h] [rbp-58h]
  __int128 v72; // [rsp+C0h] [rbp-50h] BYREF
  RECT *lprect; // [rsp+D0h] [rbp-40h]
  HGDIOBJ h; // [rsp+D8h] [rbp-38h]
  void **v75; // [rsp+E0h] [rbp-30h] BYREF
  HDC v76; // [rsp+E8h] [rbp-28h]
  LONG v77; // [rsp+F0h] [rbp-20h]
  INT v78; // [rsp+F4h] [rbp-1Ch]
  int v79; // [rsp+F8h] [rbp-18h]
  HGDIOBJ ho[2]; // [rsp+100h] [rbp-10h]
  HGDIOBJ v81[2]; // [rsp+110h] [rbp+0h]
  struct tagPOINT v82; // [rsp+120h] [rbp+10h] BYREF
  int v83; // [rsp+128h] [rbp+18h]
  __int64 v84; // [rsp+12Ch] [rbp+1Ch]
  __int64 v85; // [rsp+138h] [rbp+28h]
  int *v86; // [rsp+140h] [rbp+30h]
  int v87; // [rsp+148h] [rbp+38h]
  int v88; // [rsp+14Ch] [rbp+3Ch]
  void **v89; // [rsp+150h] [rbp+40h] BYREF
  int v90; // [rsp+158h] [rbp+48h]
  int v91; // [rsp+160h] [rbp+50h] BYREF
  _DWORD v92[5]; // [rsp+164h] [rbp+54h] BYREF
  RECT rect; // [rsp+178h] [rbp+68h] BYREF
  _QWORD v94[3]; // [rsp+190h] [rbp+80h] BYREF
  int v95; // [rsp+1A8h] [rbp+98h]

  v14 = 0;
  v16 = (struct _ABC *)piJustify;
  lpString = pwGlyphs;
  lpDx = piAdvance;
  lprect = (RECT *)lprc;
  v71 = pGoffset;
  ya = y;
  pt.x = x;
  hdca = (HDC)psc;
  c = cGlyphs;
  v70 = (struct _ABC *)piJustify;
  *(_QWORD *)&v72 = 0;
  if ( !hdc || !psa || !pwGlyphs || !piAdvance )
    return -2147024809;
  v68 = UspAcquireTempAlloc((unsigned int)hdc);
  if ( (*(_WORD *)psa & 0x4400) == 0x4400 )
  {
    v19 = 4LL * cGlyphs;
    h = (HGDIOBJ)v19;
    v70 = (struct _ABC *)((2LL * cGlyphs + 3) & 0xFFFFFFFFFFFFFFFCuLL);
    v20 = (char *)v70 + v19;
    if ( (struct _ABC *)((char *)v70 + v19) < v70
      || (v44 = &v20[v19], &v20[v19] < v20)
      || (v45 = (unsigned __int64)&v44[8 * cGlyphs], v45 > 0x7FFFFFFF)
      || v45 < (unsigned __int64)v44 )
    {
      CTempMemory::~CTempMemory((CTempMemory *)&v68);
      return -2147024882;
    }
    v46 = UspAllocTemp(v45, &v72);
    if ( v46 < 0 )
    {
      CTempMemory::~CTempMemory((CTempMemory *)&v68);
      return v46;
    }
    v14 = (WORD *)v72;
    v47 = 0;
    v48 = h;
    v49 = (int *)((char *)&v70->abcA + v72);
    for ( i = (struct _ABC *)((char *)v70 + v72 + (_QWORD)h); (int)v47 < cGlyphs; v47 = (unsigned int)(v47 + 1) )
    {
      v51 = cGlyphs - (unsigned __int64)(unsigned int)v47;
      v14[v47] = pwGlyphs[v51 - 1];
      v49[v47] = piAdvance[v51 - 1];
    }
    if ( piJustify )
    {
      for ( j = 0; (int)j < cGlyphs; j = (unsigned int)(j + 1) )
        *(&i->abcA + j) = piJustify[cGlyphs - (unsigned __int64)(unsigned int)j - 1];
      v16 = i;
    }
    v23 = v71;
    if ( v71 )
    {
      v24 = (const GOFFSET *)((char *)i + (_QWORD)v48);
      for ( k = 0; (int)k < cGlyphs; v54->dv = *(LONG *)((char *)&v23->dv + v53) )
      {
        v53 = 8 * (cGlyphs - (unsigned __int64)(unsigned int)k) - 8;
        v54 = (GOFFSET *)&v24[k];
        k = (unsigned int)(k + 1);
        v54->du = -*(LONG *)((char *)&v23->du + v53);
      }
    }
    else
    {
      v24 = 0;
    }
    p_abcA = &v16->abcA;
    v71 = v24;
    v70 = v16;
    lpString = v14;
    lpDx = v49;
  }
  else
  {
    p_abcA = piJustify;
  }
  v25 = fuOptions & 6;
  if ( *(_WORD *)psa < 0 )
  {
    if ( p_abcA && lpDx )
      lpDx = p_abcA;
    if ( ExtTextOutW(hdc, pt.x, ya, v25 | 0x1000, lprect, lpString, c, lpDx) )
      v40 = 0;
    else
      v40 = HRESULT_FROM_LAST_WIN32_ERROR();
    goto LABEL_33;
  }
  if ( !hdca )
    goto LABEL_49;
  v26 = *(_WORD *)psa & 0x3FF;
  if ( !*(_QWORD *)hdca || (v27 = *(_QWORD *)(*(_QWORD *)hdca + 80LL)) == 0 )
  {
LABEL_19:
    EnterCriticalSection(&csCache);
    v28 = v26;
    v29 = hdca;
    LODWORD(hdca) = UpdateCache((void **)hdca, v28, hdc);
    LeaveCriticalSection(&csCache);
    if ( (int)hdca < 0 && (_DWORD)hdca != -2147220992 )
    {
      CTempMemory::~CTempMemory((CTempMemory *)&v68);
      return (int)hdca;
    }
    goto LABEL_21;
  }
  if ( (unsigned int)v26 >= 0xE1 )
  {
LABEL_49:
    CTempMemory::~CTempMemory((CTempMemory *)&v68);
    return -2147024809;
  }
  if ( *(_QWORD *)(v27 + 8 * v26 + 344) == -1 )
    goto LABEL_19;
  v29 = hdca;
LABEL_21:
  v30 = *(_WORD *)psa;
  v31 = *(_QWORD *)v29;
  v32 = *(_WORD *)psa & 0x3FF;
  v33 = *(_QWORD *)(*(_QWORD *)v29 + 80LL);
  v34 = *(_DWORD *)(v33 + 4 * ((v30 >> 5) & 0x1F) + 248);
  if ( _bittest(&v34, *(_BYTE *)psa & 0x1F) )
  {
    v35 = *(_WORD *)(v33 + 20);
    v89 = &CUspShapingClient::`vftable';
    v90 = 0;
    v94[0] = &CUspShapingFont::`vftable';
    v94[1] = hdc;
    v94[2] = v31;
    v95 = 0;
    v92[3] = 0;
    qmemcpy(v92, "dfltdflt", 8);
    v36 = *((unsigned __int16 *)&ShlScriptSupport + 4 * (v30 & 0x3FF));
    v92[2] = v35 == 64;
    v37 = *(_WORD *)&psa->s & 0x400 | 0x2000;
    v76 = hdc;
    *(_OWORD *)ho = 0;
    v92[4] = (v37 >> 7) | ((v30 & 0x400 | ((unsigned int)v30 >> 1) & 0x1800) >> 10);
    *(_OWORD *)v81 = 0;
    if ( v36 == 0xFFFF )
      v36 = 1;
    v79 = 1;
    v91 = v36;
    v75 = &CUspShapingDrawingSurface::`vftable';
    v77 = pt.x;
    v78 = ya;
    ya = 1000;
    v72 = 0;
    v83 = -1;
    v84 = 0;
    v85 = v31;
    v86 = &v91;
    v87 = v32;
    v88 = -1;
    pt = 0;
    TextAlign = GetTextAlign(hdc);
    GetCurrentPositionEx(hdc, &pt);
    BkMode = GetBkMode(hdc);
    SetTextAlign(hdc, TextAlign & 0xFFFFFFF8 | 1);
    SetBkMode(hdc, 1);
    MoveToEx(hdc, 0, 0, 0);
    rect = 0;
    ExtTextOutW(hdc, 0, 0, 0x1004u, &rect, L" ", 1u, &ya);
    GetCurrentPositionEx(hdc, &v82);
    if ( !v82.x && !v82.y )
    {
      v82.x = ya;
      h = (HGDIOBJ)GetDCObject(hdc, 655360);
      if ( h )
      {
        CompatibleDC = CreateCompatibleDC(hdc);
        hdca = CompatibleDC;
        if ( CompatibleDC )
        {
          SelectObject(CompatibleDC, h);
          if ( GetGraphicsMode(hdc) == 2 )
            SetGraphicsMode(hdca, 2);
          v43 = GetTextAlign(hdca);
          SetTextAlign(hdca, v43 & 0xFFFFFFF8 | 1);
          SetBkMode(hdca, 1);
          MoveToEx(hdca, 0, 0, 0);
          ExtTextOutW(hdca, 0, 0, 0x1000u, &rect, L" ", 1u, &ya);
          GetCurrentPositionEx(hdca, &v82);
          if ( !v82.x && !v82.y )
            v82.x = ya;
          DeleteDC(hdca);
        }
      }
    }
    MoveToEx(hdc, pt.x, pt.y, 0);
    SetTextAlign(hdc, TextAlign);
    if ( BkMode != 1 )
      SetBkMode(hdc, BkMode);
    v40 = 0;
    HIDWORD(v84) = GetTextAlign(hdc);
    if ( v91 == 23 )
    {
      v55 = (struct _ABC *)lpDx;
      v56 = 0;
      if ( v70 )
        v55 = v70;
      if ( (int)c > 0 )
      {
        v57 = 0;
        if ( c < 8 )
          goto LABEL_88;
        v58 = 0;
        v59 = 0;
        do
        {
          v60 = v57;
          v57 += 8;
          v58 = _mm_add_epi32(v58, _mm_loadu_si128((const __m128i *)(&v55->abcA + v60)));
          v59 = _mm_add_epi32(v59, _mm_loadu_si128((const __m128i *)(&v55[1].abcB + v60)));
        }
        while ( v57 < (int)(c & 0xFFFFFFF8) );
        v61 = _mm_add_epi32(v59, v58);
        v62 = _mm_add_epi32(v61, _mm_srli_si128(v61, 8));
        v56 = _mm_cvtsi128_si32(_mm_add_epi32(v62, _mm_srli_si128(v62, 4)));
        if ( v57 < (int)c )
        {
LABEL_88:
          do
          {
            v63 = v57++;
            v56 += *(&v55->abcA + v63);
          }
          while ( v57 < (int)c );
        }
      }
      v88 = v56;
    }
    *(_QWORD *)&v72 = lprect;
    DWORD2(v72) = fuOptions & 6;
    v41 = ShapingDrawGlyphs(&v89, v94, &v91, 0, 0, 0, 0, lpString, 0, c, lpDx, v70, v71, &v75, &v72, 0, 0);
    if ( v41 )
    {
      if ( v41 == -2 )
      {
        CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v75);
        v40 = -2147024882;
      }
      else
      {
        v40 = -2147483638;
        if ( v95 == -2147483638 )
        {
          CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v75);
        }
        else
        {
          CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v75);
          v40 = -2147467259;
        }
      }
    }
    else
    {
      v75 = &CUspShapingDrawingSurface::`vftable';
      if ( ho[0] )
      {
        SelectObject(v76, ho[1]);
        DeleteObject(ho[0]);
      }
      if ( v81[0] )
      {
        SelectObject(v76, v81[1]);
        DeleteObject(v81[0]);
      }
    }
  }
  else
  {
    v40 = ((__int64 (__fastcall *)(const HDC, HDC, _QWORD, _QWORD, UINT, RECT *, const SCRIPT_ANALYSIS *, const WORD *, UINT, const int *, struct _ABC *, const GOFFSET *))funcs_180021072[3 * (v30 & 0x3FF)])(
            hdc,
            v29,
            (unsigned int)pt.x,
            (unsigned int)ya,
            v25,
            lprect,
            psa,
            lpString,
            c,
            lpDx,
            v70,
            v71);
  }
LABEL_33:
  if ( v14 )
    UspFreeMem(v14);
  CTempMemory::~CTempMemory((CTempMemory *)&v68);
  return v40;
}

```

## disassembly

```asm
0x180020a90  push    rbp
0x180020a92  push    rbx
0x180020a93  push    rsi
0x180020a94  push    rdi
0x180020a95  push    r12
0x180020a97  push    r13
0x180020a99  push    r14
0x180020a9b  push    r15
0x180020a9d  lea     rbp, [rsp-138h]
0x180020aa5  sub     rsp, 248h
0x180020aac  mov     rax, cs:__security_cookie
0x180020ab3  xor     rax, rsp
0x180020ab6  mov     [rbp+170h+var_50], rax
0x180020abd  mov     rax, [rbp+170h+lprc]
0x180020ac4  xor     r15d, r15d
0x180020ac7  movsxd  rdi, [rbp+170h+cGlyphs]
0x180020ace  mov     r14, rcx
0x180020ad1  mov     rsi, [rbp+170h+piJustify]
0x180020ad8  mov     rbx, [rbp+170h+psa]
0x180020adf  mov     r13, [rbp+170h+pwGlyphs]
0x180020ae6  mov     r12, [rbp+170h+piAdvance]
0x180020aed  mov     [rbp+170h+var_1B0], rax
0x180020af1  mov     rax, [rbp+170h+pGoffset]
0x180020af8  mov     [rbp+170h+var_1C8], rax
0x180020afc  mov     [rbp+170h+y], r9d
0x180020b00  mov     [rbp+170h+pt.x], r8d
0x180020b04  mov     [rbp+170h+hdc], rdx
0x180020b08  mov     [rbp+170h+var_1E0], edi
0x180020b0b  mov     [rbp+170h+var_1D0], rsi
0x180020b0f  mov     qword ptr [rbp+170h+var_1C0], r15
0x180020b13  test    rcx, rcx
0x180020b16  jz      loc_180021012
0x180020b1c  test    rbx, rbx
0x180020b1f  jz      loc_180021012
0x180020b25  test    r13, r13
0x180020b28  jz      loc_180021012
0x180020b2e  test    r12, r12
0x180020b31  jz      loc_180021012
0x180020b37  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x180020b3c  mov     [rbp+170h+var_1DC], eax
0x180020b3f  mov     ecx, 4400h
0x180020b44  movzx   eax, word ptr [rbx]
0x180020b47  and     ax, cx
0x180020b4a  cmp     ax, cx
0x180020b4d  jnz     short loc_180020B8B
0x180020b4f  lea     r8, ds:0[rdi*4]
0x180020b57  lea     rax, ds:3[rdi*2]
0x180020b5f  mov     [rbp+170h+h], r8
0x180020b63  and     rax, 0FFFFFFFFFFFFFFFCh
0x180020b67  mov     [rbp+170h+var_1D0], rax
0x180020b6b  lea     rdx, [r8+rax]
0x180020b6f  cmp     rdx, rax
0x180020b72  jnb     loc_1800211DB
0x180020b78  lea     rcx, [rbp+170h+var_1DC]; this
0x180020b7c  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180020b81  mov     eax, 8007000Eh
0x180020b86  jmp     loc_180020F71
0x180020b8b  mov     rax, rsi
0x180020b8e  jmp     short loc_180020BBA
0x180020b90  test    rsi, rsi
0x180020b93  jnz     loc_18002136E
0x180020b99  mov     r8, [rbp+170h+var_1C8]
0x180020b9d  test    r8, r8
0x180020ba0  jnz     loc_18002126A
0x180020ba6  xor     r11d, r11d
0x180020ba9  mov     rax, rsi
0x180020bac  mov     [rbp+170h+var_1C8], r11
0x180020bb0  mov     [rbp+170h+var_1D0], rax
0x180020bb4  mov     r13, r15
0x180020bb7  mov     r12, r10
0x180020bba  mov     edi, [rbp+170h+fuOptions]
0x180020bc0  movzx   esi, word ptr [rbx]
0x180020bc3  and     edi, 6
0x180020bc6  test    si, si
0x180020bc9  js      loc_180020F9F
0x180020bcf  mov     rax, [rbp+170h+hdc]
0x180020bd3  test    rax, rax
0x180020bd6  jz      loc_1800210A8
0x180020bdc  mov     rcx, [rax]
0x180020bdf  and     esi, 3FFh
0x180020be5  test    rcx, rcx
0x180020be8  jz      short loc_180020C0E
0x180020bea  mov     rdx, [rcx+50h]
0x180020bee  test    rdx, rdx
0x180020bf1  jz      short loc_180020C0E
0x180020bf3  cmp     esi, 0E1h
0x180020bf9  jnb     loc_1800210A8
0x180020bff  cmp     qword ptr [rdx+rsi*8+158h], 0FFFFFFFFFFFFFFFFh
0x180020c08  jnz     loc_18002100A
0x180020c0e  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020c15  call    cs:__imp_EnterCriticalSection
0x180020c1c  nop     dword ptr [rax+rax+00h]
0x180020c21  mov     edx, esi; int
0x180020c23  mov     r8, r14; HDC
0x180020c26  mov     rsi, [rbp+170h+hdc]
0x180020c2a  mov     rcx, rsi; void **
0x180020c2d  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x180020c32  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180020c39  mov     dword ptr [rbp+170h+hdc], eax
0x180020c3c  call    cs:__imp_LeaveCriticalSection
0x180020c43  nop     dword ptr [rax+rax+00h]
0x180020c48  mov     eax, dword ptr [rbp+170h+hdc]
0x180020c4b  test    eax, eax
0x180020c4d  jns     short loc_180020C5A
0x180020c4f  cmp     eax, 80040200h
0x180020c54  jnz     loc_18002108A
0x180020c5a  movzx   r9d, word ptr [rbx]
0x180020c5e  mov     r10, [rsi]
0x180020c61  mov     r8d, r9d
0x180020c64  and     r8d, 3FFh
0x180020c6b  mov     eax, r8d
0x180020c6e  mov     rdx, [r10+50h]
0x180020c72  and     eax, 8000001Fh
0x180020c77  jge     short loc_180020C80
0x180020c79  dec     eax
0x180020c7b  or      eax, 0FFFFFFE0h
0x180020c7e  inc     eax
0x180020c80  movzx   ecx, al
0x180020c83  lea     r11, __ImageBase
0x180020c8a  mov     rax, r9
0x180020c8d  shr     rax, 5
0x180020c91  and     eax, 1Fh
0x180020c94  mov     eax, [rdx+rax*4+0F8h]
0x180020c9b  bt      eax, ecx
0x180020c9e  jnb     loc_18002101C
0x180020ca4  movzx   ecx, word ptr [rdx+14h]
0x180020ca8  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x180020caf  mov     [rbp+170h+var_130], rax
0x180020cb3  xor     esi, esi
0x180020cb5  lea     rax, ??_7CUspShapingFont@@6B@; const CUspShapingFont::`vftable'
0x180020cbc  mov     [rbp+170h+var_128], esi
0x180020cbf  mov     [rbp+170h+var_F0], rax
0x180020cc6  xorps   xmm0, xmm0
0x180020cc9  mov     rax, r9
0x180020ccc  mov     [rbp+170h+var_E8], r14
0x180020cd3  and     eax, 3FFh
0x180020cd8  mov     [rbp+170h+var_E0], r10
0x180020cdf  cmp     cx, 40h ; '@'
0x180020ce3  mov     [rbp+170h+var_D8], esi
0x180020ce9  mov     ecx, r9d
0x180020cec  mov     [rbp+170h+var_110], esi
0x180020cef  xorps   xmm1, xmm1
0x180020cf2  mov     [rbp+170h+var_11C], 746C6664h
0x180020cf9  movzx   edx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r11+rax*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180020d02  mov     eax, esi
0x180020d04  setz    al
0x180020d07  mov     [rbp+170h+var_118], 746C6664h
0x180020d0e  shr     ecx, 1
0x180020d10  and     r9d, 400h
0x180020d17  mov     [rbp+170h+var_114], eax
0x180020d1a  and     ecx, 1800h
0x180020d20  movzx   eax, word ptr [rbx+2]
0x180020d24  or      ecx, r9d
0x180020d27  and     eax, 400h
0x180020d2c  shr     ecx, 0Ah
0x180020d2f  bts     eax, 0Dh
0x180020d33  mov     [rbp+170h+var_198], r14
0x180020d37  shr     eax, 7
0x180020d3a  or      ecx, eax
0x180020d3c  movdqu  xmmword ptr [rbp+170h+ho], xmm0
0x180020d41  cmp     edx, 0FFFFh
0x180020d47  mov     [rbp+170h+var_10C], ecx
0x180020d4a  mov     ecx, 1
0x180020d4f  movdqu  xmmword ptr [rbp+170h+var_170], xmm1
0x180020d54  cmovz   edx, ecx
0x180020d57  mov     [rbp+170h+var_188], ecx
0x180020d5a  mov     [rbp+170h+var_120], edx
0x180020d5d  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x180020d64  mov     edx, [rbp+170h+pt.x]
0x180020d67  mov     rcx, r14; hdc
0x180020d6a  mov     [rbp+170h+var_1A0], rax
0x180020d6e  lea     rax, [rbp+170h+var_120]
0x180020d72  mov     [rbp+170h+var_190], edx
0x180020d75  mov     edx, [rbp+170h+y]
0x180020d78  mov     [rbp+170h+var_18C], edx
0x180020d7b  mov     [rbp+170h+y], 3E8h
0x180020d82  movups  [rbp+170h+var_1C0], xmm0
0x180020d86  mov     [rbp+170h+var_158], 0FFFFFFFFh
0x180020d8d  mov     [rbp+170h+var_154], rsi
0x180020d91  mov     [rbp+170h+var_148], r10
0x180020d95  mov     [rbp+170h+var_140], rax
0x180020d99  mov     [rbp+170h+var_138], r8d
0x180020d9d  mov     [rbp+170h+var_134], 0FFFFFFFFh
0x180020da4  mov     qword ptr [rbp+170h+pt.x], rsi
0x180020da8  call    GetTextAlign
0x180020dad  lea     rdx, [rbp+170h+pt]; lppt
0x180020db1  mov     rcx, r14; hdc
0x180020db4  mov     esi, eax
0x180020db6  call    GetCurrentPositionEx
0x180020dbb  mov     rcx, r14; hdc
0x180020dbe  call    GetBkMode
0x180020dc3  mov     edx, esi
0x180020dc5  mov     rcx, r14; hdc
0x180020dc8  and     edx, 0FFFFFFF9h
0x180020dcb  mov     ebx, eax
0x180020dcd  or      edx, 1; align
0x180020dd0  call    cs:__imp_SetTextAlign
0x180020dd7  nop     dword ptr [rax+rax+00h]
0x180020ddc  mov     edx, 1; mode
0x180020de1  mov     rcx, r14; hdc
0x180020de4  call    cs:__imp_SetBkMode
0x180020deb  nop     dword ptr [rax+rax+00h]
0x180020df0  xor     r9d, r9d; lppt
0x180020df3  xor     r8d, r8d; y
0x180020df6  xor     edx, edx; x
0x180020df8  mov     rcx, r14; hdc
0x180020dfb  call    cs:__imp_MoveToEx
0x180020e02  nop     dword ptr [rax+rax+00h]
0x180020e07  xorps   xmm0, xmm0
0x180020e0a  lea     rax, [rbp+170h+y]
0x180020e0e  mov     r9d, 1004h; options
0x180020e14  mov     [rsp+280h+lpDx], rax; lpDx
0x180020e19  xor     r8d, r8d; y
0x180020e1c  lea     rax, String; " "
0x180020e23  mov     [rsp+280h+c], 1; c
0x180020e2b  mov     [rsp+280h+lpString], rax; lpString
0x180020e30  xor     edx, edx; x
0x180020e32  lea     rax, [rbp+170h+rect]
0x180020e36  mov     rcx, r14; hdc
0x180020e39  mov     [rsp+280h+lprect], rax; lprect
0x180020e3e  movdqu  xmmword ptr [rbp+170h+rect.left], xmm0
0x180020e43  call    cs:__imp_ExtTextOutW
0x180020e4a  nop     dword ptr [rax+rax+00h]
0x180020e4f  lea     rdx, [rbp+170h+var_160]; lppt
0x180020e53  mov     rcx, r14; hdc
0x180020e56  call    GetCurrentPositionEx
0x180020e5b  cmp     [rbp+170h+var_160.x], 0
0x180020e5f  jz      loc_1800210BD
0x180020e65  mov     r8d, [rbp+170h+pt.y]; y
0x180020e69  xor     r9d, r9d; lppt
0x180020e6c  mov     edx, [rbp+170h+pt.x]; x
0x180020e6f  mov     rcx, r14; hdc
0x180020e72  call    cs:__imp_MoveToEx
0x180020e79  nop     dword ptr [rax+rax+00h]
0x180020e7e  mov     edx, esi; align
0x180020e80  mov     rcx, r14; hdc
0x180020e83  call    cs:__imp_SetTextAlign
0x180020e8a  nop     dword ptr [rax+rax+00h]
0x180020e8f  cmp     ebx, 1
0x180020e92  jz      short loc_180020EA5
0x180020e94  mov     edx, ebx; mode
0x180020e96  mov     rcx, r14; hdc
0x180020e99  call    cs:__imp_SetBkMode
0x180020ea0  nop     dword ptr [rax+rax+00h]
0x180020ea5  mov     rcx, r14; hdc
0x180020ea8  call    GetTextAlign
0x180020ead  mov     rcx, [rbp+170h+var_1D0]
0x180020eb1  xor     ebx, ebx
0x180020eb3  cmp     [rbp+170h+var_120], 17h
0x180020eb7  mov     edx, [rbp+170h+var_1E0]
0x180020eba  mov     dword ptr [rbp+170h+var_154+4], eax
0x180020ebd  jz      loc_1800212B2
0x180020ec3  mov     r8, [rbp+170h+var_1C8]
0x180020ec7  lea     rax, [rbp+170h+var_1C0]
0x180020ecb  mov     r9, [rbp+170h+var_1B0]
0x180020ecf  mov     [rsp+280h+var_200], ebx
0x180020ed6  mov     [rsp+280h+var_208], ebx
0x180020eda  mov     [rsp+280h+var_210], rax
0x180020edf  lea     rax, [rbp+170h+var_1A0]
0x180020ee3  mov     [rsp+280h+var_218], rax
0x180020ee8  mov     [rsp+280h+var_220], r8
0x180020eed  lea     r8, [rbp+170h+var_120]
0x180020ef1  mov     [rsp+280h+var_228], rcx
0x180020ef6  lea     rcx, [rbp+170h+var_130]
0x180020efa  mov     [rsp+280h+var_230], r12
0x180020eff  mov     dword ptr [rsp+280h+var_238], edx
0x180020f03  lea     rdx, [rbp+170h+var_F0]
0x180020f0a  mov     [rsp+280h+var_240], rbx
0x180020f0f  mov     [rsp+280h+lpDx], r13
0x180020f14  mov     [rsp+280h+c], ebx
0x180020f18  mov     qword ptr [rbp+170h+var_1C0], r9
0x180020f1c  xor     r9d, r9d
0x180020f1f  mov     [rsp+280h+lpString], rbx
0x180020f24  mov     [rsp+280h+lprect], rbx
0x180020f29  mov     dword ptr [rbp+170h+var_1C0+8], edi
0x180020f2c  call    cs:__imp_ShapingDrawGlyphs
0x180020f33  nop     dword ptr [rax+rax+00h]
0x180020f38  test    eax, eax
0x180020f3a  jnz     loc_180020FEE
0x180020f40  cmp     [rbp+170h+ho], 0
0x180020f45  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x180020f4c  mov     [rbp+170h+var_1A0], rax
0x180020f50  jnz     loc_1800213CD
0x180020f56  cmp     [rbp+170h+var_170], 0
0x180020f5b  jnz     loc_1800213F6
0x180020f61  test    r15, r15
0x180020f64  jnz     short loc_180020F95
0x180020f66  lea     rcx, [rbp+170h+var_1DC]; this
0x180020f6a  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180020f6f  mov     eax, ebx
0x180020f71  mov     rcx, [rbp+170h+var_50]
0x180020f78  xor     rcx, rsp; StackCookie
0x180020f7b  call    __security_check_cookie
0x180020f80  add     rsp, 248h
0x180020f87  pop     r15
0x180020f89  pop     r14
0x180020f8b  pop     r13
0x180020f8d  pop     r12
0x180020f8f  pop     rdi
0x180020f90  pop     rsi
  ... truncated ...
```
