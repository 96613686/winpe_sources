# CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture(void)

- ea: `0x18003eb08`
- end: `0x18003f6b6`
- name: `?UpdateSphereMapTempTexture@CxCodeVideoProcD3D11DataHandler@@AEAAJXZ`
- size: `2990`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cb40`
- `0x180015ef0`
- `0x18003d0d4`

## callees

- `0x180005c58`
- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001d3d8`
- `0x18003639c`
- `0x1800364d0`
- `0x18003eb08`
- `0x18005342c`
- `0x180054140`
- `0x180067058`
- `0x1800685b8`
- `0x18006a218`
- `0x180070b60`
- `0x180072b0c`
- `0x1800c0704`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ef0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f075`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f247`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f4f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee12`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ef0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f075`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f189`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f247`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f4f3`

## string_xrefs

- `0x18003ecfe`: `CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture`
- `0x18003f338`: `CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture`
- `0x18003f3eb`: `CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture`
- `0x18003f498`: `CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture(CxCodeVideoProcD3D11DataHandler *this)
{
  char v2; // r13
  _DWORD *v3; // rbx
  __m128i v4; // xmm1
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rcx
  int v8; // r14d
  int v9; // edx
  int v10; // r14d
  int v11; // edx
  __int64 v12; // r8
  __int32 v13; // edi
  int v14; // eax
  __int64 v15; // r9
  __int32 v16; // r15d
  int v17; // eax
  __int32 v18; // r12d
  __int64 v19; // rcx
  int v20; // eax
  int D3D11ShaderPostTempSample; // ebx
  __int64 v22; // rcx
  struct tagRECT v23; // xmm6
  unsigned int v24; // r12d
  __int64 v25; // rax
  __int64 v26; // r13
  struct IMFDXGIBuffer **v27; // r9
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, GUID *, __int64 *); // rbx
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  LONG v37; // edx
  LONG v38; // ecx
  _DWORD *v39; // r9
  unsigned int v40; // eax
  unsigned int v41; // eax
  __int64 *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  struct IMFDXGIBuffer **v46; // r9
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, GUID *, __int64 *); // rbx
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _DWORD *v55; // rdx
  __int64 *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  char v68; // al
  __int64 v69; // rdx
  unsigned __int64 v70; // rcx
  char v72; // [rsp+70h] [rbp-90h] BYREF
  char v73; // [rsp+71h] [rbp-8Fh]
  __int64 v74; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v75[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i v76; // [rsp+90h] [rbp-70h] BYREF
  int v77; // [rsp+A0h] [rbp-60h]
  struct tagSIZE v78; // [rsp+B0h] [rbp-50h]
  struct tagRECT v79; // [rsp+C0h] [rbp-40h] BYREF
  struct tagSIZE v80[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v81; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v82[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v83[28]; // [rsp+100h] [rbp+0h] BYREF

  v2 = 0;
  CxCodeVideoProcD3DSphereGeometry::ComputeCurrentBounds((char *)this + 208, &v76);
  v3 = (_DWORD *)*((_QWORD *)this + 2);
  v4 = *(__m128i *)RectFtoRECT(&v79, (const struct RectF *)&v76, v3[20] - v3[18], v3[21] - v3[19]);
  v81 = 0;
  v5 = v3[20];
  v6 = v3[21];
  v7 = (unsigned int)v3[326];
  v76 = v4;
  v8 = _mm_cvtsi128_si32(v4);
  v9 = v8 % 2;
  if ( v8 % 2 <= 0 )
    v9 = 0;
  v10 = v8 - v9;
  v11 = v4.m128i_i32[1] % 2;
  v77 = v10;
  v76.m128i_i32[0] = v10;
  if ( v4.m128i_i32[1] % 2 <= 0 )
    v11 = 0;
  v12 = (unsigned int)(v5 - v3[18]);
  v13 = v4.m128i_i32[1] - v11;
  v76.m128i_i32[1] = v4.m128i_i32[1] - v11;
  v14 = v12;
  if ( v4.m128i_i32[2] % 2 < (int)v12 )
    v14 = v4.m128i_i32[2] % 2;
  v15 = (unsigned int)(v6 - v3[19]);
  v16 = v14 + v4.m128i_i32[2];
  v76.m128i_i32[2] = v14 + v4.m128i_i32[2];
  v17 = v15;
  if ( v4.m128i_i32[3] % 2 < (int)v15 )
    v17 = v4.m128i_i32[3] % 2;
  v18 = v17 + v4.m128i_i32[3];
  v76.m128i_i32[3] = v17 + v4.m128i_i32[3];
  if ( (_DWORD)v7 == 90 || (_DWORD)v7 == 270 || (unsigned int)(v3[89] - 2) <= 1 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v72,
      "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
      2780);
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 158, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    v63 = (__int64 *)CallStackTracing::s_wpInstance;
    D3D11ShaderPostTempSample = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v64;
      if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
      {
        v63 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v63 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v63 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
          2781,
          -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_135;
    v59 = 159;
  }
  else
  {
    DestinationSpaceToSourceSpace(v7, &v76, v12, v15, &v81, v3);
    v19 = *((_QWORD *)this + 2);
    v20 = *(_DWORD *)(v19 + 864);
    if ( v20 == 2 )
    {
      if ( *(_DWORD *)(v19 + 2144) )
      {
        D3D11ShaderPostTempSample = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int128 *))(**((_QWORD **)this + 290) + 240LL))(
          *((_QWORD *)this + 290),
          *((_QWORD *)this + 294),
          0,
          1,
          &v81);
        v22 = *((_QWORD *)this + 290);
        v23 = (struct tagRECT)v76;
        v24 = v16 - v10;
        v80[1].cy = v76.m128i_i32[3] - v76.m128i_i32[1];
        v80[1].cx = v16 - v10;
        v80[0] = 0;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64, struct tagSIZE *))(*(_QWORD *)v22 + 248LL))(
          v22,
          *((_QWORD *)this + 294),
          0,
          1,
          v80);
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, struct tagSIZE *))(**((_QWORD **)this + 290) + 104LL))(
          *((_QWORD *)this + 290),
          *((_QWORD *)this + 294),
          1,
          v80);
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v72,
          "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
          2804);
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_qdddddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 42),
            160,
            &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
            this,
            v81,
            DWORD1(v81),
            DWORD2(v81),
            HIDWORD(v81),
            v80[0].cx,
            v80[0].cy,
            v80[1].cx,
            v80[1].cy);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
        v25 = *((_QWORD *)this + 2);
        v73 = 1;
        *(_DWORD *)(v25 + 120) = 1;
        *(_OWORD *)(*((_QWORD *)this + 2) + 104LL) = v81;
        v26 = *((_QWORD *)this + 146);
        *(_QWORD *)v75 = 0;
        v74 = 0;
        memset(v83, 0, sizeof(v83));
        *(_OWORD *)v82 = 0;
        if ( v26 )
        {
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)&v72,
            "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
            2828);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
          D3D11ShaderPostTempSample = MFD3D::DXGIBufferFromSample(*((MFD3D **)this + 146), 0, (unsigned int)v75, v27);
          if ( D3D11ShaderPostTempSample < 0 )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)v30 + 499) != D3D11ShaderPostTempSample )
                CallStackContext::TraceFailure(
                  v30,
                  "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
                  2828,
                  D3D11ShaderPostTempSample);
            }
            if ( !g_wppLevels )
              goto LABEL_29;
            v31 = 163;
LABEL_28:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v31,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              D3D11ShaderPostTempSample);
LABEL_29:
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
            v18 = v76.m128i_i32[3];
LABEL_30:
            v2 = v73;
            goto LABEL_136;
          }
          v32 = *(_QWORD *)v75;
          v33 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v75 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
          D3D11ShaderPostTempSample = v33(v32, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v74);
          if ( D3D11ShaderPostTempSample < 0 )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)v36 + 499) != D3D11ShaderPostTempSample )
                CallStackContext::TraceFailure(
                  v36,
                  "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
                  2829,
                  D3D11ShaderPostTempSample);
            }
            if ( !g_wppLevels )
              goto LABEL_29;
            v31 = 164;
            goto LABEL_28;
          }
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v74 + 80LL))(v74, v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
          v13 = v76.m128i_i32[1];
        }
        v37 = v82[1];
        v38 = v82[0];
        if ( *((_QWORD *)this + 146) && v24 <= v82[0] && v76.m128i_i32[3] - v13 <= v82[1] )
        {
          v18 = v76.m128i_i32[3];
        }
        else
        {
          v39 = (_DWORD *)*((_QWORD *)this + 2);
          v40 = v82[0];
          if ( v24 > v82[0] )
            v40 = v16 - v10;
          if ( v40 + 20 >= v39[20] - v39[18] )
          {
            v82[0] = v39[20] - v39[18];
          }
          else
          {
            if ( v24 > v82[0] )
              v38 = v16 - v10;
            v82[0] = v38 + 20;
          }
          v18 = v76.m128i_i32[3];
          v41 = v82[1];
          if ( v76.m128i_i32[3] - v13 > v82[1] )
            v41 = v76.m128i_i32[3] - v13;
          if ( v41 + 20 >= v39[21] - v39[19] )
          {
            v82[1] = v39[21] - v39[19];
          }
          else
          {
            if ( v76.m128i_i32[3] - v13 > v82[1] )
              v37 = v76.m128i_i32[3] - v13;
            v82[1] = v37 + 20;
          }
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)&v72,
            "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
            2837);
          D3D11ShaderPostTempSample = CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample(
                                        this,
                                        *(_DWORD *)(*((_QWORD *)this + 2) + 1208LL),
                                        v82[0],
                                        v82[1]);
          if ( D3D11ShaderPostTempSample < 0 )
          {
            v42 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v43;
              if ( v43
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
              {
                v42 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v42 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v42 + 8) )
            {
              v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
              if ( *((_DWORD *)v44 + 499) != D3D11ShaderPostTempSample )
                CallStackContext::TraceFailure(
                  v44,
                  "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
                  2837,
                  D3D11ShaderPostTempSample);
            }
            if ( !g_wppLevels )
              goto LABEL_72;
            v45 = 165;
LABEL_71:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v45,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              D3D11ShaderPostTempSample);
LABEL_72:
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
LABEL_73:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
            goto LABEL_30;
          }
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
          v37 = v82[1];
          v38 = v82[0];
        }
        if ( !v26 )
        {
          CallStackScopeTrace::CallStackScopeTrace(
            (CallStackScopeTrace *)&v72,
            "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
            2843);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v75);
          D3D11ShaderPostTempSample = MFD3D::DXGIBufferFromSample(*((MFD3D **)this + 146), 0, (unsigned int)v75, v46);
          if ( D3D11ShaderPostTempSample < 0 )
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
              if ( *((_DWORD *)v49 + 499) != D3D11ShaderPostTempSample )
                CallStackContext::TraceFailure(
                  v49,
                  "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
                  2843,
                  D3D11ShaderPostTempSample);
            }
            if ( !g_wppLevels )
              goto LABEL_72;
            v45 = 166;
            goto LABEL_71;
          }
          v50 = *(_QWORD *)v75;
          v51 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v75 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
          D3D11ShaderPostTempSample = v51(v50, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v74);
          if ( D3D11ShaderPostTempSample < 0 )
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
              if ( *((_DWORD *)v54 + 499) != D3D11ShaderPostTempSample )
                CallStackContext::TraceFailure(
                  v54,
                  "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
                  2844,
                  D3D11ShaderPostTempSample);
            }
            if ( !g_wppLevels )
              goto LABEL_72;
            v45 = 167;
            goto LABEL_71;
          }
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v74 + 80LL))(v74, v82);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
          v37 = v82[1];
          v38 = v82[0];
        }
        v78.cy = v37;
        v55 = (_DWORD *)*((_QWORD *)this + 2);
        v78.cx = v38;
        v79 = v23;
        v80[0].cx = v55[20] - v55[18];
        v80[0].cy = v55[21] - v55[19];
        CxCodeVideoProcD3DSphereGeometry::SetTextureOffset(
          (CxCodeVideoProcD3D11DataHandler *)((char *)this + 208),
          &v79,
          v80[0],
          v78);
        goto LABEL_73;
      }
    }
    else if ( v20 == 1 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v72,
        "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
        2810);
      v56 = (__int64 *)CallStackTracing::s_wpInstance;
      D3D11ShaderPostTempSample = -2147467259;
      if ( !CallStackTracing::s_wpInstance )
      {
        v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v57;
        if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
        {
          v56 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v56 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
        if ( *((_DWORD *)v58 + 499) != -2147467259 )
          CallStackContext::TraceFailure(
            v58,
            "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
            2810,
            -2147467259);
      }
      if ( !g_wppLevels )
        goto LABEL_135;
      v59 = 161;
      goto LABEL_134;
    }
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v72,
      "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
      2814);
    v60 = (__int64 *)CallStackTracing::s_wpInstance;
    D3D11ShaderPostTempSample = -2147467259;
    if ( !CallStackTracing::s_wpInstance )
    {
      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v61;
      if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v60 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v60 + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
      if ( *((_DWORD *)v62 + 499) != -2147467259 )
        CallStackContext::TraceFailure(
          v62,
          "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
          2814,
          -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_135;
    v59 = 162;
  }
LABEL_134:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v59,
    &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
    this,
    -2147467259);
LABEL_135:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
LABEL_136:
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v72,
    "CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture",
    2854);
  v68 = byte_180153DE0;
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
  {
    WPP_SF_qDdddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      v66,
      v67,
      this,
      D3D11ShaderPostTempSample,
      v77,
      v76.m128i_i32[1],
      v76.m128i_i32[2],
      v18,
      v81,
      DWORD1(v81),
      DWORD2(v81),
      HIDWORD(v81));
    v68 = byte_180153DE0;
  }
  if ( D3D11ShaderPostTempSample < 0 && !v2 )
  {
    if ( (unsigned __int8)v68 >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 169, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    v69 = *((_QWORD *)this + 2);
    v70 = -(__int64)(*(_DWORD *)(v69 + 920) != 0) & 0xFFFFFFFFFFFFFFF0uLL;
    D3D11ShaderPostTempSample = CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample(
                                  this,
                                  *(_DWORD *)(v69 + 1208),
                                  *(_DWORD *)(v70 + v69 + 96) - *(_DWORD *)(v70 + v69 + 88),
                                  *(_DWORD *)(v70 + v69 + 100) - *(_DWORD *)(v70 + v69 + 92));
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 2144LL) )
      CxCodeVideoProcD3D11DataHandler::ConfigureD3D11VideoProcessorRects(this);
    *(_DWORD *)(*((_QWORD *)this + 2) + 120LL) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v72);
  return (unsigned int)D3D11ShaderPostTempSample;
}

```

## disassembly

```asm
0x18003eb08  mov     rax, rsp
0x18003eb0b  push    rbp
0x18003eb0c  push    rbx
0x18003eb0d  push    rsi
0x18003eb0e  push    rdi
0x18003eb0f  push    r12
0x18003eb11  push    r13
0x18003eb13  push    r14
0x18003eb15  push    r15
0x18003eb17  lea     rbp, [rsp-48h]
0x18003eb1c  sub     rsp, 148h
0x18003eb23  movaps  xmmword ptr [rax-58h], xmm6
0x18003eb27  mov     rax, cs:__security_cookie
0x18003eb2e  xor     rax, rsp
0x18003eb31  mov     [rbp+80h+var_60], rax
0x18003eb35  mov     rsi, rcx
0x18003eb38  lea     rdx, [rbp+80h+var_F0]
0x18003eb3c  add     rcx, 0D0h
0x18003eb43  xor     r13b, r13b
0x18003eb46  call    ?ComputeCurrentBounds@CxCodeVideoProcD3DSphereGeometry@@QEAA?AURectF@@XZ; CxCodeVideoProcD3DSphereGeometry::ComputeCurrentBounds(void)
0x18003eb4b  mov     rbx, [rsi+10h]
0x18003eb4f  lea     rdx, [rbp+80h+var_F0]; struct RectF *
0x18003eb53  lea     rcx, [rbp+80h+var_C0]; retstr
0x18003eb57  mov     r9d, [rbx+54h]
0x18003eb5b  mov     r8d, [rbx+50h]
0x18003eb5f  sub     r9d, [rbx+4Ch]; unsigned int
0x18003eb63  sub     r8d, [rbx+48h]; unsigned int
0x18003eb67  call    ?RectFtoRECT@@YA?AUtagRECT@@AEBURectF@@II@Z; RectFtoRECT(RectF const &,uint,uint)
0x18003eb6c  mov     r10d, 2
0x18003eb72  xorps   xmm0, xmm0
0x18003eb75  movups  xmm1, xmmword ptr [rax]
0x18003eb78  movups  [rbp+80h+var_A0], xmm0
0x18003eb7c  mov     r8d, [rbx+50h]
0x18003eb80  mov     r9d, [rbx+54h]
0x18003eb84  mov     ecx, [rbx+518h]
0x18003eb8a  movaps  [rbp+80h+var_F0], xmm1
0x18003eb8e  mov     edi, dword ptr [rbp+80h+var_F0+4]
0x18003eb91  mov     r15d, dword ptr [rbp+80h+var_F0+8]
0x18003eb95  mov     r12d, dword ptr [rbp+80h+var_F0+0Ch]
0x18003eb99  movd    r14d, xmm1
0x18003eb9e  mov     eax, r14d
0x18003eba1  cdq
0x18003eba2  idiv    r10d
0x18003eba5  xor     eax, eax
0x18003eba7  test    edx, edx
0x18003eba9  cmovle  edx, eax
0x18003ebac  mov     eax, edi
0x18003ebae  sub     r14d, edx
0x18003ebb1  cdq
0x18003ebb2  idiv    r10d
0x18003ebb5  xor     eax, eax
0x18003ebb7  mov     [rbp+80h+var_E0], r14d
0x18003ebbb  test    edx, edx
0x18003ebbd  mov     dword ptr [rbp+80h+var_F0], r14d
0x18003ebc1  cmovle  edx, eax
0x18003ebc4  sub     r8d, [rbx+48h]
0x18003ebc8  sub     edi, edx
0x18003ebca  mov     eax, r15d
0x18003ebcd  cdq
0x18003ebce  mov     dword ptr [rbp+80h+var_F0+4], edi
0x18003ebd1  idiv    r10d
0x18003ebd4  mov     eax, r8d
0x18003ebd7  cmp     edx, r8d
0x18003ebda  cmovl   eax, edx
0x18003ebdd  sub     r9d, [rbx+4Ch]
0x18003ebe1  add     r15d, eax
0x18003ebe4  mov     eax, r12d
0x18003ebe7  cdq
0x18003ebe8  mov     dword ptr [rbp+80h+var_F0+8], r15d
0x18003ebec  idiv    r10d
0x18003ebef  mov     eax, r9d
0x18003ebf2  cmp     edx, r9d
0x18003ebf5  cmovl   eax, edx
0x18003ebf8  add     r12d, eax
0x18003ebfb  mov     dword ptr [rbp+80h+var_F0+0Ch], r12d
0x18003ebff  cmp     ecx, 5Ah ; 'Z'
0x18003ec02  jz      loc_18003F498
0x18003ec08  cmp     ecx, 10Eh
0x18003ec0e  jz      loc_18003F498
0x18003ec14  mov     eax, [rbx+164h]
0x18003ec1a  sub     eax, r10d
0x18003ec1d  cmp     eax, 1
0x18003ec20  jbe     loc_18003F498
0x18003ec26  lea     rax, [rbp+80h+var_A0]
0x18003ec2a  mov     [rsp+180h+var_158], rbx
0x18003ec2f  lea     rdx, [rbp+80h+var_F0]
0x18003ec33  mov     [rsp+180h+var_160], rax
0x18003ec38  call    ?DestinationSpaceToSourceSpace@@YAXW4_MFVideoRotationFormat@@AEBUtagRECT@@IIPEAU2@PEAUxvpDataHandlerState@@@Z; DestinationSpaceToSourceSpace(_MFVideoRotationFormat,tagRECT const &,uint,uint,tagRECT *,xvpDataHandlerState *)
0x18003ec3d  mov     rcx, [rsi+10h]
0x18003ec41  mov     eax, [rcx+360h]
0x18003ec47  cmp     eax, 2
0x18003ec4a  jnz     loc_18003F329
0x18003ec50  cmp     dword ptr [rcx+860h], 0
0x18003ec57  jz      loc_18003F3E5
0x18003ec5d  mov     rcx, [rsi+910h]
0x18003ec64  lea     rdx, [rbp+80h+var_A0]
0x18003ec68  mov     [rsp+180h+var_160], rdx
0x18003ec6d  xor     ebx, ebx
0x18003ec6f  mov     rdx, [rsi+930h]
0x18003ec76  xor     r8d, r8d
0x18003ec79  mov     rax, [rcx]
0x18003ec7c  lea     r13d, [rbx+1]
0x18003ec80  mov     r9d, r13d
0x18003ec83  mov     rax, [rax+0F0h]
0x18003ec8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ec8f  mov     rcx, [rsi+910h]
0x18003ec96  lea     rdx, [rbp+80h+var_B0]
0x18003ec9a  movaps  xmm6, [rbp+80h+var_F0]
0x18003ec9e  mov     r12d, r15d
0x18003eca1  movdqa  xmmword ptr [rbp+80h+var_B0.cx], xmm6
0x18003eca6  sub     r12d, r14d
0x18003eca9  mov     rax, qword ptr [rbp+80h+var_B0.cx]
0x18003ecad  mov     r9d, r13d
0x18003ecb0  shr     rax, 20h
0x18003ecb4  xor     r8d, r8d
0x18003ecb7  sub     [rbp+80h+var_B0.cy+8], eax
0x18003ecba  mov     [rbp+80h+var_B0.cx+8], r12d
0x18003ecbe  mov     qword ptr [rbp+80h+var_B0.cx], rbx
0x18003ecc2  mov     rax, [rcx]
0x18003ecc5  mov     [rsp+180h+var_160], rdx
0x18003ecca  mov     rdx, [rsi+930h]
0x18003ecd1  mov     rax, [rax+0F8h]
0x18003ecd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecdd  mov     rcx, [rsi+910h]
0x18003ece4  lea     r9, [rbp+80h+var_B0]
0x18003ece8  mov     rdx, [rsi+930h]
0x18003ecef  mov     r8d, r13d
0x18003ecf2  mov     rax, [rcx]
0x18003ecf5  mov     rax, [rax+68h]
0x18003ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ecfe  lea     r14, aCxcodevideopro_110; "CxCodeVideoProcD3D11DataHandler::Update"...
0x18003ed05  mov     r8d, 0AF4h; int
0x18003ed0b  mov     rdx, r14; char *
0x18003ed0e  lea     rcx, [rsp+180h+var_110]; this
0x18003ed13  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ed18  cmp     cs:byte_180153DE0, 20h ; ' '
0x18003ed1f  lea     r15, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18003ed26  jb      short loc_18003ED7E
0x18003ed28  mov     eax, [rbp+80h+var_B0.cy+8]
0x18003ed2b  mov     edx, 0A0h
0x18003ed30  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed37  mov     r9, rsi
0x18003ed3a  mov     [rsp+180h+var_128], eax
0x18003ed3e  mov     r8, r15
0x18003ed41  mov     eax, [rbp+80h+var_B0.cx+8]
0x18003ed44  mov     [rsp+180h+var_130], eax
0x18003ed48  mov     eax, [rbp+80h+var_B0.cy]
0x18003ed4b  mov     rcx, [rcx+150h]
0x18003ed52  mov     [rsp+180h+var_138], eax
0x18003ed56  mov     eax, [rbp+80h+var_B0.cx]
0x18003ed59  mov     [rsp+180h+var_140], eax
0x18003ed5d  mov     eax, dword ptr [rbp+80h+var_A0+0Ch]
0x18003ed60  mov     [rsp+180h+var_148], eax
0x18003ed64  mov     eax, dword ptr [rbp+80h+var_A0+8]
0x18003ed67  mov     [rsp+180h+var_150], eax
0x18003ed6b  mov     eax, dword ptr [rbp+80h+var_A0+4]
0x18003ed6e  mov     dword ptr [rsp+180h+var_158], eax
0x18003ed72  mov     eax, dword ptr [rbp+80h+var_A0]
0x18003ed75  mov     dword ptr [rsp+180h+var_160], eax
0x18003ed79  call    WPP_SF_qdddddddd
0x18003ed7e  lea     rcx, [rsp+180h+var_110]; this
0x18003ed83  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003ed88  mov     rax, [rsi+10h]
0x18003ed8c  mov     [rsp+180h+var_10F], r13b
0x18003ed91  mov     [rax+78h], r13d
0x18003ed95  mov     rax, [rsi+10h]
0x18003ed99  movups  xmm0, [rbp+80h+var_A0]
0x18003ed9d  movdqu  xmmword ptr [rax+68h], xmm0
0x18003eda2  mov     r13, [rsi+490h]
0x18003eda9  xor     eax, eax
0x18003edab  xorps   xmm0, xmm0
0x18003edae  mov     qword ptr [rbp+80h+var_100], rax
0x18003edb2  mov     [rsp+180h+var_108], rax
0x18003edb7  movups  xmmword ptr [rbp+80h+var_80], xmm0
0x18003edbb  movups  xmmword ptr [rbp+80h+var_80+0Ch], xmm0
0x18003edbf  movups  xmmword ptr [rbp+80h+var_90], xmm0
0x18003edc3  test    r13, r13
0x18003edc6  jz      loc_18003EFAD
0x18003edcc  mov     edi, 0B0Ch
0x18003edd1  lea     rcx, [rsp+180h+var_110]; this
0x18003edd6  mov     r8d, edi; int
0x18003edd9  mov     rdx, r14; char *
0x18003eddc  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ede1  lea     rcx, [rbp+80h+var_100]
0x18003ede5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003edea  mov     rcx, [rsi+490h]; this
0x18003edf1  lea     r8, [rbp+80h+var_100]; unsigned int
0x18003edf5  xor     edx, edx; struct IMFSample *
0x18003edf7  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x18003edfc  mov     ebx, eax
0x18003edfe  test    eax, eax
0x18003ee00  jns     loc_18003EECA
0x18003ee06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee0d  test    rcx, rcx
0x18003ee10  jnz     short loc_18003EE53
0x18003ee12  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ee18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee1f  mov     rcx, rax
0x18003ee22  test    rax, rax
0x18003ee25  jz      short loc_18003EE45
0x18003ee27  mov     rax, [rax]
0x18003ee2a  mov     edx, 7F0h
0x18003ee2f  mov     rax, [rax+8]
0x18003ee33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee38  test    eax, eax
0x18003ee3a  jz      short loc_18003EE45
0x18003ee3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee43  jmp     short loc_18003EE53
0x18003ee45  lea     rcx, qword_180153440; this
0x18003ee4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee53  cmp     byte ptr [rcx+8], 0
0x18003ee57  jz      short loc_18003EE77
0x18003ee59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ee5e  cmp     [rax+7CCh], ebx
0x18003ee64  jz      short loc_18003EE77
0x18003ee66  mov     r9d, ebx; int
0x18003ee69  mov     r8d, edi; int
0x18003ee6c  mov     rdx, r14; char *
0x18003ee6f  mov     rcx, rax; this
0x18003ee72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ee77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ee7e  jb      short loc_18003EE9F
0x18003ee80  mov     edx, 0A3h
0x18003ee85  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee8c  mov     r9, rsi
0x18003ee8f  mov     r8, r15
0x18003ee92  mov     dword ptr [rsp+180h+var_160], ebx
0x18003ee96  mov     rcx, [rcx+10h]
0x18003ee9a  call    WPP_SF_qD
0x18003ee9f  lea     rcx, [rsp+180h+var_110]; this
0x18003eea4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003eea9  lea     rcx, [rsp+180h+var_108]
0x18003eeae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003eeb3  lea     rcx, [rbp+80h+var_100]
0x18003eeb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003eebc  mov     r12d, dword ptr [rbp+80h+var_F0+0Ch]
0x18003eec0  mov     r13b, [rsp+180h+var_10F]
0x18003eec5  jmp     loc_18003F58D
0x18003eeca  mov     rdi, qword ptr [rbp+80h+var_100]
0x18003eece  lea     rcx, [rsp+180h+var_108]
0x18003eed3  mov     rax, [rdi]
0x18003eed6  mov     rbx, [rax+18h]
0x18003eeda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003eedf  lea     r8, [rsp+180h+var_108]
0x18003eee4  mov     rcx, rdi
0x18003eee7  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x18003eeee  mov     rax, rbx
0x18003eef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eef6  mov     ebx, eax
0x18003eef8  test    eax, eax
0x18003eefa  jns     loc_18003EF8B
0x18003ef00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef07  test    rcx, rcx
0x18003ef0a  jnz     short loc_18003EF4D
0x18003ef0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ef12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef19  mov     rcx, rax
0x18003ef1c  test    rax, rax
0x18003ef1f  jz      short loc_18003EF3F
0x18003ef21  mov     rax, [rax]
0x18003ef24  mov     edx, 7F0h
0x18003ef29  mov     rax, [rax+8]
0x18003ef2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef32  test    eax, eax
0x18003ef34  jz      short loc_18003EF3F
0x18003ef36  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef3d  jmp     short loc_18003EF4D
0x18003ef3f  lea     rcx, qword_180153440; this
0x18003ef46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef4d  cmp     byte ptr [rcx+8], 0
0x18003ef51  jz      short loc_18003EF74
0x18003ef53  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ef58  cmp     [rax+7CCh], ebx
0x18003ef5e  jz      short loc_18003EF74
0x18003ef60  mov     r9d, ebx; int
0x18003ef63  mov     r8d, 0B0Dh; int
0x18003ef69  mov     rdx, r14; char *
0x18003ef6c  mov     rcx, rax; this
0x18003ef6f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ef74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ef7b  jb      loc_18003EE9F
0x18003ef81  mov     edx, 0A4h
0x18003ef86  jmp     loc_18003EE85
0x18003ef8b  mov     rcx, [rsp+180h+var_108]
0x18003ef90  lea     rdx, [rbp+80h+var_90]
0x18003ef94  mov     rax, [rcx]
0x18003ef97  mov     rax, [rax+50h]
0x18003ef9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efa0  lea     rcx, [rsp+180h+var_110]; this
0x18003efa5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003efaa  mov     edi, dword ptr [rbp+80h+var_F0+4]
0x18003efad  cmp     qword ptr [rsi+490h], 0
0x18003efb5  mov     edx, [rbp+80h+var_90+4]
0x18003efb8  mov     ecx, [rbp+80h+var_90]
0x18003efbb  jz      short loc_18003EFCF
0x18003efbd  cmp     r12d, ecx
0x18003efc0  ja      short loc_18003EFCF
0x18003efc2  mov     eax, dword ptr [rbp+80h+var_F0+0Ch]
0x18003efc5  sub     eax, edi
0x18003efc7  cmp     eax, edx
  ... truncated ...
```
