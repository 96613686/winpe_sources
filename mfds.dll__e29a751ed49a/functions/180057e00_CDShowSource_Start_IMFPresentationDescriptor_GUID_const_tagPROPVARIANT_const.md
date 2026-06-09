# CDShowSource::Start(IMFPresentationDescriptor *,_GUID const *,tagPROPVARIANT const *)

- ea: `0x180057e00`
- end: `0x18005843d`
- name: `?Start@CDShowSource@@UEAAJPEAUIMFPresentationDescriptor@@PEBU_GUID@@PEBUtagPROPVARIANT@@@Z`
- size: `1597`
- prototype: `int(CDShowSource *__hidden this, struct IMFPresentationDescriptor *, const struct _GUID *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x180032a50`
- `0x180051ce4`
- `0x1800527ac`
- `0x180057e00`
- `0x180073d0c`
- `0x180074160`
- `0x180087a4c`
- `0x180087ad4`
- `0x180088310`
- `0x180099870`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058408`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058408`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057eb2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180058270`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180058270`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057ee2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005803e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800580f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800581c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058340`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057ee2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180057f9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005803e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800580f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800581c1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058292`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058340`

## pseudocode

```c
__int64 __fastcall CDShowSource::Start(
        CDShowSource *this,
        struct IMFPresentationDescriptor *a2,
        const struct _GUID *a3,
        const struct tagPROPVARIANT *a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  bool v11; // zf
  CallStackTracing *v12; // rcx
  HRESULT v13; // edi
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  void *v26; // rax
  struct CBaseOperation *v27; // rbx
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  int v31; // r8d
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  _BYTE v39[8]; // [rsp+30h] [rbp-58h] BYREF
  struct CBaseOperation *v40[2]; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "CDShowSource::Start", 1014);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 137) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 137) + 296LL))(*((_QWORD *)this + 137));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, struct CBaseOperation **))(**((_QWORD **)this + 137) + 280LL))(
                       *((_QWORD *)this + 137),
                       v40);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v11 = *((_DWORD *)this + 22) == 0;
  v40[0] = 0;
  if ( v11 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        if ( !a3 || (unsigned __int8)_(&GUID_00000000_0000_0000_0000_000000000000, a3) )
        {
          v26 = operator new(0x48u);
          if ( v26 )
            v26 = (void *)CDShowSourceOp::CDShowSourceOp(v26, 1);
          ComSmartPtr<CDShowSourceOp>::Attach(v40, v26);
          v27 = v40[0];
          if ( v40[0] )
          {
            *((_QWORD *)v40[0] + 3) = a2;
            ((void (__fastcall *)(struct IMFPresentationDescriptor *))a2->lpVtbl->AddRef)(a2);
            *((GUID *)v27 + 2) = GUID_00000000_0000_0000_0000_000000000000;
            v13 = PropVariantCopy((PROPVARIANT *)v27 + 2, a4);
            if ( v13 >= 0 )
            {
              v13 = COpQueue::QueueOperation((CDShowSource *)((char *)this + 224), v27, v31);
              if ( v13 >= 0 )
              {
                if ( (unsigned __int8)byte_1800EACCB >= 8u )
                  WPP_SF_qqq(
                    *((_QWORD *)WPP_GLOBAL_Control + 17),
                    112,
                    &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
                    this,
                    a2,
                    v27);
              }
              else
              {
                v35 = CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                  CallStackTracing::s_wpInstance = v36;
                  if ( v36
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                  {
                    v35 = CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v35 = (CallStackTracing *)&qword_1800EB130;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                  }
                }
                if ( *((_BYTE *)v35 + 8) )
                {
                  v37 = CallStackTracing::GetThreadRelativeContext(v35);
                  if ( *((_DWORD *)v37 + 499) != v13 )
                    CallStackContext::TraceFailure(v37, "CDShowSource::Start", 1047, v13);
                }
                if ( g_wppLevels )
                {
                  v16 = 111;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v32 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                {
                  v32 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v32 = (CallStackTracing *)&qword_1800EB130;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
                }
              }
              if ( *((_BYTE *)v32 + 8) )
              {
                v34 = CallStackTracing::GetThreadRelativeContext(v32);
                if ( *((_DWORD *)v34 + 499) != v13 )
                  CallStackContext::TraceFailure(v34, "CDShowSource::Start", 1045, v13);
              }
              if ( g_wppLevels )
              {
                v16 = 110;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v28 = CallStackTracing::s_wpInstance;
            v13 = -2147024882;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = (CallStackTracing *)&qword_1800EB130;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              v30 = CallStackTracing::GetThreadRelativeContext(v28);
              if ( *((_DWORD *)v30 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v30, "CDShowSource::Start", 1038, -2147024882);
            }
            if ( g_wppLevels )
            {
              v16 = 109;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v23 = CallStackTracing::s_wpInstance;
          v13 = -1072875835;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext(v23);
            if ( *((_DWORD *)v25 + 499) != -1072875835 )
              CallStackContext::TraceFailure(v25, "CDShowSource::Start", 1034, -1072875835);
          }
          if ( g_wppLevels )
          {
            v16 = 108;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v20 = CallStackTracing::s_wpInstance;
        v13 = -2147024809;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v20);
          if ( *((_DWORD *)v22 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v22, "CDShowSource::Start", 1022, -2147024809);
        }
        if ( g_wppLevels )
        {
          v16 = 107;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v17 = CallStackTracing::s_wpInstance;
      v13 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v19 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v19, "CDShowSource::Start", 1021, -2147467261);
      }
      if ( g_wppLevels )
      {
        v16 = 106;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v12 = CallStackTracing::s_wpInstance;
    v13 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( *((_DWORD *)v15 + 499) != -1072873851 )
        CallStackContext::TraceFailure(v15, "CDShowSource::Start", 1019, -1072873851);
    }
    if ( g_wppLevels )
    {
      v16 = 105;
LABEL_15:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids, this, v13);
    }
  }
  ComSmartPtr<CDShowSourceOp>::~ComSmartPtr<CDShowSourceOp>(v40);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180057e00  push    rbx
0x180057e02  push    rbp
0x180057e03  push    rsi
0x180057e04  push    rdi
0x180057e05  push    r12
0x180057e07  push    r14
0x180057e09  push    r15
0x180057e0b  sub     rsp, 50h
0x180057e0f  mov     rax, cs:__security_cookie
0x180057e16  xor     rax, rsp
0x180057e19  mov     [rsp+88h+var_40], rax
0x180057e1e  mov     rbp, r8
0x180057e21  lea     rbx, aCdshowsourceSt; "CDShowSource::Start"
0x180057e28  mov     r14, rdx
0x180057e2b  mov     rsi, rcx
0x180057e2e  mov     rdx, rbx; char *
0x180057e31  lea     rcx, [rsp+88h+var_58]; this
0x180057e36  mov     r8d, 3F6h; int
0x180057e3c  mov     r15, r9
0x180057e3f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180057e44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180057e4b  cmp     byte ptr [rcx+8], 0
0x180057e4f  jz      short loc_180057EAE
0x180057e51  cmp     qword ptr [rsi+448h], 0
0x180057e59  jz      short loc_180057EAE
0x180057e5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057e60  mov     rcx, [rsi+448h]
0x180057e67  mov     rdi, rax
0x180057e6a  mov     rdx, [rcx]
0x180057e6d  mov     rax, [rdx+128h]
0x180057e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e79  mov     rcx, [rsi+448h]
0x180057e80  mov     ebx, eax
0x180057e82  mov     rdx, [rcx]
0x180057e85  mov     rax, [rdx+118h]
0x180057e8c  lea     rdx, [rsp+88h+var_50]
0x180057e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e96  movups  xmm0, xmmword ptr [rax]
0x180057e99  mov     [rdi+7E0h], ebx
0x180057e9f  lea     rbx, aCdshowsourceSt; "CDShowSource::Start"
0x180057ea6  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180057eae  lea     rcx, [rsi+30h]; lpCriticalSection
0x180057eb2  call    cs:__imp_EnterCriticalSection
0x180057eb9  nop     dword ptr [rax+rax+00h]
0x180057ebe  cmp     dword ptr [rsi+58h], 0
0x180057ec2  mov     [rsp+88h+var_50], 0
0x180057ecb  jz      loc_180057F85
0x180057ed1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057ed8  mov     edi, 0C00D3E85h
0x180057edd  test    rcx, rcx
0x180057ee0  jnz     short loc_180057F29
0x180057ee2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057ee9  nop     dword ptr [rax+rax+00h]
0x180057eee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057ef5  mov     rcx, rax
0x180057ef8  test    rax, rax
0x180057efb  jz      short loc_180057F1B
0x180057efd  mov     rax, [rax]
0x180057f00  mov     edx, 7F0h
0x180057f05  mov     rax, [rax+8]
0x180057f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f0e  test    eax, eax
0x180057f10  jz      short loc_180057F1B
0x180057f12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f19  jmp     short loc_180057F29
0x180057f1b  lea     rcx, qword_1800EB130; this
0x180057f22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f29  cmp     byte ptr [rcx+8], 0
0x180057f2d  jz      short loc_180057F50
0x180057f2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057f34  cmp     [rax+7CCh], edi
0x180057f3a  jz      short loc_180057F50
0x180057f3c  mov     r9d, edi; int
0x180057f3f  mov     r8d, 3FBh; int
0x180057f45  mov     rdx, rbx; char *
0x180057f48  mov     rcx, rax; this
0x180057f4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180057f50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180057f57  jb      loc_1800583FA
0x180057f5d  mov     edx, 69h ; 'i'
0x180057f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180057f69  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x180057f70  mov     r9, rsi
0x180057f73  mov     dword ptr [rsp+88h+var_68], edi
0x180057f77  mov     rcx, [rcx+10h]
0x180057f7b  call    WPP_SF_qD
0x180057f80  jmp     loc_1800583FA
0x180057f85  test    r14, r14
0x180057f88  jnz     loc_180058024
0x180057f8e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057f95  mov     edi, 80004003h
0x180057f9a  test    rcx, rcx
0x180057f9d  jnz     short loc_180057FE6
0x180057f9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180057fa6  nop     dword ptr [rax+rax+00h]
0x180057fab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180057fb2  mov     rcx, rax
0x180057fb5  test    rax, rax
0x180057fb8  jz      short loc_180057FD8
0x180057fba  mov     rax, [rax]
0x180057fbd  mov     edx, 7F0h
0x180057fc2  mov     rax, [rax+8]
0x180057fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fcb  test    eax, eax
0x180057fcd  jz      short loc_180057FD8
0x180057fcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180057fd6  jmp     short loc_180057FE6
0x180057fd8  lea     rcx, qword_1800EB130; this
0x180057fdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180057fe6  cmp     byte ptr [rcx+8], 0
0x180057fea  jz      short loc_18005800D
0x180057fec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180057ff1  cmp     [rax+7CCh], edi
0x180057ff7  jz      short loc_18005800D
0x180057ff9  mov     r9d, edi; int
0x180057ffc  mov     r8d, 3FDh; int
0x180058002  mov     rdx, rbx; char *
0x180058005  mov     rcx, rax; this
0x180058008  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005800d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058014  jb      loc_1800583FA
0x18005801a  mov     edx, 6Ah ; 'j'
0x18005801f  jmp     loc_180057F62
0x180058024  test    r15, r15
0x180058027  jnz     loc_1800580C3
0x18005802d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058034  mov     edi, 80070057h
0x180058039  test    rcx, rcx
0x18005803c  jnz     short loc_180058085
0x18005803e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058045  nop     dword ptr [rax+rax+00h]
0x18005804a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058051  mov     rcx, rax
0x180058054  test    rax, rax
0x180058057  jz      short loc_180058077
0x180058059  mov     rax, [rax]
0x18005805c  mov     edx, 7F0h
0x180058061  mov     rax, [rax+8]
0x180058065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005806a  test    eax, eax
0x18005806c  jz      short loc_180058077
0x18005806e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058075  jmp     short loc_180058085
0x180058077  lea     rcx, qword_1800EB130; this
0x18005807e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058085  cmp     byte ptr [rcx+8], 0
0x180058089  jz      short loc_1800580AC
0x18005808b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058090  cmp     [rax+7CCh], edi
0x180058096  jz      short loc_1800580AC
0x180058098  mov     r9d, edi; int
0x18005809b  mov     r8d, 3FEh; int
0x1800580a1  mov     rdx, rbx; char *
0x1800580a4  mov     rcx, rax; this
0x1800580a7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800580ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800580b3  jb      loc_1800583FA
0x1800580b9  mov     edx, 6Bh ; 'k'
0x1800580be  jmp     loc_180057F62
0x1800580c3  test    rbp, rbp
0x1800580c6  jz      loc_180058179
0x1800580cc  mov     rdx, rbp
0x1800580cf  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x1800580d6  call    __
0x1800580db  test    al, al
0x1800580dd  jnz     loc_180058179
0x1800580e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800580ea  mov     edi, 0C00D36C5h
0x1800580ef  test    rcx, rcx
0x1800580f2  jnz     short loc_18005813B
0x1800580f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800580fb  nop     dword ptr [rax+rax+00h]
0x180058100  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058107  mov     rcx, rax
0x18005810a  test    rax, rax
0x18005810d  jz      short loc_18005812D
0x18005810f  mov     rax, [rax]
0x180058112  mov     edx, 7F0h
0x180058117  mov     rax, [rax+8]
0x18005811b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058120  test    eax, eax
0x180058122  jz      short loc_18005812D
0x180058124  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005812b  jmp     short loc_18005813B
0x18005812d  lea     rcx, qword_1800EB130; this
0x180058134  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005813b  cmp     byte ptr [rcx+8], 0
0x18005813f  jz      short loc_180058162
0x180058141  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058146  cmp     [rax+7CCh], edi
0x18005814c  jz      short loc_180058162
0x18005814e  mov     r9d, edi; int
0x180058151  mov     r8d, 40Ah; int
0x180058157  mov     rdx, rbx; char *
0x18005815a  mov     rcx, rax; this
0x18005815d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058162  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058169  jb      loc_1800583FA
0x18005816f  mov     edx, 6Ch ; 'l'
0x180058174  jmp     loc_180057F62
0x180058179  mov     ecx, 48h ; 'H'; Size
0x18005817e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058183  test    rax, rax
0x180058186  jz      short loc_180058195
0x180058188  mov     edx, 1
0x18005818d  mov     rcx, rax
0x180058190  call    ??0CDShowSourceOp@@QEAA@W4OP_TYPE@0@@Z; CDShowSourceOp::CDShowSourceOp(CDShowSourceOp::OP_TYPE)
0x180058195  mov     rdx, rax
0x180058198  lea     rcx, [rsp+88h+var_50]
0x18005819d  call    ?Attach@?$ComSmartPtr@VCDShowSourceOp@@@@QEAAXPEAVCDShowSourceOp@@@Z; ComSmartPtr<CDShowSourceOp>::Attach(CDShowSourceOp *)
0x1800581a2  mov     rbx, [rsp+88h+var_50]
0x1800581a7  test    rbx, rbx
0x1800581aa  jnz     loc_18005824A
0x1800581b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581b7  mov     edi, 8007000Eh
0x1800581bc  test    rcx, rcx
0x1800581bf  jnz     short loc_180058208
0x1800581c1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800581c8  nop     dword ptr [rax+rax+00h]
0x1800581cd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581d4  mov     rcx, rax
0x1800581d7  test    rax, rax
0x1800581da  jz      short loc_1800581FA
0x1800581dc  mov     rax, [rax]
0x1800581df  mov     edx, 7F0h
0x1800581e4  mov     rax, [rax+8]
0x1800581e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581ed  test    eax, eax
0x1800581ef  jz      short loc_1800581FA
0x1800581f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800581f8  jmp     short loc_180058208
0x1800581fa  lea     rcx, qword_1800EB130; this
0x180058201  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058208  cmp     byte ptr [rcx+8], 0
0x18005820c  jz      short loc_180058233
0x18005820e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058213  cmp     [rax+7CCh], edi
0x180058219  jz      short loc_180058233
0x18005821b  mov     r9d, edi; int
0x18005821e  lea     rdx, aCdshowsourceSt; "CDShowSource::Start"
0x180058225  mov     r8d, 40Eh; int
0x18005822b  mov     rcx, rax; this
0x18005822e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058233  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005823a  jb      loc_1800583FA
0x180058240  mov     edx, 6Dh ; 'm'
0x180058245  jmp     loc_180057F62
0x18005824a  mov     [rbx+18h], r14
0x18005824e  mov     rcx, r14
0x180058251  mov     rax, [r14]
0x180058254  mov     rax, [rax+8]
0x180058258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005825d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180058264  lea     rcx, [rbx+30h]; pvarDest
0x180058268  mov     rdx, r15; pvarSrc
0x18005826b  movdqu  xmmword ptr [rbx+20h], xmm0
0x180058270  call    cs:__imp_PropVariantCopy
0x180058277  nop     dword ptr [rax+rax+00h]
0x18005827c  mov     edi, eax
0x18005827e  test    eax, eax
0x180058280  jns     loc_18005831B
0x180058286  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005828d  test    rcx, rcx
0x180058290  jnz     short loc_1800582D9
0x180058292  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058299  nop     dword ptr [rax+rax+00h]
0x18005829e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800582a5  mov     rcx, rax
0x1800582a8  test    rax, rax
0x1800582ab  jz      short loc_1800582CB
0x1800582ad  mov     rax, [rax]
0x1800582b0  mov     edx, 7F0h
0x1800582b5  mov     rax, [rax+8]
0x1800582b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582be  test    eax, eax
0x1800582c0  jz      short loc_1800582CB
0x1800582c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800582c9  jmp     short loc_1800582D9
0x1800582cb  lea     rcx, qword_1800EB130; this
0x1800582d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800582d9  cmp     byte ptr [rcx+8], 0
0x1800582dd  jz      short loc_180058304
0x1800582df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800582e4  cmp     [rax+7CCh], edi
0x1800582ea  jz      short loc_180058304
0x1800582ec  mov     r9d, edi; int
0x1800582ef  lea     rdx, aCdshowsourceSt; "CDShowSource::Start"
0x1800582f6  mov     r8d, 415h; int
0x1800582fc  mov     rcx, rax; this
0x1800582ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058304  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005830b  jb      loc_1800583FA
0x180058311  mov     edx, 6Eh ; 'n'
0x180058316  jmp     loc_180057F62
0x18005831b  lea     rcx, [rsi+0E0h]; this
0x180058322  mov     rdx, rbx; struct CBaseOperation *
0x180058325  call    ?QueueOperation@COpQueue@@QEAAJPEAVCBaseOperation@@H@Z; COpQueue::QueueOperation(CBaseOperation *,int)
0x18005832a  mov     edi, eax
0x18005832c  test    eax, eax
0x18005832e  jns     loc_1800583C5
  ... truncated ...
```
