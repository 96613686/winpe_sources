# CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate(uint)

- ea: `0x18003c230`
- end: `0x18003c716`
- name: `?CreateRendererEffectIntermediate@CxCodeVideoProcD3D11DataHandler@@UEAAJI@Z`
- size: `1254`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb40`
- `0x18003d0d4`
- `0x18005ddd0`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x18003c230`
- `0x18003c71c`
- `0x180054140`
- `0x180066ee0`
- `0x1800734e0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x18003c2d6`
- `MFPlat!MFCreateSample` at `0x18003c2d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c5a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c62f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c2f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c511`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c5a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003c62f`

## string_xrefs

- `0x18003c291`: `CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate`
- `0x18003c349`: `CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate`
- `0x18003c568`: `CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate`
- `0x18003c5f7`: `CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate`
- `0x18003c686`: `CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate(
        CxCodeVideoProcD3D11DataHandler *this,
        int a2)
{
  __int64 v3; // rcx
  HRESULT v4; // ebx
  unsigned int v6; // r8d
  __int64 v7; // rax
  unsigned int v8; // r12d
  __int64 v9; // rbx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  _DWORD *v14; // rcx
  int v15; // r9d
  int v16; // eax
  int v17; // r8d
  unsigned int i; // r15d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _OWORD *, _QWORD, __int64 *); // rbx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  _BYTE v34[8]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v35; // [rsp+48h] [rbp-11h] BYREF
  __int64 v36; // [rsp+50h] [rbp-9h] BYREF
  _OWORD v37[3]; // [rsp+58h] [rbp-1h] BYREF

  v3 = *((_QWORD *)this + 2);
  v4 = 0;
  v36 = 0;
  memset(v37, 0, 44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v3 + 2128);
  if ( *((_QWORD *)this + 289) )
  {
    v7 = *((_QWORD *)this + 2);
    v35 = 0;
    v8 = (*(_DWORD *)(v7 + 356) == 1) + 1;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v34,
      "CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate",
      2670);
    v9 = *((_QWORD *)this + 2);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v9 + 2128);
    v4 = MFCreateSample((IMFSample **)(v9 + 2128));
    if ( v4 >= 0 )
    {
      v14 = (_DWORD *)*((_QWORD *)this + 2);
      *(_QWORD *)&v37[0] = 0;
      v37[1] = 0;
      *(_QWORD *)((char *)&v37[2] + 4) = 0;
      LODWORD(v37[2]) = 40;
      *((_QWORD *)&v37[0] + 1) = 0x100000001LL;
      if ( v14[526] == 2 )
        v15 = v14[82];
      else
        v15 = v14[141];
      LODWORD(v37[1]) = v15;
      if ( ((v14[526] - 2) & 0xFFFFFFFB) != 0 )
      {
        v16 = v14[101];
        LODWORD(v37[0]) = v16;
        v17 = v14[100];
      }
      else
      {
        v16 = v14[13];
        LODWORD(v37[0]) = v16;
        v17 = v14[12];
      }
      DWORD1(v37[0]) = v17;
      DWORD1(v37[1]) = 1;
      DWORD2(v37[2]) = a2;
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          153,
          &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
          this,
          v15,
          v16,
          v17);
      for ( i = 0; ; ++i )
      {
        if ( i >= v8 )
        {
          *(_DWORD *)(*((_QWORD *)this + 2) + 1204LL) = v37[1];
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          goto LABEL_60;
        }
        v19 = *((_QWORD *)this + 285);
        v20 = *(__int64 (__fastcall **)(__int64, _OWORD *, _QWORD, __int64 *))(*(_QWORD *)v19 + 40LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        v4 = v20(v19, v37, 0, &v35);
        if ( v4 < 0 )
          break;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        v4 = dlMFCreateDXGISurfaceBuffer(v21, v35, v22, v23, (__int64)&v36);
        if ( v4 < 0 )
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate",
                2698,
                v4);
          }
          if ( g_wppLevels )
          {
            v13 = 155;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
        v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 2128LL) + 336LL))(
               *(_QWORD *)(*((_QWORD *)this + 2) + 2128LL),
               v36);
        if ( v4 < 0 )
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
            if ( *((_DWORD *)v26 + 499) != v4 )
              CallStackContext::TraceFailure(
                v26,
                "CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate",
                2699,
                v4);
          }
          if ( g_wppLevels )
          {
            v13 = 156;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      }
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
        if ( *((_DWORD *)v32 + 499) != v4 )
          CallStackContext::TraceFailure(
            v32,
            "CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate",
            2697,
            v4);
      }
      if ( g_wppLevels )
      {
        v13 = 154;
        goto LABEL_13;
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
        if ( *((_DWORD *)v12 + 499) != v4 )
          CallStackContext::TraceFailure(
            v12,
            "CxCodeVideoProcD3D11DataHandler::CreateRendererEffectIntermediate",
            2670,
            v4);
      }
      if ( g_wppLevels )
      {
        v13 = 152;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v4);
      }
    }
LABEL_14:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  }
  else
  {
LABEL_60:
    CxCodeVideoProcD3D11DataHandler::ClearFrame(
      this,
      *(struct IMFSample **)(*((_QWORD *)this + 2) + 2128LL),
      v6,
      v37[1]);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c230  mov     [rsp-8+arg_10], rbx
0x18003c235  push    rbp
0x18003c236  push    rsi
0x18003c237  push    rdi
0x18003c238  push    r12
0x18003c23a  push    r15
0x18003c23c  lea     rbp, [rsp-37h]
0x18003c241  sub     rsp, 90h
0x18003c248  mov     rax, cs:__security_cookie
0x18003c24f  xor     rax, rsp
0x18003c252  mov     [rbp+57h+var_28], rax
0x18003c256  xorps   xmm0, xmm0
0x18003c259  mov     rsi, rcx
0x18003c25c  mov     rcx, [rcx+10h]
0x18003c260  xor     ebx, ebx
0x18003c262  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18003c266  add     rcx, 850h
0x18003c26d  mov     [rbp+57h+var_60], rbx
0x18003c271  mov     edi, edx
0x18003c273  movups  [rbp+57h+var_58], xmm0
0x18003c277  movups  xmmword ptr [rbp+57h+var_48+0Ch], xmm0
0x18003c27b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c280  cmp     [rsi+908h], rbx
0x18003c287  jz      loc_18003C6D1
0x18003c28d  mov     rax, [rsi+10h]
0x18003c291  lea     rdx, aCxcodevideopro_120; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003c298  xor     r12d, r12d
0x18003c29b  mov     [rbp+57h+var_68], rbx
0x18003c29f  mov     r15d, 0A6Eh
0x18003c2a5  lea     rcx, [rbp+57h+var_70]; this
0x18003c2a9  mov     r8d, r15d; int
0x18003c2ac  cmp     dword ptr [rax+164h], 1
0x18003c2b3  setz    r12b
0x18003c2b7  inc     r12d
0x18003c2ba  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003c2bf  mov     rbx, [rsi+10h]
0x18003c2c3  lea     rcx, [rbx+850h]
0x18003c2ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c2cf  lea     rcx, [rbx+850h]; ppIMFSample
0x18003c2d6  call    cs:__imp_MFCreateSample
0x18003c2dc  mov     ebx, eax
0x18003c2de  test    eax, eax
0x18003c2e0  jns     loc_18003C39E
0x18003c2e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c2ed  test    rcx, rcx
0x18003c2f0  jnz     short loc_18003C333
0x18003c2f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c2f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c2ff  mov     rcx, rax
0x18003c302  test    rax, rax
0x18003c305  jz      short loc_18003C325
0x18003c307  mov     rax, [rax]
0x18003c30a  mov     edx, 7F0h
0x18003c30f  mov     rax, [rax+8]
0x18003c313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c318  test    eax, eax
0x18003c31a  jz      short loc_18003C325
0x18003c31c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c323  jmp     short loc_18003C333
0x18003c325  lea     rcx, qword_180153440; this
0x18003c32c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c333  cmp     byte ptr [rcx+8], 0
0x18003c337  jz      short loc_18003C35B
0x18003c339  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c33e  cmp     [rax+7CCh], ebx
0x18003c344  jz      short loc_18003C35B
0x18003c346  mov     r9d, ebx; int
0x18003c349  lea     rdx, aCxcodevideopro_120; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003c350  mov     r8d, r15d; int
0x18003c353  mov     rcx, rax; this
0x18003c356  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c35b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c362  jb      short loc_18003C387
0x18003c364  mov     edx, 98h
0x18003c369  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c370  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18003c377  mov     r9, rsi
0x18003c37a  mov     dword ptr [rsp+0B0h+var_90], ebx
0x18003c37e  mov     rcx, [rcx+10h]
0x18003c382  call    WPP_SF_qD
0x18003c387  lea     rcx, [rbp+57h+var_70]; this
0x18003c38b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c390  lea     rcx, [rbp+57h+var_68]
0x18003c394  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c399  jmp     loc_18003C6E8
0x18003c39e  mov     rcx, [rsi+10h]
0x18003c3a2  xorps   xmm0, xmm0
0x18003c3a5  mov     qword ptr [rbp+57h+var_58], 0
0x18003c3ad  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18003c3b2  mov     [rbp+57h+var_34], 0
0x18003c3ba  mov     dword ptr [rbp+57h+var_58+0Ch], 1
0x18003c3c1  mov     [rbp+57h+var_38], 28h ; '('
0x18003c3c8  mov     dword ptr [rbp+57h+var_58+8], 1
0x18003c3cf  cmp     dword ptr [rcx+838h], 2
0x18003c3d6  jnz     short loc_18003C3E1
0x18003c3d8  mov     r9d, [rcx+148h]
0x18003c3df  jmp     short loc_18003C3E8
0x18003c3e1  mov     r9d, [rcx+234h]
0x18003c3e8  mov     [rbp+57h+var_48], r9d
0x18003c3ec  mov     eax, [rcx+838h]
0x18003c3f2  sub     eax, 2
0x18003c3f5  test    eax, 0FFFFFFFBh
0x18003c3fa  jz      short loc_18003C40E
0x18003c3fc  mov     eax, [rcx+194h]
0x18003c402  mov     dword ptr [rbp+57h+var_58], eax
0x18003c405  mov     r8d, [rcx+190h]
0x18003c40c  jmp     short loc_18003C418
0x18003c40e  mov     eax, [rcx+34h]
0x18003c411  mov     dword ptr [rbp+57h+var_58], eax
0x18003c414  mov     r8d, [rcx+30h]
0x18003c418  mov     dword ptr [rbp+57h+var_58+4], r8d
0x18003c41c  mov     [rbp+57h+var_48+4], 1
0x18003c423  mov     dword ptr [rbp+57h+var_34+4], edi
0x18003c426  cmp     cs:byte_180153DE0, 20h ; ' '
0x18003c42d  jb      short loc_18003C45F
0x18003c42f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c436  mov     edx, 99h
0x18003c43b  mov     [rsp+0B0h+var_80], r8d
0x18003c440  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18003c447  mov     [rsp+0B0h+var_88], eax
0x18003c44b  mov     dword ptr [rsp+0B0h+var_90], r9d
0x18003c450  mov     r9, rsi
0x18003c453  mov     rcx, [rcx+150h]
0x18003c45a  call    WPP_SF_qddd
0x18003c45f  xor     r15d, r15d
0x18003c462  cmp     r15d, r12d
0x18003c465  jnb     loc_18003C6B2
0x18003c46b  mov     rdi, [rsi+8E8h]
0x18003c472  lea     rcx, [rbp+57h+var_68]
0x18003c476  mov     rax, [rdi]
0x18003c479  mov     rbx, [rax+28h]
0x18003c47d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c482  lea     r9, [rbp+57h+var_68]
0x18003c486  xor     r8d, r8d
0x18003c489  lea     rdx, [rbp+57h+var_58]
0x18003c48d  mov     rcx, rdi
0x18003c490  mov     rax, rbx
0x18003c493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c498  mov     ebx, eax
0x18003c49a  test    eax, eax
0x18003c49c  js      loc_18003C623
0x18003c4a2  lea     rcx, [rbp+57h+var_60]
0x18003c4a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c4ab  mov     rdx, [rbp+57h+var_68]
0x18003c4af  lea     rax, [rbp+57h+var_60]
0x18003c4b3  mov     [rsp+0B0h+var_90], rax
0x18003c4b8  call    dlMFCreateDXGISurfaceBuffer
0x18003c4bd  mov     ebx, eax
0x18003c4bf  test    eax, eax
0x18003c4c1  js      loc_18003C594
0x18003c4c7  mov     rax, [rsi+10h]
0x18003c4cb  mov     rdx, [rbp+57h+var_60]
0x18003c4cf  mov     rcx, [rax+850h]
0x18003c4d6  mov     rax, [rcx]
0x18003c4d9  mov     rax, [rax+150h]
0x18003c4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4e5  mov     ebx, eax
0x18003c4e7  test    eax, eax
0x18003c4e9  js      short loc_18003C505
0x18003c4eb  lea     rcx, [rbp+57h+var_60]
0x18003c4ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c4f4  lea     rcx, [rbp+57h+var_68]
0x18003c4f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c4fd  inc     r15d
0x18003c500  jmp     loc_18003C462
0x18003c505  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c50c  test    rcx, rcx
0x18003c50f  jnz     short loc_18003C552
0x18003c511  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c517  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c51e  mov     rcx, rax
0x18003c521  test    rax, rax
0x18003c524  jz      short loc_18003C544
0x18003c526  mov     rax, [rax]
0x18003c529  mov     edx, 7F0h
0x18003c52e  mov     rax, [rax+8]
0x18003c532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c537  test    eax, eax
0x18003c539  jz      short loc_18003C544
0x18003c53b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c542  jmp     short loc_18003C552
0x18003c544  lea     rcx, qword_180153440; this
0x18003c54b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c552  cmp     byte ptr [rcx+8], 0
0x18003c556  jz      short loc_18003C57D
0x18003c558  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c55d  cmp     [rax+7CCh], ebx
0x18003c563  jz      short loc_18003C57D
0x18003c565  mov     r9d, ebx; int
0x18003c568  lea     rdx, aCxcodevideopro_120; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003c56f  mov     r8d, 0A8Bh; int
0x18003c575  mov     rcx, rax; this
0x18003c578  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c57d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c584  jb      loc_18003C387
0x18003c58a  mov     edx, 9Ch
0x18003c58f  jmp     loc_18003C369
0x18003c594  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c59b  test    rcx, rcx
0x18003c59e  jnz     short loc_18003C5E1
0x18003c5a0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c5a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5ad  mov     rcx, rax
0x18003c5b0  test    rax, rax
0x18003c5b3  jz      short loc_18003C5D3
0x18003c5b5  mov     rax, [rax]
0x18003c5b8  mov     edx, 7F0h
0x18003c5bd  mov     rax, [rax+8]
0x18003c5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5c6  test    eax, eax
0x18003c5c8  jz      short loc_18003C5D3
0x18003c5ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5d1  jmp     short loc_18003C5E1
0x18003c5d3  lea     rcx, qword_180153440; this
0x18003c5da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c5e1  cmp     byte ptr [rcx+8], 0
0x18003c5e5  jz      short loc_18003C60C
0x18003c5e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c5ec  cmp     [rax+7CCh], ebx
0x18003c5f2  jz      short loc_18003C60C
0x18003c5f4  mov     r9d, ebx; int
0x18003c5f7  lea     rdx, aCxcodevideopro_120; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003c5fe  mov     r8d, 0A8Ah; int
0x18003c604  mov     rcx, rax; this
0x18003c607  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c60c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c613  jb      loc_18003C387
0x18003c619  mov     edx, 9Bh
0x18003c61e  jmp     loc_18003C369
0x18003c623  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c62a  test    rcx, rcx
0x18003c62d  jnz     short loc_18003C670
0x18003c62f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003c635  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c63c  mov     rcx, rax
0x18003c63f  test    rax, rax
0x18003c642  jz      short loc_18003C662
0x18003c644  mov     rax, [rax]
0x18003c647  mov     edx, 7F0h
0x18003c64c  mov     rax, [rax+8]
0x18003c650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c655  test    eax, eax
0x18003c657  jz      short loc_18003C662
0x18003c659  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c660  jmp     short loc_18003C670
0x18003c662  lea     rcx, qword_180153440; this
0x18003c669  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003c670  cmp     byte ptr [rcx+8], 0
0x18003c674  jz      short loc_18003C69B
0x18003c676  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003c67b  cmp     [rax+7CCh], ebx
0x18003c681  jz      short loc_18003C69B
0x18003c683  mov     r9d, ebx; int
0x18003c686  lea     rdx, aCxcodevideopro_120; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18003c68d  mov     r8d, 0A89h; int
0x18003c693  mov     rcx, rax; this
0x18003c696  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003c69b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c6a2  jb      loc_18003C387
0x18003c6a8  mov     edx, 9Ah
0x18003c6ad  jmp     loc_18003C369
0x18003c6b2  mov     rcx, [rsi+10h]
0x18003c6b6  mov     eax, [rbp+57h+var_48]
0x18003c6b9  mov     [rcx+4B4h], eax
0x18003c6bf  lea     rcx, [rbp+57h+var_70]; this
0x18003c6c3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003c6c8  lea     rcx, [rbp+57h+var_68]
0x18003c6cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c6d1  mov     rdx, [rsi+10h]
0x18003c6d5  mov     rcx, rsi; this
0x18003c6d8  mov     r9d, [rbp+57h+var_48]; enum DXGI_FORMAT
0x18003c6dc  mov     rdx, [rdx+850h]; struct IMFSample *
0x18003c6e3  call    ?ClearFrame@CxCodeVideoProcD3D11DataHandler@@AEAAJPEAUIMFSample@@IW4DXGI_FORMAT@@@Z; CxCodeVideoProcD3D11DataHandler::ClearFrame(IMFSample *,uint,DXGI_FORMAT)
0x18003c6e8  lea     rcx, [rbp+57h+var_60]
0x18003c6ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003c6f1  mov     eax, ebx
0x18003c6f3  mov     rcx, [rbp+57h+var_28]
0x18003c6f7  xor     rcx, rsp; StackCookie
0x18003c6fa  call    __security_check_cookie
0x18003c6ff  mov     rbx, [rsp+0B0h+arg_10]
0x18003c707  add     rsp, 90h
0x18003c70e  pop     r15
0x18003c710  pop     r12
0x18003c712  pop     rdi
0x18003c713  pop     rsi
0x18003c714  pop     rbp
0x18003c715  retn
```
