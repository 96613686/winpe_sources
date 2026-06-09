# DfsRegistryStore::MoveLinkPaths(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *)

- ea: `0x140023320`
- end: `0x1400244b8`
- name: `?MoveLinkPaths@DfsRegistryStore@@UEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@2KPEAK@Z`
- size: `4504`
- prototype: `unsigned int(DfsRegistryStore *__hidden this, unsigned __int64, struct DfsRootFolder *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140005a94`
- `0x1400096ac`
- `0x14000ab08`
- `0x14000abc4`
- `0x14000b890`
- `0x14000fca8`
- `0x14000fd24`
- `0x140010194`
- `0x140023320`
- `0x140024a98`
- `0x140024b08`
- `0x140024bb0`
- `0x140024c0c`
- `0x14002a7b4`
- `0x14002e544`
- `0x140031108`
- `0x1400316bc`
- `0x140058078`
- `0x14005864c`
- `0x1400586a8`
- `0x140058708`
- `0x140058db8`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `msvcrt!free` at `0x140023bab`
- `msvcrt!free` at `0x1400241a4`
- `msvcrt!free` at `0x1400241e7`
- `msvcrt!free` at `0x14002421e`
- `msvcrt!free` at `0x14005d721`
- `msvcrt!free` at `0x14005d762`
- `msvcrt!free` at `0x14005d792`
- `msvcrt!free` at `0x140023bab`
- `msvcrt!free` at `0x1400241a4`
- `msvcrt!free` at `0x1400241e7`
- `msvcrt!free` at `0x14002421e`
- `msvcrt!free` at `0x14005d721`
- `msvcrt!free` at `0x14005d762`
- `msvcrt!free` at `0x14005d792`
- `msvcrt!malloc` at `0x14002352c`
- `msvcrt!malloc` at `0x14002402f`
- `msvcrt!malloc` at `0x14002352c`
- `msvcrt!malloc` at `0x14002402f`
- `RPCRT4!UuidCreate` at `0x1400235c0`
- `RPCRT4!UuidCreate` at `0x1400235c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400234e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400234e1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140023582`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140023582`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::MoveLinkPaths(
        DfsRegistryStore *this,
        HKEY a2,
        struct DfsRootFolder *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        char a6,
        unsigned int *a7)
{
  unsigned int v9; // r14d
  WCHAR *v10; // r13
  DWORD v11; // esi
  struct DfsFolder *v12; // rdx
  unsigned int v13; // ebx
  DWORD v14; // ebx
  unsigned int FirstComponent; // eax
  void **i; // rsi
  unsigned int *v17; // rcx
  __int64 v18; // rdx
  unsigned int *v19; // rcx
  struct _UNICODE_STRING *v20; // r9
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // r8d
  unsigned int *v24; // rcx
  int v25; // r9d
  int v26; // edx
  _QWORD *v27; // rax
  _QWORD *v28; // r14
  unsigned __int16 *j; // rsi
  unsigned int updated; // eax
  __int64 v31; // rbx
  __int64 v32; // r8
  char v33; // al
  void **v34; // rax
  void **v35; // rbx
  void **v36; // rax
  void **v37; // rsi
  void **v38; // r14
  HKEY v39; // rsi
  __int64 v40; // r8
  unsigned int v41; // r14d
  int v42; // r12d
  DfsRootFolder *v43; // r15
  __int64 v44; // r9
  unsigned int v45; // eax
  unsigned int v46; // esi
  char v48; // [rsp+64h] [rbp-154h]
  char v49; // [rsp+65h] [rbp-153h]
  int v50; // [rsp+68h] [rbp-150h]
  unsigned __int8 v51[4]; // [rsp+6Ch] [rbp-14Ch] BYREF
  struct _UNICODE_STRING *v52; // [rsp+70h] [rbp-148h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-140h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-138h]
  DfsRootFolder *v55; // [rsp+88h] [rbp-130h]
  void *Block; // [rsp+90h] [rbp-128h] BYREF
  void **p_Block; // [rsp+98h] [rbp-120h]
  DWORD cchName; // [rsp+A0h] [rbp-118h] BYREF
  unsigned int v59; // [rsp+A4h] [rbp-114h]
  int v60; // [rsp+A8h] [rbp-110h]
  DfsGeneric *v61; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-100h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-F8h]
  WCHAR *v64; // [rsp+C8h] [rbp-F0h]
  __int128 v65; // [rsp+D0h] [rbp-E8h] BYREF
  struct DfsFolder *v66; // [rsp+E0h] [rbp-D8h] BYREF
  PCUNICODE_STRING v67; // [rsp+E8h] [rbp-D0h]
  HKEY v68; // [rsp+F0h] [rbp-C8h]
  __int128 v69; // [rsp+F8h] [rbp-C0h] BYREF
  DfsRegistryStore *v70; // [rsp+108h] [rbp-B0h]
  struct _UNICODE_STRING v71; // [rsp+110h] [rbp-A8h] BYREF
  __int128 v72; // [rsp+120h] [rbp-98h] BYREF
  int v73; // [rsp+130h] [rbp-88h]
  unsigned int v74; // [rsp+134h] [rbp-84h]
  DWORD v75; // [rsp+138h] [rbp-80h]
  int v76; // [rsp+13Ch] [rbp-7Ch]
  unsigned int *v77; // [rsp+140h] [rbp-78h]
  UUID Uuid; // [rsp+148h] [rbp-70h] BYREF
  __int128 v79; // [rsp+158h] [rbp-60h] BYREF
  PWSTR Buffer; // [rsp+168h] [rbp-50h]

  v63 = (__int64)a4;
  v55 = a3;
  hKey = a2;
  v70 = this;
  v68 = a2;
  v67 = a5;
  v77 = a7;
  v69 = 0;
  v72 = 0;
  v71 = 0;
  v65 = 0;
  v61 = 0;
  v52 = 0;
  v62 = 0;
  v66 = 0;
  v9 = 0;
  v59 = 0;
  v50 = 0;
  v60 = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  v10 = 0;
  v64 = 0;
  v11 = 0;
  v51[0] = 0;
  v48 = 0;
  v49 = 0;
  Uuid = 0;
  v79 = 0;
  Buffer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qZZ(
      *((_QWORD *)pWppControl + 2),
      34,
      (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
      (_DWORD)this,
      (__int64)a4,
      (__int64)a5);
  }
  p_Block = &Block;
  Block = &Block;
  DfsRtlInitUnicodeStringEx(&v65, 0);
  v13 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v13 )
    goto LABEL_154;
  if ( cbMaxSubKeyLen >= 0x7FFF )
  {
    v13 = 206;
    goto LABEL_154;
  }
  v14 = ++cbMaxSubKeyLen;
  while ( 1 )
  {
    if ( !v10 )
    {
      v10 = (WCHAR *)malloc(2LL * v14);
      v64 = v10;
      if ( !v10 )
        goto LABEL_12;
    }
    cchName = v14;
    FirstComponent = RegEnumKeyExW(hKey, v11, v10, &cchName, 0, 0, 0, 0);
    v13 = FirstComponent;
    if ( FirstComponent == 259 )
      break;
    if ( FirstComponent == 234 )
    {
      free(v10);
      v10 = 0;
      v64 = 0;
      v14 = cchName + 1;
      cbMaxSubKeyLen = cchName + 1;
    }
    else
    {
      if ( FirstComponent )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_154;
        v17 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_154;
        v18 = 35;
        goto LABEL_91;
      }
      v75 = ++v11;
      FirstComponent = (*(__int64 (__fastcall **)(DfsRegistryStore *, HKEY, WCHAR *, struct _UNICODE_STRING **))(*(_QWORD *)this + 96LL))(
                         this,
                         hKey,
                         v10,
                         &v52);
      v13 = FirstComponent;
      if ( FirstComponent )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_154;
        v17 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_154;
        v18 = 36;
        goto LABEL_91;
      }
      FirstComponent = DfsGetFirstComponent(&v52[1], &v72, &v69);
      v13 = FirstComponent;
      if ( FirstComponent )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_154;
        v17 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_154;
        v18 = 37;
        goto LABEL_91;
      }
      if ( (_WORD)v69
        && *((_QWORD *)&v69 + 1)
        && **((_WORD **)&v69 + 1)
        && (v31 = v63, (unsigned __int8)DfsPathPrefixUnicodeString(v63, &v69, 0)) )
      {
        FirstComponent = DfsSubstitutePrefix(0, v31, v67, v52 + 1);
        v13 = FirstComponent;
        if ( FirstComponent )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_154;
          v17 = pWppControl;
          if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
            goto LABEL_154;
          v18 = 38;
          goto LABEL_91;
        }
        v48 = 1;
        FirstComponent = DfsGetFirstComponent(&v52[1], &v72, &v71);
        v13 = FirstComponent;
        if ( FirstComponent )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_154;
          v17 = pWppControl;
          if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
            goto LABEL_154;
          v18 = 39;
          goto LABEL_91;
        }
        if ( !(unsigned __int8)DfsPathPrefixUnicodeString(v63, &v71, v32) )
        {
          v13 = DfsRootFolder::ValidateLinkName(v55, &v71, v51, 1u, &v61, 0);
          if ( v13 || (v33 = 1, (a6 & 1) == 0) )
            v33 = 0;
          if ( v13 != 1168 && !v33 )
          {
            if ( v13 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x820) != 0
                && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                WPP_SF_ZD(
                  *((_QWORD *)pWppControl + 2),
                  41,
                  (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
                  (unsigned int)&v71,
                  v13);
              }
            }
            else
            {
              v13 = 80;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                v19 = pWppControl;
                if ( pWppControl )
                {
                  if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
                  {
                    v21 = 40;
                    v20 = &v71;
LABEL_35:
                    WPP_SF_Z(*((_QWORD *)v19 + 2), v21, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v20);
                  }
                }
              }
            }
            goto LABEL_154;
          }
        }
        FirstComponent = DfsSubstitutePrefix(0, v63, v67, v52 + 2);
        v13 = FirstComponent;
        if ( FirstComponent )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            goto LABEL_154;
          v17 = pWppControl;
          if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
            goto LABEL_154;
          v18 = 42;
LABEL_91:
          WPP_SF_D(*((_QWORD *)v17 + 2), v18, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, FirstComponent);
          goto LABEL_154;
        }
        v49 = 1;
        v34 = (void **)malloc(0x40u);
        v35 = v34;
        if ( !v34 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x80000020) != 0
            && *((_BYTE *)pWppControl + 25) )
          {
            WPP_SF_(*((_QWORD *)pWppControl + 2), 43, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids);
          }
LABEL_12:
          v13 = 8;
          goto LABEL_154;
        }
        v34[2] = v52;
        v34[3] = v61;
        DfsRtlInitUnicodeStringEx(v34 + 4, v10);
        DfsRtlInitUnicodeStringEx(v35 + 6, 0);
        v36 = p_Block;
        if ( *p_Block != &Block )
          __fastfail(3u);
        *v35 = &Block;
        v35[1] = v36;
        *v36 = v35;
        p_Block = v35;
        v76 = ++v50;
        v48 = 0;
        v49 = 0;
        v10 = 0;
        v64 = 0;
        v52 = 0;
        v61 = 0;
      }
      else
      {
        (*(void (__fastcall **)(DfsRegistryStore *, HKEY, struct _UNICODE_STRING *))(*(_QWORD *)this + 104LL))(
          this,
          hKey,
          v52);
        v52 = 0;
      }
      v14 = cbMaxSubKeyLen;
    }
  }
  for ( i = (void **)Block; ; i = (void **)*i )
  {
    if ( i == &Block )
    {
      for ( j = (unsigned __int16 *)Block; ; j = *(unsigned __int16 **)j )
      {
        if ( j == (unsigned __int16 *)&Block )
        {
          v13 = 0;
          goto LABEL_154;
        }
        updated = DfsRootFolder::UpdateLinkInformation(v55, (unsigned __int64)hKey, *((unsigned __int16 **)j + 7), 1u);
        v13 = updated;
        if ( updated )
          break;
        (*(void (__fastcall **)(DfsRegistryStore *, unsigned __int16 *))(*(_QWORD *)this + 88LL))(this, j + 24);
        DfsRtlInitUnicodeStringEx(j + 24, 0);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x820) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_ZDd(
          *((_QWORD *)pWppControl + 2),
          52,
          (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
          (_DWORD)j + 48,
          updated,
          v9);
      }
      goto LABEL_154;
    }
    v13 = UuidCreate(&Uuid);
    if ( v13 )
      goto LABEL_154;
    FirstComponent = (*(__int64 (__fastcall **)(DfsRegistryStore *, UUID *, __int128 *))(*(_QWORD *)this + 80LL))(
                       this,
                       &Uuid,
                       &v65);
    v13 = FirstComponent;
    if ( FirstComponent )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v17 = pWppControl;
        if ( pWppControl )
        {
          if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
          {
            v18 = 44;
            goto LABEL_91;
          }
        }
      }
      goto LABEL_154;
    }
    FirstComponent = (*(__int64 (__fastcall **)(DfsRegistryStore *, HKEY, void *, __int64 *))(*(_QWORD *)this + 120LL))(
                       this,
                       hKey,
                       i[5],
                       &v62);
    v13 = FirstComponent;
    if ( FirstComponent )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v17 = pWppControl;
        if ( pWppControl )
        {
          if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
          {
            v18 = 45;
            goto LABEL_91;
          }
        }
      }
      goto LABEL_154;
    }
    v13 = (*(__int64 (__fastcall **)(DfsRegistryStore *, HKEY, void *, __int64, __int128 *))(*(_QWORD *)this + 24LL))(
            this,
            hKey,
            i[2],
            v62,
            &v65);
    (*(void (__fastcall **)(DfsRegistryStore *, HKEY, __int64))(*(_QWORD *)this + 128LL))(this, hKey, v62);
    v62 = 0;
    if ( v13 )
      break;
    *((_OWORD *)i + 3) = v65;
    DfsRtlInitUnicodeStringEx(&v65, 0);
    v22 = DfsRootFolder::LookupFolderByMetadataName(v55, (unsigned __int16 *)i[5], &v66);
    v13 = v22;
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x820) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_Zdd(*((_QWORD *)pWppControl + 2), (_DWORD)v12, v23, (_DWORD)i + 32, v22, v9);
      }
      goto LABEL_154;
    }
    v13 = DfsRootFolder::RemoveLinkFolder(v55, v66, 1u);
    DfsGeneric::ReleaseReference(v66);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_154;
      v24 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
        goto LABEL_154;
      v25 = (_DWORD)i + 32;
      v26 = 48;
LABEL_48:
      WPP_SF_ZDd(*((_QWORD *)v24 + 2), v26, (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v25, v13, v9);
      goto LABEL_154;
    }
    v27 = i[3];
    if ( v27 )
    {
      v28 = v27 + 8;
      v13 = (*(__int64 (__fastcall **)(DfsRegistryStore *, HKEY, _QWORD))(*(_QWORD *)this + 32LL))(this, hKey, v27[9]);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x820) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_Z(*((_QWORD *)pWppControl + 2), 49, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v28);
        }
        *(_QWORD *)&v79 = *((_QWORD *)v55 + 38);
        *((_QWORD *)&v79 + 1) = v28[1];
        DfsRootFolder::GenerateEventLog(v55, 0xC00038CC, 2u, (const unsigned __int16 **const)&v79, v13);
        (*(void (__fastcall **)(DfsRegistryStore *, HKEY, void *))(*(_QWORD *)this + 32LL))(this, hKey, i[7]);
        goto LABEL_154;
      }
      v73 = ++v60;
      v9 = v59;
    }
    v13 = (*(__int64 (__fastcall **)(DfsRegistryStore *, HKEY, void *))(*(_QWORD *)this + 32LL))(this, hKey, i[5]);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x820) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_Z(*((_QWORD *)pWppControl + 2), 50, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, i + 4);
      }
      *(_QWORD *)&v79 = *((_QWORD *)v55 + 38);
      *((_QWORD *)&v79 + 1) = i[5];
      DfsRootFolder::GenerateEventLog(v55, 0xC00038CC, 2u, (const unsigned __int16 **const)&v79, v13);
      goto LABEL_154;
    }
    v59 = ++v9;
    v74 = v9;
    v12 = (struct DfsFolder *)i[3];
    if ( v12 )
    {
      v13 = DfsRootFolder::RemoveLinkFolder(v55, v12, 1u);
      DfsGeneric::ReleaseReference((DfsGeneric *)i[3]);
      i[3] = 0;
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_154;
        v24 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_154;
        v26 = 51;
        v25 = 64;
        goto LABEL_48;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v19 = pWppControl;
    if ( pWppControl )
    {
      if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
      {
        v20 = (struct _UNICODE_STRING *)((char *)i[2] + 16);
        v21 = 46;
        goto LABEL_35;
      }
    }
  }
LABEL_154:
  v37 = (void **)Block;
  while ( v37 != &Block )
  {
    v38 = v37;
    DfsFreeUnicodeString((char *)v37[2] + 16);
    DfsFreeUnicodeString((char *)v37[2] + 32);
    (*(void (__fastcall **)(DfsRegistryStore *, HKEY, void *))(*(_QWORD *)this + 104LL))(this, hKey, v37[2]);
    free(v37[5]);
    if ( v37[7] )
      (*(void (__fastcall **)(DfsRegistryStore *, void **))(*(_QWORD *)this + 88LL))(this, v37 + 6);
    if ( v37[3] )
      DfsGeneric::ReleaseReference(v61);
    v37 = (void **)*v37;
    free(v38);
  }
  if ( v61 )
    DfsGeneric::ReleaseReference(v61);
  if ( v10 )
    free(v10);
  if ( v52 )
  {
    if ( v48 )
      DfsFreeUnicodeString(&v52[1]);
    if ( v49 )
      DfsFreeUnicodeString(&v52[2]);
    v39 = hKey;
    (*(void (__fastcall **)(DfsRegistryStore *, HKEY, struct _UNICODE_STRING *))(*(_QWORD *)this + 104LL))(
      this,
      hKey,
      v52);
  }
  else
  {
    v39 = hKey;
  }
  v40 = v62;
  if ( v62 )
    (*(void (__fastcall **)(DfsRegistryStore *, HKEY))(*(_QWORD *)this + 128LL))(this, v39);
  if ( *((_QWORD *)&v65 + 1) )
    (*(void (__fastcall **)(DfsRegistryStore *, __int128 *))(*(_QWORD *)this + 88LL))(this, &v65);
  v41 = v59;
  if ( !v59 )
  {
    if ( !v13 )
      v13 = 1168;
    goto LABEL_192;
  }
  if ( !v13 )
  {
LABEL_192:
    v42 = v50;
    goto LABEL_193;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && pWppControl && (pWppControl[7] & 0x820) != 0 )
  {
    v42 = v50;
    if ( *((_BYTE *)pWppControl + 25) )
      WPP_SF_ddD(*((_QWORD *)pWppControl + 2), 53, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v59, v50, v13);
  }
  else
  {
    v42 = v50;
  }
  v43 = v55;
  *(_QWORD *)&v79 = *((_QWORD *)v55 + 38);
  *((_QWORD *)&v79 + 1) = *(_QWORD *)(v63 + 8);
  Buffer = v67->Buffer;
  DfsRootFolder::GenerateEventLog(v55, 0x800038CA, 3u, (const unsigned __int16 **const)&v79, v13);
  LOBYTE(v44) = 1;
  v45 = (*(__int64 (__fastcall **)(DfsRootFolder *, __int64, _QWORD, __int64))(*(_QWORD *)v43 + 32LL))(v43, 2, 0, v44);
  v46 = v45;
  if ( v45 )
  {
    *(_QWORD *)&v79 = *((_QWORD *)v43 + 38);
    DfsRootFolder::GenerateEventLog(v43, 0xC00038CB, 1u, (const unsigned __int16 **const)&v79, v45);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_ddDD(*((_QWORD *)pWppControl + 2), v12, v40, v41, v42, v13, v46);
    }
  }
LABEL_193:
  if ( v77 )
    *v77 = v41;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Dddd(*((_QWORD *)pWppControl + 2), v12, v40, v13, v42, v41, v60);
  }
  return v13;
}

```

## disassembly

```asm
0x140023320  mov     r11, rsp
0x140023323  push    rbx
0x140023324  push    rsi
0x140023325  push    rdi
0x140023326  push    r12
0x140023328  push    r13
0x14002332a  push    r14
0x14002332c  push    r15
0x14002332e  sub     rsp, 180h
0x140023335  mov     rax, cs:__security_cookie
0x14002333c  xor     rax, rsp
0x14002333f  mov     [rsp+1B8h+var_48], rax
0x140023347  mov     rax, r9
0x14002334a  mov     [rsp+1B8h+var_F8], rax
0x140023352  mov     [rsp+1B8h+var_130], r8
0x14002335a  mov     rbx, rdx
0x14002335d  mov     [rsp+1B8h+hKey], rdx
0x140023365  mov     r12, rcx
0x140023368  mov     [rsp+1B8h+var_B0], rcx
0x140023370  mov     [rsp+1B8h+var_C8], rdx
0x140023378  mov     r8, [rsp+1B8h+arg_20]
0x140023380  mov     [rsp+1B8h+var_D0], r8
0x140023388  mov     rcx, [rsp+1B8h+arg_30]
0x140023390  mov     [rsp+1B8h+var_78], rcx
0x140023398  xorps   xmm0, xmm0
0x14002339b  movups  [rsp+1B8h+var_C0], xmm0
0x1400233a3  xorps   xmm1, xmm1
0x1400233a6  movups  [rsp+1B8h+var_98], xmm1
0x1400233ae  movups  xmmword ptr [rsp+1B8h+var_A8.Length], xmm0
0x1400233b6  movups  [rsp+1B8h+var_E8], xmm1
0x1400233be  xor     edi, edi
0x1400233c0  mov     [r11-108h], rdi
0x1400233c7  mov     [rsp+1B8h+var_148], rdi
0x1400233cc  mov     [r11-100h], rdi
0x1400233d3  mov     [r11-0D8h], rdi
0x1400233da  mov     r14d, edi
0x1400233dd  mov     [rsp+1B8h+var_114], edi
0x1400233e4  mov     [rsp+1B8h+var_150], edi
0x1400233e8  mov     [rsp+1B8h+var_110], edi
0x1400233ef  mov     [rsp+1B8h+cbMaxSubKeyLen], edi
0x1400233f3  mov     [rsp+1B8h+cchName], edi
0x1400233fa  mov     r13d, edi
0x1400233fd  mov     [r11-0F0h], rdi
0x140023404  mov     esi, edi
0x140023406  mov     [rsp+1B8h+var_14C], dil
0x14002340b  mov     [rsp+1B8h+var_154], dil
0x140023410  mov     [rsp+1B8h+var_153], dil
0x140023415  movups  xmmword ptr [r11-70h], xmm0
0x14002341a  xor     ecx, ecx
0x14002341c  movups  xmmword ptr [r11-60h], xmm1
0x140023421  mov     [r11-50h], rcx
0x140023425  lea     rcx, WPP_GLOBAL_Control
0x14002342c  cmp     cs:WPP_GLOBAL_Control, rcx
0x140023433  jz      short loc_140023472
0x140023435  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002343c  test    rcx, rcx
0x14002343f  jz      short loc_140023472
0x140023441  test    byte ptr [rcx+1Ch], 20h
0x140023445  jz      short loc_140023472
0x140023447  lea     r15, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x14002344e  cmp     byte ptr [rcx+19h], 3
0x140023452  jb      short loc_140023479
0x140023454  lea     edx, [rdi+22h]
0x140023457  mov     [rsp+1B8h+lpcbMaxSubKeyLen], r8
0x14002345c  mov     [rsp+1B8h+lpcSubKeys], rax
0x140023461  mov     r9, r12
0x140023464  mov     r8, r15
0x140023467  mov     rcx, [rcx+10h]
0x14002346b  call    WPP_SF_qZZ
0x140023470  jmp     short loc_140023479
0x140023472  lea     r15, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140023479  lea     rax, [rsp+1B8h+Block]
0x140023481  mov     [rsp+1B8h+var_120], rax
0x140023489  lea     rax, [rsp+1B8h+Block]
0x140023491  mov     [rsp+1B8h+Block], rax
0x140023499  xor     edx, edx
0x14002349b  lea     rcx, [rsp+1B8h+var_E8]
0x1400234a3  call    DfsRtlInitUnicodeStringEx
0x1400234a8  nop
0x1400234a9  mov     [rsp+1B8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1400234ae  mov     [rsp+1B8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1400234b3  mov     [rsp+1B8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1400234b8  mov     [rsp+1B8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1400234bd  mov     [rsp+1B8h+lpcValues], rdi; lpcValues
0x1400234c2  mov     [rsp+1B8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1400234c7  lea     rax, [rsp+1B8h+cbMaxSubKeyLen]
0x1400234cc  mov     [rsp+1B8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400234d1  mov     [rsp+1B8h+lpcSubKeys], rdi; lpcSubKeys
0x1400234d6  xor     r9d, r9d; lpReserved
0x1400234d9  xor     r8d, r8d; lpcchClass
0x1400234dc  xor     edx, edx; lpClass
0x1400234de  mov     rcx, rbx; hKey
0x1400234e1  call    cs:__imp_RegQueryInfoKeyW
0x1400234e8  nop     dword ptr [rax+rax+00h]
0x1400234ed  mov     ebx, eax
0x1400234ef  mov     [rsp+1B8h+var_158], eax
0x1400234f3  xor     r8d, r8d
0x1400234f6  lea     edi, [r8+1]
0x1400234fa  test    eax, eax
0x1400234fc  jnz     loc_14002415A
0x140023502  mov     ebx, [rsp+1B8h+cbMaxSubKeyLen]
0x140023506  cmp     ebx, 7FFFh
0x14002350c  jb      short loc_14002351C
0x14002350e  mov     ebx, 0CEh
0x140023513  mov     [rsp+1B8h+var_158], ebx
0x140023517  jmp     loc_14002415A
0x14002351c  add     ebx, edi
0x14002351e  mov     [rsp+1B8h+cbMaxSubKeyLen], ebx
0x140023522  test    r13, r13
0x140023525  jnz     short loc_140023552
0x140023527  mov     ecx, ebx
0x140023529  add     rcx, rcx; Size
0x14002352c  call    cs:__imp_malloc
0x140023533  nop     dword ptr [rax+rax+00h]
0x140023538  mov     r13, rax
0x14002353b  mov     [rsp+1B8h+var_F0], rax
0x140023543  xor     r8d, r8d
0x140023546  test    rax, rax
0x140023549  jnz     short loc_140023552
0x14002354b  mov     ebx, 8
0x140023550  jmp     short loc_140023513
0x140023552  mov     [rsp+1B8h+cchName], ebx
0x140023559  mov     [rsp+1B8h+lpcValues], r8; lpftLastWriteTime
0x14002355e  mov     [rsp+1B8h+lpcbMaxClassLen], r8; lpcchClass
0x140023563  mov     [rsp+1B8h+lpcbMaxSubKeyLen], r8; lpClass
0x140023568  mov     [rsp+1B8h+lpcSubKeys], r8; lpReserved
0x14002356d  lea     r9, [rsp+1B8h+cchName]; lpcchName
0x140023575  mov     r8, r13; lpName
0x140023578  mov     edx, esi; dwIndex
0x14002357a  mov     rcx, [rsp+1B8h+hKey]; hKey
0x140023582  call    cs:__imp_RegEnumKeyExW
0x140023589  nop     dword ptr [rax+rax+00h]
0x14002358e  mov     ebx, eax
0x140023590  mov     [rsp+1B8h+var_158], eax
0x140023594  cmp     eax, 103h
0x140023599  jnz     loc_140023BA1
0x14002359f  mov     rsi, [rsp+1B8h+Block]
0x1400235a7  lea     rax, [rsp+1B8h+Block]
0x1400235af  cmp     rsi, rax
0x1400235b2  jz      loc_140023ADC
0x1400235b8  lea     rcx, [rsp+1B8h+Uuid]; Uuid
0x1400235c0  call    cs:__imp_UuidCreate
0x1400235c7  nop     dword ptr [rax+rax+00h]
0x1400235cc  mov     ebx, eax
0x1400235ce  mov     [rsp+1B8h+var_158], eax
0x1400235d2  test    eax, eax
0x1400235d4  jnz     loc_14002415A
0x1400235da  mov     rax, [r12]
0x1400235de  lea     r8, [rsp+1B8h+var_E8]
0x1400235e6  lea     rdx, [rsp+1B8h+Uuid]
0x1400235ee  mov     rcx, r12
0x1400235f1  mov     rax, [rax+50h]
0x1400235f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400235fa  mov     ebx, eax
0x1400235fc  mov     [rsp+1B8h+var_158], eax
0x140023600  test    eax, eax
0x140023602  jz      short loc_140023649
0x140023604  lea     rcx, WPP_GLOBAL_Control
0x14002360b  cmp     cs:WPP_GLOBAL_Control, rcx
0x140023612  jz      loc_14002415A
0x140023618  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002361f  test    rcx, rcx
0x140023622  jz      loc_14002415A
0x140023628  test    dword ptr [rcx+1Ch], 820h
0x14002362f  jz      loc_14002415A
0x140023635  cmp     [rcx+19h], dil
0x140023639  jb      loc_14002415A
0x14002363f  mov     edx, 2Ch ; ','
0x140023644  jmp     loc_140023C1B
0x140023649  mov     rax, [r12]
0x14002364d  lea     r9, [rsp+1B8h+var_100]
0x140023655  mov     r8, [rsi+28h]
0x140023659  mov     rdx, [rsp+1B8h+hKey]
0x140023661  mov     rcx, r12
0x140023664  mov     rax, [rax+78h]
0x140023668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002366d  mov     ebx, eax
0x14002366f  mov     [rsp+1B8h+var_158], eax
0x140023673  test    eax, eax
0x140023675  jz      short loc_1400236BC
0x140023677  lea     rcx, WPP_GLOBAL_Control
0x14002367e  cmp     cs:WPP_GLOBAL_Control, rcx
0x140023685  jz      loc_14002415A
0x14002368b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140023692  test    rcx, rcx
0x140023695  jz      loc_14002415A
0x14002369b  test    dword ptr [rcx+1Ch], 820h
0x1400236a2  jz      loc_14002415A
0x1400236a8  cmp     [rcx+19h], dil
0x1400236ac  jb      loc_14002415A
0x1400236b2  mov     edx, 2Dh ; '-'
0x1400236b7  jmp     loc_140023C1B
0x1400236bc  mov     rax, [r12]
0x1400236c0  lea     rcx, [rsp+1B8h+var_E8]
0x1400236c8  mov     [rsp+1B8h+lpcSubKeys], rcx
0x1400236cd  mov     r9, [rsp+1B8h+var_100]
0x1400236d5  mov     r8, [rsi+10h]
0x1400236d9  mov     rdx, [rsp+1B8h+hKey]
0x1400236e1  mov     rcx, r12
0x1400236e4  mov     rax, [rax+18h]
0x1400236e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400236ed  mov     ebx, eax
0x1400236ef  mov     [rsp+1B8h+var_158], eax
0x1400236f3  mov     rax, [r12]
0x1400236f7  mov     r8, [rsp+1B8h+var_100]
0x1400236ff  mov     rdx, [rsp+1B8h+hKey]
0x140023707  mov     rcx, r12
0x14002370a  mov     rax, [rax+80h]
0x140023711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023716  xor     r8d, r8d
0x140023719  mov     [rsp+1B8h+var_100], r8
0x140023721  test    ebx, ebx
0x140023723  jz      short loc_14002377D
0x140023725  lea     rcx, WPP_GLOBAL_Control
0x14002372c  cmp     cs:WPP_GLOBAL_Control, rcx
0x140023733  jz      loc_14002415A
0x140023739  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140023740  test    rcx, rcx
0x140023743  jz      loc_14002415A
0x140023749  test    dword ptr [rcx+1Ch], 820h
0x140023750  jz      loc_14002415A
0x140023756  cmp     [rcx+19h], dil
0x14002375a  jb      loc_14002415A
0x140023760  mov     r9, [rsi+10h]
0x140023764  add     r9, 10h
0x140023768  lea     edx, [r8+2Eh]
0x14002376c  mov     r8, r15
0x14002376f  mov     rcx, [rcx+10h]
0x140023773  call    WPP_SF_Z
0x140023778  jmp     loc_14002415A
0x14002377d  movups  xmm0, [rsp+1B8h+var_E8]
0x140023785  movdqu  xmmword ptr [rsi+30h], xmm0
0x14002378a  xor     edx, edx
0x14002378c  lea     rcx, [rsp+1B8h+var_E8]
0x140023794  call    DfsRtlInitUnicodeStringEx
0x140023799  lea     r8, [rsp+1B8h+var_D8]; struct DfsFolder **
0x1400237a1  mov     rdx, [rsi+28h]; unsigned __int16 *
0x1400237a5  mov     rcx, [rsp+1B8h+var_130]; this
0x1400237ad  call    ?LookupFolderByMetadataName@DfsRootFolder@@QEAAKPEAGPEAPEAVDfsFolder@@@Z; DfsRootFolder::LookupFolderByMetadataName(ushort *,DfsFolder * *)
0x1400237b2  mov     ebx, eax
0x1400237b4  mov     [rsp+1B8h+var_158], eax
0x1400237b8  test    eax, eax
0x1400237ba  jz      short loc_140023812
0x1400237bc  lea     rcx, WPP_GLOBAL_Control
0x1400237c3  cmp     cs:WPP_GLOBAL_Control, rcx
0x1400237ca  jz      loc_14002415A
0x1400237d0  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400237d7  test    rcx, rcx
0x1400237da  jz      loc_14002415A
0x1400237e0  test    dword ptr [rcx+1Ch], 820h
0x1400237e7  jz      loc_14002415A
0x1400237ed  cmp     [rcx+19h], dil
0x1400237f1  jb      loc_14002415A
0x1400237f7  lea     r9, [rsi+20h]
0x1400237fb  mov     dword ptr [rsp+1B8h+lpcbMaxSubKeyLen], r14d
0x140023800  mov     dword ptr [rsp+1B8h+lpcSubKeys], eax
0x140023804  mov     rcx, [rcx+10h]
0x140023808  call    WPP_SF_Zdd
0x14002380d  jmp     loc_14002415A
0x140023812  mov     r8b, dil; unsigned __int8
0x140023815  mov     rdx, [rsp+1B8h+var_D8]; struct DfsFolder *
0x14002381d  mov     rcx, [rsp+1B8h+var_130]; this
0x140023825  call    ?RemoveLinkFolder@DfsRootFolder@@QEAAKPEAVDfsFolder@@E@Z; DfsRootFolder::RemoveLinkFolder(DfsFolder *,uchar)
0x14002382a  mov     ebx, eax
0x14002382c  mov     [rsp+1B8h+var_158], eax
0x140023830  mov     rcx, [rsp+1B8h+var_D8]; this
0x140023838  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14002383d  test    ebx, ebx
0x14002383f  jz      short loc_14002389F
0x140023841  lea     rcx, WPP_GLOBAL_Control
0x140023848  cmp     cs:WPP_GLOBAL_Control, rcx
0x14002384f  jz      loc_14002415A
0x140023855  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002385c  test    rcx, rcx
0x14002385f  jz      loc_14002415A
0x140023865  test    dword ptr [rcx+1Ch], 820h
0x14002386c  jz      loc_14002415A
0x140023872  cmp     [rcx+19h], dil
0x140023876  jb      loc_14002415A
0x14002387c  lea     r9, [rsi+20h]
0x140023880  mov     edx, 30h ; '0'
0x140023885  mov     dword ptr [rsp+1B8h+lpcbMaxSubKeyLen], r14d
0x14002388a  mov     dword ptr [rsp+1B8h+lpcSubKeys], ebx
0x14002388e  mov     r8, r15
0x140023891  mov     rcx, [rcx+10h]
0x140023895  call    WPP_SF_ZDd
0x14002389a  jmp     loc_14002415A
0x14002389f  mov     rax, [rsi+18h]
0x1400238a3  test    rax, rax
0x1400238a6  jz      loc_140023998
0x1400238ac  lea     r14, [rax+40h]
0x1400238b0  mov     rax, [r12]
0x1400238b4  mov     r8, [r14+8]
0x1400238b8  mov     rdx, [rsp+1B8h+hKey]
0x1400238c0  mov     rcx, r12
0x1400238c3  mov     rax, [rax+20h]
0x1400238c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400238cc  mov     ebx, eax
0x1400238ce  mov     [rsp+1B8h+var_158], eax
0x1400238d2  test    eax, eax
  ... truncated ...
```
