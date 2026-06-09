# CreateCoreResTypes

- ea: `0x18003628c`
- end: `0x180036c84`
- name: `CreateCoreResTypes`
- size: `2552`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18003359c`
- `0x18003bf50`

## callees

- `0x180002f50`
- `0x180014638`
- `0x18001b4d8`
- `0x18001cb44`
- `0x180028f30`
- `0x180029578`
- `0x180029978`
- `0x18003628c`
- `0x18003dd38`
- `0x18003e4a4`
- `0x18006c790`
- `0x18006f910`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c0f`

## string_xrefs

- `0x180036960`: `DumpServices`
- `0x18003644b`: `CreateCoreResTypes`
- `0x18003673d`: `CreateCoreResTypes`
- `0x180036808`: `CreateCoreResTypes`
- `0x1800368dc`: `CreateCoreResTypes`
- `0x1800369b0`: `CreateCoreResTypes`
- `0x180036a6a`: `CreateCoreResTypes`
- `0x180036b35`: `CreateCoreResTypes`
- `0x180036c40`: `CreateCoreResTypes`
- `0x180036471`: `clusapi!CreateCoreResTypes`
- `0x180036c29`: `Failed to create resource type '%ws'. Error %d.`
- `0x180036b76`: `Failed to set admin extension for resource type '%ws'. Error %d.`
- `0x18003699e`: `Failed to set DumpServices for resource type '%ws'. Error %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateCoreResTypes(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  char v4; // r15
  __int64 v5; // r10
  _WORD *v6; // r9
  struct _HCLUSTER **v7; // r13
  unsigned int v8; // ebx
  unsigned int v9; // edi
  const WCHAR *v10; // rsi
  __int64 v11; // r14
  wchar_t *v12; // rax
  int v13; // eax
  _QWORD *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r14
  const WCHAR *v17; // rax
  unsigned int ClusterResourceType; // eax
  __int64 v19; // rcx
  wchar_t *v20; // r14
  struct _HCLUSTER *v21; // rbx
  __int64 v22; // rcx
  wchar_t *v23; // r14
  struct _HCLUSTER *v24; // rbx
  __int64 v25; // rcx
  wchar_t *v26; // r14
  struct _HCLUSTER *v27; // rbx
  __int64 v28; // rcx
  wchar_t *v29; // r14
  struct _HCLUSTER *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // rcx
  wchar_t *v33; // r14
  struct _HCLUSTER *v34; // rbx
  int v35; // eax
  __int64 v36; // rdx
  const WCHAR *v37; // rcx
  unsigned int v38; // r14d
  __int64 v39; // r15
  __int64 v40; // rcx
  wchar_t *v41; // r12
  struct _HCLUSTER *v42; // rbx
  int v43; // eax
  __int64 v44; // rdx
  const WCHAR *v45; // rcx
  unsigned int v46; // r14d
  __int64 v47; // r15
  __int64 v48; // rcx
  wchar_t *v49; // r12
  struct _HCLUSTER *v50; // rbx
  int v51; // eax
  __int64 v52; // rdx
  const WCHAR *v53; // rcx
  unsigned int v54; // r14d
  __int64 v55; // r15
  __int64 v56; // rcx
  wchar_t *v57; // r12
  struct _HCLUSTER *v58; // rbx
  int v59; // eax
  __int64 v60; // rdx
  const WCHAR *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  wchar_t *v64; // r14
  struct _HCLUSTER *v65; // rbx
  int v66; // eax
  __int64 v67; // rdx
  const WCHAR *v68; // rcx
  unsigned int v69; // r14d
  wchar_t *v70; // r15
  __int64 v71; // rcx
  wchar_t *v72; // r12
  struct _HCLUSTER *v73; // rbx
  int v74; // eax
  __int64 v75; // rdx
  const WCHAR *v76; // rcx
  const wchar_t *v77; // rax
  __int64 v78; // r9
  __int64 v79; // rdx
  DWORD LastError; // eax
  wchar_t *v82; // [rsp+30h] [rbp-49h]
  __int64 v84; // [rsp+48h] [rbp-31h] BYREF
  _WORD *v85; // [rsp+50h] [rbp-29h]
  __int64 v86; // [rsp+58h] [rbp-21h]
  char v87[16]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v88[16]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v89; // [rsp+80h] [rbp+7h]

  v4 = a4;
  v5 = a3;
  v86 = a3;
  v6 = (_WORD *)a2;
  v85 = (_WORD *)a2;
  v7 = (struct _HCLUSTER **)a1;
  v8 = 0;
  v9 = 0;
  v10 = &base;
  while ( v9 < 0x37 )
  {
    v11 = 17LL * v9;
    v12 = (&off_18011D0D0)[v11 + 8];
    if ( v12 )
    {
      if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64, _WORD *))v12)(a1, a2, a3, v6) )
        goto LABEL_102;
      v6 = v85;
      v5 = v86;
    }
    if ( !v4 )
      goto LABEL_26;
    a1 = (unsigned __int16)*v6;
    if ( !(_WORD)a1 )
      goto LABEL_26;
    LOBYTE(a2) = 0;
    a3 = *((unsigned int *)&off_18011D0D0 + 2 * v11 + 31);
    do
    {
      LOWORD(a1) = (unsigned __int16)a1 >> 1;
      a2 = (unsigned __int8)a2;
      if ( ((unsigned __int16)a1 & (unsigned __int16)a3) != 0 )
        a2 = 1;
    }
    while ( (_WORD)a1 );
    if ( !(_BYTE)a2 )
    {
LABEL_26:
      if ( (v13 = *((_DWORD *)&off_18011D0D0 + 2 * v11 + 31), (v13 & 0x30) != 0) && *v6 >= 0xCu
        || (v13 & 0x20) != 0 && *v6 >= 0xBu
        || (v13 & 0x10) != 0 && *v6 == 10
        || (a2 = 8, (v13 & 8) != 0) && *v6 == 9
        || (v13 & 4) != 0 && *v6 == 8
        || (a1 = 7, (v13 & 2) != 0) && *v6 == 7
        || (v13 & 1) != 0 && *v6 < 7u )
      {
        v14 = (_QWORD *)std::map<unsigned long,std::wstring>::_Try_emplace<unsigned long,>(
                          v5,
                          v87,
                          &qword_18011D0D8[17 * v9]);
        std::wstring::wstring(v88, *v14 + 40LL);
        if ( !v89 )
          std::wstring::assign(v88, (&off_18011D0D0)[17 * v9], v15);
        v16 = 17LL * v9;
        v17 = &base;
        if ( (&off_18011D0D0)[v16] )
          v17 = (&off_18011D0D0)[v16];
        TraceMsg(4, 0, L"CreateCoreResTypes", 3355, L"Creating resource type '%ws'", v17);
        std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v88);
        ClusterResourceType = CreateClusterResourceTypeEx(*v7, 5000, 60000, (wchar_t *)L"clusapi!CreateCoreResTypes");
        v8 = ClusterResourceType;
        if ( v4 && ClusterResourceType == 183 )
          v8 = 0;
        if ( v8 )
        {
          LastError = GetLastError();
          if ( (&off_18011D0D0)[v16] )
            v10 = (&off_18011D0D0)[v16];
          LODWORD(v82) = LastError;
          v77 = L"Failed to create resource type '%ws'. Error %d.";
          v78 = 3372;
          goto LABEL_118;
        }
        if ( *(&off_18011D0D0 + 17 * v9 + 3) )
        {
          v8 = SetAdminExtension(*v7, (&off_18011D0D0)[17 * v9]);
          if ( v8 )
          {
            LODWORD(v82) = GetLastError();
            v77 = L"Failed to set admin extension for resource type '%ws'. Error %d.";
            v78 = 3382;
LABEL_112:
            v79 = 17LL * v9;
            if ( (&off_18011D0D0)[v79] )
              v10 = (&off_18011D0D0)[v79];
LABEL_118:
            TraceMsg(2, 0, L"CreateCoreResTypes", v78, v77, v10, v82);
            std::wstring::_Tidy_deallocate(v88);
            return v8;
          }
        }
        if ( LODWORD((&off_18011D0D0)[17 * v9 + 2]) )
        {
          LODWORD(v84) = (&off_18011D0D0)[17 * v9 + 2];
          v19 = 17LL * v9;
          v20 = (&off_18011D0D0)[v19];
          v21 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v19 * 8,
                                   *v7) )
          {
            v8 = 6;
LABEL_105:
            LODWORD(v82) = GetLastError();
            v77 = L"Failed to set IsAlivePollInterval for resource type '%ws'. Error %d.";
            v78 = 3393;
            goto LABEL_112;
          }
          v8 = SetResTypePolicy(v21, v20, (__int64)&v84, 4);
          if ( v8 )
            goto LABEL_105;
          v8 = 0;
        }
        if ( *((_DWORD *)&off_18011D0D0 + 34 * v9 + 9) )
        {
          LODWORD(v84) = *((_DWORD *)&off_18011D0D0 + 34 * v9 + 9);
          v22 = 17LL * v9;
          v23 = (&off_18011D0D0)[v22];
          v24 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v22 * 8,
                                   *v7) )
          {
            v8 = 6;
LABEL_107:
            LODWORD(v82) = GetLastError();
            v77 = L"Failed to set LooksAlivePollInterval for resource type '%ws'. Error %d.";
            v78 = 3404;
            goto LABEL_112;
          }
          v8 = SetResTypePolicy(v24, v23, (__int64)&v84, 4);
          if ( v8 )
            goto LABEL_107;
          v8 = 0;
        }
        if ( *((_DWORD *)&off_18011D0D0 + 34 * v9 + 10) )
        {
          LODWORD(v84) = *((_DWORD *)&off_18011D0D0 + 34 * v9 + 10);
          v25 = 17LL * v9;
          v26 = (&off_18011D0D0)[v25];
          v27 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v25 * 8,
                                   *v7) )
          {
            v8 = 6;
LABEL_109:
            LODWORD(v82) = GetLastError();
            v77 = L"Failed to set PendingTimeout for resource type '%ws'. Error %d.";
            v78 = 3415;
            goto LABEL_112;
          }
          v8 = SetResTypePolicy(v27, v26, (__int64)&v84, 4);
          if ( v8 )
            goto LABEL_109;
          v8 = 0;
        }
        if ( *((_DWORD *)&off_18011D0D0 + 34 * v9 + 11) )
        {
          LODWORD(v84) = *((_DWORD *)&off_18011D0D0 + 34 * v9 + 11);
          v28 = 17LL * v9;
          v29 = (&off_18011D0D0)[v28];
          v30 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v28 * 8,
                                   *v7) )
          {
            v8 = 6;
LABEL_111:
            LODWORD(v82) = GetLastError();
            v77 = L"Failed to set DeadlockTimeout for resource type '%ws'. Error %d.";
            v78 = 3426;
            goto LABEL_112;
          }
          v8 = SetResTypePolicy(v30, v29, (__int64)&v84, 4);
          if ( v8 )
            goto LABEL_111;
          v8 = 0;
        }
        v31 = 17LL * v9;
        if ( (&off_18011D0D0)[v31 + 3] != (wchar_t *)-1LL )
        {
          v84 = (__int64)(&off_18011D0D0)[v31 + 3];
          v32 = 17LL * v9;
          v33 = (&off_18011D0D0)[v32];
          v34 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v32 * 8,
                                   *v7) )
          {
            v35 = 6;
            goto LABEL_57;
          }
          v35 = SetResTypePolicy(v34, v33, (__int64)&v84, 8);
          if ( v35 )
          {
LABEL_57:
            v36 = 17LL * v9;
            v37 = &base;
            if ( (&off_18011D0D0)[v36] )
              v37 = (&off_18011D0D0)[v36];
            LODWORD(v82) = v35;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3437,
              L"Failed to set DumpPolicy for resource type '%ws'. Error %d.",
              v37,
              v82);
          }
          v8 = 0;
        }
        v38 = (unsigned int)(&off_18011D0D0)[17 * v9 + 5];
        if ( v38 > 1 )
        {
          v39 = (__int64)*(&off_18011D0D0 + 17 * v9 + 9);
          v40 = 17LL * v9;
          v41 = (&off_18011D0D0)[v40];
          v42 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v40 * 8,
                                   *v7) )
          {
            v43 = 6;
            goto LABEL_65;
          }
          v43 = SetResTypePolicy(v42, v41, v39, 2 * v38);
          if ( v43 )
          {
LABEL_65:
            v44 = 17LL * v9;
            v45 = &base;
            if ( (&off_18011D0D0)[v44] )
              v45 = (&off_18011D0D0)[v44];
            LODWORD(v82) = v43;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3452,
              L"Failed to set DumpLogQuery for resource type '%ws'. Error %d.",
              v45,
              v82);
          }
          v8 = 0;
        }
        v46 = (unsigned int)(&off_18011D0D0)[17 * v9 + 6];
        if ( v46 > 1 )
        {
          v47 = (__int64)*(&off_18011D0D0 + 17 * v9 + 11);
          v48 = 17LL * v9;
          v49 = (&off_18011D0D0)[v48];
          v50 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v48 * 8,
                                   *v7) )
          {
            v51 = 6;
            goto LABEL_73;
          }
          v51 = SetResTypePolicy(v50, v49, v47, 2 * v46);
          if ( v51 )
          {
LABEL_73:
            v52 = 17LL * v9;
            v53 = &base;
            if ( (&off_18011D0D0)[v52] )
              v53 = (&off_18011D0D0)[v52];
            LODWORD(v82) = v51;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3467,
              L"Failed to set EnabledEventLogs for resource type '%ws'. Error %d.",
              v53,
              v82);
          }
          v8 = 0;
        }
        v54 = (unsigned int)(&off_18011D0D0)[17 * v9 + 4];
        if ( v54 > 1 )
        {
          v55 = (__int64)*(&off_18011D0D0 + 17 * v9 + 7);
          v56 = 17LL * v9;
          v57 = (&off_18011D0D0)[v56];
          v58 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v56 * 8,
                                   *v7) )
          {
            v59 = 6;
            goto LABEL_81;
          }
          v59 = SetResTypePolicy(v58, v57, v55, 2 * v54);
          if ( v59 )
          {
LABEL_81:
            v60 = 17LL * v9;
            v61 = &base;
            if ( (&off_18011D0D0)[v60] )
              v61 = (&off_18011D0D0)[v60];
            LODWORD(v82) = v59;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3481,
              L"Failed to set DumpServices for resource type '%ws'. Error %d.",
              v61,
              v82);
          }
          v8 = 0;
        }
        v62 = 17LL * v9;
        if ( *(&off_18011D0D0 + v62 + 13) != (wchar_t *)-1LL )
        {
          v84 = (__int64)*(&off_18011D0D0 + v62 + 13);
          v63 = 17LL * v9;
          v64 = (&off_18011D0D0)[v63];
          v65 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v63 * 8,
                                   *v7) )
          {
            v66 = 6;
            goto LABEL_89;
          }
          v66 = SetResTypePolicy(v65, v64, (__int64)&v84, 8);
          if ( v66 )
          {
LABEL_89:
            v67 = 17LL * v9;
            v68 = &base;
            if ( (&off_18011D0D0)[v67] )
              v68 = (&off_18011D0D0)[v67];
            LODWORD(v82) = v66;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3495,
              L"Failed to set WprStartAfter for resource type '%ws'. Error %d.",
              v68,
              v82);
          }
          v8 = 0;
        }
        v69 = *((_DWORD *)&off_18011D0D0 + 34 * v9 + 30);
        if ( v69 > 1 )
        {
          v70 = (&off_18011D0D0)[17 * v9 + 7];
          v71 = 17LL * v9;
          v72 = (&off_18011D0D0)[v71];
          v73 = *v7;
          if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                                   v71 * 8,
                                   *v7) )
          {
            v74 = 6;
            goto LABEL_97;
          }
          v74 = SetResTypePolicy(v73, v72, (__int64)v70, 2 * v69);
          if ( v74 )
          {
LABEL_97:
            v75 = 17LL * v9;
            v76 = &base;
            if ( (&off_18011D0D0)[v75] )
              v76 = (&off_18011D0D0)[v75];
            LODWORD(v82) = v74;
            TraceMsg(
              2,
              0,
              L"CreateCoreResTypes",
              3510,
              L"Failed to set WprProfiles for resource type '%ws'. Error %d.",
              v76,
              v82);
          }
          v8 = 0;
        }
        std::wstring::_Tidy_deallocate(v88);
        v4 = a4;
      }
    }
LABEL_102:
    ++v9;
    v6 = v85;
    v5 = v86;
  }
  return v8;
}

```

## disassembly

```asm
0x18003628c  mov     [rsp-8+arg_8], rbx
0x180036291  push    rbp
0x180036292  push    rsi
0x180036293  push    rdi
0x180036294  push    r12
0x180036296  push    r13
0x180036298  push    r14
0x18003629a  push    r15
0x18003629c  lea     rbp, [rsp-27h]
0x1800362a1  sub     rsp, 0A0h
0x1800362a8  mov     rax, cs:__security_cookie
0x1800362af  xor     rax, rsp
0x1800362b2  mov     [rbp+57h+var_40], rax
0x1800362b6  mov     r15b, r9b
0x1800362b9  mov     [rbp+57h+var_90], r9b
0x1800362bd  mov     r10, r8
0x1800362c0  mov     [rbp+57h+var_78], r8
0x1800362c4  mov     r9, rdx
0x1800362c7  mov     [rbp+57h+var_80], rdx
0x1800362cb  mov     r13, rcx
0x1800362ce  xor     r12d, r12d
0x1800362d1  mov     ebx, r12d
0x1800362d4  mov     edi, r12d
0x1800362d7  lea     r11, off_18011D0D0; "Volume Shadow Copy Service Task"
0x1800362de  lea     rsi, base
0x1800362e5  cmp     edi, 37h ; '7'
0x1800362e8  jnb     loc_180036C5B
0x1800362ee  mov     eax, edi
0x1800362f0  imul    r14, rax, 88h
0x1800362f7  mov     rax, [r14+r11+80h]
0x1800362ff  test    rax, rax
0x180036302  jz      short loc_180036320
0x180036304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036309  lea     r11, off_18011D0D0; "Volume Shadow Copy Service Task"
0x180036310  test    eax, eax
0x180036312  jnz     loc_180036B5D
0x180036318  mov     r9, [rbp+57h+var_80]
0x18003631c  mov     r10, [rbp+57h+var_78]
0x180036320  test    r15b, r15b
0x180036323  jz      short loc_180036360
0x180036325  movzx   ecx, word ptr [r9]
0x180036329  test    cx, cx
0x18003632c  jz      short loc_180036360
0x18003632e  mov     dl, r12b
0x180036331  mov     r8d, [r14+r11+7Ch]
0x180036336  mov     r11d, 1
0x18003633c  shr     cx, 1
0x18003633f  movzx   eax, cx
0x180036342  test    r8d, eax
0x180036345  movzx   edx, dl
0x180036348  cmovnz  edx, r11d
0x18003634c  test    cx, cx
0x18003634f  jnz     short loc_18003633C
0x180036351  lea     r11, off_18011D0D0; "Volume Shadow Copy Service Task"
0x180036358  test    dl, dl
0x18003635a  jnz     loc_180036B5D
0x180036360  mov     eax, [r14+r11+7Ch]
0x180036365  test    al, 30h
0x180036367  jz      short loc_180036370
0x180036369  cmp     word ptr [r9], 0Ch
0x18003636e  jnb     short loc_1800363C5
0x180036370  test    al, 20h
0x180036372  jz      short loc_18003637F
0x180036374  mov     ecx, 0Bh
0x180036379  cmp     [r9], cx
0x18003637d  jnb     short loc_1800363C5
0x18003637f  test    al, 10h
0x180036381  jz      short loc_18003638A
0x180036383  cmp     word ptr [r9], 0Ah
0x180036388  jz      short loc_1800363C5
0x18003638a  mov     edx, 8
0x18003638f  test    dl, al
0x180036391  jz      short loc_18003639A
0x180036393  cmp     word ptr [r9], 9
0x180036398  jz      short loc_1800363C5
0x18003639a  test    al, 4
0x18003639c  jz      short loc_1800363A4
0x18003639e  cmp     [r9], dx
0x1800363a2  jz      short loc_1800363C5
0x1800363a4  mov     ecx, 7
0x1800363a9  test    al, 2
0x1800363ab  jz      short loc_1800363B3
0x1800363ad  cmp     [r9], cx
0x1800363b1  jz      short loc_1800363C5
0x1800363b3  test    al, 1
0x1800363b5  jz      loc_180036B5D
0x1800363bb  cmp     [r9], cx
0x1800363bf  jnb     loc_180036B5D
0x1800363c5  mov     eax, edi
0x1800363c7  imul    r8, rax, 88h
0x1800363ce  lea     rax, qword_18011D0D8
0x1800363d5  add     r8, rax
0x1800363d8  lea     rdx, [rbp+57h+var_70]
0x1800363dc  mov     rcx, r10
0x1800363df  call    ??$_Try_emplace@K$$V@?$map@KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::map<ulong,std::wstring>::_Try_emplace<ulong,>(ulong &&)
0x1800363e4  mov     rdx, [rax]
0x1800363e7  add     rdx, 28h ; '('
0x1800363eb  lea     rcx, [rbp+57h+var_60]
0x1800363ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800363f4  nop
0x1800363f5  cmp     [rbp+57h+var_50], r12
0x1800363f9  jnz     short loc_180036418
0x1800363fb  mov     eax, edi
0x1800363fd  imul    rdx, rax, 88h
0x180036404  lea     rax, off_18011D0D0; "Volume Shadow Copy Service Task"
0x18003640b  mov     rdx, [rdx+rax]
0x18003640f  lea     rcx, [rbp+57h+var_60]
0x180036413  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180036418  mov     eax, edi
0x18003641a  imul    r14, rax, 88h
0x180036421  mov     rax, rsi
0x180036424  lea     rcx, off_18011D0D0; "Volume Shadow Copy Service Task"
0x18003642b  cmp     [r14+rcx], r12
0x18003642f  cmovnz  rax, [r14+rcx]
0x180036434  mov     qword ptr [rsp+0D0h+var_A8], rax
0x180036439  lea     rax, aCreatingResour; "Creating resource type '%ws'"
0x180036440  mov     [rsp+0D0h+var_B0], rax
0x180036445  mov     r9d, 0D1Bh
0x18003644b  lea     r8, aCreatecorerest; "CreateCoreResTypes"
0x180036452  xor     edx, edx
0x180036454  lea     ecx, [rdx+4]
0x180036457  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003645c  mov     eax, edi
0x18003645e  imul    rbx, rax, 88h
0x180036465  lea     rcx, [rbp+57h+var_60]
0x180036469  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003646e  mov     r8, rax
0x180036471  lea     rax, aClusapiCreatec_2; "clusapi!CreateCoreResTypes"
0x180036478  mov     [rsp+0D0h+var_A0], rax; wchar_t *
0x18003647d  mov     [rsp+0D0h+var_A8], 0EA60h; int
0x180036485  mov     dword ptr [rsp+0D0h+var_B0], 1388h; int
0x18003648d  lea     rax, off_18011D0D0; "Volume Shadow Copy Service Task"
0x180036494  mov     r9, [rbx+rax+10h]
0x180036499  mov     rdx, [r14+rax]
0x18003649d  mov     rcx, [r13+0]; struct _HCLUSTER *
0x1800364a1  call    CreateClusterResourceTypeEx
0x1800364a6  mov     ebx, eax
0x1800364a8  test    r15b, r15b
0x1800364ab  jz      short loc_1800364B6
0x1800364ad  cmp     eax, 0B7h
0x1800364b2  cmovz   ebx, r12d
0x1800364b6  test    ebx, ebx
0x1800364b8  jnz     loc_180036C0F
0x1800364be  mov     ecx, edi
0x1800364c0  imul    rax, rcx, 88h
0x1800364c7  lea     r15, off_18011D0D0; "Volume Shadow Copy Service Task"
0x1800364ce  mov     r8, [rax+r15+18h]
0x1800364d3  test    r8, r8
0x1800364d6  jz      short loc_1800364F8
0x1800364d8  mov     eax, edi
0x1800364da  imul    rdx, rax, 88h
0x1800364e1  mov     rdx, [rdx+r15]; wchar_t *
0x1800364e5  mov     rcx, [r13+0]; hCluster
0x1800364e9  call    SetAdminExtension
0x1800364ee  mov     ebx, eax
0x1800364f0  test    eax, eax
0x1800364f2  jnz     loc_180036B6C
0x1800364f8  mov     eax, edi
0x1800364fa  imul    rcx, rax, 88h
0x180036501  mov     eax, [rcx+r15+20h]
0x180036506  test    eax, eax
0x180036508  jz      short loc_180036562
0x18003650a  mov     dword ptr [rbp+57h+var_88], eax
0x18003650d  mov     eax, edi
0x18003650f  imul    rcx, rax, 88h
0x180036516  mov     r14, [rcx+r15]
0x18003651a  mov     rbx, [r13+0]
0x18003651e  mov     rdx, rbx
0x180036521  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180036526  test    al, al
0x180036528  jz      loc_180036B85
0x18003652e  mov     ecx, 4
0x180036533  mov     [rsp+0D0h+var_A8], ecx; int
0x180036537  lea     rax, [rbp+57h+var_88]
0x18003653b  mov     [rsp+0D0h+var_B0], rax; __int64
0x180036540  mov     r9d, ecx
0x180036543  lea     r8, aIsalivepollint; "IsAlivePollInterval"
0x18003654a  mov     rdx, r14; wchar_t *
0x18003654d  mov     rcx, rbx; hCluster
0x180036550  call    SetResTypePolicy
0x180036555  mov     ebx, eax
0x180036557  test    eax, eax
0x180036559  jnz     loc_180036B8A
0x18003655f  mov     ebx, r12d
0x180036562  mov     eax, edi
0x180036564  imul    rcx, rax, 88h
0x18003656b  mov     eax, [rcx+r15+24h]
0x180036570  test    eax, eax
0x180036572  jz      short loc_1800365CC
0x180036574  mov     dword ptr [rbp+57h+var_88], eax
0x180036577  mov     eax, edi
0x180036579  imul    rcx, rax, 88h
0x180036580  mov     r14, [rcx+r15]
0x180036584  mov     rbx, [r13+0]
0x180036588  mov     rdx, rbx
0x18003658b  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180036590  test    al, al
0x180036592  jz      loc_180036BA3
0x180036598  mov     ecx, 4
0x18003659d  mov     [rsp+0D0h+var_A8], ecx; int
0x1800365a1  lea     rax, [rbp+57h+var_88]
0x1800365a5  mov     [rsp+0D0h+var_B0], rax; __int64
0x1800365aa  mov     r9d, ecx
0x1800365ad  lea     r8, aLooksalivepoll; "LooksAlivePollInterval"
0x1800365b4  mov     rdx, r14; wchar_t *
0x1800365b7  mov     rcx, rbx; hCluster
0x1800365ba  call    SetResTypePolicy
0x1800365bf  mov     ebx, eax
0x1800365c1  test    eax, eax
0x1800365c3  jnz     loc_180036BA8
0x1800365c9  mov     ebx, r12d
0x1800365cc  mov     eax, edi
0x1800365ce  imul    rcx, rax, 88h
0x1800365d5  mov     eax, [rcx+r15+28h]
0x1800365da  test    eax, eax
0x1800365dc  jz      short loc_180036636
0x1800365de  mov     dword ptr [rbp+57h+var_88], eax
0x1800365e1  mov     eax, edi
0x1800365e3  imul    rcx, rax, 88h
0x1800365ea  mov     r14, [rcx+r15]
0x1800365ee  mov     rbx, [r13+0]
0x1800365f2  mov     rdx, rbx
0x1800365f5  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x1800365fa  test    al, al
0x1800365fc  jz      loc_180036BC1
0x180036602  mov     ecx, 4
0x180036607  mov     [rsp+0D0h+var_A8], ecx; int
0x18003660b  lea     rax, [rbp+57h+var_88]
0x18003660f  mov     [rsp+0D0h+var_B0], rax; __int64
0x180036614  mov     r9d, ecx
0x180036617  lea     r8, aPendingtimeout; "PendingTimeout"
0x18003661e  mov     rdx, r14; wchar_t *
0x180036621  mov     rcx, rbx; hCluster
0x180036624  call    SetResTypePolicy
0x180036629  mov     ebx, eax
0x18003662b  test    eax, eax
0x18003662d  jnz     loc_180036BC6
0x180036633  mov     ebx, r12d
0x180036636  mov     eax, edi
0x180036638  imul    rcx, rax, 88h
0x18003663f  mov     eax, [rcx+r15+2Ch]
0x180036644  test    eax, eax
0x180036646  jz      short loc_1800366A0
0x180036648  mov     dword ptr [rbp+57h+var_88], eax
0x18003664b  mov     eax, edi
0x18003664d  imul    rcx, rax, 88h
0x180036654  mov     r14, [rcx+r15]
0x180036658  mov     rbx, [r13+0]
0x18003665c  mov     rdx, rbx
0x18003665f  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180036664  test    al, al
0x180036666  jz      loc_180036BDF
0x18003666c  mov     ecx, 4
0x180036671  mov     [rsp+0D0h+var_A8], ecx; int
0x180036675  lea     rax, [rbp+57h+var_88]
0x180036679  mov     [rsp+0D0h+var_B0], rax; __int64
0x18003667e  mov     r9d, ecx
0x180036681  lea     r8, aDeadlocktimeou; "DeadlockTimeout"
0x180036688  mov     rdx, r14; wchar_t *
0x18003668b  mov     rcx, rbx; hCluster
0x18003668e  call    SetResTypePolicy
0x180036693  mov     ebx, eax
0x180036695  test    eax, eax
0x180036697  jnz     loc_180036BE4
0x18003669d  mov     ebx, r12d
0x1800366a0  mov     eax, edi
0x1800366a2  imul    rcx, rax, 88h
0x1800366a9  mov     rax, [rcx+r15+30h]
0x1800366ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800366b2  jz      loc_180036751
0x1800366b8  mov     [rbp+57h+var_88], rax
0x1800366bc  mov     eax, edi
0x1800366be  imul    rcx, rax, 88h
0x1800366c5  mov     r14, [rcx+r15]
0x1800366c9  mov     rbx, [r13+0]
0x1800366cd  mov     rdx, rbx
0x1800366d0  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x1800366d5  test    al, al
0x1800366d7  jnz     short loc_1800366E0
0x1800366d9  mov     eax, 6
0x1800366de  jmp     short loc_18003670D
0x1800366e0  mov     [rsp+0D0h+var_A8], 8; int
0x1800366e8  lea     rax, [rbp+57h+var_88]
0x1800366ec  mov     [rsp+0D0h+var_B0], rax; __int64
0x1800366f1  mov     r9d, 0Bh
0x1800366f7  lea     r8, aDumppolicy; "DumpPolicy"
0x1800366fe  mov     rdx, r14; wchar_t *
0x180036701  mov     rcx, rbx; hCluster
0x180036704  call    SetResTypePolicy
0x180036709  test    eax, eax
0x18003670b  jz      short loc_18003674E
0x18003670d  mov     ecx, edi
0x18003670f  imul    rdx, rcx, 88h
0x180036716  mov     rcx, rsi
0x180036719  cmp     [rdx+r15], r12
0x18003671d  cmovnz  rcx, [rdx+r15]
0x180036722  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180036726  mov     qword ptr [rsp+0D0h+var_A8], rcx
0x18003672b  lea     rax, aFailedToSetDum; "Failed to set DumpPolicy for resource t"...
0x180036732  mov     [rsp+0D0h+var_B0], rax
  ... truncated ...
```
