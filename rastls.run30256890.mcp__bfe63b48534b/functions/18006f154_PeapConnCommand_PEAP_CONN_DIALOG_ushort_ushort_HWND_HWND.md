# PeapConnCommand(_PEAP_CONN_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x18006f154`
- end: `0x18006fad7`
- name: `?PeapConnCommand@@YAHPEAU_PEAP_CONN_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `2435`
- prototype: `__int64 __usercall@<rax>(struct _PEAP_CONN_DIALOG *@<rcx>, unsigned __int16@<dx>, unsigned __int16@<r8w>, HWND@<r9>, HWND)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fae0`

## callees

- `0x180005010`
- `0x180011cc8`
- `0x180038e4c`
- `0x18004d58c`
- `0x180069f00`
- `0x18006a004`
- `0x18006f154`
- `0x18007022c`
- `0x1800703b8`
- `0x180071b64`
- `0x18007bdb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006f943`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006f943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f42a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f59d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f791`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f3ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f4c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f577`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f774`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f3ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f400`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f4c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f577`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f774`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f683`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f6a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f7c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f683`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f6a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f7c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fa76`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f29c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f2c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f84d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f29c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f2c4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006f84d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f2e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f343`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f35a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f2e8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f343`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006f35a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006f52d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006f5d8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006f52d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18006f5d8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006f672`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18006f672`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006f7e4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006f7e4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f1c8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f1f7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f223`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f81c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f8a2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f1c8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f1f7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f223`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f81c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006f8a2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x18006f266`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x18006f266`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006f482`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006f498`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006f482`
- `ext-ms-win-ntuser-window-l1-1-1!GetWindowTextLengthW` at `0x18006f498`

## pseudocode

```c
__int64 __fastcall PeapConnCommand(struct _PEAP_CONN_DIALOG *a1, __int16 a2, unsigned __int16 a3, HWND a4, HWND a5)
{
  unsigned int v7; // ebp
  HWND v8; // r15
  UINT v9; // eax
  __int64 v10; // rdx
  int v11; // ecx
  unsigned int v12; // ecx
  UINT v13; // eax
  __int64 v14; // rdx
  int v15; // ecx
  unsigned int v16; // ecx
  UINT v17; // eax
  __int64 v18; // rdx
  int v19; // ecx
  UINT v20; // r8d
  int v22; // eax
  LRESULT v23; // rax
  int v24; // edx
  int v25; // eax
  unsigned int v26; // r8d
  HWND v27; // rcx
  __int64 v28; // r13
  DWORD LastError; // eax
  __int64 v30; // rdx
  struct _EAPTLS_HASH *v31; // rax
  __int64 v32; // r14
  __int64 v33; // rax
  unsigned int v34; // r14d
  WCHAR *v35; // rax
  WCHAR *v36; // rdi
  DWORD v37; // eax
  WCHAR *v38; // rax
  WCHAR *v39; // r15
  DWORD v40; // eax
  unsigned __int16 *v41; // rsi
  unsigned __int16 *v42; // rax
  const WCHAR *v43; // rdx
  const WCHAR *v44; // r8
  unsigned __int16 *v45; // rdi
  int v46; // ebx
  int v47; // r8d
  unsigned int v48; // r13d
  __int64 v49; // rax
  unsigned int v50; // ecx
  struct _EAPTLS_CONTROL_BLOCK *v51; // rcx
  __int64 v52; // rdx
  _DWORD *v53; // rax
  _DWORD *v54; // r15
  DWORD v55; // eax
  struct _EAPTLS_HASH *v56; // r13
  UINT v57; // eax
  unsigned int v58; // edx
  int v59; // eax
  int v60; // r8d
  __int64 v61; // rdx
  int v62; // ecx
  __int64 v63; // rax
  UINT v64; // eax
  unsigned int v65; // edx
  int v66; // eax
  _DWORD *v67; // r14
  __int64 v68; // rax
  __int64 v69; // rdx
  size_t v70; // rax
  const void *v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rcx
  char *v74; // rcx
  WCHAR *v75; // r14
  void *v76; // rcx
  unsigned int v77; // [rsp+20h] [rbp-78h]
  unsigned int v78; // [rsp+30h] [rbp-68h]
  int nMaxCount; // [rsp+34h] [rbp-64h]
  struct _EAPTLS_HASH *hMem; // [rsp+38h] [rbp-60h]
  WCHAR *Src; // [rsp+40h] [rbp-58h]
  WCHAR *v82; // [rsp+48h] [rbp-50h]
  unsigned __int64 v83; // [rsp+50h] [rbp-48h]
  int v84; // [rsp+50h] [rbp-48h]
  struct _EAPTLS_CERT_NODE **v85; // [rsp+58h] [rbp-40h]

  v7 = 1;
  v8 = a4;
  switch ( a3 )
  {
    case 1u:
      v27 = (HWND)*((_QWORD *)a1 + 11);
      v7 = 0;
      LODWORD(a5) = 0;
      CertListSelectedCount(v27, (unsigned int *)&a5);
      v28 = (unsigned int)a5;
      v78 = (unsigned int)a5;
      if ( (_DWORD)a5 )
      {
        v85 = (struct _EAPTLS_CERT_NODE **)LocalAlloc(0x40u, 8LL * (unsigned int)a5);
        if ( !v85 )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return 1;
          LastError = GetLastError();
          v30 = 213;
LABEL_43:
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v30,
            &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
            LastError);
          return 1;
        }
        v31 = (struct _EAPTLS_HASH *)LocalAlloc(0x40u, 24 * v28);
        hMem = v31;
        if ( !v31 )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return 1;
          LastError = GetLastError();
          v30 = 214;
          goto LABEL_43;
        }
        CertListSelected(*((HWND *)a1 + 11), *((struct _EAPTLS_CERT_NODE **)a1 + 1), v85, v31, v77);
      }
      else
      {
        hMem = 0;
        v85 = 0;
      }
      v82 = 0;
      LODWORD(v32) = GetWindowTextLengthW(*((HWND *)a1 + 8));
      LODWORD(v33) = GetWindowTextLengthW(*((HWND *)a1 + 17));
      LODWORD(a5) = v33;
      if ( (_DWORD)v32 )
      {
        v34 = v32 + 1;
        v35 = (WCHAR *)LocalAlloc(0x40u, 2LL * v34);
        v82 = v35;
        v36 = v35;
        if ( !v35 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v37 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v37);
          }
          goto LABEL_84;
        }
        GetWindowTextW(*((HWND *)a1 + 8), v35, v34);
        v32 = -1;
        do
          ++v32;
        while ( v36[v32] );
        LODWORD(v33) = (_DWORD)a5;
      }
      if ( (_DWORD)v33 )
      {
        nMaxCount = v33 + 1;
        v83 = (unsigned int)(v33 + 1);
        v38 = (WCHAR *)LocalAlloc(0x40u, 2 * v83);
        Src = v38;
        v39 = v38;
        if ( !v38 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v40 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v40);
          }
          goto LABEL_83;
        }
        GetWindowTextW(*((HWND *)a1 + 17), v38, nMaxCount);
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            217,
            (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
            (_DWORD)v39,
            (char)a5);
        if ( !(unsigned int)isValidIdentity(v39, v83) )
        {
          v41 = WszFromId(g_hInstance, 0x64Cu);
          v42 = WszFromId(g_hInstance, 0x64Du);
          v43 = &String;
          v44 = &String;
          v45 = v42;
          if ( v41 )
            v44 = v41;
          if ( v42 )
            v43 = v42;
          v46 = MessageBoxW(a4, v43, v44, 0x10u);
          LocalFree(v41);
          LocalFree(v45);
          LocalFree(v39);
          LOBYTE(v7) = v46 != 0;
          return v7;
        }
        v33 = -1;
        do
          ++v33;
        while ( v39[v33] );
      }
      else
      {
        Src = 0;
      }
      v47 = 2 * v33 + 2;
      v84 = v33;
      LODWORD(a5) = 2 * (v32 + 12 * v28);
      v48 = v47 + (_DWORD)a5 + 38;
      if ( v48 < (int)a5 + 38 )
      {
        v51 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          return 1;
        v52 = 218;
        goto LABEL_118;
      }
      v49 = *((_QWORD *)a1 + 5);
      if ( v49 )
      {
        v50 = v48 + 15;
        if ( *(_QWORD *)(v49 + 152) )
        {
          v47 = *(_DWORD *)(v49 + 160);
          v48 = v47 + v50;
          if ( v47 + v50 < v50 )
          {
            v51 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              return 1;
            v52 = 219;
LABEL_118:
            WPP_SF_DD(*((_QWORD *)v51 + 2), v52, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, 0xFFFFFFFFLL, v47);
            return 1;
          }
        }
        else
        {
          v47 = *(_DWORD *)(v49 + 144);
          v48 = v47 + v50;
          if ( v47 + v50 < v50 )
          {
            v51 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              return 1;
            v52 = 220;
            goto LABEL_118;
          }
        }
      }
      v53 = LocalAlloc(0x40u, v48);
      v54 = v53;
      if ( !v53 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v55 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v55);
        }
        v56 = hMem;
LABEL_82:
        LocalFree(v56);
LABEL_83:
        v8 = a4;
LABEL_84:
        v7 = 1;
        goto LABEL_85;
      }
      v53[1] = v48;
      *v53 = 1;
      v53[2] = *((_QWORD *)a1 + 5) != 0;
      v57 = IsDlgButtonChecked(a4, 1025);
      v58 = v54[3] | 1;
      if ( v57 != 1 )
        v58 = v54[3] & 0xFFFFFFFE;
      v54[3] = v58;
      v59 = SendMessageW(*((HWND *)a1 + 9), 0x147u, 0, 0);
      v60 = v59;
      if ( v59 != -1 )
      {
        v61 = *((_QWORD *)a1 + 3);
        v62 = *(_DWORD *)(v61 + 24);
        if ( !v59 )
        {
          *(_DWORD *)(v61 + 24) = v62 | 0x20;
          v63 = *((_QWORD *)a1 + 3);
LABEL_92:
          *(_DWORD *)(v63 + 24) &= ~0x200u;
          goto LABEL_94;
        }
        *(_DWORD *)(v61 + 24) = v62 & 0xFFFFFFDF;
        v63 = *((_QWORD *)a1 + 3);
        if ( v60 == 1 )
          goto LABEL_92;
        *(_DWORD *)(v63 + 24) |= 0x200u;
      }
LABEL_94:
      v54[3] &= ~8u;
      v64 = IsDlgButtonChecked(a4, 1609);
      v56 = hMem;
      v65 = v54[3] | 4;
      if ( v64 != 1 )
        v65 = v54[3] & 0xFFFFFFFB;
      v54[3] = v65;
      v54[3] = v65 | *(_DWORD *)(*((_QWORD *)a1 + 3) + 12LL) & 0x10;
      v66 = (_DWORD)a5 + 22;
      *((_OWORD *)v54 + 1) = *(_OWORD *)(*((_QWORD *)a1 + 3) + 16LL);
      v54[5] = v66;
      if ( hMem )
        memcpy_0(v54 + 8, hMem, 24LL * v78);
      v54[4] = 2;
      v54[7] = v78;
      if ( (_DWORD)v32 )
        _o_wcscpy_s(&v54[4 * v78 + 8 + 2 * v78], (unsigned int)(v32 + 1), v82);
      v67 = (_DWORD *)((char *)&v54[6 * v78 + 8] + 2 * (unsigned int)v32 + 2);
      if ( !*((_QWORD *)a1 + 5) )
      {
        v73 = 0;
        goto LABEL_109;
      }
      *v67 = 1;
      v67[2] = *(_DWORD *)(*((_QWORD *)a1 + 5) + 8LL);
      v67[1] = 15;
      v68 = *((_QWORD *)a1 + 5);
      if ( *(_QWORD *)(v68 + 152) )
      {
        v67[1] = *(_DWORD *)(v68 + 160) + 15;
        v69 = *((_QWORD *)a1 + 5);
        v70 = *(unsigned int *)(v69 + 160);
        if ( (_DWORD)v70 )
        {
          v71 = *(const void **)(v69 + 152);
LABEL_106:
          memcpy_0(v67 + 3, v71, v70);
        }
      }
      else
      {
        v67[1] = *(_DWORD *)(v68 + 144) + 15;
        v72 = *((_QWORD *)a1 + 5);
        v70 = *(unsigned int *)(v72 + 144);
        if ( (_DWORD)v70 )
        {
          v71 = *(const void **)(v72 + 136);
          goto LABEL_106;
        }
      }
      v73 = (unsigned int)v67[1];
LABEL_109:
      if ( v84 )
      {
        v74 = (char *)v67 + v73;
        v75 = Src;
        memcpy_0(v74, Src, 2LL * (unsigned int)(v84 + 1));
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            222,
            (unsigned int)&WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
            (_DWORD)Src,
            v84);
      }
      else
      {
        v75 = Src;
      }
      LocalFree(v75);
      LocalFree(v82);
      LocalFree(*((HLOCAL *)a1 + 3));
      v76 = (void *)*((_QWORD *)a1 + 2);
      if ( v76 )
        LocalFree(v76);
      *((_QWORD *)a1 + 2) = v85;
      *((_QWORD *)a1 + 3) = v54;
      goto LABEL_82;
    case 2u:
LABEL_85:
      EndDialog(v8, a3);
      return v7;
    case 0x3F4u:
      if ( a2 != 1 )
        return 0;
      break;
    case 0x3F5u:
      break;
    case 0x516u:
      v17 = IsDlgButtonChecked(a4, 1302);
      v18 = *((_QWORD *)a1 + 3);
      v19 = *(_DWORD *)(v18 + 24);
      if ( v17 == 1 )
      {
        v20 = 1;
        *(_DWORD *)(v18 + 24) = v19 & 0xFFFFFFFD;
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 24LL) &= ~4u;
      }
      else
      {
        *(_DWORD *)(v18 + 24) = v19 | 2;
        *(_DWORD *)(*((_QWORD *)a1 + 3) + 24LL) |= 4u;
        v20 = 0;
      }
      CheckDlgButton(v8, 1303, v20);
      goto LABEL_20;
    case 0x517u:
      v13 = IsDlgButtonChecked(a4, 1303);
      v14 = *((_QWORD *)a1 + 3);
      v15 = *(_DWORD *)(v14 + 24);
      if ( v13 == 1 )
        v16 = v15 & 0xFFFFFFFB;
      else
        v16 = v15 | 4;
      *(_DWORD *)(v14 + 24) = v16;
      goto LABEL_20;
    case 0x64Au:
      v9 = IsDlgButtonChecked(a4, 1610);
      v10 = *((_QWORD *)a1 + 3);
      v11 = *(_DWORD *)(v10 + 12);
      if ( v9 == 1 )
        v12 = v11 | 0x10;
      else
        v12 = v11 & 0xFFFFFFEF;
      *(_DWORD *)(v10 + 12) = v12;
LABEL_20:
      PeapEnableValidateNameControls(a1);
      return v7;
    default:
      return 0;
  }
  v22 = SendMessageW(*((HWND *)a1 + 12), 0x147u, 0, 0);
  if ( v22 == -1 )
  {
    EnableWindow(*((HWND *)a1 + 13), 0);
    *((_QWORD *)a1 + 5) = 0;
  }
  else
  {
    v23 = SendMessageW(*((HWND *)a1 + 12), 0x150u, v22, 0);
    *((_QWORD *)a1 + 5) = v23;
    if ( v23 && *(_QWORD *)(v23 + 32) )
    {
      EnableWindow(*((HWND *)a1 + 13), 1);
      v24 = *(_DWORD *)a1 & 1 | 0x80;
      if ( (*(_DWORD *)a1 & 2) == 0 )
        v24 = *(_DWORD *)a1 & 1;
      v25 = v24 | 0x80000;
      if ( (*(_DWORD *)a1 & 0x80000) == 0 )
        v25 = v24;
      v26 = v25 | 2;
      if ( a3 == 1013 )
        v26 = v25;
      PeapEapInfoInvokeClientConfigUI(v8, *((HMODULE **)a1 + 5), v26);
    }
    else
    {
      EnableWindow(*((HWND *)a1 + 13), 0);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18006f154  mov     [rsp+arg_0], rbx
0x18006f159  mov     [rsp+hWnd], r9
0x18006f15e  mov     [rsp+arg_10], r8w
0x18006f164  push    rbp
0x18006f165  push    rsi
0x18006f166  push    rdi
0x18006f167  push    r12
0x18006f169  push    r13
0x18006f16b  push    r14
0x18006f16d  push    r15
0x18006f16f  sub     rsp, 60h
0x18006f173  mov     rbx, rcx
0x18006f176  movzx   esi, r8w
0x18006f17a  mov     ecx, esi
0x18006f17c  mov     ebp, 1
0x18006f181  mov     r15, r9
0x18006f184  sub     ecx, ebp
0x18006f186  jz      loc_18006F371
0x18006f18c  sub     ecx, ebp
0x18006f18e  jz      loc_18006F7D9
0x18006f194  sub     ecx, 3F2h
0x18006f19a  jz      loc_18006F281
0x18006f1a0  sub     ecx, ebp
0x18006f1a2  jz      loc_18006F28D
0x18006f1a8  sub     ecx, 121h
0x18006f1ae  jz      short loc_18006F21B
0x18006f1b0  sub     ecx, ebp
0x18006f1b2  jz      short loc_18006F1EF
0x18006f1b4  cmp     ecx, 133h
0x18006f1ba  jnz     loc_18006F286
0x18006f1c0  mov     edx, 64Ah; nIDButton
0x18006f1c5  mov     rcx, r9; hDlg
0x18006f1c8  call    cs:__imp_IsDlgButtonChecked
0x18006f1cf  nop     dword ptr [rax+rax+00h]
0x18006f1d4  mov     rdx, [rbx+18h]
0x18006f1d8  mov     ecx, [rdx+0Ch]
0x18006f1db  cmp     eax, ebp
0x18006f1dd  jnz     short loc_18006F1E4
0x18006f1df  or      ecx, 10h
0x18006f1e2  jmp     short loc_18006F1E7
0x18006f1e4  and     ecx, 0FFFFFFEFh
0x18006f1e7  mov     [rdx+0Ch], ecx
0x18006f1ea  jmp     loc_18006F272
0x18006f1ef  mov     edx, 517h; nIDButton
0x18006f1f4  mov     rcx, r15; hDlg
0x18006f1f7  call    cs:__imp_IsDlgButtonChecked
0x18006f1fe  nop     dword ptr [rax+rax+00h]
0x18006f203  mov     rdx, [rbx+18h]
0x18006f207  mov     ecx, [rdx+18h]
0x18006f20a  cmp     eax, ebp
0x18006f20c  jnz     short loc_18006F213
0x18006f20e  and     ecx, 0FFFFFFFBh
0x18006f211  jmp     short loc_18006F216
0x18006f213  or      ecx, 4
0x18006f216  mov     [rdx+18h], ecx
0x18006f219  jmp     short loc_18006F272
0x18006f21b  mov     edx, 516h; nIDButton
0x18006f220  mov     rcx, r15; hDlg
0x18006f223  call    cs:__imp_IsDlgButtonChecked
0x18006f22a  nop     dword ptr [rax+rax+00h]
0x18006f22f  mov     rdx, [rbx+18h]
0x18006f233  mov     ecx, [rdx+18h]
0x18006f236  cmp     eax, ebp
0x18006f238  jnz     short loc_18006F24D
0x18006f23a  and     ecx, 0FFFFFFFDh
0x18006f23d  mov     r8d, ebp
0x18006f240  mov     [rdx+18h], ecx
0x18006f243  mov     rax, [rbx+18h]
0x18006f247  and     dword ptr [rax+18h], 0FFFFFFFBh
0x18006f24b  jmp     short loc_18006F25E
0x18006f24d  or      ecx, 2
0x18006f250  mov     [rdx+18h], ecx
0x18006f253  mov     rax, [rbx+18h]
0x18006f257  or      dword ptr [rax+18h], 4
0x18006f25b  xor     r8d, r8d; uCheck
0x18006f25e  mov     edx, 517h; nIDButton
0x18006f263  mov     rcx, r15; hDlg
0x18006f266  call    cs:__imp_CheckDlgButton
0x18006f26d  nop     dword ptr [rax+rax+00h]
0x18006f272  mov     rcx, rbx; struct _PEAP_CONN_DIALOG *
0x18006f275  call    ?PeapEnableValidateNameControls@@YAXPEAU_PEAP_CONN_DIALOG@@@Z; PeapEnableValidateNameControls(_PEAP_CONN_DIALOG *)
0x18006f27a  mov     eax, ebp
0x18006f27c  jmp     loc_18006FABE
0x18006f281  cmp     bp, dx
0x18006f284  jz      short loc_18006F28D
0x18006f286  xor     eax, eax
0x18006f288  jmp     loc_18006FABE
0x18006f28d  mov     rcx, [rbx+60h]; hWnd
0x18006f291  xor     r9d, r9d; lParam
0x18006f294  xor     r8d, r8d; wParam
0x18006f297  mov     edx, 147h; Msg
0x18006f29c  call    cs:__imp_SendMessageW
0x18006f2a3  nop     dword ptr [rax+rax+00h]
0x18006f2a8  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006f2ac  cmp     eax, r12d
0x18006f2af  jz      loc_18006F354
0x18006f2b5  mov     rcx, [rbx+60h]; hWnd
0x18006f2b9  xor     r9d, r9d; lParam
0x18006f2bc  movsxd  r8, eax; wParam
0x18006f2bf  mov     edx, 150h; Msg
0x18006f2c4  call    cs:__imp_SendMessageW
0x18006f2cb  nop     dword ptr [rax+rax+00h]
0x18006f2d0  xor     ebp, ebp
0x18006f2d2  mov     [rbx+28h], rax
0x18006f2d6  test    rax, rax
0x18006f2d9  jz      short loc_18006F33D
0x18006f2db  cmp     [rax+20h], rbp
0x18006f2df  jz      short loc_18006F33D
0x18006f2e1  mov     rcx, [rbx+68h]; hWnd
0x18006f2e5  lea     edx, [rbp+1]; bEnable
0x18006f2e8  call    cs:__imp_EnableWindow
0x18006f2ef  nop     dword ptr [rax+rax+00h]
0x18006f2f4  mov     r8d, [rbx]
0x18006f2f7  mov     ecx, r8d
0x18006f2fa  and     ecx, 1
0x18006f2fd  mov     edx, ecx
0x18006f2ff  bts     edx, 7
0x18006f303  test    r8b, 2
0x18006f307  cmovz   edx, ecx
0x18006f30a  mov     ecx, 80000h
0x18006f30f  mov     eax, edx
0x18006f311  or      eax, ecx
0x18006f313  test    ecx, r8d
0x18006f316  mov     ecx, 3F5h
0x18006f31b  cmovz   eax, edx
0x18006f31e  mov     rdx, [rbx+28h]; struct _PEAP_EAP_INFO *
0x18006f322  mov     r8d, eax
0x18006f325  or      r8d, 2
0x18006f329  cmp     si, cx
0x18006f32c  mov     rcx, r15; HWND
0x18006f32f  cmovz   r8d, eax; unsigned int
0x18006f333  call    ?PeapEapInfoInvokeClientConfigUI@@YAKPEAUHWND__@@PEAU_PEAP_EAP_INFO@@K@Z; PeapEapInfoInvokeClientConfigUI(HWND__ *,_PEAP_EAP_INFO *,ulong)
0x18006f338  jmp     loc_18006FAB9
0x18006f33d  mov     rcx, [rbx+68h]; hWnd
0x18006f341  xor     edx, edx; bEnable
0x18006f343  call    cs:__imp_EnableWindow
0x18006f34a  nop     dword ptr [rax+rax+00h]
0x18006f34f  jmp     loc_18006FAB9
0x18006f354  mov     rcx, [rbx+68h]; hWnd
0x18006f358  xor     edx, edx; bEnable
0x18006f35a  call    cs:__imp_EnableWindow
0x18006f361  nop     dword ptr [rax+rax+00h]
0x18006f366  xor     ebp, ebp
0x18006f368  mov     [rbx+28h], rbp
0x18006f36c  jmp     loc_18006FAB9
0x18006f371  mov     rcx, [rbx+58h]; hWnd
0x18006f375  lea     rdx, [rsp+98h+arg_20]; unsigned int *
0x18006f37d  xor     ebp, ebp
0x18006f37f  mov     dword ptr [rsp+98h+arg_20], ebp
0x18006f386  call    ?CertListSelectedCount@@YAXPEAUHWND__@@PEAK@Z; CertListSelectedCount(HWND__ *,ulong *)
0x18006f38b  mov     r13d, dword ptr [rsp+98h+arg_20]
0x18006f393  mov     [rsp+98h+var_68], r13d
0x18006f398  test    r13d, r13d
0x18006f39b  jz      loc_18006F46F
0x18006f3a1  lea     rdx, ds:0[r13*8]; uBytes
0x18006f3a9  lea     ecx, [rbp+40h]; uFlags
0x18006f3ac  call    cs:__imp_LocalAlloc
0x18006f3b3  nop     dword ptr [rax+rax+00h]
0x18006f3b8  mov     [rsp+98h+var_40], rax
0x18006f3bd  mov     rsi, rax
0x18006f3c0  test    rax, rax
0x18006f3c3  jnz     short loc_18006F3EC
0x18006f3c5  lea     rdi, WPP_GLOBAL_Control
0x18006f3cc  cmp     cs:WPP_GLOBAL_Control, rdi
0x18006f3d3  jz      loc_18006FAB9
0x18006f3d9  call    cs:__imp_GetLastError
0x18006f3e0  nop     dword ptr [rax+rax+00h]
0x18006f3e5  mov     edx, 0D5h
0x18006f3ea  jmp     short loc_18006F43B
0x18006f3ec  lea     rdx, ds:0[r13*2]
0x18006f3f4  mov     ecx, 40h ; '@'; uFlags
0x18006f3f9  add     rdx, r13
0x18006f3fc  shl     rdx, 3; uBytes
0x18006f400  call    cs:__imp_LocalAlloc
0x18006f407  nop     dword ptr [rax+rax+00h]
0x18006f40c  mov     [rsp+98h+hMem], rax
0x18006f411  test    rax, rax
0x18006f414  jnz     short loc_18006F45A
0x18006f416  lea     rdi, WPP_GLOBAL_Control
0x18006f41d  cmp     cs:WPP_GLOBAL_Control, rdi
0x18006f424  jz      loc_18006FAB9
0x18006f42a  call    cs:__imp_GetLastError
0x18006f431  nop     dword ptr [rax+rax+00h]
0x18006f436  mov     edx, 0D6h
0x18006f43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f442  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006f449  mov     r9d, eax
0x18006f44c  mov     rcx, [rcx+10h]
0x18006f450  call    WPP_SF_d
0x18006f455  jmp     loc_18006FAB9
0x18006f45a  mov     rdx, [rbx+8]; struct _EAPTLS_CERT_NODE *
0x18006f45e  mov     r9, rax; struct _EAPTLS_HASH *
0x18006f461  mov     rcx, [rbx+58h]; hWnd
0x18006f465  mov     r8, rsi; struct _EAPTLS_CERT_NODE **
0x18006f468  call    ?CertListSelected@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_NODE@@PEAPEAU2@PEAU_EAPTLS_HASH@@K@Z; CertListSelected(HWND__ *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_NODE * *,_EAPTLS_HASH *,ulong)
0x18006f46d  jmp     short loc_18006F479
0x18006f46f  mov     [rsp+98h+hMem], rbp
0x18006f474  mov     [rsp+98h+var_40], rbp
0x18006f479  mov     rcx, [rbx+40h]; hWnd
0x18006f47d  mov     [rsp+98h+var_50], rbp
0x18006f482  call    cs:__imp_GetWindowTextLengthW
0x18006f489  nop     dword ptr [rax+rax+00h]
0x18006f48e  mov     rcx, [rbx+88h]; hWnd
0x18006f495  mov     r14d, eax
0x18006f498  call    cs:__imp_GetWindowTextLengthW
0x18006f49f  nop     dword ptr [rax+rax+00h]
0x18006f4a4  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006f4a8  mov     dword ptr [rsp+98h+arg_20], eax
0x18006f4af  test    r14d, r14d
0x18006f4b2  jz      loc_18006F54D
0x18006f4b8  inc     r14d
0x18006f4bb  lea     ecx, [r12+41h]; uFlags
0x18006f4c0  mov     edx, r14d
0x18006f4c3  add     rdx, rdx; uBytes
0x18006f4c6  call    cs:__imp_LocalAlloc
0x18006f4cd  nop     dword ptr [rax+rax+00h]
0x18006f4d2  mov     [rsp+98h+var_50], rax
0x18006f4d7  mov     rdi, rax
0x18006f4da  test    rax, rax
0x18006f4dd  jnz     short loc_18006F523
0x18006f4df  lea     rdi, WPP_GLOBAL_Control
0x18006f4e6  cmp     cs:WPP_GLOBAL_Control, rdi
0x18006f4ed  jz      loc_18006F7D4
0x18006f4f3  call    cs:__imp_GetLastError
0x18006f4fa  nop     dword ptr [rax+rax+00h]
0x18006f4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f506  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006f50d  mov     edx, 0D7h
0x18006f512  mov     r9d, eax
0x18006f515  mov     rcx, [rcx+10h]
0x18006f519  call    WPP_SF_d
0x18006f51e  jmp     loc_18006F7D4
0x18006f523  mov     rcx, [rbx+40h]; hWnd
0x18006f527  mov     r8d, r14d; nMaxCount
0x18006f52a  mov     rdx, rdi; lpString
0x18006f52d  call    cs:__imp_GetWindowTextW
0x18006f534  nop     dword ptr [rax+rax+00h]
0x18006f539  mov     r14, r12
0x18006f53c  inc     r14
0x18006f53f  cmp     [rdi+r14*2], bp
0x18006f544  jnz     short loc_18006F53C
0x18006f546  mov     eax, dword ptr [rsp+98h+arg_20]
0x18006f54d  lea     rdi, WPP_GLOBAL_Control
0x18006f554  lea     rsi, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006f55b  test    eax, eax
0x18006f55d  jz      loc_18006F6C7
0x18006f563  inc     eax
0x18006f565  mov     ecx, 40h ; '@'; uFlags
0x18006f56a  mov     [rsp+98h+nMaxCount], eax
0x18006f56e  mov     [rsp+98h+var_48], rax
0x18006f573  lea     rdx, [rax+rax]; uBytes
0x18006f577  call    cs:__imp_LocalAlloc
0x18006f57e  nop     dword ptr [rax+rax+00h]
0x18006f583  mov     [rsp+98h+Src], rax
0x18006f588  mov     r15, rax
0x18006f58b  test    rax, rax
0x18006f58e  jnz     short loc_18006F5C9
0x18006f590  cmp     cs:WPP_GLOBAL_Control, rdi
0x18006f597  jz      loc_18006F7CC
0x18006f59d  call    cs:__imp_GetLastError
0x18006f5a4  nop     dword ptr [rax+rax+00h]
0x18006f5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5b0  mov     edx, 0D8h
0x18006f5b5  mov     r9d, eax
0x18006f5b8  mov     r8, rsi
0x18006f5bb  mov     rcx, [rcx+10h]
0x18006f5bf  call    WPP_SF_d
0x18006f5c4  jmp     loc_18006F7CC
0x18006f5c9  mov     r8d, [rsp+98h+nMaxCount]; nMaxCount
0x18006f5ce  mov     rdx, r15; lpString
0x18006f5d1  mov     rcx, [rbx+88h]; hWnd
0x18006f5d8  call    cs:__imp_GetWindowTextW
0x18006f5df  nop     dword ptr [rax+rax+00h]
0x18006f5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5eb  cmp     rcx, rdi
0x18006f5ee  jz      short loc_18006F60F
0x18006f5f0  mov     eax, dword ptr [rsp+98h+arg_20]
0x18006f5f7  mov     edx, 0D9h
0x18006f5fc  mov     rcx, [rcx+10h]
0x18006f600  mov     r9, r15
0x18006f603  mov     r8, rsi
0x18006f606  mov     [rsp+98h+var_78], eax
0x18006f60a  call    WPP_SF_Sd
0x18006f60f  mov     rdx, [rsp+98h+var_48]; unsigned __int64
0x18006f614  mov     rcx, r15; unsigned __int16 *
0x18006f617  call    ?isValidIdentity@@YAHPEAG_K@Z; isValidIdentity(ushort *,unsigned __int64)
0x18006f61c  test    eax, eax
0x18006f61e  jnz     loc_18006F6B8
0x18006f624  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006f62b  mov     edx, 64Ch; uID
0x18006f630  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x18006f635  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006f63c  mov     edx, 64Dh; uID
0x18006f641  mov     rsi, rax
0x18006f644  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x18006f649  mov     rcx, [rsp+98h+hWnd]; hWnd
0x18006f651  lea     rdx, String
0x18006f658  mov     r8, rdx
0x18006f65b  test    rsi, rsi
0x18006f65e  mov     r9d, 10h; uType
  ... truncated ...
```
