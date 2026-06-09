# NDXGI::CDevice::PresentMultiplaneOverlay(IDXGIResource *,uint,_DXGI_PRESENT_MULTIPLANE_OVERLAY const *,void *)

- ea: `0x180098550`
- end: `0x180099042`
- name: `?PresentMultiplaneOverlay@CDevice@NDXGI@@UEAAJPEAUIDXGIResource@@IPEBU_DXGI_PRESENT_MULTIPLANE_OVERLAY@@PEAX@Z`
- size: `2802`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, struct IDXGIResource *, unsigned int, const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800bd8f0`

## callees

- `0x18002d0f0`
- `0x18002d174`
- `0x18002e220`
- `0x18002fde0`
- `0x180037290`
- `0x1800438e0`
- `0x180053c88`
- `0x180058970`
- `0x1800608b4`
- `0x1800608c4`
- `0x180074d78`
- `0x1800964b0`
- `0x180098550`
- `0x18009f7e8`
- `0x1800a9d20`
- `0x1800aa9a8`
- `0x1800b76b0`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098bb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098d6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098666`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098666`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098601`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098601`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098e73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098e73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098d60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098df3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098d60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180098df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall NDXGI::CDevice::PresentMultiplaneOverlay(
        NDXGI::CDevice *this,
        struct IDXGIResource *a2,
        unsigned int a3,
        const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *a4,
        unsigned int *a5)
{
  unsigned int v5; // r13d
  HANDLE v7; // rbx
  __int64 v9; // r14
  unsigned int *v10; // r15
  struct IErrorInfo *v11; // r8
  bool v12; // r9
  __int64 *v13; // rdx
  __int64 *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rcx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edi
  unsigned int v21; // r12d
  __int64 v22; // r15
  const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *v23; // rcx
  char *v24; // r14
  __int64 v25; // rbx
  int v26; // eax
  void (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v28; // rcx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  unsigned int v32; // r12d
  __int64 v33; // r15
  const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *v34; // rcx
  char *v35; // r14
  __int64 v36; // rbx
  int v37; // eax
  void (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // rcx
  int v39; // ebx
  __int64 v40; // r12
  unsigned int v41; // r14d
  __int64 v42; // r12
  const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *v43; // rcx
  char *v44; // r15
  __int64 v45; // r13
  __int64 v46; // rbx
  _QWORD *v47; // rbx
  RTL_SRWLOCK *v48; // r14
  _QWORD *v49; // r15
  DWORD CurrentThreadId; // eax
  int v51; // eax
  int v52; // r13d
  _QWORD *v53; // rdx
  _QWORD *v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  int v57; // eax
  unsigned int v58; // [rsp+40h] [rbp-978h]
  int v59; // [rsp+40h] [rbp-978h]
  __int64 v60; // [rsp+48h] [rbp-970h] BYREF
  int v61; // [rsp+50h] [rbp-968h] BYREF
  unsigned int v62; // [rsp+54h] [rbp-964h]
  const struct _DXGI_PRESENT_MULTIPLANE_OVERLAY *v63; // [rsp+58h] [rbp-960h]
  struct IDXGIResource *v64; // [rsp+60h] [rbp-958h] BYREF
  __int128 v65; // [rsp+68h] [rbp-950h] BYREF
  __int128 v66; // [rsp+78h] [rbp-940h]
  __int128 v67; // [rsp+88h] [rbp-930h]
  unsigned int *v68; // [rsp+98h] [rbp-920h]
  _QWORD *v69; // [rsp+A0h] [rbp-918h]
  _QWORD *v70; // [rsp+A8h] [rbp-910h] BYREF
  _QWORD v71[3]; // [rsp+B8h] [rbp-900h] BYREF
  int v72; // [rsp+D0h] [rbp-8E8h]
  __int64 v73; // [rsp+D4h] [rbp-8E4h]
  _QWORD v74[4]; // [rsp+E0h] [rbp-8D8h] BYREF
  int v75; // [rsp+100h] [rbp-8B8h]
  _com_error *v76; // [rsp+108h] [rbp-8B0h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+110h] [rbp-8A8h] BYREF
  _DWORD v78[512]; // [rsp+130h] [rbp-888h] BYREF
  _OWORD v79[4]; // [rsp+930h] [rbp-88h] BYREF

  v63 = a4;
  v5 = a3;
  v62 = a3;
  v64 = a2;
  v7 = a5;
  if ( *((int *)this + 308) < 0 )
    return 2289696773LL;
  v9 = *((_QWORD *)this + 7);
  if ( *(_BYTE *)(v9 + 1112) > 9u
    || *(_BYTE *)(v9 + 1112) == 9 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 1232) + 96LL) + 912LL)) >= 4u )
  {
    try
    {
      v7 = NDXGI::OpaqueHandleManager<BatchablePresentMPO>::AcquireToken<_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3>(
             (LPCRITICAL_SECTION)((char *)this + 1904),
             (__int64)a5);
      v69 = (_QWORD *)((char *)this + 1904);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1904));
      v13 = (__int64 *)*((_QWORD *)this + 243);
      v14 = (__int64 *)v13[1];
      LODWORD(v73) = 0;
      v15 = v13;
      while ( !*((_BYTE *)v14 + 25) )
      {
        if ( v14[4] >= (unsigned __int64)v7 )
        {
          v15 = v14;
          v14 = (__int64 *)*v14;
        }
        else
        {
          v14 = (__int64 *)v14[2];
        }
      }
      if ( *((_BYTE *)v15 + 25) || (unsigned __int64)v7 < v15[4] || v15 == v13 )
      {
        _com_error::_com_error((_com_error *)pExceptionObject, -2147024809, v11, v12);
        throw (_com_error *)pExceptionObject;
      }
      v10 = (unsigned int *)v15[5];
      v68 = v10;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1904));
      v9 = *((_QWORD *)this + 7);
    }
    catch ( _com_error *v76 )
    {
      return *((unsigned int *)v76 + 2);
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
  }
  else
  {
    v10 = a5;
    v68 = a5;
  }
  v65 = 0;
  v66 = 0;
  v67 = 0;
  memset_0(v78, 0, sizeof(v78));
  v61 = 1;
  if ( (unsigned __int8)std::_Is_all_bits_zero<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN>(&v61) )
  {
    std::_Fill_zero_memset<enum D3DWDDM2_0DDI_SWIZZLE_PATTERN *>(v79, 16);
  }
  else
  {
    v79[0] = _mm_load_si128((const __m128i *)&_xmm);
    v79[1] = v79[0];
    v79[2] = v79[0];
    v79[3] = v79[0];
    v9 = *((_QWORD *)this + 7);
  }
  v58 = v10[6];
  if ( *(int *)(v9 + 1124) >= 4 && *((_QWORD *)this + 103) )
  {
    *(_QWORD *)&v65 = *((_QWORD *)this + 82);
    *((_QWORD *)&v65 + 1) = v7;
    LODWORD(v66) = v10[4];
    DWORD1(v66) = 2;
    *((_QWORD *)&v67 + 1) = v79;
    if ( !v10[7] )
      goto LABEL_30;
    v16 = *((_QWORD *)v10 + 4);
    if ( !v16 )
      goto LABEL_30;
    v17 = *(_DWORD *)(*(_QWORD *)v16 + 8LL);
    if ( !v17 )
      goto LABEL_31;
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 == 1 )
          DWORD2(v66) = 3;
        else
          DWORD2(v66) = 4;
      }
      else
      {
        DWORD2(v66) = 2;
      }
    }
    else
    {
LABEL_30:
      DWORD2(v66) = 1;
    }
LABEL_31:
    v20 = 0;
    v61 = 0;
    v21 = 0;
    if ( v5 )
    {
      v22 = 0;
      v23 = v63;
      do
      {
        v24 = (char *)v23 + 136 * v22;
        v25 = v22 << 7;
        v26 = *(_DWORD *)v24;
        if ( *((_DWORD *)v24 + 1) )
        {
          v78[32 * v22] = v26;
          v78[32 * v22 + 1] = 1;
          v27 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))v64;
          if ( *((_QWORD *)v24 + 1) )
            v27 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v24 + 1);
          v60 = 0;
          (**v27)(v27, &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea, &v60);
          (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 24LL))(v60, (char *)&v78[2] + v25);
          if ( v60 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
          v78[32 * v22 + 4] = *((_DWORD *)v24 + 4);
          NDXGI::CDevice::ConvertToDDI(
            v24 + 24,
            (char *)&v78[6] + v25,
            *(unsigned int *)(*((_QWORD *)this + 7) + 1124LL));
          v23 = v63;
        }
        else
        {
          *(_OWORD *)&v78[32 * v22 + 1] = 0;
          *(_OWORD *)&v78[32 * v22 + 5] = 0;
          *(_OWORD *)&v78[32 * v22 + 9] = 0;
          *(_OWORD *)&v78[32 * v22 + 13] = 0;
          *(_OWORD *)&v78[32 * v22 + 17] = 0;
          *(_OWORD *)&v78[32 * v22 + 21] = 0;
          *(_OWORD *)&v78[32 * v22 + 25] = 0;
          *(_OWORD *)&v78[32 * v22 + 28] = 0;
          v78[32 * v22] = v26;
          v78[32 * v22 + 1] = 0;
        }
        ++v21;
        ++v22;
      }
      while ( v21 < v5 );
      v9 = *((_QWORD *)this + 7);
    }
    goto LABEL_65;
  }
  if ( !*((_QWORD *)this + 97) )
    return (unsigned int)-2147467263;
  *(_QWORD *)&v65 = *((_QWORD *)this + 82);
  *((_QWORD *)&v65 + 1) = v7;
  LODWORD(v66) = v10[4];
  DWORD1(v66) = 2;
  if ( !v10[7] || (v28 = *((_QWORD *)v10 + 4)) == 0 )
  {
LABEL_52:
    DWORD2(v66) = 1;
    goto LABEL_53;
  }
  v29 = *(_DWORD *)(*(_QWORD *)v28 + 8LL);
  if ( v29 )
  {
    v30 = v29 - 1;
    if ( v30 )
    {
      v31 = v30 - 1;
      if ( v31 )
      {
        if ( v31 == 1 )
          DWORD2(v66) = 3;
        else
          DWORD2(v66) = 4;
      }
      else
      {
        DWORD2(v66) = 2;
      }
      goto LABEL_53;
    }
    goto LABEL_52;
  }
LABEL_53:
  v20 = 0;
  v32 = 0;
  if ( v5 )
  {
    v33 = 0;
    v34 = v63;
    do
    {
      v35 = (char *)v34 + 136 * v33;
      v36 = v33 << 7;
      v37 = *(_DWORD *)v35;
      if ( *((_DWORD *)v35 + 1) )
      {
        v78[32 * v33] = v37;
        v78[32 * v33 + 1] = 1;
        v38 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))v64;
        if ( *((_QWORD *)v35 + 1) )
          v38 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v35 + 1);
        v60 = 0;
        (**v38)(v38, &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea, &v60);
        (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v60 + 24LL))(v60, (char *)&v78[2] + v36);
        if ( v60 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
        v78[32 * v33 + 4] = *((_DWORD *)v35 + 4);
        NDXGI::CDevice::ConvertToDDI(
          (const struct DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES *)(v35 + 24),
          (struct DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES *)((char *)&v78[6] + v36));
        v34 = v63;
      }
      else
      {
        *(_OWORD *)&v78[32 * v33 + 1] = 0;
        *(_OWORD *)&v78[32 * v33 + 5] = 0;
        *(_OWORD *)&v78[32 * v33 + 9] = 0;
        *(_OWORD *)&v78[32 * v33 + 13] = 0;
        *(_OWORD *)&v78[32 * v33 + 17] = 0;
        *(_OWORD *)&v78[32 * v33 + 21] = 0;
        *(_OWORD *)&v78[32 * v33 + 25] = 0;
        *(_OWORD *)&v78[32 * v33 + 28] = 0;
        v78[32 * v33] = v37;
        v78[32 * v33 + 1] = 0;
      }
      ++v32;
      ++v33;
    }
    while ( v32 < v5 );
    v9 = *((_QWORD *)this + 7);
  }
  v61 = 1;
LABEL_65:
  *(_QWORD *)&v67 = v78;
  HIDWORD(v66) = v5;
  v39 = v58 & 0x400;
  v59 = v39;
  v40 = *(_QWORD *)(v9 + 1080);
  v74[0] = v40;
  v74[1] = 0;
  v74[2] = CContext::AcquireDevCtxIfaceNoSync((CContext *)v40, 0);
  v74[3] = v40 + 264;
  v75 = 2;
  v60 = 0;
  if ( *(_BYTE *)(*((_QWORD *)this + 7) + 1112LL) >= 0xFu )
  {
    v41 = 0;
    if ( v5 )
    {
      v42 = 0;
      v43 = v63;
      while ( 1 )
      {
        v44 = (char *)v43 + 136 * v42;
        if ( !*((_DWORD *)v44 + 1) || !v39 && *((_QWORD *)v44 + 1) )
          goto LABEL_77;
        LODWORD(v64) = 0;
        v45 = *(_QWORD *)(*((_QWORD *)this + 7) + 1080LL);
        v71[2] = v45;
        v72 = *(_DWORD *)(v45 + 3688);
        v46 = *(_QWORD *)(v45 + 3692);
        v73 = v46;
        *(_DWORD *)(v45 + 3688) = GetCurrentThreadId();
        *(_BYTE *)(v45 + 3692) = 1;
        *(_WORD *)(v45 + 3693) = *(_WORD *)((char *)&v70 + 1);
        *(_BYTE *)(v45 + 3695) = BYTE3(v70);
        *(_DWORD *)(v45 + 3696) = 0;
        v70 = (_QWORD *)(v42 << 7);
        v71[0] = &v78[32 * v42 + 4];
        v69 = &v78[32 * v42 + 2];
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int, struct IDXGIResource **))(v45 + 2872))(
          *(_QWORD *)(*((_QWORD *)this + 7) + 1080LL) + 40768LL,
          *v69,
          *(unsigned int *)v71[0],
          v68[4],
          v41,
          &v64);
        if ( ((unsigned __int8)v64 & 1) != 0 )
          break;
        if ( ((unsigned __int8)v64 & 2) != 0 )
        {
          if ( (v44[24] & 0x10) == 0 )
            break;
          *(_DWORD *)((char *)&v78[6] + (_QWORD)v70) |= 8u;
          DWORD1(v66) |= 0x40u;
        }
LABEL_76:
        *(_DWORD *)(v45 + 3688) = v72;
        *(_QWORD *)(v45 + 3692) = v46;
        v5 = v62;
        v43 = v63;
        v39 = v59;
LABEL_77:
        ++v41;
        ++v42;
        if ( v41 >= v5 )
        {
          v40 = v74[0];
          goto LABEL_79;
        }
      }
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int, char *))(v45 + 2880))(
        *(_QWORD *)(*((_QWORD *)this + 7) + 1080LL) + 40768LL,
        *v69,
        *(unsigned int *)v71[0],
        v68[4],
        v41,
        (char *)&v78[7] + (_QWORD)v70);
      goto LABEL_76;
    }
  }
LABEL_79:
  if ( *((_BYTE *)this + 882) )
  {
    v47 = 0;
    *((_QWORD *)this + 174) = &v60;
    v48 = (RTL_SRWLOCK *)((char *)this + 1320);
    v49 = (_QWORD *)((char *)this + 1328);
    goto LABEL_84;
  }
  v48 = (RTL_SRWLOCK *)((char *)this + 1320);
  v69 = (_QWORD *)((char *)this + 1320);
  AcquireSRWLockExclusive((PSRWLOCK)this + 165);
  v49 = (_QWORD *)((char *)this + 1328);
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    LODWORD(v71[0]) = CurrentThreadId;
    v71[1] = &v60;
    std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *>>(
      (char *)this + 1328,
      &v70,
      v71);
    v47 = v70;
    if ( this != (NDXGI::CDevice *)-1320LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 165);
  }
  catch ( std::bad_alloc )
  {
    CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v74);
    return 2147942414LL;
  }
LABEL_84:
  if ( v61 )
    v51 = (*((__int64 (__fastcall **)(__int128 *))this + 97))(&v65);
  else
    v51 = (*((__int64 (__fastcall **)(__int128 *))this + 103))(&v65);
  v52 = v51;
  if ( *((_BYTE *)this + 882) )
  {
    *((_QWORD *)this + 174) = 0;
  }
  else
  {
    AcquireSRWLockExclusive(v48);
    v53 = (_QWORD *)(v49[3] + 16 * (std::_Hash_representation<unsigned long>(v47 + 2) & v49[6]));
    v54 = (_QWORD *)*v53;
    if ( (_QWORD *)v53[1] == v47 )
    {
      if ( v54 == v47 )
      {
        v55 = v49[1];
        *v53 = v55;
      }
      else
      {
        v55 = v47[1];
      }
      v53[1] = v55;
    }
    else if ( v54 == v47 )
    {
      *v53 = *v47;
    }
    v56 = *v47;
    --v49[2];
    *(_QWORD *)v47[1] = v56;
    *(_QWORD *)(v56 + 8) = v47[1];
    SmallDDIElLayout::operator delete(v47, 0x20u);
    if ( v48 )
      ReleaseSRWLockExclusive(v48);
  }
  if ( v52 == -2005530512 )
    goto LABEL_128;
  if ( v52 )
  {
    NDXGI::CDevice::DriverInternalError((NDXGI::CDevice *)((char *)this - 16), v52);
    v20 = -2005270523;
    goto LABEL_129;
  }
  if ( (_DWORD)v60 == -2005530512 )
  {
LABEL_128:
    v20 = -2005270523;
    (*(void (__fastcall **)(NDXGI::CDevice *))(*(_QWORD *)this + 264LL))(this);
    goto LABEL_129;
  }
  if ( SHIDWORD(v60) > -1071775733 )
  {
    switch ( HIDWORD(v60) )
    {
      case 0xC01E0018:
        v20 = 142213127;
        if ( v59 )
          v20 = -2005270428;
        break;
      case 0xC01E0019:
        v57 = -2005270427;
        if ( !v59 )
          v57 = 142213127;
        v20 = v57;
        break;
      case 0xC01E0102:
        v20 = -2005270518;
        break;
      case 0xC01E0342:
        v20 = 142213126;
        break;
      case 0x103:
        v20 = 142213130;
        break;
    }
  }
  else
  {
    switch ( HIDWORD(v60) )
    {
      case 0xC01E000B:
        v20 = 142213124;
        break;
      case 0xC000000D:
        v20 = -2147024809;
        if ( !v59 )
          v20 = -2005270523;
        break;
      case 0xC01E0000:
        goto LABEL_108;
      case 0xC01E0005:
        v20 = 142213127;
        break;
      default:
        if ( (unsigned int)(HIDWORD(v60) + 1071775738) <= 1 )
LABEL_108:
          v20 = 142213121;
        break;
    }
  }
LABEL_129:
  --*(_DWORD *)(v40 + 39632);
  if ( !*(_DWORD *)(v40 + 3712) && !*(_DWORD *)(v40 + 39632) )
  {
    if ( *(_BYTE *)(v40 + 256) )
      CDDISync::CSingleThreadedLowFreqLock::Leave(*(struct CDevice **)(v40 + 160));
  }
  if ( v20 >= 0 )
  {
    CDevice::IncrementConservativeFlushCount(*((CDevice **)this + 7));
    return (unsigned int)v20;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180098550  push    rbx
0x180098552  push    rsi
0x180098553  push    rdi
0x180098554  push    r12
0x180098556  push    r13
0x180098558  push    r14
0x18009855a  push    r15
0x18009855c  sub     rsp, 980h
0x180098563  mov     rax, cs:__security_cookie
0x18009856a  xor     rax, rsp
0x18009856d  mov     [rsp+9B8h+var_48], rax
0x180098575  mov     [rsp+9B8h+var_960], r9
0x18009857a  mov     r13d, r8d
0x18009857d  mov     [rsp+9B8h+var_964], r8d
0x180098582  mov     [rsp+9B8h+var_958], rdx
0x180098587  mov     rsi, rcx
0x18009858a  mov     rbx, [rsp+9B8h+arg_20]
0x180098592  mov     eax, [rcx+4D0h]
0x180098598  test    eax, eax
0x18009859a  jns     short loc_1800985A6
0x18009859c  mov     eax, 887A0005h
0x1800985a1  jmp     loc_180098FF7
0x1800985a6  mov     r14, [rcx+38h]
0x1800985aa  cmp     byte ptr [r14+458h], 9
0x1800985b2  ja      short loc_1800985E1
0x1800985b4  jnz     short loc_1800985D1
0x1800985b6  mov     rax, [r14+4D0h]
0x1800985bd  mov     rcx, [rax+60h]
0x1800985c1  mov     eax, [rcx+390h]
0x1800985c7  shr     rax, 10h
0x1800985cb  cmp     ax, 4
0x1800985cf  jnb     short loc_1800985E1
0x1800985d1  mov     r15, rbx
0x1800985d4  mov     [rsp+9B8h+var_920], rbx
0x1800985dc  jmp     loc_180098670
0x1800985e1  lea     rdi, [rsi+770h]
0x1800985e8  mov     rdx, rbx
0x1800985eb  mov     rcx, rdi; lpCriticalSection
0x1800985ee  call    ??$AcquireToken@U_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@@?$OpaqueHandleManager@UBatchablePresentMPO@@@NDXGI@@QEAAPEAXAEBU_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3@@@Z; NDXGI::OpaqueHandleManager<BatchablePresentMPO>::AcquireToken<_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3>(_D3DKMT_PRESENT_MULTIPLANE_OVERLAY3 const &)
0x1800985f3  mov     rbx, rax
0x1800985f6  mov     [rsp+9B8h+var_918], rdi
0x1800985fe  mov     rcx, rdi; lpCriticalSection
0x180098601  call    cs:__imp_EnterCriticalSection
0x180098607  nop
0x180098608  mov     rdx, [rdi+28h]
0x18009860c  mov     rax, [rdx+8]
0x180098610  xor     ecx, ecx
0x180098612  mov     dword ptr [rsp+9B8h+var_8E4], ecx
0x180098619  mov     rcx, rdx
0x18009861c  cmp     byte ptr [rax+19h], 0
0x180098620  jnz     short loc_18009863A
0x180098622  cmp     [rax+20h], rbx
0x180098626  jnb     short loc_18009862E
0x180098628  mov     rax, [rax+10h]
0x18009862c  jmp     short loc_180098634
0x18009862e  mov     rcx, rax
0x180098631  mov     rax, [rax]
0x180098634  cmp     byte ptr [rax+19h], 0
0x180098638  jz      short loc_180098622
0x18009863a  cmp     byte ptr [rcx+19h], 0
0x18009863e  jnz     loc_18009901A
0x180098644  cmp     rbx, [rcx+20h]
0x180098648  jb      loc_18009901A
0x18009864e  cmp     rcx, rdx
0x180098651  jz      loc_18009901A
0x180098657  mov     r15, [rcx+28h]
0x18009865b  mov     [rsp+9B8h+var_920], r15
0x180098663  mov     rcx, rdi; lpCriticalSection
0x180098666  call    cs:__imp_LeaveCriticalSection
0x18009866c  mov     r14, [rsi+38h]
0x180098670  xorps   xmm0, xmm0
0x180098673  movups  [rsp+9B8h+var_950], xmm0
0x180098678  movups  [rsp+9B8h+var_940], xmm0
0x18009867d  movups  [rsp+9B8h+var_930], xmm0
0x180098685  xor     edx, edx; Val
0x180098687  mov     r8d, 800h; Size
0x18009868d  lea     rcx, [rsp+9B8h+var_888]; void *
0x180098695  call    memset_0
0x18009869a  mov     [rsp+9B8h+var_968], 1
0x1800986a2  lea     rcx, [rsp+9B8h+var_968]
0x1800986a7  call    ??$_Is_all_bits_zero@W4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@std@@YA_NAEBW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@Z; std::_Is_all_bits_zero<D3DWDDM2_0DDI_SWIZZLE_PATTERN>(D3DWDDM2_0DDI_SWIZZLE_PATTERN const &)
0x1800986ac  test    al, al
0x1800986ae  jz      short loc_1800986D0
0x1800986b0  mov     edx, 10h
0x1800986b5  lea     rcx, [rsp+9B8h+var_88]
0x1800986bd  call    ??$_Fill_zero_memset@PEAW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@@std@@YAXPEAW4D3DWDDM2_0DDI_SWIZZLE_PATTERN@@_K@Z; std::_Fill_zero_memset<D3DWDDM2_0DDI_SWIZZLE_PATTERN *>(D3DWDDM2_0DDI_SWIZZLE_PATTERN *,unsigned __int64)
0x1800986c2  jmp     short loc_1800986FC
0x1800986d0  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x1800986d8  movups  [rsp+9B8h+var_88], xmm0
0x1800986e0  movups  [rsp+9B8h+var_78], xmm0
0x1800986e8  movups  [rsp+9B8h+var_68], xmm0
0x1800986f0  movups  [rsp+9B8h+var_58], xmm0
0x1800986f8  mov     r14, [rsi+38h]
0x1800986fc  mov     ecx, [r15+18h]
0x180098700  mov     [rsp+9B8h+var_978], ecx
0x180098704  cmp     dword ptr [r14+464h], 4
0x18009870c  jl      loc_1800988FB
0x180098712  cmp     qword ptr [rsi+338h], 0
0x18009871a  jz      loc_1800988FB
0x180098720  mov     rax, [rsi+290h]
0x180098727  mov     qword ptr [rsp+9B8h+var_950], rax
0x18009872c  mov     qword ptr [rsp+9B8h+var_950+8], rbx
0x180098731  mov     eax, [r15+10h]
0x180098735  mov     dword ptr [rsp+9B8h+var_940], eax
0x180098739  mov     dword ptr [rsp+9B8h+var_940+4], 2
0x180098741  lea     rax, [rsp+9B8h+var_88]
0x180098749  mov     qword ptr [rsp+9B8h+var_930+8], rax
0x180098751  cmp     dword ptr [r15+1Ch], 0
0x180098756  jbe     short loc_1800987A1
0x180098758  mov     rcx, [r15+20h]
0x18009875c  test    rcx, rcx
0x18009875f  jz      short loc_1800987A1
0x180098761  mov     rcx, [rcx]
0x180098764  mov     edx, [rcx+8]
0x180098767  test    edx, edx
0x180098769  jz      short loc_1800987AC
0x18009876b  sub     edx, 1
0x18009876e  jz      short loc_1800987A1
0x180098770  sub     edx, 1
0x180098773  jz      short loc_180098794
0x180098775  cmp     edx, 1
0x180098778  jz      short loc_180098787
0x18009877a  mov     dword ptr [rsp+9B8h+var_940+8], 4
0x180098785  jmp     short loc_1800987AC
0x180098787  mov     dword ptr [rsp+9B8h+var_940+8], 3
0x180098792  jmp     short loc_1800987AC
0x180098794  mov     dword ptr [rsp+9B8h+var_940+8], 2
0x18009879f  jmp     short loc_1800987AC
0x1800987a1  mov     dword ptr [rsp+9B8h+var_940+8], 1
0x1800987ac  xor     edi, edi
0x1800987ae  mov     [rsp+9B8h+var_968], edi
0x1800987b2  mov     r12d, edi
0x1800987b5  test    r13d, r13d
0x1800987b8  jz      loc_180098AC3
0x1800987be  mov     r15d, edi
0x1800987c1  mov     rcx, [rsp+9B8h+var_960]
0x1800987c6  nop     word ptr [rax+rax+00000000h]
0x1800987d0  imul    r14, r15, 88h
0x1800987d7  add     r14, rcx
0x1800987da  mov     rbx, r15
0x1800987dd  shl     rbx, 7
0x1800987e1  mov     eax, [r14]
0x1800987e4  cmp     dword ptr [r14+4], 0
0x1800987e9  jz      loc_180098892
0x1800987ef  mov     [rsp+rbx+9B8h+var_888], eax
0x1800987f6  mov     dword ptr [rsp+rbx+9B8h+var_884], 1
0x180098801  mov     rax, [r14+8]
0x180098805  mov     rcx, [rsp+9B8h+var_958]
0x18009880a  test    rax, rax
0x18009880d  cmovnz  rcx, rax
0x180098811  mov     [rsp+9B8h+var_970], rdi
0x180098816  mov     rax, [rcx]
0x180098819  lea     r8, [rsp+9B8h+var_970]
0x18009881e  lea     rdx, _GUID_79d2046c_22ef_451b_9e74_2245d9c760ea
0x180098825  mov     rax, [rax]
0x180098828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009882d  mov     rcx, [rsp+9B8h+var_970]
0x180098832  mov     rax, [rcx]
0x180098835  lea     rdx, [rsp+9B8h+var_884+4]
0x18009883d  add     rdx, rbx
0x180098840  mov     rax, [rax+18h]
0x180098844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098849  nop
0x18009884a  mov     rcx, [rsp+9B8h+var_970]
0x18009884f  test    rcx, rcx
0x180098852  jz      short loc_180098861
0x180098854  mov     rax, [rcx]
0x180098857  mov     rax, [rax+10h]
0x18009885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098860  nop
0x180098861  mov     eax, [r14+10h]
0x180098865  mov     dword ptr [rsp+rbx+9B8h+var_884+0Ch], eax
0x18009886c  mov     r8, [rsi+38h]
0x180098870  lea     rdx, [rsp+9B8h+var_870]
0x180098878  add     rdx, rbx
0x18009887b  lea     rcx, [r14+18h]
0x18009887f  mov     r8d, [r8+464h]
0x180098886  call    ?ConvertToDDI@CDevice@NDXGI@@KAXPEBUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@PEAUDXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES1@@W4_D3D_DRIVER_DDI_VERSION@@@Z; NDXGI::CDevice::ConvertToDDI(DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES const *,DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES1 *,_D3D_DRIVER_DDI_VERSION)
0x18009888b  mov     rcx, [rsp+9B8h+var_960]
0x180098890  jmp     short loc_1800988E3
0x180098892  xorps   xmm0, xmm0
0x180098895  movups  [rsp+rbx+9B8h+var_884], xmm0
0x18009889d  movups  xmmword ptr [rsp+rbx+144h], xmm0
0x1800988a5  movups  [rsp+rbx+9B8h+var_864], xmm0
0x1800988ad  movups  [rsp+rbx+9B8h+var_854], xmm0
0x1800988b5  movups  [rsp+rbx+9B8h+var_844], xmm0
0x1800988bd  movups  [rsp+rbx+9B8h+var_834], xmm0
0x1800988c5  movups  [rsp+rbx+9B8h+var_824], xmm0
0x1800988cd  movups  [rsp+rbx+9B8h+var_824+0Ch], xmm0
0x1800988d5  mov     [rsp+rbx+9B8h+var_888], eax
0x1800988dc  mov     dword ptr [rsp+rbx+9B8h+var_884], edi
0x1800988e3  inc     r12d
0x1800988e6  inc     r15
0x1800988e9  cmp     r12d, r13d
0x1800988ec  jb      loc_1800987D0
0x1800988f2  mov     r14, [rsi+38h]
0x1800988f6  jmp     loc_180098AC3
0x1800988fb  cmp     qword ptr [rsi+308h], 0
0x180098903  jz      loc_180098FE3
0x180098909  mov     rax, [rsi+290h]
0x180098910  mov     qword ptr [rsp+9B8h+var_950], rax
0x180098915  mov     qword ptr [rsp+9B8h+var_950+8], rbx
0x18009891a  mov     eax, [r15+10h]
0x18009891e  mov     dword ptr [rsp+9B8h+var_940], eax
0x180098922  mov     dword ptr [rsp+9B8h+var_940+4], 2
0x18009892a  cmp     dword ptr [r15+1Ch], 0
0x18009892f  jbe     short loc_18009897A
0x180098931  mov     rcx, [r15+20h]
0x180098935  test    rcx, rcx
0x180098938  jz      short loc_18009897A
0x18009893a  mov     rcx, [rcx]
0x18009893d  mov     edx, [rcx+8]
0x180098940  test    edx, edx
0x180098942  jz      short loc_180098985
0x180098944  sub     edx, 1
0x180098947  jz      short loc_18009897A
0x180098949  sub     edx, 1
0x18009894c  jz      short loc_18009896D
0x18009894e  cmp     edx, 1
0x180098951  jz      short loc_180098960
0x180098953  mov     dword ptr [rsp+9B8h+var_940+8], 4
0x18009895e  jmp     short loc_180098985
0x180098960  mov     dword ptr [rsp+9B8h+var_940+8], 3
0x18009896b  jmp     short loc_180098985
0x18009896d  mov     dword ptr [rsp+9B8h+var_940+8], 2
0x180098978  jmp     short loc_180098985
0x18009897a  mov     dword ptr [rsp+9B8h+var_940+8], 1
0x180098985  xor     edi, edi
0x180098987  mov     r12d, edi
0x18009898a  test    r13d, r13d
0x18009898d  jz      loc_180098ABB
0x180098993  mov     r15d, edi
0x180098996  mov     rcx, [rsp+9B8h+var_960]
0x18009899b  nop     dword ptr [rax+rax+00h]
0x1800989a0  imul    r14, r15, 88h
0x1800989a7  add     r14, rcx
0x1800989aa  mov     rbx, r15
0x1800989ad  shl     rbx, 7
0x1800989b1  mov     eax, [r14]
0x1800989b4  cmp     dword ptr [r14+4], 0
0x1800989b9  jz      loc_180098A57
0x1800989bf  mov     [rsp+rbx+9B8h+var_888], eax
0x1800989c6  mov     dword ptr [rsp+rbx+9B8h+var_884], 1
0x1800989d1  mov     rax, [r14+8]
0x1800989d5  mov     rcx, [rsp+9B8h+var_958]
0x1800989da  test    rax, rax
0x1800989dd  cmovnz  rcx, rax
0x1800989e1  mov     [rsp+9B8h+var_970], rdi
0x1800989e6  mov     rax, [rcx]
0x1800989e9  lea     r8, [rsp+9B8h+var_970]
0x1800989ee  lea     rdx, _GUID_79d2046c_22ef_451b_9e74_2245d9c760ea
0x1800989f5  mov     rax, [rax]
0x1800989f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800989fd  mov     rcx, [rsp+9B8h+var_970]
0x180098a02  mov     rax, [rcx]
0x180098a05  lea     rdx, [rsp+9B8h+var_884+4]
0x180098a0d  add     rdx, rbx
0x180098a10  mov     rax, [rax+18h]
0x180098a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a19  nop
0x180098a1a  mov     rcx, [rsp+9B8h+var_970]
0x180098a1f  test    rcx, rcx
0x180098a22  jz      short loc_180098A31
0x180098a24  mov     rax, [rcx]
0x180098a27  mov     rax, [rax+10h]
0x180098a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098a30  nop
0x180098a31  mov     eax, [r14+10h]
0x180098a35  mov     dword ptr [rsp+rbx+9B8h+var_884+0Ch], eax
0x180098a3c  lea     rdx, [rsp+9B8h+var_870]
0x180098a44  add     rdx, rbx; struct DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES *
0x180098a47  lea     rcx, [r14+18h]; struct DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES *
0x180098a4b  call    ?ConvertToDDI@CDevice@NDXGI@@KAXPEBUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@PEAUDXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES@@@Z; NDXGI::CDevice::ConvertToDDI(DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES const *,DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES *)
0x180098a50  mov     rcx, [rsp+9B8h+var_960]
0x180098a55  jmp     short loc_180098AA8
0x180098a57  xorps   xmm0, xmm0
0x180098a5a  movups  [rsp+rbx+9B8h+var_884], xmm0
0x180098a62  movups  xmmword ptr [rsp+rbx+144h], xmm0
0x180098a6a  movups  [rsp+rbx+9B8h+var_864], xmm0
0x180098a72  movups  [rsp+rbx+9B8h+var_854], xmm0
0x180098a7a  movups  [rsp+rbx+9B8h+var_844], xmm0
0x180098a82  movups  [rsp+rbx+9B8h+var_834], xmm0
0x180098a8a  movups  [rsp+rbx+9B8h+var_824], xmm0
0x180098a92  movups  [rsp+rbx+9B8h+var_824+0Ch], xmm0
0x180098a9a  mov     [rsp+rbx+9B8h+var_888], eax
0x180098aa1  mov     dword ptr [rsp+rbx+9B8h+var_884], edi
0x180098aa8  inc     r12d
0x180098aab  inc     r15
0x180098aae  cmp     r12d, r13d
0x180098ab1  jb      loc_1800989A0
0x180098ab7  mov     r14, [rsi+38h]
0x180098abb  mov     [rsp+9B8h+var_968], 1
0x180098ac3  lea     rax, [rsp+9B8h+var_888]
0x180098acb  mov     qword ptr [rsp+9B8h+var_930], rax
0x180098ad3  mov     dword ptr [rsp+9B8h+var_940+0Ch], r13d
0x180098adb  mov     ebx, [rsp+9B8h+var_978]
0x180098adf  and     ebx, 400h
0x180098ae5  mov     [rsp+9B8h+var_978], ebx
0x180098ae9  mov     r12, [r14+438h]
0x180098af0  mov     [rsp+9B8h+var_8D8], r12
  ... truncated ...
```
