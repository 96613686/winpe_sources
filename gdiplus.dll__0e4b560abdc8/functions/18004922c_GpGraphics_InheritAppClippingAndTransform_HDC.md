# GpGraphics::InheritAppClippingAndTransform(HDC__ *)

- ea: `0x18004922c`
- end: `0x180049663`
- name: `?InheritAppClippingAndTransform@GpGraphics@@IEAA?AW4Status@@PEAUHDC__@@@Z`
- size: `1079`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018178`
- `0x18006ecbc`
- `0x18006fdc0`
- `0x18006fef8`

## callees

- `0x18001b2d0`
- `0x18001b8b0`
- `0x18001c000`
- `0x18001e464`
- `0x18001f504`
- `0x18001f950`
- `0x180021ff8`
- `0x180048ac0`
- `0x18004922c`
- `0x1800b3330`
- `0x1800e5044`
- `0x1800e9380`
- `0x180175010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180049652`
- `GDI32!DeleteObject` at `0x180049652`
- `GDI32!GetViewportOrgEx` at `0x180049479`
- `GDI32!GetViewportOrgEx` at `0x180049479`
- `GDI32!GetRegionData` at `0x1800493da`
- `GDI32!GetRegionData` at `0x1800495ca`
- `GDI32!GetRegionData` at `0x180049602`
- `GDI32!GetRegionData` at `0x1800493da`
- `GDI32!GetRegionData` at `0x1800495ca`
- `GDI32!GetRegionData` at `0x180049602`
- `GDI32!ScaleRgn` at `0x180049619`
- `GDI32!ScaleRgn` at `0x180049619`
- `GDI32!GetRandomRgn` at `0x1800493a0`
- `GDI32!GetRandomRgn` at `0x1800493a0`
- `GDI32!LPtoDP` at `0x1800492a0`
- `GDI32!LPtoDP` at `0x1800492a0`

## pseudocode

```c
__int64 __fastcall GpGraphics::InheritAppClippingAndTransform(__int64 a1, HDC a2)
{
  PointF *v3; // rbx
  __int64 v5; // rsi
  LONG y; // edx
  __int64 v7; // rcx
  float x; // xmm0_4
  __m128i v9; // xmm4
  int v10; // eax
  float v11; // xmm5_4
  float v12; // xmm2_4
  float v13; // xmm1_4
  int v14; // eax
  __int64 v15; // rcx
  HRGN CachedGdiRegion; // rax
  HRGN v17; // rsi
  unsigned int v18; // r14d
  signed int RegionData; // eax
  _RGNDATA *p_RgnData; // rbx
  __int64 v21; // rcx
  LONG v22; // r15d
  LONG v23; // ebx
  __int64 v24; // rax
  __int64 result; // rax
  __int64 v26; // rcx
  signed int v27; // eax
  DWORD v28; // r14d
  struct _RGNDATA *v29; // rax
  struct tagPOINT point; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v31; // [rsp+28h] [rbp-D8h] BYREF
  struct tagPOINT pt[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  int v34; // [rsp+4Ch] [rbp-B4h]
  float v35[8]; // [rsp+50h] [rbp-B0h] BYREF
  _RGNDATA RgnData; // [rsp+70h] [rbp-90h] BYREF

  v3 = (PointF *)v35;
  v5 = 3;
  do
  {
    PointF::PointF(v3);
    v3 = (PointF *)((char *)v3 + 8);
    --v5;
  }
  while ( v5 );
  v33 = 0;
  v34 = 0x2000;
  *(__m128i *)&pt[0].x = _mm_load_si128((const __m128i *)&_xmm);
  if ( !LPtoDP(a2, pt, 3) )
    return 1;
  y = pt[0].y;
  v31 = _xmm;
  if ( pt[0].y == pt[1].y && pt[0].x == v33 )
  {
    v7 = *(_QWORD *)(a1 + 136) + 192LL;
    x = (float)pt[0].x;
    v9 = _mm_cvtsi32_si128(pt[1].x - pt[0].x);
    v10 = v34;
    *(_DWORD *)(v7 + 20) = 0;
    *(_DWORD *)(v7 + 24) = 0;
    *(float *)v9.m128i_i32 = _mm_cvtepi32_ps(v9).m128_f32[0] + x;
    v11 = (float)(v10 - y) + (float)y;
    v12 = (float)(*(float *)v9.m128i_i32 - x) * 0.00012207031;
    *(float *)(v7 + 16) = v12;
    v13 = (float)(v11 - (float)y) * 0.00012207031;
    *(float *)(v7 + 28) = v13;
    *(float *)(v7 + 32) = *(float *)v9.m128i_i32 - (float)(v12 * 8192.0);
    *(float *)(v7 + 36) = v11 - (float)(v13 * 8192.0);
    v14 = GpMatrix::ComputeComplexity((GpMatrix *)v7);
    *(_DWORD *)(v15 + 40) = v14;
  }
  else
  {
    v26 = *(_QWORD *)(a1 + 136) + 192LL;
    v35[0] = (float)pt[0].x;
    v35[1] = (float)pt[0].y;
    v35[2] = (float)pt[1].x;
    v35[3] = (float)pt[1].y;
    v35[4] = (float)v33;
    v35[5] = (float)v34;
    result = GpMatrix::InferAffineMatrix(v26, v35, &v31);
    if ( (_DWORD)result )
      return result;
  }
  DpContext::UpdateWorldToDeviceMatrix(*(DpContext **)(a1 + 136));
  CachedGdiRegion = GetCachedGdiRegion();
  v17 = CachedGdiRegion;
  if ( !CachedGdiRegion )
    return 3;
  v18 = 0;
  if ( GetRandomRgn(a2, CachedGdiRegion, 1) != 1 )
    goto LABEL_16;
  if ( *(int *)(*(_QWORD *)(a1 + 136) + 776LL) <= 1 || (unsigned int)ScaleRgn(a2, v17) )
  {
    RegionData = GetRegionData(v17, 0x400u, &RgnData);
    p_RgnData = &RgnData;
    if ( RegionData >= 1 && (unsigned int)RegionData <= 0x400 )
      goto LABEL_12;
    v27 = GetRegionData(v17, 0, 0);
    v28 = v27;
    if ( v27 <= 1 )
      goto LABEL_12;
    v29 = (struct _RGNDATA *)GpMallocEx(v27, 0);
    p_RgnData = v29;
    if ( v29 )
    {
      v29->rdh.nCount = 0;
      GetRegionData(v17, v28, v29);
LABEL_12:
      if ( (unsigned int)DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, p_RgnData->Buffer, p_RgnData->rdh.nCount)
        || (unsigned int)DpRegion::And(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928) )
      {
        DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928, 0);
      }
      v18 = DpRegion::And(*(_QWORD *)(a1 + 136) + 304LL, *(_QWORD *)(a1 + 136) + 408LL);
      if ( p_RgnData != &RgnData )
        GpFree(p_RgnData);
      goto LABEL_16;
    }
    return 3;
  }
  v18 = 1;
LABEL_16:
  point = 0;
  GetViewportOrgEx(a2, &point);
  v21 = *(_QWORD *)(a1 + 56);
  v22 = point.y;
  v23 = point.x;
  if ( v21 )
  {
    v24 = *(_QWORD *)(a1 + 136);
    if ( point.x != *(_DWORD *)(v24 + 36) || point.y != *(_DWORD *)(v24 + 40) )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v21 + 384LL))(
        v21,
        (unsigned int)point.x,
        (unsigned int)point.y);
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 36LL) = v23;
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 40LL) = v22;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&Globals::CachedGdiRegion, (signed __int64)v17, 0) )
    DeleteObject(v17);
  return v18;
}

```

## disassembly

```asm
0x18004922c  mov     [rsp-8+arg_10], rbx
0x180049231  push    rbp
0x180049232  push    rsi
0x180049233  push    rdi
0x180049234  push    r14
0x180049236  push    r15
0x180049238  lea     rbp, [rsp-380h]
0x180049240  sub     rsp, 480h
0x180049247  mov     rax, cs:__security_cookie
0x18004924e  xor     rax, rsp
0x180049251  mov     [rbp+3A0h+var_30], rax
0x180049258  mov     r15, rdx
0x18004925b  lea     rbx, [rsp+4A0h+var_450]
0x180049260  mov     rdi, rcx
0x180049263  mov     esi, 3
0x180049268  mov     rcx, rbx; this
0x18004926b  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x180049270  add     rbx, 8
0x180049274  sub     rsi, 1
0x180049278  jnz     short loc_180049268
0x18004927a  movdqa  xmm0, cs:__xmm@00000000000020000000000000000000
0x180049282  lea     r8d, [rsi+3]; c
0x180049286  and     [rsp+4A0h+var_458], esi
0x18004928a  lea     rdx, [rsp+4A0h+pt]; lppt
0x18004928f  mov     rcx, r15; hdc
0x180049292  mov     [rsp+4A0h+var_454], 2000h
0x18004929a  movdqu  xmmword ptr [rsp+4A0h+pt.x], xmm0
0x1800492a0  call    cs:__imp_LPtoDP
0x1800492a7  nop     dword ptr [rax+rax+00h]
0x1800492ac  test    eax, eax
0x1800492ae  jz      loc_180049583
0x1800492b4  movaps  xmm0, cs:__xmm@46000000460000000000000000000000
0x1800492bb  mov     edx, [rsp+4A0h+pt.y]
0x1800492bf  mov     r8d, [rsp+4A0h+pt.x]
0x1800492c4  movups  [rsp+4A0h+var_478], xmm0
0x1800492c9  cmp     edx, [rsp+4A0h+pt.y+8]
0x1800492cd  jnz     loc_180049502
0x1800492d3  cmp     r8d, [rsp+4A0h+var_458]
0x1800492d8  jnz     loc_180049502
0x1800492de  mov     eax, [rsp+4A0h+pt.x+8]
0x1800492e2  mov     rcx, [rdi+88h]
0x1800492e9  sub     eax, r8d
0x1800492ec  add     rcx, 0C0h; this
0x1800492f3  movd    xmm0, r8d
0x1800492f8  cvtdq2ps xmm0, xmm0
0x1800492fb  movd    xmm4, eax
0x1800492ff  mov     eax, [rsp+4A0h+var_454]
0x180049303  and     [rcx+14h], esi
0x180049306  sub     eax, edx
0x180049308  and     [rcx+18h], esi
0x18004930b  cvtdq2ps xmm4, xmm4
0x18004930e  movd    xmm5, eax
0x180049312  cvtdq2ps xmm5, xmm5
0x180049315  addss   xmm4, xmm0
0x180049319  movd    xmm3, edx
0x18004931d  cvtdq2ps xmm3, xmm3
0x180049320  movaps  xmm2, xmm4
0x180049323  addss   xmm5, xmm3
0x180049327  subss   xmm2, xmm0
0x18004932b  movaps  xmm1, xmm5
0x18004932e  mulss   xmm2, cs:__real@39000000
0x180049336  subss   xmm1, xmm3
0x18004933a  movss   dword ptr [rcx+10h], xmm2
0x18004933f  mulss   xmm1, cs:__real@39000000
0x180049347  mulss   xmm2, cs:__real@46000000
0x18004934f  movss   dword ptr [rcx+1Ch], xmm1
0x180049354  mulss   xmm1, cs:__real@46000000
0x18004935c  subss   xmm4, xmm2
0x180049360  subss   xmm5, xmm1
0x180049364  movss   dword ptr [rcx+20h], xmm4
0x180049369  movss   dword ptr [rcx+24h], xmm5
0x18004936e  call    ?ComputeComplexity@GpMatrix@@IEBAHXZ; GpMatrix::ComputeComplexity(void)
0x180049373  mov     [rcx+28h], eax
0x180049376  mov     rcx, [rdi+88h]; this
0x18004937d  call    ?UpdateWorldToDeviceMatrix@DpContext@@QEAAXXZ; DpContext::UpdateWorldToDeviceMatrix(void)
0x180049382  call    ?GetCachedGdiRegion@@YAPEAUHRGN__@@XZ; GetCachedGdiRegion(void)
0x180049387  mov     rsi, rax
0x18004938a  test    rax, rax
0x18004938d  jz      loc_1800495AB
0x180049393  xor     r14d, r14d
0x180049396  mov     rdx, rax; hrgn
0x180049399  mov     rcx, r15; hdc
0x18004939c  lea     r8d, [r14+1]; i
0x1800493a0  call    cs:__imp_GetRandomRgn
0x1800493a7  nop     dword ptr [rax+rax+00h]
0x1800493ac  cmp     eax, 1
0x1800493af  jnz     loc_18004946B
0x1800493b5  mov     rax, [rdi+88h]
0x1800493bc  cmp     dword ptr [rax+308h], 1
0x1800493c3  jg      loc_180049613
0x1800493c9  mov     r14d, 400h
0x1800493cf  lea     r8, [rsp+4A0h+RgnData]; lpRgnData
0x1800493d4  mov     edx, r14d; nCount
0x1800493d7  mov     rcx, rsi; hrgn
0x1800493da  call    cs:__imp_GetRegionData
0x1800493e1  nop     dword ptr [rax+rax+00h]
0x1800493e6  lea     rbx, [rsp+4A0h+RgnData]
0x1800493eb  cmp     eax, 1
0x1800493ee  jl      loc_1800495C2
0x1800493f4  cmp     eax, r14d
0x1800493f7  ja      loc_1800495C2
0x1800493fd  mov     rcx, [rdi+88h]
0x180049404  lea     rdx, [rbx+20h]
0x180049408  mov     r8d, [rbx+8]
0x18004940c  mov     r14d, 198h
0x180049412  add     rcx, r14
0x180049415  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBUtagRECT@@H@Z; DpRegion::Set(tagRECT const *,int)
0x18004941a  test    eax, eax
0x18004941c  jnz     loc_18004958D
0x180049422  mov     rcx, [rdi+88h]
0x180049429  lea     rdx, [rdi+3A0h]
0x180049430  add     rcx, r14
0x180049433  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x180049438  test    eax, eax
0x18004943a  jnz     loc_18004958D
0x180049440  mov     rcx, [rdi+88h]
0x180049447  lea     rdx, [rcx+198h]
0x18004944e  add     rcx, 130h
0x180049455  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x18004945a  mov     r14d, eax
0x18004945d  lea     rax, [rsp+4A0h+RgnData]
0x180049462  cmp     rbx, rax
0x180049465  jnz     loc_1800495B5
0x18004946b  and     qword ptr [rsp+4A0h+point.x], 0
0x180049471  lea     rdx, [rsp+4A0h+point]; lppoint
0x180049476  mov     rcx, r15; hdc
0x180049479  call    cs:__imp_GetViewportOrgEx
0x180049480  nop     dword ptr [rax+rax+00h]
0x180049485  mov     rcx, [rdi+38h]
0x180049489  mov     r15d, [rsp+4A0h+point.y]
0x18004948e  mov     rbx, qword ptr [rsp+4A0h+point.x]
0x180049493  test    rcx, rcx
0x180049496  jz      short loc_1800494B2
0x180049498  mov     rax, [rdi+88h]
0x18004949f  cmp     ebx, [rax+24h]
0x1800494a2  jnz     loc_180049636
0x1800494a8  cmp     r15d, [rax+28h]
0x1800494ac  jnz     loc_180049636
0x1800494b2  mov     rax, [rdi+88h]
0x1800494b9  mov     [rax+24h], ebx
0x1800494bc  mov     rax, [rdi+88h]
0x1800494c3  mov     [rax+28h], r15d
0x1800494c7  xor     eax, eax
0x1800494c9  lock cmpxchg cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rsi; HRGN__ * Globals::CachedGdiRegion
0x1800494d2  jnz     loc_18004964F
0x1800494d8  mov     eax, r14d
0x1800494db  mov     rcx, [rbp+3A0h+var_30]
0x1800494e2  xor     rcx, rsp; StackCookie
0x1800494e5  call    __security_check_cookie
0x1800494ea  mov     rbx, [rsp+4A0h+arg_10]
0x1800494f2  add     rsp, 480h
0x1800494f9  pop     r15
0x1800494fb  pop     r14
0x1800494fd  pop     rdi
0x1800494fe  pop     rsi
0x1800494ff  pop     rbp
0x180049500  retn
0x180049502  mov     rcx, [rdi+88h]
0x180049509  movd    xmm0, r8d
0x18004950e  add     rcx, 0C0h
0x180049515  cvtdq2ps xmm0, xmm0
0x180049518  lea     r8, [rsp+4A0h+var_478]
0x18004951d  movd    xmm1, edx
0x180049521  lea     rdx, [rsp+4A0h+var_450]
0x180049526  cvtdq2ps xmm1, xmm1
0x180049529  movss   [rsp+4A0h+var_450], xmm0
0x18004952f  movd    xmm0, [rsp+4A0h+pt.x+8]
0x180049535  movss   [rsp+4A0h+var_44C], xmm1
0x18004953b  movd    xmm1, [rsp+4A0h+pt.y+8]
0x180049541  cvtdq2ps xmm0, xmm0
0x180049544  cvtdq2ps xmm1, xmm1
0x180049547  movss   [rsp+4A0h+var_448], xmm0
0x18004954d  movd    xmm0, [rsp+4A0h+var_458]
0x180049553  movss   [rsp+4A0h+var_444], xmm1
0x180049559  movd    xmm1, [rsp+4A0h+var_454]
0x18004955f  cvtdq2ps xmm0, xmm0
0x180049562  cvtdq2ps xmm1, xmm1
0x180049565  movss   [rsp+4A0h+var_440], xmm0
0x18004956b  movss   [rsp+4A0h+var_43C], xmm1
0x180049571  call    ?InferAffineMatrix@GpMatrix@@QEAA?AW4Status@@PEBVPointF@@AEBVRectF@@@Z; GpMatrix::InferAffineMatrix(PointF const *,RectF const &)
0x180049576  test    eax, eax
0x180049578  jnz     loc_1800494DB
0x18004957e  jmp     loc_180049376
0x180049583  mov     eax, 1
0x180049588  jmp     loc_1800494DB
0x18004958d  mov     rcx, [rdi+88h]
0x180049594  lea     rdx, [rdi+3A0h]
0x18004959b  add     rcx, r14
0x18004959e  xor     r8d, r8d
0x1800495a1  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBV1@H@Z; DpRegion::Set(DpRegion const *,int)
0x1800495a6  jmp     loc_180049440
0x1800495ab  mov     eax, 3
0x1800495b0  jmp     loc_1800494DB
0x1800495b5  mov     rcx, rbx
0x1800495b8  call    GpFree
0x1800495bd  jmp     loc_18004946B
0x1800495c2  xor     r8d, r8d; lpRgnData
0x1800495c5  xor     edx, edx; nCount
0x1800495c7  mov     rcx, rsi; hrgn
0x1800495ca  call    cs:__imp_GetRegionData
0x1800495d1  nop     dword ptr [rax+rax+00h]
0x1800495d6  movsxd  r14, eax
0x1800495d9  cmp     r14d, 1
0x1800495dd  jle     loc_1800493FD
0x1800495e3  mov     rcx, r14
0x1800495e6  xor     edx, edx
0x1800495e8  call    GpMallocEx
0x1800495ed  mov     rbx, rax
0x1800495f0  test    rax, rax
0x1800495f3  jz      short loc_1800495AB
0x1800495f5  and     dword ptr [rax+8], 0
0x1800495f9  mov     r8, rax; lpRgnData
0x1800495fc  mov     edx, r14d; nCount
0x1800495ff  mov     rcx, rsi; hrgn
0x180049602  call    cs:__imp_GetRegionData
0x180049609  nop     dword ptr [rax+rax+00h]
0x18004960e  jmp     loc_1800493FD
0x180049613  mov     rdx, rsi
0x180049616  mov     rcx, r15
0x180049619  call    cs:__imp_ScaleRgn
0x180049620  nop     dword ptr [rax+rax+00h]
0x180049625  test    eax, eax
0x180049627  jnz     loc_1800493C9
0x18004962d  lea     r14d, [rax+1]
0x180049631  jmp     loc_18004946B
0x180049636  mov     rax, [rcx]
0x180049639  mov     r8d, r15d
0x18004963c  mov     edx, ebx
0x18004963e  mov     rax, [rax+180h]
0x180049645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004964a  jmp     loc_1800494B2
0x18004964f  mov     rcx, rsi; ho
0x180049652  call    cs:__imp_DeleteObject
0x180049659  nop     dword ptr [rax+rax+00h]
0x18004965e  jmp     loc_1800494D8
```
