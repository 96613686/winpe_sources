# sub_1402FED0C

- ea: `0x1402fed0c`
- end: `0x1402ffe1b`
- name: `sub_1402FED0C`
- size: `4367`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140301fd2`

## callees

- `0x140042c98`
- `0x14005e7d0`
- `0x14007d1e0`
- `0x14007d520`
- `0x140087310`
- `0x140087de0`
- `0x14008d690`
- `0x14008d6d0`
- `0x14009fa52`
- `0x1400c1130`
- `0x1400c2510`
- `0x1400c2540`
- `0x1400c30d0`
- `0x1400c3120`
- `0x1400cd110`
- `0x1400cd440`
- `0x1400cd490`
- `0x1400e4070`
- `0x1400ec5e0`
- `0x1400ec980`
- `0x14012cfce`
- `0x14012fc90`
- `0x140160e00`
- `0x14025fd50`
- `0x140260110`
- `0x1402601e0`
- `0x1402fe0a3`
- `0x1402fe2c0`
- `0x1402feb8a`
- `0x1402fed0c`
- `0x1402ffe1b`
- `0x14030269a`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x1402ff12e`
- `ADVAPI32!RevertToSelf` at `0x1402ff12e`

## string_xrefs

- `0x1402fed45`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402fed5a`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402fefb9`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402feff3`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff011`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff059`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff06e`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff1d5`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff1ea`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff286`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff29b`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff57e`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff593`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff7b7`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff7d0`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff8d0`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff8e5`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff966`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff97b`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffa0d`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffa22`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffb59`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffb6e`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffc6d`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffc8b`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffccd`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ffce9`: `..\..\chrome\installer\util\edge_msix_installer.cc`
- `0x1402ff9a6`: `Failed to CoCreate IPackageManager: `
- `0x1402ff2c6`: `There is no active user to impersonate.`
- `0x1402ffd14`: `There is no active user to impersonate.`
- `0x1402ffcb6`: `There is no version on the device matching the installer version.`
- `0x1402ff099`: `Failed to register MSIX package with hr:`
- `0x1402ff03c`: `Timed out waiting for MSIX package to be registered.`

## pseudocode

```c
__int64 __fastcall sub_1402FED0C(__int64 a1, __int128 *a2, __int64 a3, char a4, char a5, unsigned __int8 a6, char a7)
{
  int v11; // eax
  int v12; // eax
  HSTRING v13; // rbx
  char v14; // di
  HSTRING v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  __int128 *v22; // rdi
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  int v26; // ebx
  HSTRING v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // r15
  __int64 v30; // rax
  HSTRING v31; // r15
  HSTRING v32; // rax
  const char *v33; // rdx
  __int64 v34; // rcx
  HSTRING v35; // rax
  WCHAR *v36; // rbx
  __int64 v37; // rax
  char v38; // di
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // r14
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // r15
  __int64 v49; // rbx
  HSTRING *v50; // r13
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // rbx
  __int64 v54; // r13
  int v55; // eax
  __int64 v56; // rax
  HSTRING v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  int v60; // eax
  __int64 v61; // rax
  __int64 v62; // rax
  int v63; // eax
  HSTRING v64; // rcx
  int v65; // eax
  __int64 v66; // rcx
  __int64 v67; // [rsp+0h] [rbp-348h] BYREF
  HSTRING v68; // [rsp+40h] [rbp-308h] BYREF
  __int64 v69; // [rsp+48h] [rbp-300h] BYREF
  __int64 v70; // [rsp+50h] [rbp-2F8h] BYREF
  _QWORD v71[2]; // [rsp+58h] [rbp-2F0h] BYREF
  __int64 v72; // [rsp+68h] [rbp-2E0h]
  _QWORD *v73; // [rsp+70h] [rbp-2D8h]
  __int64 v74; // [rsp+78h] [rbp-2D0h]
  HSTRING *v75; // [rsp+80h] [rbp-2C8h]
  __int64 v76; // [rsp+88h] [rbp-2C0h]
  const WCHAR *v77; // [rsp+90h] [rbp-2B8h]
  __int64 v78; // [rsp+98h] [rbp-2B0h]
  WCHAR sourceString[8]; // [rsp+A0h] [rbp-2A8h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-298h]
  __int128 v81; // [rsp+C0h] [rbp-288h] BYREF
  _QWORD v82[2]; // [rsp+D0h] [rbp-278h] BYREF
  __int128 v83; // [rsp+E0h] [rbp-268h] BYREF
  __int64 v84; // [rsp+F0h] [rbp-258h]
  _QWORD v85[4]; // [rsp+100h] [rbp-248h] BYREF
  __int128 v86; // [rsp+120h] [rbp-228h] BYREF
  __int128 v87; // [rsp+130h] [rbp-218h] BYREF
  __int64 v88; // [rsp+140h] [rbp-208h]
  __int128 v89; // [rsp+150h] [rbp-1F8h]
  __int64 v90; // [rsp+168h] [rbp-1E0h] BYREF
  __int64 v91; // [rsp+170h] [rbp-1D8h] BYREF
  __int64 (__fastcall ***v92)(_QWORD, __int64 *, HSTRING *); // [rsp+178h] [rbp-1D0h] BYREF
  __int128 v93; // [rsp+180h] [rbp-1C8h] BYREF
  HSTRING v94[2]; // [rsp+190h] [rbp-1B8h] BYREF
  __int128 v95; // [rsp+1A0h] [rbp-1A8h]
  HSTRING v96[40]; // [rsp+1B0h] [rbp-198h] BYREF

  if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
  {
    sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 588, 0xFFFFFFFFLL);
    sub_140042C98((__int64)&v96[2], (__int64)"RegisterPackage", 15);
    sub_1400EC980(v96);
  }
  v92 = 0;
  sub_1400C30D0(v96, L"Windows.Management.Deployment.PackageManager");
  v11 = RoActivateInstance(v96[0], &v92);
  if ( v11 < 0 )
  {
    LODWORD(v13) = v11;
    goto LABEL_37;
  }
  v91 = 2147500037LL;
  v90 = 0;
  if ( !a4 )
  {
    v94[0] = 0;
    v12 = (**v92)(v92, qword_140358DE8, v94);
    if ( v12 < 0 )
    {
      LODWORD(v13) = v12;
    }
    else
    {
      if ( !a7 )
        goto LABEL_7;
      v25 = sub_1402FEB8A(&v91);
      if ( v25 == 315 )
      {
        if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
        {
          sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 622, 0xFFFFFFFFLL);
          sub_140042C98((__int64)&v96[2], (__int64)"There is no active user to impersonate.", 39);
          sub_1400EC980(v96);
        }
        v14 = 0;
        LODWORD(v13) = 0;
        goto LABEL_11;
      }
      LODWORD(v13) = v25;
      if ( v25 >= 0 )
      {
LABEL_7:
        v13 = v94[0];
        v89 = *a2;
        sub_1400C2540(v96);
        (*(void (__fastcall **)(HSTRING, HSTRING, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v13 + 64LL))(
          v13,
          v96[1],
          0,
          a6,
          0,
          0,
          &v90);
        v96[0] = (HSTRING)&off_140313288;
        if ( LOBYTE(v96[2]) == 1 )
          goto LABEL_148;
        if ( v96[1] )
          j_WindowsDeleteString(v96[1]);
        v14 = 1;
LABEL_11:
        v15 = v94[0];
        if ( v94[0] )
        {
          v94[0] = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
        }
        if ( !v14 )
          goto LABEL_30;
LABEL_14:
        *(_OWORD *)v94 = 0;
        sub_14005E7D0((__int64 *)v94, 1, 1);
        v16 = sub_14008D690(32, &byte_14032F109);
        v17 = (_QWORD *)v16;
        if ( v16 )
        {
          *(_DWORD *)(v16 + 12) = 1;
          *(_QWORD *)v16 = off_140312B00;
          if ( qword_14038CA78 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_14038CA78 + 8LL))(qword_14038CA78);
          v17[2] = a1;
          v17[3] = v94;
          *v17 = off_140313260;
        }
        LODWORD(v13) = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v90 + 64LL))(v90, v17);
        if ( (int)v13 < 0 )
        {
          if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) <= 0 )
          {
LABEL_27:
            if ( v17 )
              (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
            sub_14007D1E0(v94);
            goto LABEL_30;
          }
          sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 742, 0xFFFFFFFFLL);
          v18 = sub_140042C98((__int64)&v96[2], (__int64)"Failed to register MSIX package with hr:", 40);
          *(_DWORD *)(v18 + *(int *)(*(_QWORD *)v18 + 4LL) + 8) = *(_DWORD *)(v18 + *(int *)(*(_QWORD *)v18 + 4LL) + 8)
                                                                & 0xFFFFFFB5
                                                                | 8;
          sub_14009FA52(v18, (unsigned int)v13);
        }
        else
        {
          sub_140087DE0(v96, "RegisterPackage", "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 746);
          if ( (unsigned __int8)sub_14007D520(v94, 300000000, v96) )
            goto LABEL_27;
          LODWORD(v13) = -2147024638;
          if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) <= 0 )
            goto LABEL_27;
          sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 747, 0xFFFFFFFFLL);
          sub_140042C98((__int64)&v96[2], (__int64)"Timed out waiting for MSIX package to be registered.", 52);
        }
        sub_1400EC980(v96);
        goto LABEL_27;
      }
    }
    v14 = 0;
    goto LABEL_11;
  }
  v22 = &v87;
  v87 = 0;
  v88 = 0;
  v86 = *a2;
  v23 = sub_1402FE0A3(&v86, &v87);
  if ( v23 < 0 )
  {
    LODWORD(v13) = v23;
    if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
    {
      sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 641, 0xFFFFFFFFLL);
      v24 = sub_140042C98((__int64)&v96[2], (__int64)"Failed to get provisioned versions with hr: ", 44);
      *(_DWORD *)(v24 + *(int *)(*(_QWORD *)v24 + 4LL) + 8) = *(_DWORD *)(v24 + *(int *)(*(_QWORD *)v24 + 4LL) + 8)
                                                            & 0xFFFFFFB5
                                                            | 8;
      sub_14009FA52(v24, (unsigned int)v13);
      sub_1400EC980(v96);
    }
    v96[0] = (HSTRING)&v87;
    sub_14030269A();
    goto LABEL_30;
  }
  LOBYTE(v22) = a5;
  memset(v85, 0, 24);
  sub_1402FFE1B(v85, &v87, a3, (unsigned int)v22);
  if ( !(unsigned __int8)sub_1400CD440(v85) )
  {
    if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
    {
      sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 649, 0xFFFFFFFFLL);
      v49 = sub_140042C98((__int64)&v96[2], (__int64)"The version ", 12);
      v50 = v94;
      sub_1400CD490(a3, v94);
      v51 = SBYTE7(v95);
      if ( SBYTE7(v95) < 0 )
      {
        v51 = (__int64)v94[1];
        v50 = (HSTRING *)v94[0];
      }
      v52 = sub_140042C98(v49, (__int64)v50, v51);
      sub_140042C98(v52, (__int64)" is not provisioned. Trying to find all versions.", 49);
      if ( SBYTE7(v95) < 0 )
        sub_14008D6D0(v94[0], v95 & 0x7FFFFFFFFFFFFFFFLL);
      sub_1400EC980(v96);
    }
    v53 = *((_QWORD *)&v87 + 1);
    v54 = v87;
    if ( (_QWORD)v87 != *((_QWORD *)&v87 + 1) )
    {
      while ( 1 )
      {
        v53 -= 24;
        if ( !v53 )
          break;
        sub_1400CD110(v53);
        if ( v53 == v54 )
          goto LABEL_104;
      }
LABEL_130:
      BUG();
    }
LABEL_104:
    *((_QWORD *)&v87 + 1) = v54;
    v93 = *a2;
    if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
    {
      sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 144, 0xFFFFFFFFLL);
      sub_140042C98((__int64)&v96[2], (__int64)"GetAllPackageVersions", 21);
      sub_1400EC980(v96);
    }
    v94[0] = 0;
    sub_1400C30D0(v96, L"Windows.Management.Deployment.PackageManager");
    v55 = RoActivateInstance(v96[0], v94);
    if ( v55 >= 0 )
    {
      *(_QWORD *)&v83 = 0;
      v60 = (*(__int64 (__fastcall **)(HSTRING, __int128 *))(*(_QWORD *)v94[0] + 88LL))(v94[0], &v83);
      if ( v60 >= 0 )
      {
        v96[0] = (HSTRING)v83;
        if ( (_QWORD)v83 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v83 + 8LL))(v83);
        LODWORD(v13) = sub_1402FE2C0(&v93, v96, &v87);
      }
      else
      {
        LODWORD(v13) = v60;
        if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
        {
          sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 162, 0xFFFFFFFFLL);
          v61 = sub_140042C98((__int64)&v96[2], (__int64)"Failed to find packages with hr: ", 33);
          *(_DWORD *)(v61 + *(int *)(*(_QWORD *)v61 + 4LL) + 8) = *(_DWORD *)(v61 + *(int *)(*(_QWORD *)v61 + 4LL) + 8)
                                                                & 0xFFFFFFB5
                                                                | 8;
          sub_14009FA52(v61, (unsigned int)v13);
          sub_1400EC980(v96);
        }
      }
      v59 = v83;
      if ( (_QWORD)v83 )
      {
        *(_QWORD *)&v83 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      }
    }
    else
    {
      LODWORD(v13) = v55;
      if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
      {
        sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 154, 0xFFFFFFFFLL);
        v56 = sub_140042C98((__int64)&v96[2], (__int64)"Failed to CoCreate IPackageManager: ", 36);
        *(_DWORD *)(v56 + *(int *)(*(_QWORD *)v56 + 4LL) + 8) = *(_DWORD *)(v56 + *(int *)(*(_QWORD *)v56 + 4LL) + 8)
                                                              & 0xFFFFFFB5
                                                              | 8;
        sub_14009FA52(v56, (unsigned int)v13);
        sub_1400EC980(v96);
      }
    }
    v57 = v94[0];
    if ( v94[0] )
    {
      v94[0] = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v57 + 16LL))(v57);
    }
    if ( (int)v13 >= 0 )
    {
      sub_1402FFE1B(v96, &v87, a3, (unsigned int)v22);
      if ( v85[0] )
      {
        v62 = v85[1];
        while ( v62 != v85[0] )
        {
          v62 -= 4;
          if ( !v62 )
            goto LABEL_130;
        }
        v85[1] = v85[0];
        sub_14008D6D0(v85[0], v85[2] - v85[0]);
      }
      v85[0] = v96[0];
      *(_OWORD *)&v85[1] = *(_OWORD *)&v96[1];
      memset(v96, 0, 24);
      sub_1400CD110(v96);
      if ( (unsigned __int8)sub_1400CD440(v85) )
        goto LABEL_52;
      LODWORD(v13) = -2147023727;
      if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
      {
        sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 662, 0xFFFFFFFFLL);
        sub_140042C98(
          (__int64)&v96[2],
          (__int64)"There is no version on the device matching the installer version.",
          65);
        goto LABEL_114;
      }
    }
    else if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
    {
      sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 654, 0xFFFFFFFFLL);
      v58 = sub_140042C98((__int64)&v96[2], (__int64)"Failed to get provisioned versions with hr: ", 44);
      *(_DWORD *)(v58 + *(int *)(*(_QWORD *)v58 + 4LL) + 8) = *(_DWORD *)(v58 + *(int *)(*(_QWORD *)v58 + 4LL) + 8)
                                                            & 0xFFFFFFB5
                                                            | 8;
      sub_14009FA52(v58, (unsigned int)v13);
LABEL_114:
      sub_1400EC980(v96);
    }
    v38 = 0;
    goto LABEL_116;
  }
LABEL_52:
  v26 = sub_1400C1130();
  v84 = 0;
  v83 = 0;
  v82[0] = "_";
  v82[1] = 1;
  v81 = *a2;
  sub_1402601E0((unsigned int)&v83, (unsigned int)&v81, (unsigned int)v82, 0, 0);
  v80 = 0;
  *(_OWORD *)sourceString = 0;
  v77 = &word_14032C15C;
  v78 = 0;
  v27 = (HSTRING)v83;
  if ( *((_QWORD *)&v83 + 1) == (_QWORD)v83 )
    goto LABEL_130;
  v28 = *(char *)(v83 + 23);
  if ( v28 < 0 )
  {
    v28 = *(_QWORD *)(v83 + 8);
    v27 = *(HSTRING *)v83;
  }
  v96[0] = v27;
  v96[1] = (HSTRING)v28;
  v96[2] = (HSTRING)"_";
  v96[3] = (HSTRING)1;
  v29 = v71;
  sub_1400CD490(v85, v71);
  v30 = SHIBYTE(v72);
  if ( v72 < 0 )
  {
    v30 = v71[1];
    v29 = (_QWORD *)v71[0];
  }
  v73 = v29;
  v74 = v30;
  v31 = (HSTRING)v94;
  sub_14025FD50(v94);
  v32 = (HSTRING)SBYTE7(v95);
  if ( SBYTE7(v95) < 0 )
  {
    v32 = v94[1];
    v31 = v94[0];
  }
  v96[4] = v31;
  v96[5] = v32;
  v96[6] = (HSTRING)"_";
  v96[7] = (HSTRING)1;
  v33 = "x";
  if ( v26 == 4 )
    v33 = "a";
  v96[8] = (HSTRING)v33;
  v96[9] = (HSTRING)(2LL * (v26 == 4) + 3);
  v96[10] = (HSTRING)"_";
  v96[11] = (HSTRING)2;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v83 + 1) - v83) >> 3) <= 1 )
    goto LABEL_130;
  v34 = *(char *)(v83 + 47);
  if ( v34 < 0 )
  {
    v34 = *(_QWORD *)(v83 + 32);
    v35 = *(HSTRING *)(v83 + 24);
  }
  else
  {
    v35 = (HSTRING)(v83 + 24);
  }
  v96[12] = v35;
  v96[13] = (HSTRING)v34;
  v75 = v96;
  v76 = 7;
  v36 = sourceString;
  sub_140260110((int)sourceString);
  if ( SBYTE7(v95) < 0 )
    sub_14008D6D0(v94[0], 2 * v95);
  if ( v72 < 0 )
    sub_14008D6D0(v71[0], v72 & 0x7FFFFFFFFFFFFFFFLL);
  if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
  {
    sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 682, 0xFFFFFFFFLL);
    v37 = sub_140042C98((__int64)&v96[2], (__int64)"Registering package with full name: ", 36);
    sub_1400E4070(v37, sourceString);
    sub_1400EC980(v96);
  }
  v95 = 0;
  *(_OWORD *)v94 = 0;
  if ( v80 < 0 )
    v36 = *(WCHAR **)sourceString;
  sub_1400C30D0(v94, v36);
  v38 = 0;
  v71[0] = 0;
  sub_14012CFCE(v71);
  (*(void (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)v71[0] + 104LL))(v71[0], v94[0]);
  v70 = 0;
  v39 = (**(__int64 (__fastcall ***)(_QWORD, __int128 *, __int64 *))v71[0])(v71[0], &xmmword_140358D98, &v70);
  if ( v39 < 0 )
  {
    LODWORD(v13) = v39;
    goto LABEL_80;
  }
  v69 = 0;
  sub_1400C30D0(v96, L"Windows.Management.Deployment.RegisterPackageOptions");
  v40 = RoActivateInstance(v96[0], &v69);
  if ( v40 >= 0 )
  {
    LOBYTE(v41) = 1;
    v40 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 216LL))(v69, v41);
    if ( v40 >= 0 )
    {
      v68 = 0;
      v63 = (**v92)(v92, qword_140358DF8, &v68);
      if ( v63 >= 0 )
      {
        if ( !a7 )
          goto LABEL_145;
        v65 = sub_1402FEB8A(&v91);
        if ( v65 == 315 )
        {
          v38 = 0;
          LODWORD(v13) = 0;
          if ( (int)sub_140087310("..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 51) > 0 )
          {
            sub_1400EC5E0(v96, "..\\..\\chrome\\installer\\util\\edge_msix_installer.cc", 722, 0xFFFFFFFFLL);
            sub_140042C98((__int64)&v96[2], (__int64)"There is no active user to impersonate.", 39);
            sub_1400EC980(v96);
            v38 = 0;
            LODWORD(v13) = 0;
          }
          goto LABEL_140;
        }
        LODWORD(v13) = v65;
        if ( v65 >= 0 )
        {
LABEL_145:
          v13 = v68;
          v66 = v90;
          if ( v90 )
          {
            v90 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
          }
          (*(void (__fastcall **)(HSTRING, __int64, __int64, __int64 *))(*(_QWORD *)v13 + 80LL))(v13, v70, v69, &v90);
          v38 = 1;
          goto LABEL_140;
        }
      }
      else
      {
        LODWORD(v13) = v63;
      }
      v38 = 0;
LABEL_140:
      v64 = v68;
      if ( v68 )
      {
        v68 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v64 + 16LL))(v64);
      }
      goto LABEL_77;
    }
  }
  LODWORD(v13) = v40;
  v38 = 0;
LABEL_77:
  v42 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
LABEL_80:
  v43 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v71[0];
  if ( v71[0] )
  {
    v71[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( v80 < 0 )
    sub_14008D6D0(*(_QWORD *)sourceString, 2 * v80);
  v45 = v83;
  if ( (_QWORD)v83 )
  {
    v46 = *((_QWORD *)&v83 + 1);
    v47 = v83;
    if ( (_QWORD)v83 != *((_QWORD *)&v83 + 1) )
    {
      v48 = *((_QWORD *)&v83 + 1);
      do
      {
        v48 -= 24;
        if ( !v48 )
          goto LABEL_130;
        if ( *(char *)(v46 - 1) < 0 )
          sub_14008D6D0(*(_QWORD *)(v46 - 24), 2LL * *(_QWORD *)(v46 - 8));
        v46 = v48;
      }
      while ( v48 != v45 );
      v47 = v83;
    }
    *((_QWORD *)&v83 + 1) = v45;
    sub_14008D6D0(v47, v84 - v47);
  }
LABEL_116:
  sub_1400CD110(v85);
  v96[0] = (HSTRING)&v87;
  sub_14030269A();
  if ( v38 )
    goto LABEL_14;
LABEL_30:
  v19 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( !(_DWORD)v91 && !BYTE4(v91) && !RevertToSelf() )
  {
    __debugbreak();
    BUG();
  }
LABEL_37:
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v92;
  if ( v92 )
  {
    v92 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
  }
  if ( _security_cookie != ((unsigned __int64)&v67 ^ (unsigned __int64)v96[39]) )
LABEL_148:
    __debugbreak();
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1402fed0c  push    r15
0x1402fed0e  push    r14
0x1402fed10  push    r13
0x1402fed12  push    r12
0x1402fed14  push    rsi
0x1402fed15  push    rdi
0x1402fed16  push    rbp
0x1402fed17  push    rbx
0x1402fed18  sub     rsp, 308h
0x1402fed1f  movaps  [rsp+348h+var_58], xmm6
0x1402fed27  mov     edi, r9d
0x1402fed2a  mov     r12, r8
0x1402fed2d  mov     r15, rdx
0x1402fed30  mov     rsi, rcx
0x1402fed33  mov     rax, cs:__security_cookie
0x1402fed3a  xor     rax, rsp
0x1402fed3d  mov     [rsp+348h+var_60], rax
0x1402fed45  lea     rcx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402fed4c  mov     edx, 33h ; '3'
0x1402fed51  call    sub_140087310
0x1402fed56  test    eax, eax
0x1402fed58  jle     short loc_1402FED9F
0x1402fed5a  lea     rdx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402fed61  lea     rbx, [rsp+348h+var_198]
0x1402fed69  mov     rcx, rbx
0x1402fed6c  mov     r8d, 24Ch
0x1402fed72  mov     r9d, 0FFFFFFFFh
0x1402fed78  call    sub_1400EC5E0
0x1402fed7d  lea     rcx, [rsp+348h+var_188]
0x1402fed85  lea     rdx, aRegisterpackag; "RegisterPackage"
0x1402fed8c  mov     r8d, 0Fh
0x1402fed92  call    sub_140042C98
0x1402fed97  mov     rcx, rbx
0x1402fed9a  call    sub_1400EC980
0x1402fed9f  lea     rbx, [rsp+348h+var_1D0]
0x1402feda7  mov     qword ptr [rbx], 0
0x1402fedae  lea     rdx, sourceString; "Windows.Management.Deployment.PackageMa"...
0x1402fedb5  lea     r14, [rsp+348h+var_198]
0x1402fedbd  mov     rcx, r14; string
0x1402fedc0  call    sub_1400C30D0
0x1402fedc5  mov     rcx, [r14]
0x1402fedc8  mov     rdx, rbx
0x1402fedcb  call    RoActivateInstance
0x1402fedd0  test    eax, eax
0x1402fedd2  js      loc_1402FF13D
0x1402fedd8  mov     bpl, [rsp+348h+arg_30]
0x1402fede0  mov     eax, 80004005h
0x1402fede5  mov     [rsp+348h+var_1D8], rax
0x1402feded  mov     [rsp+348h+var_1E0], 0
0x1402fedf9  test    dil, dil
0x1402fedfc  jnz     loc_1402FF19E
0x1402fee02  lea     r8, [rsp+348h+var_1B8]
0x1402fee0a  mov     qword ptr [r8], 0
0x1402fee11  mov     rcx, [rsp+348h+var_1D0]
0x1402fee19  mov     rax, [rcx]
0x1402fee1c  mov     rax, [rax]
0x1402fee1f  lea     rdx, qword_140358DE8
0x1402fee26  call    cs:__guard_dispatch_icall_fptr
0x1402fee2c  test    eax, eax
0x1402fee2e  js      loc_1402FF050
0x1402fee34  test    bpl, bpl
0x1402fee37  jnz     loc_1402FF263
0x1402fee3d  movzx   edi, [rsp+348h+arg_28]
0x1402fee45  mov     rbx, [rsp+348h+var_1B8]
0x1402fee4d  mov     rcx, [rsp+348h+var_1E0]
0x1402fee55  test    rcx, rcx
0x1402fee58  jz      short loc_1402FEE73
0x1402fee5a  mov     [rsp+348h+var_1E0], 0
0x1402fee66  mov     rax, [rcx]
0x1402fee69  mov     rax, [rax+10h]
0x1402fee6d  call    cs:__guard_dispatch_icall_fptr
0x1402fee73  movups  xmm0, xmmword ptr [r15]
0x1402fee77  lea     rdx, [rsp+348h+var_1F8]
0x1402fee7f  movaps  xmmword ptr [rdx], xmm0
0x1402fee82  lea     r14, [rsp+348h+var_198]
0x1402fee8a  mov     rcx, r14
0x1402fee8d  call    sub_1400C2540
0x1402fee92  mov     rdx, [r14+8]
0x1402fee96  mov     rax, [rbx]
0x1402fee99  mov     rax, [rax+40h]
0x1402fee9d  lea     rcx, [rsp+348h+var_1E0]
0x1402feea5  mov     [rsp+348h+var_318], rcx
0x1402feeaa  xorps   xmm0, xmm0
0x1402feead  movups  [rsp+348h+var_328], xmm0
0x1402feeb2  mov     rcx, rbx
0x1402feeb5  xor     r8d, r8d
0x1402feeb8  mov     r9d, edi
0x1402feebb  call    cs:__guard_dispatch_icall_fptr
0x1402feec1  lea     rax, off_140313288
0x1402feec8  mov     [r14], rax
0x1402feecb  cmp     byte ptr [r14+10h], 1
0x1402feed0  jz      loc_1402FFE14
0x1402feed6  mov     rcx, [rsp+348h+string]; string
0x1402feede  test    rcx, rcx
0x1402feee1  jz      short loc_1402FEEE8
0x1402feee3  call    j_WindowsDeleteString
0x1402feee8  mov     dil, 1
0x1402feeeb  mov     rcx, [rsp+348h+var_1B8]
0x1402feef3  test    rcx, rcx
0x1402feef6  jz      short loc_1402FEF11
0x1402feef8  mov     [rsp+348h+var_1B8], 0
0x1402fef04  mov     rax, [rcx]
0x1402fef07  mov     rax, [rax+10h]
0x1402fef0b  call    cs:__guard_dispatch_icall_fptr
0x1402fef11  test    dil, dil
0x1402fef14  jz      loc_1402FF0F4
0x1402fef1a  xorps   xmm0, xmm0
0x1402fef1d  lea     rbx, [rsp+348h+var_1B8]
0x1402fef25  movaps  xmmword ptr [rbx], xmm0
0x1402fef28  mov     rcx, rbx
0x1402fef2b  mov     edx, 1
0x1402fef30  mov     r8d, 1
0x1402fef36  call    sub_14005E7D0
0x1402fef3b  lea     rdx, byte_14032F109
0x1402fef42  mov     ecx, 20h ; ' '
0x1402fef47  call    sub_14008D690
0x1402fef4c  mov     rdi, rax
0x1402fef4f  test    rax, rax
0x1402fef52  jz      short loc_1402FEF90
0x1402fef54  mov     dword ptr [rdi+0Ch], 1
0x1402fef5b  lea     rax, off_140312B00
0x1402fef62  mov     [rdi], rax
0x1402fef65  mov     rcx, cs:qword_14038CA78
0x1402fef6c  test    rcx, rcx
0x1402fef6f  jz      short loc_1402FEF7E
0x1402fef71  mov     rax, [rcx]
0x1402fef74  mov     rax, [rax+8]
0x1402fef78  call    cs:__guard_dispatch_icall_fptr
0x1402fef7e  mov     [rdi+10h], rsi
0x1402fef82  mov     [rdi+18h], rbx
0x1402fef86  lea     rax, off_140313260
0x1402fef8d  mov     [rdi], rax
0x1402fef90  mov     rcx, [rsp+348h+var_1E0]
0x1402fef98  mov     rax, [rcx]
0x1402fef9b  mov     rax, [rax+40h]
0x1402fef9f  mov     rdx, rdi
0x1402fefa2  call    cs:__guard_dispatch_icall_fptr
0x1402fefa8  mov     ebx, eax
0x1402fefaa  test    eax, eax
0x1402fefac  js      loc_1402FF059
0x1402fefb2  lea     rdx, aRegisterpackag; "RegisterPackage"
0x1402fefb9  lea     r8, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402fefc0  lea     rsi, [rsp+348h+var_198]
0x1402fefc8  mov     rcx, rsi
0x1402fefcb  mov     r9d, 2EAh
0x1402fefd1  call    sub_140087DE0
0x1402fefd6  lea     rcx, [rsp+348h+var_1B8]
0x1402fefde  mov     edx, 11E1A300h
0x1402fefe3  mov     r8, rsi
0x1402fefe6  call    sub_14007D520
0x1402fefeb  test    al, al
0x1402fefed  jnz     loc_1402FF0D2
0x1402feff3  lea     rcx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402feffa  mov     edx, 33h ; '3'
0x1402fefff  call    sub_140087310
0x1402ff004  mov     ebx, 80070102h
0x1402ff009  test    eax, eax
0x1402ff00b  jle     loc_1402FF0D2
0x1402ff011  lea     rdx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff018  lea     rsi, [rsp+348h+var_198]
0x1402ff020  mov     rcx, rsi
0x1402ff023  mov     r8d, 2EBh
0x1402ff029  mov     r9d, 0FFFFFFFFh
0x1402ff02f  call    sub_1400EC5E0
0x1402ff034  lea     rcx, [rsp+348h+var_188]
0x1402ff03c  lea     rdx, aTimedOutWaitin; "Timed out waiting for MSIX package to b"...
0x1402ff043  mov     r8d, 34h ; '4'
0x1402ff049  call    sub_140042C98
0x1402ff04e  jmp     short loc_1402FF0CA
0x1402ff050  mov     ebx, eax
0x1402ff052  xor     edi, edi
0x1402ff054  jmp     loc_1402FEEEB
0x1402ff059  lea     rcx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff060  mov     edx, 33h ; '3'
0x1402ff065  call    sub_140087310
0x1402ff06a  test    eax, eax
0x1402ff06c  jle     short loc_1402FF0D2
0x1402ff06e  lea     rdx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff075  lea     rsi, [rsp+348h+var_198]
0x1402ff07d  mov     rcx, rsi
0x1402ff080  mov     r8d, 2E6h
0x1402ff086  mov     r9d, 0FFFFFFFFh
0x1402ff08c  call    sub_1400EC5E0
0x1402ff091  lea     rcx, [rsp+348h+var_188]
0x1402ff099  lea     rdx, aFailedToRegist_1; "Failed to register MSIX package with hr"...
0x1402ff0a0  mov     r8d, 28h ; '('
0x1402ff0a6  call    sub_140042C98
0x1402ff0ab  mov     rcx, [rax]
0x1402ff0ae  movsxd  rcx, dword ptr [rcx+4]
0x1402ff0b2  mov     edx, [rax+rcx+8]
0x1402ff0b6  and     edx, 0FFFFFFB5h
0x1402ff0b9  or      edx, 8
0x1402ff0bc  mov     [rax+rcx+8], edx
0x1402ff0c0  mov     rcx, rax
0x1402ff0c3  mov     edx, ebx
0x1402ff0c5  call    sub_14009FA52
0x1402ff0ca  mov     rcx, rsi
0x1402ff0cd  call    sub_1400EC980
0x1402ff0d2  test    rdi, rdi
0x1402ff0d5  jz      short loc_1402FF0E7
0x1402ff0d7  mov     rax, [rdi]
0x1402ff0da  mov     rax, [rax+10h]
0x1402ff0de  mov     rcx, rdi
0x1402ff0e1  call    cs:__guard_dispatch_icall_fptr
0x1402ff0e7  lea     rcx, [rsp+348h+var_1B8]
0x1402ff0ef  call    sub_14007D1E0
0x1402ff0f4  mov     rcx, [rsp+348h+var_1E0]
0x1402ff0fc  test    rcx, rcx
0x1402ff0ff  jz      short loc_1402FF11A
0x1402ff101  mov     [rsp+348h+var_1E0], 0
0x1402ff10d  mov     rax, [rcx]
0x1402ff110  mov     rax, [rax+10h]
0x1402ff114  call    cs:__guard_dispatch_icall_fptr
0x1402ff11a  cmp     dword ptr [rsp+348h+var_1D8], 0
0x1402ff122  jnz     short loc_1402FF13F
0x1402ff124  cmp     byte ptr [rsp+348h+var_1D8+4], 0
0x1402ff12c  jnz     short loc_1402FF13F
0x1402ff12e  call    cs:RevertToSelf
0x1402ff134  test    eax, eax
0x1402ff136  jnz     short loc_1402FF13F
0x1402ff138  jmp     loc_1402FFE17
0x1402ff13d  mov     ebx, eax
0x1402ff13f  mov     rcx, [rsp+348h+var_1D0]
0x1402ff147  test    rcx, rcx
0x1402ff14a  jz      short loc_1402FF165
0x1402ff14c  mov     [rsp+348h+var_1D0], 0
0x1402ff158  mov     rax, [rcx]
0x1402ff15b  mov     rax, [rax+10h]
0x1402ff15f  call    cs:__guard_dispatch_icall_fptr
0x1402ff165  mov     rax, [rsp+348h+var_60]
0x1402ff16d  xor     rax, rsp
0x1402ff170  mov     rcx, cs:__security_cookie
0x1402ff177  cmp     rcx, rax
0x1402ff17a  jnz     loc_1402FFE04
0x1402ff180  mov     eax, ebx
0x1402ff182  movaps  xmm6, [rsp+348h+var_58]
0x1402ff18a  add     rsp, 308h
0x1402ff191  pop     rbx
0x1402ff192  pop     rbp
0x1402ff193  pop     rdi
0x1402ff194  pop     rsi
0x1402ff195  pop     r12
0x1402ff197  pop     r13
0x1402ff199  pop     r14
0x1402ff19b  pop     r15
0x1402ff19d  retn
0x1402ff19e  xorps   xmm6, xmm6
0x1402ff1a1  lea     rdi, [rsp+348h+var_218]
0x1402ff1a9  movaps  xmmword ptr [rdi], xmm6
0x1402ff1ac  mov     qword ptr [rdi+10h], 0
0x1402ff1b4  movups  xmm0, xmmword ptr [r15]
0x1402ff1b8  lea     rcx, [rsp+348h+var_228]
0x1402ff1c0  movaps  xmmword ptr [rcx], xmm0
0x1402ff1c3  mov     rdx, rdi
0x1402ff1c6  call    sub_1402FE0A3
0x1402ff1cb  test    eax, eax
0x1402ff1cd  jns     loc_1402FF2E9
0x1402ff1d3  mov     ebx, eax
0x1402ff1d5  lea     rcx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff1dc  mov     edx, 33h ; '3'
0x1402ff1e1  call    sub_140087310
0x1402ff1e6  test    eax, eax
0x1402ff1e8  jle     short loc_1402FF24E
0x1402ff1ea  lea     rdx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff1f1  lea     rsi, [rsp+348h+var_198]
0x1402ff1f9  mov     rcx, rsi
0x1402ff1fc  mov     r8d, 281h
0x1402ff202  mov     r9d, 0FFFFFFFFh
0x1402ff208  call    sub_1400EC5E0
0x1402ff20d  lea     rcx, [rsp+348h+var_188]
0x1402ff215  lea     rdx, aFailedToGetPro_0; "Failed to get provisioned versions with"...
0x1402ff21c  mov     r8d, 2Ch ; ','
0x1402ff222  call    sub_140042C98
0x1402ff227  mov     rcx, [rax]
0x1402ff22a  movsxd  rcx, dword ptr [rcx+4]
0x1402ff22e  mov     edx, [rax+rcx+8]
0x1402ff232  and     edx, 0FFFFFFB5h
0x1402ff235  or      edx, 8
0x1402ff238  mov     [rax+rcx+8], edx
0x1402ff23c  mov     rcx, rax
0x1402ff23f  mov     edx, ebx
0x1402ff241  call    sub_14009FA52
0x1402ff246  mov     rcx, rsi
0x1402ff249  call    sub_1400EC980
0x1402ff24e  lea     rcx, [rsp+348h+var_198]
0x1402ff256  mov     [rcx], rdi
0x1402ff259  call    sub_14030269A
0x1402ff25e  jmp     loc_1402FF0F4
0x1402ff263  lea     rcx, [rsp+348h+var_1D8]
0x1402ff26b  call    sub_1402FEB8A
0x1402ff270  cmp     eax, 13Bh
0x1402ff275  jz      short loc_1402FF286
0x1402ff277  mov     ebx, eax
0x1402ff279  test    eax, eax
0x1402ff27b  jns     loc_1402FEE3D
0x1402ff281  jmp     loc_1402FF052
0x1402ff286  lea     rcx, aChromeInstalle_0; "..\\..\\chrome\\installer\\util\\edge_m"...
0x1402ff28d  mov     edx, 33h ; '3'
0x1402ff292  call    sub_140087310
0x1402ff297  test    eax, eax
  ... truncated ...
```
