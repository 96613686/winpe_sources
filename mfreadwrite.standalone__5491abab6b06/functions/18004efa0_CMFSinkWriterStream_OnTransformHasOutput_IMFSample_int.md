# CMFSinkWriterStream::OnTransformHasOutput(IMFSample * *,int *)

- ea: `0x18004efa0`
- end: `0x18004f69f`
- name: `?OnTransformHasOutput@CMFSinkWriterStream@@AEAAJPEAPEAUIMFSample@@PEAH@Z`
- size: `1791`
- prototype: `__int64 __fastcall(CMFSinkWriterStream *__hidden this, struct IMFSample **, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d430`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x180032a9c`
- `0x18004efa0`
- `0x18006c1b0`
- `0x18009a628`
- `0x1800acd2c`
- `0x1800b8a8c`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f3c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f510`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f012`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f3c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004f510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f19d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f19d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f4bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004effd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f142`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f36b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f4b2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004effd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f142`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f36b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004f4b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f2fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f38c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f4d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f2fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f38c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f423`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004f4d3`

## string_xrefs

- `0x18004efd9`: `CMFSinkWriterStream::OnTransformHasOutput`
- `0x18004f01e`: `CMFSinkWriterStream::OnTransformHasOutput`
- `0x18004f3df`: `CMFSinkWriterStream::OnTransformHasOutput`
- `0x18004f526`: `CMFSinkWriterStream::OnTransformHasOutput`
- `0x18004f2a1`: `CMFSinkWriterStream::TraceSample`

## pseudocode

```c
__int64 __fastcall CMFSinkWriterStream::OnTransformHasOutput(CMFSinkWriterStream *this, struct IMFSample **a2, int *a3)
{
  CallStackTracing *v3; // rbx
  char *v7; // rdi
  DWORD LastError; // r12d
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // edi
  __int64 *v16; // rbx
  _QWORD *v17; // rcx
  unsigned int v18; // edx
  unsigned int i; // ebx
  __int64 v20; // rsi
  __int64 v21; // rcx
  CallStackTracing *v22; // rbx
  CallStackContext *v23; // rsi
  DWORD v24; // r14d
  CallStackContext *v25; // rax
  int v26; // edx
  int v27; // edx
  CallStackTracing *v29; // rcx
  __int64 v30; // rax
  CallStackTracing *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // r15d
  __int64 *v35; // rcx
  int (__fastcall *v36)(__int64 *, __int64 *); // rax
  int v37; // r8d
  CallStackTracing *v38; // rbx
  CallStackTracing *v39; // rax
  __int64 v40; // rdx
  CallStackContext *v41; // r15
  DWORD v42; // r12d
  CallStackContext *v43; // rax
  __int64 v44; // rdx
  CallStackTracing *v45; // rcx
  CallStackTracing *v46; // rax
  __int64 v47; // rax
  CallStackTracing *v48; // rbx
  CallStackTracing *v49; // rax
  CallStackContext *v50; // r15
  DWORD v51; // r12d
  CallStackContext *v52; // rax
  __int64 v53; // rdx
  CallStackTracing *v54; // rcx
  CallStackTracing *v55; // rax
  __int64 v56; // rax
  char v57; // cl
  char v58; // al
  __int64 v59; // rdx
  __int64 v60; // rcx
  unsigned int v61; // [rsp+68h] [rbp+7h] BYREF
  unsigned int v62; // [rsp+6Ch] [rbp+Bh] BYREF
  LPVOID pv; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v64; // [rsp+78h] [rbp+17h] BYREF
  __int64 v65; // [rsp+80h] [rbp+1Fh] BYREF
  char v66; // [rsp+C8h] [rbp+67h] BYREF
  int v67; // [rsp+D0h] [rbp+6Fh] BYREF
  int v68; // [rsp+E0h] [rbp+7Fh] BYREF

  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v29 = CallStackTracing::s_wpInstance;
      }
      v30 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
      if ( v30 )
        v7 = (char *)v30;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CMFSinkWriterStream::OnTransformHasOutput";
      *(_DWORD *)&v7[8 * v11 + 8] = 3140;
    }
    ++*((_DWORD *)v7 + 497);
  }
  *a2 = 0;
  v12 = *((_QWORD *)this + 30);
  pv = 0;
  v61 = 0;
  v62 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, LPVOID *, unsigned int *, unsigned int *, _QWORD))(*(_QWORD *)v12 + 104LL))(
          v12,
          &pv,
          &v61,
          &v62,
          0);
  if ( v15 >= 0 )
  {
    v16 = *(__int64 **)pv;
    if ( *(_QWORD *)pv )
    {
      if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
      {
        v33 = *v16;
        v34 = *((_DWORD *)this + 29);
        v35 = *(__int64 **)pv;
        v65 = 0;
        v64 = 0;
        v36 = *(int (__fastcall **)(__int64 *, __int64 *))(v33 + 280);
        v68 = 0;
        v67 = 0;
        if ( v36(v35, &v65) < 0 )
          v65 = 0;
        if ( (*(int (__fastcall **)(__int64 *, __int64 *))(*v16 + 296))(v16, &v64) < 0 )
          v64 = 0;
        if ( (*(int (__fastcall **)(__int64 *, const GUID *, int *))(*v16 + 56))(
               v16,
               &MFSampleExtension_Discontinuity,
               &v68) < 0 )
          v68 = 0;
        if ( (*(int (__fastcall **)(__int64 *, const GUID *, int *))(*v16 + 56))(
               v16,
               &MFSampleExtension_CleanPoint,
               &v67) < 0 )
          v67 = 0;
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v66, "CMFSinkWriterStream::TraceSample", 3577);
        if ( (unsigned __int8)byte_18010CAF1 >= 0x10u )
        {
          v57 = 95;
          v58 = 95;
          if ( v67 )
            v58 = 67;
          if ( v68 )
            v57 = 68;
          WPP_SF_qsqDIIcc(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            68,
            v37,
            (_DWORD)this,
            (__int64)"MFTChain->ProcessOutput",
            *((_QWORD *)this + 30),
            v34,
            v65,
            v64,
            v57,
            v58);
        }
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 16) + 64LL))(
        *((_QWORD *)this + 16),
        *((unsigned int *)this + 29),
        *(_QWORD *)pv);
      v17 = pv;
      *a2 = *(struct IMFSample **)pv;
      *v17 = 0;
    }
    else
    {
      if ( byte_18010CAF1 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 333, &WPP_10c5bd23ec87306545c11a0d5cbbba16_Traceguids, this);
      *a3 = 1;
    }
    goto LABEL_13;
  }
  if ( v15 == -1072861855 )
  {
    v15 = CMFSinkWriterStream::OnTransformStreamChange(this, v62);
    if ( v15 < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v60, v59);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v38 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v38 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v41 = (CallStackTracing *)((char *)v38 + 208);
        v42 = GetLastError();
        v43 = (CallStackContext *)TlsGetValue(*((_DWORD *)v38 + 3));
        if ( v43 )
        {
          v41 = v43;
        }
        else if ( !GetLastError() )
        {
          v45 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
            CallStackTracing::s_wpInstance = v46;
            if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
            {
              v45 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v45 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v47 = (**(__int64 (__fastcall ***)(CallStackTracing *))v45)(v45);
          if ( v47 )
            v41 = (CallStackContext *)v47;
        }
        SetLastError(v42);
        if ( *((_DWORD *)v41 + 499) != v15 )
          CallStackContext::TraceFailure(v41, "CMFSinkWriterStream::OnTransformHasOutput", 3176, v15);
      }
      if ( g_wppLevels )
      {
        v40 = 334;
LABEL_75:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_10c5bd23ec87306545c11a0d5cbbba16_Traceguids, this, v15);
      }
    }
  }
  else
  {
    if ( byte_18010CAF1 )
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        335,
        &WPP_10c5bd23ec87306545c11a0d5cbbba16_Traceguids,
        this,
        *((_QWORD *)this + 30),
        v15);
    v48 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v48 + 8) )
    {
      v50 = (CallStackTracing *)((char *)v48 + 208);
      v51 = GetLastError();
      v52 = (CallStackContext *)TlsGetValue(*((_DWORD *)v48 + 3));
      if ( v52 )
      {
        v50 = v52;
      }
      else if ( !GetLastError() )
      {
        v54 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v56 = (**(__int64 (__fastcall ***)(CallStackTracing *))v54)(v54);
        if ( v56 )
          v50 = (CallStackContext *)v56;
      }
      SetLastError(v51);
      if ( *((_DWORD *)v50 + 499) != v15 )
        CallStackContext::TraceFailure(v50, "CMFSinkWriterStream::OnTransformHasOutput", 3181, v15);
    }
    if ( g_wppLevels )
    {
      v40 = 336;
      goto LABEL_75;
    }
  }
LABEL_13:
  v18 = v61;
  for ( i = 0; i < v18; ++i )
  {
    v20 = 8LL * i;
    v21 = *(_QWORD *)((char *)pv + v20);
    if ( v21 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      *(_QWORD *)((char *)pv + v20) = 0;
      v18 = v61;
    }
  }
  CoTaskMemFree(pv);
  pv = 0;
  if ( v15 < 0 && *a2 )
  {
    ((void (__fastcall *)(_QWORD))(*a2)->lpVtbl->Release)(*a2);
    *a2 = 0;
  }
  v22 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v23 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
    v24 = GetLastError();
    v25 = (CallStackContext *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v25 )
    {
      v23 = v25;
    }
    else if ( !GetLastError() )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v31 = CallStackTracing::s_wpInstance;
      }
      v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
      if ( v32 )
        v23 = (CallStackContext *)v32;
    }
    SetLastError(v24);
    v26 = *((_DWORD *)v23 + 497);
    if ( v26 )
    {
      v27 = v26 - 1;
      *((_DWORD *)v23 + 497) = v27;
      if ( !v27 )
        CallStackContext::ClearState(v23);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004efa0  mov     rax, rsp
0x18004efa3  push    rbp
0x18004efa4  push    rbx
0x18004efa5  push    rsi
0x18004efa6  push    rdi
0x18004efa7  push    r14
0x18004efa9  lea     rbp, [rax-5Fh]
0x18004efad  sub     rsp, 90h
0x18004efb4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004efbb  mov     r14, rdx
0x18004efbe  mov     [rax-30h], r13
0x18004efc2  mov     rsi, rcx
0x18004efc5  mov     [rax-38h], r15
0x18004efc9  mov     r15, r8
0x18004efcc  test    rbx, rbx
0x18004efcf  jz      loc_18004F18C
0x18004efd5  cmp     byte ptr [rbx+8], 0
0x18004efd9  lea     rcx, aCmfsinkwriters_45; "CMFSinkWriterStream::OnTransformHasOutp"...
0x18004efe0  mov     [rsp+0B0h+arg_10], r12
0x18004efe8  jz      short loc_18004F042
0x18004efea  lea     rdi, [rbx+0D0h]
0x18004eff1  call    cs:__imp_GetLastError
0x18004eff7  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004effa  mov     r12d, eax
0x18004effd  call    cs:__imp_TlsGetValue
0x18004f003  test    rax, rax
0x18004f006  jz      loc_18004F19D
0x18004f00c  mov     rdi, rax
0x18004f00f  mov     ecx, r12d; dwErrCode
0x18004f012  call    cs:__imp_SetLastError
0x18004f018  mov     eax, [rdi+7C4h]
0x18004f01e  lea     rcx, aCmfsinkwriters_45; "CMFSinkWriterStream::OnTransformHasOutp"...
0x18004f025  cmp     eax, [rdi+7C8h]
0x18004f02b  jnb     short loc_18004F03C
0x18004f02d  add     rax, rax
0x18004f030  mov     [rdi+rax*8], rcx
0x18004f034  mov     dword ptr [rdi+rax*8+8], 0C44h
0x18004f03c  inc     dword ptr [rdi+7C4h]
0x18004f042  xor     r13d, r13d
0x18004f045  lea     r9, [rbp+57h+var_4C]
0x18004f049  mov     [r14], r13
0x18004f04c  lea     r8, [rbp+57h+var_50]
0x18004f050  mov     rcx, [rsi+0F0h]
0x18004f057  lea     rdx, [rbp+57h+pv]
0x18004f05b  mov     [rbp+57h+pv], r13
0x18004f05f  mov     [rbp+57h+var_50], r13d
0x18004f063  mov     [rbp+57h+var_4C], r13d
0x18004f067  mov     rax, [rcx]
0x18004f06a  mov     [rsp+0B0h+var_90], r13
0x18004f06f  mov     rax, [rax+68h]
0x18004f073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f078  mov     edi, eax
0x18004f07a  test    eax, eax
0x18004f07c  js      loc_18004F600
0x18004f082  mov     rax, [rbp+57h+pv]
0x18004f086  mov     rbx, [rax]
0x18004f089  test    rbx, rbx
0x18004f08c  jz      loc_18004F55E
0x18004f092  cmp     cs:byte_18010CAF1, 10h
0x18004f099  jnb     loc_18004F207
0x18004f09f  mov     rcx, [rsi+80h]
0x18004f0a6  mov     r8, [rbp+57h+pv]
0x18004f0aa  mov     edx, [rsi+74h]
0x18004f0ad  mov     rax, [rcx]
0x18004f0b0  mov     r8, [r8]
0x18004f0b3  mov     rax, [rax+40h]
0x18004f0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0bc  mov     rcx, [rbp+57h+pv]
0x18004f0c0  mov     rax, [rcx]
0x18004f0c3  mov     [r14], rax
0x18004f0c6  mov     [rcx], r13
0x18004f0c9  mov     edx, [rbp+57h+var_50]
0x18004f0cc  mov     ebx, r13d
0x18004f0cf  mov     r15, [rsp+0B0h+var_30]
0x18004f0d7  mov     r12, [rsp+0B0h+arg_10]
0x18004f0df  test    edx, edx
0x18004f0e1  jz      short loc_18004F104
0x18004f0e3  mov     eax, ebx
0x18004f0e5  lea     rsi, ds:0[rax*8]
0x18004f0ed  mov     rax, [rbp+57h+pv]
0x18004f0f1  mov     rcx, [rsi+rax]
0x18004f0f5  test    rcx, rcx
0x18004f0f8  jnz     loc_18004F663
0x18004f0fe  inc     ebx
0x18004f100  cmp     ebx, edx
0x18004f102  jb      short loc_18004F0E3
0x18004f104  mov     rcx, [rbp+57h+pv]; pv
0x18004f108  call    cs:__imp_CoTaskMemFree
0x18004f10e  mov     [rbp+57h+pv], r13
0x18004f112  test    edi, edi
0x18004f114  js      loc_18004F67F
0x18004f11a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f121  mov     r13, [rsp+88h]
0x18004f129  cmp     byte ptr [rbx+8], 0
0x18004f12d  jz      short loc_18004F172
0x18004f12f  lea     rsi, [rbx+0D0h]
0x18004f136  call    cs:__imp_GetLastError
0x18004f13c  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004f13f  mov     r14d, eax
0x18004f142  call    cs:__imp_TlsGetValue
0x18004f148  test    rax, rax
0x18004f14b  jz      loc_18004F1D2
0x18004f151  mov     rsi, rax
0x18004f154  mov     ecx, r14d; dwErrCode
0x18004f157  call    cs:__imp_SetLastError
0x18004f15d  mov     edx, [rsi+7C4h]
0x18004f163  test    edx, edx
0x18004f165  jz      short loc_18004F172
0x18004f167  sub     edx, 1
0x18004f16a  mov     [rsi+7C4h], edx
0x18004f170  jz      short loc_18004F182
0x18004f172  mov     eax, edi
0x18004f174  add     rsp, 90h
0x18004f17b  pop     r14
0x18004f17d  pop     rdi
0x18004f17e  pop     rsi
0x18004f17f  pop     rbx
0x18004f180  pop     rbp
0x18004f181  retn
0x18004f182  mov     rcx, rsi; this
0x18004f185  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18004f18a  jmp     short loc_18004F172
0x18004f18c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004f191  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f198  jmp     loc_18004EFD5
0x18004f19d  call    cs:__imp_GetLastError
0x18004f1a3  test    eax, eax
0x18004f1a5  jnz     loc_18004F00F
0x18004f1ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f1b2  test    rcx, rcx
0x18004f1b5  jz      loc_18004F2CC
0x18004f1bb  mov     rax, [rcx]
0x18004f1be  mov     rax, [rax]
0x18004f1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1c6  test    rax, rax
0x18004f1c9  cmovnz  rdi, rax
0x18004f1cd  jmp     loc_18004F00F
0x18004f1d2  call    cs:__imp_GetLastError
0x18004f1d8  test    eax, eax
0x18004f1da  jnz     loc_18004F154
0x18004f1e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f1e7  test    rcx, rcx
0x18004f1ea  jz      loc_18004F2DD
0x18004f1f0  mov     rax, [rcx]
0x18004f1f3  mov     rax, [rax]
0x18004f1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1fb  test    rax, rax
0x18004f1fe  cmovnz  rsi, rax
0x18004f202  jmp     loc_18004F154
0x18004f207  mov     rax, [rbx]
0x18004f20a  lea     rdx, [rbp+57h+var_38]
0x18004f20e  mov     r15d, [rsi+74h]
0x18004f212  mov     rcx, rbx
0x18004f215  mov     [rbp+57h+var_38], r13
0x18004f219  mov     [rbp+57h+var_40], r13
0x18004f21d  mov     rax, [rax+118h]
0x18004f224  mov     [rbp+57h+arg_18], r13d
0x18004f228  mov     [rbp+57h+arg_8], r13d
0x18004f22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f231  test    eax, eax
0x18004f233  jns     short loc_18004F239
0x18004f235  mov     [rbp+57h+var_38], r13
0x18004f239  mov     rax, [rbx]
0x18004f23c  lea     rdx, [rbp+57h+var_40]
0x18004f240  mov     rcx, rbx
0x18004f243  mov     rax, [rax+128h]
0x18004f24a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f24f  test    eax, eax
0x18004f251  jns     short loc_18004F257
0x18004f253  mov     [rbp+57h+var_40], r13
0x18004f257  mov     rax, [rbx]
0x18004f25a  lea     r8, [rbp+57h+arg_18]
0x18004f25e  lea     rdx, MFSampleExtension_Discontinuity
0x18004f265  mov     rcx, rbx
0x18004f268  mov     rax, [rax+38h]
0x18004f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f271  test    eax, eax
0x18004f273  jns     short loc_18004F279
0x18004f275  mov     [rbp+57h+arg_18], r13d
0x18004f279  mov     rax, [rbx]
0x18004f27c  lea     r8, [rbp+57h+arg_8]
0x18004f280  lea     rdx, MFSampleExtension_CleanPoint
0x18004f287  mov     rcx, rbx
0x18004f28a  mov     rax, [rax+38h]
0x18004f28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f293  test    eax, eax
0x18004f295  jns     short loc_18004F29B
0x18004f297  mov     [rbp+57h+arg_8], r13d
0x18004f29b  mov     r8d, 0DF9h; int
0x18004f2a1  lea     rdx, aCmfsinkwriters_3; "CMFSinkWriterStream::TraceSample"
0x18004f2a8  lea     rcx, [rbp+57h+arg_0]; this
0x18004f2ac  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004f2b1  cmp     cs:byte_18010CAF1, 10h
0x18004f2b8  jnb     loc_18004F592
0x18004f2be  lea     rcx, [rbp+57h+arg_0]; this
0x18004f2c2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004f2c7  jmp     loc_18004F09F
0x18004f2cc  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004f2d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2d8  jmp     loc_18004F1BB
0x18004f2dd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004f2e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2e9  jmp     loc_18004F1F0
0x18004f2ee  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f2f5  test    rbx, rbx
0x18004f2f8  jnz     short loc_18004F32B
0x18004f2fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f300  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f307  mov     rcx, rax
0x18004f30a  test    rax, rax
0x18004f30d  jz      short loc_18004F348
0x18004f30f  mov     rax, [rax]
0x18004f312  mov     edx, 7F0h
0x18004f317  mov     rax, [rax+8]
0x18004f31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f320  test    eax, eax
0x18004f322  jz      short loc_18004F348
0x18004f324  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f32b  cmp     [rbx+8], r13b
0x18004f32f  jnz     short loc_18004F358
0x18004f331  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f338  jb      loc_18004F0C9
0x18004f33e  mov     edx, 14Eh
0x18004f343  jmp     loc_18004F46C
0x18004f348  lea     rbx, qword_18010C230
0x18004f34f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f356  jmp     short loc_18004F32B
0x18004f358  lea     r15, [rbx+0D0h]
0x18004f35f  call    cs:__imp_GetLastError
0x18004f365  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004f368  mov     r12d, eax
0x18004f36b  call    cs:__imp_TlsGetValue
0x18004f371  test    rax, rax
0x18004f374  jnz     short loc_18004F3C3
0x18004f376  call    cs:__imp_GetLastError
0x18004f37c  test    eax, eax
0x18004f37e  jnz     short loc_18004F3C6
0x18004f380  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f387  test    rcx, rcx
0x18004f38a  jnz     short loc_18004F3AF
0x18004f38c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f392  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f399  mov     rcx, rax
0x18004f39c  test    rax, rax
0x18004f39f  jnz     short loc_18004F3F9
0x18004f3a1  lea     rcx, qword_18010C230
0x18004f3a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f3af  mov     rax, [rcx]
0x18004f3b2  mov     rax, [rax]
0x18004f3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3ba  test    rax, rax
0x18004f3bd  cmovnz  r15, rax
0x18004f3c1  jmp     short loc_18004F3C6
0x18004f3c3  mov     r15, rax
0x18004f3c6  mov     ecx, r12d; dwErrCode
0x18004f3c9  call    cs:__imp_SetLastError
0x18004f3cf  cmp     [r15+7CCh], edi
0x18004f3d6  jz      loc_18004F331
0x18004f3dc  mov     r9d, edi; int
0x18004f3df  lea     rdx, aCmfsinkwriters_45; "CMFSinkWriterStream::OnTransformHasOutp"...
0x18004f3e6  mov     r8d, 0C68h; int
0x18004f3ec  mov     rcx, r15; this
0x18004f3ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004f3f4  jmp     loc_18004F331
0x18004f3f9  mov     rax, [rax]
0x18004f3fc  mov     edx, 7F0h
0x18004f401  mov     rax, [rax+8]
0x18004f405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f40a  test    eax, eax
0x18004f40c  jz      short loc_18004F3A1
0x18004f40e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f415  jmp     short loc_18004F3AF
0x18004f417  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f41e  test    rbx, rbx
0x18004f421  jnz     short loc_18004F454
0x18004f423  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004f429  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f430  mov     rcx, rax
0x18004f433  test    rax, rax
0x18004f436  jz      short loc_18004F48F
0x18004f438  mov     rax, [rax]
0x18004f43b  mov     edx, 7F0h
0x18004f440  mov     rax, [rax+8]
0x18004f444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f449  test    eax, eax
0x18004f44b  jz      short loc_18004F48F
0x18004f44d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004f454  cmp     [rbx+8], r13b
0x18004f458  jnz     short loc_18004F49F
0x18004f45a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f461  jb      loc_18004F0C9
0x18004f467  mov     edx, 150h
0x18004f46c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f473  lea     r8, WPP_10c5bd23ec87306545c11a0d5cbbba16_Traceguids
0x18004f47a  mov     r9, rsi
0x18004f47d  mov     dword ptr [rsp+0B0h+var_90], edi
0x18004f481  mov     rcx, [rcx+10h]
0x18004f485  call    WPP_SF_qD
0x18004f48a  jmp     loc_18004F0C9
0x18004f48f  lea     rbx, qword_18010C230
  ... truncated ...
```
