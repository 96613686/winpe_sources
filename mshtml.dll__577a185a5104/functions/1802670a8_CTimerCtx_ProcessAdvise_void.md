# CTimerCtx::ProcessAdvise(void)

- ea: `0x1802670a8`
- end: `0x180267a11`
- name: `?ProcessAdvise@CTimerCtx@@IEAAJXZ`
- size: `2409`
- prototype: `HRESULT __fastcall(CTimerCtx *this)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180267030`
- `0x180267070`
- `0x180b62040`

## callees

- `0x18006ad94`
- `0x180157d14`
- `0x180157d3c`
- `0x1801afc40`
- `0x180266fa0`
- `0x1802670a8`
- `0x180267cc4`
- `0x180267d24`
- `0x180632368`
- `0x18074c5ac`
- `0x1807a7ab4`
- `0x181104010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1802675d4`
- `KERNEL32!QueryPerformanceCounter` at `0x1802675d4`
- `KERNEL32!QueryPerformanceFrequency` at `0x18026780c`
- `KERNEL32!QueryPerformanceFrequency` at `0x18026780c`
- `KERNEL32!GetLastError` at `0x180267941`
- `KERNEL32!GetLastError` at `0x180267941`
- `KERNEL32!GetCurrentThreadId` at `0x1802676ee`
- `KERNEL32!GetCurrentThreadId` at `0x1802676ee`
- `KERNEL32!LeaveCriticalSection` at `0x18026735d`
- `KERNEL32!LeaveCriticalSection` at `0x18026740a`
- `KERNEL32!LeaveCriticalSection` at `0x18026735d`
- `KERNEL32!LeaveCriticalSection` at `0x18026740a`
- `KERNEL32!EnterCriticalSection` at `0x180267327`
- `KERNEL32!EnterCriticalSection` at `0x1802673ee`
- `KERNEL32!EnterCriticalSection` at `0x180267327`
- `KERNEL32!EnterCriticalSection` at `0x1802673ee`
- `KERNEL32!SetEvent` at `0x1802673d5`
- `KERNEL32!SetEvent` at `0x1802673d5`
- `KERNEL32!CreateEventW` at `0x180267929`
- `KERNEL32!CreateEventW` at `0x180267929`
- `USER32!GetWindowThreadProcessId` at `0x1802676e0`
- `USER32!GetWindowThreadProcessId` at `0x1802676e0`
- `USER32!SetTimer` at `0x180267754`
- `USER32!SetTimer` at `0x1802677f4`
- `USER32!SetTimer` at `0x180267754`
- `USER32!SetTimer` at `0x1802677f4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18026718b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18026719f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802671b6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802671c6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267376`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267386`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267560`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267576`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267702`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18026718b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18026719f`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802671b6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1802671c6`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267376`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267386`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267560`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267576`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180267702`
- `OLEAUT32!__imp_VariantInit` at `0x1802670fa`
- `OLEAUT32!__imp_VariantInit` at `0x180267231`
- `OLEAUT32!__imp_VariantInit` at `0x180267780`
- `OLEAUT32!__imp_VariantInit` at `0x1802670fa`
- `OLEAUT32!__imp_VariantInit` at `0x180267231`
- `OLEAUT32!__imp_VariantInit` at `0x180267780`
- `OLEAUT32!__imp_VariantClear` at `0x18026710a`
- `OLEAUT32!__imp_VariantClear` at `0x18026710a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180267884`
- `OLEAUT32!__imp_VariantChangeType` at `0x180267884`

## pseudocode

```c
HRESULT __fastcall CTimerCtx::ProcessAdvise(CTimerCtx *this)
{
  VARTYPE vt; // cx
  unsigned int Lo; // ebx
  HRESULT v4; // r14d
  int v5; // r13d
  __int64 v6; // r12
  __int64 v7; // r15
  __int128 v8; // xmm6
  __int128 v9; // xmm7
  struct IE_GLOBAL_THREAD_STATE *v10; // rax
  unsigned int v11; // r12d
  unsigned int v12; // r15d
  void (__fastcall *v13)(__int64, VARIANTARG *); // rax
  BOOL v14; // ecx
  _DWORD *v15; // r13
  unsigned int v16; // r8d
  unsigned int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // r15
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  __int64 v24; // rdx
  struct _RTL_CRITICAL_SECTION *v25; // rcx
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  struct _RTL_CRITICAL_SECTION *v27; // rcx
  int v28; // ebx
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v30; // r13
  __int64 v31; // rcx
  int v32; // edx
  __int64 v33; // r15
  __int64 v34; // rax
  __int64 v35; // r14
  __int64 v36; // rax
  int v37; // ecx
  __int64 v38; // rbx
  CImplAry *v39; // rcx
  int v40; // r8d
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // r9
  unsigned int v44; // eax
  int v45; // edx
  __int64 v46; // r8
  unsigned int v47; // ebx
  HWND v48; // rcx
  __int64 v50; // rcx
  __int64 v51; // r12
  __int64 v52; // r15
  int v53; // ebx
  int v54; // ecx
  GUID v55; // xmm0
  HRESULT result; // eax
  __int64 v57; // rsi
  LARGE_INTEGER v58; // r8
  unsigned __int64 v59; // rbx
  __int128 *UserInputId; // rax
  UINT_PTR v61; // rdx
  __int128 v62; // xmm0
  __int64 (__fastcall *v63)(_QWORD, UINT_PTR, __int64); // rax
  UINT_PTR v64; // rax
  DWORD WindowThreadProcessId; // ebx
  unsigned int v66; // edx
  CTimerAdvise *v67; // rcx
  void (__fastcall *v68)(__int64, VARIANTARG *); // rax
  unsigned int v69; // edx
  CTimerAdvise *v70; // rcx
  signed int LastError; // r12d
  HANDLE EventW; // rax
  int v73; // edx
  unsigned int v74; // ebx
  __int64 v75; // rdx
  unsigned int v76; // edx
  CTimerAdvise *v77; // rcx
  char v78; // [rsp+38h] [rbp-D0h]
  int v79; // [rsp+3Ch] [rbp-CCh]
  int v80; // [rsp+3Ch] [rbp-CCh]
  HRESULT v81; // [rsp+40h] [rbp-C8h]
  __int64 v82; // [rsp+48h] [rbp-C0h]
  unsigned int v83; // [rsp+50h] [rbp-B8h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG v85; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG v87; // [rsp+A0h] [rbp-68h] BYREF
  VARIANTARG v88; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v89; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG pvargDest; // [rsp+E0h] [rbp-28h] BYREF

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
    v57 = *((_QWORD *)this + 4);
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v58 = CQPCTick::s_qpcFrequency;
    if ( CQPCTick::s_qpcFrequency.QuadPart
      || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
          v58 = CQPCTick::s_qpcFrequency,
          CQPCTick::s_qpcFrequency.QuadPart) )
    {
      LODWORD(v59) = PerformanceCount.LowPart;
      if ( PerformanceCount.QuadPart && v58.QuadPart && v58.QuadPart != 1000 )
        v59 = 1000 * (PerformanceCount.QuadPart % (unsigned __int64)v58.QuadPart) / v58.QuadPart
            + 1000 * (PerformanceCount.QuadPart / (unsigned __int64)v58.QuadPart);
    }
    else
    {
      LODWORD(v59) = 0;
    }
    Lo = v59 - *(_DWORD *)(v57 + 536);
    vt = pvarg.vt;
    pvarg.lVal = Lo;
  }
  if ( vt == 19 )
  {
    v4 = 0;
    v81 = 0;
  }
  else
  {
    memset(&pvargDest, 0, sizeof(pvargDest));
    result = VariantChangeType(&pvargDest, &pvarg, 0, 0x13u);
    v81 = result;
    v4 = result;
    if ( result < 0 )
      return result;
    Lo = pvargDest.cyVal.Lo;
  }
  v5 = *((_DWORD *)this + 11) - 1;
  *((_DWORD *)this + 16) = Lo;
  v79 = v5;
  *((_DWORD *)this + 18) = 1;
  if ( v5 < 0 )
    goto LABEL_39;
  v6 = v5;
  v82 = v5;
  do
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v6);
    v8 = *(_OWORD *)(v7 + 60);
    v89 = *(_QWORD *)(v7 + 24);
    v9 = *(_OWORD *)GlobalThreadState();
    *(_OWORD *)&v85.vt = v9;
    v78 = *((_BYTE *)GlobalThreadState() + 16);
    *((_BYTE *)&v85.decVal + 16) = v78;
    *(_OWORD *)GlobalThreadState() = v8;
    v10 = GlobalThreadState();
    *((_DWORD *)&v85.decVal + 5) = 1;
    *((_BYTE *)v10 + 16) = 1;
    if ( !*(_DWORD *)(v7 + 40) )
    {
      v83 = *(_DWORD *)(v7 + 4);
      if ( v83 >= Lo )
      {
        v11 = *(_DWORD *)(v7 + 12);
        if ( v11 > Lo && !*(_DWORD *)(v7 + 44) )
        {
LABEL_35:
          v6 = v82;
LABEL_36:
          *(_OWORD *)GlobalThreadState() = v9;
          *((_BYTE *)GlobalThreadState() + 16) = v78;
          goto LABEL_37;
        }
        *(_DWORD *)(v7 + 44) = 0;
        if ( v11 > Lo )
        {
          v11 = Lo;
          *(_DWORD *)(v7 + 12) = Lo;
        }
        v12 = *(_DWORD *)(v7 + 8);
        if ( v12 )
        {
          memset(&v88, 0, sizeof(v88));
          VariantInit(&v88);
          v88.vt = 19;
          v88.lVal = Lo - (Lo - v11) % v12;
          if ( v89 )
          {
            v13 = *(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v89 + 24LL);
            v85 = v88;
            v13(v89, &v85);
          }
          v14 = 0;
          v6 = v82;
          v15 = *(_DWORD **)(*((_QWORD *)this + 6) + 8 * v82);
          v16 = v15[2];
          if ( v16 <= 0x14 )
          {
            v17 = 4 * v16;
            v18 = Lo - v15[12];
            v15[12] = Lo;
            if ( 4 * v16 < 0x14 )
              v17 = 20;
            if ( v18 > v17 )
              v18 = v17;
            ++v15[14];
            v15[13] += v18;
            v19 = v15[14];
            v20 = v15[13];
            if ( v19 >= 0x14 )
            {
              v20 >>= 1;
              v19 >>= 1;
              v15[14] = v19;
              v15[13] = v20;
            }
            v14 = v20 / v19 >= v16;
          }
          v15[11] = v14;
          v21 = v12 + v15[3];
          if ( v21 <= Lo )
          {
            v21 = v12 + Lo;
            v15[11] = 1;
          }
          if ( v83 == -1 || v21 < v83 )
          {
            v15[3] = v21;
            v22 = *((_QWORD *)this + 4);
            if ( *(_DWORD *)(v22 + 468) )
              goto LABEL_30;
            LastError = 0;
            CBaseFT::EnterCriticalSection(*((CBaseFT **)this + 4));
            if ( !*(_DWORD *)(v22 + 468) )
            {
              EventW = CreateEventW(0, 0, 0, 0);
              *(_QWORD *)(v22 + 480) = EventW;
              if ( EventW || (LastError = GetLastError()) == 0 )
              {
                LastError = CExecFT::Launch((CExecFT *)v22, v73);
                if ( !LastError )
                  *(_DWORD *)(v22 + 468) = 1;
              }
            }
            CBaseFT::LeaveCriticalSection((CBaseFT *)v22);
            if ( LastError >= 0 )
            {
LABEL_30:
              v23 = *(struct _RTL_CRITICAL_SECTION **)(v22 + 8);
              if ( v23 )
                EnterCriticalSection(v23);
              v24 = 32LL * (unsigned int)(v15[8] - 1);
              *(_DWORD *)(v24 + *(_QWORD *)(v22 + 72)) = v15[3];
              *(_DWORD *)(v24 + *(_QWORD *)(v22 + 72) + 4) = v15[11];
              v25 = *(struct _RTL_CRITICAL_SECTION **)(v22 + 8);
              if ( v25 )
                LeaveCriticalSection(v25);
            }
            v5 = v79;
            *((_DWORD *)this + 22) = 1;
            goto LABEL_35;
          }
          CTimerMan::RemoveAdvise(
            *((CTimerMan **)this + 4),
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v82) + 32LL) - 1);
          v70 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8 * v82);
          if ( v70 )
            CTimerAdvise::`scalar deleting destructor'(v70, v69);
          v5 = v79;
LABEL_109:
          CImplAry::Delete((CTimerCtx *)((char *)this + 40), 8u, v5);
          goto LABEL_36;
        }
        memset(&v87, 0, sizeof(v87));
        VariantInit(&v87);
        v87.vt = 19;
        v87.lVal = v11;
        if ( v89 )
        {
          v68 = *(void (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v89 + 24LL);
          v85 = v87;
          v68(v89, &v85);
        }
        v6 = v82;
      }
      CTimerMan::RemoveAdvise(
        *((CTimerMan **)this + 4),
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v6) + 32LL) - 1);
      v67 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8 * v6);
      if ( v67 )
        CTimerAdvise::`scalar deleting destructor'(v67, v66);
      goto LABEL_109;
    }
    ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v85);
LABEL_37:
    --v5;
    --v6;
    v79 = v5;
    v82 = v6;
  }
  while ( v5 >= 0 );
  v4 = v81;
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
        v77 = *(CTimerAdvise **)(*((_QWORD *)this + 6) + 8LL * v74);
        if ( v77 )
          CTimerAdvise::`scalar deleting destructor'(v77, v76);
        CImplAry::Delete((CTimerCtx *)((char *)this + 40), 8u, v74);
      }
    }
    *((_DWORD *)this + 19) = 0;
  }
  if ( *((_DWORD *)this + 22) )
  {
    SetEvent(*(HANDLE *)(*((_QWORD *)this + 4) + 480LL));
    *((_DWORD *)this + 22) = 0;
  }
  v26 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  if ( v26 )
    EnterCriticalSection(v26);
  v27 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
  v28 = *((_DWORD *)this + 21);
  *((_DWORD *)this + 18) = 0;
  if ( v27 )
    LeaveCriticalSection(v27);
  if ( v28 )
  {
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v30 = 0;
    v31 = (unsigned int)tls_index;
    v32 = *((_DWORD *)this + 23) + 1;
    *((_DWORD *)this + 23) = v32;
    v80 = v32;
    v33 = ThreadLocalStoragePointer[v31];
    v34 = *(_QWORD *)(v33 + 16);
    if ( v34 )
      v30 = *(_QWORD *)(v34 + 232);
    if ( !*(_QWORD *)(v30 + 96) )
      return -2147467259;
    v35 = 0;
    if ( v34 )
      v35 = *(_QWORD *)(v34 + 232);
    v36 = *(_QWORD *)(v35 + 112);
    v37 = *(_DWORD *)(v36 + 4);
    v38 = *(_QWORD *)(v36 + 8);
    while ( v37 > 0 )
    {
      if ( *(CTimerCtx **)v38 == this && *(_DWORD *)(v38 + 16) == v32 )
      {
        if ( *(_DWORD *)(v38 + 24) != 10 )
          *(_DWORD *)(v38 + 24) = 10;
        if ( *(_DWORD *)(v38 + 32)
          || ((UserInputId = (__int128 *)GetUserInputId(&v89, v35),
               v61 = *(unsigned int *)(v38 + 20),
               v62 = *UserInputId,
               v63 = (__int64 (__fastcall *)(_QWORD, UINT_PTR, __int64))qword_1815C4E28,
               *(_OWORD *)(v38 + 40) = v62,
               !v63)
            ? (v64 = SetTimer(*(HWND *)(v35 + 96), v61, 0xAu, 0))
            : (v64 = v63(*(_QWORD *)(v35 + 96), v61, 10)),
              v64) )
        {
          if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
            McTemplateU0pqpq_EventWriteTransfer(
              v37,
              (unsigned int)MSHTML_FORMSTIMER_RESET,
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
    v39 = *(CImplAry **)(v30 + 112);
    v40 = *((_DWORD *)v39 + 1) + 1;
    if ( (unsigned int)v40 > *(_DWORD *)v39 >> 2 )
    {
      if ( v40 < 0 )
        return -2147024809;
      v4 = CImplAry::EnsureSizeWorker(v39, 0x38u, v40);
      if ( v4 )
        return v4;
    }
    else
    {
      v4 = 0;
    }
    v41 = *(_QWORD *)(v33 + 16);
    v42 = v41 ? *(_QWORD *)(v41 + 232) : 0LL;
    v43 = *(_QWORD *)(v42 + 112);
LABEL_61:
    v44 = *(_DWORD *)(v42 + 104) + 1;
    *(_DWORD *)(v42 + 104) = v44;
    if ( v44 < 0x2002 )
    {
      *(_DWORD *)(v42 + 104) = 8194;
      v44 = 8194;
    }
    v45 = *(_DWORD *)(v43 + 4);
    v46 = *(_QWORD *)(v43 + 8);
    while ( v45 > 0 )
    {
      if ( v44 == *(_DWORD *)(v46 + 20) )
        goto LABEL_61;
      --v45;
      v46 += 56;
    }
    v47 = *(_DWORD *)(v42 + 104);
    v48 = *(HWND *)(v30 + 96);
    if ( qword_1815C4E28
       ? ((__int64 (__fastcall *)(HWND, _QWORD, __int64))qword_1815C4E28)(v48, v47, 10)
       : SetTimer(v48, v47, 0xAu, 0) )
    {
      v50 = *(_QWORD *)(v30 + 112);
      v51 = *(_QWORD *)(v50 + 8);
      v52 = 56LL * *(int *)(v50 + 4);
      *(_QWORD *)(v52 + v51 + 8) = CTimerCtx::TimerCallback;
      *(_DWORD *)(v52 + v51 + 20) = v47;
      v53 = v80;
      *(_QWORD *)(v52 + v51 + 32) = 0;
      *(_QWORD *)(v52 + v51) = this;
      *(_DWORD *)(v52 + v51 + 16) = v80;
      *(_QWORD *)(v52 + v51 + 24) = 10;
      if ( *((_BYTE *)GlobalThreadState() + 16) )
      {
        v55 = *(GUID *)GlobalThreadState();
      }
      else
      {
        WindowThreadProcessId = GetWindowThreadProcessId(*(HWND *)(v30 + 96), 0);
        if ( WindowThreadProcessId == GetCurrentThreadId() )
          v55 = *(GUID *)GlobalThreadState();
        else
          v55 = GUID_NULL;
        v53 = v80;
      }
      *(GUID *)(v52 + v51 + 40) = v55;
      ++*(_DWORD *)(*(_QWORD *)(v30 + 112) + 4LL);
      if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
        McTemplateU0pqpq_EventWriteTransfer(
          v54,
          (unsigned int)MSHTML_FORMSTIMER_SET,
          (_DWORD)this,
          v53,
          (char)CTimerCtx::TimerCallback,
          10);
    }
    else
    {
      return -2147467259;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1802670a8  mov     rax, rsp
0x1802670ab  mov     [rax+8], rcx
0x1802670af  push    rbp
0x1802670b0  push    rbx
0x1802670b1  push    rsi
0x1802670b2  push    rdi
0x1802670b3  push    r12
0x1802670b5  push    r13
0x1802670b7  push    r14
0x1802670b9  push    r15
0x1802670bb  lea     rbp, [rax-58h]
0x1802670bf  sub     rsp, 118h
0x1802670c6  mov     rdi, [rbp+50h+arg_0]
0x1802670ca  xor     r12d, r12d
0x1802670cd  movaps  xmmword ptr [rax-58h], xmm6
0x1802670d1  movaps  xmmword ptr [rax-68h], xmm7
0x1802670d5  cmp     [rdi+44h], r12d
0x1802670d9  jg      loc_180267862
0x1802670df  cmp     [rdi+48h], r12d
0x1802670e3  jnz     loc_18026785B
0x1802670e9  xorps   xmm0, xmm0
0x1802670ec  lea     rcx, [rbp+50h+pvarg]; pvarg
0x1802670f0  xor     eax, eax
0x1802670f2  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x1802670f6  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x1802670fa  call    cs:__imp_VariantInit
0x180267101  nop     dword ptr [rax+rax+00h]
0x180267106  lea     rcx, [rbp+50h+pvarg]; pvarg
0x18026710a  call    cs:__imp_VariantClear
0x180267111  nop     dword ptr [rax+rax+00h]
0x180267116  lea     r14d, [r12+13h]
0x18026711b  movzx   ecx, r14w
0x18026711f  mov     word ptr [rbp+50h+pvarg], cx
0x180267123  cmp     [rdi+44h], r12d
0x180267127  jg      short loc_180267133
0x180267129  cmp     [rdi+48h], r12d
0x18026712d  jz      loc_1802675C6
0x180267133  mov     eax, [rdi+40h]
0x180267136  mov     ebx, eax
0x180267138  mov     dword ptr [rbp+50h+pvarg+8], eax
0x18026713b  cmp     cx, r14w
0x18026713f  jnz     loc_180267869
0x180267145  mov     r14d, r12d
0x180267148  mov     dword ptr [rsp+150h+var_118], r12d
0x18026714d  mov     r13d, [rdi+2Ch]
0x180267151  mov     esi, 1
0x180267156  sub     r13d, esi
0x180267159  mov     [rdi+40h], ebx
0x18026715c  mov     [rsp+150h+var_11C], r13d
0x180267161  mov     [rdi+48h], esi
0x180267164  js      loc_1802673BA
0x18026716a  movsxd  r12, r13d
0x18026716d  lea     r14d, [rsi+12h]
0x180267171  mov     [rsp+150h+var_110], r12
0x180267176  mov     rax, [rdi+30h]
0x18026717a  mov     r15, [rax+r12*8]
0x18026717e  mov     rax, [r15+18h]
0x180267182  movups  xmm6, xmmword ptr [r15+3Ch]
0x180267187  mov     [rbp+50h+var_88], rax
0x18026718b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180267192  nop     dword ptr [rax+rax+00h]
0x180267197  movups  xmm7, xmmword ptr [rax]
0x18026719a  movups  xmmword ptr [rsp+150h+var_F8+8], xmm7
0x18026719f  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802671a6  nop     dword ptr [rax+rax+00h]
0x1802671ab  mov     al, [rax+10h]
0x1802671ae  mov     byte ptr [rsp+150h+var_120], al
0x1802671b2  mov     byte ptr [rsp+150h+var_E0], al
0x1802671b6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802671bd  nop     dword ptr [rax+rax+00h]
0x1802671c2  movdqu  xmmword ptr [rax], xmm6
0x1802671c6  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1802671cd  nop     dword ptr [rax+rax+00h]
0x1802671d2  xor     ecx, ecx
0x1802671d4  mov     dword ptr [rsp+150h+var_E0+4], esi
0x1802671d8  mov     [rax+10h], sil
0x1802671dc  cmp     [r15+28h], ecx
0x1802671e0  jnz     loc_180267765
0x1802671e6  mov     eax, [r15+4]
0x1802671ea  mov     dword ptr [rsp+150h+var_108], eax
0x1802671ee  cmp     eax, ebx
0x1802671f0  jb      loc_1802677A7
0x1802671f6  mov     r12d, [r15+0Ch]
0x1802671fa  cmp     r12d, ebx
0x1802671fd  ja      loc_180267745
0x180267203  mov     [r15+2Ch], ecx
0x180267207  cmp     r12d, ebx
0x18026720a  jbe     short loc_180267213
0x18026720c  mov     r12d, ebx
0x18026720f  mov     [r15+0Ch], ebx
0x180267213  mov     r15d, [r15+8]
0x180267217  xor     eax, eax
0x180267219  xorps   xmm0, xmm0
0x18026721c  test    r15d, r15d
0x18026721f  jz      loc_180267774
0x180267225  lea     rcx, [rbp+50h+var_A0]; pvarg
0x180267229  mov     qword ptr [rbp+50h+var_A0+10h], rax
0x18026722d  movups  xmmword ptr [rbp+50h+var_A0], xmm0
0x180267231  call    cs:__imp_VariantInit
0x180267238  nop     dword ptr [rax+rax+00h]
0x18026723d  mov     rcx, [rbp+50h+var_88]
0x180267241  xor     edx, edx
0x180267243  mov     eax, ebx
0x180267245  mov     word ptr [rbp+50h+var_A0], r14w
0x18026724a  sub     eax, r12d
0x18026724d  div     r15d
0x180267250  mov     eax, ebx
0x180267252  sub     eax, edx
0x180267254  mov     dword ptr [rbp+50h+var_A0+8], eax
0x180267257  test    rcx, rcx
0x18026725a  jz      short loc_180267281
0x18026725c  mov     rax, [rcx]
0x18026725f  lea     rdx, [rsp+150h+var_F8+8]
0x180267264  movups  xmm0, xmmword ptr [rbp+50h+var_A0]
0x180267268  movsd   xmm1, qword ptr [rbp+50h+var_A0+10h]
0x18026726d  mov     rax, [rax+18h]
0x180267271  movaps  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x180267276  movsd   [rsp+150h+var_E0], xmm1
0x18026727c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180267281  mov     rax, [rdi+30h]
0x180267285  xor     ecx, ecx
0x180267287  mov     r12, [rsp+150h+var_110]
0x18026728c  lea     edx, [rcx+14h]
0x18026728f  mov     r13, [rax+r12*8]
0x180267293  mov     r8d, [r13+8]
0x180267297  cmp     r8d, edx
0x18026729a  ja      short loc_1802672E4
0x18026729c  lea     eax, ds:0[r8*4]
0x1802672a4  mov     ecx, ebx
0x1802672a6  sub     ecx, [r13+30h]
0x1802672aa  cmp     eax, edx
0x1802672ac  mov     [r13+30h], ebx
0x1802672b0  cmovb   eax, edx
0x1802672b3  cmp     ecx, eax
0x1802672b5  cmova   ecx, eax
0x1802672b8  add     [r13+38h], esi
0x1802672bc  add     [r13+34h], ecx
0x1802672c0  mov     ecx, [r13+38h]
0x1802672c4  mov     eax, [r13+34h]
0x1802672c8  cmp     ecx, edx
0x1802672ca  jb      short loc_1802672D8
0x1802672cc  shr     eax, 1
0x1802672ce  shr     ecx, 1
0x1802672d0  mov     [r13+38h], ecx
0x1802672d4  mov     [r13+34h], eax
0x1802672d8  xor     edx, edx
0x1802672da  div     ecx
0x1802672dc  xor     ecx, ecx
0x1802672de  cmp     eax, r8d
0x1802672e1  setnb   cl
0x1802672e4  mov     [r13+2Ch], ecx
0x1802672e8  mov     ecx, [r13+0Ch]
0x1802672ec  add     ecx, r15d
0x1802672ef  cmp     ecx, ebx
0x1802672f1  ja      short loc_1802672FB
0x1802672f3  lea     ecx, [r15+rbx]
0x1802672f7  mov     [r13+2Ch], esi
0x1802672fb  mov     eax, dword ptr [rsp+150h+var_108]
0x1802672ff  cmp     eax, 0FFFFFFFFh
0x180267302  jnz     loc_1802678D1
0x180267308  mov     [r13+0Ch], ecx
0x18026730c  mov     r15, [rdi+20h]
0x180267310  cmp     dword ptr [r15+1D4h], 0
0x180267318  jz      loc_18026790B
0x18026731e  mov     rcx, [r15+8]; lpCriticalSection
0x180267322  test    rcx, rcx
0x180267325  jz      short loc_180267333
0x180267327  call    cs:__imp_EnterCriticalSection
0x18026732e  nop     dword ptr [rax+rax+00h]
0x180267333  mov     edx, [r13+20h]
0x180267337  mov     rcx, [r15+48h]
0x18026733b  sub     edx, esi
0x18026733d  mov     eax, [r13+0Ch]
0x180267341  shl     rdx, 5
0x180267345  mov     [rdx+rcx], eax
0x180267348  mov     rcx, [r15+48h]
0x18026734c  mov     eax, [r13+2Ch]
0x180267350  mov     [rdx+rcx+4], eax
0x180267354  mov     rcx, [r15+8]; lpCriticalSection
0x180267358  test    rcx, rcx
0x18026735b  jz      short loc_180267369
0x18026735d  call    cs:__imp_LeaveCriticalSection
0x180267364  nop     dword ptr [rax+rax+00h]
0x180267369  mov     r13d, [rsp+150h+var_11C]
0x18026736e  mov     [rdi+58h], esi
0x180267371  mov     r12, [rsp+150h+var_110]
0x180267376  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18026737d  nop     dword ptr [rax+rax+00h]
0x180267382  movdqu  xmmword ptr [rax], xmm7
0x180267386  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18026738d  nop     dword ptr [rax+rax+00h]
0x180267392  mov     cl, byte ptr [rsp+150h+var_120]
0x180267396  mov     [rax+10h], cl
0x180267399  sub     r13d, esi
0x18026739c  sub     r12, rsi
0x18026739f  mov     [rsp+150h+var_11C], r13d
0x1802673a4  mov     [rsp+150h+var_110], r12
0x1802673a9  test    r13d, r13d
0x1802673ac  jns     loc_180267176
0x1802673b2  mov     r14d, dword ptr [rsp+150h+var_118]
0x1802673b7  xor     r12d, r12d
0x1802673ba  cmp     [rdi+4Ch], r12d
0x1802673be  jnz     loc_180267980
0x1802673c4  cmp     [rdi+58h], r12d
0x1802673c8  jz      short loc_1802673E5
0x1802673ca  mov     rcx, [rdi+20h]
0x1802673ce  mov     rcx, [rcx+1E0h]; hEvent
0x1802673d5  call    cs:__imp_SetEvent
0x1802673dc  nop     dword ptr [rax+rax+00h]
0x1802673e1  mov     [rdi+58h], r12d
0x1802673e5  mov     rcx, [rdi+8]; lpCriticalSection
0x1802673e9  test    rcx, rcx
0x1802673ec  jz      short loc_1802673FA
0x1802673ee  call    cs:__imp_EnterCriticalSection
0x1802673f5  nop     dword ptr [rax+rax+00h]
0x1802673fa  mov     rcx, [rdi+8]; lpCriticalSection
0x1802673fe  mov     ebx, [rdi+54h]
0x180267401  mov     [rdi+48h], r12d
0x180267405  test    rcx, rcx
0x180267408  jz      short loc_180267416
0x18026740a  call    cs:__imp_LeaveCriticalSection
0x180267411  nop     dword ptr [rax+rax+00h]
0x180267416  test    ebx, ebx
0x180267418  jz      loc_1802675A0
0x18026741e  mov     rax, gs:58h
0x180267427  mov     r13, r12
0x18026742a  mov     edx, [rdi+5Ch]
0x18026742d  mov     ecx, cs:_tls_index
0x180267433  add     edx, esi
0x180267435  mov     r8d, 10h
0x18026743b  mov     [rdi+5Ch], edx
0x18026743e  mov     [rsp+150h+var_11C], edx
0x180267442  mov     r15, [rax+rcx*8]
0x180267446  mov     rax, [r15+r8]
0x18026744a  test    rax, rax
0x18026744d  jz      short loc_180267456
0x18026744f  mov     r13, [rax+0E8h]
0x180267456  cmp     [r13+60h], r12
0x18026745a  jz      loc_1802676BA
0x180267460  mov     r14, r12
0x180267463  test    rax, rax
0x180267466  jz      short loc_18026746F
0x180267468  mov     r14, [rax+0E8h]
0x18026746f  mov     rax, [r14+70h]
0x180267473  mov     ecx, [rax+4]
0x180267476  mov     rbx, [rax+8]
0x18026747a  test    ecx, ecx
0x18026747c  jle     short loc_18026748F
0x18026747e  cmp     [rbx], rdi
0x180267481  jz      loc_180267642
0x180267487  sub     ecx, esi
0x180267489  add     rbx, 38h ; '8'
0x18026748d  jmp     short loc_18026747A
0x18026748f  mov     rcx, [r13+70h]; this
0x180267493  mov     r8d, [rcx+4]
0x180267497  mov     eax, [rcx]
0x180267499  inc     r8d; int
0x18026749c  shr     eax, 2
0x18026749f  cmp     r8d, eax
0x1802674a2  ja      loc_180267722
0x1802674a8  mov     r14d, r12d
0x1802674ab  mov     ecx, 10h
0x1802674b0  mov     rcx, [r15+rcx]
0x1802674b4  test    rcx, rcx
0x1802674b7  jz      loc_18026771A
0x1802674bd  mov     rcx, [rcx+0E8h]
0x1802674c4  mov     r9, [rcx+70h]
0x1802674c8  mov     r10d, 2002h
0x1802674ce  mov     eax, [rcx+68h]
0x1802674d1  inc     eax
0x1802674d3  mov     [rcx+68h], eax
0x1802674d6  cmp     eax, r10d
0x1802674d9  jb      loc_1802679F9
0x1802674df  mov     edx, [r9+4]
0x1802674e3  mov     r8, [r9+8]
0x1802674e7  test    edx, edx
0x1802674e9  jg      loc_1802676C5
0x1802674ef  mov     ebx, [rcx+68h]
0x1802674f2  xor     r9d, r9d; lpTimerFunc
0x1802674f5  mov     rax, cs:qword_1815C4E28
0x1802674fc  mov     edx, ebx; nIDEvent
0x1802674fe  mov     rcx, [r13+60h]; hWnd
0x180267502  lea     r8d, [r9+0Ah]; uElapse
0x180267506  test    rax, rax
0x180267509  jz      loc_180267754
0x18026750f  mov     [rsp+150h+var_130], r12d
0x180267514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180267519  test    rax, rax
0x18026751c  jz      loc_1802676BA
0x180267522  mov     rcx, [r13+70h]
0x180267526  movsxd  rax, dword ptr [rcx+4]
0x18026752a  mov     r12, [rcx+8]
0x18026752e  imul    r15, rax, 38h ; '8'
0x180267532  lea     rax, ?TimerCallback@CTimerCtx@@QEAAJI@Z; CTimerCtx::TimerCallback(uint)
0x180267539  mov     [r15+r12+8], rax
0x18026753e  xor     eax, eax
0x180267540  mov     [r15+r12+14h], ebx
0x180267545  mov     ebx, [rsp+150h+var_11C]
0x180267549  mov     [r15+r12+20h], rax
0x18026754e  mov     [r15+r12], rdi
  ... truncated ...
```
