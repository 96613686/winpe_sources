# PiiSafeFolderList::Initialize(void)

- ea: `0x180047360`
- end: `0x180047a22`
- name: `?Initialize@PiiSafeFolderList@@QEAAXXZ`
- size: `1730`
- prototype: `void __fastcall(PiiSafeFolderList *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ad64`

## callees

- `0x18001d18c`
- `0x1800254e0`
- `0x180026394`
- `0x18003a4cc`
- `0x180047360`
- `0x18005137c`
- `0x180052cc4`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180047787`
- `SHELL32!SHParseDisplayName` at `0x180047787`
- `SHELL32!SHGetKnownFolderPath` at `0x18004759c`
- `SHELL32!SHGetKnownFolderPath` at `0x1800479cf`
- `SHELL32!SHGetKnownFolderPath` at `0x18004759c`
- `SHELL32!SHGetKnownFolderPath` at `0x1800479cf`

## pseudocode

```c
void __fastcall PiiSafeFolderList::Initialize(PiiSafeFolderList *this)
{
  unsigned int v2; // r14d
  __int64 v3; // rsi
  PWSTR *v4; // rax
  unsigned int v5; // r14d
  const WCHAR *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // rsi
  PWSTR *v11; // rax
  _QWORD v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszName; // [rsp+40h] [rbp-C0h]
  char v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+49h] [rbp-B7h]
  __int16 v16; // [rsp+4Dh] [rbp-B3h]
  char v17; // [rsp+4Fh] [rbp-B1h]
  const wchar_t *v18; // [rsp+50h] [rbp-B0h]
  char v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+59h] [rbp-A7h]
  __int16 v21; // [rsp+5Dh] [rbp-A3h]
  char v22; // [rsp+5Fh] [rbp-A1h]
  const wchar_t *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+69h] [rbp-97h]
  __int16 v26; // [rsp+6Dh] [rbp-93h]
  char v27; // [rsp+6Fh] [rbp-91h]
  const WCHAR *v28; // [rsp+70h] [rbp-90h]
  char v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+79h] [rbp-87h]
  __int16 v31; // [rsp+7Dh] [rbp-83h]
  char v32; // [rsp+7Fh] [rbp-81h]
  const wchar_t *v33; // [rsp+80h] [rbp-80h]
  char v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+89h] [rbp-77h]
  __int16 v36; // [rsp+8Dh] [rbp-73h]
  char v37; // [rsp+8Fh] [rbp-71h]
  const wchar_t *v38; // [rsp+90h] [rbp-70h]
  char v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+99h] [rbp-67h]
  __int16 v41; // [rsp+9Dh] [rbp-63h]
  char v42; // [rsp+9Fh] [rbp-61h]
  const wchar_t *v43; // [rsp+A0h] [rbp-60h]
  char v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+A9h] [rbp-57h]
  __int16 v46; // [rsp+ADh] [rbp-53h]
  char v47; // [rsp+AFh] [rbp-51h]
  const wchar_t *v48; // [rsp+B0h] [rbp-50h]
  char v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+B9h] [rbp-47h]
  __int16 v51; // [rsp+BDh] [rbp-43h]
  char v52; // [rsp+BFh] [rbp-41h]
  const wchar_t *v53; // [rsp+C0h] [rbp-40h]
  char v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+C9h] [rbp-37h]
  __int16 v56; // [rsp+CDh] [rbp-33h]
  char v57; // [rsp+CFh] [rbp-31h]
  const wchar_t *v58; // [rsp+D0h] [rbp-30h]
  char v59; // [rsp+D8h] [rbp-28h]
  int v60; // [rsp+D9h] [rbp-27h]
  __int16 v61; // [rsp+DDh] [rbp-23h]
  char v62; // [rsp+DFh] [rbp-21h]
  const wchar_t *v63; // [rsp+E0h] [rbp-20h]
  char v64; // [rsp+E8h] [rbp-18h]
  int v65; // [rsp+E9h] [rbp-17h]
  __int16 v66; // [rsp+EDh] [rbp-13h]
  char v67; // [rsp+EFh] [rbp-11h]
  const wchar_t *v68; // [rsp+F0h] [rbp-10h]
  char v69; // [rsp+F8h] [rbp-8h]
  int v70; // [rsp+F9h] [rbp-7h]
  __int16 v71; // [rsp+FDh] [rbp-3h]
  char v72; // [rsp+FFh] [rbp-1h]
  const wchar_t *v73; // [rsp+100h] [rbp+0h]
  char v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+109h] [rbp+9h]
  __int16 v76; // [rsp+10Dh] [rbp+Dh]
  char v77; // [rsp+10Fh] [rbp+Fh]
  _QWORD *v78; // [rsp+110h] [rbp+10h] BYREF
  LPITEMIDLIST ppidl; // [rsp+118h] [rbp+18h] BYREF
  char v80; // [rsp+120h] [rbp+20h]
  GUID v81; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v82[4]; // [rsp+140h] [rbp+40h]
  GUID v83; // [rsp+144h] [rbp+44h]
  char v84; // [rsp+154h] [rbp+54h]
  GUID v85; // [rsp+158h] [rbp+58h]
  char v86; // [rsp+168h] [rbp+68h]
  GUID v87; // [rsp+16Ch] [rbp+6Ch]
  char v88; // [rsp+17Ch] [rbp+7Ch]
  GUID v89; // [rsp+180h] [rbp+80h]
  char v90; // [rsp+190h] [rbp+90h]
  GUID v91; // [rsp+194h] [rbp+94h]
  char v92; // [rsp+1A4h] [rbp+A4h]
  GUID v93; // [rsp+1A8h] [rbp+A8h]
  char v94; // [rsp+1B8h] [rbp+B8h]
  GUID v95; // [rsp+1BCh] [rbp+BCh]
  char v96; // [rsp+1CCh] [rbp+CCh]
  GUID v97; // [rsp+1D0h] [rbp+D0h]
  char v98; // [rsp+1E0h] [rbp+E0h]
  GUID v99; // [rsp+1E4h] [rbp+E4h]
  char v100; // [rsp+1F4h] [rbp+F4h]
  GUID v101; // [rsp+1F8h] [rbp+F8h]
  char v102; // [rsp+208h] [rbp+108h]
  GUID v103; // [rsp+20Ch] [rbp+10Ch]
  char v104; // [rsp+21Ch] [rbp+11Ch]
  GUID v105; // [rsp+220h] [rbp+120h]
  char v106; // [rsp+230h] [rbp+130h]
  GUID v107; // [rsp+234h] [rbp+134h]
  char v108; // [rsp+244h] [rbp+144h]
  GUID v109; // [rsp+248h] [rbp+148h]
  char v110; // [rsp+258h] [rbp+158h]
  GUID v111; // [rsp+25Ch] [rbp+15Ch]
  char v112; // [rsp+26Ch] [rbp+16Ch]
  GUID v113; // [rsp+270h] [rbp+170h]
  char v114; // [rsp+280h] [rbp+180h]
  GUID v115; // [rsp+284h] [rbp+184h]
  char v116; // [rsp+294h] [rbp+194h]
  GUID v117; // [rsp+298h] [rbp+198h]
  char v118; // [rsp+2A8h] [rbp+1A8h]
  GUID v119; // [rsp+2ACh] [rbp+1ACh]
  char v120; // [rsp+2BCh] [rbp+1BCh]
  GUID v121; // [rsp+2C0h] [rbp+1C0h]
  char v122; // [rsp+2D0h] [rbp+1D0h]
  GUID v123; // [rsp+2D4h] [rbp+1D4h]
  char v124; // [rsp+2E4h] [rbp+1E4h]
  GUID v125; // [rsp+2E8h] [rbp+1E8h]
  char v126; // [rsp+2F8h] [rbp+1F8h]
  GUID v127; // [rsp+2FCh] [rbp+1FCh]
  char v128; // [rsp+30Ch] [rbp+20Ch]

  v82[0] = 51;
  v84 = 52;
  v86 = 53;
  v88 = 54;
  v90 = 50;
  v92 = 11;
  v81 = FOLDERID_SkyDriveDocuments;
  v83 = FOLDERID_SkyDriveCameraRoll;
  v85 = FOLDERID_SkyDrivePictures;
  v87 = FOLDERID_SkyDriveMusic;
  v89 = FOLDERID_OneDrive;
  v91 = FOLDERID_Profile;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
  {
    v94 = 113;
    v2 = 0;
    v96 = 114;
    v93 = FOLDERID_Fonts;
    v98 = 115;
    v100 = 116;
    v102 = 117;
    v95 = FOLDERID_ProgramFilesX86;
    v104 = 118;
    v106 = 22;
    v108 = 23;
    v97 = FOLDERID_ProgramFilesX64;
    v110 = 24;
    v112 = 25;
    v114 = 26;
    v99 = FOLDERID_ProgramFiles;
    v116 = 27;
    v118 = 28;
    v120 = 29;
    v101 = FOLDERID_Windows;
    v122 = 30;
    v103 = FOLDERID_HomeGroup;
    *((_DWORD *)this + 360) = 21;
    v105 = FOLDERID_Desktop;
    v107 = FOLDERID_Documents;
    v109 = FOLDERID_Downloads;
    v111 = FOLDERID_CameraRoll;
    v113 = FOLDERID_Pictures;
    v115 = FOLDERID_Music;
    v117 = FOLDERID_Videos;
    v119 = FOLDERID_Objects3D;
    v121 = FOLDERID_Screenshots;
    do
    {
      v3 = (int)v2;
      v4 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put((char *)this + 8 * (int)v2 + 1040);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v81 + 20 * (int)v2), 0x4100u, 0, v4) >= 0 )
        *((_QWORD *)this + 2 * (int)v2) = *((_QWORD *)this + (int)v2 + 130);
      ++v2;
      *((_BYTE *)this + 16 * v3 + 8) = v82[20 * v3];
    }
    while ( v2 < 0x15 );
    v14 = 120;
    pszName = L"shell:::{f874310e-b6b7-47dc-bc84-b9e6b38f5903}";
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = L"shell:::{20D04FE0-3AEA-1069-A2D8-08002B30309D}";
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = L"shell:::{645FF040-5081-101B-9F08-00AA002F954E}";
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = L"shell:::{e88865ea-0e1c-4e20-9aa6-edcd0212c87c}";
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = L"shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC332AEAE}";
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = L"shell:::{031e4825-7b94-4dc3-b131-e946b44c8dd5}";
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = L"shell:::{26EE0668-A00A-44D7-9371-BEB064C98683}";
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\CameraRoll.library-ms";
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Documents.library-ms";
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Music.library-ms";
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Pictures.library-ms";
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\SavedPictures.library-ms";
    v19 = 110;
    v24 = 112;
    v29 = 121;
    v34 = 123;
    v39 = 122;
    v44 = 111;
    v49 = 124;
    v54 = 125;
    v59 = 126;
    v64 = 127;
    v69 = 0x80;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = L"shell:::{031E4825-7B94-4DC3-B131-E946B44C8DD5}\\Videos.library-ms";
    v75 = 0;
    v5 = 0;
    v76 = 0;
    v77 = 0;
    v74 = -127;
    do
    {
      v12[0] = 0;
      ppidl = 0;
      v80 = 1;
      *((_BYTE *)this + 16 * (int)v5 + 800) = *(&v14 + 16 * (int)v5);
      v6 = (&pszName)[2 * (int)v5];
      v78 = v12;
      v7 = (unsigned int)SHParseDisplayName(v6, 0, &ppidl, 0, 0) >> 31;
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v78);
      if ( (_BYTE)v7 )
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v12,
          0);
      v8 = v12[0];
      v12[0] = 0;
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        (char *)this + 16 * (int)v5 + 808,
        v8);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        v12,
        0);
      ++v5;
    }
    while ( v5 < 0xD );
  }
  else
  {
    v94 = 110;
    v96 = 111;
    v93 = FOLDERID_ComputerFolder;
    v98 = 112;
    v100 = 113;
    v102 = 114;
    v95 = FOLDERID_ControlPanelFolder;
    v104 = 115;
    v106 = 116;
    v108 = 117;
    v97 = FOLDERID_RecycleBinFolder;
    v110 = 118;
    v112 = 22;
    v114 = 23;
    v99 = FOLDERID_Fonts;
    v116 = 24;
    v118 = 25;
    v120 = 26;
    v101 = FOLDERID_ProgramFilesX86;
    v122 = 27;
    v124 = 28;
    v126 = 29;
    v103 = FOLDERID_ProgramFilesX64;
    v128 = 30;
    v105 = FOLDERID_ProgramFiles;
    v107 = FOLDERID_Windows;
    v109 = FOLDERID_HomeGroup;
    v111 = FOLDERID_Desktop;
    v113 = FOLDERID_Documents;
    v115 = FOLDERID_Downloads;
    v117 = FOLDERID_CameraRoll;
    v119 = FOLDERID_Pictures;
    v121 = FOLDERID_Music;
    v123 = FOLDERID_Videos;
    v125 = FOLDERID_Objects3D;
    v127 = FOLDERID_Screenshots;
    memset_0(this, 0, 0x320u);
    memset_0((char *)this + 1040, 0, 0x190u);
    v9 = 0;
    *((_DWORD *)this + 360) = 24;
    do
    {
      v10 = (int)v9;
      v11 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put((char *)this + 8 * (int)v9 + 1040);
      if ( SHGetKnownFolderPath((GUID *)((char *)&v81 + 20 * (int)v9), 0x4100u, 0, v11) >= 0 )
        *((_QWORD *)this + 2 * (int)v9) = *((_QWORD *)this + (int)v9 + 130);
      ++v9;
      *((_BYTE *)this + 16 * v10 + 8) = v82[20 * v10];
    }
    while ( v9 < 0x18 );
  }
}

```

## disassembly

```asm
0x180047360  mov     [rsp-8+arg_8], rbx
0x180047365  mov     [rsp-8+arg_10], rsi
0x18004736a  push    rbp
0x18004736b  push    rdi
0x18004736c  push    r12
0x18004736e  push    r14
0x180047370  push    r15
0x180047372  lea     rbp, [rsp-220h]
0x18004737a  sub     rsp, 320h
0x180047381  mov     rax, cs:__security_cookie
0x180047388  xor     rax, rsp
0x18004738b  mov     [rbp+240h+var_30], rax
0x180047392  mov     rdi, rcx
0x180047395  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56275225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225> `wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl(void)'::`2'::impl
0x18004739c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56275225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(void)
0x1800473a1  mov     [rbp+240h+var_200], 33h ; '3'
0x1800473a5  mov     [rbp+240h+var_1EC], 34h ; '4'
0x1800473a9  mov     [rbp+240h+var_1D8], 35h ; '5'
0x1800473ad  mov     [rbp+240h+var_1C4], 36h ; '6'
0x1800473b1  mov     [rbp+240h+var_1B0], 32h ; '2'
0x1800473b8  mov     [rbp+240h+var_19C], 0Bh
0x1800473bf  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveDocuments.Data1
0x1800473c6  movdqu  [rbp+240h+var_210], xmm0
0x1800473cb  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveCameraRoll.Data1
0x1800473d2  movdqu  [rbp+240h+var_1FC], xmm0
0x1800473d7  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDrivePictures.Data1
0x1800473de  movdqu  [rbp+240h+var_1E8], xmm0
0x1800473e3  movups  xmm0, xmmword ptr cs:FOLDERID_SkyDriveMusic.Data1
0x1800473ea  movdqu  [rbp+240h+var_1D4], xmm0
0x1800473ef  movups  xmm0, xmmword ptr cs:FOLDERID_OneDrive.Data1
0x1800473f6  movdqu  [rbp+240h+var_1C0], xmm0
0x1800473fe  movups  xmm0, xmmword ptr cs:FOLDERID_Profile.Data1
0x180047405  movdqu  [rbp+240h+var_1AC], xmm0
0x18004740d  test    al, al
0x18004740f  jz      loc_1800477E6
0x180047415  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x18004741c  mov     [rbp+240h+var_188], 71h ; 'q'
0x180047423  xor     r14d, r14d
0x180047426  mov     [rbp+240h+var_174], 72h ; 'r'
0x18004742d  movdqu  [rbp+240h+var_198], xmm0
0x180047435  mov     [rbp+240h+var_160], 73h ; 's'
0x18004743c  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180047443  mov     [rbp+240h+var_14C], 74h ; 't'
0x18004744a  mov     [rbp+240h+var_138], 75h ; 'u'
0x180047451  movdqu  [rbp+240h+var_184], xmm0
0x180047459  mov     [rbp+240h+var_124], 76h ; 'v'
0x180047460  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x180047467  mov     [rbp+240h+var_110], 16h
0x18004746e  mov     [rbp+240h+var_FC], 17h
0x180047475  movdqu  [rbp+240h+var_170], xmm0
0x18004747d  mov     [rbp+240h+var_E8], 18h
0x180047484  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x18004748b  mov     [rbp+240h+var_D4], 19h
0x180047492  mov     [rbp+240h+var_C0], 1Ah
0x180047499  movdqu  [rbp+240h+var_15C], xmm0
0x1800474a1  mov     [rbp+240h+var_AC], 1Bh
0x1800474a8  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x1800474af  mov     [rbp+240h+var_98], 1Ch
0x1800474b6  mov     [rbp+240h+var_84], 1Dh
0x1800474bd  movdqu  [rbp+240h+var_148], xmm0
0x1800474c5  mov     [rbp+240h+var_70], 1Eh
0x1800474cc  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x1800474d3  movdqu  [rbp+240h+var_134], xmm0
0x1800474db  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x1800474e2  mov     dword ptr [rdi+5A0h], 15h
0x1800474ec  movdqu  [rbp+240h+var_120], xmm0
0x1800474f4  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x1800474fb  movdqu  [rbp+240h+var_10C], xmm0
0x180047503  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x18004750a  movdqu  [rbp+240h+var_F8], xmm0
0x180047512  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x180047519  movdqu  [rbp+240h+var_E4], xmm0
0x180047521  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x180047528  movdqu  [rbp+240h+var_D0], xmm0
0x180047530  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x180047537  movdqu  [rbp+240h+var_BC], xmm0
0x18004753f  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x180047546  movdqu  [rbp+240h+var_A8], xmm0
0x18004754e  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
0x180047555  movdqu  [rbp+240h+var_94], xmm0
0x18004755d  movups  xmm0, xmmword ptr cs:FOLDERID_Screenshots.Data1
0x180047564  movdqu  [rbp+240h+var_80], xmm0
0x18004756c  movsxd  rsi, r14d
0x18004756f  lea     rcx, [rdi+410h]
0x180047576  lea     rcx, [rcx+rsi*8]
0x18004757a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18004757f  lea     rcx, [rbp+240h+var_210]
0x180047583  mov     rbx, rsi
0x180047586  lea     r15, [rsi+rsi*4]
0x18004758a  mov     r9, rax; ppszPath
0x18004758d  lea     rcx, [rcx+r15*4]; rfid
0x180047591  xor     r8d, r8d; hToken
0x180047594  mov     edx, 4100h; dwFlags
0x180047599  add     rbx, rbx
0x18004759c  call    cs:__imp_SHGetKnownFolderPath
0x1800475a2  test    eax, eax
0x1800475a4  js      short loc_1800475B2
0x1800475a6  mov     rax, [rdi+rsi*8+410h]
0x1800475ae  mov     [rdi+rbx*8], rax
0x1800475b2  mov     al, [rbp+r15*4+240h+var_200]
0x1800475b7  inc     r14d
0x1800475ba  mov     [rdi+rbx*8+8], al
0x1800475be  cmp     r14d, 15h
0x1800475c2  jb      short loc_18004756C
0x1800475c4  lea     rax, aShellF874310eB; "shell:::{f874310e-b6b7-47dc-bc84-b9e6b3"...
0x1800475cb  mov     [rsp+340h+var_2F8], 78h ; 'x'
0x1800475d0  mov     [rsp+340h+pszName], rax
0x1800475d5  xor     eax, eax
0x1800475d7  mov     [rsp+340h+var_2F7], eax
0x1800475db  mov     [rsp+340h+var_2F3], ax
0x1800475e0  mov     [rsp+340h+var_2F1], al
0x1800475e4  lea     rax, aShell20d04fe03; "shell:::{20D04FE0-3AEA-1069-A2D8-08002B"...
0x1800475eb  mov     [rsp+340h+var_2F0], rax
0x1800475f0  xor     eax, eax
0x1800475f2  mov     [rsp+340h+var_2E7], eax
0x1800475f6  mov     [rsp+340h+var_2E3], ax
0x1800475fb  mov     [rsp+340h+var_2E1], al
0x1800475ff  lea     rax, aShell645ff0405; "shell:::{645FF040-5081-101B-9F08-00AA00"...
0x180047606  mov     [rsp+340h+var_2E0], rax
0x18004760b  xor     eax, eax
0x18004760d  mov     [rsp+340h+var_2D7], eax
0x180047611  mov     [rsp+340h+var_2D3], ax
0x180047616  mov     [rsp+340h+var_2D1], al
0x18004761a  lea     rax, pszName; "shell:::{e88865ea-0e1c-4e20-9aa6-edcd02"...
0x180047621  mov     [rsp+340h+var_2D0], rax
0x180047626  xor     eax, eax
0x180047628  mov     [rsp+340h+var_2C7], eax
0x18004762c  mov     [rsp+340h+var_2C3], ax
0x180047631  mov     [rsp+340h+var_2C1], al
0x180047635  lea     rax, aShell1b3ea5dcB; "shell:::{1B3EA5DC-B587-4786-B4EF-BD1DC3"...
0x18004763c  mov     [rbp+240h+var_2C0], rax
0x180047640  xor     eax, eax
0x180047642  mov     [rbp+240h+var_2B7], eax
0x180047645  mov     [rbp+240h+var_2B3], ax
0x180047649  mov     [rbp+240h+var_2B1], al
0x18004764c  lea     rax, aShell031e48257_2; "shell:::{031e4825-7b94-4dc3-b131-e946b4"...
0x180047653  mov     [rbp+240h+var_2B0], rax
0x180047657  xor     eax, eax
0x180047659  mov     [rbp+240h+var_2A7], eax
0x18004765c  mov     [rbp+240h+var_2A3], ax
0x180047660  mov     [rbp+240h+var_2A1], al
0x180047663  lea     rax, aShell26ee0668A; "shell:::{26EE0668-A00A-44D7-9371-BEB064"...
0x18004766a  mov     [rbp+240h+var_2A0], rax
0x18004766e  xor     eax, eax
0x180047670  mov     [rbp+240h+var_297], eax
0x180047673  mov     [rbp+240h+var_293], ax
0x180047677  mov     [rbp+240h+var_291], al
0x18004767a  lea     rax, aShell031e48257_4; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180047681  mov     [rbp+240h+var_290], rax
0x180047685  xor     eax, eax
0x180047687  mov     [rbp+240h+var_287], eax
0x18004768a  mov     [rbp+240h+var_283], ax
0x18004768e  mov     [rbp+240h+var_281], al
0x180047691  lea     rax, aShell031e48257_3; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180047698  mov     [rbp+240h+var_280], rax
0x18004769c  xor     eax, eax
0x18004769e  mov     [rbp+240h+var_277], eax
0x1800476a1  mov     [rbp+240h+var_273], ax
0x1800476a5  mov     [rbp+240h+var_271], al
0x1800476a8  lea     rax, aShell031e48257_5; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x1800476af  mov     [rbp+240h+var_270], rax
0x1800476b3  xor     eax, eax
0x1800476b5  mov     [rbp+240h+var_267], eax
0x1800476b8  mov     [rbp+240h+var_263], ax
0x1800476bc  mov     [rbp+240h+var_261], al
0x1800476bf  lea     rax, aShell031e48257; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x1800476c6  mov     [rbp+240h+var_260], rax
0x1800476ca  xor     eax, eax
0x1800476cc  mov     [rbp+240h+var_257], eax
0x1800476cf  mov     [rbp+240h+var_253], ax
0x1800476d3  mov     [rbp+240h+var_251], al
0x1800476d6  lea     rax, aShell031e48257_1; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x1800476dd  mov     [rbp+240h+var_250], rax
0x1800476e1  xor     eax, eax
0x1800476e3  mov     [rsp+340h+var_2E8], 6Eh ; 'n'
0x1800476e8  mov     [rsp+340h+var_2D8], 70h ; 'p'
0x1800476ed  mov     [rsp+340h+var_2C8], 79h ; 'y'
0x1800476f2  mov     [rbp+240h+var_2B8], 7Bh ; '{'
0x1800476f6  mov     [rbp+240h+var_2A8], 7Ah ; 'z'
0x1800476fa  mov     [rbp+240h+var_298], 6Fh ; 'o'
0x1800476fe  mov     [rbp+240h+var_288], 7Ch ; '|'
0x180047702  mov     [rbp+240h+var_278], 7Dh ; '}'
0x180047706  mov     [rbp+240h+var_268], 7Eh ; '~'
0x18004770a  mov     [rbp+240h+var_258], 7Fh
0x18004770e  mov     [rbp+240h+var_248], 80h
0x180047712  mov     [rbp+240h+var_247], eax
0x180047715  mov     [rbp+240h+var_243], ax
0x180047719  mov     [rbp+240h+var_241], al
0x18004771c  lea     rax, aShell031e48257_0; "shell:::{031E4825-7B94-4DC3-B131-E946B4"...
0x180047723  mov     [rbp+240h+var_240], rax
0x180047727  xor     eax, eax
0x180047729  mov     [rbp+240h+var_237], eax
0x18004772c  xor     r14d, r14d
0x18004772f  mov     [rbp+240h+var_233], ax
0x180047733  mov     [rbp+240h+var_231], al
0x180047736  mov     [rbp+240h+var_238], 81h
0x18004773a  movsxd  rcx, r14d
0x18004773d  lea     r8, [rbp+240h+ppidl]; ppidl
0x180047741  mov     rsi, rcx
0x180047744  mov     [rsp+340h+var_310], 0
0x18004774d  add     rcx, 32h ; '2'
0x180047751  shl     rsi, 4
0x180047755  add     rcx, rcx
0x180047758  mov     [rbp+240h+ppidl], 0
0x180047760  xor     r9d, r9d; sfgaoIn
0x180047763  mov     [rbp+240h+var_220], 1
0x180047767  xor     edx, edx; pbc
0x180047769  mov     [rsp+340h+psfgaoOut], 0; psfgaoOut
0x180047772  mov     al, [rsp+rsi+340h+var_2F8]
0x180047776  mov     [rdi+rcx*8], al
0x180047779  lea     rax, [rsp+340h+var_310]
0x18004777e  mov     rcx, [rsp+rsi+340h+pszName]; pszName
0x180047783  mov     [rbp+240h+var_230], rax
0x180047787  call    cs:__imp_SHParseDisplayName
0x18004778d  mov     ebx, eax
0x18004778f  lea     rcx, [rbp+240h+var_230]
0x180047793  shr     ebx, 1Fh
0x180047796  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004779b  test    bl, bl
0x18004779d  jz      short loc_1800477AB
0x18004779f  xor     edx, edx
0x1800477a1  lea     rcx, [rsp+340h+var_310]
0x1800477a6  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800477ab  mov     rdx, [rsp+340h+var_310]
0x1800477b0  lea     rcx, [rdi+328h]
0x1800477b7  add     rcx, rsi
0x1800477ba  mov     [rsp+340h+var_310], 0
0x1800477c3  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800477c8  xor     edx, edx
0x1800477ca  lea     rcx, [rsp+340h+var_310]
0x1800477cf  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800477d4  inc     r14d
0x1800477d7  cmp     r14d, 0Dh
0x1800477db  jb      loc_18004773A
0x1800477e1  jmp     loc_1800479F7
0x1800477e6  movups  xmm0, xmmword ptr cs:FOLDERID_ComputerFolder.Data1
0x1800477ed  xor     edx, edx; Val
0x1800477ef  mov     [rbp+240h+var_188], 6Eh ; 'n'
0x1800477f6  mov     r8d, 320h; Size
0x1800477fc  mov     [rbp+240h+var_174], 6Fh ; 'o'
0x180047803  movdqu  [rbp+240h+var_198], xmm0
0x18004780b  mov     rcx, rdi; void *
0x18004780e  mov     [rbp+240h+var_160], 70h ; 'p'
0x180047815  movups  xmm0, xmmword ptr cs:FOLDERID_ControlPanelFolder.Data1
0x18004781c  mov     [rbp+240h+var_14C], 71h ; 'q'
0x180047823  mov     [rbp+240h+var_138], 72h ; 'r'
0x18004782a  movdqu  [rbp+240h+var_184], xmm0
0x180047832  mov     [rbp+240h+var_124], 73h ; 's'
0x180047839  movups  xmm0, xmmword ptr cs:FOLDERID_RecycleBinFolder.Data1
0x180047840  mov     [rbp+240h+var_110], 74h ; 't'
0x180047847  mov     [rbp+240h+var_FC], 75h ; 'u'
0x18004784e  movdqu  [rbp+240h+var_170], xmm0
0x180047856  mov     [rbp+240h+var_E8], 76h ; 'v'
0x18004785d  movups  xmm0, xmmword ptr cs:FOLDERID_Fonts.Data1
0x180047864  mov     [rbp+240h+var_D4], 16h
0x18004786b  mov     [rbp+240h+var_C0], 17h
0x180047872  movdqu  [rbp+240h+var_15C], xmm0
0x18004787a  mov     [rbp+240h+var_AC], 18h
0x180047881  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180047888  mov     [rbp+240h+var_98], 19h
0x18004788f  mov     [rbp+240h+var_84], 1Ah
0x180047896  movdqu  [rbp+240h+var_148], xmm0
0x18004789e  mov     [rbp+240h+var_70], 1Bh
0x1800478a5  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX64.Data1
0x1800478ac  mov     [rbp+240h+var_5C], 1Ch
0x1800478b3  mov     [rbp+240h+var_48], 1Dh
0x1800478ba  movdqu  [rbp+240h+var_134], xmm0
0x1800478c2  mov     [rbp+240h+var_34], 1Eh
0x1800478c9  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x1800478d0  movdqu  [rbp+240h+var_120], xmm0
0x1800478d8  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x1800478df  movdqu  [rbp+240h+var_10C], xmm0
0x1800478e7  movups  xmm0, xmmword ptr cs:FOLDERID_HomeGroup.Data1
0x1800478ee  movdqu  [rbp+240h+var_F8], xmm0
0x1800478f6  movups  xmm0, xmmword ptr cs:FOLDERID_Desktop.Data1
0x1800478fd  movdqu  [rbp+240h+var_E4], xmm0
0x180047905  movups  xmm0, xmmword ptr cs:FOLDERID_Documents.Data1
0x18004790c  movdqu  [rbp+240h+var_D0], xmm0
0x180047914  movups  xmm0, xmmword ptr cs:FOLDERID_Downloads.Data1
0x18004791b  movdqu  [rbp+240h+var_BC], xmm0
0x180047923  movups  xmm0, xmmword ptr cs:FOLDERID_CameraRoll.Data1
0x18004792a  movdqu  [rbp+240h+var_A8], xmm0
0x180047932  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x180047939  movdqu  [rbp+240h+var_94], xmm0
0x180047941  movups  xmm0, xmmword ptr cs:FOLDERID_Music.Data1
0x180047948  movdqu  [rbp+240h+var_80], xmm0
0x180047950  movups  xmm0, xmmword ptr cs:FOLDERID_Videos.Data1
0x180047957  movdqu  [rbp+240h+var_6C], xmm0
0x18004795f  movups  xmm0, xmmword ptr cs:FOLDERID_Objects3D.Data1
0x180047966  movdqu  [rbp+240h+var_58], xmm0
0x18004796e  movups  xmm0, xmmword ptr cs:FOLDERID_Screenshots.Data1
0x180047975  movdqu  [rbp+240h+var_44], xmm0
0x18004797d  call    memset_0
0x180047982  lea     r12, [rdi+410h]
0x180047989  xor     edx, edx; Val
0x18004798b  mov     rcx, r12; void *
0x18004798e  mov     r8d, 190h; Size
0x180047994  call    memset_0
0x180047999  xor     r14d, r14d
0x18004799c  mov     dword ptr [rdi+5A0h], 18h
  ... truncated ...
```
