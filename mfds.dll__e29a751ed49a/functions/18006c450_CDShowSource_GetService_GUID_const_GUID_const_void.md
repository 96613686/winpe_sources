# CDShowSource::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x18006c450`
- end: `0x18006cb3f`
- name: `?GetService@CDShowSource@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `1775`
- prototype: `int(CDShowSource *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180010350`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180051ce4`
- `0x180052ca8`
- `0x18006c450`
- `0x180074160`
- `0x180088e3c`
- `0x180089ab0`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cb0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cb0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c4fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c4fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c528`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c5cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c730`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c8b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c995`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ca69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c528`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c5cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c730`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c803`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c8b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006c995`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006ca69`

## string_xrefs

- `0x18006c47b`: `CDShowSource::GetService`
- `0x18006c585`: `CDShowSource::GetService`
- `0x18006c628`: `CDShowSource::GetService`
- `0x18006c78d`: `CDShowSource::GetService`
- `0x18006c860`: `CDShowSource::GetService`
- `0x18006c90d`: `CDShowSource::GetService`
- `0x18006c9f2`: `CDShowSource::GetService`
- `0x18006cac6`: `CDShowSource::GetService`

## pseudocode

```c
__int64 __fastcall CDShowSource::GetService(
        CDShowSource *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v9; // ebx
  __int128 v10; // xmm0
  CDShowSource *v11; // rdi
  CallStackTracing *v12; // rcx
  int Interface; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CDShowWrapper *v20; // rcx
  CallStackTracing *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  CallStackTracing *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  _BYTE v38[8]; // [rsp+30h] [rbp-28h] BYREF
  struct IBaseFilter *v39[2]; // [rsp+38h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v38, "CDShowSource::GetService", 361);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 136) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 136) + 296LL))(*((_QWORD *)this + 136));
    v10 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, struct IBaseFilter **))(**((_QWORD **)this + 136) + 280LL))(
                       *((_QWORD *)this + 136),
                       v39);
    *((_DWORD *)ThreadRelativeContext + 504) = v9;
    *((_OWORD *)ThreadRelativeContext + 125) = v10;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v11 = (CDShowSource *)((char *)this - 8);
  if ( *((_DWORD *)this + 20) )
  {
    v12 = CallStackTracing::s_wpInstance;
    Interface = -1072873851;
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
        CallStackContext::TraceFailure(v15, "CDShowSource::GetService", 365, -1072873851);
    }
    if ( g_wppLevels )
    {
      v16 = 22;
LABEL_97:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
        v11,
        Interface);
      goto LABEL_98;
    }
    goto LABEL_98;
  }
  if ( a4 )
  {
    if ( (unsigned __int8)_(&MF_RATE_CONTROL_SERVICE, a2) )
    {
      if ( (unsigned __int8)_(a3, &IID_IMFRateSupport) || (unsigned __int8)_(a3, &IID_IMFRateControl) )
      {
        Interface = CDShowSource::QueryInterface((CDShowSource *)((char *)this - 8), a3, a4);
        if ( Interface < 0 )
        {
          v28 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
            if ( *((_DWORD *)v30 + 499) != Interface )
              CallStackContext::TraceFailure(v30, "CDShowSource::GetService", 373, Interface);
          }
          if ( g_wppLevels )
          {
            v16 = 24;
            goto LABEL_97;
          }
        }
        goto LABEL_98;
      }
      if ( !(unsigned __int8)_(a3, &IID_IDvdControl2)
        && !(unsigned __int8)_(a3, &IID_IDvdInfo2)
        && !(unsigned __int8)_(a3, &IID_IMFMediaEventGenerator)
        && !(unsigned __int8)_(a3, &IID_IMFTelemetryComponent) )
      {
        Interface = 0;
        goto LABEL_98;
      }
      v20 = (CDShowWrapper *)*((_QWORD *)this + 91);
      if ( v20 && *((_DWORD *)v20 + 118) )
      {
        v39[0] = 0;
        Interface = CDShowWrapper::GetDShowSourceFilter(v20, v39);
        if ( Interface >= 0 )
        {
          Interface = ((__int64 (__fastcall *)(struct IBaseFilter *, const struct _GUID *, void **))v39[0]->lpVtbl->QueryInterface)(
                        v39[0],
                        a3,
                        a4);
          if ( Interface >= 0 )
            goto LABEL_84;
          v25 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext(v25);
            if ( *((_DWORD *)v27 + 499) != Interface )
              CallStackContext::TraceFailure(v27, "CDShowSource::GetService", 385, Interface);
          }
          if ( !g_wppLevels )
            goto LABEL_84;
          v24 = 26;
        }
        else
        {
          v21 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext(v21);
            if ( *((_DWORD *)v23 + 499) != Interface )
              CallStackContext::TraceFailure(v23, "CDShowSource::GetService", 383, Interface);
          }
          if ( !g_wppLevels )
            goto LABEL_84;
          v24 = 25;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v24,
          &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
          (char *)this - 8,
          Interface);
LABEL_84:
        ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(v39);
        goto LABEL_98;
      }
    }
    else
    {
      if ( !(unsigned __int8)_(&MF_PROPERTY_HANDLER_SERVICE, a2) )
      {
        v34 = CallStackTracing::s_wpInstance;
        Interface = -1072875846;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext(v34);
          if ( *((_DWORD *)v36 + 499) != -1072875846 )
            CallStackContext::TraceFailure(v36, "CDShowSource::GetService", 415, -1072875846);
        }
        if ( g_wppLevels )
        {
          v16 = 28;
          goto LABEL_97;
        }
        goto LABEL_98;
      }
      if ( (unsigned __int8)_(&IID_IPropertyStore, a3) )
      {
        v39[0] = 0;
        Interface = CDShowSource::GetShellPropertyStore(v11, (struct IPropertyStore **)v39);
        if ( Interface >= 0 )
        {
          *a4 = v39[0];
          v39[0] = 0;
        }
        else
        {
          v31 = CallStackTracing::s_wpInstance;
          Interface = -2147467262;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext(v31);
            if ( *((_DWORD *)v33 + 499) != -2147467262 )
              CallStackContext::TraceFailure(v33, "CDShowSource::GetService", 403, -2147467262);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids,
              v11,
              -2147467262);
        }
        goto LABEL_84;
      }
    }
    Interface = -2147467262;
    goto LABEL_98;
  }
  v17 = CallStackTracing::s_wpInstance;
  Interface = -2147467261;
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
      CallStackContext::TraceFailure(v19, "CDShowSource::GetService", 366, -2147467261);
  }
  if ( g_wppLevels )
  {
    v16 = 23;
    goto LABEL_97;
  }
LABEL_98:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18006c450  push    rbp
0x18006c452  push    rbx
0x18006c453  push    rsi
0x18006c454  push    rdi
0x18006c455  push    r12
0x18006c457  push    r13
0x18006c459  push    r14
0x18006c45b  push    r15
0x18006c45d  mov     rbp, rsp
0x18006c460  sub     rsp, 58h
0x18006c464  mov     rax, cs:__security_cookie
0x18006c46b  xor     rax, rsp
0x18006c46e  mov     [rbp+var_10], rax
0x18006c472  mov     rsi, r8
0x18006c475  mov     r12, rdx
0x18006c478  mov     r14, rcx
0x18006c47b  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c482  mov     r8d, 169h; int
0x18006c488  lea     rcx, [rbp+var_28]; this
0x18006c48c  mov     r15, r9
0x18006c48f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18006c494  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18006c49b  cmp     byte ptr [rcx+8], 0
0x18006c49f  jz      short loc_18006C4F6
0x18006c4a1  cmp     qword ptr [r14+440h], 0
0x18006c4a9  jz      short loc_18006C4F6
0x18006c4ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c4b0  mov     rcx, [r14+440h]
0x18006c4b7  mov     rdi, rax
0x18006c4ba  mov     rdx, [rcx]
0x18006c4bd  mov     rax, [rdx+128h]
0x18006c4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4c9  mov     rcx, [r14+440h]
0x18006c4d0  mov     ebx, eax
0x18006c4d2  mov     rdx, [rcx]
0x18006c4d5  mov     rax, [rdx+118h]
0x18006c4dc  lea     rdx, [rbp+var_20]
0x18006c4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4e5  movups  xmm0, xmmword ptr [rax]
0x18006c4e8  mov     [rdi+7E0h], ebx
0x18006c4ee  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18006c4f6  lea     r13, [r14+28h]
0x18006c4fa  mov     rcx, r13; lpCriticalSection
0x18006c4fd  call    cs:__imp_EnterCriticalSection
0x18006c504  nop     dword ptr [rax+rax+00h]
0x18006c509  lea     rdi, [r14-8]
0x18006c50d  cmp     dword ptr [rdi+58h], 0
0x18006c511  jz      loc_18006C5B1
0x18006c517  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c51e  mov     ebx, 0C00D3E85h
0x18006c523  test    rcx, rcx
0x18006c526  jnz     short loc_18006C56F
0x18006c528  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c52f  nop     dword ptr [rax+rax+00h]
0x18006c534  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c53b  mov     rcx, rax
0x18006c53e  test    rax, rax
0x18006c541  jz      short loc_18006C561
0x18006c543  mov     rax, [rax]
0x18006c546  mov     edx, 7F0h
0x18006c54b  mov     rax, [rax+8]
0x18006c54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c554  test    eax, eax
0x18006c556  jz      short loc_18006C561
0x18006c558  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c55f  jmp     short loc_18006C56F
0x18006c561  lea     rcx, qword_1800EB130; this
0x18006c568  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c56f  cmp     byte ptr [rcx+8], 0
0x18006c573  jz      short loc_18006C59A
0x18006c575  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c57a  cmp     [rax+7CCh], ebx
0x18006c580  jz      short loc_18006C59A
0x18006c582  mov     r9d, ebx; int
0x18006c585  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c58c  mov     r8d, 16Dh; int
0x18006c592  mov     rcx, rax; this
0x18006c595  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c59a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c5a1  jb      loc_18006CB07
0x18006c5a7  mov     edx, 16h
0x18006c5ac  jmp     loc_18006CAE9
0x18006c5b1  test    r15, r15
0x18006c5b4  jnz     loc_18006C654
0x18006c5ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c5c1  mov     ebx, 80004003h
0x18006c5c6  test    rcx, rcx
0x18006c5c9  jnz     short loc_18006C612
0x18006c5cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c5d2  nop     dword ptr [rax+rax+00h]
0x18006c5d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c5de  mov     rcx, rax
0x18006c5e1  test    rax, rax
0x18006c5e4  jz      short loc_18006C604
0x18006c5e6  mov     rax, [rax]
0x18006c5e9  mov     edx, 7F0h
0x18006c5ee  mov     rax, [rax+8]
0x18006c5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5f7  test    eax, eax
0x18006c5f9  jz      short loc_18006C604
0x18006c5fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c602  jmp     short loc_18006C612
0x18006c604  lea     rcx, qword_1800EB130; this
0x18006c60b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c612  cmp     byte ptr [rcx+8], 0
0x18006c616  jz      short loc_18006C63D
0x18006c618  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c61d  cmp     [rax+7CCh], ebx
0x18006c623  jz      short loc_18006C63D
0x18006c625  mov     r9d, ebx; int
0x18006c628  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c62f  mov     r8d, 16Eh; int
0x18006c635  mov     rcx, rax; this
0x18006c638  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c63d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c644  jb      loc_18006CB07
0x18006c64a  mov     edx, 17h
0x18006c64f  jmp     loc_18006CAE9
0x18006c654  mov     rdx, r12
0x18006c657  lea     rcx, MF_RATE_CONTROL_SERVICE
0x18006c65e  call    __
0x18006c663  test    al, al
0x18006c665  jz      loc_18006C939
0x18006c66b  lea     rdx, IID_IMFRateSupport
0x18006c672  mov     rcx, rsi
0x18006c675  call    __
0x18006c67a  xor     r12d, r12d
0x18006c67d  test    al, al
0x18006c67f  jnz     loc_18006C88C
0x18006c685  lea     rdx, IID_IMFRateControl
0x18006c68c  mov     rcx, rsi
0x18006c68f  call    __
0x18006c694  test    al, al
0x18006c696  jnz     loc_18006C88C
0x18006c69c  lea     rdx, IID_IDvdControl2
0x18006c6a3  mov     rcx, rsi
0x18006c6a6  call    __
0x18006c6ab  test    al, al
0x18006c6ad  jnz     short loc_18006C6F0
0x18006c6af  lea     rdx, IID_IDvdInfo2
0x18006c6b6  mov     rcx, rsi
0x18006c6b9  call    __
0x18006c6be  test    al, al
0x18006c6c0  jnz     short loc_18006C6F0
0x18006c6c2  lea     rdx, IID_IMFMediaEventGenerator
0x18006c6c9  mov     rcx, rsi
0x18006c6cc  call    __
0x18006c6d1  test    al, al
0x18006c6d3  jnz     short loc_18006C6F0
0x18006c6d5  lea     rdx, IID_IMFTelemetryComponent
0x18006c6dc  mov     rcx, rsi
0x18006c6df  call    __
0x18006c6e4  test    al, al
0x18006c6e6  jnz     short loc_18006C6F0
0x18006c6e8  mov     ebx, r12d
0x18006c6eb  jmp     loc_18006CB07
0x18006c6f0  mov     rcx, [r14+2D8h]; this
0x18006c6f7  test    rcx, rcx
0x18006c6fa  jz      loc_18006CA4E
0x18006c700  cmp     [rcx+1D8h], r12d
0x18006c707  jz      loc_18006CA4E
0x18006c70d  lea     rdx, [rbp+var_20]; struct IBaseFilter **
0x18006c711  mov     [rbp+var_20], r12
0x18006c715  call    ?GetDShowSourceFilter@CDShowWrapper@@QEAAJPEAPEAUIBaseFilter@@@Z; CDShowWrapper::GetDShowSourceFilter(IBaseFilter * *)
0x18006c71a  mov     ebx, eax
0x18006c71c  test    eax, eax
0x18006c71e  jns     loc_18006C7DC
0x18006c724  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c72b  test    rcx, rcx
0x18006c72e  jnz     short loc_18006C777
0x18006c730  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c737  nop     dword ptr [rax+rax+00h]
0x18006c73c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c743  mov     rcx, rax
0x18006c746  test    rax, rax
0x18006c749  jz      short loc_18006C769
0x18006c74b  mov     rax, [rax]
0x18006c74e  mov     edx, 7F0h
0x18006c753  mov     rax, [rax+8]
0x18006c757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c75c  test    eax, eax
0x18006c75e  jz      short loc_18006C769
0x18006c760  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c767  jmp     short loc_18006C777
0x18006c769  lea     rcx, qword_1800EB130; this
0x18006c770  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c777  cmp     [rcx+8], r12b
0x18006c77b  jz      short loc_18006C7A2
0x18006c77d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c782  cmp     [rax+7CCh], ebx
0x18006c788  jz      short loc_18006C7A2
0x18006c78a  mov     r9d, ebx; int
0x18006c78d  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c794  mov     r8d, 17Fh; int
0x18006c79a  mov     rcx, rax; this
0x18006c79d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c7a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c7a9  jb      short loc_18006C7CE
0x18006c7ab  mov     edx, 19h
0x18006c7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c7b7  lea     r8, WPP_fc9d812e38f834ce3857a60a35cbba0e_Traceguids
0x18006c7be  mov     r9, rdi
0x18006c7c1  mov     [rsp+58h+var_38], ebx
0x18006c7c5  mov     rcx, [rcx+10h]
0x18006c7c9  call    WPP_SF_qD
0x18006c7ce  lea     rcx, [rbp+var_20]; void *
0x18006c7d2  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x18006c7d7  jmp     loc_18006CB07
0x18006c7dc  mov     rcx, [rbp+var_20]
0x18006c7e0  mov     r8, r15
0x18006c7e3  mov     rdx, rsi
0x18006c7e6  mov     rax, [rcx]
0x18006c7e9  mov     rax, [rax]
0x18006c7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7f1  mov     ebx, eax
0x18006c7f3  test    eax, eax
0x18006c7f5  jns     short loc_18006C7CE
0x18006c7f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c7fe  test    rcx, rcx
0x18006c801  jnz     short loc_18006C84A
0x18006c803  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c80a  nop     dword ptr [rax+rax+00h]
0x18006c80f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c816  mov     rcx, rax
0x18006c819  test    rax, rax
0x18006c81c  jz      short loc_18006C83C
0x18006c81e  mov     rax, [rax]
0x18006c821  mov     edx, 7F0h
0x18006c826  mov     rax, [rax+8]
0x18006c82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c82f  test    eax, eax
0x18006c831  jz      short loc_18006C83C
0x18006c833  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c83a  jmp     short loc_18006C84A
0x18006c83c  lea     rcx, qword_1800EB130; this
0x18006c843  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c84a  cmp     [rcx+8], r12b
0x18006c84e  jz      short loc_18006C875
0x18006c850  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c855  cmp     [rax+7CCh], ebx
0x18006c85b  jz      short loc_18006C875
0x18006c85d  mov     r9d, ebx; int
0x18006c860  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c867  mov     r8d, 181h; int
0x18006c86d  mov     rcx, rax; this
0x18006c870  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c875  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c87c  jb      loc_18006C7CE
0x18006c882  mov     edx, 1Ah
0x18006c887  jmp     loc_18006C7B0
0x18006c88c  mov     r8, r15; void **
0x18006c88f  mov     rdx, rsi; struct _GUID *
0x18006c892  mov     rcx, rdi; this
0x18006c895  call    ?QueryInterface@CDShowSource@@UEAAJAEBU_GUID@@PEAPEAX@Z; CDShowSource::QueryInterface(_GUID const &,void * *)
0x18006c89a  mov     ebx, eax
0x18006c89c  test    eax, eax
0x18006c89e  jns     loc_18006CB07
0x18006c8a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8ab  test    rcx, rcx
0x18006c8ae  jnz     short loc_18006C8F7
0x18006c8b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006c8b7  nop     dword ptr [rax+rax+00h]
0x18006c8bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8c3  mov     rcx, rax
0x18006c8c6  test    rax, rax
0x18006c8c9  jz      short loc_18006C8E9
0x18006c8cb  mov     rax, [rax]
0x18006c8ce  mov     edx, 7F0h
0x18006c8d3  mov     rax, [rax+8]
0x18006c8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8dc  test    eax, eax
0x18006c8de  jz      short loc_18006C8E9
0x18006c8e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8e7  jmp     short loc_18006C8F7
0x18006c8e9  lea     rcx, qword_1800EB130; this
0x18006c8f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006c8f7  cmp     [rcx+8], r12b
0x18006c8fb  jz      short loc_18006C922
0x18006c8fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006c902  cmp     [rax+7CCh], ebx
0x18006c908  jz      short loc_18006C922
0x18006c90a  mov     r9d, ebx; int
0x18006c90d  lea     rdx, aCdshowsourceGe; "CDShowSource::GetService"
0x18006c914  mov     r8d, 175h; int
0x18006c91a  mov     rcx, rax; this
0x18006c91d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006c922  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c929  jb      loc_18006CB07
0x18006c92f  mov     edx, 18h
0x18006c934  jmp     loc_18006CAE9
0x18006c939  mov     rdx, r12
0x18006c93c  lea     rcx, MF_PROPERTY_HANDLER_SERVICE
0x18006c943  call    __
0x18006c948  xor     r14d, r14d
0x18006c94b  test    al, al
0x18006c94d  jz      loc_18006CA58
0x18006c953  mov     rdx, rsi
0x18006c956  lea     rcx, IID_IPropertyStore
0x18006c95d  call    __
0x18006c962  test    al, al
  ... truncated ...
```
