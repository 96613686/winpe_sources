# MPCHeadMovementDetector::AccumulateYawVelocity(void)

- ea: `0x18006bef4`
- end: `0x18006c1d9`
- name: `?AccumulateYawVelocity@MPCHeadMovementDetector@@AEAA_NXZ`
- size: `741`
- prototype: `bool __fastcall(MPCHeadMovementDetector *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006be10`

## callees

- `0x18006bef4`
- `0x18006c864`
- `0x18008dcac`
- `0x18008e194`
- `0x1800ac630`
- `0x1800f0990`
- `0x180116c30`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006bf35`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006bf35`

## string_xrefs

- `0x18006bf6e`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006bf8d`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006bfce`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006bfed`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006c032`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006c073`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`
- `0x18006c0cc`: `onecoreuap\windows\moderncore\inputv2\rawinputproviders\mpc\lib\mpcheadmovementdetector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall MPCHeadMovementDetector::AccumulateYawVelocity(__int64 **this, float a2)
{
  bool result; // al
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  const char *v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  const char *v11; // r9
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __m128 v18; // xmm6
  float v19; // xmm4_4
  __m128 v20; // xmm3
  __m128 v21; // xmm2
  __m128 v22; // xmm3
  __m128 v23; // xmm1
  __m128 v24; // xmm3
  __m128 v25; // xmm6
  int v26; // [rsp+28h] [rbp-49h]
  __int64 v27; // [rsp+38h] [rbp-39h] BYREF
  __int64 v28; // [rsp+40h] [rbp-31h] BYREF
  __int64 v29; // [rsp+48h] [rbp-29h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-21h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-11h] BYREF
  float v32[4]; // [rsp+68h] [rbp-9h] BYREF
  __int128 v33; // [rsp+78h] [rbp+7h] BYREF
  __m128 v34; // [rsp+88h] [rbp+17h] BYREF
  __int128 v35; // [rsp+98h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  result = MPCHeadMovementDetector::EnsureFrameOfReference((MPCHeadMovementDetector *)this);
  if ( result )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v28 = 0;
    v4 = this[12];
    v5 = *v4;
    v28 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, LARGE_INTEGER, __int64 *))(v5 + 56))(v4, PerformanceCount, &v28);
    if ( v6 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
        (const char *)(unsigned int)v6,
        v26);
    if ( !v28 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
        v7);
    v29 = 0;
    v8 = this[11];
    v9 = *v8;
    v29 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v9 + 88))(v8, v28, &v29);
    if ( v10 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
        (const char *)(unsigned int)v10,
        v26);
    if ( !v29 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
        v11);
    v27 = 0;
    v12 = this[10];
    v13 = *v12;
    v27 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v13 + 88))(v12, v28, v29, &v27);
    if ( v14 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
        (const char *)(unsigned int)v14,
        v26);
    v15 = v27;
    if ( v27 )
    {
      v35 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v27 + 56LL))(v27, &v35);
      if ( v16 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
          (const char *)(unsigned int)v16,
          v26);
      v33 = v35;
      LODWORD(v30[0]) = 0;
      *(_QWORD *)((char *)v30 + 4) = 1065353216;
      Windows::Foundation::Numerics::transform(v32, v30, &v33);
      v17 = (*(__int64 (__fastcall **)(__int64, __m128 *))(*(_QWORD *)v27 + 80LL))(v27, &v34);
      if ( v17 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\mpc\\lib\\mpcheadmovementdetector.cpp",
          (const char *)(unsigned int)v17,
          v26);
      v18 = v34;
      v19 = DirectX::XMScalarACos(retaddr, a2);
      v20 = _mm_mul_ps(v18, v18);
      v21 = _mm_shuffle_ps(v20, v20, 153);
      v20.m128_f32[0] = (float)(v20.m128_f32[0] + v21.m128_f32[0]) + _mm_shuffle_ps(v21, v21, 85).m128_f32[0];
      v22 = _mm_shuffle_ps(v20, v20, 0);
      v23 = _mm_sqrt_ps(v22);
      v24 = _mm_cmpneq_ps(v22, DirectX::g_XMInfinity);
      v25 = _mm_or_ps(
              _mm_and_ps(_mm_and_ps(_mm_div_ps(v18, v23), _mm_cmpneq_ps(v23, (__m128)0LL)), v24),
              _mm_andnot_ps(v24, DirectX::g_XMQNaN));
      v30[0] = v25.m128_u64[0];
      *((float *)this + 26) = (float)((float)((float)(_mm_shuffle_ps(v25, v25, 170).m128_f32[0] * v32[2])
                                            + (float)((float)(v25.m128_f32[1] * v32[1])
                                                    + (float)(v25.m128_f32[0] * v32[0])))
                                    * (float)(v19 + v19))
                            + *((float *)this + 26);
      ++*((_DWORD *)this + 27);
      v15 = v27;
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18006bef4  mov     rax, rsp
0x18006bef7  mov     [rax+10h], rbx
0x18006befb  push    rbp
0x18006befc  lea     rbp, [rax-5Fh]
0x18006bf00  sub     rsp, 0C0h
0x18006bf07  movaps  xmmword ptr [rax-18h], xmm6
0x18006bf0b  mov     rax, cs:__security_cookie
0x18006bf12  xor     rax, rsp
0x18006bf15  mov     [rbp+57h+var_20], rax
0x18006bf19  mov     rbx, rcx
0x18006bf1c  call    ?EnsureFrameOfReference@MPCHeadMovementDetector@@AEAA_NXZ; MPCHeadMovementDetector::EnsureFrameOfReference(void)
0x18006bf21  test    al, al
0x18006bf23  jz      loc_18006C1B7
0x18006bf29  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x18006bf31  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18006bf35  call    cs:__imp_QueryPerformanceCounter
0x18006bf3b  mov     [rbp+57h+var_88], 0
0x18006bf43  mov     rcx, [rbx+60h]
0x18006bf47  mov     rax, [rcx]
0x18006bf4a  mov     [rbp+57h+var_88], 0
0x18006bf52  lea     r8, [rbp+57h+var_88]
0x18006bf56  mov     rdx, qword ptr [rbp+57h+PerformanceCount]
0x18006bf5a  mov     rax, [rax+38h]
0x18006bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf63  mov     rcx, [rbp+5Fh]; this
0x18006bf67  test    eax, eax
0x18006bf69  jns     short loc_18006BF80
0x18006bf6b  mov     r9d, eax; char *
0x18006bf6e  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006bf75  mov     edx, 0D3h; void *
0x18006bf7a  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18006bf80  mov     rcx, [rbp+5Fh]; this
0x18006bf84  mov     rdx, [rbp+57h+var_88]
0x18006bf88  test    rdx, rdx
0x18006bf8b  jnz     short loc_18006BF9F
0x18006bf8d  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006bf94  mov     edx, 0D4h; void *
0x18006bf99  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006bf9f  mov     [rbp+57h+var_80], 0
0x18006bfa7  mov     rcx, [rbx+58h]
0x18006bfab  mov     rax, [rcx]
0x18006bfae  mov     [rbp+57h+var_80], 0
0x18006bfb6  lea     r8, [rbp+57h+var_80]
0x18006bfba  mov     rax, [rax+58h]
0x18006bfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bfc3  mov     rcx, [rbp+5Fh]; this
0x18006bfc7  test    eax, eax
0x18006bfc9  jns     short loc_18006BFE0
0x18006bfcb  mov     r9d, eax; char *
0x18006bfce  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006bfd5  mov     edx, 0DAh; void *
0x18006bfda  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18006bfe0  mov     rcx, [rbp+5Fh]; this
0x18006bfe4  mov     r8, [rbp+57h+var_80]
0x18006bfe8  test    r8, r8
0x18006bfeb  jnz     short loc_18006BFFF
0x18006bfed  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006bff4  mov     edx, 0DBh; void *
0x18006bff9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006bfff  mov     [rbp+57h+var_90], 0
0x18006c007  mov     rcx, [rbx+50h]
0x18006c00b  mov     rax, [rcx]
0x18006c00e  mov     [rbp+57h+var_90], 0
0x18006c016  lea     r9, [rbp+57h+var_90]
0x18006c01a  mov     rdx, [rbp+57h+var_88]
0x18006c01e  mov     rax, [rax+58h]
0x18006c022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c027  mov     rcx, [rbp+5Fh]; this
0x18006c02b  test    eax, eax
0x18006c02d  jns     short loc_18006C044
0x18006c02f  mov     r9d, eax; char *
0x18006c032  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006c039  mov     edx, 0DEh; void *
0x18006c03e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18006c044  mov     rcx, [rbp+57h+var_90]
0x18006c048  test    rcx, rcx
0x18006c04b  jz      loc_18006C177
0x18006c051  xorps   xmm0, xmm0
0x18006c054  movups  [rbp+57h+var_30], xmm0
0x18006c058  mov     rax, [rcx]
0x18006c05b  lea     rdx, [rbp+57h+var_30]
0x18006c05f  mov     rax, [rax+38h]
0x18006c063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c068  mov     rcx, [rbp+5Fh]; this
0x18006c06c  test    eax, eax
0x18006c06e  jns     short loc_18006C085
0x18006c070  mov     r9d, eax; char *
0x18006c073  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006c07a  mov     edx, 0E4h; void *
0x18006c07f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18006c085  movups  xmm0, [rbp+57h+var_30]
0x18006c089  movups  [rbp+57h+var_50], xmm0
0x18006c08d  mov     dword ptr [rbp+57h+var_78], 0
0x18006c094  mov     qword ptr [rbp+57h+var_78+4], 3F800000h
0x18006c09c  lea     r8, [rbp+57h+var_50]
0x18006c0a0  lea     rdx, [rbp+57h+var_78]
0x18006c0a4  lea     rcx, [rbp+57h+var_60]
0x18006c0a8  call    ?transform@Numerics@Foundation@Windows@@YA?AUfloat3@123@AEBU4123@AEBUquaternion@123@@Z; Windows::Foundation::Numerics::transform(Windows::Foundation::Numerics::float3 const &,Windows::Foundation::Numerics::quaternion const &)
0x18006c0ad  mov     rcx, [rbp+57h+var_90]
0x18006c0b1  mov     rax, [rcx]
0x18006c0b4  lea     rdx, [rbp+57h+var_40]
0x18006c0b8  mov     rax, [rax+50h]
0x18006c0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0c1  mov     rcx, [rbp+5Fh]; this
0x18006c0c5  test    eax, eax
0x18006c0c7  jns     short loc_18006C0DE
0x18006c0c9  mov     r9d, eax; char *
0x18006c0cc  lea     r8, aOnecoreuapWind_175; "onecoreuap\\windows\\moderncore\\inputv"...
0x18006c0d3  mov     edx, 0E9h; void *
0x18006c0d8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18006c0de  movups  xmm6, [rbp+57h+var_40]
0x18006c0e2  movaps  xmm0, xmm6
0x18006c0e5  shufps  xmm0, xmm6, 0FFh
0x18006c0e9  call    ?XMScalarACos@DirectX@@YAMM@Z; DirectX::XMScalarACos(float)
0x18006c0ee  movaps  xmm4, xmm0
0x18006c0f1  movaps  xmm3, xmm6
0x18006c0f4  mulps   xmm3, xmm6
0x18006c0f7  movaps  xmm2, xmm3
0x18006c0fa  shufps  xmm2, xmm3, 99h
0x18006c0fe  movaps  xmm1, xmm2
0x18006c101  shufps  xmm1, xmm2, 55h ; 'U'
0x18006c105  addss   xmm3, xmm2
0x18006c109  addss   xmm3, xmm1
0x18006c10d  shufps  xmm3, xmm3, 0
0x18006c111  sqrtps  xmm1, xmm3
0x18006c114  cmpneqps xmm3, cs:?g_XMInfinity@DirectX@@3UXMVECTORI32@1@B; DirectX::XMVECTORI32 const DirectX::g_XMInfinity
0x18006c11c  divps   xmm6, xmm1
0x18006c11f  xorps   xmm0, xmm0
0x18006c122  cmpneqps xmm1, xmm0
0x18006c126  andps   xmm6, xmm1
0x18006c129  andps   xmm6, xmm3
0x18006c12c  andnps  xmm3, cs:?g_XMQNaN@DirectX@@3UXMVECTORI32@1@B; DirectX::XMVECTORI32 const DirectX::g_XMQNaN
0x18006c133  orps    xmm6, xmm3
0x18006c136  movsd   qword ptr [rbp+57h+var_78], xmm6
0x18006c13b  movaps  xmm1, xmm6
0x18006c13e  shufps  xmm1, xmm6, 0AAh
0x18006c142  mulss   xmm1, [rbp+57h+var_58]
0x18006c147  movss   xmm0, dword ptr [rbp+57h+var_78+4]
0x18006c14c  mulss   xmm0, [rbp+57h+var_5C]
0x18006c151  mulss   xmm6, [rbp+57h+var_60]
0x18006c156  addss   xmm0, xmm6
0x18006c15a  addss   xmm1, xmm0
0x18006c15e  addss   xmm4, xmm4
0x18006c162  mulss   xmm1, xmm4
0x18006c166  addss   xmm1, dword ptr [rbx+68h]
0x18006c16b  movss   dword ptr [rbx+68h], xmm1
0x18006c170  inc     dword ptr [rbx+6Ch]
0x18006c173  mov     rcx, [rbp+57h+var_90]
0x18006c177  test    rcx, rcx
0x18006c17a  jz      short loc_18006C189
0x18006c17c  mov     rax, [rcx]
0x18006c17f  mov     rax, [rax+10h]
0x18006c183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c188  nop
0x18006c189  mov     rcx, [rbp+57h+var_80]
0x18006c18d  test    rcx, rcx
0x18006c190  jz      short loc_18006C19F
0x18006c192  mov     rax, [rcx]
0x18006c195  mov     rax, [rax+10h]
0x18006c199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c19e  nop
0x18006c19f  mov     rcx, [rbp+57h+var_88]
0x18006c1a3  test    rcx, rcx
0x18006c1a6  jz      short loc_18006C1B5
0x18006c1a8  mov     rdx, [rcx]
0x18006c1ab  mov     rax, [rdx+10h]
0x18006c1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1b4  nop
0x18006c1b5  mov     al, 1
0x18006c1b7  mov     rcx, [rbp+57h+var_20]
0x18006c1bb  xor     rcx, rsp; StackCookie
0x18006c1be  call    __security_check_cookie
0x18006c1c3  lea     r11, [rsp+0C0h+var_s0]
0x18006c1cb  mov     rbx, [r11+18h]
0x18006c1cf  movaps  xmm6, xmmword ptr [r11-10h]
0x18006c1d4  mov     rsp, r11
0x18006c1d7  pop     rbp
0x18006c1d8  retn
```
