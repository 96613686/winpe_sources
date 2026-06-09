# CxCodeVideoProcD3DSphereGeometry::Commit(void)

- ea: `0x180068170`
- end: `0x1800685af`
- name: `?Commit@CxCodeVideoProcD3DSphereGeometry@@UEAAJXZ`
- size: `1087`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DSphereGeometry *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180036268`
- `0x18003639c`
- `0x18003730c`
- `0x180054140`
- `0x180068170`
- `0x180069ca4`
- `0x18006a900`
- `0x18006aa14`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800681e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800684cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800681e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682dd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800684cf`

## string_xrefs

- `0x180068195`: `CxCodeVideoProcD3DSphereGeometry::Commit`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DSphereGeometry::Commit(__m128 *this)
{
  int Geometry; // ebx
  unsigned int v3; // edx
  unsigned int v4; // r8d
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __m128 v12; // xmm1
  __m128 v13; // xmm0
  __m128 v14; // xmm3
  __m128 v15; // xmm2
  __m128 v16; // xmm1
  __m128 v17; // xmm0
  __int64 v18; // rcx
  __int64 *v19; // rcx
  __m128 v20; // xmm5
  __m128 v21; // xmm4
  __int64 v22; // rax
  __m128 v23; // xmm1
  __int64 (__fastcall *v24)(__int64 *, struct stD3DVSConstants **); // rax
  __m128 v25; // xmm2
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  char v33[8]; // [rsp+30h] [rbp-29h] BYREF
  struct stD3DVSConstants *v34; // [rsp+38h] [rbp-21h] BYREF
  __m128 v35; // [rsp+40h] [rbp-19h] BYREF
  __m128 v36; // [rsp+50h] [rbp-9h]
  __m128 v37; // [rsp+60h] [rbp+7h]
  __m128 v38; // [rsp+70h] [rbp+17h]

  Geometry = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v33, "CxCodeVideoProcD3DSphereGeometry::Commit", 625);
  if ( !this[2].m128_i8[8] )
  {
    Geometry = (*(__int64 (__fastcall **)(__m128 *))(this->m128_u64[0] + 16))(this);
    if ( Geometry < 0 )
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != Geometry )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CxCodeVideoProcD3DSphereGeometry::Commit",
            630,
            Geometry);
      }
      if ( g_wppLevels )
      {
        v8 = 46;
LABEL_13:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids,
          this,
          Geometry);
        goto LABEL_53;
      }
      goto LABEL_53;
    }
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      47,
      &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids,
      this,
      this[2].m128_u8[9],
      this[2].m128_u8[10]);
  if ( !this[2].m128_i8[9] )
  {
LABEL_29:
    if ( this[2].m128_i8[10] )
    {
      v12 = (__m128)this[3].m128_u32[3];
      v13 = (__m128)this[3].m128_u32[2];
      *(double *)v13.m128_u64 = DirectX::XMMatrixPerspectiveFovLH();
      v38 = (__m128)LODWORD(FLOAT_1_1);
      v14 = this[7];
      v37 = (__m128)LODWORD(FLOAT_0_0099999998);
      v15 = this[6];
      v36 = v12;
      v16 = this[5];
      v35 = v13;
      v17 = this[4];
      *(double *)v17.m128_u64 = DirectX::XMMatrixMultiply(v18, &v35);
      v19 = (__int64 *)this->m128_u64[1];
      v34 = 0;
      v20 = _mm_shuffle_ps(v17, v16, 238);
      v21 = _mm_shuffle_ps(v17, v16, 68);
      v22 = *v19;
      v23 = _mm_shuffle_ps(v15, v14, 68);
      v35 = _mm_shuffle_ps(v21, v23, 136);
      v24 = *(__int64 (__fastcall **)(__int64 *, struct stD3DVSConstants **))(v22 + 24);
      v25 = _mm_shuffle_ps(v15, v14, 238);
      v37 = _mm_shuffle_ps(v20, v25, 136);
      v36 = _mm_shuffle_ps(v21, v23, 221);
      v38 = _mm_shuffle_ps(v20, v25, 221);
      Geometry = v24(v19, &v34);
      if ( Geometry >= 0 )
      {
        Geometry = CxCodeVideoProcD3DGeometry::SetProjection(
                     (CxCodeVideoProcD3DGeometry *)this,
                     v34,
                     (const struct DirectX::XMMATRIX *)&v35,
                     (const struct DirectX::XMMATRIX *)&this[8]);
        if ( Geometry >= 0 )
        {
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)this->m128_u64[1] + 32LL))(this->m128_u64[1]);
          this[2].m128_i8[10] = 0;
        }
        else
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
            v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)v31 + 499) != Geometry )
              CallStackContext::TraceFailure(v31, "CxCodeVideoProcD3DSphereGeometry::Commit", 644, Geometry);
          }
          if ( g_wppLevels )
          {
            v8 = 50;
            goto LABEL_13;
          }
        }
      }
      else
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
          if ( *((_DWORD *)v28 + 499) != Geometry )
            CallStackContext::TraceFailure(v28, "CxCodeVideoProcD3DSphereGeometry::Commit", 643, Geometry);
        }
        if ( g_wppLevels )
        {
          v8 = 49;
          goto LABEL_13;
        }
      }
    }
    goto LABEL_53;
  }
  Geometry = CxCodeVideoProcD3DSphereGeometry::GenerateGeometry((CxCodeVideoProcD3DSphereGeometry *)this, v3, v4);
  if ( Geometry >= 0 )
  {
    this[2].m128_i8[9] = 0;
    goto LABEL_29;
  }
  v9 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v10;
    if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v9 = &qword_180153440;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
    }
  }
  if ( *((_BYTE *)v9 + 8) )
  {
    v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
    if ( *((_DWORD *)v11 + 499) != Geometry )
      CallStackContext::TraceFailure(v11, "CxCodeVideoProcD3DSphereGeometry::Commit", 635, Geometry);
  }
  if ( g_wppLevels )
  {
    v8 = 48;
    goto LABEL_13;
  }
LABEL_53:
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      51,
      &WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids,
      this,
      Geometry);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v33);
  return (unsigned int)Geometry;
}

```

## disassembly

```asm
0x180068170  push    rbp
0x180068172  push    rbx
0x180068173  push    rdi
0x180068174  push    r14
0x180068176  push    r15
0x180068178  lea     rbp, [rsp-37h]
0x18006817d  sub     rsp, 90h
0x180068184  mov     rax, cs:__security_cookie
0x18006818b  xor     rax, rsp
0x18006818e  mov     [rbp+57h+var_30], rax
0x180068192  mov     rdi, rcx
0x180068195  lea     r15, aCxcodevideopro_139; "CxCodeVideoProcD3DSphereGeometry::Commi"...
0x18006819c  mov     rdx, r15; char *
0x18006819f  lea     rcx, [rbp+57h+var_80]; this
0x1800681a3  mov     r8d, 271h; int
0x1800681a9  xor     ebx, ebx
0x1800681ab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800681b0  lea     r14, WPP_f2247c3ba6503e84ce3705a64d6fea80_Traceguids
0x1800681b7  cmp     [rdi+28h], bl
0x1800681ba  jnz     loc_18006827E
0x1800681c0  mov     rax, [rdi]
0x1800681c3  mov     rcx, rdi
0x1800681c6  mov     rax, [rax+10h]
0x1800681ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681cf  mov     ebx, eax
0x1800681d1  test    eax, eax
0x1800681d3  jns     loc_18006827E
0x1800681d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800681e0  test    rcx, rcx
0x1800681e3  jnz     short loc_180068226
0x1800681e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800681eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800681f2  mov     rcx, rax
0x1800681f5  test    rax, rax
0x1800681f8  jz      short loc_180068218
0x1800681fa  mov     rax, [rax]
0x1800681fd  mov     edx, 7F0h
0x180068202  mov     rax, [rax+8]
0x180068206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006820b  test    eax, eax
0x18006820d  jz      short loc_180068218
0x18006820f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068216  jmp     short loc_180068226
0x180068218  lea     rcx, qword_180153440; this
0x18006821f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068226  cmp     byte ptr [rcx+8], 0
0x18006822a  jz      short loc_18006824D
0x18006822c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068231  cmp     [rax+7CCh], ebx
0x180068237  jz      short loc_18006824D
0x180068239  mov     r9d, ebx; int
0x18006823c  mov     r8d, 276h; int
0x180068242  mov     rdx, r15; char *
0x180068245  mov     rcx, rax; this
0x180068248  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006824d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068254  jb      loc_18006855E
0x18006825a  mov     edx, 2Eh ; '.'
0x18006825f  mov     rcx, cs:WPP_GLOBAL_Control
0x180068266  mov     r9, rdi
0x180068269  mov     r8, r14
0x18006826c  mov     [rsp+0B0h+var_90], ebx
0x180068270  mov     rcx, [rcx+10h]
0x180068274  call    WPP_SF_qD
0x180068279  jmp     loc_18006855E
0x18006827e  cmp     cs:byte_180153DE0, 20h ; ' '
0x180068285  jb      short loc_1800682B5
0x180068287  movzx   ecx, byte ptr [rdi+29h]
0x18006828b  mov     edx, 2Fh ; '/'
0x180068290  movzx   eax, byte ptr [rdi+2Ah]
0x180068294  mov     r9, rdi
0x180068297  mov     [rsp+0B0h+var_88], eax
0x18006829b  mov     r8, r14
0x18006829e  mov     [rsp+0B0h+var_90], ecx
0x1800682a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800682a9  mov     rcx, [rcx+150h]
0x1800682b0  call    WPP_SF_qdd
0x1800682b5  cmp     byte ptr [rdi+29h], 0
0x1800682b9  jz      loc_180068360
0x1800682bf  mov     rcx, rdi; this
0x1800682c2  call    ?GenerateGeometry@CxCodeVideoProcD3DSphereGeometry@@IEAAJII@Z; CxCodeVideoProcD3DSphereGeometry::GenerateGeometry(uint,uint)
0x1800682c7  mov     ebx, eax
0x1800682c9  test    eax, eax
0x1800682cb  jns     loc_18006835C
0x1800682d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800682d8  test    rcx, rcx
0x1800682db  jnz     short loc_18006831E
0x1800682dd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800682e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800682ea  mov     rcx, rax
0x1800682ed  test    rax, rax
0x1800682f0  jz      short loc_180068310
0x1800682f2  mov     rax, [rax]
0x1800682f5  mov     edx, 7F0h
0x1800682fa  mov     rax, [rax+8]
0x1800682fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068303  test    eax, eax
0x180068305  jz      short loc_180068310
0x180068307  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006830e  jmp     short loc_18006831E
0x180068310  lea     rcx, qword_180153440; this
0x180068317  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006831e  cmp     byte ptr [rcx+8], 0
0x180068322  jz      short loc_180068345
0x180068324  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068329  cmp     [rax+7CCh], ebx
0x18006832f  jz      short loc_180068345
0x180068331  mov     r9d, ebx; int
0x180068334  mov     r8d, 27Bh; int
0x18006833a  mov     rdx, r15; char *
0x18006833d  mov     rcx, rax; this
0x180068340  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068345  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006834c  jb      loc_18006855E
0x180068352  mov     edx, 30h ; '0'
0x180068357  jmp     loc_18006825F
0x18006835c  mov     byte ptr [rdi+29h], 0
0x180068360  cmp     byte ptr [rdi+2Ah], 0
0x180068364  jz      loc_18006855E
0x18006836a  movss   xmm3, cs:__real@3f8ccccd
0x180068372  movss   xmm2, cs:__real@3c23d70a
0x18006837a  movss   xmm1, dword ptr [rdi+3Ch]
0x18006837f  movss   xmm0, dword ptr [rdi+38h]
0x180068384  call    ?XMMatrixPerspectiveFovLH@DirectX@@YQ?AUXMMATRIX@1@MMMM@Z; DirectX::XMMatrixPerspectiveFovLH(float,float,float,float)
0x180068389  movaps  [rbp+57h+var_40], xmm3
0x18006838d  lea     rdx, [rbp+57h+var_70]
0x180068391  movups  xmm3, xmmword ptr [rdi+70h]
0x180068395  movaps  [rbp+57h+var_50], xmm2
0x180068399  movups  xmm2, xmmword ptr [rdi+60h]
0x18006839d  movaps  [rbp+57h+var_60], xmm1
0x1800683a1  movups  xmm1, xmmword ptr [rdi+50h]
0x1800683a5  movaps  [rbp+57h+var_70], xmm0
0x1800683a9  movups  xmm0, xmmword ptr [rdi+40h]
0x1800683ad  call    ?XMMatrixMultiply@DirectX@@YQ?AUXMMATRIX@1@U21@AEBU21@@Z; DirectX::XMMatrixMultiply(DirectX::XMMATRIX,DirectX::XMMATRIX const &)
0x1800683b2  mov     rcx, [rdi+8]
0x1800683b6  lea     rdx, [rbp+57h+var_78]
0x1800683ba  movaps  xmm5, xmm0
0x1800683bd  mov     [rbp+57h+var_78], 0
0x1800683c5  movaps  xmm4, xmm0
0x1800683c8  shufps  xmm5, xmm1, 0EEh
0x1800683cc  shufps  xmm4, xmm1, 44h ; 'D'
0x1800683d0  movaps  xmm1, xmm2
0x1800683d3  mov     rax, [rcx]
0x1800683d6  movaps  xmm0, xmm4
0x1800683d9  shufps  xmm1, xmm3, 44h ; 'D'
0x1800683dd  shufps  xmm0, xmm1, 88h
0x1800683e1  movaps  [rbp+57h+var_70], xmm0
0x1800683e5  movaps  xmm0, xmm5
0x1800683e8  mov     rax, [rax+18h]
0x1800683ec  shufps  xmm2, xmm3, 0EEh
0x1800683f0  shufps  xmm0, xmm2, 88h
0x1800683f4  shufps  xmm4, xmm1, 0DDh
0x1800683f8  shufps  xmm5, xmm2, 0DDh
0x1800683fc  movaps  [rbp+57h+var_50], xmm0
0x180068400  movaps  [rbp+57h+var_60], xmm4
0x180068404  movaps  [rbp+57h+var_40], xmm5
0x180068408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006840d  mov     ebx, eax
0x18006840f  test    eax, eax
0x180068411  jns     loc_1800684A2
0x180068417  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006841e  test    rcx, rcx
0x180068421  jnz     short loc_180068464
0x180068423  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068429  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068430  mov     rcx, rax
0x180068433  test    rax, rax
0x180068436  jz      short loc_180068456
0x180068438  mov     rax, [rax]
0x18006843b  mov     edx, 7F0h
0x180068440  mov     rax, [rax+8]
0x180068444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068449  test    eax, eax
0x18006844b  jz      short loc_180068456
0x18006844d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068454  jmp     short loc_180068464
0x180068456  lea     rcx, qword_180153440; this
0x18006845d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068464  cmp     byte ptr [rcx+8], 0
0x180068468  jz      short loc_18006848B
0x18006846a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006846f  cmp     [rax+7CCh], ebx
0x180068475  jz      short loc_18006848B
0x180068477  mov     r9d, ebx; int
0x18006847a  mov     r8d, 283h; int
0x180068480  mov     rdx, r15; char *
0x180068483  mov     rcx, rax; this
0x180068486  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006848b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068492  jb      loc_18006855E
0x180068498  mov     edx, 31h ; '1'
0x18006849d  jmp     loc_18006825F
0x1800684a2  mov     rdx, [rbp+57h+var_78]; struct stD3DVSConstants *
0x1800684a6  lea     r9, [rdi+80h]; struct DirectX::XMMATRIX *
0x1800684ad  lea     r8, [rbp+57h+var_70]; struct DirectX::XMMATRIX *
0x1800684b1  mov     rcx, rdi; this
0x1800684b4  call    ?SetProjection@CxCodeVideoProcD3DGeometry@@IEAAJPEAUstD3DVSConstants@@AEBUXMMATRIX@DirectX@@1@Z; CxCodeVideoProcD3DGeometry::SetProjection(stD3DVSConstants *,DirectX::XMMATRIX const &,DirectX::XMMATRIX const &)
0x1800684b9  mov     ebx, eax
0x1800684bb  test    eax, eax
0x1800684bd  jns     loc_18006854A
0x1800684c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800684ca  test    rcx, rcx
0x1800684cd  jnz     short loc_180068510
0x1800684cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800684d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800684dc  mov     rcx, rax
0x1800684df  test    rax, rax
0x1800684e2  jz      short loc_180068502
0x1800684e4  mov     rax, [rax]
0x1800684e7  mov     edx, 7F0h
0x1800684ec  mov     rax, [rax+8]
0x1800684f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800684f5  test    eax, eax
0x1800684f7  jz      short loc_180068502
0x1800684f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068500  jmp     short loc_180068510
0x180068502  lea     rcx, qword_180153440; this
0x180068509  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068510  cmp     byte ptr [rcx+8], 0
0x180068514  jz      short loc_180068537
0x180068516  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006851b  cmp     [rax+7CCh], ebx
0x180068521  jz      short loc_180068537
0x180068523  mov     r9d, ebx; int
0x180068526  mov     r8d, 284h; int
0x18006852c  mov     rdx, r15; char *
0x18006852f  mov     rcx, rax; this
0x180068532  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068537  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006853e  jb      short loc_18006855E
0x180068540  mov     edx, 32h ; '2'
0x180068545  jmp     loc_18006825F
0x18006854a  mov     rcx, [rdi+8]
0x18006854e  mov     rax, [rcx]
0x180068551  mov     rax, [rax+20h]
0x180068555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006855a  mov     byte ptr [rdi+2Ah], 0
0x18006855e  cmp     cs:byte_180153DE0, 20h ; ' '
0x180068565  jb      short loc_180068589
0x180068567  mov     rcx, cs:WPP_GLOBAL_Control
0x18006856e  mov     edx, 33h ; '3'
0x180068573  mov     r9, rdi
0x180068576  mov     [rsp+0B0h+var_90], ebx
0x18006857a  mov     r8, r14
0x18006857d  mov     rcx, [rcx+150h]
0x180068584  call    WPP_SF_qD
0x180068589  lea     rcx, [rbp+57h+var_80]; this
0x18006858d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180068592  mov     eax, ebx
0x180068594  mov     rcx, [rbp+57h+var_30]
0x180068598  xor     rcx, rsp; StackCookie
0x18006859b  call    __security_check_cookie
0x1800685a0  add     rsp, 90h
0x1800685a7  pop     r15
0x1800685a9  pop     r14
0x1800685ab  pop     rdi
0x1800685ac  pop     rbx
0x1800685ad  pop     rbp
0x1800685ae  retn
```
