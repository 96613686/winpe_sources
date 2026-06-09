# CMP3MediaSourcePlugin::PrepareBuffer(unsigned __int64,IMFMediaBuffer *,unsigned __int64)

- ea: `0x18005511c`
- end: `0x180055888`
- name: `?PrepareBuffer@CMP3MediaSourcePlugin@@AEAAJ_KPEAUIMFMediaBuffer@@0@Z`
- size: `1900`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *this, __int64, struct IMFMediaBuffer *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053d00`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18004e074`
- `0x18005511c`
- `0x180055890`
- `0x180073b14`
- `0x18007450c`
- `0x1801099f0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005532f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800553f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800554a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005554e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800555fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055720`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800557d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005532f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800553f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800554a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005554e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800555fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180055720`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800557d4`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800553db`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800553db`

## string_xrefs

- `0x180055168`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x18005527e`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180055386`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x18005544e`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800554f9`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x1800555a5`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180055651`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x180055777`: `CMP3MediaSourcePlugin::PrepareBuffer`
- `0x18005582b`: `CMP3MediaSourcePlugin::PrepareBuffer`

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
            v23 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v28 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v32 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v36 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v15 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v53 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v48 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x18005511c  mov     [rsp-38h+arg_8], rbx
0x180055121  push    rbp
0x180055122  push    rsi
0x180055123  push    rdi
0x180055124  push    r12
0x180055126  push    r13
0x180055128  push    r14
0x18005512a  push    r15
0x18005512c  mov     rbp, rsp
0x18005512f  sub     rsp, 70h
0x180055133  mov     rax, cs:__security_cookie
0x18005513a  xor     rax, rsp
0x18005513d  mov     [rbp+var_8], rax
0x180055141  mov     rbx, r8
0x180055144  mov     qword ptr [rbp+cbMaxLength], r9
0x180055148  xor     r12d, r12d
0x18005514b  mov     [rbp+var_28], rbx
0x18005514f  mov     rsi, rcx
0x180055152  mov     [rbp+var_18], r12
0x180055156  mov     r8d, 22Dh; int
0x18005515c  mov     [rbp+var_10], r12d
0x180055160  lea     rcx, [rbp+var_40]; this
0x180055164  mov     [rbp+var_C], r12d
0x180055168  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x18005516f  mov     r15, r9
0x180055172  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055177  mov     rax, [rbx]
0x18005517a  lea     r9, [rbp+var_10]
0x18005517e  lea     r8, [rbp+var_C]
0x180055182  mov     rcx, rbx
0x180055185  lea     rdx, [rbp+var_18]
0x180055189  mov     rax, [rax+18h]
0x18005518d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055192  mov     edi, eax
0x180055194  test    eax, eax
0x180055196  js      loc_180055859
0x18005519c  mov     rax, [rbx]
0x18005519f  mov     rcx, rbx
0x1800551a2  mov     rax, [rax+20h]
0x1800551a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551ab  lea     r13, [rsi+190h]
0x1800551b2  mov     rbx, [r13+0]
0x1800551b6  lea     r14, [rsi+80h]
0x1800551bd  test    rbx, rbx
0x1800551c0  jz      loc_1800556C5
0x1800551c6  mov     rax, [r14]
0x1800551c9  cmp     r15, rax
0x1800551cc  jb      loc_1800556C5
0x1800551d2  lea     r12, [rsi+0A0h]
0x1800551d9  mov     rcx, [r12]
0x1800551dd  add     rax, rcx
0x1800551e0  cmp     r15, rax
0x1800551e3  ja      loc_1800556C5
0x1800551e9  mov     eax, [rbp+var_10]
0x1800551ec  lea     r15, [rsi+0A8h]
0x1800551f3  add     rax, rcx
0x1800551f6  cmp     [r15], rax
0x1800551f9  jb      loc_1800552C8
0x1800551ff  mov     rdx, [rbp+var_28]; struct IMFMediaBuffer *
0x180055203  mov     r9, rbx; struct IMFMediaBuffer *
0x180055206  xor     r8d, r8d; unsigned int
0x180055209  mov     rcx, rsi; this
0x18005520c  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x180055211  mov     edi, eax
0x180055213  test    eax, eax
0x180055215  jns     loc_1800556F6
0x18005521b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055222  test    rcx, rcx
0x180055225  jnz     short loc_180055268
0x180055227  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005522d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055234  mov     rcx, rax
0x180055237  test    rax, rax
0x18005523a  jz      short loc_18005525A
0x18005523c  mov     rax, [rax]
0x18005523f  mov     edx, 7F0h
0x180055244  mov     rax, [rax+8]
0x180055248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005524d  test    eax, eax
0x18005524f  jz      short loc_18005525A
0x180055251  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055258  jmp     short loc_180055268
0x18005525a  lea     rcx, qword_1801B07E0; this
0x180055261  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055268  cmp     byte ptr [rcx+8], 0
0x18005526c  jz      short loc_180055293
0x18005526e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180055273  cmp     [rax+7CCh], edi
0x180055279  jz      short loc_180055293
0x18005527b  mov     r9d, edi; int
0x18005527e  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x180055285  mov     r8d, 248h; int
0x18005528b  mov     rcx, rax; this
0x18005528e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180055293  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005529a  jb      loc_180055859
0x1800552a0  mov     edx, 3Ch ; '<'
0x1800552a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552ac  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800552b3  mov     r9, rsi
0x1800552b6  mov     [rsp+70h+var_50], edi
0x1800552ba  mov     rcx, [rcx+10h]
0x1800552be  call    WPP_SF_qD
0x1800552c3  jmp     loc_180055859
0x1800552c8  mov     rax, [rbx]
0x1800552cb  mov     rcx, rbx
0x1800552ce  mov     [rbp+var_38], rbx
0x1800552d2  mov     rax, [rax+8]
0x1800552d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552db  mov     rax, [r14]
0x1800552de  xor     edx, edx
0x1800552e0  sub     rax, [rsi+98h]
0x1800552e7  mov     rcx, r13
0x1800552ea  mov     rdi, [r12]
0x1800552ee  mov     qword ptr [rbp+var_20], rax
0x1800552f2  sub     rdi, rax
0x1800552f5  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x1800552fa  test    rdi, rdi
0x1800552fd  jz      loc_180055693
0x180055303  mov     ecx, [rbp+var_10]
0x180055306  lea     rdx, [rbp+cbMaxLength]; unsigned int *
0x18005530a  add     rcx, rdi; unsigned __int64
0x18005530d  mov     [rbp+cbMaxLength], 0
0x180055314  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180055319  mov     edi, eax
0x18005531b  test    eax, eax
0x18005531d  jns     loc_1800553D5
0x180055323  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005532a  test    rcx, rcx
0x18005532d  jnz     short loc_180055370
0x18005532f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180055335  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005533c  mov     rcx, rax
0x18005533f  test    rax, rax
0x180055342  jz      short loc_180055362
0x180055344  mov     rax, [rax]
0x180055347  mov     edx, 7F0h
0x18005534c  mov     rax, [rax+8]
0x180055350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055355  test    eax, eax
0x180055357  jz      short loc_180055362
0x180055359  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055360  jmp     short loc_180055370
0x180055362  lea     rcx, qword_1801B07E0; this
0x180055369  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055370  cmp     byte ptr [rcx+8], 0
0x180055374  jz      short loc_18005539B
0x180055376  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005537b  cmp     [rax+7CCh], edi
0x180055381  jz      short loc_18005539B
0x180055383  mov     r9d, edi; int
0x180055386  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x18005538d  mov     r8d, 256h; int
0x180055393  mov     rcx, rax; this
0x180055396  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005539b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800553a2  jb      short loc_1800553C7
0x1800553a4  mov     edx, 3Dh ; '='
0x1800553a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553b0  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800553b7  mov     r9, rsi
0x1800553ba  mov     [rsp+70h+var_50], edi
0x1800553be  mov     rcx, [rcx+10h]
0x1800553c2  call    WPP_SF_qD
0x1800553c7  lea     rcx, [rbp+var_38]; void *
0x1800553cb  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800553d0  jmp     loc_180055859
0x1800553d5  mov     ecx, [rbp+cbMaxLength]; cbMaxLength
0x1800553d8  mov     rdx, r13; ppBuffer
0x1800553db  call    cs:__imp_MFCreateMemoryBuffer
0x1800553e1  mov     edi, eax
0x1800553e3  test    eax, eax
0x1800553e5  jns     loc_18005547A
0x1800553eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800553f2  test    rcx, rcx
0x1800553f5  jnz     short loc_180055438
0x1800553f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800553fd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055404  mov     rcx, rax
0x180055407  test    rax, rax
0x18005540a  jz      short loc_18005542A
0x18005540c  mov     rax, [rax]
0x18005540f  mov     edx, 7F0h
0x180055414  mov     rax, [rax+8]
0x180055418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005541d  test    eax, eax
0x18005541f  jz      short loc_18005542A
0x180055421  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055428  jmp     short loc_180055438
0x18005542a  lea     rcx, qword_1801B07E0; this
0x180055431  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180055438  cmp     byte ptr [rcx+8], 0
0x18005543c  jz      short loc_180055463
0x18005543e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180055443  cmp     [rax+7CCh], edi
0x180055449  jz      short loc_180055463
0x18005544b  mov     r9d, edi; int
0x18005544e  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x180055455  mov     r8d, 257h; int
0x18005545b  mov     rcx, rax; this
0x18005545e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180055463  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005546a  jb      loc_1800553C7
0x180055470  mov     edx, 3Eh ; '>'
0x180055475  jmp     loc_1800553A9
0x18005547a  mov     rcx, [r13+0]
0x18005547e  xor     edx, edx
0x180055480  mov     rax, [rcx]
0x180055483  mov     rax, [rax+30h]
0x180055487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005548c  mov     edi, eax
0x18005548e  test    eax, eax
0x180055490  jns     loc_180055525
0x180055496  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005549d  test    rcx, rcx
0x1800554a0  jnz     short loc_1800554E3
0x1800554a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800554a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800554af  mov     rcx, rax
0x1800554b2  test    rax, rax
0x1800554b5  jz      short loc_1800554D5
0x1800554b7  mov     rax, [rax]
0x1800554ba  mov     edx, 7F0h
0x1800554bf  mov     rax, [rax+8]
0x1800554c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554c8  test    eax, eax
0x1800554ca  jz      short loc_1800554D5
0x1800554cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800554d3  jmp     short loc_1800554E3
0x1800554d5  lea     rcx, qword_1801B07E0; this
0x1800554dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800554e3  cmp     byte ptr [rcx+8], 0
0x1800554e7  jz      short loc_18005550E
0x1800554e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800554ee  cmp     [rax+7CCh], edi
0x1800554f4  jz      short loc_18005550E
0x1800554f6  mov     r9d, edi; int
0x1800554f9  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x180055500  mov     r8d, 258h; int
0x180055506  mov     rcx, rax; this
0x180055509  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005550e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180055515  jb      loc_1800553C7
0x18005551b  mov     edx, 3Fh ; '?'
0x180055520  jmp     loc_1800553A9
0x180055525  mov     r8d, [rbp+var_20]; unsigned int
0x180055529  mov     rdx, rbx; struct IMFMediaBuffer *
0x18005552c  mov     r9, [r13+0]; struct IMFMediaBuffer *
0x180055530  mov     rcx, rsi; this
0x180055533  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x180055538  mov     edi, eax
0x18005553a  test    eax, eax
0x18005553c  jns     loc_1800555D1
0x180055542  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055549  test    rcx, rcx
0x18005554c  jnz     short loc_18005558F
0x18005554e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180055554  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005555b  mov     rcx, rax
0x18005555e  test    rax, rax
0x180055561  jz      short loc_180055581
0x180055563  mov     rax, [rax]
0x180055566  mov     edx, 7F0h
0x18005556b  mov     rax, [rax+8]
0x18005556f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055574  test    eax, eax
0x180055576  jz      short loc_180055581
0x180055578  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005557f  jmp     short loc_18005558F
0x180055581  lea     rcx, qword_1801B07E0; this
0x180055588  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005558f  cmp     byte ptr [rcx+8], 0
0x180055593  jz      short loc_1800555BA
0x180055595  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005559a  cmp     [rax+7CCh], edi
0x1800555a0  jz      short loc_1800555BA
0x1800555a2  mov     r9d, edi; int
0x1800555a5  lea     rdx, aCmp3mediasourc_41; "CMP3MediaSourcePlugin::PrepareBuffer"
0x1800555ac  mov     r8d, 259h; int
0x1800555b2  mov     rcx, rax; this
0x1800555b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800555ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800555c1  jb      loc_1800553C7
0x1800555c7  mov     edx, 40h ; '@'
0x1800555cc  jmp     loc_1800553A9
0x1800555d1  mov     r9, [r13+0]; struct IMFMediaBuffer *
0x1800555d5  xor     r8d, r8d; unsigned int
0x1800555d8  mov     rdx, [rbp+var_28]; struct IMFMediaBuffer *
0x1800555dc  mov     rcx, rsi; this
0x1800555df  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x1800555e4  mov     edi, eax
0x1800555e6  test    eax, eax
0x1800555e8  jns     loc_18005567D
0x1800555ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800555f5  test    rcx, rcx
0x1800555f8  jnz     short loc_18005563B
0x1800555fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180055600  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180055607  mov     rcx, rax
0x18005560a  test    rax, rax
  ... truncated ...
```
