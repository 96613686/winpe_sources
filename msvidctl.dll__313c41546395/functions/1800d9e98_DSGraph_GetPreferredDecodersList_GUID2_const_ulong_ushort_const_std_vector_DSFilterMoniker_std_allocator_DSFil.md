# DSGraph::GetPreferredDecodersList(GUID2 * const,ulong,ushort const *,std::vector<DSFilterMoniker,std::allocator<DSFilterMoniker>> &)

- ea: `0x1800d9e98`
- end: `0x1800da3b4`
- name: `?GetPreferredDecodersList@DSGraph@@QEAAJQEAVGUID2@@KPEBGAEAV?$vector@VDSFilterMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@std@@@Z`
- size: `1308`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180066c70`
- `0x1800d9980`
- `0x1800d9a10`

## callees

- `0x180004640`
- `0x180004740`
- `0x180004b48`
- `0x1800054bc`
- `0x180006b38`
- `0x18000df18`
- `0x18000e1b8`
- `0x18000ff74`
- `0x180010e9c`
- `0x180011c40`
- `0x18001414c`
- `0x18001a0f8`
- `0x180030cb4`
- `0x1800598ec`
- `0x18005a120`
- `0x18005a308`
- `0x180076d64`
- `0x180077244`
- `0x18008061c`
- `0x180085ea4`
- `0x1800a0890`
- `0x1800b4ba0`
- `0x1800b4cbc`
- `0x1800b4f84`
- `0x1800d71d0`
- `0x1800d7474`
- `0x1800d9e98`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800da23c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800da23c`
- `ole32!CreateBindCtx` at `0x1800d9fab`
- `ole32!CreateBindCtx` at `0x1800d9fab`
- `ole32!MkParseDisplayName` at `0x1800d9fce`
- `ole32!MkParseDisplayName` at `0x1800d9fce`
- `ADVAPI32!RegEnumValueW` at `0x1800da224`
- `ADVAPI32!RegEnumValueW` at `0x1800da224`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800da192`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800da192`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall DSGraph::GetPreferredDecodersList(
        __int64 a1,
        struct _GUID *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        _QWORD *a5)
{
  LPMONIKER v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  bool v12; // bl
  void (__fastcall ***v13)(_QWORD, GUID *, LPBC *); // rcx
  HKEY v14; // rsi
  LSTATUS v15; // eax
  char v16; // r14
  DWORD v17; // ebx
  unsigned __int64 v18; // rdx
  WCHAR *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // r8
  int v24; // r9d
  int lpcbMaxValueLen; // [rsp+48h] [rbp-B8h]
  int lpcbSecurityDescriptor; // [rsp+50h] [rbp-B0h]
  ULONG pchEaten; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+88h] [rbp-78h] BYREF
  LPMONIKER ppmk; // [rsp+90h] [rbp-70h] BYREF
  LPBC ppbc; // [rsp+98h] [rbp-68h] BYREF
  LPCOLESTR szUserName; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cValues; // [rsp+A8h] [rbp-58h] BYREF
  DWORD cSubKeys; // [rsp+ACh] [rbp-54h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v41[8]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v42[8]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[8]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v44[24]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v45[8]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v46[3]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v47[3]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v48[24]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v49[8]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v50; // [rsp+160h] [rbp+60h]
  _BYTE v51[16]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v52[48]; // [rsp+180h] [rbp+80h] BYREF

  std::vector<DSPin>::vector<DSPin>(v44);
  std::vector<DSPin>::vector<DSPin>(v48);
  memset(v46, 0, sizeof(v46));
  memset_0(v52, 0, 0x52u);
  WTL::CString::CString(
    (WTL::CString *)&lpSubKey,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Media Center\\Decoder");
  if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v46, HKEY_LOCAL_MACHINE, lpSubKey, 0x20019u, 0) )
  {
    cbMaxValueLen = 82;
    if ( ATL::CRegKey::QueryValue((ATL::CRegKey *)v46, v52, a4, &cbMaxValueLen) )
    {
      memset_0(v52, 0, 0x52u);
    }
    else
    {
      WTL::CString::CString((WTL::CString *)&szUserName, L"@device:sw:{083863F1-70DE-11D0-BD40-00A0C911CE86}\\");
      WTL::CString::operator+=((WTL::CString *)&szUserName, v52);
      ppbc = 0;
      CreateBindCtx(0, &ppbc);
      ppmk = 0;
      if ( ppbc )
      {
        pchEaten = 0;
        if ( MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk) >= 0 )
        {
          std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
            v44,
            &ppmk);
        }
        else
        {
          v8 = ppmk;
          if ( ppmk )
          {
            ppmk = 0;
            ((void (__fastcall *)(LPMONIKER))v8->lpVtbl->Release)(v8);
          }
        }
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppmk);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppbc);
      WTL::CString::~CString((WTL::CString *)&szUserName);
    }
  }
  ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(
    v45,
    *(_QWORD *)(a1 + 8));
  DSFilterMapper::DSFilterMapper(
    (DSFilterMapper *)v49,
    0x600000u,
    1,
    1u,
    a2,
    0,
    lpcbMaxValueLen,
    lpcbSecurityDescriptor,
    1,
    0,
    0,
    0);
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v45);
  if ( v50 )
  {
    Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(
      v49,
      v37);
    while ( 1 )
    {
      v11 = Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::end(
              v10,
              v51);
      v12 = v38 != *(_QWORD *)(v11 + 8);
      enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v51);
      if ( !v12 )
        break;
      v13 = *(void (__fastcall ****)(_QWORD, GUID *, LPBC *))enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(
                                                               v37,
                                                               v41);
      ppbc = 0;
      if ( v13 )
        (**v13)(v13, &GUID_a8809222_07bb_48ea_951c_33158100625b, &ppbc);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v41);
      if ( !ppbc )
        goto LABEL_26;
      hKey = 0;
      if ( ((int (__fastcall *)(LPBC, HKEY *))ppbc->lpVtbl->RegisterObjectBound)(ppbc, &hKey) < 0 )
        goto LABEL_26;
      v47[1] = 0;
      v47[2] = 0;
      v14 = hKey;
      v47[0] = hKey;
      cSubKeys = 0;
      cValues = 0;
      pchEaten = 0;
      cbMaxValueNameLen = 0;
      cbMaxValueLen = 0;
      v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &pchEaten, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
      v9 = v15;
      if ( v15 )
      {
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        ATL::CRegKey::Close((ATL::CRegKey *)v47);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppbc);
        enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v37);
        goto LABEL_33;
      }
      v16 = 0;
      pchEaten = 2 * pchEaten + 2;
      cbMaxValueNameLen = 2 * cbMaxValueNameLen + 2;
      v17 = 0;
      v19 = (WCHAR *)operator new[](saturated_mul(cbMaxValueNameLen + 1, 2u));
      while ( v17 < cbMaxValueLen )
      {
        LODWORD(szUserName) = 0;
        LODWORD(ppmk) = cbMaxValueNameLen + 1;
        cbData = 0;
        if ( !RegEnumValueW(v14, v17, v19, (LPDWORD)&ppmk, 0, (LPDWORD)&szUserName, 0, &cbData)
          && !(unsigned int)_o__wcsnicmp(v19, L"{374AC4Df-7C98-4257-B13D-36087DBEE458}", 38) )
        {
          v16 = 1;
          v20 = enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(
                  v37,
                  v42);
          std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
            v44,
            v20);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v42);
          break;
        }
        ++v17;
      }
      operator delete(v19, v18);
      ATL::CRegKey::Close((ATL::CRegKey *)v47);
      if ( !v16 )
      {
LABEL_26:
        v21 = enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(
                v37,
                v43);
        std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(
          v48,
          v21);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v43);
      }
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppbc);
      enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator++(v37);
    }
    enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(v37);
    std::vector<ATL::CComBSTR>::end(v48, v43);
    std::_Tree<std::_Tmap_traits<ATL::CComBSTR,unsigned long,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,unsigned long>>,0>>::end(
      v48,
      v42);
    v22 = (_QWORD *)std::vector<ATL::CComBSTR>::end(v44, v41);
    std::vector<DSFilterMoniker>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilterMoniker>>>,0>(
      (unsigned int)v44,
      (unsigned int)&ppmk,
      *v22,
      v24,
      v23);
    std::vector<DSFilterMoniker>::operator=(a5, v44);
    v9 = -2147220907;
    if ( a5[1] != *a5 )
      v9 = 0;
  }
  else
  {
    v9 = -2147467259;
  }
LABEL_33:
  DSFilterMapper::~DSFilterMapper((DSFilterMapper *)v49);
  WTL::CString::~CString((WTL::CString *)&lpSubKey);
  ATL::CRegKey::Close((ATL::CRegKey *)v46);
  std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v48);
  std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>::_Tidy(v44);
  return v9;
}

```

## disassembly

```asm
0x1800d9e98  mov     [rsp-8+arg_8], rbx
0x1800d9e9d  mov     [rsp-8+arg_10], rsi
0x1800d9ea2  push    rbp
0x1800d9ea3  push    rdi
0x1800d9ea4  push    r12
0x1800d9ea6  push    r14
0x1800d9ea8  push    r15
0x1800d9eaa  lea     rbp, [rsp-0F0h]
0x1800d9eb2  sub     rsp, 1F0h
0x1800d9eb9  mov     rax, cs:__security_cookie
0x1800d9ec0  xor     rax, rsp
0x1800d9ec3  mov     [rbp+110h+var_30], rax
0x1800d9eca  mov     rbx, r9
0x1800d9ecd  mov     rdi, rdx
0x1800d9ed0  mov     rsi, rcx
0x1800d9ed3  mov     r15, [rbp+110h+arg_20]
0x1800d9eda  lea     rcx, [rbp+110h+var_120]
0x1800d9ede  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800d9ee3  nop
0x1800d9ee4  lea     rcx, [rbp+110h+var_D0]
0x1800d9ee8  call    ??0?$vector@VDSPin@@V?$allocator@VDSPin@@@std@@@std@@QEAA@XZ; std::vector<DSPin>::vector<DSPin>(void)
0x1800d9eed  nop
0x1800d9eee  xor     r12d, r12d
0x1800d9ef1  mov     [rbp+110h+var_100], r12
0x1800d9ef5  mov     [rbp+110h+var_F8], r12
0x1800d9ef9  mov     [rbp+110h+var_F0], r12
0x1800d9efd  lea     r14d, [r12+52h]
0x1800d9f02  mov     r8d, r14d; Size
0x1800d9f05  xor     edx, edx; Val
0x1800d9f07  lea     rcx, [rbp+110h+var_90]; void *
0x1800d9f0e  call    memset_0
0x1800d9f13  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d9f1a  lea     rcx, [rbp+110h+lpSubKey]; this
0x1800d9f1e  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x1800d9f23  nop
0x1800d9f24  mov     dword ptr [rsp+210h+lpcSubKeys], r12d; unsigned int
0x1800d9f29  mov     r9d, 20019h; unsigned int
0x1800d9f2f  mov     r8, [rbp+110h+lpSubKey]; lpSubKey
0x1800d9f33  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800d9f3a  lea     rcx, [rbp+110h+var_100]; this
0x1800d9f3e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x1800d9f43  test    eax, eax
0x1800d9f45  jnz     loc_1800DA01E
0x1800d9f4b  mov     [rbp+110h+cbMaxValueLen], r14d
0x1800d9f4f  lea     r9, [rbp+110h+cbMaxValueLen]; unsigned int *
0x1800d9f53  mov     r8, rbx; unsigned __int16 *
0x1800d9f56  lea     rdx, [rbp+110h+var_90]; unsigned __int16 *
0x1800d9f5d  lea     rcx, [rbp+110h+var_100]; this
0x1800d9f61  call    ?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z; ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x1800d9f66  test    eax, eax
0x1800d9f68  jz      short loc_1800D9F80
0x1800d9f6a  mov     r8d, r14d; Size
0x1800d9f6d  xor     edx, edx; Val
0x1800d9f6f  lea     rcx, [rbp+110h+var_90]; void *
0x1800d9f76  call    memset_0
0x1800d9f7b  jmp     loc_1800DA01E
0x1800d9f80  lea     rdx, aDeviceSw083863; "@device:sw:{083863F1-70DE-11D0-BD40-00A"...
0x1800d9f87  lea     rcx, [rbp+110h+szUserName]; this
0x1800d9f8b  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x1800d9f90  nop
0x1800d9f91  lea     rdx, [rbp+110h+var_90]; unsigned __int16 *
0x1800d9f98  lea     rcx, [rbp+110h+szUserName]; this
0x1800d9f9c  call    ??YCString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator+=(ushort const *)
0x1800d9fa1  mov     [rbp+110h+ppbc], r12
0x1800d9fa5  lea     rdx, [rbp+110h+ppbc]; ppbc
0x1800d9fa9  xor     ecx, ecx; reserved
0x1800d9fab  call    cs:__imp_CreateBindCtx
0x1800d9fb1  mov     [rbp+110h+ppmk], r12
0x1800d9fb5  mov     rcx, [rbp+110h+ppbc]; pbc
0x1800d9fb9  test    rcx, rcx
0x1800d9fbc  jz      short loc_1800DA001
0x1800d9fbe  mov     [rbp+110h+pchEaten], r12d
0x1800d9fc2  lea     r9, [rbp+110h+ppmk]; ppmk
0x1800d9fc6  lea     r8, [rbp+110h+pchEaten]; pchEaten
0x1800d9fca  mov     rdx, [rbp+110h+szUserName]; szUserName
0x1800d9fce  call    cs:__imp_MkParseDisplayName
0x1800d9fd4  test    eax, eax
0x1800d9fd6  jns     short loc_1800D9FF3
0x1800d9fd8  mov     rcx, [rbp+110h+ppmk]
0x1800d9fdc  test    rcx, rcx
0x1800d9fdf  jz      short loc_1800DA001
0x1800d9fe1  mov     [rbp+110h+ppmk], r12
0x1800d9fe5  mov     rax, [rcx]
0x1800d9fe8  mov     rax, [rax+10h]
0x1800d9fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ff1  jmp     short loc_1800DA001
0x1800d9ff3  lea     rdx, [rbp+110h+ppmk]
0x1800d9ff7  lea     rcx, [rbp+110h+var_120]
0x1800d9ffb  call    ?push_back@?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXAEBV?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e> const &)
0x1800da000  nop
0x1800da001  lea     rcx, [rbp+110h+ppmk]
0x1800da005  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da00a  nop
0x1800da00b  lea     rcx, [rbp+110h+ppbc]
0x1800da00f  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da014  nop
0x1800da015  lea     rcx, [rbp+110h+szUserName]; this
0x1800da019  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800da01e  mov     rdx, [rsi+8]
0x1800da022  lea     rcx, [rbp+110h+var_108]
0x1800da026  call    ??0?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2>(IUnknown *)
0x1800da02b  nop
0x1800da02c  mov     [rsp+210h+var_1A0], r12; struct REGPINMEDIUM *
0x1800da031  mov     [rsp+210h+var_1A8], r12; struct _GUID *
0x1800da036  mov     [rsp+210h+var_1B0], r12d; unsigned int
0x1800da03b  mov     dword ptr [rsp+210h+lpftLastWriteTime], 1; int
0x1800da043  mov     [rsp+210h+lpcbMaxValueNameLen], r12; struct REGPINMEDIUM *
0x1800da048  mov     [rsp+210h+lpcValues], rdi; struct _GUID *
0x1800da04d  mov     dword ptr [rsp+210h+lpcbMaxClassLen], 1; unsigned int
0x1800da055  mov     dword ptr [rsp+210h+lpcbMaxSubKeyLen], 1; int
0x1800da05d  mov     dword ptr [rsp+210h+lpcSubKeys], 600000h; unsigned int
0x1800da065  mov     r9d, 1
0x1800da06b  mov     rdx, rax
0x1800da06e  lea     rcx, [rbp+110h+var_B8]; this
0x1800da072  call    ??0DSFilterMapper@@QEAA@AEAV?$CComQIPtr@UIFilterMapper2@@$1?IID_IFilterMapper2@@3U_GUID@@B@ATL@@KHKHKPEBU_GUID@@PEBUREGPINMEDIUM@@1HHK121@Z; DSFilterMapper::DSFilterMapper(ATL::CComQIPtr<IFilterMapper2,&_GUID const IID_IFilterMapper2> &,ulong,int,ulong,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *,int,int,ulong,_GUID const *,REGPINMEDIUM const *,_GUID const *)
0x1800da077  nop
0x1800da078  lea     rcx, [rbp+110h+var_108]
0x1800da07c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da081  cmp     [rbp+110h+var_B0], r12
0x1800da085  jnz     short loc_1800DA091
0x1800da087  mov     ebx, 80004005h
0x1800da08c  jmp     loc_1800DA356
0x1800da091  lea     rdx, [rbp+110h+var_158]
0x1800da095  lea     rcx, [rbp+110h+var_B8]
0x1800da099  call    ?begin@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::begin(void)
0x1800da09e  nop
0x1800da09f  lea     rdx, [rbp+110h+var_A0]
0x1800da0a3  call    ?end@?$Forward_Sequence@V?$CComQIPtr@UICreateDevEnum@@$1?IID_ICreateDevEnum@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@2@VDSFilterMoniker@@UICreateDevEnum@@UIEnumMoniker@@PEAUIMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@@QEAA?AV?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@XZ; Forward_Sequence<ATL::CComQIPtr<ICreateDevEnum,&_GUID const IID_ICreateDevEnum>,ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,ICreateDevEnum,IEnumMoniker,IMoniker *,std::allocator<DSFilterMoniker>>::end(void)
0x1800da0a8  mov     rcx, [rax+8]
0x1800da0ac  cmp     [rbp+110h+var_150], rcx
0x1800da0b0  setnz   bl
0x1800da0b3  lea     rcx, [rbp+110h+var_A0]
0x1800da0b7  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800da0bc  test    bl, bl
0x1800da0be  jz      loc_1800DA2EE
0x1800da0c4  lea     rdx, [rbp+110h+var_138]
0x1800da0c8  lea     rcx, [rbp+110h+var_158]
0x1800da0cc  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEBA?AVDSFilterMoniker@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(void)
0x1800da0d1  nop
0x1800da0d2  mov     rcx, [rax]
0x1800da0d5  mov     [rbp+110h+ppbc], r12
0x1800da0d9  test    rcx, rcx
0x1800da0dc  jz      short loc_1800DA0F5
0x1800da0de  mov     rax, [rcx]
0x1800da0e1  lea     r8, [rbp+110h+ppbc]
0x1800da0e5  lea     rdx, _GUID_a8809222_07bb_48ea_951c_33158100625b
0x1800da0ec  mov     rax, [rax]
0x1800da0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da0f4  nop
0x1800da0f5  lea     rcx, [rbp+110h+var_138]
0x1800da0f9  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da0fe  mov     rcx, [rbp+110h+ppbc]
0x1800da102  test    rcx, rcx
0x1800da105  jz      loc_1800DA288
0x1800da10b  mov     [rbp+110h+hKey], r12
0x1800da10f  mov     rax, [rcx]
0x1800da112  lea     rdx, [rbp+110h+hKey]
0x1800da116  mov     rax, [rax+18h]
0x1800da11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da11f  test    eax, eax
0x1800da121  js      loc_1800DA288
0x1800da127  mov     [rbp+110h+var_E0], r12
0x1800da12b  mov     [rbp+110h+var_D8], r12
0x1800da12f  mov     rsi, [rbp+110h+hKey]
0x1800da133  mov     [rbp+110h+var_E8], rsi
0x1800da137  mov     [rbp+110h+cSubKeys], r12d
0x1800da13b  mov     [rbp+110h+cValues], r12d
0x1800da13f  mov     [rbp+110h+pchEaten], r12d
0x1800da143  mov     [rbp+110h+cbMaxValueNameLen], r12d
0x1800da147  mov     [rbp+110h+cbMaxValueLen], r12d
0x1800da14b  mov     [rsp+210h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800da150  mov     [rsp+210h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800da155  lea     rax, [rbp+110h+cbMaxValueLen]
0x1800da159  mov     [rsp+210h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800da15e  lea     rax, [rbp+110h+cbMaxValueNameLen]
0x1800da162  mov     [rsp+210h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800da167  lea     rax, [rbp+110h+cValues]
0x1800da16b  mov     [rsp+210h+lpcValues], rax; lpcValues
0x1800da170  mov     [rsp+210h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800da175  lea     rax, [rbp+110h+pchEaten]
0x1800da179  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800da17e  lea     rax, [rbp+110h+cSubKeys]
0x1800da182  mov     [rsp+210h+lpcSubKeys], rax; lpcSubKeys
0x1800da187  xor     r9d, r9d; lpReserved
0x1800da18a  xor     r8d, r8d; lpcchClass
0x1800da18d  xor     edx, edx; lpClass
0x1800da18f  mov     rcx, rsi; hKey
0x1800da192  call    cs:__imp_RegQueryInfoKeyW
0x1800da198  mov     ebx, eax
0x1800da19a  test    eax, eax
0x1800da19c  jnz     loc_1800DA2C4
0x1800da1a2  mov     r14b, r12b
0x1800da1a5  mov     eax, [rbp+110h+pchEaten]
0x1800da1a8  lea     eax, ds:2[rax*2]
0x1800da1af  mov     [rbp+110h+pchEaten], eax
0x1800da1b2  mov     eax, [rbp+110h+cbMaxValueNameLen]
0x1800da1b5  lea     eax, ds:2[rax*2]
0x1800da1bc  mov     [rbp+110h+cbMaxValueNameLen], eax
0x1800da1bf  mov     ebx, r12d
0x1800da1c2  lea     ecx, [rax+1]
0x1800da1c5  mov     eax, 2
0x1800da1ca  mul     rcx
0x1800da1cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800da1d4  cmovb   rax, rcx
0x1800da1d8  mov     rcx, rax; unsigned __int64
0x1800da1db  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800da1e0  mov     rdi, rax
0x1800da1e3  cmp     ebx, [rbp+110h+cbMaxValueLen]
0x1800da1e6  jnb     loc_1800DA271
0x1800da1ec  mov     dword ptr [rbp+110h+szUserName], r12d
0x1800da1f0  mov     ecx, [rbp+110h+cbMaxValueNameLen]
0x1800da1f3  inc     ecx
0x1800da1f5  mov     dword ptr [rbp+110h+ppmk], ecx
0x1800da1f8  mov     [rbp+110h+cbData], r12d
0x1800da1fc  lea     rax, [rbp+110h+cbData]
0x1800da200  mov     [rsp+210h+lpcValues], rax; lpcbData
0x1800da205  mov     [rsp+210h+lpcbMaxClassLen], r12; lpData
0x1800da20a  lea     rax, [rbp+110h+szUserName]
0x1800da20e  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpType
0x1800da213  mov     [rsp+210h+lpcSubKeys], r12; lpReserved
0x1800da218  lea     r9, [rbp+110h+ppmk]; lpcchValueName
0x1800da21c  mov     r8, rdi; lpValueName
0x1800da21f  mov     edx, ebx; dwIndex
0x1800da221  mov     rcx, rsi; hKey
0x1800da224  call    cs:__imp_RegEnumValueW
0x1800da22a  test    eax, eax
0x1800da22c  jnz     short loc_1800DA246
0x1800da22e  lea     r8d, [rax+26h]
0x1800da232  lea     rdx, a374ac4df7c9842; "{374AC4Df-7C98-4257-B13D-36087DBEE458}"
0x1800da239  mov     rcx, rdi
0x1800da23c  call    cs:__imp__o__wcsnicmp
0x1800da242  test    eax, eax
0x1800da244  jz      short loc_1800DA24A
0x1800da246  inc     ebx
0x1800da248  jmp     short loc_1800DA1E3
0x1800da24a  mov     r14b, 1
0x1800da24d  lea     rdx, [rbp+110h+var_130]
0x1800da251  lea     rcx, [rbp+110h+var_158]
0x1800da255  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEBA?AVDSFilterMoniker@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(void)
0x1800da25a  nop
0x1800da25b  mov     rdx, rax
0x1800da25e  lea     rcx, [rbp+110h+var_120]
0x1800da262  call    ?push_back@?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXAEBV?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e> const &)
0x1800da267  nop
0x1800da268  lea     rcx, [rbp+110h+var_130]
0x1800da26c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da271  mov     rcx, rdi; void *
0x1800da274  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800da279  nop
0x1800da27a  lea     rcx, [rbp+110h+var_E8]; this
0x1800da27e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800da283  test    r14b, r14b
0x1800da286  jnz     short loc_1800DA2AD
0x1800da288  lea     rdx, [rbp+110h+var_128]
0x1800da28c  lea     rcx, [rbp+110h+var_158]
0x1800da290  call    ??D?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEBA?AVDSFilterMoniker@@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator*(void)
0x1800da295  nop
0x1800da296  mov     rdx, rax
0x1800da299  lea     rcx, [rbp+110h+var_D0]
0x1800da29d  call    ?push_back@?$vector@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@std@@@std@@QEAAXAEBV?$CComQIPtr@UIMSVidDevice@@$1?_GUID_1c15d47c_911d_11d2_b632_00c04f79498e@@3U__s_GUID@@B@ATL@@@Z; std::vector<ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e>>::push_back(ATL::CComQIPtr<IMSVidDevice,&__s_GUID const _GUID_1c15d47c_911d_11d2_b632_00c04f79498e> const &)
0x1800da2a2  nop
0x1800da2a3  lea     rcx, [rbp+110h+var_128]
0x1800da2a7  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da2ac  nop
0x1800da2ad  lea     rcx, [rbp+110h+ppbc]
0x1800da2b1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da2b6  lea     rcx, [rbp+110h+var_158]
0x1800da2ba  call    ??E?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAAAEAV0@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::operator++(void)
0x1800da2bf  jmp     loc_1800DA09F
0x1800da2c4  jle     short loc_1800DA2CF
0x1800da2c6  movzx   ebx, ax
0x1800da2c9  or      ebx, 80070000h
0x1800da2cf  lea     rcx, [rbp+110h+var_E8]; this
0x1800da2d3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800da2d8  nop
0x1800da2d9  lea     rcx, [rbp+110h+ppbc]
0x1800da2dd  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800da2e2  nop
0x1800da2e3  lea     rcx, [rbp+110h+var_158]
0x1800da2e7  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800da2ec  jmp     short loc_1800DA356
0x1800da2ee  lea     rcx, [rbp+110h+var_158]
0x1800da2f2  call    ??1?$enumerator_iterator@V?$CComQIPtr@UIEnumMoniker@@$1?IID_IEnumMoniker@@3U_GUID@@B@ATL@@VDSFilterMoniker@@UIEnumMoniker@@PEAUIMoniker@@_J@@QEAA@XZ; enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>::~enumerator_iterator<ATL::CComQIPtr<IEnumMoniker,&_GUID const IID_IEnumMoniker>,DSFilterMoniker,IEnumMoniker,IMoniker *,__int64>(void)
0x1800da2f7  lea     rdx, [rbp+110h+var_128]
0x1800da2fb  lea     rcx, [rbp+110h+var_D0]
0x1800da2ff  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800da304  mov     r8, [rax]
0x1800da307  lea     rdx, [rbp+110h+var_130]
0x1800da30b  lea     rcx, [rbp+110h+var_D0]
0x1800da30f  call    ?end@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ulong,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ulong>>,0>>::end(void)
0x1800da314  mov     r9, [rax]
0x1800da317  lea     rdx, [rbp+110h+var_138]
0x1800da31b  lea     rcx, [rbp+110h+var_120]
0x1800da31f  call    ?end@?$vector@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCComBSTR@ATL@@@std@@@std@@@2@XZ; std::vector<ATL::CComBSTR>::end(void)
0x1800da324  mov     [rsp+210h+lpcSubKeys], r8
0x1800da329  mov     r8, [rax]
0x1800da32c  lea     rdx, [rbp+110h+ppmk]
0x1800da330  lea     rcx, [rbp+110h+var_120]
0x1800da334  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VDSFilterMoniker@@@std@@@std@@@std@@$0A@@?$vector@VDSFilterMoniker@@V?$allocator@VDSFilterMoniker@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VDSFilterMoniker@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VDSFilterMoniker@@@std@@@std@@@1@V21@1@Z; std::vector<DSFilterMoniker>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilterMoniker>>>,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<DSFilterMoniker>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilterMoniker>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<DSFilterMoniker>>>)
0x1800da339  lea     rdx, [rbp+110h+var_120]
  ... truncated ...
```
