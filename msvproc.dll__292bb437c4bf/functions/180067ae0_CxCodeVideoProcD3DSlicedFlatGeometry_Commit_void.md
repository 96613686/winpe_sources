# CxCodeVideoProcD3DSlicedFlatGeometry::Commit(void)

- ea: `0x180067ae0`
- end: `0x180068162`
- name: `?Commit@CxCodeVideoProcD3DSlicedFlatGeometry@@UEAAJXZ`
- size: `1666`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DSlicedFlatGeometry *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180054140`
- `0x180054e00`
- `0x180067ae0`
- `0x180068dc0`
- `0x180068fa8`
- `0x180069ca4`
- `0x18006a900`
- `0x18006ab4c`
- `0x18006b2ac`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067b80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067cea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067b80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067cea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680e3`

## string_xrefs

- `0x180067b32`: `CxCodeVideoProcD3DSlicedFlatGeometry::Commit`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DSlicedFlatGeometry::Commit(
        CxCodeVideoProcD3DSlicedFlatGeometry *this,
        __int64 a2,
        __int64 a3)
{
  int v3; // edi
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  float v15; // xmm6_4
  float v16; // xmm7_4
  float v17; // xmm9_4
  __m128 v18; // xmm8
  __m128 si128; // xmm13
  unsigned int i; // esi
  unsigned int v21; // ecx
  __m128 v22; // xmm0
  __m128 v23; // xmm2
  __m128 v24; // xmm7
  __m128 v25; // xmm5
  __m128 v26; // xmm4
  __m128 v27; // xmm0
  __m128 v28; // xmm1
  __m128 v29; // xmm3
  __m128 v30; // xmm0
  __m128 v31; // xmm2
  __int64 v32; // rcx
  __int64 *v33; // rcx
  __int64 v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  _BYTE v41[8]; // [rsp+38h] [rbp-D0h] BYREF
  struct stD3DVSConstants *v42[2]; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v43[4]; // [rsp+58h] [rbp-B0h] BYREF
  _OWORD v44[4]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v45[64]; // [rsp+D8h] [rbp-30h] BYREF

  v3 = 0;
  if ( !*((_BYTE *)this + 40) )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)v41,
      "CxCodeVideoProcD3DSlicedFlatGeometry::Commit",
      310);
    v3 = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DSlicedFlatGeometry *))(*(_QWORD *)this + 16LL))(this);
    if ( v3 < 0 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcD3DSlicedFlatGeometry::Commit", 310, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v8 = 30;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids, this, v3);
LABEL_14:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
      goto LABEL_33;
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  }
  if ( *((_BYTE *)this + 41) )
  {
    *(_OWORD *)v42 = *(_OWORD *)((char *)this + 24);
    CxCodeVideoProcD3DFlatGeometry::GeometryUpdate(this, v42);
    *((_BYTE *)this + 41) = 0;
  }
  if ( *((_BYTE *)this + 42) )
  {
    v43[0] = DirectX::g_XMIdentityR0;
    v43[1] = DirectX::g_XMIdentityR1;
    v43[2] = DirectX::g_XMIdentityR2;
    v43[3] = DirectX::g_XMIdentityR3;
    CxCodeVideoProcD3DFlatGeometry::GetBaseProjectionMatrix(this, v45, a3, 24);
    if ( *((_DWORD *)this + 12) == 1 )
    {
      v42[0] = 0;
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v41,
        "CxCodeVideoProcD3DSlicedFlatGeometry::Commit",
        324);
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct stD3DVSConstants **))(**((_QWORD **)this + 7) + 8LL))(
             *((_QWORD *)this + 7),
             0,
             v42);
      if ( v3 < 0 )
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
          if ( *((_DWORD *)v13 + 499) != v3 )
            CallStackContext::TraceFailure(v13, "CxCodeVideoProcD3DSlicedFlatGeometry::Commit", 324, v3);
        }
        if ( !g_wppLevels )
          goto LABEL_14;
        v8 = 31;
        goto LABEL_13;
      }
      v3 = CxCodeVideoProcD3DGeometry::SetProjection(
             this,
             v42[0],
             (const struct DirectX::XMMATRIX *)v45,
             (const struct DirectX::XMMATRIX *)v43);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7), 0);
    }
    else
    {
      v15 = (float)*((int *)this + 13);
      v16 = (float)*((int *)this + 12);
      v18 = (__m128)LODWORD(FLOAT_1_0);
      v17 = floorf((float)((float)((float)(*((float *)this + 9) - *(float *)(v10 + v9)) * v15) / v16) + 0.5) / v15;
      v18.m128_f32[0] = 1.0 / v17;
      floorf((float)(v16 - 0.5) * 0.5);
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)v41,
        "CxCodeVideoProcD3DSlicedFlatGeometry::Commit",
        334);
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_ggg(*((_QWORD *)WPP_GLOBAL_Control + 42));
      si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
      for ( i = 0; ; ++i )
      {
        v21 = *((_DWORD *)this + 12);
        if ( i >= v21 )
          break;
        if ( i == v21 - 1 )
        {
          v18 = (__m128)LODWORD(FLOAT_1_0);
          v18.m128_f32[0] = 1.0
                          / (float)((float)((float)(*((float *)this + 9) - *((float *)this + 6))
                                          - (float)((float)(int)i * v17))
                                  - (float)(1.0 / (float)*((int *)this + 13)));
        }
        v22 = 0;
        v23 = _mm_unpacklo_ps(si128, _mm_unpacklo_ps(v18, (__m128)LODWORD(FLOAT_1_0)));
        *(double *)v22.m128_u64 = DirectX::XMMatrixTransformation2D();
        v24 = _mm_shuffle_ps(v22, (__m128)0LL, 238);
        v25 = _mm_shuffle_ps(v23, (__m128)0LL, 238);
        v26 = _mm_shuffle_ps(v23, (__m128)0LL, 68);
        v27 = _mm_shuffle_ps(v22, (__m128)0LL, 68);
        v28 = _mm_shuffle_ps(v27, v26, 221);
        v29 = _mm_shuffle_ps(v24, v25, 221);
        v30 = _mm_shuffle_ps(v27, v26, 136);
        v31 = _mm_shuffle_ps(v24, v25, 136);
        *(double *)v30.m128_u64 = DirectX::XMMatrixMultiply(v32, v45);
        v33 = (__int64 *)*((_QWORD *)this + 7);
        v42[0] = 0;
        v44[3] = v29;
        v44[2] = v31;
        v34 = *v33;
        v44[1] = v28;
        v44[0] = v30;
        v3 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct stD3DVSConstants **))(v34 + 8))(v33, i, v42);
        if ( v3 < 0 )
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
            if ( *((_DWORD *)v40 + 499) != v3 )
              CallStackContext::TraceFailure(v40, "CxCodeVideoProcD3DSlicedFlatGeometry::Commit", 358, v3);
          }
          if ( g_wppLevels )
          {
            v8 = 33;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
        v3 = CxCodeVideoProcD3DGeometry::SetProjection(
               this,
               v42[0],
               (const struct DirectX::XMMATRIX *)v44,
               (const struct DirectX::XMMATRIX *)v43);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 16LL))(*((_QWORD *)this + 7), i);
        if ( v3 < 0 )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != v3 )
              CallStackContext::TraceFailure(v37, "CxCodeVideoProcD3DSlicedFlatGeometry::Commit", 361, v3);
          }
          if ( g_wppLevels )
          {
            v8 = 34;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
      }
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
    *((_BYTE *)this + 42) = 0;
  }
LABEL_33:
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v41,
    "CxCodeVideoProcD3DSlicedFlatGeometry::Commit",
    367);
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 35, &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids, this, v3);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180067ae0  mov     rax, rsp
0x180067ae3  push    rbp
0x180067ae4  push    rbx
0x180067ae5  push    rsi
0x180067ae6  push    rdi
0x180067ae7  push    r12
0x180067ae9  push    r15
0x180067aeb  lea     rbp, [rax-0B8h]
0x180067af2  sub     rsp, 188h
0x180067af9  movaps  xmmword ptr [rax-48h], xmm6
0x180067afd  movaps  xmmword ptr [rax-58h], xmm7
0x180067b01  movaps  xmmword ptr [rax-68h], xmm8
0x180067b06  movaps  xmmword ptr [rax-78h], xmm9
0x180067b0b  movaps  xmmword ptr [rax-88h], xmm12
0x180067b13  movaps  xmmword ptr [rax-98h], xmm13
0x180067b1b  mov     rax, cs:__security_cookie
0x180067b22  xor     rax, rsp
0x180067b25  mov     [rbp+0B0h+var_A0], rax
0x180067b29  xor     edi, edi
0x180067b2b  lea     r12, WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids
0x180067b32  lea     r15, aCxcodevideopro_165; "CxCodeVideoProcD3DSlicedFlatGeometry::C"...
0x180067b39  mov     rbx, rcx
0x180067b3c  cmp     [rcx+28h], dil
0x180067b40  jnz     loc_180067C26
0x180067b46  mov     esi, 136h
0x180067b4b  lea     rcx, [rsp+1B0h+var_180]; this
0x180067b50  mov     r8d, esi; int
0x180067b53  mov     rdx, r15; char *
0x180067b56  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067b5b  mov     rax, [rbx]
0x180067b5e  mov     rcx, rbx
0x180067b61  mov     rax, [rax+10h]
0x180067b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b6a  mov     edi, eax
0x180067b6c  test    eax, eax
0x180067b6e  jns     loc_180067C1C
0x180067b74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067b7b  test    rcx, rcx
0x180067b7e  jnz     short loc_180067BC1
0x180067b80  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067b86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067b8d  mov     rcx, rax
0x180067b90  test    rax, rax
0x180067b93  jz      short loc_180067BB3
0x180067b95  mov     rax, [rax]
0x180067b98  mov     edx, 7F0h
0x180067b9d  mov     rax, [rax+8]
0x180067ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ba6  test    eax, eax
0x180067ba8  jz      short loc_180067BB3
0x180067baa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067bb1  jmp     short loc_180067BC1
0x180067bb3  lea     rcx, qword_180153440; this
0x180067bba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067bc1  cmp     byte ptr [rcx+8], 0
0x180067bc5  jz      short loc_180067BE5
0x180067bc7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067bcc  cmp     [rax+7CCh], edi
0x180067bd2  jz      short loc_180067BE5
0x180067bd4  mov     r9d, edi; int
0x180067bd7  mov     r8d, esi; int
0x180067bda  mov     rdx, r15; char *
0x180067bdd  mov     rcx, rax; this
0x180067be0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067be5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067bec  jb      short loc_180067C0D
0x180067bee  mov     edx, 1Eh
0x180067bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180067bfa  mov     r9, rbx
0x180067bfd  mov     r8, r12
0x180067c00  mov     dword ptr [rsp+1B0h+var_190], edi
0x180067c04  mov     rcx, [rcx+10h]
0x180067c08  call    WPP_SF_qD
0x180067c0d  lea     rcx, [rsp+1B0h+var_180]; this
0x180067c12  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067c17  jmp     loc_180067D9E
0x180067c1c  lea     rcx, [rsp+1B0h+var_180]; this
0x180067c21  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067c26  cmp     byte ptr [rbx+29h], 0
0x180067c2a  jz      short loc_180067C47
0x180067c2c  movups  xmm0, xmmword ptr [rbx+18h]
0x180067c30  lea     rdx, [rsp+1B0h+var_178+8]
0x180067c35  mov     rcx, rbx
0x180067c38  movdqu  xmmword ptr [rsp+1B0h+var_178+8], xmm0
0x180067c3e  call    ?GeometryUpdate@CxCodeVideoProcD3DFlatGeometry@@MEAAJURectF@@@Z; CxCodeVideoProcD3DFlatGeometry::GeometryUpdate(RectF)
0x180067c43  mov     byte ptr [rbx+29h], 0
0x180067c47  cmp     byte ptr [rbx+2Ah], 0
0x180067c4b  mov     r9d, 18h
0x180067c51  mov     r10, rbx
0x180067c54  jz      loc_180067D9E
0x180067c5a  movaps  xmm0, cs:?g_XMIdentityR0@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR0
0x180067c61  lea     rdx, [rbp+0B0h+var_E0]
0x180067c65  movaps  xmm1, cs:?g_XMIdentityR1@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR1
0x180067c6c  mov     rcx, rbx
0x180067c6f  movaps  [rsp+1B0h+var_168+8], xmm0
0x180067c74  movaps  xmm0, cs:?g_XMIdentityR2@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR2
0x180067c7b  movaps  [rsp+1B0h+var_158+8], xmm1
0x180067c80  movaps  xmm1, cs:?g_XMIdentityR3@DirectX@@3UXMVECTORF32@1@B; DirectX::XMVECTORF32 const DirectX::g_XMIdentityR3
0x180067c87  movaps  [rsp+1B0h+var_148+8], xmm0
0x180067c8c  movaps  [rbp+0B0h+var_130], xmm1
0x180067c90  call    ?GetBaseProjectionMatrix@CxCodeVideoProcD3DFlatGeometry@@IEAA?AUXMMATRIX@DirectX@@XZ; CxCodeVideoProcD3DFlatGeometry::GetBaseProjectionMatrix(void)
0x180067c95  cmp     dword ptr [rbx+30h], 1
0x180067c99  jnz     loc_180067E26
0x180067c9f  mov     esi, 144h
0x180067ca4  mov     [rsp+1B0h+var_178+8], 0
0x180067cad  mov     r8d, esi; int
0x180067cb0  lea     rcx, [rsp+1B0h+var_180]; this
0x180067cb5  mov     rdx, r15; char *
0x180067cb8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067cbd  mov     rcx, [rbx+38h]
0x180067cc1  lea     r8, [rsp+1B0h+var_178+8]
0x180067cc6  xor     edx, edx
0x180067cc8  mov     rax, [rcx]
0x180067ccb  mov     rax, [rax+8]
0x180067ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067cd4  mov     edi, eax
0x180067cd6  test    eax, eax
0x180067cd8  jns     loc_180067D66
0x180067cde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ce5  test    rcx, rcx
0x180067ce8  jnz     short loc_180067D2B
0x180067cea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067cf0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067cf7  mov     rcx, rax
0x180067cfa  test    rax, rax
0x180067cfd  jz      short loc_180067D1D
0x180067cff  mov     rax, [rax]
0x180067d02  mov     edx, 7F0h
0x180067d07  mov     rax, [rax+8]
0x180067d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d10  test    eax, eax
0x180067d12  jz      short loc_180067D1D
0x180067d14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d1b  jmp     short loc_180067D2B
0x180067d1d  lea     rcx, qword_180153440; this
0x180067d24  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067d2b  cmp     byte ptr [rcx+8], 0
0x180067d2f  jz      short loc_180067D4F
0x180067d31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067d36  cmp     [rax+7CCh], edi
0x180067d3c  jz      short loc_180067D4F
0x180067d3e  mov     r9d, edi; int
0x180067d41  mov     r8d, esi; int
0x180067d44  mov     rdx, r15; char *
0x180067d47  mov     rcx, rax; this
0x180067d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067d56  jb      loc_180067C0D
0x180067d5c  mov     edx, 1Fh
0x180067d61  jmp     loc_180067BF3
0x180067d66  mov     rdx, [rsp+1B0h+var_178+8]; struct stD3DVSConstants *
0x180067d6b  lea     r9, [rsp+1B0h+var_168+8]; struct DirectX::XMMATRIX *
0x180067d70  lea     r8, [rbp+0B0h+var_E0]; struct DirectX::XMMATRIX *
0x180067d74  mov     rcx, rbx; this
0x180067d77  call    ?SetProjection@CxCodeVideoProcD3DGeometry@@IEAAJPEAUstD3DVSConstants@@AEBUXMMATRIX@DirectX@@1@Z; CxCodeVideoProcD3DGeometry::SetProjection(stD3DVSConstants *,DirectX::XMMATRIX const &,DirectX::XMMATRIX const &)
0x180067d7c  mov     rcx, [rbx+38h]
0x180067d80  mov     edi, eax
0x180067d82  xor     edx, edx
0x180067d84  mov     rax, [rcx]
0x180067d87  mov     rax, [rax+10h]
0x180067d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067d90  lea     rcx, [rsp+1B0h+var_180]; this
0x180067d95  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067d9a  mov     byte ptr [rbx+2Ah], 0
0x180067d9e  mov     r8d, 16Fh; int
0x180067da4  lea     rcx, [rsp+1B0h+var_180]; this
0x180067da9  mov     rdx, r15; char *
0x180067dac  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067db1  cmp     cs:byte_180153DE0, 20h ; ' '
0x180067db8  jb      short loc_180067DDC
0x180067dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180067dc1  mov     edx, 23h ; '#'
0x180067dc6  mov     r9, rbx
0x180067dc9  mov     dword ptr [rsp+1B0h+var_190], edi
0x180067dcd  mov     r8, r12
0x180067dd0  mov     rcx, [rcx+150h]
0x180067dd7  call    WPP_SF_qD
0x180067ddc  lea     rcx, [rsp+1B0h+var_180]; this
0x180067de1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180067de6  mov     eax, edi
0x180067de8  mov     rcx, [rbp+0B0h+var_A0]
0x180067dec  xor     rcx, rsp; StackCookie
0x180067def  call    __security_check_cookie
0x180067df4  lea     r11, [rsp+1B0h+var_28]
0x180067dfc  movaps  xmm6, xmmword ptr [r11-18h]
0x180067e01  movaps  xmm7, xmmword ptr [r11-28h]
0x180067e06  movaps  xmm8, xmmword ptr [r11-38h]
0x180067e0b  movaps  xmm9, xmmword ptr [r11-48h]
0x180067e10  movaps  xmm12, xmmword ptr [r11-58h]
0x180067e15  movaps  xmm13, xmmword ptr [r11-68h]
0x180067e1a  mov     rsp, r11
0x180067e1d  pop     r15
0x180067e1f  pop     r12
0x180067e21  pop     rdi
0x180067e22  pop     rsi
0x180067e23  pop     rbx
0x180067e24  pop     rbp
0x180067e25  retn
0x180067e26  mov     eax, [rbx+34h]
0x180067e29  xorps   xmm6, xmm6
0x180067e2c  movss   xmm0, dword ptr [rbx+24h]
0x180067e31  xorps   xmm7, xmm7
0x180067e34  subss   xmm0, dword ptr [r10+r9]
0x180067e3a  cvtsi2ss xmm6, rax
0x180067e3f  mov     eax, [rbx+30h]
0x180067e42  cvtsi2ss xmm7, rax
0x180067e47  mulss   xmm0, xmm6
0x180067e4b  divss   xmm0, xmm7
0x180067e4f  addss   xmm0, cs:__real@3f000000; X
0x180067e57  call    floorf
0x180067e5c  subss   xmm7, cs:__real@3f000000
0x180067e64  movss   xmm8, cs:__real@3f800000
0x180067e6d  movaps  xmm9, xmm0
0x180067e71  divss   xmm9, xmm6
0x180067e76  mulss   xmm7, cs:__real@3f000000
0x180067e7e  divss   xmm8, xmm9
0x180067e83  movaps  xmm0, xmm7; X
0x180067e86  call    floorf
0x180067e8b  mov     r8d, 14Eh; int
0x180067e91  lea     rcx, [rsp+1B0h+var_180]; this
0x180067e96  mov     rdx, r15; char *
0x180067e99  movaps  xmm12, xmm0
0x180067e9d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067ea2  cmp     cs:byte_180153DE0, 20h ; ' '
0x180067ea9  jb      short loc_180067EDE
0x180067eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180067eb2  xorps   xmm1, xmm1
0x180067eb5  cvtss2sd xmm1, xmm12
0x180067eba  mov     rcx, [rcx+150h]
0x180067ec1  xorps   xmm3, xmm3
0x180067ec4  cvtps2pd xmm2, xmm8
0x180067ec8  movsd   qword ptr [rsp+1B0h+var_188], xmm1
0x180067ece  cvtss2sd xmm3, xmm9
0x180067ed3  movsd   [rsp+1B0h+var_190], xmm2
0x180067ed9  call    WPP_SF_ggg
0x180067ede  movdqa  xmm13, cs:__xmm@00000000000000003f8000003f800000
0x180067ee7  xor     esi, esi
0x180067ee9  mov     ecx, [rbx+30h]
0x180067eec  cmp     esi, ecx
0x180067eee  jnb     loc_180067D90
0x180067ef4  mov     eax, esi
0x180067ef6  xorps   xmm3, xmm3
0x180067ef9  cvtsi2ss xmm3, rax
0x180067efe  lea     eax, [rcx-1]
0x180067f01  cmp     esi, eax
0x180067f03  jnz     short loc_180067F44
0x180067f05  movss   xmm2, dword ptr [rbx+24h]
0x180067f0a  movaps  xmm0, xmm3
0x180067f0d  subss   xmm2, dword ptr [rbx+18h]
0x180067f12  mov     eax, [rbx+34h]
0x180067f15  movss   xmm1, cs:__real@3f800000
0x180067f1d  movss   xmm8, cs:__real@3f800000
0x180067f26  mulss   xmm0, xmm9
0x180067f2b  subss   xmm2, xmm0
0x180067f2f  xorps   xmm0, xmm0
0x180067f32  cvtsi2ss xmm0, rax
0x180067f37  divss   xmm1, xmm0
0x180067f3b  subss   xmm2, xmm1
0x180067f3f  divss   xmm8, xmm2
0x180067f44  mov     eax, [rbx+34h]
0x180067f47  subss   xmm3, xmm12
0x180067f4c  xorps   xmm0, xmm0
0x180067f4f  movaps  xmm1, xmm8
0x180067f53  xorps   xmm5, xmm5
0x180067f56  movaps  xmm2, xmm13
0x180067f5a  xorps   xmm4, xmm4
0x180067f5d  cvtsi2ss xmm0, rax
0x180067f62  subss   xmm3, cs:__real@3f000000
0x180067f6a  divss   xmm1, xmm0
0x180067f6e  addss   xmm3, xmm3
0x180067f72  xorps   xmm0, xmm0
0x180067f75  addss   xmm1, xmm3
0x180067f79  movaps  xmm3, xmm8
0x180067f7d  unpcklps xmm1, xmm0
0x180067f80  unpcklps xmm5, xmm1
0x180067f83  movss   xmm1, cs:__real@3f800000
0x180067f8b  unpcklps xmm3, xmm1
0x180067f8e  xorps   xmm1, xmm1
0x180067f91  unpcklps xmm2, xmm3
0x180067f94  xorps   xmm3, xmm3
0x180067f97  call    ?XMMatrixTransformation2D@DirectX@@YQ?AUXMMATRIX@1@T__m128@@M00M0@Z; DirectX::XMMatrixTransformation2D(__m128,float,__m128,__m128,float,__m128)
0x180067f9c  movaps  xmm7, xmm0
0x180067f9f  lea     rdx, [rbp+0B0h+var_E0]
0x180067fa3  movaps  xmm6, xmm0
0x180067fa6  shufps  xmm7, xmm1, 0EEh
0x180067faa  movaps  xmm5, xmm2
0x180067fad  shufps  xmm6, xmm1, 44h ; 'D'
0x180067fb1  movaps  xmm4, xmm2
0x180067fb4  shufps  xmm5, xmm3, 0EEh
0x180067fb8  shufps  xmm4, xmm3, 44h ; 'D'
0x180067fbc  movaps  xmm0, xmm6
0x180067fbf  movaps  xmm2, xmm7
0x180067fc2  shufps  xmm6, xmm4, 0DDh
0x180067fc6  shufps  xmm7, xmm5, 0DDh
0x180067fca  movaps  xmm1, xmm6
0x180067fcd  movaps  xmm3, xmm7
0x180067fd0  shufps  xmm0, xmm4, 88h
0x180067fd4  shufps  xmm2, xmm5, 88h
0x180067fd8  call    ?XMMatrixMultiply@DirectX@@YQ?AUXMMATRIX@1@U21@AEBU21@@Z; DirectX::XMMatrixMultiply(DirectX::XMMATRIX,DirectX::XMMATRIX const &)
0x180067fdd  mov     rcx, [rbx+38h]
  ... truncated ...
```
