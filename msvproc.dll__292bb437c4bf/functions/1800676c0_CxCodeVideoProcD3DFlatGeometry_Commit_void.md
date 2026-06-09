# CxCodeVideoProcD3DFlatGeometry::Commit(void)

- ea: `0x1800676c0`
- end: `0x180067ad2`
- name: `?Commit@CxCodeVideoProcD3DFlatGeometry@@UEAAJXZ`
- size: `1042`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DFlatGeometry *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x1800676c0`
- `0x180068fa8`
- `0x180069ca4`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006772e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006781e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067930`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800679d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006772e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006781e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067930`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800679d9`

## string_xrefs

- `0x1800676e4`: `CxCodeVideoProcD3DFlatGeometry::Commit`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DFlatGeometry::Commit(
        CxCodeVideoProcD3DFlatGeometry *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(CxCodeVideoProcD3DFlatGeometry *, __int128 *); // rax
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int128 v21; // [rsp+30h] [rbp-49h] BYREF
  _OWORD v22[4]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v23[64]; // [rsp+80h] [rbp+7h] BYREF
  char v24; // [rsp+E0h] [rbp+67h] BYREF
  struct stD3DVSConstants *v25; // [rsp+E8h] [rbp+6Fh] BYREF

  v4 = 0;
  if ( !*((_BYTE *)this + 40) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "CxCodeVideoProcD3DFlatGeometry::Commit", 186);
    v4 = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DFlatGeometry *))(*(_QWORD *)this + 16LL))(this);
    if ( v4 < 0 )
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcD3DFlatGeometry::Commit", 186, v4);
      }
      if ( !g_wppLevels )
        goto LABEL_52;
      v9 = 16;
      goto LABEL_13;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  }
  if ( *((_BYTE *)this + 41) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "CxCodeVideoProcD3DFlatGeometry::Commit", 190);
    v10 = *(__int64 (__fastcall **)(CxCodeVideoProcD3DFlatGeometry *, __int128 *))(*(_QWORD *)this + 56LL);
    v21 = *(_OWORD *)((char *)this + 24);
    v4 = v10(this, &v21);
    if ( v4 < 0 )
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
        if ( *((_DWORD *)v13 + 499) != v4 )
          CallStackContext::TraceFailure(v13, "CxCodeVideoProcD3DFlatGeometry::Commit", 190, v4);
      }
      if ( !g_wppLevels )
        goto LABEL_52;
      v9 = 17;
      goto LABEL_13;
    }
    *((_BYTE *)this + 41) = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  }
  if ( !*((_BYTE *)this + 42) )
    goto LABEL_53;
  v22[0] = DirectX::g_XMIdentityR0;
  v22[1] = DirectX::g_XMIdentityR1;
  v22[2] = DirectX::g_XMIdentityR2;
  v22[3] = DirectX::g_XMIdentityR3;
  CxCodeVideoProcD3DFlatGeometry::GetBaseProjectionMatrix(this, v23, a3, a4);
  v25 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "CxCodeVideoProcD3DFlatGeometry::Commit", 198);
  v4 = (*(__int64 (__fastcall **)(_QWORD, struct stD3DVSConstants **))(**((_QWORD **)this + 1) + 24LL))(
         *((_QWORD *)this + 1),
         &v25);
  if ( v4 >= 0 )
  {
    v4 = CxCodeVideoProcD3DGeometry::SetProjection(
           this,
           v25,
           (const struct DirectX::XMMATRIX *)v23,
           (const struct DirectX::XMMATRIX *)v22);
    if ( v4 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
      *((_BYTE *)this + 42) = 0;
      goto LABEL_52;
    }
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
      if ( *((_DWORD *)v19 + 499) != v4 )
        CallStackContext::TraceFailure(v19, "CxCodeVideoProcD3DFlatGeometry::Commit", 199, v4);
    }
    if ( !g_wppLevels )
      goto LABEL_52;
    v9 = 19;
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
      if ( *((_DWORD *)v16 + 499) != v4 )
        CallStackContext::TraceFailure(v16, "CxCodeVideoProcD3DFlatGeometry::Commit", 198, v4);
    }
    if ( !g_wppLevels )
      goto LABEL_52;
    v9 = 18;
  }
LABEL_13:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids, this, v4);
LABEL_52:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
LABEL_53:
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v24, "CxCodeVideoProcD3DFlatGeometry::Commit", 204);
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 20, &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids, this, v4);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800676c0  mov     [rsp-8+arg_10], rbx
0x1800676c5  mov     [rsp-8+arg_18], rdi
0x1800676ca  push    rbp
0x1800676cb  push    r14
0x1800676cd  push    r15
0x1800676cf  lea     rbp, [rsp-47h]
0x1800676d4  sub     rsp, 0C0h
0x1800676db  xor     ebx, ebx
0x1800676dd  lea     r15, WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids
0x1800676e4  lea     r14, aCxcodevideopro_50; "CxCodeVideoProcD3DFlatGeometry::Commit"
0x1800676eb  mov     rdi, rcx
0x1800676ee  cmp     [rcx+28h], bl
0x1800676f1  jnz     loc_1800677D0
0x1800676f7  mov     r8d, 0BAh; int
0x1800676fd  lea     rcx, [rbp+57h+arg_0]; this
0x180067701  mov     rdx, r14; char *
0x180067704  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067709  mov     rax, [rdi]
0x18006770c  mov     rcx, rdi
0x18006770f  mov     rax, [rax+10h]
0x180067713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067718  mov     ebx, eax
0x18006771a  test    eax, eax
0x18006771c  jns     loc_1800677C7
0x180067722  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067729  test    rcx, rcx
0x18006772c  jnz     short loc_18006776F
0x18006772e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067734  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006773b  mov     rcx, rax
0x18006773e  test    rax, rax
0x180067741  jz      short loc_180067761
0x180067743  mov     rax, [rax]
0x180067746  mov     edx, 7F0h
0x18006774b  mov     rax, [rax+8]
0x18006774f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067754  test    eax, eax
0x180067756  jz      short loc_180067761
0x180067758  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006775f  jmp     short loc_18006776F
0x180067761  lea     rcx, qword_180153440; this
0x180067768  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006776f  cmp     byte ptr [rcx+8], 0
0x180067773  jz      short loc_180067796
0x180067775  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006777a  cmp     [rax+7CCh], ebx
0x180067780  jz      short loc_180067796
0x180067782  mov     r9d, ebx; int
0x180067785  mov     r8d, 0BAh; int
0x18006778b  mov     rdx, r14; char *
0x18006778e  mov     rcx, rax; this
0x180067791  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067796  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006779d  jb      loc_180067A68
0x1800677a3  mov     edx, 10h
0x1800677a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800677af  mov     r9, rdi
0x1800677b2  mov     r8, r15
0x1800677b5  mov     [rsp+0D0h+var_B0], ebx
0x1800677b9  mov     rcx, [rcx+10h]
0x1800677bd  call    WPP_SF_qD
0x1800677c2  jmp     loc_180067A68
0x1800677c7  lea     rcx, [rbp+57h+arg_0]; this
0x1800677cb  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800677d0  cmp     byte ptr [rdi+29h], 0
0x1800677d4  jz      loc_1800678AA
0x1800677da  mov     r8d, 0BEh; int
0x1800677e0  lea     rcx, [rbp+57h+arg_0]; this
0x1800677e4  mov     rdx, r14; char *
0x1800677e7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800677ec  mov     rax, [rdi]
0x1800677ef  lea     rdx, [rbp+57h+var_A0]
0x1800677f3  movups  xmm0, xmmword ptr [rdi+18h]
0x1800677f7  mov     rcx, rdi
0x1800677fa  mov     rax, [rax+38h]
0x1800677fe  movdqu  [rbp+57h+var_A0], xmm0
0x180067803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067808  mov     ebx, eax
0x18006780a  test    eax, eax
0x18006780c  jns     loc_18006789D
0x180067812  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067819  test    rcx, rcx
0x18006781c  jnz     short loc_18006785F
0x18006781e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067824  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006782b  mov     rcx, rax
0x18006782e  test    rax, rax
0x180067831  jz      short loc_180067851
0x180067833  mov     rax, [rax]
0x180067836  mov     edx, 7F0h
0x18006783b  mov     rax, [rax+8]
0x18006783f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067844  test    eax, eax
0x180067846  jz      short loc_180067851
0x180067848  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006784f  jmp     short loc_18006785F
0x180067851  lea     rcx, qword_180153440; this
0x180067858  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006785f  cmp     byte ptr [rcx+8], 0
0x180067863  jz      short loc_180067886
0x180067865  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006786a  cmp     [rax+7CCh], ebx
0x180067870  jz      short loc_180067886
0x180067872  mov     r9d, ebx; int
0x180067875  mov     r8d, 0BEh; int
0x18006787b  mov     rdx, r14; char *
0x18006787e  mov     rcx, rax; this
0x180067881  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067886  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006788d  jb      loc_180067A68
0x180067893  mov     edx, 11h
0x180067898  jmp     loc_1800677A8
0x18006789d  lea     rcx, [rbp+57h+arg_0]; this
0x1800678a1  mov     byte ptr [rdi+29h], 0
0x1800678a5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800678aa  cmp     byte ptr [rdi+2Ah], 0
0x1800678ae  jz      loc_180067A71
0x1800678b4  movaps  xmm0, cs:?g_XMIdentityR0@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR0
0x1800678bb  lea     rdx, [rbp+57h+var_50]
0x1800678bf  movaps  xmm1, cs:?g_XMIdentityR1@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR1
0x1800678c6  mov     rcx, rdi
0x1800678c9  movaps  [rbp+57h+var_90], xmm0
0x1800678cd  movaps  xmm0, cs:?g_XMIdentityR2@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR2
0x1800678d4  movaps  [rbp+57h+var_80], xmm1
0x1800678d8  movaps  xmm1, cs:?g_XMIdentityR3@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR3
0x1800678df  movaps  [rbp+57h+var_70], xmm0
0x1800678e3  movaps  [rbp+57h+var_60], xmm1
0x1800678e7  call    ?GetBaseProjectionMatrix@CxCodeVideoProcD3DFlatGeometry@@IEAA?AUXMMATRIX@DirectX@@XZ; CxCodeVideoProcD3DFlatGeometry::GetBaseProjectionMatrix(void)
0x1800678ec  mov     r8d, 0C6h; int
0x1800678f2  mov     [rbp+57h+arg_8], 0
0x1800678fa  mov     rdx, r14; char *
0x1800678fd  lea     rcx, [rbp+57h+arg_0]; this
0x180067901  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067906  mov     rcx, [rdi+8]
0x18006790a  lea     rdx, [rbp+57h+arg_8]
0x18006790e  mov     rax, [rcx]
0x180067911  mov     rax, [rax+18h]
0x180067915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006791a  mov     ebx, eax
0x18006791c  test    eax, eax
0x18006791e  jns     loc_1800679AF
0x180067924  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006792b  test    rcx, rcx
0x18006792e  jnz     short loc_180067971
0x180067930  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067936  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006793d  mov     rcx, rax
0x180067940  test    rax, rax
0x180067943  jz      short loc_180067963
0x180067945  mov     rax, [rax]
0x180067948  mov     edx, 7F0h
0x18006794d  mov     rax, [rax+8]
0x180067951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067956  test    eax, eax
0x180067958  jz      short loc_180067963
0x18006795a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067961  jmp     short loc_180067971
0x180067963  lea     rcx, qword_180153440; this
0x18006796a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067971  cmp     byte ptr [rcx+8], 0
0x180067975  jz      short loc_180067998
0x180067977  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006797c  cmp     [rax+7CCh], ebx
0x180067982  jz      short loc_180067998
0x180067984  mov     r9d, ebx; int
0x180067987  mov     r8d, 0C6h; int
0x18006798d  mov     rdx, r14; char *
0x180067990  mov     rcx, rax; this
0x180067993  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006799f  jb      loc_180067A68
0x1800679a5  mov     edx, 12h
0x1800679aa  jmp     loc_1800677A8
0x1800679af  mov     rdx, [rbp+57h+arg_8]; struct stD3DVSConstants *
0x1800679b3  lea     r9, [rbp+57h+var_90]; struct DirectX::XMMATRIX *
0x1800679b7  lea     r8, [rbp+57h+var_50]; struct DirectX::XMMATRIX *
0x1800679bb  mov     rcx, rdi; this
0x1800679be  call    ?SetProjection@CxCodeVideoProcD3DGeometry@@IEAAJPEAUstD3DVSConstants@@AEBUXMMATRIX@DirectX@@1@Z; CxCodeVideoProcD3DGeometry::SetProjection(stD3DVSConstants *,DirectX::XMMATRIX const &,DirectX::XMMATRIX const &)
0x1800679c3  mov     ebx, eax
0x1800679c5  test    eax, eax
0x1800679c7  jns     loc_180067A54
0x1800679cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679d4  test    rcx, rcx
0x1800679d7  jnz     short loc_180067A1A
0x1800679d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800679df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679e6  mov     rcx, rax
0x1800679e9  test    rax, rax
0x1800679ec  jz      short loc_180067A0C
0x1800679ee  mov     rax, [rax]
0x1800679f1  mov     edx, 7F0h
0x1800679f6  mov     rax, [rax+8]
0x1800679fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679ff  test    eax, eax
0x180067a01  jz      short loc_180067A0C
0x180067a03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a0a  jmp     short loc_180067A1A
0x180067a0c  lea     rcx, qword_180153440; this
0x180067a13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a1a  cmp     byte ptr [rcx+8], 0
0x180067a1e  jz      short loc_180067A41
0x180067a20  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067a25  cmp     [rax+7CCh], ebx
0x180067a2b  jz      short loc_180067A41
0x180067a2d  mov     r9d, ebx; int
0x180067a30  mov     r8d, 0C7h; int
0x180067a36  mov     rdx, r14; char *
0x180067a39  mov     rcx, rax; this
0x180067a3c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067a41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067a48  jb      short loc_180067A68
0x180067a4a  mov     edx, 13h
0x180067a4f  jmp     loc_1800677A8
0x180067a54  mov     rcx, [rdi+8]
0x180067a58  mov     rax, [rcx]
0x180067a5b  mov     rax, [rax+20h]
0x180067a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a64  mov     byte ptr [rdi+2Ah], 0
0x180067a68  lea     rcx, [rbp+57h+arg_0]; this
0x180067a6c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067a71  mov     r8d, 0CCh; int
0x180067a77  lea     rcx, [rbp+57h+arg_0]; this
0x180067a7b  mov     rdx, r14; char *
0x180067a7e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067a83  cmp     cs:byte_180153DE0, 20h ; ' '
0x180067a8a  jb      short loc_180067AAE
0x180067a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067a93  mov     edx, 14h
0x180067a98  mov     r9, rdi
0x180067a9b  mov     [rsp+0D0h+var_B0], ebx
0x180067a9f  mov     r8, r15
0x180067aa2  mov     rcx, [rcx+150h]
0x180067aa9  call    WPP_SF_qD
0x180067aae  lea     rcx, [rbp+57h+arg_0]; this
0x180067ab2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067ab7  lea     r11, [rsp+0D0h+var_10]
0x180067abf  mov     eax, ebx
0x180067ac1  mov     rbx, [r11+30h]
0x180067ac5  mov     rdi, [r11+38h]
0x180067ac9  mov     rsp, r11
0x180067acc  pop     r15
0x180067ace  pop     r14
0x180067ad0  pop     rbp
0x180067ad1  retn
```
