# MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor(void)

- ea: `0x180022d90`
- end: `0x1800234a2`
- name: `?GenerateStreamDescriptor@MkvMfStream@MkvMfSourceLib@@MEAAJXZ`
- size: `1810`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002dd70`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180022d90`
- `0x1800744d8`
- `0x1800afcf4`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022e04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022efd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023097`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800231a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002326b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800233d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022e04`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022efd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022fb2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023097`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800231a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002326b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023324`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800233d3`
- `MFPlat!MFCreateStreamDescriptor` at `0x180022f90`
- `MFPlat!MFCreateStreamDescriptor` at `0x180022f90`

## string_xrefs

- `0x180022dc7`: `MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor(MkvMfSourceLib::MkvMfStream *this)
{
  IMFStreamDescriptor **v2; // r14
  DWORD v3; // esi
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  _QWORD *v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  _QWORD *v25; // r8
  const wchar_t *v26; // rdi
  __int64 v27; // rdx
  int v28; // esi
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // r9
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  char v60; // [rsp+60h] [rbp+30h] BYREF
  IMFMediaType *apMediaTypes; // [rsp+68h] [rbp+38h] BYREF
  __int64 v62; // [rsp+70h] [rbp+40h] BYREF

  v2 = (IMFStreamDescriptor **)((char *)this + 64);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
  v3 = *(_DWORD *)(*((_QWORD *)this + 9) + 36LL);
  apMediaTypes = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v60,
    "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor",
    285);
  v5 = (*(__int64 (__fastcall **)(MkvMfSourceLib::MkvMfStream *, IMFMediaType **))(*(_QWORD *)this + 104LL))(
         this,
         &apMediaTypes);
  if ( v5 < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor",
          285,
          v5);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v11 = 26;
    goto LABEL_12;
  }
  v12 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 21) > 7u )
    v12 = (_QWORD *)*v12;
  if ( v12 )
  {
    if ( *(_WORD *)v12 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *))apMediaTypes->lpVtbl->SetString)(
             apMediaTypes,
             MF_MT_CONTAINER_SUBTYPE_NAME);
      if ( v5 < 0 )
      {
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v18 + 499) != v5 )
            CallStackContext::TraceFailure(v18, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 290, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_107;
        v11 = 27;
        goto LABEL_12;
      }
    }
  }
  v5 = MFCreateStreamDescriptor(v3, 1u, &apMediaTypes, v2);
  if ( v5 < 0 )
  {
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)v24 + 499) != v5 )
        CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 293, v5);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v11 = 28;
    goto LABEL_12;
  }
  v25 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 13) > 7u )
    v25 = (_QWORD *)*v25;
  v26 = (const wchar_t *)((char *)this + 112);
  if ( *((_QWORD *)this + 17) > 7u )
    v26 = *(const wchar_t **)v26;
  if ( !v25
    || !*(_WORD *)v25
    || (v28 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, const IID *))(*v2)->lpVtbl->SetString)(
                *v2,
                &MF_SD_STREAM_NAME),
        v28 >= 0) )
  {
    if ( v26 )
    {
      if ( *v26 )
      {
        if ( wcscmp_0(v26, L"und") )
        {
          v5 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, const IID *, const wchar_t *))(*v2)->lpVtbl->SetString)(
                 *v2,
                 &MF_SD_LANGUAGE,
                 v26);
          if ( v5 < 0 )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
              CallStackTracing::s_wpInstance = v39;
              if ( v39
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
              {
                v38 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v38 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
              }
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)v40 + 499) != v5 )
                CallStackContext::TraceFailure(v40, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 306, v5);
            }
            if ( !g_wppLevels )
              goto LABEL_107;
            v11 = 30;
            goto LABEL_12;
          }
        }
      }
    }
    v5 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *, bool))(*v2)->lpVtbl->SetUINT32)(
           *v2,
           MF_SD_MEDIASOURCE_STATUS,
           *((_BYTE *)this + 436) != 0);
    if ( v5 < 0 )
    {
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v42, v43);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v5 )
          CallStackContext::TraceFailure(v46, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 310, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v11 = 31;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v5);
LABEL_107:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&apMediaTypes);
      return (unsigned int)v5;
    }
    v62 = 0;
    v5 = ((__int64 (__fastcall *)(IMFStreamDescriptor *, __int64 *))(*v2)->lpVtbl->GetMediaTypeHandler)(*v2, &v62);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, IMFMediaType *))(*(_QWORD *)v62 + 48LL))(v62, apMediaTypes);
      if ( v5 >= 0 )
      {
        v5 = 0;
        goto LABEL_106;
      }
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54, v55, v56);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != v5 )
          CallStackContext::TraceFailure(v59, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 317, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_106;
      v53 = 33;
    }
    else
    {
      v50 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v48, v49);
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v50 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v50 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v50 + 8) )
      {
        v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
        if ( *((_DWORD *)v52 + 499) != v5 )
          CallStackContext::TraceFailure(v52, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 314, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_106;
      v53 = 32;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v5);
LABEL_106:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
    goto LABEL_107;
  }
  v31 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v29, v30);
    CallStackTracing::s_wpInstance = v32;
    if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
    {
      v31 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v31 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v31 + 8) )
  {
    v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
    if ( *((_DWORD *)v33 + 499) != v28 )
      CallStackContext::TraceFailure(v33, "MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor", 301, v28);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v28);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&apMediaTypes);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x180022d90  mov     [rsp-28h+arg_18], rbx
0x180022d95  push    rbp
0x180022d96  push    rsi
0x180022d97  push    rdi
0x180022d98  push    r12
0x180022d9a  push    r14
0x180022d9c  mov     rbp, rsp
0x180022d9f  sub     rsp, 30h
0x180022da3  mov     rbx, rcx
0x180022da6  lea     r14, [rcx+40h]
0x180022daa  mov     rcx, r14
0x180022dad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022db2  mov     rax, [rbx+48h]
0x180022db6  mov     esi, [rax+24h]
0x180022db9  mov     [rbp+apMediaTypes], 0
0x180022dc1  mov     r8d, 11Dh; int
0x180022dc7  lea     r12, aMkvmfsourcelib_105; "MkvMfSourceLib::MkvMfStream::GenerateSt"...
0x180022dce  mov     rdx, r12; char *
0x180022dd1  lea     rcx, [rbp+arg_0]; this
0x180022dd5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180022dda  nop
0x180022ddb  mov     rax, [rbx]
0x180022dde  lea     rdx, [rbp+apMediaTypes]
0x180022de2  mov     rcx, rbx
0x180022de5  mov     rax, [rax+68h]
0x180022de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dee  mov     edi, eax
0x180022df0  test    eax, eax
0x180022df2  jns     loc_180022EA7
0x180022df8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022dff  test    rcx, rcx
0x180022e02  jnz     short loc_180022E4B
0x180022e04  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022e0b  nop     dword ptr [rax+rax+00h]
0x180022e10  mov     rcx, rax
0x180022e13  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e1a  test    rax, rax
0x180022e1d  jz      short loc_180022E3D
0x180022e1f  mov     rax, [rax]
0x180022e22  mov     edx, 7F0h
0x180022e27  mov     rax, [rax+8]
0x180022e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e30  test    eax, eax
0x180022e32  jz      short loc_180022E3D
0x180022e34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e3b  jmp     short loc_180022E4B
0x180022e3d  lea     rcx, qword_1800DBF70; this
0x180022e44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022e4b  cmp     byte ptr [rcx+8], 0
0x180022e4f  jz      short loc_180022E72
0x180022e51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022e56  cmp     [rax+7CCh], edi
0x180022e5c  jz      short loc_180022E72
0x180022e5e  mov     r9d, edi; int
0x180022e61  mov     r8d, 11Dh; int
0x180022e67  mov     rdx, r12; char *
0x180022e6a  mov     rcx, rax; this
0x180022e6d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022e72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022e79  jb      loc_18002347B
0x180022e7f  mov     edx, 1Ah
0x180022e84  mov     [rsp+30h+var_10], edi
0x180022e88  mov     r9, rbx
0x180022e8b  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180022e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e99  mov     rcx, [rcx+10h]
0x180022e9d  call    WPP_SF_qD
0x180022ea2  jmp     loc_18002347B
0x180022ea7  lea     r8, [rbx+90h]
0x180022eae  cmp     qword ptr [r8+18h], 7
0x180022eb3  jbe     short loc_180022EB8
0x180022eb5  mov     r8, [r8]
0x180022eb8  test    r8, r8
0x180022ebb  jz      loc_180022F82
0x180022ec1  xor     eax, eax
0x180022ec3  cmp     [r8], ax
0x180022ec7  jz      loc_180022F82
0x180022ecd  mov     rcx, [rbp+apMediaTypes]
0x180022ed1  mov     rax, [rcx]
0x180022ed4  lea     rdx, MF_MT_CONTAINER_SUBTYPE_NAME
0x180022edb  mov     rax, [rax+0C8h]
0x180022ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee7  mov     edi, eax
0x180022ee9  test    eax, eax
0x180022eeb  jns     loc_180022F82
0x180022ef1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ef8  test    rcx, rcx
0x180022efb  jnz     short loc_180022F44
0x180022efd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022f04  nop     dword ptr [rax+rax+00h]
0x180022f09  mov     rcx, rax
0x180022f0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022f13  test    rax, rax
0x180022f16  jz      short loc_180022F36
0x180022f18  mov     rax, [rax]
0x180022f1b  mov     edx, 7F0h
0x180022f20  mov     rax, [rax+8]
0x180022f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f29  test    eax, eax
0x180022f2b  jz      short loc_180022F36
0x180022f2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022f34  jmp     short loc_180022F44
0x180022f36  lea     rcx, qword_1800DBF70; this
0x180022f3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022f44  cmp     byte ptr [rcx+8], 0
0x180022f48  jz      short loc_180022F6B
0x180022f4a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022f4f  cmp     [rax+7CCh], edi
0x180022f55  jz      short loc_180022F6B
0x180022f57  mov     r9d, edi; int
0x180022f5a  mov     r8d, 122h; int
0x180022f60  mov     rdx, r12; char *
0x180022f63  mov     rcx, rax; this
0x180022f66  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022f6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022f72  jb      loc_18002347B
0x180022f78  mov     edx, 1Bh
0x180022f7d  jmp     loc_180022E84
0x180022f82  mov     r9, r14; ppDescriptor
0x180022f85  lea     r8, [rbp+apMediaTypes]; apMediaTypes
0x180022f89  mov     edx, 1; cMediaTypes
0x180022f8e  mov     ecx, esi; dwStreamIdentifier
0x180022f90  call    cs:__imp_MFCreateStreamDescriptor
0x180022f97  nop     dword ptr [rax+rax+00h]
0x180022f9c  mov     edi, eax
0x180022f9e  test    eax, eax
0x180022fa0  jns     loc_180023037
0x180022fa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022fad  test    rcx, rcx
0x180022fb0  jnz     short loc_180022FF9
0x180022fb2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022fb9  nop     dword ptr [rax+rax+00h]
0x180022fbe  mov     rcx, rax
0x180022fc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022fc8  test    rax, rax
0x180022fcb  jz      short loc_180022FEB
0x180022fcd  mov     rax, [rax]
0x180022fd0  mov     edx, 7F0h
0x180022fd5  mov     rax, [rax+8]
0x180022fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fde  test    eax, eax
0x180022fe0  jz      short loc_180022FEB
0x180022fe2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022fe9  jmp     short loc_180022FF9
0x180022feb  lea     rcx, qword_1800DBF70; this
0x180022ff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ff9  cmp     byte ptr [rcx+8], 0
0x180022ffd  jz      short loc_180023020
0x180022fff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023004  cmp     [rax+7CCh], edi
0x18002300a  jz      short loc_180023020
0x18002300c  mov     r9d, edi; int
0x18002300f  mov     r8d, 125h; int
0x180023015  mov     rdx, r12; char *
0x180023018  mov     rcx, rax; this
0x18002301b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023020  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023027  jb      loc_18002347B
0x18002302d  mov     edx, 1Ch
0x180023032  jmp     loc_180022E84
0x180023037  lea     r8, [rbx+50h]
0x18002303b  cmp     qword ptr [r8+18h], 7
0x180023040  jbe     short loc_180023045
0x180023042  mov     r8, [r8]
0x180023045  lea     rdi, [rbx+70h]
0x180023049  cmp     qword ptr [rdi+18h], 7
0x18002304e  jbe     short loc_180023053
0x180023050  mov     rdi, [rdi]
0x180023053  test    r8, r8
0x180023056  jz      loc_18002314C
0x18002305c  xor     eax, eax
0x18002305e  cmp     [r8], ax
0x180023062  jz      loc_18002314C
0x180023068  mov     rcx, [r14]
0x18002306b  mov     rax, [rcx]
0x18002306e  lea     rdx, MF_SD_STREAM_NAME
0x180023075  mov     rax, [rax+0C8h]
0x18002307c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023081  mov     esi, eax
0x180023083  test    eax, eax
0x180023085  jns     loc_18002314C
0x18002308b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023092  test    rcx, rcx
0x180023095  jnz     short loc_1800230DE
0x180023097  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002309e  nop     dword ptr [rax+rax+00h]
0x1800230a3  mov     rcx, rax
0x1800230a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800230ad  test    rax, rax
0x1800230b0  jz      short loc_1800230D0
0x1800230b2  mov     rax, [rax]
0x1800230b5  mov     edx, 7F0h
0x1800230ba  mov     rax, [rax+8]
0x1800230be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c3  test    eax, eax
0x1800230c5  jz      short loc_1800230D0
0x1800230c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800230ce  jmp     short loc_1800230DE
0x1800230d0  lea     rcx, qword_1800DBF70; this
0x1800230d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800230de  cmp     byte ptr [rcx+8], 0
0x1800230e2  jz      short loc_180023105
0x1800230e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800230e9  cmp     [rax+7CCh], esi
0x1800230ef  jz      short loc_180023105
0x1800230f1  mov     r9d, esi; int
0x1800230f4  mov     r8d, 12Dh; int
0x1800230fa  mov     rdx, r12; char *
0x1800230fd  mov     rcx, rax; this
0x180023100  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023105  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002310c  jb      short loc_180023132
0x18002310e  mov     edx, 1Dh
0x180023113  mov     [rsp+30h+var_10], esi
0x180023117  mov     r9, rbx
0x18002311a  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180023121  mov     rcx, cs:WPP_GLOBAL_Control
0x180023128  mov     rcx, [rcx+10h]
0x18002312c  call    WPP_SF_qD
0x180023131  nop
0x180023132  lea     rcx, [rbp+arg_0]; this
0x180023136  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002313b  nop
0x18002313c  lea     rcx, [rbp+apMediaTypes]
0x180023140  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023145  mov     eax, esi
0x180023147  jmp     loc_180023490
0x18002314c  test    rdi, rdi
0x18002314f  jz      loc_18002322E
0x180023155  xor     eax, eax
0x180023157  cmp     [rdi], ax
0x18002315a  jz      loc_18002322E
0x180023160  lea     rdx, aUnd; "und"
0x180023167  mov     rcx, rdi; String1
0x18002316a  call    wcscmp_0
0x18002316f  test    eax, eax
0x180023171  jz      loc_18002322E
0x180023177  mov     rcx, [r14]
0x18002317a  mov     rax, [rcx]
0x18002317d  mov     r8, rdi
0x180023180  lea     rdx, MF_SD_LANGUAGE
0x180023187  mov     rax, [rax+0C8h]
0x18002318e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023193  mov     edi, eax
0x180023195  test    eax, eax
0x180023197  jns     loc_18002322E
0x18002319d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800231a4  test    rcx, rcx
0x1800231a7  jnz     short loc_1800231F0
0x1800231a9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800231b0  nop     dword ptr [rax+rax+00h]
0x1800231b5  mov     rcx, rax
0x1800231b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800231bf  test    rax, rax
0x1800231c2  jz      short loc_1800231E2
0x1800231c4  mov     rax, [rax]
0x1800231c7  mov     edx, 7F0h
0x1800231cc  mov     rax, [rax+8]
0x1800231d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d5  test    eax, eax
0x1800231d7  jz      short loc_1800231E2
0x1800231d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800231e0  jmp     short loc_1800231F0
0x1800231e2  lea     rcx, qword_1800DBF70; this
0x1800231e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800231f0  cmp     byte ptr [rcx+8], 0
0x1800231f4  jz      short loc_180023217
0x1800231f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800231fb  cmp     [rax+7CCh], edi
0x180023201  jz      short loc_180023217
0x180023203  mov     r9d, edi; int
0x180023206  mov     r8d, 132h; int
0x18002320c  mov     rdx, r12; char *
0x18002320f  mov     rcx, rax; this
0x180023212  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023217  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002321e  jb      loc_18002347B
0x180023224  mov     edx, 1Eh
0x180023229  jmp     loc_180022E84
0x18002322e  mov     rcx, [r14]
0x180023231  mov     rax, [rcx]
0x180023234  xor     r8d, r8d
0x180023237  cmp     [rbx+1B4h], r8b
0x18002323e  setnz   r8b
0x180023242  lea     rdx, MF_SD_MEDIASOURCE_STATUS
0x180023249  mov     rax, [rax+0A8h]
0x180023250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023255  mov     edi, eax
0x180023257  test    eax, eax
0x180023259  jns     loc_1800232F0
0x18002325f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023266  test    rcx, rcx
0x180023269  jnz     short loc_1800232B2
0x18002326b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180023272  nop     dword ptr [rax+rax+00h]
0x180023277  mov     rcx, rax
0x18002327a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180023281  test    rax, rax
0x180023284  jz      short loc_1800232A4
0x180023286  mov     rax, [rax]
  ... truncated ...
```
