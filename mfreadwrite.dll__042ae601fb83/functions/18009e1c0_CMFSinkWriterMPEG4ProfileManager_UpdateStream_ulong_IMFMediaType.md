# CMFSinkWriterMPEG4ProfileManager::UpdateStream(ulong,IMFMediaType *)

- ea: `0x18009e1c0`
- end: `0x18009e793`
- name: `?UpdateStream@CMFSinkWriterMPEG4ProfileManager@@UEAAJKPEAUIMFMediaType@@@Z`
- size: `1491`
- prototype: `__int64 __fastcall(CMFSinkWriterMPEG4ProfileManager *__hidden this, unsigned int, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x1800252a0`
- `0x18009e1c0`
- `0x1800db3a0`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e31f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e6fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e31f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e452`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e591`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e2b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e3e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e695`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e2a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e3d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e518`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e685`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e2a6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e3d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e518`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009e685`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e37e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e3ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e4bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e53e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e6ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e37e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e3ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e4bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e53e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e62a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009e6ab`
- `MFPlat!MFCreateMediaType` at `0x18009e35d`
- `MFPlat!MFCreateMediaType` at `0x18009e35d`

## string_xrefs

- `0x18009e1eb`: `CMFSinkWriterMPEG4ProfileManager::UpdateStream`

## pseudocode

```c
__int64 __fastcall CMFSinkWriterMPEG4ProfileManager::UpdateStream(
        CMFSinkWriterMPEG4ProfileManager *this,
        unsigned int a2,
        struct IMFMediaType *a3)
{
  __int64 v4; // rdi
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetGUID)(IMFMediaType *, const GUID *const, GUID *); // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  HRESULT v10; // ebx
  CallStackTracing *v11; // rdi
  CallStackTracing *v12; // rax
  CallStackContext *v13; // rbp
  DWORD v14; // r15d
  CallStackContext *v15; // rax
  __int64 v16; // rdx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  CallStackTracing *v23; // rdi
  CallStackTracing *v24; // rax
  CallStackContext *v25; // rbp
  DWORD v26; // r15d
  CallStackContext *v27; // rax
  __int64 v28; // rdx
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  CallStackTracing *v34; // rdi
  CallStackTracing *v35; // rax
  CallStackContext *v36; // rbp
  DWORD v37; // r15d
  CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  IMFMediaType *v44; // rcx
  __int64 v45; // rax
  CallStackTracing *v46; // rdi
  CallStackTracing *v47; // rax
  CallStackContext *v48; // rbp
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v51; // rdx
  CallStackTracing *v52; // rcx
  CallStackTracing *v53; // rax
  __int64 v54; // rax
  char v56[8]; // [rsp+30h] [rbp-68h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-60h] BYREF
  __int128 v58; // [rsp+40h] [rbp-58h] BYREF

  v4 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v56,
    "CMFSinkWriterMPEG4ProfileManager::UpdateStream",
    935);
  lpVtbl = a3->lpVtbl;
  ppMFType = 0;
  GetGUID = lpVtbl->GetGUID;
  v58 = 0;
  v10 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, __int128 *))GetGUID)(a3, &MF_MT_MAJOR_TYPE, &v58);
  if ( v10 >= 0 )
  {
    v10 = MFCreateMediaType(&ppMFType);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a3->lpVtbl->CopyAllItems)(a3, ppMFType);
      if ( v10 >= 0 )
      {
        if ( (unsigned int)v4 < *((_DWORD *)this + 12) && (_DWORD)v4 )
        {
          if ( *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v4) )
          {
            _mm_lfence();
            v43 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v4);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v4) = 0;
          }
          v44 = ppMFType;
          v45 = *((_QWORD *)this + 5);
          ppMFType = 0;
          *(_QWORD *)(v45 + 8 * v4) = v44;
        }
        else
        {
          v46 = CallStackTracing::s_wpInstance;
          v10 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v33, v32);
            CallStackTracing::s_wpInstance = v47;
            if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
            {
              v46 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v46 + 8) )
          {
            v48 = (CallStackTracing *)((char *)v46 + 208);
            LastError = GetLastError();
            Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v46 + 3));
            if ( Value )
            {
              v48 = Value;
            }
            else if ( !GetLastError() )
            {
              v52 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                {
                  v52 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v52 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v54 = (**(__int64 (__fastcall ***)(CallStackTracing *))v52)(v52);
              if ( v54 )
                v48 = (CallStackContext *)v54;
            }
            SetLastError(LastError);
            if ( *((_DWORD *)v48 + 499) != -2147418113 )
              CallStackContext::TraceFailure(v48, "CMFSinkWriterMPEG4ProfileManager::UpdateStream", 949, -2147418113);
          }
          if ( g_wppLevels )
          {
            v20 = 91;
            goto LABEL_89;
          }
        }
      }
      else
      {
        v34 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v33, v32);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = (CallStackTracing *)((char *)v34 + 208);
          v37 = GetLastError();
          v38 = (CallStackContext *)TlsGetValue(*((_DWORD *)v34 + 3));
          if ( v38 )
          {
            v36 = v38;
          }
          else if ( !GetLastError() )
          {
            v40 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
              CallStackTracing::s_wpInstance = v41;
              if ( v41
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
              {
                v40 = CallStackTracing::s_wpInstance;
              }
              else
              {
                v40 = (CallStackTracing *)&qword_18010C230;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
              }
            }
            v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
            if ( v42 )
              v36 = (CallStackContext *)v42;
          }
          SetLastError(v37);
          if ( *((_DWORD *)v36 + 499) != v10 )
            CallStackContext::TraceFailure(v36, "CMFSinkWriterMPEG4ProfileManager::UpdateStream", 944, v10);
        }
        if ( g_wppLevels )
        {
          v20 = 90;
          goto LABEL_89;
        }
      }
    }
    else
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v22, v21);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = (CallStackTracing *)((char *)v23 + 208);
        v26 = GetLastError();
        v27 = (CallStackContext *)TlsGetValue(*((_DWORD *)v23 + 3));
        if ( v27 )
        {
          v25 = v27;
        }
        else if ( !GetLastError() )
        {
          v29 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
            CallStackTracing::s_wpInstance = v30;
            if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
            {
              v29 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v29 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v29)(v29);
          if ( v31 )
            v25 = (CallStackContext *)v31;
        }
        SetLastError(v26);
        if ( *((_DWORD *)v25 + 499) != v10 )
          CallStackContext::TraceFailure(v25, "CMFSinkWriterMPEG4ProfileManager::UpdateStream", 942, v10);
      }
      if ( g_wppLevels )
      {
        v20 = 89;
        goto LABEL_89;
      }
    }
  }
  else
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = (CallStackTracing *)((char *)v11 + 208);
      v14 = GetLastError();
      v15 = (CallStackContext *)TlsGetValue(*((_DWORD *)v11 + 3));
      if ( v15 )
      {
        v13 = v15;
      }
      else if ( !GetLastError() )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v19 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
        if ( v19 )
          v13 = (CallStackContext *)v19;
      }
      SetLastError(v14);
      if ( *((_DWORD *)v13 + 499) != v10 )
        CallStackContext::TraceFailure(v13, "CMFSinkWriterMPEG4ProfileManager::UpdateStream", 940, v10);
    }
    if ( g_wppLevels )
    {
      v20 = 88;
LABEL_89:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_cb88a1e5dded39afaa094c6f3342a822_Traceguids, this, v10);
    }
  }
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18009e1c0  mov     [rsp+arg_18], rbx
0x18009e1c5  push    rbp
0x18009e1c6  push    rsi
0x18009e1c7  push    rdi
0x18009e1c8  push    r12
0x18009e1ca  push    r13
0x18009e1cc  push    r14
0x18009e1ce  push    r15
0x18009e1d0  sub     rsp, 60h
0x18009e1d4  mov     rax, cs:__security_cookie
0x18009e1db  xor     rax, rsp
0x18009e1de  mov     [rsp+98h+var_48], rax
0x18009e1e3  mov     rsi, r8
0x18009e1e6  mov     edi, edx
0x18009e1e8  mov     r14, rcx
0x18009e1eb  lea     r13, aCmfsinkwriterm_15; "CMFSinkWriterMPEG4ProfileManager::Updat"...
0x18009e1f2  mov     rdx, r13; char *
0x18009e1f5  lea     rcx, [rsp+98h+var_68]; this
0x18009e1fa  mov     r8d, 3A7h; int
0x18009e200  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009e205  mov     rax, [rsi]
0x18009e208  lea     r8, [rsp+98h+var_58]
0x18009e20d  xorps   xmm0, xmm0
0x18009e210  lea     rdx, MF_MT_MAJOR_TYPE
0x18009e217  xor     r12d, r12d
0x18009e21a  mov     rcx, rsi
0x18009e21d  mov     [rsp+98h+ppMFType], r12
0x18009e222  mov     rax, [rax+50h]
0x18009e226  movups  [rsp+98h+var_58], xmm0
0x18009e22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e230  mov     ebx, eax
0x18009e232  test    eax, eax
0x18009e234  jns     loc_18009E358
0x18009e23a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e241  mov     esi, 7F0h
0x18009e246  test    rdi, rdi
0x18009e249  jnz     short loc_18009E289
0x18009e24b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e251  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e258  mov     rcx, rax
0x18009e25b  test    rax, rax
0x18009e25e  jz      short loc_18009E27B
0x18009e260  mov     rax, [rax]
0x18009e263  mov     edx, esi
0x18009e265  mov     rax, [rax+8]
0x18009e269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e26e  test    eax, eax
0x18009e270  jz      short loc_18009E27B
0x18009e272  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e279  jmp     short loc_18009E289
0x18009e27b  lea     rdi, qword_18010C230
0x18009e282  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e289  cmp     [rdi+8], r12b
0x18009e28d  jz      loc_18009E341
0x18009e293  lea     rbp, [rdi+0D0h]
0x18009e29a  call    cs:__imp_GetLastError
0x18009e2a0  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009e2a3  mov     r15d, eax
0x18009e2a6  call    cs:__imp_TlsGetValue
0x18009e2ac  test    rax, rax
0x18009e2af  jz      short loc_18009E2B6
0x18009e2b1  mov     rbp, rax
0x18009e2b4  jmp     short loc_18009E31C
0x18009e2b6  call    cs:__imp_GetLastError
0x18009e2bc  test    eax, eax
0x18009e2be  jnz     short loc_18009E31C
0x18009e2c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e2c7  test    rcx, rcx
0x18009e2ca  jnz     short loc_18009E30A
0x18009e2cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e2d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e2d9  mov     rcx, rax
0x18009e2dc  test    rax, rax
0x18009e2df  jz      short loc_18009E2FC
0x18009e2e1  mov     rax, [rax]
0x18009e2e4  mov     edx, esi
0x18009e2e6  mov     rax, [rax+8]
0x18009e2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e2ef  test    eax, eax
0x18009e2f1  jz      short loc_18009E2FC
0x18009e2f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e2fa  jmp     short loc_18009E30A
0x18009e2fc  lea     rcx, qword_18010C230
0x18009e303  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e30a  mov     rax, [rcx]
0x18009e30d  mov     rax, [rax]
0x18009e310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e315  test    rax, rax
0x18009e318  cmovnz  rbp, rax
0x18009e31c  mov     ecx, r15d; dwErrCode
0x18009e31f  call    cs:__imp_SetLastError
0x18009e325  cmp     [rbp+7CCh], ebx
0x18009e32b  jz      short loc_18009E341
0x18009e32d  mov     r9d, ebx; int
0x18009e330  mov     r8d, 3ACh; int
0x18009e336  mov     rdx, r13; char *
0x18009e339  mov     rcx, rbp; this
0x18009e33c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e341  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e348  jb      loc_18009E74C
0x18009e34e  mov     edx, 58h ; 'X'
0x18009e353  jmp     loc_18009E72E
0x18009e358  lea     rcx, [rsp+98h+ppMFType]; ppMFType
0x18009e35d  call    cs:__imp_MFCreateMediaType
0x18009e363  mov     ebx, eax
0x18009e365  test    eax, eax
0x18009e367  jns     loc_18009E48B
0x18009e36d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e374  mov     esi, 7F0h
0x18009e379  test    rdi, rdi
0x18009e37c  jnz     short loc_18009E3BC
0x18009e37e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e384  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e38b  mov     rcx, rax
0x18009e38e  test    rax, rax
0x18009e391  jz      short loc_18009E3AE
0x18009e393  mov     rax, [rax]
0x18009e396  mov     edx, esi
0x18009e398  mov     rax, [rax+8]
0x18009e39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e3a1  test    eax, eax
0x18009e3a3  jz      short loc_18009E3AE
0x18009e3a5  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e3ac  jmp     short loc_18009E3BC
0x18009e3ae  lea     rdi, qword_18010C230
0x18009e3b5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e3bc  cmp     [rdi+8], r12b
0x18009e3c0  jz      loc_18009E474
0x18009e3c6  lea     rbp, [rdi+0D0h]
0x18009e3cd  call    cs:__imp_GetLastError
0x18009e3d3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009e3d6  mov     r15d, eax
0x18009e3d9  call    cs:__imp_TlsGetValue
0x18009e3df  test    rax, rax
0x18009e3e2  jz      short loc_18009E3E9
0x18009e3e4  mov     rbp, rax
0x18009e3e7  jmp     short loc_18009E44F
0x18009e3e9  call    cs:__imp_GetLastError
0x18009e3ef  test    eax, eax
0x18009e3f1  jnz     short loc_18009E44F
0x18009e3f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e3fa  test    rcx, rcx
0x18009e3fd  jnz     short loc_18009E43D
0x18009e3ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e405  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e40c  mov     rcx, rax
0x18009e40f  test    rax, rax
0x18009e412  jz      short loc_18009E42F
0x18009e414  mov     rax, [rax]
0x18009e417  mov     edx, esi
0x18009e419  mov     rax, [rax+8]
0x18009e41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e422  test    eax, eax
0x18009e424  jz      short loc_18009E42F
0x18009e426  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e42d  jmp     short loc_18009E43D
0x18009e42f  lea     rcx, qword_18010C230
0x18009e436  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e43d  mov     rax, [rcx]
0x18009e440  mov     rax, [rax]
0x18009e443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e448  test    rax, rax
0x18009e44b  cmovnz  rbp, rax
0x18009e44f  mov     ecx, r15d; dwErrCode
0x18009e452  call    cs:__imp_SetLastError
0x18009e458  cmp     [rbp+7CCh], ebx
0x18009e45e  jz      short loc_18009E474
0x18009e460  mov     r9d, ebx; int
0x18009e463  mov     r8d, 3AEh; int
0x18009e469  mov     rdx, r13; char *
0x18009e46c  mov     rcx, rbp; this
0x18009e46f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e474  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e47b  jb      loc_18009E74C
0x18009e481  mov     edx, 59h ; 'Y'
0x18009e486  jmp     loc_18009E72E
0x18009e48b  mov     rax, [rsi]
0x18009e48e  mov     rcx, rsi
0x18009e491  mov     rdx, [rsp+98h+ppMFType]
0x18009e496  mov     rax, [rax+100h]
0x18009e49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e4a2  mov     ebx, eax
0x18009e4a4  test    eax, eax
0x18009e4a6  jns     loc_18009E5CA
0x18009e4ac  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e4b3  mov     esi, 7F0h
0x18009e4b8  test    rdi, rdi
0x18009e4bb  jnz     short loc_18009E4FB
0x18009e4bd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e4c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e4ca  mov     rcx, rax
0x18009e4cd  test    rax, rax
0x18009e4d0  jz      short loc_18009E4ED
0x18009e4d2  mov     rax, [rax]
0x18009e4d5  mov     edx, esi
0x18009e4d7  mov     rax, [rax+8]
0x18009e4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e4e0  test    eax, eax
0x18009e4e2  jz      short loc_18009E4ED
0x18009e4e4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e4eb  jmp     short loc_18009E4FB
0x18009e4ed  lea     rdi, qword_18010C230
0x18009e4f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e4fb  cmp     [rdi+8], r12b
0x18009e4ff  jz      loc_18009E5B3
0x18009e505  lea     rbp, [rdi+0D0h]
0x18009e50c  call    cs:__imp_GetLastError
0x18009e512  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009e515  mov     r15d, eax
0x18009e518  call    cs:__imp_TlsGetValue
0x18009e51e  test    rax, rax
0x18009e521  jz      short loc_18009E528
0x18009e523  mov     rbp, rax
0x18009e526  jmp     short loc_18009E58E
0x18009e528  call    cs:__imp_GetLastError
0x18009e52e  test    eax, eax
0x18009e530  jnz     short loc_18009E58E
0x18009e532  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e539  test    rcx, rcx
0x18009e53c  jnz     short loc_18009E57C
0x18009e53e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e544  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e54b  mov     rcx, rax
0x18009e54e  test    rax, rax
0x18009e551  jz      short loc_18009E56E
0x18009e553  mov     rax, [rax]
0x18009e556  mov     edx, esi
0x18009e558  mov     rax, [rax+8]
0x18009e55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e561  test    eax, eax
0x18009e563  jz      short loc_18009E56E
0x18009e565  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e56c  jmp     short loc_18009E57C
0x18009e56e  lea     rcx, qword_18010C230
0x18009e575  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e57c  mov     rax, [rcx]
0x18009e57f  mov     rax, [rax]
0x18009e582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e587  test    rax, rax
0x18009e58a  cmovnz  rbp, rax
0x18009e58e  mov     ecx, r15d; dwErrCode
0x18009e591  call    cs:__imp_SetLastError
0x18009e597  cmp     [rbp+7CCh], ebx
0x18009e59d  jz      short loc_18009E5B3
0x18009e59f  mov     r9d, ebx; int
0x18009e5a2  mov     r8d, 3B0h; int
0x18009e5a8  mov     rdx, r13; char *
0x18009e5ab  mov     rcx, rbp; this
0x18009e5ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009e5b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009e5ba  jb      loc_18009E74C
0x18009e5c0  mov     edx, 5Ah ; 'Z'
0x18009e5c5  jmp     loc_18009E72E
0x18009e5ca  cmp     edi, [r14+30h]
0x18009e5ce  jnb     short loc_18009E614
0x18009e5d0  test    edi, edi
0x18009e5d2  jz      short loc_18009E614
0x18009e5d4  mov     rax, [r14+28h]
0x18009e5d8  cmp     [rax+rdi*8], r12
0x18009e5dc  jz      short loc_18009E5FD
0x18009e5de  lfence
0x18009e5e1  mov     rax, [r14+28h]
0x18009e5e5  mov     rcx, [rax+rdi*8]
0x18009e5e9  mov     rax, [rcx]
0x18009e5ec  mov     rax, [rax+10h]
0x18009e5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5f5  mov     rax, [r14+28h]
0x18009e5f9  mov     [rax+rdi*8], r12
0x18009e5fd  mov     rcx, [rsp+98h+ppMFType]
0x18009e602  mov     rax, [r14+28h]
0x18009e606  mov     [rsp+98h+ppMFType], r12
0x18009e60b  mov     [rax+rdi*8], rcx
0x18009e60f  jmp     loc_18009E74C
0x18009e614  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e61b  mov     ebx, 8000FFFFh
0x18009e620  mov     esi, 7F0h
0x18009e625  test    rdi, rdi
0x18009e628  jnz     short loc_18009E668
0x18009e62a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009e630  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e637  mov     rcx, rax
0x18009e63a  test    rax, rax
0x18009e63d  jz      short loc_18009E65A
0x18009e63f  mov     rax, [rax]
0x18009e642  mov     edx, esi
0x18009e644  mov     rax, [rax+8]
0x18009e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e64d  test    eax, eax
0x18009e64f  jz      short loc_18009E65A
0x18009e651  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e658  jmp     short loc_18009E668
0x18009e65a  lea     rdi, qword_18010C230
0x18009e661  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18009e668  cmp     [rdi+8], r12b
0x18009e66c  jz      loc_18009E720
0x18009e672  lea     rbp, [rdi+0D0h]
0x18009e679  call    cs:__imp_GetLastError
0x18009e67f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18009e682  mov     r15d, eax
0x18009e685  call    cs:__imp_TlsGetValue
  ... truncated ...
```
