# ViewPageCRLGeneral(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009000`
- end: `0x18000961e`
- name: `?ViewPageCRLGeneral@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1566`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callees

- `0x18000767c`
- `0x1800089bc`
- `0x180008b10`
- `0x180009000`
- `0x180009624`
- `0x1800116f8`
- `0x180011a28`
- `0x180011b88`
- `0x180011cf4`
- `0x180032318`
- `0x1800323e0`
- `0x180032c70`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800091bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800091f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800092b8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800091bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800091f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800092b8`
- `GDI32!DeleteObject` at `0x18000917e`
- `GDI32!DeleteObject` at `0x1800095e4`
- `GDI32!DeleteObject` at `0x18000917e`
- `GDI32!DeleteObject` at `0x1800095e4`
- `GDI32!GetBkColor` at `0x180009511`
- `GDI32!GetBkColor` at `0x180009511`
- `USER32!DrawIcon` at `0x180009550`
- `USER32!DrawIcon` at `0x180009550`
- `USER32!LoadBitmapA` at `0x18000914e`
- `USER32!LoadBitmapA` at `0x18000914e`
- `USER32!GetUpdateRect` at `0x1800094eb`
- `USER32!GetUpdateRect` at `0x1800094eb`
- `USER32!BeginPaint` at `0x180009500`
- `USER32!BeginPaint` at `0x180009500`
- `USER32!EndPaint` at `0x18000955d`
- `USER32!EndPaint` at `0x18000955d`
- `USER32!LoadIconA` at `0x18000929b`
- `USER32!LoadIconA` at `0x18000929b`
- `USER32!SendMessageA` at `0x180009175`
- `USER32!SendMessageA` at `0x1800091d7`
- `USER32!SendMessageA` at `0x18000920b`
- `USER32!SendMessageA` at `0x180009289`
- `USER32!SendMessageA` at `0x180009323`
- `USER32!SendMessageA` at `0x1800093c2`
- `USER32!SendMessageA` at `0x1800093e2`
- `USER32!SendMessageA` at `0x180009425`
- `USER32!SendMessageA` at `0x180009535`
- `USER32!SendMessageA` at `0x180009596`
- `USER32!SendMessageA` at `0x1800095c2`
- `USER32!SendMessageA` at `0x180009175`
- `USER32!SendMessageA` at `0x1800091d7`
- `USER32!SendMessageA` at `0x18000920b`
- `USER32!SendMessageA` at `0x180009289`
- `USER32!SendMessageA` at `0x180009323`
- `USER32!SendMessageA` at `0x1800093c2`
- `USER32!SendMessageA` at `0x1800093e2`
- `USER32!SendMessageA` at `0x180009425`
- `USER32!SendMessageA` at `0x180009535`
- `USER32!SendMessageA` at `0x180009596`
- `USER32!SendMessageA` at `0x1800095c2`
- `USER32!GetWindowLongPtrA` at `0x18000908c`
- `USER32!GetWindowLongPtrA` at `0x18000908c`
- `USER32!SetWindowLongPtrA` at `0x1800090f9`
- `USER32!SetWindowLongPtrA` at `0x180009469`
- `USER32!SetWindowLongPtrA` at `0x180009489`
- `USER32!SetWindowLongPtrA` at `0x1800090f9`
- `USER32!SetWindowLongPtrA` at `0x180009469`
- `USER32!SetWindowLongPtrA` at `0x180009489`
- `USER32!GetDlgItem` at `0x18000911b`
- `USER32!GetDlgItem` at `0x1800092d9`
- `USER32!GetDlgItem` at `0x18000930d`
- `USER32!GetDlgItem` at `0x180009339`
- `USER32!GetDlgItem` at `0x1800093ab`
- `USER32!GetDlgItem` at `0x180009445`
- `USER32!GetDlgItem` at `0x180009521`
- `USER32!GetDlgItem` at `0x180009570`
- `USER32!GetDlgItem` at `0x18000911b`
- `USER32!GetDlgItem` at `0x1800092d9`
- `USER32!GetDlgItem` at `0x18000930d`
- `USER32!GetDlgItem` at `0x180009339`
- `USER32!GetDlgItem` at `0x1800093ab`
- `USER32!GetDlgItem` at `0x180009445`
- `USER32!GetDlgItem` at `0x180009521`
- `USER32!GetDlgItem` at `0x180009570`

## pseudocode

```c
_BOOL8 __fastcall ViewPageCRLGeneral(HWND hDlg, int a2, __int64 a3, __int64 a4)
{
  LONG_PTR WindowLongPtrA; // r14
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  _QWORD *v14; // r15
  const CRL_CONTEXT *v15; // r13
  HWND v16; // r12
  LPARAM v17; // r14
  HBITMAP BitmapA; // rax
  HBITMAP v19; // rsi
  HICON IconA; // rax
  HINSTANCE v21; // rcx
  HWND v22; // rax
  HWND v23; // rax
  HWND v25; // rax
  int v26; // eax
  HWND v27; // r14
  int v28; // ebx
  HWND v29; // rax
  LONG_PTR v30; // r8
  HDC v31; // rax
  HDC v32; // rsi
  COLORREF BkColor; // ebx
  HWND v34; // rax
  HICON v35; // r9
  HWND DlgItem; // rdi
  int v37; // eax
  void *v38; // rcx
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  LPARAM lParam[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v41; // [rsp+48h] [rbp-B8h]
  __int128 v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  LPARAM v44; // [rsp+70h] [rbp-90h] BYREF
  int v45; // [rsp+7Ch] [rbp-84h]
  int v46; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+98h] [rbp-68h]
  LPARAM v48[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[28]; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT Rect; // [rsp+110h] [rbp+10h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Buffer[768]; // [rsp+170h] [rbp+70h] BYREF

  WindowLongPtrA = 0;
  v43 = 0;
  *(_OWORD *)lParam = 0;
  v41 = 0;
  v42 = 0;
  memset_0(&v44, 0, 0x58u);
  memset(v50, 0, sizeof(v50));
  *(_OWORD *)v48 = 0;
  v49 = 0;
  if ( a2 != 272 )
  {
    WindowLongPtrA = GetWindowLongPtrA(hDlg, 16);
    if ( !WindowLongPtrA )
      return 0;
  }
  v9 = a2 - 2;
  if ( !v9 )
  {
    DlgItem = GetDlgItem(hDlg, 100);
    memset_0(&v44, 0, 0x58u);
    v37 = SendMessageA(DlgItem, 0x1004u, 0, 0);
    LODWORD(v44) = 4;
    HIDWORD(v44) = v37 - 1;
    if ( v37 - 1 >= 0 )
    {
      do
      {
        if ( (unsigned int)SendMessageA(DlgItem, 0x104Bu, 0, (LPARAM)&v44) )
          FreeListDisplayHelper(hMem);
        --HIDWORD(v44);
      }
      while ( v44 >= 0 );
    }
    v38 = *(void **)(WindowLongPtrA + 16);
    if ( v38 )
    {
      DeleteObject(v38);
      *(_QWORD *)(WindowLongPtrA + 16) = 0;
    }
    return 0;
  }
  v10 = v9 - 13;
  if ( !v10 )
  {
    Rect = 0;
    memset_0(&Paint, 0, sizeof(Paint));
    if ( GetUpdateRect(hDlg, &Rect, 0) )
    {
      v31 = BeginPaint(hDlg, &Paint);
      v32 = v31;
      if ( v31 )
      {
        BkColor = GetBkColor(v31);
        v34 = GetDlgItem(hDlg, 102);
        SendMessageA(v34, 0x443u, 0, BkColor);
        v35 = *(HICON *)(WindowLongPtrA + 16);
        if ( v35 )
          DrawIcon(v32, 21, 10, v35);
      }
      EndPaint(hDlg, &Paint);
    }
    return 0;
  }
  v11 = v10 - 63;
  if ( !v11 )
  {
    v26 = *(_DWORD *)(a4 + 16);
    if ( v26 == -209 )
    {
      *(_DWORD *)(WindowLongPtrA + 24) = 1;
      return 0;
    }
    if ( v26 == -205 )
      return 1;
    if ( v26 == -203 )
    {
      v30 = 0;
    }
    else
    {
      if ( v26 != -202 )
      {
        if ( v26 == -201 )
        {
          SetWindowLongPtrA(hDlg, 0, 0);
          return 1;
        }
        if ( v26 == -100 )
        {
          if ( *(_QWORD *)(a4 + 8) == 100 )
          {
            if ( (*(_BYTE *)(a4 + 32) & 2) != 0 )
            {
              v28 = *(_DWORD *)(a4 + 24);
              v29 = GetDlgItem(hDlg, 100);
              DisplayHelperTextInEdit(v29, hDlg, 0x65u, v28);
            }
            return 1;
          }
        }
        else if ( v26 == -7 && *(_QWORD *)(a4 + 8) == 100 )
        {
          v27 = GetDlgItem(hDlg, 100);
          if ( (unsigned int)SendMessageA(v27, 0x1004u, 0, 0) )
          {
            if ( (unsigned int)SendMessageA(v27, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2) == -1 )
            {
              memset_0(&v44, 0, 0x58u);
              v44 = 8;
              v45 = 1;
              v46 = 1;
              SendMessageA(v27, 0x1006u, 0, (LPARAM)&v44);
            }
          }
        }
LABEL_35:
        if ( a3 == 103 && ((*(_DWORD *)(a4 + 16) + 4) & 0xFFFFFFFD) == 0 )
          DisplayHtmlHelp(hDlg, (LPCWSTR)(a4 + 136));
        return 0;
      }
      v30 = 1;
    }
    SetWindowLongPtrA(hDlg, 0, v30);
    goto LABEL_35;
  }
  v12 = v11 - 5;
  if ( !v12 )
  {
    v25 = GetDlgItem(hDlg, 103);
    InvokeHelpLink(v25);
    return 0;
  }
  v13 = v12 - 189;
  if ( v13 )
    return v13 == 1 && (_WORD)a3 == 9;
  v14 = *(_QWORD **)(a4 + 48);
  v15 = *(const CRL_CONTEXT **)(*v14 + 32LL);
  SetWindowLongPtrA(hDlg, 16, (LONG_PTR)v14);
  CryptUISetRicheditTextW(hDlg, 0x65u, &Src);
  v16 = GetDlgItem(hDlg, 100);
  v17 = IsolationAwareImageList_Create(16, 16, 32, 1);
  if ( v17 )
  {
    BitmapA = LoadBitmapA(HinstDll, (LPCSTR)0x134);
    v19 = BitmapA;
    if ( BitmapA )
    {
      IsolationAwareImageList_Add(v17, BitmapA);
      SendMessageA(v16, 0x1003u, 1u, v17);
      DeleteObject(v19);
    }
  }
  lParam[0] = 15;
  *(_QWORD *)&v41 = Buffer;
  HIDWORD(v41) = 0;
  LODWORD(lParam[1]) = 130;
  LoadStringW(HinstDll, 0xC92u, Buffer, 768);
  SendMessageA(v16, 0x1061u, 0, (LPARAM)lParam);
  LODWORD(lParam[1]) = 190;
  LoadStringW(HinstDll, 0xC93u, Buffer, 768);
  SendMessageA(v16, 0x1061u, 1u, (LPARAM)lParam);
  v39 = 0;
  DisplayV1Fields(v16);
  DisplayExtensions(v16, v15->pCrlInfo->cExtension, v15->pCrlInfo->rgExtension, 0, &v39);
  DisplayExtensions(v16, v15->pCrlInfo->cExtension, v15->pCrlInfo->rgExtension, 1, &v39);
  DisplayProperties(v16, v15);
  SendMessageA(v16, 0x1036u, 0, 32);
  IconA = LoadIconA(HinstDll, (LPCSTR)0xD59);
  v21 = HinstDll;
  v14[2] = IconA;
  LoadStringW(v21, 0xCEEu, Buffer, 768);
  CryptUISetRicheditTextW(hDlg, 0x66u, Buffer);
  v22 = GetDlgItem(hDlg, 102);
  CertSubclassEditControlForArrowCursor(v22);
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  v48[0] = 0x10000003CLL;
  v48[1] = 1;
  v23 = GetDlgItem(hDlg, 102);
  SendMessageA(v23, 0x444u, 4u, (LPARAM)v48);
  return 1;
}

```

## disassembly

```asm
0x180009000  mov     [rsp-8+arg_8], rbx
0x180009005  push    rbp
0x180009006  push    rsi
0x180009007  push    rdi
0x180009008  push    r12
0x18000900a  push    r13
0x18000900c  push    r14
0x18000900e  push    r15
0x180009010  lea     rbp, [rsp-680h]
0x180009018  sub     rsp, 780h
0x18000901f  mov     rax, cs:__security_cookie
0x180009026  xor     rax, rsp
0x180009029  mov     [rbp+6B0h+var_40], rax
0x180009030  xorps   xmm0, xmm0
0x180009033  mov     r15, r8
0x180009036  mov     ebx, edx
0x180009038  mov     rdi, rcx
0x18000903b  xor     eax, eax
0x18000903d  lea     rcx, [rsp+7B0h+var_740]; void *
0x180009042  xor     r14d, r14d
0x180009045  mov     [rsp+7B0h+var_748], rax
0x18000904a  xor     edx, edx; Val
0x18000904c  mov     rsi, r9
0x18000904f  movups  xmmword ptr [rsp+7B0h+lParam], xmm0
0x180009054  lea     r12d, [r14+58h]
0x180009058  mov     r8d, r12d; Size
0x18000905b  movups  [rsp+7B0h+var_768], xmm0
0x180009060  movups  [rsp+7B0h+var_758], xmm0
0x180009065  call    memset_0
0x18000906a  xorps   xmm0, xmm0
0x18000906d  movups  xmmword ptr [rbp+6B0h+var_6C0], xmm0
0x180009071  movups  xmmword ptr [rbp+6B0h+var_6C0+0Ch], xmm0
0x180009075  movups  xmmword ptr [rbp+6B0h+var_6E0], xmm0
0x180009079  movups  [rbp+6B0h+var_6D0], xmm0
0x18000907d  cmp     ebx, 110h
0x180009083  jz      short loc_18000909E
0x180009085  lea     edx, [r14+10h]; nIndex
0x180009089  mov     rcx, rdi; hWnd
0x18000908c  call    cs:__imp_GetWindowLongPtrA
0x180009092  mov     r14, rax
0x180009095  test    rax, rax
0x180009098  jz      loc_1800095F2
0x18000909e  sub     ebx, 2
0x1800090a1  jz      loc_180009568
0x1800090a7  sub     ebx, 0Dh
0x1800090aa  jz      loc_1800094CB
0x1800090b0  sub     ebx, 3Fh ; '?'
0x1800090b3  jz      loc_18000934C
0x1800090b9  sub     ebx, 5
0x1800090bc  jz      loc_180009331
0x1800090c2  sub     ebx, 0BDh
0x1800090c8  jz      short loc_1800090E3
0x1800090ca  cmp     ebx, 1
0x1800090cd  jnz     loc_1800095F2
0x1800090d3  cmp     r15w, 9
0x1800090d8  jz      loc_18000946F
0x1800090de  jmp     loc_1800095F2
0x1800090e3  mov     r15, [rsi+30h]
0x1800090e7  mov     edx, 10h; nIndex
0x1800090ec  mov     r8, r15; dwNewLong
0x1800090ef  mov     rcx, rdi; hWnd
0x1800090f2  mov     rax, [r15]
0x1800090f5  mov     r13, [rax+20h]
0x1800090f9  call    cs:__imp_SetWindowLongPtrA
0x1800090ff  lea     r8, Src; unsigned __int16 *
0x180009106  mov     edx, 65h ; 'e'; nIDDlgItem
0x18000910b  mov     rcx, rdi; hDlg
0x18000910e  call    ?CryptUISetRicheditTextW@@YAKPEAUHWND__@@IPEBG@Z; CryptUISetRicheditTextW(HWND__ *,uint,ushort const *)
0x180009113  mov     edx, 64h ; 'd'; nIDDlgItem
0x180009118  mov     rcx, rdi; hDlg
0x18000911b  call    cs:__imp_GetDlgItem
0x180009121  mov     ebx, 1
0x180009126  mov     r12, rax
0x180009129  mov     r9d, ebx
0x18000912c  lea     ecx, [rbx+0Fh]
0x18000912f  mov     edx, ecx
0x180009131  lea     r8d, [rbx+1Fh]
0x180009135  call    IsolationAwareImageList_Create
0x18000913a  mov     r14, rax
0x18000913d  test    rax, rax
0x180009140  jz      short loc_180009184
0x180009142  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180009149  mov     edx, 134h; lpBitmapName
0x18000914e  call    cs:__imp_LoadBitmapA
0x180009154  mov     rsi, rax
0x180009157  test    rax, rax
0x18000915a  jz      short loc_180009184
0x18000915c  mov     rdx, rax
0x18000915f  mov     rcx, r14
0x180009162  call    IsolationAwareImageList_Add
0x180009167  mov     r9, r14; lParam
0x18000916a  mov     r8d, ebx; wParam
0x18000916d  mov     edx, 1003h; Msg
0x180009172  mov     rcx, r12; hWnd
0x180009175  call    cs:__imp_SendMessageA
0x18000917b  mov     rcx, rsi; ho
0x18000917e  call    cs:__imp_DeleteObject
0x180009184  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000918b  lea     rax, [rbp+6B0h+Buffer]
0x18000918f  mov     r14d, 300h
0x180009195  mov     [rsp+7B0h+lParam], 0Fh
0x18000919e  mov     r9d, r14d; cchBufferMax
0x1800091a1  mov     qword ptr [rsp+7B0h+var_768], rax
0x1800091a6  lea     r8, [rbp+6B0h+Buffer]; lpBuffer
0x1800091aa  mov     dword ptr [rsp+7B0h+var_768+0Ch], 0
0x1800091b2  mov     edx, 0C92h; uID
0x1800091b7  mov     dword ptr [rsp+7B0h+lParam+8], 82h
0x1800091bf  call    cs:__imp_LoadStringW
0x1800091c5  mov     esi, 1061h
0x1800091ca  lea     r9, [rsp+7B0h+lParam]; lParam
0x1800091cf  mov     edx, esi; Msg
0x1800091d1  xor     r8d, r8d; wParam
0x1800091d4  mov     rcx, r12; hWnd
0x1800091d7  call    cs:__imp_SendMessageA
0x1800091dd  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800091e4  lea     r8, [rbp+6B0h+Buffer]; lpBuffer
0x1800091e8  mov     r9d, r14d; cchBufferMax
0x1800091eb  mov     dword ptr [rsp+7B0h+lParam+8], 0BEh
0x1800091f3  mov     edx, 0C93h; uID
0x1800091f8  call    cs:__imp_LoadStringW
0x1800091fe  lea     r9, [rsp+7B0h+lParam]; lParam
0x180009203  mov     r8, rbx; wParam
0x180009206  mov     edx, esi; Msg
0x180009208  mov     rcx, r12; hWnd
0x18000920b  call    cs:__imp_SendMessageA
0x180009211  mov     rdx, [r13+18h]
0x180009215  lea     r8, [rsp+7B0h+var_780]
0x18000921a  mov     rcx, r12; hWnd
0x18000921d  mov     [rsp+7B0h+var_780], 0
0x180009225  call    DisplayV1Fields
0x18000922a  mov     rdx, [r13+18h]
0x18000922e  lea     rax, [rsp+7B0h+var_780]
0x180009233  xor     r9d, r9d; int
0x180009236  mov     [rsp+7B0h+var_790], rax; unsigned int *
0x18000923b  mov     rcx, r12; hWnd
0x18000923e  mov     r8, [rdx+58h]; struct _CERT_EXTENSION *
0x180009242  mov     edx, [rdx+50h]; unsigned int
0x180009245  call    ?DisplayExtensions@@YAXPEAUHWND__@@KPEAU_CERT_EXTENSION@@HPEAK@Z; DisplayExtensions(HWND__ *,ulong,_CERT_EXTENSION *,int,ulong *)
0x18000924a  mov     rdx, [r13+18h]
0x18000924e  lea     rax, [rsp+7B0h+var_780]
0x180009253  mov     r9d, ebx; int
0x180009256  mov     [rsp+7B0h+var_790], rax; unsigned int *
0x18000925b  mov     rcx, r12; hWnd
0x18000925e  mov     r8, [rdx+58h]; struct _CERT_EXTENSION *
0x180009262  mov     edx, [rdx+50h]; unsigned int
0x180009265  call    ?DisplayExtensions@@YAXPEAUHWND__@@KPEAU_CERT_EXTENSION@@HPEAK@Z; DisplayExtensions(HWND__ *,ulong,_CERT_EXTENSION *,int,ulong *)
0x18000926a  lea     r8, [rsp+7B0h+var_780]
0x18000926f  mov     rdx, r13; pCrlContext
0x180009272  mov     rcx, r12; hWnd
0x180009275  call    DisplayProperties
0x18000927a  mov     r9d, 20h ; ' '; lParam
0x180009280  lea     edx, [rsi-2Bh]; Msg
0x180009283  xor     r8d, r8d; wParam
0x180009286  mov     rcx, r12; hWnd
0x180009289  call    cs:__imp_SendMessageA
0x18000928f  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180009296  mov     edx, 0D59h; lpIconName
0x18000929b  call    cs:__imp_LoadIconA
0x1800092a1  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800092a8  lea     r8, [rbp+6B0h+Buffer]; lpBuffer
0x1800092ac  mov     r9d, r14d; cchBufferMax
0x1800092af  mov     [r15+10h], rax
0x1800092b3  mov     edx, 0CEEh; uID
0x1800092b8  call    cs:__imp_LoadStringW
0x1800092be  mov     r15d, 66h ; 'f'
0x1800092c4  lea     r8, [rbp+6B0h+Buffer]; unsigned __int16 *
0x1800092c8  mov     edx, r15d; nIDDlgItem
0x1800092cb  mov     rcx, rdi; hDlg
0x1800092ce  call    ?CryptUISetRicheditTextW@@YAKPEAUHWND__@@IPEBG@Z; CryptUISetRicheditTextW(HWND__ *,uint,ushort const *)
0x1800092d3  mov     edx, r15d; nIDDlgItem
0x1800092d6  mov     rcx, rdi; hDlg
0x1800092d9  call    cs:__imp_GetDlgItem
0x1800092df  mov     rcx, rax; hWnd
0x1800092e2  call    ?CertSubclassEditControlForArrowCursor@@YAXPEAUHWND__@@@Z; CertSubclassEditControlForArrowCursor(HWND__ *)
0x1800092e7  xorps   xmm0, xmm0
0x1800092ea  movups  xmmword ptr [rbp+6B0h+var_6E0], xmm0
0x1800092ee  movups  [rbp+6B0h+var_6D0], xmm0
0x1800092f2  movups  xmmword ptr [rbp+6B0h+var_6C0], xmm0
0x1800092f6  mov     edx, r15d; nIDDlgItem
0x1800092f9  mov     dword ptr [rbp+6B0h+var_6E0], 3Ch ; '<'
0x180009300  mov     rcx, rdi; hDlg
0x180009303  mov     dword ptr [rbp+6B0h+var_6E0+4], ebx
0x180009306  movups  xmmword ptr [rbp+6B0h+var_6C0+0Ch], xmm0
0x18000930a  mov     dword ptr [rbp+6B0h+var_6E0+8], ebx
0x18000930d  call    cs:__imp_GetDlgItem
0x180009313  lea     r9, [rbp+6B0h+var_6E0]; lParam
0x180009317  mov     edx, 444h; Msg
0x18000931c  mov     rcx, rax; hWnd
0x18000931f  lea     r8d, [r15-62h]; wParam
0x180009323  call    cs:__imp_SendMessageA
0x180009329  mov     rax, rbx
0x18000932c  jmp     loc_1800095F4
0x180009331  mov     edx, 67h ; 'g'; nIDDlgItem
0x180009336  mov     rcx, rdi; hDlg
0x180009339  call    cs:__imp_GetDlgItem
0x18000933f  mov     rcx, rax; HWND
0x180009342  call    ?InvokeHelpLink@@YAXPEAUHWND__@@@Z; InvokeHelpLink(HWND__ *)
0x180009347  jmp     loc_1800095F2
0x18000934c  mov     eax, [rsi+10h]
0x18000934f  cmp     eax, 0FFFFFF2Fh
0x180009354  jz      loc_1800094BE
0x18000935a  cmp     eax, 0FFFFFF33h
0x18000935f  jz      loc_18000946F
0x180009365  cmp     eax, 0FFFFFF35h
0x18000936a  jz      loc_180009481
0x180009370  cmp     eax, 0FFFFFF36h
0x180009375  jz      loc_180009479
0x18000937b  cmp     eax, 0FFFFFF37h
0x180009380  jz      loc_180009461
0x180009386  cmp     eax, 0FFFFFF9Ch
0x180009389  jz      loc_18000942D
0x18000938f  cmp     eax, 0FFFFFFF9h
0x180009392  jnz     loc_18000948F
0x180009398  cmp     qword ptr [rsi+8], 64h ; 'd'
0x18000939d  jnz     loc_18000948F
0x1800093a3  mov     edx, 64h ; 'd'; nIDDlgItem
0x1800093a8  mov     rcx, rdi; hDlg
0x1800093ab  call    cs:__imp_GetDlgItem
0x1800093b1  xor     r9d, r9d; lParam
0x1800093b4  xor     r8d, r8d; wParam
0x1800093b7  mov     rcx, rax; hWnd
0x1800093ba  mov     edx, 1004h; Msg
0x1800093bf  mov     r14, rax
0x1800093c2  call    cs:__imp_SendMessageA
0x1800093c8  test    eax, eax
0x1800093ca  jz      loc_18000948F
0x1800093d0  mov     r9d, 2; lParam
0x1800093d6  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800093da  mov     edx, 100Ch; Msg
0x1800093df  mov     rcx, r14; hWnd
0x1800093e2  call    cs:__imp_SendMessageA
0x1800093e8  cmp     eax, 0FFFFFFFFh
0x1800093eb  jnz     loc_18000948F
0x1800093f1  mov     r8, r12; Size
0x1800093f4  lea     rcx, [rsp+7B0h+var_740]; void *
0x1800093f9  xor     edx, edx; Val
0x1800093fb  call    memset_0
0x180009400  mov     ebx, 1
0x180009405  mov     [rsp+7B0h+var_740], 8
0x18000940e  lea     r9, [rsp+7B0h+var_740]; lParam
0x180009413  mov     [rsp+7B0h+var_734], ebx
0x180009417  xor     r8d, r8d; wParam
0x18000941a  mov     [rbp+6B0h+var_730], ebx
0x18000941d  mov     edx, 1006h; Msg
0x180009422  mov     rcx, r14; hWnd
0x180009425  call    cs:__imp_SendMessageA
0x18000942b  jmp     short loc_18000948F
0x18000942d  cmp     qword ptr [rsi+8], 64h ; 'd'
0x180009432  jnz     short loc_18000948F
0x180009434  test    byte ptr [rsi+20h], 2
0x180009438  jz      short loc_18000946F
0x18000943a  mov     ebx, [rsi+18h]
0x18000943d  mov     edx, 64h ; 'd'; nIDDlgItem
0x180009442  mov     rcx, rdi; hDlg
0x180009445  call    cs:__imp_GetDlgItem
0x18000944b  mov     r9d, ebx; int
0x18000944e  mov     r8d, 65h ; 'e'; nIDDlgItem
0x180009454  mov     rcx, rax; hWnd
0x180009457  mov     rdx, rdi; hDlg
0x18000945a  call    ?DisplayHelperTextInEdit@@YAXPEAUHWND__@@0HH@Z; DisplayHelperTextInEdit(HWND__ *,HWND__ *,int,int)
0x18000945f  jmp     short loc_18000946F
0x180009461  xor     r8d, r8d; dwNewLong
0x180009464  xor     edx, edx; nIndex
0x180009466  mov     rcx, rdi; hWnd
0x180009469  call    cs:__imp_SetWindowLongPtrA
0x18000946f  mov     eax, 1
0x180009474  jmp     loc_1800095F4
0x180009479  mov     r8d, 1
0x18000947f  jmp     short loc_180009484
0x180009481  xor     r8d, r8d; dwNewLong
0x180009484  xor     edx, edx; nIndex
0x180009486  mov     rcx, rdi; hWnd
0x180009489  call    cs:__imp_SetWindowLongPtrA
0x18000948f  cmp     r15, 67h ; 'g'
0x180009493  jnz     loc_1800095F2
0x180009499  mov     eax, [rsi+10h]
0x18000949c  add     eax, 4
0x18000949f  test    eax, 0FFFFFFFDh
0x1800094a4  jnz     loc_1800095F2
0x1800094aa  lea     rdx, [rsi+88h]; lpParameters
0x1800094b1  mov     rcx, rdi; hwndCaller
0x1800094b4  call    ?DisplayHtmlHelp@@YAXPEAUHWND__@@PEBG@Z; DisplayHtmlHelp(HWND__ *,ushort const *)
0x1800094b9  jmp     loc_1800095F2
0x1800094be  mov     dword ptr [r14+18h], 1
0x1800094c6  jmp     loc_1800095F2
0x1800094cb  xor     edx, edx; Val
0x1800094cd  lea     rcx, [rbp+6B0h+Paint]; void *
0x1800094d1  xorps   xmm0, xmm0
0x1800094d4  movups  xmmword ptr [rbp+6B0h+Rect.left], xmm0
0x1800094d8  lea     r8d, [rdx+48h]; Size
0x1800094dc  call    memset_0
0x1800094e1  xor     r8d, r8d; bErase
0x1800094e4  lea     rdx, [rbp+6B0h+Rect]; lpRect
0x1800094e8  mov     rcx, rdi; hWnd
0x1800094eb  call    cs:__imp_GetUpdateRect
0x1800094f1  test    eax, eax
0x1800094f3  jz      loc_1800095F2
0x1800094f9  lea     rdx, [rbp+6B0h+Paint]; lpPaint
0x1800094fd  mov     rcx, rdi; hWnd
0x180009500  call    cs:__imp_BeginPaint
  ... truncated ...
```
