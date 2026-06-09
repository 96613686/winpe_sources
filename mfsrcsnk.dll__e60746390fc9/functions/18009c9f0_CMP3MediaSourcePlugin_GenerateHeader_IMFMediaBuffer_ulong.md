# CMP3MediaSourcePlugin::GenerateHeader(IMFMediaBuffer *,ulong *)

- ea: `0x18009c9f0`
- end: `0x18009cfce`
- name: `?GenerateHeader@CMP3MediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@PEAK@Z`
- size: `1502`
- prototype: `int(CMP3MediaSourcePlugin *__hidden this, struct IMFMediaBuffer *, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18004b7c4`
- `0x18004f08c`
- `0x1800629a4`
- `0x180073b14`
- `0x18009c9f0`
- `0x1801099f0`
- `0x18010a450`
- `0x180151c6c`
- `0x1801618b0`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cf9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cf9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ca45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ca45`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009caac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cbac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cc88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cd80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ce74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009caac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cbac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cc88`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009cd80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009ce74`

## string_xrefs

- `0x18009ca68`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cb03`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cb71`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cc03`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cc4f`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009ccdf`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cdd7`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cecb`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x18009cf4a`: `CMP3MediaSourcePlugin::GenerateHeader`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::GenerateHeader(
        CMP3MediaSourcePlugin *this,
        struct IMFMediaBuffer *a2,
        unsigned int *a3)
{
  char *v6; // r12
  char *v7; // rsi
  CMP3Properties **v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  size_t v24; // rdi
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  char *v30; // r9
  __int64 v31; // rdx
  int v32; // ecx
  size_t v33; // rax
  CMP3Properties *v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  unsigned __int64 v40; // rcx
  size_t v41; // rdi
  char v43[8]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v44[16]; // [rsp+38h] [rbp-48h] BYREF
  size_t Size; // [rsp+48h] [rbp-38h] BYREF
  void *v46; // [rsp+50h] [rbp-30h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-28h]
  unsigned __int64 v48; // [rsp+60h] [rbp-20h] BYREF
  size_t v49; // [rsp+68h] [rbp-18h] BYREF
  char *v50; // [rsp+70h] [rbp-10h]

  v48 = 0;
  v49 = 0;
  v50 = 0;
  Size = 0;
  v6 = 0;
  v46 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v7 = (char *)this - 48;
  v8 = (CMP3Properties **)((char *)this + 360);
  if ( *((_DWORD *)this + 338) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "CMP3MediaSourcePlugin::GenerateHeader", 3386);
    v9 = (__int64)*v8 + *(int *)(*((_QWORD *)*v8 + 2) + 8LL) + 16;
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v11 < 0 )
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::GenerateHeader", 3386, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v15 = 320;
      goto LABEL_13;
    }
    *((_DWORD *)v7 + 350) = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  }
  if ( !a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "CMP3MediaSourcePlugin::GenerateHeader", 3392);
    v11 = CMP3Properties::SerializeHeader(*((CMP3Properties **)v7 + 51), 0, &v48);
    if ( v11 >= 0 )
    {
      *a3 = v48 + *((_DWORD *)v7 + 342);
      goto LABEL_14;
    }
    v17 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)v19 + 499) != v11 )
        CallStackContext::TraceFailure(v19, "CMP3MediaSourcePlugin::GenerateHeader", 3392, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v15 = 321;
LABEL_13:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      (char *)this - 48,
      v11);
LABEL_14:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
    goto LABEL_77;
  }
  MFBUFFER::CMFBufferWrapper::CMFBufferWrapper((MFBUFFER::CMFBufferWrapper *)v44, a2);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "CMP3MediaSourcePlugin::GenerateHeader", 3400);
  v11 = MFBUFFER::CMFBufferWrapper::Lock((MFBUFFER::CMFBufferWrapper *)v44, (struct MFBUFFER::CBuffer *)&Size, 0);
  if ( v11 >= 0 )
  {
    v24 = Size;
    v6 = (char *)v46;
    memset_0(v46, 0, Size);
    v25 = *((unsigned int *)v7 + 342);
    if ( v24 >= v25 )
    {
      v50 = v6;
      v33 = v24 - v25;
      v34 = *v8;
      if ( v33 > v24 )
        v33 = v24;
      v49 = v33;
      v35 = CMP3Properties::SerializeHeader(v34, (struct MFBUFFER::CBuffer *)&v49, &v48);
      v11 = v35;
      if ( v35 != -1072875855 )
      {
        if ( v35 < 0 )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
            CallStackTracing::s_wpInstance = v38;
            if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
            {
              v37 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v37 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v37 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
            if ( *((_DWORD *)v39 + 499) != v11 )
              CallStackContext::TraceFailure(v39, "CMP3MediaSourcePlugin::GenerateHeader", 3420, v11);
          }
          if ( !g_wppLevels )
            goto LABEL_76;
          v31 = 324;
          v30 = (char *)this - 48;
LABEL_53:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v31,
            &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
            v30,
            v11);
LABEL_76:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
          MFBUFFER::CMFBufferWrapper::~CMFBufferWrapper((MFBUFFER::CMFBufferWrapper *)v44);
          goto LABEL_77;
        }
        v40 = v48;
        if ( v48 > v24 )
          v40 = v24;
        v41 = v24 - v40;
        if ( *((unsigned int *)this + 330) <= v41 )
          v41 = *((unsigned int *)this + 330);
        memcpy_0(&v6[v40], *((const void **)this + 168), v41);
      }
      v32 = *((_DWORD *)this + 330);
    }
    else
    {
      v11 = CMP3Properties::SerializeHeader(*v8, 0, &v48);
      if ( v11 < 0 )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
          CallStackTracing::s_wpInstance = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v27 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)v29 + 499) != v11 )
            CallStackContext::TraceFailure(v29, "CMP3MediaSourcePlugin::GenerateHeader", 3406, v11);
        }
        if ( !g_wppLevels )
          goto LABEL_76;
        v30 = (char *)this - 48;
        v31 = 323;
        goto LABEL_53;
      }
      v32 = *((_DWORD *)v7 + 342);
      v11 = -1072875855;
    }
    *a3 = v48 + v32;
    goto LABEL_76;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != v11 )
      CallStackContext::TraceFailure(v23, "CMP3MediaSourcePlugin::GenerateHeader", 3400, v11);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      322,
      &WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      (char *)this - 48,
      v11);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  MFBUFFER::CMFBufferWrapper::~CMFBufferWrapper((MFBUFFER::CMFBufferWrapper *)v44);
  v6 = (char *)v46;
LABEL_77:
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v43, "CMP3MediaSourcePlugin::GenerateHeader", 3435);
  if ( (unsigned __int8)byte_1801B110B >= 8u )
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      325,
      (unsigned int)&WPP_d883d89413f235918ed5b1c680996b82_Traceguids,
      (_DWORD)this - 48,
      (__int64)v6);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v43);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18009c9f0  mov     [rsp-38h+arg_18], rbx
0x18009c9f5  push    rbp
0x18009c9f6  push    rsi
0x18009c9f7  push    rdi
0x18009c9f8  push    r12
0x18009c9fa  push    r13
0x18009c9fc  push    r14
0x18009c9fe  push    r15
0x18009ca00  mov     rbp, rsp
0x18009ca03  sub     rsp, 80h
0x18009ca0a  mov     rax, cs:__security_cookie
0x18009ca11  xor     rax, rsp
0x18009ca14  mov     [rbp+var_8], rax
0x18009ca18  xor     ebx, ebx
0x18009ca1a  lea     rax, [rcx+8]
0x18009ca1e  mov     r15, rcx
0x18009ca21  mov     [rbp+var_20], rbx
0x18009ca25  mov     rcx, rax; lpCriticalSection
0x18009ca28  mov     [rbp+var_18], rbx
0x18009ca2c  mov     r13, r8
0x18009ca2f  mov     [rbp+var_10], rbx
0x18009ca33  mov     rdi, rdx
0x18009ca36  mov     [rbp+Size], rbx
0x18009ca3a  mov     r12d, ebx
0x18009ca3d  mov     [rbp+var_30], rbx
0x18009ca41  mov     [rbp+lpCriticalSection], rax
0x18009ca45  call    cs:__imp_EnterCriticalSection
0x18009ca4b  lea     rsi, [r15-30h]
0x18009ca4f  lea     r14, [r15+168h]
0x18009ca56  cmp     [rsi+578h], ebx
0x18009ca5c  jz      loc_18009CB63
0x18009ca62  mov     r8d, 0D3Ah; int
0x18009ca68  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009ca6f  lea     rcx, [rbp+var_50]; this
0x18009ca73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009ca78  mov     rdx, [r14]
0x18009ca7b  mov     rax, [rdx+10h]
0x18009ca7f  add     rdx, 10h
0x18009ca83  movsxd  rcx, dword ptr [rax+8]
0x18009ca87  add     rcx, rdx
0x18009ca8a  mov     rax, [rcx]
0x18009ca8d  mov     rax, [rax+10h]
0x18009ca91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca96  mov     ebx, eax
0x18009ca98  test    eax, eax
0x18009ca9a  jns     loc_18009CB52
0x18009caa0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009caa7  test    rcx, rcx
0x18009caaa  jnz     short loc_18009CAED
0x18009caac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009cab2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cab9  mov     rcx, rax
0x18009cabc  test    rax, rax
0x18009cabf  jz      short loc_18009CADF
0x18009cac1  mov     rax, [rax]
0x18009cac4  mov     edx, 7F0h
0x18009cac9  mov     rax, [rax+8]
0x18009cacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cad2  test    eax, eax
0x18009cad4  jz      short loc_18009CADF
0x18009cad6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cadd  jmp     short loc_18009CAED
0x18009cadf  lea     rcx, qword_1801B07E0; this
0x18009cae6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009caed  cmp     [rcx+8], r12b
0x18009caf1  jz      short loc_18009CB18
0x18009caf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009caf8  cmp     [rax+7CCh], ebx
0x18009cafe  jz      short loc_18009CB18
0x18009cb00  mov     r9d, ebx; int
0x18009cb03  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cb0a  mov     r8d, 0D3Ah; int
0x18009cb10  mov     rcx, rax; this
0x18009cb13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009cb18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009cb1f  jb      short loc_18009CB44
0x18009cb21  mov     edx, 140h
0x18009cb26  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cb2d  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18009cb34  mov     r9, rsi
0x18009cb37  mov     dword ptr [rsp+80h+var_60], ebx
0x18009cb3b  mov     rcx, [rcx+10h]
0x18009cb3f  call    WPP_SF_qD
0x18009cb44  lea     rcx, [rbp+var_50]; this
0x18009cb48  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009cb4d  jmp     loc_18009CF44
0x18009cb52  xor     ebx, ebx
0x18009cb54  lea     rcx, [rbp+var_50]; this
0x18009cb58  mov     [rsi+578h], ebx
0x18009cb5e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009cb63  test    rdi, rdi
0x18009cb66  jnz     loc_18009CC3E
0x18009cb6c  mov     edi, 0D40h
0x18009cb71  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cb78  mov     r8d, edi; int
0x18009cb7b  lea     rcx, [rbp+var_50]; this
0x18009cb7f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009cb84  mov     rcx, [rsi+198h]; this
0x18009cb8b  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18009cb8f  xor     edx, edx; struct MFBUFFER::CBuffer *
0x18009cb91  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x18009cb96  mov     ebx, eax
0x18009cb98  test    eax, eax
0x18009cb9a  jns     loc_18009CC2C
0x18009cba0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cba7  test    rcx, rcx
0x18009cbaa  jnz     short loc_18009CBED
0x18009cbac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009cbb2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cbb9  mov     rcx, rax
0x18009cbbc  test    rax, rax
0x18009cbbf  jz      short loc_18009CBDF
0x18009cbc1  mov     rax, [rax]
0x18009cbc4  mov     edx, 7F0h
0x18009cbc9  mov     rax, [rax+8]
0x18009cbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbd2  test    eax, eax
0x18009cbd4  jz      short loc_18009CBDF
0x18009cbd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cbdd  jmp     short loc_18009CBED
0x18009cbdf  lea     rcx, qword_1801B07E0; this
0x18009cbe6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cbed  cmp     [rcx+8], r12b
0x18009cbf1  jz      short loc_18009CC15
0x18009cbf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009cbf8  cmp     [rax+7CCh], ebx
0x18009cbfe  jz      short loc_18009CC15
0x18009cc00  mov     r9d, ebx; int
0x18009cc03  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cc0a  mov     r8d, edi; int
0x18009cc0d  mov     rcx, rax; this
0x18009cc10  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009cc15  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009cc1c  jb      loc_18009CB44
0x18009cc22  mov     edx, 141h
0x18009cc27  jmp     loc_18009CB26
0x18009cc2c  mov     ecx, [rsi+558h]
0x18009cc32  add     ecx, dword ptr [rbp+var_20]
0x18009cc35  mov     [r13+0], ecx
0x18009cc39  jmp     loc_18009CB44
0x18009cc3e  mov     rdx, rdi; struct IMFMediaBuffer *
0x18009cc41  lea     rcx, [rbp+var_48]; this
0x18009cc45  call    ??0CMFBufferWrapper@MFBUFFER@@QEAA@PEAUIMFMediaBuffer@@@Z; MFBUFFER::CMFBufferWrapper::CMFBufferWrapper(IMFMediaBuffer *)
0x18009cc4a  mov     edi, 0D48h
0x18009cc4f  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cc56  mov     r8d, edi; int
0x18009cc59  lea     rcx, [rbp+var_50]; this
0x18009cc5d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009cc62  xor     r8d, r8d; unsigned int *
0x18009cc65  lea     rdx, [rbp+Size]; struct MFBUFFER::CBuffer *
0x18009cc69  lea     rcx, [rbp+var_48]; this
0x18009cc6d  call    ?Lock@CMFBufferWrapper@MFBUFFER@@QEAAJPEAVCBuffer@2@PEAK@Z; MFBUFFER::CMFBufferWrapper::Lock(MFBUFFER::CBuffer *,ulong *)
0x18009cc72  mov     ebx, eax
0x18009cc74  test    eax, eax
0x18009cc76  jns     loc_18009CD38
0x18009cc7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cc83  test    rcx, rcx
0x18009cc86  jnz     short loc_18009CCC9
0x18009cc88  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009cc8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cc95  mov     rcx, rax
0x18009cc98  test    rax, rax
0x18009cc9b  jz      short loc_18009CCBB
0x18009cc9d  mov     rax, [rax]
0x18009cca0  mov     edx, 7F0h
0x18009cca5  mov     rax, [rax+8]
0x18009cca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ccae  test    eax, eax
0x18009ccb0  jz      short loc_18009CCBB
0x18009ccb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ccb9  jmp     short loc_18009CCC9
0x18009ccbb  lea     rcx, qword_1801B07E0; this
0x18009ccc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ccc9  cmp     [rcx+8], r12b
0x18009cccd  jz      short loc_18009CCF1
0x18009cccf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009ccd4  cmp     [rax+7CCh], ebx
0x18009ccda  jz      short loc_18009CCF1
0x18009ccdc  mov     r9d, ebx; int
0x18009ccdf  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cce6  mov     r8d, edi; int
0x18009cce9  mov     rcx, rax; this
0x18009ccec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009ccf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009ccf8  jb      short loc_18009CD1D
0x18009ccfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009cd01  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18009cd08  mov     edx, 142h
0x18009cd0d  mov     dword ptr [rsp+80h+var_60], ebx
0x18009cd11  mov     r9, rsi
0x18009cd14  mov     rcx, [rcx+10h]
0x18009cd18  call    WPP_SF_qD
0x18009cd1d  lea     rcx, [rbp+var_50]; this
0x18009cd21  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18009cd26  lea     rcx, [rbp+var_48]; this
0x18009cd2a  call    ??1CMFBufferWrapper@MFBUFFER@@QEAA@XZ; MFBUFFER::CMFBufferWrapper::~CMFBufferWrapper(void)
0x18009cd2f  mov     r12, [rbp+var_30]
0x18009cd33  jmp     loc_18009CF44
0x18009cd38  mov     rdi, [rbp+Size]
0x18009cd3c  xor     edx, edx; Val
0x18009cd3e  mov     r12, [rbp+var_30]
0x18009cd42  mov     r8, rdi; Size
0x18009cd45  mov     rcx, r12; void *
0x18009cd48  call    memset_0
0x18009cd4d  mov     ecx, [rsi+558h]
0x18009cd53  lea     r8, [rbp+var_20]; unsigned __int64 *
0x18009cd57  cmp     rdi, rcx
0x18009cd5a  jnb     loc_18009CE32
0x18009cd60  mov     rcx, [r14]; this
0x18009cd63  xor     edx, edx; struct MFBUFFER::CBuffer *
0x18009cd65  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x18009cd6a  mov     ebx, eax
0x18009cd6c  test    eax, eax
0x18009cd6e  jns     loc_18009CE22
0x18009cd74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cd7b  test    rcx, rcx
0x18009cd7e  jnz     short loc_18009CDC1
0x18009cd80  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009cd86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cd8d  mov     rcx, rax
0x18009cd90  test    rax, rax
0x18009cd93  jz      short loc_18009CDB3
0x18009cd95  mov     rax, [rax]
0x18009cd98  mov     edx, 7F0h
0x18009cd9d  mov     rax, [rax+8]
0x18009cda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cda6  test    eax, eax
0x18009cda8  jz      short loc_18009CDB3
0x18009cdaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cdb1  jmp     short loc_18009CDC1
0x18009cdb3  lea     rcx, qword_1801B07E0; this
0x18009cdba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cdc1  cmp     byte ptr [rcx+8], 0
0x18009cdc5  jz      short loc_18009CDEC
0x18009cdc7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009cdcc  cmp     [rax+7CCh], ebx
0x18009cdd2  jz      short loc_18009CDEC
0x18009cdd4  mov     r9d, ebx; int
0x18009cdd7  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009cdde  mov     r8d, 0D4Eh; int
0x18009cde4  mov     rcx, rax; this
0x18009cde7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009cdec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009cdf3  jb      loc_18009CF32
0x18009cdf9  lea     r9, [r15-30h]
0x18009cdfd  mov     edx, 143h
0x18009ce02  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ce09  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x18009ce10  mov     dword ptr [rsp+80h+var_60], ebx
0x18009ce14  mov     rcx, [rcx+10h]
0x18009ce18  call    WPP_SF_qD
0x18009ce1d  jmp     loc_18009CF32
0x18009ce22  mov     ecx, [rsi+558h]
0x18009ce28  mov     ebx, 0C00D36B1h
0x18009ce2d  jmp     loc_18009CF2B
0x18009ce32  mov     rax, rdi
0x18009ce35  mov     [rbp+var_10], r12
0x18009ce39  sub     rax, rcx
0x18009ce3c  lea     rdx, [rbp+var_18]; struct MFBUFFER::CBuffer *
0x18009ce40  mov     rcx, [r14]; this
0x18009ce43  cmp     rax, rdi
0x18009ce46  cmova   rax, rdi
0x18009ce4a  mov     [rbp+var_18], rax
0x18009ce4e  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x18009ce53  mov     ebx, eax
0x18009ce55  cmp     eax, 0C00D36B1h
0x18009ce5a  jz      loc_18009CF24
0x18009ce60  test    eax, eax
0x18009ce62  jns     loc_18009CEF6
0x18009ce68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ce6f  test    rcx, rcx
0x18009ce72  jnz     short loc_18009CEB5
0x18009ce74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009ce7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ce81  mov     rcx, rax
0x18009ce84  test    rax, rax
0x18009ce87  jz      short loc_18009CEA7
0x18009ce89  mov     rax, [rax]
0x18009ce8c  mov     edx, 7F0h
0x18009ce91  mov     rax, [rax+8]
0x18009ce95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce9a  test    eax, eax
0x18009ce9c  jz      short loc_18009CEA7
0x18009ce9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009cea5  jmp     short loc_18009CEB5
0x18009cea7  lea     rcx, qword_1801B07E0; this
0x18009ceae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009ceb5  cmp     byte ptr [rcx+8], 0
0x18009ceb9  jz      short loc_18009CEE0
0x18009cebb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009cec0  cmp     [rax+7CCh], ebx
0x18009cec6  jz      short loc_18009CEE0
0x18009cec8  mov     r9d, ebx; int
0x18009cecb  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x18009ced2  mov     r8d, 0D5Ch; int
0x18009ced8  mov     rcx, rax; this
0x18009cedb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009cee0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009cee7  jb      short loc_18009CF32
0x18009cee9  mov     edx, 144h
  ... truncated ...
```
