# ViewPageViewSignatures(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180036160`
- end: `0x180036fe9`
- name: `?ViewPageViewSignatures@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `3721`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x18001e380`
- `0x18001e9a8`
- `0x180033080`
- `0x1800343d4`
- `0x180034870`
- `0x180034dcc`
- `0x180035384`
- `0x180035b18`
- `0x180036160`
- `0x1800370e8`
- `0x180037384`
- `0x180037560`
- `0x180037abc`
- `0x180039994`
- `0x180039c10`
- `0x180039d5c`
- `0x180039f48`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036976`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fd1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036777`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036951`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036777`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036951`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a18`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036ad6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a18`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036a9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180036ad6`
- `CRYPT32!CryptMsgClose` at `0x180036563`
- `CRYPT32!CryptMsgClose` at `0x180036716`
- `CRYPT32!CryptMsgClose` at `0x18003673e`
- `CRYPT32!CryptMsgClose` at `0x1800368f6`
- `CRYPT32!CryptMsgClose` at `0x180036563`
- `CRYPT32!CryptMsgClose` at `0x180036716`
- `CRYPT32!CryptMsgClose` at `0x18003673e`
- `CRYPT32!CryptMsgClose` at `0x1800368f6`
- `USER32!IsWindowEnabled` at `0x180036d1b`
- `USER32!IsWindowEnabled` at `0x180036d5f`
- `USER32!IsWindowEnabled` at `0x180036d1b`
- `USER32!IsWindowEnabled` at `0x180036d5f`
- `USER32!SendMessageA` at `0x180036325`
- `USER32!SendMessageA` at `0x180036361`
- `USER32!SendMessageA` at `0x18003660d`
- `USER32!SendMessageA` at `0x180036648`
- `USER32!SendMessageA` at `0x180036a30`
- `USER32!SendMessageA` at `0x180036a75`
- `USER32!SendMessageA` at `0x180036ab0`
- `USER32!SendMessageA` at `0x180036aec`
- `USER32!SendMessageA` at `0x180036b03`
- `USER32!SendMessageA` at `0x180036b17`
- `USER32!SendMessageA` at `0x180036d48`
- `USER32!SendMessageA` at `0x180036db3`
- `USER32!SendMessageA` at `0x180036dd3`
- `USER32!SendMessageA` at `0x180036e4c`
- `USER32!SendMessageA` at `0x180036e8c`
- `USER32!SendMessageA` at `0x180036f2e`
- `USER32!SendMessageA` at `0x180036f55`
- `USER32!SendMessageA` at `0x180036fa3`
- `USER32!SendMessageA` at `0x180036fc3`
- `USER32!SendMessageA` at `0x180036325`
- `USER32!SendMessageA` at `0x180036361`
- `USER32!SendMessageA` at `0x18003660d`
- `USER32!SendMessageA` at `0x180036648`
- `USER32!SendMessageA` at `0x180036a30`
- `USER32!SendMessageA` at `0x180036a75`
- `USER32!SendMessageA` at `0x180036ab0`
- `USER32!SendMessageA` at `0x180036aec`
- `USER32!SendMessageA` at `0x180036b03`
- `USER32!SendMessageA` at `0x180036b17`
- `USER32!SendMessageA` at `0x180036d48`
- `USER32!SendMessageA` at `0x180036db3`
- `USER32!SendMessageA` at `0x180036dd3`
- `USER32!SendMessageA` at `0x180036e4c`
- `USER32!SendMessageA` at `0x180036e8c`
- `USER32!SendMessageA` at `0x180036f2e`
- `USER32!SendMessageA` at `0x180036f55`
- `USER32!SendMessageA` at `0x180036fa3`
- `USER32!SendMessageA` at `0x180036fc3`
- `USER32!GetWindowLongPtrA` at `0x1800361e2`
- `USER32!GetWindowLongPtrA` at `0x1800361e2`
- `USER32!SetWindowLongPtrA` at `0x180036923`
- `USER32!SetWindowLongPtrA` at `0x180036c13`
- `USER32!SetWindowLongPtrA` at `0x180036ec0`
- `USER32!SetWindowLongPtrA` at `0x180036ee4`
- `USER32!SetWindowLongPtrA` at `0x180036923`
- `USER32!SetWindowLongPtrA` at `0x180036c13`
- `USER32!SetWindowLongPtrA` at `0x180036ec0`
- `USER32!SetWindowLongPtrA` at `0x180036ee4`
- `USER32!GetDlgItem` at `0x1800362fb`
- `USER32!GetDlgItem` at `0x1800365e4`
- `USER32!GetDlgItem` at `0x1800369be`
- `USER32!GetDlgItem` at `0x1800369d7`
- `USER32!GetDlgItem` at `0x180036b5a`
- `USER32!GetDlgItem` at `0x180036baa`
- `USER32!GetDlgItem` at `0x180036bbe`
- `USER32!GetDlgItem` at `0x180036bd5`
- `USER32!GetDlgItem` at `0x180036be8`
- `USER32!GetDlgItem` at `0x180036bfb`
- `USER32!GetDlgItem` at `0x180036ce2`
- `USER32!GetDlgItem` at `0x180036d12`
- `USER32!GetDlgItem` at `0x180036d31`
- `USER32!GetDlgItem` at `0x180036d56`
- `USER32!GetDlgItem` at `0x180036d77`
- `USER32!GetDlgItem` at `0x180036d9c`
- `USER32!GetDlgItem` at `0x180036e36`
- `USER32!GetDlgItem` at `0x180036e62`
- `USER32!GetDlgItem` at `0x180036e7b`
- `USER32!GetDlgItem` at `0x180036ea2`
- `USER32!GetDlgItem` at `0x180036f02`
- `USER32!GetDlgItem` at `0x180036f7d`
- `USER32!GetDlgItem` at `0x1800362fb`
- `USER32!GetDlgItem` at `0x1800365e4`
- `USER32!GetDlgItem` at `0x1800369be`
- `USER32!GetDlgItem` at `0x1800369d7`
- `USER32!GetDlgItem` at `0x180036b5a`
- `USER32!GetDlgItem` at `0x180036baa`
- `USER32!GetDlgItem` at `0x180036bbe`
- `USER32!GetDlgItem` at `0x180036bd5`
- `USER32!GetDlgItem` at `0x180036be8`
- `USER32!GetDlgItem` at `0x180036bfb`
- `USER32!GetDlgItem` at `0x180036ce2`
- `USER32!GetDlgItem` at `0x180036d12`
- `USER32!GetDlgItem` at `0x180036d31`
- `USER32!GetDlgItem` at `0x180036d56`
- `USER32!GetDlgItem` at `0x180036d77`
- `USER32!GetDlgItem` at `0x180036d9c`
- `USER32!GetDlgItem` at `0x180036e36`
- `USER32!GetDlgItem` at `0x180036e62`
- `USER32!GetDlgItem` at `0x180036e7b`
- `USER32!GetDlgItem` at `0x180036ea2`
- `USER32!GetDlgItem` at `0x180036f02`
- `USER32!GetDlgItem` at `0x180036f7d`
- `USER32!EnableWindow` at `0x1800369c9`
- `USER32!EnableWindow` at `0x180036e6d`
- `USER32!EnableWindow` at `0x180036ead`
- `USER32!EnableWindow` at `0x1800369c9`
- `USER32!EnableWindow` at `0x180036e6d`
- `USER32!EnableWindow` at `0x180036ead`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ViewPageViewSignatures(HWND hDlg, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  LONG_PTR WindowLongPtrA; // r14
  __int64 v9; // r13
  __int64 v10; // rdi
  HWND v11; // rbx
  LRESULT v12; // r15
  struct SIP_DISPATCH_INFO_ *v13; // r9
  void *Signature; // rbx
  int v15; // eax
  const char *v16; // rsi
  const char *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned int v20; // r9d
  HWND v21; // rbx
  LRESULT v22; // r12
  int v23; // eax
  unsigned int v24; // edx
  __int64 v25; // rbx
  __int64 v26; // r15
  void *v27; // r15
  __int64 v28; // rdi
  void **v30; // r12
  void *v31; // rcx
  HANDLE v32; // rax
  void *v33; // rbx
  int v34; // eax
  const char *v35; // rsi
  const char *v36; // rcx
  unsigned int v37; // r9d
  const unsigned __int16 *v38; // rcx
  __int64 *v39; // r15
  __int64 v40; // rbx
  HANDLE FileW; // rax
  HLOCAL v42; // rbx
  signed int i; // ebx
  HWND v44; // rax
  HWND v45; // r14
  unsigned int v46; // r13d
  LRESULT v47; // r13
  HWND v48; // rax
  HWND v49; // r14
  HWND v50; // rcx
  HWND v51; // rcx
  int v52; // eax
  int v53; // edx
  HWND v54; // rax
  LPARAM p_lParam; // r9
  WPARAM v56; // r8
  UINT v57; // edx
  HWND v58; // rcx
  HWND v59; // rax
  HWND v60; // rax
  HWND v61; // rax
  int v62; // edx
  HWND v63; // rbx
  HWND v64; // rax
  BOOL v65; // ebx
  HWND v66; // rax
  HWND v67; // rax
  BOOL v68; // ebx
  HWND v69; // rax
  HWND DlgItem; // rbx
  bool v71; // sf
  int v72; // eax
  HWND v73; // rbx
  int v74; // eax
  void **dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  void **dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  HLOCAL v77; // [rsp+40h] [rbp-C0h] BYREF
  void *v78; // [rsp+48h] [rbp-B8h] BYREF
  int v79[2]; // [rsp+50h] [rbp-B0h] BYREF
  void ***v80; // [rsp+58h] [rbp-A8h]
  LPARAM lParam; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v82[4]; // [rsp+68h] [rbp-98h] BYREF
  int v83; // [rsp+6Ch] [rbp-94h]
  int v84; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  void **v86[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v87; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v88; // [rsp+E0h] [rbp-20h]
  __int128 v89; // [rsp+F0h] [rbp-10h]
  __int64 v90; // [rsp+100h] [rbp+0h]
  LPARAM v91[2]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v92; // [rsp+118h] [rbp+18h]
  __int128 v93; // [rsp+128h] [rbp+28h]
  __int64 v94; // [rsp+138h] [rbp+38h]
  _OWORD v95[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v96[2]; // [rsp+160h] [rbp+60h] BYREF
  _DWORD v97[3]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v98; // [rsp+18Ch] [rbp+8Ch]
  int v99; // [rsp+19Ch] [rbp+9Ch]
  int v100; // [rsp+1A0h] [rbp+A0h] BYREF
  HWND v101; // [rsp+1A8h] [rbp+A8h]
  int v102; // [rsp+1B0h] [rbp+B0h]
  HLOCAL v103; // [rsp+1C0h] [rbp+C0h]
  void *v104; // [rsp+1C8h] [rbp+C8h]
  const char *v105; // [rsp+1D0h] [rbp+D0h]
  _OWORD *v106; // [rsp+1D8h] [rbp+D8h]
  int v107; // [rsp+1E0h] [rbp+E0h]
  __int64 v108; // [rsp+1E8h] [rbp+E8h]
  int v109; // [rsp+200h] [rbp+100h] BYREF
  HWND v110; // [rsp+208h] [rbp+108h]
  int v111; // [rsp+210h] [rbp+110h]
  HLOCAL v112; // [rsp+220h] [rbp+120h]
  void *v113; // [rsp+228h] [rbp+128h]
  const char *v114; // [rsp+230h] [rbp+130h]
  _OWORD *v115; // [rsp+238h] [rbp+138h]
  WINTRUST_DATA v116; // [rsp+260h] [rbp+160h] BYREF
  _DWORD *v117; // [rsp+2B0h] [rbp+1B0h]
  WINTRUST_DATA pWinTrustData; // [rsp+2C0h] [rbp+1C0h] BYREF
  struct SIP_SUBJECTINFO_ v119; // [rsp+320h] [rbp+220h] BYREF
  int nIDDlgItem[4]; // [rsp+3A0h] [rbp+2A0h] BYREF
  CRYPT_PROVIDER_DEFUSAGE psUsage; // [rsp+3B0h] [rbp+2B0h] BYREF
  CRYPT_PROVIDER_DEFUSAGE v122; // [rsp+3D8h] [rbp+2D8h] BYREF
  WCHAR Buffer[768]; // [rsp+400h] [rbp+300h] BYREF

  *(_OWORD *)v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  WindowLongPtrA = 0;
  memset_0(&lParam, 0, 0x58u);
  v78 = 0;
  v77 = 0;
  if ( a2 != 272 )
  {
    WindowLongPtrA = GetWindowLongPtrA(hDlg, 16);
    if ( !WindowLongPtrA )
      goto LABEL_29;
  }
  v79[0] = 101;
  v79[1] = 103;
  nIDDlgItem[0] = 100;
  nIDDlgItem[1] = 102;
  switch ( a2 )
  {
    case 2u:
      DlgItem = GetDlgItem(hDlg, 101);
      memset_0(&lParam, 0, 0x58u);
      v72 = SendMessageA(DlgItem, 0x1004u, 0, 0) - 1;
      v71 = v72 < 0;
      LODWORD(lParam) = 4;
      while ( 1 )
      {
        HIDWORD(lParam) = v72;
        if ( v71 )
          break;
        if ( (unsigned int)SendMessageA(DlgItem, 0x104Bu, 0, (LPARAM)&lParam) )
          LocalFree(hMem);
        v71 = HIDWORD(lParam) - 1 < 0;
        v72 = HIDWORD(lParam) - 1;
      }
      v73 = GetDlgItem(hDlg, 103);
      memset_0(&lParam, 0, 0x58u);
      v74 = SendMessageA(v73, 0x1004u, 0, 0);
      LODWORD(lParam) = 4;
      while ( 1 )
      {
        HIDWORD(lParam) = v74 - 1;
        if ( v74 - 1 < 0 )
          break;
        if ( (unsigned int)SendMessageA(v73, 0x104Bu, 0, (LPARAM)&lParam) )
          LocalFree(hMem);
        v74 = HIDWORD(lParam);
      }
      goto LABEL_29;
    case 0x4Eu:
      v52 = *(_DWORD *)(a4 + 16);
      if ( v52 != -205 )
      {
        if ( v52 == -203 )
        {
          SetWindowLongPtrA(hDlg, 0, 0);
          goto LABEL_29;
        }
        if ( v52 != -201 )
        {
          switch ( v52 )
          {
            case -101:
              if ( ((*(_QWORD *)(a4 + 8) - 101LL) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
              {
                v64 = GetDlgItem(hDlg, 101);
                v65 = SendMessageA(v64, 0x1032u, 0, 0) != 0;
                v66 = GetDlgItem(hDlg, 100);
                EnableWindow(v66, v65);
                v67 = GetDlgItem(hDlg, 103);
                v68 = SendMessageA(v67, 0x1032u, 0, 0) != 0;
                v69 = GetDlgItem(hDlg, 102);
                EnableWindow(v69, v68);
              }
              goto LABEL_29;
            case -7:
              if ( *(_QWORD *)(a4 + 8) == 101 )
              {
                v62 = 101;
              }
              else
              {
                if ( *(_QWORD *)(a4 + 8) != 103 )
                  goto LABEL_29;
                v62 = 103;
              }
              v63 = GetDlgItem(hDlg, v62);
              if ( !(unsigned int)SendMessageA(v63, 0x1004u, 0, 0)
                || (unsigned int)SendMessageA(v63, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2) != -1 )
              {
                goto LABEL_29;
              }
              memset_0(&lParam, 0, 0x58u);
              lParam = 8;
              v83 = 1;
              v84 = 1;
              p_lParam = (LPARAM)&lParam;
              v56 = 0;
              v57 = 4102;
              v58 = v63;
              break;
            case -3:
              if ( *(_QWORD *)(a4 + 8) == 101 )
              {
                v61 = GetDlgItem(hDlg, 100);
                if ( !IsWindowEnabled(v61) )
                  goto LABEL_29;
                v60 = GetDlgItem(hDlg, 100);
                v56 = 100;
              }
              else
              {
                if ( *(_QWORD *)(a4 + 8) != 103 )
                  goto LABEL_29;
                v59 = GetDlgItem(hDlg, 102);
                if ( !IsWindowEnabled(v59) )
                  goto LABEL_29;
                v60 = GetDlgItem(hDlg, 102);
                v56 = 102;
              }
              v57 = 273;
              p_lParam = (LPARAM)v60;
              v58 = hDlg;
              break;
            case -2:
              if ( *(_QWORD *)(a4 + 8) == 101 )
              {
                v53 = 101;
              }
              else
              {
                if ( *(_QWORD *)(a4 + 8) != 103 )
                  goto LABEL_29;
                v53 = 103;
              }
              v54 = GetDlgItem(hDlg, v53);
              p_lParam = 2;
              v56 = -1;
              v57 = 4108;
              v58 = v54;
              break;
            default:
              goto LABEL_29;
          }
          SendMessageA(v58, v57, v56, p_lParam);
          goto LABEL_29;
        }
        SetWindowLongPtrA(hDlg, 0, 0);
        std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
LABEL_101:
        v28 = 1;
        break;
      }
LABEL_51:
      std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      goto LABEL_101;
    case 0x53u:
    case 0x7Bu:
      if ( a2 == 83 )
        v49 = GetDlgItem(hDlg, *(_DWORD *)(a4 + 8));
      else
        v49 = (HWND)a3;
      if ( v49 == GetDlgItem(hDlg, 101) || v49 == GetDlgItem(hDlg, 100) )
      {
        v28 = (int)OnContextHelp(v50, a2, a3, a4, (ULONG_PTR)"e");
        std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      }
      else if ( v49 == GetDlgItem(hDlg, 103) || v49 == GetDlgItem(hDlg, 102) )
      {
        v28 = (int)OnContextHelp(v51, a2, a3, a4, (ULONG_PTR)&qword_180045E70);
        std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      }
      else
      {
        v28 = 1;
        SetWindowLongPtrA(hDlg, 0, 1);
        std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      }
      break;
    case 0x110u:
      v39 = *(__int64 **)(a4 + 48);
      v40 = *v39;
      SetWindowLongPtrA(hDlg, 16, (LONG_PTR)v39);
      v28 = 1;
      FileW = CreateFileW(*(LPCWSTR *)(v40 + 56), 0x80000000, 1u, 0, 3u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v78,
        FileW);
      if ( v78 == (void *)-1LL )
        goto LABEL_29;
      v42 = LocalAlloc(0x40u, 0x38u);
      if ( !v42 )
        goto LABEL_29;
      std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      v77 = v42;
      SetCatalogSignaturesStruct(v42, v78);
      v77 = 0;
      v39[1] = (__int64)v42;
      for ( i = 0; (unsigned int)i < 2; ++i )
      {
        v44 = GetDlgItem(hDlg, nIDDlgItem[i]);
        EnableWindow(v44, 0);
        v45 = GetDlgItem(hDlg, v79[i]);
        v91[0] = 15;
        *(_QWORD *)&v92 = Buffer;
        HIDWORD(v92) = 0;
        LODWORD(v91[1]) = 100;
        LoadStringW(HinstDll, 0xCCCu, Buffer, 768);
        v46 = 1;
        SendMessageA(v45, 0x1061u, 0, (LPARAM)v91);
        if ( i == 1 )
        {
          LODWORD(v91[1]) = 100;
          LoadStringW(HinstDll, 0xD7Au, Buffer, 768);
          v46 = 2;
          SendMessageA(v45, 0x1061u, 1u, (LPARAM)v91);
        }
        LODWORD(v91[1]) = 100;
        LoadStringW(HinstDll, 0xCCFu, Buffer, 768);
        SendMessageA(v45, 0x1061u, v46, (LPARAM)v91);
        LODWORD(v91[1]) = 125;
        LoadStringW(HinstDll, 0xCD3u, Buffer, 768);
        SendMessageA(v45, 0x1061u, v46 + 1, (LPARAM)v91);
        SendMessageA(v45, 0x1036u, 0, 32);
        v47 = SendMessageA(v45, 0x101Fu, 0, 0);
        IsolationAwareSetWindowSubclass(v45, TabSubclassProc<list_view_tag>::Proc, i, 0);
        if ( v47 )
        {
          IsolationAwareSetWindowSubclass(v47, TabSubclassProc<list_header_tag>::Proc, i, hDlg);
          v48 = GetDlgItem(hDlg, nIDDlgItem[i]);
          IsolationAwareSetWindowSubclass(v48, TabSubclassProc<detail_button_tag>::Proc, i, v47);
        }
        DisplaySignatures(v45, v39, (unsigned int)i);
      }
      std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
      break;
    case 0x111u:
      if ( (_WORD)a3 != 9 )
      {
        v9 = *(_QWORD *)WindowLongPtrA;
        if ( (_WORD)a3 != 100 )
        {
          if ( (_DWORD)a3 == 102 )
          {
            memset_0(&v109, 0, 0x60u);
            v87 = 0;
            v88 = 0;
            v89 = 0;
            v90 = 0;
            v10 = *(_QWORD *)(v9 + 56);
            memset(v95, 0, sizeof(v95));
            memset(&psUsage, 0, sizeof(psUsage));
            memset_0(&pWinTrustData, 0, 0x58u);
            v11 = GetDlgItem(hDlg, 103);
            pWinTrustData.cbStruct = 88;
            pWinTrustData.dwUIChoice = 2;
            v12 = SendMessageA(v11, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
            *(_QWORD *)v79 = v12;
            memset_0(v82, 0, 0x50u);
            HIDWORD(lParam) = v12;
            LODWORD(lParam) = 4;
            if ( (unsigned int)SendMessageA(v11, 0x104Bu, 0, (LPARAM)&lParam) )
            {
              *(_OWORD *)nIDDlgItem = 0;
              memset_0(&v119, 0, sizeof(v119));
              Signature = I_GetSignature(
                            *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(WindowLongPtrA + 8) + 16LL)
                                                       + 8LL * (int)v12),
                            &v119,
                            (struct _GUID *)nIDDlgItem,
                            v13);
              memset_0(&v109, 0, 0x60u);
              v109 = 96;
              v112 = hMem;
              v110 = hDlg;
              v113 = Signature;
              v15 = fUseCTLSigning((struct CERT_VIEWSIGNATURES_HELPER *)WindowLongPtrA);
              v16 = "1.3.6.1.4.1.311.10.3.1";
              v17 = "1.3.6.1.4.1.311.10.3.1";
              if ( !v15 )
                v17 = "1.3.6.1.5.5.7.3.3";
              v114 = v17;
              v88 = 0;
              v89 = 0;
              v90 = 0;
              v87 = 0x38u;
              v18 = *(_QWORD *)(WindowLongPtrA + 8);
              *(_QWORD *)&v89 = *(_QWORD *)(v18 + 32);
              DWORD2(v88) = *(_DWORD *)(v18 + 24);
              v90 = *(_QWORD *)(v18 + 48);
              DWORD2(v89) = *(_DWORD *)(v18 + 40);
              DWORD2(v87) = *(_DWORD *)(v18 + 8);
              HIDWORD(v87) = v79[0];
              *(_QWORD *)(*(_QWORD *)WindowLongPtrA + 56LL) = *(_QWORD *)(*(_QWORD *)(v18 + 16) + 8LL * (int)v12);
              v19 = *(_QWORD *)(WindowLongPtrA + 8);
              *(_QWORD *)&v88 = *(_QWORD *)(v19 + 16);
              if ( *(_QWORD *)(*(_QWORD *)(v19 + 16) + 8LL * (int)v12) )
              {
                if ( !(unsigned int)fUseCTLSigning((struct CERT_VIEWSIGNATURES_HELPER *)WindowLongPtrA) )
                  v16 = "1.3.6.1.5.5.7.3.3";
                BuildWinVTrustState(
                  *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(WindowLongPtrA + 8) + 16LL) + 8LL * (int)v12),
                  0,
                  0,
                  0,
                  0,
                  v16,
                  (struct CERT_VIEWSIGNERINFO_PRIVATE *)v95,
                  &pWinTrustData);
                *(_QWORD *)((char *)v95 + 12) = 0;
                *(_QWORD *)((char *)&v95[1] + 4) = 0;
                v111 |= 0x80000000;
                v115 = v95;
              }
              v86[0] = (void **)&v109;
              v86[1] = (void **)&v87;
              *(_QWORD *)v79 = 2;
              v80 = v86;
              CryptUIDlgViewSignerInfoExW(v79);
              if ( *(_QWORD *)(v9 + 56) )
                FreeWinVTrustState(
                  *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(WindowLongPtrA + 8) + 16LL) + 8LL * (int)v12),
                  0,
                  0,
                  v20,
                  dwCreationDisposition,
                  "1.3.6.1.5.5.7.3.3",
                  &psUsage,
                  &pWinTrustData);
              if ( Signature )
                CryptMsgClose(Signature);
              *(_QWORD *)(*(_QWORD *)WindowLongPtrA + 56LL) = v10;
              *(_QWORD *)(v9 + 56) = v10;
            }
          }
          goto LABEL_29;
        }
        if ( !WORD1(a3) )
        {
          memset_0(&v100, 0, 0x60u);
          memset(v96, 0, sizeof(v96));
          memset(&v122, 0, sizeof(v122));
          memset_0(&v116, 0, 0x58u);
          v86[0] = 0;
          nIDDlgItem[0] = 0;
          v21 = GetDlgItem(hDlg, 101);
          v116.cbStruct = 88;
          v116.dwUIChoice = 2;
          v22 = SendMessageA(v21, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
          *(_QWORD *)v79 = v22;
          memset_0(v82, 0, 0x50u);
          HIDWORD(lParam) = v22;
          LODWORD(lParam) = 4;
          v23 = SendMessageA(v21, 0x104Bu, 0, (LPARAM)&lParam);
          v25 = 0;
          if ( v23 )
          {
            v26 = *(_QWORD *)WindowLongPtrA;
            if ( *(_WORD *)(*(_QWORD *)WindowLongPtrA + 32LL) == 1 )
            {
              v27 = I_OpenBlob(0x10001u, *(unsigned __int8 **)(v26 + 48), *(_DWORD *)(v26 + 40));
              if ( !v27 )
                goto LABEL_29;
            }
            else
            {
              v27 = *(void **)(v26 + 40);
            }
            if ( (int)v22 > 0 )
            {
              if ( (int)I_GetSecondarySignatures(v27, v24, v86, (unsigned int *)nIDDlgItem) < 0 )
                goto LABEL_29;
              v30 = v86[0];
              I_OrderSignatures(v86[0], nIDDlgItem[0]);
              if ( *(_WORD *)(*(_QWORD *)WindowLongPtrA + 32LL) == 1 )
                CryptMsgClose(v27);
              v27 = v30[v79[0] - 1];
              v30[v79[0] - 1] = 0;
              if ( nIDDlgItem[0] )
              {
                do
                {
                  v31 = v30[v25];
                  if ( v31 )
                    CryptMsgClose(v31);
                  v25 = (unsigned int)(v25 + 1);
                }
                while ( (unsigned int)v25 < nIDDlgItem[0] );
              }
            }
            v32 = CreateFileW(*(LPCWSTR *)(v9 + 56), 0x80000000, 1u, 0, 3u, 0x80u, 0);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v78,
              v32);
            v33 = v78;
            if ( v78 != (void *)-1LL )
            {
              memset_0(&v100, 0, 0x60u);
              v100 = 96;
              v103 = hMem;
              v101 = hDlg;
              v104 = v27;
              v34 = fUseCTLSigning((struct CERT_VIEWSIGNATURES_HELPER *)WindowLongPtrA);
              v35 = "1.3.6.1.4.1.311.10.3.1";
              v36 = "1.3.6.1.4.1.311.10.3.1";
              if ( !v34 )
                v36 = "1.3.6.1.5.5.7.3.3";
              v105 = v36;
              v107 = *(_DWORD *)(v9 + 88);
              v108 = *(_QWORD *)(v9 + 96);
              v98 = 0;
              v99 = 0;
              v117 = v97;
              v97[0] = 32;
              v97[2] = 1;
              v97[1] = v79[0];
              if ( *(_QWORD *)(v9 + 56) )
              {
                if ( !(unsigned int)fUseCTLSigning((struct CERT_VIEWSIGNATURES_HELPER *)WindowLongPtrA) )
                  v35 = "1.3.6.1.5.5.7.3.3";
                BuildWinVTrustState(
                  *(const unsigned __int16 **)(v9 + 56),
                  v33,
                  0,
                  0,
                  0,
                  v35,
                  (struct CERT_VIEWSIGNERINFO_PRIVATE *)v96,
                  &v116);
                *(_QWORD *)((char *)v96 + 12) = 0;
                *(_QWORD *)((char *)&v96[1] + 4) = 0;
                v102 |= 0x80000000;
                v106 = v96;
              }
              CryptUIDlgViewSignerInfoW(&v100);
              v38 = *(const unsigned __int16 **)(v9 + 56);
              if ( v38 )
                FreeWinVTrustState(v38, v33, 0, v37, dwCreationDispositiona, "1.3.6.1.5.5.7.3.3", &v122, &v116);
              if ( *(_WORD *)(*(_QWORD *)WindowLongPtrA + 32LL) == 1 )
                CryptMsgClose(v27);
            }
          }
        }
LABEL_29:
        std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(&v77);
        v28 = 0;
        break;
      }
      goto LABEL_51;
    default:
      goto LABEL_29;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v78);
  return v28;
}

```

## disassembly

```asm
0x180036160  mov     [rsp-8+arg_8], rbx
0x180036165  push    rbp
0x180036166  push    rsi
0x180036167  push    rdi
0x180036168  push    r12
0x18003616a  push    r13
0x18003616c  push    r14
0x18003616e  push    r15
0x180036170  lea     rbp, [rsp-910h]
0x180036178  sub     rsp, 0A10h
0x18003617f  mov     rax, cs:__security_cookie
0x180036186  xor     rax, rsp
0x180036189  mov     [rbp+940h+var_40], rax
0x180036190  mov     rdi, r9
0x180036193  mov     rbx, r8
0x180036196  mov     r15d, edx
0x180036199  mov     rsi, rcx
0x18003619c  xorps   xmm0, xmm0
0x18003619f  xor     eax, eax
0x1800361a1  movups  xmmword ptr [rbp+940h+var_938], xmm0
0x1800361a5  movups  [rbp+940h+var_928], xmm0
0x1800361a9  movups  [rbp+940h+var_918], xmm0
0x1800361ad  mov     [rbp+940h+var_908], rax
0x1800361b1  xor     r12d, r12d
0x1800361b4  mov     r14d, r12d
0x1800361b7  xor     edx, edx; Val
0x1800361b9  lea     r8d, [rax+58h]; Size
0x1800361bd  lea     rcx, [rsp+0A40h+lParam]; void *
0x1800361c2  call    memset_0
0x1800361c7  mov     [rsp+0A40h+var_9F8], r12
0x1800361cc  mov     [rsp+0A40h+var_A00], r12
0x1800361d1  cmp     r15d, 110h
0x1800361d8  jz      short loc_180036200
0x1800361da  lea     edx, [r12+10h]; nIndex
0x1800361df  mov     rcx, rsi; hWnd
0x1800361e2  call    cs:__imp_GetWindowLongPtrA
0x1800361e8  mov     r14, rax
0x1800361eb  test    rax, rax
0x1800361ee  jnz     short loc_180036200
0x1800361f0  lea     rcx, [rsp+0A40h+var_A00]
0x1800361f5  call    ?_Delete@?$unique_ptr@UtagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW@@UCatalogSignerInfoDeleter@@@std@@AEAAXXZ; std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(void)
0x1800361fa  nop
0x1800361fb  jmp     loc_18003669B
0x180036200  mov     r13d, 65h ; 'e'
0x180036206  mov     [rsp+0A40h+var_9F0], r13d
0x18003620b  lea     ecx, [r13+2]
0x18003620f  mov     [rsp+0A40h+var_9F0+4], ecx
0x180036213  lea     edx, [rcx-3]; nIDDlgItem
0x180036216  mov     [rbp+940h+nIDDlgItem], edx
0x18003621c  lea     r8d, [r13+1]
0x180036220  mov     [rbp+940h+nIDDlgItem+4], r8d
0x180036227  mov     eax, r15d
0x18003622a  sub     eax, 2
0x18003622d  jz      loc_180036EFC
0x180036233  sub     eax, 4Ch ; 'L'
0x180036236  jz      loc_180036C84
0x18003623c  sub     eax, 5
0x18003623f  jz      loc_180036B9E
0x180036245  sub     eax, 28h ; '('
0x180036248  jz      loc_180036B9E
0x18003624e  sub     eax, 95h
0x180036253  jz      loc_180036911
0x180036259  cmp     eax, 1
0x18003625c  jnz     loc_180036690
0x180036262  cmp     bx, 9
0x180036266  jz      loc_180036901
0x18003626c  mov     r13, [r14]
0x18003626f  cmp     bx, dx
0x180036272  jz      loc_180036579
0x180036278  cmp     bx, r8w
0x18003627c  jnz     loc_180036690
0x180036282  shr     rbx, 10h
0x180036286  test    bx, bx
0x180036289  jnz     loc_180036690
0x18003628f  lea     r12d, [rcx-7]
0x180036293  mov     r8d, r12d; Size
0x180036296  xor     edx, edx; Val
0x180036298  lea     rcx, [rbp+940h+var_840]; void *
0x18003629f  call    memset_0
0x1800362a4  xorps   xmm0, xmm0
0x1800362a7  xor     eax, eax
0x1800362a9  movups  [rbp+940h+var_970], xmm0
0x1800362ad  movups  [rbp+940h+var_960], xmm0
0x1800362b1  movups  [rbp+940h+var_950], xmm0
0x1800362b5  mov     [rbp+940h+var_940], rax
0x1800362b9  mov     rdi, [r13+38h]
0x1800362bd  movups  [rbp+940h+var_900], xmm0
0x1800362c1  movups  [rbp+940h+var_8F0], xmm0
0x1800362c5  xorps   xmm1, xmm1
0x1800362c8  movups  xmmword ptr [rbp+940h+psUsage.cbStruct], xmm1
0x1800362cf  movups  xmmword ptr [rbp+940h+psUsage.gActionID.Data4+4], xmm1
0x1800362d6  mov     [rbp+940h+psUsage.pDefSIPClientData], rax
0x1800362dd  lea     r15d, [r12-8]
0x1800362e2  mov     r8d, r15d; Size
0x1800362e5  xor     edx, edx; Val
0x1800362e7  lea     rcx, [rbp+940h+var_780]; void *
0x1800362ee  call    memset_0
0x1800362f3  lea     edx, [r12+7]; nIDDlgItem
0x1800362f8  mov     rcx, rsi; hDlg
0x1800362fb  call    cs:__imp_GetDlgItem
0x180036301  mov     rbx, rax
0x180036304  mov     [rbp+940h+var_780.cbStruct], r15d
0x18003630b  lea     eax, [r12-5Eh]
0x180036310  mov     [rbp+940h+var_780.dwUIChoice], eax
0x180036316  mov     r9d, eax; lParam
0x180036319  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18003631d  mov     edx, 100Ch; Msg
0x180036322  mov     rcx, rbx; hWnd
0x180036325  call    cs:__imp_SendMessageA
0x18003632b  mov     r15, rax
0x18003632e  mov     qword ptr [rsp+0A40h+var_9F0], rax
0x180036333  xor     edx, edx; Val
0x180036335  lea     r8d, [r12-10h]; Size
0x18003633a  lea     rcx, [rsp+0A40h+var_9D8]; void *
0x18003633f  call    memset_0
0x180036344  mov     dword ptr [rsp+0A40h+lParam+4], r15d
0x180036349  mov     dword ptr [rsp+0A40h+lParam], 4
0x180036351  lea     r9, [rsp+0A40h+lParam]; lParam
0x180036356  xor     r8d, r8d; wParam
0x180036359  mov     edx, 104Bh; Msg
0x18003635e  mov     rcx, rbx; hWnd
0x180036361  call    cs:__imp_SendMessageA
0x180036367  xor     ebx, ebx
0x180036369  test    eax, eax
0x18003636b  jnz     short loc_18003637D
0x18003636d  lea     rcx, [rsp+0A40h+var_A00]
0x180036372  call    ?_Delete@?$unique_ptr@UtagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW@@UCatalogSignerInfoDeleter@@@std@@AEAAXXZ; std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(void)
0x180036377  nop
0x180036378  jmp     loc_18003665F
0x18003637d  xorps   xmm0, xmm0
0x180036380  movups  xmmword ptr [rbp+940h+nIDDlgItem], xmm0
0x180036387  xor     edx, edx; Val
0x180036389  mov     r8d, 80h; Size
0x18003638f  lea     rcx, [rbp+940h+var_720]; void *
0x180036396  call    memset_0
0x18003639b  movsxd  r15, r15d
0x18003639e  mov     rax, [r14+8]
0x1800363a2  mov     rcx, [rax+10h]
0x1800363a6  lea     r8, [rbp+940h+nIDDlgItem]; struct _GUID *
0x1800363ad  lea     rdx, [rbp+940h+var_720]; struct SIP_SUBJECTINFO_ *
0x1800363b4  mov     rcx, [rcx+r15*8]; unsigned __int16 *
0x1800363b8  call    ?I_GetSignature@@YAPEAXPEBGPEAUSIP_SUBJECTINFO_@@PEAU_GUID@@PEAUSIP_DISPATCH_INFO_@@@Z; I_GetSignature(ushort const *,SIP_SUBJECTINFO_ *,_GUID *,SIP_DISPATCH_INFO_ *)
0x1800363bd  mov     rbx, rax
0x1800363c0  mov     r8, r12; Size
0x1800363c3  xor     edx, edx; Val
0x1800363c5  lea     rcx, [rbp+940h+var_840]; void *
0x1800363cc  call    memset_0
0x1800363d1  mov     [rbp+940h+var_840], r12d
0x1800363d8  mov     rcx, [rbp+940h+hMem]
0x1800363dc  mov     [rbp+940h+var_820], rcx
0x1800363e3  mov     [rbp+940h+var_838], rsi
0x1800363ea  mov     [rbp+940h+var_818], rbx
0x1800363f1  mov     rcx, r14; struct CERT_VIEWSIGNATURES_HELPER *
0x1800363f4  call    ?fUseCTLSigning@@YAHPEAUCERT_VIEWSIGNATURES_HELPER@@@Z; fUseCTLSigning(CERT_VIEWSIGNATURES_HELPER *)
0x1800363f9  lea     rsi, pszUsageOID; "1.3.6.1.4.1.311.10.3.1"
0x180036400  mov     rcx, rsi
0x180036403  lea     r12, a136155733; "1.3.6.1.5.5.7.3.3"
0x18003640a  xor     edx, edx
0x18003640c  test    eax, eax
0x18003640e  cmovz   rcx, r12
0x180036412  mov     [rbp+940h+var_810], rcx
0x180036419  xorps   xmm0, xmm0
0x18003641c  xor     eax, eax
0x18003641e  movups  [rbp+940h+var_970], xmm0
0x180036422  movups  [rbp+940h+var_960], xmm0
0x180036426  movups  [rbp+940h+var_950], xmm0
0x18003642a  mov     [rbp+940h+var_940], rax
0x18003642e  mov     qword ptr [rbp+940h+var_970], 38h ; '8'
0x180036436  mov     rcx, [r14+8]
0x18003643a  mov     rax, [rcx+20h]
0x18003643e  mov     qword ptr [rbp+940h+var_950], rax
0x180036442  mov     eax, [rcx+18h]
0x180036445  mov     dword ptr [rbp+940h+var_960+8], eax
0x180036448  mov     rax, [rcx+30h]
0x18003644c  mov     [rbp+940h+var_940], rax
0x180036450  mov     eax, [rcx+28h]
0x180036453  mov     dword ptr [rbp+940h+var_950+8], eax
0x180036456  mov     eax, [rcx+8]
0x180036459  mov     dword ptr [rbp+940h+var_970+8], eax
0x18003645c  mov     rax, qword ptr [rsp+0A40h+var_9F0]
0x180036461  mov     dword ptr [rbp+940h+var_970+0Ch], eax
0x180036464  mov     rax, [rcx+10h]
0x180036468  mov     rcx, [r14]
0x18003646b  mov     rax, [rax+r15*8]
0x18003646f  mov     [rcx+38h], rax
0x180036473  mov     rcx, [r14+8]
0x180036477  mov     rax, [rcx+10h]
0x18003647b  mov     qword ptr [rbp+940h+var_960], rax
0x18003647f  mov     rax, [rcx+10h]
0x180036483  cmp     [rax+r15*8], rdx
0x180036487  jz      short loc_1800364EE
0x180036489  mov     rcx, r14; struct CERT_VIEWSIGNATURES_HELPER *
0x18003648c  call    ?fUseCTLSigning@@YAHPEAUCERT_VIEWSIGNATURES_HELPER@@@Z; fUseCTLSigning(CERT_VIEWSIGNATURES_HELPER *)
0x180036491  test    eax, eax
0x180036493  cmovz   rsi, r12
0x180036497  mov     rax, [r14+8]
0x18003649b  mov     rcx, [rax+10h]
0x18003649f  lea     rax, [rbp+940h+var_780]
0x1800364a6  mov     [rsp+0A40h+pWinTrustData], rax; pWinTrustData
0x1800364ab  lea     rax, [rbp+940h+var_900]
0x1800364af  mov     [rsp+0A40h+hTemplateFile], rax; struct CERT_VIEWSIGNERINFO_PRIVATE *
0x1800364b4  mov     qword ptr [rsp+0A40h+dwFlagsAndAttributes], rsi; char *
0x1800364b9  xor     esi, esi
0x1800364bb  mov     qword ptr [rsp+0A40h+dwCreationDisposition], rsi; void **
0x1800364c0  xor     r9d, r9d; unsigned int
0x1800364c3  xor     r8d, r8d; struct _CMSG_SIGNER_INFO *
0x1800364c6  xor     edx, edx; void *
0x1800364c8  mov     rcx, [rcx+r15*8]; unsigned __int16 *
0x1800364cc  call    ?BuildWinVTrustState@@YAHPEBGPEAXPEBU_CMSG_SIGNER_INFO@@KPEAPEAXPEBDPEAUCERT_VIEWSIGNERINFO_PRIVATE@@PEAU_WINTRUST_DATA@@@Z; BuildWinVTrustState(ushort const *,void *,_CMSG_SIGNER_INFO const *,ulong,void * *,char const *,CERT_VIEWSIGNERINFO_PRIVATE *,_WINTRUST_DATA *)
0x1800364d1  mov     qword ptr [rbp+940h+var_900+0Ch], rsi
0x1800364d5  mov     qword ptr [rbp+940h+var_8F0+4], rsi
0x1800364d9  bts     [rbp+940h+var_830], 1Fh
0x1800364e1  lea     rax, [rbp+940h+var_900]
0x1800364e5  mov     [rbp+940h+var_808], rax
0x1800364ec  jmp     short loc_1800364F0
0x1800364ee  xor     esi, esi
0x1800364f0  lea     rax, [rbp+940h+var_840]
0x1800364f7  mov     [rbp+940h+var_980], rax
0x1800364fb  lea     rax, [rbp+940h+var_970]
0x1800364ff  mov     [rbp+940h+var_978], rax
0x180036503  mov     qword ptr [rsp+0A40h+var_9F0], 2
0x18003650c  lea     rax, [rbp+940h+var_980]
0x180036510  mov     [rsp+0A40h+var_9E8], rax
0x180036515  lea     rcx, [rsp+0A40h+var_9F0]
0x18003651a  call    CryptUIDlgViewSignerInfoExW
0x18003651f  cmp     [r13+38h], rsi
0x180036523  jz      short loc_180036558
0x180036525  mov     rax, [r14+8]
0x180036529  mov     rcx, [rax+10h]
0x18003652d  lea     rax, [rbp+940h+var_780]
0x180036534  mov     [rsp+0A40h+pWinTrustData], rax; pWinTrustData
0x180036539  lea     rax, [rbp+940h+psUsage]
0x180036540  mov     [rsp+0A40h+hTemplateFile], rax; psUsage
0x180036545  mov     qword ptr [rsp+0A40h+dwFlagsAndAttributes], r12; pszUsageOID
0x18003654a  xor     r8d, r8d; struct _CMSG_SIGNER_INFO *
0x18003654d  xor     edx, edx; void *
0x18003654f  mov     rcx, [rcx+r15*8]; unsigned __int16 *
0x180036553  call    ?FreeWinVTrustState@@YAHPEBGPEAXPEBU_CMSG_SIGNER_INFO@@KPEAPEAXPEBDPEAU_CRYPT_PROVIDER_DEFUSAGE@@PEAU_WINTRUST_DATA@@@Z; FreeWinVTrustState(ushort const *,void *,_CMSG_SIGNER_INFO const *,ulong,void * *,char const *,_CRYPT_PROVIDER_DEFUSAGE *,_WINTRUST_DATA *)
0x180036558  xor     r12d, r12d
0x18003655b  test    rbx, rbx
0x18003655e  jz      short loc_180036569
0x180036560  mov     rcx, rbx; hCryptMsg
0x180036563  call    cs:__imp_CryptMsgClose
0x180036569  mov     rax, [r14]
0x18003656c  mov     [rax+38h], rdi
0x180036570  mov     [r13+38h], rdi
0x180036574  jmp     loc_180036690
0x180036579  shr     rbx, 10h
0x18003657d  test    bx, bx
0x180036580  jnz     loc_180036690
0x180036586  xor     edx, edx; Val
0x180036588  lea     r8d, [rdx+60h]; Size
0x18003658c  lea     rcx, [rbp+940h+var_8A0]; void *
0x180036593  call    memset_0
0x180036598  xorps   xmm0, xmm0
0x18003659b  movups  [rbp+940h+var_8E0], xmm0
0x18003659f  movups  [rbp+940h+var_8D0], xmm0
0x1800365a3  xorps   xmm1, xmm1
0x1800365a6  xor     eax, eax
0x1800365a8  movups  xmmword ptr [rbp+940h+var_668.cbStruct], xmm1
0x1800365af  movups  xmmword ptr [rbp+940h+var_668.gActionID.Data4+4], xmm1
0x1800365b6  mov     [rbp+940h+var_668.pDefSIPClientData], rax
0x1800365bd  lea     r15d, [rax+58h]
0x1800365c1  mov     r8d, r15d; Size
0x1800365c4  xor     edx, edx; Val
0x1800365c6  lea     rcx, [rbp+940h+var_7E0]; void *
0x1800365cd  call    memset_0
0x1800365d2  mov     [rbp+940h+var_980], r12
0x1800365d6  mov     [rbp+940h+nIDDlgItem], r12d
0x1800365dd  lea     edx, [r15+0Dh]; nIDDlgItem
0x1800365e1  mov     rcx, rsi; hDlg
0x1800365e4  call    cs:__imp_GetDlgItem
0x1800365ea  mov     rbx, rax
0x1800365ed  mov     [rbp+940h+var_7E0.cbStruct], r15d
0x1800365f4  lea     eax, [r15-56h]
0x1800365f8  mov     [rbp+940h+var_7E0.dwUIChoice], eax
0x1800365fe  mov     r9d, eax; lParam
0x180036601  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180036605  mov     edx, 100Ch; Msg
0x18003660a  mov     rcx, rbx; hWnd
0x18003660d  call    cs:__imp_SendMessageA
0x180036613  mov     r12, rax
0x180036616  mov     qword ptr [rsp+0A40h+var_9F0], rax
0x18003661b  xor     edx, edx; Val
0x18003661d  lea     r8d, [r15-8]; Size
0x180036621  lea     rcx, [rsp+0A40h+var_9D8]; void *
0x180036626  call    memset_0
0x18003662b  mov     dword ptr [rsp+0A40h+lParam+4], r12d
0x180036630  mov     dword ptr [rsp+0A40h+lParam], 4
0x180036638  lea     r9, [rsp+0A40h+lParam]; lParam
0x18003663d  xor     r8d, r8d; wParam
0x180036640  mov     edx, 104Bh; Msg
0x180036645  mov     rcx, rbx; hWnd
0x180036648  call    cs:__imp_SendMessageA
0x18003664e  xor     ebx, ebx
0x180036650  test    eax, eax
0x180036652  jnz     short loc_180036664
0x180036654  lea     rcx, [rsp+0A40h+var_A00]
0x180036659  call    ?_Delete@?$unique_ptr@UtagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW@@UCatalogSignerInfoDeleter@@@std@@AEAAXXZ; std::unique_ptr<tagCRYPTUI_VIEWCATALOGSIGNERINFO_STRUCTW,CatalogSignerInfoDeleter>::_Delete(void)
0x18003665e  nop
  ... truncated ...
```
