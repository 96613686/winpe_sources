# TdhpFindMatchClassFromWBEM(IWbemServices *,ulong,_GUID const *,uchar,ulong *,_TRACE_EVENT_INFO * * *,ulong *)

- ea: `0x180014ff4`
- end: `0x1800159a4`
- name: `?TdhpFindMatchClassFromWBEM@@YAKPEAUIWbemServices@@KPEBU_GUID@@EPEAKPEAPEAPEAU_TRACE_EVENT_INFO@@2@Z`
- size: `2480`
- prototype: `__int64 __fastcall(struct IWbemServices *, unsigned int, const struct _GUID *, unsigned __int8, unsigned int *, struct _TRACE_EVENT_INFO ***, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fb0`
- `0x180018198`

## callees

- `0x180012fd0`
- `0x18001443c`
- `0x180014fd8`
- `0x180014ff4`
- `0x1800159ac`
- `0x180017d74`
- `0x180018258`
- `0x18001c7d0`
- `0x18001cfb0`
- `0x18001d1d0`
- `0x1800207c0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015650`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015650`
- `OLEAUT32!__imp_SysAllocString` at `0x180015121`
- `OLEAUT32!__imp_SysAllocString` at `0x180015121`
- `OLEAUT32!__imp_SysFreeString` at `0x1800158c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800158c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800153a1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800153a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800152c0`
- `OLEAUT32!__imp_VariantClear` at `0x180015349`
- `OLEAUT32!__imp_VariantClear` at `0x180015367`
- `OLEAUT32!__imp_VariantClear` at `0x180015441`
- `OLEAUT32!__imp_VariantClear` at `0x180015567`
- `OLEAUT32!__imp_VariantClear` at `0x1800155f1`
- `OLEAUT32!__imp_VariantClear` at `0x180015675`
- `OLEAUT32!__imp_VariantClear` at `0x1800158da`
- `OLEAUT32!__imp_VariantClear` at `0x1800158ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800158fe`
- `OLEAUT32!__imp_VariantClear` at `0x1800152c0`
- `OLEAUT32!__imp_VariantClear` at `0x180015349`
- `OLEAUT32!__imp_VariantClear` at `0x180015367`
- `OLEAUT32!__imp_VariantClear` at `0x180015441`
- `OLEAUT32!__imp_VariantClear` at `0x180015567`
- `OLEAUT32!__imp_VariantClear` at `0x1800155f1`
- `OLEAUT32!__imp_VariantClear` at `0x180015675`
- `OLEAUT32!__imp_VariantClear` at `0x1800158da`
- `OLEAUT32!__imp_VariantClear` at `0x1800158ec`
- `OLEAUT32!__imp_VariantClear` at `0x1800158fe`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800156b5`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800156b5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015936`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180015936`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TdhpFindMatchClassFromWBEM(
        struct IWbemServices *a1,
        unsigned int a2,
        const struct _GUID *a3,
        unsigned __int8 a4,
        unsigned int *a5,
        struct _TRACE_EVENT_INFO ***a6,
        unsigned int *a7)
{
  __int64 *v8; // rbx
  OLECHAR *v9; // r15
  unsigned int PropertiesFromWBEM; // edi
  HRESULT (__stdcall *CreateClassEnum)(IWbemServices *, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // rbx
  int v12; // ebx
  __int64 v13; // rdx
  char v14; // si
  char v15; // r13
  __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // rbx
  int (__fastcall *v23)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD); // r14
  __int64 v24; // rcx
  BSTR bstrVal; // r8
  __int64 v26; // rdx
  OLECHAR *v27; // rax
  OLECHAR v28; // r9
  OLECHAR *v29; // rcx
  __int64 *v30; // rbx
  int (__fastcall *v31)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD); // r14
  int v32; // r11d
  struct IWbemServicesVtbl *lpVtbl; // rax
  int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // ebx
  __int64 v38; // rdx
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, __int64 *); // r14
  __int64 v41; // rdx
  int v42; // ebx
  __int64 v43; // rdx
  __int64 v44; // rbx
  int (__fastcall *v45)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD); // r14
  __int64 v46; // rcx
  BSTR v47; // r8
  __int64 v48; // rdx
  wchar_t *v49; // rax
  wchar_t v50; // r9
  wchar_t *v51; // rcx
  unsigned __int64 v52; // r11
  __int64 v53; // rbx
  int (__fastcall *v54)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD); // r14
  SHORT iVal; // bx
  __int64 v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v59; // [rsp+70h] [rbp-90h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v63; // [rsp+90h] [rbp-70h]
  __int64 *v64; // [rsp+A0h] [rbp-60h] BYREF
  int v65; // [rsp+A8h] [rbp-58h] BYREF
  int v66; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v67; // [rsp+B0h] [rbp-50h]
  unsigned int v68; // [rsp+B4h] [rbp-4Ch]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v70; // [rsp+D0h] [rbp-30h] BYREF
  struct IWbemServices *v71; // [rsp+E8h] [rbp-18h] BYREF
  char v72; // [rsp+F0h] [rbp-10h]
  VARIANTARG pvargDest; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int *v74; // [rsp+110h] [rbp+10h]
  _QWORD *v75; // [rsp+118h] [rbp+18h]
  _DWORD *v76; // [rsp+120h] [rbp+20h]
  const struct _GUID *v77; // [rsp+128h] [rbp+28h]
  OLECHAR *v78; // [rsp+130h] [rbp+30h] BYREF
  wchar_t v79[128]; // [rsp+140h] [rbp+40h] BYREF
  __int16 v80; // [rsp+240h] [rbp+140h] BYREF
  char v81[72]; // [rsp+242h] [rbp+142h] BYREF
  int v82; // [rsp+28Ah] [rbp+18Ah]
  _BYTE v83[256]; // [rsp+340h] [rbp+240h] BYREF
  wchar_t v84[128]; // [rsp+440h] [rbp+340h] BYREF
  wchar_t v85[1024]; // [rsp+540h] [rbp+440h] BYREF

  v77 = a3;
  v68 = a2;
  v76 = a5;
  v75 = a6;
  v74 = a7;
  v71 = 0;
  v72 = 0;
  v8 = 0;
  v64 = 0;
  memset(&v70, 0, sizeof(v70));
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pvargDest, 0, sizeof(pvargDest));
  v65 = 0;
  v66 = 0;
  v9 = 0;
  v78 = 0;
  if ( !a5 || !a7 )
  {
    utl::unique_ptr<wchar_t [0],tlx::sysfreestring_delete>::~unique_ptr<wchar_t [0],tlx::sysfreestring_delete>(&v78);
    tlx::unique_variant::reset((tlx::unique_variant *)&pvargDest);
    tlx::unique_variant::reset((tlx::unique_variant *)&pvarg);
    tlx::unique_variant::reset((tlx::unique_variant *)&v70);
    std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v64);
    WBEM_SERVICE::~WBEM_SERVICE((WBEM_SERVICE *)&v71);
    return 87;
  }
  *a5 = 0;
  v85[0] = 0;
  v80 = 123;
  tlx::guid_to_string_upper<unsigned short>(v81, a3);
  v82 = 125;
  if ( a1 )
    goto LABEL_8;
  PropertiesFromWBEM = WBEM_SERVICE::Connect((WBEM_SERVICE *)&v71, 0);
  if ( !PropertiesFromWBEM )
  {
    if ( !v71 )
    {
      PropertiesFromWBEM = 4208;
      goto LABEL_113;
    }
    a1 = v71;
    v8 = v64;
LABEL_8:
    v64 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
    v9 = SysAllocString(L"EventTrace");
    v78 = v9;
    if ( v9 )
    {
      PropertiesFromWBEM = 1168;
      CreateClassEnum = a1->lpVtbl->CreateClassEnum;
      v62 = 0;
      v63 = (__int64 *)&v64;
      v64 = 0;
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64, _QWORD, __int64 *))CreateClassEnum)(
              a1,
              v9,
              131073,
              0,
              &v62);
      if ( v62 )
      {
        v13 = *v63;
        *v63 = v62;
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      if ( v12 >= 0 )
      {
        v67 = 0;
        v14 = 1;
        v65 = 1;
        v15 = 0;
        while ( 1 )
        {
          v59 = 0;
          v16 = *v64;
          v62 = 0;
          v63 = (__int64 *)&v59;
          v59 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *, int *))(v16 + 32))(
                  v64,
                  0xFFFFFFFFLL,
                  1,
                  &v62,
                  &v65);
          if ( v62 )
          {
            v18 = *v63;
            *v63 = v62;
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          if ( v17 < 0 )
          {
            if ( v59 )
              (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
            goto LABEL_113;
          }
          if ( !v65 )
            break;
          if ( v65 != 1 )
            goto LABEL_100;
          v58 = 0;
          v19 = *v59;
          v62 = 0;
          v63 = &v58;
          v58 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 24))(v59, &v62);
          if ( v62 )
          {
            v21 = *v63;
            *v63 = v62;
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          if ( v20 < 0 )
          {
            if ( v58 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
            if ( v59 )
              (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
            goto LABEL_113;
          }
          v22 = v58;
          v23 = *(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v58 + 24LL);
          if ( pvarg.vt )
            VariantClear(&pvarg);
          if ( v23(v22, L"Guid", 0, &pvarg, 0) < 0 )
            goto LABEL_99;
          v24 = 2147483646;
          bstrVal = pvarg.bstrVal;
          v26 = 128;
          v27 = (OLECHAR *)v83;
          do
          {
            if ( !v24 )
              break;
            v28 = *bstrVal;
            if ( !*bstrVal )
              break;
            ++bstrVal;
            *v27++ = v28;
            --v24;
            --v26;
          }
          while ( v26 );
          v29 = v27 - 1;
          if ( v26 )
            v29 = v27;
          *v29 = 0;
          if ( !v26 )
            goto LABEL_99;
          if ( pvarg.vt )
            VariantClear(&pvarg);
          v30 = v59;
          v31 = *(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*v59 + 32);
          if ( v70.vt )
            VariantClear(&v70);
          if ( v31(v30, L"__CLASS", 0, &v70, 0, 0) < 0 )
            goto LABEL_99;
          if ( SysStringLen(v70.bstrVal) )
          {
            if ( (int)StringCchCopyW(v85, 0x400u, v70.bstrVal) < 0 )
              goto LABEL_99;
            v67 = 2 * v32 + 2;
          }
          lpVtbl = a1->lpVtbl;
          v62 = 0;
          v63 = (__int64 *)&v61;
          v61 = 0;
          v34 = ((__int64 (__fastcall *)(struct IWbemServices *, LONGLONG, __int64, _QWORD, __int64 *))lpVtbl->CreateClassEnum)(
                  a1,
                  v70.llVal,
                  131073,
                  0,
                  &v62);
          if ( v62 )
          {
            v35 = *v63;
            *v63 = v62;
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          if ( v70.vt )
            VariantClear(&v70);
          if ( v34 < 0 )
          {
LABEL_98:
            std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v61);
LABEL_99:
            std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v58);
LABEL_100:
            std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v59);
            goto LABEL_113;
          }
          v66 = 1;
          while ( 1 )
          {
            v60 = 0;
            v36 = *v61;
            v62 = 0;
            v63 = &v60;
            v60 = 0;
            v37 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *, int *))(v36 + 32))(
                    v61,
                    0xFFFFFFFFLL,
                    1,
                    &v62,
                    &v66);
            if ( v62 )
            {
              v38 = *v63;
              *v63 = v62;
              if ( v38 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            }
            if ( v37 < 0 )
            {
LABEL_97:
              std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v60);
              goto LABEL_98;
            }
            if ( !v66 )
              break;
            if ( v66 != 1 )
              goto LABEL_97;
            v39 = v60;
            v40 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 24LL);
            v62 = 0;
            v63 = &v58;
            v41 = v58;
            v58 = 0;
            if ( v41 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
            v42 = v40(v39, &v62);
            if ( v62 )
            {
              v43 = *v63;
              *v63 = v62;
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
            if ( v42 < 0 )
              goto LABEL_97;
            v44 = v58;
            v45 = *(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v58 + 24LL);
            if ( pvarg.vt )
              VariantClear(&pvarg);
            if ( v45(v44, L"Guid", 0, &pvarg, 0) < 0 )
              goto LABEL_97;
            v46 = 2147483646;
            v47 = pvarg.bstrVal;
            v48 = 128;
            v49 = v79;
            do
            {
              if ( !v46 )
                break;
              v50 = *v47;
              if ( !*v47 )
                break;
              ++v47;
              *v49++ = v50;
              --v46;
              --v48;
            }
            while ( v48 );
            v51 = v49 - 1;
            if ( v48 )
              v51 = v49;
            *v51 = 0;
            if ( !v48 )
              goto LABEL_97;
            if ( pvarg.vt )
              VariantClear(&pvarg);
            if ( v79[0] != 123
              && ((int)StringCchCopyW(v84, 0x80u, v79) < 0 || (int)StringCchPrintfW(v79, v52, L"{%ws}", v84) < 0) )
            {
              goto LABEL_97;
            }
            if ( !(unsigned int)_o__wcsicmp(&v80, v79) )
            {
              v15 = 1;
              v53 = v58;
              v54 = *(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))(*(_QWORD *)v58 + 24LL);
              if ( pvargDest.vt )
                VariantClear(&pvargDest);
              if ( v54(v53, L"EventVersion", 0, &pvargDest, 0) < 0 )
              {
                PropertiesFromWBEM = TdhpGetPropertiesFromWBEM(
                                       v68,
                                       (__int64)v83,
                                       (__int64)v85,
                                       v67,
                                       (__int64)a1,
                                       v60,
                                       (__int64)v77,
                                       a4,
                                       v76,
                                       v75,
                                       v74);
                if ( v60 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                goto LABEL_96;
              }
              VariantChangeType(&pvargDest, &pvargDest, 0, 2u);
              iVal = pvargDest.iVal;
              tlx::unique_variant::reset((tlx::unique_variant *)&pvargDest);
              if ( a4 == iVal )
              {
                PropertiesFromWBEM = TdhpGetPropertiesFromWBEM(
                                       v68,
                                       (__int64)v83,
                                       (__int64)v85,
                                       v67,
                                       (__int64)a1,
                                       v60,
                                       (__int64)v77,
                                       a4,
                                       v76,
                                       v75,
                                       v74);
                std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v60);
LABEL_96:
                std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v61);
                std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v58);
                goto LABEL_107;
              }
            }
            std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v60);
          }
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          if ( v61 )
            (*(void (__fastcall **)(__int64 *))(*v61 + 16))(v61);
          if ( v58 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          if ( v59 )
            (*(void (__fastcall **)(__int64 *))(*v59 + 16))(v59);
        }
        v14 = 0;
LABEL_107:
        std::unique_ptr<IUnknown,XmlReader::ReleaseDelete>::~unique_ptr<IUnknown,XmlReader::ReleaseDelete>(&v59);
        if ( !v14 )
          PropertiesFromWBEM = (v15 != 0) - 1073217792;
      }
    }
    else
    {
      PropertiesFromWBEM = 8;
    }
  }
LABEL_113:
  if ( v9 )
    SysFreeString(v9);
  if ( pvargDest.vt )
    VariantClear(&pvargDest);
  if ( pvarg.vt )
    VariantClear(&pvarg);
  if ( v70.vt )
    VariantClear(&v70);
  if ( v64 )
    (*(void (__fastcall **)(__int64 *))(*v64 + 16))(v64);
  if ( v71 )
    ((void (__fastcall *)(struct IWbemServices *))v71->lpVtbl->Release)(v71);
  if ( v72 )
    CoUninitialize();
  return PropertiesFromWBEM;
}

```

## disassembly

```asm
0x180014ff4  push    rbp
0x180014ff6  push    rbx
0x180014ff7  push    rsi
0x180014ff8  push    rdi
0x180014ff9  push    r12
0x180014ffb  push    r13
0x180014ffd  push    r14
0x180014fff  push    r15
0x180015001  lea     rbp, [rsp-0C58h]
0x180015009  sub     rsp, 0D58h
0x180015010  mov     rax, cs:__security_cookie
0x180015017  xor     rax, rsp
0x18001501a  mov     [rbp+0C90h+var_50], rax
0x180015021  mov     [rsp+0D90h+var_D30], r9b
0x180015026  mov     [rbp+0C90h+var_C68], r8
0x18001502a  mov     [rbp+0C90h+var_CDC], edx
0x18001502d  mov     r12, rcx
0x180015030  mov     rax, [rbp+0C90h+arg_20]
0x180015037  mov     [rbp+0C90h+var_C70], rax
0x18001503b  mov     rcx, [rbp+0C90h+arg_28]
0x180015042  mov     [rbp+0C90h+var_C78], rcx
0x180015046  mov     rcx, [rbp+0C90h+arg_30]
0x18001504d  mov     [rbp+0C90h+var_C80], rcx
0x180015051  xor     r14d, r14d
0x180015054  mov     [rbp+0C90h+var_CA8], r14
0x180015058  mov     [rbp+0C90h+var_CA0], r14b
0x18001505c  mov     ebx, r14d
0x18001505f  mov     [rbp+0C90h+var_CF0], rbx
0x180015063  xorps   xmm0, xmm0
0x180015066  xor     edx, edx
0x180015068  movups  xmmword ptr [rbp+0C90h+var_CC0], xmm0
0x18001506c  mov     qword ptr [rbp+0C90h+var_CC0+10h], rdx
0x180015070  movups  xmmword ptr [rbp+0C90h+pvarg], xmm0
0x180015074  mov     qword ptr [rbp+0C90h+pvarg+10h], rdx
0x180015078  movups  xmmword ptr [rbp+0C90h+pvargDest], xmm0
0x18001507c  mov     qword ptr [rbp+0C90h+pvargDest+10h], rdx
0x180015080  mov     [rbp+0C90h+var_CE8], r14d
0x180015084  mov     [rbp+0C90h+var_CE4], r14d
0x180015088  mov     r15d, r14d
0x18001508b  mov     [rbp+0C90h+var_C60], r14
0x18001508f  test    rax, rax
0x180015092  jz      loc_180015941
0x180015098  test    rcx, rcx
0x18001509b  jz      loc_180015941
0x1800150a1  mov     [rax], r14d
0x1800150a4  mov     [rbp+0C90h+var_850], r14w
0x1800150ac  lea     eax, [rdx+7Bh]
0x1800150af  mov     [rbp+0C90h+var_B50], ax
0x1800150b6  mov     rdx, r8
0x1800150b9  lea     rcx, [rbp+0C90h+var_B4E]
0x1800150c0  call    ??$guid_to_string_upper@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<ushort>(ushort *,_GUID const &,bool)
0x1800150c5  mov     [rbp+0C90h+var_B06], 7Dh ; '}'
0x1800150cf  test    r12, r12
0x1800150d2  jnz     short loc_180015101
0x1800150d4  xor     edx, edx; wchar_t *
0x1800150d6  lea     rcx, [rbp+0C90h+var_CA8]; this
0x1800150da  call    ?Connect@WBEM_SERVICE@@QEAAKPEB_W@Z; WBEM_SERVICE::Connect(wchar_t const *)
0x1800150df  mov     edi, eax
0x1800150e1  test    eax, eax
0x1800150e3  jnz     loc_1800158C0
0x1800150e9  cmp     [rbp+0C90h+var_CA8], r14
0x1800150ed  jnz     short loc_1800150F9
0x1800150ef  mov     edi, 1070h
0x1800150f4  jmp     loc_1800158C0
0x1800150f9  mov     r12, [rbp+0C90h+var_CA8]
0x1800150fd  mov     rbx, [rbp+0C90h+var_CF0]
0x180015101  mov     [rbp+0C90h+var_CF0], r14
0x180015105  test    rbx, rbx
0x180015108  jz      short loc_18001511A
0x18001510a  mov     rax, [rbx]
0x18001510d  mov     rcx, rbx
0x180015110  mov     rax, [rax+10h]
0x180015114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015119  nop
0x18001511a  lea     rcx, psz; "EventTrace"
0x180015121  call    cs:__imp_SysAllocString
0x180015127  mov     r15, rax
0x18001512a  mov     [rbp+0C90h+var_C60], rax
0x18001512e  test    rax, rax
0x180015131  jz      loc_1800158BB
0x180015137  mov     edi, 490h
0x18001513c  mov     rax, [r12]
0x180015140  mov     rbx, [rax+60h]
0x180015144  mov     [rbp+0C90h+var_D08], r14
0x180015148  lea     rax, [rbp+0C90h+var_CF0]
0x18001514c  mov     [rbp+0C90h+var_D00], rax
0x180015150  mov     rcx, [rbp+0C90h+var_CF0]
0x180015154  mov     [rbp+0C90h+var_CF0], r14
0x180015158  test    rcx, rcx
0x18001515b  jz      short loc_18001516A
0x18001515d  mov     rax, [rcx]
0x180015160  mov     rax, [rax+10h]
0x180015164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015169  nop
0x18001516a  lea     rax, [rbp+0C90h+var_D08]
0x18001516e  mov     [rsp+0D90h+var_D70], rax
0x180015173  xor     r9d, r9d
0x180015176  mov     r8d, 20001h
0x18001517c  mov     rdx, r15
0x18001517f  mov     rcx, r12
0x180015182  mov     rax, rbx
0x180015185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001518a  mov     ebx, eax
0x18001518c  mov     r8, [rbp+0C90h+var_D08]
0x180015190  test    r8, r8
0x180015193  jz      short loc_1800151B4
0x180015195  mov     rcx, [rbp+0C90h+var_D00]
0x180015199  mov     rdx, [rcx]
0x18001519c  mov     [rcx], r8
0x18001519f  test    rdx, rdx
0x1800151a2  jz      short loc_1800151B4
0x1800151a4  mov     rax, [rdx]
0x1800151a7  mov     rcx, rdx
0x1800151aa  mov     rax, [rax+10h]
0x1800151ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151b3  nop
0x1800151b4  test    ebx, ebx
0x1800151b6  js      loc_1800158C0
0x1800151bc  mov     [rbp+0C90h+var_CE0], r14d
0x1800151c0  mov     esi, 1
0x1800151c5  mov     [rbp+0C90h+var_CE8], esi
0x1800151c8  mov     r13b, r14b
0x1800151cb  mov     [rsp+0D90h+var_D20], r14
0x1800151d0  mov     rcx, [rbp+0C90h+var_CF0]
0x1800151d4  mov     rax, [rcx]
0x1800151d7  mov     [rbp+0C90h+var_D08], r14
0x1800151db  lea     rdx, [rsp+0D90h+var_D20]
0x1800151e0  mov     [rbp+0C90h+var_D00], rdx
0x1800151e4  mov     [rsp+0D90h+var_D20], r14
0x1800151e9  lea     rdx, [rbp+0C90h+var_CE8]
0x1800151ed  mov     [rsp+0D90h+var_D70], rdx
0x1800151f2  lea     r9, [rbp+0C90h+var_D08]
0x1800151f6  mov     r8d, esi
0x1800151f9  or      edx, 0FFFFFFFFh
0x1800151fc  mov     rax, [rax+20h]
0x180015200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015205  mov     ebx, eax
0x180015207  mov     r8, [rbp+0C90h+var_D08]
0x18001520b  test    r8, r8
0x18001520e  jz      short loc_18001522F
0x180015210  mov     rcx, [rbp+0C90h+var_D00]
0x180015214  mov     rdx, [rcx]
0x180015217  mov     [rcx], r8
0x18001521a  test    rdx, rdx
0x18001521d  jz      short loc_18001522F
0x18001521f  mov     rax, [rdx]
0x180015222  mov     rcx, rdx
0x180015225  mov     rax, [rax+10h]
0x180015229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001522e  nop
0x18001522f  test    ebx, ebx
0x180015231  js      loc_1800158A2
0x180015237  mov     eax, [rbp+0C90h+var_CE8]
0x18001523a  test    eax, eax
0x18001523c  jz      loc_180015881
0x180015242  cmp     eax, esi
0x180015244  jnz     loc_180015845
0x18001524a  mov     [rsp+0D90h+var_D28], r14
0x18001524f  mov     rcx, [rsp+0D90h+var_D20]
0x180015254  mov     rax, [rcx]
0x180015257  mov     [rbp+0C90h+var_D08], r14
0x18001525b  lea     rdx, [rsp+0D90h+var_D28]
0x180015260  mov     [rbp+0C90h+var_D00], rdx
0x180015264  mov     [rsp+0D90h+var_D28], r14
0x180015269  lea     rdx, [rbp+0C90h+var_D08]
0x18001526d  mov     rax, [rax+18h]
0x180015271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015276  mov     ebx, eax
0x180015278  mov     r8, [rbp+0C90h+var_D08]
0x18001527c  test    r8, r8
0x18001527f  jz      short loc_1800152A0
0x180015281  mov     rcx, [rbp+0C90h+var_D00]
0x180015285  mov     rdx, [rcx]
0x180015288  mov     [rcx], r8
0x18001528b  test    rdx, rdx
0x18001528e  jz      short loc_1800152A0
0x180015290  mov     rax, [rdx]
0x180015293  mov     rcx, rdx
0x180015296  mov     rax, [rax+10h]
0x18001529a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001529f  nop
0x1800152a0  test    ebx, ebx
0x1800152a2  js      loc_180015851
0x1800152a8  mov     rbx, [rsp+0D90h+var_D28]
0x1800152ad  mov     rax, [rbx]
0x1800152b0  mov     r14, [rax+18h]
0x1800152b4  xor     eax, eax
0x1800152b6  cmp     word ptr [rbp+0C90h+pvarg], ax
0x1800152ba  jz      short loc_1800152C8
0x1800152bc  lea     rcx, [rbp+0C90h+pvarg]; pvarg
0x1800152c0  call    cs:__imp_VariantClear
0x1800152c6  xor     eax, eax
0x1800152c8  mov     [rsp+0D90h+var_D70], rax
0x1800152cd  lea     r9, [rbp+0C90h+pvarg]
0x1800152d1  xor     r8d, r8d
0x1800152d4  lea     rdx, aGuid; "Guid"
0x1800152db  mov     rcx, rbx
0x1800152de  mov     rax, r14
0x1800152e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152e6  xor     r14d, r14d
0x1800152e9  test    eax, eax
0x1800152eb  js      loc_18001583A
0x1800152f1  mov     ecx, 7FFFFFFEh
0x1800152f6  mov     r8, qword ptr [rbp+0C90h+pvarg+8]
0x1800152fa  mov     edx, 80h
0x1800152ff  lea     rax, [rbp+0C90h+var_A50]
0x180015306  test    rcx, rcx
0x180015309  jz      short loc_180015329
0x18001530b  movzx   r9d, word ptr [r8]
0x18001530f  test    r9w, r9w
0x180015313  jz      short loc_180015329
0x180015315  add     r8, 2
0x180015319  mov     [rax], r9w
0x18001531d  add     rax, 2
0x180015321  sub     rcx, rsi
0x180015324  sub     rdx, rsi
0x180015327  jnz     short loc_180015306
0x180015329  lea     rcx, [rax-2]
0x18001532d  test    rdx, rdx
0x180015330  cmovnz  rcx, rax
0x180015334  mov     [rcx], r14w
0x180015338  jz      loc_18001583A
0x18001533e  cmp     word ptr [rbp+0C90h+pvarg], r14w
0x180015343  jz      short loc_18001534F
0x180015345  lea     rcx, [rbp+0C90h+pvarg]; pvarg
0x180015349  call    cs:__imp_VariantClear
0x18001534f  mov     rbx, [rsp+0D90h+var_D20]
0x180015354  mov     rax, [rbx]
0x180015357  mov     r14, [rax+20h]
0x18001535b  xor     eax, eax
0x18001535d  cmp     word ptr [rbp+0C90h+var_CC0], ax
0x180015361  jz      short loc_18001536F
0x180015363  lea     rcx, [rbp+0C90h+var_CC0]; pvarg
0x180015367  call    cs:__imp_VariantClear
0x18001536d  xor     eax, eax
0x18001536f  mov     [rsp+0D90h+var_D68], rax
0x180015374  mov     [rsp+0D90h+var_D70], rax
0x180015379  lea     r9, [rbp+0C90h+var_CC0]
0x18001537d  xor     r8d, r8d
0x180015380  lea     rdx, aClass; "__CLASS"
0x180015387  mov     rcx, rbx
0x18001538a  mov     rax, r14
0x18001538d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015392  xor     r14d, r14d
0x180015395  test    eax, eax
0x180015397  js      loc_18001583A
0x18001539d  mov     rcx, qword ptr [rbp+0C90h+var_CC0+8]; pbstr
0x1800153a1  call    cs:__imp_SysStringLen
0x1800153a7  mov     r11d, eax
0x1800153aa  test    eax, eax
0x1800153ac  jz      short loc_1800153D6
0x1800153ae  mov     r8, qword ptr [rbp+0C90h+var_CC0+8]; wchar_t *
0x1800153b2  mov     edx, 400h; unsigned __int64
0x1800153b7  lea     rcx, [rbp+0C90h+var_850]; wchar_t *
0x1800153be  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800153c3  test    eax, eax
0x1800153c5  js      loc_18001583A
0x1800153cb  lea     eax, ds:2[r11*2]
0x1800153d3  mov     [rbp+0C90h+var_CE0], eax
0x1800153d6  mov     rax, [r12]
0x1800153da  mov     [rbp+0C90h+var_D08], r14
0x1800153de  lea     rcx, [rbp+0C90h+var_D10]
0x1800153e2  mov     [rbp+0C90h+var_D00], rcx
0x1800153e6  mov     [rbp+0C90h+var_D10], r14
0x1800153ea  lea     rcx, [rbp+0C90h+var_D08]
0x1800153ee  mov     [rsp+0D90h+var_D70], rcx
0x1800153f3  xor     r9d, r9d
0x1800153f6  mov     r8d, 20001h
0x1800153fc  mov     rdx, qword ptr [rbp+0C90h+var_CC0+8]
0x180015400  mov     rcx, r12
0x180015403  mov     rax, [rax+60h]
0x180015407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001540c  mov     ebx, eax
0x18001540e  mov     r8, [rbp+0C90h+var_D08]
0x180015412  test    r8, r8
0x180015415  jz      short loc_180015436
0x180015417  mov     rcx, [rbp+0C90h+var_D00]
0x18001541b  mov     rdx, [rcx]
0x18001541e  mov     [rcx], r8
0x180015421  test    rdx, rdx
0x180015424  jz      short loc_180015436
0x180015426  mov     rax, [rdx]
0x180015429  mov     rcx, rdx
0x18001542c  mov     rax, [rax+10h]
0x180015430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015435  nop
0x180015436  cmp     word ptr [rbp+0C90h+var_CC0], r14w
0x18001543b  jz      short loc_180015447
0x18001543d  lea     rcx, [rbp+0C90h+var_CC0]; pvarg
0x180015441  call    cs:__imp_VariantClear
0x180015447  test    ebx, ebx
0x180015449  js      loc_180015830
0x18001544f  mov     [rbp+0C90h+var_CE4], esi
0x180015452  mov     [rsp+0D90h+var_D18], r14
0x180015457  mov     rcx, [rbp+0C90h+var_D10]
0x18001545b  mov     rax, [rcx]
0x18001545e  mov     [rbp+0C90h+var_D08], r14
0x180015462  lea     rdx, [rsp+0D90h+var_D18]
0x180015467  mov     [rbp+0C90h+var_D00], rdx
0x18001546b  mov     [rsp+0D90h+var_D18], r14
  ... truncated ...
```
