# CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback(uint,IMFSample *,Microsoft::WRL::ComPtr<IMFSample> &,uint)

- ea: `0x1800387dc`
- end: `0x180038d57`
- name: `?EnsureTextureFallback@CxCodeVideoProcD3D11DataHandler@@AEAAJIPEAUIMFSample@@AEAV?$ComPtr@UIMFSample@@@WRL@Microsoft@@I@Z`
- size: `1403`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006eb24`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800364d0`
- `0x1800387dc`
- `0x180054140`
- `0x1800734e0`
- `0x1800c0704`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x18003888b`
- `MFPlat!MFCreateSample` at `0x18003888b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800388a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038957`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038a1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800388a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038957`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038a1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038b11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038bc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180038c74`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback(
        __int64 a1,
        unsigned int a2,
        MFD3D *a3,
        IMFSample **a4,
        int a5)
{
  HRESULT v9; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  struct IMFDXGIBuffer **v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, GUID *, __int64 *); // rbx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _OWORD *, _QWORD, __int64 *); // rbx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v38[8]; // [rsp+30h] [rbp-51h] BYREF
  __int64 v39; // [rsp+38h] [rbp-49h] BYREF
  __int64 v40; // [rsp+40h] [rbp-41h] BYREF
  __int64 v41; // [rsp+48h] [rbp-39h] BYREF
  unsigned int v42[2]; // [rsp+50h] [rbp-31h] BYREF
  _OWORD v43[3]; // [rsp+58h] [rbp-29h] BYREF

  *(_QWORD *)v42 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v9 = 0;
  memset(v43, 0, 44);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v38,
    "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback",
    4162);
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 239, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, a1);
  if ( !*a4 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a4);
    v9 = MFCreateSample(a4);
    if ( v9 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
      v9 = MFD3D::DXGIBufferFromSample(a3, (struct IMFSample *)a2, (unsigned int)v42, v14);
      if ( v9 >= 0 )
      {
        v18 = *(_QWORD *)v42;
        v19 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(**(_QWORD **)v42 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        v9 = v19(v18, &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c, &v41);
        if ( v9 >= 0 )
        {
          (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v41 + 80LL))(v41, v43);
          v23 = *(_QWORD *)(a1 + 2280);
          *(_QWORD *)&v43[2] = (a5 | LODWORD(v43[2])) & 0xFFFFF9FF;
          HIDWORD(v43[1]) = 0;
          HIDWORD(v43[0]) = 1;
          v24 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, __int64 *))(*(_QWORD *)v23 + 40LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
          v9 = v24(v23, v43, 0, &v40);
          if ( v9 >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
            v9 = dlMFCreateDXGISurfaceBuffer(v28, v40, v29, v30, (__int64)&v39);
            if ( v9 >= 0 )
            {
              v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))(*a4)->lpVtbl->AddBuffer)(*a4, v39);
              if ( v9 < 0 )
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
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback",
                      4181,
                      v9);
                }
                if ( g_wppLevels )
                {
                  v13 = 245;
                  goto LABEL_70;
                }
              }
            }
            else
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v32;
                if ( v32
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v31 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v31 + 8) )
              {
                v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                if ( *((_DWORD *)v33 + 499) != v9 )
                  CallStackContext::TraceFailure(
                    v33,
                    "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback",
                    4180,
                    v9);
              }
              if ( g_wppLevels )
              {
                v13 = 244;
                goto LABEL_70;
              }
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
              if ( *((_DWORD *)v27 + 499) != v9 )
                CallStackContext::TraceFailure(v27, "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback", 4179, v9);
            }
            if ( g_wppLevels )
            {
              v13 = 243;
              goto LABEL_70;
            }
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
            if ( *((_DWORD *)v22 + 499) != v9 )
              CallStackContext::TraceFailure(v22, "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback", 4169, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 242;
            goto LABEL_70;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != v9 )
            CallStackContext::TraceFailure(v17, "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback", 4168, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 241;
          goto LABEL_70;
        }
      }
    }
    else
    {
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
        if ( *((_DWORD *)v12 + 499) != v9 )
          CallStackContext::TraceFailure(v12, "CxCodeVideoProcD3D11DataHandler::EnsureTextureFallback", 4166, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 240;
LABEL_70:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, a1, v9);
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v42);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800387dc  push    rbp
0x1800387de  push    rbx
0x1800387df  push    rsi
0x1800387e0  push    rdi
0x1800387e1  push    r12
0x1800387e3  push    r13
0x1800387e5  push    r14
0x1800387e7  push    r15
0x1800387e9  lea     rbp, [rsp-17h]
0x1800387ee  sub     rsp, 98h
0x1800387f5  mov     rax, cs:__security_cookie
0x1800387fc  xor     rax, rsp
0x1800387ff  mov     [rbp+4Fh+var_48], rax
0x180038803  xor     r12d, r12d
0x180038806  xorps   xmm0, xmm0
0x180038809  mov     r15, r8
0x18003880c  mov     qword ptr [rbp+4Fh+var_80], r12
0x180038810  mov     edi, edx
0x180038812  mov     [rbp+4Fh+var_88], r12
0x180038816  mov     rsi, rcx
0x180038819  mov     [rbp+4Fh+var_90], r12
0x18003881d  movups  [rbp+4Fh+var_68], xmm0
0x180038821  mov     r8d, 1042h; int
0x180038827  mov     [rbp+4Fh+var_98], r12
0x18003882b  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038832  mov     r14, r9
0x180038835  lea     rcx, [rbp+4Fh+var_A0]; this
0x180038839  mov     ebx, r12d
0x18003883c  movups  [rbp+4Fh+var_68+0Ch], xmm0
0x180038840  movups  [rbp+4Fh+var_78], xmm0
0x180038844  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180038849  cmp     cs:byte_180153DE0, 20h ; ' '
0x180038850  lea     r13, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180038857  jb      short loc_180038877
0x180038859  mov     rcx, cs:WPP_GLOBAL_Control
0x180038860  mov     edx, 0EFh
0x180038865  mov     r9, rsi
0x180038868  mov     r8, r13
0x18003886b  mov     rcx, [rcx+150h]
0x180038872  call    WPP_SF_q
0x180038877  cmp     [r14], r12
0x18003887a  jnz     loc_180038D08
0x180038880  mov     rcx, r14
0x180038883  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038888  mov     rcx, r14; ppIMFSample
0x18003888b  call    cs:__imp_MFCreateSample
0x180038891  mov     ebx, eax
0x180038893  test    eax, eax
0x180038895  jns     loc_18003892A
0x18003889b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800388a2  test    rcx, rcx
0x1800388a5  jnz     short loc_1800388E8
0x1800388a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800388ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800388b4  mov     rcx, rax
0x1800388b7  test    rax, rax
0x1800388ba  jz      short loc_1800388DA
0x1800388bc  mov     rax, [rax]
0x1800388bf  mov     edx, 7F0h
0x1800388c4  mov     rax, [rax+8]
0x1800388c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388cd  test    eax, eax
0x1800388cf  jz      short loc_1800388DA
0x1800388d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800388d8  jmp     short loc_1800388E8
0x1800388da  lea     rcx, qword_180153440; this
0x1800388e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800388e8  cmp     [rcx+8], r12b
0x1800388ec  jz      short loc_180038913
0x1800388ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800388f3  cmp     [rax+7CCh], ebx
0x1800388f9  jz      short loc_180038913
0x1800388fb  mov     r9d, ebx; int
0x1800388fe  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038905  mov     r8d, 1046h; int
0x18003890b  mov     rcx, rax; this
0x18003890e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038913  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003891a  jb      loc_180038D08
0x180038920  mov     edx, 0F0h
0x180038925  jmp     loc_180038CEE
0x18003892a  lea     rcx, [rbp+4Fh+var_80]
0x18003892e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038933  lea     r8, [rbp+4Fh+var_80]; unsigned int
0x180038937  mov     edx, edi; struct IMFSample *
0x180038939  mov     rcx, r15; this
0x18003893c  call    ?DXGIBufferFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAPEAUIMFDXGIBuffer@@@Z; MFD3D::DXGIBufferFromSample(IMFSample *,ulong,IMFDXGIBuffer * *)
0x180038941  mov     ebx, eax
0x180038943  test    eax, eax
0x180038945  jns     loc_1800389DA
0x18003894b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038952  test    rcx, rcx
0x180038955  jnz     short loc_180038998
0x180038957  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003895d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038964  mov     rcx, rax
0x180038967  test    rax, rax
0x18003896a  jz      short loc_18003898A
0x18003896c  mov     rax, [rax]
0x18003896f  mov     edx, 7F0h
0x180038974  mov     rax, [rax+8]
0x180038978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003897d  test    eax, eax
0x18003897f  jz      short loc_18003898A
0x180038981  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038988  jmp     short loc_180038998
0x18003898a  lea     rcx, qword_180153440; this
0x180038991  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038998  cmp     [rcx+8], r12b
0x18003899c  jz      short loc_1800389C3
0x18003899e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800389a3  cmp     [rax+7CCh], ebx
0x1800389a9  jz      short loc_1800389C3
0x1800389ab  mov     r9d, ebx; int
0x1800389ae  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x1800389b5  mov     r8d, 1048h; int
0x1800389bb  mov     rcx, rax; this
0x1800389be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800389c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800389ca  jb      loc_180038D08
0x1800389d0  mov     edx, 0F1h
0x1800389d5  jmp     loc_180038CEE
0x1800389da  mov     rdi, qword ptr [rbp+4Fh+var_80]
0x1800389de  lea     rcx, [rbp+4Fh+var_88]
0x1800389e2  mov     rax, [rdi]
0x1800389e5  mov     rbx, [rax+18h]
0x1800389e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800389ee  lea     r8, [rbp+4Fh+var_88]
0x1800389f2  mov     rcx, rdi
0x1800389f5  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800389fc  mov     rax, rbx
0x1800389ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a04  mov     ebx, eax
0x180038a06  test    eax, eax
0x180038a08  jns     loc_180038A9D
0x180038a0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038a15  test    rcx, rcx
0x180038a18  jnz     short loc_180038A5B
0x180038a1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038a20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038a27  mov     rcx, rax
0x180038a2a  test    rax, rax
0x180038a2d  jz      short loc_180038A4D
0x180038a2f  mov     rax, [rax]
0x180038a32  mov     edx, 7F0h
0x180038a37  mov     rax, [rax+8]
0x180038a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038a40  test    eax, eax
0x180038a42  jz      short loc_180038A4D
0x180038a44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038a4b  jmp     short loc_180038A5B
0x180038a4d  lea     rcx, qword_180153440; this
0x180038a54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038a5b  cmp     [rcx+8], r12b
0x180038a5f  jz      short loc_180038A86
0x180038a61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038a66  cmp     [rax+7CCh], ebx
0x180038a6c  jz      short loc_180038A86
0x180038a6e  mov     r9d, ebx; int
0x180038a71  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038a78  mov     r8d, 1049h; int
0x180038a7e  mov     rcx, rax; this
0x180038a81  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038a86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038a8d  jb      loc_180038D08
0x180038a93  mov     edx, 0F2h
0x180038a98  jmp     loc_180038CEE
0x180038a9d  mov     rcx, [rbp+4Fh+var_88]
0x180038aa1  lea     rdx, [rbp+4Fh+var_78]
0x180038aa5  mov     rax, [rcx]
0x180038aa8  mov     rax, [rax+50h]
0x180038aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ab1  mov     eax, [rbp+4Fh+var_58]
0x180038ab4  lea     rcx, [rbp+4Fh+var_90]
0x180038ab8  or      eax, [rbp+4Fh+arg_20]
0x180038abb  mov     rdi, [rsi+8E8h]
0x180038ac2  and     eax, 0FFFFF9FFh
0x180038ac7  mov     [rbp+4Fh+var_58], eax
0x180038aca  mov     [rbp+4Fh+var_54], r12d
0x180038ace  mov     dword ptr [rbp+4Fh+var_68+0Ch], r12d
0x180038ad2  mov     dword ptr [rbp+4Fh+var_78+0Ch], 1
0x180038ad9  mov     rax, [rdi]
0x180038adc  mov     rbx, [rax+28h]
0x180038ae0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038ae5  lea     r9, [rbp+4Fh+var_90]
0x180038ae9  xor     r8d, r8d
0x180038aec  lea     rdx, [rbp+4Fh+var_78]
0x180038af0  mov     rcx, rdi
0x180038af3  mov     rax, rbx
0x180038af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038afb  mov     ebx, eax
0x180038afd  test    eax, eax
0x180038aff  jns     loc_180038B94
0x180038b05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038b0c  test    rcx, rcx
0x180038b0f  jnz     short loc_180038B52
0x180038b11  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038b17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038b1e  mov     rcx, rax
0x180038b21  test    rax, rax
0x180038b24  jz      short loc_180038B44
0x180038b26  mov     rax, [rax]
0x180038b29  mov     edx, 7F0h
0x180038b2e  mov     rax, [rax+8]
0x180038b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b37  test    eax, eax
0x180038b39  jz      short loc_180038B44
0x180038b3b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038b42  jmp     short loc_180038B52
0x180038b44  lea     rcx, qword_180153440; this
0x180038b4b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038b52  cmp     [rcx+8], r12b
0x180038b56  jz      short loc_180038B7D
0x180038b58  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038b5d  cmp     [rax+7CCh], ebx
0x180038b63  jz      short loc_180038B7D
0x180038b65  mov     r9d, ebx; int
0x180038b68  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038b6f  mov     r8d, 1053h; int
0x180038b75  mov     rcx, rax; this
0x180038b78  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038b7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038b84  jb      loc_180038D08
0x180038b8a  mov     edx, 0F3h
0x180038b8f  jmp     loc_180038CEE
0x180038b94  lea     rcx, [rbp+4Fh+var_98]
0x180038b98  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180038b9d  mov     rdx, [rbp+4Fh+var_90]
0x180038ba1  lea     rax, [rbp+4Fh+var_98]
0x180038ba5  mov     [rsp+0D0h+var_B0], rax
0x180038baa  call    dlMFCreateDXGISurfaceBuffer
0x180038baf  mov     ebx, eax
0x180038bb1  test    eax, eax
0x180038bb3  jns     loc_180038C48
0x180038bb9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bc0  test    rcx, rcx
0x180038bc3  jnz     short loc_180038C06
0x180038bc5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038bcb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bd2  mov     rcx, rax
0x180038bd5  test    rax, rax
0x180038bd8  jz      short loc_180038BF8
0x180038bda  mov     rax, [rax]
0x180038bdd  mov     edx, 7F0h
0x180038be2  mov     rax, [rax+8]
0x180038be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038beb  test    eax, eax
0x180038bed  jz      short loc_180038BF8
0x180038bef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038bf6  jmp     short loc_180038C06
0x180038bf8  lea     rcx, qword_180153440; this
0x180038bff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c06  cmp     [rcx+8], r12b
0x180038c0a  jz      short loc_180038C31
0x180038c0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038c11  cmp     [rax+7CCh], ebx
0x180038c17  jz      short loc_180038C31
0x180038c19  mov     r9d, ebx; int
0x180038c1c  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038c23  mov     r8d, 1054h; int
0x180038c29  mov     rcx, rax; this
0x180038c2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180038c31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180038c38  jb      loc_180038D08
0x180038c3e  mov     edx, 0F4h
0x180038c43  jmp     loc_180038CEE
0x180038c48  mov     rcx, [r14]
0x180038c4b  mov     rdx, [rbp+4Fh+var_98]
0x180038c4f  mov     rax, [rcx]
0x180038c52  mov     rax, [rax+150h]
0x180038c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c5e  mov     ebx, eax
0x180038c60  test    eax, eax
0x180038c62  jns     loc_180038D08
0x180038c68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c6f  test    rcx, rcx
0x180038c72  jnz     short loc_180038CB5
0x180038c74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180038c7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180038c81  mov     rcx, rax
0x180038c84  test    rax, rax
0x180038c87  jz      short loc_180038CA7
0x180038c89  mov     rax, [rax]
0x180038c8c  mov     edx, 7F0h
0x180038c91  mov     rax, [rax+8]
0x180038c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c9a  test    eax, eax
0x180038c9c  jz      short loc_180038CA7
0x180038c9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180038ca5  jmp     short loc_180038CB5
0x180038ca7  lea     rcx, qword_180153440; this
0x180038cae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180038cb5  cmp     [rcx+8], r12b
0x180038cb9  jz      short loc_180038CE0
0x180038cbb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180038cc0  cmp     [rax+7CCh], ebx
0x180038cc6  jz      short loc_180038CE0
0x180038cc8  mov     r9d, ebx; int
0x180038ccb  lea     rdx, aCxcodevideopro_70; "CxCodeVideoProcD3D11DataHandler::Ensure"...
0x180038cd2  mov     r8d, 1055h; int
  ... truncated ...
```
