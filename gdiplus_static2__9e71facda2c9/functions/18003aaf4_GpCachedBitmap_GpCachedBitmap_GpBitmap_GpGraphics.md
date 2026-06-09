# GpCachedBitmap::GpCachedBitmap(GpBitmap *,GpGraphics *)

- ea: `0x18003aaf4`
- end: `0x18003b224`
- name: `??0GpCachedBitmap@@QEAA@PEAVGpBitmap@@PEAVGpGraphics@@@Z`
- size: `1840`
- prototype: `void __noreturn(GpCachedBitmap *__hidden this, struct GpBitmap *, struct GpGraphics *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e10c0`

## callees

- `0x180002918`
- `0x180002980`
- `0x180010bd0`
- `0x180015c44`
- `0x18001da50`
- `0x18001fb68`
- `0x180030880`
- `0x180032458`
- `0x180033f1c`
- `0x1800394c0`
- `0x18003aaf4`
- `0x18003c804`
- `0x18003c870`
- `0x18003c920`
- `0x180063cd8`
- `0x18008ae2c`
- `0x18008f0fc`
- `0x1800af164`
- `0x180105d40`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ac34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aeed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003aeed`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003b0f8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18003b0f8`

## pseudocode

```c
void __fastcall __noreturn GpCachedBitmap::GpCachedBitmap(
        GpCachedBitmap *this,
        struct GpBitmap *a2,
        struct GpGraphics *a3)
{
  unsigned __int64 v3; // r14
  __int64 v7; // rdx
  int v8; // r8d
  __int64 v9; // r12
  __int64 v10; // rax
  __int64 v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  void **v13; // r8
  HDC *v14; // r9
  int v15; // r12d
  __int64 v16; // rdi
  signed int v17; // edx
  int v18; // eax
  char *v19; // r13
  char *v20; // r10
  int v21; // r8d
  unsigned int v22; // ecx
  int v23; // r9d
  __int64 v24; // rcx
  int v25; // edx
  unsigned __int64 v26; // r14
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rax
  GpGraphics *v31; // r13
  unsigned __int64 v32; // r14
  __int64 v33; // rax
  int v34; // r13d
  int v35; // ebx
  __int64 v36; // rdx
  int v37; // eax
  struct EpScanRecord *ScanRecord; // rax
  struct GpBitmap *v39; // rcx
  int v40; // r15d
  int v41; // edi
  GpBitmap *v42; // rax
  GpBitmap *v43; // rax
  GpBitmap *v44; // rbx
  struct ColorPalette *v45; // [rsp+20h] [rbp-E0h]
  int *v46; // [rsp+28h] [rbp-D8h]
  int v47; // [rsp+30h] [rbp-D0h]
  int v48; // [rsp+50h] [rbp-B0h]
  _BYTE v49[12]; // [rsp+54h] [rbp-ACh] BYREF
  int v50; // [rsp+60h] [rbp-A0h]
  int v51; // [rsp+64h] [rbp-9Ch]
  int v52[2]; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  unsigned __int64 v57; // [rsp+90h] [rbp-70h]
  __int128 v58; // [rsp+98h] [rbp-68h] BYREF
  __int128 v59; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v60; // [rsp+B8h] [rbp-48h]
  GpGraphics *v61; // [rsp+C0h] [rbp-40h]
  struct _RTL_CRITICAL_SECTION *v62; // [rsp+C8h] [rbp-38h]
  struct GpBitmap *v63; // [rsp+D0h] [rbp-30h]
  __int128 v64; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v65; // [rsp+E8h] [rbp-18h]
  _BYTE v66[624]; // [rsp+100h] [rbp+0h] BYREF
  void *v67[2]; // [rsp+370h] [rbp+270h] BYREF
  __int128 v68; // [rsp+380h] [rbp+280h]
  __int64 v69; // [rsp+390h] [rbp+290h]

  v3 = 0;
  v63 = a2;
  *(_QWORD *)this = &GpCachedBitmap::`vftable';
  *((_DWORD *)this + 3) = -1;
  *((_DWORD *)this + 12) = 925707;
  *((_DWORD *)this + 13) = 925707;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 7) = 0;
  v61 = a3;
  if ( (unsigned int)GpGraphics::IsTSSession(a3) )
  {
    *(_QWORD *)&v49[4] = 0;
    *((_OWORD *)this + 1) = 0;
    *((_OWORD *)this + 2) = 0;
    v40 = 1;
    *((_QWORD *)this + 6) = 0;
    if ( CreateStreamOnHGlobal(0, 1, (LPSTREAM *)&v49[4]) < 0 || !*(_QWORD *)&v49[4] )
      goto LABEL_64;
    v41 = 3;
    if ( !(*(unsigned int (__fastcall **)(struct GpBitmap *, _QWORD, GUID *, _QWORD))(*(_QWORD *)a2 + 96LL))(
            a2,
            *(_QWORD *)&v49[4],
            &PngCodecClsID,
            0) )
    {
      *(_QWORD *)v52 = 0;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)&v49[4] + 40LL))(
             *(_QWORD *)&v49[4],
             0,
             0,
             0) >= 0 )
      {
        v42 = (GpBitmap *)GpMallocEx(1504, 0);
        if ( v42 )
        {
          v43 = GpBitmap::GpBitmap(v42, *(struct IStream **)&v49[4]);
          v44 = v43;
          if ( v43 )
          {
            if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v43 + 8LL))(v43) )
            {
              *((_QWORD *)this + 7) = v44;
              v41 = 0;
            }
            else
            {
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v44 + 56LL))(v44);
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v49[4] + 16LL))(*(_QWORD *)&v49[4]);
    if ( v41 )
LABEL_64:
      v40 = 0;
    *((_DWORD *)this + 2) = v40 != 0 ? 1833059121 : 1279869254;
    return;
  }
  v64 = 0;
  v65 = 0;
  if ( !v7
    || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7)
    || (unsigned int)GpBitmap::LockBits(a2, 0, 1, 925707, &v64) )
  {
    *((_DWORD *)this + 2) = 1279869254;
    return;
  }
  v8 = DWORD1(v64);
  *((_QWORD *)this + 2) = v64;
  v54 = 0;
  v53 = 0;
  v55 = 0;
  v56 = 0;
  DynArrayImpl::Grow(&v53, 32, (unsigned int)(4 * v8));
  v9 = *((_QWORD *)a3 + 5);
  v69 = 0;
  v10 = *((_QWORD *)a3 + 16);
  *(_OWORD *)v67 = 0;
  v68 = 0;
  v11 = *(_QWORD *)(v10 + 32);
  v58 = 0;
  v59 = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
  v62 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1584));
  if ( !(unsigned int)GpDevice::GetScanBuffers((GpDevice *)v11, *(_DWORD *)(v9 + 4), v13, v14, v45, v46, v47, v67) )
    goto LABEL_32;
  v15 = *(_DWORD *)(v9 + 12);
  if ( !v15 )
    goto LABEL_32;
  if ( v15 == 397319 || v15 == 0x10000000 || v15 == 196865 || v15 == 197634 || v15 == 1052676 || (v15 & 0x10000) != 0 )
    v15 = 139273;
  v16 = v53;
  v52[0] = ((v15 >> 8) & 0xF8u) >> 3;
  v17 = 0;
LABEL_10:
  v48 = v17;
  if ( v17 < *((_DWORD *)this + 5) )
  {
    v18 = 0;
    v19 = (char *)(v65 + v17 * DWORD2(v64));
    v20 = v19;
    v57 = (unsigned __int64)v19;
    v21 = 0;
    *(_DWORD *)v49 = 0;
    while ( 1 )
    {
      v51 = v21;
      if ( v21 >= *((_DWORD *)this + 4) )
      {
        if ( v18 )
        {
          *((_QWORD *)&v58 + 1) = v19;
          DWORD2(v59) = v17;
          v27 = (unsigned __int64)(v19 - v20) >> 2;
          *(_QWORD *)&v58 = v20;
          DWORD1(v59) = v21 - v27;
          LODWORD(v59) = v18;
          HIDWORD(v59) = v27;
          if ( (unsigned int)DynArrayImpl::AddMultiple(&v53, 32, 1, &v58) )
            goto LABEL_32;
          v16 = v53;
          v17 = v48;
          if ( *(_DWORD *)v49 == 1 )
            v28 = 4 * HIDWORD(v59) + 31LL + v3;
          else
            v28 = v52[0] * HIDWORD(v59) + 31LL + v3;
          v3 = v28 & 0xFFFFFFFFFFFFFFF8uLL;
        }
        ++v17;
        goto LABEL_10;
      }
      v22 = *(_DWORD *)v19 & 0xFF000000;
      if ( v22 == -16777216 )
        v23 = 2;
      else
        v23 = v22 != 0;
      v50 = v23;
      if ( v23 != v18 )
      {
        if ( v18 )
        {
          LODWORD(v59) = v18;
          *(_QWORD *)&v58 = v20;
          *((_QWORD *)&v58 + 1) = v19;
          *(_DWORD *)&v49[4] = v21 - ((unsigned __int64)(v19 - v20) >> 2);
          *(_QWORD *)((char *)&v59 + 4) = __PAIR64__(v17, *(unsigned int *)&v49[4]);
          v60 = (unsigned __int64)(v19 - v20) >> 2;
          HIDWORD(v59) = v60;
          if ( (unsigned int)DynArrayImpl::Grow(&v53, 32, 1) )
          {
            *((_DWORD *)this + 2) = 1279869254;
            LeaveCriticalSection(v12);
            v29 = v53;
            if ( v53 != v54 )
              goto LABEL_36;
            return;
          }
          v16 = v53;
          v21 = v51;
          v23 = v50;
          v24 = (unsigned int)(32 * v56);
          *(_QWORD *)(v24 + v53) = v57;
          *(_QWORD *)(v24 + v16 + 8) = v19;
          *(_QWORD *)(v24 + v16 + 16) = *(_QWORD *)v49;
          *(_DWORD *)(v24 + v16 + 24) = v48;
          v25 = v60;
          *(_DWORD *)(v24 + v16 + 28) = v60;
          ++v56;
          if ( *(_DWORD *)v49 == 1 )
            v26 = 4 * v25 + 31LL + v3;
          else
            v26 = v52[0] * v25 + 31LL + v3;
          v17 = v48;
          v3 = v26 & 0xFFFFFFFFFFFFFFF8uLL;
        }
        v18 = v23;
        v57 = (unsigned __int64)v19;
        *(_DWORD *)v49 = v23;
        v20 = v19;
      }
      v19 += 4;
      ++v21;
    }
  }
  if ( v3 > 0xFFFFFFFF )
  {
LABEL_32:
    *((_DWORD *)this + 2) = 1279869254;
    LeaveCriticalSection(v12);
    DynArray<PathBound>::~DynArray<PathBound>(&v53);
    return;
  }
  if ( (int)v3 + 8 >= (unsigned int)v3 && (v30 = GpMallocEx((unsigned int)(v3 + 8), 0), (v60 = v30) != 0) )
  {
    v31 = v61;
    v57 = (v30 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v32 = v57;
    v33 = *((_QWORD *)v61 + 17);
    *(_DWORD *)v49 = *(_DWORD *)(v33 + 36);
    *(_DWORD *)&v49[4] = *(_DWORD *)(v33 + 40);
    GpGraphics::SetRenderingOrigin(v61, 0, 0);
    EpAlphaBlender::EpAlphaBlender((EpAlphaBlender *)v66);
    EpAlphaBlender::Initialize(v66, 1, (unsigned int)v15, 925707, *((_QWORD *)v31 + 17), 0, v67);
    v34 = 0;
    if ( v56 > 0 )
    {
      v35 = v52[0];
      do
      {
        v36 = 32LL * (unsigned int)v34;
        *(_DWORD *)(v32 + 4) = *(_DWORD *)(v36 + v16 + 20);
        *(_DWORD *)(v32 + 8) = *(_DWORD *)(v36 + v16 + 24);
        v37 = *(_DWORD *)(v36 + v16 + 28);
        *(_DWORD *)(v32 + 16) = v37;
        *(_DWORD *)(v32 + 12) = v37;
        if ( *(_DWORD *)(v36 + v16 + 16) == 2 )
        {
          *(_DWORD *)v32 = 65537;
          EpAlphaBlender::Blend(
            (EpAlphaBlender *)v66,
            (void *)(v32 + 24),
            *(void **)(v36 + v16),
            *(_DWORD *)(v36 + v16 + 28),
            *(_DWORD *)(v36 + v16 + 20),
            *(_DWORD *)(v36 + v16 + 24),
            0);
          ScanRecord = EpScanRecord::NextScanRecord((EpScanRecord *)v32, v35);
        }
        else
        {
          *(_DWORD *)v32 = 0;
          memcpy_0((void *)(v32 + 24), *(const void **)(v36 + v16), 4LL * *(int *)(v36 + v16 + 28));
          ScanRecord = (struct EpScanRecord *)EpScanRecord::InternalCalculateNextScanRecord(
                                                v32,
                                                *(unsigned __int16 *)(v32 + 2),
                                                *(unsigned int *)(v32 + 12),
                                                *(unsigned int *)(v32 + 16),
                                                4);
        }
        ++v34;
        v32 = (unsigned __int64)ScanRecord;
      }
      while ( v34 < v56 );
      v12 = v62;
    }
    GpGraphics::SetRenderingOrigin(v61, *(int *)v49, *(int *)&v49[4]);
    v39 = v63;
    *((_QWORD *)this + 3) = v60;
    *((_QWORD *)this + 4) = v57;
    *((_QWORD *)this + 5) = v32;
    *((_DWORD *)this + 12) = v15;
    *((_DWORD *)this + 13) = 925707;
    GpBitmap::UnlockBits(v39, &v64);
    *((_DWORD *)this + 2) = 1833059121;
    EpAlphaBlender::~EpAlphaBlender((EpAlphaBlender *)v66);
  }
  else
  {
    *((_DWORD *)this + 2) = 1279869254;
  }
  LeaveCriticalSection(v12);
  if ( v16 != v54 )
  {
    v29 = v16;
LABEL_36:
    GpFree(v29);
  }
}

```

## disassembly

```asm
0x18003aaf4  mov     [rsp-8+arg_18], rbx
0x18003aaf9  push    rbp
0x18003aafa  push    rsi
0x18003aafb  push    rdi
0x18003aafc  push    r12
0x18003aafe  push    r13
0x18003ab00  push    r14
0x18003ab02  push    r15
0x18003ab04  lea     rbp, [rsp-2A0h]
0x18003ab0c  sub     rsp, 3A0h
0x18003ab13  mov     rax, cs:__security_cookie
0x18003ab1a  xor     rax, rsp
0x18003ab1d  mov     [rbp+2D0h+var_38], rax
0x18003ab24  xor     r14d, r14d
0x18003ab27  mov     [rbp+2D0h+var_300], rdx
0x18003ab2b  lea     rax, ??_7GpCachedBitmap@@6B@
0x18003ab32  mov     edi, 0E200Bh
0x18003ab37  mov     [rcx], rax
0x18003ab3a  mov     rbx, r8
0x18003ab3d  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x18003ab44  mov     rsi, rcx
0x18003ab47  mov     [rcx+30h], edi
0x18003ab4a  mov     r13, rdx
0x18003ab4d  mov     [rcx+34h], edi
0x18003ab50  mov     [rcx+18h], r14
0x18003ab54  mov     [rcx+10h], r14
0x18003ab58  mov     [rcx+38h], r14
0x18003ab5c  mov     rcx, r8; this
0x18003ab5f  mov     [rbp+2D0h+var_310], rbx
0x18003ab63  call    ?IsTSSession@GpGraphics@@IEBAHXZ
0x18003ab68  xorps   xmm0, xmm0
0x18003ab6b  test    eax, eax
0x18003ab6d  jnz     loc_18003B0D7
0x18003ab73  movups  [rbp+2D0h+var_2F8], xmm0
0x18003ab77  movups  [rbp+2D0h+var_2E8], xmm0
0x18003ab7b  test    rdx, rdx
0x18003ab7e  jz      loc_18003B218
0x18003ab84  mov     rax, [rdx]
0x18003ab87  mov     rcx, rdx
0x18003ab8a  mov     rax, [rax+8]
0x18003ab8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab93  test    eax, eax
0x18003ab95  jz      loc_18003B218
0x18003ab9b  lea     rax, [rbp+2D0h+var_2F8]
0x18003ab9f  mov     r9d, edi
0x18003aba2  lea     r15d, [r14+1]
0x18003aba6  mov     [rsp+3D0h+var_3B0], rax; struct ColorPalette *
0x18003abab  mov     r8d, r15d
0x18003abae  xor     edx, edx
0x18003abb0  mov     rcx, r13
0x18003abb3  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z
0x18003abb8  test    eax, eax
0x18003abba  jnz     loc_18003B218
0x18003abc0  mov     r8d, dword ptr [rbp+2D0h+var_2F8+4]
0x18003abc4  lea     edx, [r14+20h]
0x18003abc8  mov     eax, dword ptr [rbp+2D0h+var_2F8]
0x18003abcb  lea     rcx, [rsp+3D0h+var_360]
0x18003abd0  mov     [rsi+14h], r8d
0x18003abd4  shl     r8d, 2
0x18003abd8  mov     [rsi+10h], eax
0x18003abdb  mov     [rsp+3D0h+var_358], r14
0x18003abe0  mov     [rsp+3D0h+var_360], r14
0x18003abe5  mov     [rbp+2D0h+var_350], r14
0x18003abe9  mov     [rbp+2D0h+var_348], r14d
0x18003abed  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z
0x18003abf2  mov     r12, [rbx+28h]
0x18003abf6  xor     eax, eax
0x18003abf8  mov     [rbp+2D0h+var_40], rax
0x18003abff  xorps   xmm1, xmm1
0x18003ac02  mov     rax, [rbx+80h]
0x18003ac09  xorps   xmm0, xmm0
0x18003ac0c  movups  xmmword ptr [rbp+2D0h+var_60], xmm1
0x18003ac13  movups  [rbp+2D0h+var_50], xmm1
0x18003ac1a  mov     rdi, [rax+20h]
0x18003ac1e  movups  [rbp+2D0h+var_338], xmm0
0x18003ac22  movups  [rbp+2D0h+var_328], xmm0
0x18003ac26  lea     rbx, [rdi+630h]
0x18003ac2d  mov     rcx, rbx; lpCriticalSection
0x18003ac30  mov     [rbp+2D0h+var_308], rbx
0x18003ac34  call    cs:__imp_EnterCriticalSection
0x18003ac3b  nop     dword ptr [rax+rax+00h]
0x18003ac40  mov     edx, [r12+4]; int
0x18003ac45  lea     rax, [rbp+2D0h+var_60]
0x18003ac4c  mov     rcx, rdi; this
0x18003ac4f  mov     [rsp+3D0h+var_398], rax; void **
0x18003ac54  call    ?GetScanBuffers@GpDevice@@QEAAHHPEAPEAXPEAPEAUHDC__@@PEAUColorPalette@@PEAHHQEAPEAX@Z
0x18003ac59  test    eax, eax
0x18003ac5b  jz      loc_18003AE5C
0x18003ac61  mov     r12d, [r12+0Ch]
0x18003ac66  test    r12d, r12d
0x18003ac69  jz      loc_18003AE5C
0x18003ac6f  cmp     r12d, 61007h
0x18003ac76  jnz     loc_18003B1DF
0x18003ac7c  mov     r12d, 22009h
0x18003ac82  mov     rdi, [rsp+3D0h+var_360]
0x18003ac87  mov     eax, r12d
0x18003ac8a  sar     eax, 8
0x18003ac8d  and     eax, 0F8h
0x18003ac92  shr     eax, 3
0x18003ac95  mov     [rsp+3D0h+var_368], eax
0x18003ac99  xor     edx, edx
0x18003ac9b  mov     [rsp+3D0h+var_380], edx
0x18003ac9f  cmp     edx, [rsi+14h]
0x18003aca2  jge     loc_18003AE4E
0x18003aca8  mov     eax, dword ptr [rbp+2D0h+var_2F8+8]
0x18003acab  imul    eax, edx
0x18003acae  movsxd  r13, eax
0x18003acb1  xor     eax, eax
0x18003acb3  add     r13, qword ptr [rbp+2D0h+var_2E8]
0x18003acb7  mov     r10, r13
0x18003acba  mov     [rbp+2D0h+var_340], r13
0x18003acbe  xor     r8d, r8d
0x18003acc1  mov     [rsp+3D0h+var_37C], eax
0x18003acc5  mov     [rsp+3D0h+var_36C], r8d
0x18003acca  cmp     r8d, [rsi+10h]
0x18003acce  jge     loc_18003ADDF
0x18003acd4  mov     ecx, [r13+0]
0x18003acd8  and     ecx, 0FF000000h
0x18003acde  cmp     ecx, 0FF000000h
0x18003ace4  jnz     short loc_18003ACFF
0x18003ace6  mov     r9d, 2
0x18003acec  mov     [rsp+3D0h+var_370], r9d
0x18003acf1  cmp     r9d, eax
0x18003acf4  jnz     short loc_18003AD0A
0x18003acf6  add     r13, 4
0x18003acfa  add     r8d, r15d
0x18003acfd  jmp     short loc_18003ACC5
0x18003acff  xor     r9d, r9d
0x18003ad02  test    ecx, ecx
0x18003ad04  setnz   r9b
0x18003ad08  jmp     short loc_18003ACEC
0x18003ad0a  test    eax, eax
0x18003ad0c  jz      loc_18003ADBB
0x18003ad12  mov     dword ptr [rbp+2D0h+var_328], eax
0x18003ad15  mov     ecx, r8d
0x18003ad18  mov     dword ptr [rbp+2D0h+var_328+8], edx
0x18003ad1b  mov     rax, r13
0x18003ad1e  sub     rax, r10
0x18003ad21  mov     qword ptr [rbp+2D0h+var_338], r10
0x18003ad25  shr     rax, 2
0x18003ad29  mov     r8d, r15d
0x18003ad2c  sub     ecx, eax
0x18003ad2e  mov     qword ptr [rbp+2D0h+var_338+8], r13
0x18003ad32  mov     dword ptr [rsp+3D0h+ppstm], ecx
0x18003ad36  mov     edx, 20h ; ' '
0x18003ad3b  mov     dword ptr [rbp+2D0h+var_328+4], ecx
0x18003ad3e  lea     rcx, [rsp+3D0h+var_360]
0x18003ad43  mov     [rbp+2D0h+var_318], rax
0x18003ad47  mov     dword ptr [rbp+2D0h+var_328+0Ch], eax
0x18003ad4a  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z
0x18003ad4f  test    eax, eax
0x18003ad51  jnz     loc_18003AEE3
0x18003ad57  mov     ecx, [rbp+2D0h+var_348]
0x18003ad5a  mov     rdi, [rsp+3D0h+var_360]
0x18003ad5f  mov     rax, [rbp+2D0h+var_340]
0x18003ad63  mov     r8d, [rsp+3D0h+var_36C]
0x18003ad68  mov     r9d, [rsp+3D0h+var_370]
0x18003ad6d  shl     ecx, 5
0x18003ad70  mov     [rcx+rdi], rax
0x18003ad74  mov     eax, [rsp+3D0h+var_37C]
0x18003ad78  mov     [rcx+rdi+8], r13
0x18003ad7d  mov     [rcx+rdi+10h], eax
0x18003ad81  mov     edx, dword ptr [rsp+3D0h+ppstm]
0x18003ad85  mov     [rcx+rdi+14h], edx
0x18003ad89  mov     edx, [rsp+3D0h+var_380]
0x18003ad8d  mov     [rcx+rdi+18h], edx
0x18003ad91  mov     rdx, [rbp+2D0h+var_318]
0x18003ad95  mov     [rcx+rdi+1Ch], edx
0x18003ad99  add     [rbp+2D0h+var_348], r15d
0x18003ad9d  cmp     eax, r15d
0x18003ada0  jnz     short loc_18003ADCE
0x18003ada2  lea     eax, ds:0[rdx*4]
0x18003ada9  movsxd  rcx, eax
0x18003adac  add     rcx, 1Fh
0x18003adb0  add     r14, rcx
0x18003adb3  mov     edx, [rsp+3D0h+var_380]
0x18003adb7  and     r14, 0FFFFFFFFFFFFFFF8h
0x18003adbb  mov     eax, r9d
0x18003adbe  mov     [rbp+2D0h+var_340], r13
0x18003adc2  mov     [rsp+3D0h+var_37C], eax
0x18003adc6  mov     r10, r13
0x18003adc9  jmp     loc_18003ACF6
0x18003adce  imul    edx, [rsp+3D0h+var_368]
0x18003add3  movsxd  rax, edx
0x18003add6  add     rax, 1Fh
0x18003adda  add     r14, rax
0x18003addd  jmp     short loc_18003ADB3
0x18003addf  test    eax, eax
0x18003ade1  jz      short loc_18003AE46
0x18003ade3  mov     qword ptr [rbp+2D0h+var_338+8], r13
0x18003ade7  lea     r9, [rbp+2D0h+var_338]
0x18003adeb  sub     r13, r10
0x18003adee  mov     dword ptr [rbp+2D0h+var_328+8], edx
0x18003adf1  shr     r13, 2
0x18003adf5  lea     rcx, [rsp+3D0h+var_360]
0x18003adfa  sub     r8d, r13d
0x18003adfd  mov     qword ptr [rbp+2D0h+var_338], r10
0x18003ae01  mov     dword ptr [rbp+2D0h+var_328+4], r8d
0x18003ae05  mov     edx, 20h ; ' '
0x18003ae0a  mov     r8d, r15d
0x18003ae0d  mov     dword ptr [rbp+2D0h+var_328], eax
0x18003ae10  mov     dword ptr [rbp+2D0h+var_328+0Ch], r13d
0x18003ae14  call    ?AddMultiple@DynArrayImpl@@IEAA?AW4Status@@IIPEBX@Z
0x18003ae19  test    eax, eax
0x18003ae1b  jnz     short loc_18003AE5C
0x18003ae1d  mov     eax, dword ptr [rbp+2D0h+var_328+0Ch]
0x18003ae20  mov     rdi, [rsp+3D0h+var_360]
0x18003ae25  mov     edx, [rsp+3D0h+var_380]
0x18003ae29  cmp     [rsp+3D0h+var_37C], r15d
0x18003ae2e  jz      loc_18003AED1
0x18003ae34  imul    eax, [rsp+3D0h+var_368]
0x18003ae39  cdqe
0x18003ae3b  add     rax, 1Fh
0x18003ae3f  add     r14, rax
0x18003ae42  and     r14, 0FFFFFFFFFFFFFFF8h
0x18003ae46  add     edx, r15d
0x18003ae49  jmp     loc_18003AC9B
0x18003ae4e  mov     eax, 0FFFFFFFFh
0x18003ae53  cmp     r14, rax
0x18003ae56  jbe     loc_18003B0B5
0x18003ae5c  mov     rcx, rbx; lpCriticalSection
0x18003ae5f  mov     dword ptr [rsi+8], 4C494146h
0x18003ae66  call    cs:__imp_LeaveCriticalSection
0x18003ae6d  nop     dword ptr [rax+rax+00h]
0x18003ae72  lea     rcx, [rsp+3D0h+var_360]
0x18003ae77  call    ??1?$DynArray@UPathBound@@@@QEAA@XZ
0x18003ae7c  jmp     short loc_18003AEA3
0x18003ae7e  mov     dword ptr [rsi+8], 4C494146h
0x18003ae85  mov     rcx, rbx; lpCriticalSection
0x18003ae88  call    cs:__imp_LeaveCriticalSection
0x18003ae8f  nop     dword ptr [rax+rax+00h]
0x18003ae94  cmp     rdi, [rsp+3D0h+var_358]
0x18003ae99  jz      short loc_18003AEA3
0x18003ae9b  mov     rcx, rdi
0x18003ae9e  call    GpFree
0x18003aea3  mov     rax, rsi
0x18003aea6  mov     rcx, [rbp+2D0h+var_38]
0x18003aead  xor     rcx, rsp; StackCookie
0x18003aeb0  call    __security_check_cookie
0x18003aeb5  mov     rbx, [rsp+3D0h+arg_18]
0x18003aebd  add     rsp, 3A0h
0x18003aec4  pop     r15
0x18003aec6  pop     r14
0x18003aec8  pop     r13
0x18003aeca  pop     r12
0x18003aecc  pop     rdi
0x18003aecd  pop     rsi
0x18003aece  pop     rbp
0x18003aecf  retn
0x18003aed1  shl     eax, 2
0x18003aed4  movsxd  rcx, eax
0x18003aed7  add     rcx, 1Fh
0x18003aedb  add     r14, rcx
0x18003aede  jmp     loc_18003AE42
0x18003aee3  mov     rcx, rbx; lpCriticalSection
0x18003aee6  mov     dword ptr [rsi+8], 4C494146h
0x18003aeed  call    cs:__imp_LeaveCriticalSection
0x18003aef4  nop     dword ptr [rax+rax+00h]
0x18003aef9  mov     rcx, [rsp+3D0h+var_360]
0x18003aefe  cmp     rcx, [rsp+3D0h+var_358]
0x18003af03  jnz     short loc_18003AE9E
0x18003af05  jmp     short loc_18003AEA3
0x18003af07  mov     ecx, eax
0x18003af09  xor     edx, edx
0x18003af0b  call    GpMallocEx
0x18003af10  mov     [rbp+2D0h+var_318], rax
0x18003af14  test    rax, rax
0x18003af17  jz      loc_18003AE7E
0x18003af1d  mov     r13, [rbp+2D0h+var_310]
0x18003af21  add     rax, 7
0x18003af25  and     rax, 0FFFFFFFFFFFFFFF8h
0x18003af29  xor     r8d, r8d; int
0x18003af2c  mov     [rbp+2D0h+var_340], rax
0x18003af30  mov     r14, rax
0x18003af33  xor     edx, edx; int
0x18003af35  mov     rax, [r13+88h]
0x18003af3c  mov     ecx, [rax+24h]
0x18003af3f  mov     eax, [rax+28h]
0x18003af42  mov     [rsp+3D0h+var_37C], ecx
0x18003af46  mov     rcx, r13; this
0x18003af49  mov     dword ptr [rsp+3D0h+ppstm], eax
0x18003af4d  call    ?SetRenderingOrigin@GpGraphics@@QEAAXHH@Z
0x18003af52  lea     rcx, [rbp+2D0h+var_2D0]; this
0x18003af56  call    ??0EpAlphaBlender@@QEAA@XZ
0x18003af5b  xor     ecx, ecx
0x18003af5d  lea     rax, [rbp+2D0h+var_60]
0x18003af64  mov     [rsp+3D0h+var_388], ecx
0x18003af68  mov     r9d, 0E200Bh
0x18003af6e  mov     [rsp+3D0h+var_390], ecx
0x18003af72  mov     r8d, r12d
0x18003af75  mov     [rsp+3D0h+var_3A0], rax
0x18003af7a  mov     edx, r15d
0x18003af7d  mov     rax, [r13+88h]
0x18003af84  mov     qword ptr [rsp+3D0h+var_3A8], rcx
0x18003af89  lea     rcx, [rbp+2D0h+var_2D0]
0x18003af8d  mov     [rsp+3D0h+var_3B0], rax
0x18003af92  call    ?Initialize@EpAlphaBlender@@QEAAXW4EpScanType@@HHPEBVDpContext@@PEBUColorPalette@@PEAPEAXHHK@Z
0x18003af97  xor     r13d, r13d
0x18003af9a  cmp     [rbp+2D0h+var_348], r13d
0x18003af9e  jle     loc_18003B029
  ... truncated ...
```
