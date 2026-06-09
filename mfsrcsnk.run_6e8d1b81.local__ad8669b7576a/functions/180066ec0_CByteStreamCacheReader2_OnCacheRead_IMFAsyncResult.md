# CByteStreamCacheReader2::OnCacheRead(IMFAsyncResult *)

- ea: `0x180066ec0`
- end: `0x180067667`
- name: `?OnCacheRead@CByteStreamCacheReader2@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `1959`
- prototype: `void __fastcall(CByteStreamCacheReader2 *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1801684f0`

## callees

- `0x180005eb8`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180030604`
- `0x1800308a0`
- `0x180066ec0`
- `0x180071a44`
- `0x180073b14`
- `0x180074160`
- `0x180074378`
- `0x1800b322c`
- `0x1800baefc`
- `0x18011b1e4`
- `0x180138540`
- `0x180140b84`
- `0x180168510`
- `0x1801688fc`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066f29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066f29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067026`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800671f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067296`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006733b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800673dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006747a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067564`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067026`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800671f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067296`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006733b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800673dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006747a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067564`

## string_xrefs

- `0x180066edd`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180066fd2`: `CByteStreamCacheReader2::OnCacheRead`
- `0x18006707d`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180067249`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800672ed`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180067392`: `CByteStreamCacheReader2::OnCacheRead`
- `0x180067433`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800674d1`: `CByteStreamCacheReader2::OnCacheRead`
- `0x1800675bb`: `CByteStreamCacheReader2::OnCacheRead`

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
  if ( (unsigned __int8)byte_1801B110B >= 0x20u )
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
        if ( (unsigned __int8)byte_1801B110B >= 0x20u )
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
            if ( (unsigned __int8)byte_1801B110B >= 0x20u )
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
        v15 = byte_1801B110B;
        if ( (unsigned __int8)byte_1801B110B >= 8u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 93, &WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids, this);
          v15 = byte_1801B110B;
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
                  v30 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v26 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v22 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v18 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            if ( (unsigned __int8)byte_1801B110B >= 8u )
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
              v38 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v33 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v11 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x180066ec0  mov     [rsp-38h+arg_10], rbx
0x180066ec5  push    rbp
0x180066ec6  push    rsi
0x180066ec7  push    rdi
0x180066ec8  push    r12
0x180066eca  push    r13
0x180066ecc  push    r14
0x180066ece  push    r15
0x180066ed0  mov     rbp, rsp
0x180066ed3  sub     rsp, 30h
0x180066ed7  mov     rbx, rdx
0x180066eda  mov     rdi, rcx
0x180066edd  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180066ee4  mov     r8d, 2ECh; int
0x180066eea  lea     rcx, [rbp+arg_0]; this
0x180066eee  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180066ef3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x180066efa  lea     r13, WPP_1d1f8ea057fb3e402ff6b05a908ffa65_Traceguids
0x180066f01  jb      short loc_180066F1E
0x180066f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f0a  mov     edx, 57h ; 'W'
0x180066f0f  mov     r9, rdi
0x180066f12  mov     r8, r13
0x180066f15  mov     rcx, [rcx+10h]
0x180066f19  call    WPP_SF_q
0x180066f1e  xor     r12d, r12d
0x180066f21  lea     rcx, [rdi+10h]; lpCriticalSection
0x180066f25  mov     [rbp+arg_8], r12d
0x180066f29  call    cs:__imp_EnterCriticalSection
0x180066f2f  mov     [rdi+6Ch], r12d
0x180066f33  mov     rcx, rbx
0x180066f36  mov     rax, [rbx]
0x180066f39  mov     rax, [rax+38h]
0x180066f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f42  mov     rcx, [rdi+38h]
0x180066f46  lea     r8, [rbp+arg_8]
0x180066f4a  mov     rsi, rax
0x180066f4d  mov     rdx, [rcx]
0x180066f50  mov     rax, [rdx+58h]
0x180066f54  mov     rdx, rbx
0x180066f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f5c  mov     ebx, eax
0x180066f5e  cmp     cs:byte_1801B110B, 20h ; ' '
0x180066f65  lea     r14, [rsi+10h]
0x180066f69  jb      short loc_180066F91
0x180066f6b  mov     rcx, [r14]
0x180066f6e  lea     edx, [r12+58h]
0x180066f73  mov     [rsp+30h+var_10], rcx
0x180066f78  mov     r9, rdi
0x180066f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f82  mov     r8, r13
0x180066f85  mov     rcx, [rcx+88h]
0x180066f8c  call    WPP_SF_qq
0x180066f91  mov     rcx, [r14]
0x180066f94  mov     rax, [rcx]
0x180066f97  mov     rax, [rax+20h]
0x180066f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fa0  test    ebx, ebx
0x180066fa2  jns     short loc_180066FFE
0x180066fa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066fab  test    rcx, rcx
0x180066fae  jnz     short loc_180066FBC
0x180066fb0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180066fb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180066fbc  cmp     [rcx+8], r12b
0x180066fc0  jz      short loc_180066FE7
0x180066fc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066fc7  cmp     [rax+7CCh], ebx
0x180066fcd  jz      short loc_180066FE7
0x180066fcf  mov     r9d, ebx; int
0x180066fd2  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180066fd9  mov     r8d, 307h; int
0x180066fdf  mov     rcx, rax; this
0x180066fe2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066fe7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066fee  jb      loc_1800675F8
0x180066ff4  mov     edx, 59h ; 'Y'
0x180066ff9  jmp     loc_1800675DE
0x180066ffe  mov     rcx, [r14]
0x180067001  mov     edx, [rbp+arg_8]
0x180067004  mov     rax, [rcx]
0x180067007  mov     rax, [rax+30h]
0x18006700b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067010  mov     ebx, eax
0x180067012  test    eax, eax
0x180067014  jns     loc_1800670A9
0x18006701a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067021  test    rcx, rcx
0x180067024  jnz     short loc_180067067
0x180067026  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006702c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067033  mov     rcx, rax
0x180067036  test    rax, rax
0x180067039  jz      short loc_180067059
0x18006703b  mov     rax, [rax]
0x18006703e  mov     edx, 7F0h
0x180067043  mov     rax, [rax+8]
0x180067047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006704c  test    eax, eax
0x18006704e  jz      short loc_180067059
0x180067050  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067057  jmp     short loc_180067067
0x180067059  lea     rcx, qword_1801B07E0; this
0x180067060  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067067  cmp     [rcx+8], r12b
0x18006706b  jz      short loc_180067092
0x18006706d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067072  cmp     [rax+7CCh], ebx
0x180067078  jz      short loc_180067092
0x18006707a  mov     r9d, ebx; int
0x18006707d  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067084  mov     r8d, 309h; int
0x18006708a  mov     rcx, rax; this
0x18006708d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067092  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067099  jb      loc_1800675F8
0x18006709f  mov     edx, 5Ah ; 'Z'
0x1800670a4  jmp     loc_1800675DE
0x1800670a9  mov     eax, [rbp+arg_8]
0x1800670ac  mov     [rsi+20h], eax
0x1800670af  mov     eax, [rdi+40h]
0x1800670b2  mov     ecx, [rbp+arg_8]
0x1800670b5  cmp     ecx, eax
0x1800670b7  jnb     loc_180067153
0x1800670bd  cmp     cs:byte_1801B110B, 20h ; ' '
0x1800670c4  jb      short loc_1800670EC
0x1800670c6  mov     [rsp+30h+var_8], eax
0x1800670ca  mov     edx, 5Bh ; '['
0x1800670cf  mov     dword ptr [rsp+30h+var_10], ecx
0x1800670d3  mov     r9, rdi
0x1800670d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800670dd  mov     r8, r13
0x1800670e0  mov     rcx, [rcx+88h]
0x1800670e7  call    WPP_SF_qDD
0x1800670ec  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x1800670f0  mov     [rbp+arg_0], r12
0x1800670f4  mov     rcx, rdi; this
0x1800670f7  call    ?_GetByteStreamLength@CByteStreamCacheReader2@@IEAAJPEA_K@Z; CByteStreamCacheReader2::_GetByteStreamLength(unsigned __int64 *)
0x1800670fc  test    eax, eax
0x1800670fe  js      short loc_180067153
0x180067100  mov     rbx, [rbp+arg_0]
0x180067104  cmp     [rdi+50h], rbx
0x180067108  jbe     short loc_180067153
0x18006710a  mov     ecx, [rdi+40h]
0x18006710d  mov     eax, [rbp+arg_8]
0x180067110  sub     rcx, rax
0x180067113  add     rcx, rbx
0x180067116  cmp     rcx, [rdi+50h]
0x18006711a  jnz     short loc_180067153
0x18006711c  cmp     cs:byte_1801B110B, 20h ; ' '
0x180067123  jb      short loc_180067148
0x180067125  mov     rcx, cs:WPP_GLOBAL_Control
0x18006712c  mov     edx, 5Ch ; '\'
0x180067131  mov     r9, rdi
0x180067134  mov     [rsp+30h+var_10], rbx
0x180067139  mov     r8, r13
0x18006713c  mov     rcx, [rcx+88h]
0x180067143  call    WPP_SF_qI
0x180067148  mov     rdx, rbx; unsigned __int64
0x18006714b  mov     rcx, rdi; this
0x18006714e  call    ?_SetCurrentPosition@CByteStreamCacheReader2@@IEAAJ_K@Z; CByteStreamCacheReader2::_SetCurrentPosition(unsigned __int64)
0x180067153  cmp     [rsi+24h], r12d
0x180067157  jz      loc_18006745F
0x18006715d  mov     dword ptr [rbp+arg_0], r12d
0x180067161  mov     al, cs:byte_1801B110B
0x180067167  cmp     al, 8
0x180067169  jb      short loc_18006718F
0x18006716b  mov     rcx, cs:WPP_GLOBAL_Control
0x180067172  mov     edx, 5Dh ; ']'
0x180067177  mov     r9, rdi
0x18006717a  mov     r8, r13
0x18006717d  mov     rcx, [rcx+88h]
0x180067184  call    WPP_SF_q
0x180067189  mov     al, cs:byte_1801B110B
0x18006718f  mov     rcx, [rdi+60h]
0x180067193  test    rcx, rcx
0x180067196  jz      loc_180067275
0x18006719c  cmp     [rcx+7Ch], r12d
0x1800671a0  jnz     loc_180067275
0x1800671a6  cmp     al, 4
0x1800671a8  jb      short loc_1800671C8
0x1800671aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800671b1  mov     edx, 5Eh ; '^'
0x1800671b6  mov     r9, rdi
0x1800671b9  mov     r8, r13
0x1800671bc  mov     rcx, [rcx+88h]
0x1800671c3  call    WPP_SF_q
0x1800671c8  mov     rdx, [rdi+60h]
0x1800671cc  mov     rcx, rdi; this
0x1800671cf  mov     r8d, [rdx+7Ch]; int
0x1800671d3  mov     rdx, [rdx+70h]; unsigned __int64
0x1800671d7  call    ?_BeginCacheItemRead@CByteStreamCacheReader2@@IEAAJ_KH@Z; CByteStreamCacheReader2::_BeginCacheItemRead(unsigned __int64,int)
0x1800671dc  mov     ebx, eax
0x1800671de  test    eax, eax
0x1800671e0  jns     loc_18006763C
0x1800671e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800671ed  test    rcx, rcx
0x1800671f0  jnz     short loc_180067233
0x1800671f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800671f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800671ff  mov     rcx, rax
0x180067202  test    rax, rax
0x180067205  jz      short loc_180067225
0x180067207  mov     rax, [rax]
0x18006720a  mov     edx, 7F0h
0x18006720f  mov     rax, [rax+8]
0x180067213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067218  test    eax, eax
0x18006721a  jz      short loc_180067225
0x18006721c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067223  jmp     short loc_180067233
0x180067225  lea     rcx, qword_1801B07E0; this
0x18006722c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067233  cmp     [rcx+8], r12b
0x180067237  jz      short loc_18006725E
0x180067239  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006723e  cmp     [rax+7CCh], ebx
0x180067244  jz      short loc_18006725E
0x180067246  mov     r9d, ebx; int
0x180067249  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067250  mov     r8d, 32Fh; int
0x180067256  mov     rcx, rax; this
0x180067259  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006725e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067265  jb      loc_1800675F8
0x18006726b  mov     edx, 5Fh ; '_'
0x180067270  jmp     loc_1800675DE
0x180067275  mov     rdx, rsi; struct CByteStreamCacheItem *
0x180067278  mov     rcx, rdi; this
0x18006727b  call    ?_AddToCache@CByteStreamCacheReader2@@IEAAJPEAVCByteStreamCacheItem@@@Z; CByteStreamCacheReader2::_AddToCache(CByteStreamCacheItem *)
0x180067280  mov     ebx, eax
0x180067282  test    eax, eax
0x180067284  jns     loc_180067319
0x18006728a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067291  test    rcx, rcx
0x180067294  jnz     short loc_1800672D7
0x180067296  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006729c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800672a3  mov     rcx, rax
0x1800672a6  test    rax, rax
0x1800672a9  jz      short loc_1800672C9
0x1800672ab  mov     rax, [rax]
0x1800672ae  mov     edx, 7F0h
0x1800672b3  mov     rax, [rax+8]
0x1800672b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672bc  test    eax, eax
0x1800672be  jz      short loc_1800672C9
0x1800672c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800672c7  jmp     short loc_1800672D7
0x1800672c9  lea     rcx, qword_1801B07E0; this
0x1800672d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800672d7  cmp     [rcx+8], r12b
0x1800672db  jz      short loc_180067302
0x1800672dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800672e2  cmp     [rax+7CCh], ebx
0x1800672e8  jz      short loc_180067302
0x1800672ea  mov     r9d, ebx; int
0x1800672ed  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x1800672f4  mov     r8d, 333h; int
0x1800672fa  mov     rcx, rax; this
0x1800672fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067302  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067309  jb      loc_1800675F8
0x18006730f  mov     edx, 60h ; '`'
0x180067314  jmp     loc_1800675DE
0x180067319  lea     rdx, [rbp+arg_0]; int *
0x18006731d  mov     rcx, rdi; this
0x180067320  call    ?_FillPendingCacheRead@CByteStreamCacheReader2@@IEAAJPEAH@Z; CByteStreamCacheReader2::_FillPendingCacheRead(int *)
0x180067325  mov     ebx, eax
0x180067327  test    eax, eax
0x180067329  jns     loc_1800673BE
0x18006732f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067336  test    rcx, rcx
0x180067339  jnz     short loc_18006737C
0x18006733b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067341  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067348  mov     rcx, rax
0x18006734b  test    rax, rax
0x18006734e  jz      short loc_18006736E
0x180067350  mov     rax, [rax]
0x180067353  mov     edx, 7F0h
0x180067358  mov     rax, [rax+8]
0x18006735c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067361  test    eax, eax
0x180067363  jz      short loc_18006736E
0x180067365  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006736c  jmp     short loc_18006737C
0x18006736e  lea     rcx, qword_1801B07E0; this
0x180067375  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006737c  cmp     [rcx+8], r12b
0x180067380  jz      short loc_1800673A7
0x180067382  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067387  cmp     [rax+7CCh], ebx
0x18006738d  jz      short loc_1800673A7
0x18006738f  mov     r9d, ebx; int
0x180067392  lea     rdx, aCbytestreamcac_5; "CByteStreamCacheReader2::OnCacheRead"
0x180067399  mov     r8d, 334h; int
0x18006739f  mov     rcx, rax; this
0x1800673a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800673a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
