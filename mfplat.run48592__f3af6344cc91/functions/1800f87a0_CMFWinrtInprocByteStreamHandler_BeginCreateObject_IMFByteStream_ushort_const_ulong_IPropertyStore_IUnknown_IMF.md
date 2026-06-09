# CMFWinrtInprocByteStreamHandler::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x1800f87a0`
- end: `0x1800f8dbd`
- name: `?BeginCreateObject@CMFWinrtInprocByteStreamHandler@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU4@@Z`
- size: `1565`
- prototype: `__int64 __fastcall(CMFWinrtInprocByteStreamHandler *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800f87a0`
- `0x1800f8dc4`
- `0x1801200d0`
- `0x1801584a4`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f881d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f881d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8d92`

## string_xrefs

- `0x1800f8829`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f891b`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f89b7`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f8a6c`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f8b0d`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f8bac`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f8c5b`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`
- `0x1800f8d30`: `CMFWinrtInprocByteStreamHandler::BeginCreateObject`

## pseudocode

```c
__int64 __fastcall CMFWinrtInprocByteStreamHandler::BeginCreateObject(
        CMFWinrtInprocByteStreamHandler *this,
        struct IMFByteStream *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct IPropertyStore *a5,
        struct IUnknown **a6,
        struct IMFAsyncCallback *a7,
        struct IUnknown *a8)
{
  unsigned int v8; // ebx
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v13; // ebx
  _GUID *v14; // rax
  _GUID v15; // xmm0
  int Dll; // edi
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  struct CallStackContext *v19; // rax
  struct IMFByteStreamVtbl *lpVtbl; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rcx
  struct CallStackContext *v31; // rax
  CallStackScopeTrace v33; // [rsp+50h] [rbp-88h] BYREF
  int v34; // [rsp+54h] [rbp-84h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-80h]
  struct IUnknown *v36; // [rsp+60h] [rbp-78h]
  struct IPropertyStore *v37; // [rsp+68h] [rbp-70h]
  const unsigned __int16 *v38; // [rsp+70h] [rbp-68h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-60h]
  _BYTE v40[16]; // [rsp+80h] [rbp-58h] BYREF

  v8 = a4;
  v37 = a5;
  v36 = a8;
  v35 = a4;
  v38 = a3;
  if ( a6 )
    *a6 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 144);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  CallStackScopeTrace::CallStackScopeTrace(&v33, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 60);
  v11 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 27) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 296LL))(*((_QWORD *)this + 27));
    v14 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 27) + 280LL))(
                     *((_QWORD *)this + 27),
                     v40);
    v11 = CallStackTracing::s_wpInstance;
    v15 = *v14;
    ThreadRelativeContext->m_instanceId = v13;
    v8 = v35;
    ThreadRelativeContext->m_sessionId = v15;
  }
  if ( a2 )
  {
    if ( a7 )
    {
      lpVtbl = a2->lpVtbl;
      v34 = 0;
      Dll = ((__int64 (__fastcall *)(struct IMFByteStream *, int *))lpVtbl->GetCapabilities)(a2, &v34);
      if ( Dll >= 0 )
      {
        if ( (v34 & 1) == 0 )
        {
          v24 = CallStackTracing::s_wpInstance;
          Dll = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v24 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v24->m_fEnabled )
          {
            v25 = CallStackTracing::GetThreadRelativeContext(v24);
            if ( v25->m_result != -2147024809 )
              CallStackContext::TraceFailure(v25, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 68, -2147024809);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v18 = 19;
            goto LABEL_16;
          }
          goto LABEL_79;
        }
        if ( (v8 & 1) == 0 )
        {
          v26 = CallStackTracing::s_wpInstance;
          Dll = -2147024809;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v26 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v26 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v26->m_fEnabled )
          {
            v27 = CallStackTracing::GetThreadRelativeContext(v26);
            if ( v27->m_result != -2147024809 )
              CallStackContext::TraceFailure(v27, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 74, -2147024809);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v18 = 20;
            goto LABEL_16;
          }
          goto LABEL_79;
        }
        if ( *((_QWORD *)this + 28)
          || (Dll = CMFWinrtInprocByteStreamHandler::LoadDll((CMFWinrtInprocByteStreamHandler *)((char *)this - 8)),
              Dll >= 0) )
        {
          Dll = (*(__int64 (__fastcall **)(_QWORD, struct IMFByteStream *, const unsigned __int16 *, _QWORD, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  a2,
                  v38,
                  v8,
                  v37,
                  a6,
                  a7,
                  v36);
          if ( Dll >= 0 )
            goto LABEL_79;
          v30 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v30 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v30->m_fEnabled )
          {
            v31 = CallStackTracing::GetThreadRelativeContext(v30);
            if ( v31->m_result != Dll )
              CallStackContext::TraceFailure(v31, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 91, Dll);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_79;
          v23 = 22;
        }
        else
        {
          v28 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v28 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v28->m_fEnabled )
          {
            v29 = CallStackTracing::GetThreadRelativeContext(v28);
            if ( v29->m_result != Dll )
              CallStackContext::TraceFailure(v29, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 80, Dll);
          }
          if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
            goto LABEL_79;
          v23 = 21;
        }
      }
      else
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v21 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v21->m_fEnabled )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( v22->m_result != Dll )
            CallStackContext::TraceFailure(v22, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 65, Dll);
        }
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_79;
        v23 = 18;
      }
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        WPP_1c8048c6d41e326b3681b15ca355f2c0_Traceguids,
        (char *)this - 8,
        Dll);
      goto LABEL_79;
    }
    Dll = -2147024809;
    if ( !v11 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v11 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v11->m_fEnabled )
    {
      v19 = CallStackTracing::GetThreadRelativeContext(v11);
      if ( v19->m_result != -2147024809 )
        CallStackContext::TraceFailure(v19, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 61, -2147024809);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v18 = 17;
      goto LABEL_16;
    }
  }
  else
  {
    Dll = -2147024809;
    if ( !v11 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v11 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v11->m_fEnabled )
    {
      v17 = CallStackTracing::GetThreadRelativeContext(v11);
      if ( v17->m_result != -2147024809 )
        CallStackContext::TraceFailure(v17, "CMFWinrtInprocByteStreamHandler::BeginCreateObject", 60, -2147024809);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v18 = 16;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        WPP_1c8048c6d41e326b3681b15ca355f2c0_Traceguids,
        (char *)this - 8,
        -2147024809);
    }
  }
LABEL_79:
  CMFWinrtInprocByteStreamHandler::LogTelemetry((char *)this - 8, 0, (unsigned int)Dll);
  CallStackScopeTrace::~CallStackScopeTrace(&v33);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x1800f87a0  push    rbx
0x1800f87a2  push    rbp
0x1800f87a3  push    rdi
0x1800f87a4  push    r12
0x1800f87a6  push    r13
0x1800f87a8  push    r14
0x1800f87aa  push    r15
0x1800f87ac  sub     rsp, 0A0h
0x1800f87b3  mov     rax, cs:__security_cookie
0x1800f87ba  xor     rax, rsp
0x1800f87bd  mov     [rsp+0D8h+var_48], rax
0x1800f87c5  mov     rax, [rsp+0D8h+arg_20]
0x1800f87cd  mov     ebx, r9d
0x1800f87d0  mov     r12, [rsp+0D8h+arg_28]
0x1800f87d8  mov     r15, rdx
0x1800f87db  mov     r13, [rsp+0D8h+arg_30]
0x1800f87e3  mov     r14, rcx
0x1800f87e6  mov     [rsp+0D8h+var_70], rax
0x1800f87eb  mov     rax, [rsp+0D8h+arg_38]
0x1800f87f3  mov     [rsp+0D8h+var_78], rax
0x1800f87f8  mov     [rsp+0D8h+var_80], ebx
0x1800f87fc  mov     [rsp+0D8h+var_68], r8
0x1800f8801  test    r12, r12
0x1800f8804  jz      short loc_1800F880E
0x1800f8806  mov     qword ptr [r12], 0
0x1800f880e  lea     rax, [rcx+90h]
0x1800f8815  mov     rcx, rax; lpCriticalSection
0x1800f8818  mov     [rsp+0D8h+lpCriticalSection], rax
0x1800f881d  call    cs:__imp_EnterCriticalSection
0x1800f8823  mov     r8d, 3Ch ; '<'; int
0x1800f8829  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8830  lea     rcx, [rsp+0D8h+var_88]; this
0x1800f8835  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f883a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8841  cmp     byte ptr [rcx+8], 0
0x1800f8845  jz      short loc_1800F88AB
0x1800f8847  cmp     qword ptr [r14+0D8h], 0
0x1800f884f  jz      short loc_1800F88AB
0x1800f8851  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8856  mov     rcx, [r14+0D8h]
0x1800f885d  mov     rdi, rax
0x1800f8860  mov     rdx, [rcx]
0x1800f8863  mov     rax, [rdx+128h]
0x1800f886a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f886f  mov     rcx, [r14+0D8h]
0x1800f8876  mov     ebx, eax
0x1800f8878  mov     rdx, [rcx]
0x1800f887b  mov     rax, [rdx+118h]
0x1800f8882  lea     rdx, [rsp+0D8h+var_58]
0x1800f888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f888f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8896  movups  xmm0, xmmword ptr [rax]
0x1800f8899  mov     [rdi+7E0h], ebx
0x1800f889f  mov     ebx, [rsp+0D8h+var_80]
0x1800f88a3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800f88ab  lea     rbp, [r14-8]
0x1800f88af  test    r15, r15
0x1800f88b2  jnz     loc_1800F894B
0x1800f88b8  mov     ebx, 80070057h
0x1800f88bd  mov     edi, ebx
0x1800f88bf  test    rcx, rcx
0x1800f88c2  jnz     short loc_1800F8905
0x1800f88c4  mov     rax, cs:stru_1801FC290.__vftable
0x1800f88cb  lea     r8, stru_1801FC290
0x1800f88d2  mov     edx, 7F0h
0x1800f88d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f88de  mov     rcx, r8
0x1800f88e1  mov     rax, [rax+8]
0x1800f88e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f88ea  test    eax, eax
0x1800f88ec  jnz     short loc_1800F88FE
0x1800f88ee  lea     rcx, stru_1801F8A30
0x1800f88f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f88fc  jmp     short loc_1800F8905
0x1800f88fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8905  cmp     byte ptr [rcx+8], 0
0x1800f8909  jz      short loc_1800F8930
0x1800f890b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8910  cmp     [rax+7CCh], ebx
0x1800f8916  jz      short loc_1800F8930
0x1800f8918  mov     r9d, ebx; int
0x1800f891b  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8922  mov     r8d, 3Ch ; '<'; int
0x1800f8928  mov     rcx, rax; this
0x1800f892b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8930  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8937  jb      loc_1800F8D71
0x1800f893d  mov     edx, 10h
0x1800f8942  mov     dword ptr [rsp+0D8h+var_B8], ebx
0x1800f8946  jmp     loc_1800F8D57
0x1800f894b  test    r13, r13
0x1800f894e  jnz     loc_1800F89E3
0x1800f8954  mov     ebx, 80070057h
0x1800f8959  mov     edi, ebx
0x1800f895b  test    rcx, rcx
0x1800f895e  jnz     short loc_1800F89A1
0x1800f8960  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8967  lea     r8, stru_1801FC290
0x1800f896e  mov     edx, 7F0h
0x1800f8973  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f897a  mov     rcx, r8
0x1800f897d  mov     rax, [rax+8]
0x1800f8981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8986  test    eax, eax
0x1800f8988  jnz     short loc_1800F899A
0x1800f898a  lea     rcx, stru_1801F8A30
0x1800f8991  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8998  jmp     short loc_1800F89A1
0x1800f899a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f89a1  cmp     byte ptr [rcx+8], 0
0x1800f89a5  jz      short loc_1800F89CC
0x1800f89a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f89ac  cmp     [rax+7CCh], ebx
0x1800f89b2  jz      short loc_1800F89CC
0x1800f89b4  mov     r9d, ebx; int
0x1800f89b7  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f89be  mov     r8d, 3Dh ; '='; int
0x1800f89c4  mov     rcx, rax; this
0x1800f89c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f89cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f89d3  jb      loc_1800F8D71
0x1800f89d9  mov     edx, 11h
0x1800f89de  jmp     loc_1800F8942
0x1800f89e3  mov     rax, [r15]
0x1800f89e6  lea     rdx, [rsp+0D8h+var_84]
0x1800f89eb  mov     rcx, r15
0x1800f89ee  mov     [rsp+0D8h+var_84], 0
0x1800f89f6  mov     rax, [rax+18h]
0x1800f89fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f89ff  mov     edi, eax
0x1800f8a01  test    eax, eax
0x1800f8a03  jns     loc_1800F8A98
0x1800f8a09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8a10  test    rcx, rcx
0x1800f8a13  jnz     short loc_1800F8A56
0x1800f8a15  mov     rcx, cs:stru_1801FC290.__vftable
0x1800f8a1c  lea     r8, stru_1801FC290
0x1800f8a23  mov     edx, 7F0h
0x1800f8a28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8a2f  mov     rax, [rcx+8]
0x1800f8a33  mov     rcx, r8
0x1800f8a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8a3b  test    eax, eax
0x1800f8a3d  jnz     short loc_1800F8A4F
0x1800f8a3f  lea     rcx, stru_1801F8A30
0x1800f8a46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8a4d  jmp     short loc_1800F8A56
0x1800f8a4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8a56  cmp     byte ptr [rcx+8], 0
0x1800f8a5a  jz      short loc_1800F8A81
0x1800f8a5c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8a61  cmp     [rax+7CCh], edi
0x1800f8a67  jz      short loc_1800F8A81
0x1800f8a69  mov     r9d, edi; int
0x1800f8a6c  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8a73  mov     r8d, 41h ; 'A'; int
0x1800f8a79  mov     rcx, rax; this
0x1800f8a7c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8a81  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8a88  jb      loc_1800F8D71
0x1800f8a8e  mov     edx, 12h
0x1800f8a93  jmp     loc_1800F8D53
0x1800f8a98  test    byte ptr [rsp+0D8h+var_84], 1
0x1800f8a9d  jnz     loc_1800F8B39
0x1800f8aa3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8aaa  mov     ebx, 80070057h
0x1800f8aaf  mov     edi, ebx
0x1800f8ab1  test    rcx, rcx
0x1800f8ab4  jnz     short loc_1800F8AF7
0x1800f8ab6  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8abd  lea     r8, stru_1801FC290
0x1800f8ac4  mov     edx, 7F0h
0x1800f8ac9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8ad0  mov     rcx, r8
0x1800f8ad3  mov     rax, [rax+8]
0x1800f8ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8adc  test    eax, eax
0x1800f8ade  jnz     short loc_1800F8AF0
0x1800f8ae0  lea     rcx, stru_1801F8A30
0x1800f8ae7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8aee  jmp     short loc_1800F8AF7
0x1800f8af0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8af7  cmp     byte ptr [rcx+8], 0
0x1800f8afb  jz      short loc_1800F8B22
0x1800f8afd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8b02  cmp     [rax+7CCh], ebx
0x1800f8b08  jz      short loc_1800F8B22
0x1800f8b0a  mov     r9d, ebx; int
0x1800f8b0d  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8b14  mov     r8d, 44h ; 'D'; int
0x1800f8b1a  mov     rcx, rax; this
0x1800f8b1d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8b22  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8b29  jb      loc_1800F8D71
0x1800f8b2f  mov     edx, 13h
0x1800f8b34  jmp     loc_1800F8942
0x1800f8b39  test    bl, 1
0x1800f8b3c  jnz     loc_1800F8BD8
0x1800f8b42  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8b49  mov     ebx, 80070057h
0x1800f8b4e  mov     edi, ebx
0x1800f8b50  test    rcx, rcx
0x1800f8b53  jnz     short loc_1800F8B96
0x1800f8b55  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8b5c  lea     r8, stru_1801FC290
0x1800f8b63  mov     edx, 7F0h
0x1800f8b68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8b6f  mov     rcx, r8
0x1800f8b72  mov     rax, [rax+8]
0x1800f8b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8b7b  test    eax, eax
0x1800f8b7d  jnz     short loc_1800F8B8F
0x1800f8b7f  lea     rcx, stru_1801F8A30
0x1800f8b86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8b8d  jmp     short loc_1800F8B96
0x1800f8b8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8b96  cmp     byte ptr [rcx+8], 0
0x1800f8b9a  jz      short loc_1800F8BC1
0x1800f8b9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8ba1  cmp     [rax+7CCh], ebx
0x1800f8ba7  jz      short loc_1800F8BC1
0x1800f8ba9  mov     r9d, ebx; int
0x1800f8bac  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8bb3  mov     r8d, 4Ah ; 'J'; int
0x1800f8bb9  mov     rcx, rax; this
0x1800f8bbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8bc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8bc8  jb      loc_1800F8D71
0x1800f8bce  mov     edx, 14h
0x1800f8bd3  jmp     loc_1800F8942
0x1800f8bd8  cmp     qword ptr [rbp+0E8h], 0
0x1800f8be0  jnz     loc_1800F8C87
0x1800f8be6  mov     rcx, rbp; this
0x1800f8be9  call    ?LoadDll@CMFWinrtInprocByteStreamHandler@@AEAAJXZ; CMFWinrtInprocByteStreamHandler::LoadDll(void)
0x1800f8bee  mov     edi, eax
0x1800f8bf0  test    eax, eax
0x1800f8bf2  jns     loc_1800F8C87
0x1800f8bf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8bff  test    rcx, rcx
0x1800f8c02  jnz     short loc_1800F8C45
0x1800f8c04  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8c0b  lea     r8, stru_1801FC290
0x1800f8c12  mov     edx, 7F0h
0x1800f8c17  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8c1e  mov     rcx, r8
0x1800f8c21  mov     rax, [rax+8]
0x1800f8c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8c2a  test    eax, eax
0x1800f8c2c  jnz     short loc_1800F8C3E
0x1800f8c2e  lea     rcx, stru_1801F8A30
0x1800f8c35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8c3c  jmp     short loc_1800F8C45
0x1800f8c3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8c45  cmp     byte ptr [rcx+8], 0
0x1800f8c49  jz      short loc_1800F8C70
0x1800f8c4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8c50  cmp     [rax+7CCh], edi
0x1800f8c56  jz      short loc_1800F8C70
0x1800f8c58  mov     r9d, edi; int
0x1800f8c5b  lea     rdx, aCmfwinrtinproc_0; "CMFWinrtInprocByteStreamHandler::BeginC"...
0x1800f8c62  mov     r8d, 50h ; 'P'; int
0x1800f8c68  mov     rcx, rax; this
0x1800f8c6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8c70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8c77  jb      loc_1800F8D71
0x1800f8c7d  mov     edx, 15h
0x1800f8c82  jmp     loc_1800F8D53
0x1800f8c87  mov     rcx, [r14+0E0h]
0x1800f8c8e  mov     rdx, r15
0x1800f8c91  mov     r9, [rsp+0D8h+var_78]
0x1800f8c96  mov     r8, [rsp+0D8h+var_68]
0x1800f8c9b  mov     [rsp+0D8h+var_A0], r9
0x1800f8ca0  mov     r9, [rsp+0D8h+var_70]
0x1800f8ca5  mov     rax, [rcx]
0x1800f8ca8  mov     [rsp+0D8h+var_A8], r13
0x1800f8cad  mov     [rsp+0D8h+var_B0], r12
0x1800f8cb2  mov     [rsp+0D8h+var_B8], r9
0x1800f8cb7  mov     r9d, ebx
0x1800f8cba  mov     rax, [rax+18h]
0x1800f8cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8cc3  mov     edi, eax
0x1800f8cc5  test    eax, eax
0x1800f8cc7  jns     loc_1800F8D71
0x1800f8ccd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8cd4  test    rcx, rcx
0x1800f8cd7  jnz     short loc_1800F8D1A
0x1800f8cd9  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8ce0  lea     r8, stru_1801FC290
0x1800f8ce7  mov     edx, 7F0h
0x1800f8cec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8cf3  mov     rcx, r8
0x1800f8cf6  mov     rax, [rax+8]
0x1800f8cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8cff  test    eax, eax
0x1800f8d01  jnz     short loc_1800F8D13
0x1800f8d03  lea     rcx, stru_1801F8A30
0x1800f8d0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8d11  jmp     short loc_1800F8D1A
0x1800f8d13  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8d1a  cmp     byte ptr [rcx+8], 0
  ... truncated ...
```
