# GpGraphics::InheritAppClippingAndTransform(HDC__ *)

- ea: `0x1800348c8`
- end: `0x180034d02`
- name: `?InheritAppClippingAndTransform@GpGraphics@@IEAA?AW4Status@@PEAUHDC__@@@Z`
- size: `1082`
- prototype: `enum Status __high(HDC)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034410`
- `0x180066100`
- `0x1800663e8`
- `0x18006651c`

## callees

- `0x180010bd0`
- `0x180011f4c`
- `0x180012220`
- `0x1800348c8`
- `0x180035b10`
- `0x180036328`
- `0x1800391f4`
- `0x180051890`
- `0x180053f94`
- `0x180063cd8`
- `0x1800cb6e0`
- `0x180105d40`
- `0x180172010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180034cf1`
- `GDI32!DeleteObject` at `0x180034cf1`
- `GDI32!GetViewportOrgEx` at `0x180034b17`
- `GDI32!GetViewportOrgEx` at `0x180034b17`
- `GDI32!GetRegionData` at `0x180034a75`
- `GDI32!GetRegionData` at `0x180034c4b`
- `GDI32!GetRegionData` at `0x180034c8a`
- `GDI32!GetRegionData` at `0x180034a75`
- `GDI32!GetRegionData` at `0x180034c4b`
- `GDI32!GetRegionData` at `0x180034c8a`
- `GDI32!ScaleRgn` at `0x180034cd1`
- `GDI32!ScaleRgn` at `0x180034cd1`
- `GDI32!GetRandomRgn` at `0x180034a3b`
- `GDI32!GetRandomRgn` at `0x180034a3b`
- `GDI32!LPtoDP` at `0x18003493c`
- `GDI32!LPtoDP` at `0x18003493c`

## pseudocode

```c
__int64 __fastcall GpGraphics::InheritAppClippingAndTransform(__int64 a1, HDC a2)
{
  PointF *v3; // rdi
  __int64 v5; // rsi
  LONG y; // edx
  __int64 v7; // rcx
  float x; // xmm0_4
  float v9; // xmm4_4
  int v10; // eax
  float v11; // xmm4_4
  float v12; // xmm5_4
  float v13; // xmm2_4
  float v14; // xmm1_4
  int v15; // eax
  __int64 v16; // rcx
  HRGN CachedGdiRegion; // rax
  HRGN v18; // rdi
  unsigned int v19; // r14d
  signed int RegionData; // eax
  _RGNDATA *p_RgnData; // rsi
  __int64 v22; // rcx
  LONG v23; // esi
  LONG v24; // r15d
  __int64 result; // rax
  __int64 v26; // rcx
  signed int v27; // eax
  DWORD v28; // r14d
  struct _RGNDATA *v29; // rax
  __int64 v30; // rax
  struct tagPOINT point; // [rsp+20h] [rbp-E0h] BYREF
  __m128i si128; // [rsp+28h] [rbp-D8h] BYREF
  struct tagPOINT pt[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+48h] [rbp-B8h]
  int v35; // [rsp+4Ch] [rbp-B4h]
  float v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  _RGNDATA RgnData; // [rsp+70h] [rbp-90h] BYREF

  v3 = (PointF *)v36;
  v5 = 3;
  do
  {
    PointF::PointF(v3);
    v3 = (PointF *)((char *)v3 + 8);
    --v5;
  }
  while ( v5 );
  v34 = 0;
  v35 = 0x2000;
  *(__m128i *)&pt[0].x = _mm_load_si128((const __m128i *)&_xmm);
  if ( !LPtoDP(a2, pt, 3) )
    return 1;
  y = pt[0].y;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( pt[0].x == v34 && pt[0].y == pt[1].y )
  {
    v7 = *(_QWORD *)(a1 + 136) + 192LL;
    x = (float)pt[0].x;
    v9 = (float)(pt[1].x - pt[0].x);
    v10 = v35 - pt[0].y;
    *(_QWORD *)(v7 + 20) = 0;
    v11 = v9 + x;
    v12 = (float)v10 + (float)y;
    v13 = (float)(v11 - x) * 0.00012207031;
    *(float *)(v7 + 16) = v13;
    v14 = (float)(v12 - (float)y) * 0.00012207031;
    *(float *)(v7 + 28) = v14;
    *(float *)(v7 + 32) = v11 - (float)(v13 * 8192.0);
    *(float *)(v7 + 36) = v12 - (float)(v14 * 8192.0);
    v15 = GpMatrix::ComputeComplexity((GpMatrix *)v7);
    *(_DWORD *)(v16 + 40) = v15;
  }
  else
  {
    v26 = *(_QWORD *)(a1 + 136) + 192LL;
    v36[0] = (float)pt[0].x;
    v36[1] = (float)pt[0].y;
    v36[2] = (float)pt[1].x;
    v36[3] = (float)pt[1].y;
    v36[4] = (float)v34;
    v36[5] = (float)v35;
    result = GpMatrix::InferAffineMatrix(v26, v36, &si128);
    if ( (_DWORD)result )
      return result;
  }
  DpContext::UpdateWorldToDeviceMatrix(*(DpContext **)(a1 + 136));
  CachedGdiRegion = GetCachedGdiRegion();
  v18 = CachedGdiRegion;
  if ( !CachedGdiRegion )
    return 3;
  v19 = 0;
  if ( GetRandomRgn(a2, CachedGdiRegion, 1) != 1 )
    goto LABEL_16;
  if ( *(int *)(*(_QWORD *)(a1 + 136) + 776LL) <= 1 || (unsigned int)ScaleRgn(a2, v18) )
  {
    RegionData = GetRegionData(v18, 0x400u, &RgnData);
    p_RgnData = &RgnData;
    if ( RegionData >= 1 && (unsigned int)RegionData <= 0x400 )
      goto LABEL_12;
    v27 = GetRegionData(v18, 0, 0);
    v28 = v27;
    if ( v27 <= 1 )
      goto LABEL_12;
    v29 = (struct _RGNDATA *)GpMallocEx(v27, 0);
    p_RgnData = v29;
    if ( v29 )
    {
      v29->rdh.nCount = 0;
      GetRegionData(v18, v28, v29);
LABEL_12:
      if ( (unsigned int)DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, p_RgnData->Buffer, p_RgnData->rdh.nCount)
        || (unsigned int)DpRegion::And(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928) )
      {
        DpRegion::Set(*(_QWORD *)(a1 + 136) + 408LL, a1 + 928, 0);
      }
      v19 = DpRegion::And(*(_QWORD *)(a1 + 136) + 304LL, *(_QWORD *)(a1 + 136) + 408LL);
      if ( p_RgnData != &RgnData )
        GpFree(p_RgnData);
      goto LABEL_16;
    }
    return 3;
  }
  v19 = 1;
LABEL_16:
  point = 0;
  GetViewportOrgEx(a2, &point);
  v22 = *(_QWORD *)(a1 + 56);
  v23 = point.y;
  v24 = point.x;
  if ( v22 )
  {
    v30 = *(_QWORD *)(a1 + 136);
    if ( point.x != *(_DWORD *)(v30 + 36) || point.y != *(_DWORD *)(v30 + 40) )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 384LL))(
        v22,
        (unsigned int)point.x,
        (unsigned int)point.y);
  }
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 36LL) = v24;
  *(_DWORD *)(*(_QWORD *)(a1 + 136) + 40LL) = v23;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&Globals::CachedGdiRegion, (signed __int64)v18, 0) )
    DeleteObject(v18);
  return v19;
}

```

## disassembly

```asm
0x1800348c8  mov     [rsp-8+arg_10], rbx
0x1800348cd  push    rbp
0x1800348ce  push    rsi
0x1800348cf  push    rdi
0x1800348d0  push    r14
0x1800348d2  push    r15
0x1800348d4  lea     rbp, [rsp-380h]
0x1800348dc  sub     rsp, 480h
0x1800348e3  mov     rax, cs:__security_cookie
0x1800348ea  xor     rax, rsp
0x1800348ed  mov     [rbp+3A0h+var_30], rax
0x1800348f4  mov     r15, rdx
0x1800348f7  lea     rdi, [rsp+4A0h+var_450]
0x1800348fc  mov     rbx, rcx
0x1800348ff  mov     esi, 3
0x180034904  mov     rcx, rdi; this
0x180034907  call    ??0PointF@@QEAA@XZ; PointF::PointF(void)
0x18003490c  add     rdi, 8
0x180034910  sub     rsi, 1
0x180034914  jnz     short loc_180034904
0x180034916  movdqa  xmm0, cs:__xmm@00000000000020000000000000000000
0x18003491e  lea     r8d, [rsi+3]; c
0x180034922  lea     rdx, [rsp+4A0h+pt]; lppt
0x180034927  mov     [rsp+4A0h+var_458], esi
0x18003492b  mov     rcx, r15; hdc
0x18003492e  mov     [rsp+4A0h+var_454], 2000h
0x180034936  movdqu  xmmword ptr [rsp+4A0h+pt.x], xmm0
0x18003493c  call    cs:__imp_LPtoDP
0x180034943  nop     dword ptr [rax+rax+00h]
0x180034948  test    eax, eax
0x18003494a  jz      loc_180034B89
0x180034950  movdqa  xmm0, cs:__xmm@46000000460000000000000000000000
0x180034958  mov     r8d, [rsp+4A0h+pt.x]
0x18003495d  mov     edx, [rsp+4A0h+pt.y]
0x180034961  movups  [rsp+4A0h+var_478], xmm0
0x180034966  cmp     r8d, [rsp+4A0h+var_458]
0x18003496b  jnz     loc_180034BC2
0x180034971  cmp     edx, [rsp+4A0h+pt.y+8]
0x180034975  jnz     loc_180034BC2
0x18003497b  mov     eax, [rsp+4A0h+pt.x+8]
0x18003497f  mov     rcx, [rbx+88h]
0x180034986  sub     eax, r8d
0x180034989  add     rcx, 0C0h; this
0x180034990  movd    xmm0, r8d
0x180034995  cvtdq2ps xmm0, xmm0
0x180034998  movd    xmm4, eax
0x18003499c  mov     eax, [rsp+4A0h+var_454]
0x1800349a0  cvtdq2ps xmm4, xmm4
0x1800349a3  sub     eax, edx
0x1800349a5  mov     [rcx+14h], rsi
0x1800349a9  movd    xmm3, edx
0x1800349ad  cvtdq2ps xmm3, xmm3
0x1800349b0  addss   xmm4, xmm0
0x1800349b4  movd    xmm5, eax
0x1800349b8  cvtdq2ps xmm5, xmm5
0x1800349bb  movaps  xmm2, xmm4
0x1800349be  addss   xmm5, xmm3
0x1800349c2  subss   xmm2, xmm0
0x1800349c6  movaps  xmm1, xmm5
0x1800349c9  mulss   xmm2, cs:__real@39000000
0x1800349d1  subss   xmm1, xmm3
0x1800349d5  movss   dword ptr [rcx+10h], xmm2
0x1800349da  mulss   xmm1, cs:__real@39000000
0x1800349e2  mulss   xmm2, cs:__real@46000000
0x1800349ea  movss   dword ptr [rcx+1Ch], xmm1
0x1800349ef  mulss   xmm1, cs:__real@46000000
0x1800349f7  subss   xmm4, xmm2
0x1800349fb  subss   xmm5, xmm1
0x1800349ff  movss   dword ptr [rcx+20h], xmm4
0x180034a04  movss   dword ptr [rcx+24h], xmm5
0x180034a09  call    ?ComputeComplexity@GpMatrix@@IEBAHXZ; GpMatrix::ComputeComplexity(void)
0x180034a0e  mov     [rcx+28h], eax
0x180034a11  mov     rcx, [rbx+88h]; this
0x180034a18  call    ?UpdateWorldToDeviceMatrix@DpContext@@QEAAXXZ; DpContext::UpdateWorldToDeviceMatrix(void)
0x180034a1d  call    ?GetCachedGdiRegion@@YAPEAUHRGN__@@XZ; GetCachedGdiRegion(void)
0x180034a22  mov     rdi, rax
0x180034a25  test    rax, rax
0x180034a28  jz      loc_180034BBB
0x180034a2e  xor     r14d, r14d
0x180034a31  mov     rdx, rax; hrgn
0x180034a34  mov     rcx, r15; hdc
0x180034a37  lea     r8d, [r14+1]; i
0x180034a3b  call    cs:__imp_GetRandomRgn
0x180034a42  nop     dword ptr [rax+rax+00h]
0x180034a47  cmp     eax, 1
0x180034a4a  jnz     loc_180034B06
0x180034a50  mov     rax, [rbx+88h]
0x180034a57  cmp     dword ptr [rax+308h], 1
0x180034a5e  jg      loc_180034CCB
0x180034a64  mov     r14d, 400h
0x180034a6a  lea     r8, [rsp+4A0h+RgnData]; lpRgnData
0x180034a6f  mov     edx, r14d; nCount
0x180034a72  mov     rcx, rdi; hrgn
0x180034a75  call    cs:__imp_GetRegionData
0x180034a7c  nop     dword ptr [rax+rax+00h]
0x180034a81  lea     rsi, [rsp+4A0h+RgnData]
0x180034a86  cmp     eax, 1
0x180034a89  jl      loc_180034C43
0x180034a8f  cmp     eax, r14d
0x180034a92  ja      loc_180034C43
0x180034a98  mov     rcx, [rbx+88h]
0x180034a9f  lea     rdx, [rsi+20h]
0x180034aa3  mov     r8d, [rsi+8]
0x180034aa7  mov     r14d, 198h
0x180034aad  add     rcx, r14
0x180034ab0  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBUtagRECT@@H@Z; DpRegion::Set(tagRECT const *,int)
0x180034ab5  test    eax, eax
0x180034ab7  jnz     loc_180034B9D
0x180034abd  mov     rcx, [rbx+88h]
0x180034ac4  lea     rdx, [rbx+3A0h]
0x180034acb  add     rcx, r14
0x180034ace  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x180034ad3  test    eax, eax
0x180034ad5  jnz     loc_180034B9D
0x180034adb  mov     rcx, [rbx+88h]
0x180034ae2  lea     rdx, [rcx+198h]
0x180034ae9  add     rcx, 130h
0x180034af0  call    ?And@DpRegion@@QEAA?AW4Status@@PEBV1@@Z; DpRegion::And(DpRegion const *)
0x180034af5  mov     r14d, eax
0x180034af8  lea     rax, [rsp+4A0h+RgnData]
0x180034afd  cmp     rsi, rax
0x180034b00  jnz     loc_180034B90
0x180034b06  lea     rdx, [rsp+4A0h+point]; lppoint
0x180034b0b  mov     qword ptr [rsp+4A0h+point.x], 0
0x180034b14  mov     rcx, r15; hdc
0x180034b17  call    cs:__imp_GetViewportOrgEx
0x180034b1e  nop     dword ptr [rax+rax+00h]
0x180034b23  mov     rcx, [rbx+38h]
0x180034b27  mov     esi, [rsp+4A0h+point.y]
0x180034b2b  mov     r15d, [rsp+4A0h+point.x]
0x180034b30  test    rcx, rcx
0x180034b33  jnz     loc_180034C9B
0x180034b39  mov     rax, [rbx+88h]
0x180034b40  mov     [rax+24h], r15d
0x180034b44  mov     rax, [rbx+88h]
0x180034b4b  mov     [rax+28h], esi
0x180034b4e  xor     eax, eax
0x180034b50  lock cmpxchg cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rdi; HRGN__ * Globals::CachedGdiRegion
0x180034b59  jnz     loc_180034CEE
0x180034b5f  mov     eax, r14d
0x180034b62  mov     rcx, [rbp+3A0h+var_30]
0x180034b69  xor     rcx, rsp; StackCookie
0x180034b6c  call    __security_check_cookie
0x180034b71  mov     rbx, [rsp+4A0h+arg_10]
0x180034b79  add     rsp, 480h
0x180034b80  pop     r15
0x180034b82  pop     r14
0x180034b84  pop     rdi
0x180034b85  pop     rsi
0x180034b86  pop     rbp
0x180034b87  retn
0x180034b89  mov     eax, 1
0x180034b8e  jmp     short loc_180034B62
0x180034b90  mov     rcx, rsi
0x180034b93  call    GpFree
0x180034b98  jmp     loc_180034B06
0x180034b9d  mov     rcx, [rbx+88h]
0x180034ba4  lea     rdx, [rbx+3A0h]
0x180034bab  add     rcx, r14
0x180034bae  xor     r8d, r8d
0x180034bb1  call    ?Set@DpRegion@@QEAA?AW4Status@@PEBV1@H@Z; DpRegion::Set(DpRegion const *,int)
0x180034bb6  jmp     loc_180034ADB
0x180034bbb  mov     eax, 3
0x180034bc0  jmp     short loc_180034B62
0x180034bc2  mov     rcx, [rbx+88h]
0x180034bc9  movd    xmm0, r8d
0x180034bce  add     rcx, 0C0h
0x180034bd5  cvtdq2ps xmm0, xmm0
0x180034bd8  lea     r8, [rsp+4A0h+var_478]
0x180034bdd  movd    xmm1, edx
0x180034be1  lea     rdx, [rsp+4A0h+var_450]
0x180034be6  cvtdq2ps xmm1, xmm1
0x180034be9  movss   [rsp+4A0h+var_450], xmm0
0x180034bef  movd    xmm0, [rsp+4A0h+pt.x+8]
0x180034bf5  movss   [rsp+4A0h+var_44C], xmm1
0x180034bfb  movd    xmm1, [rsp+4A0h+pt.y+8]
0x180034c01  cvtdq2ps xmm0, xmm0
0x180034c04  cvtdq2ps xmm1, xmm1
0x180034c07  movss   [rsp+4A0h+var_448], xmm0
0x180034c0d  movd    xmm0, [rsp+4A0h+var_458]
0x180034c13  movss   [rsp+4A0h+var_444], xmm1
0x180034c19  movd    xmm1, [rsp+4A0h+var_454]
0x180034c1f  cvtdq2ps xmm0, xmm0
0x180034c22  cvtdq2ps xmm1, xmm1
0x180034c25  movss   [rsp+4A0h+var_440], xmm0
0x180034c2b  movss   [rsp+4A0h+var_43C], xmm1
0x180034c31  call    ?InferAffineMatrix@GpMatrix@@QEAA?AW4Status@@PEBVPointF@@AEBVRectF@@@Z; GpMatrix::InferAffineMatrix(PointF const *,RectF const &)
0x180034c36  test    eax, eax
0x180034c38  jnz     loc_180034B62
0x180034c3e  jmp     loc_180034A11
0x180034c43  xor     r8d, r8d; lpRgnData
0x180034c46  xor     edx, edx; nCount
0x180034c48  mov     rcx, rdi; hrgn
0x180034c4b  call    cs:__imp_GetRegionData
0x180034c52  nop     dword ptr [rax+rax+00h]
0x180034c57  movsxd  r14, eax
0x180034c5a  cmp     r14d, 1
0x180034c5e  jle     loc_180034A98
0x180034c64  mov     rcx, r14
0x180034c67  xor     edx, edx
0x180034c69  call    GpMallocEx
0x180034c6e  mov     rsi, rax
0x180034c71  test    rax, rax
0x180034c74  jz      loc_180034BBB
0x180034c7a  mov     r8, rax; lpRgnData
0x180034c7d  mov     dword ptr [rax+8], 0
0x180034c84  mov     edx, r14d; nCount
0x180034c87  mov     rcx, rdi; hrgn
0x180034c8a  call    cs:__imp_GetRegionData
0x180034c91  nop     dword ptr [rax+rax+00h]
0x180034c96  jmp     loc_180034A98
0x180034c9b  mov     rax, [rbx+88h]
0x180034ca2  cmp     r15d, [rax+24h]
0x180034ca6  jnz     short loc_180034CB1
0x180034ca8  cmp     esi, [rax+28h]
0x180034cab  jz      loc_180034B39
0x180034cb1  mov     rax, [rcx]
0x180034cb4  mov     r8d, esi
0x180034cb7  mov     edx, r15d
0x180034cba  mov     rax, [rax+180h]
0x180034cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cc6  jmp     loc_180034B39
0x180034ccb  mov     rdx, rdi
0x180034cce  mov     rcx, r15
0x180034cd1  call    cs:__imp_ScaleRgn
0x180034cd8  nop     dword ptr [rax+rax+00h]
0x180034cdd  test    eax, eax
0x180034cdf  jnz     loc_180034A64
0x180034ce5  lea     r14d, [rax+1]
0x180034ce9  jmp     loc_180034B06
0x180034cee  mov     rcx, rdi; ho
0x180034cf1  call    cs:__imp_DeleteObject
0x180034cf8  nop     dword ptr [rax+rax+00h]
0x180034cfd  jmp     loc_180034B5F
```
