# CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources(void)

- ea: `0x18004e5f0`
- end: `0x18004f52a`
- name: `?CreateD3DShaderResources@CxCodeVideoProcD3D11DataHandler@@EEAAJXZ`
- size: `3898`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005ddb0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18003d0d4`
- `0x18004823c`
- `0x18004d904`
- `0x18004e5f0`
- `0x180054140`
- `0x180054ee4`
- `0x180065fd0`
- `0x180066510`
- `0x180069150`
- `0x1800696bc`
- `0x18006a1a4`
- `0x18006bf70`
- `0x18006d05c`
- `0x18007005c`
- `0x180070600`
- `0x1800717b0`
- `0x180071cd4`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e67c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e8ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e978`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ea1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ead5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ec3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ed0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eda8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ee45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ef65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f04e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f176`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f247`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f3be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e67c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e8ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e978`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ea1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ead5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ec3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ed0b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004eda8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ee45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ef65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f04e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f176`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f247`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f3be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f467`

## string_xrefs

- `0x18004e620`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004efbc`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004f0a5`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004f1cd`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004f29e`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004f415`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`
- `0x18004f4be`: `CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources(CxCodeVideoProcD3D11DataHandler *this)
{
  __int64 v2; // rcx
  unsigned int MiscFlagsForOutputTexture; // eax
  int D3D11ShaderTempSamples; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  char *v10; // rbx
  __int64 v11; // r8
  LONG *v12; // rdx
  char *v13; // r9
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rax
  struct tagSIZE v23; // xmm0_8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  struct tagRECT *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 *v38; // rcx
  struct tagSIZE *v39; // rdx
  __int64 v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  struct tagRECT *v45; // rdx
  struct CxCodeVideoProcD3DGeometry *v46; // r8
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, __int64 *, __int64, _QWORD, char *); // rbx
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  __int64 v61; // rsi
  __int64 (__fastcall *v62)(__int64, _DWORD *, __int64, __int64 *, __int64, char *); // rdi
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdi
  __int64 (__fastcall *v68)(__int64, _DWORD *, char *); // rbx
  __int64 *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  __int64 v72; // rsi
  __int64 (__fastcall *v73)(__int64, _DWORD *, char *); // rdi
  __int64 *v74; // rcx
  CallStackTracing *v75; // rax
  struct CallStackContext *v76; // rax
  __int64 v77; // rdi
  void (__fastcall *v78)(__int64, _DWORD *, char *); // rbx
  __int64 v79; // rbx
  int v80; // edi
  int v81; // eax
  __int64 v82; // rdi
  __int64 (__fastcall *v83)(__int64, _BYTE *, char *); // rbx
  __int64 *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  __int64 *v87; // rcx
  CallStackTracing *v88; // rax
  struct CallStackContext *v89; // rax
  _BYTE v91[16]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSIZE v92; // [rsp+50h] [rbp-B0h] BYREF
  int v93; // [rsp+58h] [rbp-A8h]
  struct tagRECT v94; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v95[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v96[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v97; // [rsp+B8h] [rbp-48h]
  int v98; // [rsp+BCh] [rbp-44h]
  int v99; // [rsp+C0h] [rbp-40h]
  int v100; // [rsp+C4h] [rbp-3Ch]
  int v101; // [rsp+C8h] [rbp-38h]
  int v102; // [rsp+CCh] [rbp-34h]
  int v103; // [rsp+D0h] [rbp-30h]
  char v104; // [rsp+D4h] [rbp-2Ch]

  v2 = *((_QWORD *)this + 2);
  *(_QWORD *)&v94.left = 0;
  v94.right = *(_DWORD *)(v2 + 52);
  v94.bottom = *(_DWORD *)(v2 + 48);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v91,
    "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
    2931);
  MiscFlagsForOutputTexture = CxCodeVideoProcD3D11DataHandler::GetMiscFlagsForOutputTexture(this);
  D3D11ShaderTempSamples = CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples(
                             this,
                             MiscFlagsForOutputTexture);
  if ( D3D11ShaderTempSamples < 0 )
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != D3D11ShaderTempSamples )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
          2934,
          D3D11ShaderTempSamples);
    }
    if ( g_wppLevels )
    {
      v8 = 177;
LABEL_207:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        D3D11ShaderTempSamples);
      goto LABEL_208;
    }
    goto LABEL_208;
  }
  if ( ExpensiveShader((const struct FallbackShaderCaps *)(*((_QWORD *)this + 2) + 996LL)) )
  {
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        178,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        *(_DWORD *)(v9 + 1260));
    v10 = (char *)this + 144;
    CxCodeVideoProcD3DSlicedFlatGeometry::SetSlices(
      (CxCodeVideoProcD3D11DataHandler *)((char *)this + 144),
      *(_DWORD *)(*((_QWORD *)this + 2) + 1260LL));
  }
  else
  {
    v10 = (char *)this + 144;
  }
  if ( ExpensiveShader((const struct FallbackShaderCaps *)(*((_QWORD *)this + 2) + 1096LL)) )
  {
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        179,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        *(_DWORD *)(v11 + 1260));
    CxCodeVideoProcD3DSlicedFlatGeometry::SetSlices(
      (CxCodeVideoProcD3D11DataHandler *)((char *)this + 72),
      *(_DWORD *)(*((_QWORD *)this + 2) + 1260LL));
  }
  v12 = (LONG *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 17) = v10;
  *((_QWORD *)this + 267) = (char *)this + 1912;
  if ( v12[187] )
  {
    v13 = (char *)this + 208;
    if ( v12[215] == 1 )
    {
      v14 = MFD3D::D3DCbufferWrapper<_stD3D11ReprojectGlobals>::operator->((char *)this + 688, v12, v11, v13);
      MFD3D::D3DCbufferWrapper<_stD3D11ReprojectGlobals>::operator->(v16, v15, v14 + 16, v17);
      CxCodeVideoProcD3DSphereGeometry::GetReprojectParams(v18);
      MFD3D::D3D11CbufferWrapperImpl::create(
        (CxCodeVideoProcD3D11DataHandler *)((char *)this + 2168),
        *((struct ID3D11Device **)this + 285),
        (CxCodeVideoProcD3D11DataHandler *)((char *)this + 688));
    }
    else
    {
      *((_QWORD *)this + 17) = v13;
      *((_QWORD *)this + 267) = (char *)this + 2032;
      v92.cx = v12[101];
      v92.cy = v12[100];
      CxCodeVideoProcD3DSphereGeometry::SetFrame((CxCodeVideoProcD3D11DataHandler *)((char *)this + 208), &v92);
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 752LL) )
  {
    D3D11ShaderTempSamples = MFD3D::D3D11CbufferWrapperImpl::create(
                               (CxCodeVideoProcD3D11DataHandler *)((char *)this + 2216),
                               *((struct ID3D11Device **)this + 285),
                               (CxCodeVideoProcD3D11DataHandler *)((char *)this + 1072));
    if ( D3D11ShaderTempSamples < 0 )
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v21,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            2972,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 180;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
    v22 = *((_QWORD *)this + 2);
    v23 = *(struct tagSIZE *)(v22 + 756);
    LODWORD(v22) = *(_DWORD *)(v22 + 764);
    v92 = v23;
    v93 = v22;
    D3D11ShaderTempSamples = CxCodeVideoProcD3DDataHandler::UpdateD3DOutsideModeParams(this, &v92);
    if ( D3D11ShaderTempSamples < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v26,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            2973,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 181;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
    D3D11ShaderTempSamples = MFD3D::D3D11CbufferWrapperImpl::update(
                               (CxCodeVideoProcD3D11DataHandler *)((char *)this + 2216),
                               *((struct ID3D11Device **)this + 285));
    if ( D3D11ShaderTempSamples < 0 )
    {
      v27 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v29,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            2974,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 182;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 992LL) )
  {
    D3D11ShaderTempSamples = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 16LL))(*((_QWORD *)this + 17));
    if ( D3D11ShaderTempSamples < 0 )
    {
      v30 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
        if ( *((_DWORD *)v32 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v32,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            2979,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 183;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
    v33 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v33 + 864) == 3 )
      v34 = (struct tagRECT *)(v33 + 72);
    else
      v34 = &v94;
    CxCodeVideoProcD3DDataHandler::SetD3DShaderSrcRect(this, v34, *((struct CxCodeVideoProcD3DGeometry **)this + 17));
    v35 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v35 + 1304) && *(_DWORD *)(v35 + 920) )
    {
      v36 = **((_QWORD **)this + 17);
    }
    else
    {
      v36 = **((_QWORD **)this + 17);
      v92.cx = 0;
    }
    (*(void (**)(void))(v36 + 32))();
    v37 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v37 + 1312) && *(_DWORD *)(v37 + 920) )
    {
      v38 = (__int64 *)*((_QWORD *)this + 17);
      v39 = (struct tagSIZE *)(v37 + 980);
      v40 = *v38;
    }
    else
    {
      v38 = (__int64 *)*((_QWORD *)this + 17);
      v39 = &v92;
      v40 = *v38;
      v92.cx = 0;
    }
    (*(void (__fastcall **)(__int64 *, struct tagSIZE *))(v40 + 40))(v38, v39);
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 988LL) )
  {
    D3D11ShaderTempSamples = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 16LL))((char *)this + 72);
    if ( D3D11ShaderTempSamples < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v43,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            3011,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 184;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
    v44 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v44 + 864) == 1 )
    {
      v45 = (struct tagRECT *)(v44 + 72);
      v46 = (CxCodeVideoProcD3D11DataHandler *)((char *)this + 72);
    }
    else
    {
      v46 = (struct CxCodeVideoProcD3DGeometry *)*((_QWORD *)this + 17);
      v45 = &v94;
    }
    CxCodeVideoProcD3DDataHandler::SetD3DShaderSrcRect(this, v45, v46);
    D3D11ShaderTempSamples = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 9) + 24LL))((char *)this + 72);
    if ( D3D11ShaderTempSamples < 0 )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
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
        if ( *((_DWORD *)v49 + 499) != D3D11ShaderTempSamples )
          CallStackContext::TraceFailure(
            v49,
            "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
            3023,
            D3D11ShaderTempSamples);
      }
      if ( g_wppLevels )
      {
        v8 = 185;
        goto LABEL_207;
      }
      goto LABEL_208;
    }
  }
  D3D11ShaderTempSamples = CxCodeVideoProcD3D11DataHandler::ConfigureLUTGeneration(this);
  if ( D3D11ShaderTempSamples >= 0 )
  {
    D3D11ShaderTempSamples = CxCodeVideoProcD3D11DataHandler::ConfigureD3D11ColorConversionShader(this);
    if ( D3D11ShaderTempSamples >= 0 )
    {
      if ( !*((_QWORD *)this + 284) )
      {
        v56 = *((_QWORD *)this + 285);
        *(_QWORD *)v95 = "POSITION";
        v95[2] = 0;
        *(_QWORD *)&v95[8] = "TEXCOORD";
        *(_QWORD *)&v95[3] = 2;
        *(_QWORD *)&v95[5] = 0;
        v95[7] = 0;
        v95[10] = 0;
        *(_QWORD *)&v95[11] = 16;
        *(_QWORD *)&v95[13] = 16;
        v95[15] = 0;
        v57 = *(__int64 (__fastcall **)(__int64, __int64 *, __int64, _QWORD, char *))(*(_QWORD *)v56 + 96LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2272);
        D3D11ShaderTempSamples = v57(v56, qword_1800E0770, 1284, 0, (char *)this + 2272);
        if ( D3D11ShaderTempSamples < 0 )
        {
          v58 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v59;
            if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
            {
              v58 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v58 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v58 + 8) )
          {
            v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
            if ( *((_DWORD *)v60 + 499) != D3D11ShaderTempSamples )
              CallStackContext::TraceFailure(
                v60,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
                3043,
                D3D11ShaderTempSamples);
          }
          if ( g_wppLevels )
          {
            v8 = 188;
            goto LABEL_207;
          }
          goto LABEL_208;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2264);
        v61 = *((_QWORD *)this + 285);
        v62 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, __int64 *, __int64, char *))(*(_QWORD *)v61 + 88LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2264);
        D3D11ShaderTempSamples = v62(v61, v95, 2, qword_1800E0770, 1284, (char *)this + 2264);
        if ( D3D11ShaderTempSamples < 0 )
        {
          v63 = (__int64 *)CallStackTracing::s_wpInstance;
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
            v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
            if ( *((_DWORD *)v65 + 499) != D3D11ShaderTempSamples )
              CallStackContext::TraceFailure(
                v65,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
                3045,
                D3D11ShaderTempSamples);
          }
          if ( g_wppLevels )
          {
            v8 = 189;
            goto LABEL_207;
          }
          goto LABEL_208;
        }
      }
      if ( !*((_QWORD *)this + 212) )
      {
        v66 = *((_QWORD *)this + 2);
        memset(v95, 0, 52);
        if ( *(_DWORD *)(v66 + 860) == 1 )
        {
          *(_QWORD *)&v95[1] = 0x100000001LL;
          v95[3] = 1;
        }
        else
        {
          *(_QWORD *)&v95[1] = 0x300000003LL;
          v95[3] = 3;
        }
        v67 = *((_QWORD *)this + 285);
        v95[0] = 21;
        v95[12] = 2139095039;
        v68 = *(__int64 (__fastcall **)(__int64, _DWORD *, char *))(*(_QWORD *)v67 + 184LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1696);
        D3D11ShaderTempSamples = v68(v67, v95, (char *)this + 1696);
        if ( D3D11ShaderTempSamples < 0 )
        {
          v69 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v70;
            if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
            {
              v69 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v69 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v69 + 8) )
          {
            v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
            if ( *((_DWORD *)v71 + 499) != D3D11ShaderTempSamples )
              CallStackContext::TraceFailure(
                v71,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
                3068,
                D3D11ShaderTempSamples);
          }
          if ( g_wppLevels )
          {
            v8 = 190;
            goto LABEL_207;
          }
          goto LABEL_208;
        }
        v72 = *((_QWORD *)this + 285);
        v95[0] = 0;
        v73 = *(__int64 (__fastcall **)(__int64, _DWORD *, char *))(*(_QWORD *)v72 + 184LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1704);
        D3D11ShaderTempSamples = v73(v72, v95, (char *)this + 1704);
        if ( D3D11ShaderTempSamples < 0 )
        {
          v74 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v75 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v75;
            if ( v75 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v75 + 8LL))(v75, 2032) )
            {
              v74 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v74 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v74 + 8) )
          {
            v76 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v74);
            if ( *((_DWORD *)v76 + 499) != D3D11ShaderTempSamples )
              CallStackContext::TraceFailure(
                v76,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
                3070,
                D3D11ShaderTempSamples);
          }
          if ( g_wppLevels )
          {
            v8 = 191;
            goto LABEL_207;
          }
          goto LABEL_208;
        }
      }
      if ( !*((_QWORD *)this + 214) )
      {
        v77 = *((_QWORD *)this + 285);
        v95[5] = 0;
        v95[0] = 3;
        *(_OWORD *)&v95[1] = 1u;
        *(__m128i *)&v95[6] = _mm_load_si128((const __m128i *)&_xmm);
        v78 = *(void (__fastcall **)(__int64, _DWORD *, char *))(*(_QWORD *)v77 + 176LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1712);
        v78(v77, v95, (char *)this + 1712);
      }
      if ( *((_QWORD *)this + 215) || (v79 = *((_QWORD *)this + 2), v80 = *(_DWORD *)(v79 + 1316), v80 == 2) )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1720);
      }
      else
      {
        memset_0(v96, 0, 0x108u);
        v97 = 1;
        v100 = 1;
        v103 = 1;
        v81 = *(_DWORD *)(v79 + 1320);
        v98 = v80;
        v82 = *((_QWORD *)this + 285);
        v99 = v81;
        v102 = 1;
        v104 = 15;
        v101 = 1;
        v83 = *(__int64 (__fastcall **)(__int64, _BYTE *, char *))(*(_QWORD *)v82 + 160LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1720);
        D3D11ShaderTempSamples = v83(v82, v96, (char *)this + 1720);
        if ( D3D11ShaderTempSamples < 0 )
        {
          v84 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v85;
            if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
            {
              v84 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v84 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v84 + 8) )
          {
            v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
            if ( *((_DWORD *)v86 + 499) != D3D11ShaderTempSamples )
              CallStackContext::TraceFailure(
                v86,
                "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
                3112,
                D3D11ShaderTempSamples);
          }
          if ( g_wppLevels )
          {
            v8 = 192;
            goto LABEL_207;
          }
          goto LABEL_208;
        }
      }
      D3D11ShaderTempSamples = CxCodeVideoProcD3D11DataHandler::GenerateLUT(this);
      if ( D3D11ShaderTempSamples < 0 )
      {
        v87 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v88 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v88;
          if ( v88 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v88 + 8LL))(v88, 2032) )
          {
            v87 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v87 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v87 + 8) )
        {
          v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v87);
          if ( *((_DWORD *)v89 + 499) != D3D11ShaderTempSamples )
            CallStackContext::TraceFailure(
              v89,
              "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
              3120,
              D3D11ShaderTempSamples);
        }
        if ( g_wppLevels )
        {
          v8 = 193;
          goto LABEL_207;
        }
      }
      goto LABEL_208;
    }
    v53 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v54;
      if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
      {
        v53 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v53 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v53 + 8) )
    {
      v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
      if ( *((_DWORD *)v55 + 499) != D3D11ShaderTempSamples )
        CallStackContext::TraceFailure(
          v55,
          "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
          3030,
          D3D11ShaderTempSamples);
    }
    if ( g_wppLevels )
    {
      v8 = 187;
      goto LABEL_207;
    }
  }
  else
  {
    v50 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v52 + 499) != D3D11ShaderTempSamples )
        CallStackContext::TraceFailure(
          v52,
          "CxCodeVideoProcD3D11DataHandler::CreateD3DShaderResources",
          3027,
          D3D11ShaderTempSamples);
    }
    if ( g_wppLevels )
    {
      v8 = 186;
      goto LABEL_207;
    }
  }
LABEL_208:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v91);
  return (unsigned int)D3D11ShaderTempSamples;
}

```

## disassembly

```asm
0x18004e5f0  push    rbp
0x18004e5f2  push    rbx
0x18004e5f3  push    rsi
0x18004e5f4  push    rdi
0x18004e5f5  push    r12
0x18004e5f7  push    r13
0x18004e5f9  push    r14
0x18004e5fb  push    r15
0x18004e5fd  lea     rbp, [rsp-0D8h]
0x18004e605  sub     rsp, 1D8h
0x18004e60c  mov     rax, cs:__security_cookie
0x18004e613  xor     rax, rsp
0x18004e616  mov     [rbp+110h+var_50], rax
0x18004e61d  mov     r14, rcx
0x18004e620  lea     rsi, aCxcodevideopro_138; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18004e627  mov     rcx, [rcx+10h]
0x18004e62b  xor     r13d, r13d
0x18004e62e  mov     r8d, 0B73h; int
0x18004e634  mov     qword ptr [rsp+210h+var_1B0.left], r13
0x18004e639  mov     rdx, rsi; char *
0x18004e63c  mov     eax, [rcx+34h]
0x18004e63f  mov     [rsp+210h+var_1B0.right], eax
0x18004e643  mov     eax, [rcx+30h]
0x18004e646  lea     rcx, [rsp+210h+var_1D0]; this
0x18004e64b  mov     [rsp+210h+var_1B0.bottom], eax
0x18004e64f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004e654  mov     rcx, r14; this
0x18004e657  call    ?GetMiscFlagsForOutputTexture@CxCodeVideoProcD3D11DataHandler@@AEAAIXZ; CxCodeVideoProcD3D11DataHandler::GetMiscFlagsForOutputTexture(void)
0x18004e65c  mov     edx, eax; unsigned int
0x18004e65e  mov     rcx, r14; this
0x18004e661  call    ?CreateD3D11ShaderTempSamples@CxCodeVideoProcD3D11DataHandler@@AEAAJI@Z; CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples(uint)
0x18004e666  mov     ebx, eax
0x18004e668  test    eax, eax
0x18004e66a  jns     loc_18004E708
0x18004e670  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e677  test    rcx, rcx
0x18004e67a  jnz     short loc_18004E6BD
0x18004e67c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e682  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e689  mov     rcx, rax
0x18004e68c  test    rax, rax
0x18004e68f  jz      short loc_18004E6AF
0x18004e691  mov     rax, [rax]
0x18004e694  mov     edx, 7F0h
0x18004e699  mov     rax, [rax+8]
0x18004e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6a2  test    eax, eax
0x18004e6a4  jz      short loc_18004E6AF
0x18004e6a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6ad  jmp     short loc_18004E6BD
0x18004e6af  lea     rcx, qword_180153440; this
0x18004e6b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e6bd  cmp     [rcx+8], r13b
0x18004e6c1  jz      short loc_18004E6E4
0x18004e6c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e6c8  cmp     [rax+7CCh], ebx
0x18004e6ce  jz      short loc_18004E6E4
0x18004e6d0  mov     r9d, ebx; int
0x18004e6d3  mov     r8d, 0B76h; int
0x18004e6d9  mov     rdx, rsi; char *
0x18004e6dc  mov     rcx, rax; this
0x18004e6df  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e6e4  mov     r15d, 1
0x18004e6ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004e6f1  jb      loc_18004F4FB
0x18004e6f7  mov     edx, 0B1h
0x18004e6fc  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18004e703  jmp     loc_18004F4E4
0x18004e708  mov     r8, [r14+10h]
0x18004e70c  lea     rcx, [r8+3E4h]; struct FallbackShaderCaps *
0x18004e713  call    ?ExpensiveShader@@YA_NAEBUFallbackShaderCaps@@@Z; ExpensiveShader(FallbackShaderCaps const &)
0x18004e718  lea     r12, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18004e71f  test    al, al
0x18004e721  jz      short loc_18004E770
0x18004e723  cmp     cs:byte_180153DE0, 20h ; ' '
0x18004e72a  jb      short loc_18004E755
0x18004e72c  mov     eax, [r8+4ECh]
0x18004e733  mov     edx, 0B2h
0x18004e738  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e73f  mov     r9, r14
0x18004e742  mov     r8, r12
0x18004e745  mov     dword ptr [rsp+210h+var_1F0], eax
0x18004e749  mov     rcx, [rcx+150h]
0x18004e750  call    WPP_SF_qD
0x18004e755  mov     rdx, [r14+10h]
0x18004e759  lea     rbx, [r14+90h]
0x18004e760  mov     rcx, rbx; this
0x18004e763  mov     edx, [rdx+4ECh]; unsigned int
0x18004e769  call    ?SetSlices@CxCodeVideoProcD3DSlicedFlatGeometry@@QEAAJI@Z; CxCodeVideoProcD3DSlicedFlatGeometry::SetSlices(uint)
0x18004e76e  jmp     short loc_18004E777
0x18004e770  lea     rbx, [r14+90h]
0x18004e777  mov     r8, [r14+10h]
0x18004e77b  lea     rcx, [r8+448h]; struct FallbackShaderCaps *
0x18004e782  call    ?ExpensiveShader@@YA_NAEBUFallbackShaderCaps@@@Z; ExpensiveShader(FallbackShaderCaps const &)
0x18004e787  test    al, al
0x18004e789  jz      short loc_18004E7D0
0x18004e78b  cmp     cs:byte_180153DE0, 20h ; ' '
0x18004e792  jb      short loc_18004E7BD
0x18004e794  mov     eax, [r8+4ECh]
0x18004e79b  mov     edx, 0B3h
0x18004e7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e7a7  mov     r9, r14
0x18004e7aa  mov     r8, r12
0x18004e7ad  mov     dword ptr [rsp+210h+var_1F0], eax
0x18004e7b1  mov     rcx, [rcx+150h]
0x18004e7b8  call    WPP_SF_qD
0x18004e7bd  mov     rdx, [r14+10h]
0x18004e7c1  lea     rcx, [r14+48h]; this
0x18004e7c5  mov     edx, [rdx+4ECh]; unsigned int
0x18004e7cb  call    ?SetSlices@CxCodeVideoProcD3DSlicedFlatGeometry@@QEAAJI@Z; CxCodeVideoProcD3DSlicedFlatGeometry::SetSlices(uint)
0x18004e7d0  mov     rdx, [r14+10h]
0x18004e7d4  lea     rax, [r14+778h]
0x18004e7db  mov     [r14+88h], rbx
0x18004e7e2  mov     r15d, 1
0x18004e7e8  mov     [r14+858h], rax
0x18004e7ef  cmp     [rdx+2ECh], r13d
0x18004e7f6  jz      short loc_18004E876
0x18004e7f8  lea     r9, [r14+0D0h]
0x18004e7ff  cmp     [rdx+35Ch], r15d
0x18004e806  jnz     short loc_18004E840
0x18004e808  lea     rbx, [r14+2B0h]
0x18004e80f  mov     rcx, rbx
0x18004e812  call    ??C?$D3DCbufferWrapper@U_stD3D11ReprojectGlobals@@@MFD3D@@QEAAPEAU_stD3D11ReprojectGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ReprojectGlobals>::operator->(void)
0x18004e817  lea     r8, [rax+10h]
0x18004e81b  call    ??C?$D3DCbufferWrapper@U_stD3D11ReprojectGlobals@@@MFD3D@@QEAAPEAU_stD3D11ReprojectGlobals@@XZ; MFD3D::D3DCbufferWrapper<_stD3D11ReprojectGlobals>::operator->(void)
0x18004e820  mov     rcx, r9
0x18004e823  call    ?GetReprojectParams@CxCodeVideoProcD3DSphereGeometry@@QEAAXUXMFLOAT2@DirectX@@PEAUXMFLOAT4X4@3@@Z; CxCodeVideoProcD3DSphereGeometry::GetReprojectParams(DirectX::XMFLOAT2,DirectX::XMFLOAT4X4 *)
0x18004e828  mov     rdx, [r14+8E8h]; struct ID3D11Device *
0x18004e82f  lea     rcx, [r14+878h]; this
0x18004e836  mov     r8, rbx; struct MFD3D::D3DCbufferWrapperIface *
0x18004e839  call    ?create@D3D11CbufferWrapperImpl@MFD3D@@QEAAJPEAUID3D11Device@@PEAVD3DCbufferWrapperIface@2@@Z; MFD3D::D3D11CbufferWrapperImpl::create(ID3D11Device *,MFD3D::D3DCbufferWrapperIface *)
0x18004e83e  jmp     short loc_18004E876
0x18004e840  lea     rax, [r14+7F0h]
0x18004e847  mov     [r14+88h], r9
0x18004e84e  mov     [r14+858h], rax
0x18004e855  mov     rcx, r9; this
0x18004e858  mov     eax, [rdx+194h]
0x18004e85e  mov     [rsp+210h+var_1C0.cx], eax
0x18004e862  mov     eax, [rdx+190h]
0x18004e868  lea     rdx, [rsp+210h+var_1C0]; struct tagSIZE *
0x18004e86d  mov     [rsp+210h+var_1C0.cy], eax
0x18004e871  call    ?SetFrame@CxCodeVideoProcD3DSphereGeometry@@QEAAXAEBUtagSIZE@@@Z; CxCodeVideoProcD3DSphereGeometry::SetFrame(tagSIZE const &)
0x18004e876  mov     rax, [r14+10h]
0x18004e87a  cmp     [rax+2F0h], r13d
0x18004e881  jz      loc_18004EA9B
0x18004e887  mov     rdx, [r14+8E8h]; struct ID3D11Device *
0x18004e88e  lea     rdi, [r14+8A8h]
0x18004e895  mov     rcx, rdi; this
0x18004e898  lea     r8, [r14+430h]; struct MFD3D::D3DCbufferWrapperIface *
0x18004e89f  call    ?create@D3D11CbufferWrapperImpl@MFD3D@@QEAAJPEAUID3D11Device@@PEAVD3DCbufferWrapperIface@2@@Z; MFD3D::D3D11CbufferWrapperImpl::create(ID3D11Device *,MFD3D::D3DCbufferWrapperIface *)
0x18004e8a4  mov     ebx, eax
0x18004e8a6  test    eax, eax
0x18004e8a8  jns     loc_18004E939
0x18004e8ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e8b5  test    rcx, rcx
0x18004e8b8  jnz     short loc_18004E8FB
0x18004e8ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e8c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e8c7  mov     rcx, rax
0x18004e8ca  test    rax, rax
0x18004e8cd  jz      short loc_18004E8ED
0x18004e8cf  mov     rax, [rax]
0x18004e8d2  mov     edx, 7F0h
0x18004e8d7  mov     rax, [rax+8]
0x18004e8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8e0  test    eax, eax
0x18004e8e2  jz      short loc_18004E8ED
0x18004e8e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e8eb  jmp     short loc_18004E8FB
0x18004e8ed  lea     rcx, qword_180153440; this
0x18004e8f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e8fb  cmp     [rcx+8], r13b
0x18004e8ff  jz      short loc_18004E922
0x18004e901  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e906  cmp     [rax+7CCh], ebx
0x18004e90c  jz      short loc_18004E922
0x18004e90e  mov     r9d, ebx; int
0x18004e911  mov     r8d, 0B9Ch; int
0x18004e917  mov     rdx, rsi; char *
0x18004e91a  mov     rcx, rax; this
0x18004e91d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e922  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004e929  jb      loc_18004F4FB
0x18004e92f  mov     edx, 0B4h
0x18004e934  jmp     loc_18004F4E1
0x18004e939  mov     rax, [r14+10h]
0x18004e93d  lea     rdx, [rsp+210h+var_1C0]
0x18004e942  mov     rcx, r14
0x18004e945  movsd   xmm0, qword ptr [rax+2F4h]
0x18004e94d  mov     eax, [rax+2FCh]
0x18004e953  movsd   qword ptr [rsp+210h+var_1C0.cx], xmm0
0x18004e959  mov     [rsp+210h+var_1B8], eax
0x18004e95d  call    ?UpdateD3DOutsideModeParams@CxCodeVideoProcD3DDataHandler@@IEAAJU_OutsideModeParameters@@@Z; CxCodeVideoProcD3DDataHandler::UpdateD3DOutsideModeParams(_OutsideModeParameters)
0x18004e962  mov     ebx, eax
0x18004e964  test    eax, eax
0x18004e966  jns     loc_18004E9F7
0x18004e96c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e973  test    rcx, rcx
0x18004e976  jnz     short loc_18004E9B9
0x18004e978  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004e97e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e985  mov     rcx, rax
0x18004e988  test    rax, rax
0x18004e98b  jz      short loc_18004E9AB
0x18004e98d  mov     rax, [rax]
0x18004e990  mov     edx, 7F0h
0x18004e995  mov     rax, [rax+8]
0x18004e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e99e  test    eax, eax
0x18004e9a0  jz      short loc_18004E9AB
0x18004e9a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e9a9  jmp     short loc_18004E9B9
0x18004e9ab  lea     rcx, qword_180153440; this
0x18004e9b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e9b9  cmp     [rcx+8], r13b
0x18004e9bd  jz      short loc_18004E9E0
0x18004e9bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e9c4  cmp     [rax+7CCh], ebx
0x18004e9ca  jz      short loc_18004E9E0
0x18004e9cc  mov     r9d, ebx; int
0x18004e9cf  mov     r8d, 0B9Dh; int
0x18004e9d5  mov     rdx, rsi; char *
0x18004e9d8  mov     rcx, rax; this
0x18004e9db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004e9e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004e9e7  jb      loc_18004F4FB
0x18004e9ed  mov     edx, 0B5h
0x18004e9f2  jmp     loc_18004F4E1
0x18004e9f7  mov     rdx, [r14+8E8h]; struct ID3D11Device *
0x18004e9fe  mov     rcx, rdi; this
0x18004ea01  call    ?update@D3D11CbufferWrapperImpl@MFD3D@@QEAAJPEAUID3D11Device@@@Z; MFD3D::D3D11CbufferWrapperImpl::update(ID3D11Device *)
0x18004ea06  mov     ebx, eax
0x18004ea08  test    eax, eax
0x18004ea0a  jns     loc_18004EA9B
0x18004ea10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ea17  test    rcx, rcx
0x18004ea1a  jnz     short loc_18004EA5D
0x18004ea1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ea22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ea29  mov     rcx, rax
0x18004ea2c  test    rax, rax
0x18004ea2f  jz      short loc_18004EA4F
0x18004ea31  mov     rax, [rax]
0x18004ea34  mov     edx, 7F0h
0x18004ea39  mov     rax, [rax+8]
0x18004ea3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea42  test    eax, eax
0x18004ea44  jz      short loc_18004EA4F
0x18004ea46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ea4d  jmp     short loc_18004EA5D
0x18004ea4f  lea     rcx, qword_180153440; this
0x18004ea56  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ea5d  cmp     [rcx+8], r13b
0x18004ea61  jz      short loc_18004EA84
0x18004ea63  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004ea68  cmp     [rax+7CCh], ebx
0x18004ea6e  jz      short loc_18004EA84
0x18004ea70  mov     r9d, ebx; int
0x18004ea73  mov     r8d, 0B9Eh; int
0x18004ea79  mov     rdx, rsi; char *
0x18004ea7c  mov     rcx, rax; this
0x18004ea7f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004ea84  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18004ea8b  jb      loc_18004F4FB
0x18004ea91  mov     edx, 0B6h
0x18004ea96  jmp     loc_18004F4E1
0x18004ea9b  mov     rax, [r14+10h]
0x18004ea9f  cmp     [rax+3E0h], r13d
0x18004eaa6  jz      loc_18004EC03
0x18004eaac  mov     rcx, [r14+88h]
0x18004eab3  mov     rax, [rcx]
0x18004eab6  mov     rax, [rax+10h]
0x18004eaba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eabf  mov     ebx, eax
0x18004eac1  test    eax, eax
0x18004eac3  jns     loc_18004EB54
0x18004eac9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ead0  test    rcx, rcx
0x18004ead3  jnz     short loc_18004EB16
0x18004ead5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004eadb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eae2  mov     rcx, rax
0x18004eae5  test    rax, rax
0x18004eae8  jz      short loc_18004EB08
0x18004eaea  mov     rax, [rax]
0x18004eaed  mov     edx, 7F0h
0x18004eaf2  mov     rax, [rax+8]
0x18004eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eafb  test    eax, eax
0x18004eafd  jz      short loc_18004EB08
0x18004eaff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eb06  jmp     short loc_18004EB16
0x18004eb08  lea     rcx, qword_180153440; this
0x18004eb0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004eb16  cmp     [rcx+8], r13b
0x18004eb1a  jz      short loc_18004EB3D
0x18004eb1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004eb21  cmp     [rax+7CCh], ebx
0x18004eb27  jz      short loc_18004EB3D
0x18004eb29  mov     r9d, ebx; int
  ... truncated ...
```
