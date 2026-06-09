# GpCachedBitmap::GpCachedBitmap(GpBitmap *,GpGraphics *)

- ea: `0x1800218ac`
- end: `0x180021ff0`
- name: `??0GpCachedBitmap@@QEAA@PEAVGpBitmap@@PEAVGpGraphics@@@Z`
- size: `1860`
- prototype: `GpCachedBitmap *__fastcall(GpCachedBitmap *this, struct GpBitmap *, struct GpGraphics *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c8f50`

## callees

- `0x18000d670`
- `0x180011960`
- `0x1800126d0`
- `0x180015320`
- `0x180016660`
- `0x18001f950`
- `0x18001f9ec`
- `0x1800218ac`
- `0x1800222b0`
- `0x180042094`
- `0x180051ec0`
- `0x180052330`
- `0x180058c70`
- `0x18005d524`
- `0x180065f50`
- `0x18009571c`
- `0x1800d5bc0`
- `0x1800e5044`
- `0x1800e9380`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800219f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800219f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021e21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021e21`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021ed2`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180021ed2`

## pseudocode

```c
GpCachedBitmap *__fastcall GpCachedBitmap::GpCachedBitmap(
        GpCachedBitmap *this,
        struct GpBitmap *a2,
        struct GpGraphics *a3)
{
  GpCachedBitmap *v3; // rsi
  __int64 v6; // rdx
  int v7; // r8d
  __int64 v8; // r13
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  __int64 v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  void **v13; // r8
  HDC *v14; // r9
  int v15; // edi
  __int64 v16; // r13
  int v17; // r8d
  char *v18; // r12
  char *v19; // r10
  int v20; // eax
  int v21; // edx
  unsigned int v22; // ecx
  int v23; // r9d
  int v24; // eax
  __int128 v25; // xmm1
  __int64 v26; // rax
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // r12
  unsigned __int64 v29; // r14
  __int64 v31; // rax
  GpGraphics *v32; // r14
  unsigned __int64 v33; // r12
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 v39; // r14
  int v40; // r13d
  int v41; // eax
  struct EpScanRecord *ScanRecord; // rax
  GpBitmap *v43; // rcx
  int v44; // edi
  int v45; // r15d
  GpBitmap *v46; // rax
  GpBitmap *v47; // rax
  GpBitmap *v48; // rbx
  struct ColorPalette *v49; // [rsp+20h] [rbp-E0h]
  int *v50; // [rsp+28h] [rbp-D8h]
  int v51; // [rsp+28h] [rbp-D8h]
  int v52; // [rsp+30h] [rbp-D0h]
  int v53; // [rsp+30h] [rbp-D0h]
  int v54; // [rsp+38h] [rbp-C8h]
  int v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+84h] [rbp-7Ch]
  int v57; // [rsp+84h] [rbp-7Ch]
  LPSTREAM ppstm; // [rsp+88h] [rbp-78h] BYREF
  int v59[2]; // [rsp+90h] [rbp-70h]
  unsigned __int64 v60; // [rsp+98h] [rbp-68h]
  __int64 v61; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  int v64; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v67[24]; // [rsp+D8h] [rbp-28h]
  int v68; // [rsp+F0h] [rbp-10h]
  int v69; // [rsp+F4h] [rbp-Ch]
  GpGraphics *v70; // [rsp+F8h] [rbp-8h]
  struct _RTL_CRITICAL_SECTION *v71; // [rsp+100h] [rbp+0h]
  GpCachedBitmap *v72; // [rsp+108h] [rbp+8h]
  struct GpBitmap *v73; // [rsp+110h] [rbp+10h]
  __int128 v74; // [rsp+118h] [rbp+18h] BYREF
  __int128 v75; // [rsp+128h] [rbp+28h]
  _BYTE v76[144]; // [rsp+140h] [rbp+40h] BYREF
  char v77; // [rsp+1D0h] [rbp+D0h] BYREF
  void *v78[2]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int128 v79; // [rsp+3C0h] [rbp+2C0h]
  __int64 v80; // [rsp+3D0h] [rbp+2D0h]

  v72 = this;
  v70 = a3;
  *(_QWORD *)this = &GpCachedBitmap::`vftable';
  *((_DWORD *)this + 3) = -1;
  v3 = this;
  *((_DWORD *)this + 12) = 925707;
  *((_DWORD *)this + 13) = 925707;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 7) = 0;
  v73 = a2;
  if ( (unsigned int)GpGraphics::IsTSSession(a3) )
  {
    *((_OWORD *)v3 + 1) = 0;
    ppstm = 0;
    *((_OWORD *)v3 + 2) = 0;
    v44 = 3;
    *((_QWORD *)v3 + 6) = 0;
    v45 = 1;
    if ( CreateStreamOnHGlobal(0, 1, &ppstm) < 0 || !ppstm )
      goto LABEL_61;
    if ( !(*(unsigned int (__fastcall **)(struct GpBitmap *, LPSTREAM, GUID *, _QWORD))(*(_QWORD *)a2 + 96LL))(
            a2,
            ppstm,
            &PngCodecClsID,
            0) )
    {
      *(_QWORD *)v59 = 0;
      if ( (*(int (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0) >= 0 )
      {
        v46 = (GpBitmap *)GpMallocEx(1504, 0);
        if ( v46 )
        {
          v47 = GpBitmap::GpBitmap(v46, ppstm);
          v48 = v47;
          if ( v47 )
          {
            if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v47 + 8LL))(v47) )
            {
              *((_QWORD *)v3 + 7) = v48;
              v44 = 0;
            }
            else
            {
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v48 + 56LL))(v48);
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    if ( v44 )
LABEL_61:
      v45 = 0;
    *((_DWORD *)v3 + 2) = v45 != 0 ? 1833059121 : 1279869254;
  }
  else
  {
    v74 = 0;
    v75 = 0;
    if ( v6
      && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6)
      && !(unsigned int)GpBitmap::LockBits(a2, 0, 1u, 0xE200Bu, (__int64)&v74) )
    {
      v7 = DWORD1(v74);
      *((_QWORD *)v3 + 2) = v74;
      v62 = 0;
      v61 = 0;
      v63 = 0;
      v64 = 0;
      DynArrayImpl::Grow(&v61, 32, (unsigned int)(4 * v7));
      v8 = *((_QWORD *)a3 + 5);
      v80 = 0;
      v9 = *((_QWORD *)a3 + 16);
      *(_OWORD *)v78 = 0;
      v10 = 0;
      v79 = 0;
      v11 = *(_QWORD *)(v9 + 32);
      v66 = 0;
      *(_OWORD *)v67 = 0;
      v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
      v71 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
      EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1584));
      if ( !(unsigned int)GpDevice::GetScanBuffers((GpDevice *)v11, *(_DWORD *)(v8 + 4), v13, v14, v49, v50, v52, v78) )
        goto LABEL_32;
      v15 = *(_DWORD *)(v8 + 12);
      if ( !v15 )
        goto LABEL_32;
      if ( v15 == 397319
        || v15 == 0x10000000
        || v15 == 196865
        || v15 == 197634
        || v15 == 1052676
        || (v15 & 0x10000) != 0 )
      {
        v15 = 139273;
      }
      v16 = v61;
      v17 = 0;
      v55 = 0;
      LODWORD(ppstm) = ((v15 >> 8) & 0xF8u) >> 3;
      while ( v17 < *((_DWORD *)v3 + 5) )
      {
        v18 = (char *)(v75 + v17 * DWORD2(v74));
        v19 = v18;
        v20 = 0;
        v21 = 0;
        v59[0] = 0;
        while ( 1 )
        {
          v56 = v21;
          if ( v21 >= *((_DWORD *)v3 + 4) )
            break;
          v22 = *(_DWORD *)v18 & 0xFF000000;
          if ( v22 == -16777216 )
            v23 = 2;
          else
            v23 = v22 != 0;
          LODWORD(v60) = v23;
          if ( v23 != v20 )
          {
            if ( v20 )
            {
              *(_DWORD *)v67 = v20;
              *(_DWORD *)&v67[8] = v17;
              v65 = (unsigned __int64)(v18 - v19) >> 2;
              *(_DWORD *)&v67[12] = v65;
              *(_DWORD *)&v67[4] = v21 - v65;
              *(_QWORD *)&v66 = v19;
              *((_QWORD *)&v66 + 1) = v18;
              if ( (unsigned int)DynArrayImpl::Grow(&v61, 32, 1) )
                goto LABEL_32;
              v24 = v64;
              v16 = v61;
              ++v64;
              v25 = *(_OWORD *)v67;
              v21 = v56;
              v17 = v55;
              v23 = v60;
              v26 = (unsigned int)(32 * v24);
              *(_OWORD *)(v26 + v61) = v66;
              *(_OWORD *)(v26 + v16 + 16) = v25;
              if ( v59[0] == 1 )
                v27 = 4 * (int)v65 + 31LL + v10;
              else
                v27 = (int)ppstm * (int)v65 + 31LL + v10;
              v10 = v27 & 0xFFFFFFFFFFFFFFF8uLL;
            }
            v20 = v23;
            v19 = v18;
            v59[0] = v23;
          }
          v18 += 4;
          ++v21;
        }
        if ( v20 )
        {
          *((_QWORD *)&v66 + 1) = v18;
          *(_DWORD *)&v67[8] = v17;
          v28 = (unsigned __int64)(v18 - v19) >> 2;
          *(_QWORD *)&v66 = v19;
          *(_DWORD *)&v67[4] = v21 - v28;
          *(_DWORD *)v67 = v20;
          *(_DWORD *)&v67[12] = v28;
          if ( (unsigned int)DynArrayImpl::AddMultiple(&v61, 32, 1, &v66) )
            goto LABEL_32;
          v16 = v61;
          v17 = v55;
          if ( v59[0] == 1 )
            v29 = 4 * *(_DWORD *)&v67[12] + 31LL + v10;
          else
            v29 = (int)ppstm * *(_DWORD *)&v67[12] + 31LL + v10;
          v10 = v29 & 0xFFFFFFFFFFFFFFF8uLL;
        }
        v55 = ++v17;
      }
      if ( v10 <= 0xFFFFFFFF && (int)v10 + 8 >= (unsigned int)v10 )
      {
        v31 = GpMallocEx((unsigned int)(v10 + 8), 0);
        v65 = v31;
        if ( v31 )
        {
          v32 = v70;
          v60 = (v31 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          v33 = v60;
          v34 = *((_QWORD *)v70 + 17);
          v57 = *(_DWORD *)(v34 + 36);
          v59[0] = *(_DWORD *)(v34 + 40);
          GpGraphics::SetRenderingOrigin(v70, 0, 0);
          EpAlphaBlender::EpAlphaBlender((EpAlphaBlender *)v76);
          v35 = *((_QWORD *)v32 + 17);
          *((_QWORD *)&v66 + 1) = v78;
          *(_DWORD *)v67 = 0;
          *(_QWORD *)&v66 = &v77;
          v54 = *(_DWORD *)(v35 + 44);
          v53 = *(_DWORD *)(v35 + 32);
          v51 = *(_DWORD *)(v35 + 28);
          v36 = *(_QWORD *)(v35 + 672);
          *(__m128i *)&v67[8] = _mm_load_si128((const __m128i *)&_xmm);
          v68 = 1;
          v69 = 2;
          EpAlphaBlender::BuildPipeline(v76, 1, (unsigned int)v15, 925707, v36, v51, v53, v54, 0, v78, 1, 0, 0, &v66, 1);
          v37 = v64;
          *(_QWORD *)(v66 - 8) = 0;
          if ( v37 > 0 )
          {
            v38 = v64;
            v39 = v16 + 24;
            v40 = (int)ppstm;
            do
            {
              *(_DWORD *)(v33 + 4) = *(_DWORD *)(v39 - 4);
              *(_DWORD *)(v33 + 8) = *(_DWORD *)v39;
              v41 = *(_DWORD *)(v39 + 4);
              *(_DWORD *)(v33 + 16) = v41;
              *(_DWORD *)(v33 + 12) = v41;
              if ( *(_DWORD *)(v39 - 8) == 2 )
              {
                *(_DWORD *)v33 = 65537;
                EpAlphaBlender::Blend(
                  (EpAlphaBlender *)v76,
                  (void *)(v33 + 24),
                  *(void **)(v39 - 24),
                  *(_DWORD *)(v39 + 4),
                  *(_DWORD *)(v39 - 4),
                  *(_DWORD *)v39,
                  0);
                ScanRecord = EpScanRecord::NextScanRecord((EpScanRecord *)v33, v40);
              }
              else
              {
                *(_DWORD *)v33 = 0;
                memcpy_0((void *)(v33 + 24), *(const void **)(v39 - 24), 4LL * *(int *)(v39 + 4));
                ScanRecord = (struct EpScanRecord *)EpScanRecord::InternalCalculateNextScanRecord(
                                                      v33,
                                                      *(unsigned __int16 *)(v33 + 2),
                                                      *(unsigned int *)(v33 + 12),
                                                      *(unsigned int *)(v33 + 16),
                                                      4);
              }
              v39 += 32;
              v33 = (unsigned __int64)ScanRecord;
              --v38;
            }
            while ( v38 );
            v12 = v71;
            v3 = v72;
            v16 = v61;
            v32 = v70;
          }
          GpGraphics::SetRenderingOrigin(v32, v57, v59[0]);
          v43 = v73;
          *((_QWORD *)v3 + 3) = v65;
          *((_QWORD *)v3 + 4) = v60;
          *((_QWORD *)v3 + 5) = v33;
          *((_DWORD *)v3 + 12) = v15;
          *((_DWORD *)v3 + 13) = 925707;
          GpBitmap::UnlockBits(v43, (__int64)&v74);
          *((_DWORD *)v3 + 2) = 1833059121;
          EpAlphaBlender::~EpAlphaBlender((EpAlphaBlender *)v76);
        }
        else
        {
          *((_DWORD *)v3 + 2) = 1279869254;
        }
        LeaveCriticalSection(v12);
        if ( v16 != v62 )
          GpFree(v16);
      }
      else
      {
LABEL_32:
        *((_DWORD *)v3 + 2) = 1279869254;
        LeaveCriticalSection(v12);
        DynArray<PathBound>::~DynArray<PathBound>(&v61);
      }
    }
    else
    {
      *((_DWORD *)v3 + 2) = 1279869254;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800218ac  mov     [rsp-8+arg_18], rbx
0x1800218b1  push    rbp
0x1800218b2  push    rsi
0x1800218b3  push    rdi
0x1800218b4  push    r12
0x1800218b6  push    r13
0x1800218b8  push    r14
0x1800218ba  push    r15
0x1800218bc  lea     rbp, [rsp-2E0h]
0x1800218c4  sub     rsp, 3E0h
0x1800218cb  mov     rax, cs:__security_cookie
0x1800218d2  xor     rax, rsp
0x1800218d5  mov     [rbp+310h+var_38], rax
0x1800218dc  xor     r12d, r12d
0x1800218df  mov     [rbp+310h+var_308], rcx
0x1800218e3  lea     rax, ??_7GpCachedBitmap@@6B@; const GpCachedBitmap::`vftable'
0x1800218ea  mov     [rbp+310h+var_318], r8
0x1800218ee  mov     [rcx], rax
0x1800218f1  mov     r14d, 0E200Bh
0x1800218f7  or      dword ptr [rcx+0Ch], 0FFFFFFFFh
0x1800218fb  mov     rsi, rcx
0x1800218fe  mov     [rcx+30h], r14d
0x180021902  mov     rdi, r8
0x180021905  mov     [rcx+34h], r14d
0x180021909  mov     rbx, rdx
0x18002190c  mov     [rcx+18h], r12
0x180021910  mov     [rcx+10h], r12
0x180021914  mov     [rcx+38h], r12
0x180021918  mov     rcx, r8; this
0x18002191b  mov     [rbp+310h+var_300], rdx
0x18002191f  call    ?IsTSSession@GpGraphics@@IEBAHXZ; GpGraphics::IsTSSession(void)
0x180021924  xorps   xmm0, xmm0
0x180021927  test    eax, eax
0x180021929  jnz     loc_180021EAE
0x18002192f  movups  [rbp+310h+var_2F8], xmm0
0x180021933  movups  [rbp+310h+var_2E8], xmm0
0x180021937  test    rdx, rdx
0x18002193a  jz      loc_180021FE4
0x180021940  mov     rax, [rdx]
0x180021943  mov     rcx, rdx
0x180021946  mov     rax, [rax+8]
0x18002194a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002194f  test    eax, eax
0x180021951  jz      loc_180021FE4
0x180021957  lea     rax, [rbp+310h+var_2F8]
0x18002195b  mov     r9d, r14d
0x18002195e  lea     r15d, [r12+1]
0x180021963  mov     [rsp+410h+var_3F0], rax; struct ColorPalette *
0x180021968  mov     r8d, r15d
0x18002196b  xor     edx, edx
0x18002196d  mov     rcx, rbx
0x180021970  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; GpBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x180021975  test    eax, eax
0x180021977  jnz     loc_180021FE4
0x18002197d  mov     r8d, dword ptr [rbp+310h+var_2F8+4]
0x180021981  lea     edx, [r12+20h]
0x180021986  mov     eax, dword ptr [rbp+310h+var_2F8]
0x180021989  lea     rcx, [rbp+310h+var_370]
0x18002198d  mov     [rsi+14h], r8d
0x180021991  shl     r8d, 2
0x180021995  mov     [rsi+10h], eax
0x180021998  mov     [rbp+310h+var_368], r12
0x18002199c  mov     [rbp+310h+var_370], r12
0x1800219a0  mov     [rbp+310h+var_360], r12
0x1800219a4  mov     [rbp+310h+var_358], r12d
0x1800219a8  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z; DynArrayImpl::Grow(uint,uint,int)
0x1800219ad  mov     r13, [rdi+28h]
0x1800219b1  xor     eax, eax
0x1800219b3  mov     [rbp+310h+var_40], rax
0x1800219ba  xorps   xmm1, xmm1
0x1800219bd  mov     rax, [rdi+80h]
0x1800219c4  xorps   xmm0, xmm0
0x1800219c7  movups  xmmword ptr [rbp+310h+var_60], xmm1
0x1800219ce  mov     r14d, r12d
0x1800219d1  movups  [rbp+310h+var_50], xmm1
0x1800219d8  mov     rdi, [rax+20h]
0x1800219dc  movups  [rbp+310h+var_348], xmm0
0x1800219e0  movups  xmmword ptr [rbp+310h+var_338], xmm0
0x1800219e4  lea     rbx, [rdi+630h]
0x1800219eb  mov     rcx, rbx; lpCriticalSection
0x1800219ee  mov     [rbp+310h+var_310], rbx
0x1800219f2  call    cs:__imp_EnterCriticalSection
0x1800219f9  nop     dword ptr [rax+rax+00h]
0x1800219fe  mov     edx, [r13+4]; int
0x180021a02  lea     rax, [rbp+310h+var_60]
0x180021a09  mov     rcx, rdi; this
0x180021a0c  mov     [rsp+410h+var_3D8], rax; void **
0x180021a11  call    ?GetScanBuffers@GpDevice@@QEAAHHPEAPEAXPEAPEAUHDC__@@PEAUColorPalette@@PEAHHQEAPEAX@Z; GpDevice::GetScanBuffers(int,void * *,HDC__ * *,ColorPalette *,int *,int,void * * const)
0x180021a16  test    eax, eax
0x180021a18  jz      loc_180021BE6
0x180021a1e  mov     edi, [r13+0Ch]
0x180021a22  test    edi, edi
0x180021a24  jz      loc_180021BE6
0x180021a2a  cmp     edi, 61007h
0x180021a30  jnz     loc_180021FAF
0x180021a36  mov     edi, 22009h
0x180021a3b  mov     r13, [rbp+310h+var_370]
0x180021a3f  mov     eax, edi
0x180021a41  sar     eax, 8
0x180021a44  mov     r8d, r12d
0x180021a47  and     eax, 0F8h
0x180021a4c  mov     [rbp+310h+var_390], r12d
0x180021a50  shr     eax, 3
0x180021a53  mov     dword ptr [rbp+310h+ppstm], eax
0x180021a56  cmp     r8d, [rsi+14h]
0x180021a5a  jge     loc_180021BD8
0x180021a60  mov     eax, dword ptr [rbp+310h+var_2F8+8]
0x180021a63  imul    eax, r8d
0x180021a67  movsxd  r12, eax
0x180021a6a  add     r12, qword ptr [rbp+310h+var_2E8]
0x180021a6e  xor     r11d, r11d
0x180021a71  mov     r10, r12
0x180021a74  mov     eax, r11d
0x180021a77  mov     edx, r11d
0x180021a7a  mov     [rbp+310h+var_380], eax
0x180021a7d  mov     [rbp+310h+var_38C], edx
0x180021a80  cmp     edx, [rsi+10h]
0x180021a83  jge     loc_180021B6D
0x180021a89  mov     ecx, [r12]
0x180021a8d  and     ecx, 0FF000000h
0x180021a93  cmp     ecx, 0FF000000h
0x180021a99  jnz     short loc_180021AB3
0x180021a9b  mov     r9d, 2
0x180021aa1  mov     dword ptr [rbp+310h+var_378], r9d
0x180021aa5  cmp     r9d, eax
0x180021aa8  jnz     short loc_180021ABE
0x180021aaa  add     r12, 4
0x180021aae  add     edx, r15d
0x180021ab1  jmp     short loc_180021A7D
0x180021ab3  test    ecx, ecx
0x180021ab5  mov     r9d, r11d
0x180021ab8  setnz   r9b
0x180021abc  jmp     short loc_180021AA1
0x180021abe  test    eax, eax
0x180021ac0  jz      loc_180021B50
0x180021ac6  mov     dword ptr [rbp+310h+var_338], eax
0x180021ac9  mov     rcx, r12
0x180021acc  sub     rcx, r10
0x180021acf  mov     dword ptr [rbp+310h+var_338+8], r8d
0x180021ad3  shr     rcx, 2
0x180021ad7  mov     eax, edx
0x180021ad9  sub     eax, ecx
0x180021adb  mov     [rbp+310h+var_350], rcx
0x180021adf  mov     dword ptr [rbp+310h+var_338+0Ch], ecx
0x180021ae2  mov     r8d, r15d
0x180021ae5  lea     rcx, [rbp+310h+var_370]
0x180021ae9  mov     dword ptr [rbp+310h+var_338+4], eax
0x180021aec  mov     edx, 20h ; ' '
0x180021af1  mov     qword ptr [rbp+310h+var_348], r10
0x180021af5  mov     qword ptr [rbp+310h+var_348+8], r12
0x180021af9  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z; DynArrayImpl::Grow(uint,uint,int)
0x180021afe  xor     r11d, r11d
0x180021b01  test    eax, eax
0x180021b03  jnz     loc_180021BE6
0x180021b09  mov     eax, [rbp+310h+var_358]
0x180021b0c  mov     r13, [rbp+310h+var_370]
0x180021b10  movups  xmm0, [rbp+310h+var_348]
0x180021b14  add     [rbp+310h+var_358], r15d
0x180021b18  movups  xmm1, xmmword ptr [rbp+310h+var_338]
0x180021b1c  mov     edx, [rbp+310h+var_38C]
0x180021b1f  mov     r8d, [rbp+310h+var_390]
0x180021b23  mov     r9d, dword ptr [rbp+310h+var_378]
0x180021b27  shl     eax, 5
0x180021b2a  movups  xmmword ptr [rax+r13], xmm0
0x180021b2f  movups  xmmword ptr [rax+r13+10h], xmm1
0x180021b35  mov     rax, [rbp+310h+var_350]
0x180021b39  cmp     [rbp+310h+var_380], r15d
0x180021b3d  jnz     short loc_180021B5E
0x180021b3f  shl     eax, 2
0x180021b42  movsxd  rcx, eax
0x180021b45  add     rcx, 1Fh
0x180021b49  add     r14, rcx
0x180021b4c  and     r14, 0FFFFFFFFFFFFFFF8h
0x180021b50  mov     eax, r9d
0x180021b53  mov     r10, r12
0x180021b56  mov     [rbp+310h+var_380], eax
0x180021b59  jmp     loc_180021AAA
0x180021b5e  imul    eax, dword ptr [rbp+310h+ppstm]
0x180021b62  cdqe
0x180021b64  add     rax, 1Fh
0x180021b68  add     r14, rax
0x180021b6b  jmp     short loc_180021B4C
0x180021b6d  test    eax, eax
0x180021b6f  jz      short loc_180021BCC
0x180021b71  mov     qword ptr [rbp+310h+var_348+8], r12
0x180021b75  lea     r9, [rbp+310h+var_348]
0x180021b79  sub     r12, r10
0x180021b7c  mov     dword ptr [rbp+310h+var_338+8], r8d
0x180021b80  shr     r12, 2
0x180021b84  lea     rcx, [rbp+310h+var_370]
0x180021b88  sub     edx, r12d
0x180021b8b  mov     qword ptr [rbp+310h+var_348], r10
0x180021b8f  mov     dword ptr [rbp+310h+var_338+4], edx
0x180021b92  mov     r8d, r15d
0x180021b95  mov     edx, 20h ; ' '
0x180021b9a  mov     dword ptr [rbp+310h+var_338], eax
0x180021b9d  mov     dword ptr [rbp+310h+var_338+0Ch], r12d
0x180021ba1  call    ?AddMultiple@DynArrayImpl@@IEAA?AW4Status@@IIPEBX@Z; DynArrayImpl::AddMultiple(uint,uint,void const *)
0x180021ba6  test    eax, eax
0x180021ba8  jnz     short loc_180021BE6
0x180021baa  mov     eax, dword ptr [rbp+310h+var_338+0Ch]
0x180021bad  mov     r13, [rbp+310h+var_370]
0x180021bb1  mov     r8d, [rbp+310h+var_390]
0x180021bb5  cmp     [rbp+310h+var_380], r15d
0x180021bb9  jz      short loc_180021C33
0x180021bbb  imul    eax, dword ptr [rbp+310h+ppstm]
0x180021bbf  cdqe
0x180021bc1  add     rax, 1Fh
0x180021bc5  add     r14, rax
0x180021bc8  and     r14, 0FFFFFFFFFFFFFFF8h
0x180021bcc  add     r8d, r15d
0x180021bcf  mov     [rbp+310h+var_390], r8d
0x180021bd3  jmp     loc_180021A56
0x180021bd8  mov     eax, 0FFFFFFFFh
0x180021bdd  cmp     r14, rax
0x180021be0  jbe     loc_180021E8D
0x180021be6  mov     rcx, rbx; lpCriticalSection
0x180021be9  mov     dword ptr [rsi+8], 4C494146h
0x180021bf0  call    cs:__imp_LeaveCriticalSection
0x180021bf7  nop     dword ptr [rax+rax+00h]
0x180021bfc  lea     rcx, [rbp+310h+var_370]
0x180021c00  call    ??1?$DynArray@UPathBound@@@@QEAA@XZ; DynArray<PathBound>::~DynArray<PathBound>(void)
0x180021c05  mov     rax, rsi
0x180021c08  mov     rcx, [rbp+310h+var_38]
0x180021c0f  xor     rcx, rsp; StackCookie
0x180021c12  call    __security_check_cookie
0x180021c17  mov     rbx, [rsp+410h+arg_18]
0x180021c1f  add     rsp, 3E0h
0x180021c26  pop     r15
0x180021c28  pop     r14
0x180021c2a  pop     r13
0x180021c2c  pop     r12
0x180021c2e  pop     rdi
0x180021c2f  pop     rsi
0x180021c30  pop     rbp
0x180021c31  retn
0x180021c33  shl     eax, 2
0x180021c36  movsxd  rcx, eax
0x180021c39  add     rcx, 1Fh
0x180021c3d  add     r14, rcx
0x180021c40  jmp     short loc_180021BC8
0x180021c42  mov     ecx, eax
0x180021c44  xor     edx, edx
0x180021c46  call    GpMallocEx
0x180021c4b  mov     [rbp+310h+var_350], rax
0x180021c4f  test    rax, rax
0x180021c52  jz      loc_180021E84
0x180021c58  mov     r14, [rbp+310h+var_318]
0x180021c5c  add     rax, 7
0x180021c60  and     rax, 0FFFFFFFFFFFFFFF8h
0x180021c64  xor     r8d, r8d; int
0x180021c67  mov     [rbp+310h+var_378], rax
0x180021c6b  mov     r12, rax
0x180021c6e  xor     edx, edx; int
0x180021c70  mov     rax, [r14+88h]
0x180021c77  mov     ecx, [rax+24h]
0x180021c7a  mov     eax, [rax+28h]
0x180021c7d  mov     [rbp+310h+var_38C], ecx
0x180021c80  mov     rcx, r14; this
0x180021c83  mov     [rbp+310h+var_380], eax
0x180021c86  call    ?SetRenderingOrigin@GpGraphics@@QEAAXHH@Z; GpGraphics::SetRenderingOrigin(int,int)
0x180021c8b  lea     rcx, [rbp+310h+var_2D0]; this
0x180021c8f  call    ??0EpAlphaBlender@@QEAA@XZ; EpAlphaBlender::EpAlphaBlender(void)
0x180021c94  mov     rcx, [r14+88h]
0x180021c9b  lea     rax, [rbp+310h+var_60]
0x180021ca2  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x180021caa  xor     edx, edx
0x180021cac  mov     [rsp+410h+var_3A0], r15d
0x180021cb1  mov     r9d, 0E200Bh
0x180021cb7  mov     qword ptr [rbp+310h+var_348+8], rax
0x180021cbb  mov     r8d, edi
0x180021cbe  lea     rax, [rbp+310h+var_240]
0x180021cc5  mov     dword ptr [rbp+310h+var_338], edx
0x180021cc8  mov     qword ptr [rbp+310h+var_348], rax
0x180021ccc  lea     rax, [rbp+310h+var_348]
0x180021cd0  mov     [rsp+410h+var_3A8], rax
0x180021cd5  lea     rax, [rbp+310h+var_60]
0x180021cdc  mov     [rsp+410h+var_3B0], edx
0x180021ce0  mov     [rsp+410h+var_3B8], edx
0x180021ce4  mov     [rsp+410h+var_3C0], r15d
0x180021ce9  mov     [rsp+410h+var_3C8], rax
0x180021cee  mov     eax, [rcx+2Ch]
0x180021cf1  mov     [rsp+410h+var_3D0], rdx
0x180021cf6  mov     edx, r15d
0x180021cf9  mov     dword ptr [rsp+410h+var_3D8], eax
0x180021cfd  mov     eax, [rcx+20h]
0x180021d00  mov     dword ptr [rsp+410h+var_3E0], eax
0x180021d04  mov     eax, [rcx+1Ch]
0x180021d07  mov     dword ptr [rsp+410h+var_3E8], eax
0x180021d0b  mov     rax, [rcx+2A0h]
0x180021d12  lea     rcx, [rbp+310h+var_2D0]
0x180021d16  mov     [rsp+410h+var_3F0], rax
0x180021d1b  movdqu  xmmword ptr [rbp+310h+var_338+8], xmm0
0x180021d20  mov     [rbp+310h+var_320], r15d
0x180021d24  mov     [rbp+310h+var_31C], 2
0x180021d2b  call    ?BuildPipeline@EpAlphaBlender@@AEAAXW4EpScanType@@HHPEBVEpPaletteMap@@W4CompositingMode@@W4CompositingQuality@@IPEBUColorPalette@@PEAPEAXHHKAEAVBuilder@1@H@Z; EpAlphaBlender::BuildPipeline(EpScanType,int,int,EpPaletteMap const *,CompositingMode,CompositingQuality,uint,ColorPalette const *,void * *,int,int,ulong,EpAlphaBlender::Builder &,int)
0x180021d30  mov     rax, qword ptr [rbp+310h+var_348]
0x180021d34  movsxd  rcx, [rbp+310h+var_358]
0x180021d38  and     qword ptr [rax-8], 0
0x180021d3d  test    rcx, rcx
  ... truncated ...
```
