# CMP3BytewiseMediaSource::CreateMetadataPropertyStore(void)

- ea: `0x180154ffc`
- end: `0x180155634`
- name: `?CreateMetadataPropertyStore@CMP3BytewiseMediaSource@@IEAAJXZ`
- size: `1592`
- prototype: `__int64 __fastcall(CMP3BytewiseMediaSource *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004dfb0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180110ed0`
- `0x180154ffc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801550ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801551a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015525c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015530d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801553d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180155483`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180155537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801550ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801551a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015525c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015530d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801553d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180155483`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180155537`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801553af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801553af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801555d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801555d5`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1801552eb`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1801552eb`

## string_xrefs

- `0x180155029`: `CMP3BytewiseMediaSource::CreateMetadataPropertyStore`

## pseudocode

```c
__int64 __fastcall CMP3BytewiseMediaSource::CreateMetadataPropertyStore(CMP3BytewiseMediaSource *this)
{
  HRESULT v2; // esi
  __int64 v3; // rdx
  wchar_t *v4; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v6; // ebx
  __int128 *v7; // rax
  __int128 v8; // xmm0
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // r9
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
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
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  _BYTE v38[8]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v39[16]; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR pszFile; // [rsp+48h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-30h] BYREF
  int v42; // [rsp+58h] [rbp-28h] BYREF
  __int64 v43; // [rsp+60h] [rbp-20h] BYREF
  IStream *ppstm; // [rsp+68h] [rbp-18h] BYREF

  v2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v38,
    "CMP3BytewiseMediaSource::CreateMetadataPropertyStore",
    383);
  v4 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 139) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
    v7 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 139) + 280LL))(
                       *((_QWORD *)this + 139),
                       v39);
    v4 = (wchar_t *)CallStackTracing::s_wpInstance;
    v8 = *v7;
    *((_DWORD *)ThreadRelativeContext + 504) = v6;
    *((_OWORD *)ThreadRelativeContext + 125) = v8;
  }
  ppv = 0;
  ppstm = 0;
  v43 = 0;
  pszFile = 0;
  v42 = 0;
  if ( !*((_QWORD *)this + 138) )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 90);
    if ( v9 )
    {
      v2 = (**v9)(*((_QWORD *)this + 90), &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, &v43);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, const IID *, LPCWSTR *, int *))(*(_QWORD *)v43 + 104LL))(
               v43,
               &MF_BYTESTREAM_ORIGIN_NAME,
               &pszFile,
               &v42);
        if ( v2 >= 0 )
        {
          v2 = SHCreateStreamOnFileW(pszFile, 0, &ppstm);
          if ( v2 >= 0 )
          {
            v2 = CoCreateInstance(&CLSID_MFMP3PropertyHandler, 0, 1u, &GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f, &ppv);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(LPVOID, IStream *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, ppstm, 0);
              if ( v2 >= 0 )
              {
                v2 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(
                       ppv,
                       &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                       (char *)this + 1104);
                if ( v2 < 0 )
                {
                  v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
                    CallStackTracing::s_wpInstance = v35;
                    if ( v35
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                    {
                      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v34 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v34 + 8) )
                  {
                    v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                    if ( *((_DWORD *)v36 + 499) != v2 )
                      CallStackContext::TraceFailure(
                        v36,
                        "CMP3BytewiseMediaSource::CreateMetadataPropertyStore",
                        415,
                        v2);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 40;
                    goto LABEL_82;
                  }
                }
              }
              else
              {
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
                  v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                  if ( *((_DWORD *)v32 + 499) != v2 )
                    CallStackContext::TraceFailure(v32, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 413, v2);
                }
                if ( g_wppLevels )
                {
                  v12 = 39;
                  goto LABEL_82;
                }
              }
            }
            else
            {
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
                if ( *((_DWORD *)v28 + 499) != v2 )
                  CallStackContext::TraceFailure(v28, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 411, v2);
              }
              if ( g_wppLevels )
              {
                v12 = 38;
                goto LABEL_82;
              }
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
              if ( *((_DWORD *)v24 + 499) != v2 )
                CallStackContext::TraceFailure(v24, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 409, v2);
            }
            if ( g_wppLevels )
            {
              v12 = 37;
              goto LABEL_82;
            }
          }
        }
        else
        {
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
            if ( *((_DWORD *)v20 + 499) != v2 )
              CallStackContext::TraceFailure(v20, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 403, v2);
          }
          if ( g_wppLevels )
          {
            v12 = 36;
            goto LABEL_82;
          }
        }
      }
      else
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v2 )
            CallStackContext::TraceFailure(v16, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 401, v2);
        }
        if ( g_wppLevels )
        {
          v12 = 35;
          goto LABEL_82;
        }
      }
    }
    else
    {
      v2 = -2147418113;
      if ( !v4 )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v4 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v4 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v4 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
        if ( *((_DWORD *)v11 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v11, "CMP3BytewiseMediaSource::CreateMetadataPropertyStore", 399, -2147418113);
      }
      if ( g_wppLevels )
      {
        v12 = 34;
LABEL_82:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids, this, v2);
      }
    }
  }
  CoTaskMemFree((LPVOID)pszFile);
  pszFile = 0;
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v43);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppstm);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppv);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180154ffc  mov     [rsp-28h+arg_8], rbx
0x180155001  mov     [rsp-28h+arg_10], rsi
0x180155006  push    rbp
0x180155007  push    rdi
0x180155008  push    r12
0x18015500a  push    r14
0x18015500c  push    r15
0x18015500e  mov     rbp, rsp
0x180155011  sub     rsp, 80h
0x180155018  mov     rax, cs:__security_cookie
0x18015501f  xor     rax, rsp
0x180155022  mov     [rbp+var_10], rax
0x180155026  mov     r14, rcx
0x180155029  lea     r12, aCmp3bytewiseme_8; "CMP3BytewiseMediaSource::CreateMetadata"...
0x180155030  xor     r15d, r15d
0x180155033  lea     rcx, [rbp+var_50]; this
0x180155037  mov     rdx, r12; char *
0x18015503a  mov     r8d, 17Fh; int
0x180155040  mov     esi, r15d
0x180155043  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180155048  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18015504f  cmp     [rcx+8], r15b
0x180155053  jz      short loc_1801550B0
0x180155055  cmp     [r14+458h], r15
0x18015505c  jz      short loc_1801550B0
0x18015505e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180155063  mov     rcx, [r14+458h]
0x18015506a  mov     rdi, rax
0x18015506d  mov     rax, [rcx]
0x180155070  mov     rax, [rax+128h]
0x180155077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015507c  mov     rcx, [r14+458h]
0x180155083  lea     rdx, [rbp+var_48]
0x180155087  mov     ebx, eax
0x180155089  mov     rax, [rcx]
0x18015508c  mov     rax, [rax+118h]
0x180155093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155098  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015509f  movups  xmm0, xmmword ptr [rax]
0x1801550a2  mov     [rdi+7E0h], ebx
0x1801550a8  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801550b0  lea     rbx, [r14+450h]
0x1801550b7  mov     [rbp+var_30], r15
0x1801550bb  mov     [rbp+ppstm], r15
0x1801550bf  mov     [rbp+var_20], r15
0x1801550c3  mov     [rbp+pszFile], r15
0x1801550c7  mov     [rbp+var_28], r15d
0x1801550cb  cmp     [rbx], r15
0x1801550ce  jnz     loc_1801555D1
0x1801550d4  mov     r9, [r14+2D0h]
0x1801550db  test    r9, r9
0x1801550de  jnz     loc_180155173
0x1801550e4  mov     esi, 8000FFFFh
0x1801550e9  test    rcx, rcx
0x1801550ec  jnz     short loc_180155135
0x1801550ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801550f5  nop     dword ptr [rax+rax+00h]
0x1801550fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180155101  mov     rcx, rax
0x180155104  test    rax, rax
0x180155107  jz      short loc_180155127
0x180155109  mov     rax, [rax]
0x18015510c  mov     edx, 7F0h
0x180155111  mov     rax, [rax+8]
0x180155115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015511a  test    eax, eax
0x18015511c  jz      short loc_180155127
0x18015511e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155125  jmp     short loc_180155135
0x180155127  lea     rcx, qword_1801B97E0; this
0x18015512e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180155135  cmp     [rcx+8], r15b
0x180155139  jz      short loc_18015515C
0x18015513b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180155140  cmp     [rax+7CCh], esi
0x180155146  jz      short loc_18015515C
0x180155148  mov     r9d, esi; int
0x18015514b  mov     r8d, 18Fh; int
0x180155151  mov     rdx, r12; char *
0x180155154  mov     rcx, rax; this
0x180155157  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015515c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180155163  jb      loc_1801555D1
0x180155169  mov     edx, 22h ; '"'
0x18015516e  jmp     loc_1801555B3
0x180155173  mov     rax, [r9]
0x180155176  lea     r8, [rbp+var_20]
0x18015517a  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x180155181  mov     rcx, r9
0x180155184  mov     rax, [rax]
0x180155187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015518c  mov     esi, eax
0x18015518e  test    eax, eax
0x180155190  jns     loc_180155227
0x180155196  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015519d  test    rcx, rcx
0x1801551a0  jnz     short loc_1801551E9
0x1801551a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801551a9  nop     dword ptr [rax+rax+00h]
0x1801551ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801551b5  mov     rcx, rax
0x1801551b8  test    rax, rax
0x1801551bb  jz      short loc_1801551DB
0x1801551bd  mov     rax, [rax]
0x1801551c0  mov     edx, 7F0h
0x1801551c5  mov     rax, [rax+8]
0x1801551c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801551ce  test    eax, eax
0x1801551d0  jz      short loc_1801551DB
0x1801551d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801551d9  jmp     short loc_1801551E9
0x1801551db  lea     rcx, qword_1801B97E0; this
0x1801551e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801551e9  cmp     [rcx+8], r15b
0x1801551ed  jz      short loc_180155210
0x1801551ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801551f4  cmp     [rax+7CCh], esi
0x1801551fa  jz      short loc_180155210
0x1801551fc  mov     r9d, esi; int
0x1801551ff  mov     r8d, 191h; int
0x180155205  mov     rdx, r12; char *
0x180155208  mov     rcx, rax; this
0x18015520b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180155210  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180155217  jb      loc_1801555D1
0x18015521d  mov     edx, 23h ; '#'
0x180155222  jmp     loc_1801555B3
0x180155227  mov     rcx, [rbp+var_20]
0x18015522b  lea     r9, [rbp+var_28]
0x18015522f  lea     r8, [rbp+pszFile]
0x180155233  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x18015523a  mov     rax, [rcx]
0x18015523d  mov     rax, [rax+68h]
0x180155241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155246  mov     esi, eax
0x180155248  test    eax, eax
0x18015524a  jns     loc_1801552E1
0x180155250  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155257  test    rcx, rcx
0x18015525a  jnz     short loc_1801552A3
0x18015525c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180155263  nop     dword ptr [rax+rax+00h]
0x180155268  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015526f  mov     rcx, rax
0x180155272  test    rax, rax
0x180155275  jz      short loc_180155295
0x180155277  mov     rax, [rax]
0x18015527a  mov     edx, 7F0h
0x18015527f  mov     rax, [rax+8]
0x180155283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155288  test    eax, eax
0x18015528a  jz      short loc_180155295
0x18015528c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155293  jmp     short loc_1801552A3
0x180155295  lea     rcx, qword_1801B97E0; this
0x18015529c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801552a3  cmp     [rcx+8], r15b
0x1801552a7  jz      short loc_1801552CA
0x1801552a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801552ae  cmp     [rax+7CCh], esi
0x1801552b4  jz      short loc_1801552CA
0x1801552b6  mov     r9d, esi; int
0x1801552b9  mov     r8d, 193h; int
0x1801552bf  mov     rdx, r12; char *
0x1801552c2  mov     rcx, rax; this
0x1801552c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801552ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801552d1  jb      loc_1801555D1
0x1801552d7  mov     edx, 24h ; '$'
0x1801552dc  jmp     loc_1801555B3
0x1801552e1  mov     rcx, [rbp+pszFile]; pszFile
0x1801552e5  lea     r8, [rbp+ppstm]; ppstm
0x1801552e9  xor     edx, edx; grfMode
0x1801552eb  call    cs:__imp_SHCreateStreamOnFileW
0x1801552f2  nop     dword ptr [rax+rax+00h]
0x1801552f7  mov     esi, eax
0x1801552f9  test    eax, eax
0x1801552fb  jns     loc_180155392
0x180155301  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155308  test    rcx, rcx
0x18015530b  jnz     short loc_180155354
0x18015530d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180155314  nop     dword ptr [rax+rax+00h]
0x180155319  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180155320  mov     rcx, rax
0x180155323  test    rax, rax
0x180155326  jz      short loc_180155346
0x180155328  mov     rax, [rax]
0x18015532b  mov     edx, 7F0h
0x180155330  mov     rax, [rax+8]
0x180155334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155339  test    eax, eax
0x18015533b  jz      short loc_180155346
0x18015533d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155344  jmp     short loc_180155354
0x180155346  lea     rcx, qword_1801B97E0; this
0x18015534d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180155354  cmp     [rcx+8], r15b
0x180155358  jz      short loc_18015537B
0x18015535a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015535f  cmp     [rax+7CCh], esi
0x180155365  jz      short loc_18015537B
0x180155367  mov     r9d, esi; int
0x18015536a  mov     r8d, 199h; int
0x180155370  mov     rdx, r12; char *
0x180155373  mov     rcx, rax; this
0x180155376  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015537b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180155382  jb      loc_1801555D1
0x180155388  mov     edx, 25h ; '%'
0x18015538d  jmp     loc_1801555B3
0x180155392  xor     edx, edx; pUnkOuter
0x180155394  lea     rax, [rbp+var_30]
0x180155398  lea     r9, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f; riid
0x18015539f  mov     [rsp+80h+ppv], rax; ppv
0x1801553a4  lea     rcx, CLSID_MFMP3PropertyHandler; rclsid
0x1801553ab  lea     r8d, [rdx+1]; dwClsContext
0x1801553af  call    cs:__imp_CoCreateInstance
0x1801553b6  nop     dword ptr [rax+rax+00h]
0x1801553bb  mov     esi, eax
0x1801553bd  test    eax, eax
0x1801553bf  jns     loc_180155456
0x1801553c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801553cc  test    rcx, rcx
0x1801553cf  jnz     short loc_180155418
0x1801553d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801553d8  nop     dword ptr [rax+rax+00h]
0x1801553dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801553e4  mov     rcx, rax
0x1801553e7  test    rax, rax
0x1801553ea  jz      short loc_18015540A
0x1801553ec  mov     rax, [rax]
0x1801553ef  mov     edx, 7F0h
0x1801553f4  mov     rax, [rax+8]
0x1801553f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801553fd  test    eax, eax
0x1801553ff  jz      short loc_18015540A
0x180155401  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180155408  jmp     short loc_180155418
0x18015540a  lea     rcx, qword_1801B97E0; this
0x180155411  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180155418  cmp     [rcx+8], r15b
0x18015541c  jz      short loc_18015543F
0x18015541e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180155423  cmp     [rax+7CCh], esi
0x180155429  jz      short loc_18015543F
0x18015542b  mov     r9d, esi; int
0x18015542e  mov     r8d, 19Bh; int
0x180155434  mov     rdx, r12; char *
0x180155437  mov     rcx, rax; this
0x18015543a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015543f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180155446  jb      loc_1801555D1
0x18015544c  mov     edx, 26h ; '&'
0x180155451  jmp     loc_1801555B3
0x180155456  mov     rcx, [rbp+var_30]
0x18015545a  xor     r8d, r8d
0x18015545d  mov     rdx, [rbp+ppstm]
0x180155461  mov     rax, [rcx]
0x180155464  mov     rax, [rax+18h]
0x180155468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015546d  mov     esi, eax
0x18015546f  test    eax, eax
0x180155471  jns     loc_180155508
0x180155477  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015547e  test    rcx, rcx
0x180155481  jnz     short loc_1801554CA
0x180155483  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015548a  nop     dword ptr [rax+rax+00h]
0x18015548f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180155496  mov     rcx, rax
0x180155499  test    rax, rax
0x18015549c  jz      short loc_1801554BC
0x18015549e  mov     rax, [rax]
0x1801554a1  mov     edx, 7F0h
0x1801554a6  mov     rax, [rax+8]
0x1801554aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801554af  test    eax, eax
0x1801554b1  jz      short loc_1801554BC
0x1801554b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801554ba  jmp     short loc_1801554CA
0x1801554bc  lea     rcx, qword_1801B97E0; this
0x1801554c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801554ca  cmp     [rcx+8], r15b
0x1801554ce  jz      short loc_1801554F1
0x1801554d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801554d5  cmp     [rax+7CCh], esi
0x1801554db  jz      short loc_1801554F1
0x1801554dd  mov     r9d, esi; int
0x1801554e0  mov     r8d, 19Dh; int
0x1801554e6  mov     rdx, r12; char *
0x1801554e9  mov     rcx, rax; this
0x1801554ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801554f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801554f8  jb      loc_1801555D1
0x1801554fe  mov     edx, 27h ; '''
0x180155503  jmp     loc_1801555B3
0x180155508  mov     rcx, [rbp+var_30]
0x18015550c  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180155513  mov     r8, rbx
  ... truncated ...
```
