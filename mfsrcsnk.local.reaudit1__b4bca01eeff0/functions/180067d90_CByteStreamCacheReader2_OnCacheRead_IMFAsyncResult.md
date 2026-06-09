# CByteStreamCacheReader2::OnCacheRead(IMFAsyncResult *)

- ea: `0x180067d90`
- end: `0x18006856e`
- name: `?OnCacheRead@CByteStreamCacheReader2@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `2014`
- prototype: `void __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180171480`

## callees

- `0x180005cf4`
- `0x180008890`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800527cc`
- `0x180052a30`
- `0x180067d90`
- `0x180075cb8`
- `0x180075e94`
- `0x180077708`
- `0x180079680`
- `0x1800b8958`
- `0x1800c0990`
- `0x180121750`
- `0x18013fe10`
- `0x1801488b0`
- `0x1801714a0`
- `0x18017188c`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068540`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068540`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067df9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180067df9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068178`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068223`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006836e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006845e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067efc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800680ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068178`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180068223`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800682ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006836e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006845e`

## string_xrefs

- `0x180067dad`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180067ea8`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180067f59`: `CByteStreamCacheReader2::OnCacheRead`
- `0x18006812b`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800681d5`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180068280`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180068327`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800683cb`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800684bb`: `CByteStreamCacheReader2::OnCacheRead`

## pseudocode

```c
void __fastcall CByteStreamCacheReader2::OnCacheRead(CByteStreamCacheReader2 *this, struct IMFAsyncResult *a2)
{
  _DWORD *v4; // rsi
  int v5; // ebx
  _QWORD *v6; // r14
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  unsigned __int64 v14; // rbx
  char v15; // al
  __int64 v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rax
  int v42; // edx
  unsigned __int64 v43; // [rsp+70h] [rbp+40h] BYREF
  unsigned int v44; // [rsp+78h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v43, "CByteStreamCacheReader2::OnCacheRead", 748);
  if ( g_wppLevels >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
  v44 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 27) = 0;
  v4 = (_DWORD *)((__int64 (__fastcall *)(struct IMFAsyncResult *))a2->lpVtbl->GetStateNoAddRef)(a2);
  v5 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAsyncResult *, unsigned int *))(**((_QWORD **)this + 7) + 88LL))(
         *((_QWORD *)this + 7),
         a2,
         &v44);
  v6 = v4 + 4;
  if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 17), 88, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, *v6);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 32LL))(*v6);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v6 + 48LL))(*v6, v44);
    if ( v5 >= 0 )
    {
      v4[8] = v44;
      if ( v44 < *((_DWORD *)this + 16) )
      {
        if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
          WPP_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            91,
            &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
            this,
            v44,
            *((_DWORD *)this + 16));
        v43 = 0;
        if ( (int)CByteStreamCacheReader2::_GetByteStreamLength(this, &v43) >= 0 )
        {
          v14 = v43;
          if ( *((_QWORD *)this + 10) > v43
            && v43 + *((unsigned int *)this + 16) - (unsigned __int64)v44 == *((_QWORD *)this + 10) )
          {
            if ( (unsigned __int8)byte_1801BA10B >= 0x20u )
              WPP_SF_qI(
                *((_QWORD *)WPP_GLOBAL_Control + 17),
                92,
                &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
                this,
                v43);
            CByteStreamCacheReader2::_SetCurrentPosition(this, v14);
          }
        }
      }
      if ( v4[9] )
      {
        LODWORD(v43) = 0;
        v15 = byte_1801BA10B;
        if ( (unsigned __int8)byte_1801BA10B >= 8u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 93, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
          v15 = byte_1801BA10B;
        }
        v16 = *((_QWORD *)this + 12);
        if ( !v16 || *(_DWORD *)(v16 + 124) )
        {
          v5 = CByteStreamCacheReader2::_AddToCache(this, (struct CByteStreamCacheItem *)v4);
          if ( v5 >= 0 )
          {
            v5 = CByteStreamCacheReader2::_FillPendingCacheRead(this, (int *)&v43);
            if ( v5 >= 0 )
            {
              v5 = CByteStreamCacheReader2::_BeginCacheEnabledRead(this);
              if ( v5 >= 0 )
                goto LABEL_117;
              v30 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                CallStackTracing::s_wpInstance = v31;
                if ( v31
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                {
                  v30 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v30 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v30 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "CByteStreamCacheReader2::OnCacheRead", 821, v5);
              }
              if ( !g_wppLevels )
                goto LABEL_110;
              v9 = 98;
              goto LABEL_109;
            }
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)v28 + 499) != v5 )
                CallStackContext::TraceFailure(v28, "CByteStreamCacheReader2::OnCacheRead", 820, v5);
            }
            if ( g_wppLevels )
            {
              v9 = 97;
              goto LABEL_109;
            }
          }
          else
          {
            v22 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
              {
                v22 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v22 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v22 + 8) )
            {
              v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v24 + 499) != v5 )
                CallStackContext::TraceFailure(v24, "CByteStreamCacheReader2::OnCacheRead", 819, v5);
            }
            if ( g_wppLevels )
            {
              v9 = 96;
              goto LABEL_109;
            }
          }
        }
        else
        {
          if ( (unsigned __int8)v15 >= 4u )
            WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 94, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
          v5 = CByteStreamCacheReader2::_BeginCacheItemRead(
                 (DWORD *)this,
                 *(_QWORD *)(*((_QWORD *)this + 12) + 112LL),
                 *(_DWORD *)(*((_QWORD *)this + 12) + 124LL));
          if ( v5 >= 0 )
            goto LABEL_117;
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
            CallStackTracing::s_wpInstance = v19;
            if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
            {
              v18 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v18 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v18 + 8) )
          {
            v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
            if ( *((_DWORD *)v20 + 499) != v5 )
              CallStackContext::TraceFailure(v20, "CByteStreamCacheReader2::OnCacheRead", 815, v5);
          }
          if ( g_wppLevels )
          {
            v9 = 95;
            goto LABEL_109;
          }
        }
      }
      else
      {
        if ( *((_QWORD *)this + 12) )
        {
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 8LL))(v4);
          v36 = *(_QWORD *)(*((_QWORD *)this + 12) + 104LL);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          *(_QWORD *)(*((_QWORD *)this + 12) + 104LL) = v4;
          CByteStreamCacheReader2::_TracePendingCacheRead(this);
          if ( !*((_DWORD *)this + 29)
            || (v5 = CByteStreamCacheReader2::_SetCurrentPosition(this, *((_QWORD *)this + 10) + (unsigned int)v4[8]),
                v5 >= 0) )
          {
            if ( (unsigned __int8)byte_1801BA10B >= 8u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 17),
                101,
                &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids,
                this);
            v42 = 0;
            goto LABEL_116;
          }
          v38 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)v40 + 499) != v5 )
              CallStackContext::TraceFailure(v40, "CByteStreamCacheReader2::OnCacheRead", 836, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_110;
          v9 = 100;
          goto LABEL_109;
        }
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        v5 = -2147418113;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != -2147418113 )
            CallStackContext::TraceFailure(v35, "CByteStreamCacheReader2::OnCacheRead", 825, -2147418113);
        }
        if ( g_wppLevels )
        {
          v9 = 99;
          goto LABEL_109;
        }
      }
    }
    else
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != v5 )
          CallStackContext::TraceFailure(v13, "CByteStreamCacheReader2::OnCacheRead", 777, v5);
      }
      if ( g_wppLevels )
      {
        v9 = 90;
        goto LABEL_109;
      }
    }
  }
  else
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v8 + 499) != v5 )
        CallStackContext::TraceFailure(v8, "CByteStreamCacheReader2::OnCacheRead", 775, v5);
    }
    if ( g_wppLevels )
    {
      v9 = 89;
LABEL_109:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this, v5);
    }
  }
LABEL_110:
  v41 = *((_QWORD *)this + 12);
  if ( v41 && !*(_DWORD *)(v41 + 120) )
  {
    v42 = v5;
LABEL_116:
    CByteStreamCacheReader2::_CompletePendingRead(this, v42);
  }
LABEL_117:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v43);
}

```

## disassembly

```asm
0x180067d90  mov     [rsp-38h+arg_10], rbx
0x180067d95  push    rbp
0x180067d96  push    rsi
0x180067d97  push    rdi
0x180067d98  push    r12
0x180067d9a  push    r13
0x180067d9c  push    r14
0x180067d9e  push    r15
0x180067da0  mov     rbp, rsp
0x180067da3  sub     rsp, 30h
0x180067da7  mov     rbx, rdx
0x180067daa  mov     rdi, rcx
0x180067dad  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067db4  mov     r8d, 2ECh; int
0x180067dba  lea     rcx, [rbp+arg_0]; this
0x180067dbe  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180067dc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180067dca  lea     r13, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x180067dd1  jb      short loc_180067DEE
0x180067dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180067dda  mov     edx, 57h ; 'W'
0x180067ddf  mov     r9, rdi
0x180067de2  mov     r8, r13
0x180067de5  mov     rcx, [rcx+10h]
0x180067de9  call    WPP_SF_q
0x180067dee  xor     r12d, r12d
0x180067df1  lea     rcx, [rdi+10h]; lpCriticalSection
0x180067df5  mov     [rbp+arg_8], r12d
0x180067df9  call    cs:__imp_EnterCriticalSection
0x180067e00  nop     dword ptr [rax+rax+00h]
0x180067e05  mov     [rdi+6Ch], r12d
0x180067e09  mov     rcx, rbx
0x180067e0c  mov     rax, [rbx]
0x180067e0f  mov     rax, [rax+38h]
0x180067e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e18  mov     rcx, [rdi+38h]
0x180067e1c  lea     r8, [rbp+arg_8]
0x180067e20  mov     rsi, rax
0x180067e23  mov     rdx, [rcx]
0x180067e26  mov     rax, [rdx+58h]
0x180067e2a  mov     rdx, rbx
0x180067e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e32  mov     ebx, eax
0x180067e34  cmp     cs:byte_1801BA10B, 20h ; ' '
0x180067e3b  lea     r14, [rsi+10h]
0x180067e3f  jb      short loc_180067E67
0x180067e41  mov     rcx, [r14]
0x180067e44  lea     edx, [r12+58h]
0x180067e49  mov     [rsp+30h+var_10], rcx
0x180067e4e  mov     r9, rdi
0x180067e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180067e58  mov     r8, r13
0x180067e5b  mov     rcx, [rcx+88h]
0x180067e62  call    WPP_SF_qq
0x180067e67  mov     rcx, [r14]
0x180067e6a  mov     rax, [rcx]
0x180067e6d  mov     rax, [rax+20h]
0x180067e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e76  test    ebx, ebx
0x180067e78  jns     short loc_180067ED4
0x180067e7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067e81  test    rcx, rcx
0x180067e84  jnz     short loc_180067E92
0x180067e86  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180067e8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180067e92  cmp     [rcx+8], r12b
0x180067e96  jz      short loc_180067EBD
0x180067e98  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067e9d  cmp     [rax+7CCh], ebx
0x180067ea3  jz      short loc_180067EBD
0x180067ea5  mov     r9d, ebx; int
0x180067ea8  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067eaf  mov     r8d, 307h; int
0x180067eb5  mov     rcx, rax; this
0x180067eb8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067ebd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067ec4  jb      loc_1800684F8
0x180067eca  mov     edx, 59h ; 'Y'
0x180067ecf  jmp     loc_1800684DE
0x180067ed4  mov     rcx, [r14]
0x180067ed7  mov     edx, [rbp+arg_8]
0x180067eda  mov     rax, [rcx]
0x180067edd  mov     rax, [rax+30h]
0x180067ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ee6  mov     ebx, eax
0x180067ee8  test    eax, eax
0x180067eea  jns     loc_180067F85
0x180067ef0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ef7  test    rcx, rcx
0x180067efa  jnz     short loc_180067F43
0x180067efc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067f03  nop     dword ptr [rax+rax+00h]
0x180067f08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f0f  mov     rcx, rax
0x180067f12  test    rax, rax
0x180067f15  jz      short loc_180067F35
0x180067f17  mov     rax, [rax]
0x180067f1a  mov     edx, 7F0h
0x180067f1f  mov     rax, [rax+8]
0x180067f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067f28  test    eax, eax
0x180067f2a  jz      short loc_180067F35
0x180067f2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f33  jmp     short loc_180067F43
0x180067f35  lea     rcx, qword_1801B97E0; this
0x180067f3c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067f43  cmp     [rcx+8], r12b
0x180067f47  jz      short loc_180067F6E
0x180067f49  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067f4e  cmp     [rax+7CCh], ebx
0x180067f54  jz      short loc_180067F6E
0x180067f56  mov     r9d, ebx; int
0x180067f59  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067f60  mov     r8d, 309h; int
0x180067f66  mov     rcx, rax; this
0x180067f69  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067f6e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067f75  jb      loc_1800684F8
0x180067f7b  mov     edx, 5Ah ; 'Z'
0x180067f80  jmp     loc_1800684DE
0x180067f85  mov     eax, [rbp+arg_8]
0x180067f88  mov     [rsi+20h], eax
0x180067f8b  mov     eax, [rdi+40h]
0x180067f8e  mov     ecx, [rbp+arg_8]
0x180067f91  cmp     ecx, eax
0x180067f93  jnb     loc_18006802F
0x180067f99  cmp     cs:byte_1801BA10B, 20h ; ' '
0x180067fa0  jb      short loc_180067FC8
0x180067fa2  mov     [rsp+30h+var_8], eax
0x180067fa6  mov     edx, 5Bh ; '['
0x180067fab  mov     dword ptr [rsp+30h+var_10], ecx
0x180067faf  mov     r9, rdi
0x180067fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180067fb9  mov     r8, r13
0x180067fbc  mov     rcx, [rcx+88h]
0x180067fc3  call    WPP_SF_qDD
0x180067fc8  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x180067fcc  mov     [rbp+arg_0], r12
0x180067fd0  mov     rcx, rdi; this
0x180067fd3  call    ?_GetByteStreamLength@CByteStreamCacheReader2@@IEAAJPEA_K@Z; CByteStreamCacheReader2::_GetByteStreamLength(unsigned __int64 *)
0x180067fd8  test    eax, eax
0x180067fda  js      short loc_18006802F
0x180067fdc  mov     rbx, [rbp+arg_0]
0x180067fe0  cmp     [rdi+50h], rbx
0x180067fe4  jbe     short loc_18006802F
0x180067fe6  mov     ecx, [rdi+40h]
0x180067fe9  mov     eax, [rbp+arg_8]
0x180067fec  sub     rcx, rax
0x180067fef  add     rcx, rbx
0x180067ff2  cmp     rcx, [rdi+50h]
0x180067ff6  jnz     short loc_18006802F
0x180067ff8  cmp     cs:byte_1801BA10B, 20h ; ' '
0x180067fff  jb      short loc_180068024
0x180068001  mov     rcx, cs:WPP_GLOBAL_Control
0x180068008  mov     edx, 5Ch ; '\'
0x18006800d  mov     r9, rdi
0x180068010  mov     [rsp+30h+var_10], rbx
0x180068015  mov     r8, r13
0x180068018  mov     rcx, [rcx+88h]
0x18006801f  call    WPP_SF_qI
0x180068024  mov     rdx, rbx; unsigned __int64
0x180068027  mov     rcx, rdi; this
0x18006802a  call    ?_SetCurrentPosition@CByteStreamCacheReader2@@IEAAJ_K@Z; CByteStreamCacheReader2::_SetCurrentPosition(unsigned __int64)
0x18006802f  cmp     [rsi+24h], r12d
0x180068033  jz      loc_180068353
0x180068039  mov     dword ptr [rbp+arg_0], r12d
0x18006803d  mov     al, cs:byte_1801BA10B
0x180068043  cmp     al, 8
0x180068045  jb      short loc_18006806B
0x180068047  mov     rcx, cs:WPP_GLOBAL_Control
0x18006804e  mov     edx, 5Dh ; ']'
0x180068053  mov     r9, rdi
0x180068056  mov     r8, r13
0x180068059  mov     rcx, [rcx+88h]
0x180068060  call    WPP_SF_q
0x180068065  mov     al, cs:byte_1801BA10B
0x18006806b  mov     rcx, [rdi+60h]
0x18006806f  test    rcx, rcx
0x180068072  jz      loc_180068157
0x180068078  cmp     [rcx+7Ch], r12d
0x18006807c  jnz     loc_180068157
0x180068082  cmp     al, 4
0x180068084  jb      short loc_1800680A4
0x180068086  mov     rcx, cs:WPP_GLOBAL_Control
0x18006808d  mov     edx, 5Eh ; '^'
0x180068092  mov     r9, rdi
0x180068095  mov     r8, r13
0x180068098  mov     rcx, [rcx+88h]
0x18006809f  call    WPP_SF_q
0x1800680a4  mov     rdx, [rdi+60h]
0x1800680a8  mov     rcx, rdi; this
0x1800680ab  mov     r8d, [rdx+7Ch]; int
0x1800680af  mov     rdx, [rdx+70h]; unsigned __int64
0x1800680b3  call    ?_BeginCacheItemRead@CByteStreamCacheReader2@@IEAAJ_KH@Z; CByteStreamCacheReader2::_BeginCacheItemRead(unsigned __int64,int)
0x1800680b8  mov     ebx, eax
0x1800680ba  test    eax, eax
0x1800680bc  jns     loc_18006853C
0x1800680c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800680c9  test    rcx, rcx
0x1800680cc  jnz     short loc_180068115
0x1800680ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800680d5  nop     dword ptr [rax+rax+00h]
0x1800680da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800680e1  mov     rcx, rax
0x1800680e4  test    rax, rax
0x1800680e7  jz      short loc_180068107
0x1800680e9  mov     rax, [rax]
0x1800680ec  mov     edx, 7F0h
0x1800680f1  mov     rax, [rax+8]
0x1800680f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680fa  test    eax, eax
0x1800680fc  jz      short loc_180068107
0x1800680fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068105  jmp     short loc_180068115
0x180068107  lea     rcx, qword_1801B97E0; this
0x18006810e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068115  cmp     [rcx+8], r12b
0x180068119  jz      short loc_180068140
0x18006811b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068120  cmp     [rax+7CCh], ebx
0x180068126  jz      short loc_180068140
0x180068128  mov     r9d, ebx; int
0x18006812b  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180068132  mov     r8d, 32Fh; int
0x180068138  mov     rcx, rax; this
0x18006813b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068140  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068147  jb      loc_1800684F8
0x18006814d  mov     edx, 5Fh ; '_'
0x180068152  jmp     loc_1800684DE
0x180068157  mov     rdx, rsi; struct CByteStreamCacheItem *
0x18006815a  mov     rcx, rdi; this
0x18006815d  call    ?_AddToCache@CByteStreamCacheReader2@@IEAAJPEAVCByteStreamCacheItem@@@Z; CByteStreamCacheReader2::_AddToCache(CByteStreamCacheItem *)
0x180068162  mov     ebx, eax
0x180068164  test    eax, eax
0x180068166  jns     loc_180068201
0x18006816c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068173  test    rcx, rcx
0x180068176  jnz     short loc_1800681BF
0x180068178  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006817f  nop     dword ptr [rax+rax+00h]
0x180068184  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006818b  mov     rcx, rax
0x18006818e  test    rax, rax
0x180068191  jz      short loc_1800681B1
0x180068193  mov     rax, [rax]
0x180068196  mov     edx, 7F0h
0x18006819b  mov     rax, [rax+8]
0x18006819f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800681a4  test    eax, eax
0x1800681a6  jz      short loc_1800681B1
0x1800681a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800681af  jmp     short loc_1800681BF
0x1800681b1  lea     rcx, qword_1801B97E0; this
0x1800681b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800681bf  cmp     [rcx+8], r12b
0x1800681c3  jz      short loc_1800681EA
0x1800681c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800681ca  cmp     [rax+7CCh], ebx
0x1800681d0  jz      short loc_1800681EA
0x1800681d2  mov     r9d, ebx; int
0x1800681d5  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x1800681dc  mov     r8d, 333h; int
0x1800681e2  mov     rcx, rax; this
0x1800681e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800681ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800681f1  jb      loc_1800684F8
0x1800681f7  mov     edx, 60h ; '`'
0x1800681fc  jmp     loc_1800684DE
0x180068201  lea     rdx, [rbp+arg_0]; int *
0x180068205  mov     rcx, rdi; this
0x180068208  call    ?_FillPendingCacheRead@CByteStreamCacheReader2@@IEAAJPEAH@Z; CByteStreamCacheReader2::_FillPendingCacheRead(int *)
0x18006820d  mov     ebx, eax
0x18006820f  test    eax, eax
0x180068211  jns     loc_1800682AC
0x180068217  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006821e  test    rcx, rcx
0x180068221  jnz     short loc_18006826A
0x180068223  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006822a  nop     dword ptr [rax+rax+00h]
0x18006822f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068236  mov     rcx, rax
0x180068239  test    rax, rax
0x18006823c  jz      short loc_18006825C
0x18006823e  mov     rax, [rax]
0x180068241  mov     edx, 7F0h
0x180068246  mov     rax, [rax+8]
0x18006824a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006824f  test    eax, eax
0x180068251  jz      short loc_18006825C
0x180068253  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006825a  jmp     short loc_18006826A
0x18006825c  lea     rcx, qword_1801B97E0; this
0x180068263  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006826a  cmp     [rcx+8], r12b
0x18006826e  jz      short loc_180068295
0x180068270  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068275  cmp     [rax+7CCh], ebx
0x18006827b  jz      short loc_180068295
0x18006827d  mov     r9d, ebx; int
  ... truncated ...
```
