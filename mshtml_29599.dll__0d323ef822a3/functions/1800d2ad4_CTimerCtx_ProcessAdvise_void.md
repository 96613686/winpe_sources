# CTimerCtx::ProcessAdvise(void)

- ea: `0x1800d2ad4`
- end: `0x1800d33ee`
- name: `?ProcessAdvise@CTimerCtx@@IEAAJXZ`
- size: `2330`
- prototype: `__int64 __fastcall(CTimerCtx *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d2a60`
- `0x1800d2aa0`
- `0x180b49410`

## callees

- `0x1800d28e0`
- `0x1800d2ad4`
- `0x1800d351c`
- `0x1801cd074`
- `0x180332974`
- `0x180497b20`
- `0x180497b40`
- `0x180635c24`
- `0x1807462f4`
- `0x18079b8d4`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800d2fa5`
- `KERNEL32!QueryPerformanceCounter` at `0x1800d2fa5`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d31eb`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800d31eb`
- `KERNEL32!GetLastError` at `0x1800d330e`
- `KERNEL32!GetLastError` at `0x1800d330e`
- `KERNEL32!GetCurrentThreadId` at `0x1800d30c1`
- `KERNEL32!GetCurrentThreadId` at `0x1800d31a9`
- `KERNEL32!GetCurrentThreadId` at `0x1800d30c1`
- `KERNEL32!GetCurrentThreadId` at `0x1800d31a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2d5d`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2dec`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2d5d`
- `KERNEL32!LeaveCriticalSection` at `0x1800d2dec`
- `KERNEL32!EnterCriticalSection` at `0x1800d2d2c`
- `KERNEL32!EnterCriticalSection` at `0x1800d2dd6`
- `KERNEL32!EnterCriticalSection` at `0x1800d2d2c`
- `KERNEL32!EnterCriticalSection` at `0x1800d2dd6`
- `KERNEL32!SetEvent` at `0x1800d2dc3`
- `KERNEL32!SetEvent` at `0x1800d2dc3`
- `KERNEL32!CreateEventW` at `0x1800d32fc`
- `KERNEL32!CreateEventW` at `0x1800d32fc`
- `USER32!GetWindowThreadProcessId` at `0x1800d30b9`
- `USER32!GetWindowThreadProcessId` at `0x1800d31a1`
- `USER32!GetWindowThreadProcessId` at `0x1800d30b9`
- `USER32!GetWindowThreadProcessId` at `0x1800d31a1`
- `USER32!SetTimer` at `0x1800d3112`
- `USER32!SetTimer` at `0x1800d31d9`
- `USER32!SetTimer` at `0x1800d3112`
- `USER32!SetTimer` at `0x1800d31d9`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bad`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bbb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bcc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bd6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2d71`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2d7b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2f3e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2f4e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d3029`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d3039`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d30cf`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d31b7`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bad`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bbb`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bcc`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2bd6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2d71`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2d7b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2f3e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d2f4e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d3029`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d3039`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d30cf`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800d31b7`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2b26`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2c3c`
- `OLEAUT32!__imp_VariantInit` at `0x1800d3138`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2b26`
- `OLEAUT32!__imp_VariantInit` at `0x1800d2c3c`
- `OLEAUT32!__imp_VariantInit` at `0x1800d3138`
- `OLEAUT32!__imp_VariantClear` at `0x1800d2b30`
- `OLEAUT32!__imp_VariantClear` at `0x1800d2b30`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d325d`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800d325d`

## pseudocode

```c
HRESULT __fastcall CTimerCtx::ProcessAdvise(CTimerCtx *this)
{
  __int64 v2; // r15
  VARTYPE vt; // cx
  unsigned int Lo; // ebx
  HRESULT v5; // esi
  int v6; // r13d
  __int64 v7; // r12
  __int64 v8; // r15
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  struct IE_GLOBAL_THREAD_STATE *v11; // rax
  unsigned int v12; // r12d
  unsigned int v13; // r15d
  void (__fastcall *v14)(__int64, LARGE_INTEGER *); // rax
  BOOL v15; // ecx
  _DWORD *v16; // r13
  unsigned int v17; // r8d
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // ecx
  __int64 v23; // r15
  struct _RTL_CRITICAL_SECTION *v24; // rcx
  __int64 v25; // rdx
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  struct _RTL_CRITICAL_SECTION *v27; // rcx
  struct _RTL_CRITICAL_SECTION *v28; // rcx
  int v29; // ebx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v31; // r13
  __int64 v32; // rcx
  int v33; // ebx
  __int64 v34; // r12
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rsi
  CImplAry *v39; // rcx
  int v40; // r8d
  __int64 v41; // rcx
  __int64 v42; // r9
  unsigned int v43; // eax
  int v44; // edx
  __int64 v45; // r8
  unsigned int v46; // eax
  HWND v47; // rcx
  __int64 v49; // rcx
  __int64 v50; // r12
  __int64 v51; // r15
  int v52; // ecx
  GUID v53; // xmm0
  HRESULT result; // eax
  __int64 v55; // rsi
  LARGE_INTEGER v56; // r8
  unsigned __int64 v57; // rbx
  HWND *v58; // r15
  __int128 v59; // xmm0
  __int64 (__fastcall *v60)(HWND, UINT_PTR, __int64); // rax
  UINT_PTR v61; // rdx
  HWND v62; // rcx
  DWORD v64; // ebx
  unsigned int v65; // edx
  CTimerAdvise *v66; // rcx
  DWORD WindowThreadProcessId; // ebx
  void (__fastcall *v68)(__int64, LARGE_INTEGER *); // rax
  unsigned int v69; // edx
  CTimerAdvise *v70; // rcx
  signed int LastError; // r12d
  HANDLE EventW; // rax
  int v73; // edx
  unsigned int v74; // ebx
  __int64 v75; // rdx
  unsigned int v76; // edx
  CTimerAdvise *v77; // rcx
  int v78; // [rsp+38h] [rbp-D0h]
  int v79; // [rsp+38h] [rbp-D0h]
  char v80; // [rsp+3Ch] [rbp-CCh]
  HRESULT v81; // [rsp+40h] [rbp-C8h]
  __int64 v82; // [rsp+48h] [rbp-C0h]
  __int64 v83; // [rsp+50h] [rbp-B8h]
  unsigned int v84; // [rsp+50h] [rbp-B8h]
  unsigned int v85; // [rsp+58h] [rbp-B0h]
  LARGE_INTEGER PerformanceCount[3]; // [rsp+60h] [rbp-A8h] BYREF
  IRecordInfo *pRecInfo; // [rsp+78h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v89; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v90; // [rsp+B8h] [rbp-50h] BYREF
  VARIANTARG pvargDest; // [rsp+D0h] [rbp-38h] BYREF

  v2 = 0;
  if ( *((int *)this + 17) > 0 )
    return 0;
  if ( *((_DWORD *)this + 18) )
  {
    *((_DWORD *)this + 22) = 1;
    return 0;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  VariantClear(&pvarg);
  vt = 19;
  pvarg.vt = 19;
  if ( *((int *)this + 17) > 0 || *((_DWORD *)this + 18) )
  {
    Lo = *((_DWORD *)this + 16);
    pvarg.lVal = Lo;
  }
  else
  {
    v55 = *((_QWORD *)this + 4);
    PerformanceCount[0].QuadPart = 0;
    QueryPerformanceCounter(PerformanceCount);
    v56 = CQPCTick::s_qpcFrequency;
    if ( CQPCTick::s_qpcFrequency.QuadPart
      || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
          v56 = CQPCTick::s_qpcFrequency,
          CQPCTick::s_qpcFrequency.QuadPart) )
    {
      LODWORD(v57) = PerformanceCount[0].LowPart;
      if ( PerformanceCount[0].QuadPart && v56.QuadPart && v56.QuadPart != 1000 )
        v57 = 1000 * (PerformanceCount[0].QuadPart % (unsigned __int64)v56.QuadPart) / v56.QuadPart
            + 1000 * (PerformanceCount[0].QuadPart / (unsigned __int64)v56.QuadPart);
    }
    else
    {
      LODWORD(v57) = 0;
    }
    Lo = v57 - *(_DWORD *)(v55 + 536);
    vt = pvarg.vt;
    pvarg.lVal = Lo;
  }
  if ( vt == 19 )
  {
    v5 = 0;
    v81 = 0;
  }
  else
  {
    memset(&pvargDest, 0, sizeof(pvargDest));
    result = VariantChangeType(&pvargDest, &pvarg, 0, 0x13u);
    v81 = result;
    v5 = result;
    if ( result < 0 )
      return result;
    Lo = pvargDest.cyVal.Lo;
  }
  v6 = *((_DWORD *)this + 11) - 1;
  *((_DWORD *)this + 16) = Lo;
  v78 = v6;
  *((_DWORD *)this + 18) = 1;
  if ( v6 < 0 )
    goto LABEL_39;
  v7 = v6;
  v82 = v6;
  do
  {
    v8 = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v7);
    v9 = *(_OWORD *)(v8 + 60);
    v83 = *(_QWORD *)(v8 + 24);
    v10 = *(_OWORD *)GlobalThreadState();
    *(_OWORD *)&PerformanceCount[1].LowPart = v10;
    v80 = *((_BYTE *)GlobalThreadState() + 16);
    LOBYTE(pRecInfo) = v80;
    *(_OWORD *)GlobalThreadState() = v9;
    v11 = GlobalThreadState();
    HIDWORD(pRecInfo) = 1;
    *((_BYTE *)v11 + 16) = 1;
    if ( !*(_DWORD *)(v8 + 40) )
    {
      v85 = *(_DWORD *)(v8 + 4);
      if ( v85 >= Lo )
      {
        v12 = *(_DWORD *)(v8 + 12);
        if ( v12 > Lo && !*(_DWORD *)(v8 + 44) )
        {
LABEL_35:
          v7 = v82;
LABEL_36:
          *(_OWORD *)GlobalThreadState() = v10;
          *((_BYTE *)GlobalThreadState() + 16) = v80;
          goto LABEL_37;
        }
        *(_DWORD *)(v8 + 44) = 0;
        if ( v12 > Lo )
        {
          v12 = Lo;
          *(_DWORD *)(v8 + 12) = Lo;
        }
        v13 = *(_DWORD *)(v8 + 8);
        if ( v13 )
        {
          memset(&v90, 0, sizeof(v90));
          VariantInit(&v90);
          v90.vt = 19;
          v90.lVal = Lo - (Lo - v12) % v13;
          if ( v83 )
          {
            v14 = *(void (__fastcall **)(__int64, LARGE_INTEGER *))(*(_QWORD *)v83 + 24LL);
            *(_OWORD *)&PerformanceCount[1].LowPart = *(_OWORD *)&v90.vt;
            pRecInfo = v90.pRecInfo;
            v14(v83, &PerformanceCount[1]);
          }
          v15 = 0;
          v7 = v82;
          v16 = *(_DWORD **)(*((_QWORD *)this + 6) + 8 * v82);
          v17 = v16[2];
          if ( v17 <= 0x14 )
          {
            v18 = 4 * v17;
            v19 = Lo - v16[12];
            v16[12] = Lo;
            if ( 4 * v17 < 0x14 )
              v18 = 20;
            if ( v19 > v18 )
              v19 = v18;
            ++v16[14];
            v16[13] += v19;
            v20 = v16[14];
            v21 = v16[13];
            if ( v20 >= 0x14 )
            {
              v21 >>= 1;
              v20 >>= 1;
              v16[14] = v20;
              v16[13] = v21;
            }
            v15 = v21 / v20 >= v17;
          }
          v16[11] = v15;
          v22 = v13 + v16[3];
          if ( v22 <= Lo )
          {
            v22 = v13 + Lo;
            v16[11] = 1;
          }
          if ( v85 == -1 || v22 < v85 )
          {
            v16[3] = v22;
            v23 = *((_QWORD *)this + 4);
            if ( *(_DWORD *)(v23 + 468) )
              goto LABEL_30;
            LastError = 0;
            CBaseFT::EnterCriticalSection(*((CBaseFT **)this + 4));
            if ( !*(_DWORD *)(v23 + 468) )
            {
              EventW = CreateEventW(0, 0, 0, 0);
              *(_QWORD *)(v23 + 480) = EventW;
              if ( EventW || (LastError = GetLastError()) == 0 )
              {
                LastError = CExecFT::Launch((CExecFT *)v23, v73);
                if ( !LastError )
                  *(_DWORD *)(v23 + 468) = 1;
              }
            }
            CBaseFT::LeaveCriticalSection((CBaseFT *)v23);
            if ( LastError >= 0 )
            {
LABEL_30:
              v24 = *(struct _RTL_CRITICAL_SECTION **)(v23 + 8);
              if ( v24 )
                EnterCriticalSection(v24);
              v25 = 32LL * (unsigned int)(v16[8] - 1);
              *(_DWORD *)(v25 + *(_QWORD *)(v23 + 72)) = v16[3];
              *(_DWORD *)(v25 + *(_QWORD *)(v23 + 72) + 4) = v16[11];
              v26 = *(struct _RTL_CRITICAL_SECTION **)(v23 + 8);
              if ( v26 )
                LeaveCriticalSection(v26);
            }
            v6 = v78;
            *((_DWORD *)this + 22) = 1;
            goto LABEL_35;
          }
          CTimerMan::RemoveAdvise(
            *((CTimerMan **)this + 4),
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v82) + 32LL) - 1);
          v70 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8 * v82);
          if ( v70 )
            CTimerAdvise::`scalar deleting destructor'(v70, v69);
          v6 = v78;
LABEL_110:
          CImplAry::Delete((CTimerCtx *)((char *)this + 40), 8u, v6);
          goto LABEL_36;
        }
        memset(&v89, 0, sizeof(v89));
        VariantInit(&v89);
        v89.vt = 19;
        v89.lVal = v12;
        if ( v83 )
        {
          v68 = *(void (__fastcall **)(__int64, LARGE_INTEGER *))(*(_QWORD *)v83 + 24LL);
          *(_OWORD *)&PerformanceCount[1].LowPart = *(_OWORD *)&v89.vt;
          pRecInfo = v89.pRecInfo;
          v68(v83, &PerformanceCount[1]);
        }
        v7 = v82;
      }
      CTimerMan::RemoveAdvise(
        *((CTimerMan **)this + 4),
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v7) + 32LL) - 1);
      v66 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8 * v7);
      if ( v66 )
        CTimerAdvise::`scalar deleting destructor'(v66, v65);
      goto LABEL_110;
    }
    ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&PerformanceCount[1]);
LABEL_37:
    --v6;
    --v7;
    v2 = 0;
    v78 = v6;
    v82 = v7;
  }
  while ( v6 >= 0 );
  v5 = v81;
LABEL_39:
  if ( *((_DWORD *)this + 19) )
  {
    v74 = *((_DWORD *)this + 11);
    while ( (--v74 & 0x80000000) == 0 )
    {
      v75 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * v74);
      if ( *(_DWORD *)(v75 + 40) )
      {
        CTimerMan::RemoveAdvise(*((CTimerMan **)this + 4), *(_DWORD *)(v75 + 32) - 1);
        v2 = 0;
        v77 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8LL * v74);
        if ( v77 )
          CTimerAdvise::`scalar deleting destructor'(v77, v76);
        CImplAry::Delete((CTimerCtx *)((char *)this + 40), 8u, v74);
      }
      else
      {
        v2 = 0;
      }
    }
    *((_DWORD *)this + 19) = 0;
  }
  if ( *((_DWORD *)this + 22) )
  {
    SetEvent(*(HANDLE *)(*((_QWORD *)this + 4) + 480LL));
    *((_DWORD *)this + 22) = 0;
  }
  v27 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  if ( v27 )
    EnterCriticalSection(v27);
  v28 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  v29 = *((_DWORD *)this + 21);
  *((_DWORD *)this + 18) = 0;
  if ( v28 )
    LeaveCriticalSection(v28);
  if ( v29 )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v31 = 0;
    v32 = (unsigned int)tls_index;
    v33 = *((_DWORD *)this + 23) + 1;
    *((_DWORD *)this + 23) = v33;
    v79 = v33;
    v34 = ThreadLocalStoragePointer[v32];
    v35 = *(_QWORD *)(v34 + 16);
    if ( v35 )
      v31 = *(_QWORD *)(v35 + 232);
    if ( !*(_QWORD *)(v31 + 96) )
      return -2147467259;
    if ( v35 )
      v2 = *(_QWORD *)(v35 + 232);
    v36 = *(_QWORD *)(v2 + 112);
    v37 = *(_DWORD *)(v36 + 4);
    v38 = *(_QWORD *)(v36 + 8);
    while ( v37 > 0 )
    {
      if ( *(CTimerCtx **)v38 == this && *(_DWORD *)(v38 + 16) == v33 )
      {
        if ( *(_DWORD *)(v38 + 24) != 10 )
          *(_DWORD *)(v38 + 24) = 10;
        if ( *(_DWORD *)(v38 + 32) )
          goto LABEL_89;
        if ( *((_BYTE *)GlobalThreadState() + 16) )
        {
          v58 = (HWND *)(v2 + 96);
          v59 = *(_OWORD *)GlobalThreadState();
        }
        else
        {
          v58 = (HWND *)(v2 + 96);
          WindowThreadProcessId = GetWindowThreadProcessId(*v58, 0);
          v59 = WindowThreadProcessId == GetCurrentThreadId() ? *(_OWORD *)GlobalThreadState() : *(_OWORD *)&GUID_NULL;
          v33 = v79;
        }
        v60 = (__int64 (__fastcall *)(HWND, UINT_PTR, __int64))qword_181591D28;
        v61 = *(unsigned int *)(v38 + 20);
        *(_OWORD *)(v38 + 40) = v59;
        v62 = *v58;
        if ( v60 ? v60(v62, v61, 10) : SetTimer(v62, v61, 0xAu, 0) )
        {
LABEL_89:
          if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
            McTemplateU0pqpq_EventWriteTransfer(
              v37,
              (unsigned int)&MSHTML_FORMSTIMER_RESET,
              *(_QWORD *)v38,
              *(_DWORD *)(v38 + 16),
              *(_QWORD *)(v38 + 8),
              *(_DWORD *)(v38 + 24));
          return 0;
        }
        break;
      }
      --v37;
      v38 += 56;
    }
    v39 = *(CImplAry **)(v31 + 112);
    v40 = *((_DWORD *)v39 + 1) + 1;
    if ( (unsigned int)v40 > *(_DWORD *)v39 >> 2 )
    {
      if ( v40 < 0 )
        return -2147024809;
      v5 = CImplAry::EnsureSizeWorker(v39, 0x38u, v40);
      if ( v5 )
        return v5;
    }
    else
    {
      v5 = 0;
    }
    v41 = *(_QWORD *)(v34 + 16);
    if ( v41 )
      v41 = *(_QWORD *)(v41 + 232);
    v42 = *(_QWORD *)(v41 + 112);
LABEL_61:
    v43 = *(_DWORD *)(v41 + 104) + 1;
    *(_DWORD *)(v41 + 104) = v43;
    if ( v43 < 0x2002 )
    {
      *(_DWORD *)(v41 + 104) = 8194;
      v43 = 8194;
    }
    v44 = *(_DWORD *)(v42 + 4);
    v45 = *(_QWORD *)(v42 + 8);
    while ( v44 > 0 )
    {
      if ( v43 == *(_DWORD *)(v45 + 20) )
        goto LABEL_61;
      --v44;
      v45 += 56;
    }
    v46 = *(_DWORD *)(v41 + 104);
    v47 = *(HWND *)(v31 + 96);
    v84 = v46;
    if ( qword_181591D28
       ? ((__int64 (__fastcall *)(HWND, _QWORD, __int64))qword_181591D28)(v47, v46, 10)
       : SetTimer(v47, v46, 0xAu, 0) )
    {
      v49 = *(_QWORD *)(v31 + 112);
      v50 = *(_QWORD *)(v49 + 8);
      v51 = 56LL * *(int *)(v49 + 4);
      *(_QWORD *)(v51 + v50 + 8) = CTimerCtx::TimerCallback;
      *(_DWORD *)(v51 + v50 + 20) = v84;
      *(_QWORD *)(v51 + v50 + 32) = 0;
      *(_QWORD *)(v51 + v50) = this;
      *(_DWORD *)(v51 + v50 + 16) = v33;
      *(_QWORD *)(v51 + v50 + 24) = 10;
      if ( *((_BYTE *)GlobalThreadState() + 16) )
      {
        v53 = *(GUID *)GlobalThreadState();
      }
      else
      {
        v64 = GetWindowThreadProcessId(*(HWND *)(v31 + 96), 0);
        if ( v64 == GetCurrentThreadId() )
          v53 = *(GUID *)GlobalThreadState();
        else
          v53 = GUID_NULL;
        v33 = v79;
      }
      *(GUID *)(v51 + v50 + 40) = v53;
      ++*(_DWORD *)(*(_QWORD *)(v31 + 112) + 4LL);
      if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
        McTemplateU0pqpq_EventWriteTransfer(
          v52,
          (unsigned int)&MSHTML_FORMSTIMER_SET,
          (_DWORD)this,
          v33,
          (char)CTimerCtx::TimerCallback,
          10);
    }
    else
    {
      return -2147467259;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800d2ad4  mov     rax, rsp
0x1800d2ad7  mov     [rax+8], rcx
0x1800d2adb  push    rbp
0x1800d2adc  push    rbx
0x1800d2add  push    rsi
0x1800d2ade  push    rdi
0x1800d2adf  push    r12
0x1800d2ae1  push    r13
0x1800d2ae3  push    r14
0x1800d2ae5  push    r15
0x1800d2ae7  lea     rbp, [rax-48h]
0x1800d2aeb  sub     rsp, 108h
0x1800d2af2  mov     rdi, [rbp+40h+arg_0]
0x1800d2af6  xor     r15d, r15d
0x1800d2af9  movaps  xmmword ptr [rax-58h], xmm6
0x1800d2afd  movaps  xmmword ptr [rax-68h], xmm7
0x1800d2b01  cmp     [rdi+44h], r15d
0x1800d2b05  jg      loc_1800D323B
0x1800d2b0b  cmp     [rdi+48h], r15d
0x1800d2b0f  jnz     loc_1800D3234
0x1800d2b15  xorps   xmm0, xmm0
0x1800d2b18  lea     rcx, [rbp+40h+pvarg]; pvarg
0x1800d2b1c  xor     eax, eax
0x1800d2b1e  movups  xmmword ptr [rbp+40h+pvarg], xmm0
0x1800d2b22  mov     qword ptr [rbp+40h+pvarg+10h], rax
0x1800d2b26  call    cs:__imp_VariantInit
0x1800d2b2c  lea     rcx, [rbp+40h+pvarg]; pvarg
0x1800d2b30  call    cs:__imp_VariantClear
0x1800d2b36  lea     r14d, [r15+13h]
0x1800d2b3a  movzx   ecx, r14w
0x1800d2b3e  mov     word ptr [rbp+40h+pvarg], cx
0x1800d2b42  cmp     [rdi+44h], r15d
0x1800d2b46  jg      short loc_1800D2B52
0x1800d2b48  cmp     [rdi+48h], r15d
0x1800d2b4c  jz      loc_1800D2F97
0x1800d2b52  mov     eax, [rdi+40h]
0x1800d2b55  mov     ebx, eax
0x1800d2b57  mov     dword ptr [rbp+40h+pvarg+8], eax
0x1800d2b5a  cmp     cx, r14w
0x1800d2b5e  jnz     loc_1800D3242
0x1800d2b64  mov     esi, r15d
0x1800d2b67  mov     dword ptr [rsp+140h+var_108], r15d
0x1800d2b6c  mov     r13d, [rdi+2Ch]
0x1800d2b70  mov     r14d, 1
0x1800d2b76  sub     r13d, r14d
0x1800d2b79  mov     [rdi+40h], ebx
0x1800d2b7c  mov     [rsp+140h+var_110], r13d
0x1800d2b81  mov     [rdi+48h], r14d
0x1800d2b85  js      loc_1800D2DA8
0x1800d2b8b  movsxd  r12, r13d
0x1800d2b8e  lea     esi, [r14+12h]
0x1800d2b92  mov     [rsp+140h+var_100], r12
0x1800d2b97  mov     rax, [rdi+30h]
0x1800d2b9b  mov     r15, [rax+r12*8]
0x1800d2b9f  mov     rax, [r15+18h]
0x1800d2ba3  movups  xmm6, xmmword ptr [r15+3Ch]
0x1800d2ba8  mov     [rsp+140h+var_F8], rax
0x1800d2bad  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2bb3  movups  xmm7, xmmword ptr [rax]
0x1800d2bb6  movups  xmmword ptr [rsp+140h+PerformanceCount+8], xmm7
0x1800d2bbb  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2bc1  mov     al, [rax+10h]
0x1800d2bc4  mov     [rsp+140h+var_10C], al
0x1800d2bc8  mov     byte ptr [rsp+140h+var_D0], al
0x1800d2bcc  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2bd2  movdqu  xmmword ptr [rax], xmm6
0x1800d2bd6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2bdc  xor     ecx, ecx
0x1800d2bde  mov     dword ptr [rsp+140h+var_D0+4], r14d
0x1800d2be3  mov     [rax+10h], r14b
0x1800d2be7  cmp     [r15+28h], ecx
0x1800d2beb  jnz     loc_1800D311D
0x1800d2bf1  mov     eax, [r15+4]
0x1800d2bf5  mov     dword ptr [rsp+140h+var_F0], eax
0x1800d2bf9  cmp     eax, ebx
0x1800d2bfb  jb      loc_1800D3159
0x1800d2c01  mov     r12d, [r15+0Ch]
0x1800d2c05  cmp     r12d, ebx
0x1800d2c08  ja      loc_1800D3103
0x1800d2c0e  mov     [r15+2Ch], ecx
0x1800d2c12  cmp     r12d, ebx
0x1800d2c15  jbe     short loc_1800D2C1E
0x1800d2c17  mov     r12d, ebx
0x1800d2c1a  mov     [r15+0Ch], ebx
0x1800d2c1e  mov     r15d, [r15+8]
0x1800d2c22  xor     eax, eax
0x1800d2c24  xorps   xmm0, xmm0
0x1800d2c27  test    r15d, r15d
0x1800d2c2a  jz      loc_1800D312C
0x1800d2c30  lea     rcx, [rbp+40h+var_90]; pvarg
0x1800d2c34  mov     qword ptr [rbp+40h+var_90+10h], rax
0x1800d2c38  movups  xmmword ptr [rbp+40h+var_90], xmm0
0x1800d2c3c  call    cs:__imp_VariantInit
0x1800d2c42  mov     rcx, [rsp+140h+var_F8]
0x1800d2c47  xor     edx, edx
0x1800d2c49  mov     eax, ebx
0x1800d2c4b  mov     word ptr [rbp+40h+var_90], si
0x1800d2c4f  sub     eax, r12d
0x1800d2c52  div     r15d
0x1800d2c55  mov     eax, ebx
0x1800d2c57  sub     eax, edx
0x1800d2c59  mov     dword ptr [rbp+40h+var_90+8], eax
0x1800d2c5c  test    rcx, rcx
0x1800d2c5f  jz      short loc_1800D2C86
0x1800d2c61  mov     rax, [rcx]
0x1800d2c64  lea     rdx, [rsp+140h+PerformanceCount+8]
0x1800d2c69  movups  xmm0, xmmword ptr [rbp+40h+var_90]
0x1800d2c6d  movsd   xmm1, qword ptr [rbp+40h+var_90+10h]
0x1800d2c72  mov     rax, [rax+18h]
0x1800d2c76  movaps  xmmword ptr [rsp+140h+PerformanceCount+8], xmm0
0x1800d2c7b  movsd   [rsp+140h+var_D0], xmm1
0x1800d2c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c86  mov     rax, [rdi+30h]
0x1800d2c8a  xor     ecx, ecx
0x1800d2c8c  mov     r12, [rsp+140h+var_100]
0x1800d2c91  lea     edx, [rcx+14h]
0x1800d2c94  mov     r13, [rax+r12*8]
0x1800d2c98  mov     r8d, [r13+8]
0x1800d2c9c  cmp     r8d, edx
0x1800d2c9f  ja      short loc_1800D2CE9
0x1800d2ca1  lea     eax, ds:0[r8*4]
0x1800d2ca9  mov     ecx, ebx
0x1800d2cab  sub     ecx, [r13+30h]
0x1800d2caf  cmp     eax, edx
0x1800d2cb1  mov     [r13+30h], ebx
0x1800d2cb5  cmovb   eax, edx
0x1800d2cb8  cmp     ecx, eax
0x1800d2cba  cmova   ecx, eax
0x1800d2cbd  add     [r13+38h], r14d
0x1800d2cc1  add     [r13+34h], ecx
0x1800d2cc5  mov     ecx, [r13+38h]
0x1800d2cc9  mov     eax, [r13+34h]
0x1800d2ccd  cmp     ecx, edx
0x1800d2ccf  jb      short loc_1800D2CDD
0x1800d2cd1  shr     eax, 1
0x1800d2cd3  shr     ecx, 1
0x1800d2cd5  mov     [r13+38h], ecx
0x1800d2cd9  mov     [r13+34h], eax
0x1800d2cdd  xor     edx, edx
0x1800d2cdf  div     ecx
0x1800d2ce1  xor     ecx, ecx
0x1800d2ce3  cmp     eax, r8d
0x1800d2ce6  setnb   cl
0x1800d2ce9  mov     [r13+2Ch], ecx
0x1800d2ced  mov     ecx, [r13+0Ch]
0x1800d2cf1  add     ecx, r15d
0x1800d2cf4  cmp     ecx, ebx
0x1800d2cf6  ja      short loc_1800D2D00
0x1800d2cf8  lea     ecx, [r15+rbx]
0x1800d2cfc  mov     [r13+2Ch], r14d
0x1800d2d00  mov     eax, dword ptr [rsp+140h+var_F0]
0x1800d2d04  cmp     eax, 0FFFFFFFFh
0x1800d2d07  jnz     loc_1800D32A3
0x1800d2d0d  mov     [r13+0Ch], ecx
0x1800d2d11  mov     r15, [rdi+20h]
0x1800d2d15  cmp     dword ptr [r15+1D4h], 0
0x1800d2d1d  jz      loc_1800D32DE
0x1800d2d23  mov     rcx, [r15+8]; lpCriticalSection
0x1800d2d27  test    rcx, rcx
0x1800d2d2a  jz      short loc_1800D2D32
0x1800d2d2c  call    cs:__imp_EnterCriticalSection
0x1800d2d32  mov     edx, [r13+20h]
0x1800d2d36  mov     rcx, [r15+48h]
0x1800d2d3a  sub     edx, r14d
0x1800d2d3d  mov     eax, [r13+0Ch]
0x1800d2d41  shl     rdx, 5
0x1800d2d45  mov     [rdx+rcx], eax
0x1800d2d48  mov     rcx, [r15+48h]
0x1800d2d4c  mov     eax, [r13+2Ch]
0x1800d2d50  mov     [rdx+rcx+4], eax
0x1800d2d54  mov     rcx, [r15+8]; lpCriticalSection
0x1800d2d58  test    rcx, rcx
0x1800d2d5b  jz      short loc_1800D2D63
0x1800d2d5d  call    cs:__imp_LeaveCriticalSection
0x1800d2d63  mov     r13d, [rsp+140h+var_110]
0x1800d2d68  mov     [rdi+58h], r14d
0x1800d2d6c  mov     r12, [rsp+140h+var_100]
0x1800d2d71  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2d77  movdqu  xmmword ptr [rax], xmm7
0x1800d2d7b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2d81  mov     cl, [rsp+140h+var_10C]
0x1800d2d85  mov     [rax+10h], cl
0x1800d2d88  sub     r13d, r14d
0x1800d2d8b  sub     r12, r14
0x1800d2d8e  xor     r15d, r15d
0x1800d2d91  mov     [rsp+140h+var_110], r13d
0x1800d2d96  mov     [rsp+140h+var_100], r12
0x1800d2d9b  test    r13d, r13d
0x1800d2d9e  jns     loc_1800D2B97
0x1800d2da4  mov     esi, dword ptr [rsp+140h+var_108]
0x1800d2da8  cmp     [rdi+4Ch], r15d
0x1800d2dac  jnz     loc_1800D3347
0x1800d2db2  cmp     [rdi+58h], r15d
0x1800d2db6  jz      short loc_1800D2DCD
0x1800d2db8  mov     rcx, [rdi+20h]
0x1800d2dbc  mov     rcx, [rcx+1E0h]; hEvent
0x1800d2dc3  call    cs:__imp_SetEvent
0x1800d2dc9  mov     [rdi+58h], r15d
0x1800d2dcd  mov     rcx, [rdi+8]; lpCriticalSection
0x1800d2dd1  test    rcx, rcx
0x1800d2dd4  jz      short loc_1800D2DDC
0x1800d2dd6  call    cs:__imp_EnterCriticalSection
0x1800d2ddc  mov     rcx, [rdi+8]; lpCriticalSection
0x1800d2de0  mov     ebx, [rdi+54h]
0x1800d2de3  mov     [rdi+48h], r15d
0x1800d2de7  test    rcx, rcx
0x1800d2dea  jz      short loc_1800D2DF2
0x1800d2dec  call    cs:__imp_LeaveCriticalSection
0x1800d2df2  test    ebx, ebx
0x1800d2df4  jz      loc_1800D2F73
0x1800d2dfa  mov     rax, gs:58h
0x1800d2e03  mov     r13, r15
0x1800d2e06  mov     ebx, [rdi+5Ch]
0x1800d2e09  mov     ecx, cs:_tls_index
0x1800d2e0f  add     ebx, r14d
0x1800d2e12  mov     edx, 10h
0x1800d2e17  mov     [rdi+5Ch], ebx
0x1800d2e1a  mov     [rsp+140h+var_110], ebx
0x1800d2e1e  mov     r12, [rax+rcx*8]
0x1800d2e22  mov     rax, [r12+rdx]
0x1800d2e26  test    rax, rax
0x1800d2e29  jz      short loc_1800D2E32
0x1800d2e2b  mov     r13, [rax+0E8h]
0x1800d2e32  cmp     [r13+60h], r15
0x1800d2e36  jz      loc_1800D3093
0x1800d2e3c  test    rax, rax
0x1800d2e3f  jz      short loc_1800D2E48
0x1800d2e41  mov     r15, [rax+0E8h]
0x1800d2e48  mov     rax, [r15+70h]
0x1800d2e4c  mov     ecx, [rax+4]
0x1800d2e4f  mov     rsi, [rax+8]
0x1800d2e53  test    ecx, ecx
0x1800d2e55  jle     short loc_1800D2E69
0x1800d2e57  cmp     [rsi], rdi
0x1800d2e5a  jz      loc_1800D300D
0x1800d2e60  sub     ecx, r14d
0x1800d2e63  add     rsi, 38h ; '8'
0x1800d2e67  jmp     short loc_1800D2E53
0x1800d2e69  mov     rcx, [r13+70h]; this
0x1800d2e6d  mov     r8d, [rcx+4]
0x1800d2e71  mov     eax, [rcx]
0x1800d2e73  inc     r8d; int
0x1800d2e76  shr     eax, 2
0x1800d2e79  cmp     r8d, eax
0x1800d2e7c  ja      loc_1800D30E1
0x1800d2e82  xor     esi, esi
0x1800d2e84  mov     ecx, 10h
0x1800d2e89  mov     rcx, [r12+rcx]
0x1800d2e8d  test    rcx, rcx
0x1800d2e90  jz      short loc_1800D2E99
0x1800d2e92  mov     rcx, [rcx+0E8h]
0x1800d2e99  mov     r9, [rcx+70h]
0x1800d2e9d  mov     r10d, 2002h
0x1800d2ea3  mov     eax, [rcx+68h]
0x1800d2ea6  inc     eax
0x1800d2ea8  mov     [rcx+68h], eax
0x1800d2eab  cmp     eax, r10d
0x1800d2eae  jb      loc_1800D33D6
0x1800d2eb4  mov     edx, [r9+4]
0x1800d2eb8  mov     r8, [r9+8]
0x1800d2ebc  test    edx, edx
0x1800d2ebe  jg      loc_1800D309D
0x1800d2ec4  mov     eax, [rcx+68h]
0x1800d2ec7  xor     r9d, r9d; lpTimerFunc
0x1800d2eca  mov     r10, cs:qword_181591D28
0x1800d2ed1  mov     edx, eax; nIDEvent
0x1800d2ed3  mov     rcx, [r13+60h]; hWnd
0x1800d2ed7  mov     [rsp+140h+var_F8], rax
0x1800d2edc  lea     r8d, [r9+0Ah]; uElapse
0x1800d2ee0  test    r10, r10
0x1800d2ee3  jz      loc_1800D3112
0x1800d2ee9  mov     rax, r10
0x1800d2eec  mov     [rsp+140h+var_120], r9d
0x1800d2ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2ef6  test    rax, rax
0x1800d2ef9  jz      loc_1800D3093
0x1800d2eff  mov     rcx, [r13+70h]
0x1800d2f03  movsxd  rax, dword ptr [rcx+4]
0x1800d2f07  mov     r12, [rcx+8]
0x1800d2f0b  imul    r15, rax, 38h ; '8'
0x1800d2f0f  lea     rax, ?TimerCallback@CTimerCtx@@QEAAJI@Z; CTimerCtx::TimerCallback(uint)
0x1800d2f16  mov     [r15+r12+8], rax
0x1800d2f1b  mov     rax, [rsp+140h+var_F8]
0x1800d2f20  mov     [r15+r12+14h], eax
0x1800d2f25  xor     eax, eax
0x1800d2f27  mov     [r15+r12+20h], rax
0x1800d2f2c  mov     [r15+r12], rdi
0x1800d2f30  mov     [r15+r12+10h], ebx
0x1800d2f35  mov     qword ptr [r15+r12+18h], 0Ah
0x1800d2f3e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2f44  cmp     byte ptr [rax+10h], 0
0x1800d2f48  jz      loc_1800D30B3
0x1800d2f4e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800d2f54  movups  xmm0, xmmword ptr [rax]
0x1800d2f57  movdqu  xmmword ptr [r15+r12+28h], xmm0
0x1800d2f5e  mov     rax, [r13+70h]
0x1800d2f62  add     [rax+4], r14d
0x1800d2f66  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1800d2f6d  jnz     loc_1800D3209
0x1800d2f73  mov     eax, esi
  ... truncated ...
```
