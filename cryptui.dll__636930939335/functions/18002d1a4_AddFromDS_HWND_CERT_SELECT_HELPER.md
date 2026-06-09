# AddFromDS(HWND__ *,_CERT_SELECT_HELPER *)

- ea: `0x18002d1a4`
- end: `0x18002d73a`
- name: `?AddFromDS@@YAJPEAUHWND__@@PEAU_CERT_SELECT_HELPER@@@Z`
- size: `1430`
- prototype: `__int64 __fastcall(HWND, struct _CERT_SELECT_HELPER *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d1a4`
- `0x18002d840`

## callees

- `0x18000c754`
- `0x18000df7c`
- `0x18002cc88`
- `0x18002d1a4`
- `0x18002d740`
- `0x18002e498`
- `0x18003e582`
- `0x18003e5c0`
- `0x18003e680`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d68f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d68f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d553`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d607`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d65c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d553`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d607`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d65c`
- `CRYPT32!CertOpenStore` at `0x18002d43d`
- `CRYPT32!CertOpenStore` at `0x18002d43d`
- `CRYPT32!CertCloseStore` at `0x18002d6a1`
- `CRYPT32!CertCloseStore` at `0x18002d6a1`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18002d45d`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18002d45d`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d6af`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d6af`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d63c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d63c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002d6be`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002d6be`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002d39d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002d39d`
- `USER32!SendMessageA` at `0x18002d4fa`
- `USER32!SendMessageA` at `0x18002d4fa`
- `USER32!MessageBoxW` at `0x18002d595`
- `USER32!MessageBoxW` at `0x18002d67b`
- `USER32!MessageBoxW` at `0x18002d595`
- `USER32!MessageBoxW` at `0x18002d67b`
- `USER32!GetDlgItem` at `0x18002d27e`
- `USER32!GetDlgItem` at `0x18002d27e`
- `USER32!RegisterClipboardFormatA` at `0x18002d202`
- `USER32!RegisterClipboardFormatA` at `0x18002d202`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d701`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d701`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d2ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d2ae`
- `ole32!ReleaseStgMedium` at `0x18002d6cf`
- `ole32!ReleaseStgMedium` at `0x18002d6cf`
- `ole32!CoInitialize` at `0x18002d28b`
- `ole32!CoInitialize` at `0x18002d28b`

## pseudocode

```c
__int64 __fastcall AddFromDS(HWND a1, struct _CERT_SELECT_HELPER *a2)
{
  unsigned int v3; // edi
  _QWORD *v5; // r13
  LPCWSTR v6; // r12
  PCCERT_CONTEXT v7; // rsi
  signed int v8; // ebx
  int v9; // eax
  int v10; // ebx
  const unsigned __int16 *v11; // r8
  __int64 v12; // rax
  HCERTSTORE v13; // rax
  unsigned int (__fastcall *v14)(PCCERT_CONTEXT, int *, _QWORD); // rax
  WPARAM v15; // r12
  WCHAR *v16; // r8
  signed int v17; // eax
  HCERTSTORE v18; // rcx
  signed int LastError; // eax
  WCHAR v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+4Ch] [rbp-B4h]
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-B0h]
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  HWND hWnd; // [rsp+70h] [rbp-90h]
  STGMEDIUM v29; // [rsp+78h] [rbp-88h] BYREF
  __int16 v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+92h] [rbp-6Eh]
  __int16 v32; // [rsp+96h] [rbp-6Ah]
  __int64 v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A4h] [rbp-5Ch]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  CertContextList *v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v39; // [rsp+C8h] [rbp-38h]
  __int128 v40; // [rsp+D8h] [rbp-28h]
  LPARAM lParam; // [rsp+F0h] [rbp-10h] BYREF
  int v42; // [rsp+FCh] [rbp-4h]
  int v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+150h] [rbp+50h] BYREF
  __int64 v45; // [rsp+154h] [rbp+54h]
  int v46; // [rsp+15Ch] [rbp+5Ch]
  __int128 v47; // [rsp+160h] [rbp+60h]
  __int128 v48; // [rsp+170h] [rbp+70h]
  __int64 v49; // [rsp+180h] [rbp+80h]
  WCHAR Buffer[512]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR Caption[512]; // [rsp+590h] [rbp+490h] BYREF
  WCHAR v52[512]; // [rsp+990h] [rbp+890h] BYREF
  WCHAR v53[512]; // [rsp+D90h] [rbp+C90h] BYREF
  unsigned __int16 pvPara[2048]; // [rsp+1190h] [rbp+1090h] BYREF

  v3 = 0;
  ppv = 0;
  v27 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v33 = 0;
  v30 = RegisterClipboardFormatA("CFSTR_DSOP_DS_SELECTION_LIST");
  *(_QWORD *)&v29.tymed = 1;
  v31 = 0;
  v32 = 0;
  v34 = 1;
  v35 = -1;
  v36 = 1;
  v22 = 0;
  *(_OWORD *)&v29.hBitmap = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  v5 = *(_QWORD **)a2;
  if ( !*(_QWORD *)a2 )
    return 2147942487LL;
  v37 = (CertContextList *)*((_QWORD *)a2 + 6);
  if ( !v37 )
    return 2147942487LL;
  v23 = 0;
  hCertStore = 0;
  v6 = 0;
  v7 = 0;
  hWnd = GetDlgItem(a1, 100);
  CoInitialize(0);
  v8 = CoCreateInstance(&CLSID_DsObjectPicker, 0, 1u, &IID_IDsObjectPicker, &ppv);
  if ( v8 < 0 )
    goto LABEL_40;
  if ( !ppv )
    goto LABEL_40;
  v38 = 0x30u;
  v49 = 0;
  v44 = 56;
  v47 = 0;
  *((_QWORD *)&v39 + 1) = &v44;
  v48 = 0;
  v45 = 14;
  v46 = 2;
  DWORD2(v47) = -2147483647;
  *(_QWORD *)&v39 = 1;
  v40 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 24LL))(ppv, &v38);
  if ( v8 < 0 )
    goto LABEL_40;
  v9 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, a1, &v27);
  v8 = v9;
  if ( v9 < 0 )
    goto LABEL_40;
  if ( v9 != 1 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int16 *, STGMEDIUM *))(*(_QWORD *)v27 + 24LL))(v27, &v30, &v29);
    if ( v8 >= 0 )
    {
      v23 = 1;
      *(_QWORD *)v21 = GlobalLock(v29.hBitmap);
      v6 = *(LPCWSTR *)v21;
      if ( *(_QWORD *)v21 )
      {
        while ( 2 )
        {
          if ( v3 >= *(_DWORD *)v6 )
          {
            v8 = 0;
            goto LABEL_46;
          }
          v10 = 0;
          v26 = 0;
          v11 = *(const unsigned __int16 **)&v6[24 * v3 + 8];
          if ( !v11 )
            goto LABEL_18;
          v12 = -1;
          do
            ++v12;
          while ( v11[v12] );
          if ( (unsigned int)(v12 + 17) > 0x800 )
          {
            v8 = -2147418113;
          }
          else
          {
LABEL_18:
            StringCchCopyW(pvPara, 0x800u, v11);
            StringCchCatW(pvPara, 0x800u, L"?userCertificate");
            v13 = CertOpenStore("Ldap", 0x10001u, 0, 0x8000u, pvPara);
            hCertStore = v13;
            if ( v13 )
            {
              v7 = 0;
              while ( 1 )
              {
                v7 = CertEnumCertificatesInStore(v13, v7);
                if ( !v7 )
                  break;
                v14 = (unsigned int (__fastcall *)(PCCERT_CONTEXT, int *, _QWORD))v5[6];
                if ( v14 && v14(v7, &v22, v5[8]) || (unsigned int)SupportEncryptedFileSystem(v7) )
                {
                  v8 = CertContextList::Add(v37, v7, &v26);
                  if ( v8 )
                  {
                    v6 = *(LPCWSTR *)v21;
                    goto LABEL_40;
                  }
                  v10 = 1;
                  v15 = (int)ReplaceCertInList(hWnd);
                  if ( v22 )
                  {
                    memset_0(&lParam, 0, 0x58u);
                    v43 = 2;
                    v42 = 2;
                    SendMessageA(hWnd, 0x102Bu, v15, (LPARAM)&lParam);
                  }
                }
                v13 = hCertStore;
              }
              if ( GetLastError() != -2146885628 )
              {
                v6 = *(LPCWSTR *)v21;
                goto LABEL_36;
              }
              if ( v10 )
              {
                v6 = *(LPCWSTR *)v21;
                ++v3;
                continue;
              }
              LoadStringW(HinstDll, 0xD45u, Buffer, 512);
              v16 = (WCHAR *)v5[3];
              if ( !v16 )
              {
                LoadStringW(HinstDll, 0xCFAu, Caption, 512);
                v16 = Caption;
              }
              MessageBoxW(a1, Buffer, v16, 0x30u);
              v17 = AddFromDS(a1, a2);
              v18 = hCertStore;
              v8 = v17;
              v6 = *(LPCWSTR *)v21;
              goto LABEL_47;
            }
LABEL_36:
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          break;
        }
      }
    }
LABEL_40:
    *(_QWORD *)v21 = 0;
    if ( LoadStringW(HinstDll, 0xCE9u, v53, 512)
      && FormatMessageW(0x1300u, 0, v8, 0x400u, v21, 0, 0)
      && LoadStringW(HinstDll, 0xCFAu, v52, 512) )
    {
      MessageBoxW(a1, *(LPCWSTR *)v21, v52, 0x10u);
    }
    if ( *(_QWORD *)v21 )
      LocalFree(*(HLOCAL *)v21);
LABEL_46:
    v18 = hCertStore;
    if ( !hCertStore )
    {
LABEL_48:
      if ( v7 )
        CertFreeCertificateContext(v7);
      if ( v6 )
        GlobalUnlock(v29.hBitmap);
      if ( v23 )
        ReleaseStgMedium(&v29);
      goto LABEL_54;
    }
LABEL_47:
    CertCloseStore(v18, 0);
    goto LABEL_48;
  }
  v8 = -2147467260;
LABEL_54:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CoUninitialize();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002d1a4  mov     [rsp-8+arg_10], rbx
0x18002d1a9  push    rbp
0x18002d1aa  push    rsi
0x18002d1ab  push    rdi
0x18002d1ac  push    r12
0x18002d1ae  push    r13
0x18002d1b0  push    r14
0x18002d1b2  push    r15
0x18002d1b4  lea     rbp, [rsp-20A0h]
0x18002d1bc  mov     eax, 21A0h
0x18002d1c1  call    _alloca_probe
0x18002d1c6  sub     rsp, rax
0x18002d1c9  mov     rax, cs:__security_cookie
0x18002d1d0  xor     rax, rsp
0x18002d1d3  mov     [rbp+20D0h+var_40], rax
0x18002d1da  xorps   xmm0, xmm0
0x18002d1dd  mov     r15, rcx
0x18002d1e0  xor     edi, edi
0x18002d1e2  lea     rcx, szFormat; "CFSTR_DSOP_DS_SELECTION_LIST"
0x18002d1e9  mov     [rsp+21D0h+var_2178], rdi
0x18002d1ee  mov     r14, rdx
0x18002d1f1  mov     [rsp+21D0h+var_2168], rdi
0x18002d1f6  movups  [rbp+20D0h+var_2118], xmm0
0x18002d1fa  movups  [rbp+20D0h+var_2108], xmm0
0x18002d1fe  movups  [rbp+20D0h+var_20F8], xmm0
0x18002d202  call    cs:__imp_RegisterClipboardFormatA
0x18002d208  lea     ebx, [rdi+1]
0x18002d20b  mov     [rbp+20D0h+var_2138], rdi
0x18002d20f  mov     [rbp+20D0h+var_2140], ax
0x18002d213  xorps   xmm0, xmm0
0x18002d216  xor     eax, eax
0x18002d218  mov     qword ptr [rsp+21D0h+var_2158.tymed], rbx
0x18002d21d  mov     [rbp+20D0h+var_213E], eax
0x18002d220  mov     [rbp+20D0h+var_213A], ax
0x18002d224  mov     [rbp+20D0h+var_2130], ebx
0x18002d227  mov     [rbp+20D0h+var_212C], 0FFFFFFFFh
0x18002d22e  mov     [rbp+20D0h+var_2128], rbx
0x18002d232  mov     [rsp+21D0h+var_2188], edi
0x18002d236  movdqu  xmmword ptr [rbp+20D0h+var_2158.8], xmm0
0x18002d23b  test    r15, r15
0x18002d23e  jz      loc_18002D70B
0x18002d244  test    r14, r14
0x18002d247  jz      loc_18002D70B
0x18002d24d  mov     r13, [r14]
0x18002d250  test    r13, r13
0x18002d253  jz      loc_18002D70B
0x18002d259  mov     rax, [r14+30h]
0x18002d25d  mov     [rbp+20D0h+var_2120], rax
0x18002d261  test    rax, rax
0x18002d264  jz      loc_18002D70B
0x18002d26a  lea     edx, [rdi+64h]; nIDDlgItem
0x18002d26d  mov     [rsp+21D0h+var_2184], edi
0x18002d271  mov     rcx, r15; hDlg
0x18002d274  mov     [rsp+21D0h+hCertStore], rdi
0x18002d279  mov     r12d, edi
0x18002d27c  mov     esi, edi
0x18002d27e  call    cs:__imp_GetDlgItem
0x18002d284  xor     ecx, ecx; pvReserved
0x18002d286  mov     [rsp+21D0h+hWnd], rax
0x18002d28b  call    cs:__imp_CoInitialize
0x18002d291  lea     rax, [rsp+21D0h+var_2178]
0x18002d296  mov     r8d, ebx; dwClsContext
0x18002d299  lea     r9, IID_IDsObjectPicker; riid
0x18002d2a0  mov     [rsp+21D0h+ppv], rax; ppv
0x18002d2a5  xor     edx, edx; pUnkOuter
0x18002d2a7  lea     rcx, CLSID_DsObjectPicker; rclsid
0x18002d2ae  call    cs:__imp_CoCreateInstance
0x18002d2b4  mov     ebx, eax
0x18002d2b6  test    eax, eax
0x18002d2b8  js      loc_18002D5E7
0x18002d2be  mov     rcx, [rsp+21D0h+var_2178]
0x18002d2c3  test    rcx, rcx
0x18002d2c6  jz      loc_18002D5E7
0x18002d2cc  xor     eax, eax
0x18002d2ce  mov     qword ptr [rbp+20D0h+var_2118], 30h ; '0'
0x18002d2d6  xorps   xmm0, xmm0
0x18002d2d9  mov     [rbp+20D0h+var_2050], rax
0x18002d2e0  movups  [rbp+20D0h+var_2080], xmm0
0x18002d2e4  lea     rax, [rbp+20D0h+var_2080]
0x18002d2e8  mov     dword ptr [rbp+20D0h+var_2080], 38h ; '8'
0x18002d2ef  movups  [rbp+20D0h+var_2070], xmm0
0x18002d2f3  mov     qword ptr [rbp+20D0h+var_2108+8], rax
0x18002d2f7  lea     rdx, [rbp+20D0h+var_2118]
0x18002d2fb  movups  [rbp+20D0h+var_2060], xmm0
0x18002d2ff  mov     dword ptr [rbp+20D0h+var_2080+4], 0Eh
0x18002d306  mov     dword ptr [rbp+20D0h+var_2080+0Ch], 2
0x18002d30d  mov     dword ptr [rbp+20D0h+var_2070+8], 80000001h
0x18002d314  mov     qword ptr [rbp+20D0h+var_2108], 1
0x18002d31c  movdqu  [rbp+20D0h+var_20F8], xmm0
0x18002d321  mov     qword ptr [rbp+20D0h+var_2118+8], rdi
0x18002d325  mov     rax, [rcx]
0x18002d328  mov     rax, [rax+18h]
0x18002d32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d331  mov     ebx, eax
0x18002d333  test    eax, eax
0x18002d335  js      loc_18002D5E7
0x18002d33b  mov     rcx, [rsp+21D0h+var_2178]
0x18002d340  lea     r8, [rsp+21D0h+var_2168]
0x18002d345  mov     rdx, r15
0x18002d348  mov     rax, [rcx]
0x18002d34b  mov     rax, [rax+20h]
0x18002d34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d354  mov     ebx, eax
0x18002d356  test    eax, eax
0x18002d358  js      loc_18002D5E7
0x18002d35e  cmp     eax, 1
0x18002d361  jnz     short loc_18002D36D
0x18002d363  mov     ebx, 80004004h
0x18002d368  jmp     loc_18002D6D5
0x18002d36d  mov     rcx, [rsp+21D0h+var_2168]
0x18002d372  lea     r8, [rsp+21D0h+var_2158]
0x18002d377  lea     rdx, [rbp+20D0h+var_2140]
0x18002d37b  mov     rax, [rcx]
0x18002d37e  mov     rax, [rax+18h]
0x18002d382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d387  mov     ebx, eax
0x18002d389  test    eax, eax
0x18002d38b  js      loc_18002D5E7
0x18002d391  mov     rcx, qword ptr [rbp+20D0h+var_2158.8]; hMem
0x18002d395  mov     [rsp+21D0h+var_2184], 1
0x18002d39d  call    cs:__imp_GlobalLock
0x18002d3a3  mov     qword ptr [rsp+21D0h+var_2190], rax
0x18002d3a8  mov     r12, rax
0x18002d3ab  test    rax, rax
0x18002d3ae  jz      loc_18002D5E7
0x18002d3b4  cmp     edi, [r12]
0x18002d3b8  jnb     loc_18002D5D7
0x18002d3be  xor     ebx, ebx
0x18002d3c0  mov     eax, edi
0x18002d3c2  mov     [rsp+21D0h+var_2170], ebx
0x18002d3c6  lea     rcx, [rax+rax*2]
0x18002d3ca  add     rcx, rcx
0x18002d3cd  mov     r8, [r12+rcx*8+10h]; unsigned __int16 *
0x18002d3d2  test    r8, r8
0x18002d3d5  jz      short loc_18002D3F3
0x18002d3d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d3db  inc     rax
0x18002d3de  cmp     [r8+rax*2], bx
0x18002d3e3  jnz     short loc_18002D3DB
0x18002d3e5  add     eax, 11h
0x18002d3e8  cmp     eax, 800h
0x18002d3ed  ja      loc_18002D52E
0x18002d3f3  mov     edx, 800h; unsigned __int64
0x18002d3f8  lea     rcx, [rbp+20D0h+pvPara]; unsigned __int16 *
0x18002d3ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d404  lea     r8, aUsercertificat; "?userCertificate"
0x18002d40b  mov     edx, 800h; unsigned __int64
0x18002d410  lea     rcx, [rbp+20D0h+pvPara]; unsigned __int16 *
0x18002d417  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d41c  lea     rax, [rbp+20D0h+pvPara]
0x18002d423  mov     r9d, 8000h; dwFlags
0x18002d429  xor     r8d, r8d; hCryptProv
0x18002d42c  mov     [rsp+21D0h+ppv], rax; pvPara
0x18002d431  mov     edx, 10001h; dwEncodingType
0x18002d436  lea     rcx, szStoreProvider; "Ldap"
0x18002d43d  call    cs:__imp_CertOpenStore
0x18002d443  mov     [rsp+21D0h+hCertStore], rax
0x18002d448  test    rax, rax
0x18002d44b  jz      loc_18002D5BE
0x18002d451  xor     r12d, r12d
0x18002d454  mov     esi, r12d
0x18002d457  mov     rdx, rsi; pPrevCertContext
0x18002d45a  mov     rcx, rax; hCertStore
0x18002d45d  call    cs:__imp_CertEnumCertificatesInStore
0x18002d463  mov     rsi, rax
0x18002d466  test    rax, rax
0x18002d469  jz      loc_18002D50D
0x18002d46f  mov     rax, [r13+30h]
0x18002d473  test    rax, rax
0x18002d476  jz      short loc_18002D48D
0x18002d478  mov     r8, [r13+40h]
0x18002d47c  lea     rdx, [rsp+21D0h+var_2188]
0x18002d481  mov     rcx, rsi
0x18002d484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d489  test    eax, eax
0x18002d48b  jnz     short loc_18002D499
0x18002d48d  mov     rcx, rsi; pCertContext
0x18002d490  call    ?SupportEncryptedFileSystem@@YAHPEBU_CERT_CONTEXT@@@Z; SupportEncryptedFileSystem(_CERT_CONTEXT const *)
0x18002d495  test    eax, eax
0x18002d497  jz      short loc_18002D503
0x18002d499  mov     rcx, [rbp+20D0h+var_2120]; this
0x18002d49d  lea     r8, [rsp+21D0h+var_2170]; int *
0x18002d4a2  mov     rdx, rsi; struct _CERT_CONTEXT *
0x18002d4a5  call    ?Add@CertContextList@@QEAAJPEBU_CERT_CONTEXT@@PEAH@Z; CertContextList::Add(_CERT_CONTEXT const *,int *)
0x18002d4aa  mov     ebx, eax
0x18002d4ac  test    eax, eax
0x18002d4ae  jnz     loc_18002D5E0
0x18002d4b4  mov     rcx, [rsp+21D0h+hWnd]; hWnd
0x18002d4b9  lea     ebx, [rax+1]
0x18002d4bc  mov     r8, rsi
0x18002d4bf  mov     rdx, r14
0x18002d4c2  call    ReplaceCertInList
0x18002d4c7  cmp     [rsp+21D0h+var_2188], 0
0x18002d4cc  movsxd  r12, eax
0x18002d4cf  jz      short loc_18002D500
0x18002d4d1  xor     edx, edx; Val
0x18002d4d3  lea     r8d, [rbx+57h]; Size
0x18002d4d7  lea     rcx, [rbp+20D0h+lParam]; void *
0x18002d4db  call    memset_0
0x18002d4e0  mov     rcx, [rsp+21D0h+hWnd]; hWnd
0x18002d4e5  lea     eax, [rbx+1]
0x18002d4e8  mov     r8, r12; wParam
0x18002d4eb  mov     [rbp+20D0h+var_20D0], eax
0x18002d4ee  lea     r9, [rbp+20D0h+lParam]; lParam
0x18002d4f2  mov     [rbp+20D0h+var_20D4], eax
0x18002d4f5  mov     edx, 102Bh; Msg
0x18002d4fa  call    cs:__imp_SendMessageA
0x18002d500  xor     r12d, r12d
0x18002d503  mov     rax, [rsp+21D0h+hCertStore]
0x18002d508  jmp     loc_18002D457
0x18002d50d  call    cs:__imp_GetLastError
0x18002d513  cmp     eax, 80092004h
0x18002d518  jnz     loc_18002D5B9
0x18002d51e  test    ebx, ebx
0x18002d520  jz      short loc_18002D538
0x18002d522  mov     r12, qword ptr [rsp+21D0h+var_2190]
0x18002d527  inc     edi
0x18002d529  jmp     loc_18002D3B4
0x18002d52e  mov     ebx, 8000FFFFh
0x18002d533  jmp     loc_18002D5E5
0x18002d538  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18002d53f  lea     r8, [rbp+20D0h+Buffer]; lpBuffer
0x18002d546  mov     edi, 200h
0x18002d54b  mov     edx, 0D45h; uID
0x18002d550  mov     r9d, edi; cchBufferMax
0x18002d553  call    cs:__imp_LoadStringW
0x18002d559  mov     r8, [r13+18h]
0x18002d55d  test    r8, r8
0x18002d560  jnz     short loc_18002D585
0x18002d562  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18002d569  lea     r8, [rbp+20D0h+Caption]; lpBuffer
0x18002d570  mov     r9d, edi; cchBufferMax
0x18002d573  mov     edx, 0CFAh; uID
0x18002d578  call    cs:__imp_LoadStringW
0x18002d57e  lea     r8, [rbp+20D0h+Caption]; lpCaption
0x18002d585  mov     r9d, 30h ; '0'; uType
0x18002d58b  lea     rdx, [rbp+20D0h+Buffer]; lpText
0x18002d592  mov     rcx, r15; hWnd
0x18002d595  call    cs:__imp_MessageBoxW
0x18002d59b  mov     rdx, r14; struct _CERT_SELECT_HELPER *
0x18002d59e  mov     rcx, r15; HWND
0x18002d5a1  call    ?AddFromDS@@YAJPEAUHWND__@@PEAU_CERT_SELECT_HELPER@@@Z; AddFromDS(HWND__ *,_CERT_SELECT_HELPER *)
0x18002d5a6  mov     rcx, [rsp+21D0h+hCertStore]
0x18002d5ab  mov     ebx, eax
0x18002d5ad  mov     r12, qword ptr [rsp+21D0h+var_2190]
0x18002d5b2  xor     edi, edi
0x18002d5b4  jmp     loc_18002D69F
0x18002d5b9  mov     r12, qword ptr [rsp+21D0h+var_2190]
0x18002d5be  call    cs:__imp_GetLastError
0x18002d5c4  xor     edi, edi
0x18002d5c6  mov     ebx, eax
0x18002d5c8  test    eax, eax
0x18002d5ca  jle     short loc_18002D5E7
0x18002d5cc  movzx   ebx, ax
0x18002d5cf  or      ebx, 80070000h
0x18002d5d5  jmp     short loc_18002D5E7
0x18002d5d7  xor     edi, edi
0x18002d5d9  mov     ebx, edi
0x18002d5db  jmp     loc_18002D695
0x18002d5e0  mov     r12, qword ptr [rsp+21D0h+var_2190]
0x18002d5e5  xor     edi, edi
0x18002d5e7  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18002d5ee  lea     r8, [rbp+20D0h+var_1440]; lpBuffer
0x18002d5f5  mov     qword ptr [rsp+21D0h+var_2190], rdi
0x18002d5fa  mov     edx, 0CE9h; uID
0x18002d5ff  mov     edi, 200h
0x18002d604  mov     r9d, edi; cchBufferMax
0x18002d607  call    cs:__imp_LoadStringW
0x18002d60d  test    eax, eax
0x18002d60f  jz      short loc_18002D683
0x18002d611  mov     [rsp+21D0h+Arguments], 0; Arguments
0x18002d61a  lea     rax, [rsp+21D0h+var_2190]
0x18002d61f  mov     [rsp+21D0h+nSize], 0; nSize
0x18002d627  mov     r9d, 400h; dwLanguageId
0x18002d62d  mov     r8d, ebx; dwMessageId
0x18002d630  mov     [rsp+21D0h+ppv], rax; lpBuffer
0x18002d635  xor     edx, edx; lpSource
0x18002d637  mov     ecx, 1300h; dwFlags
0x18002d63c  call    cs:__imp_FormatMessageW
0x18002d642  test    eax, eax
0x18002d644  jz      short loc_18002D683
0x18002d646  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18002d64d  lea     r8, [rbp+20D0h+var_1840]; lpBuffer
0x18002d654  mov     r9d, edi; cchBufferMax
0x18002d657  mov     edx, 0CFAh; uID
0x18002d65c  call    cs:__imp_LoadStringW
0x18002d662  xor     edi, edi
0x18002d664  test    eax, eax
0x18002d666  jz      short loc_18002D685
0x18002d668  mov     rdx, qword ptr [rsp+21D0h+var_2190]; lpText
0x18002d66d  lea     r9d, [rdi+10h]; uType
0x18002d671  lea     r8, [rbp+20D0h+var_1840]; lpCaption
0x18002d678  mov     rcx, r15; hWnd
0x18002d67b  call    cs:__imp_MessageBoxW
0x18002d681  jmp     short loc_18002D685
0x18002d683  xor     edi, edi
0x18002d685  mov     rcx, qword ptr [rsp+21D0h+var_2190]; hMem
0x18002d68a  test    rcx, rcx
0x18002d68d  jz      short loc_18002D695
0x18002d68f  call    cs:__imp_LocalFree
  ... truncated ...
```
