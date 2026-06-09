# ATL::CAxDialogImpl<CExpInterDlg,ATL::CWindow>::CreateActiveXControls(uint)

- ea: `0x14001a2a0`
- end: `0x14001a804`
- name: `?CreateActiveXControls@?$CAxDialogImpl@VCExpInterDlg@@VCWindow@ATL@@@ATL@@UEAAJI@Z`
- size: `1380`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1400044f8`
- `0x14000e4f8`
- `0x14001043c`
- `0x1400138f8`
- `0x1400192b8`
- `0x14001a1fc`
- `0x14001a2a0`
- `0x14001a80c`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14001a474`
- `KERNEL32!GlobalAlloc` at `0x14001a474`
- `KERNEL32!LockResource` at `0x14001a31f`
- `KERNEL32!LockResource` at `0x14001a379`
- `KERNEL32!LockResource` at `0x14001a31f`
- `KERNEL32!LockResource` at `0x14001a379`
- `KERNEL32!LoadResource` at `0x14001a30b`
- `KERNEL32!LoadResource` at `0x14001a361`
- `KERNEL32!LoadResource` at `0x14001a30b`
- `KERNEL32!LoadResource` at `0x14001a361`
- `KERNEL32!GlobalUnlock` at `0x14001a4dd`
- `KERNEL32!GlobalUnlock` at `0x14001a4dd`
- `KERNEL32!GlobalLock` at `0x14001a48f`
- `KERNEL32!GlobalLock` at `0x14001a48f`
- `KERNEL32!FindResourceW` at `0x14001a2e3`
- `KERNEL32!FindResourceW` at `0x14001a342`
- `KERNEL32!FindResourceW` at `0x14001a2e3`
- `KERNEL32!FindResourceW` at `0x14001a342`
- `USER32!SetWindowContextHelpId` at `0x14001a629`
- `USER32!SetWindowContextHelpId` at `0x14001a629`
- `USER32!MapDialogRect` at `0x14001a59f`
- `USER32!MapDialogRect` at `0x14001a59f`
- `USER32!GetWindow` at `0x14001a3c7`
- `USER32!GetWindow` at `0x14001a6d3`
- `USER32!GetWindow` at `0x14001a3c7`
- `USER32!GetWindow` at `0x14001a6d3`
- `USER32!SetWindowPos` at `0x14001a680`
- `USER32!SetWindowPos` at `0x14001a680`
- `msvcrt!memcpy_s` at `0x14001a4a6`
- `msvcrt!memcpy_s` at `0x14001a4a6`
- `ole32!CreateStreamOnHGlobal` at `0x14001a4f5`
- `ole32!CreateStreamOnHGlobal` at `0x14001a4f5`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a6a0`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a78d`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a6a0`
- `OLEAUT32!__imp_SysFreeString` at `0x14001a78d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CAxDialogImpl<CExpInterDlg,ATL::CWindow>::CreateActiveXControls(
        __int64 a1,
        unsigned __int16 a2)
{
  const WCHAR *v3; // rbx
  HRSRC ResourceW; // rax
  unsigned __int16 *v5; // rdi
  int inited; // esi
  HGLOBAL Resource; // rax
  HRSRC v8; // rax
  HGLOBAL v9; // rax
  const struct DLGTEMPLATE *v10; // rax
  __int16 style_high; // r15
  __int64 v12; // rcx
  unsigned __int16 v13; // r12
  struct DLGITEMTEMPLATE *FirstDlgItem; // r14
  HWND Window; // rbx
  __int16 v16; // r13
  __int64 v17; // rax
  int id; // r8d
  char *v19; // r12
  unsigned __int16 *v20; // rsi
  unsigned __int16 *v21; // rcx
  int v22; // eax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  struct IStream *v26; // rcx
  unsigned int v27; // edi
  HGLOBAL v28; // rax
  void *v29; // rbx
  void *v30; // rax
  errno_t v31; // eax
  OLECHAR *v32; // rdi
  __int64 v33; // rax
  LONG v34; // ecx
  __int64 v35; // rax
  LONG v36; // edx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rbx
  struct DLGITEMTEMPLATE *v40; // rcx
  __int16 style; // ax
  __int16 v42; // ax
  unsigned __int16 v43; // ax
  unsigned __int16 v45; // [rsp+40h] [rbp-39h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-31h] BYREF
  HWND v47; // [rsp+50h] [rbp-29h]
  HWND hWnd; // [rsp+58h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v50; // [rsp+68h] [rbp-11h]
  __int64 v51; // [rsp+70h] [rbp-9h]
  __int64 i; // [rsp+78h] [rbp-1h]
  struct tagRECT Rect; // [rsp+80h] [rbp+7h] BYREF

  v51 = a1;
  v3 = (const WCHAR *)a2;
  ResourceW = FindResourceW(hModule, (LPCWSTR)a2, (LPCWSTR)0xF0);
  v5 = 0;
  v50 = 0;
  inited = 0;
  if ( ResourceW )
  {
    Resource = LoadResource(hModule, ResourceW);
    if ( Resource )
    {
      v5 = (unsigned __int16 *)LockResource(Resource);
      v50 = v5;
    }
  }
  v8 = FindResourceW(hModule, v3, (LPCWSTR)5);
  if ( v8 )
  {
    v9 = LoadResource(hModule, v8);
    if ( !v9 || (v10 = (const struct DLGTEMPLATE *)LockResource(v9)) == 0 )
      return (unsigned int)ATL::AtlHresultFromLastError();
    style_high = HIWORD(v10->style);
    v12 = 8;
    if ( style_high == -1 )
      v12 = 16;
    v13 = *(_WORD *)((char *)&v10->style + v12);
    v45 = v13;
    FirstDlgItem = ATL::_DialogSplitHelper::FindFirstDlgItem(v10);
    Window = GetWindow(*(HWND *)(a1 + 8), 5u);
    v47 = Window;
    v16 = 0;
    if ( v13 )
    {
      v17 = 24;
      if ( style_high != -1 )
        v17 = 18;
      for ( i = v17; ; v17 = i )
      {
        if ( style_high == -1 )
          id = *(DWORD *)((char *)&FirstDlgItem[1].style + 2);
        else
          id = FirstDlgItem->id;
        v19 = (char *)FirstDlgItem + v17;
        if ( *(_WORD *)((char *)&FirstDlgItem->style + v17) == 123 )
        {
          v20 = 0;
          v21 = v5;
          if ( !v5 )
            goto LABEL_20;
          while ( 1 )
          {
            v22 = *v21;
            v23 = v21 + 1;
            v24 = *(unsigned int *)(v23 + 1);
            if ( v22 == id )
              break;
            v21 = (unsigned __int16 *)((char *)v23 + v24 + 6);
            if ( !v21 )
              goto LABEL_20;
          }
          if ( *v23 == 888 )
          {
LABEL_20:
            v25 = 0;
          }
          else
          {
            v20 = v23;
            v25 = v24 + 6;
          }
          v26 = 0;
          ppstm = 0;
          if ( v25 )
          {
            v27 = v25;
            v28 = GlobalAlloc(0x42u, v25);
            v29 = v28;
            if ( !v28 )
            {
              inited = -2147024882;
              if ( ppstm )
                (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
              return (unsigned int)inited;
            }
            v30 = GlobalLock(v28);
            v31 = memcpy_s(v30, v27, v20, v27);
            if ( v31 )
            {
              if ( v31 == 12 )
                ATL::AtlThrowImpl(-2147024882);
              if ( v31 == 22 || v31 == 34 )
                ATL::AtlThrowImpl(-2147024809);
              if ( v31 != 80 )
                ATL::AtlThrowImpl(-2147467259);
            }
            GlobalUnlock(v29);
            CreateStreamOnHGlobal(v29, 1, &ppstm);
            v26 = ppstm;
            Window = v47;
          }
          bstrString = 0;
          inited = ATL::_DialogSplitHelper::ParseInitData(v26, &bstrString);
          v32 = bstrString;
          if ( inited >= 0 )
          {
            hWnd = 0;
            AtlAxWinInit();
            Rect = 0;
            v33 = 12;
            if ( style_high != -1 )
              v33 = 8;
            v34 = *(__int16 *)((char *)&FirstDlgItem->style + v33);
            Rect.left = v34;
            v35 = 14;
            if ( style_high != -1 )
              v35 = 10;
            v36 = *(__int16 *)((char *)&FirstDlgItem->style + v35);
            Rect.top = v36;
            v37 = 16;
            if ( style_high != -1 )
              v37 = 12;
            Rect.right = v34 + *(__int16 *)((char *)&FirstDlgItem->style + v37);
            v38 = 18;
            if ( style_high != -1 )
              v38 = 14;
            Rect.bottom = v36 + *(__int16 *)((char *)&FirstDlgItem->style + v38);
            v39 = v51;
            MapDialogRect(*(HWND *)(v51 + 8), &Rect);
            ATL::CAxWindow2T<ATL::CWindow>::Create(&hWnd, *(_QWORD *)(v39 + 8), &Rect);
            Window = hWnd;
            if ( hWnd )
            {
              if ( style_high == -1 && FirstDlgItem->style )
                SetWindowContextHelpId(hWnd, FirstDlgItem->style);
              inited = ATL::CAxWindow2T<ATL::CWindow>::CreateControlLic(&hWnd, v19, ppstm);
              if ( inited < 0 )
              {
                SysFreeString(v32);
                if ( ppstm )
                  (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
                return (unsigned int)inited;
              }
              SetWindowPos(Window, (HWND)((unsigned __int64)v47 & -(__int64)(v16 != 0)), 0, 0, 0, 0, 0x13u);
              v47 = Window;
            }
            else
            {
              inited = ATL::AtlHresultFromLastError();
              Window = v47;
            }
          }
          SysFreeString(v32);
          if ( ppstm )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        }
        else if ( v16 )
        {
          Window = GetWindow(Window, 2u);
          v47 = Window;
        }
        v40 = (struct DLGITEMTEMPLATE *)((char *)FirstDlgItem + 24);
        if ( style_high != -1 )
          v40 = FirstDlgItem + 1;
        if ( LOWORD(v40->style) == 0xFFFF )
        {
          v40 = (struct DLGITEMTEMPLATE *)((char *)v40 + 4);
        }
        else
        {
          do
          {
            style = v40->style;
            v40 = (struct DLGITEMTEMPLATE *)((char *)v40 + 2);
          }
          while ( style );
        }
        if ( LOWORD(v40->style) == 0xFFFF )
        {
          v40 = (struct DLGITEMTEMPLATE *)((char *)v40 + 4);
        }
        else
        {
          do
          {
            v42 = v40->style;
            v40 = (struct DLGITEMTEMPLATE *)((char *)v40 + 2);
          }
          while ( v42 );
        }
        v43 = v40->style;
        if ( LOWORD(v40->style) && style_high != -1 )
          v43 -= 2;
        FirstDlgItem = (struct DLGITEMTEMPLATE *)(((unsigned __int64)&v40->dwExtendedStyle + v43 + 1)
                                                & 0xFFFFFFFFFFFFFFFCuLL);
        if ( (unsigned __int16)++v16 >= v45 )
          return (unsigned int)inited;
        v5 = v50;
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14001a2a0  mov     [rsp-8+arg_10], rbx
0x14001a2a5  push    rbp
0x14001a2a6  push    rsi
0x14001a2a7  push    rdi
0x14001a2a8  push    r12
0x14001a2aa  push    r13
0x14001a2ac  push    r14
0x14001a2ae  push    r15
0x14001a2b0  lea     rbp, [rsp-27h]
0x14001a2b5  sub     rsp, 0A0h
0x14001a2bc  mov     rax, cs:__security_cookie
0x14001a2c3  xor     rax, rsp
0x14001a2c6  mov     [rbp+57h+var_40], rax
0x14001a2ca  mov     r13, rcx
0x14001a2cd  mov     [rbp+57h+var_60], rcx
0x14001a2d1  movzx   ebx, dx
0x14001a2d4  mov     r8d, 0F0h; lpType
0x14001a2da  mov     edx, ebx; lpName
0x14001a2dc  mov     rcx, cs:hModule; hModule
0x14001a2e3  call    cs:__imp_FindResourceW
0x14001a2ea  nop     dword ptr [rax+rax+00h]
0x14001a2ef  xor     r14d, r14d
0x14001a2f2  mov     edi, r14d
0x14001a2f5  mov     [rbp+57h+var_68], r14
0x14001a2f9  mov     esi, r14d
0x14001a2fc  test    rax, rax
0x14001a2ff  jz      short loc_14001A332
0x14001a301  mov     rdx, rax; hResInfo
0x14001a304  mov     rcx, cs:hModule; hModule
0x14001a30b  call    cs:__imp_LoadResource
0x14001a312  nop     dword ptr [rax+rax+00h]
0x14001a317  test    rax, rax
0x14001a31a  jz      short loc_14001A332
0x14001a31c  mov     rcx, rax; hResData
0x14001a31f  call    cs:__imp_LockResource
0x14001a326  nop     dword ptr [rax+rax+00h]
0x14001a32b  mov     rdi, rax
0x14001a32e  mov     [rbp+57h+var_68], rax
0x14001a332  mov     r8d, 5; lpType
0x14001a338  mov     rdx, rbx; lpName
0x14001a33b  mov     rcx, cs:hModule; hModule
0x14001a342  call    cs:__imp_FindResourceW
0x14001a349  nop     dword ptr [rax+rax+00h]
0x14001a34e  test    rax, rax
0x14001a351  jz      loc_14001A7B9
0x14001a357  mov     rdx, rax; hResInfo
0x14001a35a  mov     rcx, cs:hModule; hModule
0x14001a361  call    cs:__imp_LoadResource
0x14001a368  nop     dword ptr [rax+rax+00h]
0x14001a36d  test    rax, rax
0x14001a370  jz      loc_14001A7B2
0x14001a376  mov     rcx, rax; hResData
0x14001a379  call    cs:__imp_LockResource
0x14001a380  nop     dword ptr [rax+rax+00h]
0x14001a385  test    rax, rax
0x14001a388  jz      loc_14001A7B2
0x14001a38e  movzx   r15d, word ptr [rax+2]
0x14001a393  mov     edx, 0FFFFh
0x14001a398  mov     ecx, 8
0x14001a39d  lea     r8d, [rcx+8]
0x14001a3a1  cmp     r15w, dx
0x14001a3a5  cmovz   ecx, r8d
0x14001a3a9  movzx   r12d, word ptr [rcx+rax]
0x14001a3ae  mov     [rbp+57h+var_90], r12w
0x14001a3b3  mov     rcx, rax; struct DLGTEMPLATE *
0x14001a3b6  call    ?FindFirstDlgItem@_DialogSplitHelper@ATL@@SAPEAUDLGITEMTEMPLATE@@PEBUDLGTEMPLATE@@@Z; ATL::_DialogSplitHelper::FindFirstDlgItem(DLGTEMPLATE const *)
0x14001a3bb  mov     r14, rax
0x14001a3be  mov     edx, 5; uCmd
0x14001a3c3  mov     rcx, [r13+8]; hWnd
0x14001a3c7  call    cs:__imp_GetWindow
0x14001a3ce  nop     dword ptr [rax+rax+00h]
0x14001a3d3  mov     rbx, rax
0x14001a3d6  mov     [rbp+57h+var_80], rax
0x14001a3da  xor     r10d, r10d
0x14001a3dd  mov     r13d, r10d
0x14001a3e0  cmp     r10w, r12w
0x14001a3e4  jnb     loc_14001A7B9
0x14001a3ea  lea     eax, [r10+18h]
0x14001a3ee  lea     ecx, [rax-6]
0x14001a3f1  mov     r8d, 0FFFFh
0x14001a3f7  cmp     r15w, r8w
0x14001a3fb  cmovnz  eax, ecx
0x14001a3fe  mov     [rbp+57h+var_58], rax
0x14001a402  lea     edx, [rcx-10h]; uCmd
0x14001a405  lea     r9d, [r10+1]
0x14001a409  cmp     r15w, r8w
0x14001a40d  jnz     short loc_14001A415
0x14001a40f  mov     r8d, [r14+14h]
0x14001a413  jmp     short loc_14001A41A
0x14001a415  movzx   r8d, word ptr [r14+10h]
0x14001a41a  lea     r12, [rax+r14]
0x14001a41e  cmp     word ptr [r12], 7Bh ; '{'
0x14001a424  jnz     loc_14001A6CA
0x14001a42a  mov     rsi, r10
0x14001a42d  mov     rcx, rdi
0x14001a430  test    rdi, rdi
0x14001a433  jz      short loc_14001A459
0x14001a435  movzx   eax, word ptr [rcx]
0x14001a438  add     rcx, rdx
0x14001a43b  lea     r9, [rcx+2]
0x14001a43f  mov     edx, [r9]
0x14001a442  cmp     eax, r8d
0x14001a445  jz      loc_14001A5C4
0x14001a44b  lea     rcx, [rdx+4]
0x14001a44f  add     rcx, r9
0x14001a452  mov     edx, 2
0x14001a457  jnz     short loc_14001A435
0x14001a459  mov     eax, r10d
0x14001a45c  mov     rcx, r10
0x14001a45f  mov     [rbp+57h+ppstm], rcx
0x14001a463  test    eax, eax
0x14001a465  jz      loc_14001A50C
0x14001a46b  mov     edi, eax
0x14001a46d  mov     edx, eax; dwBytes
0x14001a46f  mov     ecx, 42h ; 'B'; uFlags
0x14001a474  call    cs:__imp_GlobalAlloc
0x14001a47b  nop     dword ptr [rax+rax+00h]
0x14001a480  mov     rbx, rax
0x14001a483  test    rax, rax
0x14001a486  jz      loc_14001A76D
0x14001a48c  mov     rcx, rax; hMem
0x14001a48f  call    cs:__imp_GlobalLock
0x14001a496  nop     dword ptr [rax+rax+00h]
0x14001a49b  mov     r9d, edi; SourceSize
0x14001a49e  mov     r8, rsi; Source
0x14001a4a1  mov     edx, edi; DestinationSize
0x14001a4a3  mov     rcx, rax; Destination
0x14001a4a6  call    cs:__imp_memcpy_s
0x14001a4ad  nop     dword ptr [rax+rax+00h]
0x14001a4b2  test    eax, eax
0x14001a4b4  jz      short loc_14001A4DA
0x14001a4b6  cmp     eax, 0Ch
0x14001a4b9  jz      loc_14001A7E3
0x14001a4bf  cmp     eax, 16h
0x14001a4c2  jz      loc_14001A7F9
0x14001a4c8  cmp     eax, 22h ; '"'
0x14001a4cb  jz      loc_14001A7F9
0x14001a4d1  cmp     eax, 50h ; 'P'
0x14001a4d4  jnz     loc_14001A7EE
0x14001a4da  mov     rcx, rbx; hMem
0x14001a4dd  call    cs:__imp_GlobalUnlock
0x14001a4e4  nop     dword ptr [rax+rax+00h]
0x14001a4e9  lea     r8, [rbp+57h+ppstm]; ppstm
0x14001a4ed  mov     edx, 1; fDeleteOnRelease
0x14001a4f2  mov     rcx, rbx; hGlobal
0x14001a4f5  call    cs:__imp_CreateStreamOnHGlobal
0x14001a4fc  nop     dword ptr [rax+rax+00h]
0x14001a501  mov     rcx, [rbp+57h+ppstm]; struct IStream *
0x14001a505  mov     rbx, [rbp+57h+var_80]
0x14001a509  xor     r10d, r10d
0x14001a50c  mov     [rbp+57h+bstrString], r10
0x14001a510  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x14001a514  call    ?ParseInitData@_DialogSplitHelper@ATL@@SAJPEAUIStream@@PEAPEAG@Z; ATL::_DialogSplitHelper::ParseInitData(IStream *,ushort * *)
0x14001a519  mov     esi, eax
0x14001a51b  mov     rdi, [rbp+57h+bstrString]
0x14001a51f  test    eax, eax
0x14001a521  js      loc_14001A69D
0x14001a527  xor     esi, esi
0x14001a529  mov     [rbp+57h+hWnd], rsi
0x14001a52d  call    AtlAxWinInit
0x14001a532  xorps   xmm0, xmm0
0x14001a535  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x14001a539  lea     r9d, [rsi+0Ch]
0x14001a53d  mov     eax, r9d
0x14001a540  mov     r8d, 0FFFFh
0x14001a546  cmp     r15w, r8w
0x14001a54a  lea     ecx, [rsi+8]
0x14001a54d  cmovnz  eax, ecx
0x14001a550  movsx   ecx, word ptr [rax+r14]
0x14001a555  mov     [rbp+57h+Rect.left], ecx
0x14001a558  lea     r10d, [rsi+0Eh]
0x14001a55c  mov     eax, r10d
0x14001a55f  lea     edx, [rsi+0Ah]
0x14001a562  cmovnz  eax, edx
0x14001a565  movsx   edx, word ptr [rax+r14]
0x14001a56a  mov     [rbp+57h+Rect.top], edx
0x14001a56d  lea     eax, [rsi+10h]
0x14001a570  cmovnz  eax, r9d
0x14001a574  movsx   eax, word ptr [rax+r14]
0x14001a579  add     eax, ecx
0x14001a57b  mov     [rbp+57h+Rect.right], eax
0x14001a57e  lea     eax, [rsi+12h]
0x14001a581  cmp     r15w, r8w
0x14001a585  cmovnz  eax, r10d
0x14001a589  movsx   eax, word ptr [rax+r14]
0x14001a58e  add     eax, edx
0x14001a590  mov     [rbp+57h+Rect.bottom], eax
0x14001a593  lea     rdx, [rbp+57h+Rect]; lpRect
0x14001a597  mov     rbx, [rbp+57h+var_60]
0x14001a59b  mov     rcx, [rbx+8]; hDlg
0x14001a59f  call    cs:__imp_MapDialogRect
0x14001a5a6  nop     dword ptr [rax+rax+00h]
0x14001a5ab  mov     eax, 0FFFFh
0x14001a5b0  cmp     r15w, ax
0x14001a5b4  jnz     short loc_14001A5DD
0x14001a5b6  mov     ecx, [r14+4]
0x14001a5ba  lea     rax, [r14+8]
0x14001a5be  mov     edx, [r14+14h]
0x14001a5c2  jmp     short loc_14001A5E7
0x14001a5c4  mov     eax, 378h
0x14001a5c9  cmp     [rcx], ax
0x14001a5cc  jz      loc_14001A459
0x14001a5d2  mov     rsi, rcx
0x14001a5d5  lea     eax, [rdx+6]
0x14001a5d8  jmp     loc_14001A45C
0x14001a5dd  mov     ecx, esi
0x14001a5df  mov     rax, r14
0x14001a5e2  movzx   edx, word ptr [r14+10h]
0x14001a5e7  mov     eax, [rax]
0x14001a5e9  bts     eax, 10h
0x14001a5ed  mov     qword ptr [rsp+0D0h+uFlags], rdx
0x14001a5f2  mov     [rsp+0D0h+cy], ecx
0x14001a5f6  mov     [rsp+0D0h+var_B0], eax
0x14001a5fa  lea     r8, [rbp+57h+Rect]
0x14001a5fe  mov     rdx, [rbx+8]
0x14001a602  lea     rcx, [rbp+57h+hWnd]
0x14001a606  call    ?Create@?$CAxWindow2T@VCWindow@ATL@@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@PEAX@Z; ATL::CAxWindow2T<ATL::CWindow>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,void *)
0x14001a60b  mov     rbx, [rbp+57h+hWnd]
0x14001a60f  test    rbx, rbx
0x14001a612  jz      short loc_14001A692
0x14001a614  mov     eax, 0FFFFh
0x14001a619  cmp     r15w, ax
0x14001a61d  jnz     short loc_14001A635
0x14001a61f  mov     edx, [r14]; DWORD
0x14001a622  test    edx, edx
0x14001a624  jz      short loc_14001A635
0x14001a626  mov     rcx, rbx; HWND
0x14001a629  call    cs:__imp_SetWindowContextHelpId
0x14001a630  nop     dword ptr [rax+rax+00h]
0x14001a635  mov     qword ptr [rsp+0D0h+var_B0], rdi
0x14001a63a  mov     r8, [rbp+57h+ppstm]
0x14001a63e  mov     rdx, r12
0x14001a641  lea     rcx, [rbp+57h+hWnd]
0x14001a645  call    ?CreateControlLic@?$CAxWindow2T@VCWindow@ATL@@@ATL@@QEAAJPEBGPEAUIStream@@PEAPEAUIUnknown@@PEAG@Z; ATL::CAxWindow2T<ATL::CWindow>::CreateControlLic(ushort const *,IStream *,IUnknown * *,ushort *)
0x14001a64a  mov     esi, eax
0x14001a64c  xor     r12d, r12d
0x14001a64f  test    eax, eax
0x14001a651  js      loc_14001A78A
0x14001a657  movzx   eax, r13w
0x14001a65b  neg     ax
0x14001a65e  sbb     rdx, rdx
0x14001a661  and     rdx, [rbp+57h+var_80]; hWndInsertAfter
0x14001a665  mov     [rsp+0D0h+uFlags], 13h; uFlags
0x14001a66d  mov     [rsp+0D0h+cy], r12d; cy
0x14001a672  mov     [rsp+0D0h+var_B0], r12d; cx
0x14001a677  xor     r9d, r9d; Y
0x14001a67a  xor     r8d, r8d; X
0x14001a67d  mov     rcx, rbx; hWnd
0x14001a680  call    cs:__imp_SetWindowPos
0x14001a687  nop     dword ptr [rax+rax+00h]
0x14001a68c  mov     [rbp+57h+var_80], rbx
0x14001a690  jmp     short loc_14001A69D
0x14001a692  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14001a697  mov     esi, eax
0x14001a699  mov     rbx, [rbp+57h+var_80]
0x14001a69d  mov     rcx, rdi; bstrString
0x14001a6a0  call    cs:__imp_SysFreeString
0x14001a6a7  nop     dword ptr [rax+rax+00h]
0x14001a6ac  nop
0x14001a6ad  mov     rcx, [rbp+57h+ppstm]
0x14001a6b1  xor     r10d, r10d
0x14001a6b4  test    rcx, rcx
0x14001a6b7  jz      short loc_14001A6C8
0x14001a6b9  mov     rax, [rcx]
0x14001a6bc  mov     rax, [rax+10h]
0x14001a6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a6c5  xor     r10d, r10d
0x14001a6c8  jmp     short loc_14001A6E9
0x14001a6ca  test    r13w, r13w
0x14001a6ce  jz      short loc_14001A6F3
0x14001a6d0  mov     rcx, rbx; hWnd
0x14001a6d3  call    cs:__imp_GetWindow
0x14001a6da  nop     dword ptr [rax+rax+00h]
0x14001a6df  mov     rbx, rax
0x14001a6e2  mov     [rbp+57h+var_80], rax
0x14001a6e6  xor     r10d, r10d
0x14001a6e9  mov     r9d, 1
0x14001a6ef  lea     edx, [r9+1]
0x14001a6f3  mov     r8d, 0FFFFh
0x14001a6f9  cmp     r15w, r8w
0x14001a6fd  lea     rcx, [r14+18h]
0x14001a701  jz      short loc_14001A707
0x14001a703  lea     rcx, [r14+12h]
0x14001a707  cmp     [rcx], r8w
0x14001a70b  jnz     short loc_14001A713
0x14001a70d  add     rcx, 4
0x14001a711  jmp     short loc_14001A71E
0x14001a713  movzx   eax, word ptr [rcx]
0x14001a716  add     rcx, rdx
0x14001a719  test    ax, ax
0x14001a71c  jnz     short loc_14001A713
0x14001a71e  cmp     [rcx], r8w
0x14001a722  jnz     short loc_14001A72A
0x14001a724  add     rcx, 4
0x14001a728  jmp     short loc_14001A735
0x14001a72a  movzx   eax, word ptr [rcx]
0x14001a72d  add     rcx, rdx
0x14001a730  test    ax, ax
0x14001a733  jnz     short loc_14001A72A
0x14001a735  movzx   eax, word ptr [rcx]
  ... truncated ...
```
