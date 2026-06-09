# CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal(void)

- ea: `0x180025ef0`
- end: `0x18002670c`
- name: `?CreateD3DVideoProcessorInternal@CxCodeVideoProcWARPDataHandler@@MEAAJXZ`
- size: `2076`
- prototype: `__int64 __fastcall(CxCodeVideoProcWARPDataHandler *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180025ef0`
- `0x18003639c`
- `0x1800364d0`
- `0x180054140`
- `0x18006dad0`
- `0x1800734e0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x180025fab`
- `MFPlat!MFCreateSample` at `0x18002633b`
- `MFPlat!MFCreateSample` at `0x180025fab`
- `MFPlat!MFCreateSample` at `0x18002633b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025fc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800261c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026474`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026503`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026592`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026637`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180025fc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026138`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800261c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026256`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026474`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026503`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026592`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026637`

## string_xrefs

- `0x180025f1b`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x18002601e`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x18002618f`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x18002621e`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x1800262ad`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x180026375`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x1800264cb`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x18002655a`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x1800265e9`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`
- `0x18002668e`: `CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal(
        CxCodeVideoProcWARPDataHandler *this)
{
  __int64 v2; // rax
  _DWORD *v3; // rcx
  HRESULT D3DVideoProcessorInternal; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  int v9; // r12d
  int v10; // r15d
  __int64 v11; // rsi
  char *v12; // rbx
  __int64 (__fastcall *v13)(__int64, _OWORD *, _QWORD, char *); // rdi
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _DWORD *v27; // rcx
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  int v30; // r12d
  int v31; // r15d
  __int64 v32; // rsi
  __int64 (__fastcall *v33)(__int64, _OWORD *, _QWORD, char *); // rdi
  char *v34; // rbx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  _BYTE v51[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v52; // [rsp+38h] [rbp-31h] BYREF
  _OWORD v53[3]; // [rsp+40h] [rbp-29h] BYREF

  *(_DWORD *)(*((_QWORD *)this + 2) + 884LL) = 1;
  *(_DWORD *)(*((_QWORD *)this + 2) + 1260LL) = 1;
  v2 = *((_QWORD *)this + 2);
  v53[0] = 0;
  *((_QWORD *)this + 156) = v2;
  v3 = (_DWORD *)*((_QWORD *)this + 2);
  memset(&v53[1], 0, 28);
  LODWORD(v53[1]) = v3[82];
  LODWORD(v53[0]) = v3[13];
  DWORD1(v53[0]) = v3[12];
  *(_QWORD *)&v53[2] = 0x1000000000008LL;
  *((_QWORD *)&v53[0] + 1) = 0x100000001LL;
  HIDWORD(v53[1]) = 0;
  DWORD1(v53[1]) = 1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v51,
    "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
    61);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1192);
  D3DVideoProcessorInternal = MFCreateSample((IMFSample **)this + 149);
  if ( D3DVideoProcessorInternal >= 0 )
  {
    v9 = 0;
    v10 = (*(_DWORD *)(*((_QWORD *)this + 2) + 356LL) == 1) + 1;
    while ( v9 < v10 )
    {
      v11 = *((_QWORD *)this + 146);
      v52 = 0;
      v12 = (char *)this + 8 * v9;
      v13 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, char *))(*(_QWORD *)v11 + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v12 + 1176);
      D3DVideoProcessorInternal = v13(v11, v53, 0, v12 + 1176);
      if ( D3DVideoProcessorInternal < 0 )
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
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != D3DVideoProcessorInternal )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
              67,
              D3DVideoProcessorInternal);
        }
        if ( !g_wppLevels )
          goto LABEL_50;
        v20 = 11;
LABEL_49:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v20,
          WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids,
          this,
          D3DVideoProcessorInternal);
        goto LABEL_50;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      D3DVideoProcessorInternal = dlMFCreateDXGISurfaceBuffer(
                                    v14,
                                    *((_QWORD *)this + v9 + 147),
                                    v15,
                                    v16,
                                    (__int64)&v52);
      if ( D3DVideoProcessorInternal < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != D3DVideoProcessorInternal )
            CallStackContext::TraceFailure(
              v23,
              "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
              68,
              D3DVideoProcessorInternal);
        }
        if ( !g_wppLevels )
          goto LABEL_50;
        v20 = 12;
        goto LABEL_49;
      }
      D3DVideoProcessorInternal = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 149) + 336LL))(
                                    *((_QWORD *)this + 149),
                                    v52);
      if ( D3DVideoProcessorInternal < 0 )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != D3DVideoProcessorInternal )
            CallStackContext::TraceFailure(
              v19,
              "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
              69,
              D3DVideoProcessorInternal);
        }
        if ( g_wppLevels )
        {
          v20 = 13;
          goto LABEL_49;
        }
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        goto LABEL_108;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      ++v9;
    }
    v27 = (_DWORD *)*((_QWORD *)this + 2);
    LODWORD(v53[1]) = v27[141];
    LODWORD(v53[0]) = v27[101];
    DWORD1(v53[0]) = v27[100];
    *(_QWORD *)&v53[2] = 0x2000000000020LL;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1216);
    D3DVideoProcessorInternal = MFCreateSample((IMFSample **)this + 152);
    if ( D3DVideoProcessorInternal >= 0 )
    {
      v30 = 0;
      v31 = (*(_DWORD *)(*((_QWORD *)this + 2) + 744LL) == 1) + 1;
      while ( v30 < v31 )
      {
        v32 = *((_QWORD *)this + 146);
        v52 = 0;
        v33 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, char *))(*(_QWORD *)v32 + 40LL);
        v34 = (char *)this + 8 * v30;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v34 + 1200);
        D3DVideoProcessorInternal = v33(v32, v53, 0, v34 + 1200);
        if ( D3DVideoProcessorInternal < 0 )
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
            if ( *((_DWORD *)v46 + 499) != D3DVideoProcessorInternal )
              CallStackContext::TraceFailure(
                v46,
                "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
                83,
                D3DVideoProcessorInternal);
          }
          if ( g_wppLevels )
          {
            v20 = 15;
            goto LABEL_49;
          }
          goto LABEL_50;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        D3DVideoProcessorInternal = dlMFCreateDXGISurfaceBuffer(
                                      v35,
                                      *((_QWORD *)this + v30 + 150),
                                      v36,
                                      v37,
                                      (__int64)&v52);
        if ( D3DVideoProcessorInternal < 0 )
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
            if ( *((_DWORD *)v43 + 499) != D3DVideoProcessorInternal )
              CallStackContext::TraceFailure(
                v43,
                "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
                84,
                D3DVideoProcessorInternal);
          }
          if ( g_wppLevels )
          {
            v20 = 16;
            goto LABEL_49;
          }
          goto LABEL_50;
        }
        D3DVideoProcessorInternal = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 152) + 336LL))(
                                      *((_QWORD *)this + 152),
                                      v52);
        if ( D3DVideoProcessorInternal < 0 )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)v40 + 499) != D3DVideoProcessorInternal )
              CallStackContext::TraceFailure(
                v40,
                "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
                85,
                D3DVideoProcessorInternal);
          }
          if ( g_wppLevels )
          {
            v20 = 17;
            goto LABEL_49;
          }
          goto LABEL_50;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        ++v30;
      }
      D3DVideoProcessorInternal = CxCodeVideoProcD3D11DataHandler::CreateD3DVideoProcessorInternal((CxCodeVideoProcWARPDataHandler *)((char *)this + 1232));
      if ( D3DVideoProcessorInternal >= 0 )
      {
        if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 19, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids, this);
      }
      else
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
          if ( *((_DWORD *)v49 + 499) != D3DVideoProcessorInternal )
            CallStackContext::TraceFailure(
              v49,
              "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
              88,
              D3DVideoProcessorInternal);
        }
        if ( g_wppLevels )
        {
          v8 = 18;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v28 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(v28);
        if ( *((_DWORD *)v29 + 499) != D3DVideoProcessorInternal )
          CallStackContext::TraceFailure(
            v29,
            "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
            77,
            D3DVideoProcessorInternal);
      }
      if ( g_wppLevels )
      {
        v8 = 14;
        goto LABEL_12;
      }
    }
  }
  else
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
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != D3DVideoProcessorInternal )
        CallStackContext::TraceFailure(
          v7,
          "CxCodeVideoProcWARPDataHandler::CreateD3DVideoProcessorInternal",
          61,
          D3DVideoProcessorInternal);
    }
    if ( g_wppLevels )
    {
      v8 = 10;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids,
        this,
        D3DVideoProcessorInternal);
    }
  }
LABEL_108:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  return (unsigned int)D3DVideoProcessorInternal;
}

```

## disassembly

```asm
0x180025ef0  push    rbp
0x180025ef2  push    rbx
0x180025ef3  push    rsi
0x180025ef4  push    rdi
0x180025ef5  push    r12
0x180025ef7  push    r13
0x180025ef9  push    r14
0x180025efb  push    r15
0x180025efd  lea     rbp, [rsp-1Fh]
0x180025f02  sub     rsp, 88h
0x180025f09  mov     rax, cs:__security_cookie
0x180025f10  xor     rax, rsp
0x180025f13  mov     [rbp+57h+var_50], rax
0x180025f17  mov     rax, [rcx+10h]
0x180025f1b  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x180025f22  mov     esi, 1
0x180025f27  xorps   xmm0, xmm0
0x180025f2a  mov     r14, rcx
0x180025f2d  xor     edi, edi
0x180025f2f  mov     [rax+374h], esi
0x180025f35  mov     rax, [rcx+10h]
0x180025f39  lea     r15d, [rsi+3Ch]
0x180025f3d  mov     r8d, r15d; int
0x180025f40  mov     [rax+4ECh], esi
0x180025f46  mov     rax, [rcx+10h]
0x180025f4a  movups  [rbp+57h+var_80], xmm0
0x180025f4e  mov     [rcx+4E0h], rax
0x180025f55  mov     rcx, [rcx+10h]
0x180025f59  movups  [rbp+57h+var_70], xmm0
0x180025f5d  movups  [rbp+57h+var_70+0Ch], xmm0
0x180025f61  mov     eax, [rcx+148h]
0x180025f67  mov     dword ptr [rbp+57h+var_70], eax
0x180025f6a  mov     eax, [rcx+34h]
0x180025f6d  mov     dword ptr [rbp+57h+var_80], eax
0x180025f70  mov     eax, [rcx+30h]
0x180025f73  lea     rcx, [rbp+57h+var_90]; this
0x180025f77  mov     dword ptr [rbp+57h+var_80+4], eax
0x180025f7a  mov     dword ptr [rbp+57h+var_80+0Ch], esi
0x180025f7d  mov     [rbp+57h+var_60], 8
0x180025f84  mov     dword ptr [rbp+57h+var_80+8], esi
0x180025f87  mov     dword ptr [rbp+57h+var_70+0Ch], edi
0x180025f8a  mov     [rbp+57h+var_5C], 10000h
0x180025f91  mov     dword ptr [rbp+57h+var_70+4], esi
0x180025f94  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180025f99  lea     rbx, [r14+4A8h]
0x180025fa0  mov     rcx, rbx
0x180025fa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025fa8  mov     rcx, rbx; ppIMFSample
0x180025fab  call    cs:__imp_MFCreateSample
0x180025fb1  mov     ebx, eax
0x180025fb3  test    eax, eax
0x180025fb5  jns     loc_180026065
0x180025fbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025fc2  test    rcx, rcx
0x180025fc5  jnz     short loc_180026008
0x180025fc7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180025fcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180025fd4  mov     rcx, rax
0x180025fd7  test    rax, rax
0x180025fda  jz      short loc_180025FFA
0x180025fdc  mov     rax, [rax]
0x180025fdf  mov     edx, 7F0h
0x180025fe4  mov     rax, [rax+8]
0x180025fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fed  test    eax, eax
0x180025fef  jz      short loc_180025FFA
0x180025ff1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180025ff8  jmp     short loc_180026008
0x180025ffa  lea     rcx, qword_180153440; this
0x180026001  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026008  cmp     [rcx+8], dil
0x18002600c  jz      short loc_180026030
0x18002600e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026013  cmp     [rax+7CCh], ebx
0x180026019  jz      short loc_180026030
0x18002601b  mov     r9d, ebx; int
0x18002601e  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x180026025  mov     r8d, r15d; int
0x180026028  mov     rcx, rax; this
0x18002602b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026030  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180026037  jb      loc_1800266E1
0x18002603d  mov     edx, 0Ah
0x180026042  mov     rcx, cs:WPP_GLOBAL_Control
0x180026049  lea     r8, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids
0x180026050  mov     r9, r14
0x180026053  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180026057  mov     rcx, [rcx+10h]
0x18002605b  call    WPP_SF_qD
0x180026060  jmp     loc_1800266E1
0x180026065  mov     rax, [r14+10h]
0x180026069  mov     r15d, edi
0x18002606c  mov     r12d, edi
0x18002606f  cmp     [rax+164h], esi
0x180026075  setz    r15b
0x180026079  add     r15d, esi
0x18002607c  cmp     r12d, r15d
0x18002607f  jge     loc_1800262FC
0x180026085  mov     rsi, [r14+490h]
0x18002608c  mov     [rbp+57h+var_88], rdi
0x180026090  movsxd  r13, r12d
0x180026093  mov     rax, [rsi]
0x180026096  lea     rbx, [r14+r13*8]
0x18002609a  lea     rcx, [rbx+498h]
0x1800260a1  mov     rdi, [rax+28h]
0x1800260a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800260aa  lea     r9, [rbx+498h]
0x1800260b1  xor     r8d, r8d
0x1800260b4  lea     rdx, [rbp+57h+var_80]
0x1800260b8  mov     rcx, rsi
0x1800260bb  mov     rax, rdi
0x1800260be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260c3  xor     edi, edi
0x1800260c5  mov     ebx, eax
0x1800260c7  test    eax, eax
0x1800260c9  js      loc_18002624A
0x1800260cf  lea     rcx, [rbp+57h+var_88]
0x1800260d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800260d8  mov     rdx, [r14+r13*8+498h]
0x1800260e0  lea     rax, [rbp+57h+var_88]
0x1800260e4  mov     [rsp+0C0h+var_A0], rax
0x1800260e9  call    dlMFCreateDXGISurfaceBuffer
0x1800260ee  mov     ebx, eax
0x1800260f0  test    eax, eax
0x1800260f2  js      loc_1800261BB
0x1800260f8  mov     rcx, [r14+4A8h]
0x1800260ff  mov     rdx, [rbp+57h+var_88]
0x180026103  mov     rax, [rcx]
0x180026106  mov     rax, [rax+150h]
0x18002610d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026112  mov     ebx, eax
0x180026114  test    eax, eax
0x180026116  js      short loc_18002612C
0x180026118  lea     rcx, [rbp+57h+var_88]
0x18002611c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026121  lea     esi, [rdi+1]
0x180026124  add     r12d, esi
0x180026127  jmp     loc_18002607C
0x18002612c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026133  test    rcx, rcx
0x180026136  jnz     short loc_180026179
0x180026138  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002613e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026145  mov     rcx, rax
0x180026148  test    rax, rax
0x18002614b  jz      short loc_18002616B
0x18002614d  mov     rax, [rax]
0x180026150  mov     edx, 7F0h
0x180026155  mov     rax, [rax+8]
0x180026159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002615e  test    eax, eax
0x180026160  jz      short loc_18002616B
0x180026162  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026169  jmp     short loc_180026179
0x18002616b  lea     rcx, qword_180153440; this
0x180026172  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026179  cmp     [rcx+8], dil
0x18002617d  jz      short loc_1800261A4
0x18002617f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026184  cmp     [rax+7CCh], ebx
0x18002618a  jz      short loc_1800261A4
0x18002618c  mov     r9d, ebx; int
0x18002618f  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x180026196  mov     r8d, 45h ; 'E'; int
0x18002619c  mov     rcx, rax; this
0x18002619f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800261a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800261ab  jb      loc_1800262EE
0x1800261b1  mov     edx, 0Dh
0x1800261b6  jmp     loc_1800262D0
0x1800261bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800261c2  test    rcx, rcx
0x1800261c5  jnz     short loc_180026208
0x1800261c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800261cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800261d4  mov     rcx, rax
0x1800261d7  test    rax, rax
0x1800261da  jz      short loc_1800261FA
0x1800261dc  mov     rax, [rax]
0x1800261df  mov     edx, 7F0h
0x1800261e4  mov     rax, [rax+8]
0x1800261e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261ed  test    eax, eax
0x1800261ef  jz      short loc_1800261FA
0x1800261f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800261f8  jmp     short loc_180026208
0x1800261fa  lea     rcx, qword_180153440; this
0x180026201  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026208  cmp     [rcx+8], dil
0x18002620c  jz      short loc_180026233
0x18002620e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180026213  cmp     [rax+7CCh], ebx
0x180026219  jz      short loc_180026233
0x18002621b  mov     r9d, ebx; int
0x18002621e  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x180026225  mov     r8d, 44h ; 'D'; int
0x18002622b  mov     rcx, rax; this
0x18002622e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180026233  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002623a  jb      loc_1800262EE
0x180026240  mov     edx, 0Ch
0x180026245  jmp     loc_1800262D0
0x18002624a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026251  test    rcx, rcx
0x180026254  jnz     short loc_180026297
0x180026256  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002625c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026263  mov     rcx, rax
0x180026266  test    rax, rax
0x180026269  jz      short loc_180026289
0x18002626b  mov     rax, [rax]
0x18002626e  mov     edx, 7F0h
0x180026273  mov     rax, [rax+8]
0x180026277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002627c  test    eax, eax
0x18002627e  jz      short loc_180026289
0x180026280  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026287  jmp     short loc_180026297
0x180026289  lea     rcx, qword_180153440; this
0x180026290  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180026297  cmp     [rcx+8], dil
0x18002629b  jz      short loc_1800262C2
0x18002629d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800262a2  cmp     [rax+7CCh], ebx
0x1800262a8  jz      short loc_1800262C2
0x1800262aa  mov     r9d, ebx; int
0x1800262ad  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x1800262b4  mov     r8d, 43h ; 'C'; int
0x1800262ba  mov     rcx, rax; this
0x1800262bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800262c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800262c9  jb      short loc_1800262EE
0x1800262cb  mov     edx, 0Bh
0x1800262d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262d7  lea     r8, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids
0x1800262de  mov     r9, r14
0x1800262e1  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800262e5  mov     rcx, [rcx+10h]
0x1800262e9  call    WPP_SF_qD
0x1800262ee  lea     rcx, [rbp+57h+var_88]
0x1800262f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800262f7  jmp     loc_1800266E1
0x1800262fc  mov     rcx, [r14+10h]
0x180026300  lea     r13, [r14+4C0h]
0x180026307  mov     eax, [rcx+234h]
0x18002630d  mov     dword ptr [rbp+57h+var_70], eax
0x180026310  mov     eax, [rcx+194h]
0x180026316  mov     dword ptr [rbp+57h+var_80], eax
0x180026319  mov     eax, [rcx+190h]
0x18002631f  mov     rcx, r13
0x180026322  mov     dword ptr [rbp+57h+var_80+4], eax
0x180026325  mov     [rbp+57h+var_60], 20h ; ' '
0x18002632c  mov     [rbp+57h+var_5C], 20000h
0x180026333  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026338  mov     rcx, r13; ppIMFSample
0x18002633b  call    cs:__imp_MFCreateSample
0x180026341  mov     ebx, eax
0x180026343  test    eax, eax
0x180026345  jns     short loc_1800263A1
0x180026347  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002634e  test    rcx, rcx
0x180026351  jnz     short loc_18002635F
0x180026353  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180026358  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002635f  cmp     [rcx+8], dil
0x180026363  jz      short loc_18002638A
0x180026365  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002636a  cmp     [rax+7CCh], ebx
0x180026370  jz      short loc_18002638A
0x180026372  mov     r9d, ebx; int
0x180026375  lea     rdx, aCxcodevideopro_48; "CxCodeVideoProcWARPDataHandler::CreateD"...
0x18002637c  mov     r8d, 4Dh ; 'M'; int
0x180026382  mov     rcx, rax; this
0x180026385  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002638a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180026391  jb      loc_1800266E1
0x180026397  mov     edx, 0Eh
0x18002639c  jmp     loc_180026042
0x1800263a1  mov     rax, [r14+10h]
0x1800263a5  mov     r15d, edi
0x1800263a8  mov     r12d, edi
0x1800263ab  cmp     [rax+2E8h], esi
0x1800263b1  setz    r15b
0x1800263b5  add     r15d, esi
0x1800263b8  cmp     r12d, r15d
0x1800263bb  jge     loc_180026615
0x1800263c1  mov     rsi, [r14+490h]
0x1800263c8  mov     [rbp+57h+var_88], rdi
0x1800263cc  mov     rax, [rsi]
0x1800263cf  mov     rdi, [rax+28h]
0x1800263d3  movsxd  rax, r12d
0x1800263d6  lea     rbx, [r14+rax*8]
0x1800263da  lea     rcx, [rbx+4B0h]
0x1800263e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800263e6  lea     r9, [rbx+4B0h]
0x1800263ed  xor     r8d, r8d
0x1800263f0  lea     rdx, [rbp+57h+var_80]
0x1800263f4  mov     rcx, rsi
0x1800263f7  mov     rax, rdi
0x1800263fa  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
