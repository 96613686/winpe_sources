# CMP3MediaSourcePlugin::PrepareBuffer(unsigned __int64,IMFMediaBuffer *,unsigned __int64)

- ea: `0x180058348`
- end: `0x180058aeb`
- name: `?PrepareBuffer@CMP3MediaSourcePlugin@@AEAAJ_KPEAUIMFMediaBuffer@@0@Z`
- size: `1955`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *this, __int64, struct IMFMediaBuffer *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056ea0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180052f24`
- `0x180058348`
- `0x180058af4`
- `0x180079680`
- `0x180079f34`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058453`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058635`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800586e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058798`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005884a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058a30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058453`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058561`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058635`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800586e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058798`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005884a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058976`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058a30`
- `MFPlat!MFCreateMemoryBuffer` at `0x180058613`
- `MFPlat!MFCreateMemoryBuffer` at `0x180058613`

## string_xrefs

- `0x180058394`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800584b0`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800585be`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180058692`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180058743`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800587f5`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800588a7`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800589d3`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180058a8d`: `CMP3MediaSourcePlugin::PrepareBuffer`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::PrepareBuffer(
        CMP3MediaSourcePlugin *this,
        __int64 a2,
        struct IMFMediaBuffer *a3,
        unsigned __int64 a4)
{
  HRESULT v7; // edi
  struct IMFMediaBuffer **v8; // r13
  struct IMFMediaBuffer *v9; // rbx
  unsigned __int64 *v10; // r14
  __int64 *v11; // r12
  __int64 v12; // rcx
  _QWORD *v13; // r15
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  struct IMFMediaBuffer v19; // rax
  __int64 v20; // rdi
  __int64 v21; // rdi
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v26; // rdx
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  unsigned __int64 v43; // rax
  struct IMFMediaBuffer *v44; // rdx
  struct IMFMediaBuffer *v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  struct IMFMediaBuffer *v51; // rcx
  __int64 v52; // rdx
  wchar_t *v53; // rcx
  CallStackTracing *v54; // rax
  struct CallStackContext *v55; // rax
  _BYTE v57[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v58; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbMaxLength[2]; // [rsp+40h] [rbp-30h] BYREF
  struct IMFMediaBuffer *v60; // [rsp+48h] [rbp-28h]
  unsigned int v61[2]; // [rsp+50h] [rbp-20h]
  __int64 v62; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v63; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v64; // [rsp+64h] [rbp-Ch] BYREF

  *(_QWORD *)cbMaxLength = a4;
  v60 = a3;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v57, "CMP3MediaSourcePlugin::PrepareBuffer", 557);
  v7 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, __int64 *, unsigned int *, unsigned int *))a3->lpVtbl->Lock)(
         a3,
         &v62,
         &v64,
         &v63);
  if ( v7 < 0 )
    goto LABEL_103;
  ((void (__fastcall *)(struct IMFMediaBuffer *))a3->lpVtbl->Unlock)(a3);
  v8 = (struct IMFMediaBuffer **)((char *)this + 400);
  v9 = (struct IMFMediaBuffer *)*((_QWORD *)this + 50);
  v10 = (unsigned __int64 *)((char *)this + 128);
  if ( !v9 || a4 < *v10 || (v11 = (__int64 *)((char *)this + 160), v12 = *((_QWORD *)this + 20), a4 > v12 + *v10) )
  {
    v11 = (__int64 *)((char *)this + 160);
    v45 = v60;
    *((_QWORD *)this + 20) = v63;
    v46 = v64;
    *v10 = a4;
    *((_QWORD *)this + 19) = a4;
    v13 = (_QWORD *)((char *)this + 168);
    *((_QWORD *)this + 21) = v46;
    ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 400, v45);
    goto LABEL_80;
  }
  v13 = (_QWORD *)((char *)this + 168);
  if ( *((_QWORD *)this + 21) < v12 + (unsigned __int64)v63 )
  {
    v19.lpVtbl = v9->lpVtbl;
    v58 = *((_QWORD *)this + 50);
    ((void (__fastcall *)(__int64))v19.lpVtbl->AddRef)(v58);
    v20 = *v11;
    *(_QWORD *)v61 = *v10 - *((_QWORD *)this + 19);
    v21 = v20 - *(_QWORD *)v61;
    ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 400, 0);
    if ( v21 )
    {
      cbMaxLength[0] = 0;
      v7 = ULongLongToULong(v21 + v63, cbMaxLength);
      if ( v7 < 0 )
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::PrepareBuffer", 598, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_31;
        v26 = 61;
LABEL_30:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v7);
LABEL_31:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v58);
        goto LABEL_103;
      }
      v7 = MFCreateMemoryBuffer(cbMaxLength[0], (IMFMediaBuffer **)this + 50);
      if ( v7 < 0 )
      {
        v28 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v7 )
            CallStackContext::TraceFailure(v30, "CMP3MediaSourcePlugin::PrepareBuffer", 599, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_31;
        v26 = 62;
        goto LABEL_30;
      }
      v7 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _QWORD))(*v8)->lpVtbl->SetCurrentLength)(*v8, 0);
      if ( v7 < 0 )
      {
        v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
          if ( *((_DWORD *)v34 + 499) != v7 )
            CallStackContext::TraceFailure(v34, "CMP3MediaSourcePlugin::PrepareBuffer", 600, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_31;
        v26 = 63;
        goto LABEL_30;
      }
      v7 = CMP3MediaSourcePlugin::AppendToBuffer(this, v9, v61[0], *v8);
      if ( v7 < 0 )
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != v7 )
            CallStackContext::TraceFailure(v38, "CMP3MediaSourcePlugin::PrepareBuffer", 601, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_31;
        v26 = 64;
        goto LABEL_30;
      }
      v7 = CMP3MediaSourcePlugin::AppendToBuffer(this, v60, 0, *v8);
      if ( v7 < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != v7 )
            CallStackContext::TraceFailure(v42, "CMP3MediaSourcePlugin::PrepareBuffer", 602, v7);
        }
        if ( !g_wppLevels )
          goto LABEL_31;
        v26 = 65;
        goto LABEL_30;
      }
      *v13 = *v11 + v63;
      *((_QWORD *)this + 19) = *v10;
    }
    else
    {
      v43 = *(_QWORD *)cbMaxLength;
      v44 = v60;
      *v10 = *(_QWORD *)cbMaxLength;
      *((_QWORD *)this + 19) = v43;
      *v11 = v63;
      *v13 = v64;
      ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 400, v44);
    }
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v58);
    goto LABEL_80;
  }
  v7 = CMP3MediaSourcePlugin::AppendToBuffer(this, v60, 0, *((struct IMFMediaBuffer **)this + 50));
  if ( v7 < 0 )
  {
    v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != v7 )
        CallStackContext::TraceFailure(v17, "CMP3MediaSourcePlugin::PrepareBuffer", 584, v7);
    }
    if ( g_wppLevels )
    {
      v18 = 60;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v7);
      goto LABEL_103;
    }
    goto LABEL_103;
  }
LABEL_80:
  v7 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))(*v8)->lpVtbl->GetCurrentLength)(*v8, &v63);
  if ( v7 >= 0 )
  {
    v51 = *v8;
    *v11 = v63;
    v7 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, unsigned int *))v51->lpVtbl->GetMaxLength)(v51, &v64);
    if ( v7 >= 0 )
    {
      *v13 = v64;
      goto LABEL_103;
    }
    v53 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v54 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v52);
      CallStackTracing::s_wpInstance = v54;
      if ( v54 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
      {
        v53 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v53 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v53 + 8) )
    {
      v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v53);
      if ( *((_DWORD *)v55 + 499) != v7 )
        CallStackContext::TraceFailure(v55, "CMP3MediaSourcePlugin::PrepareBuffer", 621, v7);
    }
    if ( g_wppLevels )
    {
      v18 = 67;
      goto LABEL_17;
    }
  }
  else
  {
    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
      CallStackTracing::s_wpInstance = v49;
      if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
      {
        v48 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v48 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v48 + 8) )
    {
      v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
      if ( *((_DWORD *)v50 + 499) != v7 )
        CallStackContext::TraceFailure(v50, "CMP3MediaSourcePlugin::PrepareBuffer", 619, v7);
    }
    if ( g_wppLevels )
    {
      v18 = 66;
      goto LABEL_17;
    }
  }
LABEL_103:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v57);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180058348  mov     [rsp-38h+arg_8], rbx
0x18005834d  push    rbp
0x18005834e  push    rsi
0x18005834f  push    rdi
0x180058350  push    r12
0x180058352  push    r13
0x180058354  push    r14
0x180058356  push    r15
0x180058358  mov     rbp, rsp
0x18005835b  sub     rsp, 70h
0x18005835f  mov     rax, cs:__security_cookie
0x180058366  xor     rax, rsp
0x180058369  mov     [rbp+var_8], rax
0x18005836d  mov     rbx, r8
0x180058370  mov     qword ptr [rbp+cbMaxLength], r9
0x180058374  xor     r12d, r12d
0x180058377  mov     [rbp+var_28], rbx
0x18005837b  mov     rsi, rcx
0x18005837e  mov     [rbp+var_18], r12
0x180058382  mov     r8d, 22Dh; int
0x180058388  mov     [rbp+var_10], r12d
0x18005838c  lea     rcx, [rbp+var_40]; this
0x180058390  mov     [rbp+var_C], r12d
0x180058394  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x18005839b  mov     r15, r9
0x18005839e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800583a3  mov     rax, [rbx]
0x1800583a6  lea     r9, [rbp+var_10]
0x1800583aa  lea     r8, [rbp+var_C]
0x1800583ae  mov     rcx, rbx
0x1800583b1  lea     rdx, [rbp+var_18]
0x1800583b5  mov     rax, [rax+18h]
0x1800583b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583be  mov     edi, eax
0x1800583c0  test    eax, eax
0x1800583c2  js      loc_180058ABB
0x1800583c8  mov     rax, [rbx]
0x1800583cb  mov     rcx, rbx
0x1800583ce  mov     rax, [rax+20h]
0x1800583d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583d7  lea     r13, [rsi+190h]
0x1800583de  mov     rbx, [r13+0]
0x1800583e2  lea     r14, [rsi+80h]
0x1800583e9  test    rbx, rbx
0x1800583ec  jz      loc_18005891B
0x1800583f2  mov     rax, [r14]
0x1800583f5  cmp     r15, rax
0x1800583f8  jb      loc_18005891B
0x1800583fe  lea     r12, [rsi+0A0h]
0x180058405  mov     rcx, [r12]
0x180058409  add     rax, rcx
0x18005840c  cmp     r15, rax
0x18005840f  ja      loc_18005891B
0x180058415  mov     eax, [rbp+var_10]
0x180058418  lea     r15, [rsi+0A8h]
0x18005841f  add     rax, rcx
0x180058422  cmp     [r15], rax
0x180058425  jb      loc_1800584FA
0x18005842b  mov     rdx, [rbp+var_28]; struct IMFMediaBuffer *
0x18005842f  mov     r9, rbx; struct IMFMediaBuffer *
0x180058432  xor     r8d, r8d; unsigned int
0x180058435  mov     rcx, rsi; this
0x180058438  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x18005843d  mov     edi, eax
0x18005843f  test    eax, eax
0x180058441  jns     loc_18005894C
0x180058447  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005844e  test    rcx, rcx
0x180058451  jnz     short loc_18005849A
0x180058453  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005845a  nop     dword ptr [rax+rax+00h]
0x18005845f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058466  mov     rcx, rax
0x180058469  test    rax, rax
0x18005846c  jz      short loc_18005848C
0x18005846e  mov     rax, [rax]
0x180058471  mov     edx, 7F0h
0x180058476  mov     rax, [rax+8]
0x18005847a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005847f  test    eax, eax
0x180058481  jz      short loc_18005848C
0x180058483  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005848a  jmp     short loc_18005849A
0x18005848c  lea     rcx, qword_1801B97E0; this
0x180058493  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005849a  cmp     byte ptr [rcx+8], 0
0x18005849e  jz      short loc_1800584C5
0x1800584a0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800584a5  cmp     [rax+7CCh], edi
0x1800584ab  jz      short loc_1800584C5
0x1800584ad  mov     r9d, edi; int
0x1800584b0  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x1800584b7  mov     r8d, 248h; int
0x1800584bd  mov     rcx, rax; this
0x1800584c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800584c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800584cc  jb      loc_180058ABB
0x1800584d2  mov     edx, 3Ch ; '<'
0x1800584d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800584de  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800584e5  mov     r9, rsi
0x1800584e8  mov     [rsp+70h+var_50], edi
0x1800584ec  mov     rcx, [rcx+10h]
0x1800584f0  call    WPP_SF_qD
0x1800584f5  jmp     loc_180058ABB
0x1800584fa  mov     rax, [rbx]
0x1800584fd  mov     rcx, rbx
0x180058500  mov     [rbp+var_38], rbx
0x180058504  mov     rax, [rax+8]
0x180058508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005850d  mov     rax, [r14]
0x180058510  xor     edx, edx
0x180058512  sub     rax, [rsi+98h]
0x180058519  mov     rcx, r13
0x18005851c  mov     rdi, [r12]
0x180058520  mov     qword ptr [rbp+var_20], rax
0x180058524  sub     rdi, rax
0x180058527  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x18005852c  test    rdi, rdi
0x18005852f  jz      loc_1800588E9
0x180058535  mov     ecx, [rbp+var_10]
0x180058538  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x18005853c  add     rcx, rdi; unsigned __int64
0x18005853f  mov     [rbp+cbMaxLength], 0
0x180058546  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18005854b  mov     edi, eax
0x18005854d  test    eax, eax
0x18005854f  jns     loc_18005860D
0x180058555  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005855c  test    rcx, rcx
0x18005855f  jnz     short loc_1800585A8
0x180058561  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058568  nop     dword ptr [rax+rax+00h]
0x18005856d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058574  mov     rcx, rax
0x180058577  test    rax, rax
0x18005857a  jz      short loc_18005859A
0x18005857c  mov     rax, [rax]
0x18005857f  mov     edx, 7F0h
0x180058584  mov     rax, [rax+8]
0x180058588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005858d  test    eax, eax
0x18005858f  jz      short loc_18005859A
0x180058591  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058598  jmp     short loc_1800585A8
0x18005859a  lea     rcx, qword_1801B97E0; this
0x1800585a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800585a8  cmp     byte ptr [rcx+8], 0
0x1800585ac  jz      short loc_1800585D3
0x1800585ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800585b3  cmp     [rax+7CCh], edi
0x1800585b9  jz      short loc_1800585D3
0x1800585bb  mov     r9d, edi; int
0x1800585be  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x1800585c5  mov     r8d, 256h; int
0x1800585cb  mov     rcx, rax; this
0x1800585ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800585d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800585da  jb      short loc_1800585FF
0x1800585dc  mov     edx, 3Dh ; '='
0x1800585e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800585e8  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800585ef  mov     r9, rsi
0x1800585f2  mov     [rsp+70h+var_50], edi
0x1800585f6  mov     rcx, [rcx+10h]
0x1800585fa  call    WPP_SF_qD
0x1800585ff  lea     rcx, [rbp+var_38]; void *
0x180058603  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180058608  jmp     loc_180058ABB
0x18005860d  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x180058610  mov     rdx, r13; ppBuffer
0x180058613  call    cs:__imp_MFCreateMemoryBuffer
0x18005861a  nop     dword ptr [rax+rax+00h]
0x18005861f  mov     edi, eax
0x180058621  test    eax, eax
0x180058623  jns     loc_1800586BE
0x180058629  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058630  test    rcx, rcx
0x180058633  jnz     short loc_18005867C
0x180058635  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005863c  nop     dword ptr [rax+rax+00h]
0x180058641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058648  mov     rcx, rax
0x18005864b  test    rax, rax
0x18005864e  jz      short loc_18005866E
0x180058650  mov     rax, [rax]
0x180058653  mov     edx, 7F0h
0x180058658  mov     rax, [rax+8]
0x18005865c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058661  test    eax, eax
0x180058663  jz      short loc_18005866E
0x180058665  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005866c  jmp     short loc_18005867C
0x18005866e  lea     rcx, qword_1801B97E0; this
0x180058675  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005867c  cmp     byte ptr [rcx+8], 0
0x180058680  jz      short loc_1800586A7
0x180058682  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058687  cmp     [rax+7CCh], edi
0x18005868d  jz      short loc_1800586A7
0x18005868f  mov     r9d, edi; int
0x180058692  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x180058699  mov     r8d, 257h; int
0x18005869f  mov     rcx, rax; this
0x1800586a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800586a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800586ae  jb      loc_1800585FF
0x1800586b4  mov     edx, 3Eh ; '>'
0x1800586b9  jmp     loc_1800585E1
0x1800586be  mov     rcx, [r13+0]
0x1800586c2  xor     edx, edx
0x1800586c4  mov     rax, [rcx]
0x1800586c7  mov     rax, [rax+30h]
0x1800586cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586d0  mov     edi, eax
0x1800586d2  test    eax, eax
0x1800586d4  jns     loc_18005876F
0x1800586da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800586e1  test    rcx, rcx
0x1800586e4  jnz     short loc_18005872D
0x1800586e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800586ed  nop     dword ptr [rax+rax+00h]
0x1800586f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800586f9  mov     rcx, rax
0x1800586fc  test    rax, rax
0x1800586ff  jz      short loc_18005871F
0x180058701  mov     rax, [rax]
0x180058704  mov     edx, 7F0h
0x180058709  mov     rax, [rax+8]
0x18005870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058712  test    eax, eax
0x180058714  jz      short loc_18005871F
0x180058716  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005871d  jmp     short loc_18005872D
0x18005871f  lea     rcx, qword_1801B97E0; this
0x180058726  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005872d  cmp     byte ptr [rcx+8], 0
0x180058731  jz      short loc_180058758
0x180058733  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058738  cmp     [rax+7CCh], edi
0x18005873e  jz      short loc_180058758
0x180058740  mov     r9d, edi; int
0x180058743  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x18005874a  mov     r8d, 258h; int
0x180058750  mov     rcx, rax; this
0x180058753  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058758  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005875f  jb      loc_1800585FF
0x180058765  mov     edx, 3Fh ; '?'
0x18005876a  jmp     loc_1800585E1
0x18005876f  mov     r8d, [rbp+var_20]; unsigned int
0x180058773  mov     rdx, rbx; struct IMFMediaBuffer *
0x180058776  mov     r9, [r13+0]; struct IMFMediaBuffer *
0x18005877a  mov     rcx, rsi; this
0x18005877d  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x180058782  mov     edi, eax
0x180058784  test    eax, eax
0x180058786  jns     loc_180058821
0x18005878c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058793  test    rcx, rcx
0x180058796  jnz     short loc_1800587DF
0x180058798  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005879f  nop     dword ptr [rax+rax+00h]
0x1800587a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587ab  mov     rcx, rax
0x1800587ae  test    rax, rax
0x1800587b1  jz      short loc_1800587D1
0x1800587b3  mov     rax, [rax]
0x1800587b6  mov     edx, 7F0h
0x1800587bb  mov     rax, [rax+8]
0x1800587bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587c4  test    eax, eax
0x1800587c6  jz      short loc_1800587D1
0x1800587c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587cf  jmp     short loc_1800587DF
0x1800587d1  lea     rcx, qword_1801B97E0; this
0x1800587d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800587df  cmp     byte ptr [rcx+8], 0
0x1800587e3  jz      short loc_18005880A
0x1800587e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800587ea  cmp     [rax+7CCh], edi
0x1800587f0  jz      short loc_18005880A
0x1800587f2  mov     r9d, edi; int
0x1800587f5  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x1800587fc  mov     r8d, 259h; int
0x180058802  mov     rcx, rax; this
0x180058805  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005880a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058811  jb      loc_1800585FF
0x180058817  mov     edx, 40h ; '@'
0x18005881c  jmp     loc_1800585E1
0x180058821  mov     r9, [r13+0]; struct IMFMediaBuffer *
0x180058825  xor     r8d, r8d; unsigned int
0x180058828  mov     rdx, [rbp+var_28]; struct IMFMediaBuffer *
0x18005882c  mov     rcx, rsi; this
0x18005882f  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x180058834  mov     edi, eax
0x180058836  test    eax, eax
0x180058838  jns     loc_1800588D3
0x18005883e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
