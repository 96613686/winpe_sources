# NDXGIOn12::CDevice::PresentMultiplaneOverlay(IDXGIResource *,uint,_DXGI_PRESENT_MULTIPLANE_OVERLAY const *,void *)

- ea: `0x1800bd8f0`
- end: `0x1800bded6`
- name: `?PresentMultiplaneOverlay@CDevice@NDXGIOn12@@UEAAJPEAUIDXGIResource@@IPEBU_DXGI_PRESENT_MULTIPLANE_OVERLAY@@PEAX@Z`
- size: `1510`
- prototype: `__int64 __fastcall(NDXGIOn12::CDevice *__hidden this, struct IDXGIResource *, unsigned int, const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *, void *)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x1800147d0`
- `0x180022400`
- `0x18002d0f0`
- `0x18002e160`
- `0x18002fc60`
- `0x18002fde0`
- `0x180034550`
- `0x1800438e0`
- `0x180058970`
- `0x18005ec80`
- `0x180060b4c`
- `0x180067100`
- `0x180098550`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800b76b0`
- `0x1800bc458`
- `0x1800bd8f0`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdcf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bdcf3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdd25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdd75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdd25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bdd75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdce5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdd52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdce5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bdd52`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NDXGIOn12::CDevice::PresentMultiplaneOverlay(
        NDXGIOn12::CDevice *this,
        struct IDXGIResource *a2,
        unsigned int a3,
        const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *a4,
        unsigned int *a5)
{
  unsigned int *v9; // rdi
  unsigned int i; // ebx
  __int64 v12; // rax
  struct IDXGIResource *v13; // rax
  struct IDXGIResource *v14; // rdx
  __int64 v15; // rdx
  unsigned int *DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4; // r13
  unsigned int v17; // r14d
  __int64 v18; // r8
  __int64 (__fastcall **v19)(__int64, GUID *, __int64); // rdx
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r9
  int v26; // eax
  __int64 v27; // rcx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  __int64 v31; // r13
  __int64 v32; // r14
  int v33; // ebx
  __int64 v34; // rcx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64); // rbx
  __int64 v37; // rax
  __int64 v38; // rcx
  DWORD CurrentThreadId; // eax
  __int64 (*v40)(void); // rax
  int v41; // edi
  int v42; // ebx
  unsigned int v43; // [rsp+30h] [rbp-938h] BYREF
  __int64 v44; // [rsp+38h] [rbp-930h] BYREF
  __int64 v45; // [rsp+40h] [rbp-928h] BYREF
  __int64 v46; // [rsp+48h] [rbp-920h] BYREF
  __int64 v47; // [rsp+50h] [rbp-918h]
  __int64 v48; // [rsp+58h] [rbp-910h] BYREF
  _QWORD v49[4]; // [rsp+60h] [rbp-908h] BYREF
  __int128 v50; // [rsp+80h] [rbp-8E8h]
  __int128 v51; // [rsp+90h] [rbp-8D8h]
  _com_error *v52; // [rsp+A0h] [rbp-8C8h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-8C0h] BYREF
  _BYTE v54[40]; // [rsp+B8h] [rbp-8B0h] BYREF
  _BYTE v55[64]; // [rsp+E0h] [rbp-888h] BYREF
  _DWORD v56[512]; // [rsp+120h] [rbp-848h] BYREF

  v49[0] = a2;
  v9 = a5;
  if ( !(*(unsigned int (__fastcall **)(NDXGIOn12::CDevice *))(*(_QWORD *)this + 328LL))(this) )
    return NDXGI::CDevice::PresentMultiplaneOverlay(this, a2, a3, a4, a5);
  if ( *((int *)this + 308) < 0 )
    return 2289696773LL;
  for ( i = 0; i < a3; ++i )
  {
    v12 = 136LL * i;
    if ( *(_DWORD *)((char *)a4 + v12 + 4) )
    {
      v13 = *(struct IDXGIResource **)((char *)a4 + v12 + 8);
      v14 = a2;
      if ( v13 )
        v14 = v13;
      (*(void (__fastcall **)(_QWORD, struct IDXGIResourceVtbl *, _QWORD))(**((_QWORD **)this + 258) + 80LL))(
        *((_QWORD *)this + 258),
        v14[17].lpVtbl,
        0);
    }
  }
  NDXGI::CDevice::Flush((char *)this - 16, 0, 0);
  LOBYTE(v15) = 9;
  if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*((_QWORD *)this + 7), v15, 4) )
  {
    try
    {
      v9 = (unsigned int *)NDXGI::OpaqueHandleManager<BatchablePresentMPO>::AcquireToken<_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3>(
                             (LPCRITICAL_SECTION)((char *)this + 1904),
                             (__int64)a5);
      DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4 = (unsigned int *)NDXGI::OpaqueHandleManager_BatchablePresentMPO_::GetDataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4___((LPCRITICAL_SECTION)((char *)this + 1904));
    }
    catch ( _com_error *v52 )
    {
      return *((unsigned int *)v52 + 2);
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
  }
  else
  {
    DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4 = a5;
  }
  v43 = 1;
  std::fill<enum DXGI_DDI_MODE_ROTATION *,enum DXGI_DDI_MODE_ROTATION>(v55, v56, &v43);
  v17 = DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4[6];
  LODWORD(v44) = v17;
  v45 = 0;
  v18 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v45, **((_QWORD **)this + 259));
  v21 = (*v19)(v20, &GUID_36871736_2446_4858_8473_99bd44555307, v18);
  ThrowFailure(v21);
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 152LL))(v45);
  v46 = 0;
  v23 = IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(&v46, **((_QWORD **)this + 258));
  v26 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(v24 + 8))(
          v25,
          &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
          v23);
  ThrowFailure(v26);
  v48 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 168LL))(v45, v46);
  v50 = 0;
  v51 = 0;
  v49[2] = v22;
  v49[3] = v9;
  LODWORD(v50) = DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4[4];
  DWORD1(v50) = 2;
  *((_QWORD *)&v51 + 1) = v55;
  if ( !DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4[7] )
    goto LABEL_22;
  v27 = *((_QWORD *)DataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4 + 4);
  if ( !v27 )
    goto LABEL_22;
  v28 = *(_DWORD *)(*(_QWORD *)v27 + 8LL);
  if ( !v28 )
    goto LABEL_23;
  v29 = v28 - 1;
  if ( v29 )
  {
    v30 = v29 - 1;
    if ( v30 )
    {
      if ( v30 == 1 )
        DWORD2(v50) = 3;
      else
        DWORD2(v50) = 4;
    }
    else
    {
      DWORD2(v50) = 2;
    }
  }
  else
  {
LABEL_22:
    DWORD2(v50) = 1;
  }
LABEL_23:
  v43 = 0;
  if ( a3 )
  {
    v31 = 0;
    do
    {
      v47 = 136 * v31;
      v32 = v31 << 7;
      v33 = *((_DWORD *)a4 + 34 * v31);
      if ( *((_DWORD *)a4 + 34 * v31 + 1) )
      {
        v56[32 * v31] = v33;
        v56[32 * v31 + 1] = 1;
        v34 = v49[0];
        if ( *((_QWORD *)a4 + 17 * v31 + 1) )
          v34 = *((_QWORD *)a4 + 17 * v31 + 1);
        v35 = v45;
        v36 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 160LL);
        v37 = (***(__int64 (__fastcall ****)(_QWORD))(v34 + 136))(*(_QWORD *)(v34 + 136));
        *(_QWORD *)&v56[32 * v31 + 2] = v36(v35, v37);
        v38 = v47;
        v56[32 * v31 + 4] = *(_DWORD *)((char *)a4 + v47 + 16);
        NDXGI::CDevice::ConvertToDDI(
          (char *)a4 + v38 + 24,
          (char *)&v56[6] + v32,
          *(unsigned int *)(*((_QWORD *)this + 7) + 1124LL));
      }
      else
      {
        memset_0((char *)&v56[1] + v32, 0, 0x7Cu);
        v56[32 * v31] = v33;
        v56[32 * v31 + 1] = 0;
      }
      ++v43;
      ++v31;
    }
    while ( v43 < a3 );
    LOWORD(v17) = v44;
  }
  HIDWORD(v50) = a3;
  *(_QWORD *)&v51 = v56;
  CDevCtxInterface::CDevCtxInterface(
    (CDevCtxInterface *)v54,
    *(struct CContext **)(*((_QWORD *)this + 7) + 1080LL),
    1,
    0,
    0);
  v44 = 0;
  v47 = (__int64)this + 1320;
  AcquireSRWLockExclusive((PSRWLOCK)this + 165);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(v49[0]) = CurrentThreadId;
  v49[1] = &v44;
  try
  {
    std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *>>(
      (char *)this + 1328,
      &v53,
      v49);
    if ( this != (NDXGIOn12::CDevice *)-1320LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 165);
    v40 = (__int64 (*)(void))*((_QWORD *)this + 264);
  }
  catch ( std::bad_alloc )
  {
    CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v54);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v46);
    ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v45);
    return 2147942414LL;
  }
  v41 = v40();
  AcquireSRWLockExclusive((PSRWLOCK)this + 165);
  std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>>>,0>(
    (char *)this + 1328,
    &v48,
    v53);
  if ( this != (NDXGIOn12::CDevice *)-1320LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 165);
  if ( v41 == -2005530512 )
    goto LABEL_61;
  if ( !v41 )
  {
    if ( (_DWORD)v44 != -2005530512 )
    {
      if ( SHIDWORD(v44) > -1071775733 )
      {
        switch ( HIDWORD(v44) )
        {
          case 0xC01E0018:
            v42 = (v17 & 0x400) != 0 ? -2005270428 : 142213127;
            goto LABEL_62;
          case 0xC01E0102:
            v42 = -2005270518;
            goto LABEL_62;
          case 0xC01E0342:
            v42 = 142213126;
            goto LABEL_62;
          case 0x103:
            v42 = 142213130;
            goto LABEL_62;
        }
      }
      else
      {
        switch ( HIDWORD(v44) )
        {
          case 0xC01E000B:
            v42 = 142213124;
            goto LABEL_62;
          case 0xC000000D:
            goto LABEL_41;
          case 0xC01E0000:
            goto LABEL_49;
          case 0xC01E0005:
            v42 = 142213127;
            goto LABEL_62;
        }
        if ( (unsigned int)(HIDWORD(v44) + 1071775738) <= 1 )
        {
LABEL_49:
          v42 = 142213121;
          goto LABEL_62;
        }
      }
      v42 = 0;
      goto LABEL_62;
    }
LABEL_61:
    v42 = -2005270523;
    (*(void (__fastcall **)(NDXGIOn12::CDevice *, __int64))(*(_QWORD *)this + 264LL))(this, 2289696773LL);
    goto LABEL_62;
  }
  NDXGI::CDevice::DriverInternalError((NDXGIOn12::CDevice *)((char *)this - 16), v41);
LABEL_41:
  v42 = -2005270523;
LABEL_62:
  CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v54);
  if ( v42 >= 0 )
    CDevice::IncrementConservativeFlushCount(*((CDevice **)this + 7));
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v46);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v45);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x1800bd8f0  push    rbx
0x1800bd8f2  push    rsi
0x1800bd8f3  push    rdi
0x1800bd8f4  push    r12
0x1800bd8f6  push    r13
0x1800bd8f8  push    r14
0x1800bd8fa  push    r15
0x1800bd8fc  sub     rsp, 930h
0x1800bd903  mov     rax, cs:__security_cookie
0x1800bd90a  xor     rax, rsp
0x1800bd90d  mov     [rsp+968h+var_48], rax
0x1800bd915  mov     r12, r9
0x1800bd918  mov     r15d, r8d
0x1800bd91b  mov     r14, rdx
0x1800bd91e  mov     [rsp+968h+var_908], rdx
0x1800bd923  mov     rsi, rcx
0x1800bd926  mov     rdi, [rsp+968h+arg_20]
0x1800bd92e  mov     rax, [rcx]
0x1800bd931  mov     rax, [rax+148h]
0x1800bd938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd93d  test    eax, eax
0x1800bd93f  jnz     short loc_1800BD95C
0x1800bd941  mov     [rsp+968h+var_948], rdi; void *
0x1800bd946  mov     r9, r12; struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *
0x1800bd949  mov     r8d, r15d; unsigned int
0x1800bd94c  mov     rdx, r14; struct IDXGIResource *
0x1800bd94f  mov     rcx, rsi; this
0x1800bd952  call    ?PresentMultiplaneOverlay@CDevice@NDXGI@@UEAAJPEAUIDXGIResource@@IPEBU_DXGI_PRESENT_MULTIPLANE_OVERLAY@@PEAX@Z; NDXGI::CDevice::PresentMultiplaneOverlay(IDXGIResource *,uint,_DXGI_PRESENT_MULTIPLANE_OVERLAY const *,void *)
0x1800bd957  jmp     loc_1800BDEB3
0x1800bd95c  mov     eax, [rsi+4D0h]
0x1800bd962  test    eax, eax
0x1800bd964  jns     short loc_1800BD970
0x1800bd966  mov     eax, 887A0005h
0x1800bd96b  jmp     loc_1800BDEB3
0x1800bd970  xor     ebx, ebx
0x1800bd972  test    r15d, r15d
0x1800bd975  jz      short loc_1800BD9BB
0x1800bd977  mov     eax, ebx
0x1800bd979  imul    rax, 88h
0x1800bd980  cmp     dword ptr [rax+r12+4], 0
0x1800bd986  jz      short loc_1800BD9B4
0x1800bd988  mov     rax, [rax+r12+8]
0x1800bd98d  mov     rdx, r14
0x1800bd990  test    rax, rax
0x1800bd993  cmovnz  rdx, rax
0x1800bd997  mov     rcx, [rsi+810h]
0x1800bd99e  mov     rax, [rcx]
0x1800bd9a1  xor     r8d, r8d
0x1800bd9a4  mov     rdx, [rdx+88h]
0x1800bd9ab  mov     rax, [rax+50h]
0x1800bd9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9b4  inc     ebx
0x1800bd9b6  cmp     ebx, r15d
0x1800bd9b9  jb      short loc_1800BD977
0x1800bd9bb  lea     rcx, [rsi-10h]
0x1800bd9bf  xor     r8d, r8d
0x1800bd9c2  xor     edx, edx
0x1800bd9c4  call    ?Flush@CDevice@NDXGI@@QEAAHIW4D3DWDDM2_0DDI_CONTEXTTYPE_FLAG@@@Z; NDXGI::CDevice::Flush(uint,D3DWDDM2_0DDI_CONTEXTTYPE_FLAG)
0x1800bd9c9  mov     r8d, 4
0x1800bd9cf  mov     dl, 9
0x1800bd9d1  mov     rcx, [rsi+38h]
0x1800bd9d5  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800bd9da  test    al, al
0x1800bd9dc  jz      short loc_1800BDA13
0x1800bd9de  lea     rbx, [rsi+770h]
0x1800bd9e5  mov     rdx, rdi
0x1800bd9e8  mov     rcx, rbx; lpCriticalSection
0x1800bd9eb  call    ??$AcquireToken@U_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAPEAXAEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::AcquireToken<_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3>(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const &)
0x1800bd9f0  mov     rdi, rax
0x1800bd9f3  mov     rdx, rax
0x1800bd9f6  mov     rcx, rbx; lpCriticalSection
0x1800bd9f9  call    NDXGI__OpaqueHandleManager_BatchablePresentMPO___GetDataFromToken__lambda_95231fb00a59257dd4369b31f9f035e4___
0x1800bd9fe  mov     r13, rax
0x1800bda01  jmp     short loc_1800BDA16
0x1800bda03  mov     eax, [rsp+968h+var_938]
0x1800bda07  jmp     short loc_1800BDA0E
0x1800bda09  mov     eax, 8007000Eh
0x1800bda0e  jmp     loc_1800BDEB3
0x1800bda13  mov     r13, rdi
0x1800bda16  mov     [rsp+968h+var_938], 1
0x1800bda1e  lea     r8, [rsp+968h+var_938]
0x1800bda23  lea     rdx, [rsp+968h+var_848]
0x1800bda2b  lea     rcx, [rsp+968h+var_888]
0x1800bda33  call    ??$fill@PEAW4DXGI_DDI_MODE_ROTATION@@W41@@std@@YAXQEAW4DXGI_DDI_MODE_ROTATION@@0AEBW41@@Z; std::fill<DXGI_DDI_MODE_ROTATION *,DXGI_DDI_MODE_ROTATION>(DXGI_DDI_MODE_ROTATION * const,DXGI_DDI_MODE_ROTATION * const,DXGI_DDI_MODE_ROTATION const &)
0x1800bda38  mov     r14d, [r13+18h]
0x1800bda3c  mov     dword ptr [rsp+968h+var_930], r14d
0x1800bda41  mov     [rsp+968h+var_928], 0
0x1800bda4a  mov     r9, [rsi+818h]
0x1800bda51  mov     rdx, [r9]
0x1800bda54  lea     rcx, [rsp+968h+var_928]
0x1800bda59  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800bda5e  mov     r8, rax
0x1800bda61  mov     rax, [rdx]
0x1800bda64  lea     rdx, _GUID_36871736_2446_4858_8473_99bd44555307
0x1800bda6b  mov     rcx, r9
0x1800bda6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda73  mov     ecx, eax; int
0x1800bda75  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800bda7a  mov     rcx, [rsp+968h+var_928]
0x1800bda7f  mov     rax, [rcx]
0x1800bda82  mov     rax, [rax+98h]
0x1800bda89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bda8e  mov     rbx, rax
0x1800bda91  mov     [rsp+968h+var_920], 0
0x1800bda9a  mov     r9, [rsi+810h]
0x1800bdaa1  mov     rdx, [r9]
0x1800bdaa4  lea     rcx, [rsp+968h+var_920]
0x1800bdaa9  call    ??$IID_PPV_ARGS_Helper@UID3D11UnorderedAccessView@@@@YAPEAPEAXPEAPEAUID3D11UnorderedAccessView@@@Z; IID_PPV_ARGS_Helper<ID3D11UnorderedAccessView>(ID3D11UnorderedAccessView * *)
0x1800bdaae  mov     r8, rax
0x1800bdab1  mov     rax, [rdx+8]
0x1800bdab5  lea     rdx, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x1800bdabc  mov     rcx, r9
0x1800bdabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdac4  mov     ecx, eax; int
0x1800bdac6  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800bdacb  mov     rcx, [rsp+968h+var_928]
0x1800bdad0  mov     rax, [rcx]
0x1800bdad3  mov     rdx, [rsp+968h+var_920]
0x1800bdad8  mov     rax, [rax+0A8h]
0x1800bdadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdae4  mov     [rsp+968h+var_910], rax
0x1800bdae9  xorps   xmm0, xmm0
0x1800bdaec  movdqu  [rsp+968h+var_8E8], xmm0
0x1800bdaf5  xorps   xmm1, xmm1
0x1800bdaf8  movdqu  [rsp+968h+var_8D8], xmm1
0x1800bdb01  mov     [rsp+968h+var_8F8], rbx
0x1800bdb06  mov     [rsp+968h+var_8F0], rdi
0x1800bdb0b  mov     eax, [r13+10h]
0x1800bdb0f  mov     dword ptr [rsp+968h+var_8E8], eax
0x1800bdb16  mov     r8d, 2
0x1800bdb1c  mov     dword ptr [rsp+968h+var_8E8+4], r8d
0x1800bdb24  lea     rax, [rsp+968h+var_888]
0x1800bdb2c  mov     qword ptr [rsp+968h+var_8D8+8], rax
0x1800bdb34  xor     edi, edi
0x1800bdb36  cmp     [r13+1Ch], edi
0x1800bdb3a  jbe     short loc_1800BDB82
0x1800bdb3c  mov     rcx, [r13+20h]
0x1800bdb40  test    rcx, rcx
0x1800bdb43  jz      short loc_1800BDB82
0x1800bdb45  mov     rcx, [rcx]
0x1800bdb48  mov     edx, [rcx+8]
0x1800bdb4b  test    edx, edx
0x1800bdb4d  jz      short loc_1800BDB8D
0x1800bdb4f  sub     edx, 1
0x1800bdb52  jz      short loc_1800BDB82
0x1800bdb54  sub     edx, 1
0x1800bdb57  jz      short loc_1800BDB78
0x1800bdb59  cmp     edx, 1
0x1800bdb5c  jz      short loc_1800BDB6B
0x1800bdb5e  mov     dword ptr [rsp+968h+var_8E8+8], 4
0x1800bdb69  jmp     short loc_1800BDB8D
0x1800bdb6b  mov     dword ptr [rsp+968h+var_8E8+8], 3
0x1800bdb76  jmp     short loc_1800BDB8D
0x1800bdb78  mov     dword ptr [rsp+968h+var_8E8+8], r8d
0x1800bdb80  jmp     short loc_1800BDB8D
0x1800bdb82  mov     dword ptr [rsp+968h+var_8E8+8], 1
0x1800bdb8d  mov     [rsp+968h+var_938], edi
0x1800bdb91  test    r15d, r15d
0x1800bdb94  jz      loc_1800BDC91
0x1800bdb9a  mov     r13, rdi
0x1800bdb9d  imul    rax, r13, 88h
0x1800bdba4  mov     [rsp+968h+var_918], rax
0x1800bdba9  mov     r14, r13
0x1800bdbac  shl     r14, 7
0x1800bdbb0  mov     ebx, [rax+r12]
0x1800bdbb4  cmp     [rax+r12+4], edi
0x1800bdbb9  jz      loc_1800BDC53
0x1800bdbbf  mov     [rsp+r14+968h+var_848], ebx
0x1800bdbc7  mov     [rsp+r14+968h+var_844], 1
0x1800bdbd3  mov     rax, [rax+r12+8]
0x1800bdbd8  mov     rcx, [rsp+968h+var_908]
0x1800bdbdd  test    rax, rax
0x1800bdbe0  cmovnz  rcx, rax
0x1800bdbe4  mov     rdi, [rsp+968h+var_928]
0x1800bdbe9  mov     rax, [rdi]
0x1800bdbec  mov     rbx, [rax+0A0h]
0x1800bdbf3  mov     rcx, [rcx+88h]
0x1800bdbfa  mov     rdx, [rcx]
0x1800bdbfd  mov     rax, [rdx]
0x1800bdc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc05  mov     rdx, rax
0x1800bdc08  mov     rcx, rdi
0x1800bdc0b  mov     rax, rbx
0x1800bdc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdc13  mov     [rsp+r14+968h+var_840], rax
0x1800bdc1b  mov     rcx, [rsp+968h+var_918]
0x1800bdc20  mov     eax, [rcx+r12+10h]
0x1800bdc25  mov     [rsp+r14+968h+var_838], eax
0x1800bdc2d  mov     r8, [rsi+38h]
0x1800bdc31  lea     rdx, [rsp+968h+var_830]
0x1800bdc39  add     rdx, r14
0x1800bdc3c  add     rcx, 18h
0x1800bdc40  add     rcx, r12
0x1800bdc43  mov     r8d, [r8+464h]
0x1800bdc4a  call    ?ConvertToDDI@CDevice@NDXGI@@KAXPEBUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@PEAUDXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES1@@W4_D3D_DRIVER_DDI_VERSION@@@Z; NDXGI::CDevice::ConvertToDDI(DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES const *,DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES1 *,_D3D_DRIVER_DDI_VERSION)
0x1800bdc4f  xor     edi, edi
0x1800bdc51  jmp     short loc_1800BDC76
0x1800bdc53  lea     rcx, [rsp+r14+968h+var_844]; void *
0x1800bdc5b  xor     edx, edx; Val
0x1800bdc5d  lea     r8d, [rdx+7Ch]; Size
0x1800bdc61  call    memset_0
0x1800bdc66  mov     [rsp+r14+968h+var_848], ebx
0x1800bdc6e  mov     [rsp+r14+968h+var_844], edi
0x1800bdc76  mov     ecx, [rsp+968h+var_938]
0x1800bdc7a  inc     ecx
0x1800bdc7c  mov     [rsp+968h+var_938], ecx
0x1800bdc80  inc     r13
0x1800bdc83  cmp     ecx, r15d
0x1800bdc86  jb      loc_1800BDB9D
0x1800bdc8c  mov     r14d, dword ptr [rsp+968h+var_930]
0x1800bdc91  mov     dword ptr [rsp+968h+var_8E8+0Ch], r15d
0x1800bdc99  lea     rax, [rsp+968h+var_848]
0x1800bdca1  mov     qword ptr [rsp+968h+var_8D8], rax
0x1800bdca9  mov     rdx, [rsi+38h]
0x1800bdcad  mov     byte ptr [rsp+968h+var_948], dil; bool
0x1800bdcb2  xor     r9d, r9d; bool
0x1800bdcb5  mov     r8b, 1; bool
0x1800bdcb8  mov     rdx, [rdx+438h]; struct CContext *
0x1800bdcbf  lea     rcx, [rsp+968h+var_8B0]; this
0x1800bdcc7  call    ??$?0VCContext@@@CDevCtxInterface@@QEAA@PEAVCContext@@_N11@Z; CDevCtxInterface::CDevCtxInterface(CContext *,bool,bool,bool)
0x1800bdccc  nop
0x1800bdccd  mov     [rsp+968h+var_930], 0
0x1800bdcd6  lea     rbx, [rsi+528h]
0x1800bdcdd  mov     [rsp+968h+var_918], rbx
0x1800bdce2  mov     rcx, rbx; SRWLock
0x1800bdce5  call    cs:__imp_AcquireSRWLockExclusive
0x1800bdceb  nop
0x1800bdcec  lea     r15, [rsi+530h]
0x1800bdcf3  call    cs:__imp_GetCurrentThreadId
0x1800bdcf9  mov     dword ptr [rsp+968h+var_908], eax
0x1800bdcfd  lea     rax, [rsp+968h+var_930]
0x1800bdd02  mov     [rsp+968h+var_900], rax
0x1800bdd07  lea     r8, [rsp+968h+var_908]
0x1800bdd0c  lea     rdx, [rsp+968h+var_8C0]
0x1800bdd14  mov     rcx, r15
0x1800bdd17  call    ??$emplace@U?$pair@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@?$_Hash@V?$_Umap_traits@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@1@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::emplace<std::pair<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *>>(std::pair<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *> &&)
0x1800bdd1c  nop
0x1800bdd1d  test    rbx, rbx
0x1800bdd20  jz      short loc_1800BDD2C
0x1800bdd22  mov     rcx, rbx; SRWLock
0x1800bdd25  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bdd2b  nop
0x1800bdd2c  lea     r9, ?PresentMultiplaneOverlay1CB@CDevice@NDXGIOn12@@SAJPEAXPEBUDXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1@@@Z; NDXGIOn12::CDevice::PresentMultiplaneOverlay1CB(void *,DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY1 const *)
0x1800bdd33  mov     r8, [rsp+968h+var_910]
0x1800bdd38  lea     rdx, [rsi-10h]
0x1800bdd3c  lea     rcx, [rsp+968h+var_8F8]
0x1800bdd41  mov     rax, [rsi+840h]
0x1800bdd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd4d  mov     edi, eax
0x1800bdd4f  mov     rcx, rbx; SRWLock
0x1800bdd52  call    cs:__imp_AcquireSRWLockExclusive
0x1800bdd58  mov     r8, [rsp+968h+var_8C0]
0x1800bdd60  lea     rdx, [rsp+968h+var_910]
0x1800bdd65  mov     rcx, r15
0x1800bdd68  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@KPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSPresentCBThreadLocalData@CDevice@NDXGI@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<ulong,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,NDXGI::CDevice::SPresentCBThreadLocalData *>>>>)
0x1800bdd6d  test    rbx, rbx
0x1800bdd70  jz      short loc_1800BDD7B
0x1800bdd72  mov     rcx, rbx; SRWLock
0x1800bdd75  call    cs:__imp_ReleaseSRWLockExclusive
0x1800bdd7b  mov     eax, 88760870h
0x1800bdd80  cmp     edi, eax
0x1800bdd82  jz      loc_1800BDE3D
0x1800bdd88  test    edi, edi
0x1800bdd8a  jz      short loc_1800BDDA1
0x1800bdd8c  mov     edx, edi; int
0x1800bdd8e  lea     rcx, [rsi-10h]; this
0x1800bdd92  call    ?DriverInternalError@CDevice@NDXGI@@QEAAXJ@Z; NDXGI::CDevice::DriverInternalError(long)
0x1800bdd97  mov     ebx, 887A0005h
0x1800bdd9c  jmp     loc_1800BDE57
0x1800bdda1  cmp     dword ptr [rsp+968h+var_930], eax
0x1800bdda5  jz      loc_1800BDE3D
0x1800bddab  mov     eax, dword ptr [rsp+968h+var_930+4]
0x1800bddaf  mov     ecx, 0C01E000Bh
0x1800bddb4  cmp     eax, ecx
0x1800bddb6  jg      short loc_1800BDDEE
0x1800bddb8  jz      short loc_1800BDDE7
0x1800bddba  cmp     eax, 0C000000Dh
0x1800bddbf  jz      short loc_1800BDD97
0x1800bddc1  cmp     eax, 0C01E0000h
0x1800bddc6  jz      short loc_1800BDDD9
0x1800bddc8  cmp     eax, 0C01E0005h
0x1800bddcd  jz      short loc_1800BDDE0
0x1800bddcf  add     eax, 3FE1FFFAh
0x1800bddd4  cmp     eax, 1
0x1800bddd7  ja      short loc_1800BDE0A
0x1800bddd9  mov     ebx, 87A0001h
0x1800bddde  jmp     short loc_1800BDE57
0x1800bdde0  mov     ebx, 87A0007h
0x1800bdde5  jmp     short loc_1800BDE57
0x1800bdde7  mov     ebx, 87A0004h
0x1800bddec  jmp     short loc_1800BDE57
0x1800bddee  cmp     eax, 0C01E0018h
0x1800bddf3  jz      short loc_1800BDE23
0x1800bddf5  cmp     eax, 0C01E0102h
0x1800bddfa  jz      short loc_1800BDE1C
0x1800bddfc  cmp     eax, 0C01E0342h
0x1800bde01  jz      short loc_1800BDE15
0x1800bde03  cmp     eax, 103h
0x1800bde08  jz      short loc_1800BDE0E
0x1800bde0a  xor     ebx, ebx
  ... truncated ...
```
