# CMFWinrtInprocByteStreamHandler::EndCreateObject(IMFAsyncResult *,MF_OBJECT_TYPE *,IUnknown * *)

- ea: `0x1800f8020`
- end: `0x1800f8798`
- name: `?EndCreateObject@CMFWinrtInprocByteStreamHandler@@UEAAJPEAUIMFAsyncResult@@PEAW4MF_OBJECT_TYPE@@PEAPEAUIUnknown@@@Z`
- size: `1912`
- prototype: `__int64 __fastcall(CMFWinrtInprocByteStreamHandler *__hidden this, struct IMFAsyncResult *, enum MF_OBJECT_TYPE *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004870`
- `0x180011454`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800a0a4c`
- `0x1800f8020`
- `0x1800f8dc4`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f807c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f807c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8758`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8758`

## string_xrefs

- `0x1800f809d`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f8184`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f823a`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f82d6`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f8373`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f8432`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f84d0`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f859b`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f8641`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`
- `0x1800f86f8`: `CMFWinrtInprocByteStreamHandler::EndCreateObject`

## pseudocode

```c
__int64 __fastcall CMFWinrtInprocByteStreamHandler::EndCreateObject(
        CMFWinrtInprocByteStreamHandler *this,
        struct IMFAsyncResult *a2,
        enum MF_OBJECT_TYPE *a3,
        struct IUnknown **a4)
{
  CallStackTracing *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v10; // ebx
  _GUID *v11; // rax
  _GUID v12; // xmm0
  int v13; // ebx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdi
  struct CallStackContext *v20; // rax
  __int64 (__fastcall *v21)(__int64, struct IMFAsyncResult *, enum MF_OBJECT_TYPE *, struct IUnknown **); // rbx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 (__fastcall *v26)(char *, void *, GUID *, __int64 *); // rbx
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackScopeTrace v34; // [rsp+30h] [rbp-48h] BYREF
  enum MF_OBJECT_TYPE v35; // [rsp+34h] [rbp-44h] BYREF
  struct IUnknown *v36; // [rsp+38h] [rbp-40h] BYREF
  __int64 v37; // [rsp+40h] [rbp-38h] BYREF
  __int64 v38; // [rsp+48h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-28h]
  _BYTE v40[16]; // [rsp+58h] [rbp-20h] BYREF

  v36 = 0;
  v37 = 0;
  v38 = 0;
  v35 = MF_OBJECT_INVALID;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 144);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  if ( a3 )
    *a3 = MF_OBJECT_INVALID;
  if ( a4 )
    *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v34, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 152);
  v8 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 27) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 296LL))(*((_QWORD *)this + 27));
    v11 = (_GUID *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 27) + 280LL))(
                     *((_QWORD *)this + 27),
                     v40);
    v8 = CallStackTracing::s_wpInstance;
    v12 = *v11;
    ThreadRelativeContext->m_instanceId = v10;
    ThreadRelativeContext->m_sessionId = v12;
  }
  if ( !a2 )
  {
    v13 = -2147024809;
    if ( !v8 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v14->m_result != -2147024809 )
        CallStackContext::TraceFailure(v14, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 152, -2147024809);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v15 = 30;
LABEL_18:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_1c8048c6d41e326b3681b15ca355f2c0_Traceguids,
        (char *)this - 8,
        v13);
      goto LABEL_102;
    }
    goto LABEL_102;
  }
  if ( !a3 )
  {
    v13 = -2147467261;
    if ( !v8 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v16->m_result != -2147467261 )
        CallStackContext::TraceFailure(v16, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 153, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_102;
    v17 = 31;
    goto LABEL_30;
  }
  if ( !a4 )
  {
    v13 = -2147467261;
    if ( !v8 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v18->m_result != -2147467261 )
        CallStackContext::TraceFailure(v18, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 154, -2147467261);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_102;
    v17 = 32;
LABEL_30:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_1c8048c6d41e326b3681b15ca355f2c0_Traceguids,
      (char *)this - 8,
      -2147467261);
    goto LABEL_102;
  }
  v19 = *((_QWORD *)this + 28);
  if ( v19 )
  {
    v21 = *(__int64 (__fastcall **)(__int64, struct IMFAsyncResult *, enum MF_OBJECT_TYPE *, struct IUnknown **))(*(_QWORD *)v19 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v13 = v21(v19, a2, &v35, &v36);
    if ( v13 >= 0 )
    {
      if ( v35 )
      {
        v24 = CallStackTracing::s_wpInstance;
        v13 = -2147418113;
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
          if ( v25->m_result != -2147418113 )
            CallStackContext::TraceFailure(v25, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 165, -2147418113);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v15 = 35;
          goto LABEL_18;
        }
      }
      else
      {
        v26 = *(__int64 (__fastcall **)(char *, void *, GUID *, __int64 *))(*((_QWORD *)this + 2) + 136LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        v13 = v26((char *)this + 16, &MF_INPROCDLL_LIFETIME_MANAGER, &GUID_00000000_0000_0000_c000_000000000046, &v37);
        if ( v13 >= 0 )
        {
          v13 = Microsoft::WRL::ComPtr<IUnknown>::As<IMFAttributes>(&v36, &v38);
          if ( v13 >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v38 + 216LL))(
                    v38,
                    &MF_INPROCDLL_LIFETIME_MANAGER,
                    v37);
            if ( v13 >= 0 )
            {
              *a3 = v35;
              *a4 = v36;
              v36 = 0;
              goto LABEL_102;
            }
            v31 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v31 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v31 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v31->m_fEnabled )
            {
              v32 = CallStackTracing::GetThreadRelativeContext(v31);
              if ( v32->m_result != v13 )
                CallStackContext::TraceFailure(v32, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 174, v13);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v15 = 38;
              goto LABEL_18;
            }
          }
          else
          {
            v29 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
              {
                v29 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &stru_1801F8A30;
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
              }
            }
            if ( v29->m_fEnabled )
            {
              v30 = CallStackTracing::GetThreadRelativeContext(v29);
              if ( v30->m_result != v13 )
                CallStackContext::TraceFailure(v30, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 173, v13);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
            {
              v15 = 37;
              goto LABEL_18;
            }
          }
        }
        else
        {
          v27 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v27 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v27->m_fEnabled )
          {
            v28 = CallStackTracing::GetThreadRelativeContext(v27);
            if ( v28->m_result != v13 )
              CallStackContext::TraceFailure(v28, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 172, v13);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v15 = 36;
            goto LABEL_18;
          }
        }
      }
    }
    else
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v22->m_fEnabled )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( v23->m_result != v13 )
          CallStackContext::TraceFailure(v23, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 161, v13);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v15 = 34;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v13 = -1072875854;
    if ( !v8 )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v8->m_fEnabled )
    {
      v20 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( v20->m_result != -1072875854 )
        CallStackContext::TraceFailure(v20, "CMFWinrtInprocByteStreamHandler::EndCreateObject", 157, -1072875854);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v15 = 33;
      goto LABEL_18;
    }
  }
LABEL_102:
  CMFWinrtInprocByteStreamHandler::LogTelemetry((char *)this - 8, 2, (unsigned int)v13);
  CallStackScopeTrace::~CallStackScopeTrace(&v34);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800f8020  push    rbp
0x1800f8022  push    rbx
0x1800f8023  push    rsi
0x1800f8024  push    rdi
0x1800f8025  push    r12
0x1800f8027  push    r13
0x1800f8029  push    r14
0x1800f802b  push    r15
0x1800f802d  mov     rbp, rsp
0x1800f8030  sub     rsp, 78h
0x1800f8034  mov     rax, cs:__security_cookie
0x1800f803b  xor     rax, rsp
0x1800f803e  mov     [rbp+var_10], rax
0x1800f8042  lea     rax, [rcx+90h]
0x1800f8049  mov     [rbp+var_40], 0
0x1800f8051  mov     r15, rcx
0x1800f8054  mov     [rbp+var_38], 0
0x1800f805c  mov     ebx, 2
0x1800f8061  mov     [rbp+var_30], 0
0x1800f8069  mov     rcx, rax; lpCriticalSection
0x1800f806c  mov     [rbp+var_44], ebx
0x1800f806f  mov     r14, r9
0x1800f8072  mov     [rbp+lpCriticalSection], rax
0x1800f8076  mov     r12, r8
0x1800f8079  mov     r13, rdx
0x1800f807c  call    cs:__imp_EnterCriticalSection
0x1800f8082  test    r12, r12
0x1800f8085  jz      short loc_1800F808B
0x1800f8087  mov     [r12], ebx
0x1800f808b  test    r14, r14
0x1800f808e  jz      short loc_1800F8097
0x1800f8090  mov     qword ptr [r14], 0
0x1800f8097  mov     r8d, 98h; int
0x1800f809d  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f80a4  lea     rcx, [rbp+var_48]; this
0x1800f80a8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f80ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f80b4  cmp     byte ptr [rcx+8], 0
0x1800f80b8  jz      short loc_1800F8116
0x1800f80ba  cmp     qword ptr [r15+0D8h], 0
0x1800f80c2  jz      short loc_1800F8116
0x1800f80c4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f80c9  mov     rcx, [r15+0D8h]
0x1800f80d0  mov     rdi, rax
0x1800f80d3  mov     rdx, [rcx]
0x1800f80d6  mov     rax, [rdx+128h]
0x1800f80dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80e2  mov     rcx, [r15+0D8h]
0x1800f80e9  mov     ebx, eax
0x1800f80eb  mov     rdx, [rcx]
0x1800f80ee  mov     rax, [rdx+118h]
0x1800f80f5  lea     rdx, [rbp+var_20]
0x1800f80f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f80fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8105  movups  xmm0, xmmword ptr [rax]
0x1800f8108  mov     [rdi+7E0h], ebx
0x1800f810e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800f8116  lea     rsi, [r15-8]
0x1800f811a  test    r13, r13
0x1800f811d  jnz     loc_1800F81CE
0x1800f8123  mov     ebx, 80070057h
0x1800f8128  test    rcx, rcx
0x1800f812b  jnz     short loc_1800F816E
0x1800f812d  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8134  lea     r8, stru_1801FC290
0x1800f813b  mov     edx, 7F0h
0x1800f8140  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8147  mov     rcx, r8
0x1800f814a  mov     rax, [rax+8]
0x1800f814e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8153  test    eax, eax
0x1800f8155  jnz     short loc_1800F8167
0x1800f8157  lea     rcx, stru_1801F8A30
0x1800f815e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8165  jmp     short loc_1800F816E
0x1800f8167  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f816e  cmp     byte ptr [rcx+8], 0
0x1800f8172  jz      short loc_1800F8199
0x1800f8174  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8179  cmp     [rax+7CCh], ebx
0x1800f817f  jz      short loc_1800F8199
0x1800f8181  mov     r9d, ebx; int
0x1800f8184  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f818b  mov     r8d, 98h; int
0x1800f8191  mov     rcx, rax; this
0x1800f8194  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8199  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f81a0  jb      loc_1800F8736
0x1800f81a6  mov     edx, 1Eh
0x1800f81ab  mov     [rsp+78h+var_58], ebx
0x1800f81af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f81b6  lea     r8, WPP_1c8048c6d41e326b3681b15ca355f2c0_Traceguids
0x1800f81bd  mov     r9, rsi
0x1800f81c0  mov     rcx, [rcx+10h]
0x1800f81c4  call    WPP_SF_qD
0x1800f81c9  jmp     loc_1800F8736
0x1800f81ce  test    r12, r12
0x1800f81d1  jnz     loc_1800F826A
0x1800f81d7  mov     edi, 80004003h
0x1800f81dc  mov     ebx, edi
0x1800f81de  test    rcx, rcx
0x1800f81e1  jnz     short loc_1800F8224
0x1800f81e3  mov     rax, cs:stru_1801FC290.__vftable
0x1800f81ea  lea     r8, stru_1801FC290
0x1800f81f1  mov     edx, 7F0h
0x1800f81f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f81fd  mov     rcx, r8
0x1800f8200  mov     rax, [rax+8]
0x1800f8204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8209  test    eax, eax
0x1800f820b  jnz     short loc_1800F821D
0x1800f820d  lea     rcx, stru_1801F8A30
0x1800f8214  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f821b  jmp     short loc_1800F8224
0x1800f821d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f8224  cmp     byte ptr [rcx+8], 0
0x1800f8228  jz      short loc_1800F824F
0x1800f822a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f822f  cmp     [rax+7CCh], edi
0x1800f8235  jz      short loc_1800F824F
0x1800f8237  mov     r9d, edi; int
0x1800f823a  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f8241  mov     r8d, 99h; int
0x1800f8247  mov     rcx, rax; this
0x1800f824a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f824f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f8256  jb      loc_1800F8736
0x1800f825c  mov     edx, 1Fh
0x1800f8261  mov     [rsp+78h+var_58], edi
0x1800f8265  jmp     loc_1800F81AF
0x1800f826a  test    r14, r14
0x1800f826d  jnz     loc_1800F8302
0x1800f8273  mov     edi, 80004003h
0x1800f8278  mov     ebx, edi
0x1800f827a  test    rcx, rcx
0x1800f827d  jnz     short loc_1800F82C0
0x1800f827f  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8286  lea     r8, stru_1801FC290
0x1800f828d  mov     edx, 7F0h
0x1800f8292  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8299  mov     rcx, r8
0x1800f829c  mov     rax, [rax+8]
0x1800f82a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f82a5  test    eax, eax
0x1800f82a7  jnz     short loc_1800F82B9
0x1800f82a9  lea     rcx, stru_1801F8A30
0x1800f82b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f82b7  jmp     short loc_1800F82C0
0x1800f82b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f82c0  cmp     byte ptr [rcx+8], 0
0x1800f82c4  jz      short loc_1800F82EB
0x1800f82c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f82cb  cmp     [rax+7CCh], edi
0x1800f82d1  jz      short loc_1800F82EB
0x1800f82d3  mov     r9d, edi; int
0x1800f82d6  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f82dd  mov     r8d, 9Ah; int
0x1800f82e3  mov     rcx, rax; this
0x1800f82e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f82eb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f82f2  jb      loc_1800F8736
0x1800f82f8  mov     edx, 20h ; ' '
0x1800f82fd  jmp     loc_1800F8261
0x1800f8302  mov     rdi, [rsi+0E8h]
0x1800f8309  test    rdi, rdi
0x1800f830c  jnz     loc_1800F839F
0x1800f8312  mov     ebx, 0C00D36B2h
0x1800f8317  test    rcx, rcx
0x1800f831a  jnz     short loc_1800F835D
0x1800f831c  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8323  lea     r8, stru_1801FC290
0x1800f832a  mov     edx, 7F0h
0x1800f832f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8336  mov     rcx, r8
0x1800f8339  mov     rax, [rax+8]
0x1800f833d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8342  test    eax, eax
0x1800f8344  jnz     short loc_1800F8356
0x1800f8346  lea     rcx, stru_1801F8A30
0x1800f834d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8354  jmp     short loc_1800F835D
0x1800f8356  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f835d  cmp     byte ptr [rcx+8], 0
0x1800f8361  jz      short loc_1800F8388
0x1800f8363  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8368  cmp     [rax+7CCh], ebx
0x1800f836e  jz      short loc_1800F8388
0x1800f8370  mov     r9d, ebx; int
0x1800f8373  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f837a  mov     r8d, 9Dh; int
0x1800f8380  mov     rcx, rax; this
0x1800f8383  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8388  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f838f  jb      loc_1800F8736
0x1800f8395  mov     edx, 21h ; '!'
0x1800f839a  jmp     loc_1800F81AB
0x1800f839f  mov     rax, [rdi]
0x1800f83a2  lea     rcx, [rbp+var_40]
0x1800f83a6  mov     rbx, [rax+20h]
0x1800f83aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f83af  lea     r9, [rbp+var_40]
0x1800f83b3  mov     rdx, r13
0x1800f83b6  lea     r8, [rbp+var_44]
0x1800f83ba  mov     rcx, rdi
0x1800f83bd  mov     rax, rbx
0x1800f83c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f83c5  mov     ebx, eax
0x1800f83c7  test    eax, eax
0x1800f83c9  jns     loc_1800F845E
0x1800f83cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f83d6  test    rcx, rcx
0x1800f83d9  jnz     short loc_1800F841C
0x1800f83db  mov     rcx, cs:stru_1801FC290.__vftable
0x1800f83e2  lea     r8, stru_1801FC290
0x1800f83e9  mov     edx, 7F0h
0x1800f83ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f83f5  mov     rax, [rcx+8]
0x1800f83f9  mov     rcx, r8
0x1800f83fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8401  test    eax, eax
0x1800f8403  jnz     short loc_1800F8415
0x1800f8405  lea     rcx, stru_1801F8A30
0x1800f840c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8413  jmp     short loc_1800F841C
0x1800f8415  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f841c  cmp     byte ptr [rcx+8], 0
0x1800f8420  jz      short loc_1800F8447
0x1800f8422  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f8427  cmp     [rax+7CCh], ebx
0x1800f842d  jz      short loc_1800F8447
0x1800f842f  mov     r9d, ebx; int
0x1800f8432  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f8439  mov     r8d, 0A1h; int
0x1800f843f  mov     rcx, rax; this
0x1800f8442  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f8447  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f844e  jb      loc_1800F8736
0x1800f8454  mov     edx, 22h ; '"'
0x1800f8459  jmp     loc_1800F81AB
0x1800f845e  cmp     [rbp+var_44], 0
0x1800f8462  jz      loc_1800F84FC
0x1800f8468  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f846f  mov     ebx, 8000FFFFh
0x1800f8474  test    rcx, rcx
0x1800f8477  jnz     short loc_1800F84BA
0x1800f8479  mov     rax, cs:stru_1801FC290.__vftable
0x1800f8480  lea     r8, stru_1801FC290
0x1800f8487  mov     edx, 7F0h
0x1800f848c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f8493  mov     rcx, r8
0x1800f8496  mov     rax, [rax+8]
0x1800f849a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f849f  test    eax, eax
0x1800f84a1  jnz     short loc_1800F84B3
0x1800f84a3  lea     rcx, stru_1801F8A30
0x1800f84aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f84b1  jmp     short loc_1800F84BA
0x1800f84b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f84ba  cmp     byte ptr [rcx+8], 0
0x1800f84be  jz      short loc_1800F84E5
0x1800f84c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f84c5  cmp     [rax+7CCh], ebx
0x1800f84cb  jz      short loc_1800F84E5
0x1800f84cd  mov     r9d, ebx; int
0x1800f84d0  lea     rdx, aCmfwinrtinproc_8; "CMFWinrtInprocByteStreamHandler::EndCre"...
0x1800f84d7  mov     r8d, 0A5h; int
0x1800f84dd  mov     rcx, rax; this
0x1800f84e0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f84e5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f84ec  jb      loc_1800F8736
0x1800f84f2  mov     edx, 23h ; '#'
0x1800f84f7  jmp     loc_1800F81AB
0x1800f84fc  mov     rax, [r15+10h]
0x1800f8500  lea     rcx, [rbp+var_38]
0x1800f8504  mov     rbx, [rax+88h]
0x1800f850b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f8510  lea     r9, [rbp+var_38]
0x1800f8514  mov     rax, rbx
0x1800f8517  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x1800f851e  lea     rdx, MF_INPROCDLL_LIFETIME_MANAGER
0x1800f8525  lea     rcx, [r15+10h]
0x1800f8529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f852e  mov     ebx, eax
0x1800f8530  test    eax, eax
0x1800f8532  jns     loc_1800F85C7
0x1800f8538  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f853f  test    rcx, rcx
0x1800f8542  jnz     short loc_1800F8585
0x1800f8544  mov     rax, cs:stru_1801FC290.__vftable
0x1800f854b  lea     r8, stru_1801FC290
0x1800f8552  mov     edx, 7F0h
0x1800f8557  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f855e  mov     rcx, r8
0x1800f8561  mov     rax, [rax+8]
0x1800f8565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f856a  test    eax, eax
0x1800f856c  jnz     short loc_1800F857E
0x1800f856e  lea     rcx, stru_1801F8A30
0x1800f8575  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f857c  jmp     short loc_1800F8585
  ... truncated ...
```
