# CMP3BytewiseMediaSource::CreateMetadataPropertyStore(void)

- ea: `0x18014cbec`
- end: `0x18014d1e7`
- name: `?CreateMetadataPropertyStore@CMP3BytewiseMediaSource@@IEAAJXZ`
- size: `1531`
- prototype: `__int64 __fastcall(CMP3BytewiseMediaSource *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a630`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1801099f0`
- `0x18014cbec`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ccde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cd8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ce40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cee5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cf9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d0f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ccde`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cd8c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ce40`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cee5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014cf9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d049`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014d0f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014cf81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18014cf81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d18f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014d18f`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18014cec9`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x18014cec9`

## string_xrefs

- `0x18014cc19`: `CMP3BytewiseMediaSource::CreateMetadataPropertyStore`

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
                      v34 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                    v30 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                  v26 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v22 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v18 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v14 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v4 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x18014cbec  mov     [rsp-28h+arg_8], rbx
0x18014cbf1  mov     [rsp-28h+arg_10], rsi
0x18014cbf6  push    rbp
0x18014cbf7  push    rdi
0x18014cbf8  push    r12
0x18014cbfa  push    r14
0x18014cbfc  push    r15
0x18014cbfe  mov     rbp, rsp
0x18014cc01  sub     rsp, 80h
0x18014cc08  mov     rax, cs:__security_cookie
0x18014cc0f  xor     rax, rsp
0x18014cc12  mov     [rbp+var_10], rax
0x18014cc16  mov     r14, rcx
0x18014cc19  lea     r12, aCmp3bytewiseme_8; "CMP3BytewiseMediaSource::CreateMetadata"...
0x18014cc20  xor     r15d, r15d
0x18014cc23  lea     rcx, [rbp+var_50]; this
0x18014cc27  mov     rdx, r12; char *
0x18014cc2a  mov     r8d, 17Fh; int
0x18014cc30  mov     esi, r15d
0x18014cc33  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18014cc38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18014cc3f  cmp     [rcx+8], r15b
0x18014cc43  jz      short loc_18014CCA0
0x18014cc45  cmp     [r14+458h], r15
0x18014cc4c  jz      short loc_18014CCA0
0x18014cc4e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014cc53  mov     rcx, [r14+458h]
0x18014cc5a  mov     rdi, rax
0x18014cc5d  mov     rax, [rcx]
0x18014cc60  mov     rax, [rax+128h]
0x18014cc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cc6c  mov     rcx, [r14+458h]
0x18014cc73  lea     rdx, [rbp+var_48]
0x18014cc77  mov     ebx, eax
0x18014cc79  mov     rax, [rcx]
0x18014cc7c  mov     rax, [rax+118h]
0x18014cc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cc88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cc8f  movups  xmm0, xmmword ptr [rax]
0x18014cc92  mov     [rdi+7E0h], ebx
0x18014cc98  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18014cca0  lea     rbx, [r14+450h]
0x18014cca7  mov     [rbp+var_30], r15
0x18014ccab  mov     [rbp+ppstm], r15
0x18014ccaf  mov     [rbp+var_20], r15
0x18014ccb3  mov     [rbp+pszFile], r15
0x18014ccb7  mov     [rbp+var_28], r15d
0x18014ccbb  cmp     [rbx], r15
0x18014ccbe  jnz     loc_18014D18B
0x18014ccc4  mov     r9, [r14+2D0h]
0x18014cccb  test    r9, r9
0x18014ccce  jnz     loc_18014CD5D
0x18014ccd4  mov     esi, 8000FFFFh
0x18014ccd9  test    rcx, rcx
0x18014ccdc  jnz     short loc_18014CD1F
0x18014ccde  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014cce4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cceb  mov     rcx, rax
0x18014ccee  test    rax, rax
0x18014ccf1  jz      short loc_18014CD11
0x18014ccf3  mov     rax, [rax]
0x18014ccf6  mov     edx, 7F0h
0x18014ccfb  mov     rax, [rax+8]
0x18014ccff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cd04  test    eax, eax
0x18014cd06  jz      short loc_18014CD11
0x18014cd08  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cd0f  jmp     short loc_18014CD1F
0x18014cd11  lea     rcx, qword_1801B07E0; this
0x18014cd18  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cd1f  cmp     [rcx+8], r15b
0x18014cd23  jz      short loc_18014CD46
0x18014cd25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014cd2a  cmp     [rax+7CCh], esi
0x18014cd30  jz      short loc_18014CD46
0x18014cd32  mov     r9d, esi; int
0x18014cd35  mov     r8d, 18Fh; int
0x18014cd3b  mov     rdx, r12; char *
0x18014cd3e  mov     rcx, rax; this
0x18014cd41  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014cd46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014cd4d  jb      loc_18014D18B
0x18014cd53  mov     edx, 22h ; '"'
0x18014cd58  jmp     loc_18014D16D
0x18014cd5d  mov     rax, [r9]
0x18014cd60  lea     r8, [rbp+var_20]
0x18014cd64  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x18014cd6b  mov     rcx, r9
0x18014cd6e  mov     rax, [rax]
0x18014cd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cd76  mov     esi, eax
0x18014cd78  test    eax, eax
0x18014cd7a  jns     loc_18014CE0B
0x18014cd80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cd87  test    rcx, rcx
0x18014cd8a  jnz     short loc_18014CDCD
0x18014cd8c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014cd92  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cd99  mov     rcx, rax
0x18014cd9c  test    rax, rax
0x18014cd9f  jz      short loc_18014CDBF
0x18014cda1  mov     rax, [rax]
0x18014cda4  mov     edx, 7F0h
0x18014cda9  mov     rax, [rax+8]
0x18014cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cdb2  test    eax, eax
0x18014cdb4  jz      short loc_18014CDBF
0x18014cdb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cdbd  jmp     short loc_18014CDCD
0x18014cdbf  lea     rcx, qword_1801B07E0; this
0x18014cdc6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cdcd  cmp     [rcx+8], r15b
0x18014cdd1  jz      short loc_18014CDF4
0x18014cdd3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014cdd8  cmp     [rax+7CCh], esi
0x18014cdde  jz      short loc_18014CDF4
0x18014cde0  mov     r9d, esi; int
0x18014cde3  mov     r8d, 191h; int
0x18014cde9  mov     rdx, r12; char *
0x18014cdec  mov     rcx, rax; this
0x18014cdef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014cdf4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014cdfb  jb      loc_18014D18B
0x18014ce01  mov     edx, 23h ; '#'
0x18014ce06  jmp     loc_18014D16D
0x18014ce0b  mov     rcx, [rbp+var_20]
0x18014ce0f  lea     r9, [rbp+var_28]
0x18014ce13  lea     r8, [rbp+pszFile]
0x18014ce17  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x18014ce1e  mov     rax, [rcx]
0x18014ce21  mov     rax, [rax+68h]
0x18014ce25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce2a  mov     esi, eax
0x18014ce2c  test    eax, eax
0x18014ce2e  jns     loc_18014CEBF
0x18014ce34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ce3b  test    rcx, rcx
0x18014ce3e  jnz     short loc_18014CE81
0x18014ce40  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014ce46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ce4d  mov     rcx, rax
0x18014ce50  test    rax, rax
0x18014ce53  jz      short loc_18014CE73
0x18014ce55  mov     rax, [rax]
0x18014ce58  mov     edx, 7F0h
0x18014ce5d  mov     rax, [rax+8]
0x18014ce61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ce66  test    eax, eax
0x18014ce68  jz      short loc_18014CE73
0x18014ce6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ce71  jmp     short loc_18014CE81
0x18014ce73  lea     rcx, qword_1801B07E0; this
0x18014ce7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ce81  cmp     [rcx+8], r15b
0x18014ce85  jz      short loc_18014CEA8
0x18014ce87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014ce8c  cmp     [rax+7CCh], esi
0x18014ce92  jz      short loc_18014CEA8
0x18014ce94  mov     r9d, esi; int
0x18014ce97  mov     r8d, 193h; int
0x18014ce9d  mov     rdx, r12; char *
0x18014cea0  mov     rcx, rax; this
0x18014cea3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014cea8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014ceaf  jb      loc_18014D18B
0x18014ceb5  mov     edx, 24h ; '$'
0x18014ceba  jmp     loc_18014D16D
0x18014cebf  mov     rcx, [rbp+pszFile]; pszFile
0x18014cec3  lea     r8, [rbp+ppstm]; ppstm
0x18014cec7  xor     edx, edx; grfMode
0x18014cec9  call    cs:__imp_SHCreateStreamOnFileW
0x18014cecf  mov     esi, eax
0x18014ced1  test    eax, eax
0x18014ced3  jns     loc_18014CF64
0x18014ced9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cee0  test    rcx, rcx
0x18014cee3  jnz     short loc_18014CF26
0x18014cee5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014ceeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cef2  mov     rcx, rax
0x18014cef5  test    rax, rax
0x18014cef8  jz      short loc_18014CF18
0x18014cefa  mov     rax, [rax]
0x18014cefd  mov     edx, 7F0h
0x18014cf02  mov     rax, [rax+8]
0x18014cf06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cf0b  test    eax, eax
0x18014cf0d  jz      short loc_18014CF18
0x18014cf0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cf16  jmp     short loc_18014CF26
0x18014cf18  lea     rcx, qword_1801B07E0; this
0x18014cf1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cf26  cmp     [rcx+8], r15b
0x18014cf2a  jz      short loc_18014CF4D
0x18014cf2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014cf31  cmp     [rax+7CCh], esi
0x18014cf37  jz      short loc_18014CF4D
0x18014cf39  mov     r9d, esi; int
0x18014cf3c  mov     r8d, 199h; int
0x18014cf42  mov     rdx, r12; char *
0x18014cf45  mov     rcx, rax; this
0x18014cf48  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014cf4d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014cf54  jb      loc_18014D18B
0x18014cf5a  mov     edx, 25h ; '%'
0x18014cf5f  jmp     loc_18014D16D
0x18014cf64  xor     edx, edx; pUnkOuter
0x18014cf66  lea     rax, [rbp+var_30]
0x18014cf6a  lea     r9, _GUID_b824b49d_22ac_4161_ac8a_9916e8fa3f7f; riid
0x18014cf71  mov     [rsp+80h+ppv], rax; ppv
0x18014cf76  lea     rcx, CLSID_MFMP3PropertyHandler; rclsid
0x18014cf7d  lea     r8d, [rdx+1]; dwClsContext
0x18014cf81  call    cs:__imp_CoCreateInstance
0x18014cf87  mov     esi, eax
0x18014cf89  test    eax, eax
0x18014cf8b  jns     loc_18014D01C
0x18014cf91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cf98  test    rcx, rcx
0x18014cf9b  jnz     short loc_18014CFDE
0x18014cf9d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014cfa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cfaa  mov     rcx, rax
0x18014cfad  test    rax, rax
0x18014cfb0  jz      short loc_18014CFD0
0x18014cfb2  mov     rax, [rax]
0x18014cfb5  mov     edx, 7F0h
0x18014cfba  mov     rax, [rax+8]
0x18014cfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cfc3  test    eax, eax
0x18014cfc5  jz      short loc_18014CFD0
0x18014cfc7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cfce  jmp     short loc_18014CFDE
0x18014cfd0  lea     rcx, qword_1801B07E0; this
0x18014cfd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014cfde  cmp     [rcx+8], r15b
0x18014cfe2  jz      short loc_18014D005
0x18014cfe4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014cfe9  cmp     [rax+7CCh], esi
0x18014cfef  jz      short loc_18014D005
0x18014cff1  mov     r9d, esi; int
0x18014cff4  mov     r8d, 19Bh; int
0x18014cffa  mov     rdx, r12; char *
0x18014cffd  mov     rcx, rax; this
0x18014d000  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014d005  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014d00c  jb      loc_18014D18B
0x18014d012  mov     edx, 26h ; '&'
0x18014d017  jmp     loc_18014D16D
0x18014d01c  mov     rcx, [rbp+var_30]
0x18014d020  xor     r8d, r8d
0x18014d023  mov     rdx, [rbp+ppstm]
0x18014d027  mov     rax, [rcx]
0x18014d02a  mov     rax, [rax+18h]
0x18014d02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d033  mov     esi, eax
0x18014d035  test    eax, eax
0x18014d037  jns     loc_18014D0C8
0x18014d03d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d044  test    rcx, rcx
0x18014d047  jnz     short loc_18014D08A
0x18014d049  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014d04f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d056  mov     rcx, rax
0x18014d059  test    rax, rax
0x18014d05c  jz      short loc_18014D07C
0x18014d05e  mov     rax, [rax]
0x18014d061  mov     edx, 7F0h
0x18014d066  mov     rax, [rax+8]
0x18014d06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d06f  test    eax, eax
0x18014d071  jz      short loc_18014D07C
0x18014d073  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d07a  jmp     short loc_18014D08A
0x18014d07c  lea     rcx, qword_1801B07E0; this
0x18014d083  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d08a  cmp     [rcx+8], r15b
0x18014d08e  jz      short loc_18014D0B1
0x18014d090  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014d095  cmp     [rax+7CCh], esi
0x18014d09b  jz      short loc_18014D0B1
0x18014d09d  mov     r9d, esi; int
0x18014d0a0  mov     r8d, 19Dh; int
0x18014d0a6  mov     rdx, r12; char *
0x18014d0a9  mov     rcx, rax; this
0x18014d0ac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014d0b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014d0b8  jb      loc_18014D18B
0x18014d0be  mov     edx, 27h ; '''
0x18014d0c3  jmp     loc_18014D16D
0x18014d0c8  mov     rcx, [rbp+var_30]
0x18014d0cc  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18014d0d3  mov     r8, rbx
0x18014d0d6  mov     rax, [rcx]
0x18014d0d9  mov     rax, [rax]
0x18014d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d0e1  mov     esi, eax
0x18014d0e3  test    eax, eax
0x18014d0e5  jns     loc_18014D18B
0x18014d0eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014d0f2  test    rcx, rcx
  ... truncated ...
```
