# CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples(uint)

- ea: `0x18003d0d4`
- end: `0x18003d993`
- name: `?CreateD3D11ShaderTempSamples@CxCodeVideoProcD3D11DataHandler@@AEAAJI@Z`
- size: `2239`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000cb40`
- `0x18004e5f0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18000f150`
- `0x18001bdb0`
- `0x18001e060`
- `0x18003639c`
- `0x1800364d0`
- `0x18003c230`
- `0x18003d0d4`
- `0x18003eb08`
- `0x18005342c`
- `0x180054140`
- `0x1800734e0`
- `0x1800bef3c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x18003d225`
- `MFPlat!MFCreateSample` at `0x18003d225`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d4d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d5f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d7bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d88e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d243`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d44a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d4d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d568`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d5f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d6e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d7bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003d88e`

## string_xrefs

- `0x18003d167`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d1f6`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d29a`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d4a1`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d530`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d5bf`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d64e`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d6a4`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d739`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d812`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d85a`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`
- `0x18003d8e5`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples(
        CxCodeVideoProcD3D11DataHandler *this,
        unsigned int a2)
{
  HRESULT updated; // ebx
  MFD3D **v5; // r12
  _DWORD *v6; // rax
  int v7; // edi
  unsigned int v8; // esi
  unsigned int v9; // r14d
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  bool v16; // cc
  unsigned int v17; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int128 *, _QWORD, __int64 *); // rbx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  xvpDataHandlerState *v35; // rcx
  _DWORD *v36; // rcx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  int v40; // esi
  int v41; // ebx
  int v42; // r14d
  int v43; // edi
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  struct ID3D11ShaderResourceView **v51; // [rsp+38h] [rbp-51h]
  _BYTE v52[8]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v53; // [rsp+48h] [rbp-41h] BYREF
  __int64 v54; // [rsp+50h] [rbp-39h] BYREF
  int v55; // [rsp+58h] [rbp-31h] BYREF
  int v56; // [rsp+5Ch] [rbp-2Dh]
  unsigned int v57; // [rsp+60h] [rbp-29h] BYREF
  struct ID3D11ShaderResourceView *v58; // [rsp+68h] [rbp-21h] BYREF
  __int128 v59; // [rsp+70h] [rbp-19h] BYREF
  _OWORD v60[2]; // [rsp+80h] [rbp-9h] BYREF

  v54 = 0;
  v53 = 0;
  updated = 0;
  memset(v60, 0, 28);
  v59 = 0;
  `vector constructor iterator'(&v57, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  v55 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1168);
  v5 = (MFD3D **)((char *)this + 1176);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1176);
  v56 = a2 & 0x80000;
  if ( (a2 & 0x80000) != 0 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v52,
      "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
      2579);
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 143, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 288) + 1160LL))(*((_QWORD *)this + 288), 1);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  }
  v6 = (_DWORD *)*((_QWORD *)this + 2);
  if ( v6[247] )
  {
    if ( v6[216] == 1 )
    {
      v7 = v6[20] - v6[18];
      v8 = v6[21] - v6[19];
    }
    else
    {
      v8 = v6[12];
      v7 = v6[13];
    }
    v9 = (v6[89] == 1) + 1;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v52,
      "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
      2594);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1176);
    updated = MFCreateSample((IMFSample **)this + 147);
    if ( updated >= 0 )
    {
      v14 = *((_QWORD *)this + 2);
      v59 = 0;
      memset(v60, 0, 28);
      LODWORD(v60[0]) = *(_DWORD *)(v14 + 1200);
      v15 = 40;
      LODWORD(v60[1]) = 8;
      HIDWORD(v59) = 1;
      v16 = *(_DWORD *)(v14 + 1100) <= 29;
      LODWORD(v59) = v7;
      if ( !v16 )
        v15 = 136;
      *(_QWORD *)((char *)&v59 + 4) = v8 | 0x100000000LL;
      LODWORD(v60[1]) = v15;
      HIDWORD(v60[0]) = 0;
      v17 = 0;
      DWORD1(v60[0]) = 1;
      DWORD2(v60[1]) = a2;
      while ( 1 )
      {
        if ( v17 >= v9 )
        {
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
          goto LABEL_72;
        }
        v18 = *((_QWORD *)this + 285);
        v19 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64 *))(*(_QWORD *)v18 + 40LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        updated = v19(v18, &v59, 0, &v53);
        if ( updated < 0 )
          break;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        updated = dlMFCreateDXGISurfaceBuffer(v20, v53, v21, v22, (__int64)&v54);
        if ( updated < 0 )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
                2617,
                updated);
          }
          if ( g_wppLevels )
          {
            v13 = 146;
            goto LABEL_20;
          }
          goto LABEL_21;
        }
        updated = (*(__int64 (__fastcall **)(MFD3D *, __int64))(*(_QWORD *)*v5 + 336LL))(*v5, v54);
        if ( updated < 0 )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
            if ( *((_DWORD *)v28 + 499) != updated )
              CallStackContext::TraceFailure(
                v28,
                "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
                2618,
                updated);
          }
          if ( g_wppLevels )
          {
            v13 = 147;
            goto LABEL_20;
          }
          goto LABEL_21;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        updated = MFD3D::ShaderInputViewFromSample(*v5, 0, *((_QWORD *)this + 285), 0, (MFD3D *)&v55, &v57, &v58, v51);
        if ( updated < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != updated )
              CallStackContext::TraceFailure(
                v25,
                "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
                2620,
                updated);
          }
          if ( g_wppLevels )
          {
            v13 = 148;
            goto LABEL_20;
          }
          goto LABEL_21;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        ++v17;
      }
      v32 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != updated )
          CallStackContext::TraceFailure(
            v34,
            "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
            2616,
            updated);
      }
      if ( g_wppLevels )
      {
        v13 = 145;
        goto LABEL_20;
      }
      goto LABEL_21;
    }
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != updated )
        CallStackContext::TraceFailure(
          v12,
          "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
          2594,
          updated);
    }
    if ( !g_wppLevels )
    {
LABEL_21:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
      goto LABEL_112;
    }
    v13 = 144;
LABEL_20:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, updated);
    goto LABEL_21;
  }
LABEL_72:
  v35 = (xvpDataHandlerState *)*((_QWORD *)this + 2);
  if ( *((_DWORD *)v35 + 248) && !*((_DWORD *)v35 + 223) )
  {
    if ( xvpDataHandlerState::CanUseSphereViewOpt(v35) )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v52,
        "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
        2634);
      updated = CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture(this);
      if ( updated < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != updated )
            CallStackContext::TraceFailure(
              v39,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
              2634,
              updated);
        }
        if ( !g_wppLevels )
          goto LABEL_21;
        v13 = 149;
        goto LABEL_20;
      }
    }
    else
    {
      v40 = v36[116];
      v41 = v36[117];
      v42 = v36[118];
      v43 = v36[119];
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v52,
        "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
        2639);
      updated = CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample(this, a2, v42 - v40, v43 - v41);
      if ( updated < 0 )
      {
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v45;
          if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
          {
            v44 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v44 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
          if ( *((_DWORD *)v46 + 499) != updated )
            CallStackContext::TraceFailure(
              v46,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
              2639,
              updated);
        }
        if ( !g_wppLevels )
          goto LABEL_21;
        v13 = 150;
        goto LABEL_20;
      }
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 2) + 1488LL) )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v52,
      "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
      2645);
    updated = CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate(this, a2);
    if ( updated < 0 )
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
        if ( *((_DWORD *)v49 + 499) != updated )
          CallStackContext::TraceFailure(
            v49,
            "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderTempSamples",
            2645,
            updated);
      }
      if ( !g_wppLevels )
        goto LABEL_21;
      v13 = 151;
      goto LABEL_20;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
  }
  *(_DWORD *)(*((_QWORD *)this + 2) + 1208LL) = a2;
LABEL_112:
  if ( v56 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 288) + 1160LL))(*((_QWORD *)this + 288), 0);
  `vector destructor iterator'(&v57, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18003d0d4  mov     [rsp-8+arg_10], rbx
0x18003d0d9  push    rbp
0x18003d0da  push    rsi
0x18003d0db  push    rdi
0x18003d0dc  push    r12
0x18003d0de  push    r13
0x18003d0e0  push    r14
0x18003d0e2  push    r15
0x18003d0e4  lea     rbp, [rsp-27h]
0x18003d0e9  sub     rsp, 0B0h
0x18003d0f0  mov     rax, cs:__security_cookie
0x18003d0f7  xor     rax, rsp
0x18003d0fa  mov     [rbp+57h+var_40], rax
0x18003d0fe  xor     edi, edi
0x18003d100  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x18003d107  xorps   xmm0, xmm0
0x18003d10a  mov     [rbp+57h+var_90], rdi
0x18003d10e  mov     r13d, edx
0x18003d111  mov     [rbp+57h+var_98], rdi
0x18003d115  mov     r15, rcx
0x18003d118  mov     ebx, edi
0x18003d11a  movups  [rbp+57h+var_60], xmm0
0x18003d11e  lea     edx, [rdi+8]; unsigned __int64
0x18003d121  lea     r8d, [rdi+2]; unsigned __int64
0x18003d125  lea     rcx, [rbp+57h+var_80]; void *
0x18003d129  movups  [rbp+57h+var_70], xmm0
0x18003d12d  movups  [rbp+57h+var_60+0Ch], xmm0
0x18003d131  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18003d136  lea     rcx, [r15+490h]
0x18003d13d  mov     [rbp+57h+var_88], edi
0x18003d140  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d145  lea     r12, [r15+498h]
0x18003d14c  mov     rcx, r12
0x18003d14f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d154  mov     eax, r13d
0x18003d157  and     eax, 80000h
0x18003d15c  mov     [rbp+57h+var_84], eax
0x18003d15f  jz      short loc_18003D1C6
0x18003d161  mov     r8d, 0A13h; int
0x18003d167  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d16e  lea     rcx, [rbp+57h+var_A0]; this
0x18003d172  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d177  cmp     cs:byte_180153DE0, 20h ; ' '
0x18003d17e  jb      short loc_18003D1A2
0x18003d180  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d187  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18003d18e  mov     edx, 8Fh
0x18003d193  mov     r9, r15
0x18003d196  mov     rcx, [rcx+150h]
0x18003d19d  call    WPP_SF_q
0x18003d1a2  mov     rcx, [r15+900h]
0x18003d1a9  mov     edx, 1
0x18003d1ae  mov     rax, [rcx]
0x18003d1b1  mov     rax, [rax+488h]
0x18003d1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1bd  lea     rcx, [rbp+57h+var_A0]; this
0x18003d1c1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d1c6  mov     rax, [r15+10h]
0x18003d1ca  cmp     [rax+3DCh], edi
0x18003d1d0  jz      loc_18003D683
0x18003d1d6  cmp     dword ptr [rax+360h], 1
0x18003d1dd  jnz     short loc_18003D1ED
0x18003d1df  mov     edi, [rax+50h]
0x18003d1e2  sub     edi, [rax+48h]
0x18003d1e5  mov     esi, [rax+54h]
0x18003d1e8  sub     esi, [rax+4Ch]
0x18003d1eb  jmp     short loc_18003D1F3
0x18003d1ed  mov     esi, [rax+30h]
0x18003d1f0  mov     edi, [rax+34h]
0x18003d1f3  xor     r14d, r14d
0x18003d1f6  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d1fd  cmp     dword ptr [rax+164h], 1
0x18003d204  lea     rcx, [rbp+57h+var_A0]; this
0x18003d208  mov     r8d, 0A22h; int
0x18003d20e  setz    r14b
0x18003d212  inc     r14d
0x18003d215  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003d21a  mov     rcx, r12
0x18003d21d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d222  mov     rcx, r12; ppIMFSample
0x18003d225  call    cs:__imp_MFCreateSample
0x18003d22b  mov     ebx, eax
0x18003d22d  test    eax, eax
0x18003d22f  jns     loc_18003D2E9
0x18003d235  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d23c  xor     edi, edi
0x18003d23e  test    rcx, rcx
0x18003d241  jnz     short loc_18003D284
0x18003d243  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d249  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d250  mov     rcx, rax
0x18003d253  test    rax, rax
0x18003d256  jz      short loc_18003D276
0x18003d258  mov     rax, [rax]
0x18003d25b  mov     edx, 7F0h
0x18003d260  mov     rax, [rax+8]
0x18003d264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d269  test    eax, eax
0x18003d26b  jz      short loc_18003D276
0x18003d26d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d274  jmp     short loc_18003D284
0x18003d276  lea     rcx, qword_180153440; this
0x18003d27d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d284  cmp     [rcx+8], dil
0x18003d288  jz      short loc_18003D2AF
0x18003d28a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d28f  cmp     [rax+7CCh], ebx
0x18003d295  jz      short loc_18003D2AF
0x18003d297  mov     r9d, ebx; int
0x18003d29a  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d2a1  mov     r8d, 0A22h; int
0x18003d2a7  mov     rcx, rax; this
0x18003d2aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d2af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d2b6  jb      short loc_18003D2DB
0x18003d2b8  mov     edx, 90h
0x18003d2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d2c4  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18003d2cb  mov     r9, r15
0x18003d2ce  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18003d2d2  mov     rcx, [rcx+10h]
0x18003d2d6  call    WPP_SF_qD
0x18003d2db  lea     rcx, [rbp+57h+var_A0]; this
0x18003d2df  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003d2e4  jmp     loc_18003D922
0x18003d2e9  mov     rcx, [r15+10h]
0x18003d2ed  mov     r8d, 1
0x18003d2f3  xorps   xmm0, xmm0
0x18003d2f6  movups  [rbp+57h+var_70], xmm0
0x18003d2fa  movups  [rbp+57h+var_60], xmm0
0x18003d2fe  movups  [rbp+57h+var_60+0Ch], xmm0
0x18003d302  mov     eax, [rcx+4B0h]
0x18003d308  mov     dword ptr [rbp+57h+var_60], eax
0x18003d30b  lea     eax, [r8+27h]
0x18003d30f  mov     [rbp+57h+var_50], 8
0x18003d316  mov     dword ptr [rbp+57h+var_70+0Ch], r8d
0x18003d31a  cmp     dword ptr [rcx+44Ch], 1Dh
0x18003d321  lea     edx, [rax+60h]
0x18003d324  mov     dword ptr [rbp+57h+var_70], edi
0x18003d327  cmovg   eax, edx
0x18003d32a  mov     dword ptr [rbp+57h+var_70+4], esi
0x18003d32d  xor     edi, edi
0x18003d32f  mov     [rbp+57h+var_50], eax
0x18003d332  mov     dword ptr [rbp+57h+var_60+0Ch], edi
0x18003d335  mov     esi, edi
0x18003d337  mov     dword ptr [rbp+57h+var_70+8], r8d
0x18003d33b  mov     dword ptr [rbp+57h+var_60+4], r8d
0x18003d33f  mov     [rbp+57h+var_48], r13d
0x18003d343  cmp     esi, r14d
0x18003d346  jnb     loc_18003D67A
0x18003d34c  mov     rdi, [r15+8E8h]
0x18003d353  lea     rcx, [rbp+57h+var_98]
0x18003d357  mov     rax, [rdi]
0x18003d35a  mov     rbx, [rax+28h]
0x18003d35e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d363  lea     r9, [rbp+57h+var_98]
0x18003d367  xor     r8d, r8d
0x18003d36a  lea     rdx, [rbp+57h+var_70]
0x18003d36e  mov     rcx, rdi
0x18003d371  mov     rax, rbx
0x18003d374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d379  xor     edi, edi
0x18003d37b  mov     ebx, eax
0x18003d37d  test    eax, eax
0x18003d37f  js      loc_18003D5EB
0x18003d385  lea     rcx, [rbp+57h+var_90]
0x18003d389  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d38e  mov     rdx, [rbp+57h+var_98]
0x18003d392  lea     rax, [rbp+57h+var_90]
0x18003d396  mov     [rsp+0E0h+var_C0], rax
0x18003d39b  call    dlMFCreateDXGISurfaceBuffer
0x18003d3a0  mov     ebx, eax
0x18003d3a2  test    eax, eax
0x18003d3a4  js      loc_18003D55C
0x18003d3aa  mov     rcx, [r12]
0x18003d3ae  mov     rdx, [rbp+57h+var_90]
0x18003d3b2  mov     rax, [rcx]
0x18003d3b5  mov     rax, [rax+150h]
0x18003d3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3c1  mov     ebx, eax
0x18003d3c3  test    eax, eax
0x18003d3c5  js      loc_18003D4CD
0x18003d3cb  lea     rcx, [rbp+57h+var_78]
0x18003d3cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d3d4  lea     rcx, [rbp+57h+var_80]
0x18003d3d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d3dd  mov     r8, [r15+8E8h]; unsigned int
0x18003d3e4  lea     rax, [rbp+57h+var_78]
0x18003d3e8  mov     rcx, [r12]; this
0x18003d3ec  xor     r9d, r9d; struct ID3D11Device *
0x18003d3ef  mov     [rsp+0E0h+var_B0], rax; struct ID3D11ShaderResourceView **
0x18003d3f4  xor     edx, edx; struct IMFSample *
0x18003d3f6  lea     rax, [rbp+57h+var_80]
0x18003d3fa  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18003d3ff  lea     rax, [rbp+57h+var_88]
0x18003d403  mov     [rsp+0E0h+var_C0], rax; MFD3D *
0x18003d408  call    ?ShaderInputViewFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAUID3D11Device@@HPEAIPEAPEAUID3D11ShaderResourceView@@3@Z; MFD3D::ShaderInputViewFromSample(IMFSample *,ulong,ID3D11Device *,int,uint *,ID3D11ShaderResourceView * *,ID3D11ShaderResourceView * *)
0x18003d40d  mov     ebx, eax
0x18003d40f  test    eax, eax
0x18003d411  js      short loc_18003D43E
0x18003d413  lea     rcx, [rbp+57h+var_90]
0x18003d417  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d41c  lea     rcx, [rbp+57h+var_98]
0x18003d420  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d425  lea     rcx, [rbp+57h+var_80]
0x18003d429  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d42e  lea     rcx, [rbp+57h+var_78]
0x18003d432  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d437  inc     esi
0x18003d439  jmp     loc_18003D343
0x18003d43e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d445  test    rcx, rcx
0x18003d448  jnz     short loc_18003D48B
0x18003d44a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d450  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d457  mov     rcx, rax
0x18003d45a  test    rax, rax
0x18003d45d  jz      short loc_18003D47D
0x18003d45f  mov     rax, [rax]
0x18003d462  mov     edx, 7F0h
0x18003d467  mov     rax, [rax+8]
0x18003d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d470  test    eax, eax
0x18003d472  jz      short loc_18003D47D
0x18003d474  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d47b  jmp     short loc_18003D48B
0x18003d47d  lea     rcx, qword_180153440; this
0x18003d484  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d48b  cmp     [rcx+8], dil
0x18003d48f  jz      short loc_18003D4B6
0x18003d491  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d496  cmp     [rax+7CCh], ebx
0x18003d49c  jz      short loc_18003D4B6
0x18003d49e  mov     r9d, ebx; int
0x18003d4a1  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d4a8  mov     r8d, 0A3Ch; int
0x18003d4ae  mov     rcx, rax; this
0x18003d4b1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d4b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d4bd  jb      loc_18003D2DB
0x18003d4c3  mov     edx, 94h
0x18003d4c8  jmp     loc_18003D2BD
0x18003d4cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d4d4  test    rcx, rcx
0x18003d4d7  jnz     short loc_18003D51A
0x18003d4d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d4df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d4e6  mov     rcx, rax
0x18003d4e9  test    rax, rax
0x18003d4ec  jz      short loc_18003D50C
0x18003d4ee  mov     rax, [rax]
0x18003d4f1  mov     edx, 7F0h
0x18003d4f6  mov     rax, [rax+8]
0x18003d4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4ff  test    eax, eax
0x18003d501  jz      short loc_18003D50C
0x18003d503  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d50a  jmp     short loc_18003D51A
0x18003d50c  lea     rcx, qword_180153440; this
0x18003d513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d51a  cmp     [rcx+8], dil
0x18003d51e  jz      short loc_18003D545
0x18003d520  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d525  cmp     [rax+7CCh], ebx
0x18003d52b  jz      short loc_18003D545
0x18003d52d  mov     r9d, ebx; int
0x18003d530  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d537  mov     r8d, 0A3Ah; int
0x18003d53d  mov     rcx, rax; this
0x18003d540  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003d545  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003d54c  jb      loc_18003D2DB
0x18003d552  mov     edx, 93h
0x18003d557  jmp     loc_18003D2BD
0x18003d55c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d563  test    rcx, rcx
0x18003d566  jnz     short loc_18003D5A9
0x18003d568  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003d56e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d575  mov     rcx, rax
0x18003d578  test    rax, rax
0x18003d57b  jz      short loc_18003D59B
0x18003d57d  mov     rax, [rax]
0x18003d580  mov     edx, 7F0h
0x18003d585  mov     rax, [rax+8]
0x18003d589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d58e  test    eax, eax
0x18003d590  jz      short loc_18003D59B
0x18003d592  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d599  jmp     short loc_18003D5A9
0x18003d59b  lea     rcx, qword_180153440; this
0x18003d5a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003d5a9  cmp     [rcx+8], dil
0x18003d5ad  jz      short loc_18003D5D4
0x18003d5af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003d5b4  cmp     [rax+7CCh], ebx
0x18003d5ba  jz      short loc_18003D5D4
0x18003d5bc  mov     r9d, ebx; int
0x18003d5bf  lea     rdx, aCxcodevideopro_25; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003d5c6  mov     r8d, 0A39h; int
  ... truncated ...
```
