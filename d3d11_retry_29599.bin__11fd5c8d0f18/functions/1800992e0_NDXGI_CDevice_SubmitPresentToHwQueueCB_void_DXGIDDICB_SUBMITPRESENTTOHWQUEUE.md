# NDXGI::CDevice::SubmitPresentToHwQueueCB(void *,DXGIDDICB_SUBMITPRESENTTOHWQUEUE *)

- ea: `0x1800992e0`
- end: `0x180099937`
- name: `?SubmitPresentToHwQueueCB@CDevice@NDXGI@@KAJPEAXPEAUDXGIDDICB_SUBMITPRESENTTOHWQUEUE@@@Z`
- size: `1623`
- prototype: `__int64 __fastcall(NDXGI::CDevice *this, struct DXGIDDICB_SUBMITPRESENTTOHWQUEUE *)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180022630`
- `0x1800229a0`
- `0x180030144`
- `0x180030710`
- `0x180035c00`
- `0x18004429c`
- `0x18005ec80`
- `0x180065430`
- `0x180072e5c`
- `0x180084750`
- `0x1800992e0`
- `0x1800a7328`
- `0x1800a9d20`
- `0x1800aa990`
- `0x1800aa9a8`
- `0x1800b63f8`
- `0x1800b6480`
- `0x1800b7fd0`
- `0x1800bc008`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009979f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009979f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099799`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099799`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800997dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800997dc`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTSubmitPresentToHwQueue` at `0x1800996b7`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOutputDuplPresentToHwQueue` at `0x1800994ed`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::SubmitPresentToHwQueueCB(
        NDXGI::CDevice *this,
        struct DXGIDDICB_SUBMITPRESENTTOHWQUEUE *a2)
{
  __int64 DataFromToken__lambda_fefd9c2bad47d401fe99cc4673bb956a; // rax
  const void *DataFromToken__lambda_f37d514ff23848574370a90bfbc0e697; // rbx
  char v6; // al
  __int64 v7; // rdx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // edi
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // ebx
  _DWORD *v16; // rcx
  _DWORD *v17; // rcx
  __int64 v18; // rdx
  BOOL v19; // r9d
  unsigned int v20; // r8d
  char v21; // al
  __int64 v22; // rdx
  int v23; // eax
  BOOL v24; // eax
  __int64 v25; // rdx
  bool v26; // zf
  unsigned int v27; // edi
  unsigned int *v28; // rax
  __int64 v29; // rax
  unsigned int *v30; // rax
  char v31; // al
  __int64 v32; // rdx
  char IsEnabled; // al
  __int64 v34; // rdx
  char v35; // al
  __int64 v36; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-6A8h] BYREF
  struct DXGIDDICB_SUBMITPRESENTTOHWQUEUE *v38; // [rsp+38h] [rbp-6A0h] BYREF
  NDXGI::CDevice *v39; // [rsp+40h] [rbp-698h]
  std::_Ref_count_base *v40[2]; // [rsp+48h] [rbp-690h] BYREF
  __int64 v41; // [rsp+58h] [rbp-680h] BYREF
  std::_Ref_count_base *v42; // [rsp+60h] [rbp-678h]
  _DWORD v43[4]; // [rsp+70h] [rbp-668h] BYREF
  __int64 v44; // [rsp+80h] [rbp-658h]
  __int128 v45; // [rsp+88h] [rbp-650h]
  __int128 v46; // [rsp+98h] [rbp-640h]
  unsigned int v47; // [rsp+A8h] [rbp-630h]
  int v48; // [rsp+ACh] [rbp-62Ch]
  _com_error *v49[4]; // [rsp+B0h] [rbp-628h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-608h] BYREF
  _DWORD v51[21]; // [rsp+D8h] [rbp-600h] BYREF
  int v52; // [rsp+12Ch] [rbp-5ACh]
  unsigned int v53; // [rsp+130h] [rbp-5A8h]
  unsigned int v54; // [rsp+134h] [rbp-5A4h]
  int v55; // [rsp+240h] [rbp-498h]
  int v56; // [rsp+278h] [rbp-460h]
  unsigned int v57; // [rsp+27Ch] [rbp-45Ch]
  __int128 *v58; // [rsp+678h] [rbp-60h]
  int v59; // [rsp+680h] [rbp-58h]
  _DWORD *v60; // [rsp+688h] [rbp-50h]
  _DWORD *v61; // [rsp+690h] [rbp-48h]
  int v62; // [rsp+698h] [rbp-40h]
  __int64 v63; // [rsp+6A0h] [rbp-38h]
  char v64; // [rsp+6A8h] [rbp-30h]

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v39 = this;
    v38 = a2;
    *(_OWORD *)v40 = 0;
    v49[1] = this;
    v49[2] = a2;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl) )
    {
      DataFromToken__lambda_fefd9c2bad47d401fe99cc4673bb956a = NDXGI::OpaqueHandleManager_std::shared_ptr_BatchablePresent___::GetDataFromToken__lambda_fefd9c2bad47d401fe99cc4673bb956a___((LPCRITICAL_SECTION)((char *)this + 1792));
      std::shared_ptr<BatchablePresent>::operator=(v40, DataFromToken__lambda_fefd9c2bad47d401fe99cc4673bb956a);
      if ( v42 )
        std::_Ref_count_base::_Decref(v42);
      DataFromToken__lambda_f37d514ff23848574370a90bfbc0e697 = (const void *)*((_QWORD *)v40[0] + 3);
    }
    else
    {
      DataFromToken__lambda_f37d514ff23848574370a90bfbc0e697 = (const void *)NDXGI::OpaqueHandleManager_BatchablePresent_::GetDataFromToken__lambda_f37d514ff23848574370a90bfbc0e697___((LPCRITICAL_SECTION)((char *)this + 1856));
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', v49) )
    {
      CurrentThreadId = *((_DWORD *)v49[0] + 2);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_180099875);
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
      v34 = *(_QWORD *)v38;
      if ( IsEnabled )
        NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken((char *)v39 + 1792, v34);
      else
        NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken((char *)v39 + 1856, v34);
      if ( v40[1] )
        std::_Ref_count_base::_Decref(v40[1]);
      return CurrentThreadId;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800998C2);
      v35 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
      v36 = *(_QWORD *)v38;
      if ( v35 )
        NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken((char *)v39 + 1792, v36);
      else
        NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken((char *)v39 + 1856, v36);
      if ( v40[1] )
        std::_Ref_count_base::_Decref(v40[1]);
      return 2147942414LL;
    }
  }
  memset_0(&v50, 0, 0x5E0u);
  if ( !*((_DWORD *)a2 + 8) )
  {
    v6 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
    v7 = *(_QWORD *)a2;
    if ( v6 )
      NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken((char *)this + 1792, v7);
    else
      NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken((char *)this + 1856, v7);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return 3221225485LL;
  }
  memcpy_0(v51, DataFromToken__lambda_f37d514ff23848574370a90bfbc0e697, 0x5D8u);
  std::vector<unsigned int>::vector<unsigned int>(&v41, *((unsigned int *)a2 + 8));
  v10 = 0;
  v11 = *((_DWORD *)a2 + 8);
  if ( v11 )
  {
    do
    {
      v9 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 8 * v10) + 8LL);
      *(_DWORD *)(v41 + 4 * v10) = v9;
      v10 = (unsigned int)(v10 + 1);
      v11 = *((_DWORD *)a2 + 8);
    }
    while ( (unsigned int)v10 < v11 );
  }
  v12 = v53;
  if ( (v53 & 0x800000) != 0 )
  {
    memset_0(v43, 0, 0x40u);
    v43[0] = **((_DWORD **)a2 + 1);
    v43[1] = v51[4];
    v44 = v41;
    v43[2] = v11;
    if ( v58 )
    {
      v45 = *v58;
      v46 = v58[1];
    }
    v47 = (v12 & 0x3000000 | (v12 >> 1) & 0x8000000) >> 24;
    v14 = v48;
    if ( v47 >= 8 )
      v14 = v59;
    v48 = v14;
    v15 = CallAndLogImpl<long (*)(_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE const *),_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *>(
            D3DKMTOutputDuplPresentToHwQueue,
            v13,
            v43);
    goto LABEL_54;
  }
  v51[0] = *((_DWORD *)this + 26);
  v54 = v11 - 1;
  v63 = *((_QWORD *)a2 + 5);
  v62 = *((_DWORD *)a2 + 9);
  v50 = v41;
  v16 = (_DWORD *)*((_QWORD *)a2 + 1);
  v51[5] = *v16;
  if ( v11 > 1 )
    v60 = v16 + 1;
  v17 = (_DWORD *)*((_QWORD *)a2 + 2);
  if ( v17 )
  {
    v51[6] = *v17;
    if ( v11 > 1 )
      v61 = v17 + 1;
  }
  if ( (v53 & 4) != 0 || (v53 & 0x8000) != 0 )
  {
    v12 = v53 & 0xFFFFDFFF;
    v53 &= ~0x2000u;
  }
  LOBYTE(v9) = 15;
  if ( !(unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*((_QWORD *)this + 9), v9, 2) || !*((_DWORD *)a2 + 13) )
  {
LABEL_52:
    v15 = CallAndLogImpl<long (*)(_D3DKMT_SUBMITPRESENTTOHWQUEUE *),_D3DKMT_SUBMITPRESENTTOHWQUEUE *>(
            D3DKMTSubmitPresentToHwQueue,
            v18,
            &v50);
    LOBYTE(v25) = 15;
    if ( (unsigned __int8)CDevice::IsD3DDDIVersionOrLater(*((_QWORD *)this + 9), v25, 1) )
      *((_BYTE *)a2 + 48) = v64;
LABEL_54:
    std::vector<unsigned int>::_Tidy(&v41);
    if ( v15 > -1071775731 )
    {
      if ( (unsigned int)(v15 + 1071775730) <= 1 || v15 == -1071775728 )
        goto LABEL_69;
      if ( v15 != -1071775720 && v15 != -1071774910 )
      {
        v26 = v15 == 259;
LABEL_67:
        if ( !v26 )
          goto LABEL_68;
LABEL_69:
        v27 = 0;
        goto LABEL_70;
      }
    }
    else if ( v15 == -1071775731 )
    {
      v15 = 0;
    }
    else
    {
      if ( ((v15 + 1073741811) & 0xFFFFFFEF) == 0 )
      {
LABEL_68:
        v27 = NDXGI::CDevice::NTStatusToHResult(this, v15);
        goto LABEL_70;
      }
      if ( v15 != -1071775744 && (unsigned int)(v15 + 1071775739) > 2 )
      {
        v26 = v15 == -1071775733;
        goto LABEL_67;
      }
    }
    v27 = *((int *)this + 312) < 0 ? 0x88760870 : 0;
LABEL_70:
    if ( *((_BYTE *)this + 898) )
    {
      v28 = (unsigned int *)*((_QWORD *)this + 176);
      if ( v28 )
      {
        *v28 = v27;
        v28[1] = v15;
      }
    }
    else
    {
      AcquireSRWLockShared((PSRWLOCK)this + 167);
      CurrentThreadId = GetCurrentThreadId();
      v29 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SD3D11SharedResourceCreationArgs *>>,0>>::find(
                         (char *)this + 1344,
                         &v38,
                         &CurrentThreadId);
      if ( v29 != *((_QWORD *)this + 169) )
      {
        v30 = *(unsigned int **)(v29 + 24);
        *v30 = v27;
        v30[1] = v15;
      }
      if ( this != (NDXGI::CDevice *)-1336LL )
        ReleaseSRWLockShared((PSRWLOCK)this + 167);
    }
    if ( v27 == -2005532132 || v27 == -2005530512 )
      v27 = 0;
    v31 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
    v32 = *(_QWORD *)a2;
    if ( v31 )
      NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken((char *)this + 1792, v32);
    else
      NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken((char *)this + 1856, v32);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    return v27;
  }
  v20 = *((_DWORD *)a2 + 14);
  if ( v20 <= 4 )
  {
    v18 = v20;
    goto LABEL_42;
  }
  if ( v20 == 5 )
  {
    v18 = 0;
LABEL_42:
    if ( (v12 & 4) != 0 )
    {
      v23 = v52;
      if ( (v12 & 0x8000000) == 0 )
        v23 = v18;
      v52 = v23;
    }
    if ( (v12 & 0x8000) != 0 && v55 == 2 && (v57 & 0x80000) == 0 )
    {
      v56 = v18;
      v24 = 0;
      if ( v20 == 5 )
        v24 = v19;
      v57 = v57 & 0xFF7FFFFF | v24;
    }
    goto LABEL_52;
  }
  ((void (__stdcall *)(CModule *, unsigned int, const char *, bool, bool))CModule::RecordJournal)(
    (CModule *)&g_Module,
    0x80070057,
    "Driver set invalid sync interval override.",
    v19,
    1);
  std::vector<unsigned int>::_Tidy(&v41);
  v21 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl'::`2'::impl);
  v22 = *(_QWORD *)a2;
  if ( v21 )
    NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken((char *)this + 1792, v22);
  else
    NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken((char *)this + 1856, v22);
  if ( v40[1] )
    std::_Ref_count_base::_Decref(v40[1]);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800992e0  mov     r11, rsp
0x1800992e3  mov     [r11+18h], rbx
0x1800992e7  mov     [r11+20h], rsi
0x1800992eb  push    rdi
0x1800992ec  push    r14
0x1800992ee  push    r15
0x1800992f0  sub     rsp, 6C0h
0x1800992f7  mov     rax, cs:__security_cookie
0x1800992fe  xor     rax, rsp
0x180099301  mov     [rsp+6D8h+var_28], rax
0x180099309  mov     rsi, rdx
0x18009930c  mov     r14, rcx
0x18009930f  mov     [rsp+6D8h+var_698], rcx
0x180099314  mov     [rsp+6D8h+var_6A0], rdx
0x180099319  xorps   xmm0, xmm0
0x18009931c  movdqu  xmmword ptr [rsp+6D8h+var_690], xmm0
0x180099322  mov     [r11-620h], rcx
0x180099329  mov     [r11-618h], rdx
0x180099330  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x180099337  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x18009933c  test    al, al
0x18009933e  jz      short loc_18009937B
0x180099340  lea     rcx, [r14+700h]; lpCriticalSection
0x180099347  mov     r8, [rsi]
0x18009934a  lea     rdx, [rsp+6D8h+var_680]
0x18009934f  call    NDXGI__OpaqueHandleManager_std__shared_ptr_BatchablePresent_____GetDataFromToken__lambda_fefd9c2bad47d401fe99cc4673bb956a___
0x180099354  mov     rdx, rax
0x180099357  lea     rcx, [rsp+6D8h+var_690]
0x18009935c  call    ??4?$shared_ptr@UBatchablePresent@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<BatchablePresent>::operator=(std::shared_ptr<BatchablePresent> &&)
0x180099361  mov     rcx, [rsp+6D8h+var_678]; this
0x180099366  test    rcx, rcx
0x180099369  jz      short loc_180099370
0x18009936b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180099370  mov     rax, [rsp+6D8h+var_690]
0x180099375  mov     rbx, [rax+18h]
0x180099379  jmp     short loc_18009938D
0x18009937b  lea     rcx, [r14+740h]; lpCriticalSection
0x180099382  mov     rdx, [rsi]
0x180099385  call    NDXGI__OpaqueHandleManager_BatchablePresent___GetDataFromToken__lambda_f37d514ff23848574370a90bfbc0e697___
0x18009938a  mov     rbx, rax
0x18009938d  xor     edx, edx; Val
0x18009938f  mov     r8d, 5E0h; Size
0x180099395  lea     rcx, [rsp+6D8h+var_608]; void *
0x18009939d  call    memset_0
0x1800993a2  mov     r15d, 1
0x1800993a8  cmp     [rsi+20h], r15d
0x1800993ac  jnb     short loc_1800993F5
0x1800993ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x1800993b5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x1800993ba  mov     rdx, [rsi]
0x1800993bd  test    al, al
0x1800993bf  jz      short loc_1800993CF
0x1800993c1  lea     rcx, [r14+700h]
0x1800993c8  call    ?FreeToken@?$OpaqueHandleManager@V?$shared_ptr@UBatchablePresent@@@std@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(void *)
0x1800993cd  jmp     short loc_1800993DC
0x1800993cf  lea     rcx, [r14+740h]
0x1800993d6  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresent@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(void *)
0x1800993db  nop
0x1800993dc  mov     rcx, [rsp+6D8h+var_690+8]; this
0x1800993e1  test    rcx, rcx
0x1800993e4  jz      short loc_1800993EB
0x1800993e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800993eb  mov     eax, 0C000000Dh
0x1800993f0  jmp     loc_18009990E
0x1800993f5  lea     rcx, [rsp+6D8h+var_600]; void *
0x1800993fd  mov     rdx, rbx; Src
0x180099400  mov     r8d, 5D8h; Size
0x180099406  call    memcpy_0
0x18009940b  nop
0x18009940c  mov     edx, [rsi+20h]
0x18009940f  lea     rcx, [rsp+6D8h+var_680]
0x180099414  call    ??0?$vector@IV?$allocator@I@std@@@std@@QEAA@_KAEBV?$allocator@I@1@@Z; std::vector<uint>::vector<uint>(unsigned __int64,std::allocator<uint> const &)
0x180099419  nop
0x18009941a  xor     r9d, r9d
0x18009941d  mov     edi, [rsi+20h]
0x180099420  test    edi, edi
0x180099422  jz      short loc_180099443
0x180099424  mov     rax, [rsi+18h]
0x180099428  mov     rcx, [rax+r9*8]
0x18009942c  mov     edx, [rcx+8]
0x18009942f  mov     rax, [rsp+6D8h+var_680]
0x180099434  mov     [rax+r9*4], edx
0x180099438  add     r9d, r15d
0x18009943b  mov     edi, [rsi+20h]
0x18009943e  cmp     r9d, edi
0x180099441  jb      short loc_180099424
0x180099443  mov     ebx, [rsp+6D8h+var_5A8]
0x18009944a  mov     r9d, 800000h
0x180099450  test    r9d, ebx
0x180099453  jz      loc_180099500
0x180099459  xor     edx, edx; Val
0x18009945b  lea     r8d, [rdx+40h]; Size
0x18009945f  lea     rcx, [rsp+6D8h+var_668]; void *
0x180099464  call    memset_0
0x180099469  mov     rax, [rsi+8]
0x18009946d  mov     ecx, [rax]
0x18009946f  mov     [rsp+6D8h+var_668], ecx
0x180099473  mov     eax, [rsp+6D8h+var_5F0]
0x18009947a  mov     [rsp+6D8h+var_664], eax
0x18009947e  mov     rax, [rsp+6D8h+var_680]
0x180099483  mov     [rsp+6D8h+var_658], rax
0x18009948b  mov     [rsp+6D8h+var_660], edi
0x18009948f  mov     rax, [rsp+6D8h+var_60]
0x180099497  test    rax, rax
0x18009949a  jz      short loc_1800994B3
0x18009949c  movups  xmm0, xmmword ptr [rax]
0x18009949f  movups  [rsp+6D8h+var_650], xmm0
0x1800994a7  movups  xmm1, xmmword ptr [rax+10h]
0x1800994ab  movups  [rsp+6D8h+var_640], xmm1
0x1800994b3  mov     ecx, ebx
0x1800994b5  shr     ecx, 1
0x1800994b7  and     ecx, 8000000h
0x1800994bd  and     ebx, 3000000h
0x1800994c3  or      ecx, ebx
0x1800994c5  shr     ecx, 18h
0x1800994c8  mov     [rsp+6D8h+var_630], ecx
0x1800994cf  mov     eax, [rsp+6D8h+var_62C]
0x1800994d6  cmp     ecx, 8
0x1800994d9  cmovnb  eax, [rsp+6D8h+var_58]
0x1800994e1  mov     [rsp+6D8h+var_62C], eax
0x1800994e8  lea     r8, [rsp+6D8h+var_668]
0x1800994ed  mov     rcx, cs:__imp_D3DKMTOutputDuplPresentToHwQueue
0x1800994f4  call    ??$CallAndLogImpl@P6AJPEBU_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE@@@ZPEAU1@@@YAJP6AJPEBU_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE@@@ZPEBDPEAU0@@Z; CallAndLogImpl<long (*)(_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE const *),_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *>(long (*)(_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE const *),char const *,_D3DKMT_OUTPUTDUPLPRESENTTOHWQUEUE *)
0x1800994f9  mov     ebx, eax
0x1800994fb  jmp     loc_1800996E1
0x180099500  mov     eax, [r14+68h]
0x180099504  mov     [rsp+6D8h+var_600], eax
0x18009950b  lea     eax, [rdi-1]
0x18009950e  mov     [rsp+6D8h+var_5A4], eax
0x180099515  mov     rax, [rsi+28h]
0x180099519  mov     [rsp+6D8h+var_38], rax
0x180099521  mov     eax, [rsi+24h]
0x180099524  mov     [rsp+6D8h+var_40], eax
0x18009952b  mov     rax, [rsp+6D8h+var_680]
0x180099530  mov     [rsp+6D8h+var_608], rax
0x180099538  mov     rcx, [rsi+8]
0x18009953c  mov     eax, [rcx]
0x18009953e  mov     [rsp+6D8h+var_5EC], eax
0x180099545  cmp     edi, r15d
0x180099548  jbe     short loc_180099556
0x18009954a  lea     rax, [rcx+4]
0x18009954e  mov     [rsp+6D8h+var_50], rax
0x180099556  mov     rcx, [rsi+10h]
0x18009955a  test    rcx, rcx
0x18009955d  jz      short loc_180099579
0x18009955f  mov     eax, [rcx]
0x180099561  mov     [rsp+6D8h+var_5E8], eax
0x180099568  cmp     edi, r15d
0x18009956b  jbe     short loc_180099579
0x18009956d  lea     rax, [rcx+4]
0x180099571  mov     [rsp+6D8h+var_48], rax
0x180099579  test    bl, 4
0x18009957c  jnz     short loc_180099584
0x18009957e  bt      ebx, 0Fh
0x180099582  jnb     short loc_18009958F
0x180099584  btr     ebx, 0Dh
0x180099588  mov     [rsp+6D8h+var_5A8], ebx
0x18009958f  mov     r8d, 2
0x180099595  mov     dl, 0Fh
0x180099597  mov     rcx, [r14+48h]
0x18009959b  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800995a0  test    al, al
0x1800995a2  jz      loc_1800996AF
0x1800995a8  cmp     dword ptr [rsi+34h], 0
0x1800995ac  jz      loc_1800996AF
0x1800995b2  mov     r8d, [rsi+38h]
0x1800995b6  mov     ecx, r8d
0x1800995b9  test    r8d, r8d
0x1800995bc  jz      loc_180099657
0x1800995c2  sub     ecx, 1
0x1800995c5  jz      loc_180099657
0x1800995cb  sub     ecx, 1
0x1800995ce  jz      loc_180099657
0x1800995d4  sub     ecx, 1
0x1800995d7  jz      short loc_180099657
0x1800995d9  sub     ecx, 1
0x1800995dc  jz      short loc_180099657
0x1800995de  cmp     ecx, 1
0x1800995e1  jz      short loc_180099653
0x1800995e3  mov     [rsp+6D8h+var_6B8], r15b; bool
0x1800995e8  lea     r8, aDriverSetInval; "Driver set invalid sync interval overri"...
0x1800995ef  mov     edx, 80070057h; unsigned int
0x1800995f4  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800995fb  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180099600  nop
0x180099601  lea     rcx, [rsp+6D8h+var_680]
0x180099606  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18009960b  nop
0x18009960c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix> `wil::Feature<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::GetImpl(void)'::`2'::impl
0x180099613  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D11PresentPacketsCleanupFix>::__private_IsEnabled(void)
0x180099618  mov     rdx, [rsi]
0x18009961b  test    al, al
0x18009961d  jz      short loc_18009962D
0x18009961f  lea     rcx, [r14+700h]
0x180099626  call    ?FreeToken@?$OpaqueHandleManager@V?$shared_ptr@UBatchablePresent@@@std@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<std::shared_ptr<BatchablePresent>>::FreeToken(void *)
0x18009962b  jmp     short loc_18009963A
0x18009962d  lea     rcx, [r14+740h]
0x180099634  call    ?FreeToken@?$OpaqueHandleManager@UBatchablePresent@@@NDXGI@@QEAAXPEAX@Z; NDXGI::OpaqueHandleManager<BatchablePresent>::FreeToken(void *)
0x180099639  nop
0x18009963a  mov     rcx, [rsp+6D8h+var_690+8]; this
0x18009963f  test    rcx, rcx
0x180099642  jz      short loc_180099649
0x180099644  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180099649  mov     eax, 80070057h
0x18009964e  jmp     loc_18009990E
0x180099653  xor     edx, edx
0x180099655  jmp     short loc_18009965A
0x180099657  mov     edx, r8d
0x18009965a  test    bl, 4
0x18009965d  jz      short loc_180099674
0x18009965f  bt      ebx, 1Bh
0x180099663  mov     eax, [rsp+6D8h+var_5AC]
0x18009966a  cmovnb  eax, edx
0x18009966d  mov     [rsp+6D8h+var_5AC], eax
0x180099674  bt      ebx, 0Fh
0x180099678  jnb     short loc_1800996AF
0x18009967a  cmp     [rsp+6D8h+var_498], 2
0x180099682  jnz     short loc_1800996AF
0x180099684  mov     ecx, [rsp+6D8h+var_45C]
0x18009968b  bt      ecx, 13h
0x18009968f  jb      short loc_1800996AF
0x180099691  mov     [rsp+6D8h+var_460], edx
0x180099698  xor     eax, eax
0x18009969a  cmp     r8d, 5
0x18009969e  cmovz   eax, r9d
0x1800996a2  btr     ecx, 17h
0x1800996a6  or      eax, ecx
0x1800996a8  mov     [rsp+6D8h+var_45C], eax
0x1800996af  lea     r8, [rsp+6D8h+var_608]
0x1800996b7  mov     rcx, cs:__imp_D3DKMTSubmitPresentToHwQueue
0x1800996be  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_SUBMITPRESENTTOHWQUEUE@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_SUBMITPRESENTTOHWQUEUE@@@ZPEBD0@Z; CallAndLogImpl<long (*)(_D3DKMT_SUBMITPRESENTTOHWQUEUE *),_D3DKMT_SUBMITPRESENTTOHWQUEUE *>(long (*)(_D3DKMT_SUBMITPRESENTTOHWQUEUE *),char const *,_D3DKMT_SUBMITPRESENTTOHWQUEUE *)
0x1800996c3  mov     ebx, eax
0x1800996c5  mov     r8d, r15d
0x1800996c8  mov     dl, 0Fh
0x1800996ca  mov     rcx, [r14+48h]
0x1800996ce  call    ?IsD3DDDIVersionOrLater@CDevice@@QEBA_NW4EDDIVersion@@I@Z; CDevice::IsD3DDDIVersionOrLater(EDDIVersion,uint)
0x1800996d3  test    al, al
0x1800996d5  jz      short loc_1800996E1
0x1800996d7  mov     al, [rsp+6D8h+var_30]
0x1800996de  mov     [rsi+30h], al
0x1800996e1  lea     rcx, [rsp+6D8h+var_680]
0x1800996e6  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800996eb  nop
0x1800996ec  mov     eax, 0C01E000Dh
0x1800996f1  cmp     ebx, eax
0x1800996f3  jg      short loc_180099737
0x1800996f5  jz      short loc_18009971F
0x1800996f7  lea     eax, [rbx+3FFFFFF3h]
0x1800996fd  test    eax, 0FFFFFFEFh
0x180099702  jz      short loc_180099762
0x180099704  cmp     ebx, 0C01E0000h
0x18009970a  jz      short loc_180099721
0x18009970c  lea     eax, [rbx+3FE1FFFBh]
0x180099712  cmp     eax, 2
0x180099715  jbe     short loc_180099721
0x180099717  cmp     ebx, 0C01E000Bh
0x18009971d  jmp     short loc_180099760
0x18009971f  xor     ebx, ebx
0x180099721  mov     eax, [r14+4E0h]
0x180099728  shr     eax, 1Fh
0x18009972b  neg     al
0x18009972d  sbb     edi, edi
0x18009972f  and     edi, 88760870h
0x180099735  jmp     short loc_180099772
0x180099737  lea     eax, [rbx+3FE1FFF2h]
0x18009973d  cmp     eax, r15d
0x180099740  jbe     short loc_180099770
0x180099742  cmp     ebx, 0C01E0010h
0x180099748  jz      short loc_180099770
0x18009974a  cmp     ebx, 0C01E0018h
0x180099750  jz      short loc_180099721
0x180099752  cmp     ebx, 0C01E0342h
0x180099758  jz      short loc_180099721
0x18009975a  cmp     ebx, 103h
0x180099760  jz      short loc_180099770
0x180099762  mov     edx, ebx; int
0x180099764  mov     rcx, r14; this
0x180099767  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJ@Z; NDXGI::CDevice::NTStatusToHResult(long)
0x18009976c  mov     edi, eax
0x18009976e  jmp     short loc_180099772
0x180099770  xor     edi, edi
0x180099772  cmp     byte ptr [r14+382h], 0
0x18009977a  jz      short loc_18009978F
0x18009977c  mov     rax, [r14+580h]
0x180099783  test    rax, rax
0x180099786  jz      short loc_1800997E2
0x180099788  mov     [rax], edi
0x18009978a  mov     [rax+4], ebx
0x18009978d  jmp     short loc_1800997E2
0x18009978f  lea     r15, [r14+538h]
0x180099796  mov     rcx, r15; SRWLock
0x180099799  call    cs:__imp_AcquireSRWLockShared
0x18009979f  call    cs:__imp_GetCurrentThreadId
0x1800997a5  mov     [rsp+6D8h+var_6A8], eax
0x1800997a9  lea     rcx, [r14+540h]
0x1800997b0  lea     r8, [rsp+6D8h+var_6A8]
0x1800997b5  lea     rdx, [rsp+6D8h+var_6A0]
0x1800997ba  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSD3D11SharedResourceCreationArgs@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSD3D11SharedResourceCreationArgs@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SD3D11SharedResourceCreationArgs *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SD3D11SharedResourceCreationArgs *>>,0>>::find(ulong const &)
0x1800997bf  mov     rax, [rax]
0x1800997c2  cmp     rax, [r14+548h]
  ... truncated ...
```
