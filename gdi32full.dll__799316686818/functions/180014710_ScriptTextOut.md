# ScriptTextOut

- ea: `0x180014710`
- end: `0x180015017`
- name: `ScriptTextOut`
- size: `2311`
- prototype: `HRESULT __stdcall(const HDC hdc, SCRIPT_CACHE *psc, int x, int y, UINT fuOptions, const RECT *lprc, const SCRIPT_ANALYSIS *psa, const WCHAR *pwcReserved, int iReserved, const WORD *pwGlyphs, int cGlyphs, const int *piAdvance, const int *piJustify, const GOFFSET *pGoffset)`
- caller_count: `2`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011a70`
- `0x1800133b8`

## callees

- `0x1800039f0`
- `0x1800040d0`
- `0x180005cc0`
- `0x180005fac`
- `0x180009d00`
- `0x180009ea0`
- `0x18000a0d0`
- `0x18000d620`
- `0x18000d6c0`
- `0x18000da60`
- `0x180014240`
- `0x180014710`
- `0x180015190`
- `0x180015970`
- `0x180016750`
- `0x180016900`
- `0x18001c820`
- `0x18001fe20`
- `0x180021fe0`
- `0x180029790`
- `0x18003d980`
- `0x18004140c`
- `0x18005c570`
- `0x18005c720`
- `0x180060d30`
- `0x18006df10`
- `0x18007ac50`
- `0x18009b3b0`
- `0x18009b6c0`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800148b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014895`
- `GDI32!DeleteDC` at `0x180014de9`
- `GDI32!DeleteDC` at `0x180014de9`
- `GDI32!ExtTextOutW` at `0x180014aa5`
- `GDI32!ExtTextOutW` at `0x180014c16`
- `GDI32!ExtTextOutW` at `0x180014dc8`
- `GDI32!ExtTextOutW` at `0x180014aa5`
- `GDI32!ExtTextOutW` at `0x180014c16`
- `GDI32!ExtTextOutW` at `0x180014dc8`
- `GDI32!MoveToEx` at `0x180014a63`
- `GDI32!MoveToEx` at `0x180014ace`
- `GDI32!MoveToEx` at `0x180014d8d`
- `GDI32!MoveToEx` at `0x180014a63`
- `GDI32!MoveToEx` at `0x180014ace`
- `GDI32!MoveToEx` at `0x180014d8d`
- `GDI32!SelectObject` at `0x180014d40`
- `GDI32!SelectObject` at `0x180014fe5`
- `GDI32!SelectObject` at `0x180015002`
- `GDI32!SelectObject` at `0x180014d40`
- `GDI32!SelectObject` at `0x180014fe5`
- `GDI32!SelectObject` at `0x180015002`
- `GDI32!SetBkMode` at `0x180014a52`
- `GDI32!SetBkMode` at `0x180014ae9`
- `GDI32!SetBkMode` at `0x180014d7b`
- `GDI32!SetBkMode` at `0x180014a52`
- `GDI32!SetBkMode` at `0x180014ae9`
- `GDI32!SetBkMode` at `0x180014d7b`
- `GDI32!SetTextAlign` at `0x180014a44`
- `GDI32!SetTextAlign` at `0x180014ad9`
- `GDI32!SetTextAlign` at `0x180014d6c`
- `GDI32!SetTextAlign` at `0x180014a44`
- `GDI32!SetTextAlign` at `0x180014ad9`
- `GDI32!SetTextAlign` at `0x180014d6c`
- `GDI32!DeleteObject` at `0x180014fef`
- `GDI32!DeleteObject` at `0x18001500c`
- `GDI32!DeleteObject` at `0x180014fef`
- `GDI32!DeleteObject` at `0x18001500c`
- `TextShaping!ShapingDrawGlyphs` at `0x180014b76`
- `TextShaping!ShapingDrawGlyphs` at `0x180014b76`

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
  WCHAR *v14; // r15
  struct _ABC *v16; // rsi
  const WCHAR *lpString; // r13
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
    v14 = (WCHAR *)v72;
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
    v40 = ((__int64 (__fastcall *)(const HDC, HDC, _QWORD, _QWORD, UINT, RECT *, const SCRIPT_ANALYSIS *, const WCHAR *, UINT, const int *, struct _ABC *, const GOFFSET *))funcs_180014CAF[3 * (v30 & 0x3FF)])(
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
0x180014710  push    rbp
0x180014712  push    rbx
0x180014713  push    rsi
0x180014714  push    rdi
0x180014715  push    r12
0x180014717  push    r13
0x180014719  push    r14
0x18001471b  push    r15
0x18001471d  lea     rbp, [rsp-138h]
0x180014725  sub     rsp, 248h
0x18001472c  mov     rax, cs:__security_cookie
0x180014733  xor     rax, rsp
0x180014736  mov     [rbp+170h+var_50], rax
0x18001473d  mov     rax, [rbp+170h+lprc]
0x180014744  xor     r15d, r15d
0x180014747  movsxd  rdi, [rbp+170h+cGlyphs]
0x18001474e  mov     r14, rcx
0x180014751  mov     rsi, [rbp+170h+piJustify]
0x180014758  mov     rbx, [rbp+170h+psa]
0x18001475f  mov     r13, [rbp+170h+pwGlyphs]
0x180014766  mov     r12, [rbp+170h+piAdvance]
0x18001476d  mov     [rbp+170h+var_1B0], rax
0x180014771  mov     rax, [rbp+170h+pGoffset]
0x180014778  mov     [rbp+170h+var_1C8], rax
0x18001477c  mov     [rbp+170h+y], r9d
0x180014780  mov     [rbp+170h+pt.x], r8d
0x180014784  mov     [rbp+170h+hdc], rdx
0x180014788  mov     [rbp+170h+var_1E0], edi
0x18001478b  mov     [rbp+170h+var_1D0], rsi
0x18001478f  mov     qword ptr [rbp+170h+var_1C0], r15
0x180014793  test    rcx, rcx
0x180014796  jz      loc_180014C4F
0x18001479c  test    rbx, rbx
0x18001479f  jz      loc_180014C4F
0x1800147a5  test    r13, r13
0x1800147a8  jz      loc_180014C4F
0x1800147ae  test    r12, r12
0x1800147b1  jz      loc_180014C4F
0x1800147b7  call    ?UspAcquireTempAlloc@@YAHK@Z; UspAcquireTempAlloc(ulong)
0x1800147bc  mov     [rbp+170h+var_1DC], eax
0x1800147bf  mov     ecx, 4400h
0x1800147c4  movzx   eax, word ptr [rbx]
0x1800147c7  and     ax, cx
0x1800147ca  cmp     ax, cx
0x1800147cd  jnz     short loc_18001480B
0x1800147cf  lea     r8, ds:0[rdi*4]
0x1800147d7  lea     rax, ds:3[rdi*2]
0x1800147df  mov     [rbp+170h+h], r8
0x1800147e3  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800147e7  mov     [rbp+170h+var_1D0], rax
0x1800147eb  lea     rdx, [r8+rax]
0x1800147ef  cmp     rdx, rax
0x1800147f2  jnb     loc_180014DF4
0x1800147f8  lea     rcx, [rbp+170h+var_1DC]; this
0x1800147fc  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180014801  mov     eax, 8007000Eh
0x180014806  jmp     loc_180014BB5
0x18001480b  mov     rax, rsi
0x18001480e  jmp     short loc_18001483A
0x180014810  test    rsi, rsi
0x180014813  jnz     loc_180014F7E
0x180014819  mov     r8, [rbp+170h+var_1C8]
0x18001481d  test    r8, r8
0x180014820  jnz     loc_180014E7A
0x180014826  xor     r11d, r11d
0x180014829  mov     rax, rsi
0x18001482c  mov     [rbp+170h+var_1C8], r11
0x180014830  mov     [rbp+170h+var_1D0], rax
0x180014834  mov     r13, r15
0x180014837  mov     r12, r10
0x18001483a  mov     edi, [rbp+170h+fuOptions]
0x180014840  movzx   esi, word ptr [rbx]
0x180014843  and     edi, 6
0x180014846  test    si, si
0x180014849  js      loc_180014BE2
0x18001484f  mov     rax, [rbp+170h+hdc]
0x180014853  test    rax, rax
0x180014856  jz      loc_180014CE5
0x18001485c  mov     rcx, [rax]
0x18001485f  and     esi, 3FFh
0x180014865  test    rcx, rcx
0x180014868  jz      short loc_18001488E
0x18001486a  mov     rdx, [rcx+50h]
0x18001486e  test    rdx, rdx
0x180014871  jz      short loc_18001488E
0x180014873  cmp     esi, 0E1h
0x180014879  jnb     loc_180014CE5
0x18001487f  cmp     qword ptr [rdx+rsi*8+158h], 0FFFFFFFFFFFFFFFFh
0x180014888  jnz     loc_180014C47
0x18001488e  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180014895  call    cs:__imp_EnterCriticalSection
0x18001489b  mov     edx, esi; int
0x18001489d  mov     r8, r14; HDC
0x1800148a0  mov     rsi, [rbp+170h+hdc]
0x1800148a4  mov     rcx, rsi; void **
0x1800148a7  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x1800148ac  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800148b3  mov     dword ptr [rbp+170h+hdc], eax
0x1800148b6  call    cs:__imp_LeaveCriticalSection
0x1800148bc  mov     eax, dword ptr [rbp+170h+hdc]
0x1800148bf  test    eax, eax
0x1800148c1  jns     short loc_1800148CE
0x1800148c3  cmp     eax, 80040200h
0x1800148c8  jnz     loc_180014CC7
0x1800148ce  movzx   r9d, word ptr [rbx]
0x1800148d2  mov     r10, [rsi]
0x1800148d5  mov     r8d, r9d
0x1800148d8  and     r8d, 3FFh
0x1800148df  mov     eax, r8d
0x1800148e2  mov     rdx, [r10+50h]
0x1800148e6  and     eax, 8000001Fh
0x1800148eb  jge     short loc_1800148F4
0x1800148ed  dec     eax
0x1800148ef  or      eax, 0FFFFFFE0h
0x1800148f2  inc     eax
0x1800148f4  movzx   ecx, al
0x1800148f7  lea     r11, __ImageBase
0x1800148fe  mov     rax, r9
0x180014901  shr     rax, 5
0x180014905  and     eax, 1Fh
0x180014908  mov     eax, [rdx+rax*4+0F8h]
0x18001490f  bt      eax, ecx
0x180014912  jnb     loc_180014C59
0x180014918  movzx   ecx, word ptr [rdx+14h]
0x18001491c  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x180014923  mov     [rbp+170h+var_130], rax
0x180014927  xor     esi, esi
0x180014929  lea     rax, ??_7CUspShapingFont@@6B@; const CUspShapingFont::`vftable'
0x180014930  mov     [rbp+170h+var_128], esi
0x180014933  mov     [rbp+170h+var_F0], rax
0x18001493a  xorps   xmm0, xmm0
0x18001493d  mov     rax, r9
0x180014940  mov     [rbp+170h+var_E8], r14
0x180014947  and     eax, 3FFh
0x18001494c  mov     [rbp+170h+var_E0], r10
0x180014953  cmp     cx, 40h ; '@'
0x180014957  mov     [rbp+170h+var_D8], esi
0x18001495d  mov     ecx, r9d
0x180014960  mov     [rbp+170h+var_110], esi
0x180014963  xorps   xmm1, xmm1
0x180014966  mov     [rbp+170h+var_11C], 746C6664h
0x18001496d  movzx   edx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r11+rax*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180014976  mov     eax, esi
0x180014978  setz    al
0x18001497b  mov     [rbp+170h+var_118], 746C6664h
0x180014982  shr     ecx, 1
0x180014984  and     r9d, 400h
0x18001498b  mov     [rbp+170h+var_114], eax
0x18001498e  and     ecx, 1800h
0x180014994  movzx   eax, word ptr [rbx+2]
0x180014998  or      ecx, r9d
0x18001499b  and     eax, 400h
0x1800149a0  shr     ecx, 0Ah
0x1800149a3  bts     eax, 0Dh
0x1800149a7  mov     [rbp+170h+var_198], r14
0x1800149ab  shr     eax, 7
0x1800149ae  or      ecx, eax
0x1800149b0  movdqu  xmmword ptr [rbp+170h+ho], xmm0
0x1800149b5  cmp     edx, 0FFFFh
0x1800149bb  mov     [rbp+170h+var_10C], ecx
0x1800149be  mov     ecx, 1
0x1800149c3  movdqu  xmmword ptr [rbp+170h+var_170], xmm1
0x1800149c8  cmovz   edx, ecx
0x1800149cb  mov     [rbp+170h+var_188], ecx
0x1800149ce  mov     [rbp+170h+var_120], edx
0x1800149d1  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x1800149d8  mov     edx, [rbp+170h+pt.x]
0x1800149db  mov     rcx, r14; hdc
0x1800149de  mov     [rbp+170h+var_1A0], rax
0x1800149e2  lea     rax, [rbp+170h+var_120]
0x1800149e6  mov     [rbp+170h+var_190], edx
0x1800149e9  mov     edx, [rbp+170h+y]
0x1800149ec  mov     [rbp+170h+var_18C], edx
0x1800149ef  mov     [rbp+170h+y], 3E8h
0x1800149f6  movups  [rbp+170h+var_1C0], xmm0
0x1800149fa  mov     [rbp+170h+var_158], 0FFFFFFFFh
0x180014a01  mov     [rbp+170h+var_154], rsi
0x180014a05  mov     [rbp+170h+var_148], r10
0x180014a09  mov     [rbp+170h+var_140], rax
0x180014a0d  mov     [rbp+170h+var_138], r8d
0x180014a11  mov     [rbp+170h+var_134], 0FFFFFFFFh
0x180014a18  mov     qword ptr [rbp+170h+pt.x], rsi
0x180014a1c  call    GetTextAlign
0x180014a21  lea     rdx, [rbp+170h+pt]; lppt
0x180014a25  mov     rcx, r14; hdc
0x180014a28  mov     esi, eax
0x180014a2a  call    GetCurrentPositionEx
0x180014a2f  mov     rcx, r14; hdc
0x180014a32  call    GetBkMode
0x180014a37  mov     edx, esi
0x180014a39  mov     rcx, r14; hdc
0x180014a3c  and     edx, 0FFFFFFF9h
0x180014a3f  mov     ebx, eax
0x180014a41  or      edx, 1; align
0x180014a44  call    cs:__imp_SetTextAlign
0x180014a4a  mov     edx, 1; mode
0x180014a4f  mov     rcx, r14; hdc
0x180014a52  call    cs:__imp_SetBkMode
0x180014a58  xor     r9d, r9d; lppt
0x180014a5b  xor     r8d, r8d; y
0x180014a5e  xor     edx, edx; x
0x180014a60  mov     rcx, r14; hdc
0x180014a63  call    cs:__imp_MoveToEx
0x180014a69  xorps   xmm0, xmm0
0x180014a6c  lea     rax, [rbp+170h+y]
0x180014a70  mov     r9d, 1004h; options
0x180014a76  mov     [rsp+280h+lpDx], rax; lpDx
0x180014a7b  xor     r8d, r8d; y
0x180014a7e  lea     rax, String; " "
0x180014a85  mov     [rsp+280h+c], 1; c
0x180014a8d  mov     [rsp+280h+lpString], rax; lpString
0x180014a92  xor     edx, edx; x
0x180014a94  lea     rax, [rbp+170h+rect]
0x180014a98  mov     rcx, r14; hdc
0x180014a9b  mov     [rsp+280h+lprect], rax; lprect
0x180014aa0  movdqu  xmmword ptr [rbp+170h+rect.left], xmm0
0x180014aa5  call    cs:__imp_ExtTextOutW
0x180014aab  lea     rdx, [rbp+170h+var_160]; lppt
0x180014aaf  mov     rcx, r14; hdc
0x180014ab2  call    GetCurrentPositionEx
0x180014ab7  cmp     [rbp+170h+var_160.x], 0
0x180014abb  jz      loc_180014CFA
0x180014ac1  mov     r8d, [rbp+170h+pt.y]; y
0x180014ac5  xor     r9d, r9d; lppt
0x180014ac8  mov     edx, [rbp+170h+pt.x]; x
0x180014acb  mov     rcx, r14; hdc
0x180014ace  call    cs:__imp_MoveToEx
0x180014ad4  mov     edx, esi; align
0x180014ad6  mov     rcx, r14; hdc
0x180014ad9  call    cs:__imp_SetTextAlign
0x180014adf  cmp     ebx, 1
0x180014ae2  jz      short loc_180014AEF
0x180014ae4  mov     edx, ebx; mode
0x180014ae6  mov     rcx, r14; hdc
0x180014ae9  call    cs:__imp_SetBkMode
0x180014aef  mov     rcx, r14; hdc
0x180014af2  call    GetTextAlign
0x180014af7  mov     rcx, [rbp+170h+var_1D0]
0x180014afb  xor     ebx, ebx
0x180014afd  cmp     [rbp+170h+var_120], 17h
0x180014b01  mov     edx, [rbp+170h+var_1E0]
0x180014b04  mov     dword ptr [rbp+170h+var_154+4], eax
0x180014b07  jz      loc_180014EC2
0x180014b0d  mov     r8, [rbp+170h+var_1C8]
0x180014b11  lea     rax, [rbp+170h+var_1C0]
0x180014b15  mov     r9, [rbp+170h+var_1B0]
0x180014b19  mov     [rsp+280h+var_200], ebx
0x180014b20  mov     [rsp+280h+var_208], ebx
0x180014b24  mov     [rsp+280h+var_210], rax
0x180014b29  lea     rax, [rbp+170h+var_1A0]
0x180014b2d  mov     [rsp+280h+var_218], rax
0x180014b32  mov     [rsp+280h+var_220], r8
0x180014b37  lea     r8, [rbp+170h+var_120]
0x180014b3b  mov     [rsp+280h+var_228], rcx
0x180014b40  lea     rcx, [rbp+170h+var_130]
0x180014b44  mov     [rsp+280h+var_230], r12
0x180014b49  mov     dword ptr [rsp+280h+var_238], edx
0x180014b4d  lea     rdx, [rbp+170h+var_F0]
0x180014b54  mov     [rsp+280h+var_240], rbx
0x180014b59  mov     [rsp+280h+lpDx], r13
0x180014b5e  mov     [rsp+280h+c], ebx
0x180014b62  mov     qword ptr [rbp+170h+var_1C0], r9
0x180014b66  xor     r9d, r9d
0x180014b69  mov     [rsp+280h+lpString], rbx
0x180014b6e  mov     [rsp+280h+lprect], rbx
0x180014b73  mov     dword ptr [rbp+170h+var_1C0+8], edi
0x180014b76  call    cs:__imp_ShapingDrawGlyphs
0x180014b7c  test    eax, eax
0x180014b7e  jnz     loc_180014C2B
0x180014b84  cmp     [rbp+170h+ho], 0
0x180014b89  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x180014b90  mov     [rbp+170h+var_1A0], rax
0x180014b94  jnz     loc_180014FDD
0x180014b9a  cmp     [rbp+170h+var_170], 0
0x180014b9f  jnz     loc_180014FFA
0x180014ba5  test    r15, r15
0x180014ba8  jnz     short loc_180014BD8
0x180014baa  lea     rcx, [rbp+170h+var_1DC]; this
0x180014bae  call    ??1CTempMemory@@QEAA@XZ; CTempMemory::~CTempMemory(void)
0x180014bb3  mov     eax, ebx
0x180014bb5  mov     rcx, [rbp+170h+var_50]
0x180014bbc  xor     rcx, rsp; StackCookie
0x180014bbf  call    __security_check_cookie
0x180014bc4  add     rsp, 248h
0x180014bcb  pop     r15
0x180014bcd  pop     r14
0x180014bcf  pop     r13
0x180014bd1  pop     r12
0x180014bd3  pop     rdi
0x180014bd4  pop     rsi
0x180014bd5  pop     rbx
0x180014bd6  pop     rbp
0x180014bd7  retn
0x180014bd8  mov     rcx, r15; lpMem
0x180014bdb  call    UspFreeMem
0x180014be0  jmp     short loc_180014BAA
0x180014be2  test    rax, rax
0x180014be5  jnz     loc_180014CBB
0x180014beb  mov     edx, [rbp+170h+var_1E0]
0x180014bee  bts     edi, 0Ch
  ... truncated ...
```
