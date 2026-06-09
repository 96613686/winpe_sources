# CMP3MediaSourcePlugin::GenerateHeader(IMFMediaBuffer *,ulong *)

- ea: `0x1800a1d10`
- end: `0x1800a2319`
- name: `?GenerateHeader@CMP3MediaSourcePlugin@@UEAAJPEAUIMFMediaBuffer@@PEAK@Z`
- size: `1545`
- prototype: `int(CMP3MediaSourcePlugin *__hidden this, struct IMFMediaBuffer *, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004f0f8`
- `0x180053e44`
- `0x180062abc`
- `0x180079680`
- `0x1800a1d10`
- `0x180110ed0`
- `0x180111960`
- `0x18015a310`
- `0x18016a6b0`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a22e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a22e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1d65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a1d65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1dd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a20b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a21b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1dd2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1fba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a20b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a21b2`

## string_xrefs

- `0x1800a1d8e`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a1e2f`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a1e9d`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a1f35`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a1f81`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a2017`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a2115`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a220f`: `CMP3MediaSourcePlugin::GenerateHeader`
- `0x1800a228e`: `CMP3MediaSourcePlugin::GenerateHeader`

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
          v12 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v17 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
              v37 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v27 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v21 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
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
0x1800a1d10  mov     [rsp-38h+arg_18], rbx
0x1800a1d15  push    rbp
0x1800a1d16  push    rsi
0x1800a1d17  push    rdi
0x1800a1d18  push    r12
0x1800a1d1a  push    r13
0x1800a1d1c  push    r14
0x1800a1d1e  push    r15
0x1800a1d20  mov     rbp, rsp
0x1800a1d23  sub     rsp, 80h
0x1800a1d2a  mov     rax, cs:__security_cookie
0x1800a1d31  xor     rax, rsp
0x1800a1d34  mov     [rbp+var_8], rax
0x1800a1d38  xor     ebx, ebx
0x1800a1d3a  lea     rax, [rcx+8]
0x1800a1d3e  mov     r15, rcx
0x1800a1d41  mov     [rbp+var_20], rbx
0x1800a1d45  mov     rcx, rax; lpCriticalSection
0x1800a1d48  mov     [rbp+var_18], rbx
0x1800a1d4c  mov     r13, r8
0x1800a1d4f  mov     [rbp+var_10], rbx
0x1800a1d53  mov     rdi, rdx
0x1800a1d56  mov     [rbp+Size], rbx
0x1800a1d5a  mov     r12d, ebx
0x1800a1d5d  mov     [rbp+var_30], rbx
0x1800a1d61  mov     [rbp+lpCriticalSection], rax
0x1800a1d65  call    cs:__imp_EnterCriticalSection
0x1800a1d6c  nop     dword ptr [rax+rax+00h]
0x1800a1d71  lea     rsi, [r15-30h]
0x1800a1d75  lea     r14, [r15+168h]
0x1800a1d7c  cmp     [rsi+578h], ebx
0x1800a1d82  jz      loc_1800A1E8F
0x1800a1d88  mov     r8d, 0D3Ah; int
0x1800a1d8e  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a1d95  lea     rcx, [rbp+var_50]; this
0x1800a1d99  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1d9e  mov     rdx, [r14]
0x1800a1da1  mov     rax, [rdx+10h]
0x1800a1da5  add     rdx, 10h
0x1800a1da9  movsxd  rcx, dword ptr [rax+8]
0x1800a1dad  add     rcx, rdx
0x1800a1db0  mov     rax, [rcx]
0x1800a1db3  mov     rax, [rax+10h]
0x1800a1db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1dbc  mov     ebx, eax
0x1800a1dbe  test    eax, eax
0x1800a1dc0  jns     loc_1800A1E7E
0x1800a1dc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1dcd  test    rcx, rcx
0x1800a1dd0  jnz     short loc_1800A1E19
0x1800a1dd2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1dd9  nop     dword ptr [rax+rax+00h]
0x1800a1dde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1de5  mov     rcx, rax
0x1800a1de8  test    rax, rax
0x1800a1deb  jz      short loc_1800A1E0B
0x1800a1ded  mov     rax, [rax]
0x1800a1df0  mov     edx, 7F0h
0x1800a1df5  mov     rax, [rax+8]
0x1800a1df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1dfe  test    eax, eax
0x1800a1e00  jz      short loc_1800A1E0B
0x1800a1e02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e09  jmp     short loc_1800A1E19
0x1800a1e0b  lea     rcx, qword_1801B97E0; this
0x1800a1e12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1e19  cmp     [rcx+8], r12b
0x1800a1e1d  jz      short loc_1800A1E44
0x1800a1e1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1e24  cmp     [rax+7CCh], ebx
0x1800a1e2a  jz      short loc_1800A1E44
0x1800a1e2c  mov     r9d, ebx; int
0x1800a1e2f  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a1e36  mov     r8d, 0D3Ah; int
0x1800a1e3c  mov     rcx, rax; this
0x1800a1e3f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1e44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1e4b  jb      short loc_1800A1E70
0x1800a1e4d  mov     edx, 140h
0x1800a1e52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1e59  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800a1e60  mov     r9, rsi
0x1800a1e63  mov     dword ptr [rsp+80h+var_60], ebx
0x1800a1e67  mov     rcx, [rcx+10h]
0x1800a1e6b  call    WPP_SF_qD
0x1800a1e70  lea     rcx, [rbp+var_50]; this
0x1800a1e74  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1e79  jmp     loc_1800A2288
0x1800a1e7e  xor     ebx, ebx
0x1800a1e80  lea     rcx, [rbp+var_50]; this
0x1800a1e84  mov     [rsi+578h], ebx
0x1800a1e8a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a1e8f  test    rdi, rdi
0x1800a1e92  jnz     loc_1800A1F70
0x1800a1e98  mov     edi, 0D40h
0x1800a1e9d  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a1ea4  mov     r8d, edi; int
0x1800a1ea7  lea     rcx, [rbp+var_50]; this
0x1800a1eab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1eb0  mov     rcx, [rsi+198h]; this
0x1800a1eb7  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800a1ebb  xor     edx, edx; struct MFBUFFER::CBuffer *
0x1800a1ebd  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x1800a1ec2  mov     ebx, eax
0x1800a1ec4  test    eax, eax
0x1800a1ec6  jns     loc_1800A1F5E
0x1800a1ecc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ed3  test    rcx, rcx
0x1800a1ed6  jnz     short loc_1800A1F1F
0x1800a1ed8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1edf  nop     dword ptr [rax+rax+00h]
0x1800a1ee4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1eeb  mov     rcx, rax
0x1800a1eee  test    rax, rax
0x1800a1ef1  jz      short loc_1800A1F11
0x1800a1ef3  mov     rax, [rax]
0x1800a1ef6  mov     edx, 7F0h
0x1800a1efb  mov     rax, [rax+8]
0x1800a1eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f04  test    eax, eax
0x1800a1f06  jz      short loc_1800A1F11
0x1800a1f08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f0f  jmp     short loc_1800A1F1F
0x1800a1f11  lea     rcx, qword_1801B97E0; this
0x1800a1f18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1f1f  cmp     [rcx+8], r12b
0x1800a1f23  jz      short loc_1800A1F47
0x1800a1f25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1f2a  cmp     [rax+7CCh], ebx
0x1800a1f30  jz      short loc_1800A1F47
0x1800a1f32  mov     r9d, ebx; int
0x1800a1f35  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a1f3c  mov     r8d, edi; int
0x1800a1f3f  mov     rcx, rax; this
0x1800a1f42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1f47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a1f4e  jb      loc_1800A1E70
0x1800a1f54  mov     edx, 141h
0x1800a1f59  jmp     loc_1800A1E52
0x1800a1f5e  mov     ecx, [rsi+558h]
0x1800a1f64  add     ecx, dword ptr [rbp+var_20]
0x1800a1f67  mov     [r13+0], ecx
0x1800a1f6b  jmp     loc_1800A1E70
0x1800a1f70  mov     rdx, rdi; struct IMFMediaBuffer *
0x1800a1f73  lea     rcx, [rbp+var_48]; this
0x1800a1f77  call    ??0CMFBufferWrapper@MFBUFFER@@QEAA@PEAUIMFMediaBuffer@@@Z; MFBUFFER::CMFBufferWrapper::CMFBufferWrapper(IMFMediaBuffer *)
0x1800a1f7c  mov     edi, 0D48h
0x1800a1f81  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a1f88  mov     r8d, edi; int
0x1800a1f8b  lea     rcx, [rbp+var_50]; this
0x1800a1f8f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a1f94  xor     r8d, r8d; unsigned int *
0x1800a1f97  lea     rdx, [rbp+Size]; struct MFBUFFER::CBuffer *
0x1800a1f9b  lea     rcx, [rbp+var_48]; this
0x1800a1f9f  call    ?Lock@CMFBufferWrapper@MFBUFFER@@QEAAJPEAVCBuffer@2@PEAK@Z; MFBUFFER::CMFBufferWrapper::Lock(MFBUFFER::CBuffer *,ulong *)
0x1800a1fa4  mov     ebx, eax
0x1800a1fa6  test    eax, eax
0x1800a1fa8  jns     loc_1800A2070
0x1800a1fae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1fb5  test    rcx, rcx
0x1800a1fb8  jnz     short loc_1800A2001
0x1800a1fba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1fc1  nop     dword ptr [rax+rax+00h]
0x1800a1fc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1fcd  mov     rcx, rax
0x1800a1fd0  test    rax, rax
0x1800a1fd3  jz      short loc_1800A1FF3
0x1800a1fd5  mov     rax, [rax]
0x1800a1fd8  mov     edx, 7F0h
0x1800a1fdd  mov     rax, [rax+8]
0x1800a1fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1fe6  test    eax, eax
0x1800a1fe8  jz      short loc_1800A1FF3
0x1800a1fea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ff1  jmp     short loc_1800A2001
0x1800a1ff3  lea     rcx, qword_1801B97E0; this
0x1800a1ffa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a2001  cmp     [rcx+8], r12b
0x1800a2005  jz      short loc_1800A2029
0x1800a2007  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a200c  cmp     [rax+7CCh], ebx
0x1800a2012  jz      short loc_1800A2029
0x1800a2014  mov     r9d, ebx; int
0x1800a2017  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a201e  mov     r8d, edi; int
0x1800a2021  mov     rcx, rax; this
0x1800a2024  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a2029  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a2030  jb      short loc_1800A2055
0x1800a2032  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2039  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800a2040  mov     edx, 142h
0x1800a2045  mov     dword ptr [rsp+80h+var_60], ebx
0x1800a2049  mov     r9, rsi
0x1800a204c  mov     rcx, [rcx+10h]
0x1800a2050  call    WPP_SF_qD
0x1800a2055  lea     rcx, [rbp+var_50]; this
0x1800a2059  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a205e  lea     rcx, [rbp+var_48]; this
0x1800a2062  call    ??1CMFBufferWrapper@MFBUFFER@@QEAA@XZ; MFBUFFER::CMFBufferWrapper::~CMFBufferWrapper(void)
0x1800a2067  mov     r12, [rbp+var_30]
0x1800a206b  jmp     loc_1800A2288
0x1800a2070  mov     rdi, [rbp+Size]
0x1800a2074  xor     edx, edx; Val
0x1800a2076  mov     r12, [rbp+var_30]
0x1800a207a  mov     r8, rdi; Size
0x1800a207d  mov     rcx, r12; void *
0x1800a2080  call    memset_0
0x1800a2085  mov     ecx, [rsi+558h]
0x1800a208b  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800a208f  cmp     rdi, rcx
0x1800a2092  jnb     loc_1800A2170
0x1800a2098  mov     rcx, [r14]; this
0x1800a209b  xor     edx, edx; struct MFBUFFER::CBuffer *
0x1800a209d  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x1800a20a2  mov     ebx, eax
0x1800a20a4  test    eax, eax
0x1800a20a6  jns     loc_1800A2160
0x1800a20ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a20b3  test    rcx, rcx
0x1800a20b6  jnz     short loc_1800A20FF
0x1800a20b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a20bf  nop     dword ptr [rax+rax+00h]
0x1800a20c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a20cb  mov     rcx, rax
0x1800a20ce  test    rax, rax
0x1800a20d1  jz      short loc_1800A20F1
0x1800a20d3  mov     rax, [rax]
0x1800a20d6  mov     edx, 7F0h
0x1800a20db  mov     rax, [rax+8]
0x1800a20df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a20e4  test    eax, eax
0x1800a20e6  jz      short loc_1800A20F1
0x1800a20e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a20ef  jmp     short loc_1800A20FF
0x1800a20f1  lea     rcx, qword_1801B97E0; this
0x1800a20f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a20ff  cmp     byte ptr [rcx+8], 0
0x1800a2103  jz      short loc_1800A212A
0x1800a2105  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a210a  cmp     [rax+7CCh], ebx
0x1800a2110  jz      short loc_1800A212A
0x1800a2112  mov     r9d, ebx; int
0x1800a2115  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
0x1800a211c  mov     r8d, 0D4Eh; int
0x1800a2122  mov     rcx, rax; this
0x1800a2125  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a212a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a2131  jb      loc_1800A2276
0x1800a2137  lea     r9, [r15-30h]
0x1800a213b  mov     edx, 143h
0x1800a2140  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2147  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800a214e  mov     dword ptr [rsp+80h+var_60], ebx
0x1800a2152  mov     rcx, [rcx+10h]
0x1800a2156  call    WPP_SF_qD
0x1800a215b  jmp     loc_1800A2276
0x1800a2160  mov     ecx, [rsi+558h]
0x1800a2166  mov     ebx, 0C00D36B1h
0x1800a216b  jmp     loc_1800A226F
0x1800a2170  mov     rax, rdi
0x1800a2173  mov     [rbp+var_10], r12
0x1800a2177  sub     rax, rcx
0x1800a217a  lea     rdx, [rbp+var_18]; struct MFBUFFER::CBuffer *
0x1800a217e  mov     rcx, [r14]; this
0x1800a2181  cmp     rax, rdi
0x1800a2184  cmova   rax, rdi
0x1800a2188  mov     [rbp+var_18], rax
0x1800a218c  call    ?SerializeHeader@CMP3Properties@@QEAAJPEAVCBuffer@MFBUFFER@@PEA_K@Z; CMP3Properties::SerializeHeader(MFBUFFER::CBuffer *,unsigned __int64 *)
0x1800a2191  mov     ebx, eax
0x1800a2193  cmp     eax, 0C00D36B1h
0x1800a2198  jz      loc_1800A2268
0x1800a219e  test    eax, eax
0x1800a21a0  jns     loc_1800A223A
0x1800a21a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a21ad  test    rcx, rcx
0x1800a21b0  jnz     short loc_1800A21F9
0x1800a21b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a21b9  nop     dword ptr [rax+rax+00h]
0x1800a21be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a21c5  mov     rcx, rax
0x1800a21c8  test    rax, rax
0x1800a21cb  jz      short loc_1800A21EB
0x1800a21cd  mov     rax, [rax]
0x1800a21d0  mov     edx, 7F0h
0x1800a21d5  mov     rax, [rax+8]
0x1800a21d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a21de  test    eax, eax
0x1800a21e0  jz      short loc_1800A21EB
0x1800a21e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a21e9  jmp     short loc_1800A21F9
0x1800a21eb  lea     rcx, qword_1801B97E0; this
0x1800a21f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a21f9  cmp     byte ptr [rcx+8], 0
0x1800a21fd  jz      short loc_1800A2224
0x1800a21ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a2204  cmp     [rax+7CCh], ebx
0x1800a220a  jz      short loc_1800A2224
0x1800a220c  mov     r9d, ebx; int
0x1800a220f  lea     rdx, aCmp3mediasourc_62; "CMP3MediaSourcePlugin::GenerateHeader"
  ... truncated ...
```
