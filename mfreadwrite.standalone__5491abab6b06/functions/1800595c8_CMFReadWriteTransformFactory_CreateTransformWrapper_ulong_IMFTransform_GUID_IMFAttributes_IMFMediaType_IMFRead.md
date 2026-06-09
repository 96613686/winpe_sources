# CMFReadWriteTransformFactory::CreateTransformWrapper(ulong,IMFTransform *,_GUID,IMFAttributes *,IMFMediaType *,IMFReadWriteTransform * *)

- ea: `0x1800595c8`
- end: `0x180059c9a`
- name: `?CreateTransformWrapper@CMFReadWriteTransformFactory@@SAJKPEAUIMFTransform@@U_GUID@@PEAUIMFAttributes@@PEAUIMFMediaType@@PEAPEAUIMFReadWriteTransform@@@Z`
- size: `1746`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, struct IMFTransform *@<rdx>, struct _GUID *__struct_ptr@<r8>, struct IMFAttributes *@<r9>, struct IMFMediaType *, struct IMFReadWriteTransform **)`
- caller_count: `7`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005210`
- `0x180070a10`
- `0x180071af4`
- `0x18009fe00`
- `0x1800b62c4`
- `0x1800d1270`
- `0x1800d2dec`

## callees

- `0x18000517c`
- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x180029900`
- `0x1800595c8`
- `0x180059ca0`
- `0x180059ed4`
- `0x1800906fc`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800598a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800599cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059ab0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059bf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800598a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800599cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059ab0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059bf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005984c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005997e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005984c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005997e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ba9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059841`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059973`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059a56`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059b9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059841`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059973`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059a56`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180059b9e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800597a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059a77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059b15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059bbf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800597a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059862`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059908`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059a77`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059b15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180059bbf`
- `MFCORE!MFCreateTransformWrapper` at `0x180059632`
- `MFCORE!MFCreateTransformWrapper` at `0x180059632`

## string_xrefs

- `0x1800595e5`: `CMFReadWriteTransformFactory::CreateTransformWrapper`
- `0x1800598b7`: `CMFReadWriteTransformFactory::CreateTransformWrapper`
- `0x1800599e3`: `CMFReadWriteTransformFactory::CreateTransformWrapper`
- `0x180059ac6`: `CMFReadWriteTransformFactory::CreateTransformWrapper`
- `0x180059c0e`: `CMFReadWriteTransformFactory::CreateTransformWrapper`

## pseudocode

```c
__int64 __fastcall CMFReadWriteTransformFactory::CreateTransformWrapper(
        unsigned int a1,
        struct IMFTransform *a2,
        struct _GUID *a3,
        struct IMFAttributes *a4,
        struct IMFMediaType *a5,
        struct IMFReadWriteTransform **a6)
{
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  CallStackTracing *v16; // rdi
  __int64 v17; // rdx
  struct IMFAttributesVtbl *lpVtbl; // rax
  bool v19; // sf
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  CallStackTracing *v24; // rsi
  CallStackTracing *v25; // rax
  CallStackContext *v26; // rsi
  DWORD LastError; // r14d
  CallStackContext *Value; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  CallStackTracing *v31; // rdi
  CallStackTracing *v32; // rax
  __int64 v33; // rax
  CallStackTracing *v34; // rsi
  CallStackTracing *v35; // rax
  CallStackContext *v36; // r14
  DWORD v37; // r12d
  CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  __int64 v42; // rax
  CallStackContext *v43; // r14
  DWORD v44; // r12d
  CallStackContext *v45; // rax
  __int64 v46; // rdx
  CallStackTracing *v47; // rcx
  CallStackTracing *v48; // rax
  __int64 v49; // rax
  CallStackTracing *v50; // rsi
  CallStackTracing *v51; // rax
  CallStackContext *v52; // r14
  DWORD v53; // r12d
  CallStackContext *v54; // rax
  __int64 v55; // rdx
  CallStackTracing *v56; // rcx
  CallStackTracing *v57; // rax
  __int64 v58; // rax
  int v59; // eax
  char v60[8]; // [rsp+30h] [rbp-38h] BYREF
  int v61[2]; // [rsp+38h] [rbp-30h] BYREF
  struct IUnknown *v62[2]; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID v63; // [rsp+50h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v60,
    "CMFReadWriteTransformFactory::CreateTransformWrapper",
    767);
  v62[0] = 0;
  v61[0] = 0;
  v10 = CMFReadWriteTransformFactory::UnlockAsyncMFT(a2, v61);
  if ( v10 < 0 )
  {
    v16 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v16 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v16 + 8) )
    {
      v26 = (CallStackTracing *)((char *)v16 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v16 + 3));
      if ( Value )
      {
        v26 = Value;
      }
      else if ( !GetLastError() )
      {
        v31 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v30, v29);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
        if ( v33 )
          v26 = (CallStackContext *)v33;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v26 + 499) != v10 )
        CallStackContext::TraceFailure(v26, "CMFReadWriteTransformFactory::CreateTransformWrapper", 776, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_6;
    v17 = 77;
LABEL_87:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, 0, v10);
    goto LABEL_6;
  }
  if ( v61[0] )
  {
    if ( (struct IMFTransform *)v62[0] != a2 )
      ATL::AtlComPtrAssign(v62, (struct IUnknown *)a2);
    goto LABEL_4;
  }
  v10 = MFCreateTransformWrapper(0, a2, v62);
  if ( v10 < 0 )
  {
    v34 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v36 = (CallStackTracing *)((char *)v34 + 208);
      v37 = GetLastError();
      v38 = (CallStackContext *)TlsGetValue(*((_DWORD *)v34 + 3));
      if ( v38 )
      {
        v36 = v38;
      }
      else if ( !GetLastError() )
      {
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
        if ( v42 )
          v36 = (CallStackContext *)v42;
      }
      SetLastError(v37);
      if ( *((_DWORD *)v36 + 499) != v10 )
        CallStackContext::TraceFailure(v36, "CMFReadWriteTransformFactory::CreateTransformWrapper", 784, v10);
    }
    if ( !g_wppLevels )
      goto LABEL_6;
    v17 = 78;
    goto LABEL_87;
  }
LABEL_4:
  if ( a4 )
  {
    lpVtbl = a4->lpVtbl;
    v61[0] = 0;
    v19 = ((int (__fastcall *)(struct IMFAttributes *, __int64 *, int *))lpVtbl->GetUINT32)(a4, MF_LOW_LATENCY, v61) < 0;
    v21 = 0;
    if ( !v19 )
      v21 = v61[0];
    if ( v21 )
    {
      v59 = MFLowLatencyHelpers::SetLowLatencyOnObject(1, a2, v20, a5);
      if ( v59 < 0 && g_wppLevels >= 4u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, 0, v59);
    }
    *(_QWORD *)v61 = 0;
    *(_QWORD *)&v63.Data1 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, int *))v62[0]->lpVtbl[2].Release)(v62[0], v61) >= 0
      && ((int (__fastcall *)(struct IMFAttributes *, __int64 *, struct _GUID *))a4->lpVtbl->GetUINT64)(
           a4,
           MF_SOURCE_READER_PLUGIN_PROCESSING_LATENCY,
           &v63) >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**(_QWORD **)v61 + 176LL))(
              *(_QWORD *)v61,
              MF_SA_PROCESSING_LATENCY,
              *(_QWORD *)&v63.Data1);
      if ( v10 < 0 )
      {
        v24 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v43 = (CallStackTracing *)((char *)v24 + 208);
          v44 = GetLastError();
          v45 = (CallStackContext *)TlsGetValue(*((_DWORD *)v24 + 3));
          if ( v45 )
          {
            v43 = v45;
          }
          else if ( !GetLastError() )
          {
            v47 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v46);
              CallStackTracing::s_wpInstance = v48;
              if ( v48
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
              {
                v47 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v47 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v49 = (**(__int64 (__fastcall ***)(CallStackTracing *))v47)(v47);
            if ( v49 )
              v43 = (CallStackContext *)v49;
          }
          SetLastError(v44);
          if ( *((_DWORD *)v43 + 499) != v10 )
            CallStackContext::TraceFailure(v43, "CMFReadWriteTransformFactory::CreateTransformWrapper", 813, v10);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, 0, v10);
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v61);
        goto LABEL_6;
      }
    }
    if ( *(_QWORD *)v61 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v61 + 16LL))(*(_QWORD *)v61);
  }
  v63 = *a3;
  v10 = CMFReadWriteTransform::CreateInstance(a1, (struct IMFTransform *)v62[0], &v63, a4, a6);
  if ( v10 < 0 )
  {
    v50 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13);
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = (CallStackTracing *)((char *)v50 + 208);
      v53 = GetLastError();
      v54 = (CallStackContext *)TlsGetValue(*((_DWORD *)v50 + 3));
      if ( v54 )
      {
        v52 = v54;
      }
      else if ( !GetLastError() )
      {
        v56 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
          CallStackTracing::s_wpInstance = v57;
          if ( v57 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
          {
            v56 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v56 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v58 = (**(__int64 (__fastcall ***)(CallStackTracing *))v56)(v56);
        if ( v58 )
          v52 = (CallStackContext *)v58;
      }
      SetLastError(v53);
      if ( *((_DWORD *)v52 + 499) != v10 )
        CallStackContext::TraceFailure(v52, "CMFReadWriteTransformFactory::CreateTransformWrapper", 820, v10);
    }
    if ( g_wppLevels )
    {
      v17 = 81;
      goto LABEL_87;
    }
  }
LABEL_6:
  if ( v62[0] )
    ((void (__fastcall *)(struct IUnknown *))v62[0]->lpVtbl->Release)(v62[0]);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v60);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800595c8  push    rbp
0x1800595ca  push    rbx
0x1800595cb  push    rsi
0x1800595cc  push    rdi
0x1800595cd  push    r12
0x1800595cf  push    r13
0x1800595d1  push    r14
0x1800595d3  push    r15
0x1800595d5  mov     rbp, rsp
0x1800595d8  sub     rsp, 68h
0x1800595dc  mov     r14, r8
0x1800595df  mov     rdi, rdx
0x1800595e2  mov     r15d, ecx
0x1800595e5  lea     rdx, aCmfreadwritetr_73; "CMFReadWriteTransformFactory::CreateTra"...
0x1800595ec  mov     r8d, 2FFh; int
0x1800595f2  lea     rcx, [rbp+var_38]; this
0x1800595f6  mov     rsi, r9
0x1800595f9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800595fe  xor     r13d, r13d
0x180059601  lea     rdx, [rbp+var_30]; int *
0x180059605  mov     rcx, rdi; struct IMFTransform *
0x180059608  mov     [rbp+var_28], r13
0x18005960c  mov     [rbp+var_30], r13d
0x180059610  call    ?UnlockAsyncMFT@CMFReadWriteTransformFactory@@CAJPEAUIMFTransform@@PEAH@Z; CMFReadWriteTransformFactory::UnlockAsyncMFT(IMFTransform *,int *)
0x180059615  mov     ebx, eax
0x180059617  test    eax, eax
0x180059619  js      loc_1800596AB
0x18005961f  cmp     [rbp+var_30], r13d
0x180059623  jnz     loc_180059A19
0x180059629  lea     r8, [rbp+var_28]
0x18005962d  mov     rdx, rdi
0x180059630  xor     ecx, ecx
0x180059632  call    cs:__imp_MFCreateTransformWrapper
0x180059638  mov     ebx, eax
0x18005963a  test    eax, eax
0x18005963c  js      loc_1800598EF
0x180059642  test    rsi, rsi
0x180059645  jnz     loc_1800596D8
0x18005964b  movaps  xmm0, xmmword ptr [r14]
0x18005964f  lea     r8, [rbp+var_18]; struct _GUID
0x180059653  mov     rax, [rbp+arg_28]
0x180059657  mov     r9, rsi; struct IMFAttributes *
0x18005965a  mov     rdx, [rbp+var_28]; struct IMFTransform *
0x18005965e  mov     ecx, r15d; unsigned int
0x180059661  movdqa  xmmword ptr [rbp+var_18.Data1], xmm0
0x180059666  mov     [rsp+68h+var_48], rax; struct IMFReadWriteTransform **
0x18005966b  call    ?CreateInstance@CMFReadWriteTransform@@SAJKPEAUIMFTransform@@U_GUID@@PEAUIMFAttributes@@PEAPEAUIMFReadWriteTransform@@@Z; CMFReadWriteTransform::CreateInstance(ulong,IMFTransform *,_GUID,IMFAttributes *,IMFReadWriteTransform * *)
0x180059670  mov     ebx, eax
0x180059672  test    eax, eax
0x180059674  js      loc_180059AFC
0x18005967a  mov     rcx, [rbp+var_28]
0x18005967e  test    rcx, rcx
0x180059681  jz      short loc_18005968F
0x180059683  mov     rdx, [rcx]
0x180059686  mov     rax, [rdx+10h]
0x18005968a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005968f  lea     rcx, [rbp+var_38]; this
0x180059693  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180059698  mov     eax, ebx
0x18005969a  add     rsp, 68h
0x18005969e  pop     r15
0x1800596a0  pop     r14
0x1800596a2  pop     r13
0x1800596a4  pop     r12
0x1800596a6  pop     rdi
0x1800596a7  pop     rsi
0x1800596a8  pop     rbx
0x1800596a9  pop     rbp
0x1800596aa  retn
0x1800596ab  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800596b2  test    rdi, rdi
0x1800596b5  jz      loc_18005981D
0x1800596bb  cmp     [rdi+8], r13b
0x1800596bf  jnz     loc_18005982E
0x1800596c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800596cc  jb      short loc_18005967A
0x1800596ce  mov     edx, 4Dh ; 'M'
0x1800596d3  jmp     loc_180059B5C
0x1800596d8  mov     rax, [rsi]
0x1800596db  lea     r8, [rbp+var_30]
0x1800596df  lea     rdx, MF_LOW_LATENCY
0x1800596e6  mov     [rbp+var_30], r13d
0x1800596ea  mov     rcx, rsi
0x1800596ed  mov     rax, [rax+38h]
0x1800596f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596f6  test    eax, eax
0x1800596f8  mov     eax, r13d
0x1800596fb  jns     loc_180059C44
0x180059701  test    eax, eax
0x180059703  jnz     loc_180059C4C
0x180059709  mov     rcx, [rbp+var_28]
0x18005970d  lea     rdx, [rbp+var_30]
0x180059711  mov     qword ptr [rbp+var_30], r13
0x180059715  mov     qword ptr [rbp+var_18.Data1], r13
0x180059719  mov     rax, [rcx]
0x18005971c  mov     rax, [rax+40h]
0x180059720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059725  test    eax, eax
0x180059727  jns     short loc_180059747
0x180059729  mov     rcx, qword ptr [rbp+var_30]
0x18005972d  test    rcx, rcx
0x180059730  jz      loc_18005964B
0x180059736  mov     rax, [rcx]
0x180059739  mov     rax, [rax+10h]
0x18005973d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059742  jmp     loc_18005964B
0x180059747  mov     rax, [rsi]
0x18005974a  lea     r8, [rbp+var_18]
0x18005974e  lea     rdx, MF_SOURCE_READER_PLUGIN_PROCESSING_LATENCY
0x180059755  mov     rcx, rsi
0x180059758  mov     rax, [rax+40h]
0x18005975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059761  test    eax, eax
0x180059763  js      short loc_180059729
0x180059765  mov     rcx, qword ptr [rbp+var_30]
0x180059769  lea     rdx, MF_SA_PROCESSING_LATENCY
0x180059770  mov     r8, qword ptr [rbp+var_18.Data1]
0x180059774  mov     rax, [rcx]
0x180059777  mov     rax, [rax+0B0h]
0x18005977e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059783  mov     ebx, eax
0x180059785  test    eax, eax
0x180059787  jns     short loc_180059729
0x180059789  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059790  lea     rdi, qword_18010C230
0x180059797  mov     r15d, 7F0h
0x18005979d  test    rsi, rsi
0x1800597a0  jnz     short loc_1800597D9
0x1800597a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800597a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800597af  mov     rcx, rax
0x1800597b2  test    rax, rax
0x1800597b5  jz      loc_180059A34
0x1800597bb  mov     rax, [rax]
0x1800597be  mov     edx, r15d
0x1800597c1  mov     rax, [rax+8]
0x1800597c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597ca  test    eax, eax
0x1800597cc  jz      loc_180059A34
0x1800597d2  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800597d9  cmp     [rsi+8], r13b
0x1800597dd  jnz     loc_180059A43
0x1800597e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800597ea  jb      short loc_18005980F
0x1800597ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800597f3  lea     r8, WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids
0x1800597fa  mov     edx, 50h ; 'P'
0x1800597ff  mov     dword ptr [rsp+68h+var_48], ebx
0x180059803  xor     r9d, r9d
0x180059806  mov     rcx, [rcx+10h]
0x18005980a  call    WPP_SF_qD
0x18005980f  lea     rcx, [rbp+var_30]
0x180059813  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x180059818  jmp     loc_18005967A
0x18005981d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180059822  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059829  jmp     loc_1800596BB
0x18005982e  lea     rsi, [rdi+0D0h]
0x180059835  call    cs:__imp_GetLastError
0x18005983b  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18005983e  mov     r14d, eax
0x180059841  call    cs:__imp_TlsGetValue
0x180059847  test    rax, rax
0x18005984a  jnz     short loc_18005989C
0x18005984c  call    cs:__imp_GetLastError
0x180059852  test    eax, eax
0x180059854  jnz     short loc_18005989F
0x180059856  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005985d  test    rdi, rdi
0x180059860  jnz     short loc_180059885
0x180059862  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059868  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005986f  mov     rcx, rax
0x180059872  test    rax, rax
0x180059875  jnz     short loc_1800598D1
0x180059877  lea     rdi, qword_18010C230
0x18005987e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180059885  mov     rax, [rdi]
0x180059888  mov     rcx, rdi
0x18005988b  mov     rax, [rax]
0x18005988e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059893  test    rax, rax
0x180059896  cmovnz  rsi, rax
0x18005989a  jmp     short loc_18005989F
0x18005989c  mov     rsi, rax
0x18005989f  mov     ecx, r14d; dwErrCode
0x1800598a2  call    cs:__imp_SetLastError
0x1800598a8  cmp     [rsi+7CCh], ebx
0x1800598ae  jz      loc_1800596C5
0x1800598b4  mov     r9d, ebx; int
0x1800598b7  lea     rdx, aCmfreadwritetr_73; "CMFReadWriteTransformFactory::CreateTra"...
0x1800598be  mov     r8d, 308h; int
0x1800598c4  mov     rcx, rsi; this
0x1800598c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800598cc  jmp     loc_1800596C5
0x1800598d1  mov     rax, [rax]
0x1800598d4  mov     edx, 7F0h
0x1800598d9  mov     rax, [rax+8]
0x1800598dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800598e2  test    eax, eax
0x1800598e4  jz      short loc_180059877
0x1800598e6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800598ed  jmp     short loc_180059885
0x1800598ef  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800598f6  lea     rdi, qword_18010C230
0x1800598fd  mov     r15d, 7F0h
0x180059903  test    rsi, rsi
0x180059906  jnz     short loc_180059937
0x180059908  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005990e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059915  mov     rcx, rax
0x180059918  test    rax, rax
0x18005991b  jz      short loc_180059954
0x18005991d  mov     rax, [rax]
0x180059920  mov     edx, r15d
0x180059923  mov     rax, [rax+8]
0x180059927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005992c  test    eax, eax
0x18005992e  jz      short loc_180059954
0x180059930  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059937  cmp     [rsi+8], r13b
0x18005993b  jnz     short loc_180059960
0x18005993d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059944  jb      loc_18005967A
0x18005994a  mov     edx, 4Eh ; 'N'
0x18005994f  jmp     loc_180059B5C
0x180059954  mov     rsi, rdi
0x180059957  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18005995e  jmp     short loc_180059937
0x180059960  lea     r14, [rsi+0D0h]
0x180059967  call    cs:__imp_GetLastError
0x18005996d  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180059970  mov     r12d, eax
0x180059973  call    cs:__imp_TlsGetValue
0x180059979  test    rax, rax
0x18005997c  jnz     short loc_1800599C7
0x18005997e  call    cs:__imp_GetLastError
0x180059984  test    eax, eax
0x180059986  jnz     short loc_1800599CA
0x180059988  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005998f  test    rcx, rcx
0x180059992  jnz     short loc_1800599B3
0x180059994  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005999a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800599a1  mov     rcx, rax
0x1800599a4  test    rax, rax
0x1800599a7  jnz     short loc_1800599FD
0x1800599a9  mov     rcx, rdi
0x1800599ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800599b3  mov     rax, [rcx]
0x1800599b6  mov     rax, [rax]
0x1800599b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599be  test    rax, rax
0x1800599c1  cmovnz  r14, rax
0x1800599c5  jmp     short loc_1800599CA
0x1800599c7  mov     r14, rax
0x1800599ca  mov     ecx, r12d; dwErrCode
0x1800599cd  call    cs:__imp_SetLastError
0x1800599d3  cmp     [r14+7CCh], ebx
0x1800599da  jz      loc_18005993D
0x1800599e0  mov     r9d, ebx; int
0x1800599e3  lea     rdx, aCmfreadwritetr_73; "CMFReadWriteTransformFactory::CreateTra"...
0x1800599ea  mov     r8d, 310h; int
0x1800599f0  mov     rcx, r14; this
0x1800599f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800599f8  jmp     loc_18005993D
0x1800599fd  mov     rax, [rax]
0x180059a00  mov     edx, r15d
0x180059a03  mov     rax, [rax+8]
0x180059a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a0c  test    eax, eax
0x180059a0e  jz      short loc_1800599A9
0x180059a10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059a17  jmp     short loc_1800599B3
0x180059a19  cmp     [rbp+var_28], rdi
0x180059a1d  jz      loc_180059642
0x180059a23  mov     rdx, rdi; struct IUnknown *
0x180059a26  lea     rcx, [rbp+var_28]; struct IUnknown **
0x180059a2a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180059a2f  jmp     loc_180059642
0x180059a34  mov     rsi, rdi
0x180059a37  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180059a3e  jmp     loc_1800597D9
0x180059a43  lea     r14, [rsi+0D0h]
0x180059a4a  call    cs:__imp_GetLastError
0x180059a50  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180059a53  mov     r12d, eax
0x180059a56  call    cs:__imp_TlsGetValue
0x180059a5c  test    rax, rax
0x180059a5f  jnz     short loc_180059AAA
0x180059a61  call    cs:__imp_GetLastError
0x180059a67  test    eax, eax
0x180059a69  jnz     short loc_180059AAD
0x180059a6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180059a72  test    rcx, rcx
0x180059a75  jnz     short loc_180059A96
0x180059a77  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180059a7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180059a84  mov     rcx, rax
0x180059a87  test    rax, rax
  ... truncated ...
```
