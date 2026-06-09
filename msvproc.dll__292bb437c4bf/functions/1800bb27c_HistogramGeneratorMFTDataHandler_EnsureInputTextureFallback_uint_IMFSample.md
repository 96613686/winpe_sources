# HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback(uint,IMFSample *)

- ea: `0x1800bb27c`
- end: `0x1800bb801`
- name: `?EnsureInputTextureFallback@HistogramGeneratorMFTDataHandler@@AEAAJIPEAUIMFSample@@@Z`
- size: `1413`
- prototype: `int(HistogramGeneratorMFTDataHandler *__hidden this, unsigned int, struct IMFSample *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bb808`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800364d0`
- `0x180054140`
- `0x1800bb27c`
- `0x1800c0704`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x1800bb333`
- `MFPlat!MFCreateSample` at `0x1800bb333`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x1800bb64f`
- `MFPlat!MFCreateDXGISurfaceBuffer` at `0x1800bb64f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb34f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb3fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb4ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb5ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb66b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb716`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb34f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb3fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb4ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb5ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb66b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bb716`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback(
        IMFSample **this,
        __int64 a2,
        struct IMFSample *a3)
{
  HRESULT v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  struct IMFDXGIBuffer **v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, GUID *, __int64 *); // rbx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  IMFSample *v19; // rdi
  HRESULT (__stdcall *CompareItem)(IMFSample *, const GUID *const, const PROPVARIANT *const, BOOL *); // rbx
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v31[8]; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-31h] BYREF
  IUnknown *punkSurface; // [rsp+40h] [rbp-29h] BYREF
  __int64 v34; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v35[2]; // [rsp+50h] [rbp-19h] BYREF
  _OWORD v36[3]; // [rsp+58h] [rbp-11h] BYREF

  v5 = 0;
  *(_QWORD *)v35 = 0;
  v34 = 0;
  punkSurface = 0;
  ppBuffer = 0;
  memset(v36, 0, 44);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v31,
    "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback",
    567);
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 13, &WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids, this);
  if ( !this[82] )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 82);
    v5 = MFCreateSample(this + 82);
    if ( v5 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
      v5 = MFD3D::DXGIBufferFromSample((MFD3D *)a3, 0, (unsigned int)v35, v10);
      if ( v5 >= 0 )
      {
        v14 = *(_QWORD *)v35;
        v15 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v35 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v5 = v15(v14, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v34);
        if ( v5 >= 0 )
        {
          (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v34 + 80LL))(v34, v36);
          *(_QWORD *)&v36[2] = v36[2] & 0xFFFFF9F7 | 8LL;
          HIDWORD(v36[1]) = 0;
          HIDWORD(v36[0]) = 1;
          v19 = this[30];
          CompareItem = v19->lpVtbl->CompareItem;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punkSurface);
          v5 = ((__int64 (__fastcall *)(IMFSample *, _OWORD *, _QWORD, IUnknown **))CompareItem)(
                 v19,
                 v36,
                 0,
                 &punkSurface);
          if ( v5 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppBuffer);
            v5 = MFCreateDXGISurfaceBuffer(&GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, punkSurface, 0, 0, &ppBuffer);
            if ( v5 >= 0 )
            {
              v5 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))this[82]->lpVtbl->AddBuffer)(
                     this[82],
                     ppBuffer);
              if ( v5 < 0 )
              {
                v27 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
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
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback",
                      583,
                      v5);
                }
                if ( g_wppLevels )
                {
                  v9 = 19;
                  goto LABEL_70;
                }
              }
            }
            else
            {
              v24 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v25;
                if ( v25
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
                if ( *((_DWORD *)v26 + 499) != v5 )
                  CallStackContext::TraceFailure(
                    v26,
                    "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback",
                    582,
                    v5);
              }
              if ( g_wppLevels )
              {
                v9 = 18;
                goto LABEL_70;
              }
            }
          }
          else
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v22;
              if ( v22
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
              if ( *((_DWORD *)v23 + 499) != v5 )
                CallStackContext::TraceFailure(
                  v23,
                  "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback",
                  581,
                  v5);
            }
            if ( g_wppLevels )
            {
              v9 = 17;
              goto LABEL_70;
            }
          }
        }
        else
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v17;
            if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
            {
              v16 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v16 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v16 + 8) )
          {
            v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
            if ( *((_DWORD *)v18 + 499) != v5 )
              CallStackContext::TraceFailure(
                v18,
                "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback",
                572,
                v5);
          }
          if ( g_wppLevels )
          {
            v9 = 16;
            goto LABEL_70;
          }
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
          if ( *((_DWORD *)v13 + 499) != v5 )
            CallStackContext::TraceFailure(v13, "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback", 571, v5);
        }
        if ( g_wppLevels )
        {
          v9 = 15;
          goto LABEL_70;
        }
      }
    }
    else
    {
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v6 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
        if ( *((_DWORD *)v8 + 499) != v5 )
          CallStackContext::TraceFailure(v8, "HistogramGeneratorMFTDataHandler::EnsureInputTextureFallback", 570, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 14;
LABEL_70:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids, this, v5);
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppBuffer);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&punkSurface);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800bb27c  mov     [rsp-8+arg_8], rbx
0x1800bb281  push    rbp
0x1800bb282  push    rsi
0x1800bb283  push    rdi
0x1800bb284  push    r12
0x1800bb286  push    r13
0x1800bb288  push    r14
0x1800bb28a  push    r15
0x1800bb28c  lea     rbp, [rsp-27h]
0x1800bb291  sub     rsp, 90h
0x1800bb298  mov     rax, cs:__security_cookie
0x1800bb29f  xor     rax, rsp
0x1800bb2a2  mov     [rbp+57h+var_38], rax
0x1800bb2a6  mov     rdi, r8
0x1800bb2a9  mov     rsi, rcx
0x1800bb2ac  xor     r15d, r15d
0x1800bb2af  mov     ebx, r15d
0x1800bb2b2  mov     qword ptr [rbp+57h+var_70], r15
0x1800bb2b6  mov     [rbp+57h+var_78], r15
0x1800bb2ba  mov     [rbp+57h+punkSurface], r15
0x1800bb2be  mov     [rbp+57h+var_88], r15
0x1800bb2c2  xorps   xmm0, xmm0
0x1800bb2c5  movups  [rbp+57h+var_68], xmm0
0x1800bb2c9  movups  [rbp+57h+var_58], xmm0
0x1800bb2cd  movups  [rbp+57h+var_58+0Ch], xmm0
0x1800bb2d1  mov     r8d, 237h; int
0x1800bb2d7  lea     r13, aHistogramgener; "HistogramGeneratorMFTDataHandler::Ensur"...
0x1800bb2de  mov     rdx, r13; char *
0x1800bb2e1  lea     rcx, [rbp+57h+var_90]; this
0x1800bb2e5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bb2ea  nop
0x1800bb2eb  lea     r12, WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids
0x1800bb2f2  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800bb2f9  jb      short loc_1800BB318
0x1800bb2fb  lea     edx, [r15+0Dh]
0x1800bb2ff  mov     r9, rsi
0x1800bb302  mov     r8, r12
0x1800bb305  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb30c  mov     rcx, [rcx+150h]
0x1800bb313  call    WPP_SF_q
0x1800bb318  lea     r14, [rsi+290h]
0x1800bb31f  cmp     [r14], r15
0x1800bb322  jnz     loc_1800BB7A7
0x1800bb328  mov     rcx, r14
0x1800bb32b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bb330  mov     rcx, r14; ppIMFSample
0x1800bb333  call    cs:__imp_MFCreateSample
0x1800bb339  mov     ebx, eax
0x1800bb33b  test    eax, eax
0x1800bb33d  jns     loc_1800BB3CE
0x1800bb343  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb34a  test    rcx, rcx
0x1800bb34d  jnz     short loc_1800BB390
0x1800bb34f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb355  mov     rcx, rax
0x1800bb358  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb35f  test    rax, rax
0x1800bb362  jz      short loc_1800BB382
0x1800bb364  mov     rax, [rax]
0x1800bb367  mov     edx, 7F0h
0x1800bb36c  mov     rax, [rax+8]
0x1800bb370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb375  test    eax, eax
0x1800bb377  jz      short loc_1800BB382
0x1800bb379  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb380  jmp     short loc_1800BB390
0x1800bb382  lea     rcx, qword_180153440; this
0x1800bb389  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb390  cmp     [rcx+8], r15b
0x1800bb394  jz      short loc_1800BB3B7
0x1800bb396  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb39b  cmp     [rax+7CCh], ebx
0x1800bb3a1  jz      short loc_1800BB3B7
0x1800bb3a3  mov     r9d, ebx; int
0x1800bb3a6  mov     r8d, 23Ah; int
0x1800bb3ac  mov     rdx, r13; char *
0x1800bb3af  mov     rcx, rax; this
0x1800bb3b2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb3b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb3be  jb      loc_1800BB7A7
0x1800bb3c4  mov     edx, 0Eh
0x1800bb3c9  jmp     loc_1800BB78C
0x1800bb3ce  lea     rcx, [rbp+57h+var_70]
0x1800bb3d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bb3d7  lea     r8, [rbp+57h+var_70]; unsigned int
0x1800bb3db  xor     edx, edx; struct IMFSample *
0x1800bb3dd  mov     rcx, rdi; this
0x1800bb3e0  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x1800bb3e5  mov     ebx, eax
0x1800bb3e7  test    eax, eax
0x1800bb3e9  jns     loc_1800BB47A
0x1800bb3ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb3f6  test    rcx, rcx
0x1800bb3f9  jnz     short loc_1800BB43C
0x1800bb3fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb401  mov     rcx, rax
0x1800bb404  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb40b  test    rax, rax
0x1800bb40e  jz      short loc_1800BB42E
0x1800bb410  mov     rax, [rax]
0x1800bb413  mov     edx, 7F0h
0x1800bb418  mov     rax, [rax+8]
0x1800bb41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb421  test    eax, eax
0x1800bb423  jz      short loc_1800BB42E
0x1800bb425  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb42c  jmp     short loc_1800BB43C
0x1800bb42e  lea     rcx, qword_180153440; this
0x1800bb435  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb43c  cmp     [rcx+8], r15b
0x1800bb440  jz      short loc_1800BB463
0x1800bb442  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb447  cmp     [rax+7CCh], ebx
0x1800bb44d  jz      short loc_1800BB463
0x1800bb44f  mov     r9d, ebx; int
0x1800bb452  mov     r8d, 23Bh; int
0x1800bb458  mov     rdx, r13; char *
0x1800bb45b  mov     rcx, rax; this
0x1800bb45e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb463  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb46a  jb      loc_1800BB7A7
0x1800bb470  mov     edx, 0Fh
0x1800bb475  jmp     loc_1800BB78C
0x1800bb47a  mov     rdi, qword ptr [rbp+57h+var_70]
0x1800bb47e  mov     rax, [rdi]
0x1800bb481  mov     rbx, [rax+18h]
0x1800bb485  lea     rcx, [rbp+57h+var_78]
0x1800bb489  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bb48e  lea     r8, [rbp+57h+var_78]
0x1800bb492  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800bb499  mov     rcx, rdi
0x1800bb49c  mov     rax, rbx
0x1800bb49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4a4  mov     ebx, eax
0x1800bb4a6  test    eax, eax
0x1800bb4a8  jns     loc_1800BB539
0x1800bb4ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb4b5  test    rcx, rcx
0x1800bb4b8  jnz     short loc_1800BB4FB
0x1800bb4ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb4c0  mov     rcx, rax
0x1800bb4c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb4ca  test    rax, rax
0x1800bb4cd  jz      short loc_1800BB4ED
0x1800bb4cf  mov     rax, [rax]
0x1800bb4d2  mov     edx, 7F0h
0x1800bb4d7  mov     rax, [rax+8]
0x1800bb4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4e0  test    eax, eax
0x1800bb4e2  jz      short loc_1800BB4ED
0x1800bb4e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb4eb  jmp     short loc_1800BB4FB
0x1800bb4ed  lea     rcx, qword_180153440; this
0x1800bb4f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb4fb  cmp     [rcx+8], r15b
0x1800bb4ff  jz      short loc_1800BB522
0x1800bb501  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb506  cmp     [rax+7CCh], ebx
0x1800bb50c  jz      short loc_1800BB522
0x1800bb50e  mov     r9d, ebx; int
0x1800bb511  mov     r8d, 23Ch; int
0x1800bb517  mov     rdx, r13; char *
0x1800bb51a  mov     rcx, rax; this
0x1800bb51d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb522  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb529  jb      loc_1800BB7A7
0x1800bb52f  mov     edx, 10h
0x1800bb534  jmp     loc_1800BB78C
0x1800bb539  mov     rcx, [rbp+57h+var_78]
0x1800bb53d  mov     rax, [rcx]
0x1800bb540  lea     rdx, [rbp+57h+var_68]
0x1800bb544  mov     rax, [rax+50h]
0x1800bb548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb54d  mov     eax, [rbp+57h+var_48]
0x1800bb550  and     eax, 0FFFFF9FFh
0x1800bb555  or      eax, 8
0x1800bb558  mov     [rbp+57h+var_48], eax
0x1800bb55b  mov     [rbp+57h+var_44], r15d
0x1800bb55f  mov     dword ptr [rbp+57h+var_58+0Ch], r15d
0x1800bb563  mov     dword ptr [rbp+57h+var_68+0Ch], 1
0x1800bb56a  mov     rdi, [rsi+0F0h]
0x1800bb571  mov     rax, [rdi]
0x1800bb574  mov     rbx, [rax+28h]
0x1800bb578  lea     rcx, [rbp+57h+punkSurface]
0x1800bb57c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bb581  lea     r9, [rbp+57h+punkSurface]
0x1800bb585  xor     r8d, r8d
0x1800bb588  lea     rdx, [rbp+57h+var_68]
0x1800bb58c  mov     rcx, rdi
0x1800bb58f  mov     rax, rbx
0x1800bb592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb597  mov     ebx, eax
0x1800bb599  test    eax, eax
0x1800bb59b  jns     loc_1800BB62C
0x1800bb5a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb5a8  test    rcx, rcx
0x1800bb5ab  jnz     short loc_1800BB5EE
0x1800bb5ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb5b3  mov     rcx, rax
0x1800bb5b6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb5bd  test    rax, rax
0x1800bb5c0  jz      short loc_1800BB5E0
0x1800bb5c2  mov     rax, [rax]
0x1800bb5c5  mov     edx, 7F0h
0x1800bb5ca  mov     rax, [rax+8]
0x1800bb5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb5d3  test    eax, eax
0x1800bb5d5  jz      short loc_1800BB5E0
0x1800bb5d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb5de  jmp     short loc_1800BB5EE
0x1800bb5e0  lea     rcx, qword_180153440; this
0x1800bb5e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb5ee  cmp     [rcx+8], r15b
0x1800bb5f2  jz      short loc_1800BB615
0x1800bb5f4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb5f9  cmp     [rax+7CCh], ebx
0x1800bb5ff  jz      short loc_1800BB615
0x1800bb601  mov     r9d, ebx; int
0x1800bb604  mov     r8d, 245h; int
0x1800bb60a  mov     rdx, r13; char *
0x1800bb60d  mov     rcx, rax; this
0x1800bb610  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb615  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb61c  jb      loc_1800BB7A7
0x1800bb622  mov     edx, 11h
0x1800bb627  jmp     loc_1800BB78C
0x1800bb62c  lea     rcx, [rbp+57h+var_88]
0x1800bb630  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bb635  lea     rax, [rbp+57h+var_88]
0x1800bb639  mov     [rsp+0C0h+ppBuffer], rax; ppBuffer
0x1800bb63e  xor     r9d, r9d; fBottomUpWhenLinear
0x1800bb641  xor     r8d, r8d; uSubresourceIndex
0x1800bb644  mov     rdx, [rbp+57h+punkSurface]; punkSurface
0x1800bb648  lea     rcx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c; riid
0x1800bb64f  call    cs:__imp_MFCreateDXGISurfaceBuffer
0x1800bb655  mov     ebx, eax
0x1800bb657  test    eax, eax
0x1800bb659  jns     loc_1800BB6EA
0x1800bb65f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb666  test    rcx, rcx
0x1800bb669  jnz     short loc_1800BB6AC
0x1800bb66b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb671  mov     rcx, rax
0x1800bb674  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb67b  test    rax, rax
0x1800bb67e  jz      short loc_1800BB69E
0x1800bb680  mov     rax, [rax]
0x1800bb683  mov     edx, 7F0h
0x1800bb688  mov     rax, [rax+8]
0x1800bb68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb691  test    eax, eax
0x1800bb693  jz      short loc_1800BB69E
0x1800bb695  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb69c  jmp     short loc_1800BB6AC
0x1800bb69e  lea     rcx, qword_180153440; this
0x1800bb6a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb6ac  cmp     [rcx+8], r15b
0x1800bb6b0  jz      short loc_1800BB6D3
0x1800bb6b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb6b7  cmp     [rax+7CCh], ebx
0x1800bb6bd  jz      short loc_1800BB6D3
0x1800bb6bf  mov     r9d, ebx; int
0x1800bb6c2  mov     r8d, 246h; int
0x1800bb6c8  mov     rdx, r13; char *
0x1800bb6cb  mov     rcx, rax; this
0x1800bb6ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800bb6d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb6da  jb      loc_1800BB7A7
0x1800bb6e0  mov     edx, 12h
0x1800bb6e5  jmp     loc_1800BB78C
0x1800bb6ea  mov     rcx, [r14]
0x1800bb6ed  mov     rax, [rcx]
0x1800bb6f0  mov     rdx, [rbp+57h+var_88]
0x1800bb6f4  mov     rax, [rax+150h]
0x1800bb6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb700  mov     ebx, eax
0x1800bb702  test    eax, eax
0x1800bb704  jns     loc_1800BB7A7
0x1800bb70a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb711  test    rcx, rcx
0x1800bb714  jnz     short loc_1800BB757
0x1800bb716  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800bb71c  mov     rcx, rax
0x1800bb71f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb726  test    rax, rax
0x1800bb729  jz      short loc_1800BB749
0x1800bb72b  mov     rax, [rax]
0x1800bb72e  mov     edx, 7F0h
0x1800bb733  mov     rax, [rax+8]
0x1800bb737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb73c  test    eax, eax
0x1800bb73e  jz      short loc_1800BB749
0x1800bb740  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb747  jmp     short loc_1800BB757
0x1800bb749  lea     rcx, qword_180153440; this
0x1800bb750  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800bb757  cmp     [rcx+8], r15b
0x1800bb75b  jz      short loc_1800BB77E
0x1800bb75d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800bb762  cmp     [rax+7CCh], ebx
  ... truncated ...
```
