# Microsoft::Diagnostics::CensusTaskData::QueryCensusTaskEnabled(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800866dc`
- end: `0x180086cf3`
- name: `?QueryCensusTaskEnabled@CensusTaskData@Diagnostics@Microsoft@@IEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z`
- size: `1559`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800865f8`

## callees

- `0x18001b374`
- `0x18002b318`
- `0x180064e8c`
- `0x1800866dc`
- `0x180133e1c`
- `0x1801b2060`
- `0x180369010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008694d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008694d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008672e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008672e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800867c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800867eb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800867c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800867eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a45`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b15`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180086bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180086bc8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800869e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a45`
- `OLEAUT32!__imp_SysFreeString` at `0x180086a6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b15`
- `OLEAUT32!__imp_SysFreeString` at `0x180086b65`
- `OLEAUT32!__imp_SysFreeString` at `0x180086bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180086bc8`

## string_xrefs

- `0x1800869f8`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086b35`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086b7b`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086bf8`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086c28`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086c3a`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`
- `0x180086c57`: `onecore\base\telemetry\utc\service\analysis\censustaskdata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Diagnostics::CensusTaskData::QueryCensusTaskEnabled(_DWORD *a1, __int64 a2, _QWORD *a3)
{
  int v6; // r14d
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  BSTR v11; // rax
  const char *v12; // r9
  OLECHAR *v13; // rbx
  BSTR v14; // rax
  const char *v15; // r9
  OLECHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // esi
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // esi
  int v23; // eax
  const char *v24; // r9
  unsigned int v25; // esi
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // r15d
  unsigned __int64 v32; // rsi
  unsigned __int64 v33; // r8
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-F8h]
  LPVOID v36; // [rsp+30h] [rbp-E8h] BYREF
  __int64 *v37; // [rsp+38h] [rbp-E0h] BYREF
  __int64 *v38; // [rsp+40h] [rbp-D8h] BYREF
  __int64 *v39; // [rsp+48h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-C8h] BYREF
  BSTR v41; // [rsp+58h] [rbp-C0h] BYREF
  _QWORD v42[2]; // [rsp+60h] [rbp-B8h] BYREF
  int v43[4]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+80h] [rbp-98h]
  __int128 v45; // [rsp+90h] [rbp-88h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-78h]
  __int128 v47; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-58h]
  __int128 v49; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v50; // [rsp+E0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]
  int v52; // [rsp+120h] [rbp+8h] BYREF
  int v53; // [rsp+138h] [rbp+20h] BYREF

  *a1 = -1;
  v36 = 0;
  v6 = 1;
  v7 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v36);
  try
  {
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      if ( v36 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
      result = v8;
    }
    else
    {
      *(_OWORD *)v43 = 0;
      v44 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v45 = 0;
      v46 = 0;
      v9 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v36 + 80LL))(
             v36,
             &v45,
             &v49,
             &v47);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
          (const char *)(unsigned int)v9,
          (int)v43);
        if ( v36 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
        result = v10;
      }
      else
      {
        v11 = SysAllocStringLen(*(const OLECHAR **)a2, *(_DWORD *)(a2 + 8));
        v13 = v11;
        if ( !v11 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x38,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            v12);
        v42[0] = v11;
        v14 = SysAllocStringLen((const OLECHAR *)*a3, *((_DWORD *)a3 + 2));
        v16 = v14;
        if ( !v14 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x39,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            v15);
        v41 = v14;
        v39 = 0;
        v17 = *(_QWORD *)v36;
        v39 = 0;
        v18 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64 **))(v17 + 56))(v36, v13, &v39);
        v19 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            (const char *)(unsigned int)v18,
            (int)v43);
          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v39);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v41);
          wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v42);
          wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v36);
          return v19;
        }
        v38 = 0;
        v20 = *v39;
        v38 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v20 + 112))(v39, 0, &v38);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
            (const char *)(unsigned int)v21,
            (int)v43);
          if ( v38 )
            (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
          if ( v39 )
            (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
          SysFreeString(v16);
          SysFreeString(v13);
          if ( v36 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
          result = v22;
        }
        else
        {
          v53 = 0;
          v23 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v38 + 56))(v38, &v53);
          v25 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x42,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
              (const char *)(unsigned int)v23,
              (int)v43);
            if ( v38 )
              (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
            if ( v39 )
              (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
            SysFreeString(v16);
            SysFreeString(v13);
            if ( v36 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
            result = v25;
          }
          else
          {
            v26 = v53;
            if ( !v53 )
            {
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v38);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v39);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v41);
              wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v42);
              wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v36);
              return 0;
            }
            while ( v6 <= v26 )
            {
              v37 = 0;
              *(_OWORD *)v43 = 0;
              LOWORD(v43[0]) = 3;
              v43[2] = v6;
              v27 = *v38;
              v37 = 0;
              v45 = *(_OWORD *)v43;
              v46 = 0;
              if ( (*(int (__fastcall **)(__int64 *, __int128 *, __int64 **))(v27 + 64))(v38, &v45, &v37) < 0 )
              {
                wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v37);
                goto LABEL_21;
              }
              bstrString = 0;
              v28 = *v37;
              bstrString = 0;
              if ( (*(int (__fastcall **)(__int64 *, BSTR *))(v28 + 56))(v37, &bstrString) >= 0 )
              {
                v29 = std::_WChar_traits<wchar_t>::length(bstrString);
                v31 = v29;
                v32 = a3[1];
                v33 = v32;
                if ( v29 < v32 )
                  v33 = v29;
                if ( !(unsigned int)_o__wcsnicmp(*a3, v30, v33) && (_DWORD)v32 == v31 )
                {
                  LOWORD(v52) = 0;
                  if ( (*(int (__fastcall **)(__int64 *, int *))(*v37 + 80))(v37, &v52) >= 0 )
                  {
                    *a1 = (_WORD)v52 != 0;
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( v37 )
                      (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
                    break;
                  }
                  if ( !bstrString )
                    goto LABEL_19;
                }
                else if ( !bstrString )
                {
                  goto LABEL_19;
                }
LABEL_18:
                SysFreeString(bstrString);
                goto LABEL_19;
              }
              if ( bstrString )
                goto LABEL_18;
LABEL_19:
              if ( v37 )
                (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
LABEL_21:
              ++v6;
              v26 = v53;
            }
            if ( v38 )
              (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
            if ( v39 )
              (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
            if ( v16 )
              SysFreeString(v16);
            if ( v13 )
              SysFreeString(v13);
            if ( v36 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
            result = 0;
          }
        }
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x66,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\censustaskdata.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x1800866dc  mov     [rsp+arg_8], rbx
0x1800866e1  mov     [rsp+arg_10], rsi
0x1800866e6  push    rdi
0x1800866e7  push    r12
0x1800866e9  push    r13
0x1800866eb  push    r14
0x1800866ed  push    r15
0x1800866ef  sub     rsp, 0F0h
0x1800866f6  mov     r12, r8
0x1800866f9  mov     rdi, rdx
0x1800866fc  mov     r13, rcx
0x1800866ff  mov     dword ptr [rcx], 0FFFFFFFFh
0x180086705  xor     r15d, r15d
0x180086708  mov     [rsp+118h+var_E8], r15
0x18008670d  lea     rax, [rsp+118h+var_E8]
0x180086712  mov     qword ptr [rsp+118h+ppv], rax; int
0x180086717  lea     r9, IID_ITaskService; riid
0x18008671e  lea     r14d, [r15+1]
0x180086722  mov     r8d, r14d; dwClsContext
0x180086725  xor     edx, edx; pUnkOuter
0x180086727  lea     rcx, CLSID_TaskScheduler; rclsid
0x18008672e  call    cs:__imp_CoCreateInstance
0x180086734  mov     ebx, eax
0x180086736  test    eax, eax
0x180086738  js      loc_180086B2A
0x18008673e  xorps   xmm1, xmm1
0x180086741  xor     eax, eax
0x180086743  mov     rcx, [rsp+118h+var_E8]
0x180086748  movaps  xmmword ptr [rsp+118h+var_A8], xmm1
0x18008674d  mov     [rsp+118h+var_98], rax
0x180086755  movaps  [rsp+118h+var_68], xmm1
0x18008675d  mov     [rsp+118h+var_58], rax
0x180086765  movaps  [rsp+118h+var_48], xmm1
0x18008676d  mov     [rsp+118h+var_38], rax
0x180086775  movaps  [rsp+118h+var_88], xmm1
0x18008677d  mov     [rsp+118h+var_78], rax
0x180086785  mov     rax, [rcx]
0x180086788  lea     rdx, [rsp+118h+var_A8]
0x18008678d  mov     qword ptr [rsp+118h+ppv], rdx; int
0x180086792  lea     r9, [rsp+118h+var_68]
0x18008679a  lea     r8, [rsp+118h+var_48]
0x1800867a2  lea     rdx, [rsp+118h+var_88]
0x1800867aa  mov     rax, [rax+50h]
0x1800867ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800867b3  mov     ebx, eax
0x1800867b5  test    eax, eax
0x1800867b7  js      loc_180086BED
0x1800867bd  mov     edx, [rdi+8]; ui
0x1800867c0  mov     rcx, [rdi]; strIn
0x1800867c3  call    cs:__imp_SysAllocStringLen
0x1800867c9  mov     rbx, rax
0x1800867cc  mov     rcx, [rsp+118h]; this
0x1800867d4  test    rax, rax
0x1800867d7  jz      loc_180086C28
0x1800867dd  mov     [rsp+118h+var_B8], rax
0x1800867e2  mov     edx, [r12+8]; ui
0x1800867e7  mov     rcx, [r12]; strIn
0x1800867eb  call    cs:__imp_SysAllocStringLen
0x1800867f1  mov     rdi, rax
0x1800867f4  mov     rcx, [rsp+118h]; this
0x1800867fc  test    rax, rax
0x1800867ff  jz      loc_180086C3A
0x180086805  mov     [rsp+118h+var_C0], rax
0x18008680a  mov     [rsp+118h+var_D0], r15
0x18008680f  mov     rcx, [rsp+118h+var_E8]
0x180086814  mov     rax, [rcx]
0x180086817  mov     [rsp+118h+var_D0], r15
0x18008681c  lea     r8, [rsp+118h+var_D0]
0x180086821  mov     rdx, rbx
0x180086824  mov     rax, [rax+38h]
0x180086828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008682d  mov     esi, eax
0x18008682f  test    eax, eax
0x180086831  js      loc_180086C4C
0x180086837  mov     [rsp+118h+var_D8], r15
0x18008683c  mov     rcx, [rsp+118h+var_D0]
0x180086841  mov     rax, [rcx]
0x180086844  mov     [rsp+118h+var_D8], r15
0x180086849  lea     r8, [rsp+118h+var_D8]
0x18008684e  xor     edx, edx
0x180086850  mov     rax, [rax+70h]
0x180086854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086859  mov     esi, eax
0x18008685b  test    eax, eax
0x18008685d  js      loc_1800869ED
0x180086863  mov     [rsp+118h+arg_18], r15d
0x18008686b  mov     rcx, [rsp+118h+var_D8]
0x180086870  mov     rax, [rcx]
0x180086873  lea     rdx, [rsp+118h+arg_18]
0x18008687b  mov     rax, [rax+38h]
0x18008687f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086884  mov     esi, eax
0x180086886  test    eax, eax
0x180086888  js      loc_180086B70
0x18008688e  mov     eax, [rsp+118h+arg_18]
0x180086895  test    eax, eax
0x180086897  jz      loc_180086C9B
0x18008689d  cmp     r14d, eax
0x1800868a0  jg      loc_180086ADF
0x1800868a6  mov     [rsp+118h+var_E0], r15
0x1800868ab  xorps   xmm0, xmm0
0x1800868ae  xor     edx, edx
0x1800868b0  movups  xmmword ptr [rsp+118h+var_A8], xmm0
0x1800868b5  lea     eax, [rdx+3]
0x1800868b8  mov     word ptr [rsp+118h+var_A8], ax
0x1800868bd  mov     [rsp+118h+var_A8+8], r14d
0x1800868c2  mov     rcx, [rsp+118h+var_D8]
0x1800868c7  mov     rax, [rcx]
0x1800868ca  mov     [rsp+118h+var_E0], r15
0x1800868cf  movups  xmm0, xmmword ptr [rsp+118h+var_A8]
0x1800868d4  movaps  [rsp+118h+var_88], xmm0
0x1800868dc  mov     [rsp+118h+var_78], rdx
0x1800868e4  lea     r8, [rsp+118h+var_E0]
0x1800868e9  lea     rdx, [rsp+118h+var_88]
0x1800868f1  mov     rax, [rax+40h]
0x1800868f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868fa  test    eax, eax
0x1800868fc  js      loc_180086CD8
0x180086902  mov     [rsp+118h+bstrString], r15
0x180086907  mov     rcx, [rsp+118h+var_E0]
0x18008690c  mov     rax, [rcx]
0x18008690f  mov     [rsp+118h+bstrString], r15
0x180086914  lea     rdx, [rsp+118h+bstrString]
0x180086919  mov     rax, [rax+38h]
0x18008691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086922  test    eax, eax
0x180086924  js      loc_1800869CF
0x18008692a  mov     rcx, [rsp+118h+bstrString]
0x18008692f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180086934  mov     r15, rax
0x180086937  mov     rsi, [r12+8]
0x18008693c  mov     r8, rsi
0x18008693f  cmp     rax, rsi
0x180086942  cmovb   r8, rax
0x180086946  mov     rdx, rcx
0x180086949  mov     rcx, [r12]
0x18008694d  call    cs:__imp__o__wcsnicmp
0x180086953  test    eax, eax
0x180086955  jnz     short loc_18008695C
0x180086957  sub     esi, r15d
0x18008695a  jz      short loc_18008698F
0x18008695c  mov     rcx, [rsp+118h+bstrString]; bstrString
0x180086961  xor     r15d, r15d
0x180086964  test    rcx, rcx
0x180086967  jnz     short loc_1800869E2
0x180086969  mov     rcx, [rsp+118h+var_E0]
0x18008696e  test    rcx, rcx
0x180086971  jz      short loc_180086980
0x180086973  mov     rax, [rcx]
0x180086976  mov     rax, [rax+10h]
0x18008697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008697f  nop
0x180086980  inc     r14d
0x180086983  mov     eax, [rsp+118h+arg_18]
0x18008698a  jmp     loc_18008689D
0x18008698f  xor     r15d, r15d
0x180086992  mov     word ptr [rsp+118h+arg_0], r15w
0x18008699b  mov     rcx, [rsp+118h+var_E0]
0x1800869a0  mov     rax, [rcx]
0x1800869a3  lea     rdx, [rsp+118h+arg_0]
0x1800869ab  mov     rax, [rax+50h]
0x1800869af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800869b4  test    eax, eax
0x1800869b6  jns     loc_180086AA7
0x1800869bc  mov     rcx, [rsp+118h+bstrString]; bstrString
0x1800869c1  test    rcx, rcx
0x1800869c4  jz      short loc_1800869CD
0x1800869c6  call    cs:__imp_SysFreeString
0x1800869cc  nop
0x1800869cd  jmp     short loc_180086969
0x1800869cf  mov     rcx, [rsp+118h+bstrString]; bstrString
0x1800869d4  test    rcx, rcx
0x1800869d7  jz      short loc_1800869E0
0x1800869d9  call    cs:__imp_SysFreeString
0x1800869df  nop
0x1800869e0  jmp     short loc_180086969
0x1800869e2  call    cs:__imp_SysFreeString
0x1800869e8  jmp     loc_180086969
0x1800869ed  mov     rcx, [rsp+118h]; this
0x1800869f5  mov     r9d, esi; char *
0x1800869f8  lea     r8, aOnecoreBaseTel_136; "onecore\\base\\telemetry\\utc\\service"...
0x1800869ff  mov     edx, 3Fh ; '?'; void *
0x180086a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086a09  nop
0x180086a0a  mov     rcx, [rsp+118h+var_D8]
0x180086a0f  test    rcx, rcx
0x180086a12  jz      short loc_180086A21
0x180086a14  mov     rax, [rcx]
0x180086a17  mov     rax, [rax+10h]
0x180086a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a20  nop
0x180086a21  mov     rcx, [rsp+118h+var_D0]
0x180086a26  test    rcx, rcx
0x180086a29  jz      short loc_180086A38
0x180086a2b  mov     rax, [rcx]
0x180086a2e  mov     rax, [rax+10h]
0x180086a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a37  nop
0x180086a38  mov     rcx, rdi; bstrString
0x180086a3b  call    cs:__imp_SysFreeString
0x180086a41  nop
0x180086a42  mov     rcx, rbx; bstrString
0x180086a45  call    cs:__imp_SysFreeString
0x180086a4b  nop
0x180086a4c  mov     rcx, [rsp+118h+var_E8]
0x180086a51  test    rcx, rcx
0x180086a54  jz      short loc_180086A63
0x180086a56  mov     rax, [rcx]
0x180086a59  mov     rax, [rax+10h]
0x180086a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a62  nop
0x180086a63  mov     eax, esi
0x180086a65  jmp     short loc_180086A8A
0x180086a67  mov     rcx, rbx; bstrString
0x180086a6a  call    cs:__imp_SysFreeString
0x180086a70  nop
0x180086a71  mov     rcx, [rsp+118h+var_E8]
0x180086a76  test    rcx, rcx
0x180086a79  jz      short loc_180086A88
0x180086a7b  mov     rax, [rcx]
0x180086a7e  mov     rax, [rax+10h]
0x180086a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a87  nop
0x180086a88  xor     eax, eax
0x180086a8a  lea     r11, [rsp+118h+var_28]
0x180086a92  mov     rbx, [r11+38h]
0x180086a96  mov     rsi, [r11+40h]
0x180086a9a  mov     rsp, r11
0x180086a9d  pop     r15
0x180086a9f  pop     r14
0x180086aa1  pop     r13
0x180086aa3  pop     r12
0x180086aa5  pop     rdi
0x180086aa6  retn
0x180086aa7  mov     eax, r15d
0x180086aaa  cmp     word ptr [rsp+118h+arg_0], r15w
0x180086ab3  setnz   al
0x180086ab6  mov     [r13+0], eax
0x180086aba  mov     rcx, [rsp+118h+bstrString]; bstrString
0x180086abf  test    rcx, rcx
0x180086ac2  jnz     loc_180086B65
0x180086ac8  mov     rcx, [rsp+118h+var_E0]
0x180086acd  test    rcx, rcx
0x180086ad0  jz      short loc_180086ADF
0x180086ad2  mov     rax, [rcx]
0x180086ad5  mov     rax, [rax+10h]
0x180086ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ade  nop
0x180086adf  mov     rcx, [rsp+118h+var_D8]
0x180086ae4  test    rcx, rcx
0x180086ae7  jz      short loc_180086AF6
0x180086ae9  mov     rax, [rcx]
0x180086aec  mov     rax, [rax+10h]
0x180086af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086af5  nop
0x180086af6  mov     rcx, [rsp+118h+var_D0]
0x180086afb  test    rcx, rcx
0x180086afe  jz      short loc_180086B0D
0x180086b00  mov     rax, [rcx]
0x180086b03  mov     rax, [rax+10h]
0x180086b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b0c  nop
0x180086b0d  test    rdi, rdi
0x180086b10  jz      short loc_180086B1C
0x180086b12  mov     rcx, rdi; bstrString
0x180086b15  call    cs:__imp_SysFreeString
0x180086b1b  nop
0x180086b1c  test    rbx, rbx
0x180086b1f  jz      loc_180086A71
0x180086b25  jmp     loc_180086A67
0x180086b2a  mov     rcx, [rsp+118h]; this
0x180086b32  mov     r9d, ebx; char *
0x180086b35  lea     r8, aOnecoreBaseTel_136; "onecore\\base\\telemetry\\utc\\service"...
0x180086b3c  mov     edx, 32h ; '2'; void *
0x180086b41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086b46  nop
0x180086b47  mov     rcx, [rsp+118h+var_E8]
0x180086b4c  test    rcx, rcx
0x180086b4f  jz      short loc_180086B5E
0x180086b51  mov     rax, [rcx]
0x180086b54  mov     rax, [rax+10h]
0x180086b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b5d  nop
0x180086b5e  mov     eax, ebx
0x180086b60  jmp     loc_180086A8A
0x180086b65  call    cs:__imp_SysFreeString
0x180086b6b  jmp     loc_180086AC8
0x180086b70  mov     rcx, [rsp+118h]; this
0x180086b78  mov     r9d, esi; char *
0x180086b7b  lea     r8, aOnecoreBaseTel_136; "onecore\\base\\telemetry\\utc\\service"...
0x180086b82  mov     edx, 42h ; 'B'; void *
0x180086b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086b8c  nop
0x180086b8d  mov     rcx, [rsp+118h+var_D8]
0x180086b92  test    rcx, rcx
0x180086b95  jz      short loc_180086BA4
0x180086b97  mov     rax, [rcx]
0x180086b9a  mov     rax, [rax+10h]
0x180086b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ba3  nop
  ... truncated ...
```
