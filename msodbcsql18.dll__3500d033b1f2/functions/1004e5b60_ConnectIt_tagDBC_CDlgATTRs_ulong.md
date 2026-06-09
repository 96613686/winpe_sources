# ConnectIt(tagDBC *,CDlgATTRs &,ulong)

- ea: `0x1004e5b60`
- end: `0x1004e6e3d`
- name: `?ConnectIt@@YAFPEAUtagDBC@@AEAVCDlgATTRs@@K@Z`
- size: `4829`
- prototype: `__int16 __fastcall(struct tagDBC *, struct CDlgATTRs *, unsigned int)`
- caller_count: `5`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x10048e700`
- `0x1004ecc80`
- `0x1004edde0`
- `0x10051ac58`
- `0x100528b1c`

## callees

- `0x1004077c0`
- `0x1004459c4`
- `0x10045ea54`
- `0x1004615c4`
- `0x10048c704`
- `0x1004964d4`
- `0x1004e4fd0`
- `0x1004e5b60`
- `0x1004e83bc`
- `0x1004e8494`
- `0x1004e87d0`
- `0x1004e93b0`
- `0x1004e9db4`
- `0x1004e9fc0`
- `0x1004ec4f0`
- `0x1004ec708`
- `0x1004ec7c4`
- `0x100520370`
- `0x1005212b4`
- `0x100546a24`
- `0x100546a7c`
- `0x100548140`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x1004e672b`
- `KERNEL32!GetUserDefaultLCID` at `0x1004e672b`
- `KERNEL32!CloseHandle` at `0x1004e5c53`
- `KERNEL32!CloseHandle` at `0x1004e692f`
- `KERNEL32!CloseHandle` at `0x1004e5c53`
- `KERNEL32!CloseHandle` at `0x1004e692f`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004e6803`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004e6803`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e48`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e75`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e99`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5ebd`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e62b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e6307`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e63d9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e63f2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e64ea`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e6789`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e48`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e75`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5e99`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e5ebd`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e62b3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e6307`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e63d9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e63f2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e64ea`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1004e6789`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004e634e`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004e6382`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004e634e`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x1004e6382`

## string_xrefs

- `0x1004e5e6e`: `ActiveDirectoryIntegrated`
- `0x1004e5e92`: `ActiveDirectoryInteractive`
- `0x1004e5eb6`: `ActiveDirectoryMSI`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConnectIt(struct tagDBC *a1, struct CDlgATTRs *a2, char a3)
{
  unsigned __int16 v5; // bp
  __int64 v6; // r14
  int v7; // ebx
  __int16 v8; // ax
  __int64 v9; // rbx
  __int64 v10; // rbx
  _WORD *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int16 v14; // ax
  _WORD *v15; // rax
  _WORD *v16; // rcx
  __int64 v17; // r12
  __int64 v18; // r8
  __int64 v19; // rdx
  __int16 v20; // ax
  _WORD *v21; // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rdx
  _WORD *v27; // rcx
  __int64 v28; // r8
  __int16 v29; // ax
  _WORD *v30; // rax
  __int64 v31; // r15
  __int64 v32; // r8
  _WORD *v33; // rcx
  __int64 v34; // rdx
  __int16 v35; // ax
  _WORD *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r13
  __int64 v39; // rdx
  __int64 v40; // rcx
  _WORD *v41; // rcx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int16 v44; // ax
  _WORD *v45; // rax
  __int64 v46; // rdx
  _WORD *v47; // rcx
  __int64 v48; // r8
  __int64 v49; // rdx
  __int16 v50; // ax
  _WORD *v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rbp
  __int64 v57; // rcx
  __int64 v58; // rdx
  _WORD *v59; // rcx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int16 v62; // ax
  _WORD *v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rdx
  _WORD *v66; // rcx
  __int64 v67; // rdx
  __int16 v68; // ax
  _WORD *v69; // rax
  __int64 v70; // rdx
  unsigned __int64 v71; // rax
  _WORD *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rdx
  __int16 v75; // ax
  _WORD *v76; // rax
  char v77; // al
  _WORD *v78; // rcx
  __int64 v79; // rdx
  __int16 v80; // ax
  _WORD *v81; // rax
  _WORD *v82; // rcx
  __int64 v83; // rdx
  __int16 v84; // ax
  _WORD *v85; // rax
  __int64 v86; // rdx
  __int16 v87; // ax
  int v88; // eax
  __int64 v89; // rdx
  char v90; // cl
  __int64 v91; // rdx
  __int16 v92; // ax
  char v93; // cl
  __int64 v94; // rdx
  __int16 v95; // ax
  char v96; // al
  __int64 v97; // rdx
  __int16 v98; // ax
  char v99; // al
  __int64 v100; // rcx
  char v101; // al
  const wchar_t *v102; // rbx
  int v103; // eax
  __int64 v104; // rcx
  __int64 v105; // rdx
  _WORD *v106; // rcx
  __int64 v107; // r8
  __int64 v108; // rdx
  __int16 v109; // ax
  _WORD *v110; // rax
  __int64 v111; // rcx
  char *v112; // rbx
  __int64 v113; // rdx
  _WORD *v114; // rcx
  __int64 v115; // rdx
  __int16 v116; // ax
  _WORD *v117; // rax
  __int64 v118; // rdx
  __int16 v119; // ax
  char *v120; // rbx
  char *v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // r8
  bool v125; // zf
  char v126; // al
  char v127; // dl
  char *v128; // r8
  __int64 v129; // rax
  __int64 v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rbx
  ConnectionRecoveryManager *v133; // rbp
  __int64 v134; // rcx
  __int64 v135; // r15
  __int64 v136; // rbx
  __int64 v137; // rax
  __int64 v138; // rax
  __int64 v139; // r9
  __int64 v140; // r9
  __int64 v141; // r9
  __int64 v142; // rdx
  __int64 v143; // rbp
  __int16 v144; // cx
  __int64 v145; // rbp
  const WCHAR *v146; // rbp
  const WCHAR *v147; // rbx
  int v148; // eax
  __int64 v149; // r9
  __int64 v150; // rcx
  __int16 v151; // ax
  int v153; // [rsp+30h] [rbp-68h]
  __int16 v154; // [rsp+A0h] [rbp+8h]
  int v155; // [rsp+A8h] [rbp+10h]
  int v157; // [rsp+B8h] [rbp+20h]

  v5 = 0;
  v154 = 0;
  v157 = a3 & 1;
  v153 = a3 & 4;
  v155 = 0;
  v6 = *((_QWORD *)a1 + 395);
  v7 = ValidateAccessTokenOption(a1, a2);
  if ( v7 < 0 )
    goto LABEL_245;
  _mm_lfence();
  v7 = ValidateAuthenticationOption(a1, a2);
  if ( v7 < 0 )
    goto LABEL_245;
  _mm_lfence();
  memset_0(*((void **)a1 + 395), 0, 0x190u);
  *(_QWORD *)((char *)a1 + 9180) = 0;
  *((_WORD *)a1 + 4594) = 0;
  v8 = *((_WORD *)a1 + 1244) & 0xFFFD;
  *((_WORD *)a1 + 1244) = v8;
  if ( *((_QWORD *)a1 + 58) == 1 )
    *((_WORD *)a1 + 1244) = v8 | 2;
  *((_DWORD *)a1 + 818) = 0;
  v9 = *((_QWORD *)a1 + 405);
  if ( v9 )
  {
    if ( *(_QWORD *)v9 != -1 )
    {
      CloseHandle(*(HANDLE *)v9);
      *(_QWORD *)v9 = -1;
    }
    *(_BYTE *)(v9 + 8) = 0;
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v9);
    *((_QWORD *)a1 + 405) = 0;
  }
  v10 = *((_QWORD *)a1 + 406);
  if ( v10 )
  {
    ConnectionRecoveryManager::~ConnectionRecoveryManager(*((ConnectionRecoveryManager **)a1 + 406));
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v10);
    *((_QWORD *)a1 + 406) = 0;
  }
  v11 = (_WORD *)((char *)a1 + 3312);
  v12 = 33;
  v13 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)a2 + 1) + 56LL) - ((_QWORD)a1 + 3312);
  do
  {
    if ( v12 == -2147483613 )
      break;
    v14 = *(_WORD *)((char *)v11 + v13);
    if ( !v14 )
      break;
    *v11++ = v14;
    --v12;
  }
  while ( v12 );
  v15 = v11 - 1;
  if ( v12 )
    v15 = v11;
  *v15 = 0;
  v16 = (_WORD *)((char *)a1 + 3392);
  v17 = 258;
  v18 = 258;
  v19 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 128LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) - ((_QWORD)a1 + 3392);
  do
  {
    if ( v18 == -2147483388 )
      break;
    v20 = *(_WORD *)((char *)v16 + v19);
    if ( !v20 )
      break;
    *v16++ = v20;
    --v18;
  }
  while ( v18 );
  v21 = v16 - 1;
  if ( v18 )
    v21 = v16;
  *v21 = 0;
  v22 = *((_QWORD *)a2 + 1);
  v23 = *((_QWORD *)a2 + 2);
  if ( (*(_BYTE *)(v22 + 336) & 2) == 0 || (v24 = 344, !*(_WORD *)(*(_QWORD *)(v23 + 32) + *(_QWORD *)(v22 + 344))) )
    v24 = 128;
  v25 = *(_QWORD *)(v23 + 32) + *(_QWORD *)(v24 + v22);
  v26 = 258;
  v27 = (_WORD *)((char *)a1 + 6032);
  v28 = v25 - ((_QWORD)a1 + 6032);
  do
  {
    if ( v26 == -2147483388 )
      break;
    v29 = *(_WORD *)((char *)v27 + v28);
    if ( !v29 )
      break;
    *v27++ = v29;
    --v26;
  }
  while ( v26 );
  v30 = v27 - 1;
  if ( v26 )
    v30 = v27;
  *v30 = 0;
  v31 = 129;
  v32 = 129;
  v33 = (_WORD *)((char *)a1 + 3908);
  v34 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 152LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) - ((_QWORD)a1 + 3908);
  do
  {
    if ( v32 == -2147483517 )
      break;
    v35 = *(_WORD *)((char *)v33 + v34);
    if ( !v35 )
      break;
    *v33++ = v35;
    --v32;
  }
  while ( v32 );
  v36 = v33 - 1;
  if ( v32 )
    v36 = v33;
  *v36 = 0;
  v37 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v37 + 192) & 1) != 0 )
  {
    if ( !_wcsicmp((const wchar_t *)(*(_QWORD *)(v37 + 200) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"Yes") )
      goto LABEL_45;
    v37 = *((_QWORD *)a2 + 1);
  }
  if ( (*(_BYTE *)(v37 + 912) & 1) == 0
    || _wcsicmp(
         (const wchar_t *)(*(_QWORD *)(v37 + 920) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
         L"ActiveDirectoryIntegrated")
    && _wcsicmp(
         (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
         L"ActiveDirectoryInteractive")
    && _wcsicmp(
         (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 920LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)),
         L"ActiveDirectoryMSI") )
  {
    ProtectPwdAttr(a1, a2, 7, 0);
    goto LABEL_47;
  }
LABEL_45:
  v155 = 1;
LABEL_47:
  v38 = 272;
  if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 840LL) & 1) != 0 )
  {
    ProtectPwdAttr(a1, a2, 35, (int *)a1 + 3096);
    *((_DWORD *)a1 + 3097) = 0;
    v39 = *((_QWORD *)a2 + 1);
    v40 = v39;
    if ( (*(_BYTE *)(v39 + 1056) & 1) != 0 )
    {
      ProtectPwdAttr(a1, a2, 44, (int *)a1 + 3097);
      v39 = *((_QWORD *)a2 + 1);
      v40 = v39;
    }
    if ( !*((_DWORD *)a1 + 3096) )
    {
      v41 = (_WORD *)((char *)a1 + 11260);
      v42 = 272;
      v43 = *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + *(_QWORD *)(v39 + 848) - ((_QWORD)a1 + 11260);
      do
      {
        if ( v42 == -2147483374 )
          break;
        v44 = *(_WORD *)((char *)v41 + v43);
        if ( !v44 )
          break;
        *v41++ = v44;
        --v42;
      }
      while ( v42 );
      v45 = v41 - 1;
      if ( v42 )
        v45 = v41;
      *v45 = 0;
      v40 = *((_QWORD *)a2 + 1);
    }
    if ( !*((_DWORD *)a1 + 3097) )
    {
      v46 = *(_QWORD *)(v40 + 1064) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
      v47 = (_WORD *)((char *)a1 + 11840);
      v48 = 272;
      v49 = v46 - ((_QWORD)a1 + 11840);
      do
      {
        if ( v48 == -2147483374 )
          break;
        v50 = *(_WORD *)((char *)v47 + v49);
        if ( !v50 )
          break;
        *v47++ = v50;
        --v48;
      }
      while ( v48 );
      v51 = v47 - 1;
      if ( v48 )
        v51 = v47;
      *v51 = 0;
    }
  }
  v52 = *((_QWORD *)a1 + 75);
  if ( v52 )
    *((_QWORD *)a1 + 1476) = v52;
  v53 = *((_QWORD *)a1 + 76);
  if ( v53 )
    *((_QWORD *)a1 + 1477) = v53;
  v54 = *((_QWORD *)a1 + 77);
  if ( v54 )
    *((_QWORD *)a1 + 1478) = v54;
  v55 = *((_QWORD *)a1 + 78);
  if ( v55 )
    *((_QWORD *)a1 + 1479) = v55;
  v56 = 260;
  if ( v157 )
  {
    v57 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v57 + 264) & 0x20) == 0 )
    {
      v58 = *(_QWORD *)(v57 + 272) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
      v59 = (_WORD *)((char *)a1 + 5516);
      v60 = 129;
      v61 = v58 - ((_QWORD)a1 + 5516);
      do
      {
        if ( v60 == -2147483517 )
          break;
        v62 = *(_WORD *)((char *)v59 + v61);
        if ( !v62 )
          break;
        *v59++ = v62;
        --v60;
      }
      while ( v60 );
      v63 = v59 - 1;
      if ( v60 )
        v63 = v59;
      *v63 = 0;
    }
    v64 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v64 + 288) & 0x20) == 0 )
    {
      v65 = *(_QWORD *)(v64 + 296) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
      v66 = (_WORD *)((char *)a1 + 5258);
      v67 = v65 - ((_QWORD)a1 + 5258);
      do
      {
        if ( v31 == -2147483517 )
          break;
        v68 = *(_WORD *)((char *)v66 + v67);
        if ( !v68 )
          break;
        *v66++ = v68;
        --v31;
      }
      while ( v31 );
      v69 = v66 - 1;
      if ( v31 )
        v69 = v66;
      *v69 = 0;
    }
    v70 = *((_QWORD *)a1 + 59);
    if ( v70 )
    {
      v71 = -1;
      do
        ++v71;
      while ( *(_WORD *)(v70 + 2 * v71) );
      if ( v71 > 0x104 )
        *(_WORD *)(v70 + 520) = 0;
      v72 = (_WORD *)((char *)a1 + 8114);
      v73 = 261;
      v74 = v70 - ((_QWORD)a1 + 8114);
      do
      {
        if ( v73 == -2147483385 )
          break;
        v75 = *(_WORD *)((char *)v72 + v74);
        if ( !v75 )
          break;
        *v72++ = v75;
        --v73;
      }
      while ( v73 );
      v76 = v72 - 1;
      if ( v73 )
        v76 = v72;
      *v76 = 0;
    }
  }
  v77 = *((_BYTE *)a1 + 488);
  *(_BYTE *)(v6 + 188) = v77;
  if ( v77 == 2 )
  {
    v78 = (_WORD *)((char *)a1 + 12908);
    v79 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 1256LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) - ((_QWORD)a1 + 12908);
    do
    {
      if ( v38 == -2147483374 )
        break;
      v80 = *(_WORD *)((char *)v78 + v79);
      if ( !v80 )
        break;
      *v78++ = v80;
      --v38;
    }
    while ( v38 );
    v81 = v78 - 1;
    if ( v38 )
      v81 = v78;
    *v81 = 0;
  }
  else
  {
    *(_DWORD *)(v6 + 192) = *((_QWORD *)a1 + 66) == 1;
  }
  v82 = (_WORD *)((char *)a1 + 12392);
  v83 = *(_QWORD *)(*((_QWORD *)a2 + 1) + 1184LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) - ((_QWORD)a1 + 12392);
  do
  {
    if ( v17 == -2147483388 )
      break;
    v84 = *(_WORD *)((char *)v82 + v83);
    if ( !v84 )
      break;
    *v82++ = v84;
    --v17;
  }
  while ( v17 );
  v85 = v82 - 1;
  if ( v17 )
    v85 = v82;
  *v85 = 0;
  v86 = *((_QWORD *)a2 + 1);
  v87 = *(_WORD *)(v86 + 744);
  if ( (v87 & 1) == 0 || (v87 & 0x20) != 0 )
    v88 = 0;
  else
    v88 = StringToApplicationIntent((wchar_t *)(*(_QWORD *)(v86 + 752) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)));
  *((_DWORD *)a1 + 2292) = v88;
  if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 768LL) & 1) == 0
    || (_mm_lfence(), v89 = *((_QWORD *)a2 + 1), (*(_BYTE *)(v89 + 768) & 0x20) != 0) )
  {
    v90 = *((_BYTE *)a1 + 9174) & 0xEF;
  }
  else
  {
    v90 = *((_BYTE *)a1 + 9174) & 0xEF
        | (_wcsicmp((const wchar_t *)(*(_QWORD *)(v89 + 776) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"Yes") == 0
         ? 0x10
         : 0);
  }
  *((_BYTE *)a1 + 9174) = v90;
  v91 = *((_QWORD *)a2 + 1);
  v92 = *(_WORD *)(v91 + 888);
  if ( (v92 & 1) == 0 || (v92 & 0x20) != 0 )
    v93 = v90 | 0x40;
  else
    v93 = *((_BYTE *)a1 + 9174) & 0xBF
        | (_wcsicmp((const wchar_t *)(*(_QWORD *)(v91 + 896) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"Enabled") == 0
         ? 0x40
         : 0);
  *((_BYTE *)a1 + 9174) = v93;
  v94 = *((_QWORD *)a2 + 1);
  v95 = *(_WORD *)(v94 + 792);
  if ( (v95 & 1) == 0 || (v95 & 0x20) != 0 )
    v96 = 1;
  else
    v96 = _wtoi((const wchar_t *)(*(_QWORD *)(v94 + 800) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)));
  *((_BYTE *)a1 + 9172) = v96;
  v97 = *((_QWORD *)a2 + 1);
  v98 = *(_WORD *)(v97 + 816);
  if ( (v98 & 1) == 0 || (v98 & 0x20) != 0 )
    v99 = 10;
  else
    v99 = _wtoi((const wchar_t *)(*(_QWORD *)(v97 + 824) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)));
  *((_BYTE *)a1 + 9173) = v99;
  v100 = *((_QWORD *)a1 + 88);
  v101 = 0;
  if ( v100 )
    v101 = (v100 != 1) + 1;
  *((_BYTE *)a1 + 9175) = v101;
  *((_BYTE *)a1 + 9176) = *((_BYTE *)a1 + 800);
  v102 = (const wchar_t *)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 1232LL) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL));
  if ( _wcsicmp(L"UsePlatformDefault", v102) )
    v103 = (_wcsicmp(L"IPv6First", v102) != 0) + 1;
  else
    v103 = 0;
  *((_DWORD *)a1 + 3623) = v103;
  v104 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v104 + 696) & 1) != 0 )
  {
    v105 = *(_QWORD *)(v104 + 704) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
    v106 = (_WORD *)((char *)a1 + 13452);
    v107 = 260;
    v108 = v105 - ((_QWORD)a1 + 13452);
    do
    {
      if ( v107 == -2147483386 )
        break;
      v109 = *(_WORD *)((char *)v106 + v108);
      if ( !v109 )
        break;
      *v106++ = v109;
      --v107;
    }
    while ( v107 );
    v110 = v106 - 1;
    if ( v107 )
      v110 = v106;
    *v110 = 0;
  }
  v111 = *((_QWORD *)a2 + 1);
  v112 = (char *)a1 + 13972;
  if ( (*(_BYTE *)(v111 + 720) & 1) != 0 )
  {
    v113 = *(_QWORD *)(v111 + 728) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
    v114 = (_WORD *)((char *)a1 + 13972);
    v115 = v113 - (_QWORD)v112;
    do
    {
      if ( v56 == -2147483386 )
        break;
      v116 = *(_WORD *)((char *)v114 + v115);
      if ( !v116 )
        break;
      *v114++ = v116;
      --v56;
    }
    while ( v56 );
    v117 = v114 - 1;
    if ( v56 )
      v117 = v114;
    *v117 = 0;
  }
  *((_BYTE *)a1 + 14496) = 0;
  v118 = *((_QWORD *)a2 + 1);
  v119 = *(_WORD *)(v118 + 1344);
  if ( (v119 & 1) != 0
    && (v119 & 0x20) == 0
    && !_wcsicmp((const wchar_t *)(*(_QWORD *)(v118 + 1352) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"v1") )
  {
    *((_BYTE *)a1 + 14496) = 1;
  }
  *(_DWORD *)(v6 + 212) = (*((unsigned __int8 *)a1 + 9174) >> 2) & 1;
  *(_DWORD *)(v6 + 216) = *((_DWORD *)a1 + 2290);
  *(_QWORD *)v6 = (char *)a1 + 7070;
  *(_DWORD *)(v6 + 220) = *((_DWORD *)a1 + 2291);
  *(_QWORD *)(v6 + 8) = (char *)a1 + 7592;
  *(_QWORD *)(v6 + 16) = (char *)a1 + 5516;
  *(_QWORD *)(v6 + 24) = (char *)a1 + 5258;
  *(_QWORD *)(v6 + 32) = (char *)a1 + 3908;
  *(_DWORD *)(v6 + 236) = *((_DWORD *)a1 + 2292);
  *(_DWORD *)(v6 + 224) = (*((unsigned __int8 *)a1 + 9174) >> 4) & 1;
  *(_DWORD *)(v6 + 228) = (*((unsigned __int8 *)a1 + 9174) >> 6) & 1;
  *(_DWORD *)(v6 + 240) = 0;
  *(_BYTE *)(v6 + 244) = 0;
  *(_QWORD *)(v6 + 264) = (char *)a1 + 11260;
  *(_QWORD *)(v6 + 272) = *((_QWORD *)a1 + 1476);
  *(_QWORD *)(v6 + 280) = (char *)a1 + 11840;
  *(_DWORD *)(v6 + 288) = *((_DWORD *)a1 + 3096);
  *(_DWORD *)(v6 + 292) = *((_DWORD *)a1 + 3097);
  *(_QWORD *)(v6 + 376) = (char *)a1 + 12392;
  *(_QWORD *)(v6 + 120) = (char *)a1 + 13452;
  *(_QWORD *)(v6 + 128) = v112;
  *(_QWORD *)(v6 + 384) = (char *)a1 + 12908;
  *(_DWORD *)(v6 + 392) = *((_DWORD *)a1 + 3623);
  *(_BYTE *)(v6 + 396) = *((_BYTE *)a1 + 14496);
  *(_QWORD *)(v6 + 328) = *((_QWORD *)a1 + 1479);
  *(_QWORD *)(v6 + 312) = *((_QWORD *)a1 + 1477);
  *(_QWORD *)(v6 + 320) = *((_QWORD *)a1 + 1478);
  *(_QWORD *)(v6 + 304) = 0;
  *(_DWORD *)(v6 + 248) = *((_BYTE *)a1 + 9172) != 0;
  *(_DWORD *)(v6 + 252) = 0;
  v120 = (char *)a1 + 4166;
  if ( (*(_BYTE *)(*((_QWORD *)a2 + 1) + 1368LL) & 1) != 0 )
  {
    ProtectPwdAttr(a1, a2, 57, 0);
    v121 = (char *)a1 + 4166;
    v120 = (char *)a1 + 4454;
  }
  else
  {
    v121 = 0;
  }
  *(_QWORD *)(v6 + 40) = v120;
  *(_QWORD *)(v6 + 48) = v121;
  v122 = *((_QWORD *)a1 + 98);
  if ( v122 )
  {
    *(_QWORD *)(v6 + 80) = v122;
  }
  else
  {
    v123 = *((_QWORD *)a1 + 96);
    if ( v123 )
      *(_QWORD *)(v6 + 88) = v123;
  }
  *(_QWORD *)(v6 + 72) = (char *)a1 + 6032;
  *(_QWORD *)(v6 + 56) = (char *)a1 + 5000;
  *(_QWORD *)(v6 + 96) = (char *)a1 + 4742;
  *(_QWORD *)(v6 + 112) = (char *)a1 + 8114;
  *(_QWORD *)(v6 + 104) = L"ODBC";
  *(_DWORD *)(v6 + 136) = *((unsigned __int16 *)a1 + 108);
  *(_DWORD *)(v6 + 184) = *((_QWORD *)a1 + 57) == 1;
  *(_DWORD *)(v6 + 196) = GetUserDefaultLCID();
  *(_QWORD *)(v6 + 336) = *((_QWORD *)a1 + 423);
  *(_DWORD *)(v6 + 344) = 0;
  *(_QWORD *)(v6 + 352) = MSQAAuthContextCache::getInstance();
  *(_BYTE *)(v6 + 372) = *((_BYTE *)a1 + 9176);
  v124 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v124 + 1128) & 1) == 0
    || (v125 = _wcsicmp((const wchar_t *)(*(_QWORD *)(v124 + 1136) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL)), L"Yes") == 0,
        v126 = 1,
        !v125) )
  {
    v126 = 0;
  }
  *(_BYTE *)(v6 + 373) = v126;
  *(_BYTE *)(v6 + 374) = *((_QWORD *)a1 + 104) != 0;
  v127 = 0;
  if ( *((_DWORD *)a1 + 186) != 1 )
    v127 = *((_DWORD *)a1 + 186);
  *(_BYTE *)(v6 + 140) = *((_BYTE *)a1 + 328) | v127;
  *(_BYTE *)(v6 + 256) = *((_BYTE *)a1 + 9175);
  v128 = (char *)*((_QWORD *)a1 + 97);
  if ( !v128 )
    v128 = (char *)g_pTdsParser + 52;
  memcpy_s((void *const)(v6 + 200), 6u, v128, 6u);
  *(_DWORD *)(v6 + 144) = *((_DWORD *)a1 + 124);
  *((_DWORD *)a1 + 787) = 0;
  *(_QWORD *)(v6 + 176) = (char *)a1 + 3148;
  if ( (a3 & 2) != 0 || *((_QWORD *)a1 + 32) != 1 )
  {
    *((_DWORD *)a1 + 792) = -2147483647;
    *((_DWORD *)a1 + 787) = 0;
  }
  else
  {
    *(_DWORD *)(v6 + 208) |= 1u;
    *(_QWORD *)(v6 + 168) = (char *)a1 + 3152;
    *((_DWORD *)a1 + 788) = 265936;
    *((_DWORD *)a1 + 792) = 1;
    *(_QWORD *)(v6 + 152) = 0;
    *(_QWORD *)(v6 + 296) = AsyncConnectCallback;
  }
  if ( *(_DWORD *)(v6 + 248) )
  {
    if ( *(_BYTE *)(v6 + 140) )
    {
      v129 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 16);
      v130 = v129;
      if ( !v129 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 3415049);
        PostSQLErrorEx(a1, 0x9CDDu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
        if ( (bidGblFlags & 2) != 0 )
          v7 = bidTraceHR(0, 3416073, 2147942414LL, v140);
        else
          v7 = -2147024882;
        goto LABEL_241;
      }
      *(_QWORD *)v129 = -1;
      *(_BYTE *)(v129 + 8) = 0;
      if ( (int)CThreadSecurityToken::Initialize((PHANDLE)v129) >= 0 )
      {
        *((_QWORD *)a1 + 405) = v130;
        v130 = 0;
      }
      else
      {
        *(_DWORD *)(v6 + 248) = 0;
        *((_BYTE *)a1 + 9172) = 0;
      }
      if ( v130 )
      {
        if ( *(_QWORD *)v130 != -1 )
        {
          CloseHandle(*(HANDLE *)v130);
          *(_QWORD *)v130 = -1;
        }
        *(_BYTE *)(v130 + 8) = 0;
        ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v130);
      }
    }
    if ( *(_DWORD *)(v6 + 248) )
    {
      v131 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 2128);
      v132 = v131;
      if ( v131 )
      {
        *(_QWORD *)v131 = 0;
        *(_BYTE *)(v131 + 8) = 0;
        *(_DWORD *)(v131 + 12) = 0;
        *(_DWORD *)(v131 + 16) = 0;
        *(_QWORD *)(v131 + 24) = 0;
        *(_QWORD *)(v131 + 40) = v131 + 32;
        *(_QWORD *)(v131 + 32) = v131 + 32;
        *(_QWORD *)(v131 + 48) = 0;
        *(_QWORD *)(v131 + 56) = 0;
        memset_0((void *)(v131 + 64), 0, 0x800u);
        *(_QWORD *)(v132 + 2112) = 0;
        *(_BYTE *)(v132 + 2120) = 0;
        v133 = (ConnectionRecoveryManager *)v132;
        if ( (int)ConnectionRecoveryManager::Initialize((ConnectionRecoveryManager *)v132, a1) >= 0 )
        {
          *((_QWORD *)a1 + 406) = v132;
          goto LABEL_195;
        }
      }
      else
      {
        v133 = 0;
      }
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 3440649);
      PostSQLErrorEx(a1, 0x9CDDu, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      if ( (bidGblFlags & 2) != 0 )
        v7 = bidTraceHR(0, 3441673, 2147942414LL, v141);
      else
        v7 = -2147024882;
      if ( v133 )
      {
        ConnectionRecoveryManager::~ConnectionRecoveryManager(v133);
        ((void (__fastcall *)(struct IMalloc *, ConnectionRecoveryManager *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v133);
      }
      goto LABEL_241;
    }
  }
LABEL_195:
  *(_DWORD *)(v6 + 364) = GetDSNorDriverField(a2, 45, L"KEEPALIVE", 30);
  *(_DWORD *)(v6 + 368) = GetDSNorDriverField(a2, 46, L"KEEPALIVEINTERVAL", 1);
  v134 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v134 + 1272) & 1) == 0 )
    goto LABEL_221;
  v135 = *(_QWORD *)(v134 + 1280) + *(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL);
  v136 = -1;
  do
    ++v136;
  while ( *(_WORD *)(v135 + 2 * v136) );
  v137 = 2LL * ((int)v136 + 1);
  if ( !is_mul_ok((int)v136 + 1, 2u) )
    v137 = -1;
  v138 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v137);
  *((_QWORD *)a1 + 413) = v138;
  if ( v138 )
  {
    if ( (int)v136 > 0 )
    {
      v142 = 0;
      do
      {
        *(_WORD *)(*((_QWORD *)a1 + 413) + 2 * v142) = *(_WORD *)(v135 + 2 * v142);
        ++v142;
      }
      while ( v142 < (int)v136 );
    }
    *(_WORD *)(*((_QWORD *)a1 + 413) + 2LL * (int)v136) = 0;
LABEL_221:
    v143 = *((_QWORD *)a2 + 1);
    if ( (*(_BYTE *)(v143 + 96) & 1) != 0 || (*(_BYTE *)(v143 + 48) & 1) != 0 )
    {
      v144 = *(_WORD *)(v143 + 48) & 1;
      if ( v144 )
        v145 = *(_QWORD *)(v143 + 56);
      else
        v145 = *(_QWORD *)(v143 + 104);
      v146 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 32LL) + v145);
      v147 = L"ODBCINST.INI";
      if ( v144 )
        v147 = L"ODBC.INI";
      *(_DWORD *)(v6 + 360) = GetConfigValDw(v146, L"ADALuseWAM", v147, 0);
      *(_BYTE *)(v6 + 141) = GetConfigValBool(v146, L"Trusted_ConnectionUseAAD", v147);
    }
    v148 = CTdsParser::OpenServerConnection(
             g_pTdsParser,
             (struct _LOGINSTRUCT *)v6,
             a1,
             *((_DWORD *)a1 + 345),
             (struct CConnection *volatile *)a1 + 8);
    v7 = v148;
    if ( v148 >= 0 )
    {
      if ( v148 == 265936 )
      {
        v5 = 2;
        goto LABEL_245;
      }
      _mm_lfence();
      *((_DWORD *)a1 + 792) = 0;
      *((_DWORD *)a1 + 787) = 0;
      if ( v148 == 265937 )
        v154 = 1;
      ODBCPostConnect(a1);
    }
    else
    {
      if ( v148 == -2147023673 )
      {
        _mm_lfence();
        if ( (bidGblFlags & 2) != 0 )
          bidTraceMark(0, 3495945);
        PostSQLErrorEx(a1, 0x9CE0u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
      }
      *((_DWORD *)a1 + 792) = 0;
      *((_DWORD *)a1 + 787) = 0;
      if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(0, 3500041, (unsigned int)v7, v149);
      }
    }
    goto LABEL_241;
  }
  if ( (bidGblFlags & 2) != 0 )
    v7 = bidTraceHR(0, 3460105, 2147942414LL, v139);
  else
    v7 = -2147024882;
LABEL_241:
  if ( v153 && !v155 )
  {
    UnProtectPwdAttr(a1, a2, 7);
    UnProtectPwdAttr(a1, a2, 57);
  }
  v5 = v154;
LABEL_245:
  v150 = *((_QWORD *)a2 + 1);
  v151 = *(_WORD *)(v150 + 1368);
  if ( (v151 & 1) != 0 )
  {
    *(_WORD *)(v150 + 1368) = v151 & 0xFFFE;
    if ( *((_QWORD *)a1 + 64) )
    {
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
      *((_QWORD *)a1 + 64) = 0;
    }
    *((_BYTE *)a1 + 1342) &= ~1u;
  }
  if ( v7 < 0 )
  {
    _mm_lfence();
    if ( *((_QWORD *)a1 + 8) )
      CTdsParser::Disconnect(g_pTdsParser, a1, (struct CConnection *volatile *)a1 + 8);
    *((_WORD *)a1 + 1696) = 0;
    *((_WORD *)a1 + 3016) = 0;
    *((_WORD *)a1 + 3535) = 0;
    ResetOptions(a1);
    v5 = -1;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x364C09u, v5);
  return v5;
}

```

## disassembly

```asm
0x1004e5b60  mov     [rsp+arg_10], r8d
0x1004e5b65  push    rbx
0x1004e5b66  push    rbp
0x1004e5b67  push    rsi
0x1004e5b68  push    rdi
0x1004e5b69  push    r12
0x1004e5b6b  push    r13
0x1004e5b6d  push    r14
0x1004e5b6f  push    r15
0x1004e5b71  sub     rsp, 58h
0x1004e5b75  mov     [rsp+98h+var_50], 0FFFFFFFFFFFFFFFEh
0x1004e5b7e  mov     rsi, rdx
0x1004e5b81  mov     rdi, rcx
0x1004e5b84  xor     r13d, r13d
0x1004e5b87  movzx   ebp, r13w
0x1004e5b8b  mov     [rsp+98h+arg_0], ebp
0x1004e5b92  mov     eax, r8d
0x1004e5b95  lea     r12d, [r13+1]
0x1004e5b99  and     eax, r12d
0x1004e5b9c  mov     dword ptr [rsp+98h+arg_18], eax
0x1004e5ba3  mov     eax, r8d
0x1004e5ba6  and     eax, 4
0x1004e5ba9  mov     [rsp+98h+var_68], eax
0x1004e5bad  mov     [rsp+98h+arg_8], r13d
0x1004e5bb5  mov     r14, [rcx+0C58h]
0x1004e5bbc  call    ?ValidateAccessTokenOption@@YAJPEAUtagDBC@@AEBVCDlgATTRs@@@Z; ValidateAccessTokenOption(tagDBC *,CDlgATTRs const &)
0x1004e5bc1  mov     ebx, eax
0x1004e5bc3  lea     r15d, [r13+2]
0x1004e5bc7  test    eax, eax
0x1004e5bc9  js      loc_1004E6D70
0x1004e5bcf  lfence
0x1004e5bd2  mov     rdx, rsi; struct CDlgATTRs *
0x1004e5bd5  mov     rcx, rdi; struct tagOBJBASE *
0x1004e5bd8  call    ?ValidateAuthenticationOption@@YAJPEAUtagOBJBASE@@AEBVCDlgATTRs@@@Z; ValidateAuthenticationOption(tagOBJBASE *,CDlgATTRs const &)
0x1004e5bdd  mov     ebx, eax
0x1004e5bdf  test    eax, eax
0x1004e5be1  js      loc_1004E6D70
0x1004e5be7  lfence
0x1004e5bea  xor     edx, edx; Val
0x1004e5bec  mov     r8d, 190h; Size
0x1004e5bf2  mov     rcx, [rdi+0C58h]; void *
0x1004e5bf9  call    memset_0
0x1004e5bfe  mov     [rdi+23DCh], r13
0x1004e5c05  mov     [rdi+23E4h], r13w
0x1004e5c0d  mov     eax, 0FFFDh
0x1004e5c12  and     ax, [rdi+9B8h]
0x1004e5c19  mov     [rdi+9B8h], ax
0x1004e5c20  cmp     [rdi+1D0h], r12
0x1004e5c27  jnz     short loc_1004E5C34
0x1004e5c29  or      ax, r15w
0x1004e5c2d  mov     [rdi+9B8h], ax
0x1004e5c34  mov     [rdi+0CC8h], r13d
0x1004e5c3b  mov     rbx, [rdi+0CA8h]
0x1004e5c42  test    rbx, rbx
0x1004e5c45  jz      short loc_1004E5C7E
0x1004e5c47  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1004e5c4b  cmp     [rbx], rbp
0x1004e5c4e  jz      short loc_1004E5C5C
0x1004e5c50  mov     rcx, [rbx]; hObject
0x1004e5c53  call    cs:__imp_CloseHandle
0x1004e5c59  mov     [rbx], rbp
0x1004e5c5c  mov     [rbx+8], r13b
0x1004e5c60  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004e5c67  mov     rax, [rcx]
0x1004e5c6a  mov     rdx, rbx
0x1004e5c6d  mov     rax, [rax+68h]
0x1004e5c71  call    cs:__guard_dispatch_icall_fptr
0x1004e5c77  mov     [rdi+0CA8h], r13
0x1004e5c7e  mov     rbx, [rdi+0CB0h]
0x1004e5c85  test    rbx, rbx
0x1004e5c88  jz      short loc_1004E5CB0
0x1004e5c8a  mov     rcx, rbx; this
0x1004e5c8d  call    ??1ConnectionRecoveryManager@@QEAA@XZ; ConnectionRecoveryManager::~ConnectionRecoveryManager(void)
0x1004e5c92  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004e5c99  mov     rax, [rcx]
0x1004e5c9c  mov     rdx, rbx
0x1004e5c9f  mov     rax, [rax+68h]
0x1004e5ca3  call    cs:__guard_dispatch_icall_fptr
0x1004e5ca9  mov     [rdi+0CB0h], r13
0x1004e5cb0  mov     rax, [rsi+8]
0x1004e5cb4  mov     rcx, [rsi+10h]
0x1004e5cb8  mov     rdx, [rax+38h]
0x1004e5cbc  add     rdx, [rcx+20h]
0x1004e5cc0  lea     rcx, [rdi+0CF0h]
0x1004e5cc7  mov     r8d, 21h ; '!'
0x1004e5ccd  sub     rdx, rcx
0x1004e5cd0  lea     rax, [r8+7FFFFFDDh]
0x1004e5cd7  test    rax, rax
0x1004e5cda  jz      short loc_1004E5CF0
0x1004e5cdc  movzx   eax, word ptr [rcx+rdx]
0x1004e5ce0  test    ax, ax
0x1004e5ce3  jz      short loc_1004E5CF0
0x1004e5ce5  mov     [rcx], ax
0x1004e5ce8  add     rcx, r15
0x1004e5ceb  sub     r8, r12
0x1004e5cee  jnz     short loc_1004E5CD0
0x1004e5cf0  lea     rax, [rcx-2]
0x1004e5cf4  test    r8, r8
0x1004e5cf7  cmovnz  rax, rcx
0x1004e5cfb  mov     [rax], r13w
0x1004e5cff  mov     rax, [rsi+10h]
0x1004e5d03  mov     rcx, [rsi+8]
0x1004e5d07  mov     rdx, [rax+20h]
0x1004e5d0b  add     rdx, [rcx+80h]
0x1004e5d12  lea     rcx, [rdi+0D40h]
0x1004e5d19  mov     r12d, 102h
0x1004e5d1f  mov     r8d, r12d
0x1004e5d22  sub     rdx, rcx
0x1004e5d25  lea     rax, [r8+7FFFFEFCh]
0x1004e5d2c  test    rax, rax
0x1004e5d2f  jz      short loc_1004E5D46
0x1004e5d31  movzx   eax, word ptr [rcx+rdx]
0x1004e5d35  test    ax, ax
0x1004e5d38  jz      short loc_1004E5D46
0x1004e5d3a  mov     [rcx], ax
0x1004e5d3d  add     rcx, r15
0x1004e5d40  sub     r8, 1
0x1004e5d44  jnz     short loc_1004E5D25
0x1004e5d46  lea     rax, [rcx-2]
0x1004e5d4a  test    r8, r8
0x1004e5d4d  cmovnz  rax, rcx
0x1004e5d51  mov     [rax], r13w
0x1004e5d55  mov     r8, [rsi+8]
0x1004e5d59  mov     rdx, [rsi+10h]
0x1004e5d5d  test    [r8+150h], r15b
0x1004e5d64  jz      short loc_1004E5D7D
0x1004e5d66  mov     rcx, [rdx+20h]
0x1004e5d6a  mov     rax, [r8+158h]
0x1004e5d71  cmp     [rcx+rax], r13w
0x1004e5d76  mov     eax, 158h
0x1004e5d7b  jnz     short loc_1004E5D82
0x1004e5d7d  mov     eax, 80h
0x1004e5d82  mov     r8, [rax+r8]
0x1004e5d86  add     r8, [rdx+20h]
0x1004e5d8a  lea     rax, [rdi+1790h]
0x1004e5d91  mov     rdx, r12
0x1004e5d94  mov     rcx, rax
0x1004e5d97  sub     r8, rax
0x1004e5d9a  lea     rax, [rdx+7FFFFEFCh]
0x1004e5da1  test    rax, rax
0x1004e5da4  jz      short loc_1004E5DBC
0x1004e5da6  movzx   eax, word ptr [rcx+r8]
0x1004e5dab  test    ax, ax
0x1004e5dae  jz      short loc_1004E5DBC
0x1004e5db0  mov     [rcx], ax
0x1004e5db3  add     rcx, r15
0x1004e5db6  sub     rdx, 1
0x1004e5dba  jnz     short loc_1004E5D9A
0x1004e5dbc  lea     rax, [rcx-2]
0x1004e5dc0  test    rdx, rdx
0x1004e5dc3  cmovnz  rax, rcx
0x1004e5dc7  mov     [rax], r13w
0x1004e5dcb  mov     rax, [rsi+10h]
0x1004e5dcf  mov     rcx, [rsi+8]
0x1004e5dd3  mov     rdx, [rax+20h]
0x1004e5dd7  add     rdx, [rcx+98h]
0x1004e5dde  lea     rax, [rdi+0F44h]
0x1004e5de5  mov     r15d, 81h
0x1004e5deb  mov     r8d, r15d
0x1004e5dee  mov     rcx, rax
0x1004e5df1  sub     rdx, rax
0x1004e5df4  lea     rax, [r8+7FFFFF7Dh]
0x1004e5dfb  test    rax, rax
0x1004e5dfe  jz      short loc_1004E5E16
0x1004e5e00  movzx   eax, word ptr [rcx+rdx]
0x1004e5e04  test    ax, ax
0x1004e5e07  jz      short loc_1004E5E16
0x1004e5e09  mov     [rcx], ax
0x1004e5e0c  add     rcx, 2
0x1004e5e10  sub     r8, 1
0x1004e5e14  jnz     short loc_1004E5DF4
0x1004e5e16  lea     rax, [rcx-2]
0x1004e5e1a  test    r8, r8
0x1004e5e1d  cmovnz  rax, rcx
0x1004e5e21  mov     [rax], r13w
0x1004e5e25  mov     rdx, [rsi+8]
0x1004e5e29  test    byte ptr [rdx+0C0h], 1
0x1004e5e30  jz      short loc_1004E5E56
0x1004e5e32  mov     rax, [rsi+10h]
0x1004e5e36  mov     rcx, [rax+20h]
0x1004e5e3a  add     rcx, [rdx+0C8h]; String1
0x1004e5e41  lea     rdx, aYes_1; "Yes"
0x1004e5e48  call    cs:__imp__wcsicmp
0x1004e5e4e  test    eax, eax
0x1004e5e50  jz      short loc_1004E5EC7
0x1004e5e52  mov     rdx, [rsi+8]
0x1004e5e56  test    byte ptr [rdx+390h], 1
0x1004e5e5d  jz      short loc_1004E5ED4
0x1004e5e5f  mov     rax, [rsi+10h]
0x1004e5e63  mov     rcx, [rax+20h]
0x1004e5e67  add     rcx, [rdx+398h]; String1
0x1004e5e6e  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x1004e5e75  call    cs:__imp__wcsicmp
0x1004e5e7b  test    eax, eax
0x1004e5e7d  jz      short loc_1004E5EC7
0x1004e5e7f  mov     rax, [rsi+10h]
0x1004e5e83  mov     rdx, [rsi+8]
0x1004e5e87  mov     rcx, [rax+20h]
0x1004e5e8b  add     rcx, [rdx+398h]; String1
0x1004e5e92  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x1004e5e99  call    cs:__imp__wcsicmp
0x1004e5e9f  test    eax, eax
0x1004e5ea1  jz      short loc_1004E5EC7
0x1004e5ea3  mov     rax, [rsi+10h]
0x1004e5ea7  mov     rdx, [rsi+8]
0x1004e5eab  mov     rcx, [rax+20h]
0x1004e5eaf  add     rcx, [rdx+398h]; String1
0x1004e5eb6  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x1004e5ebd  call    cs:__imp__wcsicmp
0x1004e5ec3  test    eax, eax
0x1004e5ec5  jnz     short loc_1004E5ED4
0x1004e5ec7  mov     [rsp+98h+arg_8], 1
0x1004e5ed2  jmp     short loc_1004E5EE6
0x1004e5ed4  xor     r9d, r9d; int *
0x1004e5ed7  lea     r8d, [r9+7]; int
0x1004e5edb  mov     rdx, rsi; struct CDlgATTRs *
0x1004e5ede  mov     rcx, rdi; struct tagOBJBASE *
0x1004e5ee1  call    ?ProtectPwdAttr@@YAFPEAUtagOBJBASE@@AEAVCDlgATTRs@@HPEAH@Z; ProtectPwdAttr(tagOBJBASE *,CDlgATTRs &,int,int *)
0x1004e5ee6  mov     rax, [rsi+8]
0x1004e5eea  mov     r13d, 110h
0x1004e5ef0  test    byte ptr [rax+348h], 1
0x1004e5ef7  jz      loc_1004E5FFE
0x1004e5efd  lea     rbp, [rdi+3060h]
0x1004e5f04  mov     r9, rbp; int *
0x1004e5f07  mov     r8d, 23h ; '#'; int
0x1004e5f0d  mov     rdx, rsi; struct CDlgATTRs *
0x1004e5f10  mov     rcx, rdi; struct tagOBJBASE *
0x1004e5f13  call    ?ProtectPwdAttr@@YAFPEAUtagOBJBASE@@AEAVCDlgATTRs@@HPEAH@Z; ProtectPwdAttr(tagOBJBASE *,CDlgATTRs &,int,int *)
0x1004e5f18  lea     rbx, [rdi+3064h]
0x1004e5f1f  xor     r9d, r9d
0x1004e5f22  mov     [rbx], r9d
0x1004e5f25  mov     rdx, [rsi+8]
0x1004e5f29  mov     rcx, rdx
0x1004e5f2c  test    byte ptr [rdx+420h], 1
0x1004e5f33  jz      short loc_1004E5F53
0x1004e5f35  mov     r9, rbx; int *
0x1004e5f38  mov     r8d, 2Ch ; ','; int
0x1004e5f3e  mov     rdx, rsi; struct CDlgATTRs *
0x1004e5f41  mov     rcx, rdi; struct tagOBJBASE *
0x1004e5f44  call    ?ProtectPwdAttr@@YAFPEAUtagOBJBASE@@AEAVCDlgATTRs@@HPEAH@Z; ProtectPwdAttr(tagOBJBASE *,CDlgATTRs &,int,int *)
0x1004e5f49  mov     rdx, [rsi+8]
0x1004e5f4d  mov     rcx, rdx
0x1004e5f50  xor     r9d, r9d
0x1004e5f53  cmp     [rbp+0], r9d
0x1004e5f57  jnz     short loc_1004E5FAA
0x1004e5f59  mov     rax, [rsi+10h]
0x1004e5f5d  mov     rdx, [rdx+350h]
0x1004e5f64  add     rdx, [rax+20h]
0x1004e5f68  lea     rcx, [rdi+2BFCh]
0x1004e5f6f  mov     r8, r13
0x1004e5f72  sub     rdx, rcx
0x1004e5f75  lea     rax, [r8+7FFFFEEEh]
0x1004e5f7c  test    rax, rax
0x1004e5f7f  jz      short loc_1004E5F97
0x1004e5f81  movzx   eax, word ptr [rdx+rcx]
0x1004e5f85  test    ax, ax
0x1004e5f88  jz      short loc_1004E5F97
0x1004e5f8a  mov     [rcx], ax
0x1004e5f8d  add     rcx, 2
0x1004e5f91  sub     r8, 1
0x1004e5f95  jnz     short loc_1004E5F75
0x1004e5f97  lea     rax, [rcx-2]
0x1004e5f9b  test    r8, r8
0x1004e5f9e  cmovnz  rax, rcx
0x1004e5fa2  mov     [rax], r9w
0x1004e5fa6  mov     rcx, [rsi+8]
0x1004e5faa  cmp     [rbx], r9d
0x1004e5fad  jnz     short loc_1004E6001
0x1004e5faf  mov     rax, [rsi+10h]
0x1004e5fb3  mov     rdx, [rax+20h]
0x1004e5fb7  add     rdx, [rcx+428h]
0x1004e5fbe  lea     rcx, [rdi+2E40h]
0x1004e5fc5  mov     r8, r13
0x1004e5fc8  sub     rdx, rcx
0x1004e5fcb  lea     rax, [r8+7FFFFEEEh]
0x1004e5fd2  test    rax, rax
0x1004e5fd5  jz      short loc_1004E5FED
0x1004e5fd7  movzx   eax, word ptr [rcx+rdx]
0x1004e5fdb  test    ax, ax
0x1004e5fde  jz      short loc_1004E5FED
0x1004e5fe0  mov     [rcx], ax
0x1004e5fe3  add     rcx, 2
0x1004e5fe7  sub     r8, 1
0x1004e5feb  jnz     short loc_1004E5FCB
0x1004e5fed  lea     rax, [rcx-2]
0x1004e5ff1  test    r8, r8
0x1004e5ff4  cmovnz  rax, rcx
0x1004e5ff8  mov     [rax], r9w
0x1004e5ffc  jmp     short loc_1004E6001
0x1004e5ffe  xor     r9d, r9d
0x1004e6001  mov     rax, [rdi+258h]
0x1004e6008  test    rax, rax
0x1004e600b  jz      short loc_1004E6014
0x1004e600d  mov     [rdi+2E20h], rax
0x1004e6014  mov     rax, [rdi+260h]
0x1004e601b  test    rax, rax
0x1004e601e  jz      short loc_1004E6027
0x1004e6020  mov     [rdi+2E28h], rax
0x1004e6027  mov     rax, [rdi+268h]
0x1004e602e  test    rax, rax
  ... truncated ...
```
