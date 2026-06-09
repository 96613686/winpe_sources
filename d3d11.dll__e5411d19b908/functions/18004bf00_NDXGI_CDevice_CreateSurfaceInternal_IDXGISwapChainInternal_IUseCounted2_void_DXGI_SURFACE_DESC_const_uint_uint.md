# NDXGI::CDevice::CreateSurfaceInternal(IDXGISwapChainInternal *,IUseCounted2 *,void *,DXGI_SURFACE_DESC const *,uint,uint,uint,uint,void *,IDXGIResource * *)

- ea: `0x18004bf00`
- end: `0x18004c3fe`
- name: `?CreateSurfaceInternal@CDevice@NDXGI@@UEAAJPEAUIDXGISwapChainInternal@@PEAUIUseCounted2@@PEAXPEBUDXGI_SURFACE_DESC@@IIII2PEAPEAUIDXGIResource@@@Z`
- size: `1278`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct IDXGISwapChainInternal *, struct IUseCounted2 *, void *, const struct DXGI_SURFACE_DESC *, unsigned int, unsigned int, unsigned int, unsigned int, void *, struct IDXGIResource **)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18001fbd0`
- `0x180022400`
- `0x18004bf00`
- `0x18004c404`
- `0x18004c55c`
- `0x18004cbe8`
- `0x18004ccd0`
- `0x18009d94c`
- `0x18009da0c`
- `0x1800a9d20`
- `0x1800aa128`
- `0x1800aa19c`
- `0x1800aa9a8`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c1b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c1ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c1ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c347`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c1aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c23e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c1aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c23e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NDXGI::CDevice::CreateSurfaceInternal(
        NDXGI::CDevice *this,
        struct IDXGISwapChainInternal *a2,
        struct IUseCounted2 *a3,
        void *a4,
        const struct DXGI_SURFACE_DESC *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        void *a10,
        struct IDXGIResource **a11)
{
  void *v12; // rsi
  struct IDXGIResource **v13; // rbx
  unsigned __int64 v14; // r15
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  int v17; // eax
  char v18; // al
  char v19; // al
  BOOL v20; // edx
  __int64 RequirementsTable; // rax
  __int64 Format; // rcx
  _QWORD *v23; // rbx
  int v24; // r12d
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  unsigned __int64 v29; // rbx
  struct IDXGIResource **v30; // rsi
  __int64 v32; // rdx
  unsigned __int64 i; // rbx
  __int64 v34; // rcx
  bool v35; // [rsp+40h] [rbp-288h] BYREF
  struct IUseCounted2 *v36; // [rsp+48h] [rbp-280h]
  struct IDXGISwapChainInternal *v37; // [rsp+50h] [rbp-278h]
  struct IDXGIResource **v38; // [rsp+58h] [rbp-270h]
  _QWORD v39[2]; // [rsp+60h] [rbp-268h] BYREF
  DWORD CurrentThreadId; // [rsp+70h] [rbp-258h] BYREF
  _QWORD *v41; // [rsp+78h] [rbp-250h]
  char *v42; // [rsp+80h] [rbp-248h]
  _QWORD *v43; // [rsp+90h] [rbp-238h] BYREF
  _BYTE v44[48]; // [rsp+A0h] [rbp-228h] BYREF
  _QWORD *v45; // [rsp+D0h] [rbp-1F8h]
  D3D11_TEXTURE2D_DESC1 *v46; // [rsp+E0h] [rbp-1E8h]
  unsigned int v47; // [rsp+E8h] [rbp-1E0h]
  void *v48; // [rsp+F0h] [rbp-1D8h]
  __int64 v49; // [rsp+F8h] [rbp-1D0h]
  unsigned int v50; // [rsp+100h] [rbp-1C8h]
  _QWORD v51[7]; // [rsp+110h] [rbp-1B8h] BYREF
  int v52; // [rsp+148h] [rbp-180h]
  int v53; // [rsp+14Ch] [rbp-17Ch]
  int v54; // [rsp+150h] [rbp-178h]
  char v55; // [rsp+190h] [rbp-138h]
  char v56; // [rsp+191h] [rbp-137h]
  char v57; // [rsp+192h] [rbp-136h]
  _QWORD v58[16]; // [rsp+1A0h] [rbp-128h] BYREF
  D3D11_TEXTURE2D_DESC1 v59; // [rsp+220h] [rbp-A8h] BYREF
  struct D3D11_TEXTURE2D_DESC1 v60; // [rsp+250h] [rbp-78h] BYREF

  v36 = a3;
  v37 = a2;
  v12 = a10;
  v13 = a11;
  v38 = a11;
  if ( a7 >= 0x10 )
    ThrowFailure(-2147024809);
  memset_0(v13, 0, 8LL * a7);
  `eh vector constructor iterator'(
    v58,
    8u,
    0x10u,
    ATL::CComPtr<IUseCounted>::CComPtr<IUseCounted>,
    ATL::CComPtr<ID3D12DeviceTest>::~CComPtr<ID3D12DeviceTest>);
  v14 = 0;
  v35 = 0;
  v15 = a9;
  NDXGI::CDevice::GetTexDescsForCreateSurface(
    (NDXGI::CDevice *)((char *)this - 16),
    &v59,
    &v35,
    a5,
    &a8,
    a9,
    a6,
    v12 != 0);
  memset_0(v44, 0, 0x68u);
  memset_0(v51, 0, 0x88u);
  if ( v35 )
  {
    if ( NDXGI::CUMDAdapter::SupportsSharedResources(*((NDXGI::CUMDAdapter **)this + 10))
      && (int)CDevice::InitSharedResource2DCreationParams(*((CDevice **)this + 7), &v60, v16, v51) >= 0 )
    {
      v45 = v51;
      v17 = v53;
      if ( (v15 & 0x200000) != 0 )
        v17 = 1;
      v53 = v17;
      if ( (v15 & 0x400000) != 0 )
      {
        v54 = 1;
        v52 = 1;
      }
      v18 = v56;
      if ( (v15 & 0x4000000) != 0 )
        v18 = 1;
      v56 = v18;
      v19 = v57;
      if ( (v15 & 0x8000000) != 0 )
        v19 = 1;
      v57 = v19;
    }
    if ( (v15 & 0x80u) != 0 && !v45 )
      ThrowFailure(-2147024809);
  }
  v46 = &v59;
  v20 = 0;
  if ( v45 )
  {
    RequirementsTable = CD3D11FormatHelper::GetRequirementsTable(
                          *(unsigned int *)(*((_QWORD *)this + 7) + 1284LL),
                          *(unsigned int *)(*((_QWORD *)this + 7) + 1116LL));
    Format = 0xFFFFFFFFLL;
    if ( v59.Format < 0xC0u )
      Format = (unsigned int)v59.Format;
    v20 = (*(_DWORD *)(RequirementsTable + 12 * Format + 4) & 0xC0000) == 0x40000;
  }
  v47 = (16 * v20) | ((v15 & 0x8000 | ((v15 & 0x20000 | ((v15 & 0x800000 | 0x100000) >> 4)) >> 3)) >> 13);
  v48 = v12;
  v49 = 44;
  v50 = a8;
  while ( v14 < a7 )
  {
    v39[0] = v37;
    v39[1] = 0;
    v42 = (char *)this + 1560;
    AcquireSRWLockExclusive((PSRWLOCK)this + 195);
    CurrentThreadId = GetCurrentThreadId();
    v41 = v39;
    std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>(
      (char *)this + 1568,
      &v43,
      &CurrentThreadId);
    v23 = v43;
    if ( this != (NDXGI::CDevice *)-1560LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 195);
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *))(**((_QWORD **)this + 4) + 72LL))(
            *((_QWORD *)this + 4),
            2,
            v44);
    AcquireSRWLockExclusive((PSRWLOCK)this + 195);
    v25 = std::_Conditionally_enabled_hash<unsigned long,1>::operator()(v23 + 2);
    v26 = 2 * (v25 & *((_QWORD *)this + 202));
    v27 = *((_QWORD *)this + 199);
    if ( *(_QWORD **)(v27 + 16 * (v25 & *((_QWORD *)this + 202)) + 8) == v23 )
    {
      if ( *(_QWORD **)(v27 + 16 * (v25 & *((_QWORD *)this + 202))) == v23 )
      {
        v28 = *((_QWORD *)this + 197);
        *(_QWORD *)(v27 + 8 * v26) = v28;
      }
      else
      {
        v28 = v23[1];
      }
      *(_QWORD *)(v27 + 8 * v26 + 8) = v28;
    }
    else if ( *(_QWORD **)(v27 + 16 * (v25 & *((_QWORD *)this + 202))) == v23 )
    {
      *(_QWORD *)(v27 + 16 * (v25 & *((_QWORD *)this + 202))) = *v23;
    }
    v32 = *v23;
    --*((_QWORD *)this + 198);
    *(_QWORD *)v23[1] = v32;
    *(_QWORD *)(v32 + 8) = v23[1];
    std::_Deallocate<16>(v23, 32);
    if ( this != (NDXGI::CDevice *)-1560LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 195);
    if ( v45 )
    {
      v51[0] = 0;
      v55 = 0;
    }
    if ( v24 < 0 && v36 )
    {
      for ( i = 0; i < v14; ++i )
      {
        v34 = v58[i];
        v58[i] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 56LL))(v34);
      }
    }
    ThrowFailure(v24);
    ++v14;
  }
  v29 = 0;
  v30 = v38;
  while ( v29 < a7 )
  {
    (**(void (__fastcall ***)(_QWORD, GUID *, __int64))v58[v29])(
      v58[v29],
      &GUID_035f3ab4_482e_4e50_b41f_8a7f8bd8960b,
      (__int64)&v30[v29]);
    ++v29;
  }
  if ( *((_BYTE *)this + 880) )
  {
    `eh vector destructor iterator'(v58, 8u, 0x10u, ATL::CComPtr<ID3D12DeviceTest>::~CComPtr<ID3D12DeviceTest>);
    return 142213124;
  }
  else
  {
    `eh vector destructor iterator'(v58, 8u, 0x10u, ATL::CComPtr<ID3D12DeviceTest>::~CComPtr<ID3D12DeviceTest>);
    return 0;
  }
}

```

## disassembly

```asm
0x18004bf00  push    rbx
0x18004bf02  push    rsi
0x18004bf03  push    rdi
0x18004bf04  push    r12
0x18004bf06  push    r13
0x18004bf08  push    r14
0x18004bf0a  push    r15
0x18004bf0c  sub     rsp, 290h
0x18004bf13  mov     rax, cs:__security_cookie
0x18004bf1a  xor     rax, rsp
0x18004bf1d  mov     [rsp+2C8h+var_48], rax
0x18004bf25  mov     r12, r8
0x18004bf28  mov     [rsp+2C8h+var_280], r8
0x18004bf2d  mov     [rsp+2C8h+var_278], rdx
0x18004bf32  mov     r14, rcx
0x18004bf35  mov     rdi, [rsp+2C8h+arg_20]
0x18004bf3d  mov     rsi, [rsp+2C8h+arg_48]
0x18004bf45  mov     rbx, [rsp+2C8h+arg_50]
0x18004bf4d  mov     [rsp+2C8h+var_270], rbx
0x18004bf52  cmp     [rsp+2C8h+arg_30], 10h
0x18004bf5a  jnb     loc_18004C3AB
0x18004bf60  mov     r13d, [rsp+2C8h+arg_30]
0x18004bf68  lea     r8, ds:0[r13*8]; Size
0x18004bf70  xor     edx, edx; Val
0x18004bf72  mov     rcx, rbx; void *
0x18004bf75  call    memset_0
0x18004bf7a  lea     rax, ??1?$CComPtr@UID3D12DeviceTest@@@ATL@@QEAA@XZ; ATL::CComPtr<ID3D12DeviceTest>::~CComPtr<ID3D12DeviceTest>(void)
0x18004bf81  mov     [rsp+2C8h+var_2A8], rax; void (*)(void *)
0x18004bf86  lea     r9, ??0?$CComPtr@UIUseCounted@@@ATL@@QEAA@XZ; void (*)(void *)
0x18004bf8d  mov     edx, 8; unsigned __int64
0x18004bf92  lea     r8d, [rdx+8]; unsigned __int64
0x18004bf96  lea     rcx, [rsp+2C8h+var_128]; void *
0x18004bf9e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18004bfa3  nop
0x18004bfa4  xor     r15d, r15d
0x18004bfa7  mov     [rsp+2C8h+var_288], r15b
0x18004bfac  test    rsi, rsi
0x18004bfaf  setnz   al
0x18004bfb2  lea     rcx, [r14-10h]; this
0x18004bfb6  mov     [rsp+2C8h+var_290], al; bool
0x18004bfba  mov     eax, [rsp+2C8h+arg_28]
0x18004bfc1  mov     [rsp+2C8h+var_298], eax; unsigned int
0x18004bfc5  mov     ebx, [rsp+2C8h+arg_40]
0x18004bfcc  mov     [rsp+2C8h+var_2A0], ebx; unsigned int
0x18004bfd0  lea     rax, [rsp+2C8h+arg_38]
0x18004bfd8  mov     [rsp+2C8h+var_2A8], rax; unsigned int *
0x18004bfdd  mov     r9, rdi; struct DXGI_SURFACE_DESC *
0x18004bfe0  lea     r8, [rsp+2C8h+var_288]; bool *
0x18004bfe5  lea     rdx, [rsp+2C8h+var_A8]; struct D3D11_TEXTURE2D_DESC1 *
0x18004bfed  call    ?GetTexDescsForCreateSurface@CDevice@NDXGI@@QEAAXPEAUD3D11_TEXTURE2D_DESC1@@AEA_NPEBUDXGI_SURFACE_DESC@@AEAIII_N@Z; NDXGI::CDevice::GetTexDescsForCreateSurface(D3D11_TEXTURE2D_DESC1 *,bool &,DXGI_SURFACE_DESC const *,uint &,uint,uint,bool)
0x18004bff2  xor     edx, edx; Val
0x18004bff4  lea     r8d, [r15+68h]; Size
0x18004bff8  lea     rcx, [rsp+2C8h+var_228]; void *
0x18004c000  call    memset_0
0x18004c005  xor     edx, edx; Val
0x18004c007  mov     r8d, 88h; Size
0x18004c00d  lea     rcx, [rsp+2C8h+var_1B8]; void *
0x18004c015  call    memset_0
0x18004c01a  cmp     [rsp+2C8h+var_288], r15b
0x18004c01f  jz      loc_18004C2FF
0x18004c025  mov     rcx, [r14+50h]; this
0x18004c029  call    ?SupportsSharedResources@CUMDAdapter@NDXGI@@QEBA_NXZ; NDXGI::CUMDAdapter::SupportsSharedResources(void)
0x18004c02e  test    al, al
0x18004c030  jz      loc_18004C3A1
0x18004c036  lea     r9, [rsp+2C8h+var_1B8]; void *
0x18004c03e  lea     rdx, [rsp+2C8h+var_78]; struct D3D11_TEXTURE2D_DESC1 *
0x18004c046  mov     rcx, [r14+38h]; this
0x18004c04a  call    ?InitSharedResource2DCreationParams@CDevice@@QEAAJPEBUD3D11_TEXTURE2D_DESC1@@IPEAX@Z; CDevice::InitSharedResource2DCreationParams(D3D11_TEXTURE2D_DESC1 const *,uint,void *)
0x18004c04f  test    eax, eax
0x18004c051  js      loc_18004C3A1
0x18004c057  lea     rax, [rsp+2C8h+var_1B8]
0x18004c05f  mov     [rsp+2C8h+var_1F8], rax
0x18004c067  bt      ebx, 15h
0x18004c06b  mov     eax, [rsp+2C8h+var_17C]
0x18004c072  lea     edi, [r15+1]
0x18004c076  cmovb   eax, edi
0x18004c079  mov     [rsp+2C8h+var_17C], eax
0x18004c080  bt      ebx, 16h
0x18004c084  jb      loc_18004C3BA
0x18004c08a  bt      ebx, 1Ah
0x18004c08e  movzx   eax, [rsp+2C8h+var_137]
0x18004c096  cmovb   eax, edi
0x18004c099  mov     [rsp+2C8h+var_137], al
0x18004c0a0  bt      ebx, 1Bh
0x18004c0a4  movzx   eax, [rsp+2C8h+var_136]
0x18004c0ac  cmovb   eax, edi
0x18004c0af  mov     [rsp+2C8h+var_136], al
0x18004c0b6  test    bl, bl
0x18004c0b8  jns     short loc_18004C0C8
0x18004c0ba  cmp     [rsp+2C8h+var_1F8], r15
0x18004c0c2  jz      loc_18004C3CD
0x18004c0c8  lea     rax, [rsp+2C8h+var_A8]
0x18004c0d0  mov     [rsp+2C8h+var_1E8], rax
0x18004c0d8  mov     edx, r15d
0x18004c0db  cmp     [rsp+2C8h+var_1F8], r15
0x18004c0e3  jz      short loc_18004C128
0x18004c0e5  mov     rcx, [r14+38h]
0x18004c0e9  mov     edx, [rcx+45Ch]
0x18004c0ef  mov     ecx, [rcx+504h]
0x18004c0f5  call    ?GetRequirementsTable@CD3D11FormatHelper@@CAPEBUFORMAT_REQUIREMENTS@1@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::GetRequirementsTable(D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18004c0fa  or      ecx, 0FFFFFFFFh
0x18004c0fd  cmp     [rsp+2C8h+var_A8.Format], 0C0h
0x18004c108  cmovb   ecx, [rsp+2C8h+var_A8.Format]
0x18004c110  lea     rdx, [rcx+rcx*2]
0x18004c114  mov     eax, [rax+rdx*4+4]
0x18004c118  and     eax, 0C0000h
0x18004c11d  mov     edx, r15d
0x18004c120  cmp     eax, 40000h
0x18004c125  setz    dl
0x18004c128  mov     ecx, ebx
0x18004c12a  and     ecx, 800000h
0x18004c130  bts     ecx, 14h
0x18004c134  shr     ecx, 4
0x18004c137  mov     eax, ebx
0x18004c139  and     eax, 20000h
0x18004c13e  or      ecx, eax
0x18004c140  shr     ecx, 3
0x18004c143  and     ebx, 8000h
0x18004c149  or      ecx, ebx
0x18004c14b  shr     ecx, 0Dh
0x18004c14e  shl     edx, 4
0x18004c151  or      ecx, edx
0x18004c153  mov     [rsp+2C8h+var_1E0], ecx
0x18004c15a  mov     [rsp+2C8h+var_1D8], rsi
0x18004c162  mov     [rsp+2C8h+var_1D0], 2Ch ; ','
0x18004c16e  mov     eax, [rsp+2C8h+arg_38]
0x18004c175  mov     [rsp+2C8h+var_1C8], eax
0x18004c17c  xor     esi, esi
0x18004c17e  cmp     r15, r13
0x18004c181  jnb     loc_18004C27F
0x18004c187  mov     rax, [rsp+2C8h+var_278]
0x18004c18c  mov     [rsp+2C8h+var_268], rax
0x18004c191  xor     eax, eax
0x18004c193  mov     [rsp+2C8h+var_260], rax
0x18004c198  lea     rsi, [r14+618h]
0x18004c19f  mov     [rsp+2C8h+var_248], rsi
0x18004c1a7  mov     rcx, rsi; SRWLock
0x18004c1aa  call    cs:__imp_AcquireSRWLockExclusive
0x18004c1b0  nop
0x18004c1b1  call    cs:__imp_GetCurrentThreadId
0x18004c1b7  mov     [rsp+2C8h+var_258], eax
0x18004c1bb  lea     rax, [rsp+2C8h+var_268]
0x18004c1c0  mov     [rsp+2C8h+var_250], rax
0x18004c1c5  lea     rcx, [r14+620h]
0x18004c1cc  lea     r8, [rsp+2C8h+var_258]
0x18004c1d1  lea     rdx, [rsp+2C8h+var_238]
0x18004c1d9  call    ??$emplace@U?$pair@KPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@@std@@@?$_Hash@V?$_Umap_traits@KPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAUSCreateLayeredChildThreadLocalData@CDevice@NDXGI@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>,0>>::emplace<std::pair<ulong,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *>>(std::pair<ulong,NDXGI::CDevice::SCreateLayeredChildThreadLocalData *> &&)
0x18004c1de  mov     rbx, [rsp+2C8h+var_238]
0x18004c1e6  test    rsi, rsi
0x18004c1e9  jz      short loc_18004C1F4
0x18004c1eb  mov     rcx, rsi; SRWLock
0x18004c1ee  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c1f4  mov     rcx, [r14+20h]
0x18004c1f8  mov     rax, [rcx]
0x18004c1fb  lea     rdx, [rsp+2C8h+var_128]
0x18004c203  lea     rdx, [rdx+r15*8]
0x18004c207  mov     qword ptr [rsp+2C8h+var_298], rdx
0x18004c20c  lea     rdx, _GUID_9b7e4a01_342c_4106_a19f_4f2704f689f0
0x18004c213  mov     qword ptr [rsp+2C8h+var_2A0], rdx
0x18004c218  mov     [rsp+2C8h+var_2A8], r12
0x18004c21d  mov     r9d, 68h ; 'h'
0x18004c223  lea     r8, [rsp+2C8h+var_228]
0x18004c22b  lea     edx, [r9-66h]
0x18004c22f  mov     rax, [rax+48h]
0x18004c233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c238  mov     r12d, eax
0x18004c23b  mov     rcx, rsi; SRWLock
0x18004c23e  call    cs:__imp_AcquireSRWLockExclusive
0x18004c244  lea     rcx, [rbx+10h]
0x18004c248  call    ??R?$_Conditionally_enabled_hash@K$00@std@@SA_KAEBK@Z; std::_Conditionally_enabled_hash<ulong,1>::operator()(ulong const &)
0x18004c24d  mov     rcx, [r14+650h]
0x18004c254  and     rcx, rax
0x18004c257  add     rcx, rcx
0x18004c25a  mov     rdx, [r14+638h]
0x18004c261  cmp     [rdx+rcx*8+8], rbx
0x18004c266  jnz     loc_18004C383
0x18004c26c  cmp     [rdx+rcx*8], rbx
0x18004c270  jz      loc_18004C309
0x18004c276  mov     rax, [rbx+8]
0x18004c27a  jmp     loc_18004C314
0x18004c27f  mov     rbx, rsi
0x18004c282  mov     rsi, [rsp+2C8h+var_270]
0x18004c287  cmp     rbx, r13
0x18004c28a  jb      short loc_18004C2DC
0x18004c28c  lea     r9, ??1?$CComPtr@UID3D12DeviceTest@@@ATL@@QEAA@XZ; void (*)(void *)
0x18004c293  mov     edx, 8; unsigned __int64
0x18004c298  lea     r8d, [rdx+8]; unsigned __int64
0x18004c29c  lea     rcx, [rsp+2C8h+var_128]; void *
0x18004c2a4  cmp     byte ptr [r14+370h], 0
0x18004c2ac  jnz     loc_18004C392
0x18004c2b2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004c2b7  xor     eax, eax
0x18004c2b9  mov     rcx, [rsp+2C8h+var_48]
0x18004c2c1  xor     rcx, rsp; StackCookie
0x18004c2c4  call    __security_check_cookie
0x18004c2c9  add     rsp, 290h
0x18004c2d0  pop     r15
0x18004c2d2  pop     r14
0x18004c2d4  pop     r13
0x18004c2d6  pop     r12
0x18004c2d8  pop     rdi
0x18004c2d9  pop     rsi
0x18004c2da  pop     rbx
0x18004c2db  retn
0x18004c2dc  mov     rcx, [rsp+rbx*8+2C8h+var_128]
0x18004c2e4  mov     rax, [rcx]
0x18004c2e7  lea     r8, [rsi+rbx*8]
0x18004c2eb  lea     rdx, _GUID_035f3ab4_482e_4e50_b41f_8a7f8bd8960b
0x18004c2f2  mov     rax, [rax]
0x18004c2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2fa  add     rbx, rdi
0x18004c2fd  jmp     short loc_18004C287
0x18004c2ff  mov     edi, 1
0x18004c304  jmp     loc_18004C0C8
0x18004c309  mov     rax, [r14+628h]
0x18004c310  mov     [rdx+rcx*8], rax
0x18004c314  mov     [rdx+rcx*8+8], rax
0x18004c319  mov     rdx, [rbx]
0x18004c31c  dec     qword ptr [r14+630h]
0x18004c323  mov     rax, [rbx+8]
0x18004c327  mov     [rax], rdx
0x18004c32a  mov     rax, [rbx+8]
0x18004c32e  mov     [rdx+8], rax
0x18004c332  mov     edx, 20h ; ' '
0x18004c337  mov     rcx, rbx
0x18004c33a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004c33f  test    rsi, rsi
0x18004c342  jz      short loc_18004C34D
0x18004c344  mov     rcx, rsi; SRWLock
0x18004c347  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c34d  xor     esi, esi
0x18004c34f  cmp     [rsp+2C8h+var_1F8], rsi
0x18004c357  jz      short loc_18004C369
0x18004c359  mov     [rsp+2C8h+var_1B8], rsi
0x18004c361  mov     [rsp+2C8h+var_138], sil
0x18004c369  test    r12d, r12d
0x18004c36c  js      short loc_18004C3DC
0x18004c36e  mov     ecx, r12d; int
0x18004c371  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18004c376  add     r15, rdi
0x18004c379  mov     r12, [rsp+2C8h+var_280]
0x18004c37e  jmp     loc_18004C17E
0x18004c383  cmp     [rdx+rcx*8], rbx
0x18004c387  jnz     short loc_18004C319
0x18004c389  mov     rax, [rbx]
0x18004c38c  mov     [rdx+rcx*8], rax
0x18004c390  jmp     short loc_18004C319
0x18004c392  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004c397  mov     eax, 87A0004h
0x18004c39c  jmp     loc_18004C2B9
0x18004c3a1  mov     edi, 1
0x18004c3a6  jmp     loc_18004C0B6
0x18004c3ab  mov     ecx, 80070057h; int
0x18004c3b0  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18004c3b5  jmp     loc_18004BF60
0x18004c3ba  mov     [rsp+2C8h+var_178], edi
0x18004c3c1  mov     [rsp+2C8h+var_180], edi
0x18004c3c8  jmp     loc_18004C08A
0x18004c3cd  mov     ecx, 80070057h; int
0x18004c3d2  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18004c3d7  jmp     loc_18004C0C8
0x18004c3dc  cmp     [rsp+2C8h+var_280], rsi
0x18004c3e1  jz      short loc_18004C36E
0x18004c3e3  mov     rbx, rsi
0x18004c3e6  jmp     loc_1800EAE4A
0x18004c3eb  mov     eax, 8007000Eh
0x18004c3f0  jmp     loc_1800EAE74
0x18004c3f5  mov     eax, dword ptr [rsp+2C8h+var_280]
0x18004c3f9  jmp     loc_1800EAE74
0x1800eae4a  cmp     rbx, r15
0x1800eae4d  jnb     loc_18004C36E
0x1800eae53  mov     rcx, [rsp+rbx*8+2C8h+var_128]
0x1800eae5b  mov     [rsp+rbx*8+2C8h+var_128], rsi
0x1800eae63  mov     rax, [rcx]
0x1800eae66  mov     rax, [rax+38h]
0x1800eae6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eae6f  add     rbx, rdi
0x1800eae72  jmp     short loc_1800EAE4A
0x1800eae74  jmp     loc_18004C2B9
```
