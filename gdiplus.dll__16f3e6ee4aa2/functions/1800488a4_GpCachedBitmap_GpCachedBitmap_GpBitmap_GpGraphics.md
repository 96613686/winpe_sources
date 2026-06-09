# GpCachedBitmap::GpCachedBitmap(GpBitmap *,GpGraphics *)

- ea: `0x1800488a4`
- end: `0x180048fbd`
- name: `??0GpCachedBitmap@@QEAA@PEAVGpBitmap@@PEAVGpGraphics@@@Z`
- size: `1817`
- prototype: `void __fastcall __noreturn(GpCachedBitmap *__hidden this, struct GpBitmap *, struct GpGraphics *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dadb0`

## callees

- `0x1800067bc`
- `0x18000792c`
- `0x180008060`
- `0x18001ec80`
- `0x180023ca4`
- `0x18002b670`
- `0x18002d6a0`
- `0x18003e8d0`
- `0x180040424`
- `0x180041e78`
- `0x180047260`
- `0x1800488a4`
- `0x18004a504`
- `0x18004a570`
- `0x18004a620`
- `0x18009bfe4`
- `0x1800b0378`
- `0x1800fe680`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800489ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800489ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c93`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180048e9b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180048e9b`

## pseudocode

```c
void __fastcall __noreturn GpCachedBitmap::GpCachedBitmap(
        GpCachedBitmap *this,
        struct GpBitmap *a2,
        struct GpGraphics *a3)
{
  unsigned __int64 v3; // r14
  int v6; // edi
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
  GpBitmap *v41; // rax
  GpBitmap *v42; // rax
  GpBitmap *v43; // rbx
  struct ColorPalette *v44; // [rsp+20h] [rbp-E0h]
  int *v45; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+30h] [rbp-D0h]
  int v47; // [rsp+50h] [rbp-B0h]
  _BYTE v48[12]; // [rsp+54h] [rbp-ACh] BYREF
  int v49; // [rsp+60h] [rbp-A0h]
  int v50; // [rsp+64h] [rbp-9Ch]
  int v51[2]; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  unsigned __int64 v56; // [rsp+90h] [rbp-70h]
  __int128 v57; // [rsp+98h] [rbp-68h] BYREF
  __int128 v58; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v59; // [rsp+B8h] [rbp-48h]
  GpGraphics *v60; // [rsp+C0h] [rbp-40h]
  struct _RTL_CRITICAL_SECTION *v61; // [rsp+C8h] [rbp-38h]
  struct GpBitmap *v62; // [rsp+D0h] [rbp-30h]
  __int128 v63; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v64; // [rsp+E8h] [rbp-18h]
  _BYTE v65[624]; // [rsp+100h] [rbp+0h] BYREF
  void *v66[2]; // [rsp+370h] [rbp+270h] BYREF
  __int128 v67; // [rsp+380h] [rbp+280h]
  __int64 v68; // [rsp+390h] [rbp+290h]

  v3 = 0;
  v62 = a2;
  *(_QWORD *)this = &GpCachedBitmap::`vftable';
  *((_DWORD *)this + 3) = -1;
  *((_DWORD *)this + 12) = 925707;
  v6 = 3;
  *((_DWORD *)this + 13) = 925707;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 7) = 0;
  v60 = a3;
  if ( *((_DWORD *)a3 + 27) != 3 && *((_QWORD *)a3 + 7) )
  {
    *(_QWORD *)&v48[4] = 0;
    *((_OWORD *)this + 1) = 0;
    *((_OWORD *)this + 2) = 0;
    v40 = 1;
    *((_QWORD *)this + 6) = 0;
    if ( CreateStreamOnHGlobal(0, 1, (LPSTREAM *)&v48[4]) < 0 || !*(_QWORD *)&v48[4] )
      goto LABEL_65;
    if ( !(*(unsigned int (__fastcall **)(struct GpBitmap *, _QWORD, GUID *, _QWORD))(*(_QWORD *)a2 + 96LL))(
            a2,
            *(_QWORD *)&v48[4],
            &PngCodecClsID,
            0) )
    {
      *(_QWORD *)v51 = 0;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)&v48[4] + 40LL))(
             *(_QWORD *)&v48[4],
             0,
             0,
             0) >= 0 )
      {
        v41 = (GpBitmap *)GpMallocEx(1504, 0);
        if ( v41 )
        {
          v42 = GpBitmap::GpBitmap(v41, *(struct IStream **)&v48[4]);
          v43 = v42;
          if ( v42 )
          {
            if ( (*(unsigned int (__fastcall **)(GpBitmap *))(*(_QWORD *)v42 + 8LL))(v42) )
            {
              *((_QWORD *)this + 7) = v43;
              v6 = 0;
            }
            else
            {
              (*(void (__fastcall **)(GpBitmap *))(*(_QWORD *)v43 + 56LL))(v43);
            }
          }
        }
      }
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v48[4] + 16LL))(*(_QWORD *)&v48[4]);
    if ( v6 )
LABEL_65:
      v40 = 0;
    *((_DWORD *)this + 2) = v40 != 0 ? 1833059121 : 1279869254;
    return;
  }
  v63 = 0;
  v64 = 0;
  if ( !a2
    || !(*(unsigned int (__fastcall **)(struct GpBitmap *))(*(_QWORD *)a2 + 8LL))(a2)
    || (unsigned int)GpBitmap::LockBits(a2, 0, 1, 925707, &v63) )
  {
    *((_DWORD *)this + 2) = 1279869254;
    return;
  }
  v8 = DWORD1(v63);
  *((_QWORD *)this + 2) = v63;
  v53 = 0;
  v52 = 0;
  v54 = 0;
  v55 = 0;
  DynArrayImpl::Grow(&v52, 32, (unsigned int)(4 * v8));
  v9 = *((_QWORD *)a3 + 5);
  v68 = 0;
  v10 = *((_QWORD *)a3 + 16);
  *(_OWORD *)v66 = 0;
  v67 = 0;
  v11 = *(_QWORD *)(v10 + 32);
  v57 = 0;
  v58 = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
  v61 = (struct _RTL_CRITICAL_SECTION *)(v11 + 1584);
  EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1584));
  if ( !(unsigned int)GpDevice::GetScanBuffers((GpDevice *)v11, *(_DWORD *)(v9 + 4), v13, v14, v44, v45, v46, v66) )
    goto LABEL_33;
  v15 = *(_DWORD *)(v9 + 12);
  if ( !v15 )
    goto LABEL_33;
  if ( v15 == 397319 || v15 == 0x10000000 || v15 == 196865 || v15 == 197634 || v15 == 1052676 || (v15 & 0x10000) != 0 )
    v15 = 139273;
  v16 = v52;
  v51[0] = ((v15 >> 8) & 0xF8u) >> 3;
  v17 = 0;
LABEL_11:
  v47 = v17;
  if ( v17 < *((_DWORD *)this + 5) )
  {
    v18 = 0;
    v19 = (char *)(v64 + v17 * DWORD2(v63));
    v20 = v19;
    v56 = (unsigned __int64)v19;
    v21 = 0;
    *(_DWORD *)v48 = 0;
    while ( 1 )
    {
      v50 = v21;
      if ( v21 >= *((_DWORD *)this + 4) )
      {
        if ( v18 )
        {
          *((_QWORD *)&v57 + 1) = v19;
          DWORD2(v58) = v17;
          v27 = (unsigned __int64)(v19 - v20) >> 2;
          *(_QWORD *)&v57 = v20;
          DWORD1(v58) = v21 - v27;
          LODWORD(v58) = v18;
          HIDWORD(v58) = v27;
          if ( (unsigned int)DynArrayImpl::AddMultiple(&v52, 32, 1, &v57) )
            goto LABEL_33;
          v16 = v52;
          v17 = v47;
          if ( *(_DWORD *)v48 == 1 )
            v28 = 4 * HIDWORD(v58) + 31LL + v3;
          else
            v28 = v51[0] * HIDWORD(v58) + 31LL + v3;
          v3 = v28 & 0xFFFFFFFFFFFFFFF8uLL;
        }
        ++v17;
        goto LABEL_11;
      }
      v22 = *(_DWORD *)v19 & 0xFF000000;
      if ( v22 == -16777216 )
        v23 = 2;
      else
        v23 = v22 != 0;
      v49 = v23;
      if ( v23 != v18 )
      {
        if ( v18 )
        {
          LODWORD(v58) = v18;
          *(_QWORD *)&v57 = v20;
          *((_QWORD *)&v57 + 1) = v19;
          *(_DWORD *)&v48[4] = v21 - ((unsigned __int64)(v19 - v20) >> 2);
          *(_QWORD *)((char *)&v58 + 4) = __PAIR64__(v17, *(unsigned int *)&v48[4]);
          v59 = (unsigned __int64)(v19 - v20) >> 2;
          HIDWORD(v58) = v59;
          if ( (unsigned int)DynArrayImpl::Grow(&v52, 32, 1) )
          {
            *((_DWORD *)this + 2) = 1279869254;
            LeaveCriticalSection(v12);
            v29 = v52;
            if ( v52 != v53 )
              goto LABEL_37;
            return;
          }
          v16 = v52;
          v21 = v50;
          v23 = v49;
          v24 = (unsigned int)(32 * v55);
          *(_QWORD *)(v24 + v52) = v56;
          *(_QWORD *)(v24 + v16 + 8) = v19;
          *(_QWORD *)(v24 + v16 + 16) = *(_QWORD *)v48;
          *(_DWORD *)(v24 + v16 + 24) = v47;
          v25 = v59;
          *(_DWORD *)(v24 + v16 + 28) = v59;
          ++v55;
          if ( *(_DWORD *)v48 == 1 )
            v26 = 4 * v25 + 31LL + v3;
          else
            v26 = v51[0] * v25 + 31LL + v3;
          v17 = v47;
          v3 = v26 & 0xFFFFFFFFFFFFFFF8uLL;
        }
        v18 = v23;
        v56 = (unsigned __int64)v19;
        *(_DWORD *)v48 = v23;
        v20 = v19;
      }
      v19 += 4;
      ++v21;
    }
  }
  if ( v3 > 0xFFFFFFFF )
  {
LABEL_33:
    *((_DWORD *)this + 2) = 1279869254;
    LeaveCriticalSection(v12);
    DynArray<PathBound>::~DynArray<PathBound>(&v52);
    return;
  }
  if ( (int)v3 + 8 >= (unsigned int)v3 && (v30 = GpMallocEx((unsigned int)(v3 + 8), 0), (v59 = v30) != 0) )
  {
    v31 = v60;
    v56 = (v30 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v32 = v56;
    v33 = *((_QWORD *)v60 + 17);
    *(_DWORD *)v48 = *(_DWORD *)(v33 + 36);
    *(_DWORD *)&v48[4] = *(_DWORD *)(v33 + 40);
    GpGraphics::SetRenderingOrigin(v60, 0, 0);
    EpAlphaBlender::EpAlphaBlender((EpAlphaBlender *)v65);
    EpAlphaBlender::Initialize(v65, 1, (unsigned int)v15, 925707, *((_QWORD *)v31 + 17), 0, v66);
    v34 = 0;
    if ( v55 > 0 )
    {
      v35 = v51[0];
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
            (EpAlphaBlender *)v65,
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
      while ( v34 < v55 );
      v12 = v61;
    }
    GpGraphics::SetRenderingOrigin(v60, *(int *)v48, *(int *)&v48[4]);
    v39 = v62;
    *((_QWORD *)this + 3) = v59;
    *((_QWORD *)this + 4) = v56;
    *((_QWORD *)this + 5) = v32;
    *((_DWORD *)this + 12) = v15;
    *((_DWORD *)this + 13) = 925707;
    GpBitmap::UnlockBits(v39, &v63);
    *((_DWORD *)this + 2) = 1833059121;
    EpAlphaBlender::~EpAlphaBlender((EpAlphaBlender *)v65);
  }
  else
  {
    *((_DWORD *)this + 2) = 1279869254;
  }
  LeaveCriticalSection(v12);
  if ( v16 != v53 )
  {
    v29 = v16;
LABEL_37:
    GpFree(v29);
  }
}

```

## disassembly

```asm
0x1800488a4  mov     [rsp-8+arg_18], rbx
0x1800488a9  push    rbp
0x1800488aa  push    rsi
0x1800488ab  push    rdi
0x1800488ac  push    r12
0x1800488ae  push    r13
0x1800488b0  push    r14
0x1800488b2  push    r15
0x1800488b4  lea     rbp, [rsp-2A0h]
0x1800488bc  sub     rsp, 3A0h
0x1800488c3  mov     rax, cs:__security_cookie
0x1800488ca  xor     rax, rsp
0x1800488cd  mov     [rbp+2D0h+var_38], rax
0x1800488d4  xor     r14d, r14d
0x1800488d7  mov     [rbp+2D0h+var_300], rdx
0x1800488db  mov     r15d, 0E200Bh
0x1800488e1  lea     rax, ??_7GpCachedBitmap@@6B@
0x1800488e8  mov     [rcx], rax
0x1800488eb  mov     rbx, r8
0x1800488ee  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x1800488f5  mov     r13, rdx
0x1800488f8  mov     [rcx+30h], r15d
0x1800488fc  lea     edi, [r14+3]
0x180048900  mov     [rcx+34h], r15d
0x180048904  mov     rsi, rcx
0x180048907  mov     [rcx+18h], r14
0x18004890b  mov     [rcx+10h], r14
0x18004890f  mov     [rcx+38h], r14
0x180048913  mov     [rbp+2D0h+var_310], rbx
0x180048917  cmp     [r8+6Ch], edi
0x18004891b  jz      short loc_180048927
0x18004891d  cmp     [r8+38h], r14
0x180048921  jnz     loc_180048E77
0x180048927  xorps   xmm0, xmm0
0x18004892a  movups  [rbp+2D0h+var_2F8], xmm0
0x18004892e  movups  [rbp+2D0h+var_2E8], xmm0
0x180048932  test    r13, r13
0x180048935  jz      loc_180048FB1
0x18004893b  mov     rax, [rdx]
0x18004893e  mov     rcx, r13
0x180048941  mov     rax, [rax+8]
0x180048945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004894a  test    eax, eax
0x18004894c  jz      loc_180048FB1
0x180048952  mov     r9d, r15d
0x180048955  lea     rax, [rbp+2D0h+var_2F8]
0x180048959  mov     r15d, 1
0x18004895f  mov     [rsp+3D0h+var_3B0], rax; struct ColorPalette *
0x180048964  mov     r8d, r15d
0x180048967  xor     edx, edx
0x180048969  mov     rcx, r13
0x18004896c  call    ?LockBits@GpBitmap@@QEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z
0x180048971  test    eax, eax
0x180048973  jnz     loc_180048FB1
0x180048979  mov     r8d, dword ptr [rbp+2D0h+var_2F8+4]
0x18004897d  lea     edx, [r15+1Fh]
0x180048981  mov     eax, dword ptr [rbp+2D0h+var_2F8]
0x180048984  lea     rcx, [rsp+3D0h+var_360]
0x180048989  mov     [rsi+14h], r8d
0x18004898d  shl     r8d, 2
0x180048991  mov     [rsi+10h], eax
0x180048994  mov     [rsp+3D0h+var_358], r14
0x180048999  mov     [rsp+3D0h+var_360], r14
0x18004899e  mov     [rbp+2D0h+var_350], r14
0x1800489a2  mov     [rbp+2D0h+var_348], r14d
0x1800489a6  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z
0x1800489ab  mov     r12, [rbx+28h]
0x1800489af  xor     eax, eax
0x1800489b1  mov     [rbp+2D0h+var_40], rax
0x1800489b8  xorps   xmm1, xmm1
0x1800489bb  mov     rax, [rbx+80h]
0x1800489c2  xorps   xmm0, xmm0
0x1800489c5  movups  xmmword ptr [rbp+2D0h+var_60], xmm1
0x1800489cc  movups  [rbp+2D0h+var_50], xmm1
0x1800489d3  mov     rdi, [rax+20h]
0x1800489d7  movups  [rbp+2D0h+var_338], xmm0
0x1800489db  movups  [rbp+2D0h+var_328], xmm0
0x1800489df  lea     rbx, [rdi+630h]
0x1800489e6  mov     rcx, rbx; lpCriticalSection
0x1800489e9  mov     [rbp+2D0h+var_308], rbx
0x1800489ed  call    cs:__imp_EnterCriticalSection
0x1800489f3  mov     edx, [r12+4]; int
0x1800489f8  lea     rax, [rbp+2D0h+var_60]
0x1800489ff  mov     rcx, rdi; this
0x180048a02  mov     [rsp+3D0h+var_398], rax; void **
0x180048a07  call    ?GetScanBuffers@GpDevice@@QEAAHHPEAPEAXPEAPEAUHDC__@@PEAUColorPalette@@PEAHHQEAPEAX@Z
0x180048a0c  test    eax, eax
0x180048a0e  jz      loc_180048C0F
0x180048a14  mov     r12d, [r12+0Ch]
0x180048a19  test    r12d, r12d
0x180048a1c  jz      loc_180048C0F
0x180048a22  cmp     r12d, 61007h
0x180048a29  jnz     loc_180048F78
0x180048a2f  mov     r12d, 22009h
0x180048a35  mov     rdi, [rsp+3D0h+var_360]
0x180048a3a  mov     eax, r12d
0x180048a3d  sar     eax, 8
0x180048a40  and     eax, 0F8h
0x180048a45  shr     eax, 3
0x180048a48  mov     [rsp+3D0h+var_368], eax
0x180048a4c  xor     edx, edx
0x180048a4e  mov     [rsp+3D0h+var_380], edx
0x180048a52  cmp     edx, [rsi+14h]
0x180048a55  jge     loc_180048C01
0x180048a5b  mov     eax, dword ptr [rbp+2D0h+var_2F8+8]
0x180048a5e  imul    eax, edx
0x180048a61  movsxd  r13, eax
0x180048a64  xor     eax, eax
0x180048a66  add     r13, qword ptr [rbp+2D0h+var_2E8]
0x180048a6a  mov     r10, r13
0x180048a6d  mov     [rbp+2D0h+var_340], r13
0x180048a71  xor     r8d, r8d
0x180048a74  mov     [rsp+3D0h+var_37C], eax
0x180048a78  mov     [rsp+3D0h+var_36C], r8d
0x180048a7d  cmp     r8d, [rsi+10h]
0x180048a81  jge     loc_180048B92
0x180048a87  mov     ecx, [r13+0]
0x180048a8b  and     ecx, 0FF000000h
0x180048a91  cmp     ecx, 0FF000000h
0x180048a97  jnz     short loc_180048AB2
0x180048a99  mov     r9d, 2
0x180048a9f  mov     [rsp+3D0h+var_370], r9d
0x180048aa4  cmp     r9d, eax
0x180048aa7  jnz     short loc_180048ABD
0x180048aa9  add     r13, 4
0x180048aad  add     r8d, r15d
0x180048ab0  jmp     short loc_180048A78
0x180048ab2  xor     r9d, r9d
0x180048ab5  test    ecx, ecx
0x180048ab7  setnz   r9b
0x180048abb  jmp     short loc_180048A9F
0x180048abd  test    eax, eax
0x180048abf  jz      loc_180048B6E
0x180048ac5  mov     dword ptr [rbp+2D0h+var_328], eax
0x180048ac8  mov     ecx, r8d
0x180048acb  mov     dword ptr [rbp+2D0h+var_328+8], edx
0x180048ace  mov     rax, r13
0x180048ad1  sub     rax, r10
0x180048ad4  mov     qword ptr [rbp+2D0h+var_338], r10
0x180048ad8  shr     rax, 2
0x180048adc  mov     r8d, r15d
0x180048adf  sub     ecx, eax
0x180048ae1  mov     qword ptr [rbp+2D0h+var_338+8], r13
0x180048ae5  mov     dword ptr [rsp+3D0h+ppstm], ecx
0x180048ae9  mov     edx, 20h ; ' '
0x180048aee  mov     dword ptr [rbp+2D0h+var_328+4], ecx
0x180048af1  lea     rcx, [rsp+3D0h+var_360]
0x180048af6  mov     [rbp+2D0h+var_318], rax
0x180048afa  mov     dword ptr [rbp+2D0h+var_328+0Ch], eax
0x180048afd  call    ?Grow@DynArrayImpl@@IEAA?AW4Status@@IIH@Z
0x180048b02  test    eax, eax
0x180048b04  jnz     loc_180048C89
0x180048b0a  mov     ecx, [rbp+2D0h+var_348]
0x180048b0d  mov     rdi, [rsp+3D0h+var_360]
0x180048b12  mov     rax, [rbp+2D0h+var_340]
0x180048b16  mov     r8d, [rsp+3D0h+var_36C]
0x180048b1b  mov     r9d, [rsp+3D0h+var_370]
0x180048b20  shl     ecx, 5
0x180048b23  mov     [rcx+rdi], rax
0x180048b27  mov     eax, [rsp+3D0h+var_37C]
0x180048b2b  mov     [rcx+rdi+8], r13
0x180048b30  mov     [rcx+rdi+10h], eax
0x180048b34  mov     edx, dword ptr [rsp+3D0h+ppstm]
0x180048b38  mov     [rcx+rdi+14h], edx
0x180048b3c  mov     edx, [rsp+3D0h+var_380]
0x180048b40  mov     [rcx+rdi+18h], edx
0x180048b44  mov     rdx, [rbp+2D0h+var_318]
0x180048b48  mov     [rcx+rdi+1Ch], edx
0x180048b4c  add     [rbp+2D0h+var_348], r15d
0x180048b50  cmp     eax, r15d
0x180048b53  jnz     short loc_180048B81
0x180048b55  lea     eax, ds:0[rdx*4]
0x180048b5c  movsxd  rcx, eax
0x180048b5f  add     rcx, 1Fh
0x180048b63  add     r14, rcx
0x180048b66  mov     edx, [rsp+3D0h+var_380]
0x180048b6a  and     r14, 0FFFFFFFFFFFFFFF8h
0x180048b6e  mov     eax, r9d
0x180048b71  mov     [rbp+2D0h+var_340], r13
0x180048b75  mov     [rsp+3D0h+var_37C], eax
0x180048b79  mov     r10, r13
0x180048b7c  jmp     loc_180048AA9
0x180048b81  imul    edx, [rsp+3D0h+var_368]
0x180048b86  movsxd  rax, edx
0x180048b89  add     rax, 1Fh
0x180048b8d  add     r14, rax
0x180048b90  jmp     short loc_180048B66
0x180048b92  test    eax, eax
0x180048b94  jz      short loc_180048BF9
0x180048b96  mov     qword ptr [rbp+2D0h+var_338+8], r13
0x180048b9a  lea     r9, [rbp+2D0h+var_338]
0x180048b9e  sub     r13, r10
0x180048ba1  mov     dword ptr [rbp+2D0h+var_328+8], edx
0x180048ba4  shr     r13, 2
0x180048ba8  lea     rcx, [rsp+3D0h+var_360]
0x180048bad  sub     r8d, r13d
0x180048bb0  mov     qword ptr [rbp+2D0h+var_338], r10
0x180048bb4  mov     dword ptr [rbp+2D0h+var_328+4], r8d
0x180048bb8  mov     edx, 20h ; ' '
0x180048bbd  mov     r8d, r15d
0x180048bc0  mov     dword ptr [rbp+2D0h+var_328], eax
0x180048bc3  mov     dword ptr [rbp+2D0h+var_328+0Ch], r13d
0x180048bc7  call    ?AddMultiple@DynArrayImpl@@IEAA?AW4Status@@IIPEBX@Z
0x180048bcc  test    eax, eax
0x180048bce  jnz     short loc_180048C0F
0x180048bd0  mov     eax, dword ptr [rbp+2D0h+var_328+0Ch]
0x180048bd3  mov     rdi, [rsp+3D0h+var_360]
0x180048bd8  mov     edx, [rsp+3D0h+var_380]
0x180048bdc  cmp     [rsp+3D0h+var_37C], r15d
0x180048be1  jz      loc_180048C77
0x180048be7  imul    eax, [rsp+3D0h+var_368]
0x180048bec  cdqe
0x180048bee  add     rax, 1Fh
0x180048bf2  add     r14, rax
0x180048bf5  and     r14, 0FFFFFFFFFFFFFFF8h
0x180048bf9  add     edx, r15d
0x180048bfc  jmp     loc_180048A4E
0x180048c01  mov     eax, 0FFFFFFFFh
0x180048c06  cmp     r14, rax
0x180048c09  jbe     loc_180048E55
0x180048c0f  mov     rcx, rbx; lpCriticalSection
0x180048c12  mov     dword ptr [rsi+8], 4C494146h
0x180048c19  call    cs:__imp_LeaveCriticalSection
0x180048c1f  lea     rcx, [rsp+3D0h+var_360]
0x180048c24  call    ??1?$DynArray@UPathBound@@@@QEAA@XZ
0x180048c29  jmp     short loc_180048C4A
0x180048c2b  mov     dword ptr [rsi+8], 4C494146h
0x180048c32  mov     rcx, rbx; lpCriticalSection
0x180048c35  call    cs:__imp_LeaveCriticalSection
0x180048c3b  cmp     rdi, [rsp+3D0h+var_358]
0x180048c40  jz      short loc_180048C4A
0x180048c42  mov     rcx, rdi
0x180048c45  call    GpFree
0x180048c4a  mov     rax, rsi
0x180048c4d  mov     rcx, [rbp+2D0h+var_38]
0x180048c54  xor     rcx, rsp; StackCookie
0x180048c57  call    __security_check_cookie
0x180048c5c  mov     rbx, [rsp+3D0h+arg_18]
0x180048c64  add     rsp, 3A0h
0x180048c6b  pop     r15
0x180048c6d  pop     r14
0x180048c6f  pop     r13
0x180048c71  pop     r12
0x180048c73  pop     rdi
0x180048c74  pop     rsi
0x180048c75  pop     rbp
0x180048c76  retn
0x180048c77  shl     eax, 2
0x180048c7a  movsxd  rcx, eax
0x180048c7d  add     rcx, 1Fh
0x180048c81  add     r14, rcx
0x180048c84  jmp     loc_180048BF5
0x180048c89  mov     rcx, rbx; lpCriticalSection
0x180048c8c  mov     dword ptr [rsi+8], 4C494146h
0x180048c93  call    cs:__imp_LeaveCriticalSection
0x180048c99  mov     rcx, [rsp+3D0h+var_360]
0x180048c9e  cmp     rcx, [rsp+3D0h+var_358]
0x180048ca3  jnz     short loc_180048C45
0x180048ca5  jmp     short loc_180048C4A
0x180048ca7  mov     ecx, eax
0x180048ca9  xor     edx, edx
0x180048cab  call    GpMallocEx
0x180048cb0  mov     [rbp+2D0h+var_318], rax
0x180048cb4  test    rax, rax
0x180048cb7  jz      loc_180048C2B
0x180048cbd  mov     r13, [rbp+2D0h+var_310]
0x180048cc1  add     rax, 7
0x180048cc5  and     rax, 0FFFFFFFFFFFFFFF8h
0x180048cc9  xor     r8d, r8d; int
0x180048ccc  mov     [rbp+2D0h+var_340], rax
0x180048cd0  mov     r14, rax
0x180048cd3  xor     edx, edx; int
0x180048cd5  mov     rax, [r13+88h]
0x180048cdc  mov     ecx, [rax+24h]
0x180048cdf  mov     eax, [rax+28h]
0x180048ce2  mov     [rsp+3D0h+var_37C], ecx
0x180048ce6  mov     rcx, r13; this
0x180048ce9  mov     dword ptr [rsp+3D0h+ppstm], eax
0x180048ced  call    ?SetRenderingOrigin@GpGraphics@@QEAAXHH@Z
0x180048cf2  lea     rcx, [rbp+2D0h+var_2D0]; this
0x180048cf6  call    ??0EpAlphaBlender@@QEAA@XZ
0x180048cfb  xor     ecx, ecx
0x180048cfd  lea     rax, [rbp+2D0h+var_60]
0x180048d04  mov     [rsp+3D0h+var_388], ecx
0x180048d08  mov     r9d, 0E200Bh
0x180048d0e  mov     [rsp+3D0h+var_390], ecx
0x180048d12  mov     r8d, r12d
0x180048d15  mov     [rsp+3D0h+var_3A0], rax
0x180048d1a  mov     edx, r15d
0x180048d1d  mov     rax, [r13+88h]
0x180048d24  mov     qword ptr [rsp+3D0h+var_3A8], rcx
0x180048d29  lea     rcx, [rbp+2D0h+var_2D0]
0x180048d2d  mov     [rsp+3D0h+var_3B0], rax
0x180048d32  call    ?Initialize@EpAlphaBlender@@QEAAXW4EpScanType@@HHPEBVDpContext@@PEBUColorPalette@@PEAPEAXHHK@Z
0x180048d37  xor     r13d, r13d
0x180048d3a  cmp     [rbp+2D0h+var_348], r13d
0x180048d3e  jle     loc_180048DC9
0x180048d44  mov     ebx, [rsp+3D0h+var_368]
0x180048d48  mov     edx, r13d
0x180048d4b  lea     rcx, [r14+18h]; void *
  ... truncated ...
```
