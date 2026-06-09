# CMFSinkWriter::CreateInstance(ulong,ushort const *,IMFByteStream *,IMFMediaSink *,IMFAttributes *,IUnknown * *)

- ea: `0x180091fc8`
- end: `0x180092567`
- name: `?CreateInstance@CMFSinkWriter@@CAJKPEBGPEAUIMFByteStream@@PEAUIMFMediaSink@@PEAUIMFAttributes@@PEAPEAUIUnknown@@@Z`
- size: `1439`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, struct IMFByteStream *, struct IMFMediaSink *, struct IMFAttributes *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180091a44`
- `0x18009cf1c`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x1800299a0`
- `0x1800746c0`
- `0x18008b664`
- `0x180091fc8`
- `0x180092570`
- `0x1800a2f70`
- `0x1800daf70`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800920e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092399`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800924e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800920e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092399`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800924e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009247e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092317`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009247e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180092064`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800921de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180092323`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009246e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180092064`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800921de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180092323`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009246e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009208a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092204`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800922cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092494`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009208a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092186`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092204`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800922cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092349`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092416`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180092494`

## string_xrefs

- `0x180091fe0`: `CMFSinkWriter::CreateInstance`
- `0x1800920f3`: `CMFSinkWriter::CreateInstance`
- `0x180092265`: `CMFSinkWriter::CreateInstance`
- `0x1800923aa`: `CMFSinkWriter::CreateInstance`
- `0x1800924f5`: `CMFSinkWriter::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFSinkWriter::CreateInstance(
        int a1,
        const unsigned __int16 *a2,
        struct IMFByteStream *a3,
        struct IMFMediaSink *a4,
        struct IMFAttributes *a5,
        struct IUnknown **a6)
{
  int Interface; // ebx
  CallStackTracing *v11; // rdi
  CallStackContext *v12; // rsi
  DWORD LastError; // ebp
  CallStackContext *Value; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  CallStackTracing *v17; // rdi
  CallStackTracing *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  CMFSinkWriter *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  CMFSinkWriter *v24; // rax
  CMFSinkWriter *v25; // r15
  __int64 v26; // rdx
  __int64 v27; // rcx
  CallStackTracing *v28; // rsi
  CallStackTracing *v29; // rax
  CallStackContext *v30; // rbp
  DWORD v31; // r12d
  CallStackContext *v32; // rax
  __int64 v33; // rdx
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  CallStackTracing *v40; // rsi
  CallStackTracing *v41; // rax
  CallStackContext *v42; // rbp
  DWORD v43; // r12d
  CallStackContext *v44; // rax
  __int64 v45; // rdx
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rax
  CallStackTracing *v49; // rsi
  CallStackTracing *v50; // rax
  CallStackContext *v51; // rbp
  DWORD v52; // r15d
  CallStackContext *v53; // rax
  __int64 v54; // rdx
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  char v59[8]; // [rsp+30h] [rbp-48h] BYREF
  struct IMFSinkWriterProfileManager *v60; // [rsp+38h] [rbp-40h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v59, "CMFSinkWriter::CreateInstance", 142);
  v60 = 0;
  Interface = CMFSinkWriterProfileManagerFactory::CreateInstance(a2, a3, a4, a5, &v60);
  if ( Interface < 0 )
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v12 = (CallStackTracing *)((char *)v11 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v11 + 3));
      if ( Value )
      {
        v12 = Value;
      }
      else if ( !GetLastError() )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v16, v15);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
        if ( v19 )
          v12 = (CallStackContext *)v19;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v12 + 499) != Interface )
        CallStackContext::TraceFailure(v12, "CMFSinkWriter::CreateInstance", 153, Interface);
    }
    if ( g_wppLevels )
    {
      v20 = 20;
LABEL_85:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids,
        0,
        Interface);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  v21 = (CMFSinkWriter *)operator new(0x260u);
  if ( v21 )
  {
    v24 = CMFSinkWriter::CMFSinkWriter(v21, a1, v60, a4, a5, a3);
    v25 = v24;
    if ( v24 )
    {
      Interface = CMFSinkWriter::Initialize(v24);
      if ( Interface >= 0 )
      {
        Interface = CMFSinkWriter::QueryInterface(v25, &GUID_00000000_0000_0000_c000_000000000046, (void **)a6);
        if ( Interface >= 0 )
          goto LABEL_64;
        v40 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v39, v38);
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
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = (CallStackTracing *)((char *)v40 + 208);
          v43 = GetLastError();
          v44 = (CallStackContext *)TlsGetValue(*((_DWORD *)v40 + 3));
          if ( v44 )
          {
            v42 = v44;
          }
          else if ( !GetLastError() )
          {
            v46 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
              CallStackTracing::s_wpInstance = v47;
              if ( v47
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
              {
                v46 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v46 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v48 = (**(__int64 (__fastcall ***)(CallStackTracing *))v46)(v46);
            if ( v48 )
              v42 = (CallStackContext *)v48;
          }
          SetLastError(v43);
          if ( *((_DWORD *)v42 + 499) != Interface )
            CallStackContext::TraceFailure(v42, "CMFSinkWriter::CreateInstance", 164, Interface);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v37 = 23;
      }
      else
      {
        v28 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v27, v26);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = (CallStackTracing *)((char *)v28 + 208);
          v31 = GetLastError();
          v32 = (CallStackContext *)TlsGetValue(*((_DWORD *)v28 + 3));
          if ( v32 )
          {
            v30 = v32;
          }
          else if ( !GetLastError() )
          {
            v34 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                v34 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v34 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v34)(v34);
            if ( v36 )
              v30 = (CallStackContext *)v36;
          }
          SetLastError(v31);
          if ( *((_DWORD *)v30 + 499) != Interface )
            CallStackContext::TraceFailure(v30, "CMFSinkWriter::CreateInstance", 162, Interface);
        }
        if ( !g_wppLevels )
          goto LABEL_64;
        v37 = 22;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v37,
        &WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids,
        0,
        Interface);
LABEL_64:
      CMFSinkWriter::Release(v25);
      goto LABEL_86;
    }
  }
  v49 = CallStackTracing::s_wpInstance;
  Interface = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v22);
    CallStackTracing::s_wpInstance = v50;
    if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
    {
      v49 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v49 = (CallStackTracing *)&qword_18010C230;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
    }
  }
  if ( *((_BYTE *)v49 + 8) )
  {
    v51 = (CallStackTracing *)((char *)v49 + 208);
    v52 = GetLastError();
    v53 = (CallStackContext *)TlsGetValue(*((_DWORD *)v49 + 3));
    if ( v53 )
    {
      v51 = v53;
    }
    else if ( !GetLastError() )
    {
      v55 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
        CallStackTracing::s_wpInstance = v56;
        if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
        {
          v55 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v55 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
      if ( v57 )
        v51 = (CallStackContext *)v57;
    }
    SetLastError(v52);
    if ( *((_DWORD *)v51 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v51, "CMFSinkWriter::CreateInstance", 160, -2147024882);
  }
  if ( g_wppLevels )
  {
    v20 = 21;
    goto LABEL_85;
  }
LABEL_86:
  if ( v60 )
    (*(void (__fastcall **)(struct IMFSinkWriterProfileManager *))(*(_QWORD *)v60 + 16LL))(v60);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v59);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180091fc8  push    rbx
0x180091fca  push    rbp
0x180091fcb  push    rsi
0x180091fcc  push    rdi
0x180091fcd  push    r12
0x180091fcf  push    r14
0x180091fd1  push    r15
0x180091fd3  sub     rsp, 40h
0x180091fd7  mov     rsi, r8
0x180091fda  mov     rbx, rdx
0x180091fdd  mov     r14d, ecx
0x180091fe0  lea     rdx, aCmfsinkwriterC; "CMFSinkWriter::CreateInstance"
0x180091fe7  mov     r8d, 8Eh; int
0x180091fed  lea     rcx, [rsp+78h+var_48]; this
0x180091ff2  mov     rdi, r9
0x180091ff5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180091ffa  mov     rbp, [rsp+78h+arg_20]
0x180092002  lea     rax, [rsp+78h+var_40]
0x180092007  mov     r9, rbp; struct IMFAttributes *
0x18009200a  mov     [rsp+78h+var_58], rax; struct IMFSinkWriterProfileManager **
0x18009200f  mov     r8, rdi; struct IMFMediaSink *
0x180092012  mov     [rsp+78h+var_40], 0
0x18009201b  mov     rdx, rsi; struct IMFByteStream *
0x18009201e  mov     rcx, rbx; unsigned __int16 *
0x180092021  call    ?CreateInstance@CMFSinkWriterProfileManagerFactory@@SAJPEBGPEAUIMFByteStream@@PEAUIMFMediaSink@@PEAUIMFAttributes@@PEAPEAUIMFSinkWriterProfileManager@@@Z; CMFSinkWriterProfileManagerFactory::CreateInstance(ushort const *,IMFByteStream *,IMFMediaSink *,IMFAttributes *,IMFSinkWriterProfileManager * *)
0x180092026  mov     ebx, eax
0x180092028  test    eax, eax
0x18009202a  jns     loc_18009211F
0x180092030  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092037  test    rdi, rdi
0x18009203a  jnz     short loc_180092048
0x18009203c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180092041  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092048  cmp     byte ptr [rdi+8], 0
0x18009204c  jz      loc_180092108
0x180092052  lea     rsi, [rdi+0D0h]
0x180092059  call    cs:__imp_GetLastError
0x18009205f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180092062  mov     ebp, eax
0x180092064  call    cs:__imp_TlsGetValue
0x18009206a  test    rax, rax
0x18009206d  jz      short loc_180092074
0x18009206f  mov     rsi, rax
0x180092072  jmp     short loc_1800920E0
0x180092074  call    cs:__imp_GetLastError
0x18009207a  test    eax, eax
0x18009207c  jnz     short loc_1800920E0
0x18009207e  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092085  test    rdi, rdi
0x180092088  jnz     short loc_1800920CB
0x18009208a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180092090  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092097  mov     rcx, rax
0x18009209a  test    rax, rax
0x18009209d  jz      short loc_1800920BD
0x18009209f  mov     rax, [rax]
0x1800920a2  mov     edx, 7F0h
0x1800920a7  mov     rax, [rax+8]
0x1800920ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800920b0  test    eax, eax
0x1800920b2  jz      short loc_1800920BD
0x1800920b4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800920bb  jmp     short loc_1800920CB
0x1800920bd  lea     rdi, qword_18010C230
0x1800920c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800920cb  mov     rax, [rdi]
0x1800920ce  mov     rcx, rdi
0x1800920d1  mov     rax, [rax]
0x1800920d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800920d9  test    rax, rax
0x1800920dc  cmovnz  rsi, rax
0x1800920e0  mov     ecx, ebp; dwErrCode
0x1800920e2  call    cs:__imp_SetLastError
0x1800920e8  cmp     [rsi+7CCh], ebx
0x1800920ee  jz      short loc_180092108
0x1800920f0  mov     r9d, ebx; int
0x1800920f3  lea     rdx, aCmfsinkwriterC; "CMFSinkWriter::CreateInstance"
0x1800920fa  mov     r8d, 99h; int
0x180092100  mov     rcx, rsi; this
0x180092103  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180092108  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009210f  jb      loc_180092536
0x180092115  mov     edx, 14h
0x18009211a  jmp     loc_180092518
0x18009211f  mov     ecx, 260h; Size
0x180092124  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180092129  test    rax, rax
0x18009212c  jz      loc_1800923F8
0x180092132  mov     r8, [rsp+78h+var_40]; struct IMFSinkWriterProfileManager *
0x180092137  mov     r9, rdi; struct IMFMediaSink *
0x18009213a  mov     [rsp+78h+var_50], rsi; struct IMFByteStream *
0x18009213f  mov     edx, r14d; unsigned int
0x180092142  mov     rcx, rax; this
0x180092145  mov     [rsp+78h+var_58], rbp; struct IMFAttributes *
0x18009214a  call    ??0CMFSinkWriter@@AEAA@KPEAUIMFSinkWriterProfileManager@@PEAUIMFMediaSink@@PEAUIMFAttributes@@PEAUIMFByteStream@@@Z; CMFSinkWriter::CMFSinkWriter(ulong,IMFSinkWriterProfileManager *,IMFMediaSink *,IMFAttributes *,IMFByteStream *)
0x18009214f  mov     r15, rax
0x180092152  test    rax, rax
0x180092155  jz      loc_1800923F8
0x18009215b  mov     rcx, rax; this
0x18009215e  call    ?Initialize@CMFSinkWriter@@AEAAJXZ; CMFSinkWriter::Initialize(void)
0x180092163  mov     ebx, eax
0x180092165  test    eax, eax
0x180092167  jns     loc_180092291
0x18009216d  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092174  lea     rdi, qword_18010C230
0x18009217b  mov     r14d, 7F0h
0x180092181  test    rsi, rsi
0x180092184  jnz     short loc_1800921C1
0x180092186  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009218c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092193  mov     rcx, rax
0x180092196  test    rax, rax
0x180092199  jz      short loc_1800921B7
0x18009219b  mov     rax, [rax]
0x18009219e  mov     edx, r14d
0x1800921a1  mov     rax, [rax+8]
0x1800921a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921aa  test    eax, eax
0x1800921ac  jz      short loc_1800921B7
0x1800921ae  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800921b5  jmp     short loc_1800921C1
0x1800921b7  mov     rsi, rdi
0x1800921ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800921c1  cmp     byte ptr [rsi+8], 0
0x1800921c5  jz      loc_18009227A
0x1800921cb  lea     rbp, [rsi+0D0h]
0x1800921d2  call    cs:__imp_GetLastError
0x1800921d8  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800921db  mov     r12d, eax
0x1800921de  call    cs:__imp_TlsGetValue
0x1800921e4  test    rax, rax
0x1800921e7  jz      short loc_1800921EE
0x1800921e9  mov     rbp, rax
0x1800921ec  jmp     short loc_180092251
0x1800921ee  call    cs:__imp_GetLastError
0x1800921f4  test    eax, eax
0x1800921f6  jnz     short loc_180092251
0x1800921f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800921ff  test    rcx, rcx
0x180092202  jnz     short loc_18009223F
0x180092204  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009220a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092211  mov     rcx, rax
0x180092214  test    rax, rax
0x180092217  jz      short loc_180092235
0x180092219  mov     rax, [rax]
0x18009221c  mov     edx, r14d
0x18009221f  mov     rax, [rax+8]
0x180092223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092228  test    eax, eax
0x18009222a  jz      short loc_180092235
0x18009222c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092233  jmp     short loc_18009223F
0x180092235  mov     rcx, rdi
0x180092238  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009223f  mov     rax, [rcx]
0x180092242  mov     rax, [rax]
0x180092245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009224a  test    rax, rax
0x18009224d  cmovnz  rbp, rax
0x180092251  mov     ecx, r12d; dwErrCode
0x180092254  call    cs:__imp_SetLastError
0x18009225a  cmp     [rbp+7CCh], ebx
0x180092260  jz      short loc_18009227A
0x180092262  mov     r9d, ebx; int
0x180092265  lea     rdx, aCmfsinkwriterC; "CMFSinkWriter::CreateInstance"
0x18009226c  mov     r8d, 0A2h; int
0x180092272  mov     rcx, rbp; this
0x180092275  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009227a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180092281  jb      loc_1800923EB
0x180092287  mov     edx, 16h
0x18009228c  jmp     loc_1800923CD
0x180092291  mov     r8, [rsp+78h+arg_28]; void **
0x180092299  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800922a0  mov     rcx, r15; this
0x1800922a3  call    ?QueryInterface@CMFSinkWriter@@UEAAJAEBU_GUID@@PEAPEAX@Z; CMFSinkWriter::QueryInterface(_GUID const &,void * *)
0x1800922a8  mov     ebx, eax
0x1800922aa  test    eax, eax
0x1800922ac  jns     loc_1800923EB
0x1800922b2  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800922b9  lea     rdi, qword_18010C230
0x1800922c0  mov     r14d, 7F0h
0x1800922c6  test    rsi, rsi
0x1800922c9  jnz     short loc_180092306
0x1800922cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800922d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800922d8  mov     rcx, rax
0x1800922db  test    rax, rax
0x1800922de  jz      short loc_1800922FC
0x1800922e0  mov     rax, [rax]
0x1800922e3  mov     edx, r14d
0x1800922e6  mov     rax, [rax+8]
0x1800922ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800922ef  test    eax, eax
0x1800922f1  jz      short loc_1800922FC
0x1800922f3  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800922fa  jmp     short loc_180092306
0x1800922fc  mov     rsi, rdi
0x1800922ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180092306  cmp     byte ptr [rsi+8], 0
0x18009230a  jz      loc_1800923BF
0x180092310  lea     rbp, [rsi+0D0h]
0x180092317  call    cs:__imp_GetLastError
0x18009231d  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180092320  mov     r12d, eax
0x180092323  call    cs:__imp_TlsGetValue
0x180092329  test    rax, rax
0x18009232c  jz      short loc_180092333
0x18009232e  mov     rbp, rax
0x180092331  jmp     short loc_180092396
0x180092333  call    cs:__imp_GetLastError
0x180092339  test    eax, eax
0x18009233b  jnz     short loc_180092396
0x18009233d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092344  test    rcx, rcx
0x180092347  jnz     short loc_180092384
0x180092349  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009234f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092356  mov     rcx, rax
0x180092359  test    rax, rax
0x18009235c  jz      short loc_18009237A
0x18009235e  mov     rax, [rax]
0x180092361  mov     edx, r14d
0x180092364  mov     rax, [rax+8]
0x180092368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009236d  test    eax, eax
0x18009236f  jz      short loc_18009237A
0x180092371  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092378  jmp     short loc_180092384
0x18009237a  mov     rcx, rdi
0x18009237d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180092384  mov     rax, [rcx]
0x180092387  mov     rax, [rax]
0x18009238a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009238f  test    rax, rax
0x180092392  cmovnz  rbp, rax
0x180092396  mov     ecx, r12d; dwErrCode
0x180092399  call    cs:__imp_SetLastError
0x18009239f  cmp     [rbp+7CCh], ebx
0x1800923a5  jz      short loc_1800923BF
0x1800923a7  mov     r9d, ebx; int
0x1800923aa  lea     rdx, aCmfsinkwriterC; "CMFSinkWriter::CreateInstance"
0x1800923b1  mov     r8d, 0A4h; int
0x1800923b7  mov     rcx, rbp; this
0x1800923ba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800923bf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800923c6  jb      short loc_1800923EB
0x1800923c8  mov     edx, 17h
0x1800923cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800923d4  lea     r8, WPP_4d1f6947f0d43fe86eef9ca62ba9bf82_Traceguids
0x1800923db  xor     r9d, r9d
0x1800923de  mov     dword ptr [rsp+78h+var_58], ebx
0x1800923e2  mov     rcx, [rcx+10h]
0x1800923e6  call    WPP_SF_qD
0x1800923eb  mov     rcx, r15; this
0x1800923ee  call    ?Release@CMFSinkWriter@@UEAAKXZ; CMFSinkWriter::Release(void)
0x1800923f3  jmp     loc_180092536
0x1800923f8  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800923ff  lea     rdi, qword_18010C230
0x180092406  mov     ebx, 8007000Eh
0x18009240b  mov     r14d, 7F0h
0x180092411  test    rsi, rsi
0x180092414  jnz     short loc_180092451
0x180092416  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009241c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180092423  mov     rcx, rax
0x180092426  test    rax, rax
0x180092429  jz      short loc_180092447
0x18009242b  mov     rax, [rax]
0x18009242e  mov     edx, r14d
0x180092431  mov     rax, [rax+8]
0x180092435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009243a  test    eax, eax
0x18009243c  jz      short loc_180092447
0x18009243e  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180092445  jmp     short loc_180092451
0x180092447  mov     rsi, rdi
0x18009244a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180092451  cmp     byte ptr [rsi+8], 0
0x180092455  jz      loc_18009250A
0x18009245b  lea     rbp, [rsi+0D0h]
0x180092462  call    cs:__imp_GetLastError
0x180092468  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x18009246b  mov     r15d, eax
0x18009246e  call    cs:__imp_TlsGetValue
0x180092474  test    rax, rax
0x180092477  jz      short loc_18009247E
0x180092479  mov     rbp, rax
0x18009247c  jmp     short loc_1800924E1
0x18009247e  call    cs:__imp_GetLastError
0x180092484  test    eax, eax
0x180092486  jnz     short loc_1800924E1
0x180092488  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009248f  test    rcx, rcx
0x180092492  jnz     short loc_1800924CF
0x180092494  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009249a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800924a1  mov     rcx, rax
0x1800924a4  test    rax, rax
  ... truncated ...
```
