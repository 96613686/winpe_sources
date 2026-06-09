# DsrCmdStatusHelper::PrintStatus(CLI_EXTENSIONS const &)

- ea: `0x1800a523c`
- end: `0x1800a6746`
- name: `?PrintStatus@DsrCmdStatusHelper@@SAJAEBUCLI_EXTENSIONS@@@Z`
- size: `5386`
- prototype: `__int64 __fastcall(const struct CLI_EXTENSIONS *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009b940`

## callees

- `0x18000bac0`
- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x1800138d4`
- `0x180016510`
- `0x18001ebe4`
- `0x18002927c`
- `0x18002a7e8`
- `0x18002b9b4`
- `0x18002df9c`
- `0x180033984`
- `0x1800367d8`
- `0x18003878c`
- `0x180038e44`
- `0x180043480`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800a21e4`
- `0x1800a23d0`
- `0x1800a29d8`
- `0x1800a30b8`
- `0x1800a383c`
- `0x1800a3db0`
- `0x1800a4b04`
- `0x1800a523c`
- `0x1800adf04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e9a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a6316`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a6321`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a632c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a6316`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a6321`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a632c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5e28`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a5e28`

## string_xrefs

- `0x1800a5df6`: `/WriteToFile`
- `0x1800a5f47`: `Failed to compute task output filename [0x%08x]. Exiting...\n`
- `0x1800a5f5c`: `Failed to compute task output filename [0x%08x]. Exiting...\n`
- `0x1800a5e3a`: `Successfully deleted file %s\n`
- `0x1800a5eb7`: `Failed to delete file %s. code: 0x%08x.\n`
- `0x1800a5de0`: `Diagnostics Task`
- `0x1800a65c0`: `For more information, please visit https://www.microsoft.com/aadjerrors`
- `0x1800a65d3`: `For more information, please visit https://www.microsoft.com/aadjerrors`
- `0x1800a621c`: `IE Proxy Config for Current User`

## pseudocode

```c
__int64 __fastcall DsrCmdStatusHelper::PrintStatus(const struct CLI_EXTENSIONS *a1)
{
  unsigned int VdiSettings; // edi
  const wchar_t *v3; // rbx
  __int64 CurrentRef; // rax
  const wchar_t *v5; // rcx
  const wchar_t *v6; // rbx
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rbx
  __int64 v10; // rax
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rbx
  __int64 v13; // rax
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rbx
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rbx
  __int64 v19; // rax
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rbx
  __int64 v22; // rax
  const wchar_t *v23; // rcx
  const wchar_t *v24; // rbx
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  const wchar_t *v27; // rbx
  __int64 v28; // rax
  const wchar_t *v29; // rcx
  const wchar_t *v30; // rbx
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rbx
  __int64 v34; // rax
  const wchar_t *v35; // rcx
  const wchar_t *v36; // rbx
  __int64 v37; // rax
  const wchar_t *v38; // rcx
  const wchar_t *v39; // rbx
  __int64 v40; // rax
  const wchar_t *v41; // rcx
  const wchar_t *v42; // rbx
  __int64 v43; // rax
  const wchar_t *v44; // rcx
  const wchar_t *v45; // rbx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  const wchar_t *v48; // rbx
  __int64 v49; // rax
  const wchar_t *v50; // rcx
  const wchar_t *v51; // rbx
  __int64 v52; // rax
  const wchar_t *v53; // rcx
  unsigned int v54; // ebx
  __int64 v55; // rax
  __int64 v56; // rax
  WINBOOL v57; // eax
  LPCWSTR *v58; // rbx
  const WCHAR *v59; // rcx
  __int64 v60; // rax
  signed int LastError; // eax
  __int64 v62; // rax
  __int64 v63; // rax
  const wchar_t *v64; // rbx
  __int64 v65; // rax
  const wchar_t *v66; // rcx
  wchar_t **v67; // rcx
  const wchar_t *v68; // rbx
  __int64 v69; // rax
  const wchar_t *v70; // rcx
  const wchar_t *v71; // rbx
  __int64 v72; // rax
  const wchar_t *v73; // rcx
  const wchar_t *v74; // rbx
  __int64 v75; // rax
  const wchar_t *v76; // rcx
  __int64 v77; // rax
  const wchar_t *v78; // rbx
  __int64 v79; // rax
  const wchar_t *v80; // rcx
  const wchar_t *v81; // rbx
  __int64 v82; // rax
  const wchar_t *v83; // rcx
  const wchar_t *v84; // rbx
  __int64 v85; // rax
  const wchar_t *v86; // rcx
  const wchar_t *v87; // rbx
  __int64 v88; // rax
  const wchar_t *v89; // rcx
  const wchar_t *v90; // rbx
  __int64 v91; // rax
  const wchar_t *v92; // rcx
  const wchar_t *v93; // rbx
  __int64 v94; // rax
  const wchar_t *v95; // rcx
  const wchar_t *v96; // rbx
  __int64 v97; // rax
  const wchar_t *v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  char v102; // [rsp+40h] [rbp-C0h] BYREF
  char v103; // [rsp+41h] [rbp-BFh] BYREF
  char v104; // [rsp+42h] [rbp-BEh] BYREF
  char v105; // [rsp+43h] [rbp-BDh] BYREF
  _BYTE v106[4]; // [rsp+44h] [rbp-BCh] BYREF
  WINBOOL v107; // [rsp+48h] [rbp-B8h] BYREF
  WINBOOL IsMember; // [rsp+4Ch] [rbp-B4h] BYREF
  HGLOBAL hMem[2]; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL v110[2]; // [rsp+60h] [rbp-A0h]
  _OWORD v111[2]; // [rsp+70h] [rbp-90h] BYREF
  int v112; // [rsp+90h] [rbp-70h]
  int v113; // [rsp+94h] [rbp-6Ch]
  int v114; // [rsp+98h] [rbp-68h]
  int v115; // [rsp+A0h] [rbp-60h]
  __int64 v116; // [rsp+A8h] [rbp-58h]
  int v117; // [rsp+B0h] [rbp-50h]
  int v118; // [rsp+B4h] [rbp-4Ch]
  wchar_t *v119[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v120; // [rsp+D8h] [rbp-28h]
  wchar_t *v121[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v122; // [rsp+F8h] [rbp-8h]
  _BYTE v123[32]; // [rsp+100h] [rbp+0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v125; // [rsp+138h] [rbp+38h]
  wchar_t *v126[3]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v127; // [rsp+158h] [rbp+58h]
  wchar_t *v128[3]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v129; // [rsp+178h] [rbp+78h]
  wchar_t *v130[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v131; // [rsp+198h] [rbp+98h]
  wchar_t *v132[3]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int64 v133; // [rsp+1B8h] [rbp+B8h]
  wchar_t *v134[3]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v135; // [rsp+1D8h] [rbp+D8h]
  wchar_t *v136[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int64 v137; // [rsp+1F8h] [rbp+F8h]
  wchar_t *v138[3]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v139; // [rsp+218h] [rbp+118h]
  wchar_t *v140[3]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int64 v141; // [rsp+238h] [rbp+138h]
  wchar_t *v142[3]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int64 v143; // [rsp+258h] [rbp+158h]
  wchar_t *v144[3]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int64 v145; // [rsp+278h] [rbp+178h]
  wchar_t *Format[3]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int64 v147; // [rsp+298h] [rbp+198h]
  wchar_t *v148[3]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int64 v149; // [rsp+2B8h] [rbp+1B8h]
  wchar_t *v150[3]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int64 v151; // [rsp+2D8h] [rbp+1D8h]
  wchar_t *v152[3]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int64 v153; // [rsp+2F8h] [rbp+1F8h]
  wchar_t *v154[3]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 v155; // [rsp+318h] [rbp+218h]
  wchar_t *v156[3]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int64 v157; // [rsp+338h] [rbp+238h]
  wchar_t *v158[3]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int64 v159; // [rsp+358h] [rbp+258h]
  wchar_t *v160[3]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int64 v161; // [rsp+378h] [rbp+278h]
  wchar_t *v162[3]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int64 v163; // [rsp+398h] [rbp+298h]
  wchar_t *v164[3]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int64 v165; // [rsp+3B8h] [rbp+2B8h]
  wchar_t *v166[3]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int64 v167; // [rsp+3D8h] [rbp+2D8h]
  wchar_t *v168[3]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int64 v169; // [rsp+3F8h] [rbp+2F8h]
  wchar_t *v170[3]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int64 v171; // [rsp+418h] [rbp+318h]
  wchar_t *v172[3]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int64 v173; // [rsp+438h] [rbp+338h]

  v105 = 0;
  v111[0] = _mm_load_si128((const __m128i *)&_xmm);
  v111[1] = v111[0];
  v112 = 3;
  v113 = 3;
  v114 = 3;
  v115 = 0;
  v116 = 0;
  v117 = 3;
  v118 = 3;
  v104 = 0;
  v102 = 0;
  v103 = 0;
  v106[0] = 0;
  std::wstring::wstring(v168);
  std::wstring::wstring(v166);
  std::wstring::wstring(v164);
  std::wstring::wstring(v162);
  std::wstring::wstring(v160);
  std::wstring::wstring(v126);
  std::wstring::wstring(v158);
  std::wstring::wstring(v156);
  std::wstring::wstring(v154);
  std::wstring::wstring(v152);
  std::wstring::wstring(v150);
  std::wstring::wstring(v148);
  std::wstring::wstring(Format);
  std::wstring::wstring(v144);
  std::wstring::wstring(v142);
  std::wstring::wstring(v140);
  std::wstring::wstring(v172);
  std::wstring::wstring(v170);
  std::wstring::wstring(v138);
  std::wstring::wstring(v136);
  std::wstring::wstring(v134);
  std::wstring::wstring(v132);
  DsrCmdStatusHelper::GetStatusAadJoin(
    (unsigned int)v166,
    (unsigned int)v164,
    (unsigned int)v162,
    (unsigned int)v160,
    (__int64)v126,
    (__int64)&v102,
    (__int64)&v103);
  DsrCmdStatusHelper::GetStatusDomainJoin(v158, &v104);
  DsrCmdStatusHelper::GetStatusWamDefault(v156);
  DsrCmdStatusHelper::GetStatusWorkplaceJoin(v154, v152);
  DsrCmdStatusHelper::GetDeviceName(v138);
  DsrCmdStatusHelper::GetStatusNgcSet(v168, &v105);
  DsrCmdStatusHelper::GetStatusNgcPreReq(v150, v111);
  DsrCmdStatusHelper::GetStatusPrtInfo(v148);
  VdiSettings = DsrCmdStatusHelper::GetVdiSettings(v136, v134, v106);
  std::wstring::wstring(v119, L"Device State");
  DsrCmdStatusHelper::GetDisplayHeader(v119, Format);
  std::wstring::_Tidy_deallocate(v119);
  std::wstring::wstring(v119, L"Device Details");
  DsrCmdStatusHelper::GetDisplayHeader(v119, v144);
  std::wstring::_Tidy_deallocate(v119);
  std::wstring::wstring(v119, L"Tenant Details");
  DsrCmdStatusHelper::GetDisplayHeader(v119, v142);
  std::wstring::_Tidy_deallocate(v119);
  std::wstring::wstring(v119, L"User State");
  DsrCmdStatusHelper::GetDisplayHeader(v119, v140);
  std::wstring::_Tidy_deallocate(v119);
  std::wstring::wstring(v119, L"SSO State");
  DsrCmdStatusHelper::GetDisplayHeader(v119, v172);
  std::wstring::_Tidy_deallocate(v119);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v3 = (const wchar_t *)Format;
    if ( v147 > 7 )
      v3 = Format[0];
    CurrentRef = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)CurrentRef + 184LL), v3);
  }
  v5 = (const wchar_t *)Format;
  if ( v147 > 7 )
    v5 = Format[0];
  wprintf(v5);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v6 = (const wchar_t *)v166;
    if ( v167 > 7 )
      v6 = v166[0];
    v7 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v7 + 184LL), v6);
  }
  v8 = (const wchar_t *)v166;
  if ( v167 > 7 )
    v8 = v166[0];
  wprintf(v8);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v9 = (const wchar_t *)v158;
    if ( v159 > 7 )
      v9 = v158[0];
    v10 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v10 + 184LL), v9);
  }
  v11 = (const wchar_t *)v158;
  if ( v159 > 7 )
    v11 = v158[0];
  wprintf(v11);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v12 = (const wchar_t *)v136;
    if ( v137 > 7 )
      v12 = v136[0];
    v13 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v13 + 184LL), v12);
  }
  v14 = (const wchar_t *)v136;
  if ( v137 > 7 )
    v14 = v136[0];
  wprintf(v14);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v15 = (const wchar_t *)v138;
    if ( v139 > 7 )
      v15 = v138[0];
    v16 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v16 + 184LL), v15);
  }
  v17 = (const wchar_t *)v138;
  if ( v139 > 7 )
    v17 = v138[0];
  wprintf(v17);
  if ( v102 || v103 )
  {
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v18 = (const wchar_t *)v144;
      if ( v145 > 7 )
        v18 = v144[0];
      v19 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v19 + 184LL), v18);
    }
    v20 = (const wchar_t *)v144;
    if ( v145 > 7 )
      v20 = v144[0];
    wprintf(v20);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v21 = (const wchar_t *)v164;
      if ( v165 > 7 )
        v21 = v164[0];
      v22 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v22 + 184LL), v21);
    }
    v23 = (const wchar_t *)v164;
    if ( v165 > 7 )
      v23 = v164[0];
    wprintf(v23);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v24 = (const wchar_t *)v142;
      if ( v143 > 7 )
        v24 = v142[0];
      v25 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v25 + 184LL), v24);
    }
    v26 = (const wchar_t *)v142;
    if ( v143 > 7 )
      v26 = v142[0];
    wprintf(v26);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v27 = (const wchar_t *)v162;
      if ( v163 > 7 )
        v27 = v162[0];
      v28 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v28 + 184LL), v27);
    }
    v29 = (const wchar_t *)v162;
    if ( v163 > 7 )
      v29 = v162[0];
    wprintf(v29);
  }
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v30 = (const wchar_t *)v140;
    if ( v141 > 7 )
      v30 = v140[0];
    v31 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v31 + 184LL), v30);
  }
  v32 = (const wchar_t *)v140;
  if ( v141 > 7 )
    v32 = v140[0];
  wprintf(v32);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v33 = (const wchar_t *)v168;
    if ( v169 > 7 )
      v33 = v168[0];
    v34 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v34 + 184LL), v33);
  }
  v35 = (const wchar_t *)v168;
  if ( v169 > 7 )
    v35 = v168[0];
  wprintf(v35);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v36 = (const wchar_t *)v154;
    if ( v155 > 7 )
      v36 = v154[0];
    v37 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v37 + 184LL), v36);
  }
  v38 = (const wchar_t *)v154;
  if ( v155 > 7 )
    v38 = v154[0];
  wprintf(v38);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v39 = (const wchar_t *)v156;
    if ( v157 > 7 )
      v39 = v156[0];
    v40 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v40 + 184LL), v39);
  }
  v41 = (const wchar_t *)v156;
  if ( v157 > 7 )
    v41 = v156[0];
  wprintf(v41);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v42 = (const wchar_t *)v172;
    if ( v173 > 7 )
      v42 = v172[0];
    v43 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v43 + 184LL), v42);
  }
  v44 = (const wchar_t *)v172;
  if ( v173 > 7 )
    v44 = v172[0];
  wprintf(v44);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v45 = (const wchar_t *)v148;
    if ( v149 > 7 )
      v45 = v148[0];
    v46 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v46 + 184LL), v45);
  }
  v47 = (const wchar_t *)v148;
  if ( v149 > 7 )
    v47 = v148[0];
  wprintf(v47);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v48 = (const wchar_t *)v152;
    if ( v153 > 7 )
      v48 = v152[0];
    v49 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v49 + 184LL), v48);
  }
  v50 = (const wchar_t *)v152;
  if ( v153 > 7 )
    v50 = v152[0];
  wprintf(v50);
  if ( v102 || v103 )
  {
    std::wstring::wstring(v121);
    std::wstring::wstring(v119);
    std::wstring::wstring(v123, L"Diagnostic Data");
    DsrCmdStatusHelper::GetDisplayHeader(v123, v121);
    std::wstring::_Tidy_deallocate(v123);
    DsrCmdStatusHelper::GetPostJoinDiagnosticStatus(v119);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v68 = (const wchar_t *)v121;
      if ( v122 > 7 )
        v68 = v121[0];
      v69 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v69 + 184LL), v68);
    }
    v70 = (const wchar_t *)v121;
    if ( v122 > 7 )
      v70 = v121[0];
    wprintf(v70);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v71 = (const wchar_t *)v119;
      if ( v120 > 7 )
        v71 = v119[0];
      v72 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v72 + 184LL), v71);
    }
    v73 = (const wchar_t *)v119;
    if ( v120 > 7 )
      v73 = v119[0];
    wprintf(v73);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v74 = (const wchar_t *)v160;
      if ( v161 > 7 )
        v74 = v160[0];
      v75 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v75 + 184LL), v74);
    }
    v76 = (const wchar_t *)v160;
    if ( v161 > 7 )
      v76 = v160[0];
    wprintf(v76);
    if ( v126[2] )
    {
      if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
        && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
      {
        v77 = CmdOptions::GetCurrentRef();
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v77 + 184LL), L"\n");
      }
      wprintf(L"\n");
      if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
        && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
      {
        v78 = (const wchar_t *)v126;
        if ( v127 > 7 )
          v78 = v126[0];
        v79 = CmdOptions::GetCurrentRef();
        fwprintf_s(*(FILE *const *)(*(_QWORD *)v79 + 184LL), v78);
      }
      v80 = (const wchar_t *)v126;
      if ( v127 > 7 )
        v80 = v126[0];
      wprintf(v80);
    }
    std::wstring::_Tidy_deallocate(v119);
    v67 = v121;
    goto LABEL_207;
  }
  if ( v104 )
  {
    IsMember = 0;
    v107 = 0;
    std::wstring::wstring(v119);
    std::wstring::wstring(v121);
    std::wstring::wstring(lpFileName, L"Diagnostic Data");
    DsrCmdStatusHelper::GetDisplayHeader(lpFileName, v119);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v51 = (const wchar_t *)v119;
      if ( v120 > 7 )
        v51 = v119[0];
      v52 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v52 + 184LL), v51);
    }
    v53 = (const wchar_t *)v119;
    if ( v120 > 7 )
      v53 = v119[0];
    wprintf(v53);
    v54 = IsCurrentUserElevated(&IsMember);
    if ( (v54 & 0x80000000) != 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef() )
      {
        wprintf(L"Failed when trying to check if the process is running as admin. code: 0x%08x\n", v54);
        if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL) )
        {
          if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
          {
            v55 = CmdOptions::GetCurrentRef();
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v55 + 184LL),
              L"Failed when trying to check if the process is running as admin. code: 0x%08x\n",
              v54);
          }
        }
      }
      Logger::TraceInformation(L"Failed when trying to check if the process is running as admin. code: 0x%08x\n", v54);
      IsMember = 0;
    }
    VdiSettings = IsCurrentUserSystem(&v107);
    if ( (VdiSettings & 0x80000000) == 0 )
    {
      v57 = v107;
    }
    else
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef() )
      {
        wprintf(L"Failed when trying to check if the process is running as SYSTEM. code: 0x%08x\n", VdiSettings);
        if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL) )
        {
          if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
          {
            v56 = CmdOptions::GetCurrentRef();
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v56 + 184LL),
              L"Failed when trying to check if the process is running as SYSTEM. code: 0x%08x\n",
              VdiSettings);
          }
        }
      }
      Logger::TraceInformation(
        L"Failed when trying to check if the process is running as SYSTEM. code: 0x%08x\n",
        VdiSettings);
      v57 = 0;
      v107 = 0;
    }
    if ( !IsMember || v57 )
    {
      DsrCmdStatusHelper::GetPreJoinDiagnosticStatus(a1);
    }
    else
    {
      std::wstring::wstring(lpFileName, &cchOriginalDestLength);
      VdiSettings = DsrCmdStringHelper::GetDebugFilePath(lpFileName);
      if ( (VdiSettings & 0x80000000) != 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
          && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
        {
          v63 = CmdOptions::GetCurrentRef();
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v63 + 184LL),
            L"Failed to compute task output filename [0x%08x]. Exiting...\n",
            VdiSettings);
        }
        wprintf(L"Failed to compute task output filename [0x%08x]. Exiting...\n", VdiSettings);
      }
      else
      {
        v58 = lpFileName;
        if ( v125 > 7 )
          v58 = (LPCWSTR *)lpFileName[0];
        std::wstring::wstring(v123, L"Diagnostics Task");
        DsrCmdTaskSchedulerHelper::RunTask(v123, lpFileName, L"/RunSystemTests", L"/WriteToFile", v58);
        std::wstring::_Tidy_deallocate(v123);
        v59 = (const WCHAR *)lpFileName;
        if ( v125 > 7 )
          v59 = lpFileName[0];
        if ( DeleteFileW(v59) )
        {
          if ( **(_BYTE **)CmdOptions::GetCurrentRef() )
          {
            wprintf(L"Successfully deleted file %s\n", v58);
            if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL) )
            {
              if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
              {
                v60 = CmdOptions::GetCurrentRef();
                fwprintf_s(*(FILE *const *)(*(_QWORD *)v60 + 184LL), L"Successfully deleted file %s\n", v58);
              }
            }
          }
          Logger::TraceVerbose((wchar_t *)L"Successfully deleted file %s\n", v58);
        }
        else
        {
          LastError = GetLastError();
          VdiSettings = LastError;
          if ( LastError > 0 )
            VdiSettings = (unsigned __int16)LastError | 0x80070000;
          if ( **(_BYTE **)CmdOptions::GetCurrentRef() )
          {
            wprintf(L"Failed to delete file %s. code: 0x%08x.\n", v58, VdiSettings);
            if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL) )
            {
              if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
              {
                v62 = CmdOptions::GetCurrentRef();
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v62 + 184LL),
                  L"Failed to delete file %s. code: 0x%08x.\n",
                  v58,
                  VdiSettings);
              }
            }
          }
          Logger::TraceVerbose((wchar_t *)L"Failed to delete file %s. code: 0x%08x.\n", v58, VdiSettings);
        }
      }
      std::wstring::_Tidy_deallocate(lpFileName);
    }
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v64 = (const wchar_t *)v121;
      if ( v122 > 7 )
        v64 = v121[0];
      v65 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v65 + 184LL), v64);
    }
    v66 = (const wchar_t *)v121;
    if ( v122 > 7 )
      v66 = v121[0];
    wprintf(v66);
    std::wstring::_Tidy_deallocate(v121);
    v67 = v119;
LABEL_207:
    std::wstring::_Tidy_deallocate(v67);
  }
  std::wstring::wstring(v130);
  std::wstring::wstring(v128);
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v110 = 0;
  std::wstring::wstring(v123, L"IE Proxy Config for Current User");
  DsrCmdStatusHelper::GetDisplayHeader(v123, v130);
  std::wstring::_Tidy_deallocate(v123);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v81 = (const wchar_t *)v130;
    if ( v131 > 7 )
      v81 = v130[0];
    v82 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v82 + 184LL), v81);
  }
  v83 = (const wchar_t *)v130;
  if ( v131 > 7 )
    v83 = v130[0];
  wprintf(v83);
  DsrCmdStatusHelper::GetIEProxyConfig(v128, hMem);
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v84 = (const wchar_t *)v128;
    if ( v129 > 7 )
      v84 = v128[0];
    v85 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v85 + 184LL), v84);
  }
  v86 = (const wchar_t *)v128;
  if ( v129 > 7 )
    v86 = v128[0];
  wprintf(v86);
  GlobalFree(hMem[1]);
  GlobalFree(v110[0]);
  GlobalFree(v110[1]);
  std::wstring::wstring(v121);
  std::wstring::wstring(v119);
  DsrCmdStatusHelper::DisplayDefaultWinhttpProxyConfigMessage();
  if ( !v105 )
  {
    std::wstring::wstring(v123, L"Ngc Prerequisite Check");
    DsrCmdStatusHelper::GetDisplayHeader(v123, v170);
    std::wstring::_Tidy_deallocate(v123);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v87 = (const wchar_t *)v170;
      if ( v171 > 7 )
        v87 = v170[0];
      v88 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v88 + 184LL), v87);
    }
    v89 = (const wchar_t *)v170;
    if ( v171 > 7 )
      v89 = v170[0];
    wprintf(v89);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v90 = (const wchar_t *)v150;
      if ( v151 > 7 )
        v90 = v150[0];
      v91 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v91 + 184LL), v90);
    }
    v92 = (const wchar_t *)v150;
    if ( v151 > 7 )
      v92 = v150[0];
    wprintf(v92);
  }
  if ( v106[0] )
  {
    std::wstring::wstring(v123, L"Virtual Desktop Settings");
    DsrCmdStatusHelper::GetDisplayHeader(v123, v132);
    std::wstring::_Tidy_deallocate(v123);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v93 = (const wchar_t *)v132;
      if ( v133 > 7 )
        v93 = v132[0];
      v94 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v94 + 184LL), v93);
    }
    v95 = (const wchar_t *)v132;
    if ( v133 > 7 )
      v95 = v132[0];
    wprintf(v95);
    if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
      && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
    {
      v96 = (const wchar_t *)v134;
      if ( v135 > 7 )
        v96 = v134[0];
      v97 = CmdOptions::GetCurrentRef();
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v97 + 184LL), v96);
    }
    v98 = (const wchar_t *)v134;
    if ( v135 > 7 )
      v98 = v134[0];
    wprintf(v98);
  }
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v99 = CmdOptions::GetCurrentRef();
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v99 + 184LL), L"\n");
  }
  wprintf(L"\n");
  if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 12LL)
    && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef() + 184LL) )
  {
    v100 = CmdOptions::GetCurrentRef();
    fwprintf_s(
      *(FILE *const *)(*(_QWORD *)v100 + 184LL),
      L"For more information, please visit https://www.microsoft.com/aadjerrors");
  }
  wprintf(L"For more information, please visit https://www.microsoft.com/aadjerrors");
  std::wstring::_Tidy_deallocate(v119);
  std::wstring::_Tidy_deallocate(v121);
  std::wstring::_Tidy_deallocate(v128);
  std::wstring::_Tidy_deallocate(v130);
  std::wstring::_Tidy_deallocate(v132);
  std::wstring::_Tidy_deallocate(v134);
  std::wstring::_Tidy_deallocate(v136);
  std::wstring::_Tidy_deallocate(v138);
  std::wstring::_Tidy_deallocate(v170);
  std::wstring::_Tidy_deallocate(v172);
  std::wstring::_Tidy_deallocate(v140);
  std::wstring::_Tidy_deallocate(v142);
  std::wstring::_Tidy_deallocate(v144);
  std::wstring::_Tidy_deallocate(Format);
  std::wstring::_Tidy_deallocate(v148);
  std::wstring::_Tidy_deallocate(v150);
  std::wstring::_Tidy_deallocate(v152);
  std::wstring::_Tidy_deallocate(v154);
  std::wstring::_Tidy_deallocate(v156);
  std::wstring::_Tidy_deallocate(v158);
  std::wstring::_Tidy_deallocate(v126);
  std::wstring::_Tidy_deallocate(v160);
  std::wstring::_Tidy_deallocate(v162);
  std::wstring::_Tidy_deallocate(v164);
  std::wstring::_Tidy_deallocate(v166);
  std::wstring::_Tidy_deallocate(v168);
  return VdiSettings;
}

```

## disassembly

```asm
0x1800a523c  push    rbp
0x1800a523e  push    rbx
0x1800a523f  push    rsi
0x1800a5240  push    rdi
0x1800a5241  push    r14
0x1800a5243  push    r15
0x1800a5245  lea     rbp, [rsp-358h]
0x1800a524d  sub     rsp, 458h
0x1800a5254  mov     rax, cs:__security_cookie
0x1800a525b  xor     rax, rsp
0x1800a525e  mov     [rbp+380h+var_40], rax
0x1800a5265  mov     rsi, rcx
0x1800a5268  xor     r14d, r14d
0x1800a526b  mov     [rsp+480h+var_43D], r14b
0x1800a5270  movdqa  xmm0, cs:__xmm@00000003000000030000000300000003
0x1800a5278  movdqa  [rsp+480h+var_410], xmm0
0x1800a527e  movdqa  [rbp+380h+var_400], xmm0
0x1800a5283  lea     eax, [r14+3]
0x1800a5287  mov     [rbp+380h+var_3F0], eax
0x1800a528a  mov     [rbp+380h+var_3EC], eax
0x1800a528d  mov     [rbp+380h+var_3E8], eax
0x1800a5290  mov     [rbp+380h+var_3E0], r14d
0x1800a5294  mov     [rbp+380h+var_3D8], r14
0x1800a5298  mov     [rbp+380h+var_3D0], eax
0x1800a529b  mov     [rbp+380h+var_3CC], eax
0x1800a529e  mov     [rsp+480h+var_43E], r14b
0x1800a52a3  mov     [rsp+480h+var_440], r14b
0x1800a52a8  mov     [rsp+480h+var_43F], r14b
0x1800a52ad  mov     [rsp+480h+var_43C], r14b
0x1800a52b2  lea     rcx, [rbp+380h+var_A0]
0x1800a52b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52be  nop
0x1800a52bf  lea     rcx, [rbp+380h+var_C0]
0x1800a52c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52cb  nop
0x1800a52cc  lea     rcx, [rbp+380h+var_E0]
0x1800a52d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52d8  nop
0x1800a52d9  lea     rcx, [rbp+380h+var_100]
0x1800a52e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52e5  nop
0x1800a52e6  lea     rcx, [rbp+380h+var_120]
0x1800a52ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52f2  nop
0x1800a52f3  lea     rcx, [rbp+380h+var_340]
0x1800a52f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a52fc  nop
0x1800a52fd  lea     rcx, [rbp+380h+var_140]
0x1800a5304  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5309  nop
0x1800a530a  lea     rcx, [rbp+380h+var_160]
0x1800a5311  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5316  nop
0x1800a5317  lea     rcx, [rbp+380h+var_180]
0x1800a531e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5323  nop
0x1800a5324  lea     rcx, [rbp+380h+var_1A0]
0x1800a532b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5330  nop
0x1800a5331  lea     rcx, [rbp+380h+var_1C0]
0x1800a5338  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a533d  nop
0x1800a533e  lea     rcx, [rbp+380h+var_1E0]
0x1800a5345  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a534a  nop
0x1800a534b  lea     rcx, [rbp+380h+Format]
0x1800a5352  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5357  nop
0x1800a5358  lea     rcx, [rbp+380h+var_220]
0x1800a535f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5364  nop
0x1800a5365  lea     rcx, [rbp+380h+var_240]
0x1800a536c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5371  nop
0x1800a5372  lea     rcx, [rbp+380h+var_260]
0x1800a5379  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a537e  nop
0x1800a537f  lea     rcx, [rbp+380h+var_60]
0x1800a5386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a538b  nop
0x1800a538c  lea     rcx, [rbp+380h+var_80]
0x1800a5393  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5398  nop
0x1800a5399  lea     rcx, [rbp+380h+var_280]
0x1800a53a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a53a5  nop
0x1800a53a6  lea     rcx, [rbp+380h+var_2A0]
0x1800a53ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a53b2  nop
0x1800a53b3  lea     rcx, [rbp+380h+var_2C0]
0x1800a53ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a53bf  nop
0x1800a53c0  lea     rcx, [rbp+380h+var_2E0]
0x1800a53c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a53cc  nop
0x1800a53cd  lea     rax, [rsp+480h+var_43F]
0x1800a53d2  mov     [rsp+480h+var_450], rax
0x1800a53d7  lea     rax, [rsp+480h+var_440]
0x1800a53dc  mov     [rsp+480h+var_458], rax
0x1800a53e1  lea     rax, [rbp+380h+var_340]
0x1800a53e5  mov     [rsp+480h+var_460], rax
0x1800a53ea  lea     r9, [rbp+380h+var_120]
0x1800a53f1  lea     r8, [rbp+380h+var_100]
0x1800a53f8  lea     rdx, [rbp+380h+var_E0]
0x1800a53ff  lea     rcx, [rbp+380h+var_C0]
0x1800a5406  call    ?GetStatusAadJoin@DsrCmdStatusHelper@@SAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0000AEA_N1@Z; DsrCmdStatusHelper::GetStatusAadJoin(std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,bool &,bool &)
0x1800a540b  lea     rdx, [rsp+480h+var_43E]
0x1800a5410  lea     rcx, [rbp+380h+var_140]
0x1800a5417  call    ?GetStatusDomainJoin@DsrCmdStatusHelper@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; DsrCmdStatusHelper::GetStatusDomainJoin(std::wstring &,bool &)
0x1800a541c  lea     rcx, [rbp+380h+var_160]
0x1800a5423  call    ?GetStatusWamDefault@DsrCmdStatusHelper@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DsrCmdStatusHelper::GetStatusWamDefault(std::wstring &)
0x1800a5428  lea     rdx, [rbp+380h+var_1A0]
0x1800a542f  lea     rcx, [rbp+380h+var_180]
0x1800a5436  call    ?GetStatusWorkplaceJoin@DsrCmdStatusHelper@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; DsrCmdStatusHelper::GetStatusWorkplaceJoin(std::wstring &,std::wstring &)
0x1800a543b  lea     rcx, [rbp+380h+var_280]
0x1800a5442  call    ?GetDeviceName@DsrCmdStatusHelper@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DsrCmdStatusHelper::GetDeviceName(std::wstring &)
0x1800a5447  lea     rdx, [rsp+480h+var_43D]
0x1800a544c  lea     rcx, [rbp+380h+var_A0]
0x1800a5453  call    ?GetStatusNgcSet@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; DsrCmdStatusHelper::GetStatusNgcSet(std::wstring &,bool &)
0x1800a5458  lea     rdx, [rsp+480h+var_410]
0x1800a545d  lea     rcx, [rbp+380h+var_1C0]
0x1800a5464  call    ?GetStatusNgcPreReq@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_NgcPolicyCheckResult@@@Z; DsrCmdStatusHelper::GetStatusNgcPreReq(std::wstring &,_NgcPolicyCheckResult &)
0x1800a5469  lea     rcx, [rbp+380h+var_1E0]
0x1800a5470  call    ?GetStatusPrtInfo@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DsrCmdStatusHelper::GetStatusPrtInfo(std::wstring &)
0x1800a5475  lea     r8, [rsp+480h+var_43C]
0x1800a547a  lea     rdx, [rbp+380h+var_2C0]
0x1800a5481  lea     rcx, [rbp+380h+var_2A0]
0x1800a5488  call    ?GetVdiSettings@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEA_N@Z; DsrCmdStatusHelper::GetVdiSettings(std::wstring &,std::wstring &,bool &)
0x1800a548d  mov     edi, eax
0x1800a548f  lea     rdx, aDeviceState; "Device State"
0x1800a5496  lea     rcx, [rbp+380h+var_3C0]
0x1800a549a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a549f  nop
0x1800a54a0  lea     rdx, [rbp+380h+Format]
0x1800a54a7  lea     rcx, [rbp+380h+var_3C0]
0x1800a54ab  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x1800a54b0  nop
0x1800a54b1  lea     rcx, [rbp+380h+var_3C0]
0x1800a54b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a54ba  lea     rdx, aDeviceDetails; "Device Details"
0x1800a54c1  lea     rcx, [rbp+380h+var_3C0]
0x1800a54c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a54ca  nop
0x1800a54cb  lea     rdx, [rbp+380h+var_220]
0x1800a54d2  lea     rcx, [rbp+380h+var_3C0]
0x1800a54d6  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x1800a54db  nop
0x1800a54dc  lea     rcx, [rbp+380h+var_3C0]
0x1800a54e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a54e5  lea     rdx, aTenantDetails; "Tenant Details"
0x1800a54ec  lea     rcx, [rbp+380h+var_3C0]
0x1800a54f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a54f5  nop
0x1800a54f6  lea     rdx, [rbp+380h+var_240]
0x1800a54fd  lea     rcx, [rbp+380h+var_3C0]
0x1800a5501  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x1800a5506  nop
0x1800a5507  lea     rcx, [rbp+380h+var_3C0]
0x1800a550b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5510  lea     rdx, aUserState; "User State"
0x1800a5517  lea     rcx, [rbp+380h+var_3C0]
0x1800a551b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a5520  nop
0x1800a5521  lea     rdx, [rbp+380h+var_260]
0x1800a5528  lea     rcx, [rbp+380h+var_3C0]
0x1800a552c  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x1800a5531  nop
0x1800a5532  lea     rcx, [rbp+380h+var_3C0]
0x1800a5536  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a553b  lea     rdx, aSsoState; "SSO State"
0x1800a5542  lea     rcx, [rbp+380h+var_3C0]
0x1800a5546  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a554b  nop
0x1800a554c  lea     rdx, [rbp+380h+var_60]
0x1800a5553  lea     rcx, [rbp+380h+var_3C0]
0x1800a5557  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x1800a555c  nop
0x1800a555d  lea     rcx, [rbp+380h+var_3C0]
0x1800a5561  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5566  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a556b  mov     rcx, [rax]
0x1800a556e  lea     r15d, [r14+7]
0x1800a5572  cmp     [rcx+0Ch], r14b
0x1800a5576  jz      short loc_1800A55B6
0x1800a5578  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a557d  mov     rcx, [rax]
0x1800a5580  cmp     [rcx+0B8h], r14
0x1800a5587  jz      short loc_1800A55B6
0x1800a5589  lea     rbx, [rbp+380h+Format]
0x1800a5590  cmp     [rbp+380h+var_1E8], r15
0x1800a5597  cmova   rbx, [rbp+380h+Format]
0x1800a559f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a55a4  mov     rcx, [rax]
0x1800a55a7  mov     rdx, rbx; Format
0x1800a55aa  mov     rcx, [rcx+0B8h]; Stream
0x1800a55b1  call    fwprintf_s
0x1800a55b6  lea     rcx, [rbp+380h+Format]
0x1800a55bd  cmp     [rbp+380h+var_1E8], r15
0x1800a55c4  cmova   rcx, [rbp+380h+Format]; Format
0x1800a55cc  call    wprintf
0x1800a55d1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a55d6  mov     rcx, [rax]
0x1800a55d9  cmp     [rcx+0Ch], r14b
0x1800a55dd  jz      short loc_1800A561D
0x1800a55df  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a55e4  mov     rcx, [rax]
0x1800a55e7  cmp     [rcx+0B8h], r14
0x1800a55ee  jz      short loc_1800A561D
0x1800a55f0  lea     rbx, [rbp+380h+var_C0]
0x1800a55f7  cmp     [rbp+380h+var_A8], r15
0x1800a55fe  cmova   rbx, [rbp+380h+var_C0]
0x1800a5606  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a560b  mov     rcx, [rax]
0x1800a560e  mov     rdx, rbx; Format
0x1800a5611  mov     rcx, [rcx+0B8h]; Stream
0x1800a5618  call    fwprintf_s
0x1800a561d  lea     rcx, [rbp+380h+var_C0]
0x1800a5624  cmp     [rbp+380h+var_A8], r15
0x1800a562b  cmova   rcx, [rbp+380h+var_C0]; Format
0x1800a5633  call    wprintf
0x1800a5638  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a563d  mov     rcx, [rax]
0x1800a5640  cmp     [rcx+0Ch], r14b
0x1800a5644  jz      short loc_1800A5684
0x1800a5646  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a564b  mov     rcx, [rax]
0x1800a564e  cmp     [rcx+0B8h], r14
0x1800a5655  jz      short loc_1800A5684
0x1800a5657  lea     rbx, [rbp+380h+var_140]
0x1800a565e  cmp     [rbp+380h+var_128], r15
0x1800a5665  cmova   rbx, [rbp+380h+var_140]
0x1800a566d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a5672  mov     rcx, [rax]
0x1800a5675  mov     rdx, rbx; Format
0x1800a5678  mov     rcx, [rcx+0B8h]; Stream
0x1800a567f  call    fwprintf_s
0x1800a5684  lea     rcx, [rbp+380h+var_140]
0x1800a568b  cmp     [rbp+380h+var_128], r15
0x1800a5692  cmova   rcx, [rbp+380h+var_140]; Format
0x1800a569a  call    wprintf
0x1800a569f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a56a4  mov     rcx, [rax]
0x1800a56a7  cmp     [rcx+0Ch], r14b
0x1800a56ab  jz      short loc_1800A56EB
0x1800a56ad  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a56b2  mov     rcx, [rax]
0x1800a56b5  cmp     [rcx+0B8h], r14
0x1800a56bc  jz      short loc_1800A56EB
0x1800a56be  lea     rbx, [rbp+380h+var_2A0]
0x1800a56c5  cmp     [rbp+380h+var_288], r15
0x1800a56cc  cmova   rbx, [rbp+380h+var_2A0]
0x1800a56d4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a56d9  mov     rcx, [rax]
0x1800a56dc  mov     rdx, rbx; Format
0x1800a56df  mov     rcx, [rcx+0B8h]; Stream
0x1800a56e6  call    fwprintf_s
0x1800a56eb  lea     rcx, [rbp+380h+var_2A0]
0x1800a56f2  cmp     [rbp+380h+var_288], r15
0x1800a56f9  cmova   rcx, [rbp+380h+var_2A0]; Format
0x1800a5701  call    wprintf
0x1800a5706  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a570b  mov     rcx, [rax]
0x1800a570e  cmp     [rcx+0Ch], r14b
0x1800a5712  jz      short loc_1800A5752
0x1800a5714  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a5719  mov     rcx, [rax]
0x1800a571c  cmp     [rcx+0B8h], r14
0x1800a5723  jz      short loc_1800A5752
0x1800a5725  lea     rbx, [rbp+380h+var_280]
0x1800a572c  cmp     [rbp+380h+var_268], r15
0x1800a5733  cmova   rbx, [rbp+380h+var_280]
0x1800a573b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a5740  mov     rcx, [rax]
0x1800a5743  mov     rdx, rbx; Format
0x1800a5746  mov     rcx, [rcx+0B8h]; Stream
0x1800a574d  call    fwprintf_s
0x1800a5752  lea     rcx, [rbp+380h+var_280]
0x1800a5759  cmp     [rbp+380h+var_268], r15
0x1800a5760  cmova   rcx, [rbp+380h+var_280]; Format
0x1800a5768  call    wprintf
0x1800a576d  cmp     [rsp+480h+var_440], r14b
0x1800a5772  jnz     short loc_1800A577F
0x1800a5774  cmp     [rsp+480h+var_43F], r14b
0x1800a5779  jz      loc_1800A591B
0x1800a577f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a5784  mov     rcx, [rax]
0x1800a5787  cmp     [rcx+0Ch], r14b
0x1800a578b  jz      short loc_1800A57CB
0x1800a578d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a5792  mov     rcx, [rax]
0x1800a5795  cmp     [rcx+0B8h], r14
0x1800a579c  jz      short loc_1800A57CB
0x1800a579e  lea     rbx, [rbp+380h+var_220]
0x1800a57a5  cmp     [rbp+380h+var_208], r15
0x1800a57ac  cmova   rbx, [rbp+380h+var_220]
0x1800a57b4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800a57b9  mov     rcx, [rax]
0x1800a57bc  mov     rdx, rbx; Format
0x1800a57bf  mov     rcx, [rcx+0B8h]; Stream
0x1800a57c6  call    fwprintf_s
  ... truncated ...
```
