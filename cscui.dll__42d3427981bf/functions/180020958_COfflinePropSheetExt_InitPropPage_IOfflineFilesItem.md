# COfflinePropSheetExt::_InitPropPage(IOfflineFilesItem *)

- ea: `0x180020958`
- end: `0x180020fb2`
- name: `?_InitPropPage@COfflinePropSheetExt@@AEAAXPEAUIOfflineFilesItem@@@Z`
- size: `1626`
- prototype: `void __fastcall(COfflinePropSheetExt *__hidden this, struct IOfflineFilesItem *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180021160`
- `0x18002151c`

## callees

- `0x180002810`
- `0x180003d60`
- `0x180005b70`
- `0x18000735c`
- `0x180020734`
- `0x180020958`
- `0x180021398`
- `0x18002186c`
- `0x1800329ec`
- `0x180032a30`
- `0x180032b44`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathCompactPathW` at `0x180020b81`
- `SHLWAPI!PathCompactPathW` at `0x180020b81`
- `USER32!EnableWindow` at `0x180020f27`
- `USER32!EnableWindow` at `0x180020f41`
- `USER32!EnableWindow` at `0x180020f6c`
- `USER32!EnableWindow` at `0x180020f27`
- `USER32!EnableWindow` at `0x180020f41`
- `USER32!EnableWindow` at `0x180020f6c`
- `USER32!CheckDlgButton` at `0x180020ef1`
- `USER32!CheckDlgButton` at `0x180020ef1`
- `USER32!LoadImageW` at `0x180020d59`
- `USER32!LoadImageW` at `0x180020d59`
- `USER32!ReleaseDC` at `0x180020b9d`
- `USER32!ReleaseDC` at `0x180020b9d`
- `USER32!SetWindowTextW` at `0x180020b91`
- `USER32!SetWindowTextW` at `0x180020b91`
- `USER32!GetWindowDC` at `0x180020b38`
- `USER32!GetWindowDC` at `0x180020b38`
- `USER32!GetClientRect` at `0x180020b2b`
- `USER32!GetClientRect` at `0x180020b2b`
- `USER32!GetDlgItem` at `0x180020b12`
- `USER32!GetDlgItem` at `0x180020d77`
- `USER32!GetDlgItem` at `0x180020f1a`
- `USER32!GetDlgItem` at `0x180020f34`
- `USER32!GetDlgItem` at `0x180020f61`
- `USER32!GetDlgItem` at `0x180020b12`
- `USER32!GetDlgItem` at `0x180020d77`
- `USER32!GetDlgItem` at `0x180020f1a`
- `USER32!GetDlgItem` at `0x180020f34`
- `USER32!GetDlgItem` at `0x180020f61`
- `USER32!SetDlgItemTextW` at `0x180020a7a`
- `USER32!SetDlgItemTextW` at `0x180020a7a`
- `USER32!DestroyIcon` at `0x180020d1a`
- `USER32!DestroyIcon` at `0x180020d1a`
- `USER32!SendMessageW` at `0x180020d8b`
- `USER32!SendMessageW` at `0x180020d8b`

## pseudocode

```c
void __fastcall COfflinePropSheetExt::_InitPropPage(COfflinePropSheetExt *this, struct IOfflineFilesItem *a2)
{
  char *v4; // r13
  char *v5; // r14
  char *v6; // r12
  int *v7; // r15
  const unsigned __int16 *ConstBuffer; // rax
  unsigned __int16 *v9; // rcx
  unsigned __int16 *Extension; // rax
  unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // r10
  const WCHAR *v13; // rax
  const WCHAR *FileName; // rax
  const unsigned __int16 *v15; // rax
  BOOL v16; // edi
  HWND DlgItem; // r14
  HDC WindowDC; // r15
  const unsigned __int16 *v19; // rax
  struct IOfflineFilesItemVtbl *lpVtbl; // rax
  struct IOfflineFilesItemVtbl *v21; // rax
  struct IOfflineFilesItemVtbl *v22; // rax
  struct IOfflineFilesItemVtbl *v23; // rax
  HICON v24; // rcx
  HANDLE ImageW; // rax
  WPARAM v26; // r14
  HWND v27; // rax
  unsigned __int64 v28; // rcx
  int v29; // r14d
  unsigned int v30; // r9d
  int v31; // eax
  int v32; // eax
  COfflinePropSheetExt *v33; // rcx
  int v34; // r8d
  HWND v35; // rax
  HWND v36; // rax
  HWND v37; // rax
  BOOL bEnable; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v44[260]; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+278h] [rbp+178h]
  unsigned __int16 *v46; // [rsp+280h] [rbp+180h]
  unsigned __int16 *v47; // [rsp+288h] [rbp+188h]
  unsigned __int16 *v48; // [rsp+290h] [rbp+190h]
  __int64 v49; // [rsp+298h] [rbp+198h]
  __int64 v50; // [rsp+2A0h] [rbp+1A0h]
  _WORD v51[260]; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v52; // [rsp+4B8h] [rbp+3B8h]
  _WORD *v53; // [rsp+4C0h] [rbp+3C0h]
  _WORD *v54; // [rsp+4C8h] [rbp+3C8h]
  _WORD *v55; // [rsp+4D0h] [rbp+3D0h]
  __int64 v56; // [rsp+4D8h] [rbp+3D8h]
  __int64 v57; // [rsp+4E0h] [rbp+3E0h]
  WCHAR pszPath[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v45 = 34078720;
  v47 = v44;
  v44[0] = 0;
  v48 = v44;
  v4 = (char *)this + 704;
  *((_DWORD *)this + 176) = 0;
  *((_DWORD *)this + 177) = 0;
  v5 = (char *)this + 712;
  *((_DWORD *)this + 178) = 0;
  v6 = (char *)this + 724;
  *((_DWORD *)this + 181) = 0;
  v7 = (int *)((char *)this + 728);
  *((_DWORD *)this + 182) = 0;
  *((_DWORD *)this + 180) = 0;
  v49 = 520;
  v50 = 520;
  v46 = v44;
  ConstBuffer = CPath::_GetConstBuffer((COfflinePropSheetExt *)((char *)this + 104));
  if ( (int)CPath::Copy((CPath *)v44, ConstBuffer) >= 0 )
  {
    v9 = v46;
    if ( v47 != v48 )
      v9 = v47;
    Extension = CscPath_FindExtension(v9);
    if ( v11 != v48 )
      v12 = v11;
    if ( Extension != v12 )
      *Extension = 0;
    v13 = CPath::_GetConstBuffer((CPath *)v44);
    FileName = CscPath_FindFileName(v13);
    SetDlgItemTextW(*((HWND *)this + 5), 2207, FileName);
  }
  v52 = 34078720;
  v56 = 520;
  v54 = v51;
  v55 = v51;
  v53 = v51;
  v57 = 520;
  v51[0] = 0;
  v15 = CPath::_GetConstBuffer((COfflinePropSheetExt *)((char *)this + 104));
  v16 = 1;
  if ( (int)CPath::Copy((CPath *)v51, v15) >= 0 && (int)CPath::RemoveFileSpecAndBackslash((CPath *)v51) >= 0 )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 5), 2209);
    Rect = 0;
    if ( GetClientRect(DlgItem, &Rect) )
    {
      WindowDC = GetWindowDC(DlgItem);
      if ( WindowDC )
      {
        v19 = CPath::_GetConstBuffer((CPath *)v51);
        if ( (int)StringCchCopyW(pszPath, 0x104u, v19) >= 0 )
        {
          PathCompactPathW(WindowDC, pszPath, Rect.right - Rect.left + 1);
          SetWindowTextW(DlgItem, pszPath);
        }
        ReleaseDC(DlgItem, WindowDC);
      }
      v7 = (int *)((char *)this + 728);
    }
    v5 = (char *)this + 712;
  }
  if ( a2 )
  {
    *((_DWORD *)this + 177) = 1;
    lpVtbl = a2->lpVtbl;
    v39 = 0;
    if ( ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_a96e6fa4_e0d1_4c29_960b_ee508fe68c72,
           &v39) >= 0 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 24LL))(v39, v6);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v21 = a2->lpVtbl;
    v40 = 0;
    if ( ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v21->QueryInterface)(
           a2,
           &GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00,
           &v40) >= 0 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v40 + 64LL))(v40, v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v22 = a2->lpVtbl;
    v41 = 0;
    if ( ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v22->QueryInterface)(
           a2,
           &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b,
           &v41) >= 0 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v41 + 24LL))(v41, v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v23 = a2->lpVtbl;
    v42 = 0;
    if ( ((__int64 (__fastcall *)(struct IOfflineFilesItem *, GUID *, __int64 *))v23->QueryInterface)(
           a2,
           &GUID_efb23a09_a867_4be8_83a6_86969a7d0856,
           &v42) >= 0 )
    {
      bEnable = 0;
      if ( (*(int (__fastcall **)(__int64, BOOL *, char *))(*(_QWORD *)v42 + 24LL))(v42, &bEnable, (char *)this + 744) >= 0
        && bEnable )
      {
        *((_DWORD *)this + 180) = 1;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
  }
  v24 = (HICON)*((_QWORD *)this + 86);
  if ( v24 )
  {
    DestroyIcon(v24);
    *((_QWORD *)this + 86) = 0;
  }
  ImageW = LoadImageW(g_hInstance, (LPCWSTR)((*((_DWORD *)this + 180) != 0) + 1356LL), 1u, 48, 48, 0x20u);
  *((_QWORD *)this + 86) = ImageW;
  v26 = (WPARAM)ImageW;
  if ( ImageW )
  {
    v27 = GetDlgItem(*((HWND *)this + 5), 2206);
    SendMessageW(v27, 0x170u, v26, 0);
  }
  v28 = *((unsigned int *)this + 174);
  v29 = 1;
  v30 = (*((_DWORD *)this + 174) != 0) + 4382;
  if ( *((_DWORD *)this + 180) )
  {
    v31 = *((_DWORD *)this + 186);
    v30 = ((_DWORD)v28 != 0) + 4384;
    switch ( v31 )
    {
      case 2:
        v29 = 0;
        v30 = ((_DWORD)v28 != 0) + 4386;
        break;
      case 4:
        v29 = 0;
        v30 = ((_DWORD)v28 != 0) + 4388;
        break;
      case 3:
        v30 = ((_DWORD)v28 != 0) + 4390;
        break;
      case 5:
        v30 = ((_DWORD)v28 != 0) + 4392;
        break;
      case 6:
        v30 = ((_DWORD)v28 != 0) + 4398;
        break;
    }
    if ( *((_DWORD *)this + 181) )
    {
      if ( v29 )
      {
        COfflinePropSheetExt::_QueryItemSyncConflictStatus(this, v7, 0);
        v32 = *((_DWORD *)this + 174);
        if ( *((_DWORD *)this + 182) )
          v30 = (v32 != 0) + 4396;
        else
          v30 = (v32 != 0) + 4394;
      }
      else
      {
        v28 = (unsigned int)-(int)v28;
        v30 = ((_DWORD)v28 != 0) + 4392;
      }
    }
  }
  COfflinePropSheetExt::_SetDlgItemTextResource((COfflinePropSheetExt *)v28, *((HWND *)this + 5), 0x899u, v30);
  COfflinePropSheetExt::_SetDlgItemTextResource(v33, *((HWND *)this + 5), 0x8A0u, (*((_DWORD *)this + 174) != 0) + 57);
  CheckDlgButton(*((HWND *)this + 5), 2202, *((_DWORD *)this + 178) != 0);
  v34 = *((_DWORD *)this + 178);
  bEnable = 0;
  COfflinePropSheetExt::_EnablePinCheckbox(this, a2, v34, &bEnable);
  v35 = GetDlgItem(*((HWND *)this + 5), 2202);
  EnableWindow(v35, bEnable);
  v36 = GetDlgItem(*((HWND *)this + 5), 2208);
  EnableWindow(v36, bEnable);
  if ( !*((_DWORD *)this + 177) || !v29 )
    v16 = 0;
  v37 = GetDlgItem(*((HWND *)this + 5), 2172);
  EnableWindow(v37, v16);
  CPath::~CPath((CPath *)v51);
  CPath::~CPath((CPath *)v44);
}

```

## disassembly

```asm
0x180020958  mov     [rsp-8+arg_10], rbx
0x18002095d  push    rbp
0x18002095e  push    rsi
0x18002095f  push    rdi
0x180020960  push    r12
0x180020962  push    r13
0x180020964  push    r14
0x180020966  push    r15
0x180020968  lea     rbp, [rsp-610h]
0x180020970  sub     rsp, 710h
0x180020977  mov     rax, cs:__security_cookie
0x18002097e  xor     rax, rsp
0x180020981  mov     [rbp+640h+var_40], rax
0x180020988  mov     rbx, rcx
0x18002098b  mov     [rbp+640h+var_4C8], 2080000h
0x180020995  xor     ecx, ecx
0x180020997  lea     rax, [rsp+740h+var_6D0]
0x18002099c  mov     [rbp+640h+var_4B8], rax
0x1800209a3  mov     rsi, rdx
0x1800209a6  lea     rax, [rsp+740h+var_6D0]
0x1800209ab  mov     [rsp+740h+var_6D0], cx
0x1800209b0  mov     [rbp+640h+var_4B0], rax
0x1800209b7  lea     r13, [rbx+2C0h]
0x1800209be  mov     [r13+0], ecx
0x1800209c2  lea     rax, [rsp+740h+var_6D0]
0x1800209c7  mov     [rbx+2C4h], ecx
0x1800209cd  lea     r14, [rbx+2C8h]
0x1800209d4  mov     [r14], ecx
0x1800209d7  lea     r12, [rbx+2D4h]
0x1800209de  mov     [r12], ecx
0x1800209e2  lea     r15, [rbx+2D8h]
0x1800209e9  mov     [r15], ecx
0x1800209ec  mov     edx, 208h
0x1800209f1  mov     [rbx+2D0h], ecx
0x1800209f7  lea     rcx, [rbx+68h]; this
0x1800209fb  mov     [rbp+640h+var_4A8], rdx
0x180020a02  mov     [rbp+640h+var_4A0], rdx
0x180020a09  mov     [rbp+640h+var_4C0], rax
0x180020a10  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180020a15  mov     rdx, rax; unsigned __int16 *
0x180020a18  lea     rcx, [rsp+740h+var_6D0]; this
0x180020a1d  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180020a22  test    eax, eax
0x180020a24  js      short loc_180020A80
0x180020a26  mov     r9, [rbp+640h+var_4B8]
0x180020a2d  mov     r10, [rbp+640h+var_4C0]
0x180020a34  cmp     r9, [rbp+640h+var_4B0]
0x180020a3b  mov     rcx, r10
0x180020a3e  cmovnz  rcx, r9; unsigned __int16 *
0x180020a42  call    ?CscPath_FindExtension@@YAPEAGPEBG@Z; CscPath_FindExtension(ushort const *)
0x180020a47  cmp     r9, [rbp+640h+var_4B0]
0x180020a4e  cmovnz  r10, r9
0x180020a52  cmp     rax, r10
0x180020a55  jz      short loc_180020A5C
0x180020a57  xor     ecx, ecx
0x180020a59  mov     [rax], cx
0x180020a5c  lea     rcx, [rsp+740h+var_6D0]; this
0x180020a61  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180020a66  mov     rcx, rax; SourceString
0x180020a69  call    ?CscPath_FindFileName@@YAPEBGPEBG@Z; CscPath_FindFileName(ushort const *)
0x180020a6e  mov     rcx, [rbx+28h]; hDlg
0x180020a72  mov     r8, rax; lpString
0x180020a75  mov     edx, 89Fh; nIDDlgItem
0x180020a7a  call    cs:__imp_SetDlgItemTextW
0x180020a80  mov     ecx, 208h
0x180020a85  mov     [rbp+640h+var_288], 2080000h
0x180020a8f  lea     rax, [rbp+640h+var_490]
0x180020a96  mov     [rbp+640h+var_268], rcx
0x180020a9d  mov     [rbp+640h+var_278], rax
0x180020aa4  lea     rax, [rbp+640h+var_490]
0x180020aab  mov     [rbp+640h+var_270], rax
0x180020ab2  lea     rax, [rbp+640h+var_490]
0x180020ab9  mov     [rbp+640h+var_280], rax
0x180020ac0  xor     eax, eax
0x180020ac2  mov     [rbp+640h+var_260], rcx
0x180020ac9  lea     rcx, [rbx+68h]; this
0x180020acd  mov     [rbp+640h+var_490], ax
0x180020ad4  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180020ad9  mov     rdx, rax; unsigned __int16 *
0x180020adc  lea     rcx, [rbp+640h+var_490]; this
0x180020ae3  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180020ae8  mov     edi, 1
0x180020aed  test    eax, eax
0x180020aef  js      loc_180020BB1
0x180020af5  lea     rcx, [rbp+640h+var_490]; this
0x180020afc  call    ?RemoveFileSpecAndBackslash@CPath@@QEAAJXZ; CPath::RemoveFileSpecAndBackslash(void)
0x180020b01  test    eax, eax
0x180020b03  js      loc_180020BB1
0x180020b09  mov     rcx, [rbx+28h]; hDlg
0x180020b0d  mov     edx, 8A1h; nIDDlgItem
0x180020b12  call    cs:__imp_GetDlgItem
0x180020b18  xorps   xmm0, xmm0
0x180020b1b  lea     rdx, [rsp+740h+Rect]; lpRect
0x180020b20  mov     rcx, rax; hWnd
0x180020b23  mov     r14, rax
0x180020b26  movups  xmmword ptr [rsp+740h+Rect.left], xmm0
0x180020b2b  call    cs:__imp_GetClientRect
0x180020b31  test    eax, eax
0x180020b33  jz      short loc_180020BAA
0x180020b35  mov     rcx, r14; hWnd
0x180020b38  call    cs:__imp_GetWindowDC
0x180020b3e  mov     r15, rax
0x180020b41  test    rax, rax
0x180020b44  jz      short loc_180020BA3
0x180020b46  lea     rcx, [rbp+640h+var_490]; this
0x180020b4d  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180020b52  mov     r8, rax; unsigned __int16 *
0x180020b55  lea     rcx, [rbp+640h+pszPath]; unsigned __int16 *
0x180020b5c  mov     edx, 104h; unsigned __int64
0x180020b61  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020b66  test    eax, eax
0x180020b68  js      short loc_180020B97
0x180020b6a  mov     r8d, [rsp+740h+Rect.right]
0x180020b6f  lea     rdx, [rbp+640h+pszPath]; pszPath
0x180020b76  sub     r8d, [rsp+740h+Rect.left]
0x180020b7b  mov     rcx, r15; hDC
0x180020b7e  add     r8d, edi; dx
0x180020b81  call    cs:__imp_PathCompactPathW
0x180020b87  lea     rdx, [rbp+640h+pszPath]; lpString
0x180020b8e  mov     rcx, r14; hWnd
0x180020b91  call    cs:__imp_SetWindowTextW
0x180020b97  mov     rdx, r15; hDC
0x180020b9a  mov     rcx, r14; hWnd
0x180020b9d  call    cs:__imp_ReleaseDC
0x180020ba3  lea     r15, [rbx+2D8h]
0x180020baa  lea     r14, [rbx+2C8h]
0x180020bb1  test    rsi, rsi
0x180020bb4  jz      loc_180020D0B
0x180020bba  mov     [rbx+2C4h], edi
0x180020bc0  lea     r8, [rsp+740h+var_708]
0x180020bc5  mov     rax, [rsi]
0x180020bc8  lea     rdx, _GUID_a96e6fa4_e0d1_4c29_960b_ee508fe68c72
0x180020bcf  mov     rcx, rsi
0x180020bd2  mov     [rsp+740h+var_708], 0
0x180020bdb  mov     rax, [rax]
0x180020bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be3  test    eax, eax
0x180020be5  js      short loc_180020C0C
0x180020be7  mov     rcx, [rsp+740h+var_708]
0x180020bec  mov     rdx, r12
0x180020bef  mov     rax, [rcx]
0x180020bf2  mov     rax, [rax+18h]
0x180020bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bfb  mov     rcx, [rsp+740h+var_708]
0x180020c00  mov     rax, [rcx]
0x180020c03  mov     rax, [rax+10h]
0x180020c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c0c  mov     rax, [rsi]
0x180020c0f  lea     r8, [rsp+740h+var_700]
0x180020c14  lea     rdx, _GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00
0x180020c1b  mov     [rsp+740h+var_700], 0
0x180020c24  mov     rcx, rsi
0x180020c27  mov     rax, [rax]
0x180020c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c2f  test    eax, eax
0x180020c31  js      short loc_180020C58
0x180020c33  mov     rcx, [rsp+740h+var_700]
0x180020c38  mov     rdx, r13
0x180020c3b  mov     rax, [rcx]
0x180020c3e  mov     rax, [rax+40h]
0x180020c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c47  mov     rcx, [rsp+740h+var_700]
0x180020c4c  mov     rax, [rcx]
0x180020c4f  mov     rax, [rax+10h]
0x180020c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c58  mov     rax, [rsi]
0x180020c5b  lea     r8, [rsp+740h+var_6F8]
0x180020c60  xor     r13d, r13d
0x180020c63  lea     rdx, _GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b
0x180020c6a  mov     rcx, rsi
0x180020c6d  mov     [rsp+740h+var_6F8], r13
0x180020c72  mov     rax, [rax]
0x180020c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c7a  test    eax, eax
0x180020c7c  js      short loc_180020CA3
0x180020c7e  mov     rcx, [rsp+740h+var_6F8]
0x180020c83  mov     rdx, r14
0x180020c86  mov     rax, [rcx]
0x180020c89  mov     rax, [rax+18h]
0x180020c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c92  mov     rcx, [rsp+740h+var_6F8]
0x180020c97  mov     rax, [rcx]
0x180020c9a  mov     rax, [rax+10h]
0x180020c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ca3  mov     rax, [rsi]
0x180020ca6  lea     r8, [rsp+740h+var_6F0]
0x180020cab  lea     rdx, _GUID_efb23a09_a867_4be8_83a6_86969a7d0856
0x180020cb2  mov     [rsp+740h+var_6F0], r13
0x180020cb7  mov     rcx, rsi
0x180020cba  mov     rax, [rax]
0x180020cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cc2  test    eax, eax
0x180020cc4  js      short loc_180020D0E
0x180020cc6  mov     rcx, [rsp+740h+var_6F0]
0x180020ccb  lea     r8, [rbx+2E8h]
0x180020cd2  mov     [rsp+740h+bEnable], r13d
0x180020cd7  lea     rdx, [rsp+740h+bEnable]
0x180020cdc  mov     rax, [rcx]
0x180020cdf  mov     rax, [rax+18h]
0x180020ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ce8  test    eax, eax
0x180020cea  js      short loc_180020CF8
0x180020cec  cmp     [rsp+740h+bEnable], edi
0x180020cf0  jnz     short loc_180020CF8
0x180020cf2  mov     [rbx+2D0h], edi
0x180020cf8  mov     rcx, [rsp+740h+var_6F0]
0x180020cfd  mov     rax, [rcx]
0x180020d00  mov     rax, [rax+10h]
0x180020d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d09  jmp     short loc_180020D0E
0x180020d0b  xor     r13d, r13d
0x180020d0e  mov     rcx, [rbx+2B0h]; hIcon
0x180020d15  test    rcx, rcx
0x180020d18  jz      short loc_180020D27
0x180020d1a  call    cs:__imp_DestroyIcon
0x180020d20  mov     [rbx+2B0h], r13
0x180020d27  mov     eax, [rbx+2D0h]
0x180020d2d  mov     r9d, 30h ; '0'; cx
0x180020d33  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x180020d3a  neg     eax
0x180020d3c  mov     [rsp+740h+fuLoad], 20h ; ' '; fuLoad
0x180020d44  mov     r8d, edi; type
0x180020d47  sbb     rdx, rdx
0x180020d4a  mov     [rsp+740h+cy], r9d; cy
0x180020d4f  neg     rdx
0x180020d52  add     rdx, 54Ch; name
0x180020d59  call    cs:__imp_LoadImageW
0x180020d5f  mov     [rbx+2B0h], rax
0x180020d66  mov     r14, rax
0x180020d69  test    rax, rax
0x180020d6c  jz      short loc_180020D91
0x180020d6e  mov     rcx, [rbx+28h]; hDlg
0x180020d72  mov     edx, 89Eh; nIDDlgItem
0x180020d77  call    cs:__imp_GetDlgItem
0x180020d7d  xor     r9d, r9d; lParam
0x180020d80  mov     r8, r14; wParam
0x180020d83  mov     rcx, rax; hWnd
0x180020d86  mov     edx, 170h; Msg
0x180020d8b  call    cs:__imp_SendMessageW
0x180020d91  mov     ecx, [rbx+2B8h]
0x180020d97  mov     r14d, edi
0x180020d9a  mov     eax, ecx
0x180020d9c  neg     eax
0x180020d9e  sbb     r9d, r9d
0x180020da1  neg     r9d
0x180020da4  add     r9d, 111Eh
0x180020dab  cmp     [rbx+2D0h], r13d
0x180020db2  jz      loc_180020EA4
0x180020db8  mov     eax, ecx
0x180020dba  mov     edx, 1128h
0x180020dbf  neg     eax
0x180020dc1  mov     eax, [rbx+2E8h]
0x180020dc7  sbb     r9d, r9d
0x180020dca  neg     r9d
0x180020dcd  add     r9d, 1120h
0x180020dd4  cmp     eax, 2
0x180020dd7  jnz     short loc_180020DEF
0x180020dd9  mov     eax, ecx
0x180020ddb  mov     r14d, r13d
0x180020dde  neg     eax
0x180020de0  sbb     r9d, r9d
0x180020de3  neg     r9d
0x180020de6  add     r9d, 1122h
0x180020ded  jmp     short loc_180020E4C
0x180020def  cmp     eax, 4
0x180020df2  jnz     short loc_180020E0A
0x180020df4  mov     eax, ecx
0x180020df6  mov     r14d, r13d
0x180020df9  neg     eax
0x180020dfb  sbb     r9d, r9d
0x180020dfe  neg     r9d
0x180020e01  add     r9d, 1124h
0x180020e08  jmp     short loc_180020E4C
0x180020e0a  cmp     eax, 3
0x180020e0d  jnz     short loc_180020E22
0x180020e0f  mov     eax, ecx
0x180020e11  neg     eax
0x180020e13  sbb     r9d, r9d
0x180020e16  neg     r9d
0x180020e19  add     r9d, 1126h
0x180020e20  jmp     short loc_180020E4C
0x180020e22  cmp     eax, 5
0x180020e25  jnz     short loc_180020E36
0x180020e27  mov     eax, ecx
0x180020e29  neg     eax
0x180020e2b  sbb     r9d, r9d
0x180020e2e  neg     r9d
0x180020e31  add     r9d, edx
0x180020e34  jmp     short loc_180020E4C
0x180020e36  cmp     eax, 6
0x180020e39  jnz     short loc_180020E4C
0x180020e3b  mov     eax, ecx
0x180020e3d  neg     eax
0x180020e3f  sbb     r9d, r9d
0x180020e42  neg     r9d
0x180020e45  add     r9d, 112Eh
0x180020e4c  cmp     [rbx+2D4h], r13d
0x180020e53  jz      short loc_180020EA4
0x180020e55  test    r14d, r14d
0x180020e58  jnz     short loc_180020E67
  ... truncated ...
```
