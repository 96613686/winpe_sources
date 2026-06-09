# CMVEngine::HandleStatesForPackagesInternal(std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> const &,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *)

- ea: `0x180014cf8`
- end: `0x180015738`
- name: `?HandleStatesForPackagesInternal@CMVEngine@@AEAAJAEBV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@PEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z`
- size: `2624`
- prototype: `__int64 __fastcall(CMVEngine *, const struct ProvPackage ***, __int64 **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800141f0`
- `0x180014810`

## callees

- `0x1800010c8`
- `0x1800018ec`
- `0x1800092dc`
- `0x18000c4a4`
- `0x18000c4fc`
- `0x18000f288`
- `0x180011ae4`
- `0x180014cf8`
- `0x180015740`
- `0x18001cca4`
- `0x1800221dc`
- `0x180022a08`
- `0x180022e78`
- `0x180040480`
- `0x180040584`
- `0x18004096c`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800155c7`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800155c7`
- `msvcrt!_wcsicmp` at `0x180014f94`
- `msvcrt!_wcsicmp` at `0x180014f94`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015227`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001526a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001532d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015368`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001541e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001544f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015480`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001560d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015642`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001565b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015227`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001526a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001532d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015368`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153d3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800153ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001541e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001544f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015480`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001560d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015642`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001565b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014d65`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014d65`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015026`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001527f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001567c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015054`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001527f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001567c`

## pseudocode

```c
__int64 __fastcall CMVEngine::HandleStatesForPackagesInternal(
        CMVEngine *a1,
        const struct ProvPackage ***a2,
        __int64 **a3)
{
  int v4; // r14d
  const struct ProvPackage **v5; // rdi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // r9d
  wchar_t *v9; // rax
  wchar_t *v10; // rcx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  HKEY v14; // rcx
  __int64 *v15; // rax
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  int v18; // edx
  __int64 v19; // rax
  unsigned int v20; // eax
  _QWORD *v21; // rax
  _QWORD *v22; // r15
  int v23; // r14d
  _QWORD *v24; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rax
  _QWORD *v27; // r15
  int v28; // r14d
  _QWORD *v29; // rax
  __int64 v30; // rcx
  const struct ProvPackage **v31; // rbx
  int v32; // eax
  __int16 *v33; // rdx
  __int64 **v34; // r15
  _QWORD *i; // rbx
  _QWORD *v36; // rdi
  __int64 v37; // r14
  int v38; // ecx
  __int64 v39; // rdx
  __int64 *v40; // rax
  unsigned int v41; // ebx
  HKEY hkey; // [rsp+40h] [rbp-208h] BYREF
  unsigned int v44; // [rsp+48h] [rbp-200h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-1FCh] BYREF
  int pvData; // [rsp+50h] [rbp-1F8h] BYREF
  __int64 v47; // [rsp+58h] [rbp-1F0h] BYREF
  __int128 v48; // [rsp+60h] [rbp-1E8h] BYREF
  __int64 v49; // [rsp+70h] [rbp-1D8h]
  HKEY hKey; // [rsp+78h] [rbp-1D0h] BYREF
  HKEY v51[2]; // [rsp+80h] [rbp-1C8h] BYREF
  void *v52[2]; // [rsp+90h] [rbp-1B8h] BYREF
  __int128 v53; // [rsp+A0h] [rbp-1A8h]
  __int64 v54; // [rsp+B0h] [rbp-198h]
  CMVEngine *v55; // [rsp+D0h] [rbp-178h]
  _QWORD v56[3]; // [rsp+D8h] [rbp-170h] BYREF
  char v57; // [rsp+F0h] [rbp-158h]
  __int64 **v58; // [rsp+F8h] [rbp-150h] BYREF
  wchar_t String1[4]; // [rsp+108h] [rbp-140h] BYREF
  __int64 v60; // [rsp+118h] [rbp-130h]
  unsigned __int64 v61; // [rsp+120h] [rbp-128h]
  void *v62[3]; // [rsp+128h] [rbp-120h] BYREF
  unsigned __int64 v63; // [rsp+140h] [rbp-108h]
  void *v64[3]; // [rsp+148h] [rbp-100h] BYREF
  unsigned __int64 v65; // [rsp+160h] [rbp-E8h]
  void *v66[3]; // [rsp+168h] [rbp-E0h] BYREF
  unsigned __int64 v67; // [rsp+180h] [rbp-C8h]
  void *v68[2]; // [rsp+188h] [rbp-C0h] BYREF
  __int64 v69; // [rsp+198h] [rbp-B0h]
  unsigned __int64 v70; // [rsp+1A0h] [rbp-A8h]
  int v71; // [rsp+1A8h] [rbp-A0h] BYREF
  char v72; // [rsp+1ACh] [rbp-9Ch]
  GUID ActivityId; // [rsp+1B0h] [rbp-98h] BYREF
  void *v74[3]; // [rsp+1D0h] [rbp-78h] BYREF
  unsigned __int64 v75; // [rsp+1E8h] [rbp-60h]
  HKEY *p_hkey; // [rsp+1F0h] [rbp-58h]
  __int64 v77; // [rsp+1F8h] [rbp-50h]
  __int64 *v78; // [rsp+200h] [rbp-48h]
  int v79; // [rsp+208h] [rbp-40h]
  int v80; // [rsp+20Ch] [rbp-3Ch]
  const struct ProvPackage **v81; // [rsp+210h] [rbp-38h]
  __int64 v82; // [rsp+218h] [rbp-30h]

  v58 = a3;
  v55 = a1;
  v4 = 0;
  LODWORD(hkey) = 0;
  v44 = 0;
  v71 = 0;
  v72 = 0;
  if ( (unsigned int)dword_18005A000 <= 5 )
    ActivityId = 0;
  else
    EventActivityIdControl(3u, &ActivityId);
  v71 = 1;
  if ( (unsigned int)dword_18005A000 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004F5E2, &ActivityId, 0, 2, v74);
  v56[0] = a2;
  v56[1] = &v71;
  v56[2] = &v44;
  v57 = 1;
  try
  {
    PackageInfo::PackageInfo(v51);
    v48 = 0;
    v49 = 0;
    v31 = *a2;
    v5 = a2[1];
    while ( v31 != v5 )
    {
      if ( !(*(unsigned __int8 (__fastcall **)(const struct ProvPackage *))(*(_QWORD *)*v31 + 72LL))(*v31) )
        goto LABEL_87;
      (**(void (__fastcall ***)(const struct ProvPackage *, void **))*v31)(*v31, v62);
      (*(void (__fastcall **)(const struct ProvPackage *, wchar_t *))(*(_QWORD *)*v31 + 16LL))(*v31, String1);
      (*(void (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 24LL))(*v31, v66);
      (*(void (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 32LL))(*v31, v64);
      PackageInfo::getPackageVersionInfo(v51, v52);
      v7 = CMVEngine::ResolveServicedPackages(v6, v52, v31);
      if ( v7 < 0 && (unsigned int)dword_18005A000 > 2 )
      {
        LODWORD(hkey) = v7;
        v9 = String1;
        if ( v61 >= 8 )
          v9 = *(wchar_t **)String1;
        v47 = (__int64)v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18005A000,
          (unsigned int)&byte_18004EE57,
          0,
          v8,
          (__int64)&v47,
          (__int64)&hkey);
      }
      if ( (*(unsigned __int8 (__fastcall **)(const struct ProvPackage *))(*(_QWORD *)*v31 + 88LL))(*v31) )
      {
        if ( v61 < 8 )
        {
          v10 = String1;
        }
        else
        {
          v10 = *(wchar_t **)String1;
          if ( !*(_QWORD *)String1 )
            goto LABEL_62;
        }
        if ( _wcsicmp(v10, L"{eb7d7f2f-3b77-4b87-b301-fd0d336f709a}") )
          goto LABEL_62;
        hkey = 0;
        IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
        v12 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\";
        if ( !IsStateSeparationEnabled )
          v12 = L"SOFTWARE\\Microsoft\\Provisioning\\";
        v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x2001Fu, &hkey);
        v14 = hkey;
        if ( v13 )
          goto LABEL_60;
        pvData = 0;
        pcbData = 4;
        if ( RegGetValueW(hkey, L"SkipPackages", L"SkipSecureCorePackage", 0x10u, 0, &pvData, &pcbData) || pcbData != 4 )
        {
          v14 = hkey;
LABEL_60:
          if ( v14 )
            RegCloseKey(v14);
LABEL_62:
          PackageInfo::PackageInfo(&hKey);
          PackageInfo::Add((PackageInfo *)&hKey, *v31);
          if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
          {
            v26 = (_QWORD *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 16LL))(
                              *v31,
                              v74);
            v27 = v26;
            v28 = v4 | 4;
            LODWORD(hkey) = v28;
            if ( v26[3] >= 8u )
              v27 = (_QWORD *)*v26;
            v29 = (_QWORD *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 8LL))(
                              *v31,
                              v68);
            v4 = v28 | 8;
            if ( v29[3] >= 8u )
              v29 = (_QWORD *)*v29;
            McTemplateU0zz_EventWriteTransfer(v30, PackageInitiate, v29, v27);
          }
          if ( (v4 & 8) != 0 )
          {
            v4 &= ~8u;
            if ( v70 >= 8 )
              operator delete(v68[0]);
            v70 = 7;
            v69 = 0;
            LOWORD(v68[0]) = 0;
          }
          if ( (v4 & 4) != 0 )
          {
            v4 &= ~4u;
            if ( v75 >= 8 )
              operator delete(v74[0]);
          }
          v47 = (__int64)*v31;
          std::vector<ProvSource *>::push_back(&v48, &v47);
          if ( hKey )
            RegCloseKey(hKey);
          goto LABEL_77;
        }
        v14 = hkey;
        if ( pvData != 1 )
          goto LABEL_60;
        if ( hkey )
          RegCloseKey(hkey);
        if ( (unsigned int)dword_18005A000 > 4
          && (qword_18005A010 & 0x400000000000LL) != 0
          && (qword_18005A018 & 0x400000000000LL) == qword_18005A018 )
        {
          v47 = 0x2000000;
          v15 = (__int64 *)v62;
          if ( v63 >= 8 )
            v15 = (__int64 *)v62[0];
          v16 = String1;
          if ( v61 >= 8 )
            v16 = *(wchar_t **)String1;
          v81 = (const struct ProvPackage **)&v47;
          v82 = 8;
          if ( v15 )
          {
            v17 = -1;
            do
              ++v17;
            while ( *((_WORD *)v15 + v17) );
            v18 = 2 * v17 + 2;
          }
          else
          {
            v15 = &qword_180049F78;
            v18 = 2;
          }
          v78 = v15;
          v79 = v18;
          v80 = 0;
          if ( v16 )
          {
            v19 = -1;
            do
              ++v19;
            while ( v16[v19] );
            v20 = 2 * v19 + 2;
          }
          else
          {
            v16 = (wchar_t *)&qword_180049F78;
            v20 = 2;
          }
          p_hkey = (HKEY *)v16;
          v77 = v20;
          tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E7FA, 0, 0, 5, v74);
        }
        if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
        {
          v21 = (_QWORD *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 16LL))(
                            *v31,
                            v74);
          v22 = v21;
          v23 = v4 | 1;
          LODWORD(hkey) = v23;
          if ( v21[3] >= 8u )
            v22 = (_QWORD *)*v21;
          v24 = (_QWORD *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)*v31 + 8LL))(
                            *v31,
                            v68);
          v4 = v23 | 2;
          if ( v24[3] >= 8u )
            v24 = (_QWORD *)*v24;
          McTemplateU0zz_EventWriteTransfer(v25, PackageSkipped, v24, v22);
        }
        if ( (v4 & 2) != 0 )
        {
          v4 &= ~2u;
          if ( v70 >= 8 )
            operator delete(v68[0]);
          v70 = 7;
          v69 = 0;
          LOWORD(v68[0]) = 0;
        }
        if ( (v4 & 1) != 0 )
        {
          v4 &= ~1u;
          if ( v75 >= 8 )
            operator delete(v74[0]);
        }
      }
LABEL_77:
      if ( (_QWORD)v53 )
      {
        operator delete((void *)v53);
        v53 = 0;
        v54 = 0;
      }
      std::list<std::pair<std::wstring const,std::wstring>>::clear(v52);
      operator delete(v52[0]);
      if ( v65 >= 8 )
        operator delete(v64[0]);
      v65 = 7;
      v64[2] = 0;
      LOWORD(v64[0]) = 0;
      if ( v67 >= 8 )
        operator delete(v66[0]);
      v67 = 7;
      v66[2] = 0;
      LOWORD(v66[0]) = 0;
      if ( v61 >= 8 )
        operator delete(*(void **)String1);
      v61 = 7;
      v60 = 0;
      String1[0] = 0;
      if ( v63 >= 8 )
        operator delete(v62[0]);
LABEL_87:
      ++v31;
    }
    v32 = CMVEngine::HandleStatesInternal(v55, (__int64 *)&v48);
    if ( v32 >= 0 )
    {
      if ( (unsigned __int64)((__int64)(*((_QWORD *)&v48 + 1) - v48) >> 3) <= 0xFFFFFFFF
        && (unsigned int)dword_18005A000 > 4 )
      {
        LODWORD(hkey) = (__int64)(*((_QWORD *)&v48 + 1) - v48) >> 3;
        v33 = &word_18004F406;
LABEL_94:
        p_hkey = &hkey;
        v77 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, v33, 0, 0, 3, v74);
      }
    }
    else if ( (unsigned int)dword_18005A000 > 2 )
    {
      LODWORD(hkey) = v32;
      v33 = (__int16 *)byte_18004F2BD;
      goto LABEL_94;
    }
    v34 = v58;
    if ( v58 )
    {
      v36 = (_QWORD *)*((_QWORD *)&v48 + 1);
      for ( i = (_QWORD *)v48; i != v36; ++i )
      {
        (*(void (__fastcall **)(_QWORD, void **))(*(_QWORD *)*i + 16LL))(*i, v68);
        (*(void (__fastcall **)(_QWORD, void **))(*(_QWORD *)*i + 24LL))(*i, v62);
        v37 = **v34;
        v39 = std::_List_buy<std::pair<std::wstring const,std::wstring>>::_Buynode<std::wstring,std::wstring>(
                v38,
                v37,
                *(_QWORD *)(v37 + 8),
                (unsigned int)v68,
                (__int64)v62);
        v40 = v34[1];
        if ( v40 == (__int64 *)0x333333333333332LL )
          std::_Xlength_error("list<T> too long");
        v34[1] = (__int64 *)((char *)v40 + 1);
        *(_QWORD *)(v37 + 8) = v39;
        **(_QWORD **)(v39 + 8) = v39;
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert<std::pair<std::wstring const,std::wstring> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>(
          v34,
          &v58,
          **v34 + 16);
        if ( v63 >= 8 )
          operator delete(v62[0]);
        v63 = 7;
        v62[2] = 0;
        LOWORD(v62[0]) = 0;
        if ( v70 >= 8 )
          operator delete(v68[0]);
      }
    }
    if ( (_QWORD)v48 )
    {
      operator delete((void *)v48);
      v48 = 0;
      v49 = 0;
    }
    if ( v51[0] )
      RegCloseKey(v51[0]);
    v41 = v44;
    v57 = 0;
  }
  catch ( ... )
  {
    v44 = wil::ResultFromCaughtException((wil *)v56);
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      LODWORD(hkey) = v44;
      p_hkey = &hkey;
      v77 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004ECAB, 0, 0, 3, v74);
    }
    LODWORD(hkey) = v44;
    v57 = 0;
    lambda_7ebf50bf5b5b820ae452c12fb80c7b49_::operator()(v56);
    if ( v71 == 1 )
    {
      v71 = 2;
      _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &ActivityId);
    }
    return (unsigned int)hkey;
  }
  ((void (*)(void))lambda_7ebf50bf5b5b820ae452c12fb80c7b49_::operator())();
  if ( v71 == 1 )
  {
    v71 = 2;
    _tlgWriteActivityAutoStop<0,5>(&dword_18005A000, &ActivityId);
  }
  return v41;
}

```

## disassembly

```asm
0x180014cf8  mov     [rsp+arg_8], rbx
0x180014cfd  mov     [rsp+arg_18], rsi
0x180014d02  push    rdi
0x180014d03  push    r14
0x180014d05  push    r15
0x180014d07  sub     rsp, 230h
0x180014d0e  mov     rax, cs:__security_cookie
0x180014d15  xor     rax, rsp
0x180014d18  mov     [rsp+248h+var_28], rax
0x180014d20  mov     [rsp+248h+var_150], r8
0x180014d28  mov     rdi, rdx
0x180014d2b  mov     [rsp+248h+var_178], rcx
0x180014d33  xor     esi, esi
0x180014d35  mov     r14d, esi
0x180014d38  mov     dword ptr [rsp+248h+hkey], esi
0x180014d3c  mov     [rsp+248h+var_200], esi
0x180014d40  mov     [rsp+248h+var_A0], esi
0x180014d47  mov     [rsp+248h+var_9C], sil
0x180014d4f  mov     eax, cs:dword_18005A000
0x180014d55  cmp     eax, 5
0x180014d58  jbe     short loc_180014D6D
0x180014d5a  lea     rdx, [rsp+248h+ActivityId]; ActivityId
0x180014d62  lea     ecx, [rsi+3]; ControlCode
0x180014d65  call    cs:__imp_EventActivityIdControl
0x180014d6b  jmp     short loc_180014D78
0x180014d6d  xorps   xmm0, xmm0
0x180014d70  movups  xmmword ptr [rsp+248h+ActivityId.Data1], xmm0
0x180014d78  mov     [rsp+248h+var_A0], 1
0x180014d83  mov     eax, cs:dword_18005A000
0x180014d89  cmp     eax, 5
0x180014d8c  jbe     short loc_180014DF9
0x180014d8e  cmp     [rsp+248h+var_9C], sil
0x180014d96  jz      short loc_180014DC6
0x180014d98  cmp     [rsp+248h+var_88], esi
0x180014d9f  jnz     short loc_180014DBC
0x180014da1  cmp     [rsp+248h+var_84], esi
0x180014da8  jnz     short loc_180014DBC
0x180014daa  cmp     [rsp+248h+var_80], esi
0x180014db1  jnz     short loc_180014DBC
0x180014db3  cmp     [rsp+248h+var_7C], esi
0x180014dba  jz      short loc_180014DC6
0x180014dbc  lea     r9, [rsp+248h+var_88]
0x180014dc4  jmp     short loc_180014DC9
0x180014dc6  mov     r9, rsi
0x180014dc9  lea     rax, [rsp+248h+var_78]
0x180014dd1  mov     [rsp+248h+pvData], rax
0x180014dd6  mov     dword ptr [rsp+248h+phkResult], 2
0x180014dde  lea     r8, [rsp+248h+ActivityId]
0x180014de6  lea     rdx, word_18004F5E2
0x180014ded  lea     rcx, dword_18005A000
0x180014df4  call    _tlgWriteTransfer_EventWriteTransfer
0x180014df9  mov     [rsp+248h+var_170], rdi
0x180014e01  lea     rax, [rsp+248h+var_A0]
0x180014e09  mov     [rsp+248h+var_168], rax
0x180014e11  lea     rax, [rsp+248h+var_200]
0x180014e16  mov     [rsp+248h+var_160], rax
0x180014e1e  mov     [rsp+248h+var_158], 1
0x180014e26  lea     rcx, [rsp+248h+var_1C8]; phkResult
0x180014e2e  call    ??0PackageInfo@@QEAA@XZ; PackageInfo::PackageInfo(void)
0x180014e33  nop
0x180014e34  xorps   xmm0, xmm0
0x180014e37  movdqu  [rsp+248h+var_1E8], xmm0
0x180014e3d  mov     [rsp+248h+var_1D8], rsi
0x180014e42  mov     rbx, [rdi]
0x180014e45  mov     rdi, [rdi+8]
0x180014e49  mov     r15d, 7
0x180014e4f  cmp     rbx, rdi
0x180014e52  jz      loc_18001548F
0x180014e58  mov     rcx, [rbx]
0x180014e5b  mov     rax, [rcx]
0x180014e5e  mov     rax, [rax+48h]
0x180014e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e67  test    al, al
0x180014e69  jz      loc_180015486
0x180014e6f  mov     rcx, [rbx]
0x180014e72  mov     rax, [rcx]
0x180014e75  lea     rdx, [rsp+248h+var_120]
0x180014e7d  mov     rax, [rax]
0x180014e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e85  nop
0x180014e86  mov     rcx, [rbx]
0x180014e89  mov     rax, [rcx]
0x180014e8c  lea     rdx, [rsp+248h+String1]
0x180014e94  mov     rax, [rax+10h]
0x180014e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9d  nop
0x180014e9e  mov     rcx, [rbx]
0x180014ea1  mov     rax, [rcx]
0x180014ea4  lea     rdx, [rsp+248h+var_E0]
0x180014eac  mov     rax, [rax+18h]
0x180014eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb5  nop
0x180014eb6  mov     rcx, [rbx]
0x180014eb9  mov     rax, [rcx]
0x180014ebc  lea     rdx, [rsp+248h+var_100]
0x180014ec4  mov     rax, [rax+20h]
0x180014ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ecd  nop
0x180014ece  lea     rdx, [rsp+248h+var_1B8]
0x180014ed6  lea     rcx, [rsp+248h+var_1C8]
0x180014ede  call    ?getPackageVersionInfo@PackageInfo@@QEAA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ; PackageInfo::getPackageVersionInfo(void)
0x180014ee3  nop
0x180014ee4  mov     r8, rbx
0x180014ee7  lea     rdx, [rsp+248h+var_1B8]
0x180014eef  call    ?ResolveServicedPackages@CMVEngine@@AEAAJAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@3@@Z; CMVEngine::ResolveServicedPackages(std::unordered_map<std::wstring,std::wstring> const &,std::unique_ptr<ProvPackage> const &)
0x180014ef4  test    eax, eax
0x180014ef6  jns     short loc_180014F50
0x180014ef8  mov     ecx, cs:dword_18005A000
0x180014efe  cmp     ecx, 2
0x180014f01  jbe     short loc_180014F50
0x180014f03  mov     dword ptr [rsp+248h+hkey], eax
0x180014f07  lea     rax, [rsp+248h+String1]
0x180014f0f  cmp     [rsp+248h+var_128], 8
0x180014f18  cmovnb  rax, qword ptr [rsp+248h+String1]
0x180014f21  mov     [rsp+248h+var_1F0], rax
0x180014f26  lea     rax, [rsp+248h+hkey]
0x180014f2b  mov     [rsp+248h+pvData], rax
0x180014f30  lea     rax, [rsp+248h+var_1F0]
0x180014f35  mov     [rsp+248h+phkResult], rax
0x180014f3a  xor     r8d, r8d
0x180014f3d  lea     rdx, byte_18004EE57
0x180014f44  lea     rcx, dword_18005A000
0x180014f4b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014f50  mov     rcx, [rbx]
0x180014f53  mov     rax, [rcx]
0x180014f56  mov     rax, [rax+58h]
0x180014f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f5f  test    al, al
0x180014f61  jz      loc_180015397
0x180014f67  cmp     [rsp+248h+var_128], 8
0x180014f70  jb      short loc_180014F85
0x180014f72  mov     rcx, qword ptr [rsp+248h+String1]
0x180014f7a  test    rcx, rcx
0x180014f7d  jz      loc_180015285
0x180014f83  jmp     short loc_180014F8D
0x180014f85  lea     rcx, [rsp+248h+String1]; String1
0x180014f8d  lea     rdx, aEb7d7f2f3b774b; "{eb7d7f2f-3b77-4b87-b301-fd0d336f709a}"
0x180014f94  call    cs:__imp__wcsicmp
0x180014f9a  test    eax, eax
0x180014f9c  jnz     loc_180015285
0x180014fa2  mov     [rsp+248h+hkey], rsi
0x180014fa7  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180014fac  lea     rcx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Provisioning\\"
0x180014fb3  lea     rdx, aOsdataSoftware_8; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180014fba  test    al, al
0x180014fbc  cmovz   rdx, rcx; lpSubKey
0x180014fc0  lea     rax, [rsp+248h+hkey]
0x180014fc5  mov     [rsp+248h+phkResult], rax; phkResult
0x180014fca  mov     r9d, 2001Fh; samDesired
0x180014fd0  xor     r8d, r8d; ulOptions
0x180014fd3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014fda  call    cs:__imp_RegOpenKeyExW
0x180014fe0  mov     rcx, [rsp+248h+hkey]; hkey
0x180014fe5  test    eax, eax
0x180014fe7  jnz     loc_18001527A
0x180014fed  mov     [rsp+248h+var_1F8], esi
0x180014ff1  mov     [rsp+248h+var_1FC], 4
0x180014ff9  lea     rax, [rsp+248h+var_1FC]
0x180014ffe  mov     [rsp+248h+pcbData], rax; pcbData
0x180015003  lea     rax, [rsp+248h+var_1F8]
0x180015008  mov     [rsp+248h+pvData], rax; pvData
0x18001500d  mov     [rsp+248h+phkResult], rsi; pdwType
0x180015012  mov     r9d, 10h; dwFlags
0x180015018  lea     r8, aSkipsecurecore; "SkipSecureCorePackage"
0x18001501f  lea     rdx, aSkippackages; "SkipPackages"
0x180015026  call    cs:__imp_RegGetValueW
0x18001502c  test    eax, eax
0x18001502e  jnz     loc_180015275
0x180015034  cmp     [rsp+248h+var_1FC], 4
0x180015039  jnz     loc_180015275
0x18001503f  mov     rcx, [rsp+248h+hkey]; hKey
0x180015044  cmp     [rsp+248h+var_1F8], 1
0x180015049  jnz     loc_18001527A
0x18001504f  test    rcx, rcx
0x180015052  jz      short loc_18001505A
0x180015054  call    cs:__imp_RegCloseKey
0x18001505a  mov     eax, cs:dword_18005A000
0x180015060  cmp     eax, 4
0x180015063  jbe     loc_180015197
0x180015069  mov     rcx, cs:qword_18005A018
0x180015070  mov     rax, cs:qword_18005A010
0x180015077  mov     rdx, 400000000000h
0x180015081  test    rdx, rax
0x180015084  jz      loc_180015197
0x18001508a  mov     rax, rcx
0x18001508d  and     rax, rdx
0x180015090  cmp     rax, rcx
0x180015093  jnz     loc_180015197
0x180015099  mov     [rsp+248h+var_1F0], 2000000h
0x1800150a2  lea     rax, [rsp+248h+var_120]
0x1800150aa  cmp     [rsp+248h+var_108], 8
0x1800150b3  cmovnb  rax, [rsp+248h+var_120]
0x1800150bc  lea     rcx, [rsp+248h+String1]
0x1800150c4  cmp     [rsp+248h+var_128], 8
0x1800150cd  cmovnb  rcx, qword ptr [rsp+248h+String1]
0x1800150d6  lea     rdx, [rsp+248h+var_1F0]
0x1800150db  mov     [rsp+248h+var_38], rdx
0x1800150e3  mov     [rsp+248h+var_30], 8
0x1800150ef  test    rax, rax
0x1800150f2  jz      short loc_18001510A
0x1800150f4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800150f8  inc     rdx
0x1800150fb  cmp     [rax+rdx*2], si
0x1800150ff  jnz     short loc_1800150F8
0x180015101  lea     edx, ds:2[rdx*2]
0x180015108  jmp     short loc_180015116
0x18001510a  lea     rax, qword_180049F78
0x180015111  mov     edx, 2
0x180015116  mov     [rsp+248h+var_48], rax
0x18001511e  mov     [rsp+248h+var_40], edx
0x180015125  mov     [rsp+248h+var_3C], esi
0x18001512c  test    rcx, rcx
0x18001512f  jz      short loc_180015147
0x180015131  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015135  inc     rax
0x180015138  cmp     [rcx+rax*2], si
0x18001513c  jnz     short loc_180015135
0x18001513e  lea     eax, ds:2[rax*2]
0x180015145  jmp     short loc_180015153
0x180015147  lea     rcx, qword_180049F78
0x18001514e  mov     eax, 2
0x180015153  mov     [rsp+248h+var_58], rcx
0x18001515b  mov     dword ptr [rsp+248h+var_50], eax
0x180015162  mov     dword ptr [rsp+248h+var_50+4], esi
0x180015169  lea     rax, [rsp+248h+var_78]
0x180015171  mov     [rsp+248h+pvData], rax
0x180015176  mov     dword ptr [rsp+248h+phkResult], 5
0x18001517e  xor     r9d, r9d
0x180015181  xor     r8d, r8d
0x180015184  lea     rdx, word_18004E7FA
0x18001518b  lea     rcx, dword_18005A000
0x180015192  call    _tlgWriteTransfer_EventWriteTransfer
0x180015197  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x18001519e  jz      short loc_18001520A
0x1800151a0  mov     rcx, [rbx]
0x1800151a3  mov     rax, [rcx]
0x1800151a6  lea     rdx, [rsp+248h+var_78]
0x1800151ae  mov     rax, [rax+10h]
0x1800151b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b7  mov     r15, rax
0x1800151ba  or      r14d, 1
0x1800151be  mov     dword ptr [rsp+248h+hkey], r14d
0x1800151c3  cmp     qword ptr [rax+18h], 8
0x1800151c8  jb      short loc_1800151CD
0x1800151ca  mov     r15, [rax]
0x1800151cd  mov     rcx, [rbx]
0x1800151d0  mov     rax, [rcx]
0x1800151d3  lea     rdx, [rsp+248h+var_C0]
0x1800151db  mov     rax, [rax+8]
0x1800151df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151e4  or      r14d, 2
0x1800151e8  cmp     qword ptr [rax+18h], 8
0x1800151ed  jb      short loc_1800151F2
0x1800151ef  mov     rax, [rax]
0x1800151f2  mov     r9, r15
0x1800151f5  mov     r8, rax
0x1800151f8  lea     rdx, PackageSkipped
0x1800151ff  call    McTemplateU0zz_EventWriteTransfer
0x180015204  mov     r15d, 7
0x18001520a  test    r14b, 2
0x18001520e  jz      short loc_180015245
0x180015210  and     r14d, 0FFFFFFFDh
0x180015214  cmp     [rsp+248h+var_A8], 8
0x18001521d  jb      short loc_18001522D
0x18001521f  mov     rcx, [rsp+248h+var_C0]
0x180015227  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001522d  mov     [rsp+248h+var_A8], r15
0x180015235  mov     [rsp+248h+var_B0], rsi
0x18001523d  mov     word ptr [rsp+248h+var_C0], si
0x180015245  test    r14b, 1
0x180015249  jz      loc_180015397
0x18001524f  and     r14d, 0FFFFFFFEh
0x180015253  cmp     [rsp+248h+var_60], 8
0x18001525c  jb      loc_180015397
0x180015262  mov     rcx, [rsp+248h+var_78]
0x18001526a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015270  jmp     loc_180015397
0x180015275  mov     rcx, [rsp+248h+hkey]; hKey
0x18001527a  test    rcx, rcx
0x18001527d  jz      short loc_180015285
0x18001527f  call    cs:__imp_RegCloseKey
0x180015285  lea     rcx, [rsp+248h+hKey]; phkResult
0x18001528a  call    ??0PackageInfo@@QEAA@XZ; PackageInfo::PackageInfo(void)
0x18001528f  nop
0x180015290  mov     rdx, [rbx]; struct ProvPackage *
0x180015293  lea     rcx, [rsp+248h+hKey]; this
0x180015298  call    ?Add@PackageInfo@@QEAAXAEBVProvPackage@@@Z; PackageInfo::Add(ProvPackage const &)
0x18001529d  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 1
0x1800152a4  jz      short loc_180015310
0x1800152a6  mov     rcx, [rbx]
0x1800152a9  mov     rax, [rcx]
0x1800152ac  lea     rdx, [rsp+248h+var_78]
0x1800152b4  mov     rax, [rax+10h]
0x1800152b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152bd  mov     r15, rax
0x1800152c0  or      r14d, 4
0x1800152c4  mov     dword ptr [rsp+248h+hkey], r14d
0x1800152c9  cmp     qword ptr [rax+18h], 8
0x1800152ce  jb      short loc_1800152D3
0x1800152d0  mov     r15, [rax]
  ... truncated ...
```
