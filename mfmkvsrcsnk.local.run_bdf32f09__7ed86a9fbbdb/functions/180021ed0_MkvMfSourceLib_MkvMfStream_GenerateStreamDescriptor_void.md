# MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor(void)

- ea: `0x180021ed0`
- end: `0x1800225ab`
- name: `?GenerateStreamDescriptor@MkvMfStream@MkvMfSourceLib@@MEAAJXZ`
- size: `1755`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c9b0`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180021ed0`
- `0x180071330`
- `0x1800aafa4`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021f44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022037`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800220e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800221bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800222cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022387`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002243a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800224e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180021f44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022037`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800220e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800221bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800222cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022387`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002243a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800224e3`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800220c4`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800220c4`

## string_xrefs

- `0x180021f07`: `MkvMfSourceLib::MkvMfStream::GenerateStreamDescriptor`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v16 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                v38 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v44 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v57 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v50 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v31 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180021ed0  mov     [rsp-28h+arg_18], rbx
0x180021ed5  push    rbp
0x180021ed6  push    rsi
0x180021ed7  push    rdi
0x180021ed8  push    r12
0x180021eda  push    r14
0x180021edc  mov     rbp, rsp
0x180021edf  sub     rsp, 30h
0x180021ee3  mov     rbx, rcx
0x180021ee6  lea     r14, [rcx+40h]
0x180021eea  mov     rcx, r14
0x180021eed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021ef2  mov     rax, [rbx+48h]
0x180021ef6  mov     esi, [rax+24h]
0x180021ef9  mov     [rbp+apMediaTypes], 0
0x180021f01  mov     r8d, 11Dh; int
0x180021f07  lea     r12, aMkvmfsourcelib_105; "MkvMfSourceLib::MkvMfStream::GenerateSt"...
0x180021f0e  mov     rdx, r12; char *
0x180021f11  lea     rcx, [rbp+arg_0]; this
0x180021f15  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180021f1a  nop
0x180021f1b  mov     rax, [rbx]
0x180021f1e  lea     rdx, [rbp+apMediaTypes]
0x180021f22  mov     rcx, rbx
0x180021f25  mov     rax, [rax+68h]
0x180021f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f2e  mov     edi, eax
0x180021f30  test    eax, eax
0x180021f32  jns     loc_180021FE1
0x180021f38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f3f  test    rcx, rcx
0x180021f42  jnz     short loc_180021F85
0x180021f44  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021f4a  mov     rcx, rax
0x180021f4d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f54  test    rax, rax
0x180021f57  jz      short loc_180021F77
0x180021f59  mov     rax, [rax]
0x180021f5c  mov     edx, 7F0h
0x180021f61  mov     rax, [rax+8]
0x180021f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f6a  test    eax, eax
0x180021f6c  jz      short loc_180021F77
0x180021f6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f75  jmp     short loc_180021F85
0x180021f77  lea     rcx, qword_1800D6F70; this
0x180021f7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021f85  cmp     byte ptr [rcx+8], 0
0x180021f89  jz      short loc_180021FAC
0x180021f8b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180021f90  cmp     [rax+7CCh], edi
0x180021f96  jz      short loc_180021FAC
0x180021f98  mov     r9d, edi; int
0x180021f9b  mov     r8d, 11Dh; int
0x180021fa1  mov     rdx, r12; char *
0x180021fa4  mov     rcx, rax; this
0x180021fa7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021fac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021fb3  jb      loc_180022585
0x180021fb9  mov     edx, 1Ah
0x180021fbe  mov     [rsp+30h+var_10], edi
0x180021fc2  mov     r9, rbx
0x180021fc5  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180021fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fd3  mov     rcx, [rcx+10h]
0x180021fd7  call    WPP_SF_qD
0x180021fdc  jmp     loc_180022585
0x180021fe1  lea     r8, [rbx+90h]
0x180021fe8  cmp     qword ptr [r8+18h], 7
0x180021fed  jbe     short loc_180021FF2
0x180021fef  mov     r8, [r8]
0x180021ff2  test    r8, r8
0x180021ff5  jz      loc_1800220B6
0x180021ffb  xor     eax, eax
0x180021ffd  cmp     [r8], ax
0x180022001  jz      loc_1800220B6
0x180022007  mov     rcx, [rbp+apMediaTypes]
0x18002200b  mov     rax, [rcx]
0x18002200e  lea     rdx, MF_MT_CONTAINER_SUBTYPE_NAME
0x180022015  mov     rax, [rax+0C8h]
0x18002201c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022021  mov     edi, eax
0x180022023  test    eax, eax
0x180022025  jns     loc_1800220B6
0x18002202b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022032  test    rcx, rcx
0x180022035  jnz     short loc_180022078
0x180022037  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002203d  mov     rcx, rax
0x180022040  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022047  test    rax, rax
0x18002204a  jz      short loc_18002206A
0x18002204c  mov     rax, [rax]
0x18002204f  mov     edx, 7F0h
0x180022054  mov     rax, [rax+8]
0x180022058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002205d  test    eax, eax
0x18002205f  jz      short loc_18002206A
0x180022061  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022068  jmp     short loc_180022078
0x18002206a  lea     rcx, qword_1800D6F70; this
0x180022071  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022078  cmp     byte ptr [rcx+8], 0
0x18002207c  jz      short loc_18002209F
0x18002207e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022083  cmp     [rax+7CCh], edi
0x180022089  jz      short loc_18002209F
0x18002208b  mov     r9d, edi; int
0x18002208e  mov     r8d, 122h; int
0x180022094  mov     rdx, r12; char *
0x180022097  mov     rcx, rax; this
0x18002209a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002209f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800220a6  jb      loc_180022585
0x1800220ac  mov     edx, 1Bh
0x1800220b1  jmp     loc_180021FBE
0x1800220b6  mov     r9, r14; ppDescriptor
0x1800220b9  lea     r8, [rbp+apMediaTypes]; apMediaTypes
0x1800220bd  mov     edx, 1; cMediaTypes
0x1800220c2  mov     ecx, esi; dwStreamIdentifier
0x1800220c4  call    cs:__imp_MFCreateStreamDescriptor
0x1800220ca  mov     edi, eax
0x1800220cc  test    eax, eax
0x1800220ce  jns     loc_18002215F
0x1800220d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800220db  test    rcx, rcx
0x1800220de  jnz     short loc_180022121
0x1800220e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800220e6  mov     rcx, rax
0x1800220e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800220f0  test    rax, rax
0x1800220f3  jz      short loc_180022113
0x1800220f5  mov     rax, [rax]
0x1800220f8  mov     edx, 7F0h
0x1800220fd  mov     rax, [rax+8]
0x180022101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022106  test    eax, eax
0x180022108  jz      short loc_180022113
0x18002210a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022111  jmp     short loc_180022121
0x180022113  lea     rcx, qword_1800D6F70; this
0x18002211a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022121  cmp     byte ptr [rcx+8], 0
0x180022125  jz      short loc_180022148
0x180022127  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002212c  cmp     [rax+7CCh], edi
0x180022132  jz      short loc_180022148
0x180022134  mov     r9d, edi; int
0x180022137  mov     r8d, 125h; int
0x18002213d  mov     rdx, r12; char *
0x180022140  mov     rcx, rax; this
0x180022143  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022148  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002214f  jb      loc_180022585
0x180022155  mov     edx, 1Ch
0x18002215a  jmp     loc_180021FBE
0x18002215f  lea     r8, [rbx+50h]
0x180022163  cmp     qword ptr [r8+18h], 7
0x180022168  jbe     short loc_18002216D
0x18002216a  mov     r8, [r8]
0x18002216d  lea     rdi, [rbx+70h]
0x180022171  cmp     qword ptr [rdi+18h], 7
0x180022176  jbe     short loc_18002217B
0x180022178  mov     rdi, [rdi]
0x18002217b  test    r8, r8
0x18002217e  jz      loc_18002226E
0x180022184  xor     eax, eax
0x180022186  cmp     [r8], ax
0x18002218a  jz      loc_18002226E
0x180022190  mov     rcx, [r14]
0x180022193  mov     rax, [rcx]
0x180022196  lea     rdx, MF_SD_STREAM_NAME
0x18002219d  mov     rax, [rax+0C8h]
0x1800221a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221a9  mov     esi, eax
0x1800221ab  test    eax, eax
0x1800221ad  jns     loc_18002226E
0x1800221b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800221ba  test    rcx, rcx
0x1800221bd  jnz     short loc_180022200
0x1800221bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800221c5  mov     rcx, rax
0x1800221c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800221cf  test    rax, rax
0x1800221d2  jz      short loc_1800221F2
0x1800221d4  mov     rax, [rax]
0x1800221d7  mov     edx, 7F0h
0x1800221dc  mov     rax, [rax+8]
0x1800221e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e5  test    eax, eax
0x1800221e7  jz      short loc_1800221F2
0x1800221e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800221f0  jmp     short loc_180022200
0x1800221f2  lea     rcx, qword_1800D6F70; this
0x1800221f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022200  cmp     byte ptr [rcx+8], 0
0x180022204  jz      short loc_180022227
0x180022206  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002220b  cmp     [rax+7CCh], esi
0x180022211  jz      short loc_180022227
0x180022213  mov     r9d, esi; int
0x180022216  mov     r8d, 12Dh; int
0x18002221c  mov     rdx, r12; char *
0x18002221f  mov     rcx, rax; this
0x180022222  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022227  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002222e  jb      short loc_180022254
0x180022230  mov     edx, 1Dh
0x180022235  mov     [rsp+30h+var_10], esi
0x180022239  mov     r9, rbx
0x18002223c  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180022243  mov     rcx, cs:WPP_GLOBAL_Control
0x18002224a  mov     rcx, [rcx+10h]
0x18002224e  call    WPP_SF_qD
0x180022253  nop
0x180022254  lea     rcx, [rbp+arg_0]; this
0x180022258  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002225d  nop
0x18002225e  lea     rcx, [rbp+apMediaTypes]
0x180022262  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022267  mov     eax, esi
0x180022269  jmp     loc_18002259A
0x18002226e  test    rdi, rdi
0x180022271  jz      loc_18002234A
0x180022277  xor     eax, eax
0x180022279  cmp     [rdi], ax
0x18002227c  jz      loc_18002234A
0x180022282  lea     rdx, aUnd; "und"
0x180022289  mov     rcx, rdi; String1
0x18002228c  call    wcscmp_0
0x180022291  test    eax, eax
0x180022293  jz      loc_18002234A
0x180022299  mov     rcx, [r14]
0x18002229c  mov     rax, [rcx]
0x18002229f  mov     r8, rdi
0x1800222a2  lea     rdx, MF_SD_LANGUAGE
0x1800222a9  mov     rax, [rax+0C8h]
0x1800222b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222b5  mov     edi, eax
0x1800222b7  test    eax, eax
0x1800222b9  jns     loc_18002234A
0x1800222bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800222c6  test    rcx, rcx
0x1800222c9  jnz     short loc_18002230C
0x1800222cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800222d1  mov     rcx, rax
0x1800222d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800222db  test    rax, rax
0x1800222de  jz      short loc_1800222FE
0x1800222e0  mov     rax, [rax]
0x1800222e3  mov     edx, 7F0h
0x1800222e8  mov     rax, [rax+8]
0x1800222ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222f1  test    eax, eax
0x1800222f3  jz      short loc_1800222FE
0x1800222f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800222fc  jmp     short loc_18002230C
0x1800222fe  lea     rcx, qword_1800D6F70; this
0x180022305  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002230c  cmp     byte ptr [rcx+8], 0
0x180022310  jz      short loc_180022333
0x180022312  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022317  cmp     [rax+7CCh], edi
0x18002231d  jz      short loc_180022333
0x18002231f  mov     r9d, edi; int
0x180022322  mov     r8d, 132h; int
0x180022328  mov     rdx, r12; char *
0x18002232b  mov     rcx, rax; this
0x18002232e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022333  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002233a  jb      loc_180022585
0x180022340  mov     edx, 1Eh
0x180022345  jmp     loc_180021FBE
0x18002234a  mov     rcx, [r14]
0x18002234d  mov     rax, [rcx]
0x180022350  xor     r8d, r8d
0x180022353  cmp     [rbx+1B4h], r8b
0x18002235a  setnz   r8b
0x18002235e  lea     rdx, MF_SD_MEDIASOURCE_STATUS
0x180022365  mov     rax, [rax+0A8h]
0x18002236c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022371  mov     edi, eax
0x180022373  test    eax, eax
0x180022375  jns     loc_180022406
0x18002237b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022382  test    rcx, rcx
0x180022385  jnz     short loc_1800223C8
0x180022387  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002238d  mov     rcx, rax
0x180022390  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022397  test    rax, rax
0x18002239a  jz      short loc_1800223BA
0x18002239c  mov     rax, [rax]
0x18002239f  mov     edx, 7F0h
0x1800223a4  mov     rax, [rax+8]
0x1800223a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ad  test    eax, eax
0x1800223af  jz      short loc_1800223BA
0x1800223b1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800223b8  jmp     short loc_1800223C8
  ... truncated ...
```
