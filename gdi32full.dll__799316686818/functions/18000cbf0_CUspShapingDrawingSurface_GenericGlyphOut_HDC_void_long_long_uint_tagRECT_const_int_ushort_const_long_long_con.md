# CUspShapingDrawingSurface::GenericGlyphOut(HDC__ *,void * *,long,long,uint,tagRECT const *,int,ushort const *,long,long const *,long const *,tagGOFFSET const *)

- ea: `0x18000cbf0`
- end: `0x18000d4f9`
- name: `?GenericGlyphOut@CUspShapingDrawingSurface@@CAJPEAUHDC__@@PEAPEAXJJIPEBUtagRECT@@HPEBGJPEBJ4PEBUtagGOFFSET@@@Z`
- size: `2313`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, void **@<rdx>, int@<r8d>, int@<r9d>, UINT options, const struct tagRECT *, int, const unsigned __int16 *, UINT, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18000c740`

## callees

- `0x180009d00`
- `0x18000cbf0`
- `0x18000d500`
- `0x18000d620`
- `0x18000d6c0`
- `0x18000da60`
- `0x18000e8b4`
- `0x180010e60`
- `0x180015970`
- `0x180016900`
- `0x180026640`
- `0x180079350`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `GDI32!ExtTextOutW` at `0x18000cdc3`
- `GDI32!ExtTextOutW` at `0x18000cf80`
- `GDI32!ExtTextOutW` at `0x18000d0a1`
- `GDI32!ExtTextOutW` at `0x18000cdc3`
- `GDI32!ExtTextOutW` at `0x18000cf80`
- `GDI32!ExtTextOutW` at `0x18000d0a1`
- `GDI32!GetDeviceCaps` at `0x18000cc9a`
- `GDI32!GetDeviceCaps` at `0x18000cc9a`
- `GDI32!MoveToEx` at `0x18000d11e`
- `GDI32!MoveToEx` at `0x18000d11e`
- `GDI32!SelectObject` at `0x18000cdee`
- `GDI32!SelectObject` at `0x18000d0e4`
- `GDI32!SelectObject` at `0x18000d472`
- `GDI32!SelectObject` at `0x18000d4ab`
- `GDI32!SelectObject` at `0x18000d4e5`
- `GDI32!SelectObject` at `0x18000cdee`
- `GDI32!SelectObject` at `0x18000d0e4`
- `GDI32!SelectObject` at `0x18000d472`
- `GDI32!SelectObject` at `0x18000d4ab`
- `GDI32!SelectObject` at `0x18000d4e5`
- `GDI32!SetBkMode` at `0x18000cde1`
- `GDI32!SetBkMode` at `0x18000d0ac`
- `GDI32!SetBkMode` at `0x18000d464`
- `GDI32!SetBkMode` at `0x18000d49c`
- `GDI32!SetBkMode` at `0x18000d4d8`
- `GDI32!SetBkMode` at `0x18000cde1`
- `GDI32!SetBkMode` at `0x18000d0ac`
- `GDI32!SetBkMode` at `0x18000d464`
- `GDI32!SetBkMode` at `0x18000d49c`
- `GDI32!SetBkMode` at `0x18000d4d8`
- `GDI32!pldcGet` at `0x18000d359`
- `GDI32!pldcGet` at `0x18000d359`
- `GDI32!GdiSetLastError` at `0x18000d207`
- `GDI32!GdiSetLastError` at `0x18000d419`
- `GDI32!GdiSetLastError` at `0x18000d207`
- `GDI32!GdiSetLastError` at `0x18000d419`
- `GDI32!DeleteObject` at `0x18000cdf7`
- `GDI32!DeleteObject` at `0x18000d47b`
- `GDI32!DeleteObject` at `0x18000d4b4`
- `GDI32!DeleteObject` at `0x18000d4ee`
- `GDI32!DeleteObject` at `0x18000cdf7`
- `GDI32!DeleteObject` at `0x18000d47b`
- `GDI32!DeleteObject` at `0x18000d4b4`
- `GDI32!DeleteObject` at `0x18000d4ee`
- `win32u!NtGdiExtGetObjectW` at `0x18000d223`
- `win32u!NtGdiExtGetObjectW` at `0x18000d223`

## pseudocode

```c
__int64 __fastcall CUspShapingDrawingSurface::GenericGlyphOut(
        HDC hdc,
        void **a2,
        LONG a3,
        LONG a4,
        UINT options,
        struct tagRECT *a6,
        int a7,
        const unsigned __int16 *a8,
        int c,
        int *a10,
        int *a11,
        const struct tagGOFFSET *a12)
{
  const struct tagGOFFSET *v14; // r15
  int DeviceCaps; // eax
  int v16; // eax
  INT *v17; // rax
  int v18; // ebx
  unsigned int v19; // edi
  int v20; // esi
  void *v21; // r12
  int v22; // r10d
  int v23; // ecx
  UINT v24; // edx
  int v25; // eax
  unsigned int v26; // r13d
  HDC v27; // rbx
  __int64 DCObject; // rax
  HCOLORSPACE v30; // r13
  int v31; // r9d
  LONG *v32; // r8
  WCHAR *v33; // r10
  INT v34; // edx
  LONG dv; // r11d
  INT *v36; // r12
  __int64 v37; // rax
  int v38; // r10d
  LONG v39; // ebx
  int v40; // edx
  int *v41; // rbx
  LONG v42; // edx
  UINT v43; // r9d
  const WCHAR *v44; // rcx
  HDC v45; // rbx
  unsigned int v46; // eax
  int ObjectW; // eax
  HDC v48; // r12
  signed int v49; // edx
  INT v50; // r8d
  __int64 v51; // rax
  DWORD ObjectType; // eax
  int v53; // ecx
  int v54; // eax
  void *v55; // rax
  LONG du; // ecx
  BOOL v57; // edx
  UINT v58; // ecx
  int v59; // eax
  bool v60; // zf
  signed int j; // edx
  signed int i; // eax
  LPCWSTR v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rax
  const int *v66; // r12
  INT *v67; // r13
  int v68; // eax
  INT *lpDx; // [rsp+40h] [rbp-C8h]
  int v72; // [rsp+50h] [rbp-B8h]
  int mode; // [rsp+54h] [rbp-B4h]
  BOOL v74; // [rsp+58h] [rbp-B0h]
  int v75; // [rsp+5Ch] [rbp-ACh]
  UINT v76; // [rsp+60h] [rbp-A8h]
  tagPOINT pt; // [rsp+68h] [rbp-A0h] BYREF
  INT v78[2]; // [rsp+70h] [rbp-98h] BYREF
  HDC hdca; // [rsp+78h] [rbp-90h]
  const int *v80; // [rsp+80h] [rbp-88h] BYREF
  WCHAR *v81; // [rsp+88h] [rbp-80h]
  INT *v82; // [rsp+90h] [rbp-78h]
  const int *v83; // [rsp+98h] [rbp-70h]
  HGDIOBJ h; // [rsp+A0h] [rbp-68h]
  UINT v85; // [rsp+A8h] [rbp-60h]
  void *v86; // [rsp+B0h] [rbp-58h]
  LPCWSTR lpString; // [rsp+B8h] [rbp-50h]
  RECT *lprect; // [rsp+C0h] [rbp-48h]
  void **v89; // [rsp+C8h] [rbp-40h]
  tagTEXTMETRICW tm; // [rsp+D8h] [rbp-30h] BYREF
  UINT optionsa; // [rsp+1A8h] [rbp+A0h]

  lprect = a6;
  v89 = a2;
  hdca = hdc;
  v80 = a11;
  v83 = a10;
  lpString = a8;
  if ( !a8 || !a10 || c <= 0 )
    return 2147942487LL;
  v14 = a12;
  DeviceCaps = GetDeviceCaps(hdc, 2);
  if ( (DeviceCaps & 0xFFFFFFF9) == 0 && DeviceCaps != 6 )
    goto LABEL_9;
  optionsa = options | 0x10;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 || ((unsigned int)hdc & 0x7F0000) == 0x660000 )
    goto LABEL_7;
  v65 = pldcGet(hdc);
  if ( !v65 )
  {
    GdiSetLastError(6);
LABEL_7:
    v16 = 0;
    goto LABEL_8;
  }
  v16 = (*(_DWORD *)(v65 + 8) >> 17) & 1;
LABEL_8:
  if ( v16 )
LABEL_9:
    optionsa = options | 0x10010;
  v17 = a11;
  v18 = 0;
  v19 = 1;
  if ( !a11 )
    v17 = a10;
  v20 = 0;
  v82 = v17;
  if ( a12 )
  {
    for ( i = 0; i < c; ++i )
    {
      if ( v20 )
        break;
      if ( a12[i].du )
        v18 = 1;
      if ( a12[i].dv )
      {
        v18 = 1;
        v20 = 1;
      }
    }
  }
  v75 = 0;
  if ( a7 && v80 )
  {
    for ( j = 0; j < c; ++j )
    {
      if ( v80[j] != v83[j] )
      {
        v75 = 1;
        break;
      }
    }
  }
  v78[0] = 0;
  memset(&tm, 0, sizeof(tm));
  if ( !GetTextMetricsW(hdc, &tm) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v21 = 0;
  mode = 0;
  v86 = 0;
  if ( !tm.tmUnderlined && !tm.tmStruckOut )
  {
    h = 0;
LABEL_18:
    v22 = a4;
    v23 = a3;
    goto LABEL_19;
  }
  memset_0(&tm, 0, 0x5Cu);
  DCObject = GetDCObject(hdc, 655360);
  h = (HGDIOBJ)DCObject;
  v30 = (HCOLORSPACE)DCObject;
  if ( !DCObject )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v46 = DCObject & 0x7F0000;
  if ( v46 > 0x210000 )
  {
    if ( v46 != 4587520 && v46 != 2490368 )
      goto LABEL_59;
LABEL_95:
    GdiSetLastError(6);
    return HRESULT_FROM_LAST_WIN32_ERROR();
  }
  switch ( v46 )
  {
    case 0x210000u:
      goto LABEL_95;
    case 0x90000u:
      ObjectW = GetLogColorSpaceW(v30, (LPLOGCOLORSPACEW)&tm, 0x5Cu) ? 0x24C : 0;
      goto LABEL_60;
    case 0x10000u:
      goto LABEL_95;
    case 0xA0000u:
      ObjectW = NtGdiExtGetObjectW(v30, 92, &tm);
      goto LABEL_60;
  }
LABEL_59:
  ObjectW = cjGetNonFontObject(v30, 92, &tm);
LABEL_60:
  if ( !ObjectW )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  if ( tm.tmDescent != tm.tmInternalLeading )
    goto LABEL_18;
  v48 = hdca;
  v76 = GetTextAlign(hdca) & 1;
  if ( v76 )
  {
    pt = 0;
    GetCurrentPositionEx(hdca, &pt);
    a4 = pt.y;
    a3 = pt.x;
  }
  else
  {
    v78[0] = 0;
  }
  v49 = 0;
  v50 = 0;
  do
  {
    v51 = v49++;
    v50 += v82[v51];
  }
  while ( v49 < c );
  v78[0] = v50;
  ObjectType = GetObjectType(v48);
  v53 = 0;
  if ( ((ObjectType - 4) & 0xFFFFFFF7) != 0 )
    v53 = 4096;
  ExtTextOutW(v48, a3, a4, v53 | optionsa & 0xFFFEFFEF, lprect, L" ", 1u, v78);
  v54 = SetBkMode(v48, 1);
  *(_WORD *)((char *)&tm.tmAveCharWidth + 1) = 0;
  mode = v54;
  v55 = (void *)CreateFontIndirectWImpl(&tm);
  v14 = a12;
  v21 = v55;
  v86 = v55;
  if ( !v55 )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  if ( !SelectObject(hdca, v55) )
  {
    SetBkMode(hdca, mode);
    SelectObject(hdca, v30);
    DeleteObject(v21);
    return HRESULT_FROM_LAST_WIN32_ERROR();
  }
  v24 = optionsa & 0xFFFFFFFD;
  optionsa &= ~2u;
  if ( !v76 )
  {
    v22 = a4;
    v23 = a3;
    goto LABEL_20;
  }
  MoveToEx(hdca, a3, a4, 0);
  v23 = a3;
  v22 = a4;
LABEL_19:
  v24 = optionsa;
LABEL_20:
  v25 = v75;
  v26 = 0;
  if ( !v75 && !v18 )
  {
    v27 = hdca;
    if ( !ExtTextOutW(hdca, v23, v22, v24, lprect, lpString, c, v82) )
      v26 = HRESULT_FROM_LAST_WIN32_ERROR();
    if ( v21 )
    {
      SetBkMode(v27, mode);
      SelectObject(v27, h);
      DeleteObject(v21);
      return v26;
    }
    return v26;
  }
  if ( v14 )
    du = v14->du;
  else
    du = 0;
  if ( v75 )
    v25 = *v82 - *v83;
  v72 = du + v25;
  v57 = du + v25 || v14 && v14->dv;
  v74 = v57;
  v85 = v57 + c;
  v58 = 8 * (v57 + c);
  if ( !v20 )
    v58 = 4 * (v57 + c);
  v78[1] = v58;
  if ( v57 )
    v59 = v58 + 2 * (v57 + c);
  else
    v59 = v58;
  v41 = 0;
  LODWORD(v81) = v59;
  pt = 0;
  v60 = v59 == 0;
  if ( v59 < 0 )
    goto LABEL_28;
  if ( v59 <= 0 )
  {
LABEL_87:
    if ( !v60 )
      goto LABEL_88;
LABEL_28:
    if ( v74 )
    {
      v63 = lpString;
      v33 = (WCHAR *)((char *)v41 + v78[1]);
      v81 = v33;
      v64 = 0;
      *v33 = *(_WORD *)(*((_QWORD *)*v89 + 10) + 280LL);
      do
      {
        v33[v64 + 1] = v63[v64];
        v64 = (unsigned int)(v64 + 1);
      }
      while ( (int)v64 < c );
      v31 = v72;
      v32 = v41 + 1;
      *v41 = v72;
      if ( v20 )
      {
        *v32 = v14->dv;
        v32 = v41 + 2;
        goto LABEL_31;
      }
    }
    else
    {
      v31 = v72;
      v32 = v41;
      v33 = 0;
    }
    v81 = v33;
LABEL_31:
    v34 = *v82;
    if ( v14 )
      dv = v14->dv;
    else
      dv = 0;
    if ( c > 1 )
    {
      if ( v14 )
      {
        v36 = v82;
        do
        {
          v78[1] = v14[v19].du;
          v37 = 4LL * v19;
          v80 = (const int *)v37;
          if ( v75 )
          {
            v38 = v36[v19] - v83[v19];
          }
          else
          {
            v38 = 0;
            v80 = (const int *)(4LL * v19);
          }
          v39 = v14[v19].dv;
          v40 = v34 - v31;
          v31 = v78[1] + v38;
          *v32++ = v78[1] + v38 + v40;
          if ( v20 )
          {
            *v32++ = v39 - dv;
            v37 = (__int64)v80;
          }
          v34 = *(INT *)((char *)v36 + v37);
          ++v19;
          dv = v39;
        }
        while ( (int)v19 < c );
        v26 = 0;
        v41 = (int *)pt;
        v33 = v81;
      }
      else
      {
        v66 = v83;
        v67 = v82;
        do
        {
          if ( v75 )
            v68 = v67[v19] - v66[v19];
          else
            v68 = 0;
          *v32++ = v34 + v68 - v31;
          if ( v20 )
            *v32++ = -dv;
          v31 = v68;
          dv = 0;
          v34 = v67[v19++];
        }
        while ( (int)v19 < c );
        v26 = 0;
      }
      v21 = v86;
    }
    v42 = v34 - v31;
    v43 = optionsa;
    *v32 = v42;
    if ( v20 )
    {
      v32[1] = 0;
      v43 = optionsa | 0x2000;
    }
    v44 = lpString;
    if ( v33 )
      v44 = v33;
    lpDx = v41;
    v45 = hdca;
    if ( !ExtTextOutW(hdca, a3, a4, v43, lprect, v44, v85, lpDx) )
      v26 = HRESULT_FROM_LAST_WIN32_ERROR();
    if ( v21 )
    {
      SetBkMode(v45, mode);
      SelectObject(v45, h);
      DeleteObject(v21);
    }
    if ( pt )
      UspFreeMem(*(LPVOID *)&pt);
    return v26;
  }
  v80 = 0;
  if ( (int)UspAllocTemp((unsigned int)v59, &v80) >= 0 )
  {
    v41 = (int *)v80;
    pt = (tagPOINT)v80;
    if ( v80 )
      goto LABEL_28;
    v60 = (_DWORD)v81 == 0;
    goto LABEL_87;
  }
LABEL_88:
  if ( v21 )
  {
    SetBkMode(hdca, mode);
    SelectObject(hdca, h);
    DeleteObject(v21);
    v41 = (int *)pt;
  }
  if ( v41 )
    UspFreeMem(v41);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000cbf0  mov     r11, rsp
0x18000cbf3  push    rbp
0x18000cbf4  push    rsi
0x18000cbf5  push    rdi
0x18000cbf6  push    r13
0x18000cbf8  push    r14
0x18000cbfa  lea     rbp, [r11-78h]
0x18000cbfe  sub     rsp, 150h
0x18000cc05  mov     rax, cs:__security_cookie
0x18000cc0c  xor     rax, rsp
0x18000cc0f  mov     [rbp+70h+var_40], rax
0x18000cc13  mov     rax, [rbp+70h+arg_28]
0x18000cc1a  mov     r13, rcx
0x18000cc1d  mov     rdi, [rbp+70h+arg_50]
0x18000cc24  mov     rsi, [rbp+70h+arg_48]
0x18000cc2b  mov     [rbp+70h+var_B8], rax
0x18000cc2f  mov     rax, [rbp+70h+arg_38]
0x18000cc36  mov     [rsp+170h+y], r9d
0x18000cc3b  mov     [rsp+170h+x], r8d
0x18000cc40  mov     [rbp+70h+var_B0], rdx
0x18000cc44  mov     [rsp+170h+hdc], rcx
0x18000cc49  mov     [rsp+170h+var_F8], rdi
0x18000cc4e  mov     [rbp+70h+var_E0], rsi
0x18000cc52  mov     [rbp+70h+var_C0], rax
0x18000cc56  test    rax, rax
0x18000cc59  jz      loc_18000D29C
0x18000cc5f  test    rsi, rsi
0x18000cc62  jz      loc_18000D29C
0x18000cc68  mov     r14d, [rbp+70h+arg_40]
0x18000cc6f  test    r14d, r14d
0x18000cc72  jle     loc_18000D29C
0x18000cc78  mov     [r11+10h], rbx
0x18000cc7c  mov     edx, 2; index
0x18000cc81  mov     [r11-30h], r12
0x18000cc85  mov     r12d, [rbp+70h+options]
0x18000cc8c  mov     ebx, r12d
0x18000cc8f  mov     [r11-38h], r15
0x18000cc93  mov     r15, [rbp+70h+arg_58]
0x18000cc9a  call    cs:__imp_GetDeviceCaps
0x18000cca0  xor     r9d, r9d
0x18000cca3  test    eax, 0FFFFFFF9h
0x18000cca8  jnz     short loc_18000CCAF
0x18000ccaa  cmp     eax, 6
0x18000ccad  jnz     short loc_18000CCD4
0x18000ccaf  or      r12d, 10h
0x18000ccb3  mov     eax, r13d
0x18000ccb6  and     eax, 7F0000h
0x18000ccbb  mov     [rbp+70h+options], r12d
0x18000ccc2  cmp     eax, 10000h
0x18000ccc7  jnz     loc_18000D34B
0x18000cccd  mov     eax, r9d
0x18000ccd0  test    eax, eax
0x18000ccd2  jz      short loc_18000CCE5
0x18000ccd4  mov     r12d, ebx
0x18000ccd7  or      r12d, 10010h
0x18000ccde  mov     [rbp+70h+options], r12d
0x18000cce5  test    rdi, rdi
0x18000cce8  mov     rax, rdi
0x18000cceb  mov     ebx, r9d
0x18000ccee  mov     edi, 1
0x18000ccf3  cmovz   rax, rsi
0x18000ccf7  mov     esi, r9d
0x18000ccfa  mov     [rbp+70h+var_E8], rax
0x18000ccfe  test    r15, r15
0x18000cd01  jnz     loc_18000D26F
0x18000cd07  cmp     [rbp+70h+arg_30], 0
0x18000cd0e  mov     [rsp+54h], r9d
0x18000cd13  jnz     loc_18000D22E
0x18000cd19  xorps   xmm0, xmm0
0x18000cd1c  mov     [rsp+170h+var_108], r9d
0x18000cd21  movups  xmmword ptr [rbp+70h+tm.tmOverhang], xmm0
0x18000cd25  lea     rdx, [rbp+70h+tm]; lptm
0x18000cd29  mov     rcx, r13; hdc
0x18000cd2c  movups  xmmword ptr [rbp+70h+tm.tmFirstChar], xmm0
0x18000cd30  movups  xmmword ptr [rbp+70h+tm.tmHeight], xmm0
0x18000cd34  movups  xmmword ptr [rbp+70h+tm.tmExternalLeading], xmm0
0x18000cd38  call    GetTextMetricsW
0x18000cd3d  test    eax, eax
0x18000cd3f  jz      loc_18000CE61
0x18000cd45  xor     ecx, ecx
0x18000cd47  mov     r12d, ecx
0x18000cd4a  mov     [rsp+170h+mode], ecx
0x18000cd4e  mov     [rbp+70h+var_C8], rcx
0x18000cd52  cmp     [rbp+70h+tm.tmUnderlined], cl
0x18000cd55  jnz     loc_18000CE33
0x18000cd5b  cmp     [rbp+70h+tm.tmStruckOut], cl
0x18000cd5e  jnz     loc_18000CE33
0x18000cd64  mov     [rbp+70h+h], rcx
0x18000cd68  mov     r10d, [rsp+170h+y]
0x18000cd6d  mov     ecx, [rsp+170h+x]
0x18000cd71  mov     edx, [rbp+70h+options]
0x18000cd77  mov     eax, [rsp+54h]
0x18000cd7b  xor     r13d, r13d
0x18000cd7e  mov     dword ptr [rsp+170h+var_118], r13d
0x18000cd83  test    eax, eax
0x18000cd85  jnz     loc_18000D13B
0x18000cd8b  test    ebx, ebx
0x18000cd8d  jnz     loc_18000D13B
0x18000cd93  mov     r8, [rbp+70h+var_C0]
0x18000cd97  mov     r9d, edx; options
0x18000cd9a  mov     rax, [rbp+70h+var_E8]
0x18000cd9e  mov     edx, ecx; x
0x18000cda0  mov     rbx, [rsp+170h+hdc]
0x18000cda5  mov     [rsp+170h+lpDx], rax; lpDx
0x18000cdaa  mov     rcx, rbx; hdc
0x18000cdad  mov     rax, [rbp+70h+var_B8]
0x18000cdb1  mov     [rsp+170h+c], r14d; c
0x18000cdb6  mov     [rsp+170h+lpString], r8; lpString
0x18000cdbb  mov     r8d, r10d; y
0x18000cdbe  mov     [rsp+170h+lprect], rax; lprect
0x18000cdc3  call    cs:__imp_ExtTextOutW
0x18000cdc9  test    eax, eax
0x18000cdcb  jz      loc_18000D486
0x18000cdd1  test    r12, r12
0x18000cdd4  jz      loc_18000CFA6
0x18000cdda  mov     edx, [rsp+170h+mode]; mode
0x18000cdde  mov     rcx, rbx; hdc
0x18000cde1  call    cs:__imp_SetBkMode
0x18000cde7  mov     rdx, [rbp+70h+h]; h
0x18000cdeb  mov     rcx, rbx; hdc
0x18000cdee  call    cs:__imp_SelectObject
0x18000cdf4  mov     rcx, r12; ho
0x18000cdf7  call    cs:__imp_DeleteObject
0x18000cdfd  mov     eax, r13d
0x18000ce00  mov     r12, [rsp+148h]
0x18000ce08  mov     rbx, [rsp+170h+arg_8]
0x18000ce10  mov     r15, [rsp+170h+var_30]
0x18000ce18  mov     rcx, [rbp+70h+var_40]
0x18000ce1c  xor     rcx, rsp; StackCookie
0x18000ce1f  call    __security_check_cookie
0x18000ce24  add     rsp, 150h
0x18000ce2b  pop     r14
0x18000ce2d  pop     r13
0x18000ce2f  pop     rdi
0x18000ce30  pop     rsi
0x18000ce31  pop     rbp
0x18000ce32  retn
0x18000ce33  xor     edx, edx; Val
0x18000ce35  lea     rcx, [rbp+70h+tm]; void *
0x18000ce39  mov     r8d, 5Ch ; '\'; Size
0x18000ce3f  call    memset_0
0x18000ce44  mov     edx, 0A0000h
0x18000ce49  mov     rcx, r13
0x18000ce4c  call    GetDCObject
0x18000ce51  mov     [rbp+70h+h], rax
0x18000ce55  mov     r13, rax
0x18000ce58  test    rax, rax
0x18000ce5b  jnz     loc_18000CFAE
0x18000ce61  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18000ce66  jmp     short loc_18000CE00
0x18000ce68  cmp     [rsp+170h+var_120], r13d
0x18000ce6d  jnz     loc_18000D2ED
0x18000ce73  mov     r9d, [rsp+170h+var_128]
0x18000ce78  mov     r8, rbx
0x18000ce7b  xor     r10d, r10d
0x18000ce7e  mov     [rbp+70h+var_F0], r10
0x18000ce82  mov     rax, [rbp+70h+var_E8]
0x18000ce86  mov     edx, [rax]
0x18000ce88  test    r15, r15
0x18000ce8b  jz      loc_18000D2A6
0x18000ce91  mov     r11d, [r15+4]
0x18000ce95  cmp     r14d, edi
0x18000ce98  jle     loc_18000CF2C
0x18000ce9e  mov     ecx, [rsp+54h]
0x18000cea2  test    r15, r15
0x18000cea5  jz      loc_18000D3B0
0x18000ceab  mov     r12, rax
0x18000ceae  mov     eax, edi
0x18000ceb0  mov     r10d, [r15+rax*8]
0x18000ceb4  lea     rbx, [r15+rax*8]
0x18000ceb8  mov     [rsp+170h+var_108+4], r10d
0x18000cebd  lea     rax, ds:0[rax*4]
0x18000cec5  mov     [rsp+170h+var_F8], rax
0x18000ceca  test    ecx, ecx
0x18000cecc  jnz     loc_18000D2DC
0x18000ced2  xor     r10d, r10d
0x18000ced5  mov     [rsp+170h+var_F8], rax
0x18000ceda  mov     ebx, [rbx+4]
0x18000cedd  sub     edx, r9d
0x18000cee0  mov     r9d, r10d
0x18000cee3  mov     [rsp+170h+var_128], r10d
0x18000cee8  add     r9d, [rsp+170h+var_108+4]
0x18000ceed  add     edx, r9d
0x18000cef0  mov     [r8], edx
0x18000cef3  add     r8, 4
0x18000cef7  test    esi, esi
0x18000cef9  jz      short loc_18000CF0C
0x18000cefb  mov     eax, ebx
0x18000cefd  sub     eax, r11d
0x18000cf00  mov     [r8], eax
0x18000cf03  add     r8, 4
0x18000cf07  mov     rax, [rsp+170h+var_F8]
0x18000cf0c  mov     edx, [r12+rax]
0x18000cf10  inc     edi
0x18000cf12  mov     r11d, ebx
0x18000cf15  cmp     edi, r14d
0x18000cf18  jl      short loc_18000CEAE
0x18000cf1a  mov     r13d, dword ptr [rsp+170h+var_118]
0x18000cf1f  mov     rbx, qword ptr [rsp+170h+pt.x]
0x18000cf24  mov     r10, [rbp+70h+var_F0]
0x18000cf28  mov     r12, [rbp+70h+var_C8]
0x18000cf2c  sub     edx, r9d
0x18000cf2f  mov     r9d, [rbp+70h+options]
0x18000cf36  mov     [r8], edx
0x18000cf39  test    esi, esi
0x18000cf3b  jz      short loc_18000CF4A
0x18000cf3d  mov     dword ptr [r8+4], 0
0x18000cf45  bts     r9d, 0Dh; options
0x18000cf4a  mov     eax, [rbp+70h+var_D0]
0x18000cf4d  test    r10, r10
0x18000cf50  mov     rcx, [rbp+70h+var_C0]
0x18000cf54  mov     r8d, [rsp+170h+y]; y
0x18000cf59  cmovnz  rcx, r10
0x18000cf5d  mov     edx, [rsp+170h+x]; x
0x18000cf61  mov     [rsp+170h+lpDx], rbx; lpDx
0x18000cf66  mov     rbx, [rsp+170h+hdc]
0x18000cf6b  mov     [rsp+170h+c], eax; c
0x18000cf6f  mov     rax, [rbp+70h+var_B8]
0x18000cf73  mov     [rsp+170h+lpString], rcx; lpString
0x18000cf78  mov     rcx, rbx; hdc
0x18000cf7b  mov     [rsp+170h+lprect], rax; lprect
0x18000cf80  call    cs:__imp_ExtTextOutW
0x18000cf86  test    eax, eax
0x18000cf88  jz      loc_18000D4C4
0x18000cf8e  test    r12, r12
0x18000cf91  jnz     loc_18000D4D1
0x18000cf97  mov     rcx, qword ptr [rsp+170h+pt.x]; lpMem
0x18000cf9c  test    rcx, rcx
0x18000cf9f  jz      short loc_18000CFA6
0x18000cfa1  call    UspFreeMem
0x18000cfa6  mov     eax, r13d
0x18000cfa9  jmp     loc_18000CE00
0x18000cfae  and     eax, 7F0000h
0x18000cfb3  cmp     eax, 210000h
0x18000cfb8  ja      loc_18000D1F0
0x18000cfbe  jz      loc_18000D202
0x18000cfc4  cmp     eax, 90000h
0x18000cfc9  jz      loc_18000D379
0x18000cfcf  cmp     eax, 10000h
0x18000cfd4  jz      loc_18000D202
0x18000cfda  cmp     eax, 0A0000h
0x18000cfdf  jz      loc_18000D217
0x18000cfe5  lea     r8, [rbp+70h+tm]; void *
0x18000cfe9  mov     edx, 5Ch ; '\'; int
0x18000cfee  mov     rcx, r13; void *
0x18000cff1  call    ?cjGetNonFontObject@@YAHPEAXH0@Z; cjGetNonFontObject(void *,int,void *)
0x18000cff6  test    eax, eax
0x18000cff8  jz      loc_18000CE61
0x18000cffe  mov     eax, [rbp+70h+tm.tmInternalLeading]
0x18000d001  cmp     [rbp+70h+tm.tmDescent], eax
0x18000d004  jnz     loc_18000CD68
0x18000d00a  mov     r12, [rsp+170h+hdc]
0x18000d00f  mov     rcx, r12; hdc
0x18000d012  call    GetTextAlign
0x18000d017  and     eax, edi
0x18000d019  mov     dword ptr [rsp+170h+var_118], eax
0x18000d01d  jnz     loc_18000D430
0x18000d023  mov     [rsp+170h+var_108], 0
0x18000d02b  mov     r15, [rbp+70h+var_E8]
0x18000d02f  xor     edx, edx
0x18000d031  xor     r8d, r8d
0x18000d034  movsxd  rax, edx
0x18000d037  inc     edx
0x18000d039  add     r8d, [r15+rax*4]
0x18000d03d  cmp     edx, r14d
0x18000d040  jl      short loc_18000D034
0x18000d042  mov     rcx, r12; h
0x18000d045  mov     [rsp+170h+var_108], r8d
0x18000d04a  call    GetObjectType
0x18000d04f  mov     r9d, [rbp+70h+options]
0x18000d056  add     eax, 0FFFFFFFCh
0x18000d059  mov     r8d, [rsp+170h+y]; y
0x18000d05e  xor     ecx, ecx
0x18000d060  test    eax, 0FFFFFFF7h
0x18000d065  mov     edx, 1000h
0x18000d06a  lea     rax, [rsp+170h+var_108]
0x18000d06f  mov     [rsp+170h+lpDx], rax; lpDx
0x18000d074  cmovnz  ecx, edx
0x18000d077  mov     edx, [rsp+170h+x]; x
0x18000d07b  lea     rax, String; " "
0x18000d082  and     r9d, 0FFFEFFEFh
0x18000d089  mov     [rsp+170h+c], edi; c
0x18000d08d  mov     [rsp+170h+lpString], rax; lpString
0x18000d092  or      r9d, ecx; options
0x18000d095  mov     rax, [rbp+70h+var_B8]
0x18000d099  mov     rcx, r12; hdc
0x18000d09c  mov     [rsp+170h+lprect], rax; lprect
0x18000d0a1  call    cs:__imp_ExtTextOutW
0x18000d0a7  mov     edx, edi; mode
0x18000d0a9  mov     rcx, r12; hdc
0x18000d0ac  call    cs:__imp_SetBkMode
0x18000d0b2  lea     rcx, [rbp+70h+tm]
0x18000d0b6  mov     word ptr [rbp+70h+tm.tmAveCharWidth+1], 0
0x18000d0bc  mov     [rsp+170h+mode], eax
0x18000d0c0  call    CreateFontIndirectWImpl
0x18000d0c5  mov     r15, [rbp+70h+arg_58]
0x18000d0cc  mov     r12, rax
0x18000d0cf  mov     [rbp+70h+var_C8], rax
0x18000d0d3  test    rax, rax
0x18000d0d6  jz      loc_18000CE61
  ... truncated ...
```
