# CUspShapingDrawingSurface::GenericGlyphOut(HDC__ *,void * *,long,long,uint,tagRECT const *,int,ushort const *,long,long const *,long const *,tagGOFFSET const *)

- ea: `0x180005ea0`
- end: `0x180006835`
- name: `?GenericGlyphOut@CUspShapingDrawingSurface@@CAJPEAUHDC__@@PEAPEAXJJIPEBUtagRECT@@HPEBGJPEBJ4PEBUtagGOFFSET@@@Z`
- size: `2453`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, void **@<rdx>, int@<r8d>, int@<r9d>, UINT options, const struct tagRECT *, int, const unsigned __int16 *, UINT, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800059d0`

## callees

- `0x180004f34`
- `0x180005ea0`
- `0x180006840`
- `0x180006978`
- `0x180006a28`
- `0x180006e00`
- `0x18000d040`
- `0x180019630`
- `0x180021e50`
- `0x180022b20`
- `0x18002f680`
- `0x18007def0`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `GDI32!ExtTextOutW` at `0x180006079`
- `GDI32!ExtTextOutW` at `0x18000624f`
- `GDI32!ExtTextOutW` at `0x180006376`
- `GDI32!ExtTextOutW` at `0x180006079`
- `GDI32!ExtTextOutW` at `0x18000624f`
- `GDI32!ExtTextOutW` at `0x180006376`
- `GDI32!GetDeviceCaps` at `0x180005f4a`
- `GDI32!GetDeviceCaps` at `0x180005f4a`
- `GDI32!MoveToEx` at `0x180006405`
- `GDI32!MoveToEx` at `0x180006405`
- `GDI32!SelectObject` at `0x1800060b0`
- `GDI32!SelectObject` at `0x1800063c5`
- `GDI32!SelectObject` at `0x18000677e`
- `GDI32!SelectObject` at `0x1800067c9`
- `GDI32!SelectObject` at `0x180006815`
- `GDI32!SelectObject` at `0x1800060b0`
- `GDI32!SelectObject` at `0x1800063c5`
- `GDI32!SelectObject` at `0x18000677e`
- `GDI32!SelectObject` at `0x1800067c9`
- `GDI32!SelectObject` at `0x180006815`
- `GDI32!SetBkMode` at `0x18000609d`
- `GDI32!SetBkMode` at `0x180006387`
- `GDI32!SetBkMode` at `0x18000676a`
- `GDI32!SetBkMode` at `0x1800067b4`
- `GDI32!SetBkMode` at `0x180006802`
- `GDI32!SetBkMode` at `0x18000609d`
- `GDI32!SetBkMode` at `0x180006387`
- `GDI32!SetBkMode` at `0x18000676a`
- `GDI32!SetBkMode` at `0x1800067b4`
- `GDI32!SetBkMode` at `0x180006802`
- `GDI32!pldcGet` at `0x180006657`
- `GDI32!pldcGet` at `0x180006657`
- `GDI32!GdiSetLastError` at `0x1800064f4`
- `GDI32!GdiSetLastError` at `0x180006719`
- `GDI32!GdiSetLastError` at `0x1800064f4`
- `GDI32!GdiSetLastError` at `0x180006719`
- `GDI32!DeleteObject` at `0x1800060bf`
- `GDI32!DeleteObject` at `0x18000678d`
- `GDI32!DeleteObject` at `0x1800067d8`
- `GDI32!DeleteObject` at `0x180006824`
- `GDI32!DeleteObject` at `0x1800060bf`
- `GDI32!DeleteObject` at `0x18000678d`
- `GDI32!DeleteObject` at `0x1800067d8`
- `GDI32!DeleteObject` at `0x180006824`
- `win32u!NtGdiExtGetObjectW` at `0x180006516`
- `win32u!NtGdiExtGetObjectW` at `0x180006516`

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
0x180005ea0  mov     r11, rsp
0x180005ea3  push    rbp
0x180005ea4  push    rsi
0x180005ea5  push    rdi
0x180005ea6  push    r13
0x180005ea8  push    r14
0x180005eaa  lea     rbp, [r11-78h]
0x180005eae  sub     rsp, 150h
0x180005eb5  mov     rax, cs:__security_cookie
0x180005ebc  xor     rax, rsp
0x180005ebf  mov     [rbp+70h+var_40], rax
0x180005ec3  mov     rax, [rbp+70h+arg_28]
0x180005eca  mov     r13, rcx
0x180005ecd  mov     rdi, [rbp+70h+arg_50]
0x180005ed4  mov     rsi, [rbp+70h+arg_48]
0x180005edb  mov     [rbp+70h+var_B8], rax
0x180005edf  mov     rax, [rbp+70h+arg_38]
0x180005ee6  mov     [rsp+170h+y], r9d
0x180005eeb  mov     [rsp+170h+x], r8d
0x180005ef0  mov     [rbp+70h+var_B0], rdx
0x180005ef4  mov     [rsp+170h+hdc], rcx
0x180005ef9  mov     [rsp+170h+var_F8], rdi
0x180005efe  mov     [rbp+70h+var_E0], rsi
0x180005f02  mov     [rbp+70h+var_C0], rax
0x180005f06  test    rax, rax
0x180005f09  jz      loc_18000659A
0x180005f0f  test    rsi, rsi
0x180005f12  jz      loc_18000659A
0x180005f18  mov     r14d, [rbp+70h+arg_40]
0x180005f1f  test    r14d, r14d
0x180005f22  jle     loc_18000659A
0x180005f28  mov     [r11+10h], rbx
0x180005f2c  mov     edx, 2; index
0x180005f31  mov     [r11-30h], r12
0x180005f35  mov     r12d, [rbp+70h+options]
0x180005f3c  mov     ebx, r12d
0x180005f3f  mov     [r11-38h], r15
0x180005f43  mov     r15, [rbp+70h+arg_58]
0x180005f4a  call    cs:__imp_GetDeviceCaps
0x180005f51  nop     dword ptr [rax+rax+00h]
0x180005f56  xor     r9d, r9d
0x180005f59  test    eax, 0FFFFFFF9h
0x180005f5e  jnz     short loc_180005F65
0x180005f60  cmp     eax, 6
0x180005f63  jnz     short loc_180005F8A
0x180005f65  or      r12d, 10h
0x180005f69  mov     eax, r13d
0x180005f6c  and     eax, 7F0000h
0x180005f71  mov     [rbp+70h+options], r12d
0x180005f78  cmp     eax, 10000h
0x180005f7d  jnz     loc_180006649
0x180005f83  mov     eax, r9d
0x180005f86  test    eax, eax
0x180005f88  jz      short loc_180005F9B
0x180005f8a  mov     r12d, ebx
0x180005f8d  or      r12d, 10010h
0x180005f94  mov     [rbp+70h+options], r12d
0x180005f9b  test    rdi, rdi
0x180005f9e  mov     rax, rdi
0x180005fa1  mov     ebx, r9d
0x180005fa4  mov     edi, 1
0x180005fa9  cmovz   rax, rsi
0x180005fad  mov     esi, r9d
0x180005fb0  mov     [rbp+70h+var_E8], rax
0x180005fb4  test    r15, r15
0x180005fb7  jnz     loc_180006568
0x180005fbd  cmp     [rbp+70h+arg_30], 0
0x180005fc4  mov     [rsp+54h], r9d
0x180005fc9  jnz     loc_180006527
0x180005fcf  xorps   xmm0, xmm0
0x180005fd2  mov     [rsp+170h+var_108], r9d
0x180005fd7  movups  xmmword ptr [rbp+70h+tm.tmOverhang], xmm0
0x180005fdb  lea     rdx, [rbp+70h+tm]; lptm
0x180005fdf  mov     rcx, r13; hdc
0x180005fe2  movups  xmmword ptr [rbp+70h+tm.tmFirstChar], xmm0
0x180005fe6  movups  xmmword ptr [rbp+70h+tm.tmHeight], xmm0
0x180005fea  movups  xmmword ptr [rbp+70h+tm.tmExternalLeading], xmm0
0x180005fee  call    GetTextMetricsW
0x180005ff3  test    eax, eax
0x180005ff5  jz      loc_180006130
0x180005ffb  xor     ecx, ecx
0x180005ffd  mov     r12d, ecx
0x180006000  mov     [rsp+170h+mode], ecx
0x180006004  mov     [rbp+70h+var_C8], rcx
0x180006008  cmp     [rbp+70h+tm.tmUnderlined], cl
0x18000600b  jnz     loc_180006102
0x180006011  cmp     [rbp+70h+tm.tmStruckOut], cl
0x180006014  jnz     loc_180006102
0x18000601a  mov     [rbp+70h+h], rcx
0x18000601e  mov     r10d, [rsp+170h+y]
0x180006023  mov     ecx, [rsp+170h+x]
0x180006027  mov     edx, [rbp+70h+options]
0x18000602d  mov     eax, [rsp+54h]
0x180006031  xor     r13d, r13d
0x180006034  mov     dword ptr [rsp+170h+var_118], r13d
0x180006039  test    eax, eax
0x18000603b  jnz     loc_180006428
0x180006041  test    ebx, ebx
0x180006043  jnz     loc_180006428
0x180006049  mov     r8, [rbp+70h+var_C0]
0x18000604d  mov     r9d, edx; options
0x180006050  mov     rax, [rbp+70h+var_E8]
0x180006054  mov     edx, ecx; x
0x180006056  mov     rbx, [rsp+170h+hdc]
0x18000605b  mov     [rsp+170h+lpDx], rax; lpDx
0x180006060  mov     rcx, rbx; hdc
0x180006063  mov     rax, [rbp+70h+var_B8]
0x180006067  mov     [rsp+170h+c], r14d; c
0x18000606c  mov     [rsp+170h+lpString], r8; lpString
0x180006071  mov     r8d, r10d; y
0x180006074  mov     [rsp+170h+lprect], rax; lprect
0x180006079  call    cs:__imp_ExtTextOutW
0x180006080  nop     dword ptr [rax+rax+00h]
0x180006085  test    eax, eax
0x180006087  jz      loc_18000679E
0x18000608d  test    r12, r12
0x180006090  jz      loc_18000627B
0x180006096  mov     edx, [rsp+170h+mode]; mode
0x18000609a  mov     rcx, rbx; hdc
0x18000609d  call    cs:__imp_SetBkMode
0x1800060a4  nop     dword ptr [rax+rax+00h]
0x1800060a9  mov     rdx, [rbp+70h+h]; h
0x1800060ad  mov     rcx, rbx; hdc
0x1800060b0  call    cs:__imp_SelectObject
0x1800060b7  nop     dword ptr [rax+rax+00h]
0x1800060bc  mov     rcx, r12; ho
0x1800060bf  call    cs:__imp_DeleteObject
0x1800060c6  nop     dword ptr [rax+rax+00h]
0x1800060cb  mov     eax, r13d
0x1800060ce  mov     r12, [rsp+148h]
0x1800060d6  mov     rbx, [rsp+170h+arg_8]
0x1800060de  mov     r15, [rsp+170h+var_30]
0x1800060e6  mov     rcx, [rbp+70h+var_40]
0x1800060ea  xor     rcx, rsp; StackCookie
0x1800060ed  call    __security_check_cookie
0x1800060f2  add     rsp, 150h
0x1800060f9  pop     r14
0x1800060fb  pop     r13
0x1800060fd  pop     rdi
0x1800060fe  pop     rsi
0x1800060ff  pop     rbp
0x180006100  retn
0x180006102  xor     edx, edx; Val
0x180006104  lea     rcx, [rbp+70h+tm]; void *
0x180006108  mov     r8d, 5Ch ; '\'; Size
0x18000610e  call    memset_0
0x180006113  mov     edx, 0A0000h
0x180006118  mov     rcx, r13
0x18000611b  call    GetDCObject
0x180006120  mov     [rbp+70h+h], rax
0x180006124  mov     r13, rax
0x180006127  test    rax, rax
0x18000612a  jnz     loc_180006283
0x180006130  call    HRESULT_FROM_LAST_WIN32_ERROR
0x180006135  jmp     short loc_1800060CE
0x180006137  cmp     [rsp+170h+var_120], r13d
0x18000613c  jnz     loc_1800065EB
0x180006142  mov     r9d, [rsp+170h+var_128]
0x180006147  mov     r8, rbx
0x18000614a  xor     r10d, r10d
0x18000614d  mov     [rbp+70h+var_F0], r10
0x180006151  mov     rax, [rbp+70h+var_E8]
0x180006155  mov     edx, [rax]
0x180006157  test    r15, r15
0x18000615a  jz      loc_1800065A4
0x180006160  mov     r11d, [r15+4]
0x180006164  cmp     r14d, edi
0x180006167  jle     loc_1800061FB
0x18000616d  mov     ecx, [rsp+54h]
0x180006171  test    r15, r15
0x180006174  jz      loc_1800066B4
0x18000617a  mov     r12, rax
0x18000617d  mov     eax, edi
0x18000617f  mov     r10d, [r15+rax*8]
0x180006183  lea     rbx, [r15+rax*8]
0x180006187  mov     [rsp+170h+var_108+4], r10d
0x18000618c  lea     rax, ds:0[rax*4]
0x180006194  mov     [rsp+170h+var_F8], rax
0x180006199  test    ecx, ecx
0x18000619b  jnz     loc_1800065DA
0x1800061a1  xor     r10d, r10d
0x1800061a4  mov     [rsp+170h+var_F8], rax
0x1800061a9  mov     ebx, [rbx+4]
0x1800061ac  sub     edx, r9d
0x1800061af  mov     r9d, r10d
0x1800061b2  mov     [rsp+170h+var_128], r10d
0x1800061b7  add     r9d, [rsp+170h+var_108+4]
0x1800061bc  add     edx, r9d
0x1800061bf  mov     [r8], edx
0x1800061c2  add     r8, 4
0x1800061c6  test    esi, esi
0x1800061c8  jz      short loc_1800061DB
0x1800061ca  mov     eax, ebx
0x1800061cc  sub     eax, r11d
0x1800061cf  mov     [r8], eax
0x1800061d2  add     r8, 4
0x1800061d6  mov     rax, [rsp+170h+var_F8]
0x1800061db  mov     edx, [r12+rax]
0x1800061df  inc     edi
0x1800061e1  mov     r11d, ebx
0x1800061e4  cmp     edi, r14d
0x1800061e7  jl      short loc_18000617D
0x1800061e9  mov     r13d, dword ptr [rsp+170h+var_118]
0x1800061ee  mov     rbx, qword ptr [rsp+170h+pt.x]
0x1800061f3  mov     r10, [rbp+70h+var_F0]
0x1800061f7  mov     r12, [rbp+70h+var_C8]
0x1800061fb  sub     edx, r9d
0x1800061fe  mov     r9d, [rbp+70h+options]
0x180006205  mov     [r8], edx
0x180006208  test    esi, esi
0x18000620a  jz      short loc_180006219
0x18000620c  mov     dword ptr [r8+4], 0
0x180006214  bts     r9d, 0Dh; options
0x180006219  mov     eax, [rbp+70h+var_D0]
0x18000621c  test    r10, r10
0x18000621f  mov     rcx, [rbp+70h+var_C0]
0x180006223  mov     r8d, [rsp+170h+y]; y
0x180006228  cmovnz  rcx, r10
0x18000622c  mov     edx, [rsp+170h+x]; x
0x180006230  mov     [rsp+170h+lpDx], rbx; lpDx
0x180006235  mov     rbx, [rsp+170h+hdc]
0x18000623a  mov     [rsp+170h+c], eax; c
0x18000623e  mov     rax, [rbp+70h+var_B8]
0x180006242  mov     [rsp+170h+lpString], rcx; lpString
0x180006247  mov     rcx, rbx; hdc
0x18000624a  mov     [rsp+170h+lprect], rax; lprect
0x18000624f  call    cs:__imp_ExtTextOutW
0x180006256  nop     dword ptr [rax+rax+00h]
0x18000625b  test    eax, eax
0x18000625d  jz      loc_1800067EE
0x180006263  test    r12, r12
0x180006266  jnz     loc_1800067FB
0x18000626c  mov     rcx, qword ptr [rsp+170h+pt.x]; lpMem
0x180006271  test    rcx, rcx
0x180006274  jz      short loc_18000627B
0x180006276  call    UspFreeMem
0x18000627b  mov     eax, r13d
0x18000627e  jmp     loc_1800060CE
0x180006283  and     eax, 7F0000h
0x180006288  cmp     eax, 210000h
0x18000628d  ja      loc_1800064DD
0x180006293  jz      loc_1800064EF
0x180006299  cmp     eax, 90000h
0x18000629e  jz      loc_18000667D
0x1800062a4  cmp     eax, 10000h
0x1800062a9  jz      loc_1800064EF
0x1800062af  cmp     eax, 0A0000h
0x1800062b4  jz      loc_18000650A
0x1800062ba  lea     r8, [rbp+70h+tm]; void *
0x1800062be  mov     edx, 5Ch ; '\'; int
0x1800062c3  mov     rcx, r13; void *
0x1800062c6  call    ?cjGetNonFontObject@@YAHPEAXH0@Z; cjGetNonFontObject(void *,int,void *)
0x1800062cb  test    eax, eax
0x1800062cd  jz      loc_180006130
0x1800062d3  mov     eax, [rbp+70h+tm.tmInternalLeading]
0x1800062d6  cmp     [rbp+70h+tm.tmDescent], eax
0x1800062d9  jnz     loc_18000601E
0x1800062df  mov     r12, [rsp+170h+hdc]
0x1800062e4  mov     rcx, r12; hdc
0x1800062e7  call    GetTextAlign
0x1800062ec  and     eax, edi
0x1800062ee  mov     dword ptr [rsp+170h+var_118], eax
0x1800062f2  jnz     loc_180006736
0x1800062f8  mov     [rsp+170h+var_108], 0
0x180006300  mov     r15, [rbp+70h+var_E8]
0x180006304  xor     edx, edx
0x180006306  xor     r8d, r8d
0x180006309  movsxd  rax, edx
0x18000630c  inc     edx
0x18000630e  add     r8d, [r15+rax*4]
0x180006312  cmp     edx, r14d
0x180006315  jl      short loc_180006309
0x180006317  mov     rcx, r12; h
0x18000631a  mov     [rsp+170h+var_108], r8d
0x18000631f  call    GetObjectType
0x180006324  mov     r9d, [rbp+70h+options]
0x18000632b  add     eax, 0FFFFFFFCh
0x18000632e  mov     r8d, [rsp+170h+y]; y
0x180006333  xor     ecx, ecx
0x180006335  test    eax, 0FFFFFFF7h
0x18000633a  mov     edx, 1000h
0x18000633f  lea     rax, [rsp+170h+var_108]
0x180006344  mov     [rsp+170h+lpDx], rax; lpDx
0x180006349  cmovnz  ecx, edx
0x18000634c  mov     edx, [rsp+170h+x]; x
0x180006350  lea     rax, String; " "
0x180006357  and     r9d, 0FFFEFFEFh
0x18000635e  mov     [rsp+170h+c], edi; c
0x180006362  mov     [rsp+170h+lpString], rax; lpString
0x180006367  or      r9d, ecx; options
0x18000636a  mov     rax, [rbp+70h+var_B8]
0x18000636e  mov     rcx, r12; hdc
0x180006371  mov     [rsp+170h+lprect], rax; lprect
0x180006376  call    cs:__imp_ExtTextOutW
0x18000637d  nop     dword ptr [rax+rax+00h]
0x180006382  mov     edx, edi; mode
0x180006384  mov     rcx, r12; hdc
0x180006387  call    cs:__imp_SetBkMode
0x18000638e  nop     dword ptr [rax+rax+00h]
0x180006393  lea     rcx, [rbp+70h+tm]
  ... truncated ...
```
