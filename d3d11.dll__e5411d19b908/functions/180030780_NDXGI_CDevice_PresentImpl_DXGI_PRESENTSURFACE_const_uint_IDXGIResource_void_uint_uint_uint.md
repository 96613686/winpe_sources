# NDXGI::CDevice::PresentImpl(DXGI_PRESENTSURFACE const *,uint,IDXGIResource *,void *,uint,uint,uint *)

- ea: `0x180030780`
- end: `0x180031c95`
- name: `?PresentImpl@CDevice@NDXGI@@QEAAJPEBUDXGI_PRESENTSURFACE@@IPEAUIDXGIResource@@PEAXIIPEAI@Z`
- size: `5397`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, const struct DXGI_PRESENTSURFACE *, unsigned int, struct IDXGIResource *, struct _D3DKMT_PRESENT *, __int16, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800303a0`

## callees

- `0x180011080`
- `0x180024944`
- `0x18002d0f0`
- `0x18002e220`
- `0x18002fde0`
- `0x180030710`
- `0x180030780`
- `0x1800354b8`
- `0x180037290`
- `0x1800438e0`
- `0x18004a7d4`
- `0x180053c88`
- `0x180068db0`
- `0x18006c60c`
- `0x18006f298`
- `0x18006f344`
- `0x180074d78`
- `0x180078640`
- `0x1800924a4`
- `0x18009f7e8`
- `0x1800a5600`
- `0x1800bc008`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003149e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800316cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003149e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800316cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800310d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030c20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031068`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800310d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030d20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003107e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800308e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030d20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003107e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031715`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031a3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031715`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031a3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800316c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800319b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800316c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800319b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800312ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031b05`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800312ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031b05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031574`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031b1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031574`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180031b1c`
- `win32u!NtNotifyPresentToCompositionSurface` at `0x180031331`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::PresentImpl(
        NDXGI::CDevice *this,
        const struct DXGI_PRESENTSURFACE *a2,
        unsigned int a3,
        struct IDXGIResource *a4,
        struct _D3DKMT_PRESENT *a5,
        __int16 a6,
        unsigned int a7,
        unsigned int *a8)
{
  NDXGI::CDevice *v8; // r13
  int v9; // r14d
  __int64 v10; // rcx
  struct _D3DKMT_PRESENT *v11; // r15
  volatile signed __int32 *v12; // r14
  volatile signed __int32 *v13; // rax
  volatile signed __int32 *v14; // rdi
  char *v15; // rbx
  __int64 *v16; // r15
  __int64 *v17; // rax
  __int64 *v18; // rcx
  __int64 *v19; // rsi
  __int64 **v20; // rdx
  __int64 ***v21; // r9
  __int64 *v22; // rcx
  __int64 *v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 **v26; // r8
  __int64 ***v27; // rax
  _QWORD *v28; // rcx
  _QWORD *v29; // r8
  __int64 v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // r8
  __int64 v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  __int64 v36; // rbx
  struct IErrorInfo *v37; // r8
  bool v38; // r9
  __int64 *v39; // rcx
  __int64 *v40; // rax
  __int64 *v41; // r14
  __int64 v42; // rax
  std::_Ref_count_base *v43; // rbx
  char *v44; // rdi
  __int64 *v45; // r15
  HANDLE **v46; // rax
  HANDLE **v47; // rcx
  HANDLE **v48; // rsi
  HANDLE *v49; // rbx
  HANDLE **v50; // r8
  HANDLE **v51; // rcx
  __int64 *v52; // rdx
  _QWORD **v53; // rax
  __int64 v54; // rax
  HANDLE *v55; // rdx
  HANDLE **v56; // rax
  _QWORD *v57; // rcx
  _QWORD *v58; // rdx
  __int64 v59; // rax
  _QWORD *v60; // rax
  HANDLE *v61; // rdx
  _QWORD *v62; // rax
  HANDLE **v63; // rax
  _QWORD *v64; // rax
  unsigned __int64 v65; // rbx
  struct IErrorInfo *v66; // r8
  bool v67; // r9
  _QWORD *v68; // rcx
  __int64 *v69; // rax
  _QWORD *v70; // r15
  char v71; // si
  __int64 v72; // rdx
  __int64 v73; // r9
  void *v74; // rdi
  bool v75; // bl
  void *v76; // rax
  DWORD v77; // edx
  int v79; // ebx
  _QWORD *v80; // rdi
  int v81; // esi
  CContext *v82; // rbx
  __int64 v83; // rdx
  unsigned int v84; // r13d
  __int64 v85; // rdi
  __int64 v86; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v88; // rbx
  _DWORD *v89; // rax
  char v90; // r9
  __int64 v91; // r8
  const struct DXGI_PRESENTSURFACE *v92; // r15
  char *v93; // rbx
  unsigned __int64 v94; // rax
  unsigned int i; // r9d
  char *v96; // r10
  unsigned int v97; // edx
  unsigned int v98; // ebx
  char *v99; // rdx
  _QWORD *v100; // r8
  _QWORD *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rdx
  HANDLE v104; // rbx
  bool v105; // cc
  int *v106; // rdx
  int v107; // eax
  __int64 v108; // [rsp+0h] [rbp-1E8h] BYREF
  _QWORD v109[2]; // [rsp+40h] [rbp-1A8h] BYREF
  __int64 v110; // [rsp+50h] [rbp-198h] BYREF
  const struct DXGI_PRESENTSURFACE *v111; // [rsp+58h] [rbp-190h]
  unsigned int v112; // [rsp+60h] [rbp-188h]
  __int128 v113; // [rsp+64h] [rbp-184h] BYREF
  __int128 v114; // [rsp+74h] [rbp-174h]
  int v115; // [rsp+84h] [rbp-164h]
  int v116; // [rsp+88h] [rbp-160h]
  __int128 v117; // [rsp+8Ch] [rbp-15Ch]
  int v118; // [rsp+9Ch] [rbp-14Ch]
  _QWORD v119[2]; // [rsp+A0h] [rbp-148h] BYREF
  volatile signed __int32 *v120; // [rsp+B0h] [rbp-138h] BYREF
  volatile signed __int32 *v121; // [rsp+B8h] [rbp-130h]
  std::_Ref_count_base *v122[2]; // [rsp+C0h] [rbp-128h]
  __int64 v123; // [rsp+D0h] [rbp-118h] BYREF
  HANDLE hHandle; // [rsp+D8h] [rbp-110h]
  __int64 v125; // [rsp+E0h] [rbp-108h]
  __int64 v126; // [rsp+E8h] [rbp-100h]
  int v127; // [rsp+F0h] [rbp-F8h]
  __int64 v128; // [rsp+F4h] [rbp-F4h]
  __int64 v129; // [rsp+100h] [rbp-E8h] BYREF
  __int64 v130; // [rsp+108h] [rbp-E0h]
  __int64 v131; // [rsp+110h] [rbp-D8h]
  __int64 v132; // [rsp+118h] [rbp-D0h]
  int v133; // [rsp+120h] [rbp-C8h]
  int v134; // [rsp+124h] [rbp-C4h]
  __int64 v135; // [rsp+128h] [rbp-C0h]
  int v136; // [rsp+130h] [rbp-B8h]
  int v137; // [rsp+134h] [rbp-B4h]
  _QWORD v138[4]; // [rsp+138h] [rbp-B0h] BYREF
  int v139; // [rsp+158h] [rbp-90h]
  _com_error *v140; // [rsp+160h] [rbp-88h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+168h] [rbp-80h] BYREF
  _BYTE v142[96]; // [rsp+188h] [rbp-60h] BYREF
  void *v144; // [rsp+1F0h] [rbp+8h]
  unsigned int v147; // [rsp+200h] [rbp+18h]

  v8 = this;
  v9 = 0;
  v113 = 0u;
  v114 = 0u;
  v115 = 0;
  v117 = 0u;
  v110 = *((_QWORD *)this + 84);
  v111 = a2;
  v112 = a3;
  v118 = 1;
  v116 = 1;
  *(_OWORD *)v122 = 0;
  v10 = *((_QWORD *)this + 9);
  if ( *(_BYTE *)(v10 + 1112) <= 9u
    && (*(_BYTE *)(v10 + 1112) != 9 || HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 1232) + 96LL) + 912LL)) < 4u) )
  {
    v11 = a5;
    *(_QWORD *)((char *)&v114 + 4) = a5;
    v12 = (volatile signed __int32 *)v122[1];
    goto LABEL_330;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl) )
    {
      v13 = (volatile signed __int32 *)operator new(0x30u);
      v14 = v13;
      v120 = v13;
      if ( v13 )
      {
        *((_DWORD *)v13 + 2) = 1;
        *((_DWORD *)v13 + 3) = 1;
        *(_QWORD *)v13 = &std::_Ref_count_obj2<BatchablePresent>::`vftable';
        hHandle = (HANDLE)(v13 + 4);
        *((_QWORD *)v13 + 2) = 0;
        *((_QWORD *)v13 + 3) = 0;
        *((_QWORD *)v13 + 4) = 0;
        *((_QWORD *)v13 + 5) = 0;
        BatchablePresent::Initialize((LPHANDLE)v13 + 2, a5);
      }
      else
      {
        v14 = 0;
      }
      v120 = v14 + 4;
      v121 = v14;
      a5 = (NDXGI::CDevice *)((char *)v8 + 1792);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1792));
      v15 = (char *)v8 + 1832;
      v16 = (__int64 *)*((_QWORD *)v8 + 229);
      v17 = (__int64 *)v16[1];
      LODWORD(v128) = 0;
      v18 = v16;
      if ( *((_BYTE *)v17 + 25) )
      {
        v19 = v17;
      }
      else
      {
        do
        {
          v19 = v17;
          if ( (unsigned __int64)v17[4] >= *((_QWORD *)v8 + 231) )
          {
            v9 = 1;
            v18 = v17;
            v17 = (__int64 *)*v17;
          }
          else
          {
            v9 = 0;
            v17 = (__int64 *)v17[2];
          }
        }
        while ( !*((_BYTE *)v17 + 25) );
      }
      if ( !*((_BYTE *)v18 + 25) && *((_QWORD *)v8 + 231) >= (unsigned __int64)v18[4] )
        goto LABEL_71;
      if ( *((_QWORD *)v8 + 230) == 0x492492492492492LL )
        std::_Throw_tree_length_error();
      hHandle = (char *)v8 + 1832;
      v125 = 0;
      v20 = (__int64 **)operator new(0x38u);
      v20[4] = (__int64 *)*((_QWORD *)v8 + 231);
      v20[5] = 0;
      v20[6] = 0;
      if ( v14 )
        _InterlockedIncrement(v14 + 2);
      v20[5] = (__int64 *)(v14 + 4);
      v20[6] = (__int64 *)v14;
      *v20 = v16;
      v20[1] = v16;
      v20[2] = v16;
      *((_WORD *)v20 + 12) = 0;
      ++*((_QWORD *)v8 + 230);
      v21 = *(__int64 ****)v15;
      v20[1] = v19;
      if ( v19 == (__int64 *)v21 )
      {
        *v21 = v20;
        v21[1] = v20;
        v21[2] = v20;
        *((_BYTE *)v20 + 24) = 1;
        goto LABEL_71;
      }
      if ( v9 )
      {
        *v19 = (__int64)v20;
        if ( v19 == (__int64 *)*v21 )
          *v21 = v20;
      }
      else
      {
        v19[2] = (__int64)v20;
        if ( v19 == (__int64 *)v21[2] )
          v21[2] = v20;
      }
      if ( *((_BYTE *)v20[1] + 24) )
      {
LABEL_70:
        *((_BYTE *)v21[1] + 24) = 1;
LABEL_71:
        v36 = *((_QWORD *)v8 + 231);
        *((_QWORD *)v8 + 231) = v36 + 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1792));
        *(_QWORD *)((char *)&v114 + 4) = v36;
        if ( v14 )
        {
          if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        a5 = (NDXGI::CDevice *)((char *)v8 + 1792);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1792));
        v39 = (__int64 *)*((_QWORD *)v8 + 229);
        v40 = (__int64 *)v39[1];
        LODWORD(v128) = 0;
        v41 = v39;
        while ( !*((_BYTE *)v40 + 25) )
        {
          if ( (unsigned __int64)v40[4] >= *(_QWORD *)((char *)&v114 + 4) )
          {
            v41 = v40;
            v40 = (__int64 *)*v40;
          }
          else
          {
            v40 = (__int64 *)v40[2];
          }
        }
        if ( *((_BYTE *)v41 + 25) || *(_QWORD *)((char *)&v114 + 4) < (unsigned __int64)v41[4] )
          v41 = v39;
        if ( v41 == v39 )
        {
          _com_error::_com_error((_com_error *)pExceptionObject, -2147024809, v37, v38);
          throw (_com_error *)pExceptionObject;
        }
        v42 = v41[6];
        if ( v42 )
          _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
        v43 = (std::_Ref_count_base *)v41[5];
        v12 = (volatile signed __int32 *)v41[6];
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1792));
        v122[0] = v43;
        v122[1] = (std::_Ref_count_base *)v12;
        v11 = (struct _D3DKMT_PRESENT *)*((_QWORD *)v43 + 3);
        goto LABEL_330;
      }
      while ( 1 )
      {
        v22 = v20[1];
        v23 = (__int64 *)v22[1];
        v24 = *v23;
        if ( v22 == (__int64 *)*v23 )
        {
          v25 = v23[2];
          if ( *(_BYTE *)(v25 + 24) )
          {
            v26 = (__int64 **)v22[2];
            if ( v20 == v26 )
            {
              v20 = (__int64 **)v20[1];
              v22[2] = (__int64)*v26;
              if ( !*((_BYTE *)*v26 + 25) )
                (*v26)[1] = (__int64)v22;
              v26[1] = (__int64 *)v22[1];
              if ( v22 == *(__int64 **)(*(_QWORD *)v15 + 8LL) )
              {
                *(_QWORD *)(*(_QWORD *)v15 + 8LL) = v26;
              }
              else
              {
                v27 = (__int64 ***)v22[1];
                if ( v22 == (__int64 *)*v27 )
                  *v27 = v26;
                else
                  v27[2] = v26;
              }
              *v26 = v22;
              v22[1] = (__int64)v26;
            }
            *((_BYTE *)v20[1] + 24) = 1;
            *(_BYTE *)(v20[1][1] + 24) = 0;
            v28 = (_QWORD *)v20[1][1];
            v29 = (_QWORD *)*v28;
            *v28 = *(_QWORD *)(*v28 + 16LL);
            v30 = v29[2];
            if ( !*(_BYTE *)(v30 + 25) )
              *(_QWORD *)(v30 + 8) = v28;
            v29[1] = v28[1];
            if ( v28 == *(_QWORD **)(*(_QWORD *)v15 + 8LL) )
            {
              *(_QWORD *)(*(_QWORD *)v15 + 8LL) = v29;
              v29[2] = v28;
            }
            else
            {
              v31 = (_QWORD *)v28[1];
              if ( v28 == (_QWORD *)v31[2] )
                v31[2] = v29;
              else
                *v31 = v29;
              v29[2] = v28;
            }
LABEL_68:
            v28[1] = v29;
            goto LABEL_69;
          }
          *((_BYTE *)v22 + 24) = 1;
          *(_BYTE *)(v25 + 24) = 1;
          *(_BYTE *)(v20[1][1] + 24) = 0;
          v20 = (__int64 **)v20[1][1];
        }
        else
        {
          if ( *(_BYTE *)(v24 + 24) )
          {
            v32 = (_QWORD *)*v22;
            if ( v20 == (__int64 **)*v22 )
            {
              v20 = (__int64 **)v20[1];
              *v22 = v32[2];
              v33 = v32[2];
              if ( !*(_BYTE *)(v33 + 25) )
                *(_QWORD *)(v33 + 8) = v22;
              v32[1] = v22[1];
              if ( v22 == *(__int64 **)(*(_QWORD *)v15 + 8LL) )
              {
                *(_QWORD *)(*(_QWORD *)v15 + 8LL) = v32;
              }
              else
              {
                v34 = (_QWORD *)v22[1];
                if ( v22 == (__int64 *)v34[2] )
                  v34[2] = v32;
                else
                  *v34 = v32;
              }
              v32[2] = v22;
              v22[1] = (__int64)v32;
            }
            *((_BYTE *)v20[1] + 24) = 1;
            *(_BYTE *)(v20[1][1] + 24) = 0;
            v28 = (_QWORD *)v20[1][1];
            v29 = (_QWORD *)v28[2];
            v28[2] = *v29;
            if ( !*(_BYTE *)(*v29 + 25LL) )
              *(_QWORD *)(*v29 + 8LL) = v28;
            v29[1] = v28[1];
            if ( v28 == *(_QWORD **)(*(_QWORD *)v15 + 8LL) )
            {
              *(_QWORD *)(*(_QWORD *)v15 + 8LL) = v29;
            }
            else
            {
              v35 = (_QWORD *)v28[1];
              if ( v28 == (_QWORD *)*v35 )
                *v35 = v29;
              else
                v35[2] = v29;
            }
            *v29 = v28;
            goto LABEL_68;
          }
          *((_BYTE *)v22 + 24) = 1;
          *(_BYTE *)(v24 + 24) = 1;
          *(_BYTE *)(v20[1][1] + 24) = 0;
          v20 = (__int64 **)v20[1][1];
        }
LABEL_69:
        if ( *((_BYTE *)v20[1] + 24) )
          goto LABEL_70;
      }
    }
    v120 = (volatile signed __int32 *)((char *)v8 + 1856);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1856));
    v44 = (char *)v8 + 1896;
    v45 = (__int64 *)*((_QWORD *)v8 + 237);
    v46 = (HANDLE **)v45[1];
    LODWORD(v128) = 0;
    v47 = (HANDLE **)v45;
    if ( *((_BYTE *)v46 + 25) )
    {
      v48 = v46;
    }
    else
    {
      do
      {
        v48 = v46;
        if ( (unsigned __int64)v46[4] >= *((_QWORD *)v8 + 239) )
        {
          v9 = 1;
          v47 = v46;
          v46 = (HANDLE **)*v46;
        }
        else
        {
          v9 = 0;
          v46 = (HANDLE **)v46[2];
        }
      }
      while ( !*((_BYTE *)v46 + 25) );
    }
    if ( !*((_BYTE *)v47 + 25) && *((_QWORD *)v8 + 239) >= (unsigned __int64)v47[4] )
      goto LABEL_147;
    if ( *((_QWORD *)v8 + 238) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v119[0] = (char *)v8 + 1896;
    v49 = (HANDLE *)operator new(0x48u);
    v119[1] = v49;
    v49[4] = (HANDLE)*((_QWORD *)v8 + 239);
    hHandle = v49 + 5;
    v49[5] = 0;
    v49[6] = 0;
    v49[7] = 0;
    v49[8] = 0;
    BatchablePresent::Initialize(v49 + 5, a5);
    *v49 = v45;
    v49[1] = v45;
    v49[2] = v45;
    *((_WORD *)v49 + 12) = 0;
    ++*((_QWORD *)v8 + 238);
    v50 = *(HANDLE ***)v44;
    v49[1] = v48;
    if ( v48 == v50 )
    {
      *v50 = v49;
      v50[1] = v49;
      v50[2] = v49;
      *((_BYTE *)v49 + 24) = 1;
LABEL_147:
      v65 = *((_QWORD *)v8 + 239);
      *((_QWORD *)v8 + 239) = v65 + 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1856));
      *(_QWORD *)((char *)&v114 + 4) = v65;
      a5 = (NDXGI::CDevice *)((char *)v8 + 1856);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1856));
      v68 = *(_QWORD **)v44;
      v69 = *(__int64 **)(*(_QWORD *)v44 + 8LL);
      LODWORD(v128) = 0;
      v70 = v68;
      while ( !*((_BYTE *)v69 + 25) )
      {
        if ( v69[4] >= v65 )
        {
          v70 = v69;
          v69 = (__int64 *)*v69;
        }
        else
        {
          v69 = (__int64 *)v69[2];
        }
      }
      if ( *((_BYTE *)v70 + 25) || v65 < v70[4] )
        v70 = v68;
      if ( v70 == v68 )
      {
        _com_error::_com_error((_com_error *)v142, -2147024809, v66, v67);
        throw (_com_error *)v142;
      }
      v11 = (struct _D3DKMT_PRESENT *)v70[8];
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1856));
      v12 = (volatile signed __int32 *)v122[1];
      goto LABEL_330;
    }
    if ( v9 )
    {
      *v48 = v49;
      if ( v48 == (HANDLE **)*v50 )
        *v50 = v49;
    }
    else
    {
      v48[2] = v49;
      if ( v48 == (HANDLE **)v50[2] )
        v50[2] = v49;
    }
    if ( *((_BYTE *)v49[1] + 24) )
    {
LABEL_146:
      *((_BYTE *)v50[1] + 24) = 1;
      goto LABEL_147;
    }
    while ( 1 )
    {
      v51 = (HANDLE **)v49[1];
      v52 = (__int64 *)v51[1];
      v53 = (_QWORD **)*v52;
      if ( v51 == (HANDLE **)*v52 )
      {
        v54 = v52[2];
        if ( *(_BYTE *)(v54 + 24) )
        {
          v55 = v51[2];
          if ( v49 == v55 )
          {
            v49 = (HANDLE *)v49[1];
            v51[2] = (HANDLE *)*v55;
            if ( !*((_BYTE *)*v55 + 25) )
              *((_QWORD *)*v55 + 1) = v51;
            v55[1] = v51[1];
            if ( v51 == *(HANDLE ***)(*(_QWORD *)v44 + 8LL) )
            {
              *(_QWORD *)(*(_QWORD *)v44 + 8LL) = v55;
            }
            else
            {
              v56 = (HANDLE **)v51[1];
              if ( v51 == (HANDLE **)*v56 )
                *v56 = v55;
              else
                v56[2] = v55;
            }
            *v55 = v51;
            v51[1] = v55;
          }
          *((_BYTE *)v49[1] + 24) = 1;
          *(_BYTE *)(*((_QWORD *)v49[1] + 1) + 24LL) = 0;
          v57 = (_QWORD *)*((_QWORD *)v49[1] + 1);
          v58 = (_QWORD *)*v57;
          *v57 = *(_QWORD *)(*v57 + 16LL);
          v59 = v58[2];
          if ( !*(_BYTE *)(v59 + 25) )
            *(_QWORD *)(v59 + 8) = v57;
          v58[1] = v57[1];
          if ( v57 == *(_QWORD **)(*(_QWORD *)v44 + 8LL) )
          {
            *(_QWORD *)(*(_QWORD *)v44 + 8LL) = v58;
            v58[2] = v57;
          }
          else
          {
            v60 = (_QWORD *)v57[1];
            if ( v57 == (_QWORD *)v60[2] )
              v60[2] = v58;
            else
              *v60 = v58;
            v58[2] = v57;
          }
LABEL_144:
          v57[1] = v58;
          goto LABEL_145;
        }
        *((_BYTE *)v51 + 24) = 1;
        *(_BYTE *)(v54 + 24) = 1;
        *(_BYTE *)(*((_QWORD *)v49[1] + 1) + 24LL) = 0;
        v49 = (HANDLE *)*((_QWORD *)v49[1] + 1);
      }
      else
      {
        if ( *((_BYTE *)v53 + 24) )
        {
          v61 = *v51;
          if ( v49 == *v51 )
          {
            v49 = (HANDLE *)v49[1];
            *v51 = (HANDLE *)v61[2];
            v62 = v61[2];
            if ( !*((_BYTE *)v62 + 25) )
              v62[1] = v51;
            v61[1] = v51[1];
            if ( v51 == *(HANDLE ***)(*(_QWORD *)v44 + 8LL) )
            {
              *(_QWORD *)(*(_QWORD *)v44 + 8LL) = v61;
            }
            else
            {
              v63 = (HANDLE **)v51[1];
              if ( v51 == (HANDLE **)v63[2] )
                v63[2] = v61;
              else
                *v63 = v61;
            }
            v61[2] = v51;
            v51[1] = v61;
          }
          *((_BYTE *)v49[1] + 24) = 1;
          *(_BYTE *)(*((_QWORD *)v49[1] + 1) + 24LL) = 0;
          v57 = (_QWORD *)*((_QWORD *)v49[1] + 1);
          v58 = (_QWORD *)v57[2];
          v57[2] = *v58;
          if ( !*(_BYTE *)(*v58 + 25LL) )
            *(_QWORD *)(*v58 + 8LL) = v57;
          v58[1] = v57[1];
          if ( v57 == *(_QWORD **)(*(_QWORD *)v44 + 8LL) )
          {
            *(_QWORD *)(*(_QWORD *)v44 + 8LL) = v58;
          }
          else
          {
            v64 = (_QWORD *)v57[1];
            if ( v57 == (_QWORD *)*v64 )
              *v64 = v58;
            else
              v64[2] = v58;
          }
          *v58 = v57;
          goto LABEL_144;
        }
        *((_BYTE *)v51 + 24) = 1;
        *((_BYTE *)v53 + 24) = 1;
        *(_BYTE *)(*((_QWORD *)v49[1] + 1) + 24LL) = 0;
        v49 = (HANDLE *)*((_QWORD *)v49[1] + 1);
      }
LABEL_145:
      if ( *((_BYTE *)v49[1] + 24) )
        goto LABEL_146;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v140) )
    {
      v147 = *((_DWORD *)v140 + 2);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_180031BF5);
      if ( v122[1] )
        std::_Ref_count_base::_Decref(v122[1]);
      return v147;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180031C10);
LABEL_321:
      if ( v122[1] )
        std::_Ref_count_base::_Decref(v122[1]);
      return 2147942414LL;
    }
  }
LABEL_330:
  v71 = a6;
  if ( (a6 & 7) == 2 )
    v72 = HIDWORD(v114) | 2u;
  else
    v72 = HIDWORD(v114) | 1u;
  HIDWORD(v114) = v72;
  v73 = *((_QWORD *)v8 + 9);
  if ( *(_BYTE *)(v73 + 1112) > 5u
    || *(_BYTE *)(v73 + 1112) == 5 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v73 + 1232) + 96LL) + 912LL)) )
  {
    v72 = (unsigned int)v72 ^ ((unsigned __int8)v72 ^ (unsigned __int8)(*((_DWORD *)v11 + 22) >> 15)) & 8;
    HIDWORD(v114) = v72;
  }
  if ( *(_BYTE *)(v73 + 1112) > 0xBu
    || *(_BYTE *)(v73 + 1112) == 11 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v73 + 1232) + 96LL) + 912LL)) )
  {
    if ( (a6 & 0x80u) != 0 )
    {
      v72 = (unsigned int)v72 | 0x10;
      HIDWORD(v114) = v72;
    }
    if ( (a6 & 0x100) != 0 )
    {
      v72 = (unsigned int)v72 | 0x20;
      HIDWORD(v114) = v72;
    }
  }
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1u:
        v115 = 1;
        break;
      case 2u:
        v115 = 2;
        break;
      case 3u:
        v115 = 3;
        break;
      default:
        v115 = 4;
        break;
    }
  }
  else
  {
    v115 = 0;
  }
  v74 = 0;
  hHandle = 0;
  v75 = *(_BYTE *)(v73 + 1112) > 8u
     || *(_BYTE *)(v73 + 1112) == 8 && HIWORD(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v73 + 1232) + 96LL) + 912LL));
  if ( !v11 || (*((_DWORD *)v11 + 22) & 0x8000) == 0 || *((_DWORD *)v11 + 90) != 2 )
    goto LABEL_204;
  if ( (a6 & 0x14) == 0 )
  {
    NDXGI::CDevice::AdjustPresentLimitSemaphore(v8, *((_DWORD *)v11 + 20));
    v76 = (void *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)v8 + 2) + 184LL))((char *)v8 + 16);
    v74 = v76;
    hHandle = v76;
    if ( v75 )
    {
      v77 = 0;
      if ( (*((_BYTE *)v11 + 88) & 0x10) == 0 )
        v77 = 2000;
      if ( WaitForSingleObject(v76, v77) == 258 && (*((_BYTE *)v11 + 88) & 0x10) != 0 )
      {
        if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
        return 2289696778LL;
      }
    }
    else
    {
      *((_QWORD *)v11 + 44) = v76;
    }
  }
  if ( (v71 & 4) != 0 || (*((_QWORD *)v11 + 51) = 1, !v75) )
  {
LABEL_204:
    v80 = 0;
    v123 = 0;
    v81 = 0;
    if ( a4 )
    {
      v81 = ((__int64 (__fastcall *)(struct IDXGIResource *, GUID *, __int64 *))a4->lpVtbl->QueryInterface)(
              a4,
              &GUID_79d2046c_22ef_451b_9e74_2245d9c760ea,
              &v123);
      if ( v81 < 0
        || (v81 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v123 + 24LL))(v123, (char *)&v113 + 4),
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123),
            v81 < 0) )
      {
LABEL_315:
        if ( v12 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
        return (unsigned int)v81;
      }
    }
    v82 = *(CContext **)(*((_QWORD *)v8 + 9) + 1080LL);
    v138[0] = v82;
    v138[1] = 0;
    v138[2] = CContext::AcquireDevCtxIfaceNoSync(v82, 0);
    v138[3] = (char *)v82 + 264;
    v139 = 2;
    if ( *(_BYTE *)(*((_QWORD *)v8 + 9) + 1112LL) >= 0xFu
      && (BYTE12(v114) & 2) != 0
      && (*((_DWORD *)v11 + 22) & 0x10000000) == 0 )
    {
      v84 = 0;
      if ( a3 )
      {
        v119[0] = 0;
        while ( 1 )
        {
          LODWORD(a5) = 0;
          v85 = *(_QWORD *)(*((_QWORD *)this + 9) + 1080LL);
          v126 = v85;
          v127 = *(_DWORD *)(v85 + 3688);
          v86 = *(_QWORD *)(v85 + 3692);
          v128 = v86;
          *(_DWORD *)(v85 + 3688) = GetCurrentThreadId();
          *(_BYTE *)(v85 + 3692) = 1;
          *(_WORD *)(v85 + 3693) = *(_WORD *)((char *)&this + 1);
          *(_BYTE *)(v85 + 3695) = BYTE3(this);
          *(_DWORD *)(v85 + 3696) = 0;
          v120 = (volatile signed __int32 *)((char *)a2 + 16 * v119[0]);
          (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, struct _D3DKMT_PRESENT **))(v85 + 2872))(
            *(_QWORD *)(*((_QWORD *)this + 9) + 1080LL) + 40768LL,
            *(_QWORD *)v120,
            *((unsigned int *)v120 + 2),
            *((unsigned int *)v11 + 4),
            0,
            &a5);
          if ( ((unsigned __int8)a5 & 1) != 0 )
            break;
          if ( ((unsigned __int8)a5 & 2) != 0 )
          {
            if ( (a6 & 0x200) == 0 )
              break;
            HIDWORD(v114) |= 0x40u;
          }
LABEL_229:
          *(_DWORD *)(v85 + 3688) = v127;
          *(_QWORD *)(v85 + 3692) = v86;
          ++v84;
          ++v119[0];
          v80 = 0;
          if ( v84 >= a3 )
            goto LABEL_230;
        }
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(v85 + 2880))(
          *(_QWORD *)(*((_QWORD *)this + 9) + 1080LL) + 40768LL,
          *(_QWORD *)v120,
          *((unsigned int *)v120 + 2),
          *((unsigned int *)v11 + 4),
          0,
          0);
        goto LABEL_229;
      }
LABEL_230:
      v8 = this;
    }
    v109[0] = 0;
    if ( *((_BYTE *)v8 + 898) )
    {
      *((_QWORD *)v8 + 176) = v109;
      goto LABEL_236;
    }
    AcquireSRWLockExclusive((PSRWLOCK)v8 + 167);
    CurrentThreadId = GetCurrentThreadId();
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      LODWORD(v120) = CurrentThreadId;
      v121 = (volatile signed __int32 *)v109;
      std::_Hash<std::_Umap_traits<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,NDXGI::CDevice::SPresentCBThreadLocalData *>>,0>>::emplace<std::pair<unsigned long,NDXGI::CDevice::SPresentCBThreadLocalData *>>(
        (char *)v8 + 1344,
        v119,
        &v120);
      v80 = (_QWORD *)v119[0];
      if ( v8 != (NDXGI::CDevice *)-1336LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v8 + 167);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_180031BE6);
        CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v138);
        goto LABEL_321;
      }
    }
LABEL_236:
    v88 = *((_QWORD *)v8 + 9);
    if ( *(int *)(v88 + 1124) < 3
      || *(_BYTE *)(v88 + 1112) == 1 && !(unsigned int)CDevice::SupportsLevel9PerfFeatures((CDevice *)(v88 + 48)) )
    {
      v130 = 0;
      v131 = 0;
      v134 = 0;
      v129 = v110;
      v132 = *(_QWORD *)((char *)&v113 + 4);
      v133 = HIDWORD(v113);
      v135 = *(_QWORD *)((char *)&v114 + 4);
      v136 = HIDWORD(v114);
      v137 = v115;
      v98 = 0;
      do
      {
        if ( v98 >= v112 )
          break;
        *((_DWORD *)v11 + 91) = v112 - v98 - 1;
        v99 = (char *)v111 + 16 * v98;
        v130 = *(_QWORD *)v99;
        LODWORD(v131) = *((_DWORD *)v99 + 2);
        v81 = (*((__int64 (__fastcall **)(__int64 *))v8 + 85))(&v129);
        ++v98;
      }
      while ( v81 >= 0 );
    }
    else
    {
      v89 = (_DWORD *)*((_QWORD *)v11 + 180);
      if ( v89 && !v89[4] )
      {
        HIDWORD(v117) = *v89;
        *(_QWORD *)((char *)&v117 + 4) = *(_QWORD *)(*((_QWORD *)v11 + 180) + 8LL);
      }
      v90 = 0;
      v91 = v112;
      v92 = v111;
      if ( *(_BYTE *)(v88 + 1139) )
      {
        v83 = 0;
        if ( v112 )
        {
          while ( !*((_DWORD *)v111 + 4 * (unsigned int)v83 + 2)
               || *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v111 + 2 * (unsigned int)v83) - 56LL) + 340LL) == 1 )
          {
            v83 = (unsigned int)(v83 + 1);
            if ( (unsigned int)v83 >= v112 )
              goto LABEL_249;
          }
          v90 = 1;
        }
      }
LABEL_249:
      v93 = 0;
      if ( v90 )
      {
        v94 = 16LL * v112;
        if ( !is_mul_ok(v112, 0x10u) )
          v94 = -1;
        if ( __eh34_try(-1, 4) )
        {
          __eh34_scope_strut(4);
          v93 = (char *)operator new[](v94);
          v144 = v93;
          for ( i = 0; i < v112; ++i )
          {
            v96 = &v93[16 * i];
            *(_OWORD *)v96 = *((_OWORD *)v111 + i);
            v83 = *(_QWORD *)(*((_QWORD *)v111 + 2 * i) - 56LL);
            v91 = *((unsigned int *)v96 + 2);
            if ( !*(_BYTE *)(*(_QWORD *)(v83 + 160) + 1139LL) && (int)v91 < 0 )
            {
              v83 = ((unsigned int)v91 & 0x7FFFFFFF)
                  % (*(unsigned __int8 *)(v83 + 280) * (unsigned int)*(unsigned __int16 *)(v83 + 338));
              v91 = (unsigned int)v83;
            }
            *((_DWORD *)v96 + 2) = v91;
          }
          v111 = (const struct DXGI_PRESENTSURFACE *)v93;
        }
        if ( __eh34_catch(4) )
        {
          if ( __eh34_catch_type(4, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            __eh34_try_continuation(4, &std::bad_alloc `RTTI Type Descriptor', &loc_180031872);
            if ( v144 )
              SmallDDIElLayout::operator delete(v144, (unsigned int)&v108);
            CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v138);
            goto LABEL_321;
          }
        }
      }
      v81 = (*((__int64 (__fastcall **)(__int64 *, __int64, __int64))v8 + 101))(&v110, v83, v91);
      v111 = v92;
      if ( v93 )
        SmallDDIElLayout::operator delete(v93, v97);
    }
    if ( g_bEnableResourceMonitoring )
      NDXGI::CDevice::ReadbackMonitoredResources(v8);
    if ( *((_BYTE *)v8 + 898) )
    {
      *((_QWORD *)v8 + 176) = 0;
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)v8 + 167);
      v100 = (_QWORD *)(*((_QWORD *)v8 + 171)
                      + 16 * (*((_QWORD *)v8 + 174) & std::_Hash_representation<unsigned long>(v80 + 2)));
      v101 = (_QWORD *)*v100;
      if ( (_QWORD *)v100[1] == v80 )
      {
        if ( v101 == v80 )
        {
          v102 = *((_QWORD *)v8 + 169);
          *v100 = v102;
        }
        else
        {
          v102 = v80[1];
        }
        v100[1] = v102;
      }
      else if ( v101 == v80 )
      {
        *v100 = *v80;
      }
      v103 = *v80;
      --*((_QWORD *)v8 + 170);
      *(_QWORD *)v80[1] = v103;
      *(_QWORD *)(v103 + 8) = v80[1];
      SmallDDIElLayout::operator delete(v80, 0x20u);
      if ( v8 != (NDXGI::CDevice *)-1336LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v8 + 167);
    }
    if ( v81 == -2005530512 )
      goto LABEL_307;
    if ( v81 )
    {
      NDXGI::CDevice::DriverInternalError(v8, v81);
      v81 = -2005270523;
      goto LABEL_308;
    }
    if ( LODWORD(v109[0]) == -2005530512 )
    {
LABEL_307:
      v81 = -2005270523;
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)v8 + 2) + 264LL))((char *)v8 + 16, 2289696773LL);
LABEL_308:
      CDevCtxInterface::~CDevCtxInterface((CDevCtxInterface *)v138);
      if ( v81 >= 0 )
      {
        CDevice::IncrementConservativeFlushCount(*((CDevice **)v8 + 9));
        if ( (a6 & 0x20) == 0 )
          CDevice::RecoverHardwareContentProtectionTeardown(*((CDevice **)v8 + 9));
        if ( a8 )
        {
          v105 = CDevice::PhysicalAdapterCount(*((CDevice **)v8 + 9)) <= 1;
          v107 = 1;
          if ( !v105 )
            v107 = v118;
          *v106 = v107;
        }
      }
      goto LABEL_315;
    }
    if ( SHIDWORD(v109[0]) <= -1071775739 )
    {
      if ( HIDWORD(v109[0]) != -1071775739 )
      {
        if ( HIDWORD(v109[0]) == -1073741811 )
        {
          if ( (unsigned int)IsProcessDWM() )
          {
            v81 = -2005270527;
            goto LABEL_308;
          }
        }
        else if ( HIDWORD(v109[0]) == -1071775744 )
        {
LABEL_287:
          v81 = 142213121;
          goto LABEL_308;
        }
        goto LABEL_302;
      }
      goto LABEL_306;
    }
    if ( SHIDWORD(v109[0]) > -1071775729 )
    {
      switch ( HIDWORD(v109[0]) )
      {
        case 0xC01E0018:
LABEL_306:
          v81 = 142213127;
          goto LABEL_308;
        case 0xC01E0102:
          v81 = -2005270518;
          goto LABEL_308;
        case 0xC01E0342:
          v81 = 142213126;
          goto LABEL_308;
        case 0x103:
          v81 = 142213130;
          goto LABEL_308;
      }
    }
    else
    {
      if ( HIDWORD(v109[0]) == -1071775729 )
        goto LABEL_295;
      if ( (unsigned int)(HIDWORD(v109[0]) + 1071775738) <= 1 )
        goto LABEL_287;
      if ( HIDWORD(v109[0]) == -1071775733 || HIDWORD(v109[0]) == -1071775730 )
      {
LABEL_295:
        v81 = 142213124;
        v104 = hHandle;
        if ( hHandle )
        {
          while ( !WaitForSingleObject(v104, 0) )
            ;
          ReleaseSemaphore(v104, *((_DWORD *)v8 + 240), 0);
        }
        goto LABEL_308;
      }
    }
LABEL_302:
    v81 = 0;
    goto LABEL_308;
  }
  v79 = CallAndLogImpl<long (*)(void *,_D3DKMT_PRESENTHISTORYTOKEN const *),void *,_D3DKMT_PRESENTHISTORYTOKEN *>(
          NtNotifyPresentToCompositionSurface,
          v72,
          *((_QWORD *)v11 + 48),
          (char *)v11 + 360);
  if ( v79 >= 0 )
  {
    *((_DWORD *)v11 + 105) |= 0x2000000u;
    goto LABEL_204;
  }
  ReleaseSemaphore(v74, 1, 0);
  if ( v79 == -1071775733 || v79 == -1071775730 )
  {
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    return 142213124;
  }
  else
  {
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180030780  mov     rax, rsp
0x180030783  mov     [rax+20h], r9
0x180030787  mov     [rax+18h], r8d
0x18003078b  mov     [rax+10h], rdx
0x18003078f  mov     [rax+8], rcx
0x180030793  push    rbx
0x180030794  push    rsi
0x180030795  push    rdi
0x180030796  push    r12
0x180030798  push    r13
0x18003079a  push    r14
0x18003079c  push    r15
0x18003079e  sub     rsp, 1B0h
0x1800307a5  mov     r13, rcx
0x1800307a8  xor     r14d, r14d
0x1800307ab  mov     [rsp+1E8h+var_184], r14
0x1800307b0  mov     [rsp+1E8h+var_17C], r14
0x1800307b5  mov     [rsp+1E8h+var_174], r14
0x1800307ba  mov     [rsp+1E8h+var_16C], r14
0x1800307bf  mov     [rax-164h], r14d
0x1800307c6  mov     [rax-15Ch], r14
0x1800307cd  mov     [rax-154h], r14
0x1800307d4  mov     rax, [rcx+2A0h]
0x1800307db  mov     [rsp+1E8h+var_198], rax
0x1800307e0  mov     [rsp+1E8h+var_190], rdx
0x1800307e5  mov     [rsp+1E8h+var_188], r8d
0x1800307ea  mov     ebx, 1
0x1800307ef  mov     [rsp+1E8h+var_14C], ebx
0x1800307f6  mov     [rsp+1E8h+var_160], ebx
0x1800307fd  xorps   xmm0, xmm0
0x180030800  movdqu  xmmword ptr [rsp+1E8h+var_128], xmm0
0x180030809  mov     rcx, [rcx+48h]
0x18003080d  cmp     byte ptr [rcx+458h], 9
0x180030814  ja      short loc_180030854
0x180030816  jnz     short loc_180030833
0x180030818  mov     rax, [rcx+4D0h]
0x18003081f  mov     rcx, [rax+60h]
0x180030823  mov     eax, [rcx+390h]
0x180030829  shr     rax, 10h
0x18003082d  cmp     ax, 4
0x180030831  jnb     short loc_180030854
0x180030833  mov     r15, [rsp+1E8h+arg_20]
0x18003083b  mov     [rsp+1E8h+var_174+4], r15
0x180030840  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180030847  mov     r14, [rsp+1E8h+var_128+8]
0x18003084f  jmp     loc_1800310F3
0x180030854  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x18003085b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x180030860  test    al, al
0x180030862  jz      loc_180030D0E
0x180030868  mov     ecx, 30h ; '0'; dwBytes
0x18003086d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030872  mov     rdi, rax
0x180030875  mov     [rsp+1E8h+var_138], rax
0x18003087d  test    rax, rax
0x180030880  jz      short loc_1800308BD
0x180030882  mov     [rax+8], ebx
0x180030885  mov     [rax+0Ch], ebx
0x180030888  lea     rax, ??_7?$_Ref_count_obj2@UBatchablePresent@@@std@@6B@; const std::_Ref_count_obj2<BatchablePresent>::`vftable'
0x18003088f  mov     [rdi], rax
0x180030892  lea     rcx, [rdi+10h]; lpTargetHandle
0x180030896  mov     [rsp+1E8h+hHandle], rcx
0x18003089e  mov     [rcx], r14
0x1800308a1  mov     [rcx+8], r14
0x1800308a5  mov     [rcx+10h], r14
0x1800308a9  mov     [rcx+18h], r14
0x1800308ad  mov     rdx, [rsp+1E8h+arg_20]; struct _D3DKMT_PRESENT *
0x1800308b5  call    ?Initialize@BatchablePresent@@IEAAXAEBU_D3DKMT_PRESENT@@@Z; BatchablePresent::Initialize(_D3DKMT_PRESENT const &)
0x1800308ba  nop
0x1800308bb  jmp     short loc_1800308C0
0x1800308bd  mov     rdi, r14
0x1800308c0  lea     rsi, [r13+700h]
0x1800308c7  lea     r12, [rdi+10h]
0x1800308cb  mov     [rsp+1E8h+var_138], r12
0x1800308d3  mov     [rsp+1E8h+var_130], rdi
0x1800308db  mov     [rsp+1E8h+arg_20], rsi
0x1800308e3  mov     rcx, rsi; lpCriticalSection
0x1800308e6  call    cs:__imp_EnterCriticalSection
0x1800308ec  nop
0x1800308ed  lea     rbx, [rsi+28h]
0x1800308f1  mov     r15, [rbx]
0x1800308f4  mov     rax, [r15+8]
0x1800308f8  xor     ecx, ecx
0x1800308fa  mov     dword ptr [rsp+1E8h+var_F4], ecx
0x180030901  mov     rcx, r15
0x180030904  cmp     byte ptr [rax+19h], 0
0x180030908  jnz     short loc_180030937
0x18003090a  mov     rdx, [rsi+38h]
0x18003090e  mov     r8d, 1
0x180030914  mov     rsi, rax
0x180030917  cmp     [rax+20h], rdx
0x18003091b  jnb     short loc_180030926
0x18003091d  xor     r14d, r14d
0x180030920  mov     rax, [rax+10h]
0x180030924  jmp     short loc_18003092F
0x180030926  mov     r14d, r8d
0x180030929  mov     rcx, rax
0x18003092c  mov     rax, [rax]
0x18003092f  cmp     byte ptr [rax+19h], 0
0x180030933  jz      short loc_180030914
0x180030935  jmp     short loc_18003093A
0x180030937  mov     rsi, rax
0x18003093a  cmp     byte ptr [rcx+19h], 0
0x18003093e  jnz     short loc_180030951
0x180030940  mov     rax, [rcx+20h]
0x180030944  cmp     [r13+738h], rax
0x18003094b  jnb     loc_180030C07
0x180030951  mov     rax, 492492492492492h
0x18003095b  cmp     [rbx+8], rax
0x18003095f  jz      loc_180031C3A
0x180030965  mov     [rsp+1E8h+hHandle], rbx
0x18003096d  mov     [rsp+1E8h+var_108], 0
0x180030979  mov     ecx, 38h ; '8'; dwBytes
0x18003097e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030983  mov     rdx, rax
0x180030986  mov     rcx, [r13+738h]
0x18003098d  mov     [rax+20h], rcx
0x180030991  xor     eax, eax
0x180030993  mov     [rdx+28h], rax
0x180030997  mov     [rdx+30h], rax
0x18003099b  test    rdi, rdi
0x18003099e  jz      short loc_1800309A4
0x1800309a0  lock inc dword ptr [rdi+8]
0x1800309a4  mov     [rdx+28h], r12
0x1800309a8  mov     [rdx+30h], rdi
0x1800309ac  mov     [rdx], r15
0x1800309af  mov     [rdx+8], r15
0x1800309b3  mov     [rdx+10h], r15
0x1800309b7  mov     [rdx+18h], ax
0x1800309bb  inc     qword ptr [rbx+8]
0x1800309bf  mov     r9, [rbx]
0x1800309c2  mov     [rdx+8], rsi
0x1800309c6  cmp     rsi, r9
0x1800309c9  jnz     short loc_1800309DF
0x1800309cb  mov     [r9], rdx
0x1800309ce  mov     [r9+8], rdx
0x1800309d2  mov     [r9+10h], rdx
0x1800309d6  mov     byte ptr [rdx+18h], 1
0x1800309da  jmp     loc_180030C07
0x1800309df  test    r14d, r14d
0x1800309e2  jnz     short loc_1800309F4
0x1800309e4  mov     [rsi+10h], rdx
0x1800309e8  cmp     rsi, [r9+10h]
0x1800309ec  jnz     short loc_1800309FF
0x1800309ee  mov     [r9+10h], rdx
0x1800309f2  jmp     short loc_1800309FF
0x1800309f4  mov     [rsi], rdx
0x1800309f7  cmp     rsi, [r9]
0x1800309fa  jnz     short loc_1800309FF
0x1800309fc  mov     [r9], rdx
0x1800309ff  mov     rax, [rdx+8]
0x180030a03  cmp     byte ptr [rax+18h], 0
0x180030a07  jnz     loc_180030BFF
0x180030a0d  nop     dword ptr [rax]
0x180030a10  mov     rcx, [rdx+8]
0x180030a14  mov     r8, [rcx+8]
0x180030a18  mov     rax, [r8]
0x180030a1b  cmp     rcx, rax
0x180030a1e  jnz     loc_180030B14
0x180030a24  mov     rax, [r8+10h]
0x180030a28  cmp     byte ptr [rax+18h], 0
0x180030a2c  jnz     short loc_180030A4F
0x180030a2e  mov     byte ptr [rcx+18h], 1
0x180030a32  mov     byte ptr [rax+18h], 1
0x180030a36  mov     rax, [rdx+8]
0x180030a3a  mov     rcx, [rax+8]
0x180030a3e  mov     byte ptr [rcx+18h], 0
0x180030a42  mov     rax, [rdx+8]
0x180030a46  mov     rdx, [rax+8]
0x180030a4a  jmp     loc_180030BF1
0x180030a4f  mov     r8, [rcx+10h]
0x180030a53  cmp     rdx, r8
0x180030a56  jnz     short loc_180030A9F
0x180030a58  mov     rdx, rcx
0x180030a5b  mov     rax, [r8]
0x180030a5e  mov     [rcx+10h], rax
0x180030a62  mov     rax, [r8]
0x180030a65  cmp     byte ptr [rax+19h], 0
0x180030a69  jnz     short loc_180030A6F
0x180030a6b  mov     [rax+8], rcx
0x180030a6f  mov     rax, [rcx+8]
0x180030a73  mov     [r8+8], rax
0x180030a77  mov     rax, [rbx]
0x180030a7a  cmp     rcx, [rax+8]
0x180030a7e  jnz     short loc_180030A86
0x180030a80  mov     [rax+8], r8
0x180030a84  jmp     short loc_180030A98
0x180030a86  mov     rax, [rcx+8]
0x180030a8a  cmp     rcx, [rax]
0x180030a8d  jnz     short loc_180030A94
0x180030a8f  mov     [rax], r8
0x180030a92  jmp     short loc_180030A98
0x180030a94  mov     [rax+10h], r8
0x180030a98  mov     [r8], rcx
0x180030a9b  mov     [rcx+8], r8
0x180030a9f  mov     rax, [rdx+8]
0x180030aa3  mov     byte ptr [rax+18h], 1
0x180030aa7  mov     rax, [rdx+8]
0x180030aab  mov     rcx, [rax+8]
0x180030aaf  mov     byte ptr [rcx+18h], 0
0x180030ab3  mov     rax, [rdx+8]
0x180030ab7  mov     rcx, [rax+8]
0x180030abb  mov     r8, [rcx]
0x180030abe  mov     rax, [r8+10h]
0x180030ac2  mov     [rcx], rax
0x180030ac5  mov     rax, [r8+10h]
0x180030ac9  cmp     byte ptr [rax+19h], 0
0x180030acd  jnz     short loc_180030AD3
0x180030acf  mov     [rax+8], rcx
0x180030ad3  mov     rax, [rcx+8]
0x180030ad7  mov     [r8+8], rax
0x180030adb  mov     rax, [rbx]
0x180030ade  cmp     rcx, [rax+8]
0x180030ae2  jnz     short loc_180030AF1
0x180030ae4  mov     [rax+8], r8
0x180030ae8  mov     [r8+10h], rcx
0x180030aec  jmp     loc_180030BED
0x180030af1  mov     rax, [rcx+8]
0x180030af5  cmp     rcx, [rax+10h]
0x180030af9  jnz     short loc_180030B08
0x180030afb  mov     [rax+10h], r8
0x180030aff  mov     [r8+10h], rcx
0x180030b03  jmp     loc_180030BED
0x180030b08  mov     [rax], r8
0x180030b0b  mov     [r8+10h], rcx
0x180030b0f  jmp     loc_180030BED
0x180030b14  cmp     byte ptr [rax+18h], 0
0x180030b18  jnz     short loc_180030B3B
0x180030b1a  mov     byte ptr [rcx+18h], 1
0x180030b1e  mov     byte ptr [rax+18h], 1
0x180030b22  mov     rax, [rdx+8]
0x180030b26  mov     rcx, [rax+8]
0x180030b2a  mov     byte ptr [rcx+18h], 0
0x180030b2e  mov     rax, [rdx+8]
0x180030b32  mov     rdx, [rax+8]
0x180030b36  jmp     loc_180030BF1
0x180030b3b  mov     r8, [rcx]
0x180030b3e  cmp     rdx, r8
0x180030b41  jnz     short loc_180030B8D
0x180030b43  mov     rdx, rcx
0x180030b46  mov     rax, [r8+10h]
0x180030b4a  mov     [rcx], rax
0x180030b4d  mov     rax, [r8+10h]
0x180030b51  cmp     byte ptr [rax+19h], 0
0x180030b55  jnz     short loc_180030B5B
0x180030b57  mov     [rax+8], rcx
0x180030b5b  mov     rax, [rcx+8]
0x180030b5f  mov     [r8+8], rax
0x180030b63  mov     rax, [rbx]
0x180030b66  cmp     rcx, [rax+8]
0x180030b6a  jnz     short loc_180030B72
0x180030b6c  mov     [rax+8], r8
0x180030b70  jmp     short loc_180030B85
0x180030b72  mov     rax, [rcx+8]
0x180030b76  cmp     rcx, [rax+10h]
0x180030b7a  jnz     short loc_180030B82
0x180030b7c  mov     [rax+10h], r8
0x180030b80  jmp     short loc_180030B85
0x180030b82  mov     [rax], r8
0x180030b85  mov     [r8+10h], rcx
0x180030b89  mov     [rcx+8], r8
0x180030b8d  mov     rax, [rdx+8]
0x180030b91  mov     byte ptr [rax+18h], 1
0x180030b95  mov     rax, [rdx+8]
0x180030b99  mov     rcx, [rax+8]
0x180030b9d  mov     byte ptr [rcx+18h], 0
0x180030ba1  mov     rax, [rdx+8]
0x180030ba5  mov     rcx, [rax+8]
0x180030ba9  mov     r8, [rcx+10h]
0x180030bad  mov     rax, [r8]
0x180030bb0  mov     [rcx+10h], rax
0x180030bb4  mov     rax, [r8]
0x180030bb7  cmp     byte ptr [rax+19h], 0
0x180030bbb  jnz     short loc_180030BC1
0x180030bbd  mov     [rax+8], rcx
0x180030bc1  mov     rax, [rcx+8]
0x180030bc5  mov     [r8+8], rax
0x180030bc9  mov     rax, [rbx]
0x180030bcc  cmp     rcx, [rax+8]
0x180030bd0  jnz     short loc_180030BD8
0x180030bd2  mov     [rax+8], r8
0x180030bd6  jmp     short loc_180030BEA
0x180030bd8  mov     rax, [rcx+8]
0x180030bdc  cmp     rcx, [rax]
0x180030bdf  jnz     short loc_180030BE6
0x180030be1  mov     [rax], r8
0x180030be4  jmp     short loc_180030BEA
0x180030be6  mov     [rax+10h], r8
0x180030bea  mov     [r8], rcx
0x180030bed  mov     [rcx+8], r8
0x180030bf1  mov     rax, [rdx+8]
0x180030bf5  cmp     byte ptr [rax+18h], 0
0x180030bf9  jz      loc_180030A10
0x180030bff  mov     rax, [r9+8]
0x180030c03  mov     byte ptr [rax+18h], 1
0x180030c07  mov     rbx, [r13+738h]
0x180030c0e  lea     rax, [rbx+1]
0x180030c12  mov     [r13+738h], rax
0x180030c19  lea     rcx, [r13+700h]; lpCriticalSection
0x180030c20  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
