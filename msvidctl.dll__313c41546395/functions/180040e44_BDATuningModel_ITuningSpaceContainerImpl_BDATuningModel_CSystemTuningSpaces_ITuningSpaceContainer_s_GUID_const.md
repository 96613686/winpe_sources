# BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::LoadCache(WTL::CString &)

- ea: `0x180040e44`
- end: `0x18004145d`
- name: `?LoadCache@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@QEAAJAEAVCString@WTL@@@Z`
- size: `1561`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003f8f8`
- `0x180042c4c`

## callees

- `0x180004740`
- `0x180004b48`
- `0x180006b38`
- `0x18000eee4`
- `0x18001d270`
- `0x180037610`
- `0x1800376cc`
- `0x180038294`
- `0x1800382d4`
- `0x1800385b4`
- `0x180039434`
- `0x18003978c`
- `0x18003db00`
- `0x18003e7f4`
- `0x180040e44`
- `0x18004186c`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800410e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800410e0`
- `ole32!CoTaskMemFree` at `0x18004123d`
- `ole32!CoTaskMemFree` at `0x18004123d`
- `ole32!CoCreateInstance` at `0x180040e96`
- `ole32!CoCreateInstance` at `0x180040e96`
- `OLEAUT32!__imp_SysFreeString` at `0x1800411f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800411f2`
- `OLEAUT32!__imp_SysStringLen` at `0x180041193`
- `OLEAUT32!__imp_SysStringLen` at `0x180041193`
- `OLEAUT32!__imp_VariantClear` at `0x18004122d`
- `OLEAUT32!__imp_VariantClear` at `0x1800412c6`
- `OLEAUT32!__imp_VariantClear` at `0x18004130d`
- `OLEAUT32!__imp_VariantClear` at `0x18004137b`
- `OLEAUT32!__imp_VariantClear` at `0x1800413c2`
- `OLEAUT32!__imp_VariantClear` at `0x18004140a`
- `OLEAUT32!__imp_VariantClear` at `0x18004122d`
- `OLEAUT32!__imp_VariantClear` at `0x1800412c6`
- `OLEAUT32!__imp_VariantClear` at `0x18004130d`
- `OLEAUT32!__imp_VariantClear` at `0x18004137b`
- `OLEAUT32!__imp_VariantClear` at `0x1800413c2`
- `OLEAUT32!__imp_VariantClear` at `0x18004140a`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800412a8`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800412a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::LoadCache(
        __int64 a1)
{
  __int64 v2; // rdi
  HRESULT Instance; // eax
  unsigned int v4; // r8d
  const unsigned __int16 *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  int v8; // eax
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // r8d
  const unsigned __int16 *v14; // r9
  unsigned int v15; // ebx
  char *v16; // r12
  unsigned __int64 v17; // rdx
  int v18; // edi
  unsigned int v19; // r8d
  const unsigned __int16 *v20; // r9
  unsigned int v21; // ebx
  unsigned int v22; // esi
  int v23; // r15d
  char *v24; // rdi
  const wchar_t **v25; // r14
  unsigned int v26; // eax
  __int64 v27; // rcx
  OLECHAR *v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // edi
  LONG lVal; // eax
  LONG v32; // edx
  int v33; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-F8h]
  int *v35; // [rsp+28h] [rbp-F0h]
  char **v36; // [rsp+38h] [rbp-E0h]
  __int64 v37; // [rsp+40h] [rbp-D8h] BYREF
  char v38[8]; // [rsp+48h] [rbp-D0h] BYREF
  VARIANTARG pvargDest; // [rsp+50h] [rbp-C8h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-B0h] BYREF
  int v41; // [rsp+70h] [rbp-A8h] BYREF
  wchar_t *EndPtr; // [rsp+78h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+80h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+A0h] [rbp-78h] BYREF
  ComException *v46; // [rsp+A8h] [rbp-70h] BYREF
  char v47[16]; // [rsp+B0h] [rbp-68h] BYREF
  char v48[16]; // [rsp+C0h] [rbp-58h] BYREF
  std::bad_alloc *v49; // [rsp+D0h] [rbp-48h] BYREF
  std::exception *v50; // [rsp+D8h] [rbp-40h] BYREF
  unsigned int v51; // [rsp+120h] [rbp+8h] BYREF
  unsigned int v52; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v53; // [rsp+138h] [rbp+20h] BYREF

  v2 = a1 + 128;
  WTL::CString::operator=((WTL::CString *)(a1 + 128));
  try
  {
    BDATuningModel::CAutoMutex::CAutoMutex((BDATuningModel::CAutoMutex *)v38, *(void **)(a1 + 32));
    Instance = CoCreateInstance(
                 &GUID_8a674b49_1f63_11d3_b64c_00c04f79498e,
                 0,
                 0x17u,
                 &GUID_8a674b48_1f63_11d3_b64c_00c04f79498e,
                 (LPVOID *)(a1 + 24));
    if ( Instance < 0 )
    {
      v6 = ATL::AtlSetErrorInfo2(
             &GUID_d02aac50_027e_11d3_9d8e_00c04f72d980,
             0xC0040530,
             v4,
             v5,
             &GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,
             Instance,
             hInstance,
             v36);
      BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
      return v6;
    }
    v8 = BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::OpenRootKeyAndBag(
           a1,
           v2,
           131097);
    if ( v8 < 0 )
    {
      v11 = ATL::AtlSetErrorInfo2(
              &GUID_d02aac50_027e_11d3_9d8e_00c04f72d980,
              0xC0040533,
              v9,
              v10,
              &GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,
              v8,
              hInstance,
              v36);
      BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
      return v11;
    }
    ATL::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>(
      &v37,
      *(_QWORD *)(a1 + 48));
    if ( !v37 )
    {
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
      BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
      return 2147549183LL;
    }
    BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::FlushCache(a1);
    v51 = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 48) + 40LL))(
            *(_QWORD *)(a1 + 48),
            &v51);
    if ( v12 < 0 )
    {
      v15 = ATL::AtlSetErrorInfo2(
              &GUID_d02aac50_027e_11d3_9d8e_00c04f72d980,
              0xC0040535,
              v13,
              v14,
              &GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,
              v12,
              hInstance,
              v36);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
      BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
      return v15;
    }
    v16 = (char *)operator new[](saturated_mul(v51, 0x28u));
    v53 = 0;
    v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *, unsigned int *))(**(_QWORD **)(a1 + 48) + 48LL))(
            *(_QWORD *)(a1 + 48),
            0,
            v51,
            v16,
            &v53);
    if ( v18 < 0 )
    {
      operator delete(v16, v17);
      v21 = ATL::AtlSetErrorInfo2(
              &GUID_d02aac50_027e_11d3_9d8e_00c04f72d980,
              0xC0040535,
              v19,
              v20,
              &GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,
              v18,
              hInstance,
              v36);
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
      BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
      return v21;
    }
    v22 = 0;
    v23 = 0;
    while ( v22 < v53 )
    {
      v24 = &v16[40 * v22];
      v25 = (const wchar_t **)(v24 + 16);
      if ( *((_WORD *)v24 + 2) == 13 )
      {
        EndPtr = 0;
        v52 = 0;
        v26 = wcstoul(*v25, &EndPtr, 10);
        if ( v26 - 1 > 0xFFFFFFFD || *EndPtr )
          v26 = v23 + 1;
        v52 = v26;
        memset(&pvarg, 0, sizeof(pvarg));
        pvarg.vt = 0;
        v41 = 0;
        v35 = &v41;
        ppv = (LPVOID *)&pvarg;
        if ( (*(int (__fastcall **)(_QWORD, __int64, char *))(**(_QWORD **)(a1 + 48) + 24LL))(
               *(_QWORD *)(a1 + 48),
               1,
               &v16[40 * v22]) >= 0 )
        {
          ATL::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>(
            &v43,
            pvarg.llVal);
          BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::GetUniqueName(
            v27,
            &pbstr,
            v43);
          v28 = pbstr;
          if ( pbstr )
          {
            if ( SysStringLen(pbstr) )
            {
              v29 = std::map<unsigned long,ATL::CComVariant>::_Try_emplace<unsigned long,>(a1 + 8, v47, &v52);
              ATL::CComVariant::InternalCopy((ATL::CComVariant *)(*(_QWORD *)v29 + 40LL), &pvarg);
              v30 = v52;
              *(_DWORD *)(*(_QWORD *)std::map<ATL::CComBSTR,unsigned long>::_Try_emplace<ATL::CComBSTR const &,>(
                                       a1 + 88,
                                       v48,
                                       &pbstr)
                        + 40LL) = v30;
            }
            v28 = pbstr;
          }
          SysFreeString(v28);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v43);
        }
        ++v23;
        if ( pvarg.vt == 4095 )
          pvarg.vt = 8;
        VariantClear(&pvarg);
      }
      CoTaskMemFree((LPVOID)*v25);
      ++v22;
    }
    operator delete(v16, v17);
    memset(&pvargDest, 0, sizeof(pvargDest));
    pvargDest.vt = 19;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD, LPVOID *, int *))(*(_QWORD *)v37 + 24LL))(
           v37,
           L"Max Count",
           &pvargDest,
           0,
           ppv,
           v35) < 0 )
    {
      if ( *(_QWORD *)(a1 + 16) > 0xFFFFFFFF )
      {
        if ( pvargDest.vt == 4095 )
          pvargDest.vt = 8;
        goto LABEL_45;
      }
      v33 = 32;
      if ( *(_DWORD *)(a1 + 16) > 0x20u )
        v33 = *(_DWORD *)(a1 + 16);
      *(_DWORD *)(a1 + 40) = v33;
    }
    else
    {
      if ( pvargDest.vt != 19 && VariantChangeType(&pvargDest, &pvargDest, 0, 0x13u) < 0 )
      {
        if ( pvargDest.vt == 4095 )
          pvargDest.vt = 8;
LABEL_45:
        VariantClear(&pvargDest);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
        BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
        return 2147549183LL;
      }
      if ( *(_QWORD *)(a1 + 16) > 0xFFFFFFFF )
      {
        if ( pvargDest.vt == 4095 )
          pvargDest.vt = 8;
        goto LABEL_45;
      }
      lVal = pvargDest.lVal;
      v32 = pvargDest.lVal;
      if ( pvargDest.lVal < *(_DWORD *)(a1 + 16) )
        v32 = *(_DWORD *)(a1 + 16);
      *(_DWORD *)(a1 + 40) = v32;
      if ( v32 != lVal && (*(int (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1) < 0 )
      {
        if ( pvargDest.vt == 4095 )
          pvargDest.vt = 8;
        goto LABEL_45;
      }
    }
    if ( pvargDest.vt == 4095 )
      pvargDest.vt = 8;
    VariantClear(&pvargDest);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v37);
    BDATuningModel::CAutoMutex::~CAutoMutex((BDATuningModel::CAutoMutex *)v38);
    result = 0;
  }
  catch ( long v45 )
  {
    return v45;
  }
  catch ( ComException *v46 )
  {
    return *(unsigned int *)v46;
  }
  catch ( std::bad_alloc *v49 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v50 )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180040e44  push    rbx
0x180040e46  push    rsi
0x180040e47  push    rdi
0x180040e48  push    r12
0x180040e4a  push    r13
0x180040e4c  push    r14
0x180040e4e  push    r15
0x180040e50  sub     rsp, 0E0h
0x180040e57  mov     rbx, rcx
0x180040e5a  lea     rdi, [rcx+80h]
0x180040e61  mov     rcx, rdi; this
0x180040e64  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x180040e69  nop
0x180040e6a  mov     rdx, [rbx+20h]; void *
0x180040e6e  lea     rcx, [rsp+118h+var_D0]; this
0x180040e73  call    ??0CAutoMutex@BDATuningModel@@QEAA@PEAX@Z; BDATuningModel::CAutoMutex::CAutoMutex(void *)
0x180040e78  nop
0x180040e79  lea     rax, [rbx+18h]
0x180040e7d  mov     [rsp+118h+ppv], rax; ppv
0x180040e82  lea     r9, _GUID_8a674b48_1f63_11d3_b64c_00c04f79498e; riid
0x180040e89  xor     edx, edx; pUnkOuter
0x180040e8b  lea     r8d, [rdx+17h]; dwClsContext
0x180040e8f  lea     rcx, _GUID_8a674b49_1f63_11d3_b64c_00c04f79498e; rclsid
0x180040e96  call    cs:__imp_CoCreateInstance
0x180040e9c  xor     r13d, r13d
0x180040e9f  test    eax, eax
0x180040ea1  jns     short loc_180040EE3
0x180040ea3  mov     rcx, cs:hInstance
0x180040eaa  mov     [rsp+118h+var_E8], rcx; HINSTANCE
0x180040eaf  mov     [rsp+118h+var_F0], eax; int
0x180040eb3  lea     rax, _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980
0x180040eba  mov     [rsp+118h+ppv], rax; struct _GUID *
0x180040ebf  mov     edx, 0C0040530h; dwMessageId
0x180040ec4  lea     rcx, _GUID_d02aac50_027e_11d3_9d8e_00c04f72d980; clsid
0x180040ecb  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180040ed0  mov     ebx, eax
0x180040ed2  lea     rcx, [rsp+118h+var_D0]; this
0x180040ed7  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x180040edc  mov     eax, ebx
0x180040ede  jmp     loc_180041449
0x180040ee3  mov     r8d, 20019h
0x180040ee9  mov     rdx, rdi
0x180040eec  mov     rcx, rbx
0x180040eef  call    ?OpenRootKeyAndBag@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@IEAAJAEAVCString@WTL@@K@Z; BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::OpenRootKeyAndBag(WTL::CString &,ulong)
0x180040ef4  test    eax, eax
0x180040ef6  jns     short loc_180040F38
0x180040ef8  mov     rcx, cs:hInstance
0x180040eff  mov     [rsp+118h+var_E8], rcx; HINSTANCE
0x180040f04  mov     [rsp+118h+var_F0], eax; int
0x180040f08  lea     rax, _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980
0x180040f0f  mov     [rsp+118h+ppv], rax; struct _GUID *
0x180040f14  mov     edx, 0C0040533h; dwMessageId
0x180040f19  lea     rcx, _GUID_d02aac50_027e_11d3_9d8e_00c04f72d980; clsid
0x180040f20  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180040f25  mov     ebx, eax
0x180040f27  lea     rcx, [rsp+118h+var_D0]; this
0x180040f2c  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x180040f31  mov     eax, ebx
0x180040f33  jmp     loc_180041449
0x180040f38  mov     rdx, [rbx+30h]
0x180040f3c  lea     rcx, [rsp+118h+var_D8]
0x180040f41  call    ??0?$CComQIPtr@UIPropertyBag@@$1?_GUID_55272a00_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPropertyBag,&__s_GUID const _GUID_55272a00_42cb_11ce_8135_00aa004bb851>(IUnknown *)
0x180040f46  nop
0x180040f47  cmp     [rsp+118h+var_D8], r13
0x180040f4c  jnz     short loc_180040F6D
0x180040f4e  lea     rcx, [rsp+118h+var_D8]
0x180040f53  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180040f58  nop
0x180040f59  lea     rcx, [rsp+118h+var_D0]; this
0x180040f5e  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x180040f63  mov     eax, 8000FFFFh
0x180040f68  jmp     loc_180041449
0x180040f6d  mov     rcx, rbx
0x180040f70  call    ?FlushCache@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@QEAAXXZ; BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::FlushCache(void)
0x180040f75  mov     [rsp+118h+arg_0], r13d
0x180040f7d  mov     rcx, [rbx+30h]
0x180040f81  mov     rax, [rcx]
0x180040f84  lea     rdx, [rsp+118h+arg_0]
0x180040f8c  mov     rax, [rax+28h]
0x180040f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f95  test    eax, eax
0x180040f97  jns     short loc_180040FE4
0x180040f99  mov     rcx, cs:hInstance
0x180040fa0  mov     [rsp+118h+var_E8], rcx; HINSTANCE
0x180040fa5  mov     [rsp+118h+var_F0], eax; int
0x180040fa9  lea     rax, _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980
0x180040fb0  mov     [rsp+118h+ppv], rax; struct _GUID *
0x180040fb5  mov     edx, 0C0040535h; dwMessageId
0x180040fba  lea     rcx, _GUID_d02aac50_027e_11d3_9d8e_00c04f72d980; clsid
0x180040fc1  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180040fc6  mov     ebx, eax
0x180040fc8  lea     rcx, [rsp+118h+var_D8]
0x180040fcd  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180040fd2  nop
0x180040fd3  lea     rcx, [rsp+118h+var_D0]; this
0x180040fd8  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x180040fdd  mov     eax, ebx
0x180040fdf  jmp     loc_180041449
0x180040fe4  mov     ecx, [rsp+118h+arg_0]
0x180040feb  mov     eax, 28h ; '('
0x180040ff0  mul     rcx
0x180040ff3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180040ffa  cmovb   rax, rcx
0x180040ffe  mov     rcx, rax; unsigned __int64
0x180041001  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180041006  mov     r12, rax
0x180041009  mov     [rsp+118h+arg_18], r13d
0x180041011  mov     rcx, [rbx+30h]
0x180041015  mov     rax, [rcx]
0x180041018  lea     rdx, [rsp+118h+arg_18]
0x180041020  mov     [rsp+118h+ppv], rdx
0x180041025  mov     r9, r12
0x180041028  mov     r8d, [rsp+118h+arg_0]
0x180041030  xor     edx, edx
0x180041032  mov     rax, [rax+30h]
0x180041036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004103b  mov     edi, eax
0x18004103d  test    eax, eax
0x18004103f  jns     short loc_180041094
0x180041041  mov     rcx, r12; void *
0x180041044  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180041049  mov     rcx, cs:hInstance
0x180041050  mov     [rsp+118h+var_E8], rcx; HINSTANCE
0x180041055  mov     [rsp+118h+var_F0], edi; int
0x180041059  lea     rax, _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980
0x180041060  mov     [rsp+118h+ppv], rax; struct _GUID *
0x180041065  mov     edx, 0C0040535h; dwMessageId
0x18004106a  lea     rcx, _GUID_d02aac50_027e_11d3_9d8e_00c04f72d980; clsid
0x180041071  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180041076  mov     ebx, eax
0x180041078  lea     rcx, [rsp+118h+var_D8]
0x18004107d  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180041082  nop
0x180041083  lea     rcx, [rsp+118h+var_D0]; this
0x180041088  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x18004108d  mov     eax, ebx
0x18004108f  jmp     loc_180041449
0x180041094  mov     esi, r13d
0x180041097  mov     r15d, r13d
0x18004109a  mov     edi, 0FFFh
0x18004109f  cmp     esi, [rsp+118h+arg_18]
0x1800410a6  jnb     loc_18004124A
0x1800410ac  mov     eax, esi
0x1800410ae  lea     rcx, [rax+rax*4]
0x1800410b2  lea     rdi, [r12+rcx*8]
0x1800410b6  lea     r14, [rdi+10h]
0x1800410ba  cmp     word ptr [rdi+4], 0Dh
0x1800410bf  jnz     loc_180041235
0x1800410c5  mov     [rsp+118h+EndPtr], r13
0x1800410ca  mov     [rsp+118h+arg_10], r13d
0x1800410d2  mov     r8d, 0Ah; Radix
0x1800410d8  lea     rdx, [rsp+118h+EndPtr]; EndPtr
0x1800410dd  mov     rcx, [r14]; String
0x1800410e0  call    cs:__imp_wcstoul
0x1800410e6  lea     ecx, [rax-1]
0x1800410e9  cmp     ecx, 0FFFFFFFDh
0x1800410ec  ja      short loc_1800410F9
0x1800410ee  mov     rcx, [rsp+118h+EndPtr]
0x1800410f3  cmp     [rcx], r13w
0x1800410f7  jz      short loc_1800410FD
0x1800410f9  lea     eax, [r15+1]
0x1800410fd  mov     [rsp+118h+arg_10], eax
0x180041104  xorps   xmm0, xmm0
0x180041107  xor     eax, eax
0x180041109  movups  xmmword ptr [rsp+118h+pvarg], xmm0
0x180041111  mov     qword ptr [rsp+118h+pvarg+10h], rax
0x180041119  mov     word ptr [rsp+118h+pvarg], r13w
0x180041122  mov     [rsp+118h+var_A8], r13d
0x180041127  mov     rcx, [rbx+30h]
0x18004112b  mov     rax, [rcx]
0x18004112e  lea     rdx, [rsp+118h+var_A8]
0x180041133  mov     qword ptr [rsp+118h+var_F0], rdx
0x180041138  lea     rdx, [rsp+118h+pvarg]
0x180041140  mov     [rsp+118h+ppv], rdx
0x180041145  xor     r9d, r9d
0x180041148  mov     r8, rdi
0x18004114b  lea     edx, [r9+1]
0x18004114f  mov     rax, [rax+18h]
0x180041153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041158  test    eax, eax
0x18004115a  js      loc_180041206
0x180041160  mov     rdx, qword ptr [rsp+118h+pvarg+8]
0x180041168  lea     rcx, [rsp+118h+var_98]
0x180041170  call    ??0?$CComQIPtr@UITuningSpace@@$1?_GUID_061c6e30_e622_11d2_9493_00c04f72d980@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>::CComQIPtr<ITuningSpace,&__s_GUID const _GUID_061c6e30_e622_11d2_9493_00c04f72d980>(IUnknown *)
0x180041175  nop
0x180041176  mov     r8, [rsp+118h+var_98]
0x18004117e  lea     rdx, [rsp+118h+pbstr]
0x180041183  call    ?GetUniqueName@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@IEAA?AVCComBSTR@ATL@@PEAUITuningSpace@@@Z; BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::GetUniqueName(ITuningSpace *)
0x180041188  nop
0x180041189  mov     rcx, [rsp+118h+pbstr]; pbstr
0x18004118e  test    rcx, rcx
0x180041191  jz      short loc_1800411F2
0x180041193  call    cs:__imp_SysStringLen
0x180041199  test    eax, eax
0x18004119b  jz      short loc_1800411ED
0x18004119d  lea     rcx, [rbx+8]
0x1800411a1  lea     r8, [rsp+118h+arg_10]
0x1800411a9  lea     rdx, [rsp+118h+var_68]
0x1800411b1  call    ??$_Try_emplace@K$$V@?$map@KVCComVariant@ATL@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKVCComVariant@ATL@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKVCComVariant@ATL@@@std@@PEAX@std@@_N@1@$$QEAK@Z; std::map<ulong,ATL::CComVariant>::_Try_emplace<ulong,>(ulong &&)
0x1800411b6  mov     rcx, [rax]
0x1800411b9  add     rcx, 28h ; '('; this
0x1800411bd  lea     rdx, [rsp+118h+pvarg]; struct tagVARIANT *
0x1800411c5  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x1800411ca  mov     edi, [rsp+118h+arg_10]
0x1800411d1  lea     rcx, [rbx+58h]
0x1800411d5  lea     r8, [rsp+118h+pbstr]
0x1800411da  lea     rdx, [rsp+118h+var_58]
0x1800411e2  call    ??$_Try_emplace@AEBVCComBSTR@ATL@@$$V@?$map@VCComBSTR@ATL@@KU?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@K@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@K@std@@PEAX@std@@_N@1@AEBVCComBSTR@ATL@@@Z; std::map<ATL::CComBSTR,ulong>::_Try_emplace<ATL::CComBSTR const &,>(ATL::CComBSTR const &)
0x1800411e7  mov     rax, [rax]
0x1800411ea  mov     [rax+28h], edi
0x1800411ed  mov     rcx, [rsp+118h+pbstr]; bstrString
0x1800411f2  call    cs:__imp_SysFreeString
0x1800411f8  nop
0x1800411f9  lea     rcx, [rsp+118h+var_98]
0x180041201  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180041206  inc     r15d
0x180041209  mov     edi, 0FFFh
0x18004120e  cmp     word ptr [rsp+118h+pvarg], di
0x180041216  jnz     short loc_180041225
0x180041218  mov     eax, 8
0x18004121d  mov     word ptr [rsp+118h+pvarg], ax
0x180041225  lea     rcx, [rsp+118h+pvarg]; pvarg
0x18004122d  call    cs:__imp_VariantClear
0x180041233  jmp     short loc_18004123A
0x180041235  mov     edi, 0FFFh
0x18004123a  mov     rcx, [r14]; pv
0x18004123d  call    cs:__imp_CoTaskMemFree
0x180041243  inc     esi
0x180041245  jmp     loc_18004109F
0x18004124a  mov     rcx, r12; void *
0x18004124d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180041252  xorps   xmm0, xmm0
0x180041255  xor     eax, eax
0x180041257  movups  xmmword ptr [rsp+118h+pvargDest], xmm0
0x18004125c  mov     qword ptr [rsp+118h+pvargDest+10h], rax
0x180041261  lea     esi, [rax+13h]
0x180041264  mov     word ptr [rsp+118h+pvargDest], si
0x180041269  mov     rcx, [rsp+118h+var_D8]
0x18004126e  mov     rax, [rcx]
0x180041271  xor     r9d, r9d
0x180041274  lea     r8, [rsp+118h+pvargDest]
0x180041279  lea     rdx, aMaxCount; "Max Count"
0x180041280  mov     rax, [rax+18h]
0x180041284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041289  test    eax, eax
0x18004128b  js      loc_1800413A1
0x180041291  cmp     word ptr [rsp+118h+pvargDest], si
0x180041296  jz      short loc_1800412EC
0x180041298  mov     r9d, esi; vt
0x18004129b  xor     r8d, r8d; wFlags
0x18004129e  lea     rdx, [rsp+118h+pvargDest]; pvarSrc
0x1800412a3  lea     rcx, [rsp+118h+pvargDest]; pvargDest
0x1800412a8  call    cs:__imp_VariantChangeType
0x1800412ae  test    eax, eax
0x1800412b0  jns     short loc_1800412EC
0x1800412b2  cmp     word ptr [rsp+118h+pvargDest], di
0x1800412b7  jnz     short loc_1800412C1
0x1800412b9  lea     eax, [rsi-0Bh]
0x1800412bc  mov     word ptr [rsp+118h+pvargDest], ax
0x1800412c1  lea     rcx, [rsp+118h+pvargDest]; pvarg
0x1800412c6  call    cs:__imp_VariantClear
0x1800412cc  nop
0x1800412cd  lea     rcx, [rsp+118h+var_D8]
0x1800412d2  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800412d7  nop
0x1800412d8  lea     rcx, [rsp+118h+var_D0]; this
0x1800412dd  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x1800412e2  mov     eax, 8000FFFFh
0x1800412e7  jmp     loc_180041449
0x1800412ec  mov     eax, 0FFFFFFFFh
0x1800412f1  cmp     [rbx+10h], rax
0x1800412f5  jbe     short loc_180041333
0x1800412f7  cmp     word ptr [rsp+118h+pvargDest], di
0x1800412fc  jnz     short loc_180041308
0x1800412fe  mov     eax, 8
0x180041303  mov     word ptr [rsp+118h+pvargDest], ax
0x180041308  lea     rcx, [rsp+118h+pvargDest]; pvarg
0x18004130d  call    cs:__imp_VariantClear
0x180041313  nop
0x180041314  lea     rcx, [rsp+118h+var_D8]
0x180041319  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18004131e  nop
0x18004131f  lea     rcx, [rsp+118h+var_D0]; this
0x180041324  call    ??1CAutoMutex@BDATuningModel@@QEAA@XZ; BDATuningModel::CAutoMutex::~CAutoMutex(void)
0x180041329  mov     eax, 8000FFFFh
0x18004132e  jmp     loc_180041449
0x180041333  mov     eax, dword ptr [rsp+118h+pvargDest+8]
0x180041337  mov     edx, eax
0x180041339  cmp     eax, [rbx+10h]
0x18004133c  cmovb   edx, [rbx+10h]
0x180041340  mov     [rbx+28h], edx
0x180041343  cmp     edx, eax
0x180041345  jz      loc_1800413F4
0x18004134b  mov     rax, [rbx]
0x18004134e  mov     rcx, rbx
0x180041351  mov     rax, [rax+98h]
0x180041358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004135d  test    eax, eax
0x18004135f  jns     loc_1800413F4
0x180041365  cmp     word ptr [rsp+118h+pvargDest], di
  ... truncated ...
```
