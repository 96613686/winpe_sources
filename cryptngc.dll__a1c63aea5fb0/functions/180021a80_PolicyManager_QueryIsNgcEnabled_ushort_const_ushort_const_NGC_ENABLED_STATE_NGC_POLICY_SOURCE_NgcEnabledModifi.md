# PolicyManager::QueryIsNgcEnabled(ushort const *,ushort const *,_NGC_ENABLED_STATE *,_NGC_POLICY_SOURCE *,_NgcEnabledModifiers *)

- ea: `0x180021a80`
- end: `0x18002370e`
- name: `?QueryIsNgcEnabled@PolicyManager@@YAJPEBG0PEAW4_NGC_ENABLED_STATE@@PEAW4_NGC_POLICY_SOURCE@@PEAW4_NgcEnabledModifiers@@@Z`
- size: `7310`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, enum _NGC_ENABLED_STATE *, enum _NGC_POLICY_SOURCE *, enum _NgcEnabledModifiers *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035688`
- `0x1800374f0`

## callees

- `0x1800046e0`
- `0x180004720`
- `0x180007730`
- `0x18000eae0`
- `0x18000edb0`
- `0x18000ee00`
- `0x18000fc20`
- `0x1800158e0`
- `0x18001794c`
- `0x180021a80`
- `0x180023cb0`
- `0x18002494c`
- `0x180027394`
- `0x18002cb1c`
- `0x18002cbf8`
- `0x18002dff0`
- `0x18002e02c`
- `0x18002f7db`
- `0x18002f7e7`
- `0x180038e9c`
- `0x18003dddc`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e83`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021db2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021f40`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800220fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800235da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800236cb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021db2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180021f40`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800220fb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800235da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800236cb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b18`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b3f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021f90`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002277e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180022cc4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180022eaf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023607`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b18`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021b3f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180021f90`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002277e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180022cc4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180022eaf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022754`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022896`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021e75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022754`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022896`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022c9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022e89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022dea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022dea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023414`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dfd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021e51`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021e51`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PolicyManager::QueryIsNgcEnabled(
        const WCHAR *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        enum _NGC_ENABLED_STATE *a4,
        enum _NGC_POLICY_SOURCE *a5)
{
  unsigned __int64 v5; // r15
  __int16 v6; // ax
  __int16 v7; // dx
  __int16 v8; // dx
  const WCHAR *v9; // rdx
  LPCWSTR v10; // rcx
  GUID *v11; // r9
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  BOOL v16; // ebx
  enum NgcUserAccountType *v17; // r8
  void *v18; // rcx
  signed int LastError; // ebx
  HLOCAL v20; // rcx
  bool v21; // zf
  struct _EVENT_DATA_DESCRIPTOR *v22; // rax
  int v23; // ebx
  __int64 v24; // rdx
  _OWORD *v25; // rax
  __int64 v26; // rbx
  unsigned __int64 v27; // r12
  __int64 v28; // rsi
  size_t v29; // r14
  void **v30; // rcx
  unsigned __int64 v31; // rdi
  __int64 v32; // rcx
  size_t v33; // rcx
  char *v34; // rbx
  void *v35; // rax
  size_t v36; // r8
  char *v37; // rdi
  void *v38; // rdi
  unsigned __int64 v39; // rdx
  _BYTE *v40; // rcx
  void *v41; // r12
  __int64 v42; // rdx
  unsigned __int64 v43; // rdi
  void **v44; // rbx
  unsigned __int64 v45; // rdi
  __int64 v46; // r8
  size_t v47; // rcx
  char *v48; // rbx
  void *v49; // rax
  size_t v50; // r8
  size_t v51; // rdi
  __int64 v52; // r15
  void *v53; // rdi
  unsigned __int64 v54; // rdx
  _BYTE *v55; // rcx
  __int64 v56; // r12
  unsigned __int64 v57; // r15
  __int64 v58; // rdi
  void **v59; // rbx
  _QWORD *v60; // rbx
  __int64 v61; // rdi
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  void *v64; // rax
  size_t v65; // r12
  _WORD *v66; // rsi
  void *v67; // rdi
  unsigned __int64 v68; // rdx
  void *v69; // rcx
  void **v70; // rdx
  HLOCAL v71; // rcx
  HLOCAL v72; // rcx
  __int64 v73; // r13
  unsigned __int64 v74; // r12
  __int64 v75; // rsi
  size_t v76; // r14
  __int64 v77; // rdx
  void **v78; // rcx
  unsigned __int64 v79; // rdi
  unsigned __int64 v80; // rcx
  size_t v81; // rcx
  _QWORD *v82; // rbx
  void *v83; // rax
  size_t v84; // r8
  _WORD *v85; // r13
  _WORD *v86; // rdi
  void *v87; // rdi
  unsigned __int64 v88; // rdx
  _BYTE *v89; // rcx
  __int64 v90; // r13
  unsigned __int64 v91; // r12
  __int64 v92; // rdi
  void **v93; // rbx
  int v94; // r14d
  _QWORD *v95; // rbx
  unsigned __int64 v96; // rdi
  unsigned __int64 v97; // rcx
  void *v98; // rax
  size_t v99; // r13
  _WORD *v100; // r14
  void *v101; // rdi
  unsigned __int64 v102; // rdx
  void *v103; // rcx
  void **v104; // rdx
  HLOCAL v105; // rcx
  void **v106; // rdx
  void **v107; // rdx
  int v108; // r13d
  int v109; // r12d
  int v110; // ebx
  int EnabledState; // edi
  HLOCAL v112; // rcx
  __int64 v114; // rdx
  unsigned __int64 v115; // rdi
  _WORD *v116; // rbx
  unsigned __int64 v117; // rcx
  __int64 v118; // rcx
  char *v119; // rbx
  __int64 v120; // r8
  __int64 v121; // r8
  void **v122; // rdx
  void **v123; // rdx
  void **v124; // rdx
  void **v125; // rdx
  void **v126; // rdx
  void **v127; // rdx
  void **v128; // rdx
  LSTATUS ValueW; // eax
  int v130; // edi
  __int64 v131; // rcx
  int UserAccountType; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  void *pvData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v135; // [rsp+58h] [rbp-A8h] BYREF
  int v136; // [rsp+5Ch] [rbp-A4h] BYREF
  int v137; // [rsp+60h] [rbp-A0h] BYREF
  int v138; // [rsp+64h] [rbp-9Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  char v140; // [rsp+78h] [rbp-88h]
  int v141; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData[2]; // [rsp+88h] [rbp-78h] BYREF
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  LSTATUS v144; // [rsp+98h] [rbp-68h] BYREF
  void *v145; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR StringSid; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v147; // [rsp+B0h] [rbp-50h] BYREF
  enum _NGC_ENABLED_STATE *v148; // [rsp+B8h] [rbp-48h] BYREF
  enum _NGC_POLICY_SOURCE *v149; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v150[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v151; // [rsp+110h] [rbp+10h]
  int v152; // [rsp+120h] [rbp+20h] BYREF
  char v153; // [rsp+124h] [rbp+24h]
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF
  GUID v155; // [rsp+138h] [rbp+38h] BYREF
  void *v156[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v157; // [rsp+158h] [rbp+58h]
  unsigned __int64 v158; // [rsp+160h] [rbp+60h]
  void *Src[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v160; // [rsp+178h] [rbp+78h]
  unsigned __int64 v161; // [rsp+180h] [rbp+80h]
  struct _EVENT_DATA_DESCRIPTOR v162; // [rsp+188h] [rbp+88h] BYREF
  __int16 *v163; // [rsp+198h] [rbp+98h]
  int v164; // [rsp+1A0h] [rbp+A0h]
  int v165; // [rsp+1A4h] [rbp+A4h]
  void **v166; // [rsp+1A8h] [rbp+A8h]
  __int64 v167; // [rsp+1B0h] [rbp+B0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+1C0h] [rbp+C0h] BYREF
  char *v169; // [rsp+1D0h] [rbp+D0h]
  int v170; // [rsp+1D8h] [rbp+D8h]
  int v171; // [rsp+1DCh] [rbp+DCh]
  DWORD *v172; // [rsp+1E0h] [rbp+E0h]
  __int64 v173; // [rsp+1E8h] [rbp+E8h]
  unsigned int *v174; // [rsp+1F0h] [rbp+F0h]
  __int64 v175; // [rsp+1F8h] [rbp+F8h]
  LPCWSTR v176; // [rsp+200h] [rbp+100h]
  int v177; // [rsp+208h] [rbp+108h]
  int v178; // [rsp+20Ch] [rbp+10Ch]
  const WCHAR *v179; // [rsp+210h] [rbp+110h]
  int v180; // [rsp+218h] [rbp+118h]
  int v181; // [rsp+21Ch] [rbp+11Ch]
  int *v182; // [rsp+220h] [rbp+120h]
  __int64 v183; // [rsp+228h] [rbp+128h]
  int *v184; // [rsp+230h] [rbp+130h]
  __int64 v185; // [rsp+238h] [rbp+138h]
  int *v186; // [rsp+240h] [rbp+140h]
  __int64 v187; // [rsp+248h] [rbp+148h]
  void **p_pvData; // [rsp+250h] [rbp+150h]
  __int64 v189; // [rsp+258h] [rbp+158h]

  StringSid = this;
  v145 = a2;
  v147 = a3;
  v148 = a4;
  v149 = a5;
  UserAccountType = 0;
  v144 = 0;
  v152 = 0;
  v153 = 0;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x400000000000LL) != 0
    && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
  {
    EventActivityIdControl(3u, &ActivityId);
    v155 = ActivityId;
    EventActivityIdControl(4u, &v155);
    v153 = 1;
  }
  else
  {
    ActivityId = 0;
  }
  v152 = 1;
  v5 = -1;
  if ( (unsigned int)dword_18006E000 > 5
    && (qword_18006E010 & 0x400000000000LL) != 0
    && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
  {
    LODWORD(pvData) = v144;
    v6 = -1;
    if ( v149 )
      v7 = *(_WORD *)v149;
    else
      v7 = -1;
    LOWORD(v137) = v7;
    if ( v148 )
      v8 = *(_WORD *)v148;
    else
      v8 = -1;
    LOWORD(v138) = v8;
    if ( v147 )
      v6 = *v147;
    LOWORD(v136) = v6;
    v9 = (const WCHAR *)v145;
    v10 = StringSid;
    v135 = StringSid != 0;
    pcbData[0] = UserAccountType;
    if ( v153 && (v155.Data1 || *(_DWORD *)&v155.Data2 || *(_DWORD *)v155.Data4 || *(_DWORD *)&v155.Data4[4]) )
      v11 = &v155;
    else
      v11 = 0;
    p_pvData = &pvData;
    v189 = 4;
    v186 = &v137;
    v187 = 2;
    v184 = &v138;
    v185 = 2;
    v182 = &v136;
    v183 = 2;
    if ( v145 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)v145 + v12) );
      v13 = 2 * v12 + 2;
    }
    else
    {
      v9 = &LocaleName;
      v13 = 2;
    }
    v179 = v9;
    v180 = v13;
    v181 = 0;
    if ( StringSid )
    {
      v14 = -1;
      do
        ++v14;
      while ( StringSid[v14] );
      v15 = 2 * v14 + 2;
    }
    else
    {
      v10 = &LocaleName;
      v15 = 2;
    }
    v176 = v10;
    v177 = v15;
    v178 = 0;
    v174 = &v135;
    v175 = 4;
    v172 = pcbData;
    v173 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 261;
    EventDescriptor.Keyword = 0x400000000000LL;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    UserData.Reserved = 2;
    v169 = byte_180062915;
    v170 = 148;
    v171 = 1;
    LODWORD(Size) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, v11, 0xAu, &UserData);
  }
  v150[0] = &v152;
  v150[1] = &UserAccountType;
  v150[2] = &StringSid;
  v150[3] = &v145;
  v150[4] = &v147;
  v150[5] = &v148;
  v150[6] = &v149;
  v150[7] = &v144;
  v151 = 256;
  if ( !v147 || !v148 || !StringSid || !v149 )
  {
    UserAccountType = -2146893785;
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(pvData) = UserAccountType;
      v166 = &pvData;
      v167 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      v162.Ptr = (ULONGLONG)off_18006E008;
      v162.Size = *(unsigned __int16 *)off_18006E008;
      v162.Reserved = 2;
      v163 = (__int16 *)&unk_1800628D8;
      v164 = 49;
      v165 = 1;
      v135 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v162);
    }
    LastError = UserAccountType;
    goto LABEL_331;
  }
  hMem = 0;
  *(_QWORD *)&EventDescriptor.Id = &hMem;
  EventDescriptor.Keyword = 0;
  v140 = 1;
  v16 = ConvertStringSidToSidW(StringSid, (PSID *)&EventDescriptor.Keyword);
  if ( v140 )
  {
    v17 = *(enum NgcUserAccountType **)&EventDescriptor.Id;
    v18 = **(void ***)&EventDescriptor.Id;
    **(_QWORD **)&EventDescriptor.Id = EventDescriptor.Keyword;
    if ( v18 )
      LocalFree(v18);
  }
  if ( !v16 )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(pvData) = LastError;
      v166 = &pvData;
      v167 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      v162.Ptr = (ULONGLONG)off_18006E008;
      v162.Size = *(unsigned __int16 *)off_18006E008;
      v162.Reserved = 2;
      v163 = word_1800628AA;
      v164 = 34;
      v165 = 1;
      v135 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v162);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    UserAccountType = LastError;
LABEL_48:
    v20 = hMem;
    v21 = hMem == 0;
    hMem = 0;
    if ( !v21 )
      LocalFree(v20);
    wil::details::ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4___::operator()(v150);
    if ( v152 != 1 )
      return (unsigned int)LastError;
    if ( v153 )
      EventActivityIdControl(4u, &v155);
    v152 = 2;
    if ( (unsigned int)dword_18006E000 <= 5
      || (qword_18006E010 & 0x400000000000LL) == 0
      || (qword_18006E018 & 0x400000000000LL) != qword_18006E018 )
    {
      return (unsigned int)LastError;
    }
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 0x400000000000LL;
    Src[0] = off_18006E008;
    Src[1] = (void *)(*(unsigned __int16 *)off_18006E008 | 0x200000000LL);
    v160 = (__int64)&dword_18005E36C;
    v161 = 0x100000020LL;
    v22 = (struct _EVENT_DATA_DESCRIPTOR *)Src;
LABEL_338:
    LODWORD(pvData) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, v22);
    return (unsigned int)LastError;
  }
  LODWORD(pvData) = 0;
  UserAccountType = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &pvData, v17);
  if ( UserAccountType < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(pvData) = UserAccountType;
      v166 = &pvData;
      v167 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      v162.Ptr = (ULONGLONG)off_18006E008;
      v162.Size = *(unsigned __int16 *)off_18006E008;
      v162.Reserved = 2;
      v163 = (__int16 *)&unk_180062880;
      v164 = 30;
      v165 = 1;
      v135 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v162);
    }
    LastError = UserAccountType;
    goto LABEL_48;
  }
  v136 = 2;
  v138 = 2;
  pcbData[0] = 2;
  v137 = 2;
  v141 = 2;
  LODWORD(Size) = 2;
  v23 = 0;
  v135 = 0;
  v162.Reserved1 = 1;
  PwdlessPlat::ImageCustomizations::QueryCustomizations((PwdlessPlat::ImageCustomizations *)&v162);
  if ( v162.Reserved1 )
  {
    *(_DWORD *)v147 = 1;
    *(_DWORD *)v148 = 2;
    LOBYTE(v24) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudTrust>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudTrust>::GetImpl'::`2'::impl,
      v24);
    if ( !v145 )
    {
LABEL_156:
      *(_DWORD *)v149 = v23;
      LastError = UserAccountType;
      v72 = hMem;
      hMem = 0;
      if ( v72 )
        LocalFree(v72);
LABEL_331:
      wil::details::ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4___::operator()(v150);
      if ( v152 != 1 )
        return (unsigned int)LastError;
      if ( v153 )
        EventActivityIdControl(4u, &v155);
      v152 = 2;
      if ( (unsigned int)dword_18006E000 <= 5
        || (qword_18006E010 & 0x400000000000LL) == 0
        || (qword_18006E018 & 0x400000000000LL) != qword_18006E018 )
      {
        return (unsigned int)LastError;
      }
      *(_DWORD *)&EventDescriptor.Level = 517;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      v162.Ptr = (ULONGLONG)off_18006E008;
      v162.Size = *(unsigned __int16 *)off_18006E008;
      v163 = (__int16 *)&dword_18005E36C;
      v22 = &v162;
      v165 = 1;
      v164 = 32;
      v162.Reserved = 2;
      goto LABEL_338;
    }
    *(_OWORD *)Src = 0;
    v160 = 0;
    v161 = 0;
    v25 = operator new(0x60u);
    Src[0] = v25;
    v160 = 43;
    v161 = 47;
    *v25 = *(_OWORD *)L"SOFTWARE\\Microsoft\\Policies\\PassportForWork";
    v25[1] = *(_OWORD *)L"\\Microsoft\\Policies\\PassportForWork";
    v25[2] = *(_OWORD *)L"ft\\Policies\\PassportForWork";
    v25[3] = *(_OWORD *)L"ies\\PassportForWork";
    v25[4] = *(_OWORD *)L"portForWork";
    *(_QWORD *)((char *)v25 + 78) = *(_QWORD *)L"Work";
    *((_WORD *)v25 + 43) = 0;
    v26 = v160;
    pvData = (void *)v160;
    v27 = v161;
    v28 = 0x7FFFFFFFFFFFFFFELL;
    v29 = -2;
    if ( v161 != v160 )
    {
      ++v160;
      v30 = Src;
      if ( v161 > 7 )
        v30 = (void **)Src[0];
      *((_WORD *)v30 + v26) = asc_180050E74[0];
      *((_WORD *)v30 + v26 + 1) = 0;
      goto LABEL_88;
    }
    if ( v160 == 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_342;
    *(_QWORD *)&EventDescriptor.Id = v160 + 1;
    v31 = (v160 + 1) | 7;
    if ( v31 > 0x7FFFFFFFFFFFFFFELL || (v32 = v161 >> 1, v161 > 0x7FFFFFFFFFFFFFFELL - (v161 >> 1)) )
    {
      v31 = 0x7FFFFFFFFFFFFFFELL;
      v33 = -2;
    }
    else
    {
      if ( v31 < v32 + v161 )
        v31 = v32 + v161;
      if ( v31 + 1 > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_341;
      v33 = 2 * (v31 + 1);
      if ( !v33 )
      {
        v34 = 0;
LABEL_81:
        v160 = *(_QWORD *)&EventDescriptor.Id;
        v161 = v31;
        v36 = 2LL * (_QWORD)pvData;
        v37 = &v34[2 * (_QWORD)pvData];
        *(_QWORD *)&EventDescriptor.Id = v37;
        pvData = &v34[2 * v160];
        if ( v27 <= 7 )
        {
          memcpy_0(v34, Src, v36);
          *(_WORD *)v37 = asc_180050E74[0];
          *(_WORD *)pvData = 0;
        }
        else
        {
          v38 = Src[0];
          memcpy_0(v34, Src[0], v36);
          **(_WORD **)&EventDescriptor.Id = asc_180050E74[0];
          *(_WORD *)pvData = 0;
          v39 = 2 * v27 + 2;
          if ( v39 < 0x1000 )
          {
            operator delete(v38, v39);
          }
          else
          {
            v40 = (_BYTE *)*((_QWORD *)v38 - 1);
            if ( (unsigned __int64)((_BYTE *)v38 - v40 - 8) > 0x1F )
              goto LABEL_137;
            operator delete(v40, 2 * v27 + 41);
          }
        }
        Src[0] = v34;
LABEL_88:
        v41 = v145;
        do
          ++v5;
        while ( *((_WORD *)v145 + v5) );
        v42 = v160;
        pvData = (void *)v160;
        *(_QWORD *)&EventDescriptor.Id = v161;
        if ( v5 <= v161 - v160 )
        {
          v43 = v5 + v160;
          v160 += v5;
          v44 = Src;
          if ( v161 > 7 )
            v44 = (void **)Src[0];
          memmove_0((char *)v44 + 2 * v42, v145, 2 * v5);
          *((_WORD *)v44 + v43) = 0;
          goto LABEL_116;
        }
        if ( 0x7FFFFFFFFFFFFFFELL - v160 < v5 )
          goto LABEL_342;
        v45 = (v5 + v160) | 7;
        if ( v45 > 0x7FFFFFFFFFFFFFFELL || (v46 = v161 >> 1, v161 > 0x7FFFFFFFFFFFFFFELL - (v161 >> 1)) )
        {
          v45 = 0x7FFFFFFFFFFFFFFELL;
          v47 = -2;
        }
        else
        {
          if ( v45 < v46 + v161 )
            v45 = v46 + v161;
          if ( v45 + 1 > 0x7FFFFFFFFFFFFFFFLL )
            goto LABEL_341;
          v47 = 2 * (v45 + 1);
          if ( !v47 )
          {
            v48 = 0;
LABEL_109:
            v160 = v5 + v42;
            v161 = v45;
            v50 = 2 * v42;
            v51 = 2 * v5;
            Size = 2 * v5;
            pvData = &v48[2 * v42];
            *(_QWORD *)pcbData = &v48[2 * v5 + 2 * v42];
            v52 = *(_QWORD *)&EventDescriptor.Id;
            if ( *(_QWORD *)&EventDescriptor.Id <= 7u )
            {
              memcpy_0(v48, Src, v50);
              memcpy_0(pvData, v41, v51);
              **(_WORD **)pcbData = 0;
            }
            else
            {
              v53 = Src[0];
              memcpy_0(v48, Src[0], v50);
              memcpy_0(pvData, v41, Size);
              **(_WORD **)pcbData = 0;
              v54 = 2 * v52 + 2;
              if ( v54 < 0x1000 )
              {
                operator delete(v53, v54);
              }
              else
              {
                v55 = (_BYTE *)*((_QWORD *)v53 - 1);
                if ( (unsigned __int64)((_BYTE *)v53 - v55 - 8) > 0x1F )
                  goto LABEL_137;
                operator delete(v55, 2 * v52 + 41);
              }
            }
            Src[0] = v48;
LABEL_116:
            v56 = v160;
            v57 = v161;
            if ( v161 - v160 >= 0x10 )
            {
              v58 = v160 + 16;
              v160 += 16;
              v59 = Src;
              if ( v161 > 7 )
                v59 = (void **)Src[0];
              memmove_0((char *)v59 + 2 * v56, L"\\Device\\Policies", 0x20u);
              *((_WORD *)v59 + v58) = 0;
              v60 = Src[0];
              goto LABEL_141;
            }
            if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v160) >= 0x10 )
            {
              v61 = v160 + 16;
              v62 = (v160 + 16) | 7;
              if ( v62 <= 0x7FFFFFFFFFFFFFFELL )
              {
                v63 = v161 >> 1;
                if ( v161 <= 0x7FFFFFFFFFFFFFFELL - (v161 >> 1) )
                {
                  v28 = (v160 + 16) | 7;
                  if ( v62 < v63 + v161 )
                    v28 = v63 + v161;
                  if ( (unsigned __int64)(v28 + 1) > 0x7FFFFFFFFFFFFFFFLL )
                    goto LABEL_341;
                  v29 = 2 * (v28 + 1);
                  if ( !v29 )
                  {
                    v60 = 0;
                    goto LABEL_133;
                  }
                }
              }
              if ( v29 < 0x1000 )
              {
                v60 = operator new(v29);
                goto LABEL_133;
              }
              if ( v29 + 39 >= v29 )
              {
                v64 = operator new(v29 + 39);
                if ( !v64 )
                  goto LABEL_137;
                v60 = (_QWORD *)(((unsigned __int64)v64 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                *(v60 - 1) = v64;
LABEL_133:
                v160 = v56 + 16;
                v161 = v28;
                v65 = 2 * v56;
                v66 = (_WORD *)v60 + v61;
                if ( v57 <= 7 )
                {
                  memcpy_0(v60, Src, v65);
                  *(_OWORD *)((char *)v60 + v65) = *(_OWORD *)L"\\Device\\Policies";
                  *(_OWORD *)((char *)v60 + v65 + 16) = *(_OWORD *)L"Policies";
                  *v66 = 0;
                  goto LABEL_140;
                }
                v67 = Src[0];
                memcpy_0(v60, Src[0], v65);
                *(_OWORD *)((char *)v60 + v65) = *(_OWORD *)L"\\Device\\Policies";
                *(_OWORD *)((char *)v60 + v65 + 16) = *(_OWORD *)L"Policies";
                *v66 = 0;
                v68 = 2 * v57 + 2;
                if ( v68 < 0x1000 )
                {
                  operator delete(v67, v68);
                  goto LABEL_140;
                }
                v69 = (void *)*((_QWORD *)v67 - 1);
                if ( (unsigned __int64)((_BYTE *)v67 - (_BYTE *)v69 - 8) <= 0x1F )
                {
                  operator delete(v69, 2 * v57 + 41);
LABEL_140:
                  Src[0] = v60;
LABEL_141:
                  v70 = Src;
                  if ( v161 > 7 )
                    v70 = (void **)v60;
                  LastError = PolicyManager::ReadEnabledState(-2147483646, v70, L"UseCloudTrustForOnPremAuth", &v141);
                  UserAccountType = LastError;
                  if ( LastError < 0 )
                  {
                    std::wstring::~wstring(Src);
                    v71 = hMem;
                    hMem = 0;
                    if ( v71 )
                      LocalFree(v71);
                    wil::details::ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4___::operator()(v150);
                    if ( v152 == 1 )
                    {
                      if ( v153 )
                        EventActivityIdControl(4u, &v155);
                      v152 = 2;
                      if ( (unsigned int)dword_18006E000 > 5
                        && (qword_18006E010 & 0x400000000000LL) != 0
                        && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
                      {
                        *(_DWORD *)&EventDescriptor.Id = 184549376;
                        *(_DWORD *)&EventDescriptor.Level = 517;
                        EventDescriptor.Keyword = 0x400000000000LL;
                        v162.Ptr = (ULONGLONG)off_18006E008;
                        v162.Size = *(unsigned __int16 *)off_18006E008;
                        v162.Reserved = 2;
                        v163 = (__int16 *)&dword_18005E36C;
                        v164 = 32;
                        v165 = 1;
                        LODWORD(pvData) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                        EventWriteTransfer(RegHandle, &EventDescriptor, &ActivityId, 0, 2u, &v162);
                      }
                    }
                    return (unsigned int)LastError;
                  }
                  v23 = v135;
                  if ( v141 == 1 )
                    v23 = 8;
                  std::wstring::~wstring(Src);
                  goto LABEL_156;
                }
LABEL_137:
                __fastfail(5u);
              }
LABEL_341:
              std::_Throw_bad_array_new_length();
            }
LABEL_342:
            std::_Xlen_string();
          }
        }
        if ( v47 < 0x1000 )
        {
          v48 = (char *)operator new(v47);
        }
        else
        {
          if ( v47 + 39 < v47 )
            goto LABEL_341;
          v49 = operator new(v47 + 39);
          if ( !v49 )
            goto LABEL_137;
          v48 = (char *)(((unsigned __int64)v49 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v48 - 1) = v49;
        }
        v42 = (__int64)pvData;
        goto LABEL_109;
      }
    }
    if ( v33 < 0x1000 )
    {
      v34 = (char *)operator new(v33);
    }
    else
    {
      if ( v33 + 39 < v33 )
        goto LABEL_341;
      v35 = operator new(v33 + 39);
      if ( !v35 )
        goto LABEL_137;
      v34 = (char *)(((unsigned __int64)v35 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *((_QWORD *)v34 - 1) = v35;
    }
    goto LABEL_81;
  }
  std::wstring::wstring(v156, StringSid);
  v73 = v157;
  v74 = v158;
  v75 = 0x7FFFFFFFFFFFFFFELL;
  v76 = -2;
  if ( v158 != v157 )
  {
    v77 = ++v157;
    v78 = v156;
    if ( v158 > 7 )
      v78 = (void **)v156[0];
    *((_WORD *)v78 + v73) = asc_180050E74[0];
    *((_WORD *)v78 + v77) = 0;
    goto LABEL_183;
  }
  if ( v157 == 0x7FFFFFFFFFFFFFFELL )
    goto LABEL_340;
  v79 = (v157 + 1) | 7;
  if ( v79 > 0x7FFFFFFFFFFFFFFELL || (v80 = v158 >> 1, v158 > 0x7FFFFFFFFFFFFFFELL - (v158 >> 1)) )
  {
    v79 = 0x7FFFFFFFFFFFFFFELL;
    v81 = -2;
LABEL_171:
    if ( v81 < 0x1000 )
    {
      v82 = operator new(v81);
    }
    else
    {
      if ( v81 + 39 < v81 )
        goto LABEL_343;
      v83 = operator new(v81 + 39);
      if ( !v83 )
        goto LABEL_205;
      v82 = (_QWORD *)(((unsigned __int64)v83 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v82 - 1) = v83;
    }
    goto LABEL_176;
  }
  if ( v79 < v158 + v80 )
    v79 = v158 + v80;
  if ( v79 + 1 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_343;
  v81 = 2 * (v79 + 1);
  if ( v81 )
    goto LABEL_171;
  v82 = 0;
LABEL_176:
  v157 = v73 + 1;
  v158 = v79;
  v84 = 2 * v73;
  v85 = (_WORD *)v82 + v73;
  v86 = (_WORD *)v82 + v157;
  *(_QWORD *)&EventDescriptor.Id = v86;
  if ( v74 <= 7 )
  {
    memcpy_0(v82, v156, v84);
    *v85 = asc_180050E74[0];
    *v86 = 0;
  }
  else
  {
    v87 = v156[0];
    memcpy_0(v82, v156[0], v84);
    *v85 = asc_180050E74[0];
    **(_WORD **)&EventDescriptor.Id = 0;
    v88 = 2 * v74 + 2;
    if ( v88 < 0x1000 )
    {
      operator delete(v87, v88);
    }
    else
    {
      v89 = (_BYTE *)*((_QWORD *)v87 - 1);
      if ( (unsigned __int64)((_BYTE *)v87 - v89 - 8) > 0x1F )
        goto LABEL_205;
      operator delete(v89, 2 * v74 + 41);
    }
  }
  v156[0] = v82;
LABEL_183:
  v90 = v157;
  v91 = v158;
  if ( v158 - v157 < 0x2B )
  {
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v157) >= 0x2B )
    {
      v96 = (v157 + 43) | 7;
      if ( v96 > 0x7FFFFFFFFFFFFFFELL || (v97 = v158 >> 1, v158 > 0x7FFFFFFFFFFFFFFELL - (v158 >> 1)) )
      {
        v96 = 0x7FFFFFFFFFFFFFFELL;
      }
      else
      {
        if ( v96 < v158 + v97 )
          v96 = v158 + v97;
        if ( v96 + 1 > 0x7FFFFFFFFFFFFFFFLL )
          goto LABEL_343;
        v76 = 2 * (v96 + 1);
        if ( !v76 )
        {
          v95 = 0;
          goto LABEL_201;
        }
      }
      if ( v76 < 0x1000 )
      {
        v95 = operator new(v76);
        goto LABEL_201;
      }
      if ( v76 + 39 >= v76 )
      {
        v98 = operator new(v76 + 39);
        if ( !v98 )
          goto LABEL_205;
        v95 = (_QWORD *)(((unsigned __int64)v98 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v95 - 1) = v98;
LABEL_201:
        v157 = v90 + 43;
        v158 = v96;
        v99 = 2 * v90;
        v100 = (_WORD *)v95 + v157;
        if ( v91 <= 7 )
        {
          memcpy_0(v95, v156, v99);
          *(_OWORD *)((char *)v95 + v99) = *(_OWORD *)L"SOFTWARE\\Policies\\Microsoft\\PassportForWork";
          *(_OWORD *)((char *)v95 + v99 + 16) = *(_OWORD *)L"\\Policies\\Microsoft\\PassportForWork";
          *(_OWORD *)((char *)v95 + v99 + 32) = *(_OWORD *)L"s\\Microsoft\\PassportForWork";
          *(_OWORD *)((char *)v95 + v99 + 48) = *(_OWORD *)L"oft\\PassportForWork";
          *(_OWORD *)((char *)v95 + v99 + 64) = *(_OWORD *)L"portForWork";
          *(_QWORD *)((char *)v95 + v99 + 78) = *(_QWORD *)L"Work";
          *v100 = 0;
          goto LABEL_208;
        }
        v101 = v156[0];
        memcpy_0(v95, v156[0], v99);
        *(_OWORD *)((char *)v95 + v99) = *(_OWORD *)L"SOFTWARE\\Policies\\Microsoft\\PassportForWork";
        *(_OWORD *)((char *)v95 + v99 + 16) = *(_OWORD *)L"\\Policies\\Microsoft\\PassportForWork";
        *(_OWORD *)((char *)v95 + v99 + 32) = *(_OWORD *)L"s\\Microsoft\\PassportForWork";
        *(_OWORD *)((char *)v95 + v99 + 48) = *(_OWORD *)L"oft\\PassportForWork";
        *(_OWORD *)((char *)v95 + v99 + 64) = *(_OWORD *)L"portForWork";
        *(_QWORD *)((char *)v95 + v99 + 78) = *(_QWORD *)L"Work";
        *v100 = 0;
        v102 = 2 * v91 + 2;
        if ( v102 < 0x1000 )
        {
          operator delete(v101, v102);
          goto LABEL_208;
        }
        v103 = (void *)*((_QWORD *)v101 - 1);
        if ( (unsigned __int64)((_BYTE *)v101 - (_BYTE *)v103 - 8) <= 0x1F )
        {
          operator delete(v103, 2 * v91 + 41);
LABEL_208:
          v94 = 0;
          v156[0] = v95;
          goto LABEL_209;
        }
LABEL_205:
        __fastfail(5u);
      }
LABEL_343:
      std::_Throw_bad_array_new_length();
    }
LABEL_340:
    std::_Xlen_string();
  }
  v92 = v157 + 43;
  v157 += 43;
  v93 = v156;
  if ( v158 > 7 )
    v93 = (void **)v156[0];
  memmove_0((char *)v93 + 2 * v90, L"SOFTWARE\\Policies\\Microsoft\\PassportForWork", 0x56u);
  v94 = 0;
  *((_WORD *)v93 + v92) = 0;
  v95 = v156[0];
LABEL_209:
  v104 = v156;
  if ( v158 > 7 )
    v104 = (void **)v95;
  LastError = PolicyManager::ReadEnabledState(-2147483645, v104, L"Enabled", &v136);
  UserAccountType = LastError;
  if ( LastError < 0 )
    goto LABEL_212;
  v106 = v156;
  if ( v158 > 7 )
    v106 = (void **)v156[0];
  LastError = PolicyManager::ReadEnabledState(-2147483645, v106, L"DisablePostLogonProvisioning", &v138);
  UserAccountType = LastError;
  if ( LastError < 0 )
    goto LABEL_212;
  v107 = v156;
  if ( v158 > 7 )
    v107 = (void **)v156[0];
  LastError = PolicyManager::ReadEnabledState(-2147483645, v107, L"UseCertificateForOnPremAuth", &v137);
  UserAccountType = LastError;
  if ( LastError < 0 )
    goto LABEL_212;
  v108 = v138;
  v109 = v137;
  v110 = v136;
  if ( v136 == 2 || v138 == 2 || v137 == 2 )
  {
    *(_QWORD *)&EventDescriptor.Id = 0;
    v144 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0x20019u, (PHKEY)&EventDescriptor);
    if ( *(_QWORD *)&EventDescriptor.Id )
      RegCloseKey(*(HKEY *)&EventDescriptor.Id);
  }
  if ( v110 == 2 )
  {
    LastError = PolicyManager::ReadEnabledState(
                  -2147483646,
                  L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                  L"Enabled",
                  &v136);
    UserAccountType = LastError;
    if ( LastError < 0 )
    {
LABEL_212:
      std::wstring::~wstring(v156);
      v105 = hMem;
      hMem = 0;
      if ( v105 )
        LocalFree(v105);
      wil::details::ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4___::operator()(v150);
      if ( v152 == 1 )
      {
        if ( v153 )
          EventActivityIdControl(4u, &v155);
        v152 = 2;
        if ( (unsigned int)dword_18006E000 > 5
          && (qword_18006E010 & 0x400000000000LL) != 0
          && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
        {
          tlgWriteTransfer_EventWriteTransfer(&dword_18006E000, &byte_18005E361, &ActivityId, 0, 2, &v162);
        }
      }
      return (unsigned int)LastError;
    }
    v110 = v136;
  }
  if ( v108 != 2 )
  {
LABEL_248:
    EnabledState = PolicyManager::ReadEnabledState(
                     -2147483646,
                     L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                     L"DisablePostLogonCredentialCaching",
                     pcbData);
    UserAccountType = EnabledState;
    if ( EnabledState < 0 )
      goto LABEL_237;
    if ( v109 == 2 )
    {
      EnabledState = PolicyManager::ReadEnabledState(
                       -2147483646,
                       L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                       L"UseCertificateForOnPremAuth",
                       &v137);
      UserAccountType = EnabledState;
      if ( EnabledState < 0 )
        goto LABEL_237;
      v109 = v137;
    }
    EnabledState = PolicyManager::ReadEnabledState(
                     -2147483646,
                     L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                     L"UseCloudTrustForOnPremAuth",
                     &v141);
    UserAccountType = EnabledState;
    if ( EnabledState < 0 )
      goto LABEL_237;
    EnabledState = PolicyManager::ReadEnabledState(
                     -2147483646,
                     L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                     L"UseHelloCertificatesAsSmartCardCertificates",
                     &Size);
    UserAccountType = EnabledState;
    if ( EnabledState < 0 )
      goto LABEL_237;
    if ( v110 != 2 )
    {
      v94 = 1;
      goto LABEL_305;
    }
    if ( !v145 )
      goto LABEL_306;
    LODWORD(Size) = 2;
    v115 = v158;
    if ( v158 < 0x2B )
    {
      v117 = v158 >> 1;
      if ( v158 <= 0x7FFFFFFFFFFFFFFELL - (v158 >> 1) )
      {
        v75 = 47;
        if ( v117 + v158 > 0x2F )
          v75 = v117 + v158;
      }
      v119 = (char *)std::allocator<unsigned short>::allocate(v117, v75 + 1);
      v157 = 43;
      v158 = v75;
      *(_OWORD *)v119 = *(_OWORD *)L"SOFTWARE\\Microsoft\\Policies\\PassportForWork";
      *((_OWORD *)v119 + 1) = *(_OWORD *)L"\\Microsoft\\Policies\\PassportForWork";
      *((_OWORD *)v119 + 2) = *(_OWORD *)L"ft\\Policies\\PassportForWork";
      *((_OWORD *)v119 + 3) = *(_OWORD *)L"ies\\PassportForWork";
      *((_OWORD *)v119 + 4) = *(_OWORD *)L"portForWork";
      *(_QWORD *)(v119 + 78) = *(_QWORD *)L"Work";
      *((_WORD *)v119 + 43) = 0;
      if ( v115 > 7 )
        std::wstring::_Deallocate_for_capacity(v118, v156[0], v115);
      v156[0] = v119;
    }
    else
    {
      v116 = v156[0];
      v157 = 43;
      memmove_0(v156[0], L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 0x56u);
      v116[43] = 0;
    }
    std::wstring::_Append<unsigned short>(v156);
    v120 = -1;
    do
      ++v120;
    while ( *((_WORD *)v145 + v120) );
    std::wstring::_Append<unsigned short>(v156);
    std::wstring::_Append<unsigned short>(v156);
    v121 = -1;
    do
      ++v121;
    while ( StringSid[v121] );
    std::wstring::_Append<unsigned short>(v156);
    std::wstring::_Append<unsigned short>(v156);
    v122 = v156;
    if ( v158 > 7 )
      v122 = (void **)v156[0];
    LastError = PolicyManager::ReadEnabledState(-2147483646, v122, L"UsePassportForWork", &v136);
    UserAccountType = LastError;
    if ( LastError < 0 )
      goto LABEL_212;
    *(_OWORD *)Src = 0;
    v160 = 0;
    v161 = 0;
    std::wstring::_Construct<1,unsigned short const *>(Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork", 43);
    std::wstring::_Append<unsigned short>(Src);
    do
      ++v5;
    while ( *((_WORD *)v145 + v5) );
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    v110 = v136;
    if ( v136 == 2 )
    {
      v123 = Src;
      if ( v161 > 7 )
        v123 = (void **)Src[0];
      LastError = PolicyManager::ReadEnabledState(-2147483646, v123, L"UsePassportForWork", &v136);
      UserAccountType = LastError;
      if ( LastError < 0 )
      {
        std::wstring::~wstring(Src);
        goto LABEL_212;
      }
      v110 = v136;
    }
    if ( v108 == 2 )
    {
      v124 = Src;
      if ( v161 > 7 )
        v124 = (void **)Src[0];
      EnabledState = PolicyManager::ReadEnabledState(-2147483646, v124, L"DisablePostLogonProvisioning", &v138);
      UserAccountType = EnabledState;
      if ( EnabledState < 0 )
        goto LABEL_284;
      v108 = v138;
    }
    if ( pcbData[0] != 2 )
      goto LABEL_290;
    v125 = Src;
    if ( v161 > 7 )
      v125 = (void **)Src[0];
    EnabledState = PolicyManager::ReadEnabledState(-2147483646, v125, L"DisablePostLogonCredentialCaching", pcbData);
    UserAccountType = EnabledState;
    if ( EnabledState >= 0 )
    {
LABEL_290:
      if ( v109 == 2 )
      {
        v126 = Src;
        if ( v161 > 7 )
          v126 = (void **)Src[0];
        EnabledState = PolicyManager::ReadEnabledState(-2147483646, v126, L"UseCertificateForOnPremAuth", &v137);
        UserAccountType = EnabledState;
        if ( EnabledState < 0 )
          goto LABEL_284;
        v109 = v137;
      }
      if ( v141 != 2 )
        goto LABEL_346;
      v127 = Src;
      if ( v161 > 7 )
        v127 = (void **)Src[0];
      EnabledState = PolicyManager::ReadEnabledState(-2147483646, v127, L"UseCloudTrustForOnPremAuth", &v141);
      UserAccountType = EnabledState;
      if ( EnabledState >= 0 )
      {
LABEL_346:
        v128 = Src;
        if ( v161 > 7 )
          v128 = (void **)Src[0];
        EnabledState = PolicyManager::ReadEnabledState(
                         -2147483646,
                         v128,
                         L"UseHelloCertificatesAsSmartCardCertificates",
                         &Size);
        UserAccountType = EnabledState;
        if ( EnabledState >= 0 )
        {
          if ( v110 != 2 )
            v94 = 2;
          std::wstring::~wstring(Src);
LABEL_305:
          if ( v110 != 2 )
          {
LABEL_315:
            v130 = v135;
            if ( v108 == 1 && v110 == 1 )
              v130 = 1;
            if ( v109 == 1 )
              v130 |= 2u;
            LOBYTE(v114) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudTrust>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_CloudTrust>::GetImpl'::`2'::impl,
              v114);
            if ( v141 == 1 )
            {
              if ( v109 == 1 )
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 8) != 0 )
                  McTemplateU0_EventWriteTransfer(v131, EVENT_HFB_QUERYPOLICY_WARNING);
              }
              else
              {
                v130 |= 8u;
              }
            }
            if ( (_DWORD)Size == 1 )
              v130 |= 4u;
            *(_DWORD *)v147 = v110;
            *(_DWORD *)v148 = v94;
            *(_DWORD *)v149 = v130;
            LastError = UserAccountType;
            goto LABEL_212;
          }
LABEL_306:
          if ( (_DWORD)pvData == 3 )
          {
            LODWORD(pvData) = 0;
            pcbData[0] = 4;
            ValueW = RegGetValueW(
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Policies\\Microsoft\\Windows\\System",
                       L"AllowDomainPINLogon",
                       0x10u,
                       0,
                       &pvData,
                       pcbData);
            EnabledState = ValueW;
            if ( ValueW < 0 )
            {
              if ( (unsigned int)dword_18006E000 > 2 )
              {
                v135 = ValueW;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_18006E000,
                  (unsigned int)byte_180062851,
                  0,
                  0,
                  (__int64)&v135);
              }
              UserAccountType = EnabledState;
              goto LABEL_237;
            }
            if ( !(_DWORD)pvData )
            {
              if ( (unsigned int)dword_18006E000 > 4 )
                tlgWriteTransfer_EventWriteTransfer(&dword_18006E000, &unk_180062820, 0, 0, 2, &v162);
              v110 = 0;
              v94 = 3;
            }
          }
          goto LABEL_315;
        }
      }
    }
LABEL_284:
    std::wstring::~wstring(Src);
    goto LABEL_237;
  }
  EnabledState = PolicyManager::ReadEnabledState(
                   -2147483646,
                   L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                   L"DisablePostLogonProvisioning",
                   &v138);
  UserAccountType = EnabledState;
  if ( EnabledState >= 0 )
  {
    v108 = v138;
    goto LABEL_248;
  }
LABEL_237:
  std::wstring::~wstring(v156);
  v112 = hMem;
  hMem = 0;
  if ( v112 )
    LocalFree(v112);
  wil::details::ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4___::operator()(v150);
  if ( v152 == 1 )
  {
    if ( v153 )
      EventActivityIdControl(4u, &v155);
    v152 = 2;
    if ( (unsigned int)dword_18006E000 > 5
      && (qword_18006E010 & 0x400000000000LL) != 0
      && (qword_18006E018 & 0x400000000000LL) == qword_18006E018 )
    {
      tlgWriteTransfer_EventWriteTransfer(&dword_18006E000, &byte_18005E361, &ActivityId, 0, 2, &v162);
    }
  }
  return (unsigned int)EnabledState;
}

```

## disassembly

```asm
0x180021a80  push    rbp
0x180021a82  push    rbx
0x180021a83  push    rsi
0x180021a84  push    rdi
0x180021a85  push    r12
0x180021a87  push    r13
0x180021a89  push    r14
0x180021a8b  push    r15
0x180021a8d  lea     rbp, [rsp-178h]
0x180021a95  sub     rsp, 278h
0x180021a9c  mov     rax, cs:__security_cookie
0x180021aa3  xor     rax, rsp
0x180021aa6  mov     [rbp+1B0h+var_50], rax
0x180021aad  mov     [rbp+1B0h+StringSid], rcx
0x180021ab1  mov     [rbp+1B0h+var_210], rdx
0x180021ab5  mov     [rbp+1B0h+var_200], r8
0x180021ab9  mov     [rbp+1B0h+var_1F8], r9
0x180021abd  mov     rax, [rbp+1B0h+arg_20]
0x180021ac4  mov     [rbp+1B0h+var_1F0], rax
0x180021ac8  xor     r14d, r14d
0x180021acb  mov     [rsp+2B0h+var_270], r14d
0x180021ad0  mov     [rbp+1B0h+var_218], r14d
0x180021ad4  mov     [rbp+1B0h+var_190], r14d
0x180021ad8  mov     [rbp+1B0h+var_18C], r14b
0x180021adc  mov     eax, cs:dword_18006E000
0x180021ae2  mov     rsi, 400000000000h
0x180021aec  cmp     eax, 5
0x180021aef  jbe     short loc_180021B4B
0x180021af1  mov     rcx, cs:qword_18006E018
0x180021af8  mov     rax, cs:qword_18006E010
0x180021aff  test    rsi, rax
0x180021b02  jz      short loc_180021B4B
0x180021b04  mov     rax, rcx
0x180021b07  and     rax, rsi
0x180021b0a  cmp     rax, rcx
0x180021b0d  jnz     short loc_180021B4B
0x180021b0f  lea     rdx, [rbp+1B0h+ActivityId]; ActivityId
0x180021b13  mov     ecx, 3; ControlCode
0x180021b18  call    cs:__imp_EventActivityIdControl
0x180021b1e  mov     eax, [rbp+1B0h+ActivityId.Data1]
0x180021b21  mov     [rbp+1B0h+var_178.Data1], eax
0x180021b24  mov     eax, dword ptr [rbp+1B0h+ActivityId.Data2]
0x180021b27  mov     dword ptr [rbp+1B0h+var_178.Data2], eax
0x180021b2a  mov     eax, dword ptr [rbp+1B0h+ActivityId.Data4]
0x180021b2d  mov     dword ptr [rbp+1B0h+var_178.Data4], eax
0x180021b30  mov     eax, dword ptr [rbp+1B0h+ActivityId.Data4+4]
0x180021b33  mov     dword ptr [rbp+1B0h+var_178.Data4+4], eax
0x180021b36  lea     rdx, [rbp+1B0h+var_178]; ActivityId
0x180021b3a  mov     ecx, 4; ControlCode
0x180021b3f  call    cs:__imp_EventActivityIdControl
0x180021b45  mov     [rbp+1B0h+var_18C], 1
0x180021b49  jmp     short loc_180021B52
0x180021b4b  xorps   xmm0, xmm0
0x180021b4e  movups  xmmword ptr [rbp+1B0h+ActivityId.Data1], xmm0
0x180021b52  mov     r8d, 1
0x180021b58  mov     [rbp+1B0h+var_190], r8d
0x180021b5c  mov     eax, cs:dword_18006E000
0x180021b62  mov     edi, 2
0x180021b67  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180021b6e  lea     r13, _TraceLoggingMetadataEnd
0x180021b75  lea     r12, _TraceLoggingMetadata
0x180021b7c  cmp     eax, 5
0x180021b7f  jbe     loc_180021DBE
0x180021b85  mov     rcx, cs:qword_18006E018
0x180021b8c  mov     rax, cs:qword_18006E010
0x180021b93  test    rsi, rax
0x180021b96  jz      loc_180021DBE
0x180021b9c  mov     rax, rcx
0x180021b9f  and     rax, rsi
0x180021ba2  cmp     rax, rcx
0x180021ba5  jnz     loc_180021DBE
0x180021bab  mov     eax, [rbp+1B0h+var_218]
0x180021bae  mov     dword ptr [rsp+2B0h+pvData], eax
0x180021bb2  mov     eax, 0FFFFh
0x180021bb7  mov     rcx, [rbp+1B0h+var_1F0]
0x180021bbb  test    rcx, rcx
0x180021bbe  jz      short loc_180021BC5
0x180021bc0  movzx   edx, word ptr [rcx]
0x180021bc3  jmp     short loc_180021BC7
0x180021bc5  mov     edx, eax
0x180021bc7  mov     word ptr [rsp+2B0h+var_250], dx
0x180021bcc  mov     rcx, [rbp+1B0h+var_1F8]
0x180021bd0  test    rcx, rcx
0x180021bd3  jz      short loc_180021BDA
0x180021bd5  movzx   edx, word ptr [rcx]
0x180021bd8  jmp     short loc_180021BDC
0x180021bda  mov     edx, eax
0x180021bdc  mov     word ptr [rsp+2B0h+var_24C], dx
0x180021be1  mov     rcx, [rbp+1B0h+var_200]
0x180021be5  test    rcx, rcx
0x180021be8  jz      short loc_180021BED
0x180021bea  movzx   eax, word ptr [rcx]
0x180021bed  mov     word ptr [rsp+2B0h+var_254], ax
0x180021bf2  mov     rdx, [rbp+1B0h+var_210]
0x180021bf6  mov     rcx, [rbp+1B0h+StringSid]
0x180021bfa  mov     eax, r14d
0x180021bfd  test    rcx, rcx
0x180021c00  setnz   al
0x180021c03  mov     [rsp+2B0h+var_258], eax
0x180021c07  mov     eax, [rsp+2B0h+var_270]
0x180021c0b  mov     [rbp+1B0h+var_228], eax
0x180021c0e  cmp     [rbp+1B0h+var_18C], 0
0x180021c12  jz      short loc_180021C32
0x180021c14  cmp     [rbp+1B0h+var_178.Data1], 0
0x180021c18  jnz     short loc_180021C2C
0x180021c1a  cmp     dword ptr [rbp+1B0h+var_178.Data2], 0
0x180021c1e  jnz     short loc_180021C2C
0x180021c20  cmp     dword ptr [rbp+1B0h+var_178.Data4], 0
0x180021c24  jnz     short loc_180021C2C
0x180021c26  cmp     dword ptr [rbp+1B0h+var_178.Data4+4], 0
0x180021c2a  jz      short loc_180021C32
0x180021c2c  lea     r9, [rbp+1B0h+var_178]
0x180021c30  jmp     short loc_180021C35
0x180021c32  mov     r9, r14; RelatedActivityId
0x180021c35  lea     rax, [rsp+2B0h+pvData]
0x180021c3a  mov     [rbp+1B0h+var_60], rax
0x180021c41  mov     [rbp+1B0h+var_58], 4
0x180021c4c  lea     rax, [rsp+2B0h+var_250]
0x180021c51  mov     [rbp+1B0h+var_70], rax
0x180021c58  mov     [rbp+1B0h+var_68], rdi
0x180021c5f  lea     rax, [rsp+2B0h+var_24C]
0x180021c64  mov     [rbp+1B0h+var_80], rax
0x180021c6b  mov     [rbp+1B0h+var_78], rdi
0x180021c72  lea     rax, [rsp+2B0h+var_254]
0x180021c77  mov     [rbp+1B0h+var_90], rax
0x180021c7e  mov     [rbp+1B0h+var_88], rdi
0x180021c85  test    rdx, rdx
0x180021c88  jz      short loc_180021CA4
0x180021c8a  mov     rax, r15
0x180021c8d  nop     dword ptr [rax]
0x180021c90  lea     rax, [rax+1]
0x180021c94  cmp     word ptr [rdx+rax*2], 0
0x180021c99  jnz     short loc_180021C90
0x180021c9b  lea     eax, ds:2[rax*2]
0x180021ca2  jmp     short loc_180021CAD
0x180021ca4  lea     rdx, LocaleName
0x180021cab  mov     eax, edi
0x180021cad  mov     [rbp+1B0h+var_A0], rdx
0x180021cb4  mov     [rbp+1B0h+var_98], eax
0x180021cba  mov     [rbp+1B0h+var_94], r14d
0x180021cc1  test    rcx, rcx
0x180021cc4  jz      short loc_180021CE4
0x180021cc6  mov     rax, r15
0x180021cc9  nop     dword ptr [rax+00000000h]
0x180021cd0  lea     rax, [rax+1]
0x180021cd4  cmp     word ptr [rcx+rax*2], 0
0x180021cd9  jnz     short loc_180021CD0
0x180021cdb  lea     eax, ds:2[rax*2]
0x180021ce2  jmp     short loc_180021CED
0x180021ce4  lea     rcx, LocaleName
0x180021ceb  mov     eax, edi
0x180021ced  mov     [rbp+1B0h+var_B0], rcx
0x180021cf4  mov     [rbp+1B0h+var_A8], eax
0x180021cfa  mov     [rbp+1B0h+var_A4], r14d
0x180021d01  lea     rax, [rsp+2B0h+var_258]
0x180021d06  mov     [rbp+1B0h+var_C0], rax
0x180021d0d  mov     [rbp+1B0h+var_B8], 4
0x180021d18  lea     rax, [rbp+1B0h+var_228]
0x180021d1c  mov     [rbp+1B0h+var_D0], rax
0x180021d23  mov     [rbp+1B0h+var_C8], 4
0x180021d2e  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x180021d36  movzx   eax, cs:word_18006290B
0x180021d3d  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
0x180021d41  mov     [rsp+2B0h+EventDescriptor.Keyword], rsi
0x180021d46  mov     rax, cs:off_18006E008
0x180021d4d  mov     [rbp+1B0h+var_F0.Ptr], rax
0x180021d54  movzx   eax, word ptr [rax]
0x180021d57  mov     [rbp+1B0h+var_F0.Size], eax
0x180021d5d  mov     dword ptr [rbp+1B0h+var_F0.0Ch], edi
0x180021d63  lea     rax, byte_180062915
0x180021d6a  mov     [rbp+1B0h+var_E0], rax
0x180021d71  mov     [rbp+1B0h+var_D8], 94h
0x180021d7b  mov     [rbp+1B0h+var_D4], r8d
0x180021d82  mov     rax, r13
0x180021d85  sub     eax, r12d
0x180021d88  mov     dword ptr [rbp+1B0h+Size], eax
0x180021d8b  mov     eax, dword ptr [rbp+1B0h+Size]
0x180021d8e  lea     rax, [rbp+1B0h+var_F0]
0x180021d95  mov     [rsp+2B0h+UserData], rax; UserData
0x180021d9a  mov     [rsp+2B0h+UserDataCount], 0Ah; UserDataCount
0x180021da2  lea     r8, [rbp+1B0h+ActivityId]; ActivityId
0x180021da6  lea     rdx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x180021dab  mov     rcx, cs:RegHandle; RegHandle
0x180021db2  call    cs:__imp_EventWriteTransfer
0x180021db8  mov     r8d, 1
0x180021dbe  lea     rax, [rbp+1B0h+var_190]
0x180021dc2  mov     [rbp+1B0h+var_1E0], rax
0x180021dc6  lea     rax, [rsp+2B0h+var_270]
0x180021dcb  mov     [rbp+1B0h+var_1D8], rax
0x180021dcf  lea     rax, [rbp+1B0h+StringSid]
0x180021dd3  mov     [rbp+1B0h+var_1D0], rax
0x180021dd7  lea     rax, [rbp+1B0h+var_210]
0x180021ddb  mov     [rbp+1B0h+var_1C8], rax
0x180021ddf  lea     rax, [rbp+1B0h+var_200]
0x180021de3  mov     [rbp+1B0h+var_1C0], rax
0x180021de7  lea     rax, [rbp+1B0h+var_1F8]
0x180021deb  mov     [rbp+1B0h+var_1B8], rax
0x180021def  lea     rax, [rbp+1B0h+var_1F0]
0x180021df3  mov     [rbp+1B0h+var_1B0], rax
0x180021df7  lea     rax, [rbp+1B0h+var_218]
0x180021dfb  mov     [rbp+1B0h+var_1A8], rax
0x180021dff  mov     [rbp+1B0h+var_1A0], 100h
0x180021e05  cmp     [rbp+1B0h+var_200], 0
0x180021e0a  jz      loc_18002351C
0x180021e10  cmp     [rbp+1B0h+var_1F8], 0
0x180021e15  jz      loc_18002351C
0x180021e1b  mov     rcx, [rbp+1B0h+StringSid]; StringSid
0x180021e1f  test    rcx, rcx
0x180021e22  jz      loc_18002351C
0x180021e28  cmp     [rbp+1B0h+var_1F0], 0
0x180021e2d  jz      loc_18002351C
0x180021e33  mov     [rsp+2B0h+hMem], r14
0x180021e38  lea     rax, [rsp+2B0h+hMem]
0x180021e3d  mov     qword ptr [rsp+2B0h+EventDescriptor.Id], rax
0x180021e42  mov     [rsp+2B0h+EventDescriptor.Keyword], r14
0x180021e47  mov     [rsp+2B0h+var_238], 1
0x180021e4c  lea     rdx, [rsp+2B0h+EventDescriptor.Keyword]; Sid
0x180021e51  call    cs:__imp_ConvertStringSidToSidW
0x180021e57  mov     ebx, eax
0x180021e59  cmp     [rsp+2B0h+var_238], 0
0x180021e5e  jz      short loc_180021E7B
0x180021e60  mov     r8, qword ptr [rsp+2B0h+EventDescriptor.Id]
0x180021e65  mov     rcx, [r8]; hMem
0x180021e68  mov     rdx, [rsp+2B0h+EventDescriptor.Keyword]
0x180021e6d  mov     [r8], rdx
0x180021e70  test    rcx, rcx
0x180021e73  jz      short loc_180021E7B
0x180021e75  call    cs:__imp_LocalFree
0x180021e7b  test    ebx, ebx
0x180021e7d  jnz     loc_180022022
0x180021e83  call    cs:__imp_GetLastError
0x180021e89  mov     ebx, eax
0x180021e8b  mov     eax, cs:dword_18006E000
0x180021e91  cmp     eax, 2
0x180021e94  jbe     loc_180021F46
0x180021e9a  mov     dword ptr [rsp+2B0h+pvData], ebx
0x180021e9e  lea     rax, [rsp+2B0h+pvData]
0x180021ea3  mov     [rbp+1B0h+var_108], rax
0x180021eaa  mov     [rbp+1B0h+var_100], 4
0x180021eb5  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x180021ebd  movzx   eax, cs:word_1800628A0
0x180021ec4  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
0x180021ec8  mov     [rsp+2B0h+EventDescriptor.Keyword], r14
0x180021ecd  mov     rax, cs:off_18006E008
0x180021ed4  mov     [rbp+1B0h+var_128.Ptr], rax
0x180021edb  movzx   eax, word ptr [rax]
0x180021ede  mov     [rbp+1B0h+var_128.Size], eax
0x180021ee4  mov     dword ptr [rbp+1B0h+var_128.0Ch], edi
0x180021eea  lea     rax, word_1800628AA
0x180021ef1  mov     [rbp+1B0h+var_118], rax
0x180021ef8  mov     [rbp+1B0h+var_110], 22h ; '"'
0x180021f02  mov     [rbp+1B0h+var_10C], 1
0x180021f0c  mov     rax, r13
0x180021f0f  sub     eax, r12d
0x180021f12  mov     [rsp+2B0h+var_258], eax
0x180021f16  mov     eax, [rsp+2B0h+var_258]
0x180021f1a  lea     rax, [rbp+1B0h+var_128]
0x180021f21  mov     [rsp+2B0h+UserData], rax; UserData
0x180021f26  mov     [rsp+2B0h+UserDataCount], 3; UserDataCount
0x180021f2e  xor     r9d, r9d; RelatedActivityId
0x180021f31  xor     r8d, r8d; ActivityId
0x180021f34  lea     rdx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x180021f39  mov     rcx, cs:RegHandle; RegHandle
0x180021f40  call    cs:__imp_EventWriteTransfer
0x180021f46  test    ebx, ebx
0x180021f48  jle     short loc_180021F53
0x180021f4a  movzx   ebx, bx
0x180021f4d  or      ebx, 80070000h
0x180021f53  mov     [rsp+2B0h+var_270], ebx
0x180021f57  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180021f5c  test    rcx, rcx
0x180021f5f  mov     [rsp+2B0h+hMem], r14
0x180021f64  jz      short loc_180021F6D
0x180021f66  call    cs:__imp_LocalFree
0x180021f6c  nop
0x180021f6d  lea     rcx, [rbp+1B0h+var_1E0]
0x180021f71  call    wil__details__ScopeExitFnGuard__lambda_e1b2f06b0a359e81d4a1b4dd596df8d4_____operator__
0x180021f76  nop
0x180021f77  cmp     [rbp+1B0h+var_190], 1
0x180021f7b  jnz     loc_1800236D1
0x180021f81  cmp     [rbp+1B0h+var_18C], 0
0x180021f85  jz      short loc_180021F96
0x180021f87  lea     rdx, [rbp+1B0h+var_178]; ActivityId
0x180021f8b  mov     ecx, 4; ControlCode
0x180021f90  call    cs:__imp_EventActivityIdControl
0x180021f96  mov     [rbp+1B0h+var_190], edi
0x180021f99  mov     eax, cs:dword_18006E000
0x180021f9f  cmp     eax, 5
0x180021fa2  jbe     loc_1800236D1
0x180021fa8  mov     rcx, cs:qword_18006E018
0x180021faf  mov     rax, cs:qword_18006E010
0x180021fb6  test    rsi, rax
0x180021fb9  jz      loc_1800236D1
0x180021fbf  mov     rax, rcx
0x180021fc2  and     rax, rsi
0x180021fc5  cmp     rax, rcx
0x180021fc8  jnz     loc_1800236D1
0x180021fce  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x180021fd6  movzx   eax, cs:word_18005E362
0x180021fdd  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
  ... truncated ...
```
