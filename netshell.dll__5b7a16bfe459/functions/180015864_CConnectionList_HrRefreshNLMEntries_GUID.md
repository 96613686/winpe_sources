# CConnectionList::HrRefreshNLMEntries(_GUID *)

- ea: `0x180015864`
- end: `0x1800161b4`
- name: `?HrRefreshNLMEntries@CConnectionList@@QEAAJPEAU_GUID@@@Z`
- size: `2384`
- prototype: `__int64 __fastcall(CConnectionList *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800154c8`

## callees

- `0x180002460`
- `0x180002898`
- `0x1800032b0`
- `0x180015864`
- `0x1800161bc`
- `0x18001625c`
- `0x180016324`
- `0x18001644c`
- `0x180016540`
- `0x180016568`
- `0x180016618`
- `0x180016678`
- `0x1800166ac`
- `0x1800166dc`
- `0x18001670c`
- `0x18001673c`
- `0x180016eb4`
- `0x180017674`
- `0x180019898`
- `0x18001e1e0`
- `0x18001eb7c`
- `0x1800232d8`
- `0x180025824`
- `0x180034a44`
- `0x180041994`
- `0x180041ac0`
- `0x180041d6c`
- `0x1800428fc`
- `0x180042d3c`
- `0x180049d08`
- `0x18004aa24`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015dbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c8c`
- `ole32!CoTaskMemFree` at `0x180015f9e`
- `ole32!CoTaskMemFree` at `0x180015f9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f90`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f7d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f90`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180015ff8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180015ff8`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180016003`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180016003`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CConnectionList::HrRefreshNLMEntries(CConnectionList *this, struct _GUID *a2)
{
  CConnectionList *v2; // rdi
  int updated; // r15d
  unsigned int v4; // eax
  unsigned int i; // ebx
  _QWORD *v6; // rsi
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // edi
  _QWORD *v11; // rax
  int v12; // r15d
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 *v15; // rbx
  const struct _GUID *v16; // rbx
  __int64 v17; // rax
  const struct _GUID **v18; // rcx
  const struct _GUID *n; // rax
  const struct _GUID *ii; // rcx
  __int64 v21; // rdi
  __int64 **v22; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  __int128 *v25; // rsi
  _QWORD *v26; // rax
  CConnectionList *v27; // r12
  __int64 v28; // r12
  OLECHAR *v29; // rsi
  OLECHAR *v30; // rcx
  CConnectionList *v31; // rsi
  const wchar_t **v32; // r12
  const wchar_t *v33; // rcx
  UINT v34; // eax
  BSTR v35; // rax
  _WORD *v36; // rdx
  __int64 v37; // r8
  const unsigned __int16 *Ids; // rax
  __int64 v39; // r8
  __int64 m; // rax
  __int64 v42; // [rsp+78h] [rbp-6A0h] BYREF
  const wchar_t *v43; // [rsp+80h] [rbp-698h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-690h] BYREF
  unsigned int v45; // [rsp+90h] [rbp-688h] BYREF
  CConnectionList *v46; // [rsp+98h] [rbp-680h]
  void *v47; // [rsp+A0h] [rbp-678h] BYREF
  __int128 v48; // [rsp+A8h] [rbp-670h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-660h] BYREF
  _QWORD *v50; // [rsp+C0h] [rbp-658h]
  CConnectionList *v51; // [rsp+C8h] [rbp-650h] BYREF
  _BYTE v52[8]; // [rsp+D0h] [rbp-648h] BYREF
  __int128 v53; // [rsp+D8h] [rbp-640h] BYREF
  int v54; // [rsp+E8h] [rbp-630h]
  BSTR bstrString; // [rsp+F0h] [rbp-628h] BYREF
  __int128 v56; // [rsp+100h] [rbp-618h] BYREF
  _BYTE v57[16]; // [rsp+110h] [rbp-608h] BYREF
  _BYTE v58[16]; // [rsp+120h] [rbp-5F8h] BYREF
  _BYTE v59[16]; // [rsp+130h] [rbp-5E8h] BYREF
  __int128 v60; // [rsp+140h] [rbp-5D8h] BYREF
  __int128 v61; // [rsp+150h] [rbp-5C8h] BYREF
  __int128 v62; // [rsp+160h] [rbp-5B8h] BYREF
  _BYTE v63[16]; // [rsp+170h] [rbp-5A8h] BYREF
  int v64; // [rsp+180h] [rbp-598h]
  int v65; // [rsp+184h] [rbp-594h]
  int v66; // [rsp+188h] [rbp-590h]
  _BYTE v67[32]; // [rsp+190h] [rbp-588h] BYREF
  _QWORD v68[100]; // [rsp+1B0h] [rbp-568h] BYREF
  unsigned __int16 v69[4]; // [rsp+4D0h] [rbp-248h] BYREF
  _BYTE v70[520]; // [rsp+4D8h] [rbp-240h] BYREF

  v2 = this;
  v46 = this;
  v51 = this;
  v47 = 0;
  updated = HrCreateInstanceBase(&CLSID_CNetworkListManager, 0x404u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v47);
  if ( updated < 0 )
    goto LABEL_94;
  v49 = 0;
  updated = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v47 + 40LL))(v47, &v49);
  if ( updated < 0 )
    goto LABEL_92;
  v48 = 0;
  std::_Tree<std::_Tmap_traits<_GUID,CNetworkListInterfaceEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListInterfaceEntry>>,0>>::_Alloc_sentinel_and_proxy(&v48);
  v45 = 0;
  memset_0(v68, 0, sizeof(v68));
LABEL_4:
  updated = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, unsigned int *))(*(_QWORD *)v49 + 24LL))(
              v49,
              100,
              v68,
              &v45);
  if ( updated >= 0 )
  {
    v4 = v45;
    if ( v45 )
    {
      for ( i = 0; ; ++i )
      {
        LODWORD(v43) = i;
        if ( i >= v4 )
          goto LABEL_4;
        v6 = &v68[i];
        v60 = 0;
        v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v6 + 32LL))(*v6, &v60);
        v8 = *v6;
        if ( v7 < 0 )
          goto LABEL_9;
        v61 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 40LL))(v8, &v61);
        v8 = *v6;
        if ( v9 < 0 )
          goto LABEL_9;
        LODWORD(v42) = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL))(v8, &v42) < 0 )
          break;
        v50 = &v68[i];
        pv = 0;
        v10 = 0;
        if ( (*(int (__fastcall **)(void *, __int128 *, LPVOID *))(*(_QWORD *)v47 + 48LL))(v47, &v61, &pv) >= 0 )
          v10 = IsCorpConnected((struct INetworkPrivate *)pv);
        try
        {
          v11 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::find(
                            &v48,
                            v52,
                            &v60);
          if ( *v11 == (_QWORD)v48 )
          {
            v56 = v61;
            v12 = v42;
            std::map<_GUID,bool>::map<_GUID,bool>(v63);
            std::wstring::wstring((__int64)v67);
            *(_BYTE *)(*(_QWORD *)std::map<_GUID,bool>::_Try_emplace<_GUID const &,>(v63, v58, &v56) + 44LL) = 1;
            v62 = v60;
            v64 = v12;
            v65 = v10;
            v66 = 0;
            v13 = *(_QWORD *)std::map<_GUID,CNetworkListInterfaceEntry>::_Try_emplace<_GUID const &,>(&v48, v59, &v60);
            *(_OWORD *)(v13 + 48) = v62;
            std::_Tree<std::_Tmap_traits<_GUID,bool,std::less<_GUID>,std::allocator<std::pair<_GUID const,bool>>,0>>::operator=(
              v13 + 64,
              v63);
            *(_DWORD *)(v13 + 80) = v64;
            *(_DWORD *)(v13 + 84) = v65;
            *(_DWORD *)(v13 + 88) = v66;
            std::wstring::operator=(v13 + 96, v67);
            CNetworkListInterfaceEntry::~CNetworkListInterfaceEntry((CNetworkListInterfaceEntry *)&v62);
          }
          else
          {
            v14 = *(_QWORD *)std::map<_GUID,CNetworkListInterfaceEntry>::_Try_emplace<_GUID const &,>(&v48, &v53, &v60);
            *(_DWORD *)(v14 + 80) |= v42;
            *(_DWORD *)(v14 + 84) = v10;
            *(_BYTE *)(*(_QWORD *)std::map<_GUID,bool>::_Try_emplace<_GUID const &,>(v14 + 64, v57, &v61) + 44LL) = 1;
          }
        }
        catch ( std::bad_alloc )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 16LL))(*v50);
          ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&pv);
          i = (unsigned int)v43;
          v2 = v51;
          v46 = v51;
          goto LABEL_19;
        }
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
        ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&pv);
        v2 = v46;
LABEL_19:
        v4 = v45;
      }
      v8 = *v6;
LABEL_9:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      goto LABEL_19;
    }
  }
  v15 = *(__int64 **)v48;
LABEL_21:
  if ( v15 != (__int64 *)v48 )
  {
    v21 = *(_QWORD *)v15[8];
    while ( 1 )
    {
      if ( v21 == v15[8] )
      {
        v22 = (__int64 **)v15[2];
        if ( *((_BYTE *)v22 + 25) )
        {
          for ( j = (__int64 *)v15[1]; !*((_BYTE *)j + 25) && v15 == (__int64 *)j[2]; j = (__int64 *)j[1] )
            v15 = j;
          v15 = j;
        }
        else
        {
          v15 = (__int64 *)v15[2];
          for ( k = *v22; !*((_BYTE *)k + 25); k = (__int64 *)*k )
            v15 = k;
        }
        v2 = v46;
        goto LABEL_21;
      }
      try
      {
        v25 = (__int128 *)(v21 + 28);
        v60 = 0;
        std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::_Alloc_sentinel_and_proxy(&v60);
        v26 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::find(
                          &v60,
                          v52,
                          v21 + 28);
        v27 = (CConnectionList *)v60;
        if ( *v26 != (_QWORD)v60 )
          goto LABEL_63;
        v42 = 0;
        updated = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)v47 + 48LL))(v47, v21 + 28, &v42);
        if ( updated < 0 )
          goto LABEL_62;
        LODWORD(v43) = 0;
        updated = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v42 + 104LL))(v42, &v43);
        if ( updated < 0
          || (pv = 0,
              updated = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v42 + 24LL))(v42, &pv),
              updated < 0) )
        {
          ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v42);
        }
        else
        {
          bstrString = 0;
          v53 = *v25;
          v54 = (int)v43;
          ATL::CComBSTR::operator=(&bstrString, (const OLECHAR *)pv);
          v28 = *(_QWORD *)std::map<_GUID,CNetworkListNetworkEntry>::_Try_emplace<_GUID const &,>(&v60, v57, v21 + 28);
          *(_OWORD *)(v28 + 48) = v53;
          *(_DWORD *)(v28 + 64) = v54;
          v29 = bstrString;
          v30 = *(OLECHAR **)(v28 + 72);
          if ( v30 != bstrString )
          {
            SysFreeString(v30);
            if ( v29 )
            {
              v34 = SysStringByteLen(v29);
              v35 = SysAllocStringByteLen((LPCSTR)v29, v34);
              *(_QWORD *)(v28 + 72) = v35;
              if ( !v35 )
                ATL::AtlThrowImpl(-2147024882);
            }
            else
            {
              *(_QWORD *)(v28 + 72) = 0;
            }
          }
          SysFreeString(v29);
          CoTaskMemFree(pv);
          v25 = (__int128 *)(v21 + 28);
LABEL_62:
          ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v42);
          v27 = (CConnectionList *)v60;
LABEL_63:
          std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::find(
            &v60,
            &v51,
            v25);
          v31 = v51;
          if ( v51 != v27 )
          {
            v32 = (const wchar_t **)(v15 + 12);
            if ( (unsigned __int64)v15[15] <= 7 )
              v33 = (const wchar_t *)(v15 + 12);
            else
              v33 = *v32;
            if ( std::_Traits_compare<std::char_traits<unsigned short>>(v33, v15[14], &Caption, 0) )
            {
              v50 = (_QWORD *)*((_QWORD *)v31 + 9);
              if ( (unsigned __int64)v15[15] <= 7 )
                v43 = (const wchar_t *)(v15 + 12);
              else
                v43 = *v32;
              Ids = SzLoadIds(0x486u);
              if ( DwFormatString(Ids, v69, 0x104u, v43, v50) )
              {
                v39 = -1;
                do
                  ++v39;
                while ( v69[v39] );
                std::wstring::_Assign<unsigned short>((char **)v15 + 12, v69, (char *)v39);
              }
            }
            else
            {
              v36 = (_WORD *)*((_QWORD *)v31 + 9);
              v37 = -1;
              do
                ++v37;
              while ( v36[v37] );
              std::wstring::_Assign<unsigned short>((char **)v15 + 12, v36, (char *)v37);
            }
            if ( v15[9] == 1 )
              *((_DWORD *)v15 + 22) = *((_DWORD *)v31 + 16);
            else
              *((_DWORD *)v15 + 22) = 0;
          }
        }
        std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::~_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>(&v60);
        if ( *(_BYTE *)(*(_QWORD *)(v21 + 16) + 25LL) )
        {
          for ( m = *(_QWORD *)(v21 + 8); !*(_BYTE *)(m + 25) && v21 == *(_QWORD *)(m + 16); m = *(_QWORD *)(m + 8) )
            v21 = m;
        }
        else
        {
          m = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,ConnListEntry>>>::_Min();
        }
        v21 = m;
      }
      catch ( std::bad_alloc )
      {
        LODWORD(v43) = -2147024882;
        updated = -2147024882;
        goto LABEL_91;
      }
    }
  }
  if ( updated >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)v2 + 2);
    v16 = *(const struct _GUID **)v48;
    while ( v16 != (const struct _GUID *)v48 )
    {
      ConnListEntry::ConnListEntry((ConnListEntry *)v69);
      if ( !(unsigned int)CConnectionList::HrFindConnectionByGuid((__int64 **)v46, v16 + 2, (struct ConnListEntry *)v69) )
      {
        v17 = *(_QWORD *)v16[7].Data4 <= 7u ? (__int64)&v16[6] : *(_QWORD *)&v16[6].Data1;
        updated = CConFoldEntry::UpdateData(
                    v70,
                    1792,
                    3,
                    1,
                    0,
                    0,
                    0,
                    0,
                    0,
                    v17,
                    v16[5].Data1,
                    *(_DWORD *)&v16[5].Data2,
                    *(_DWORD *)v16[5].Data4);
        if ( updated >= 0 )
          updated = CConnectionList::HrUpdateConnectionByGuid(v46, v16 + 2, (const struct ConnListEntry *)v69);
      }
      ConnListEntry::~ConnListEntry((ConnListEntry *)v69);
      v18 = *(const struct _GUID ***)&v16[1].Data1;
      if ( *((_BYTE *)v18 + 25) )
      {
        for ( n = *(const struct _GUID **)v16->Data4;
              !n[1].Data4[1] && v16 == *(const struct _GUID **)&n[1].Data1;
              n = *(const struct _GUID **)n->Data4 )
        {
          v16 = n;
        }
        v16 = n;
      }
      else
      {
        v16 = *(const struct _GUID **)&v16[1].Data1;
        for ( ii = *v18; !ii[1].Data4[1]; ii = *(const struct _GUID **)&ii->Data1 )
          v16 = ii;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)v2 + 2);
  }
LABEL_91:
  std::_Tree<std::_Tmap_traits<_GUID,CNetworkListInterfaceEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListInterfaceEntry>>,0>>::~_Tree<std::_Tmap_traits<_GUID,CNetworkListInterfaceEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListInterfaceEntry>>,0>>(&v48);
LABEL_92:
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v49);
  if ( updated >= 0 )
    updated = 1;
LABEL_94:
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&v47);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180015864  mov     r11, rsp
0x180015867  mov     [r11+10h], rbx
0x18001586b  mov     [r11+18h], rsi
0x18001586f  push    rdi
0x180015870  push    r12
0x180015872  push    r13
0x180015874  push    r14
0x180015876  push    r15
0x180015878  sub     rsp, 6F0h
0x18001587f  mov     rax, cs:__security_cookie
0x180015886  xor     rax, rsp
0x180015889  mov     [rsp+718h+var_38], rax
0x180015891  mov     rdi, rcx
0x180015894  mov     [rsp+718h+var_680], rcx
0x18001589c  mov     [rsp+718h+var_650], rcx
0x1800158a4  xor     r14d, r14d
0x1800158a7  mov     [r11-678h], r14
0x1800158ae  lea     r9, [r11-678h]; void **
0x1800158b5  lea     r8, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; struct _GUID *
0x1800158bc  mov     edx, 404h; unsigned int
0x1800158c1  lea     rcx, CLSID_CNetworkListManager; struct _GUID *
0x1800158c8  call    ?HrCreateInstanceBase@@YAJAEBU_GUID@@K0PEAPEAX@Z; HrCreateInstanceBase(_GUID const &,ulong,_GUID const &,void * *)
0x1800158cd  mov     r15d, eax
0x1800158d0  test    eax, eax
0x1800158d2  js      loc_180016177
0x1800158d8  mov     r13d, r14d
0x1800158db  mov     [rsp+718h+var_6A8], r14d
0x1800158e0  mov     [rsp+718h+var_660], r14
0x1800158e8  mov     rcx, [rsp+718h+var_678]
0x1800158f0  mov     rax, [rcx]
0x1800158f3  lea     rdx, [rsp+718h+var_660]
0x1800158fb  mov     rax, [rax+28h]
0x1800158ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015904  mov     r15d, eax
0x180015907  test    eax, eax
0x180015909  js      loc_180016158
0x18001590f  xorps   xmm0, xmm0
0x180015912  movdqu  [rsp+718h+var_670], xmm0
0x18001591b  lea     rcx, [rsp+718h+var_670]
0x180015923  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@VCNetworkListInterfaceEntry@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VCNetworkListInterfaceEntry@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,CNetworkListInterfaceEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListInterfaceEntry>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180015928  nop
0x180015929  mov     [rsp+718h+var_688], r14d
0x180015931  xor     edx, edx; Val
0x180015933  mov     r8d, 320h; Size
0x180015939  lea     rcx, [rsp+718h+var_568]; void *
0x180015941  call    memset_0
0x180015946  lea     r12d, [r14+1]
0x18001594a  mov     rcx, [rsp+718h+var_660]
0x180015952  mov     rax, [rcx]
0x180015955  lea     r9, [rsp+718h+var_688]
0x18001595d  lea     r8, [rsp+718h+var_568]
0x180015965  mov     edx, 64h ; 'd'
0x18001596a  mov     rax, [rax+18h]
0x18001596e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015973  mov     r15d, eax
0x180015976  test    eax, eax
0x180015978  js      loc_180015C66
0x18001597e  mov     eax, [rsp+718h+var_688]
0x180015985  test    eax, eax
0x180015987  jz      loc_180015C66
0x18001598d  mov     ebx, r14d
0x180015990  mov     dword ptr [rsp+718h+var_698], ebx
0x180015997  cmp     ebx, eax
0x180015999  jnb     short loc_18001594A
0x18001599b  mov     eax, ebx
0x18001599d  lea     rsi, [rsp+718h+var_568]
0x1800159a5  lea     rsi, [rsi+rax*8]
0x1800159a9  xorps   xmm0, xmm0
0x1800159ac  movups  [rsp+718h+var_5D8], xmm0
0x1800159b4  mov     rcx, [rsi]
0x1800159b7  mov     rax, [rcx]
0x1800159ba  lea     rdx, [rsp+718h+var_5D8]
0x1800159c2  mov     rax, [rax+20h]
0x1800159c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159cb  mov     rcx, [rsi]
0x1800159ce  test    eax, eax
0x1800159d0  jns     short loc_1800159E3
0x1800159d2  mov     rax, [rcx]
0x1800159d5  mov     rax, [rax+10h]
0x1800159d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159de  jmp     loc_180015C57
0x1800159e3  mov     [rsp+718h+var_6A8], r13d
0x1800159e8  xorps   xmm0, xmm0
0x1800159eb  movups  [rsp+718h+var_5C8], xmm0
0x1800159f3  mov     rax, [rcx]
0x1800159f6  lea     rdx, [rsp+718h+var_5C8]
0x1800159fe  mov     rax, [rax+28h]
0x180015a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a07  mov     rcx, [rsi]
0x180015a0a  test    eax, eax
0x180015a0c  jns     short loc_180015A1F
0x180015a0e  mov     rax, [rcx]
0x180015a11  mov     rax, [rax+10h]
0x180015a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a1a  jmp     loc_180015C52
0x180015a1f  mov     dword ptr [rsp+718h+var_6A0], r14d
0x180015a24  mov     rax, [rcx]
0x180015a27  lea     rdx, [rsp+718h+var_6A0]
0x180015a2c  mov     rax, [rax+38h]
0x180015a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a35  test    eax, eax
0x180015a37  jns     short loc_180015A3E
0x180015a39  mov     rcx, [rsi]
0x180015a3c  jmp     short loc_180015A0E
0x180015a3e  mov     [rsp+718h+var_658], rsi
0x180015a46  mov     [rsp+718h+pv], r14
0x180015a4e  mov     edi, r14d
0x180015a51  mov     rcx, [rsp+718h+var_678]
0x180015a59  mov     rax, [rcx]
0x180015a5c  lea     r8, [rsp+718h+pv]
0x180015a64  lea     rdx, [rsp+718h+var_5C8]
0x180015a6c  mov     rax, [rax+30h]
0x180015a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a75  test    eax, eax
0x180015a77  js      short loc_180015A88
0x180015a79  mov     rcx, [rsp+718h+pv]; struct INetworkPrivate *
0x180015a81  call    ?IsCorpConnected@@YAHPEAUINetworkPrivate@@@Z; IsCorpConnected(INetworkPrivate *)
0x180015a86  mov     edi, eax
0x180015a88  lea     r8, [rsp+718h+var_5D8]
0x180015a90  lea     rdx, [rsp+718h+var_648]
0x180015a98  lea     rcx, [rsp+718h+var_670]
0x180015aa0  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@VCNetworkListNetworkEntry@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VCNetworkListNetworkEntry@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@VCNetworkListNetworkEntry@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CNetworkListNetworkEntry,std::less<_GUID>,std::allocator<std::pair<_GUID const,CNetworkListNetworkEntry>>,0>>::find(_GUID const &)
0x180015aa5  mov     rcx, qword ptr [rsp+718h+var_670]
0x180015aad  cmp     [rax], rcx
0x180015ab0  jnz     loc_180015BB1
0x180015ab6  movaps  xmm0, [rsp+718h+var_5C8]
0x180015abe  movdqa  [rsp+718h+var_618], xmm0
0x180015ac7  mov     r15d, dword ptr [rsp+718h+var_6A0]
0x180015acc  lea     rcx, [rsp+718h+var_5A8]
0x180015ad4  call    ??0?$map@U_GUID@@_NU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@3@@std@@QEAA@XZ; std::map<_GUID,bool>::map<_GUID,bool>(void)
0x180015ad9  nop
0x180015ada  lea     rcx, [rsp+718h+var_588]
0x180015ae2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015ae7  nop
0x180015ae8  lea     r8, [rsp+718h+var_618]
0x180015af0  lea     rdx, [rsp+718h+var_5F8]
0x180015af8  lea     rcx, [rsp+718h+var_5A8]
0x180015b00  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@_NU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@_N@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,bool>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180015b05  mov     rax, [rax]
0x180015b08  mov     [rax+2Ch], r12b
0x180015b0c  movups  xmm0, [rsp+718h+var_5D8]
0x180015b14  movdqu  [rsp+718h+var_5B8], xmm0
0x180015b1d  mov     [rsp+718h+var_598], r15d
0x180015b25  mov     [rsp+718h+var_594], edi
0x180015b2c  mov     [rsp+718h+var_590], r14d
0x180015b34  lea     r8, [rsp+718h+var_5D8]
0x180015b3c  lea     rdx, [rsp+718h+var_5E8]
0x180015b44  lea     rcx, [rsp+718h+var_670]
0x180015b4c  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@VCNetworkListInterfaceEntry@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VCNetworkListInterfaceEntry@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VCNetworkListInterfaceEntry@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,CNetworkListInterfaceEntry>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180015b51  mov     rdi, [rax]
0x180015b54  movaps  xmm0, [rsp+718h+var_5B8]
0x180015b5c  movdqu  xmmword ptr [rdi+30h], xmm0
0x180015b61  lea     rcx, [rdi+40h]
0x180015b65  lea     rdx, [rsp+718h+var_5A8]
0x180015b6d  call    ??4?$_Tree@V?$_Tmap_traits@U_GUID@@_NU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@3@$0A@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::_Tree<std::_Tmap_traits<_GUID,bool,std::less<_GUID>,std::allocator<std::pair<_GUID const,bool>>,0>>::operator=(std::_Tree<std::_Tmap_traits<_GUID,bool,std::less<_GUID>,std::allocator<std::pair<_GUID const,bool>>,0>> const &)
0x180015b72  mov     eax, [rsp+718h+var_598]
0x180015b79  mov     [rdi+50h], eax
0x180015b7c  mov     eax, [rsp+718h+var_594]
0x180015b83  mov     [rdi+54h], eax
0x180015b86  mov     eax, [rsp+718h+var_590]
0x180015b8d  mov     [rdi+58h], eax
0x180015b90  lea     rcx, [rdi+60h]
0x180015b94  lea     rdx, [rsp+718h+var_588]
0x180015b9c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180015ba1  nop
0x180015ba2  lea     rcx, [rsp+718h+var_5B8]; this
0x180015baa  call    ??1CNetworkListInterfaceEntry@@QEAA@XZ; CNetworkListInterfaceEntry::~CNetworkListInterfaceEntry(void)
0x180015baf  jmp     short loc_180015BFB
0x180015bb1  lea     r8, [rsp+718h+var_5D8]
0x180015bb9  lea     rdx, [rsp+718h+var_640]
0x180015bc1  lea     rcx, [rsp+718h+var_670]
0x180015bc9  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@VCNetworkListInterfaceEntry@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@VCNetworkListInterfaceEntry@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@VCNetworkListInterfaceEntry@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,CNetworkListInterfaceEntry>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180015bce  mov     rcx, [rax]
0x180015bd1  mov     eax, dword ptr [rsp+718h+var_6A0]
0x180015bd5  or      [rcx+50h], eax
0x180015bd8  mov     [rcx+54h], edi
0x180015bdb  add     rcx, 40h ; '@'
0x180015bdf  lea     r8, [rsp+718h+var_5C8]
0x180015be7  lea     rdx, [rsp+718h+var_608]
0x180015bef  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@_NU?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@_N@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,bool>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180015bf4  mov     rax, [rax]
0x180015bf7  mov     [rax+2Ch], r12b
0x180015bfb  mov     rcx, [rsi]
0x180015bfe  mov     rax, [rcx]
0x180015c01  mov     rax, [rax+10h]
0x180015c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c0a  nop
0x180015c0b  lea     rcx, [rsp+718h+pv]
0x180015c13  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180015c18  mov     rdi, [rsp+718h+var_680]
0x180015c20  jmp     short loc_180015C52
0x180015c22  lea     rcx, [rsp+718h+pv]
0x180015c2a  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180015c2f  mov     r13d, [rsp+718h+var_6A8]
0x180015c34  xor     r14d, r14d
0x180015c37  lea     r12d, [r14+1]
0x180015c3b  mov     ebx, dword ptr [rsp+718h+var_698]
0x180015c42  mov     rdi, [rsp+718h+var_650]
0x180015c4a  mov     [rsp+718h+var_680], rdi
0x180015c52  mov     [rsp+718h+var_6A8], r13d
0x180015c57  add     ebx, r12d
0x180015c5a  mov     eax, [rsp+718h+var_688]
0x180015c61  jmp     loc_180015990
0x180015c66  mov     rbx, qword ptr [rsp+718h+var_670]
0x180015c6e  mov     rbx, [rbx]
0x180015c71  cmp     rbx, qword ptr [rsp+718h+var_670]
0x180015c79  jnz     loc_180015DC8
0x180015c7f  test    r15d, r15d
0x180015c82  js      loc_180016149
0x180015c88  lea     rcx, [rdi+50h]; lpCriticalSection
0x180015c8c  call    cs:__imp_EnterCriticalSection
0x180015c92  mov     rbx, qword ptr [rsp+718h+var_670]
0x180015c9a  mov     rbx, [rbx]
0x180015c9d  cmp     rbx, qword ptr [rsp+718h+var_670]
0x180015ca5  jz      loc_180015DB9
0x180015cab  lea     rcx, [rsp+718h+var_248]; this
0x180015cb3  call    ??0ConnListEntry@@QEAA@XZ; ConnListEntry::ConnListEntry(void)
0x180015cb8  lea     r8, [rsp+718h+var_248]; struct ConnListEntry *
0x180015cc0  lea     rdx, [rbx+20h]; struct _GUID *
0x180015cc4  mov     rcx, [rsp+718h+var_680]; this
0x180015ccc  call    ?HrFindConnectionByGuid@CConnectionList@@QEAAJPEFBU_GUID@@AEAVConnListEntry@@@Z; CConnectionList::HrFindConnectionByGuid(_GUID const *,ConnListEntry &)
0x180015cd1  test    eax, eax
0x180015cd3  jnz     loc_180015D5D
0x180015cd9  mov     ecx, [rbx+58h]
0x180015cdc  mov     edx, [rbx+54h]
0x180015cdf  mov     r8d, [rbx+50h]
0x180015ce3  cmp     qword ptr [rbx+78h], 7
0x180015ce8  jbe     short loc_180015CF0
0x180015cea  mov     rax, [rbx+60h]
0x180015cee  jmp     short loc_180015CF4
0x180015cf0  lea     rax, [rbx+60h]
0x180015cf4  mov     [rsp+718h+var_6B8], ecx
0x180015cf8  mov     [rsp+718h+var_6C0], edx
0x180015cfc  mov     [rsp+718h+var_6C8], r8d
0x180015d01  mov     [rsp+718h+var_6D0], rax
0x180015d06  mov     [rsp+718h+var_6D8], r14
0x180015d0b  mov     [rsp+718h+var_6E0], r14
0x180015d10  mov     [rsp+718h+var_6E8], r14
0x180015d15  mov     [rsp+718h+var_6F0], r14d
0x180015d1a  mov     dword ptr [rsp+718h+var_6F8], r14d
0x180015d1f  mov     r9d, r12d
0x180015d22  mov     edx, 700h
0x180015d27  mov     r8d, 3
0x180015d2d  lea     rcx, [rsp+718h+var_240]
0x180015d35  call    ?UpdateData@CConFoldEntry@@QEAAJKW4tagNETCON_MEDIATYPE@@W4tagNETCON_SUBMEDIATYPE@@W4tagNETCON_STATUS@@KPEBG333KHK@Z; CConFoldEntry::UpdateData(ulong,tagNETCON_MEDIATYPE,tagNETCON_SUBMEDIATYPE,tagNETCON_STATUS,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,int,ulong)
0x180015d3a  mov     r15d, eax
0x180015d3d  test    eax, eax
0x180015d3f  js      short loc_180015D5D
0x180015d41  lea     r8, [rsp+718h+var_248]; struct ConnListEntry *
0x180015d49  lea     rdx, [rbx+20h]; struct _GUID *
0x180015d4d  mov     rcx, [rsp+718h+var_680]; this
0x180015d55  call    ?HrUpdateConnectionByGuid@CConnectionList@@QEAAJPEBU_GUID@@AEBVConnListEntry@@@Z; CConnectionList::HrUpdateConnectionByGuid(_GUID const *,ConnListEntry const &)
0x180015d5a  mov     r15d, eax
0x180015d5d  lea     rcx, [rsp+718h+var_248]; this
0x180015d65  call    ??1ConnListEntry@@QEAA@XZ; ConnListEntry::~ConnListEntry(void)
0x180015d6a  mov     rcx, [rbx+10h]
0x180015d6e  cmp     [rcx+19h], r14b
0x180015d72  jz      short loc_180015D95
0x180015d74  mov     rax, [rbx+8]
0x180015d78  jmp     short loc_180015D87
0x180015d7a  cmp     rbx, [rax+10h]
0x180015d7e  jnz     short loc_180015D8D
0x180015d80  mov     rbx, rax
0x180015d83  mov     rax, [rax+8]
0x180015d87  cmp     [rax+19h], r14b
0x180015d8b  jz      short loc_180015D7A
0x180015d8d  mov     rbx, rax
0x180015d90  jmp     loc_180015C9D
0x180015d95  mov     rbx, rcx
0x180015d98  mov     rcx, [rcx]
0x180015d9b  cmp     [rcx+19h], r14b
0x180015d9f  jnz     loc_180015C9D
0x180015da5  mov     rbx, rcx
0x180015da8  mov     rax, [rcx]
0x180015dab  mov     rcx, rax
0x180015dae  cmp     [rax+19h], r14b
0x180015db2  jz      short loc_180015DA5
0x180015db4  jmp     loc_180015C9D
0x180015db9  lea     rcx, [rdi+50h]; lpCriticalSection
0x180015dbd  call    cs:__imp_LeaveCriticalSection
0x180015dc3  jmp     loc_180016149
0x180015dc8  mov     rdi, [rbx+40h]
0x180015dcc  mov     rdi, [rdi]
0x180015dcf  cmp     rdi, [rbx+40h]
0x180015dd3  jnz     short loc_180015E2B
0x180015dd5  mov     rcx, [rbx+10h]
0x180015dd9  cmp     [rcx+19h], r14b
0x180015ddd  jz      short loc_180015E0E
0x180015ddf  mov     rax, [rbx+8]
0x180015de3  jmp     short loc_180015DF2
0x180015de5  cmp     rbx, [rax+10h]
0x180015de9  jnz     short loc_180015DF8
0x180015deb  mov     rbx, rax
0x180015dee  mov     rax, [rax+8]
0x180015df2  cmp     [rax+19h], r14b
0x180015df6  jz      short loc_180015DE5
0x180015df8  mov     rbx, rax
0x180015dfb  mov     r12d, 1
0x180015e01  mov     rdi, [rsp+718h+var_680]
0x180015e09  jmp     loc_180015C71
  ... truncated ...
```
