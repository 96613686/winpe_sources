# CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample(uint,uint,uint)

- ea: `0x18005342c`
- end: `0x1800539ae`
- name: `?CreateD3D11ShaderPostTempSample@CxCodeVideoProcD3D11DataHandler@@AEAAJIII@Z`
- size: `1410`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3D11DataHandler *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d0d4`
- `0x18003eb08`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001bdb0`
- `0x18001e060`
- `0x18003639c`
- `0x18005342c`
- `0x180054140`
- `0x180066ee0`
- `0x1800734e0`
- `0x1800bef3c`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x1800534e5`
- `MFPlat!MFCreateSample` at `0x1800534e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053501`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053717`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800537a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053835`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053501`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053717`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800537a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180053835`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800538c4`

## string_xrefs

- `0x1800534ca`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`
- `0x180053558`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`
- `0x18005376e`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`
- `0x1800537fd`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`
- `0x18005388c`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`
- `0x18005391b`: `CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample(
        CxCodeVideoProcD3D11DataHandler *this,
        int a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  __int64 v8; // rax
  unsigned int v9; // r15d
  MFD3D **v10; // r13
  HRESULT v11; // ebx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int128 *, _QWORD, __int64 *); // rbx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct ID3D11ShaderResourceView **v37; // [rsp+38h] [rbp-61h]
  _BYTE v38[8]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v39; // [rsp+48h] [rbp-51h] BYREF
  __int64 v40; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v41; // [rsp+58h] [rbp-41h]
  int v42; // [rsp+5Ch] [rbp-3Dh] BYREF
  unsigned int v43; // [rsp+60h] [rbp-39h] BYREF
  struct ID3D11ShaderResourceView *v44; // [rsp+68h] [rbp-31h] BYREF
  __int128 v45; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v46[2]; // [rsp+80h] [rbp-19h] BYREF

  v41 = a4;
  v4 = 0;
  v40 = 0;
  v39 = 0;
  memset(v46, 0, 28);
  v45 = 0;
  `vector constructor iterator'(&v43, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::ComPtr<ID3D11ComputeShader>);
  v8 = *((_QWORD *)this + 2);
  v9 = 1;
  v42 = 0;
  if ( *(_DWORD *)(v8 + 356) && *(_DWORD *)(v8 + 744) == 1 )
    v9 = 2;
  v10 = (MFD3D **)((char *)this + 1168);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1168);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v38,
    "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
    2886);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1168);
  v11 = MFCreateSample((IMFSample **)this + 146);
  if ( v11 >= 0 )
  {
    v16 = *((_QWORD *)this + 2);
    v45 = 0;
    memset(v46, 0, 28);
    v17 = *(_DWORD *)(v16 + 1196);
    v18 = v41;
    DWORD2(v46[1]) = a2;
    *(_QWORD *)&v46[0] = v17 | 0x100000000LL;
    LODWORD(v46[1]) = 40;
    *((_QWORD *)&v45 + 1) = 0x100000001LL;
    *(_QWORD *)&v45 = __PAIR64__(v41, a3);
    HIDWORD(v46[0]) = 0;
    while ( v4 < v9 )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          171,
          &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
          this,
          v17,
          a3,
          v18);
      v19 = *((_QWORD *)this + 285);
      v20 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, __int64 *))(*(_QWORD *)v19 + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      v11 = v20(v19, &v45, 0, &v39);
      if ( v11 < 0 )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
              2904,
              v11);
        }
        if ( g_wppLevels )
        {
          v15 = 172;
          goto LABEL_64;
        }
        break;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      v11 = dlMFCreateDXGISurfaceBuffer(v21, v39, v22, v23, (__int64)&v40);
      if ( v11 < 0 )
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
          if ( *((_DWORD *)v32 + 499) != v11 )
            CallStackContext::TraceFailure(
              v32,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
              2905,
              v11);
        }
        if ( g_wppLevels )
        {
          v15 = 173;
          goto LABEL_64;
        }
        break;
      }
      v11 = (*(__int64 (__fastcall **)(MFD3D *, __int64))(*(_QWORD *)*v10 + 336LL))(*v10, v40);
      if ( v11 < 0 )
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
          if ( *((_DWORD *)v29 + 499) != v11 )
            CallStackContext::TraceFailure(
              v29,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
              2906,
              v11);
        }
        if ( g_wppLevels )
        {
          v15 = 174;
          goto LABEL_64;
        }
        break;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      v11 = MFD3D::ShaderInputViewFromSample(*v10, 0, *((_QWORD *)this + 285), 0, (MFD3D *)&v42, &v43, &v44, v37);
      if ( v11 < 0 )
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
          if ( *((_DWORD *)v26 + 499) != v11 )
            CallStackContext::TraceFailure(
              v26,
              "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
              2909,
              v11);
        }
        if ( g_wppLevels )
        {
          v15 = 175;
          goto LABEL_64;
        }
        break;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      v17 = v46[0];
      ++v4;
      v18 = DWORD1(v45);
      a3 = v45;
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v11 )
        CallStackContext::TraceFailure(
          v14,
          "CxCodeVideoProcD3D11DataHandler::CreateD3D11ShaderPostTempSample",
          2886,
          v11);
    }
    if ( g_wppLevels )
    {
      v15 = 170;
LABEL_64:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v11);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  `vector destructor iterator'(&v43, 8u, 2u, Microsoft::WRL::ComPtr<ID3D11ComputeShader>::~ComPtr<ID3D11ComputeShader>);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005342c  push    rbp
0x18005342e  push    rbx
0x18005342f  push    rsi
0x180053430  push    rdi
0x180053431  push    r12
0x180053433  push    r13
0x180053435  push    r14
0x180053437  push    r15
0x180053439  lea     rbp, [rsp-1Fh]
0x18005343e  sub     rsp, 0B8h
0x180053445  mov     rax, cs:__security_cookie
0x18005344c  xor     rax, rsp
0x18005344f  mov     [rbp+57h+var_50], rax
0x180053453  xorps   xmm0, xmm0
0x180053456  mov     [rbp+57h+var_98], r9d
0x18005345a  xor     r12d, r12d
0x18005345d  lea     r9, ??0?$ComPtr@UID3D11ComputeShader@@@WRL@Microsoft@@QEAA@XZ; void *(*)(void *)
0x180053464  mov     edi, r8d
0x180053467  mov     [rbp+57h+var_A0], r12
0x18005346b  mov     esi, edx
0x18005346d  mov     [rbp+57h+var_A8], r12
0x180053471  mov     r14, rcx
0x180053474  lea     rcx, [rbp+57h+var_90]; void *
0x180053478  lea     ebx, [r12+2]
0x18005347d  movups  [rbp+57h+var_70], xmm0
0x180053481  mov     r8d, ebx; unsigned __int64
0x180053484  lea     edx, [rbx+6]; unsigned __int64
0x180053487  movups  [rbp+57h+var_80], xmm0
0x18005348b  movups  [rbp+57h+var_70+0Ch], xmm0
0x18005348f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180053494  mov     rax, [r14+10h]
0x180053498  lea     r15d, [r12+1]
0x18005349d  mov     [rbp+57h+var_94], r12d
0x1800534a1  cmp     [rax+164h], r12d
0x1800534a8  jz      short loc_1800534B5
0x1800534aa  cmp     [rax+2E8h], r15d
0x1800534b1  cmovz   r15d, ebx
0x1800534b5  lea     r13, [r14+490h]
0x1800534bc  mov     rcx, r13
0x1800534bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800534c4  mov     r8d, 0B46h; int
0x1800534ca  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x1800534d1  lea     rcx, [rbp+57h+var_B0]; this
0x1800534d5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800534da  mov     rcx, r13
0x1800534dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800534e2  mov     rcx, r13; ppIMFSample
0x1800534e5  call    cs:__imp_MFCreateSample
0x1800534eb  mov     ebx, eax
0x1800534ed  test    eax, eax
0x1800534ef  jns     loc_18005358B
0x1800534f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800534fc  test    rcx, rcx
0x1800534ff  jnz     short loc_180053542
0x180053501  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180053507  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005350e  mov     rcx, rax
0x180053511  test    rax, rax
0x180053514  jz      short loc_180053534
0x180053516  mov     rax, [rax]
0x180053519  mov     edx, 7F0h
0x18005351e  mov     rax, [rax+8]
0x180053522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053527  test    eax, eax
0x180053529  jz      short loc_180053534
0x18005352b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053532  jmp     short loc_180053542
0x180053534  lea     rcx, qword_180153440; this
0x18005353b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053542  cmp     [rcx+8], r12b
0x180053546  jz      short loc_18005356D
0x180053548  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005354d  cmp     [rax+7CCh], ebx
0x180053553  jz      short loc_18005356D
0x180053555  mov     r9d, ebx; int
0x180053558  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x18005355f  mov     r8d, 0B46h; int
0x180053565  mov     rcx, rax; this
0x180053568  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005356d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053574  jb      loc_180053958
0x18005357a  mov     edx, 0AAh
0x18005357f  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180053586  jmp     loc_180053941
0x18005358b  mov     rax, [r14+10h]
0x18005358f  xorps   xmm0, xmm0
0x180053592  movups  [rbp+57h+var_80], xmm0
0x180053596  mov     edx, 1
0x18005359b  movups  [rbp+57h+var_70], xmm0
0x18005359f  movups  [rbp+57h+var_70+0Ch], xmm0
0x1800535a3  mov     ecx, [rax+4ACh]
0x1800535a9  mov     eax, [rbp+57h+var_98]
0x1800535ac  mov     [rbp+57h+var_58], esi
0x1800535af  lea     rsi, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x1800535b6  mov     dword ptr [rbp+57h+var_80+4], eax
0x1800535b9  mov     dword ptr [rbp+57h+var_70], ecx
0x1800535bc  mov     dword ptr [rbp+57h+var_80+0Ch], edx
0x1800535bf  mov     [rbp+57h+var_60], 28h ; '('
0x1800535c6  mov     dword ptr [rbp+57h+var_80+8], edx
0x1800535c9  mov     dword ptr [rbp+57h+var_80], edi
0x1800535cc  mov     dword ptr [rbp+57h+var_70+0Ch], r12d
0x1800535d0  mov     dword ptr [rbp+57h+var_70+4], edx
0x1800535d3  cmp     r12d, r15d
0x1800535d6  jnb     loc_180053958
0x1800535dc  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800535e3  jb      short loc_18005360F
0x1800535e5  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800535e9  mov     edx, 0ABh
0x1800535ee  mov     dword ptr [rsp+0F0h+var_C8], edi
0x1800535f2  mov     r9, r14
0x1800535f5  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x1800535f9  mov     r8, rsi
0x1800535fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180053603  mov     rcx, [rcx+150h]
0x18005360a  call    WPP_SF_qddd
0x18005360f  mov     rdi, [r14+8E8h]
0x180053616  lea     rcx, [rbp+57h+var_A8]
0x18005361a  mov     rax, [rdi]
0x18005361d  mov     rbx, [rax+28h]
0x180053621  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053626  lea     r9, [rbp+57h+var_A8]
0x18005362a  xor     r8d, r8d
0x18005362d  lea     rdx, [rbp+57h+var_80]
0x180053631  mov     rcx, rdi
0x180053634  mov     rax, rbx
0x180053637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005363c  xor     edi, edi
0x18005363e  mov     ebx, eax
0x180053640  test    eax, eax
0x180053642  js      loc_1800538B8
0x180053648  lea     rcx, [rbp+57h+var_A0]
0x18005364c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053651  mov     rdx, [rbp+57h+var_A8]
0x180053655  lea     rax, [rbp+57h+var_A0]
0x180053659  mov     [rsp+0F0h+var_D0], rax
0x18005365e  call    dlMFCreateDXGISurfaceBuffer
0x180053663  mov     ebx, eax
0x180053665  test    eax, eax
0x180053667  js      loc_180053829
0x18005366d  mov     rcx, [r13+0]
0x180053671  mov     rdx, [rbp+57h+var_A0]
0x180053675  mov     rax, [rcx]
0x180053678  mov     rax, [rax+150h]
0x18005367f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053684  mov     ebx, eax
0x180053686  test    eax, eax
0x180053688  js      loc_18005379A
0x18005368e  lea     rcx, [rbp+57h+var_88]
0x180053692  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180053697  lea     rcx, [rbp+57h+var_90]
0x18005369b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800536a0  mov     r8, [r14+8E8h]; unsigned int
0x1800536a7  lea     rax, [rbp+57h+var_88]
0x1800536ab  mov     rcx, [r13+0]; this
0x1800536af  xor     r9d, r9d; struct ID3D11Device *
0x1800536b2  mov     [rsp+0F0h+var_C0], rax; struct ID3D11ShaderResourceView **
0x1800536b7  xor     edx, edx; struct IMFSample *
0x1800536b9  lea     rax, [rbp+57h+var_90]
0x1800536bd  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x1800536c2  lea     rax, [rbp+57h+var_94]
0x1800536c6  mov     [rsp+0F0h+var_D0], rax; MFD3D *
0x1800536cb  call    ?ShaderInputViewFromSample@MFD3D@@YAJPEAUIMFSample@@KPEAUID3D11Device@@HPEAIPEAPEAUID3D11ShaderResourceView@@3@Z; MFD3D::ShaderInputViewFromSample(IMFSample *,ulong,ID3D11Device *,int,uint *,ID3D11ShaderResourceView * *,ID3D11ShaderResourceView * *)
0x1800536d0  mov     ebx, eax
0x1800536d2  test    eax, eax
0x1800536d4  js      short loc_18005370B
0x1800536d6  lea     rcx, [rbp+57h+var_A0]
0x1800536da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800536df  lea     rcx, [rbp+57h+var_A8]
0x1800536e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800536e8  lea     rcx, [rbp+57h+var_90]
0x1800536ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800536f1  lea     rcx, [rbp+57h+var_88]
0x1800536f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800536fa  mov     ecx, dword ptr [rbp+57h+var_70]
0x1800536fd  inc     r12d
0x180053700  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180053703  mov     edi, dword ptr [rbp+57h+var_80]
0x180053706  jmp     loc_1800535D3
0x18005370b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053712  test    rcx, rcx
0x180053715  jnz     short loc_180053758
0x180053717  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005371d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053724  mov     rcx, rax
0x180053727  test    rax, rax
0x18005372a  jz      short loc_18005374A
0x18005372c  mov     rax, [rax]
0x18005372f  mov     edx, 7F0h
0x180053734  mov     rax, [rax+8]
0x180053738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005373d  test    eax, eax
0x18005373f  jz      short loc_18005374A
0x180053741  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053748  jmp     short loc_180053758
0x18005374a  lea     rcx, qword_180153440; this
0x180053751  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053758  cmp     [rcx+8], dil
0x18005375c  jz      short loc_180053783
0x18005375e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053763  cmp     [rax+7CCh], ebx
0x180053769  jz      short loc_180053783
0x18005376b  mov     r9d, ebx; int
0x18005376e  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x180053775  mov     r8d, 0B5Dh; int
0x18005377b  mov     rcx, rax; this
0x18005377e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053783  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005378a  jb      loc_180053958
0x180053790  mov     edx, 0AFh
0x180053795  jmp     loc_18005393E
0x18005379a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800537a1  test    rcx, rcx
0x1800537a4  jnz     short loc_1800537E7
0x1800537a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800537ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800537b3  mov     rcx, rax
0x1800537b6  test    rax, rax
0x1800537b9  jz      short loc_1800537D9
0x1800537bb  mov     rax, [rax]
0x1800537be  mov     edx, 7F0h
0x1800537c3  mov     rax, [rax+8]
0x1800537c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537cc  test    eax, eax
0x1800537ce  jz      short loc_1800537D9
0x1800537d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800537d7  jmp     short loc_1800537E7
0x1800537d9  lea     rcx, qword_180153440; this
0x1800537e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800537e7  cmp     [rcx+8], dil
0x1800537eb  jz      short loc_180053812
0x1800537ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800537f2  cmp     [rax+7CCh], ebx
0x1800537f8  jz      short loc_180053812
0x1800537fa  mov     r9d, ebx; int
0x1800537fd  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x180053804  mov     r8d, 0B5Ah; int
0x18005380a  mov     rcx, rax; this
0x18005380d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180053812  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180053819  jb      loc_180053958
0x18005381f  mov     edx, 0AEh
0x180053824  jmp     loc_18005393E
0x180053829  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053830  test    rcx, rcx
0x180053833  jnz     short loc_180053876
0x180053835  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005383b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180053842  mov     rcx, rax
0x180053845  test    rax, rax
0x180053848  jz      short loc_180053868
0x18005384a  mov     rax, [rax]
0x18005384d  mov     edx, 7F0h
0x180053852  mov     rax, [rax+8]
0x180053856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005385b  test    eax, eax
0x18005385d  jz      short loc_180053868
0x18005385f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180053866  jmp     short loc_180053876
0x180053868  lea     rcx, qword_180153440; this
0x18005386f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053876  cmp     [rcx+8], dil
0x18005387a  jz      short loc_1800538A1
0x18005387c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053881  cmp     [rax+7CCh], ebx
0x180053887  jz      short loc_1800538A1
0x180053889  mov     r9d, ebx; int
0x18005388c  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x180053893  mov     r8d, 0B59h; int
0x180053899  mov     rcx, rax; this
0x18005389c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800538a1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800538a8  jb      loc_180053958
0x1800538ae  mov     edx, 0ADh
0x1800538b3  jmp     loc_18005393E
0x1800538b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538bf  test    rcx, rcx
0x1800538c2  jnz     short loc_180053905
0x1800538c4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800538ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538d1  mov     rcx, rax
0x1800538d4  test    rax, rax
0x1800538d7  jz      short loc_1800538F7
0x1800538d9  mov     rax, [rax]
0x1800538dc  mov     edx, 7F0h
0x1800538e1  mov     rax, [rax+8]
0x1800538e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538ea  test    eax, eax
0x1800538ec  jz      short loc_1800538F7
0x1800538ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800538f5  jmp     short loc_180053905
0x1800538f7  lea     rcx, qword_180153440; this
0x1800538fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180053905  cmp     [rcx+8], dil
0x180053909  jz      short loc_180053930
0x18005390b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180053910  cmp     [rax+7CCh], ebx
0x180053916  jz      short loc_180053930
0x180053918  mov     r9d, ebx; int
0x18005391b  lea     rdx, aCxcodevideopro_111; "CxCodeVideoProcD3D11DataHandler::Create"...
0x180053922  mov     r8d, 0B58h; int
  ... truncated ...
```
