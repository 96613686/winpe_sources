# MergeSdbpGatherStoreAppFiles(bool)

- ea: `0x180043424`
- end: `0x180045135`
- name: `?MergeSdbpGatherStoreAppFiles@@YAK_N@Z`
- size: `7441`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180042fa0`

## callees

- `0x1800055b8`
- `0x180007020`
- `0x18000a750`
- `0x18000b6f0`
- `0x18000c560`
- `0x18000dc08`
- `0x180012920`
- `0x1800139b4`
- `0x180020cd0`
- `0x1800211f8`
- `0x1800212b0`
- `0x1800310a8`
- `0x1800312d0`
- `0x18003530c`
- `0x18003c26c`
- `0x18003ccf8`
- `0x18003d910`
- `0x18003d988`
- `0x18003de84`
- `0x18003e1ac`
- `0x180043424`
- `0x18004513c`
- `0x18004cfa4`
- `0x18004d0f0`
- `0x18004d110`
- `0x1800538d0`
- `0x18007aa17`
- `0x180080038`
- `0x180096d58`
- `0x18009729c`
- `0x1800976c4`
- `0x180097a30`
- `0x180097e24`
- `0x1800e3f84`
- `0x1800e40b0`
- `0x1800e4254`
- `0x1800ee04c`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043828`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043828`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004447a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044d7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044dc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044e67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004447a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044d7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044dc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044e67`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044e20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800444db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044e20`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800441c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800442fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800445d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044a31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800441c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800442fd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800445d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044a31`
- `api-ms-win-core-processthreads-l1-1-7!GetMachineTypeAttributes` at `0x180043790`
- `api-ms-win-core-processthreads-l1-1-7!GetMachineTypeAttributes` at `0x180043790`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800439b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a09`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a99`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800439b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a09`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180043a99`

## string_xrefs

- `0x1800441df`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044313`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x1800445ef`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044a47`: `Failed to create and expand sdbinst.exe path (%d)`
- `0x180044443`: `RegSetValueExW failed (%d)`
- `0x18004448e`: `RegSetValueExW failed (%d)`
- `0x180044d8f`: `RegSetValueExW failed (%d)`
- `0x180044dd6`: `RegSetValueExW failed (%d)`
- `0x180044e77`: `RegSetValueExW failed (%d)`
- `0x180043838`: `RegOpenKeyExW failed (%d)`
- `0x180043873`: `MergeSdbpGetStoreAppInstallDirectory failed (%d)`
- `0x180043ac9`: `Failed to extract sys update sdb data (%d)`
- `0x180043b20`: `MergeSdbpGetStoreAppDllsForArch failed (%d)`
- `0x180043939`: `MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)`
- `0x180043bac`: `MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)`
- `0x180043965`: `ApplicationCompatibilityEnhancements.cat`
- `0x1800439be`: `msiMergeInboxStoreApp.sdb`
- `0x180043a38`: `Failed to extract msi update sdb data (%d)`
- `0x180044170`: `%ls\system32\sdbinst.exe%ls -u -g %ls`
- `0x180044593`: `%ls\system32\sdbinst.exe%ls -u -g %ls`
- `0x18004420e`: `Failed to remove installed merge db (%d)`
- `0x18004461f`: `Failed to remove installed merge db (%d)`
- `0x180043ea3`: `SdbGetPluginDll failed (%d)`
- `0x1800440b6`: `MergeSdbpCompareDlls failed (%d)`
- `0x1800449e9`: `MergeSdbpCompareDlls failed (%d)`
- `0x180044343`: `Failed to install merge db (%d)`
- `0x180044a77`: `Failed to install merge db (%d)`
- `0x18004438d`: `SdbInst.exe ran successfully for msi update/add: %d`
- `0x1800444be`: `RegDeleteValueW failed (%d)`
- `0x1800444ef`: `RegDeleteValueW failed (%d)`
- `0x180044e03`: `RegDeleteValueW failed (%d)`
- `0x180044e30`: `RegDeleteValueW failed (%d)`
- `0x180044254`: `SdbInst.exe ran successfully for msi removal: %d`
- `0x1800442b7`: `%ls\system32\sdbinst.exe%ls%ls "%ls"`
- `0x18004493f`: `%ls\system32\sdbinst.exe%ls%ls "%ls"`
- `0x180044ced`: `SdbInst.exe ran successfully for sys update/add: %d`
- `0x180044bc7`: `SdbRemovePluginDll failed, swallowing (%d)`
- `0x18004497c`: `MergeSdbpSetInstalledShimDlls failed (%d)`
- `0x180044d2a`: `MergeSdbpSetInstalledShimDlls failed (%d)`
- `0x1800448c4`: `SdbAddPluginDll failed, swallowing (%d)`
- `0x1800438ee`: `SAIDMSI`
- `0x180044428`: `SAIDMSI`
- `0x1800444a0`: `SAIDMSI`
- `0x18004381a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1800438e2`: `SATMSI`
- `0x18004446f`: `SATMSI`
- `0x1800444d0`: `SATMSI`

## pseudocode

```c
__int64 __fastcall MergeSdbpGatherStoreAppFiles(char a1)
{
  char v1; // r15
  struct _GUID v2; // xmm7
  struct _GUID v3; // xmm6
  unsigned __int64 i; // rbx
  int MachineTypeAttributes; // eax
  int v6; // eax
  unsigned int StoreAppInstallDirectory; // ebx
  const char *v8; // r9
  int v9; // r8d
  unsigned __int64 RegistryQWORD; // rax
  char v11; // r13
  char v12; // r12
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned __int64 j; // rbx
  unsigned int StoreAppDllsForArch; // esi
  unsigned __int8 **v18; // r8
  unsigned int *v19; // r9
  const char *v20; // r9
  int v21; // r8d
  unsigned __int64 k; // rsi
  const unsigned __int16 *v23; // rdx
  unsigned int RegistryMULTISTRING; // eax
  ULONGLONG *v25; // r14
  int v26; // eax
  ULONGLONG v27; // rbx
  _QWORD *v28; // r9
  _QWORD *v29; // rax
  int PluginDll; // eax
  int v31; // eax
  bool v32; // al
  __int64 v33; // rbx
  ULONGLONG *v34; // r14
  ULONGLONG v35; // rax
  ULONGLONG v36; // rdi
  const unsigned __int16 **v37; // r8
  const unsigned __int16 **v38; // r11
  const char *v39; // r9
  int v40; // r8d
  const char *v41; // r9
  int v42; // r8d
  char v43; // si
  __int64 v44; // r14
  ULONGLONG *v45; // r12
  ULONGLONG v46; // rdi
  const unsigned __int16 **v47; // rdx
  const unsigned __int16 **v48; // r11
  ULONGLONG v49; // r10
  RtlStringArray *v50; // r9
  const unsigned __int16 **v51; // rdx
  __int64 v52; // r9
  const unsigned __int16 **v53; // r11
  const unsigned __int16 *v54; // r11
  __int64 v55; // r9
  const unsigned __int16 **v56; // rax
  __int64 v57; // r9
  unsigned int RegistryDWORD; // r14d
  const wchar_t *v59; // rcx
  int v60; // eax
  DWORD v61; // eax
  unsigned __int64 v62; // r8
  const wchar_t *v63; // rcx
  const wchar_t *v64; // rax
  int v65; // eax
  DWORD v66; // eax
  unsigned __int64 v67; // r8
  int v68; // eax
  __int64 v69; // rax
  const wchar_t *v70; // rcx
  int v71; // eax
  DWORD v72; // eax
  unsigned __int64 v73; // r8
  __int64 v74; // rbx
  void *v75; // rdx
  int v76; // eax
  int v77; // eax
  unsigned __int64 m; // r15
  ULONGLONG *v79; // r12
  ULONGLONG v80; // rbx
  const unsigned __int16 **v81; // rdx
  ULONGLONG v82; // r10
  RtlStringArray *v83; // r9
  const unsigned __int16 **v84; // rdx
  __int64 v85; // r9
  const unsigned __int16 *v86; // r11
  __int64 v87; // r9
  const unsigned __int16 **v88; // rax
  __int64 v89; // r9
  unsigned int v90; // r14d
  RtlStringArray *v91; // r9
  LPCWSTR *v92; // rax
  __int64 v93; // r9
  int v94; // eax
  const wchar_t *v95; // rcx
  const wchar_t *v96; // rax
  int v97; // eax
  int v98; // r8d
  DWORD v99; // eax
  unsigned __int64 v100; // r8
  char v101; // r14
  __int64 v102; // r15
  int v103; // eax
  ULONGLONG *v104; // r12
  ULONGLONG v105; // rsi
  const unsigned __int16 **v106; // rdx
  _QWORD *v107; // rax
  int v108; // eax
  const unsigned __int16 **v109; // rdx
  int v110; // eax
  unsigned __int64 n; // rbx
  int v112; // eax
  __int64 v113; // rax
  WCHAR *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v116; // [rsp+50h] [rbp-B0h] BYREF
  char v117; // [rsp+54h] [rbp-ACh]
  bool v118; // [rsp+55h] [rbp-ABh] BYREF
  unsigned __int16 *v119; // [rsp+58h] [rbp-A8h] BYREF
  char v120; // [rsp+60h] [rbp-A0h]
  char v121; // [rsp+61h] [rbp-9Fh]
  char v122; // [rsp+62h] [rbp-9Eh]
  _BYTE v123[13]; // [rsp+63h] [rbp-9Dh] BYREF
  bool v124; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v125[2]; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  ULONGLONG v127[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v128[2]; // [rsp+B0h] [rbp-50h] BYREF
  ULONGLONG pullResult; // [rsp+B8h] [rbp-48h] BYREF
  int v130; // [rsp+C0h] [rbp-40h] BYREF
  BYTE v131[8]; // [rsp+C8h] [rbp-38h] BYREF
  BYTE v132[8]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE v133[8]; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID Buf2; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v135; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v136; // [rsp+100h] [rbp+0h]
  _BYTE v137[8]; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v138; // [rsp+110h] [rbp+10h]
  _WORD v139[4]; // [rsp+118h] [rbp+18h]
  RtlStringArray *v140; // [rsp+120h] [rbp+20h]
  RtlStringArray *v141; // [rsp+128h] [rbp+28h]
  RtlStringArray *v142; // [rsp+130h] [rbp+30h]
  struct RtlStringArray *v143; // [rsp+138h] [rbp+38h]
  RtlStringArray *v144[2]; // [rsp+140h] [rbp+40h]
  char v145; // [rsp+150h] [rbp+50h]
  char *v146; // [rsp+158h] [rbp+58h]
  __int16 v147; // [rsp+160h] [rbp+60h]
  _BYTE *v148; // [rsp+168h] [rbp+68h]
  _BYTE *v149; // [rsp+170h] [rbp+70h]
  _BYTE *v150; // [rsp+178h] [rbp+78h]
  _BYTE *v151; // [rsp+180h] [rbp+80h]
  _BYTE *v152; // [rsp+188h] [rbp+88h]
  const wchar_t *v153; // [rsp+190h] [rbp+90h]
  char v154; // [rsp+198h] [rbp+98h]
  char *v155; // [rsp+1A0h] [rbp+A0h]
  __int16 v156; // [rsp+1A8h] [rbp+A8h]
  _BYTE *v157; // [rsp+1B0h] [rbp+B0h]
  _BYTE *v158; // [rsp+1B8h] [rbp+B8h]
  _BYTE *v159; // [rsp+1C0h] [rbp+C0h]
  _BYTE *v160; // [rsp+1C8h] [rbp+C8h]
  _BYTE *v161; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v162; // [rsp+1D8h] [rbp+D8h]
  char v163; // [rsp+1E0h] [rbp+E0h]
  char *v164; // [rsp+1E8h] [rbp+E8h]
  __int16 v165; // [rsp+1F0h] [rbp+F0h]
  _BYTE *v166; // [rsp+1F8h] [rbp+F8h]
  _BYTE *v167; // [rsp+200h] [rbp+100h]
  _BYTE *v168; // [rsp+208h] [rbp+108h]
  _BYTE *v169; // [rsp+210h] [rbp+110h]
  _BYTE *v170; // [rsp+218h] [rbp+118h]
  _BYTE v171[56]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v172[56]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v173[56]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v174[56]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v175[56]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v176[56]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v177[56]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v178[56]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v179[56]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v180[56]; // [rsp+418h] [rbp+318h] BYREF
  _BYTE v181[56]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v182[56]; // [rsp+488h] [rbp+388h] BYREF
  _BYTE v183[56]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v184[56]; // [rsp+4F8h] [rbp+3F8h] BYREF
  _BYTE v185[56]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v186[56]; // [rsp+568h] [rbp+468h] BYREF
  _BYTE v187[56]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v188[56]; // [rsp+5D8h] [rbp+4D8h] BYREF
  _BYTE v189[56]; // [rsp+610h] [rbp+510h] BYREF
  _BYTE v190[56]; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v191[56]; // [rsp+680h] [rbp+580h] BYREF
  GUID Buf1; // [rsp+6B8h] [rbp+5B8h] BYREF
  GUID Guid; // [rsp+6C8h] [rbp+5C8h] BYREF
  char v194; // [rsp+6D8h] [rbp+5D8h] BYREF
  char v195; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v196; // [rsp+708h] [rbp+608h] BYREF
  char v197; // [rsp+720h] [rbp+620h] BYREF
  _WORD Data[40]; // [rsp+740h] [rbp+640h] BYREF
  _WORD v199[40]; // [rsp+790h] [rbp+690h] BYREF
  unsigned __int16 v200[264]; // [rsp+7E0h] [rbp+6E0h] BYREF
  WCHAR v201[264]; // [rsp+9F0h] [rbp+8F0h] BYREF
  WCHAR Dst[264]; // [rsp+C00h] [rbp+B00h] BYREF
  WCHAR v203[264]; // [rsp+E10h] [rbp+D10h] BYREF
  WCHAR v204[264]; // [rsp+1020h] [rbp+F20h] BYREF
  WCHAR pszPath[264]; // [rsp+1230h] [rbp+1130h] BYREF
  WCHAR Src[264]; // [rsp+1440h] [rbp+1340h] BYREF
  WCHAR v207[264]; // [rsp+1650h] [rbp+1550h] BYREF
  WCHAR FileName[264]; // [rsp+1860h] [rbp+1760h] BYREF

  v122 = a1;
  v1 = 0;
  v116 = 0;
  hKey[0] = 0;
  Guid = 0;
  Buf1 = 0;
  RtlStringArray::RtlStringArray((RtlStringArray *)v176);
  RtlStringArray::RtlStringArray((RtlStringArray *)v175);
  RtlStringArray::RtlStringArray((RtlStringArray *)v174);
  RtlStringArray::RtlStringArray((RtlStringArray *)v172);
  RtlStringArray::RtlStringArray((RtlStringArray *)v191);
  RtlStringArray::RtlStringArray((RtlStringArray *)v190);
  RtlStringArray::RtlStringArray((RtlStringArray *)v189);
  RtlStringArray::RtlStringArray((RtlStringArray *)v188);
  RtlStringArray::RtlStringArray((RtlStringArray *)v187);
  RtlStringArray::RtlStringArray((RtlStringArray *)v186);
  RtlStringArray::RtlStringArray((RtlStringArray *)v185);
  RtlStringArray::RtlStringArray((RtlStringArray *)v178);
  RtlStringArray::RtlStringArray((RtlStringArray *)v184);
  RtlStringArray::RtlStringArray((RtlStringArray *)v183);
  RtlStringArray::RtlStringArray((RtlStringArray *)v182);
  RtlStringArray::RtlStringArray((RtlStringArray *)v181);
  RtlStringArray::RtlStringArray((RtlStringArray *)v180);
  RtlStringArray::RtlStringArray((RtlStringArray *)v179);
  RtlStringArray::RtlStringArray((RtlStringArray *)v173);
  RtlStringArray::RtlStringArray((RtlStringArray *)v177);
  *(_WORD *)v123 = 0;
  *(_QWORD *)v131 = 0;
  *(_QWORD *)v132 = 0;
  *(_QWORD *)v128 = 0;
  *(_QWORD *)&v123[5] = 0;
  v2 = 0;
  v135 = 0;
  v3 = 0;
  Buf2 = 0;
  Guid = 0;
  Buf1 = 0;
  v136 = L"X86";
  v137[0] = 0;
  v138 = (unsigned __int16 *)&v194;
  v139[0] = 332;
  v140 = (RtlStringArray *)v176;
  v141 = (RtlStringArray *)v191;
  v142 = (RtlStringArray *)v187;
  v143 = (struct RtlStringArray *)v184;
  v144[0] = (RtlStringArray *)v180;
  v144[1] = (RtlStringArray *)L"AMD64";
  v145 = 0;
  v146 = &v195;
  v147 = -31132;
  v148 = v175;
  v149 = v190;
  v150 = v186;
  v151 = v183;
  v152 = v179;
  v153 = L"ARM";
  v154 = 0;
  v155 = &v196;
  v156 = 452;
  v157 = v174;
  v158 = v189;
  v159 = v185;
  v160 = v182;
  v161 = v173;
  v162 = L"ARM64";
  v163 = 0;
  v164 = &v197;
  v165 = -21916;
  v166 = v172;
  v167 = v188;
  v168 = v178;
  v169 = v181;
  v170 = v177;
  for ( i = 0; i < 4; ++i )
  {
    v130 = 0;
    MachineTypeAttributes = GetMachineTypeAttributes((unsigned __int16)v139[36 * i], &v130);
    if ( PcaFailedHr(&v116, MachineTypeAttributes) )
    {
      v8 = "GetMachineTypeAttributes failed (%d)";
      v9 = 1576;
      goto LABEL_296;
    }
    if ( (v130 & 1) != 0 )
      v137[72 * i] = 1;
    v6 = StringCchPrintfW(
           *(unsigned __int16 **)&v139[36 * i - 4],
           0xBu,
           L"%ls%ls",
           L"SACD_",
           *(_QWORD *)&v137[72 * i - 8]);
    if ( PcaFailedHr(&v116, v6) )
    {
      v9 = 1589;
LABEL_294:
      v8 = "StringCchPrintfW failed (%d)";
LABEL_296:
      StoreAppInstallDirectory = v116;
LABEL_297:
      AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v9, (_DWORD)v8);
      goto LABEL_298;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  StoreAppInstallDirectory = RegOpenKeyExW(
                               HKEY_LOCAL_MACHINE,
                               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                               0,
                               0x2001Fu,
                               hKey);
  if ( StoreAppInstallDirectory )
  {
    v8 = "RegOpenKeyExW failed (%d)";
    v9 = 1595;
    goto LABEL_297;
  }
  *(_QWORD *)v133 = 0;
  StoreAppInstallDirectory = MergeSdbpGetStoreAppInstallDirectory(v200, 0x104u, (unsigned __int64 *)v133);
  v116 = StoreAppInstallDirectory;
  if ( StoreAppInstallDirectory )
  {
    v8 = "MergeSdbpGetStoreAppInstallDirectory failed (%d)";
    v9 = 1607;
    goto LABEL_297;
  }
  RegistryQWORD = PcaUtilityGetRegistryQWORD(hKey[0], 0, L"SAV", 0xFFFFFFFFFFFFFFFFuLL);
  if ( *(_QWORD *)v133 == RegistryQWORD )
    goto LABEL_292;
  v11 = 0;
  v12 = 0;
  v121 = 0;
  if ( v200[0] )
  {
    v13 = StringCchPrintfW(pszPath, 0x104u, L"%ls\\%ls", v200, L"ApplicationCompatibilityEnhancements.cat");
    if ( PcaFailedHr(&v116, v13) )
    {
      v9 = 1638;
      goto LABEL_294;
    }
    if ( PathFileExistsW(pszPath) )
    {
      v14 = StringCchPrintfW(v201, 0x104u, L"%ls\\sdb\\%ls", v200, L"msiMergeInboxStoreApp.sdb");
      if ( PcaFailedHr(&v116, v14) )
      {
        v9 = 1649;
        goto LABEL_294;
      }
      if ( PathFileExistsW(v201) )
      {
        v11 = 1;
        StoreAppInstallDirectory = MergeSdbpExtractGuidAndTimestampFromSdb(v201, &Buf2, (unsigned __int64 *)v131);
        v116 = StoreAppInstallDirectory;
        if ( StoreAppInstallDirectory )
        {
          v8 = "Failed to extract msi update sdb data (%d)";
          v9 = 1657;
          goto LABEL_297;
        }
        v3 = Buf2;
      }
      v15 = StringCchPrintfW(v203, 0x104u, L"%ls\\sdb\\%ls", v200, L"sysMergeInboxStoreApp.sdb");
      if ( PcaFailedHr(&v116, v15) )
      {
        v9 = 1664;
        goto LABEL_294;
      }
      if ( PathFileExistsW(v203) )
      {
        v12 = 1;
        v121 = 1;
        StoreAppInstallDirectory = MergeSdbpExtractGuidAndTimestampFromSdb(v203, &v135, (unsigned __int64 *)v132);
        if ( StoreAppInstallDirectory )
        {
          v8 = "Failed to extract sys update sdb data (%d)";
          v9 = 1672;
          goto LABEL_297;
        }
        v2 = v135;
      }
      for ( j = 0; j < 4; ++j )
      {
        if ( v137[72 * j] )
        {
          StoreAppDllsForArch = MergeSdbpGetStoreAppDllsForArch(
                                  *(const unsigned __int16 **)&v137[72 * j - 8],
                                  v200,
                                  *(&v141 + 9 * j),
                                  v144[9 * j - 1]);
          if ( StoreAppDllsForArch )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              1686,
              (unsigned int)"MergeSdbpGetStoreAppDllsForArch failed (%d)");
            goto LABEL_38;
          }
        }
      }
      goto LABEL_14;
    }
LABEL_292:
    StoreAppInstallDirectory = 0;
    goto LABEL_298;
  }
  v201[0] = 0;
  v203[0] = 0;
LABEL_14:
  v119 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&v119);
  *(struct _GUID *)v125 = v3;
  StoreAppInstallDirectory = MergeSdbpGetSdbGuidAndTimestampFromRegistry(
                               hKey[0],
                               &v119,
                               &Buf1,
                               (__int64)v123,
                               (__int64)v125,
                               v11,
                               L"SAIDMSI",
                               L"SATMSI");
  if ( StoreAppInstallDirectory )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      1708,
      (unsigned int)"MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)");
    goto LABEL_16;
  }
  v125[0] = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(v125);
  *(struct _GUID *)v127 = v2;
  StoreAppInstallDirectory = MergeSdbpGetSdbGuidAndTimestampFromRegistry(
                               hKey[0],
                               v125,
                               &Guid,
                               (__int64)&v123[1],
                               (__int64)v127,
                               v12,
                               L"SAIDSYS",
                               L"SATSYS");
  v116 = StoreAppInstallDirectory;
  if ( StoreAppInstallDirectory )
  {
    v20 = "MergeSdbpGetSdbGuidAndTimestampFromRegistry failed (%d)";
    v21 = 1724;
    goto LABEL_41;
  }
  for ( k = 0; k < 4; ++k )
  {
    if ( !v137[72 * k] )
      continue;
    v127[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v127,
      0);
    RegistryMULTISTRING = PcaUtilityGetRegistryMULTISTRING(
                            hKey[0],
                            v23,
                            *(const unsigned __int16 **)&v139[36 * k - 4],
                            (unsigned __int16 **)v127);
    StoreAppInstallDirectory = RegistryMULTISTRING;
    v116 = RegistryMULTISTRING;
    if ( (RegistryMULTISTRING & 0xFFFFFFFC) != 0 || RegistryMULTISTRING == 1 )
    {
      v39 = "Regkey lookup failed (%d)";
      v40 = 1740;
      goto LABEL_91;
    }
    if ( !v127[0] )
      goto LABEL_61;
    v25 = (ULONGLONG *)*(&v140 + 9 * k);
    v26 = RtlStringArray::FromMultiString((RtlStringArray *)v25, (const unsigned __int16 *)v127[0]);
    if ( PcaFailedHr(&v116, v26) )
    {
      v39 = "FromMultiString failed (%d)";
      v40 = 1747;
      goto LABEL_87;
    }
    RtlStringArray::Sort((RtlStringArray *)v25);
    if ( !v25[2] )
      goto LABEL_61;
    v27 = 0;
    v28 = 0;
    do
    {
      v29 = 0;
      if ( v27 < v25[2] )
      {
        pullResult = 0;
        if ( ULongLongMult(v25[1], v27, &pullResult) < 0
          || (v29 = (_QWORD *)(v25[5] + pullResult), (unsigned __int64)v29 < v25[5]) )
        {
          v29 = v28;
        }
      }
      PluginDll = SdbGetPluginDll(*v29, (unsigned __int16)v139[36 * k], FileName, v28);
      if ( PcaFailedNt(&v116, PluginDll) )
      {
        v39 = "SdbGetPluginDll failed (%d)";
        v40 = 1759;
LABEL_87:
        StoreAppInstallDirectory = v116;
LABEL_91:
        AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v40, (_DWORD)v39);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v127);
        goto LABEL_42;
      }
      if ( !(unsigned int)AslDoesFileExistNtPath(FileName) )
      {
        RtlStringArray::Delete((RtlStringArray *)v25, v27--);
        v28 = 0;
        goto LABEL_59;
      }
      v31 = RtlStringArray::Append(*(&v142 + 9 * k), FileName, 0);
      v32 = PcaFailedHr(&v116, v31);
      v28 = 0;
      if ( v32 )
      {
        v39 = "Append failed (%d)";
        v40 = 1770;
        goto LABEL_87;
      }
LABEL_59:
      ++v27;
    }
    while ( v27 < v25[2] );
    v1 = 0;
LABEL_61:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v127);
  }
  if ( v123[0] != v11 || memcmp_0(&Buf1, &Buf2, 0x10u) || (v118 = 0, *(_QWORD *)v128 != *(_QWORD *)v131) )
    v118 = 1;
  v117 = v123[1];
  if ( v123[1] != v12 || memcmp_0(&Guid, &v135, 0x10u) || *(_QWORD *)&v123[5] != *(_QWORD *)v132 )
    v1 = 1;
  v120 = v1;
  v33 = 0;
  while ( 2 )
  {
    if ( v137[72 * v33] )
    {
      v34 = (ULONGLONG *)v144[9 * v33 - 1];
      v35 = v34[2];
      if ( v35 )
      {
        v36 = 0;
        while ( 1 )
        {
          v37 = 0;
          if ( v36 < v35 )
          {
            v127[0] = 0;
            if ( ULongLongMult(v34[1], v36, v127) < 0
              || (v37 = (const unsigned __int16 **)(v34[5] + v127[0]), (unsigned __int64)v37 < v34[5]) )
            {
              v37 = v38;
            }
          }
          StoreAppDllsForArch = MergeSdbpVerifySignatureAgainstCatalog(*v37, pszPath, (unsigned __int8 **)v37, v19);
          v116 = StoreAppDllsForArch;
          if ( StoreAppDllsForArch )
            break;
          ++v36;
          v35 = v34[2];
          if ( v36 >= v35 )
            goto LABEL_81;
        }
        v41 = "MergeSdbpVerifySignatureAgainstCatalog (%d)";
        v42 = 1798;
LABEL_93:
        AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v42, (_DWORD)v41);
        goto LABEL_94;
      }
    }
LABEL_81:
    if ( (unsigned __int64)++v33 < 4 )
      continue;
    break;
  }
  if ( v11 )
  {
    StoreAppInstallDirectory = MergeSdbpVerifySignatureAgainstCatalog(v201, pszPath, v18, v19);
    v116 = StoreAppInstallDirectory;
    if ( StoreAppInstallDirectory )
    {
      v21 = 1806;
LABEL_85:
      v20 = "MergeSdbpVerifySignatureAgainstCatalog (%d)";
      goto LABEL_41;
    }
  }
  if ( v12 )
  {
    StoreAppInstallDirectory = MergeSdbpVerifySignatureAgainstCatalog(v203, pszPath, v18, v19);
    v116 = StoreAppInstallDirectory;
    if ( StoreAppInstallDirectory )
    {
      v21 = 1813;
      goto LABEL_85;
    }
  }
  v43 = 0;
  if ( v1 )
    goto LABEL_126;
  v44 = 0;
  while ( 2 )
  {
    v43 = 0;
    if ( !v137[72 * v44] )
      goto LABEL_121;
    if ( *((_QWORD *)*(&v142 + 9 * v44) + 2) != *((_QWORD *)v144[9 * v44 - 1] + 2) )
    {
LABEL_124:
      v43 = 1;
      break;
    }
    v45 = (ULONGLONG *)*(&v141 + 9 * v44);
    if ( !v45[2] )
      goto LABEL_121;
    v46 = 0;
    while ( 2 )
    {
      v47 = 0;
      if ( v46 < v45[2] )
      {
        v127[0] = 0;
        if ( ULongLongMult(v45[1], v46, v127) < 0
          || (v47 = (const unsigned __int16 **)(v45[5] + v127[0]), (unsigned __int64)v47 < v45[5]) )
        {
          v47 = v48;
        }
      }
      v49 = RtlStringArray::Find(*(&v140 + 9 * v44), *v47);
      v124 = 0;
      if ( v49 == -1 )
        goto LABEL_124;
      v50 = v144[9 * v44 - 1];
      v51 = 0;
      if ( v46 < *((_QWORD *)v50 + 2) )
      {
        v127[0] = 0;
        if ( ULongLongMult(*((_QWORD *)v50 + 1), v46, v127) < 0
          || (v51 = (const unsigned __int16 **)(*(_QWORD *)(v52 + 40) + v127[0]),
              (unsigned __int64)v51 < *(_QWORD *)(v52 + 40)) )
        {
          v51 = v53;
        }
      }
      v54 = *v51;
      v55 = (__int64)*(&v142 + 9 * v44);
      v56 = 0;
      if ( v49 < *(_QWORD *)(v55 + 16) )
      {
        v127[0] = 0;
        if ( ULongLongMult(*(_QWORD *)(v55 + 8), v49, v127) < 0
          || (v56 = (const unsigned __int16 **)(*(_QWORD *)(v57 + 40) + v127[0]),
              (unsigned __int64)v56 < *(_QWORD *)(v57 + 40)) )
        {
          v56 = 0;
        }
      }
      StoreAppDllsForArch = MergeSdbpCompareDlls(*v56, v54, &v124);
      v116 = StoreAppDllsForArch;
      if ( StoreAppDllsForArch )
      {
        v41 = "MergeSdbpCompareDlls failed (%d)";
        v42 = 1844;
        goto LABEL_93;
      }
      if ( !v124 )
        goto LABEL_124;
      if ( ++v46 < v45[2] )
        continue;
      break;
    }
    v43 = 0;
LABEL_121:
    if ( (unsigned __int64)++v44 < 4 )
      continue;
    break;
  }
  v1 = v120;
  v12 = v121;
LABEL_126:
  RegistryDWORD = PcaUtilityGetRegistryDWORD(hKey[0], 0, L"TestHookRapidMitigationsForceAddition", 0);
  LODWORD(v127[0]) = RegistryDWORD;
  if ( v118 )
  {
    LODWORD(pullResult) = -1;
    if ( !v123[0] )
      goto LABEL_144;
    if ( v11 && !memcmp_0(&Buf1, &Buf2, 0x10u) && *(_QWORD *)v128 < *(_QWORD *)v131 )
      goto LABEL_145;
    v59 = L" -mm";
    if ( !v122 )
      v59 = &sourceString;
    v60 = StringCchPrintfW(Src, 0x104u, L"%ls\\system32\\sdbinst.exe%ls -u -g %ls", L"%SYSTEMROOT%", v59, v119);
    if ( PcaFailedHr(&v116, v60) )
    {
      v21 = 1892;
LABEL_135:
      v20 = "StringCchPrintfW failed (%d)";
      goto LABEL_136;
    }
    v61 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( PcaFailedHr(&v116, v61) )
    {
      v20 = "Failed to create and expand sdbinst.exe path (%d)";
      v21 = 1899;
      goto LABEL_136;
    }
    StoreAppInstallDirectory = MergeSdbpLaunchProcess(Dst, (unsigned int *)&pullResult, v62);
    v116 = StoreAppInstallDirectory;
    if ( StoreAppInstallDirectory )
    {
      v20 = "Failed to remove installed merge db (%d)";
      v21 = 1904;
      goto LABEL_41;
    }
    if ( (_DWORD)pullResult )
    {
      phkResult = Dst;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        1909,
        (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
    }
    else
    {
      LODWORD(phkResult) = 0;
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        1912,
        (unsigned int)"SdbInst.exe ran successfully for msi removal: %d");
    }
LABEL_144:
    if ( v11 )
    {
LABEL_145:
      v63 = L" -a";
      if ( !RegistryDWORD )
        v63 = &sourceString;
      v64 = L" -mm";
      if ( !v122 )
        v64 = &sourceString;
      v65 = StringCchPrintfW(Src, 0x104u, L"%ls\\system32\\sdbinst.exe%ls%ls \"%ls\"", L"%SYSTEMROOT%", v64, v63, v201);
      if ( PcaFailedHr(&v116, v65) )
      {
        v21 = 1924;
        goto LABEL_135;
      }
      v66 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
      if ( PcaFailedHr(&v116, v66) )
      {
        v20 = "Failed to create and expand sdbinst.exe path (%d)";
        v21 = 1931;
        goto LABEL_136;
      }
      StoreAppInstallDirectory = MergeSdbpLaunchProcess(Dst, (unsigned int *)&pullResult, v67);
      v116 = StoreAppInstallDirectory;
      if ( StoreAppInstallDirectory )
      {
        v20 = "Failed to install merge db (%d)";
        v21 = 1936;
        goto LABEL_41;
      }
      if ( (_DWORD)pullResult )
      {
        phkResult = Dst;
        AslLogCallPrintf(
          1,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          1941,
          (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
      }
      else
      {
        LODWORD(phkResult) = 0;
        AslLogCallPrintf(
          0,
          (unsigned int)"MergeSdbpGatherStoreAppFiles",
          1944,
          (unsigned int)"SdbInst.exe ran successfully for msi update/add: %d");
      }
    }
    if ( !(_DWORD)pullResult )
    {
      if ( v11 )
      {
        v68 = AslGuidToString(Data, 40, &Buf2);
        if ( PcaFailedNt(&v116, v68) )
        {
          v20 = "AslGuidToString failed (%d)";
          v21 = 1953;
          goto LABEL_136;
        }
        v69 = -1;
        do
          ++v69;
        while ( Data[v69] );
        StoreAppInstallDirectory = RegSetValueExW(hKey[0], L"SAIDMSI", 0, 1u, (const BYTE *)Data, 2 * v69 + 2);
        if ( StoreAppInstallDirectory )
        {
          v20 = "RegSetValueExW failed (%d)";
          v21 = 1963;
          goto LABEL_41;
        }
        StoreAppInstallDirectory = RegSetValueExW(hKey[0], L"SATMSI", 0, 0xBu, v131, 8u);
        v116 = StoreAppInstallDirectory;
        if ( StoreAppInstallDirectory )
        {
          v20 = "RegSetValueExW failed (%d)";
          v21 = 1973;
          goto LABEL_41;
        }
      }
      else
      {
        StoreAppInstallDirectory = RegDeleteValueW(hKey[0], L"SAIDMSI");
        if ( StoreAppInstallDirectory )
        {
          v20 = "RegDeleteValueW failed (%d)";
          v21 = 1979;
          goto LABEL_41;
        }
        StoreAppInstallDirectory = RegDeleteValueW(hKey[0], L"SATMSI");
        v116 = StoreAppInstallDirectory;
        if ( StoreAppInstallDirectory )
        {
          v20 = "RegDeleteValueW failed (%d)";
          v21 = 1984;
          goto LABEL_41;
        }
      }
    }
  }
  if ( !v1 && !v43 )
  {
LABEL_289:
    StoreAppInstallDirectory = RegSetValueExW(hKey[0], L"SAV", 0, 0xBu, v133, 8u);
    if ( StoreAppInstallDirectory )
    {
      v20 = "RegSetValueExW failed (%d)";
      v21 = 2256;
      goto LABEL_41;
    }
    g_TipTest_StoreAppStateWasModified = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v125);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v177);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v173);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v179);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v180);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v181);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v182);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v183);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v184);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v178);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v185);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v186);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v187);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v188);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v189);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v190);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v191);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v172);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v174);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v175);
    RtlStringArray::~RtlStringArray((RtlStringArray *)v176);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return 0;
  }
  v128[0] = -1;
  if ( !v123[1] || v43 )
    goto LABEL_190;
  if ( !v12 || memcmp_0(&Guid, &v135, 0x10u) || *(_QWORD *)&v123[5] >= *(_QWORD *)v132 )
  {
    v70 = L" -mm";
    if ( !v122 )
      v70 = &sourceString;
    v71 = StringCchPrintfW(v207, 0x104u, L"%ls\\system32\\sdbinst.exe%ls -u -g %ls", L"%SYSTEMROOT%", v70, v125[0]);
    if ( PcaFailedHr(&v116, v71) )
    {
      v21 = 2024;
      goto LABEL_135;
    }
    v72 = ExpandEnvironmentStringsW(v207, v204, 0x104u);
    if ( PcaFailedHr(&v116, v72) )
    {
      v20 = "Failed to create and expand sdbinst.exe path (%d)";
      v21 = 2031;
      goto LABEL_136;
    }
    StoreAppInstallDirectory = MergeSdbpLaunchProcess(v204, v128, v73);
    v116 = StoreAppInstallDirectory;
    if ( StoreAppInstallDirectory )
    {
      v20 = "Failed to remove installed merge db (%d)";
      v21 = 2036;
      goto LABEL_41;
    }
    if ( v128[0] )
    {
      phkResult = v204;
      AslLogCallPrintf(
        1,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2041,
        (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
    }
    else
    {
      v117 = 0;
      LODWORD(phkResult) = 0;
      AslLogCallPrintf(
        0,
        (unsigned int)"MergeSdbpGatherStoreAppFiles",
        2045,
        (unsigned int)"SdbInst.exe ran successfully for sys removal: %d");
    }
LABEL_190:
    if ( !v12 )
      goto LABEL_242;
  }
  v74 = 0;
  while ( 2 )
  {
    if ( v137[72 * v74] )
    {
      RtlStringArray::RtlStringArray((RtlStringArray *)v171);
      RtlStringArray::Initialize((RtlStringArray *)v171, v75, 0, 0x10u, (int)phkResult);
      v76 = RtlStringArray::AppendFrom((RtlStringArray *)v171, *(&v141 + 9 * v74));
      if ( PcaFailedHr(&v116, v76) )
      {
        v98 = 2065;
      }
      else
      {
        v77 = RtlStringArray::AppendFrom((RtlStringArray *)v171, *(&v140 + 9 * v74));
        if ( !PcaFailedHr(&v116, v77) )
        {
          StoreAppDllsForArch = MergeSdbpSetInstalledShimDlls(hKey, v171, *(_QWORD *)&v139[36 * v74 - 4]);
          v116 = StoreAppDllsForArch;
          if ( !StoreAppDllsForArch )
          {
            RtlStringArray::~RtlStringArray((RtlStringArray *)v171);
            goto LABEL_197;
          }
          AslLogCallPrintf(
            1,
            (unsigned int)"MergeSdbpGatherStoreAppFiles",
            2075,
            (unsigned int)"MergeSdbpSetInstalledShimDlls failed (%d)");
          RtlStringArray::~RtlStringArray((RtlStringArray *)v171);
LABEL_94:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v125);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
LABEL_38:
          StoreAppInstallDirectory = StoreAppDllsForArch;
          goto LABEL_298;
        }
        v98 = 2070;
      }
      StoreAppInstallDirectory = v116;
      AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v98, (unsigned int)"AppendFrom failed (%d)");
      RtlStringArray::~RtlStringArray((RtlStringArray *)v171);
      goto LABEL_42;
    }
LABEL_197:
    if ( (unsigned __int64)++v74 < 4 )
      continue;
    break;
  }
  for ( m = 0; m < 4; ++m )
  {
    if ( v137[72 * m] )
    {
      v79 = (ULONGLONG *)*(&v141 + 9 * m);
      if ( v79[2] )
      {
        v80 = 0;
        do
        {
          v81 = 0;
          if ( v80 < v79[2] )
          {
            *(_QWORD *)&v123[5] = 0;
            if ( ULongLongMult(v79[1], v80, (ULONGLONG *)&v123[5]) < 0
              || (v81 = (const unsigned __int16 **)(v79[5] + *(_QWORD *)&v123[5]), (unsigned __int64)v81 < v79[5]) )
            {
              v81 = 0;
            }
          }
          v82 = RtlStringArray::Find(*(&v140 + 9 * m), *v81);
          v118 = 0;
          if ( v82 == -1 )
            goto LABEL_217;
          v83 = v144[9 * m - 1];
          v84 = 0;
          if ( v80 < *((_QWORD *)v83 + 2) )
          {
            *(_QWORD *)&v123[5] = 0;
            if ( ULongLongMult(*((_QWORD *)v83 + 1), v80, (ULONGLONG *)&v123[5]) < 0
              || (v84 = (const unsigned __int16 **)(*(_QWORD *)(v85 + 40) + *(_QWORD *)&v123[5]),
                  (unsigned __int64)v84 < *(_QWORD *)(v85 + 40)) )
            {
              v84 = 0;
            }
          }
          v86 = *v84;
          v87 = (__int64)*(&v142 + 9 * m);
          v88 = 0;
          if ( v82 < *(_QWORD *)(v87 + 16) )
          {
            *(_QWORD *)&v123[5] = 0;
            if ( ULongLongMult(*(_QWORD *)(v87 + 8), v82, (ULONGLONG *)&v123[5]) < 0
              || (v88 = (const unsigned __int16 **)(*(_QWORD *)(v89 + 40) + *(_QWORD *)&v123[5]),
                  (unsigned __int64)v88 < *(_QWORD *)(v89 + 40)) )
            {
              v88 = 0;
            }
          }
          v90 = MergeSdbpCompareDlls(*v88, v86, &v118);
          v116 = v90;
          if ( v90 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              2098,
              (unsigned int)"MergeSdbpCompareDlls failed (%d)");
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v125);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
            StoreAppInstallDirectory = v90;
            goto LABEL_298;
          }
          if ( !v118 )
          {
LABEL_217:
            v91 = v144[9 * m - 1];
            v92 = 0;
            if ( v80 < *((_QWORD *)v91 + 2) )
            {
              *(_QWORD *)&v123[5] = 0;
              if ( ULongLongMult(*((_QWORD *)v91 + 1), v80, (ULONGLONG *)&v123[5]) < 0
                || (v92 = (LPCWSTR *)(*(_QWORD *)(v93 + 40) + *(_QWORD *)&v123[5]),
                    (unsigned __int64)v92 < *(_QWORD *)(v93 + 40)) )
              {
                v92 = 0;
              }
            }
            v94 = SdbAddPluginDll(*v92);
            if ( PcaFailedNt(&v116, v94) )
              AslLogCallPrintf(
                1,
                (unsigned int)"MergeSdbpGatherStoreAppFiles",
                2108,
                (unsigned int)"SdbAddPluginDll failed, swallowing (%d)");
          }
          ++v80;
        }
        while ( v80 < v79[2] );
      }
    }
  }
  v95 = L" -a";
  if ( !LODWORD(v127[0]) )
    v95 = &sourceString;
  v96 = L" -mm";
  if ( !v122 )
    v96 = &sourceString;
  v97 = StringCchPrintfW(v207, 0x104u, L"%ls\\system32\\sdbinst.exe%ls%ls \"%ls\"", L"%SYSTEMROOT%", v96, v95, v203);
  if ( PcaFailedHr(&v116, v97) )
  {
    v21 = 2118;
    goto LABEL_135;
  }
  v99 = ExpandEnvironmentStringsW(v207, v204, 0x104u);
  if ( PcaFailedHr(&v116, v99) )
  {
    v20 = "Failed to create and expand sdbinst.exe path (%d)";
    v21 = 2125;
    goto LABEL_136;
  }
  StoreAppInstallDirectory = MergeSdbpLaunchProcess(v204, v128, v100);
  v116 = StoreAppInstallDirectory;
  if ( StoreAppInstallDirectory )
  {
    v20 = "Failed to install merge db (%d)";
    v21 = 2130;
    goto LABEL_41;
  }
  if ( !v128[0] )
  {
    v101 = 1;
    v117 = 1;
    AslLogCallPrintf(
      0,
      (unsigned int)"MergeSdbpGatherStoreAppFiles",
      2140,
      (unsigned int)"SdbInst.exe ran successfully for sys update/add: %d");
    goto LABEL_243;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"MergeSdbpGatherStoreAppFiles",
    2135,
    (unsigned int)"Sdbinst.exe (%ls) returned unexpected result (%d)");
LABEL_242:
  v101 = v117;
  if ( v117 )
  {
LABEL_267:
    for ( n = 0; n < 4; ++n )
    {
      if ( v137[72 * n] )
      {
        StoreAppDllsForArch = MergeSdbpSetInstalledShimDlls(hKey, v144[9 * n], *(_QWORD *)&v139[36 * n - 4]);
        v116 = StoreAppDllsForArch;
        if ( StoreAppDllsForArch )
        {
          v41 = "MergeSdbpSetInstalledShimDlls failed (%d)";
          v42 = 2192;
          goto LABEL_93;
        }
      }
    }
    if ( v128[0] )
      goto LABEL_289;
    if ( v101 )
    {
      v112 = AslGuidToString(v199, 40, &v135);
      if ( PcaFailedNt(&v116, v112) )
      {
        v20 = "AslGuidToString failed (%d)";
        v21 = 2206;
        goto LABEL_136;
      }
      v113 = -1;
      do
        ++v113;
      while ( v199[v113] );
      StoreAppInstallDirectory = RegSetValueExW(hKey[0], L"SAIDSYS", 0, 1u, (const BYTE *)v199, 2 * v113 + 2);
      if ( StoreAppInstallDirectory )
      {
        v20 = "RegSetValueExW failed (%d)";
        v21 = 2216;
        goto LABEL_41;
      }
      StoreAppInstallDirectory = RegSetValueExW(hKey[0], L"SATSYS", 0, 0xBu, v132, 8u);
      if ( StoreAppInstallDirectory )
      {
        v20 = "RegSetValueExW failed (%d)";
        v21 = 2226;
        goto LABEL_41;
      }
    }
    else
    {
      StoreAppInstallDirectory = RegDeleteValueW(hKey[0], L"SAIDSYS");
      if ( StoreAppInstallDirectory )
      {
        v20 = "RegDeleteValueW failed (%d)";
        v21 = 2232;
        goto LABEL_41;
      }
      StoreAppInstallDirectory = RegDeleteValueW(hKey[0], L"SATSYS");
      if ( StoreAppInstallDirectory )
      {
        v20 = "RegDeleteValueW failed (%d)";
        v21 = 2237;
        goto LABEL_41;
      }
    }
    goto LABEL_289;
  }
LABEL_243:
  v102 = 0;
  while ( !v137[72 * v102] )
  {
LABEL_266:
    if ( (unsigned __int64)++v102 >= 4 )
      goto LABEL_267;
  }
  v103 = RtlStringArray::AppendFrom(v144[9 * v102], *(&v141 + 9 * v102));
  if ( !PcaFailedHr(&v116, v103) )
  {
    v104 = (ULONGLONG *)*(&v140 + 9 * v102);
    if ( v104[2] )
    {
      v105 = 0;
      while ( 1 )
      {
        if ( !v101 )
          goto LABEL_254;
        v106 = 0;
        if ( v105 < v104[2] )
        {
          *(_QWORD *)&v123[5] = 0;
          if ( ULongLongMult(v104[1], v105, (ULONGLONG *)&v123[5]) < 0
            || (v106 = (const unsigned __int16 **)(v104[5] + *(_QWORD *)&v123[5]), (unsigned __int64)v106 < v104[5]) )
          {
            v106 = 0;
          }
        }
        if ( RtlStringArray::Find(*(&v141 + 9 * v102), *v106) == -1 )
        {
LABEL_254:
          v107 = 0;
          if ( v105 < v104[2] )
          {
            *(_QWORD *)&v123[5] = 0;
            if ( ULongLongMult(v104[1], v105, (ULONGLONG *)&v123[5]) < 0
              || (v107 = (_QWORD *)(v104[5] + *(_QWORD *)&v123[5]), (unsigned __int64)v107 < v104[5]) )
            {
              v107 = 0;
            }
          }
          v108 = SdbRemovePluginDll(*v107, (unsigned __int16)v139[36 * v102]);
          if ( PcaFailedNt(&v116, v108) )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"MergeSdbpGatherStoreAppFiles",
              2171,
              (unsigned int)"SdbRemovePluginDll failed, swallowing (%d)");
            v109 = 0;
            if ( v105 < v104[2] )
            {
              *(_QWORD *)&v123[5] = 0;
              if ( ULongLongMult(v104[1], v105, (ULONGLONG *)&v123[5]) < 0
                || (v109 = (const unsigned __int16 **)(v104[5] + *(_QWORD *)&v123[5]), (unsigned __int64)v109 < v104[5]) )
              {
                v109 = 0;
              }
            }
            v110 = RtlStringArray::Append(v144[9 * v102], *v109, 0);
            if ( PcaFailedHr(&v116, v110) )
            {
              v20 = "Append failed (%d)";
              v21 = 2174;
              goto LABEL_136;
            }
          }
          v101 = v117;
        }
        if ( ++v105 >= v104[2] )
          goto LABEL_266;
      }
    }
    goto LABEL_266;
  }
  v20 = "AppendFrom failed (%d)";
  v21 = 2155;
LABEL_136:
  StoreAppInstallDirectory = v116;
LABEL_41:
  AslLogCallPrintf(1, (unsigned int)"MergeSdbpGatherStoreAppFiles", v21, (_DWORD)v20);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v125);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v119);
LABEL_298:
  RtlStringArray::~RtlStringArray((RtlStringArray *)v177);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v173);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v179);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v180);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v181);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v182);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v183);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v184);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v178);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v185);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v186);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v187);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v188);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v189);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v190);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v191);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v172);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v174);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v175);
  RtlStringArray::~RtlStringArray((RtlStringArray *)v176);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return StoreAppInstallDirectory;
}

```

## disassembly

```asm
0x180043424  push    rbp
0x180043426  push    rbx
0x180043427  push    rsi
0x180043428  push    rdi
0x180043429  push    r12
0x18004342b  push    r13
0x18004342d  push    r14
0x18004342f  push    r15
0x180043431  lea     rbp, [rsp-19A8h]
0x180043439  mov     eax, 1AA8h
0x18004343e  call    _alloca_probe
0x180043443  sub     rsp, rax
0x180043446  movaps  [rsp+1AE0h+var_50], xmm6
0x18004344e  movaps  [rsp+1AE0h+var_60], xmm7
0x180043456  mov     rax, cs:__security_cookie
0x18004345d  xor     rax, rsp
0x180043460  mov     [rbp+19E0h+var_70], rax
0x180043467  mov     [rsp+1AE0h+var_1A7E], cl
0x18004346b  xor     r15d, r15d
0x18004346e  mov     [rsp+1AE0h+var_1A90], r15d
0x180043473  mov     [rbp+19E0h+hKey], r15
0x180043477  mov     qword ptr [rbp+19E0h+var_1A10], r15
0x18004347b  mov     qword ptr [rbp+19E0h+var_1A18], r15
0x18004347f  xorps   xmm0, xmm0
0x180043482  movups  xmmword ptr [rbp+19E0h+Guid.Data1], xmm0
0x180043489  xorps   xmm1, xmm1
0x18004348c  movups  [rbp+19E0h+Buf1], xmm1
0x180043493  lea     rcx, [rbp+19E0h+var_17A8]; this
0x18004349a  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004349f  nop
0x1800434a0  lea     rcx, [rbp+19E0h+var_17E0]; this
0x1800434a7  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434ac  nop
0x1800434ad  lea     rcx, [rbp+19E0h+var_1818]; this
0x1800434b4  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434b9  nop
0x1800434ba  lea     rcx, [rbp+19E0h+var_1888]; this
0x1800434c1  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434c6  nop
0x1800434c7  lea     rcx, [rbp+19E0h+var_1460]; this
0x1800434ce  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434d3  nop
0x1800434d4  lea     rcx, [rbp+19E0h+var_1498]; this
0x1800434db  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434e0  nop
0x1800434e1  lea     rcx, [rbp+19E0h+var_14D0]; this
0x1800434e8  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434ed  nop
0x1800434ee  lea     rcx, [rbp+19E0h+var_1508]; this
0x1800434f5  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x1800434fa  nop
0x1800434fb  lea     rcx, [rbp+19E0h+var_1540]; this
0x180043502  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043507  nop
0x180043508  lea     rcx, [rbp+19E0h+var_1578]; this
0x18004350f  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043514  nop
0x180043515  lea     rcx, [rbp+19E0h+var_15B0]; this
0x18004351c  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043521  nop
0x180043522  lea     rcx, [rbp+19E0h+var_1738]; this
0x180043529  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004352e  nop
0x18004352f  lea     rcx, [rbp+19E0h+var_15E8]; this
0x180043536  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004353b  nop
0x18004353c  lea     rcx, [rbp+19E0h+var_1620]; this
0x180043543  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043548  nop
0x180043549  lea     rcx, [rbp+19E0h+var_1658]; this
0x180043550  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043555  nop
0x180043556  lea     rcx, [rbp+19E0h+var_1690]; this
0x18004355d  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043562  nop
0x180043563  lea     rcx, [rbp+19E0h+var_16C8]; this
0x18004356a  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004356f  nop
0x180043570  lea     rcx, [rbp+19E0h+var_1700]; this
0x180043577  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18004357c  nop
0x18004357d  lea     rcx, [rbp+19E0h+var_1850]; this
0x180043584  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043589  nop
0x18004358a  lea     rcx, [rbp+19E0h+var_1770]; this
0x180043591  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x180043596  nop
0x180043597  mov     [rsp+1AE0h+var_1A7D], r15b
0x18004359c  mov     [rsp+1AE0h+var_1A7D+1], r15b
0x1800435a1  mov     qword ptr [rbp+19E0h+var_1A18], r15
0x1800435a5  mov     qword ptr [rbp+19E0h+var_1A10], r15
0x1800435a9  mov     qword ptr [rbp+19E0h+var_1A30], r15
0x1800435ad  mov     qword ptr [rsp+1AE0h+var_1A7D+5], r15
0x1800435b2  xorps   xmm7, xmm7
0x1800435b5  movaps  xmmword ptr [rbp+19E0h+var_19F0.Data1], xmm7
0x1800435b9  xorps   xmm6, xmm6
0x1800435bc  movaps  [rbp+19E0h+Buf2], xmm6
0x1800435c0  xorps   xmm0, xmm0
0x1800435c3  movups  xmmword ptr [rbp+19E0h+Guid.Data1], xmm0
0x1800435ca  xorps   xmm1, xmm1
0x1800435cd  movups  [rbp+19E0h+Buf1], xmm1
0x1800435d4  lea     rax, aX86; "X86"
0x1800435db  mov     [rbp+19E0h+var_19E0], rax
0x1800435df  mov     [rbp+19E0h+var_19D8], r15b
0x1800435e3  lea     rax, [rbp+19E0h+var_1408]
0x1800435ea  mov     [rbp+19E0h+var_19D0], rax
0x1800435ee  mov     eax, 14Ch
0x1800435f3  mov     [rbp+19E0h+var_19C8], ax
0x1800435f7  lea     rax, [rbp+19E0h+var_17A8]
0x1800435fe  mov     [rbp+19E0h+var_19C0], rax
0x180043602  lea     rax, [rbp+19E0h+var_1460]
0x180043609  mov     [rbp+19E0h+var_19B8], rax
0x18004360d  lea     rax, [rbp+19E0h+var_1540]
0x180043614  mov     [rbp+19E0h+var_19B0], rax
0x180043618  lea     rax, [rbp+19E0h+var_15E8]
0x18004361f  mov     [rbp+19E0h+var_19A8], rax
0x180043623  lea     rax, [rbp+19E0h+var_16C8]
0x18004362a  mov     [rbp+19E0h+var_19A0], rax
0x18004362e  lea     rax, aAmd64; "AMD64"
0x180043635  mov     [rbp+19E0h+var_1998], rax
0x180043639  mov     [rbp+19E0h+var_1990], r15b
0x18004363d  lea     rax, [rbp+19E0h+var_13F0]
0x180043644  mov     [rbp+19E0h+var_1988], rax
0x180043648  mov     eax, 8664h
0x18004364d  mov     [rbp+19E0h+var_1980], ax
0x180043651  lea     rax, [rbp+19E0h+var_17E0]
0x180043658  mov     [rbp+19E0h+var_1978], rax
0x18004365c  lea     rax, [rbp+19E0h+var_1498]
0x180043663  mov     [rbp+19E0h+var_1970], rax
0x180043667  lea     rax, [rbp+19E0h+var_1578]
0x18004366e  mov     [rbp+19E0h+var_1968], rax
0x180043672  lea     rax, [rbp+19E0h+var_1620]
0x180043679  mov     [rbp+19E0h+var_1960], rax
0x180043680  lea     rax, [rbp+19E0h+var_1700]
0x180043687  mov     [rbp+19E0h+var_1958], rax
0x18004368e  lea     rax, aArm; "ARM"
0x180043695  mov     [rbp+19E0h+var_1950], rax
0x18004369c  mov     [rbp+19E0h+var_1948], r15b
0x1800436a3  lea     rax, [rbp+19E0h+var_13D8]
0x1800436aa  mov     [rbp+19E0h+var_1940], rax
0x1800436b1  mov     eax, 1C4h
0x1800436b6  mov     [rbp+19E0h+var_1938], ax
0x1800436bd  lea     rax, [rbp+19E0h+var_1818]
0x1800436c4  mov     [rbp+19E0h+var_1930], rax
0x1800436cb  lea     rax, [rbp+19E0h+var_14D0]
0x1800436d2  mov     [rbp+19E0h+var_1928], rax
0x1800436d9  lea     rax, [rbp+19E0h+var_15B0]
0x1800436e0  mov     [rbp+19E0h+var_1920], rax
0x1800436e7  lea     rax, [rbp+19E0h+var_1658]
0x1800436ee  mov     [rbp+19E0h+var_1918], rax
0x1800436f5  lea     rax, [rbp+19E0h+var_1850]
0x1800436fc  mov     [rbp+19E0h+var_1910], rax
0x180043703  lea     rax, aArm64; "ARM64"
0x18004370a  mov     [rbp+19E0h+var_1908], rax
0x180043711  mov     [rbp+19E0h+var_1900], r15b
0x180043718  lea     rax, [rbp+19E0h+var_13C0]
0x18004371f  mov     [rbp+19E0h+var_18F8], rax
0x180043726  mov     eax, 0AA64h
0x18004372b  mov     [rbp+19E0h+var_18F0], ax
0x180043732  lea     rax, [rbp+19E0h+var_1888]
0x180043739  mov     [rbp+19E0h+var_18E8], rax
0x180043740  lea     rax, [rbp+19E0h+var_1508]
0x180043747  mov     [rbp+19E0h+var_18E0], rax
0x18004374e  lea     rax, [rbp+19E0h+var_1738]
0x180043755  mov     [rbp+19E0h+var_18D8], rax
0x18004375c  lea     rax, [rbp+19E0h+var_1690]
0x180043763  mov     [rbp+19E0h+var_18D0], rax
0x18004376a  lea     rax, [rbp+19E0h+var_1770]
0x180043771  mov     [rbp+19E0h+var_18C8], rax
0x180043778  mov     ebx, r15d
0x18004377b  lea     r14d, [r15+1]
0x18004377f  mov     [rbp+19E0h+var_1A20], r15d
0x180043783  lea     rdi, [rbx+rbx*8]
0x180043787  lea     rdx, [rbp+19E0h+var_1A20]
0x18004378b  movzx   ecx, [rbp+rdi*8+19E0h+var_19C8]
0x180043790  call    cs:__imp_GetMachineTypeAttributes
0x180043796  mov     edx, eax; int
0x180043798  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x18004379d  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800437a2  test    al, al
0x1800437a4  jnz     loc_180044FD0
0x1800437aa  mov     eax, [rbp+19E0h+var_1A20]
0x1800437ad  and     eax, r14d
0x1800437b0  test    al, al
0x1800437b2  jz      short loc_1800437B9
0x1800437b4  mov     [rbp+rdi*8+19E0h+var_19D8], r14b
0x1800437b9  mov     rax, [rbp+rdi*8+19E0h+var_19E0]
0x1800437be  mov     [rsp+1AE0h+phkResult], rax
0x1800437c3  lea     r9, aSacd; "SACD_"
0x1800437ca  lea     r8, aLsLs_0; "%ls%ls"
0x1800437d1  mov     edx, 0Bh; unsigned __int64
0x1800437d6  mov     rcx, [rbp+rdi*8+19E0h+var_19D0]; unsigned __int16 *
0x1800437db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800437e0  mov     edx, eax; int
0x1800437e2  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x1800437e7  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x1800437ec  test    al, al
0x1800437ee  jnz     loc_180044FC1
0x1800437f4  add     rbx, r14
0x1800437f7  cmp     rbx, 4
0x1800437fb  jb      short loc_18004377F
0x1800437fd  xor     edx, edx
0x1800437ff  lea     rcx, [rbp+19E0h+hKey]
0x180043803  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043808  lea     rax, [rbp+19E0h+hKey]
0x18004380c  mov     [rsp+1AE0h+phkResult], rax; phkResult
0x180043811  mov     r9d, 2001Fh; samDesired
0x180043817  xor     r8d, r8d; ulOptions
0x18004381a  lea     rdx, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180043821  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043828  call    cs:__imp_RegOpenKeyExW
0x18004382e  mov     ebx, eax
0x180043830  test    eax, eax
0x180043832  jz      short loc_18004384A
0x180043834  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043838  lea     r9, aRegopenkeyexwF; "RegOpenKeyExW failed (%d)"
0x18004383f  mov     r8d, 63Bh
0x180043845  jmp     loc_180044FE5
0x18004384a  mov     qword ptr [rbp+19E0h+var_1A08], r15
0x18004384e  lea     r8, [rbp+19E0h+var_1A08]; unsigned __int64 *
0x180043852  mov     edi, 104h
0x180043857  mov     edx, edi; unsigned __int64
0x180043859  lea     rcx, [rbp+19E0h+var_1300]; unsigned __int16 *
0x180043860  call    ?MergeSdbpGetStoreAppInstallDirectory@@YAKPEAG_KPEA_K@Z; MergeSdbpGetStoreAppInstallDirectory(ushort *,unsigned __int64,unsigned __int64 *)
0x180043865  mov     ebx, eax
0x180043867  mov     [rsp+1AE0h+var_1A90], eax
0x18004386b  test    eax, eax
0x18004386d  jz      short loc_180043885
0x18004386f  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043873  lea     r9, aMergesdbpgetst_2; "MergeSdbpGetStoreAppInstallDirectory fa"...
0x18004387a  mov     r8d, 647h
0x180043880  jmp     loc_180044FE5
0x180043885  or      r9, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x180043889  lea     r8, aSav; "SAV"
0x180043890  xor     edx, edx; unsigned __int16 *
0x180043892  mov     rcx, [rbp+19E0h+hKey]; HKEY
0x180043896  call    ?PcaUtilityGetRegistryQWORD@@YA_KPEAUHKEY__@@PEBG1_K@Z; PcaUtilityGetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x18004389b  cmp     qword ptr [rbp+19E0h+var_1A08], rax
0x18004389f  jz      loc_180044FBC
0x1800438a5  mov     r13b, r15b
0x1800438a8  mov     r12b, r15b
0x1800438ab  mov     [rsp+1AE0h+var_1A7F], r15b
0x1800438b0  cmp     [rbp+19E0h+var_1300], r15w
0x1800438b8  jnz     loc_180043965
0x1800438be  mov     [rbp+19E0h+var_10F0], r15w
0x1800438c6  mov     [rbp+19E0h+var_CD0], r15w
0x1800438ce  mov     [rsp+1AE0h+var_1A88], r15
0x1800438d3  lea     rcx, [rsp+1AE0h+var_1A88]
0x1800438d8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1800438dd  movdqa  xmmword ptr [rbp+19E0h+var_1A60], xmm6
0x1800438e2  lea     rax, aSatmsi; "SATMSI"
0x1800438e9  mov     [rsp+1AE0h+var_1AA0], rax; unsigned __int16 *
0x1800438ee  lea     rax, aSaidmsi; "SAIDMSI"
0x1800438f5  mov     [rsp+1AE0h+lpValue], rax; lpValue
0x1800438fa  mov     [rsp+1AE0h+var_1AB0], r13b; char
0x1800438ff  lea     rax, [rbp+19E0h+var_1A60]
0x180043903  mov     qword ptr [rsp+1AE0h+cbData], rax; __int64
0x180043908  lea     rax, [rsp+1AE0h+var_1A7D]
0x18004390d  mov     [rsp+1AE0h+phkResult], rax; __int64
0x180043912  lea     r9, [rbp+19E0h+var_1A30]
0x180043916  lea     r8, [rbp+19E0h+Buf1]; Guid
0x18004391d  lea     rdx, [rsp+1AE0h+var_1A88]; unsigned __int16 **
0x180043922  mov     rcx, [rbp+19E0h+hKey]; hkey
0x180043926  call    ?MergeSdbpGetSdbGuidAndTimestampFromRegistry@@YAKPEAUHKEY__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_GUID@@AEA_KAEA_NU4@_NPEBG7@Z; MergeSdbpGetSdbGuidAndTimestampFromRegistry(HKEY__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,_GUID &,unsigned __int64 &,bool &,_GUID,bool,ushort const *,ushort const *)
0x18004392b  mov     ebx, eax
0x18004392d  test    eax, eax
0x18004392f  jz      loc_180043B43
0x180043935  mov     dword ptr [rsp+1AE0h+phkResult], eax
0x180043939  lea     r9, aMergesdbpgetsd_0; "MergeSdbpGetSdbGuidAndTimestampFromRegi"...
0x180043940  mov     r8d, 6ACh
0x180043946  lea     rdx, aMergesdbpgathe; "MergeSdbpGatherStoreAppFiles"
0x18004394d  mov     ecx, r14d
0x180043950  call    AslLogCallPrintf
0x180043955  nop
0x180043956  lea     rcx, [rsp+1AE0h+var_1A88]
0x18004395b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043960  jmp     loc_180044FF5
0x180043965  lea     rax, aApplicationcom; "ApplicationCompatibilityEnhancements.ca"...
0x18004396c  mov     [rsp+1AE0h+phkResult], rax
0x180043971  lea     r9, [rbp+19E0h+var_1300]
0x180043978  lea     r8, aLsLs; "%ls\\%ls"
0x18004397f  mov     rdx, rdi; unsigned __int64
0x180043982  lea     rcx, [rbp+19E0h+pszPath]; unsigned __int16 *
0x180043989  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004398e  mov     edx, eax; int
0x180043990  lea     rcx, [rsp+1AE0h+var_1A90]; unsigned int *
0x180043995  call    ?PcaFailedHr@@YA_NAEAKJ@Z; PcaFailedHr(ulong &,long)
0x18004399a  test    al, al
0x18004399c  jz      short loc_1800439A9
0x18004399e  mov     r8d, 666h
0x1800439a4  jmp     loc_180044FC7
0x1800439a9  lea     rcx, [rbp+19E0h+pszPath]; pszPath
0x1800439b0  call    cs:__imp_PathFileExistsW
0x1800439b6  test    eax, eax
0x1800439b8  jz      loc_180044FBC
0x1800439be  lea     rax, aMsimergeinboxs; "msiMergeInboxStoreApp.sdb"
0x1800439c5  mov     [rsp+1AE0h+phkResult], rax
0x1800439ca  lea     r9, [rbp+19E0h+var_1300]
0x1800439d1  lea     r8, aLsSdbLs; "%ls\\sdb\\%ls"
0x1800439d8  mov     rdx, rdi; unsigned __int64
  ... truncated ...
```
