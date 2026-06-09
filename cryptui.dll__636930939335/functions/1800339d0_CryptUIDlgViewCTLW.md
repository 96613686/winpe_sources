# CryptUIDlgViewCTLW

- ea: `0x1800339d0`
- end: `0x180033cb2`
- name: `CryptUIDlgViewCTLW`
- size: `738`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a160`
- `0x180010de0`
- `0x180033920`

## callees

- `0x180001f66`
- `0x180008904`
- `0x180011860`
- `0x1800333b0`
- `0x1800333f0`
- `0x1800339d0`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033c80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033c80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033a2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033a2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033c77`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180033c0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180033c0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033c55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033c55`
- `CRYPT32!CertOpenStore` at `0x180033a66`
- `CRYPT32!CertOpenStore` at `0x180033a66`
- `CRYPT32!CertCloseStore` at `0x180033c66`
- `CRYPT32!CertCloseStore` at `0x180033c66`
- `USER32!GetDesktopWindow` at `0x180033bbd`
- `USER32!GetDesktopWindow` at `0x180033bbd`

## pseudocode

```c
__int64 __fastcall CryptUIDlgViewCTLW(__int64 a1)
{
  unsigned int v3; // esi
  __int64 v4; // rax
  unsigned int v5; // eax
  PROPSHEETPAGEW_V4 *v6; // rax
  PROPSHEETPAGEW_V4 *v7; // rbx
  HINSTANCE v8; // rsi
  __int64 (__fastcall *v9)(HWND, unsigned int, unsigned __int64, __int64); // rax
  unsigned int v10; // r14d
  UINT v11; // r14d
  HWND DesktopWindow; // rax
  WCHAR *v13; // rax
  int IsCatalogFile; // eax
  UINT v15; // edx
  HMODULE LibraryA; // rsi
  __int64 v17; // rdi
  struct _PROPSHEETHEADERW_V2 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+90h] [rbp-70h] BYREF
  char v20[16]; // [rsp+98h] [rbp-68h] BYREF
  HCERTSTORE hCertStore; // [rsp+A8h] [rbp-58h]
  int v22; // [rsp+E4h] [rbp-1Ch]
  WCHAR Buffer[104]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(&v19, 0, 0x88u);
  if ( !(unsigned int)CommonInit() )
    return 0;
  if ( *(_DWORD *)a1 != 88 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  v3 = 0;
  memset_0(v20, 0, 0x80u);
  v4 = *(_QWORD *)(a1 + 32);
  v19 = a1;
  hCertStore = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, *(const void **)(v4 + 40));
  v5 = *(_DWORD *)(a1 + 72);
  if ( v5 <= 0xFF )
  {
    v6 = (PROPSHEETPAGEW_V4 *)LocalAlloc(0x40u, 104LL * (v5 + 2));
    v7 = v6;
    if ( v6 )
    {
      memset_0(v6, 0, 104LL * (unsigned int)(*(_DWORD *)(a1 + 72) + 2));
      v8 = HinstDll;
      v7->pfnDlgProc = (DLGPROC)ViewPageCTLGeneral;
      v7->lParam = (LPARAM)&v19;
      *(_QWORD *)&v7->dwSize = 104;
      v7->hInstance = v8;
      v7->hIcon = 0;
      v7->pszTitle = 0;
      v7->pfnCallback = 0;
      v7->pcRefParent = 0;
      if ( (unsigned int)fIsCatalogFile((struct _CTL_USAGE *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL)) )
      {
        v7->pszTemplate = (LPCWSTR)160;
        v9 = ViewPageCatalogEntries;
        v7[1].pszTemplate = (LPCWSTR)149;
      }
      else
      {
        v10 = 1;
        v7->pszTemplate = (LPCWSTR)138;
        if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
        {
LABEL_12:
          memcpy_0(&v7[v10], *(const void **)(a1 + 80), 104LL * *(unsigned int *)(a1 + 72));
          v11 = *(_DWORD *)(a1 + 72) + v10;
          memset_0(&v18, 0, sizeof(v18));
          DesktopWindow = *(HWND *)(a1 + 8);
          v18.dwSize = 96;
          v18.dwFlags = 33554824;
          if ( !DesktopWindow )
          {
            DesktopWindow = GetDesktopWindow();
            v8 = HinstDll;
          }
          v18.hwndParent = DesktopWindow;
          v13 = *(WCHAR **)(a1 + 24);
          v18.hInstance = v8;
          v18.hIcon = 0;
          if ( !v13 )
          {
            IsCatalogFile = fIsCatalogFile((struct _CTL_USAGE *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL));
            v15 = 3325;
            if ( !IsCatalogFile )
              v15 = 3251;
            LoadStringW(v8, v15, Buffer, 100);
            v13 = Buffer;
          }
          v18.pszCaption = v13;
          v18.pfnCallback = (PFNPROPSHEETCALLBACK)HidePropSheetCancelButtonCallback;
          v18.nPages = v11;
          v18.nStartPage = 0;
          v18.ppsp = v7;
          LibraryA = IsolationAwareLoadLibraryA();
          if ( LibraryA )
          {
            v17 = CryptUIPropertySheetW(&v18);
            FreeLibrary(LibraryA);
          }
          else
          {
            v17 = 0;
          }
          CertCloseStore(hCertStore, 0);
          if ( v22 )
            SetLastError(0x4C7u);
          LocalFree(v7);
          return v17 >= 1;
        }
        v7[1].pszTemplate = (LPCWSTR)139;
        v9 = ViewPageCTLTrustList;
      }
      v7[1].pfnDlgProc = (DLGPROC)v9;
      v10 = 2;
      v7[1].pcRefParent = 0;
      v7[1].pfnCallback = 0;
      v7[1].lParam = (LPARAM)&v19;
      v7[1].pszTitle = 0;
      v7[1].hIcon = 0;
      v7[1].hInstance = v8;
      *(_QWORD *)&v7[1].dwSize = 104;
      goto LABEL_12;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800339d0  push    rbp
0x1800339d2  push    rbx
0x1800339d3  push    rsi
0x1800339d4  push    rdi
0x1800339d5  push    r12
0x1800339d7  push    r14
0x1800339d9  lea     rbp, [rsp-108h]
0x1800339e1  sub     rsp, 208h
0x1800339e8  mov     rax, cs:__security_cookie
0x1800339ef  xor     rax, rsp
0x1800339f2  mov     [rbp+130h+var_40], rax
0x1800339f9  mov     rdi, rcx
0x1800339fc  xor     edx, edx; Val
0x1800339fe  lea     rcx, [rbp+130h+var_1A0]; void *
0x180033a02  mov     r8d, 88h; Size
0x180033a08  call    memset_0
0x180033a0d  call    CommonInit
0x180033a12  xor     r12d, r12d
0x180033a15  test    eax, eax
0x180033a17  jnz     short loc_180033A20
0x180033a19  xor     eax, eax
0x180033a1b  jmp     loc_180033C93
0x180033a20  cmp     dword ptr [rdi], 58h ; 'X'
0x180033a23  jz      short loc_180033A32
0x180033a25  mov     ecx, 80070057h; dwErrCode
0x180033a2a  call    cs:__imp_SetLastError
0x180033a30  jmp     short loc_180033A19
0x180033a32  xor     edx, edx; Val
0x180033a34  lea     rcx, [rbp+130h+var_198]; void *
0x180033a38  mov     r8d, 80h; Size
0x180033a3e  mov     esi, r12d
0x180033a41  call    memset_0
0x180033a46  mov     rax, [rdi+20h]
0x180033a4a  xor     r9d, r9d; dwFlags
0x180033a4d  mov     [rbp+130h+var_1A0], rdi
0x180033a51  xor     r8d, r8d; hCryptProv
0x180033a54  mov     edx, 10001h; dwEncodingType
0x180033a59  mov     rcx, [rax+28h]
0x180033a5d  mov     [rsp+230h+pvPara], rcx; pvPara
0x180033a62  lea     ecx, [r9+1]; lpszStoreProvider
0x180033a66  call    cs:__imp_CertOpenStore
0x180033a6c  mov     [rbp+130h+hCertStore], rax
0x180033a70  mov     eax, [rdi+48h]
0x180033a73  cmp     eax, 0FFh
0x180033a78  ja      loc_180033C91
0x180033a7e  lea     ecx, [rax+2]
0x180033a81  imul    rdx, rcx, 68h ; 'h'; uBytes
0x180033a85  mov     ecx, 40h ; '@'; uFlags
0x180033a8a  call    cs:__imp_LocalAlloc
0x180033a90  mov     rbx, rax
0x180033a93  test    rax, rax
0x180033a96  jz      loc_180033C91
0x180033a9c  mov     ecx, [rdi+48h]
0x180033a9f  xor     edx, edx; Val
0x180033aa1  add     ecx, 2
0x180033aa4  imul    r8, rcx, 68h ; 'h'; Size
0x180033aa8  mov     rcx, rax; void *
0x180033aab  call    memset_0
0x180033ab0  mov     rsi, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180033ab7  lea     rax, ?ViewPageCTLGeneral@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageCTLGeneral(HWND__ *,uint,unsigned __int64,__int64)
0x180033abe  mov     [rbx+28h], rax
0x180033ac2  lea     rax, [rbp+130h+var_1A0]
0x180033ac6  mov     [rbx+30h], rax
0x180033aca  mov     qword ptr [rbx], 68h ; 'h'
0x180033ad1  mov     [rbx+8], rsi
0x180033ad5  mov     [rbx+18h], r12
0x180033ad9  mov     [rbx+20h], r12
0x180033add  mov     [rbx+38h], r12
0x180033ae1  mov     [rbx+40h], r12
0x180033ae5  mov     rax, [rdi+20h]
0x180033ae9  mov     rcx, [rax+18h]
0x180033aed  add     rcx, 8; struct _CTL_USAGE *
0x180033af1  call    ?fIsCatalogFile@@YAHPEAU_CTL_USAGE@@@Z; fIsCatalogFile(_CTL_USAGE *)
0x180033af6  test    eax, eax
0x180033af8  jz      short loc_180033B13
0x180033afa  mov     qword ptr [rbx+10h], 0A0h
0x180033b02  lea     rax, ?ViewPageCatalogEntries@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageCatalogEntries(HWND__ *,uint,unsigned __int64,__int64)
0x180033b09  mov     qword ptr [rbx+78h], 95h
0x180033b11  jmp     short loc_180033B36
0x180033b13  mov     r14d, 1
0x180033b19  mov     qword ptr [rbx+10h], 8Ah
0x180033b21  test    [rdi+10h], r14b
0x180033b25  jnz     short loc_180033B76
0x180033b27  mov     qword ptr [rbx+78h], 8Bh
0x180033b2f  lea     rax, ?ViewPageCTLTrustList@@YA_JPEAUHWND__@@I_K_J@Z; ViewPageCTLTrustList(HWND__ *,uint,unsigned __int64,__int64)
0x180033b36  mov     [rbx+90h], rax
0x180033b3d  mov     r14d, 2
0x180033b43  mov     [rbx+0A8h], r12
0x180033b4a  lea     rax, [rbp+130h+var_1A0]
0x180033b4e  mov     [rbx+0A0h], r12
0x180033b55  mov     [rbx+98h], rax
0x180033b5c  mov     [rbx+88h], r12
0x180033b63  mov     [rbx+80h], r12
0x180033b6a  mov     [rbx+70h], rsi
0x180033b6e  mov     qword ptr [rbx+68h], 68h ; 'h'
0x180033b76  mov     eax, [rdi+48h]
0x180033b79  mov     rdx, [rdi+50h]; Src
0x180033b7d  imul    r8, rax, 68h ; 'h'; Size
0x180033b81  mov     eax, r14d
0x180033b84  imul    rcx, rax, 68h ; 'h'
0x180033b88  add     rcx, rbx; void *
0x180033b8b  call    memcpy_0
0x180033b90  add     r14d, [rdi+48h]
0x180033b94  lea     rcx, [rsp+230h+var_200]; void *
0x180033b99  xor     edx, edx; Val
0x180033b9b  lea     r8d, [rdx+60h]; Size
0x180033b9f  call    memset_0
0x180033ba4  mov     rax, [rdi+8]
0x180033ba8  mov     [rsp+230h+var_200.dwSize], 60h ; '`'
0x180033bb0  mov     [rsp+230h+var_200.dwFlags], 2000188h
0x180033bb8  test    rax, rax
0x180033bbb  jnz     short loc_180033BCA
0x180033bbd  call    cs:__imp_GetDesktopWindow
0x180033bc3  mov     rsi, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180033bca  mov     [rsp+230h+var_200.hwndParent], rax
0x180033bcf  mov     rax, [rdi+18h]
0x180033bd3  mov     [rsp+230h+var_200.hInstance], rsi
0x180033bd8  mov     qword ptr [rsp+230h+var_200.18h], r12
0x180033bdd  test    rax, rax
0x180033be0  jnz     short loc_180033C18
0x180033be2  mov     rax, [rdi+20h]
0x180033be6  mov     rcx, [rax+18h]
0x180033bea  add     rcx, 8; struct _CTL_USAGE *
0x180033bee  call    ?fIsCatalogFile@@YAHPEAU_CTL_USAGE@@@Z; fIsCatalogFile(_CTL_USAGE *)
0x180033bf3  lea     r8, [rbp+130h+Buffer]; lpBuffer
0x180033bf7  mov     r9d, 64h ; 'd'; cchBufferMax
0x180033bfd  mov     rcx, rsi; hInstance
0x180033c00  mov     edx, 0CFDh
0x180033c05  test    eax, eax
0x180033c07  jnz     short loc_180033C0E
0x180033c09  mov     edx, 0CB3h; uID
0x180033c0e  call    cs:__imp_LoadStringW
0x180033c14  lea     rax, [rbp+130h+Buffer]
0x180033c18  mov     [rsp+230h+var_200.pszCaption], rax
0x180033c1d  lea     rax, ?HidePropSheetCancelButtonCallback@@YAHPEAUHWND__@@I_J@Z; HidePropSheetCancelButtonCallback(HWND__ *,uint,__int64)
0x180033c24  mov     [rsp+230h+var_200.pfnCallback], rax
0x180033c29  mov     [rsp+230h+var_200.nPages], r14d
0x180033c2e  mov     dword ptr [rsp+230h+var_200.30h], r12d
0x180033c33  mov     qword ptr [rsp+230h+var_200.38h], rbx
0x180033c38  call    IsolationAwareLoadLibraryA
0x180033c3d  mov     rsi, rax
0x180033c40  test    rax, rax
0x180033c43  jz      short loc_180033C5D
0x180033c45  lea     rcx, [rsp+230h+var_200]; struct _PROPSHEETHEADERW_V2 *
0x180033c4a  call    ?CryptUIPropertySheetW@@YA_JPEBU_PROPSHEETHEADERW_V2@@@Z; CryptUIPropertySheetW(_PROPSHEETHEADERW_V2 const *)
0x180033c4f  mov     rcx, rsi; hLibModule
0x180033c52  mov     rdi, rax
0x180033c55  call    cs:__imp_FreeLibrary
0x180033c5b  jmp     short loc_180033C60
0x180033c5d  mov     rdi, r12
0x180033c60  mov     rcx, [rbp+130h+hCertStore]; hCertStore
0x180033c64  xor     edx, edx; dwFlags
0x180033c66  call    cs:__imp_CertCloseStore
0x180033c6c  cmp     [rbp+130h+var_14C], r12d
0x180033c70  jz      short loc_180033C7D
0x180033c72  mov     ecx, 4C7h; dwErrCode
0x180033c77  call    cs:__imp_SetLastError
0x180033c7d  mov     rcx, rbx; hMem
0x180033c80  call    cs:__imp_LocalFree
0x180033c86  cmp     rdi, 1
0x180033c8a  mov     esi, r12d
0x180033c8d  setnl   sil
0x180033c91  mov     eax, esi
0x180033c93  mov     rcx, [rbp+130h+var_40]
0x180033c9a  xor     rcx, rsp; StackCookie
0x180033c9d  call    __security_check_cookie
0x180033ca2  add     rsp, 208h
0x180033ca9  pop     r14
0x180033cab  pop     r12
0x180033cad  pop     rdi
0x180033cae  pop     rsi
0x180033caf  pop     rbx
0x180033cb0  pop     rbp
0x180033cb1  retn
```
