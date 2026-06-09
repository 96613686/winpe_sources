# Win32NetworkAdapterConfigurationHelper::RemoveUnsupportedAddresses(tagVARIANT *,tagVARIANT *,std::vector<ulong,std::allocator<ulong>> *)

- ea: `0x18022d808`
- end: `0x18022e261`
- name: `?RemoveUnsupportedAddresses@Win32NetworkAdapterConfigurationHelper@@AEAAJPEAUtagVARIANT@@0PEAV?$vector@KV?$allocator@K@std@@@std@@@Z`
- size: `2649`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x18022ac34`

## callees

- `0x180001b68`
- `0x180001c08`
- `0x180001c94`
- `0x18000414c`
- `0x1800053ac`
- `0x1800054a0`
- `0x18005f0c0`
- `0x180067c00`
- `0x18006c530`
- `0x1800776d8`
- `0x18007eb9c`
- `0x18008eb18`
- `0x18022a9e0`
- `0x18022d808`

## import_xrefs

- `ntdll!RtlIpv4StringToAddressW` at `0x18022dbdf`
- `ntdll!RtlIpv4StringToAddressW` at `0x18022dbdf`
- `OLEAUT32!__imp_SysAllocString` at `0x18022dfe1`
- `OLEAUT32!__imp_SysAllocString` at `0x18022e05e`
- `OLEAUT32!__imp_SysAllocString` at `0x18022dfe1`
- `OLEAUT32!__imp_SysAllocString` at `0x18022e05e`
- `OLEAUT32!__imp_VariantClear` at `0x18022dccd`
- `OLEAUT32!__imp_VariantClear` at `0x18022dcd6`
- `OLEAUT32!__imp_VariantClear` at `0x18022dccd`
- `OLEAUT32!__imp_VariantClear` at `0x18022dcd6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022dee5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022df48`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022df76`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022dee5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022df48`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18022df76`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18022d9a8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18022d9e2`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18022d9a8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18022d9e2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18022dadd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18022db21`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18022dadd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18022db21`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18022da25`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18022da67`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18022da25`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18022da67`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022dbc1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022dda6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022de62`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022dbc1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022dda6`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18022de62`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e03a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e0b7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e130`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e03a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e0b7`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18022e130`

## string_xrefs

- `0x18022d890`: `RemoveUnsupportedAddresses IP list is empty`
- `0x18022d953`: `RemoveUnsupportedAddresses failed to get IP safe array`
- `0x18022e1f3`: `RemoveUnsupportedAddresses subnet is not correct type`
- `0x18022d8f9`: `RemoveUnsupportedAddresses IP is not correct type`
- `0x18022d8c1`: `RemoveUnsupportedAddresses subnet list is empty`
- `0x18022da3e`: `RemoveUnsupportedAddresses failed to get IP safe array lower bound`
- `0x18022d9fc`: `RemoveUnsupportedAddresses failed to get subnet safe array dimensions`
- `0x18022d988`: `RemoveUnsupportedAddresses failed to get subnet safe array`
- `0x18022e168`: `RemoveUnsupportedAddresses succeeded`
- `0x18022e0dd`: `RemoveUnsupportedAddresses add back subnet long`
- `0x18022db3a`: `RemoveUnsupportedAddresses failed to get subnet safe array upper bound`
- `0x18022daf8`: `RemoveUnsupportedAddresses failed to get IP safe array upper bound`
- `0x18022dab4`: `RemoveUnsupportedAddresses failed lower bounds do not match`
- `0x18022da80`: `RemoveUnsupportedAddresses failed to get subnet safe array lower bound`
- `0x18022ddc1`: `RemoveUnsupportedAddresses nextSubnet`
- `0x18022de7a`: `RemoveUnsupportedAddresses nextSubnet`
- `0x18022dc72`: `RemoveUnsupportedAddresses excluded`
- `0x18022dc09`: `RemoveUnsupportedAddresses IsValidIPv4Address`
- `0x18022db6e`: `RemoveUnsupportedAddresses failed upper bounds do not match`
- `0x18022df61`: `RemoveUnsupportedAddresses could not create subnet safe array`
- `0x18022df8f`: `RemoveUnsupportedAddresses could not create subnet safe array`
- `0x18022defe`: `RemoveUnsupportedAddresses could not create IP safe array`
- `0x18022dd00`: `RemoveUnsupportedAddresses list is empty`
- `0x18022e1c2`: `RemoveUnsupportedAddresses no changes`
- `0x18022e07b`: `RemoveUnsupportedAddresses add back subnet string`
- `0x18022e186`: `RemoveUnsupportedAddresses could not allocate next subnet`
- `0x18022dffe`: `RemoveUnsupportedAddresses add back nextip`
- `0x18022e1a4`: `RemoveUnsupportedAddresses could not allocate nextip`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Win32NetworkAdapterConfigurationHelper::RemoveUnsupportedAddresses(
        __int64 a1,
        VARIANTARG *a2,
        VARIANTARG *a3,
        _DWORD **a4)
{
  unsigned int v5; // edi
  _DWORD *v6; // rcx
  void *p_psa; // rax
  void *v8; // rdx
  SAFEARRAY *parray; // rsi
  SAFEARRAY *v10; // r14
  char v11; // r12
  __m128i si128; // xmm6
  SAFEARRAY *v13; // rdi
  LONG v14; // eax
  ULONG S_addr; // esi
  _DWORD *v16; // rcx
  _DWORD *i; // rax
  _DWORD *v18; // rcx
  bool v19; // zf
  VARIANTARG *v20; // r15
  __int16 v21; // r12
  VARIANTARG *v22; // r13
  char *v23; // rax
  unsigned __int64 v24; // r8
  __m128i *v25; // rdx
  int v26; // r8d
  int v27; // r9d
  _DWORD *v28; // rcx
  unsigned __int64 v29; // r8
  __m128i *v30; // rdx
  _DWORD *v31; // rcx
  SAFEARRAY *v32; // rax
  SAFEARRAY *v33; // r14
  _DWORD *v34; // rcx
  char *v35; // rax
  void *v36; // rdx
  SAFEARRAY *v37; // rdi
  __int64 v38; // rdx
  LONG v39; // ecx
  const OLECHAR *v40; // rcx
  VARIANTARG *v41; // rax
  VARIANTARG *v42; // rsi
  const OLECHAR *v43; // rcx
  VARIANTARG *v44; // rax
  VARIANTARG *v45; // rsi
  _DWORD *v46; // rcx
  _DWORD *v47; // rcx
  char v49; // [rsp+40h] [rbp-C0h]
  VARIANTARG *pvarg; // [rsp+48h] [rbp-B8h] BYREF
  const char *v51; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG *v52; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD **v53; // [rsp+60h] [rbp-A0h]
  SAFEARRAY *psa; // [rsp+68h] [rbp-98h] BYREF
  LONG rgIndices; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR Terminator; // [rsp+78h] [rbp-88h] BYREF
  struct in_addr Addr[2]; // [rsp+80h] [rbp-80h] BYREF
  LONG v58; // [rsp+88h] [rbp-78h] BYREF
  LONG plLbound; // [rsp+8Ch] [rbp-74h] BYREF
  LONG plUbound; // [rsp+90h] [rbp-70h] BYREF
  __int128 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  __int128 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int128 v65; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-28h]
  SAFEARRAYBOUND rgsabound; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v68; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v69; // [rsp+100h] [rbp+0h]
  LPCWSTR *p_Terminator; // [rsp+110h] [rbp+10h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  const char *v72; // [rsp+120h] [rbp+20h]
  __int64 v73; // [rsp+128h] [rbp+28h]

  v53 = a4;
  v52 = a3;
  pvarg = a2;
  plLbound = 0;
  plUbound = 0;
  v58 = 0;
  rgIndices = 0;
  v5 = -2147467259;
  v61 = 0;
  v62 = 0;
  v65 = 0;
  v66 = 0;
  v63 = 0;
  v64 = 0;
  if ( !a2 )
  {
    v6 = *(_DWORD **)(a1 + 24);
    if ( *v6 > 4u )
    {
      psa = (SAFEARRAY *)"RemoveUnsupportedAddresses IP list is empty";
      p_psa = &psa;
      v8 = &unk_18034265A;
LABEL_126:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v6,
        (_DWORD)v8,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)p_psa);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  if ( a3 )
  {
    if ( a2->vt != 8200 )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses IP is not correct type";
        p_psa = &psa;
        v8 = &unk_180342710;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( a3->vt == 8200 )
    {
      v49 = 1;
    }
    else
    {
      if ( a3->vt != 8195 )
      {
        v6 = *(_DWORD **)(a1 + 24);
        if ( *v6 <= 4u )
          goto LABEL_127;
        v23 = "RemoveUnsupportedAddresses subnet is not correct type";
        v8 = &unk_18034276B;
        goto LABEL_125;
      }
      v49 = 0;
    }
    parray = a2->parray;
    psa = parray;
    if ( !parray )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get IP safe array";
        p_psa = &psa;
        v8 = &unk_180341AAF;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    v10 = a3->parray;
    if ( !v10 )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get subnet safe array";
        p_psa = &psa;
        v8 = &unk_180341B0A;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetDim(parray) != 1 )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"ApplyNetworkStaticSettings failed to get IP safe array dimensions";
        p_psa = &psa;
        v8 = &unk_180341B65;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetDim(v10) != 1 )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get subnet safe array dimensions";
        p_psa = &psa;
        v8 = &unk_18034199E;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetLBound(parray, 1u, &plLbound) )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get IP safe array lower bound";
        p_psa = &psa;
        v8 = &unk_1803419F9;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetLBound(v10, 1u, &v58) )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get subnet safe array lower bound";
        p_psa = &psa;
        v8 = &unk_180341A54;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( v58 != plLbound )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed lower bounds do not match";
        p_psa = &psa;
        v8 = &unk_18034188D;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetUBound(parray, 1u, &plUbound) )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get IP safe array upper bound";
        p_psa = &psa;
        v8 = &unk_1803418E8;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( SafeArrayGetUBound(v10, 1u, &v58) )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed to get subnet safe array upper bound";
        p_psa = &psa;
        v8 = &unk_180341943;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    if ( v58 != plUbound )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 > 4u )
      {
        psa = (SAFEARRAY *)"RemoveUnsupportedAddresses failed upper bounds do not match";
        p_psa = &psa;
        v8 = &unk_18034176B;
        goto LABEL_126;
      }
      goto LABEL_127;
    }
    rgIndices = plLbound;
    if ( plLbound > plUbound )
      goto LABEL_120;
    v11 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v13 = psa;
    do
    {
      psa = 0;
      SafeArrayGetElement(v13, &rgIndices, &psa);
      Addr[0].S_un.S_addr = 0;
      Terminator = 0;
      v14 = RtlIpv4StringToAddressW(&psa->cDims, 1u, &Terminator, Addr);
      S_addr = Addr[0].S_un.S_addr;
      if ( v14 )
        S_addr = 0;
      v16 = *(_DWORD **)(a1 + 24);
      if ( *v16 > 4u )
      {
        Addr[0].S_un.S_addr = S_addr;
        Terminator = &psa->cDims;
        v51 = "RemoveUnsupportedAddresses IsValidIPv4Address";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (unsigned int)&unk_1803417C6,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)&v51,
          (__int64)&Terminator,
          (__int64)Addr);
      }
      if ( S_addr )
      {
        if ( v53 )
        {
          for ( i = *v53; i != v53[1]; ++i )
          {
            if ( *i == S_addr )
            {
              v18 = *(_DWORD **)(a1 + 24);
              if ( *v18 > 4u )
              {
                v51 = "RemoveUnsupportedAddresses excluded";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (_DWORD)v18,
                  (unsigned int)&unk_180341832,
                  (_DWORD)a3,
                  (_DWORD)a4,
                  (__int64)&v51);
              }
              goto LABEL_58;
            }
          }
        }
        v68 = 0;
        v69 = 0;
        v24 = -1;
        do
          ++v24;
        while ( *(&psa->cDims + v24) );
        std::wstring::_Construct<1,unsigned short const *>((char **)&v68, psa, v24);
        v25 = (__m128i *)*((_QWORD *)&v61 + 1);
        if ( *((_QWORD *)&v61 + 1) == v62 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v61, *((_QWORD *)&v61 + 1), &v68);
        }
        else
        {
          **((_OWORD **)&v61 + 1) = v68;
          v25[1] = v69;
          v69 = si128;
          LOWORD(v68) = 0;
          *((_QWORD *)&v61 + 1) += 32LL;
        }
        std::wstring::~wstring(&v68);
        if ( v49 )
        {
          Terminator = (LPCWSTR)&unk_1802E2A80;
          SafeArrayGetElement(v10, &rgIndices, &Terminator);
          v28 = *(_DWORD **)(a1 + 24);
          if ( *v28 > 4u )
          {
            v51 = (const char *)Terminator;
            *(_QWORD *)&Addr[0].S_un.S_un_b.s_b1 = "RemoveUnsupportedAddresses nextSubnet";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v28,
              (unsigned int)&unk_180341F13,
              v26,
              v27,
              (__int64)Addr,
              (__int64)&v51);
          }
          v68 = 0;
          v69 = 0;
          v29 = -1;
          do
            ++v29;
          while ( Terminator[v29] );
          std::wstring::_Construct<1,unsigned short const *>((char **)&v68, Terminator, v29);
          v30 = (__m128i *)*((_QWORD *)&v65 + 1);
          if ( *((_QWORD *)&v65 + 1) == v66 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v65, *((_QWORD *)&v65 + 1), &v68);
          }
          else
          {
            **((_OWORD **)&v65 + 1) = v68;
            v30[1] = v69;
            v69 = si128;
            LOWORD(v68) = 0;
            *((_QWORD *)&v65 + 1) += 32LL;
          }
          std::wstring::~wstring(&v68);
        }
        else
        {
          Addr[0].S_un.S_addr = 0;
          SafeArrayGetElement(v10, &rgIndices, Addr);
          v31 = *(_DWORD **)(a1 + 24);
          if ( *v31 > 4u )
          {
            LODWORD(Terminator) = Addr[0];
            v51 = "RemoveUnsupportedAddresses nextSubnet";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)v31,
              (unsigned int)&unk_180341F7A,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&v51,
              (__int64)&Terminator);
          }
          if ( *((_QWORD *)&v63 + 1) == v64 )
          {
            std::vector<long>::_Emplace_reallocate<long const &>(&v63, *((_QWORD *)&v63 + 1), Addr);
          }
          else
          {
            **((_DWORD **)&v63 + 1) = Addr[0].S_un.S_addr;
            *((_QWORD *)&v63 + 1) += 4LL;
          }
        }
      }
      else
      {
LABEL_58:
        v11 = 1;
      }
      ++rgIndices;
    }
    while ( rgIndices <= plUbound );
    v19 = v11 == 0;
    v5 = -2147467259;
    v20 = v52;
    v21 = 8200;
    v22 = pvarg;
    if ( v19 )
    {
LABEL_120:
      v47 = *(_DWORD **)(a1 + 24);
      if ( *v47 > 4u )
      {
        pvarg = (VARIANTARG *)"RemoveUnsupportedAddresses no changes";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v47,
          (unsigned int)&unk_180341FE1,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)&pvarg);
      }
      v5 = 0;
      goto LABEL_127;
    }
    VariantClear(pvarg);
    VariantClear(v20);
    if ( !((__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5) )
    {
      v6 = *(_DWORD **)(a1 + 24);
      if ( *v6 <= 4u )
        goto LABEL_127;
      v23 = "RemoveUnsupportedAddresses list is empty";
      v8 = &unk_18034203C;
LABEL_125:
      pvarg = (VARIANTARG *)v23;
      p_psa = &pvarg;
      goto LABEL_126;
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5;
    v32 = SafeArrayCreate(8u, 1u, &rgsabound);
    v33 = v32;
    if ( v32 )
    {
      pvarg->vt = 8200;
      v22->llVal = (LONGLONG)v32;
      if ( v49 )
      {
        v37 = SafeArrayCreate(8u, 1u, &rgsabound);
        if ( !v37 )
        {
          v34 = *(_DWORD **)(a1 + 24);
          if ( *v34 <= 4u )
            goto LABEL_87;
          v35 = "RemoveUnsupportedAddresses could not create subnet safe array";
          v36 = &unk_180341E5D;
          goto LABEL_86;
        }
      }
      else
      {
        v37 = SafeArrayCreate(3u, 1u, &rgsabound);
        if ( !v37 )
        {
          v34 = *(_DWORD **)(a1 + 24);
          if ( *v34 <= 4u )
            goto LABEL_87;
          v35 = "RemoveUnsupportedAddresses could not create subnet safe array";
          v36 = &unk_180341EB8;
          goto LABEL_86;
        }
        v21 = 8195;
      }
      v20->vt = v21;
      v20->llVal = (LONGLONG)v37;
      rgIndices = 0;
      v38 = v61;
      if ( (int)((__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5) <= 0 )
      {
LABEL_114:
        v5 = 0;
        v6 = *(_DWORD **)(a1 + 24);
        if ( *v6 <= 4u )
          goto LABEL_127;
        v23 = "RemoveUnsupportedAddresses succeeded";
        v8 = &unk_180341C8E;
        goto LABEL_125;
      }
      v39 = 0;
      while ( 1 )
      {
        v40 = (const OLECHAR *)(v38 + 32LL * v39);
        if ( *((_QWORD *)v40 + 3) > 7u )
          v40 = *(const OLECHAR **)v40;
        v41 = (VARIANTARG *)SysAllocString(v40);
        v42 = v41;
        v34 = *(_DWORD **)(a1 + 24);
        if ( !v41 )
          break;
        if ( *v34 > 4u )
        {
          pvarg = (VARIANTARG *)"RemoveUnsupportedAddresses add back nextip";
          v52 = v41;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
            (_DWORD)v34,
            (unsigned int)&unk_180341D44,
            (_DWORD)a3,
            (_DWORD)a4,
            (__int64)&v52,
            (__int64)&pvarg);
        }
        SafeArrayPutElement(v33, &rgIndices, v42);
        if ( v49 )
        {
          v43 = (const OLECHAR *)(v65 + 32LL * rgIndices);
          if ( *((_QWORD *)v43 + 3) > 7u )
            v43 = *(const OLECHAR **)v43;
          v44 = (VARIANTARG *)SysAllocString(v43);
          v45 = v44;
          v34 = *(_DWORD **)(a1 + 24);
          if ( !v44 )
          {
            if ( *v34 <= 4u )
              goto LABEL_87;
            v35 = "RemoveUnsupportedAddresses could not allocate next subnet";
            v36 = &unk_180341DA7;
            goto LABEL_86;
          }
          if ( *v34 > 4u )
          {
            pvarg = (VARIANTARG *)"RemoveUnsupportedAddresses add back subnet string";
            v52 = v44;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
              (_DWORD)v34,
              (unsigned int)&unk_180341BC0,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&v52,
              (__int64)&pvarg);
          }
          SafeArrayPutElement(v37, &rgIndices, v45);
        }
        else
        {
          Addr[0] = *(struct in_addr *)(v63 + 4LL * rgIndices);
          v46 = *(_DWORD **)(a1 + 24);
          if ( *v46 > 4u )
          {
            LODWORD(Terminator) = Addr[0];
            v72 = "RemoveUnsupportedAddresses add back subnet long";
            v73 = 48;
            p_Terminator = &Terminator;
            v71 = 4;
            tlgWriteTransfer_EventWriteTransfer(v46, &unk_180341C27, 0, 0, 4, &v68);
          }
          SafeArrayPutElement(v37, &rgIndices, Addr);
        }
        v39 = rgIndices + 1;
        rgIndices = v39;
        v38 = v61;
        if ( v39 >= (int)((__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5) )
          goto LABEL_114;
      }
      if ( *v34 <= 4u )
        goto LABEL_87;
      v35 = "RemoveUnsupportedAddresses could not allocate nextip";
      v36 = &unk_180341CE9;
    }
    else
    {
      v34 = *(_DWORD **)(a1 + 24);
      if ( *v34 <= 4u )
      {
LABEL_87:
        v5 = -2147024882;
        goto LABEL_127;
      }
      v35 = "RemoveUnsupportedAddresses could not create IP safe array";
      v36 = &unk_180341E02;
    }
LABEL_86:
    pvarg = (VARIANTARG *)v35;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v34,
      (_DWORD)v36,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&pvarg);
    goto LABEL_87;
  }
  v6 = *(_DWORD **)(a1 + 24);
  if ( *v6 > 4u )
  {
    psa = (SAFEARRAY *)"RemoveUnsupportedAddresses subnet list is empty";
    p_psa = &psa;
    v8 = &unk_1803426B5;
    goto LABEL_126;
  }
LABEL_127:
  std::vector<std::pair<unsigned short,unsigned short>>::~vector<std::pair<unsigned short,unsigned short>>(&v63);
  std::vector<std::wstring>::_Tidy(&v65);
  std::vector<std::wstring>::_Tidy(&v61);
  return v5;
}

```

## disassembly

```asm
0x18022d808  mov     rax, rsp
0x18022d80b  mov     [rax+20h], rbx
0x18022d80f  push    rbp
0x18022d810  push    rsi
0x18022d811  push    rdi
0x18022d812  push    r12
0x18022d814  push    r13
0x18022d816  push    r14
0x18022d818  push    r15
0x18022d81a  lea     rbp, [rsp-50h]
0x18022d81f  sub     rsp, 150h
0x18022d826  movaps  xmmword ptr [rax-48h], xmm6
0x18022d82a  mov     rax, cs:__security_cookie
0x18022d831  xor     rax, rsp
0x18022d834  mov     [rbp+80h+var_50], rax
0x18022d838  mov     [rsp+180h+var_120], r9
0x18022d83d  mov     [rsp+180h+var_128], r8
0x18022d842  mov     [rsp+180h+pvarg], rdx
0x18022d847  mov     rbx, rcx
0x18022d84a  xor     ecx, ecx
0x18022d84c  mov     [rbp+80h+plLbound], ecx
0x18022d84f  mov     [rbp+80h+plUbound], ecx
0x18022d852  mov     [rbp+80h+var_F8], ecx
0x18022d855  mov     [rsp+180h+rgIndices], ecx
0x18022d859  mov     edi, 80004005h
0x18022d85e  xorps   xmm1, xmm1
0x18022d861  movdqu  [rbp+80h+var_E8], xmm1
0x18022d866  mov     [rbp+80h+var_D8], rcx
0x18022d86a  movdqu  [rbp+80h+var_B8], xmm1
0x18022d86f  mov     [rbp+80h+var_A8], rcx
0x18022d873  movdqu  [rbp+80h+var_D0], xmm1
0x18022d878  mov     [rbp+80h+var_C0], rcx
0x18022d87c  test    rdx, rdx
0x18022d87f  jnz     short loc_18022D8AD
0x18022d881  mov     rcx, [rbx+18h]
0x18022d885  mov     eax, [rcx]
0x18022d887  cmp     eax, 4
0x18022d88a  jbe     loc_18022E216
0x18022d890  lea     rax, aRemoveunsuppor_13; "RemoveUnsupportedAddresses IP list is e"...
0x18022d897  mov     [rsp+180h+psa], rax
0x18022d89c  lea     rax, [rsp+180h+psa]
0x18022d8a1  lea     rdx, unk_18034265A
0x18022d8a8  jmp     loc_18022E20B
0x18022d8ad  test    r8, r8
0x18022d8b0  jnz     short loc_18022D8DE
0x18022d8b2  mov     rcx, [rbx+18h]
0x18022d8b6  mov     eax, [rcx]
0x18022d8b8  cmp     eax, 4
0x18022d8bb  jbe     loc_18022E216
0x18022d8c1  lea     rax, aRemoveunsuppor_16; "RemoveUnsupportedAddresses subnet list "...
0x18022d8c8  mov     [rsp+180h+psa], rax
0x18022d8cd  lea     rax, [rsp+180h+psa]
0x18022d8d2  lea     rdx, unk_1803426B5
0x18022d8d9  jmp     loc_18022E20B
0x18022d8de  mov     r12d, 2008h
0x18022d8e4  cmp     [rdx], r12w
0x18022d8e8  jz      short loc_18022D916
0x18022d8ea  mov     rcx, [rbx+18h]
0x18022d8ee  mov     eax, [rcx]
0x18022d8f0  cmp     eax, 4
0x18022d8f3  jbe     loc_18022E216
0x18022d8f9  lea     rax, aRemoveunsuppor_7; "RemoveUnsupportedAddresses IP is not co"...
0x18022d900  mov     [rsp+180h+psa], rax
0x18022d905  lea     rax, [rsp+180h+psa]
0x18022d90a  lea     rdx, unk_180342710
0x18022d911  jmp     loc_18022E20B
0x18022d916  mov     eax, 2003h
0x18022d91b  cmp     [r8], r12w
0x18022d91f  jnz     short loc_18022D928
0x18022d921  mov     [rsp+180h+var_140], 1
0x18022d926  jmp     short loc_18022D936
0x18022d928  cmp     [r8], ax
0x18022d92c  jnz     loc_18022E1E8
0x18022d932  mov     [rsp+180h+var_140], cl
0x18022d936  mov     rsi, [rdx+8]
0x18022d93a  mov     [rsp+180h+psa], rsi
0x18022d93f  test    rsi, rsi
0x18022d942  jnz     short loc_18022D970
0x18022d944  mov     rcx, [rbx+18h]
0x18022d948  mov     eax, [rcx]
0x18022d94a  cmp     eax, 4
0x18022d94d  jbe     loc_18022E216
0x18022d953  lea     rax, aRemoveunsuppor_0; "RemoveUnsupportedAddresses failed to ge"...
0x18022d95a  mov     [rsp+180h+psa], rax
0x18022d95f  lea     rax, [rsp+180h+psa]
0x18022d964  lea     rdx, unk_180341AAF
0x18022d96b  jmp     loc_18022E20B
0x18022d970  mov     r14, [r8+8]
0x18022d974  test    r14, r14
0x18022d977  jnz     short loc_18022D9A5
0x18022d979  mov     rcx, [rbx+18h]
0x18022d97d  mov     eax, [rcx]
0x18022d97f  cmp     eax, 4
0x18022d982  jbe     loc_18022E216
0x18022d988  lea     rax, aRemoveunsuppor_6; "RemoveUnsupportedAddresses failed to ge"...
0x18022d98f  mov     [rsp+180h+psa], rax
0x18022d994  lea     rax, [rsp+180h+psa]
0x18022d999  lea     rdx, unk_180341B0A
0x18022d9a0  jmp     loc_18022E20B
0x18022d9a5  mov     rcx, rsi; psa
0x18022d9a8  call    cs:__imp_SafeArrayGetDim
0x18022d9ae  cmp     eax, 1
0x18022d9b1  jz      short loc_18022D9DF
0x18022d9b3  mov     rcx, [rbx+18h]
0x18022d9b7  mov     eax, [rcx]
0x18022d9b9  cmp     eax, 4
0x18022d9bc  jbe     loc_18022E216
0x18022d9c2  lea     rax, aApplynetworkst_35; "ApplyNetworkStaticSettings failed to ge"...
0x18022d9c9  mov     [rsp+180h+psa], rax
0x18022d9ce  lea     rax, [rsp+180h+psa]
0x18022d9d3  lea     rdx, unk_180341B65
0x18022d9da  jmp     loc_18022E20B
0x18022d9df  mov     rcx, r14; psa
0x18022d9e2  call    cs:__imp_SafeArrayGetDim
0x18022d9e8  cmp     eax, 1
0x18022d9eb  jz      short loc_18022DA19
0x18022d9ed  mov     rcx, [rbx+18h]
0x18022d9f1  mov     eax, [rcx]
0x18022d9f3  cmp     eax, 4
0x18022d9f6  jbe     loc_18022E216
0x18022d9fc  lea     rax, aRemoveunsuppor_3; "RemoveUnsupportedAddresses failed to ge"...
0x18022da03  mov     [rsp+180h+psa], rax
0x18022da08  lea     rax, [rsp+180h+psa]
0x18022da0d  lea     rdx, unk_18034199E
0x18022da14  jmp     loc_18022E20B
0x18022da19  lea     r8, [rbp+80h+plLbound]; plLbound
0x18022da1d  mov     edx, 1; nDim
0x18022da22  mov     rcx, rsi; psa
0x18022da25  call    cs:__imp_SafeArrayGetLBound
0x18022da2b  test    eax, eax
0x18022da2d  jz      short loc_18022DA5B
0x18022da2f  mov     rcx, [rbx+18h]
0x18022da33  mov     eax, [rcx]
0x18022da35  cmp     eax, 4
0x18022da38  jbe     loc_18022E216
0x18022da3e  lea     rax, aRemoveunsuppor_4; "RemoveUnsupportedAddresses failed to ge"...
0x18022da45  mov     [rsp+180h+psa], rax
0x18022da4a  lea     rax, [rsp+180h+psa]
0x18022da4f  lea     rdx, unk_1803419F9
0x18022da56  jmp     loc_18022E20B
0x18022da5b  lea     r8, [rbp+80h+var_F8]; plLbound
0x18022da5f  mov     edx, 1; nDim
0x18022da64  mov     rcx, r14; psa
0x18022da67  call    cs:__imp_SafeArrayGetLBound
0x18022da6d  test    eax, eax
0x18022da6f  jz      short loc_18022DA9D
0x18022da71  mov     rcx, [rbx+18h]
0x18022da75  mov     eax, [rcx]
0x18022da77  cmp     eax, 4
0x18022da7a  jbe     loc_18022E216
0x18022da80  lea     rax, aRemoveunsuppor_15; "RemoveUnsupportedAddresses failed to ge"...
0x18022da87  mov     [rsp+180h+psa], rax
0x18022da8c  lea     rax, [rsp+180h+psa]
0x18022da91  lea     rdx, unk_180341A54
0x18022da98  jmp     loc_18022E20B
0x18022da9d  mov     eax, [rbp+80h+plLbound]
0x18022daa0  cmp     [rbp+80h+var_F8], eax
0x18022daa3  jz      short loc_18022DAD1
0x18022daa5  mov     rcx, [rbx+18h]
0x18022daa9  mov     eax, [rcx]
0x18022daab  cmp     eax, 4
0x18022daae  jbe     loc_18022E216
0x18022dab4  lea     rax, aRemoveunsuppor_9; "RemoveUnsupportedAddresses failed lower"...
0x18022dabb  mov     [rsp+180h+psa], rax
0x18022dac0  lea     rax, [rsp+180h+psa]
0x18022dac5  lea     rdx, unk_18034188D
0x18022dacc  jmp     loc_18022E20B
0x18022dad1  lea     r8, [rbp+80h+plUbound]; plUbound
0x18022dad5  mov     edx, 1; nDim
0x18022dada  mov     rcx, rsi; psa
0x18022dadd  call    cs:__imp_SafeArrayGetUBound
0x18022dae3  xor     esi, esi
0x18022dae5  test    eax, eax
0x18022dae7  jz      short loc_18022DB15
0x18022dae9  mov     rcx, [rbx+18h]
0x18022daed  mov     eax, [rcx]
0x18022daef  cmp     eax, 4
0x18022daf2  jbe     loc_18022E216
0x18022daf8  lea     rax, aRemoveunsuppor_17; "RemoveUnsupportedAddresses failed to ge"...
0x18022daff  mov     [rsp+180h+psa], rax
0x18022db04  lea     rax, [rsp+180h+psa]
0x18022db09  lea     rdx, unk_1803418E8
0x18022db10  jmp     loc_18022E20B
0x18022db15  lea     r8, [rbp+80h+var_F8]; plUbound
0x18022db19  mov     edx, 1; nDim
0x18022db1e  mov     rcx, r14; psa
0x18022db21  call    cs:__imp_SafeArrayGetUBound
0x18022db27  test    eax, eax
0x18022db29  jz      short loc_18022DB57
0x18022db2b  mov     rcx, [rbx+18h]
0x18022db2f  mov     eax, [rcx]
0x18022db31  cmp     eax, 4
0x18022db34  jbe     loc_18022E216
0x18022db3a  lea     rax, aRemoveunsuppor_12; "RemoveUnsupportedAddresses failed to ge"...
0x18022db41  mov     [rsp+180h+psa], rax
0x18022db46  lea     rax, [rsp+180h+psa]
0x18022db4b  lea     rdx, unk_180341943
0x18022db52  jmp     loc_18022E20B
0x18022db57  mov     ecx, [rbp+80h+plUbound]
0x18022db5a  cmp     [rbp+80h+var_F8], ecx
0x18022db5d  jz      short loc_18022DB8B
0x18022db5f  mov     rcx, [rbx+18h]
0x18022db63  mov     eax, [rcx]
0x18022db65  cmp     eax, 4
0x18022db68  jbe     loc_18022E216
0x18022db6e  lea     rax, aRemoveunsuppor_19; "RemoveUnsupportedAddresses failed upper"...
0x18022db75  mov     [rsp+180h+psa], rax
0x18022db7a  lea     rax, [rsp+180h+psa]
0x18022db7f  lea     rdx, unk_18034176B
0x18022db86  jmp     loc_18022E20B
0x18022db8b  mov     eax, [rbp+80h+plLbound]
0x18022db8e  mov     [rsp+180h+rgIndices], eax
0x18022db92  cmp     eax, ecx
0x18022db94  jg      loc_18022E1B7
0x18022db9a  mov     r12b, sil
0x18022db9d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18022dba5  mov     rdi, [rsp+180h+psa]
0x18022dbaa  mov     r15b, [rsp+180h+var_140]
0x18022dbaf  mov     [rsp+180h+psa], rsi
0x18022dbb4  lea     r8, [rsp+180h+psa]; pv
0x18022dbb9  lea     rdx, [rsp+180h+rgIndices]; rgIndices
0x18022dbbe  mov     rcx, rdi; psa
0x18022dbc1  call    cs:__imp_SafeArrayGetElement
0x18022dbc7  mov     dword ptr [rbp+80h+Addr.S_un], esi
0x18022dbca  mov     [rsp+180h+Terminator], rsi
0x18022dbcf  lea     r9, [rbp+80h+Addr]; Addr
0x18022dbd3  lea     r8, [rsp+180h+Terminator]; Terminator
0x18022dbd8  mov     dl, 1; Strict
0x18022dbda  mov     rcx, [rsp+180h+psa]; S
0x18022dbdf  call    cs:__imp_RtlIpv4StringToAddressW
0x18022dbe5  mov     esi, dword ptr [rbp+80h+Addr.S_un]
0x18022dbe8  xor     r13d, r13d
0x18022dbeb  test    eax, eax
0x18022dbed  cmovnz  esi, r13d
0x18022dbf1  mov     rcx, [rbx+18h]
0x18022dbf5  mov     eax, [rcx]
0x18022dbf7  cmp     eax, 4
0x18022dbfa  jbe     short loc_18022DC3E
0x18022dbfc  mov     dword ptr [rbp+80h+Addr.S_un], esi
0x18022dbff  mov     rax, [rsp+180h+psa]
0x18022dc04  mov     [rsp+180h+Terminator], rax
0x18022dc09  lea     rax, aRemoveunsuppor; "RemoveUnsupportedAddresses IsValidIPv4A"...
0x18022dc10  mov     [rsp+180h+var_130], rax
0x18022dc15  lea     rax, [rbp+80h+Addr]
0x18022dc19  mov     [rsp+180h+var_150], rax
0x18022dc1e  lea     rax, [rsp+180h+Terminator]
0x18022dc23  mov     [rsp+180h+var_158], rax
0x18022dc28  lea     rax, [rsp+180h+var_130]
0x18022dc2d  mov     [rsp+180h+var_160], rax
0x18022dc32  lea     rdx, unk_1803417C6
0x18022dc39  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18022dc3e  test    esi, esi
0x18022dc40  jz      short loc_18022DC94
0x18022dc42  mov     rcx, [rsp+180h+var_120]
0x18022dc47  test    rcx, rcx
0x18022dc4a  jz      loc_18022DD13
0x18022dc50  mov     rax, [rcx]
0x18022dc53  cmp     rax, [rcx+8]
0x18022dc57  jz      loc_18022DD13
0x18022dc5d  cmp     [rax], esi
0x18022dc5f  jz      short loc_18022DC67
0x18022dc61  add     rax, 4
0x18022dc65  jmp     short loc_18022DC53
0x18022dc67  mov     rcx, [rbx+18h]
0x18022dc6b  mov     eax, [rcx]
0x18022dc6d  cmp     eax, 4
0x18022dc70  jbe     short loc_18022DC94
0x18022dc72  lea     rax, aRemoveunsuppor_2; "RemoveUnsupportedAddresses excluded"
0x18022dc79  mov     [rsp+180h+var_130], rax
0x18022dc7e  lea     rax, [rsp+180h+var_130]
0x18022dc83  mov     [rsp+180h+var_160], rax
0x18022dc88  lea     rdx, unk_180341832
0x18022dc8f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18022dc94  mov     r12b, 1
0x18022dc97  xor     esi, esi
0x18022dc99  mov     eax, [rsp+180h+rgIndices]
0x18022dc9d  inc     eax
0x18022dc9f  mov     [rsp+180h+rgIndices], eax
0x18022dca3  cmp     eax, [rbp+80h+plUbound]
0x18022dca6  jle     loc_18022DBAF
0x18022dcac  test    r12b, r12b
0x18022dcaf  mov     edi, 80004005h
0x18022dcb4  mov     r15, [rsp+180h+var_128]
0x18022dcb9  mov     r12d, 2008h
0x18022dcbf  mov     r13, [rsp+180h+pvarg]
0x18022dcc4  jz      loc_18022E1B7
0x18022dcca  mov     rcx, r13; pvarg
0x18022dccd  call    cs:__imp_VariantClear
0x18022dcd3  mov     rcx, r15; pvarg
0x18022dcd6  call    cs:__imp_VariantClear
0x18022dcdc  mov     rax, qword ptr [rbp+80h+var_E8+8]
0x18022dce0  sub     rax, qword ptr [rbp+80h+var_E8]
0x18022dce4  sar     rax, 5
0x18022dce8  test    rax, rax
0x18022dceb  jnz     loc_18022DED1
0x18022dcf1  mov     rcx, [rbx+18h]
0x18022dcf5  mov     eax, [rcx]
0x18022dcf7  cmp     eax, 4
0x18022dcfa  jbe     loc_18022E216
0x18022dd00  lea     rax, aRemoveunsuppor_22; "RemoveUnsupportedAddresses list is empt"...
  ... truncated ...
```
