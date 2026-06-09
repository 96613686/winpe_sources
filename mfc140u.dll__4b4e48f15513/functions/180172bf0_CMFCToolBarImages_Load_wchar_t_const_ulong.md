# CMFCToolBarImages::Load(wchar_t const *,ulong)

- ea: `0x180172bf0`
- end: `0x180173265`
- name: `?Load@CMFCToolBarImages@@QEAAHPEB_WK@Z`
- size: `1653`
- prototype: `int __fastcall(CMFCToolBarImages *this, const wchar_t *lpszBmpFileName, unsigned int dwMaxFileSize)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180174770`

## callees

- `0x180002e40`
- `0x18000df50`
- `0x18000e0e0`
- `0x180139860`
- `0x180172bf0`
- `0x180175af0`
- `0x180175c10`
- `0x1801772c0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802aef40`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180172d16`
- `KERNEL32!GetModuleFileNameW` at `0x180172d16`
- `KERNEL32!CloseHandle` at `0x180172e2d`
- `KERNEL32!CloseHandle` at `0x180172e2d`
- `KERNEL32!CreateFileW` at `0x180172e0e`
- `KERNEL32!CreateFileW` at `0x180172e0e`
- `KERNEL32!GetFileSize` at `0x180172e22`
- `KERNEL32!GetFileSize` at `0x180172e22`
- `KERNEL32!GetFileAttributesW` at `0x180172f10`
- `KERNEL32!GetFileAttributesW` at `0x180172f10`
- `VCRUNTIME140!wcsstr` at `0x180172c87`
- `VCRUNTIME140!wcsstr` at `0x180172cb6`
- `VCRUNTIME140!wcsstr` at `0x180172ce5`
- `VCRUNTIME140!wcsstr` at `0x180172c87`
- `VCRUNTIME140!wcsstr` at `0x180172cb6`
- `VCRUNTIME140!wcsstr` at `0x180172ce5`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180172dcc`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180172dcc`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180172dc2`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180172dc2`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180172d5a`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180172d92`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180172d5a`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180172d92`
- `USER32!LoadImageW` at `0x180172e6a`
- `USER32!LoadImageW` at `0x180172e6a`
- `GDI32!DeleteDC` at `0x180172fa1`
- `GDI32!DeleteDC` at `0x180173024`
- `GDI32!DeleteDC` at `0x1801730d7`
- `GDI32!DeleteDC` at `0x180172fa1`
- `GDI32!DeleteDC` at `0x180173024`
- `GDI32!DeleteDC` at `0x1801730d7`
- `GDI32!SetPixel` at `0x180173175`
- `GDI32!SetPixel` at `0x180173175`
- `GDI32!BitBlt` at `0x180173115`
- `GDI32!BitBlt` at `0x180173115`
- `GDI32!CreateCompatibleBitmap` at `0x180172fe3`
- `GDI32!CreateCompatibleBitmap` at `0x180172fe3`
- `GDI32!GetPixel` at `0x180173137`
- `GDI32!GetPixel` at `0x180173137`
- `GDI32!DeleteObject` at `0x180172c57`
- `GDI32!DeleteObject` at `0x180172ee7`
- `GDI32!DeleteObject` at `0x1801730b1`
- `GDI32!DeleteObject` at `0x1801731af`
- `GDI32!DeleteObject` at `0x180173206`
- `GDI32!DeleteObject` at `0x180173220`
- `GDI32!DeleteObject` at `0x180172c57`
- `GDI32!DeleteObject` at `0x180172ee7`
- `GDI32!DeleteObject` at `0x1801730b1`
- `GDI32!DeleteObject` at `0x1801731af`
- `GDI32!DeleteObject` at `0x180173206`
- `GDI32!DeleteObject` at `0x180173220`
- `GDI32!SelectObject` at `0x180172fbd`
- `GDI32!SelectObject` at `0x180172ffd`
- `GDI32!SelectObject` at `0x180173091`
- `GDI32!SelectObject` at `0x1801730a8`
- `GDI32!SelectObject` at `0x180173198`
- `GDI32!SelectObject` at `0x1801731a6`
- `GDI32!SelectObject` at `0x180172fbd`
- `GDI32!SelectObject` at `0x180172ffd`
- `GDI32!SelectObject` at `0x180173091`
- `GDI32!SelectObject` at `0x1801730a8`
- `GDI32!SelectObject` at `0x180173198`
- `GDI32!SelectObject` at `0x1801731a6`
- `GDI32!CreateCompatibleDC` at `0x180172f5d`
- `GDI32!CreateCompatibleDC` at `0x180173077`
- `GDI32!CreateCompatibleDC` at `0x180172f5d`
- `GDI32!CreateCompatibleDC` at `0x180173077`
- `GDI32!GetObjectW` at `0x180172eda`
- `GDI32!GetObjectW` at `0x180172f7a`
- `GDI32!GetObjectW` at `0x1801731d8`
- `GDI32!GetObjectW` at `0x180172eda`
- `GDI32!GetObjectW` at `0x180172f7a`
- `GDI32!GetObjectW` at `0x1801731d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMFCToolBarImages::Load(
        CMFCToolBarImages *this,
        const wchar_t *lpszBmpFileName,
        DWORD dwMaxFileSize)
{
  HBITMAP__ **p_m_hbmImageWell; // rsi
  wchar_t *v7; // rax
  wchar_t *m_pszData; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  int v11; // eax
  HANDLE FileW; // rax
  void *v13; // rdi
  DWORD FileSize; // ebx
  int m_bMapTo3DColors; // edi
  AFX_MODULE_STATE *ModuleState; // rax
  HBITMAP__ *ImageW; // rax
  wchar_t *v18; // rdx
  int bmBitsPixel; // ecx
  HDC CompatibleDC; // rax
  HGDIOBJ v22; // rbx
  int v23; // edi
  int v24; // r12d
  HBITMAP CompatibleBitmap; // r15
  HDC v26; // rax
  int v27; // eax
  HDC v28; // rax
  HDC v29; // rax
  int v30; // r15d
  int v31; // eax
  int v32; // edi
  COLORREF Pixel; // eax
  COLORREF v34; // r13d
  COLORREF v35; // eax
  HBITMAP__ **p_m_hbmImageLight; // rbx
  HBITMAP__ **p_m_hbmImageShadow; // r14
  wchar_t *v38; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strPath; // [rsp+50h] [rbp-B0h] BYREF
  CDC v40; // [rsp+58h] [rbp-A8h] BYREF
  CDC v41; // [rsp+78h] [rbp-88h] BYREF
  HGDIOBJ h; // [rsp+98h] [rbp-68h]
  HBITMAP__ *v43; // [rsp+A0h] [rbp-60h]
  _BYTE pv[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v45; // [rsp+ACh] [rbp-54h]
  int cy; // [rsp+B0h] [rbp-50h]
  __int16 v47; // [rsp+BAh] [rbp-46h]
  tagBITMAP bmp; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t drive[4]; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t path_buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t ext[256]; // [rsp+300h] [rbp+200h] BYREF
  wchar_t fname[256]; // [rsp+500h] [rbp+400h] BYREF
  wchar_t dir[256]; // [rsp+700h] [rbp+600h] BYREF
  wchar_t lpszFilePath[264]; // [rsp+900h] [rbp+800h] BYREF

  if ( this->m_bIsTemporary )
    return 0;
  if ( !lpszBmpFileName || (p_m_hbmImageWell = &this->m_hbmImageWell, this == (CMFCToolBarImages *)-160LL) )
    AfxThrowInvalidArgException();
  if ( *p_m_hbmImageWell )
  {
    DeleteObject(*p_m_hbmImageWell);
    *p_m_hbmImageWell = 0;
  }
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strPath,
    lpszBmpFileName);
  if ( *((int *)strPath.m_pszData - 4) < 0
    || ((v7 = wcsstr(strPath.m_pszData, L"\\"), m_pszData = strPath.m_pszData, !v7)
     || (unsigned int)(v7 - strPath.m_pszData) == -1)
    && (*((int *)strPath.m_pszData - 4) < 0
     || ((v9 = wcsstr(strPath.m_pszData, L"/"), m_pszData = strPath.m_pszData, !v9)
      || (unsigned int)(v9 - strPath.m_pszData) == -1)
     && (*((int *)strPath.m_pszData - 4) < 0
      || (v10 = wcsstr(strPath.m_pszData, L":")) == 0
      || (m_pszData = strPath.m_pszData, (unsigned int)(v10 - strPath.m_pszData) == -1))) )
  {
    if ( GetModuleFileNameW(0, lpszFilePath, 0x104u) )
    {
      _wsplitpath_s(lpszFilePath, drive, 3u, dir, 0x100u, 0, 0, 0, 0);
      _wsplitpath_s(lpszBmpFileName, 0, 0, 0, 0, fname, 0x100u, ext, 0x100u);
      _wmakepath_s(path_buffer, 0x104u, drive, dir, fname, ext);
      v11 = wcslen(path_buffer);
      ATL::CSimpleStringT<wchar_t,1>::SetString(&strPath, path_buffer, v11);
    }
    m_pszData = strPath.m_pszData;
  }
  if ( dwMaxFileSize )
  {
    FileW = CreateFileW(lpszBmpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
    v13 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileSize = GetFileSize(FileW, 0);
      CloseHandle(v13);
      if ( FileSize > dwMaxFileSize )
        goto LABEL_23;
    }
    m_pszData = strPath.m_pszData;
  }
  m_bMapTo3DColors = this->m_bMapTo3DColors;
  ModuleState = AfxGetModuleState();
  ImageW = (HBITMAP__ *)LoadImageW(
                          ModuleState->m_hCurrentInstanceHandle,
                          m_pszData,
                          0,
                          0,
                          0,
                          m_bMapTo3DColors != 0 ? 12304 : 8208);
  *p_m_hbmImageWell = ImageW;
  if ( !ImageW )
  {
LABEL_23:
    v18 = strPath.m_pszData - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)strPath.m_pszData - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
    return 0;
  }
  if ( !GetObjectW(ImageW, 32, &bmp) )
  {
    DeleteObject(*p_m_hbmImageWell);
    *p_m_hbmImageWell = 0;
    goto LABEL_23;
  }
  this->m_bUserImagesList = 1;
  ATL::CSimpleStringT<wchar_t,1>::operator=(&this->m_strUDLPath, (const ATL::CSimpleStringT<wchar_t,0> *)&strPath);
  if ( (GetFileAttributesW(strPath.m_pszData) & 1) != 0 )
    this->m_bReadOnly = 1;
  bmBitsPixel = bmp.bmBitsPixel;
  this->m_nBitsPerPixel = bmp.bmBitsPixel;
  if ( (unsigned int)(bmBitsPixel - 9) <= 0x16 && *p_m_hbmImageWell )
  {
    v40.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&v40.m_hDC, 0, 20);
    CompatibleDC = CreateCompatibleDC(0);
    CDC::Attach(&v40, CompatibleDC);
    if ( !GetObjectW(*p_m_hbmImageWell, 32, pv)
      || !*p_m_hbmImageWell
      || (v22 = SelectObject(v40.m_hDC, *p_m_hbmImageWell)) == 0 )
    {
      v40.__vftable = (CDC_vtbl *)CDC::`vftable';
      if ( v40.m_hDC )
        goto LABEL_41;
      goto LABEL_42;
    }
    v23 = v45;
    *(_DWORD *)drive = v45;
    v24 = cy;
    CompatibleBitmap = CreateCompatibleBitmap(v40.m_hDC, v45, cy);
    v43 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      v41.__vftable = (CDC_vtbl *)CDC::`vftable';
      memset(&v41.m_hDC, 0, 20);
      v28 = CreateCompatibleDC(v40.m_hDC);
      CDC::Attach(&v41, v28);
      h = SelectObject(v41.m_hDC, CompatibleBitmap);
      if ( !h )
      {
        SelectObject(v40.m_hDC, v22);
        DeleteObject(CompatibleBitmap);
        v41.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( v41.m_hDC )
        {
          v29 = CDC::Detach(&v41);
          DeleteDC(v29);
        }
        v40.__vftable = (CDC_vtbl *)CDC::`vftable';
LABEL_40:
        if ( v40.m_hDC )
        {
LABEL_41:
          v26 = CDC::Detach(&v40);
          DeleteDC(v26);
        }
LABEL_42:
        LOWORD(bmBitsPixel) = bmp.bmBitsPixel;
        goto LABEL_43;
      }
      BitBlt(v41.m_hDC, 0, 0, v23, v24, v40.m_hDC, 0, 0, 0xCC0020u);
      v30 = 0;
      if ( v23 > 0 )
      {
        v31 = *(_DWORD *)drive;
        do
        {
          v32 = 0;
          if ( v24 > 0 )
          {
            do
            {
              Pixel = GetPixel(v41.m_hDC, v30, v32);
              v34 = Pixel;
              if ( v47 != 24 || CMFCToolBarImages::m_bDisableTrueColorAlpha )
                v35 = CMFCToolBarImages::MapToSysColor(Pixel, 0);
              else
                v35 = CMFCToolBarImages::MapToSysColorAlpha(Pixel);
              if ( v34 != v35 )
                SetPixel(v41.m_hDC, v30, v32, v35);
              ++v32;
            }
            while ( v32 < v24 );
            v31 = *(_DWORD *)drive;
          }
          ++v30;
        }
        while ( v30 < v31 );
      }
      SelectObject(v41.m_hDC, h);
      SelectObject(v40.m_hDC, v22);
      DeleteObject(*p_m_hbmImageWell);
      *p_m_hbmImageWell = v43;
      CDC::~CDC(&v41);
    }
    else
    {
      SelectObject(v40.m_hDC, v22);
    }
    v40.__vftable = (CDC_vtbl *)CDC::`vftable';
    goto LABEL_40;
  }
LABEL_43:
  if ( (unsigned __int16)bmBitsPixel >= 0x20u )
    CMFCToolBarImages::PreMultiplyAlpha(*p_m_hbmImageWell, this->m_bAutoCheckPremlt);
  if ( *p_m_hbmImageWell && GetObjectW(*p_m_hbmImageWell, 32, pv) )
    v27 = v45 / this->m_sizeImage.cx;
  else
    v27 = 0;
  this->m_iCount = v27;
  p_m_hbmImageLight = &this->m_hbmImageLight;
  if ( this == (CMFCToolBarImages *)-168LL )
    goto LABEL_76;
  if ( *p_m_hbmImageLight )
    DeleteObject(*p_m_hbmImageLight);
  *p_m_hbmImageLight = 0;
  p_m_hbmImageShadow = &this->m_hbmImageShadow;
  if ( !p_m_hbmImageShadow )
LABEL_76:
    AfxThrowInvalidArgException();
  if ( *p_m_hbmImageShadow )
    DeleteObject(*p_m_hbmImageShadow);
  *p_m_hbmImageShadow = 0;
  v38 = strPath.m_pszData - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)strPath.m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v38 + 8LL))(*(_QWORD *)v38);
  return 1;
}

```

## disassembly

```asm
0x180172bf0  mov     [rsp-8+arg_10], rbx
0x180172bf5  push    rbp
0x180172bf6  push    rsi
0x180172bf7  push    rdi
0x180172bf8  push    r12
0x180172bfa  push    r13
0x180172bfc  push    r14
0x180172bfe  push    r15
0x180172c00  lea     rbp, [rsp-0A20h]
0x180172c08  sub     rsp, 0B20h
0x180172c0f  mov     rax, cs:__security_cookie
0x180172c16  xor     rax, rsp
0x180172c19  mov     [rbp+0A50h+var_40], rax
0x180172c20  mov     r15d, dwMaxFileSize
0x180172c23  mov     rdi, lpszBmpFileName
0x180172c26  mov     r14, this
0x180172c29  xor     r13d, r13d
0x180172c2c  cmp     [this+2Ch], r13d
0x180172c30  jnz     loc_180172E9E
0x180172c36  test    lpszBmpFileName, lpszBmpFileName
0x180172c39  jz      loc_18017325F
0x180172c3f  lea     rsi, [this+0A0h]
0x180172c46  test    rsi, rsi
0x180172c49  jz      loc_18017325F
0x180172c4f  mov     this, [rsi]; ho
0x180172c52  test    this, this
0x180172c55  jz      short loc_180172C60
0x180172c57  call    cs:__imp_DeleteObject
0x180172c5d  mov     [rsi], r13
0x180172c60  mov     lpszBmpFileName, rdi; pszSrc
0x180172c63  lea     this, [rsp+0B50h+strPath]; this
0x180172c68  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180172c6d  nop
0x180172c6e  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172c73  cmp     [rbx-10h], r13d
0x180172c77  jl      loc_180172D04
0x180172c7d  lea     lpszBmpFileName, szDelim; "\\"
0x180172c84  mov     this, rbx; Str
0x180172c87  call    cs:__imp_wcsstr
0x180172c8d  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172c92  test    rax, rax
0x180172c95  jz      short loc_180172CA6
0x180172c97  sub     rax, rbx
0x180172c9a  sar     rax, 1
0x180172c9d  cmp     eax, 0FFFFFFFFh
0x180172ca0  jnz     loc_180172DE8
0x180172ca6  cmp     [rbx-10h], r13d
0x180172caa  jl      short loc_180172D04
0x180172cac  lea     lpszBmpFileName, asc_18034F388; "/"
0x180172cb3  mov     this, rbx; Str
0x180172cb6  call    cs:__imp_wcsstr
0x180172cbc  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172cc1  test    rax, rax
0x180172cc4  jz      short loc_180172CD5
0x180172cc6  sub     rax, rbx
0x180172cc9  sar     rax, 1
0x180172ccc  cmp     eax, 0FFFFFFFFh
0x180172ccf  jnz     loc_180172DE8
0x180172cd5  cmp     [rbx-10h], r13d
0x180172cd9  jl      short loc_180172D04
0x180172cdb  lea     lpszBmpFileName, asc_18034F38C; ":"
0x180172ce2  mov     this, rbx; Str
0x180172ce5  call    cs:__imp_wcsstr
0x180172ceb  test    rax, rax
0x180172cee  jz      short loc_180172D04
0x180172cf0  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172cf5  sub     rax, rbx
0x180172cf8  sar     rax, 1
0x180172cfb  cmp     eax, 0FFFFFFFFh
0x180172cfe  jnz     loc_180172DE8
0x180172d04  mov     r12d, 104h
0x180172d0a  mov     dwMaxFileSize, r12d; nSize
0x180172d0d  lea     lpszBmpFileName, [rbp+0A50h+lpszFilePath]; lpFilename
0x180172d14  xor     ecx, ecx; hModule
0x180172d16  call    cs:__imp_GetModuleFileNameW
0x180172d1c  test    eax, eax
0x180172d1e  jz      loc_180172DE3
0x180172d24  mov     [rsp+0B50h+ExtCount], r13; ExtCount
0x180172d29  mov     [rsp+0B50h+Ext], r13; Ext
0x180172d2e  mov     [rsp+0B50h+FilenameCount], r13; FilenameCount
0x180172d33  mov     [rsp+0B50h+Filename], r13; Filename
0x180172d38  lea     ebx, [r12-4]
0x180172d3d  mov     [rsp+0B50h+DirCount], rbx; DirCount
0x180172d42  lea     r9, [rbp+0A50h+dir]; Dir
0x180172d49  mov     dwMaxFileSize, 3; DriveCount
0x180172d4f  lea     lpszBmpFileName, [rbp+0A50h+drive]; Drive
0x180172d53  lea     this, [rbp+0A50h+lpszFilePath]; FullPath
0x180172d5a  call    cs:__imp__wsplitpath_s
0x180172d60  mov     [rsp+0B50h+ExtCount], rbx; ExtCount
0x180172d65  lea     rax, [rbp+0A50h+ext]
0x180172d6c  mov     [rsp+0B50h+Ext], rax; Ext
0x180172d71  mov     [rsp+0B50h+FilenameCount], rbx; FilenameCount
0x180172d76  lea     rax, [rbp+0A50h+fname]
0x180172d7d  mov     [rsp+0B50h+Filename], rax; Filename
0x180172d82  mov     [rsp+0B50h+DirCount], r13; DirCount
0x180172d87  xor     r9d, r9d; Dir
0x180172d8a  xor     dwMaxFileSize, dwMaxFileSize; DriveCount
0x180172d8d  xor     edx, edx; Drive
0x180172d8f  mov     this, rdi; FullPath
0x180172d92  call    cs:__imp__wsplitpath_s
0x180172d98  lea     rax, [rbp+0A50h+ext]
0x180172d9f  mov     [rsp+0B50h+Filename], rax; Ext
0x180172da4  lea     rax, [rbp+0A50h+fname]
0x180172dab  mov     [rsp+0B50h+DirCount], rax; Filename
0x180172db0  lea     r9, [rbp+0A50h+dir]; Dir
0x180172db7  lea     r8, [rbp+0A50h+drive]; Drive
0x180172dbb  mov     edx, r12d; BufferCount
0x180172dbe  lea     this, [rbp+0A50h+path_buffer]; Buffer
0x180172dc2  call    cs:__imp__wmakepath_s
0x180172dc8  lea     this, [rbp+0A50h+path_buffer]; String
0x180172dcc  call    cs:__imp_wcslen
0x180172dd2  mov     dwMaxFileSize, eax; nLength
0x180172dd5  lea     lpszBmpFileName, [rbp+0A50h+path_buffer]; pszSrc
0x180172dd9  lea     this, [rsp+0B50h+strPath]; this
0x180172dde  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x180172de3  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172de8  test    r15d, r15d
0x180172deb  jz      short loc_180172E3D
0x180172ded  mov     [rsp+0B50h+FilenameCount], r13; hTemplateFile
0x180172df2  mov     dword ptr [rsp+0B50h+Filename], r13d; dwFlagsAndAttributes
0x180172df7  mov     dword ptr [rsp+0B50h+DirCount], 3; dwCreationDisposition
0x180172dff  xor     r9d, r9d; lpSecurityAttributes
0x180172e02  mov     edx, 80000000h; dwDesiredAccess
0x180172e07  lea     dwMaxFileSize, [r9+1]; dwShareMode
0x180172e0b  mov     this, rdi; lpFileName
0x180172e0e  call    cs:__imp_CreateFileW
0x180172e14  mov     rdi, rax
0x180172e17  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180172e1b  jz      short loc_180172E38
0x180172e1d  xor     edx, edx; lpFileSizeHigh
0x180172e1f  mov     this, rax; hFile
0x180172e22  call    cs:__imp_GetFileSize
0x180172e28  mov     ebx, eax
0x180172e2a  mov     this, rdi; hObject
0x180172e2d  call    cs:__imp_CloseHandle
0x180172e33  cmp     ebx, r15d
0x180172e36  ja      short loc_180172E78
0x180172e38  mov     rbx, [rsp+0B50h+strPath.m_pszData]
0x180172e3d  mov     edi, [r14+38h]
0x180172e41  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180172e46  mov     this, [rax+10h]; hInst
0x180172e4a  neg     edi
0x180172e4c  sbb     eax, eax
0x180172e4e  and     eax, 1000h
0x180172e53  add     eax, 2010h
0x180172e58  mov     dword ptr [rsp+0B50h+Filename], eax; fuLoad
0x180172e5c  mov     dword ptr [rsp+0B50h+DirCount], r13d; cy
0x180172e61  xor     r9d, r9d; cx
0x180172e64  xor     dwMaxFileSize, dwMaxFileSize; type
0x180172e67  mov     lpszBmpFileName, rbx; name
0x180172e6a  call    cs:__imp_LoadImageW
0x180172e70  mov     [rsi], rax
0x180172e73  test    rax, rax
0x180172e76  jnz     short loc_180172ECA
0x180172e78  mov     lpszBmpFileName, [rsp+0B50h+strPath.m_pszData]
0x180172e7d  add     lpszBmpFileName, 0FFFFFFFFFFFFFFE8h
0x180172e81  or      eax, 0FFFFFFFFh
0x180172e84  lock xadd [lpszBmpFileName+10h], eax
0x180172e89  sub     eax, 1
0x180172e8c  jg      short loc_180172E9E
0x180172e8e  mov     this, [lpszBmpFileName]
0x180172e91  mov     rax, [this]
0x180172e94  mov     rax, [rax+8]
0x180172e98  call    cs:__guard_dispatch_icall_fptr
0x180172e9e  xor     eax, eax
0x180172ea0  mov     this, [rbp+0A50h+var_40]
0x180172ea7  xor     this, rsp; StackCookie
0x180172eaa  call    __security_check_cookie
0x180172eaf  mov     rbx, [rsp+0B50h+arg_10]
0x180172eb7  add     rsp, 0B20h
0x180172ebe  pop     r15
0x180172ec0  pop     r14
0x180172ec2  pop     r13
0x180172ec4  pop     r12
0x180172ec6  pop     rdi
0x180172ec7  pop     rsi
0x180172ec8  pop     rbp
0x180172ec9  retn
0x180172eca  lea     r8, [rbp+0A50h+bmp]; pv
0x180172ece  mov     r15d, 20h ; ' '
0x180172ed4  mov     edx, r15d; c
0x180172ed7  mov     this, rax; h
0x180172eda  call    cs:__imp_GetObjectW
0x180172ee0  test    eax, eax
0x180172ee2  jnz     short loc_180172EF2
0x180172ee4  mov     this, [rsi]; ho
0x180172ee7  call    cs:__imp_DeleteObject
0x180172eed  mov     [rsi], r13
0x180172ef0  jmp     short loc_180172E78
0x180172ef2  mov     dword ptr [r14+1Ch], 1
0x180172efa  lea     this, [r14+0B8h]; this
0x180172f01  lea     lpszBmpFileName, [rsp+0B50h+strPath]; strSrc
0x180172f06  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x180172f0b  mov     this, [rsp+0B50h+strPath.m_pszData]; lpFileName
0x180172f10  call    cs:__imp_GetFileAttributesW
0x180172f16  test    al, 1
0x180172f18  jz      short loc_180172F22
0x180172f1a  mov     dword ptr [r14+28h], 1
0x180172f22  movzx   ecx, [rbp+0A50h+bmp.bmBitsPixel]
0x180172f26  mov     eax, ecx
0x180172f28  mov     [r14+0Ch], ecx
0x180172f2c  add     eax, 0FFFFFFF7h
0x180172f2f  cmp     eax, 16h
0x180172f32  ja      loc_180173034
0x180172f38  cmp     [rsi], r13
0x180172f3b  jz      loc_180173034
0x180172f41  lea     rdi, ??_7CDC@@6B@; const CDC::`vftable'
0x180172f48  mov     [rsp+0B50h+var_AF8.__vftable], rdi
0x180172f4d  xorps   xmm0, xmm0
0x180172f50  movdqu  xmmword ptr [rsp+0B50h+var_AF8.m_hDC], xmm0
0x180172f56  mov     [rsp+0B50h+var_AF8.m_bPrinting], r13d
0x180172f5b  xor     ecx, ecx; hdc
0x180172f5d  call    cs:__imp_CreateCompatibleDC
0x180172f63  mov     lpszBmpFileName, rax; hDC
0x180172f66  lea     this, [rsp+0B50h+var_AF8]; this
0x180172f6b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180172f70  lea     r8, [rbp+0A50h+pv]; pv
0x180172f74  mov     edx, r15d; c
0x180172f77  mov     this, [rsi]; h
0x180172f7a  call    cs:__imp_GetObjectW
0x180172f80  test    eax, eax
0x180172f82  jnz     short loc_180172FAC
0x180172f84  mov     [rsp+0B50h+var_AF8.__vftable], rdi
0x180172f89  cmp     [rsp+0B50h+var_AF8.m_hDC], r13
0x180172f8e  jz      loc_180173030
0x180172f94  lea     this, [rsp+0B50h+var_AF8]; this
0x180172f99  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180172f9e  mov     this, rax; hdc
0x180172fa1  call    cs:__imp_DeleteDC
0x180172fa7  jmp     loc_180173030
0x180172fac  mov     lpszBmpFileName, [rsi]; h
0x180172faf  test    lpszBmpFileName, lpszBmpFileName
0x180172fb2  jz      loc_1801731CC
0x180172fb8  mov     this, [rsp+0B50h+var_AF8.m_hDC]; hdc
0x180172fbd  call    cs:__imp_SelectObject
0x180172fc3  mov     rbx, rax
0x180172fc6  test    rax, rax
0x180172fc9  jz      loc_1801731CC
0x180172fcf  mov     edi, [rbp+0A50h+var_AA4]
0x180172fd2  mov     dword ptr [rbp+0A50h+drive], edi
0x180172fd5  mov     r12d, [rbp+0A50h+cy]
0x180172fd9  mov     dwMaxFileSize, r12d; cy
0x180172fdc  mov     edx, edi; cx
0x180172fde  mov     this, [rsp+0B50h+var_AF8.m_hDC]; hdc
0x180172fe3  call    cs:__imp_CreateCompatibleBitmap
0x180172fe9  mov     r15, rax
0x180172fec  mov     [rbp+0A50h+var_AB0], rax
0x180172ff0  test    rax, rax
0x180172ff3  jnz     short loc_18017305A
0x180172ff5  mov     lpszBmpFileName, rbx; h
0x180172ff8  mov     this, [rsp+0B50h+var_AF8.m_hDC]; hdc
0x180172ffd  call    cs:__imp_SelectObject
0x180173003  nop
0x180173004  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18017300b  mov     [rsp+0B50h+var_AF8.__vftable], rax
0x180173010  cmp     [rsp+0B50h+var_AF8.m_hDC], r13
0x180173015  jz      short loc_18017302A
0x180173017  lea     this, [rsp+0B50h+var_AF8]; this
0x18017301c  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180173021  mov     this, rax; hdc
0x180173024  call    cs:__imp_DeleteDC
0x18017302a  mov     r15d, 20h ; ' '
0x180173030  movzx   ecx, [rbp+0A50h+bmp.bmBitsPixel]
0x180173034  cmp     cx, r15w
0x180173038  jb      short loc_180173046
0x18017303a  mov     edx, [r14+40h]; bAutoCheckPremlt
0x18017303e  mov     this, [rsi]; hbmp
0x180173041  call    ?PreMultiplyAlpha@CMFCToolBarImages@@SAHPEAUHBITMAP__@@H@Z; CMFCToolBarImages::PreMultiplyAlpha(HBITMAP__ *,int)
0x180173046  mov     this, [rsi]; h
0x180173049  test    this, this
0x18017304c  jnz     loc_1801731D1
0x180173052  mov     eax, r13d
0x180173055  jmp     loc_1801731EE
0x18017305a  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180173061  mov     [rsp+0B50h+var_AD8.__vftable], rax
0x180173066  xorps   xmm0, xmm0
0x180173069  movdqu  xmmword ptr [rbp+0A50h+var_AD8.m_hDC], xmm0
0x18017306e  mov     [rbp+0A50h+var_AD8.m_bPrinting], r13d
0x180173072  mov     this, [rsp+0B50h+var_AF8.m_hDC]; hdc
0x180173077  call    cs:__imp_CreateCompatibleDC
0x18017307d  mov     lpszBmpFileName, rax; hDC
0x180173080  lea     this, [rsp+0B50h+var_AD8]; this
0x180173085  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017308a  mov     lpszBmpFileName, r15; h
0x18017308d  mov     this, [rbp+0A50h+var_AD8.m_hDC]; hdc
0x180173091  call    cs:__imp_SelectObject
0x180173097  mov     [rbp+0A50h+h], rax
0x18017309b  test    rax, rax
0x18017309e  jnz     short loc_1801730E8
0x1801730a0  mov     lpszBmpFileName, rbx; h
0x1801730a3  mov     this, [rsp+0B50h+var_AF8.m_hDC]; hdc
0x1801730a8  call    cs:__imp_SelectObject
0x1801730ae  mov     this, r15; ho
0x1801730b1  call    cs:__imp_DeleteObject
0x1801730b7  nop
0x1801730b8  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x1801730bf  mov     [rsp+0B50h+var_AD8.__vftable], rbx
0x1801730c4  cmp     [rbp+0A50h+var_AD8.m_hDC], r13
0x1801730c8  jz      short loc_1801730DE
0x1801730ca  lea     this, [rsp+0B50h+var_AD8]; this
  ... truncated ...
```
