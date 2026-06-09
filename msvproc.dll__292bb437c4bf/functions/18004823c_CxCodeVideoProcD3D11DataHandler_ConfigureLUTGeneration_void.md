# CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration(void)

- ea: `0x18004823c`
- end: `0x180048f05`
- name: `?ConfigureLUTGeneration@CxCodeVideoProcD3D11DataHandler@@AEAAJXZ`
- size: `3273`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e5f0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000ac20`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800364d0`
- `0x18004823c`
- `0x180054140`
- `0x180054e30`
- `0x180066ee0`
- `0x180072338`
- `0x1800a052c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048311`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800483fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800484a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048681`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004875e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048aad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048b7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048d5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048e28`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048311`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800483fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800484a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048599`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048681`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004875e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048aad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048b7d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048d5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180048e28`

## string_xrefs

- `0x180048271`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x1800485f0`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x1800486d8`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x1800487b5`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x180048b04`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x180048bd4`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x180048db3`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`
- `0x180048e7f`: `CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration(CxCodeVideoProcD3D11DataHandler *this)
{
  __int64 v2; // rax
  unsigned int v3; // r12d
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *, __int64, _QWORD, char *); // rbx
  int v6; // edi
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdi
  _QWORD *v18; // r14
  __int64 (__fastcall *v19)(__int64, int *, _QWORD, char *); // rbx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, _QWORD, int *, char *); // rdi
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, _QWORD, int *, char *); // rdi
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  CxCodeVideoProcMFTDataHandler *v33; // rbx
  struct IMFAttributes *v34; // rbx
  __int64 v35; // rax
  int i; // edi
  double v37; // xmm0_8
  float v38; // xmm1_4
  double v39; // xmm2_8
  double v40; // xmm0_8
  double v41; // xmm0_8
  double v42; // xmm1_8
  double v43; // xmm0_8
  __int64 v44; // rax
  __int64 v45; // rsi
  __int64 (__fastcall *v46)(__int64, int *, unsigned __int16 **, char *); // rdi
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // r14
  __int64 (__fastcall *v51)(__int64, _QWORD, int *, char *); // rsi
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  int j; // ebx
  double v56; // xmm1_8
  double v57; // xmm0_8
  __int64 v58; // rax
  __int64 v59; // rdi
  __int64 (__fastcall *v60)(__int64, int *, unsigned __int16 **, char *); // rbx
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 v64; // rsi
  __int64 (__fastcall *v65)(__int64, _QWORD, int *, char *); // rdi
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  int v70; // [rsp+48h] [rbp-C0h] BYREF
  int v71; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v72; // [rsp+50h] [rbp-B8h] BYREF
  struct IMFAttributes *v73; // [rsp+58h] [rbp-B0h] BYREF
  int v74; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+64h] [rbp-A4h]
  int v76; // [rsp+6Ch] [rbp-9Ch]
  __int64 v77; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v78; // [rsp+78h] [rbp-90h] BYREF
  int v79; // [rsp+80h] [rbp-88h]
  int v80; // [rsp+84h] [rbp-84h]
  int v81; // [rsp+88h] [rbp-80h] BYREF
  __int64 v82; // [rsp+8Ch] [rbp-7Ch]
  __int64 v83; // [rsp+94h] [rbp-74h]
  int v84; // [rsp+A0h] [rbp-68h] BYREF
  int v85; // [rsp+A4h] [rbp-64h]
  int v86; // [rsp+A8h] [rbp-60h]
  int v87; // [rsp+ACh] [rbp-5Ch]
  int v88; // [rsp+B0h] [rbp-58h]
  __int64 v89; // [rsp+B4h] [rbp-54h]
  int v90; // [rsp+BCh] [rbp-4Ch]
  int v91; // [rsp+C0h] [rbp-48h]
  __int64 v92; // [rsp+C4h] [rbp-44h]
  unsigned __int16 v93; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 v94; // [rsp+DAh] [rbp-2Eh]
  unsigned __int16 v95; // [rsp+DCh] [rbp-2Ch]

  v71 = 0;
  v73 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v70,
    "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
    5247);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1728);
  v2 = *((_QWORD *)this + 2);
  v3 = 1;
  if ( *(_DWORD *)(v2 + 1132) == 1 || *(_DWORD *)(v2 + 1032) == 1 )
  {
    v4 = *((_QWORD *)this + 285);
    v5 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, char *))(*(_QWORD *)v4 + 120LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1728);
    v6 = v5(v4, qword_1800DF5A0, 4540, 0, (char *)this + 1728);
    if ( v6 < 0 )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v8;
        if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
        {
          v7 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v7 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v7 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
            5255,
            v6);
      }
      if ( !g_wppLevels )
        goto LABEL_149;
      v10 = 320;
      goto LABEL_148;
    }
    *(_DWORD *)(*((_QWORD *)this + 2) + 1272LL) = 1;
  }
  if ( *((_QWORD *)this + 216) )
  {
    CxCodeVideoProcGeometryImplD3D11::Initialize(
      (CxCodeVideoProcD3D11DataHandler *)((char *)this + 2096),
      *((struct ID3D11Device **)this + 285),
      *((struct ID3D11DeviceContext **)this + 286));
    (**((void (__fastcall ***)(char *, char *))this + 50))((char *)this + 400, (char *)this + 2096);
    v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 50) + 16LL))((char *)this + 400);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 50) + 24LL))((char *)this + 400);
      if ( v6 >= 0 )
      {
        v17 = *((_QWORD *)this + 285);
        v18 = (_QWORD *)((char *)this + 1736);
        v90 = 0;
        v92 = 0;
        v88 = 10;
        v87 = 1;
        v91 = 40;
        v86 = 1;
        v84 = 34;
        v85 = 1156;
        v89 = 1;
        v19 = *(__int64 (__fastcall **)(__int64, int *, _QWORD, char *))(*(_QWORD *)v17 + 40LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1736);
        v6 = v19(v17, &v84, 0, (char *)this + 1736);
        if ( v6 >= 0 )
        {
          v23 = *((_QWORD *)this + 285);
          v74 = v88;
          v77 = 0;
          v75 = 4;
          v76 = v86;
          v24 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v23 + 56LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1784);
          v6 = v24(v23, *v18, &v74, (char *)this + 1784);
          if ( v6 >= 0 )
          {
            v28 = *((_QWORD *)this + 285);
            v83 = 0;
            v81 = v88;
            v82 = 4;
            v29 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v28 + 72LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1776);
            v6 = v29(v28, *v18, &v81, (char *)this + 1776);
            if ( v6 >= 0 )
            {
              v33 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)this + 4);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
              CxCodeVideoProcMFTDataHandler::GetAttributes(v33, &v73);
              v34 = v73;
              if ( *((_QWORD *)this + 220) )
              {
                if ( *((_QWORD *)this + 218) )
                {
                  if ( ((int (__fastcall *)(struct IMFAttributes *, __int64 *, int *))v73->lpVtbl->GetItemType)(
                         v73,
                         qword_1800E1A08,
                         &v71) < 0
                    && ((int (__fastcall *)(struct IMFAttributes *, __int64 *, int *))v34->lpVtbl->GetItemType)(
                         v34,
                         qword_1800E1A18,
                         &v71) < 0 )
                  {
                    v35 = *((_QWORD *)this + 2);
                    if ( !*(_BYTE *)(v35 + 1270) && !*(_BYTE *)(v35 + 1271) )
                      goto LABEL_149;
                  }
                }
              }
              v84 = 512;
              v88 = 56;
              v74 = 56;
              v85 = 1;
              v90 = 0;
              v91 = 8;
              LODWORD(v72) = 0;
              if ( ((int (__fastcall *)(struct IMFAttributes *, __int64 *, unsigned __int16 *, __int64, __int64 *))v34->lpVtbl->GetBlob)(
                     v34,
                     qword_1800E1A18,
                     &v93,
                     1024,
                     &v72) >= 0 )
              {
                if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                  WPP_SF_qddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 42),
                    327,
                    &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                    this,
                    v93,
                    v94,
                    v95);
                *(_BYTE *)(*((_QWORD *)this + 2) + 1271LL) = 1;
              }
              else
              {
                if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                  WPP_SF_q(
                    *((_QWORD *)WPP_GLOBAL_Control + 42),
                    326,
                    &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                    this);
                for ( i = 0; i < 512; ++i )
                {
                  v37 = pow((double)i / 511.0, 0.01268331351565597);
                  v38 = pow(fmax(v37 - 0.8359375, 0.0) / (18.8515625 - v37 * 18.6875), 6.277394636015326);
                  v39 = (float)(v38 * 2.5);
                  if ( v39 >= 0.0 )
                    v40 = fmin(1.0, v39);
                  else
                    v40 = 0.0;
                  v41 = pow(v40, 0.148615440367466);
                  v42 = pow(
                          (v41 * 18.6124246915492 + 0.642288182084638) / (v41 * 18.2547128736338 + 1.0),
                          78.7046427001135);
                  if ( v42 >= 0.0 )
                    v43 = fmin(1.0, v42);
                  else
                    v43 = 0.0;
                  v44 = (unsigned int)i;
                  *(&v93 + v44) = (int)(v43 * 65535.0);
                }
                *(_BYTE *)(*((_QWORD *)this + 2) + 1271LL) = 0;
              }
              v79 = 1024;
              v45 = *((_QWORD *)this + 285);
              v78 = &v93;
              v80 = v85 << 10;
              v46 = *(__int64 (__fastcall **)(__int64, int *, unsigned __int16 **, char *))(*(_QWORD *)v45 + 40LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1760);
              v6 = v46(v45, &v84, &v78, (char *)this + 1760);
              if ( v6 >= 0 )
              {
                v50 = *((_QWORD *)this + 285);
                v51 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v50 + 56LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1768);
                v6 = v51(v50, *((_QWORD *)this + 220), &v74, (char *)this + 1768);
                if ( v6 >= 0 )
                {
                  if ( ((int (__fastcall *)(struct IMFAttributes *, __int64 *, unsigned __int16 *, __int64, __int64 *))v34->lpVtbl->GetBlob)(
                         v34,
                         qword_1800E1A08,
                         &v93,
                         1024,
                         &v72) >= 0 )
                  {
                    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                      WPP_SF_qddd(
                        *((_QWORD *)WPP_GLOBAL_Control + 42),
                        331,
                        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                        this,
                        v93,
                        v94,
                        v95);
                    *(_BYTE *)(*((_QWORD *)this + 2) + 1270LL) = 0;
                  }
                  else
                  {
                    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
                      WPP_SF_q(
                        *((_QWORD *)WPP_GLOBAL_Control + 42),
                        330,
                        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
                        this);
                    for ( j = 0; j < 512; ++j )
                    {
                      v56 = fwd1DShape((double)j / 511.0) / 2.5;
                      if ( v56 >= 0.0 )
                        v57 = fmin(1.0, v56);
                      else
                        v57 = 0.0;
                      v58 = (unsigned int)j;
                      *(&v93 + v58) = (int)(v57 * 65535.0);
                    }
                    *(_BYTE *)(*((_QWORD *)this + 2) + 1270LL) = 1;
                  }
                  v59 = *((_QWORD *)this + 285);
                  v60 = *(__int64 (__fastcall **)(__int64, int *, unsigned __int16 **, char *))(*(_QWORD *)v59 + 40LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1744);
                  v6 = v60(v59, &v84, &v78, (char *)this + 1744);
                  if ( v6 >= 0 )
                  {
                    v64 = *((_QWORD *)this + 285);
                    v65 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v64 + 56LL);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1752);
                    v6 = v65(v64, *((_QWORD *)this + 218), &v74, (char *)this + 1752);
                    if ( v6 >= 0 )
                      goto LABEL_149;
                    v66 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v67;
                      if ( v67
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(
                             v67,
                             2032) )
                      {
                        v66 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v66 = &qword_180153440;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                      }
                    }
                    if ( *((_BYTE *)v66 + 8) )
                    {
                      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
                      if ( *((_DWORD *)v68 + 499) != v6 )
                        CallStackContext::TraceFailure(
                          v68,
                          "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
                          5365,
                          v6);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_149;
                    v10 = 333;
                  }
                  else
                  {
                    v61 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v62;
                      if ( v62
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(
                             v62,
                             2032) )
                      {
                        v61 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v61 = &qword_180153440;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                      }
                    }
                    if ( *((_BYTE *)v61 + 8) )
                    {
                      v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
                      if ( *((_DWORD *)v63 + 499) != v6 )
                        CallStackContext::TraceFailure(
                          v63,
                          "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
                          5364,
                          v6);
                    }
                    if ( !g_wppLevels )
                      goto LABEL_149;
                    v10 = 332;
                  }
                }
                else
                {
                  v52 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v53;
                    if ( v53
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                    {
                      v52 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v52 = &qword_180153440;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                    }
                  }
                  if ( *((_BYTE *)v52 + 8) )
                  {
                    v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                    if ( *((_DWORD *)v54 + 499) != v6 )
                      CallStackContext::TraceFailure(
                        v54,
                        "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
                        5344,
                        v6);
                  }
                  if ( !g_wppLevels )
                    goto LABEL_149;
                  v10 = 329;
                }
              }
              else
              {
                v47 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v48;
                  if ( v48
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v47 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
                  if ( *((_DWORD *)v49 + 499) != v6 )
                    CallStackContext::TraceFailure(
                      v49,
                      "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
                      5343,
                      v6);
                }
                if ( !g_wppLevels )
                  goto LABEL_149;
                v10 = 328;
              }
            }
            else
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)v32 + 499) != v6 )
                  CallStackContext::TraceFailure(
                    v32,
                    "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration",
                    5297,
                    v6);
              }
              if ( !g_wppLevels )
                goto LABEL_149;
              v10 = 325;
            }
          }
          else
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)v27 + 499) != v6 )
                CallStackContext::TraceFailure(v27, "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration", 5290, v6);
            }
            if ( !g_wppLevels )
              goto LABEL_149;
            v10 = 324;
          }
        }
        else
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v6 )
              CallStackContext::TraceFailure(v22, "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration", 5282, v6);
          }
          if ( !g_wppLevels )
            goto LABEL_149;
          v10 = 323;
        }
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v6 )
            CallStackContext::TraceFailure(v16, "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration", 5268, v6);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v10 = 322;
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v6 )
          CallStackContext::TraceFailure(v13, "CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration", 5267, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_149;
      v10 = 321;
    }
LABEL_148:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v6);
LABEL_149:
    v3 = v6;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v70);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  return v3;
}

```

## disassembly

```asm
0x18004823c  mov     rax, rsp
0x18004823f  push    rbp
0x180048240  push    rbx
0x180048241  push    rsi
0x180048242  push    rdi
0x180048243  push    r12
0x180048245  push    r13
0x180048247  push    r14
0x180048249  push    r15
0x18004824b  lea     rbp, [rax-438h]
0x180048252  sub     rsp, 4F8h
0x180048259  movaps  xmmword ptr [rax-58h], xmm6
0x18004825d  mov     rax, cs:__security_cookie
0x180048264  xor     rax, rsp
0x180048267  mov     [rbp+430h+var_60], rax
0x18004826e  mov     r15, rcx
0x180048271  lea     r14, aCxcodevideopro_134; "CxCodeVideoProcD3D11DataHandler::Config"...
0x180048278  xor     r13d, r13d
0x18004827b  lea     rcx, [rsp+530h+var_4F0]; this
0x180048280  mov     rdx, r14; char *
0x180048283  mov     [rsp+530h+var_4EC], r13d
0x180048288  mov     r8d, 147Fh; int
0x18004828e  mov     [rsp+530h+var_4E0], r13
0x180048293  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180048298  lea     rsi, [r15+6C0h]
0x18004829f  mov     rcx, rsi
0x1800482a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800482a7  mov     rax, [r15+10h]
0x1800482ab  lea     r12d, [r13+1]
0x1800482af  cmp     [rax+46Ch], r12d
0x1800482b6  jz      short loc_1800482C5
0x1800482b8  cmp     [rax+408h], r12d
0x1800482bf  jnz     loc_18004839B
0x1800482c5  mov     rdi, [r15+8E8h]
0x1800482cc  mov     rcx, rsi
0x1800482cf  mov     rax, [rdi]
0x1800482d2  mov     rbx, [rax+78h]
0x1800482d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800482db  xor     r9d, r9d
0x1800482de  mov     qword ptr [rsp+530h+var_510], rsi
0x1800482e3  mov     r8d, 11BCh
0x1800482e9  lea     rdx, qword_1800DF5A0
0x1800482f0  mov     rcx, rdi
0x1800482f3  mov     rax, rbx
0x1800482f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482fb  mov     edi, eax
0x1800482fd  test    eax, eax
0x1800482ff  jns     loc_180048390
0x180048305  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004830c  test    rcx, rcx
0x18004830f  jnz     short loc_180048352
0x180048311  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048317  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004831e  mov     rcx, rax
0x180048321  test    rax, rax
0x180048324  jz      short loc_180048344
0x180048326  mov     rax, [rax]
0x180048329  mov     edx, 7F0h
0x18004832e  mov     rax, [rax+8]
0x180048332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048337  test    eax, eax
0x180048339  jz      short loc_180048344
0x18004833b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048342  jmp     short loc_180048352
0x180048344  lea     rcx, qword_180153440; this
0x18004834b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180048352  cmp     [rcx+8], r13b
0x180048356  jz      short loc_180048379
0x180048358  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004835d  cmp     [rax+7CCh], edi
0x180048363  jz      short loc_180048379
0x180048365  mov     r9d, edi; int
0x180048368  mov     r8d, 1487h; int
0x18004836e  mov     rdx, r14; char *
0x180048371  mov     rcx, rax; this
0x180048374  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048379  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180048380  jb      loc_180048EC0
0x180048386  mov     edx, 140h
0x18004838b  jmp     loc_180048EA2
0x180048390  mov     rax, [r15+10h]
0x180048394  mov     [rax+4F8h], r12d
0x18004839b  cmp     [rsi], r13
0x18004839e  jz      loc_180048EC3
0x1800483a4  mov     r8, [r15+8F0h]; struct ID3D11DeviceContext *
0x1800483ab  lea     rbx, [r15+830h]
0x1800483b2  mov     rdx, [r15+8E8h]; struct ID3D11Device *
0x1800483b9  mov     rcx, rbx; this
0x1800483bc  call    ?Initialize@CxCodeVideoProcGeometryImplD3D11@@QEAAXPEAUID3D11Device@@PEAUID3D11DeviceContext@@@Z; CxCodeVideoProcGeometryImplD3D11::Initialize(ID3D11Device *,ID3D11DeviceContext *)
0x1800483c1  lea     rsi, [r15+190h]
0x1800483c8  mov     rdx, rbx
0x1800483cb  mov     rax, [rsi]
0x1800483ce  mov     rcx, rsi
0x1800483d1  mov     rax, [rax]
0x1800483d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483d9  mov     rax, [rsi]
0x1800483dc  mov     rcx, rsi
0x1800483df  mov     rax, [rax+10h]
0x1800483e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483e8  mov     edi, eax
0x1800483ea  test    eax, eax
0x1800483ec  jns     loc_18004847D
0x1800483f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800483f9  test    rcx, rcx
0x1800483fc  jnz     short loc_18004843F
0x1800483fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048404  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004840b  mov     rcx, rax
0x18004840e  test    rax, rax
0x180048411  jz      short loc_180048431
0x180048413  mov     rax, [rax]
0x180048416  mov     edx, 7F0h
0x18004841b  mov     rax, [rax+8]
0x18004841f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048424  test    eax, eax
0x180048426  jz      short loc_180048431
0x180048428  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004842f  jmp     short loc_18004843F
0x180048431  lea     rcx, qword_180153440; this
0x180048438  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004843f  cmp     [rcx+8], r13b
0x180048443  jz      short loc_180048466
0x180048445  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004844a  cmp     [rax+7CCh], edi
0x180048450  jz      short loc_180048466
0x180048452  mov     r9d, edi; int
0x180048455  mov     r8d, 1493h; int
0x18004845b  mov     rdx, r14; char *
0x18004845e  mov     rcx, rax; this
0x180048461  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048466  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18004846d  jb      loc_180048EC0
0x180048473  mov     edx, 141h
0x180048478  jmp     loc_180048EA2
0x18004847d  mov     rax, [rsi]
0x180048480  mov     rcx, rsi
0x180048483  mov     rax, [rax+18h]
0x180048487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004848c  mov     edi, eax
0x18004848e  test    eax, eax
0x180048490  jns     loc_180048521
0x180048496  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004849d  test    rcx, rcx
0x1800484a0  jnz     short loc_1800484E3
0x1800484a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800484a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800484af  mov     rcx, rax
0x1800484b2  test    rax, rax
0x1800484b5  jz      short loc_1800484D5
0x1800484b7  mov     rax, [rax]
0x1800484ba  mov     edx, 7F0h
0x1800484bf  mov     rax, [rax+8]
0x1800484c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484c8  test    eax, eax
0x1800484ca  jz      short loc_1800484D5
0x1800484cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800484d3  jmp     short loc_1800484E3
0x1800484d5  lea     rcx, qword_180153440; this
0x1800484dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800484e3  cmp     [rcx+8], r13b
0x1800484e7  jz      short loc_18004850A
0x1800484e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800484ee  cmp     [rax+7CCh], edi
0x1800484f4  jz      short loc_18004850A
0x1800484f6  mov     r9d, edi; int
0x1800484f9  mov     r8d, 1494h; int
0x1800484ff  mov     rdx, r14; char *
0x180048502  mov     rcx, rax; this
0x180048505  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004850a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180048511  jb      loc_180048EC0
0x180048517  mov     edx, 142h
0x18004851c  jmp     loc_180048EA2
0x180048521  mov     rdi, [r15+8E8h]
0x180048528  lea     r14, [r15+6C8h]
0x18004852f  mov     [rbp+430h+var_480], r13
0x180048533  mov     rcx, r14
0x180048536  mov     [rbp+430h+var_474], r13
0x18004853a  mov     [rbp+430h+var_488], 0Ah
0x180048541  mov     [rbp+430h+var_48C], r12d
0x180048545  mov     [rbp+430h+var_478], 28h ; '('
0x18004854c  mov     [rbp+430h+var_490], r12d
0x180048550  mov     [rbp+430h+var_498], 22h ; '"'
0x180048557  mov     [rbp+430h+var_494], 484h
0x18004855e  mov     [rbp+430h+var_484], r12d
0x180048562  mov     rax, [rdi]
0x180048565  mov     rbx, [rax+28h]
0x180048569  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004856e  mov     r9, r14
0x180048571  lea     rdx, [rbp+430h+var_498]
0x180048575  xor     r8d, r8d
0x180048578  mov     rcx, rdi
0x18004857b  mov     rax, rbx
0x18004857e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048583  mov     edi, eax
0x180048585  test    eax, eax
0x180048587  jns     loc_18004861C
0x18004858d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180048594  test    rcx, rcx
0x180048597  jnz     short loc_1800485DA
0x180048599  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004859f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485a6  mov     rcx, rax
0x1800485a9  test    rax, rax
0x1800485ac  jz      short loc_1800485CC
0x1800485ae  mov     rax, [rax]
0x1800485b1  mov     edx, 7F0h
0x1800485b6  mov     rax, [rax+8]
0x1800485ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800485bf  test    eax, eax
0x1800485c1  jz      short loc_1800485CC
0x1800485c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485ca  jmp     short loc_1800485DA
0x1800485cc  lea     rcx, qword_180153440; this
0x1800485d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800485da  cmp     [rcx+8], r13b
0x1800485de  jz      short loc_180048605
0x1800485e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800485e5  cmp     [rax+7CCh], edi
0x1800485eb  jz      short loc_180048605
0x1800485ed  mov     r9d, edi; int
0x1800485f0  lea     rdx, aCxcodevideopro_134; "CxCodeVideoProcD3D11DataHandler::Config"...
0x1800485f7  mov     r8d, 14A2h; int
0x1800485fd  mov     rcx, rax; this
0x180048600  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180048605  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18004860c  jb      loc_180048EC0
0x180048612  mov     edx, 143h
0x180048617  jmp     loc_180048EA2
0x18004861c  mov     eax, [rbp+430h+var_488]
0x18004861f  lea     rbx, [r15+6F8h]
0x180048626  mov     rsi, [r15+8E8h]
0x18004862d  mov     rcx, rbx
0x180048630  mov     [rsp+530h+var_4D8], eax
0x180048634  mov     eax, [rbp+430h+var_490]
0x180048637  mov     [rsp+530h+var_4C8], r13
0x18004863c  mov     qword ptr [rsp+530h+var_4D4], 4
0x180048645  mov     dword ptr [rsp+530h+var_4D0+4], eax
0x180048649  mov     rax, [rsi]
0x18004864c  mov     rdi, [rax+38h]
0x180048650  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048655  mov     rdx, [r14]
0x180048658  lea     r8, [rsp+530h+var_4D8]
0x18004865d  mov     r9, rbx
0x180048660  mov     rcx, rsi
0x180048663  mov     rax, rdi
0x180048666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004866b  mov     edi, eax
0x18004866d  test    eax, eax
0x18004866f  jns     loc_180048704
0x180048675  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004867c  test    rcx, rcx
0x18004867f  jnz     short loc_1800486C2
0x180048681  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180048687  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004868e  mov     rcx, rax
0x180048691  test    rax, rax
0x180048694  jz      short loc_1800486B4
0x180048696  mov     rax, [rax]
0x180048699  mov     edx, 7F0h
0x18004869e  mov     rax, [rax+8]
0x1800486a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486a7  test    eax, eax
0x1800486a9  jz      short loc_1800486B4
0x1800486ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800486b2  jmp     short loc_1800486C2
0x1800486b4  lea     rcx, qword_180153440; this
0x1800486bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800486c2  cmp     [rcx+8], r13b
0x1800486c6  jz      short loc_1800486ED
0x1800486c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800486cd  cmp     [rax+7CCh], edi
0x1800486d3  jz      short loc_1800486ED
0x1800486d5  mov     r9d, edi; int
0x1800486d8  lea     rdx, aCxcodevideopro_134; "CxCodeVideoProcD3D11DataHandler::Config"...
0x1800486df  mov     r8d, 14AAh; int
0x1800486e5  mov     rcx, rax; this
0x1800486e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800486ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x1800486f4  jb      loc_180048EC0
0x1800486fa  mov     edx, 144h
0x1800486ff  jmp     loc_180048EA2
0x180048704  mov     eax, [rbp+430h+var_488]
0x180048707  lea     rbx, [r15+6F0h]
0x18004870e  mov     rsi, [r15+8E8h]
0x180048715  mov     rcx, rbx
0x180048718  mov     [rbp+430h+var_4A4], r13
0x18004871c  mov     [rbp+430h+var_4B0], eax
0x18004871f  mov     [rbp+430h+var_4AC], 4
0x180048727  mov     rax, [rsi]
0x18004872a  mov     rdi, [rax+48h]
0x18004872e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048733  mov     rdx, [r14]
0x180048736  lea     r8, [rbp+430h+var_4B0]
0x18004873a  mov     r9, rbx
0x18004873d  mov     rcx, rsi
0x180048740  mov     rax, rdi
0x180048743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048748  mov     edi, eax
0x18004874a  test    eax, eax
  ... truncated ...
```
