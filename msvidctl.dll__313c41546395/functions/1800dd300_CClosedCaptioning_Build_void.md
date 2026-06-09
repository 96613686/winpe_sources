# CClosedCaptioning::Build(void)

- ea: `0x1800dd300`
- end: `0x1800dd7a6`
- name: `?Build@CClosedCaptioning@@UEAAJXZ`
- size: `1190`
- prototype: `__int64 __fastcall(CClosedCaptioning *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18000e1b8`
- `0x18000e210`
- `0x18002a658`
- `0x180032f40`
- `0x18007a20c`
- `0x18008cd90`
- `0x1800d76bc`
- `0x1800dd300`
- `0x1800f8010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800dd69e`
- `ole32!CoCreateInstance` at `0x1800dd69e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd48c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd4d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd514`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd561`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd65a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd48c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd4d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd514`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd561`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dd65a`

## pseudocode

```c
__int64 __fastcall CClosedCaptioning::Build(CClosedCaptioning *this)
{
  unsigned int v2; // edi
  int v3; // eax
  int v4; // eax
  __int64 v5; // rcx
  unsigned __int16 *v6; // rbx
  LPVOID *v7; // rcx
  LPVOID *v8; // rcx
  int v9; // r14d
  LPVOID *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // ebx
  __int64 v14; // rcx
  int v16; // [rsp+30h] [rbp-29h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-21h] BYREF
  void **v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-9h] BYREF
  LPVOID v21; // [rsp+58h] [rbp-1h] BYREF
  LPVOID v22; // [rsp+60h] [rbp+7h] BYREF
  LPVOID v23; // [rsp+68h] [rbp+Fh] BYREF
  CLSID pclsid; // [rsp+70h] [rbp+17h] BYREF
  CLSID rclsid; // [rsp+80h] [rbp+27h] BYREF

  v16 = 0;
  (*(void (__fastcall **)(char *, int *))(*((_QWORD *)this - 4) + 40LL))((char *)this - 32, &v16);
  v19 = 0;
  v18 = &DSFilter::`vftable';
  v2 = 1;
  v17 = WTL::_atltmpPchNil;
  v3 = v16;
  if ( (v16 & 8) == 0 || *((_DWORD *)this + 14) != -1 )
    goto LABEL_10;
  ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(
    &v23,
    &CLSID_CaptionsFilter);
  if ( v23 )
  {
    (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))v23)(v23, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &v19);
    WTL::CString::operator=((WTL::CString *)&v17, L"708/608 Decoder");
    if ( !v19 )
    {
      v2 = -2147418113;
      goto LABEL_8;
    }
    v4 = DSGraph::AddFilter(
           (CClosedCaptioning *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
           (struct DSFilter *)&v18,
           (struct WTL::CString *)&v17);
    if ( v4 < 0 )
    {
      v2 = v4;
      goto LABEL_8;
    }
    std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v18);
    v5 = *(int *)(*((_QWORD *)this + 1) + 4LL);
    *((_DWORD *)this + 14) = ((__int64)(*(_QWORD *)((char *)this + v5 + 64) - *(_QWORD *)((char *)this + v5 + 56)) >> 4)
                           - 1;
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
    v3 = v16;
LABEL_10:
    if ( (v3 & 4) != 0 && *((_DWORD *)this + 13) == -1 )
    {
      v6 = A2WBSTR("{12686101-F7CE-4ADF-937D-02A004B392C5}", -1);
      GUID2::operator=(&pclsid, v6);
      ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(
        &v21,
        &pclsid);
      if ( !v21 )
      {
        v7 = &v21;
LABEL_14:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v7);
        SysFreeString(v6);
LABEL_15:
        v2 = -2147467259;
        goto LABEL_44;
      }
      (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))v21)(v21, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &v19);
      WTL::CString::operator=((WTL::CString *)&v17, L"WST Renderer");
      if ( !v19 )
      {
        v8 = &v21;
LABEL_18:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v8);
        SysFreeString(v6);
LABEL_19:
        v2 = -2147418113;
        goto LABEL_44;
      }
      v9 = DSGraph::AddFilter(
             (CClosedCaptioning *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
             (struct DSFilter *)&v18,
             (struct WTL::CString *)&v17);
      if ( v9 < 0 )
      {
        v10 = &v21;
LABEL_22:
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v10);
        SysFreeString(v6);
        v2 = v9;
        goto LABEL_44;
      }
      std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v18);
      v11 = *(int *)(*((_QWORD *)this + 1) + 4LL);
      *((_DWORD *)this + 13) = ((__int64)(*(_QWORD *)((char *)this + v11 + 64) - *(_QWORD *)((char *)this + v11 + 56)) >> 4)
                             - 1;
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v21);
      SysFreeString(v6);
      v3 = v16;
    }
    if ( (v3 & 2) != 0 && *((_DWORD *)this + 13) == -1 )
    {
      v6 = A2WBSTR("{0357B11F-B957-4a71-A9C6-F1FF6D2E476C}", -1);
      GUID2::operator=(&rclsid, v6);
      ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(
        &v22,
        &rclsid);
      if ( !v22 )
      {
        v7 = &v22;
        goto LABEL_14;
      }
      (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))v22)(v22, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &v19);
      WTL::CString::operator=((WTL::CString *)&v17, L"WST Decoder");
      if ( !v19 )
      {
        v8 = &v22;
        goto LABEL_18;
      }
      v9 = DSGraph::AddFilter(
             (CClosedCaptioning *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
             (struct DSFilter *)&v18,
             (struct WTL::CString *)&v17);
      if ( v9 < 0 )
      {
        v10 = &v22;
        goto LABEL_22;
      }
      std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v18);
      v12 = *(int *)(*((_QWORD *)this + 1) + 4LL);
      *((_DWORD *)this + 13) = ((__int64)(*(_QWORD *)((char *)this + v12 + 64) - *(_QWORD *)((char *)this + v12 + 56)) >> 4)
                             - 1;
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v22);
      SysFreeString(v6);
      v3 = v16;
    }
    if ( ((v3 & 1) != 0 || !v3) && *((_DWORD *)this + 12) == -1 )
    {
      ppv = 0;
      CoCreateInstance(&CLSID_Line21Decoder2, 0, 1u, &GUID_6e8d4a21_310c_11d0_b79a_00aa003767a7, &ppv);
      if ( !ppv )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        goto LABEL_15;
      }
      (**(void (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &GUID_56a86895_0ad4_11ce_b03a_0020af0ba770, &v19);
      WTL::CString::operator=((WTL::CString *)&v17, L"Line 21 Decoder");
      if ( !v19 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        goto LABEL_19;
      }
      v13 = DSGraph::AddFilter(
              (CClosedCaptioning *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 40),
              (struct DSFilter *)&v18,
              (struct WTL::CString *)&v17);
      if ( v13 < 0 )
      {
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
        v2 = v13;
        goto LABEL_44;
      }
      std::vector<DSFilter>::push_back((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 56, &v18);
      v14 = *(int *)(*((_QWORD *)this + 1) + 4LL);
      *((_DWORD *)this + 12) = ((__int64)(*(_QWORD *)((char *)this + v14 + 64) - *(_QWORD *)((char *)this + v14 + 56)) >> 4)
                             - 1;
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&ppv);
    }
    v2 = 0;
    goto LABEL_44;
  }
LABEL_8:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
LABEL_44:
  WTL::CString::~CString((WTL::CString *)&v17);
  v18 = &Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable';
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v19);
  return v2;
}

```

## disassembly

```asm
0x1800dd300  mov     [rsp-8+arg_8], rbx
0x1800dd305  mov     [rsp-8+arg_10], rsi
0x1800dd30a  push    rbp
0x1800dd30b  push    rdi
0x1800dd30c  push    r14
0x1800dd30e  lea     rbp, [rsp-47h]
0x1800dd313  sub     rsp, 0A0h
0x1800dd31a  mov     rax, cs:__security_cookie
0x1800dd321  xor     rax, rsp
0x1800dd324  mov     [rbp+57h+var_20], rax
0x1800dd328  mov     rsi, rcx
0x1800dd32b  mov     [rbp+57h+var_80], 0
0x1800dd332  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800dd336  lea     rdx, [rbp+57h+var_80]
0x1800dd33a  mov     rax, [rcx]
0x1800dd33d  mov     rax, [rax+28h]
0x1800dd341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd346  lea     rax, ??_7DSFilter@@6B@; const DSFilter::`vftable'
0x1800dd34d  mov     [rbp+57h+var_68], 0
0x1800dd355  mov     [rbp+57h+var_70], rax
0x1800dd359  mov     edi, 1
0x1800dd35e  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800dd365  mov     [rbp+57h+var_78], rax
0x1800dd369  mov     eax, [rbp+57h+var_80]
0x1800dd36c  test    al, 8
0x1800dd36e  jz      loc_1800DD43A
0x1800dd374  cmp     dword ptr [rsi+38h], 0FFFFFFFFh
0x1800dd378  jnz     loc_1800DD43A
0x1800dd37e  lea     rdx, CLSID_CaptionsFilter; rclsid
0x1800dd385  lea     rcx, [rbp+57h+var_48]; ppv
0x1800dd389  call    ??0?$CComQIPtr@UIBaseFilter@@$1?_GUID_56a86895_0ad4_11ce_b03a_0020af0ba770@@3U__s_GUID@@B@ATL@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(_GUID const &,IUnknown *,ulong)
0x1800dd38e  mov     rcx, [rbp+57h+var_48]
0x1800dd392  test    rcx, rcx
0x1800dd395  jz      short loc_1800DD3ED
0x1800dd397  mov     rax, [rcx]
0x1800dd39a  lea     r8, [rbp+57h+var_68]
0x1800dd39e  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x1800dd3a5  mov     rax, [rax]
0x1800dd3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd3ad  lea     rdx, a708608Decoder; "708/608 Decoder"
0x1800dd3b4  lea     rcx, [rbp+57h+var_78]; this
0x1800dd3b8  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800dd3bd  cmp     [rbp+57h+var_68], 0
0x1800dd3c2  jnz     short loc_1800DD3CB
0x1800dd3c4  mov     edi, 8000FFFFh
0x1800dd3c9  jmp     short loc_1800DD3ED
0x1800dd3cb  mov     rax, [rsi+8]
0x1800dd3cf  lea     r8, [rbp+57h+var_78]; struct WTL::CString *
0x1800dd3d3  lea     rdx, [rbp+57h+var_70]; struct DSFilter *
0x1800dd3d7  movsxd  rcx, dword ptr [rax+4]
0x1800dd3db  add     rcx, 28h ; '('
0x1800dd3df  add     rcx, rsi; this
0x1800dd3e2  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x1800dd3e7  test    eax, eax
0x1800dd3e9  jns     short loc_1800DD3FB
0x1800dd3eb  mov     edi, eax
0x1800dd3ed  lea     rcx, [rbp+57h+var_48]
0x1800dd3f1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd3f6  jmp     loc_1800DD763
0x1800dd3fb  mov     rax, [rsi+8]
0x1800dd3ff  lea     rdx, [rbp+57h+var_70]
0x1800dd403  movsxd  rcx, dword ptr [rax+4]
0x1800dd407  add     rcx, 38h ; '8'
0x1800dd40b  add     rcx, rsi
0x1800dd40e  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x1800dd413  mov     rax, [rsi+8]
0x1800dd417  movsxd  rcx, dword ptr [rax+4]
0x1800dd41b  mov     rax, [rcx+rsi+40h]
0x1800dd420  sub     rax, [rcx+rsi+38h]
0x1800dd425  lea     rcx, [rbp+57h+var_48]
0x1800dd429  sar     rax, 4
0x1800dd42d  sub     eax, edi
0x1800dd42f  mov     [rsi+38h], eax
0x1800dd432  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd437  mov     eax, [rbp+57h+var_80]
0x1800dd43a  test    al, 4
0x1800dd43c  jz      loc_1800DD56A
0x1800dd442  cmp     dword ptr [rsi+34h], 0FFFFFFFFh
0x1800dd446  jnz     loc_1800DD56A
0x1800dd44c  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800dd44f  lea     rcx, a12686101F7ce4a; "{12686101-F7CE-4ADF-937D-02A004B392C5}"
0x1800dd456  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800dd45b  mov     rdx, rax; unsigned __int16 *
0x1800dd45e  lea     rcx, [rbp+57h+pclsid]; pclsid
0x1800dd462  mov     rbx, rax
0x1800dd465  call    ??4GUID2@@QEAAAEAV0@QEAG@Z; GUID2::operator=(ushort * const)
0x1800dd46a  lea     rdx, [rbp+57h+pclsid]; rclsid
0x1800dd46e  lea     rcx, [rbp+57h+var_58]; ppv
0x1800dd472  call    ??0?$CComQIPtr@UIBaseFilter@@$1?_GUID_56a86895_0ad4_11ce_b03a_0020af0ba770@@3U__s_GUID@@B@ATL@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(_GUID const &,IUnknown *,ulong)
0x1800dd477  mov     rcx, [rbp+57h+var_58]
0x1800dd47b  test    rcx, rcx
0x1800dd47e  jnz     short loc_1800DD49C
0x1800dd480  lea     rcx, [rbp+57h+var_58]
0x1800dd484  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd489  mov     rcx, rbx; bstrString
0x1800dd48c  call    cs:__imp_SysFreeString
0x1800dd492  mov     edi, 80004005h
0x1800dd497  jmp     loc_1800DD763
0x1800dd49c  mov     rax, [rcx]
0x1800dd49f  lea     r8, [rbp+57h+var_68]
0x1800dd4a3  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x1800dd4aa  mov     rax, [rax]
0x1800dd4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd4b2  lea     rdx, aWstRenderer; "WST Renderer"
0x1800dd4b9  lea     rcx, [rbp+57h+var_78]; this
0x1800dd4bd  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800dd4c2  cmp     [rbp+57h+var_68], 0
0x1800dd4c7  jnz     short loc_1800DD4E5
0x1800dd4c9  lea     rcx, [rbp+57h+var_58]
0x1800dd4cd  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd4d2  mov     rcx, rbx; bstrString
0x1800dd4d5  call    cs:__imp_SysFreeString
0x1800dd4db  mov     edi, 8000FFFFh
0x1800dd4e0  jmp     loc_1800DD763
0x1800dd4e5  mov     rax, [rsi+8]
0x1800dd4e9  lea     r8, [rbp+57h+var_78]; struct WTL::CString *
0x1800dd4ed  lea     rdx, [rbp+57h+var_70]; struct DSFilter *
0x1800dd4f1  movsxd  rcx, dword ptr [rax+4]
0x1800dd4f5  add     rcx, 28h ; '('
0x1800dd4f9  add     rcx, rsi; this
0x1800dd4fc  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x1800dd501  mov     r14d, eax
0x1800dd504  test    eax, eax
0x1800dd506  jns     short loc_1800DD522
0x1800dd508  lea     rcx, [rbp+57h+var_58]
0x1800dd50c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd511  mov     rcx, rbx; bstrString
0x1800dd514  call    cs:__imp_SysFreeString
0x1800dd51a  mov     edi, r14d
0x1800dd51d  jmp     loc_1800DD763
0x1800dd522  mov     rax, [rsi+8]
0x1800dd526  lea     rdx, [rbp+57h+var_70]
0x1800dd52a  movsxd  rcx, dword ptr [rax+4]
0x1800dd52e  add     rcx, 38h ; '8'
0x1800dd532  add     rcx, rsi
0x1800dd535  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x1800dd53a  mov     rax, [rsi+8]
0x1800dd53e  movsxd  rcx, dword ptr [rax+4]
0x1800dd542  mov     rax, [rcx+rsi+40h]
0x1800dd547  sub     rax, [rcx+rsi+38h]
0x1800dd54c  lea     rcx, [rbp+57h+var_58]
0x1800dd550  sar     rax, 4
0x1800dd554  sub     eax, edi
0x1800dd556  mov     [rsi+34h], eax
0x1800dd559  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd55e  mov     rcx, rbx; bstrString
0x1800dd561  call    cs:__imp_SysFreeString
0x1800dd567  mov     eax, [rbp+57h+var_80]
0x1800dd56a  test    al, 2
0x1800dd56c  jz      loc_1800DD663
0x1800dd572  cmp     dword ptr [rsi+34h], 0FFFFFFFFh
0x1800dd576  jnz     loc_1800DD663
0x1800dd57c  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800dd57f  lea     rcx, a0357b11fB9574a; "{0357B11F-B957-4a71-A9C6-F1FF6D2E476C}"
0x1800dd586  call    ?A2WBSTR@@YAPEAGPEBDH@Z; A2WBSTR(char const *,int)
0x1800dd58b  mov     rdx, rax; unsigned __int16 *
0x1800dd58e  lea     rcx, [rbp+57h+rclsid]; pclsid
0x1800dd592  mov     rbx, rax
0x1800dd595  call    ??4GUID2@@QEAAAEAV0@QEAG@Z; GUID2::operator=(ushort * const)
0x1800dd59a  lea     rdx, [rbp+57h+rclsid]; rclsid
0x1800dd59e  lea     rcx, [rbp+57h+var_50]; ppv
0x1800dd5a2  call    ??0?$CComQIPtr@UIBaseFilter@@$1?_GUID_56a86895_0ad4_11ce_b03a_0020af0ba770@@3U__s_GUID@@B@ATL@@QEAA@AEBU_GUID@@PEAUIUnknown@@K@Z; ATL::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>::CComQIPtr<IBaseFilter,&__s_GUID const _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770>(_GUID const &,IUnknown *,ulong)
0x1800dd5a7  mov     rcx, [rbp+57h+var_50]
0x1800dd5ab  test    rcx, rcx
0x1800dd5ae  jnz     short loc_1800DD5B9
0x1800dd5b0  lea     rcx, [rbp+57h+var_50]
0x1800dd5b4  jmp     loc_1800DD484
0x1800dd5b9  mov     rax, [rcx]
0x1800dd5bc  lea     r8, [rbp+57h+var_68]
0x1800dd5c0  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x1800dd5c7  mov     rax, [rax]
0x1800dd5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd5cf  lea     rdx, aWstDecoder; "WST Decoder"
0x1800dd5d6  lea     rcx, [rbp+57h+var_78]; this
0x1800dd5da  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800dd5df  cmp     [rbp+57h+var_68], 0
0x1800dd5e4  jnz     short loc_1800DD5EF
0x1800dd5e6  lea     rcx, [rbp+57h+var_50]
0x1800dd5ea  jmp     loc_1800DD4CD
0x1800dd5ef  mov     rax, [rsi+8]
0x1800dd5f3  lea     r8, [rbp+57h+var_78]; struct WTL::CString *
0x1800dd5f7  lea     rdx, [rbp+57h+var_70]; struct DSFilter *
0x1800dd5fb  movsxd  rcx, dword ptr [rax+4]
0x1800dd5ff  add     rcx, 28h ; '('
0x1800dd603  add     rcx, rsi; this
0x1800dd606  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x1800dd60b  mov     r14d, eax
0x1800dd60e  test    eax, eax
0x1800dd610  jns     short loc_1800DD61B
0x1800dd612  lea     rcx, [rbp+57h+var_50]
0x1800dd616  jmp     loc_1800DD50C
0x1800dd61b  mov     rax, [rsi+8]
0x1800dd61f  lea     rdx, [rbp+57h+var_70]
0x1800dd623  movsxd  rcx, dword ptr [rax+4]
0x1800dd627  add     rcx, 38h ; '8'
0x1800dd62b  add     rcx, rsi
0x1800dd62e  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x1800dd633  mov     rax, [rsi+8]
0x1800dd637  movsxd  rcx, dword ptr [rax+4]
0x1800dd63b  mov     rax, [rcx+rsi+40h]
0x1800dd640  sub     rax, [rcx+rsi+38h]
0x1800dd645  lea     rcx, [rbp+57h+var_50]
0x1800dd649  sar     rax, 4
0x1800dd64d  sub     eax, edi
0x1800dd64f  mov     [rsi+34h], eax
0x1800dd652  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd657  mov     rcx, rbx; bstrString
0x1800dd65a  call    cs:__imp_SysFreeString
0x1800dd660  mov     eax, [rbp+57h+var_80]
0x1800dd663  test    dil, al
0x1800dd666  jnz     short loc_1800DD670
0x1800dd668  test    eax, eax
0x1800dd66a  jnz     loc_1800DD761
0x1800dd670  cmp     dword ptr [rsi+30h], 0FFFFFFFFh
0x1800dd674  jnz     loc_1800DD761
0x1800dd67a  lea     rax, [rbp+57h+var_60]
0x1800dd67e  mov     [rbp+57h+var_60], 0
0x1800dd686  lea     r9, _GUID_6e8d4a21_310c_11d0_b79a_00aa003767a7; riid
0x1800dd68d  mov     [rsp+0B0h+ppv], rax; ppv
0x1800dd692  mov     r8d, edi; dwClsContext
0x1800dd695  lea     rcx, CLSID_Line21Decoder2; rclsid
0x1800dd69c  xor     edx, edx; pUnkOuter
0x1800dd69e  call    cs:__imp_CoCreateInstance
0x1800dd6a4  mov     rcx, [rbp+57h+var_60]
0x1800dd6a8  test    rcx, rcx
0x1800dd6ab  jnz     short loc_1800DD6BB
0x1800dd6ad  lea     rcx, [rbp+57h+var_60]
0x1800dd6b1  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd6b6  jmp     loc_1800DD492
0x1800dd6bb  mov     rax, [rcx]
0x1800dd6be  lea     r8, [rbp+57h+var_68]
0x1800dd6c2  lea     rdx, _GUID_56a86895_0ad4_11ce_b03a_0020af0ba770
0x1800dd6c9  mov     rax, [rax]
0x1800dd6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd6d1  lea     rdx, aLine21Decoder; "Line 21 Decoder"
0x1800dd6d8  lea     rcx, [rbp+57h+var_78]; this
0x1800dd6dc  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800dd6e1  cmp     [rbp+57h+var_68], 0
0x1800dd6e6  jnz     short loc_1800DD6F6
0x1800dd6e8  lea     rcx, [rbp+57h+var_60]
0x1800dd6ec  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd6f1  jmp     loc_1800DD4DB
0x1800dd6f6  mov     rax, [rsi+8]
0x1800dd6fa  lea     r8, [rbp+57h+var_78]; struct WTL::CString *
0x1800dd6fe  lea     rdx, [rbp+57h+var_70]; struct DSFilter *
0x1800dd702  movsxd  rcx, dword ptr [rax+4]
0x1800dd706  add     rcx, 28h ; '('
0x1800dd70a  add     rcx, rsi; this
0x1800dd70d  call    ?AddFilter@DSGraph@@QEAAJAEAVDSFilter@@AEAVCString@WTL@@@Z; DSGraph::AddFilter(DSFilter &,WTL::CString &)
0x1800dd712  mov     ebx, eax
0x1800dd714  test    eax, eax
0x1800dd716  jns     short loc_1800DD725
0x1800dd718  lea     rcx, [rbp+57h+var_60]
0x1800dd71c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd721  mov     edi, ebx
0x1800dd723  jmp     short loc_1800DD763
0x1800dd725  mov     rax, [rsi+8]
0x1800dd729  lea     rdx, [rbp+57h+var_70]
0x1800dd72d  movsxd  rcx, dword ptr [rax+4]
0x1800dd731  add     rcx, 38h ; '8'
0x1800dd735  add     rcx, rsi
0x1800dd738  call    ?push_back@?$vector@VDSFilter@@V?$allocator@VDSFilter@@@std@@@std@@QEAAXAEBVDSFilter@@@Z; std::vector<DSFilter>::push_back(DSFilter const &)
0x1800dd73d  mov     rax, [rsi+8]
0x1800dd741  movsxd  rcx, dword ptr [rax+4]
0x1800dd745  mov     rax, [rcx+rsi+40h]
0x1800dd74a  sub     rax, [rcx+rsi+38h]
0x1800dd74f  lea     rcx, [rbp+57h+var_60]
0x1800dd753  sar     rax, 4
0x1800dd757  sub     eax, edi
0x1800dd759  mov     [rsi+30h], eax
0x1800dd75c  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd761  xor     edi, edi
0x1800dd763  lea     rcx, [rbp+57h+var_78]; this
0x1800dd767  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x1800dd76c  lea     rax, ??_7?$Forward_Sequence@V?$CComQIPtr@UIBaseFilter@@$1?IID_IBaseFilter@@3U_GUID@@B@ATL@@V?$CComQIPtr@UIEnumPins@@$1?IID_IEnumPins@@3U_GUID@@B@2@VDSPin@@UIBaseFilter@@UIEnumPins@@PEAUIPin@@V?$allocator@VDSPin@@@std@@@@6B@; const Forward_Sequence<ATL::CComQIPtr<IBaseFilter,&_GUID const IID_IBaseFilter>,ATL::CComQIPtr<IEnumPins,&_GUID const IID_IEnumPins>,DSPin,IBaseFilter,IEnumPins,IPin *,std::allocator<DSPin>>::`vftable'
0x1800dd773  lea     rcx, [rbp+57h+var_68]
0x1800dd777  mov     [rbp+57h+var_70], rax
0x1800dd77b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dd780  mov     eax, edi
0x1800dd782  mov     rcx, [rbp+57h+var_20]
0x1800dd786  xor     rcx, rsp; StackCookie
0x1800dd789  call    __security_check_cookie
0x1800dd78e  lea     r11, [rsp+0B0h+var_10]
0x1800dd796  mov     rbx, [r11+28h]
0x1800dd79a  mov     rsi, [r11+30h]
0x1800dd79e  mov     rsp, r11
0x1800dd7a1  pop     r14
0x1800dd7a3  pop     rdi
0x1800dd7a4  pop     rbp
0x1800dd7a5  retn
```
