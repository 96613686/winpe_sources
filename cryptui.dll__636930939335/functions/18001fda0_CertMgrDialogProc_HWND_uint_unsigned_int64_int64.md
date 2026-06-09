# CertMgrDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001fda0`
- end: `0x180020cb7`
- name: `?CertMgrDialogProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `3863`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003400`
- `0x180004fe0`
- `0x18000767c`
- `0x180009624`
- `0x18001332c`
- `0x18001fda0`
- `0x180020e0c`
- `0x180021810`
- `0x1800219f4`
- `0x180021b40`
- `0x1800220b4`
- `0x180022178`
- `0x1800222fc`
- `0x180022ad0`
- `0x1800323e0`
- `0x180032bb8`
- `0x180032c70`
- `0x180033cc0`
- `0x180037f90`
- `0x1800380f0`
- `0x180038270`
- `0x18003e582`
- `0x18003e5c0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800205a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800205a2`
- `CRYPT32!CertOpenStore` at `0x18002026f`
- `CRYPT32!CertOpenStore` at `0x1800203ec`
- `CRYPT32!CertOpenStore` at `0x18002026f`
- `CRYPT32!CertOpenStore` at `0x1800203ec`
- `CRYPT32!CertCloseStore` at `0x1800202ea`
- `CRYPT32!CertCloseStore` at `0x180020414`
- `CRYPT32!CertCloseStore` at `0x1800202ea`
- `CRYPT32!CertCloseStore` at `0x180020414`
- `GDI32!DeleteObject` at `0x1800204f0`
- `GDI32!DeleteObject` at `0x1800204f0`
- `USER32!LoadBitmapA` at `0x1800204c0`
- `USER32!LoadBitmapA` at `0x1800204c0`
- `USER32!SetDlgItemTextW` at `0x180020a7b`
- `USER32!SetDlgItemTextW` at `0x180020a7b`
- `USER32!SendDlgItemMessageA` at `0x180020af1`
- `USER32!SendDlgItemMessageA` at `0x180020bce`
- `USER32!SendDlgItemMessageA` at `0x180020af1`
- `USER32!SendDlgItemMessageA` at `0x180020bce`
- `USER32!SendMessageA` at `0x18001ff9d`
- `USER32!SendMessageA` at `0x18001ffd7`
- `USER32!SendMessageA` at `0x180020065`
- `USER32!SendMessageA` at `0x1800200f3`
- `USER32!SendMessageA` at `0x180020145`
- `USER32!SendMessageA` at `0x1800201f2`
- `USER32!SendMessageA` at `0x180020226`
- `USER32!SendMessageA` at `0x180020246`
- `USER32!SendMessageA` at `0x18002032f`
- `USER32!SendMessageA` at `0x1800203bd`
- `USER32!SendMessageA` at `0x1800204e7`
- `USER32!SendMessageA` at `0x1800205bb`
- `USER32!SendMessageA` at `0x1800205d7`
- `USER32!SendMessageA` at `0x180020625`
- `USER32!SendMessageA` at `0x180020789`
- `USER32!SendMessageA` at `0x1800207da`
- `USER32!SendMessageA` at `0x180020891`
- `USER32!SendMessageA` at `0x1800208c8`
- `USER32!SendMessageA` at `0x180020913`
- `USER32!SendMessageA` at `0x180020972`
- `USER32!SendMessageA` at `0x1800209e9`
- `USER32!SendMessageA` at `0x180020a13`
- `USER32!SendMessageA` at `0x180020b36`
- `USER32!SendMessageA` at `0x18001ff9d`
- `USER32!SendMessageA` at `0x18001ffd7`
- `USER32!SendMessageA` at `0x180020065`
- `USER32!SendMessageA` at `0x1800200f3`
- `USER32!SendMessageA` at `0x180020145`
- `USER32!SendMessageA` at `0x1800201f2`
- `USER32!SendMessageA` at `0x180020226`
- `USER32!SendMessageA` at `0x180020246`
- `USER32!SendMessageA` at `0x18002032f`
- `USER32!SendMessageA` at `0x1800203bd`
- `USER32!SendMessageA` at `0x1800204e7`
- `USER32!SendMessageA` at `0x1800205bb`
- `USER32!SendMessageA` at `0x1800205d7`
- `USER32!SendMessageA` at `0x180020625`
- `USER32!SendMessageA` at `0x180020789`
- `USER32!SendMessageA` at `0x1800207da`
- `USER32!SendMessageA` at `0x180020891`
- `USER32!SendMessageA` at `0x1800208c8`
- `USER32!SendMessageA` at `0x180020913`
- `USER32!SendMessageA` at `0x180020972`
- `USER32!SendMessageA` at `0x1800209e9`
- `USER32!SendMessageA` at `0x180020a13`
- `USER32!SendMessageA` at `0x180020b36`
- `USER32!GetWindowLongPtrA` at `0x18001fe9c`
- `USER32!GetWindowLongPtrA` at `0x1800206e1`
- `USER32!GetWindowLongPtrA` at `0x180020c5a`
- `USER32!GetWindowLongPtrA` at `0x18001fe9c`
- `USER32!GetWindowLongPtrA` at `0x1800206e1`
- `USER32!GetWindowLongPtrA` at `0x180020c5a`
- `USER32!SetWindowLongPtrA` at `0x180020453`
- `USER32!SetWindowLongPtrA` at `0x180020453`
- `USER32!EndDialog` at `0x180020435`
- `USER32!EndDialog` at `0x180020435`
- `USER32!SetWindowTextW` at `0x180020476`
- `USER32!SetWindowTextW` at `0x180020476`
- `USER32!GetDlgItem` at `0x18001ff7c`
- `USER32!GetDlgItem` at `0x18001ffc3`
- `USER32!GetDlgItem` at `0x1800200d1`
- `USER32!GetDlgItem` at `0x180020205`
- `USER32!GetDlgItem` at `0x1800203a9`
- `USER32!GetDlgItem` at `0x180020484`
- `USER32!GetDlgItem` at `0x1800205e5`
- `USER32!GetDlgItem` at `0x18002064b`
- `USER32!GetDlgItem` at `0x18002065c`
- `USER32!GetDlgItem` at `0x1800206c6`
- `USER32!GetDlgItem` at `0x180020765`
- `USER32!GetDlgItem` at `0x1800208a4`
- `USER32!GetDlgItem` at `0x180020926`
- `USER32!GetDlgItem` at `0x180020953`
- `USER32!GetDlgItem` at `0x18002098b`
- `USER32!GetDlgItem` at `0x180020995`
- `USER32!GetDlgItem` at `0x1800209bf`
- `USER32!GetDlgItem` at `0x180020a29`
- `USER32!GetDlgItem` at `0x180020a42`
- `USER32!GetDlgItem` at `0x180020a5b`
- `USER32!GetDlgItem` at `0x180020b15`
- `USER32!GetDlgItem` at `0x180020b75`
- `USER32!GetDlgItem` at `0x180020c3c`
- `USER32!GetDlgItem` at `0x180020c82`
- `USER32!GetDlgItem` at `0x18001ff7c`
- `USER32!GetDlgItem` at `0x18001ffc3`
- `USER32!GetDlgItem` at `0x1800200d1`
- `USER32!GetDlgItem` at `0x180020205`
- `USER32!GetDlgItem` at `0x1800203a9`
- `USER32!GetDlgItem` at `0x180020484`
- `USER32!GetDlgItem` at `0x1800205e5`
- `USER32!GetDlgItem` at `0x18002064b`
- `USER32!GetDlgItem` at `0x18002065c`
- `USER32!GetDlgItem` at `0x1800206c6`
- `USER32!GetDlgItem` at `0x180020765`
- `USER32!GetDlgItem` at `0x1800208a4`
- `USER32!GetDlgItem` at `0x180020926`
- `USER32!GetDlgItem` at `0x180020953`
- `USER32!GetDlgItem` at `0x18002098b`
- `USER32!GetDlgItem` at `0x180020995`
- `USER32!GetDlgItem` at `0x1800209bf`
- `USER32!GetDlgItem` at `0x180020a29`
- `USER32!GetDlgItem` at `0x180020a42`
- `USER32!GetDlgItem` at `0x180020a5b`
- `USER32!GetDlgItem` at `0x180020b15`
- `USER32!GetDlgItem` at `0x180020b75`
- `USER32!GetDlgItem` at `0x180020c3c`
- `USER32!GetDlgItem` at `0x180020c82`
- `USER32!EnableWindow` at `0x18002066f`
- `USER32!EnableWindow` at `0x18002067f`
- `USER32!EnableWindow` at `0x18002095e`
- `USER32!EnableWindow` at `0x1800209a1`
- `USER32!EnableWindow` at `0x1800209d5`
- `USER32!EnableWindow` at `0x180020a34`
- `USER32!EnableWindow` at `0x180020a4d`
- `USER32!EnableWindow` at `0x180020a66`
- `USER32!EnableWindow` at `0x18002066f`
- `USER32!EnableWindow` at `0x18002067f`
- `USER32!EnableWindow` at `0x18002095e`
- `USER32!EnableWindow` at `0x1800209a1`
- `USER32!EnableWindow` at `0x1800209d5`
- `USER32!EnableWindow` at `0x180020a34`
- `USER32!EnableWindow` at `0x180020a4d`
- `USER32!EnableWindow` at `0x180020a66`
- `ole32!RegisterDragDrop` at `0x1800206ae`
- `ole32!RegisterDragDrop` at `0x1800206ae`
- `ole32!RevokeDragDrop` at `0x180020c45`
- `ole32!RevokeDragDrop` at `0x180020c45`

## pseudocode

```c
__int64 __fastcall CertMgrDialogProc(struct _CRYPTUI_CERT_MGR_STRUCT *hWnd, int a2, unsigned __int64 a3, LONG_PTR a4)
{
  unsigned __int64 v5; // r12
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  _QWORD *v12; // rax
  _QWORD *v13; // r15
  __int64 v14; // r14
  HWND v15; // rax
  HWND v16; // r12
  int v17; // eax
  HWND v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  UINT v23; // edx
  HWND v24; // rax
  HWND v25; // r12
  unsigned int v26; // eax
  unsigned int v27; // r13d
  HWND v28; // rax
  HWND v29; // r12
  unsigned int v30; // r13d
  HWND v31; // rbx
  HCERTSTORE v32; // rbx
  unsigned int v33; // eax
  HWND v34; // rax
  struct _CRYPTUI_CERT_MGR_STRUCT *v35; // rax
  const WCHAR *pwszTitle; // rdx
  HWND v37; // r13
  LPARAM v38; // r12
  HBITMAP BitmapA; // rax
  HBITMAP v40; // rbx
  unsigned int v41; // r12d
  WPARAM v42; // rbx
  int v43; // eax
  HWND v44; // rax
  HWND v45; // r12
  int v46; // eax
  HWND v47; // r14
  HWND v48; // rbx
  HWND v49; // rax
  _QWORD *v50; // rax
  _QWORD *v51; // r14
  __int64 v52; // rbx
  int v53; // eax
  HWND v54; // rax
  HWND v55; // r13
  struct _CRYPTUI_CERT_MGR_STRUCT *v56; // rax
  unsigned int v57; // r12d
  HWND v58; // rax
  HWND v59; // rbx
  HWND v60; // rax
  HWND v61; // r12
  BOOL v62; // ebx
  HWND v63; // rax
  HWND v64; // rax
  BOOL v65; // edx
  HWND v66; // rcx
  int v67; // eax
  HWND v68; // rcx
  HWND v69; // rax
  HWND v70; // rax
  HWND v71; // rax
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  unsigned int v75; // ebx
  HWND v76; // rax
  HWND v77; // rbx
  HWND v78; // rax
  HWND DlgItem; // rax
  LONG_PTR WindowLongPtrA; // rax
  __int64 v81; // rcx
  BOOL pfPropertiesChanged; // [rsp+30h] [rbp-5B8h] BYREF
  unsigned __int64 v84; // [rsp+38h] [rbp-5B0h]
  HWND hWnda; // [rsp+40h] [rbp-5A8h] BYREF
  struct _CRYPTUI_CERT_MGR_STRUCT *v86; // [rsp+48h] [rbp-5A0h]
  CRYPTUI_WIZ_EXPORT_INFO pExportInfo; // [rsp+50h] [rbp-598h] BYREF
  UINT uID[4]; // [rsp+80h] [rbp-568h]
  LPARAM v89[2]; // [rsp+90h] [rbp-558h] BYREF
  __int128 v90; // [rsp+A0h] [rbp-548h]
  __int128 v91; // [rsp+B0h] [rbp-538h]
  __int64 v92; // [rsp+C0h] [rbp-528h]
  CRYPTUI_VIEWCERTIFICATE_STRUCTA pCertViewInfo; // [rsp+D0h] [rbp-518h] BYREF
  int lParam; // [rsp+150h] [rbp-498h] BYREF
  unsigned int lParam_4; // [rsp+154h] [rbp-494h]
  _BYTE v96[32]; // [rsp+158h] [rbp-490h] BYREF
  const CERT_CONTEXT *v97; // [rsp+178h] [rbp-470h]
  WCHAR Buffer[512]; // [rsp+1B0h] [rbp-438h] BYREF

  v5 = a3;
  v84 = a3;
  v86 = hWnd;
  LODWORD(hWnda) = 0;
  uID[0] = 6220;
  uID[1] = 6221;
  uID[2] = 6223;
  uID[3] = 6368;
  *(_OWORD *)v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  memset_0(&lParam, 0, 0x58u);
  pfPropertiesChanged = 0;
  memset(&pExportInfo, 0, sizeof(pExportInfo));
  v8 = a2 - 2;
  if ( !v8 )
  {
    DlgItem = GetDlgItem((HWND)hWnd, 1111);
    RevokeDragDrop(DlgItem);
    WindowLongPtrA = GetWindowLongPtrA((HWND)hWnd, 16);
    if ( WindowLongPtrA )
    {
      v81 = *(_QWORD *)(WindowLongPtrA + 80);
      if ( v81 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    }
    GetDlgItem((HWND)hWnd, 1111);
    return 0;
  }
  v9 = v8 - 76;
  if ( !v9 )
  {
    v50 = (_QWORD *)GetWindowLongPtrA((HWND)hWnd, 16);
    v51 = v50;
    if ( !v50 )
      return 0;
    v52 = *v50;
    if ( !*v50 )
      return 0;
    v53 = *(_DWORD *)(a4 + 16);
    switch ( v53 )
    {
      case -551:
        *((_DWORD *)v51 + 13) = 65538;
        *((_DWORD *)v51 + 14) = 131073;
        *((_DWORD *)v51 + 15) = 131076;
        *((_DWORD *)v51 + 16) = 131088;
        *(_QWORD *)((char *)v51 + 68) = 131088;
        RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v51);
        goto LABEL_147;
      case -155:
        if ( *(_WORD *)(a4 + 24) == 46 )
        {
          v78 = GetDlgItem((HWND)hWnd, 1111);
          if ( v78 )
          {
            GetAllSelectedItem(v78, 1u, &hWnda);
            if ( (_DWORD)hWnda )
              SendDlgItemMessageA((HWND)hWnd, 1117, 0xF5u, 0, 0);
            else
              I_MessageBox((HWND)hWnd, 0x191Cu, 0x18DBu, *(LPCWSTR *)(v52 + 24), 0x30u);
          }
        }
        goto LABEL_147;
      case -111:
      case -109:
        v76 = GetDlgItem((HWND)hWnd, 1111);
        v77 = v76;
        if ( v76 && (unsigned int)SendMessageA(v76, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2) != -1 )
          CertMgrUIStartDragDrop(a4, v77, *((unsigned int *)v51 + 10), *((unsigned int *)v51 + 11));
        goto LABEL_147;
      case -108:
        v72 = *(_DWORD *)(a4 + 28);
        if ( v72 && (v73 = v72 - 1) != 0 && (v74 = v73 - 1) != 0 && (unsigned int)(v74 - 1) >= 2 )
          v75 = 0;
        else
          v75 = *((_DWORD *)v51 + *(int *)(a4 + 28) + 13);
        if ( v75 )
        {
          if ( (v75 & 0x10000) != 0 )
          {
            v75 = (unsigned __int16)v75 | 0x20000;
          }
          else if ( (v75 & 0x20000) != 0 )
          {
            v75 = (unsigned __int16)v75 | 0x10000;
          }
          SendDlgItemMessageA((HWND)hWnd, 1111, 0x1030u, v75, (LPARAM)CompareCertificate);
          *((_DWORD *)v51 + *(int *)(a4 + 28) + 13) = v75;
          *((_DWORD *)v51 + 18) = *(_DWORD *)(a4 + 28);
        }
        goto LABEL_147;
    }
    if ( v53 != -101 )
    {
      if ( v53 == -7 )
      {
        v58 = GetDlgItem((HWND)hWnd, 1111);
        v59 = v58;
        if ( v58 && (unsigned int)SendMessageA(v58, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 1) == -1 )
        {
          memset_0(&pCertViewInfo, 0, 0x58u);
          pCertViewInfo.dwFlags = 3;
          HIDWORD(pCertViewInfo.hwndParent) = 3;
          SendMessageA(v59, 0x102Bu, 0, (LPARAM)&pCertViewInfo);
        }
      }
      else if ( v53 == -3 && *(_QWORD *)(a4 + 8) == 1111 )
      {
        v54 = GetDlgItem((HWND)hWnd, 1111);
        v55 = v54;
        if ( v54 )
        {
          v56 = (struct _CRYPTUI_CERT_MGR_STRUCT *)SendMessageA(v54, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
          v57 = (unsigned int)v56;
          v86 = v56;
          if ( (_DWORD)v56 != -1 )
          {
            memset_0(v96, 0, 0x50u);
            lParam = 4;
            lParam_4 = v57;
            if ( (unsigned int)SendMessageA(v55, 0x1005u, 0, (LPARAM)&lParam) )
            {
              if ( *((_DWORD *)v51 + 2) > v57 )
              {
                memset_0(&pCertViewInfo, 0, sizeof(pCertViewInfo));
                pCertViewInfo.dwSize = 120;
                pCertViewInfo.pCertContext = v97;
                pCertViewInfo.hwndParent = (HWND)hWnd;
                pfPropertiesChanged = 0;
                CryptUIDlgViewCertificateA(&pCertViewInfo, &pfPropertiesChanged);
                if ( pfPropertiesChanged )
                {
                  RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v51);
                  memset_0(&pCertViewInfo, 0, 0x58u);
                  pCertViewInfo.dwFlags = 2;
                  HIDWORD(pCertViewInfo.hwndParent) = 2;
                  SendMessageA(v55, 0x102Bu, (int)v86, (LPARAM)&pCertViewInfo);
                }
              }
            }
          }
        }
      }
      goto LABEL_147;
    }
    v60 = GetDlgItem((HWND)hWnd, 1111);
    v61 = v60;
    if ( v60 )
    {
      if ( (*(_BYTE *)(a4 + 32) & 2) != 0 )
      {
        v62 = *((_DWORD *)v51 + 22) != 0;
        v63 = GetDlgItem((HWND)hWnd, 1115);
        EnableWindow(v63, v62);
        if ( (unsigned int)SendMessageA(v61, 0x1032u, 0, 0) <= 1 )
        {
          v64 = GetDlgItem((HWND)hWnd, 1116);
          v65 = 1;
        }
        else
        {
          v64 = GetDlgItem((HWND)hWnd, 1116);
          v65 = 0;
        }
        EnableWindow(v64, v65);
        GetAllSelectedItem(v61, 1u, &hWnda);
        v66 = GetDlgItem((HWND)hWnd, 1117);
        EnableWindow(v66, (_DWORD)hWnda != 0);
        v67 = SendMessageA(v61, 0x1032u, 0, 0);
        v68 = (HWND)hWnd;
        if ( v67 == 1 )
        {
          RefreshCertDetails((HWND)hWnd, *(const struct _CERT_CONTEXT **)(a4 + 56));
          goto LABEL_147;
        }
      }
      else
      {
        if ( (unsigned int)SendMessageA(v60, 0x1032u, 0, 0) )
          goto LABEL_147;
        v69 = GetDlgItem((HWND)hWnd, 1116);
        EnableWindow(v69, 0);
        v70 = GetDlgItem((HWND)hWnd, 1115);
        EnableWindow(v70, 0);
        v71 = GetDlgItem((HWND)hWnd, 1117);
        EnableWindow(v71, 0);
        v68 = (HWND)hWnd;
      }
      SetDlgItemTextW(v68, 1121, L" ");
    }
LABEL_147:
    if ( v84 == 1132 && ((*(_DWORD *)(a4 + 16) + 4) & 0xFFFFFFFD) == 0 )
      DisplayHtmlHelp((HWND)hWnd, (LPCWSTR)(a4 + 136));
    return 0;
  }
  v10 = v9 - 5;
  if ( !v10 )
  {
    v49 = GetDlgItem((HWND)hWnd, 1132);
    InvokeHelpLink(v49);
    return 0;
  }
  v11 = v10 - 189;
  if ( v11 )
  {
    if ( v11 != 1 )
      return 0;
    v12 = (_QWORD *)GetWindowLongPtrA((HWND)hWnd, 16);
    v13 = v12;
    if ( !v12 )
      return 0;
    v14 = *v12;
    if ( !*v12 )
      return 0;
    v86 = (struct _CRYPTUI_CERT_MGR_STRUCT *)(v5 >> 16);
    if ( WORD1(v5) )
      goto LABEL_42;
    switch ( (unsigned __int16)v5 )
    {
      case 1u:
      case 2u:
        EndDialog((HWND)hWnd, 0);
        goto LABEL_42;
      case 0x45Au:
        v32 = 0;
        if ( (*(_DWORD *)(v14 + 16) & 0x8000) != 0 )
        {
          v33 = *(_DWORD *)(v14 + 16) & 0xF;
        }
        else
        {
          v34 = GetDlgItem((HWND)hWnd, 1113);
          v33 = SendMessageA(v34, 0x130Bu, 0, 0);
        }
        if ( v33 < 6 )
          v32 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x11006u, off_180042DB8[v33]);
        CryptUIWizImport(0, (HWND)hWnd, 0, 0, v32);
        if ( v32 )
          CertCloseStore(v32, 0);
        goto LABEL_67;
      case 0x45Bu:
        v28 = GetDlgItem((HWND)hWnd, 1111);
        v29 = v28;
        if ( !v28 )
          goto LABEL_41;
        v30 = SendMessageA(v28, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
        if ( v30 != -1 )
        {
          if ( (unsigned int)SendMessageA(v29, 0x1032u, 0, 0) <= 1 )
          {
            memset_0(v96, 0, 0x50u);
            lParam = 4;
            lParam_4 = v30;
            if ( (unsigned int)SendMessageA(v29, 0x1005u, 0, (LPARAM)&lParam) && *((_DWORD *)v13 + 2) > v30 )
            {
              *(_OWORD *)&pExportInfo.dwSize = 0;
              *(&pExportInfo.dwSubjectChoice + 1) = 0;
              *(_OWORD *)&pExportInfo.cStores = 0;
              pExportInfo.dwSize = 48;
              pExportInfo.dwSubjectChoice = 1;
              pExportInfo.pCertContext = v97;
              CryptUIWizExport(0, (HWND)hWnd, 0, &pExportInfo, 0);
            }
          }
          else
          {
            hWnda = (HWND)CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
            if ( hWnda )
            {
              GetAllSelectedItem(v29, 3u, &hWnda);
              *(_OWORD *)&pExportInfo.dwSize = 0;
              *(&pExportInfo.dwSubjectChoice + 1) = 0;
              *(_OWORD *)&pExportInfo.cStores = 0;
              pExportInfo.dwSize = 48;
              pExportInfo.dwSubjectChoice = 5;
              v31 = hWnda;
              pExportInfo.pCertContext = (PCCERT_CONTEXT)hWnda;
              CryptUIWizExport(0x400u, (HWND)hWnd, 0, &pExportInfo, 0);
              UpdateAllSelectedItems(v29, v31);
              CertCloseStore(v31, 0);
            }
          }
          goto LABEL_41;
        }
        break;
      case 0x45Cu:
        v24 = GetDlgItem((HWND)hWnd, 1111);
        v25 = v24;
        hWnda = v24;
        if ( !v24 )
          goto LABEL_41;
        v26 = SendMessageA(v24, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
        v27 = v26;
        if ( v26 != -1 )
        {
          if ( *((_DWORD *)v13 + 2) > v26 )
          {
            memset_0(v96, 0, 0x50u);
            lParam = 4;
            lParam_4 = v27;
            if ( (unsigned int)SendMessageA(v25, 0x1005u, 0, (LPARAM)&lParam) )
            {
              memset_0(&pCertViewInfo, 0, sizeof(pCertViewInfo));
              pCertViewInfo.dwSize = 120;
              pCertViewInfo.pCertContext = v97;
              pCertViewInfo.hwndParent = (HWND)hWnd;
              pfPropertiesChanged = 0;
              CryptUIDlgViewCertificateA(&pCertViewInfo, &pfPropertiesChanged);
              if ( pfPropertiesChanged )
              {
                RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v13);
                memset_0(&pCertViewInfo, 0, 0x58u);
                pCertViewInfo.dwFlags = 2;
                HIDWORD(pCertViewInfo.hwndParent) = 2;
                SendMessageA(hWnda, 0x102Bu, (int)v27, (LPARAM)&pCertViewInfo);
              }
            }
          }
          goto LABEL_41;
        }
        break;
      case 0x45Du:
        v15 = GetDlgItem((HWND)hWnd, 1111);
        v16 = v15;
        if ( !v15 )
          goto LABEL_41;
        if ( (unsigned int)SendMessageA(v15, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2) != -1 )
        {
          if ( (*(_DWORD *)(v14 + 16) & 0x8000) != 0 )
          {
            v17 = *(_DWORD *)(v14 + 16) & 0xF;
          }
          else
          {
            v18 = GetDlgItem((HWND)hWnd, 1113);
            v17 = SendMessageA(v18, 0x130Bu, 0, 0);
          }
          if ( v17 != -1 )
          {
            if ( v17 )
            {
              v19 = v17 - 1;
              if ( !v19 )
              {
                v23 = 6370;
                goto LABEL_39;
              }
              v20 = v19 - 1;
              if ( !v20 )
              {
                v23 = 6371;
                goto LABEL_39;
              }
              v21 = v20 - 1;
              if ( !v21 )
              {
                v23 = 6372;
                goto LABEL_39;
              }
              v22 = v21 - 1;
              if ( !v22 )
              {
                v23 = 6444;
                goto LABEL_39;
              }
              if ( v22 == 1 )
              {
                v23 = 6446;
                goto LABEL_39;
              }
            }
            v23 = 6369;
LABEL_39:
            if ( (unsigned int)I_MessageBox((HWND)hWnd, v23, 0x18DBu, *(LPCWSTR *)(v14 + 24), 0x34u) == 6 )
            {
              GetAllSelectedItem(v16, 2u, 0);
              SendMessageA((HWND)hWnd, 0x28u, 0, 0);
              RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v13);
            }
          }
LABEL_41:
          LOWORD(v5) = v84;
          goto LABEL_42;
        }
        break;
      default:
        if ( (unsigned __int16)v5 != 1118
          || IsolationAwareDialogBoxParamW(
               HinstDll,
               (LPCWSTR)0xE6,
               (HWND)hWnd,
               (DLGPROC)CertMgrAdvancedProc,
               (LPARAM)v12) != 1
          || *((_DWORD *)v13 + 12) != 1
          || (*((_DWORD *)v13 + 12) = 0,
              RepopulatePurposeCombo((HWND)hWnd, (struct _CERT_MGR_INFO *)v13),
              !(unsigned int)IsAdvancedSelected((HWND)hWnd)) )
        {
LABEL_42:
          if ( (_WORD)v86 == 1 && (_WORD)v5 == 1112 )
            RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v13);
          return 0;
        }
LABEL_67:
        RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)v13);
        goto LABEL_42;
    }
    I_MessageBox((HWND)hWnd, 0x1851u, 0x18DBu, *(LPCWSTR *)(v14 + 24), 0x10u);
    goto LABEL_41;
  }
  SetWindowLongPtrA((HWND)hWnd, 16, a4);
  v35 = *(struct _CRYPTUI_CERT_MGR_STRUCT **)a4;
  v86 = v35;
  if ( v35 )
  {
    pwszTitle = v35->pwszTitle;
    if ( pwszTitle )
      SetWindowTextW((HWND)hWnd, pwszTitle);
    v37 = GetDlgItem((HWND)hWnd, 1111);
    if ( v37 )
    {
      v38 = IsolationAwareImageList_Create(16, 16, 32, 1);
      if ( v38 )
      {
        BitmapA = LoadBitmapA(HinstDll, (LPCSTR)0x133);
        v40 = BitmapA;
        if ( BitmapA )
        {
          IsolationAwareImageList_Add(v38, BitmapA);
          SendMessageA(v37, 0x1003u, 1u, v38);
          DeleteObject(v40);
        }
      }
      *((_QWORD *)&v90 + 1) = 0;
      v91 = 0;
      v92 = 0;
      v89[0] = 15;
      v89[1] = 80;
      *(_QWORD *)&v90 = Buffer;
      v41 = 0;
      v42 = 4;
      while ( v41 < 4 )
      {
        Buffer[0] = 0;
        if ( v41 >= 2 )
        {
          v43 = 105;
          if ( v41 == 2 )
            v43 = 70;
          LODWORD(v89[1]) = v43;
        }
        else
        {
          LODWORD(v89[1]) = 130;
        }
        LoadStringW(HinstDll, uID[v41], Buffer, 512);
        SendMessageA(v37, 0x1061u, (int)v41++, (LPARAM)v89);
      }
      SendMessageA(v37, 0x1036u, 0, 32);
      v44 = GetDlgItem((HWND)hWnd, 1113);
      v45 = v44;
      if ( v44 )
      {
        InitTabControl(v44, v86);
        if ( (v86->dwFlags & 0x800F) != 4 )
          v42 = 0;
        SendMessageA(v45, 0x130Cu, v42, 0);
        InitPurposeCombo((HWND)hWnd, (struct _CERT_MGR_INFO *)a4);
        v46 = IsWizardExtensionAvailable();
        *(_DWORD *)(a4 + 88) = v46;
        if ( !v46 )
        {
          v47 = GetDlgItem((HWND)hWnd, 1114);
          v48 = GetDlgItem((HWND)hWnd, 1115);
          if ( v47 )
            EnableWindow(v47, 0);
          if ( v48 )
            EnableWindow(v48, 0);
        }
        RefreshCertListView((HWND)hWnd, (struct _CERT_MGR_INFO *)a4);
        if ( !(unsigned int)CCertMgrDropTarget_CreateInstance((HWND)hWnd, (struct _CERT_MGR_INFO *)a4) )
          RegisterDragDrop(v37, *(LPDROPTARGET *)(a4 + 80));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001fda0  mov     r11, rsp
0x18001fda3  mov     [r11+10h], rbx
0x18001fda7  mov     [r11+18h], rsi
0x18001fdab  push    rdi
0x18001fdac  push    r12
0x18001fdae  push    r13
0x18001fdb0  push    r14
0x18001fdb2  push    r15
0x18001fdb4  sub     rsp, 5C0h
0x18001fdbb  mov     rax, cs:__security_cookie
0x18001fdc2  xor     rax, rsp
0x18001fdc5  mov     [rsp+5E8h+var_38], rax
0x18001fdcd  mov     r15, r9
0x18001fdd0  mov     r12, r8
0x18001fdd3  mov     [rsp+5E8h+var_5B0], r8
0x18001fdd8  mov     ebx, edx
0x18001fdda  mov     rsi, rcx
0x18001fddd  mov     [rsp+5E8h+var_5A0], rcx
0x18001fde2  xor     edi, edi
0x18001fde4  mov     dword ptr [rsp+5E8h+hWnd], edi
0x18001fde8  mov     [rsp+5E8h+uID], 184Ch
0x18001fdf3  mov     [rsp+5E8h+var_564], 184Dh
0x18001fdfe  mov     [rsp+5E8h+var_560], 184Fh
0x18001fe09  mov     [rsp+5E8h+var_55C], 18E0h
0x18001fe14  xorps   xmm0, xmm0
0x18001fe17  xor     eax, eax
0x18001fe19  movups  xmmword ptr [rsp+5E8h+var_558], xmm0
0x18001fe21  movups  [rsp+5E8h+var_548], xmm0
0x18001fe29  movups  [rsp+5E8h+var_538], xmm0
0x18001fe31  mov     [r11-528h], rax
0x18001fe38  xor     edx, edx; Val
0x18001fe3a  lea     r8d, [rdi+58h]; Size
0x18001fe3e  lea     rcx, [r11-498h]; void *
0x18001fe45  call    memset_0
0x18001fe4a  mov     [rsp+5E8h+pfPropertiesChanged], edi
0x18001fe4e  xorps   xmm0, xmm0
0x18001fe51  movups  xmmword ptr [rsp+5E8h+pExportInfo.dwSize], xmm0
0x18001fe56  movups  xmmword ptr [rsp+5E8h+pExportInfo.dwSubjectChoice], xmm0
0x18001fe5b  movups  xmmword ptr [rsp+5E8h+pExportInfo.cStores], xmm0
0x18001fe60  lea     r13d, [rdi+2]
0x18001fe64  sub     ebx, r13d
0x18001fe67  jz      loc_180020C34
0x18001fe6d  sub     ebx, 4Ch ; 'L'
0x18001fe70  jz      loc_1800206D9
0x18001fe76  sub     ebx, 5
0x18001fe79  jz      loc_1800206BE
0x18001fe7f  sub     ebx, 0BDh
0x18001fe85  jz      loc_180020446
0x18001fe8b  cmp     ebx, 1
0x18001fe8e  jnz     loc_180020C88
0x18001fe94  lea     ebx, [rdi+10h]
0x18001fe97  mov     edx, ebx; nIndex
0x18001fe99  mov     rcx, rsi; hWnd
0x18001fe9c  call    cs:__imp_GetWindowLongPtrA
0x18001fea2  mov     r15, rax
0x18001fea5  test    rax, rax
0x18001fea8  jz      loc_180020C88
0x18001feae  mov     r14, [rax]
0x18001feb1  test    r14, r14
0x18001feb4  jz      loc_180020C88
0x18001feba  mov     rax, r12
0x18001febd  shr     rax, 10h
0x18001fec1  mov     [rsp+5E8h+var_5A0], rax
0x18001fec6  test    ax, ax
0x18001fec9  jnz     loc_18002043B
0x18001fecf  movzx   ecx, r12w
0x18001fed3  sub     ecx, 1
0x18001fed6  jz      loc_180020430
0x18001fedc  sub     ecx, 1
0x18001fedf  jz      loc_180020430
0x18001fee5  mov     eax, 458h
0x18001feea  sub     ecx, eax
0x18001feec  jz      loc_18002038F
0x18001fef2  sub     ecx, 1
0x18001fef5  jz      loc_1800201FD
0x18001fefb  sub     ecx, 1
0x18001fefe  jz      loc_1800200C9
0x18001ff04  sub     ecx, 1
0x18001ff07  jz      short loc_18001FF74
0x18001ff09  cmp     ecx, 1
0x18001ff0c  jnz     short loc_18001FF69
0x18001ff0e  mov     [rsp+5E8h+pvPara], r15; LPARAM
0x18001ff13  lea     r9, ?CertMgrAdvancedProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001ff1a  mov     r8, rsi; hWndParent
0x18001ff1d  mov     edx, 0E6h; lpTemplateName
0x18001ff22  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18001ff29  call    IsolationAwareDialogBoxParamW
0x18001ff2e  lea     r14d, [rdi+1]
0x18001ff32  cmp     rax, r14
0x18001ff35  jnz     loc_180020081
0x18001ff3b  cmp     [r15+30h], r14d
0x18001ff3f  jnz     loc_180020081
0x18001ff45  mov     [r15+30h], edi
0x18001ff49  mov     rdx, r15; struct _CERT_MGR_INFO *
0x18001ff4c  mov     rcx, rsi; hDlg
0x18001ff4f  call    ?RepopulatePurposeCombo@@YAXPEAUHWND__@@PEAU_CERT_MGR_INFO@@@Z; RepopulatePurposeCombo(HWND__ *,_CERT_MGR_INFO *)
0x18001ff54  mov     rcx, rsi; hDlg
0x18001ff57  call    ?IsAdvancedSelected@@YAHPEAUHWND__@@@Z; IsAdvancedSelected(HWND__ *)
0x18001ff5c  test    eax, eax
0x18001ff5e  jnz     loc_180020420
0x18001ff64  jmp     loc_180020081
0x18001ff69  mov     r14d, 1
0x18001ff6f  jmp     loc_180020086
0x18001ff74  mov     edx, 457h; nIDDlgItem
0x18001ff79  mov     rcx, rsi; hDlg
0x18001ff7c  call    cs:__imp_GetDlgItem
0x18001ff82  mov     r12, rax
0x18001ff85  test    rax, rax
0x18001ff88  jz      loc_180020076
0x18001ff8e  mov     r9, r13; lParam
0x18001ff91  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001ff95  mov     edx, 100Ch; Msg
0x18001ff9a  mov     rcx, rax; hWnd
0x18001ff9d  call    cs:__imp_SendMessageA
0x18001ffa3  cmp     eax, 0FFFFFFFFh
0x18001ffa6  jz      loc_1800200AC
0x18001ffac  mov     eax, [r14+10h]
0x18001ffb0  bt      eax, 0Fh
0x18001ffb4  jnb     short loc_18001FFBB
0x18001ffb6  and     eax, 0Fh
0x18001ffb9  jmp     short loc_18001FFDD
0x18001ffbb  mov     edx, 459h; nIDDlgItem
0x18001ffc0  mov     rcx, rsi; hDlg
0x18001ffc3  call    cs:__imp_GetDlgItem
0x18001ffc9  mov     rcx, rax; hWnd
0x18001ffcc  xor     r9d, r9d; lParam
0x18001ffcf  xor     r8d, r8d; wParam
0x18001ffd2  mov     edx, 130Bh; Msg
0x18001ffd7  call    cs:__imp_SendMessageA
0x18001ffdd  cmp     eax, 0FFFFFFFFh
0x18001ffe0  jz      loc_180020076
0x18001ffe6  test    eax, eax
0x18001ffe8  jz      short loc_180020026
0x18001ffea  sub     eax, 1
0x18001ffed  jz      short loc_18002001F
0x18001ffef  sub     eax, 1
0x18001fff2  jz      short loc_180020018
0x18001fff4  sub     eax, 1
0x18001fff7  jz      short loc_180020011
0x18001fff9  sub     eax, 1
0x18001fffc  jz      short loc_18002000A
0x18001fffe  cmp     eax, 1
0x180020001  jnz     short loc_180020026
0x180020003  mov     edx, 192Eh
0x180020008  jmp     short loc_18002002B
0x18002000a  mov     edx, 192Ch
0x18002000f  jmp     short loc_18002002B
0x180020011  mov     edx, 18E4h
0x180020016  jmp     short loc_18002002B
0x180020018  mov     edx, 18E3h
0x18002001d  jmp     short loc_18002002B
0x18002001f  mov     edx, 18E2h
0x180020024  jmp     short loc_18002002B
0x180020026  mov     edx, 18E1h; uID
0x18002002b  mov     dword ptr [rsp+5E8h+pvPara], 34h ; '4'; uType
0x180020033  mov     r9, [r14+18h]; lpCaption
0x180020037  mov     r8d, 18DBh; UINT
0x18002003d  mov     rcx, rsi; hWnd
0x180020040  call    ?I_MessageBox@@YAHPEAUHWND__@@IIPEBGI@Z; I_MessageBox(HWND__ *,uint,uint,ushort const *,uint)
0x180020045  cmp     eax, 6
0x180020048  jnz     short loc_180020076
0x18002004a  xor     r8d, r8d; void *
0x18002004d  mov     edx, r13d; unsigned int
0x180020050  mov     rcx, r12; hWnd
0x180020053  call    ?GetAllSelectedItem@@YAHPEAUHWND__@@KPEAX@Z; GetAllSelectedItem(HWND__ *,ulong,void *)
0x180020058  xor     r9d, r9d; lParam
0x18002005b  xor     r8d, r8d; wParam
0x18002005e  lea     edx, [r9+28h]; Msg
0x180020062  mov     rcx, rsi; hWnd
0x180020065  call    cs:__imp_SendMessageA
0x18002006b  mov     rdx, r15; struct _CERT_MGR_INFO *
0x18002006e  mov     rcx, rsi; HWND
0x180020071  call    RefreshCertListView
0x180020076  mov     r14d, 1
0x18002007c  mov     r12, [rsp+5E8h+var_5B0]
0x180020081  mov     eax, 458h
0x180020086  cmp     word ptr [rsp+5E8h+var_5A0], r14w
0x18002008c  jnz     loc_180020C88
0x180020092  cmp     r12w, ax
0x180020096  jnz     loc_180020C88
0x18002009c  mov     rdx, r15; struct _CERT_MGR_INFO *
0x18002009f  mov     rcx, rsi; HWND
0x1800200a2  call    RefreshCertListView
0x1800200a7  jmp     loc_180020C88
0x1800200ac  mov     dword ptr [rsp+5E8h+pvPara], ebx; uType
0x1800200b0  mov     r9, [r14+18h]; lpCaption
0x1800200b4  mov     edx, 1851h; uID
0x1800200b9  mov     r8d, 18DBh; UINT
0x1800200bf  mov     rcx, rsi; hWnd
0x1800200c2  call    ?I_MessageBox@@YAHPEAUHWND__@@IIPEBGI@Z; I_MessageBox(HWND__ *,uint,uint,ushort const *,uint)
0x1800200c7  jmp     short loc_180020076
0x1800200c9  mov     edx, 457h; nIDDlgItem
0x1800200ce  mov     rcx, rsi; hDlg
0x1800200d1  call    cs:__imp_GetDlgItem
0x1800200d7  mov     r12, rax
0x1800200da  mov     [rsp+5E8h+hWnd], rax
0x1800200df  test    rax, rax
0x1800200e2  jz      short loc_180020076
0x1800200e4  mov     r9, r13; lParam
0x1800200e7  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800200eb  mov     edx, 100Ch; Msg
0x1800200f0  mov     rcx, rax; hWnd
0x1800200f3  call    cs:__imp_SendMessageA
0x1800200f9  mov     r13, rax
0x1800200fc  cmp     eax, 0FFFFFFFFh
0x1800200ff  jz      short loc_1800200AC
0x180020101  cmp     [r15+8], r13d
0x180020105  jbe     loc_180020076
0x18002010b  xor     edx, edx; Val
0x18002010d  lea     r8d, [rdx+50h]; Size
0x180020111  lea     rcx, [rsp+5E8h+var_490]; void *
0x180020119  call    memset_0
0x18002011e  mov     ebx, 4
0x180020123  mov     dword ptr [rsp+5E8h+lParam], ebx
0x18002012a  mov     dword ptr [rsp+5E8h+lParam+4], r13d
0x180020132  lea     r9, [rsp+5E8h+lParam]; lParam
0x18002013a  xor     r8d, r8d; wParam
0x18002013d  mov     edx, 1005h; Msg
0x180020142  mov     rcx, r12; hWnd
0x180020145  call    cs:__imp_SendMessageA
0x18002014b  test    eax, eax
0x18002014d  jz      loc_180020076
0x180020153  lea     r12d, [rbx+74h]
0x180020157  mov     r8d, r12d; Size
0x18002015a  xor     edx, edx; Val
0x18002015c  lea     rcx, [rsp+5E8h+pCertViewInfo]; void *
0x180020164  call    memset_0
0x180020169  mov     [rsp+5E8h+pCertViewInfo.dwSize], r12d
0x180020171  mov     rax, [rsp+5E8h+var_470]
0x180020179  mov     [rsp+5E8h+pCertViewInfo.pCertContext], rax
0x180020181  mov     [rsp+5E8h+pCertViewInfo.hwndParent], rsi
0x180020189  mov     [rsp+5E8h+pfPropertiesChanged], edi
0x18002018d  lea     rdx, [rsp+5E8h+pfPropertiesChanged]; pfPropertiesChanged
0x180020192  lea     rcx, [rsp+5E8h+pCertViewInfo]; pCertViewInfo
0x18002019a  call    CryptUIDlgViewCertificateA
0x18002019f  cmp     [rsp+5E8h+pfPropertiesChanged], edi
0x1800201a3  jz      loc_180020076
0x1800201a9  mov     rdx, r15; struct _CERT_MGR_INFO *
0x1800201ac  mov     rcx, rsi; HWND
0x1800201af  call    RefreshCertListView
0x1800201b4  xor     edx, edx; Val
0x1800201b6  lea     r8d, [rbx+54h]; Size
0x1800201ba  lea     rcx, [rsp+5E8h+pCertViewInfo]; void *
0x1800201c2  call    memset_0
0x1800201c7  mov     [rsp+5E8h+pCertViewInfo.dwFlags], 2
0x1800201d2  mov     dword ptr [rsp+5E8h+pCertViewInfo.hwndParent+4], 2
0x1800201dd  movsxd  r8, r13d; wParam
0x1800201e0  lea     r9, [rsp+5E8h+pCertViewInfo]; lParam
0x1800201e8  mov     edx, 102Bh; Msg
0x1800201ed  mov     rcx, [rsp+5E8h+hWnd]; hWnd
0x1800201f2  call    cs:__imp_SendMessageA
0x1800201f8  jmp     loc_180020076
0x1800201fd  mov     edx, 457h; nIDDlgItem
0x180020202  mov     rcx, rsi; hDlg
0x180020205  call    cs:__imp_GetDlgItem
0x18002020b  mov     r12, rax
0x18002020e  test    rax, rax
0x180020211  jz      loc_180020076
0x180020217  mov     r9, r13; lParam
0x18002021a  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18002021e  mov     edx, 100Ch; Msg
0x180020223  mov     rcx, rax; hWnd
0x180020226  call    cs:__imp_SendMessageA
0x18002022c  mov     r13, rax
0x18002022f  cmp     eax, 0FFFFFFFFh
0x180020232  jz      loc_1800200AC
0x180020238  xor     r9d, r9d; lParam
0x18002023b  xor     r8d, r8d; wParam
0x18002023e  mov     edx, 1032h; Msg
0x180020243  mov     rcx, r12; hWnd
0x180020246  call    cs:__imp_SendMessageA
0x18002024c  mov     r14d, 1
0x180020252  cmp     eax, r14d
0x180020255  jbe     loc_1800202F5
0x18002025b  mov     [rsp+5E8h+pvPara], rdi; pvPara
0x180020260  xor     r9d, r9d; dwFlags
0x180020263  xor     r8d, r8d; hCryptProv
0x180020266  mov     edx, 10001h; dwEncodingType
0x18002026b  lea     ecx, [r14+1]; lpszStoreProvider
0x18002026f  call    cs:__imp_CertOpenStore
0x180020275  mov     [rsp+5E8h+hWnd], rax
0x18002027a  test    rax, rax
0x18002027d  jz      loc_18002007C
0x180020283  lea     r8, [rsp+5E8h+hWnd]; void *
0x180020288  lea     edx, [r14+2]; unsigned int
0x18002028c  mov     rcx, r12; hWnd
0x18002028f  call    ?GetAllSelectedItem@@YAHPEAUHWND__@@KPEAX@Z; GetAllSelectedItem(HWND__ *,ulong,void *)
0x180020294  xorps   xmm0, xmm0
0x180020297  movups  xmmword ptr [rsp+5E8h+pExportInfo.dwSize], xmm0
0x18002029c  movups  xmmword ptr [rsp+5E8h+pExportInfo.dwSubjectChoice], xmm0
0x1800202a1  movups  xmmword ptr [rsp+5E8h+pExportInfo.cStores], xmm0
0x1800202a6  mov     [rsp+5E8h+pExportInfo.dwSize], 30h ; '0'
0x1800202ae  mov     [rsp+5E8h+pExportInfo.dwSubjectChoice], 5
0x1800202b6  mov     rbx, [rsp+5E8h+hWnd]
0x1800202bb  mov     qword ptr [rsp+5E8h+pExportInfo.18h], rbx
0x1800202c0  mov     [rsp+5E8h+pvPara], rdi; pvoid
0x1800202c5  lea     r9, [rsp+5E8h+pExportInfo]; pExportInfo
0x1800202ca  xor     r8d, r8d; pwszWizardTitle
0x1800202cd  mov     rdx, rsi; hwndParent
0x1800202d0  mov     ecx, 400h; dwFlags
  ... truncated ...
```
