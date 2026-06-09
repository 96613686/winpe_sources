# CMP3MediaSourcePlugin::CombineParseDataBuffer(IMFMediaBuffer *)

- ea: `0x1800ba240`
- end: `0x1800ba741`
- name: `?CombineParseDataBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(CMP3MediaSourcePlugin *__hidden this, struct IMFMediaBuffer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e3ea0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180052f24`
- `0x180058af4`
- `0x1800612cc`
- `0x180079680`
- `0x1800ba240`
- `0x180110ed0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba2ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba3a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba45a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba5d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba67f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba2ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba3a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba45a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba5d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ba67f`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ba438`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ba438`

## string_xrefs

- `0x1800ba264`: `CMP3MediaSourcePlugin::CombineParseDataBuffer`

## pseudocode

```c
__int64 __fastcall CMP3MediaSourcePlugin::CombineParseDataBuffer(
        CMP3MediaSourcePlugin *this,
        struct IMFMediaBuffer *a2)
{
  __int64 v4; // rcx
  HRESULT v5; // ebx
  __int64 v6; // rdx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  struct IMFMediaBufferVtbl *lpVtbl; // rax
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
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
  _BYTE v34[8]; // [rsp+30h] [rbp-20h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-18h] BYREF
  int v36; // [rsp+40h] [rbp-10h] BYREF
  int v37; // [rsp+44h] [rbp-Ch] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v34,
    "CMP3MediaSourcePlugin::CombineParseDataBuffer",
    1659);
  v4 = *((_QWORD *)this + 165);
  if ( !v4 )
  {
    v5 = 0;
    ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 1320, a2);
    goto LABEL_73;
  }
  v36 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 40LL))(v4, &v36);
  if ( v5 < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1668, v5);
    }
    if ( g_wppLevels )
    {
      v10 = 189;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v5);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  lpVtbl = a2->lpVtbl;
  v37 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, int *))lpVtbl->GetCurrentLength)(a2, &v37);
  if ( v5 >= 0 )
  {
    ppBuffer = 0;
    v5 = MFCreateMemoryBuffer(v37 + v36, &ppBuffer);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(IMFMediaBuffer *, _QWORD))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, 0);
      if ( v5 >= 0 )
      {
        v5 = CMP3MediaSourcePlugin::AppendToBuffer(this, *((struct IMFMediaBuffer **)this + 165), 0, ppBuffer);
        if ( v5 >= 0 )
        {
          v5 = CMP3MediaSourcePlugin::AppendToBuffer(this, a2, 0, ppBuffer);
          if ( v5 >= 0 )
          {
            ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 1320, &ppBuffer);
            goto LABEL_72;
          }
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
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
            if ( *((_DWORD *)v32 + 499) != v5 )
              CallStackContext::TraceFailure(v32, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1676, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_72;
          v20 = 194;
        }
        else
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
            CallStackTracing::s_wpInstance = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
            if ( *((_DWORD *)v28 + 499) != v5 )
              CallStackContext::TraceFailure(v28, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1675, v5);
          }
          if ( !g_wppLevels )
            goto LABEL_72;
          v20 = 193;
        }
      }
      else
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
          CallStackTracing::s_wpInstance = v23;
          if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
          if ( *((_DWORD *)v24 + 499) != v5 )
            CallStackContext::TraceFailure(v24, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1674, v5);
        }
        if ( !g_wppLevels )
          goto LABEL_72;
        v20 = 192;
      }
    }
    else
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v5 )
          CallStackContext::TraceFailure(v19, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1673, v5);
      }
      if ( !g_wppLevels )
        goto LABEL_72;
      v20 = 191;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_d883d89413f235918ed5b1c680996b82_Traceguids, this, v5);
LABEL_72:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
    goto LABEL_73;
  }
  v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    if ( *((_DWORD *)v15 + 499) != v5 )
      CallStackContext::TraceFailure(v15, "CMP3MediaSourcePlugin::CombineParseDataBuffer", 1670, v5);
  }
  if ( g_wppLevels )
  {
    v10 = 190;
    goto LABEL_14;
  }
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ba240  mov     [rsp-28h+arg_10], rbx
0x1800ba245  push    rbp
0x1800ba246  push    rsi
0x1800ba247  push    rdi
0x1800ba248  push    r12
0x1800ba24a  push    r14
0x1800ba24c  mov     rbp, rsp
0x1800ba24f  sub     rsp, 50h
0x1800ba253  mov     rax, cs:__security_cookie
0x1800ba25a  xor     rax, rsp
0x1800ba25d  mov     [rbp+var_8], rax
0x1800ba261  mov     rsi, rdx
0x1800ba264  lea     r12, aCmp3mediasourc_56; "CMP3MediaSourcePlugin::CombineParseData"...
0x1800ba26b  mov     r14, rcx
0x1800ba26e  mov     rdx, r12; char *
0x1800ba271  mov     r8d, 67Bh; int
0x1800ba277  lea     rcx, [rbp+var_20]; this
0x1800ba27b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ba280  lea     rdi, [r14+528h]
0x1800ba287  mov     rcx, [rdi]
0x1800ba28a  test    rcx, rcx
0x1800ba28d  jnz     short loc_1800BA2A1
0x1800ba28f  xor     ebx, ebx
0x1800ba291  mov     rdx, rsi
0x1800ba294  mov     rcx, rdi
0x1800ba297  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@PEAU1@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(IMFMediaBuffer *)
0x1800ba29c  jmp     loc_1800BA715
0x1800ba2a1  mov     [rbp+var_10], 0
0x1800ba2a8  lea     rdx, [rbp+var_10]
0x1800ba2ac  mov     rax, [rcx]
0x1800ba2af  mov     rax, [rax+28h]
0x1800ba2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba2b8  mov     ebx, eax
0x1800ba2ba  test    eax, eax
0x1800ba2bc  jns     loc_1800BA371
0x1800ba2c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba2c9  test    rcx, rcx
0x1800ba2cc  jnz     short loc_1800BA315
0x1800ba2ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba2d5  nop     dword ptr [rax+rax+00h]
0x1800ba2da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba2e1  mov     rcx, rax
0x1800ba2e4  test    rax, rax
0x1800ba2e7  jz      short loc_1800BA307
0x1800ba2e9  mov     rax, [rax]
0x1800ba2ec  mov     edx, 7F0h
0x1800ba2f1  mov     rax, [rax+8]
0x1800ba2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba2fa  test    eax, eax
0x1800ba2fc  jz      short loc_1800BA307
0x1800ba2fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba305  jmp     short loc_1800BA315
0x1800ba307  lea     rcx, qword_1801B97E0; this
0x1800ba30e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba315  cmp     byte ptr [rcx+8], 0
0x1800ba319  jz      short loc_1800BA33C
0x1800ba31b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba320  cmp     [rax+7CCh], ebx
0x1800ba326  jz      short loc_1800BA33C
0x1800ba328  mov     r9d, ebx; int
0x1800ba32b  mov     r8d, 684h; int
0x1800ba331  mov     rdx, r12; char *
0x1800ba334  mov     rcx, rax; this
0x1800ba337  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba33c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba343  jb      loc_1800BA715
0x1800ba349  mov     edx, 0BDh
0x1800ba34e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba355  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800ba35c  mov     r9, r14
0x1800ba35f  mov     [rsp+50h+var_30], ebx
0x1800ba363  mov     rcx, [rcx+10h]
0x1800ba367  call    WPP_SF_qD
0x1800ba36c  jmp     loc_1800BA715
0x1800ba371  mov     rax, [rsi]
0x1800ba374  lea     rdx, [rbp+var_C]
0x1800ba378  mov     rcx, rsi
0x1800ba37b  mov     [rbp+var_C], 0
0x1800ba382  mov     rax, [rax+28h]
0x1800ba386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba38b  mov     ebx, eax
0x1800ba38d  test    eax, eax
0x1800ba38f  jns     loc_1800BA426
0x1800ba395  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba39c  test    rcx, rcx
0x1800ba39f  jnz     short loc_1800BA3E8
0x1800ba3a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba3a8  nop     dword ptr [rax+rax+00h]
0x1800ba3ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba3b4  mov     rcx, rax
0x1800ba3b7  test    rax, rax
0x1800ba3ba  jz      short loc_1800BA3DA
0x1800ba3bc  mov     rax, [rax]
0x1800ba3bf  mov     edx, 7F0h
0x1800ba3c4  mov     rax, [rax+8]
0x1800ba3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3cd  test    eax, eax
0x1800ba3cf  jz      short loc_1800BA3DA
0x1800ba3d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba3d8  jmp     short loc_1800BA3E8
0x1800ba3da  lea     rcx, qword_1801B97E0; this
0x1800ba3e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba3e8  cmp     byte ptr [rcx+8], 0
0x1800ba3ec  jz      short loc_1800BA40F
0x1800ba3ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba3f3  cmp     [rax+7CCh], ebx
0x1800ba3f9  jz      short loc_1800BA40F
0x1800ba3fb  mov     r9d, ebx; int
0x1800ba3fe  mov     r8d, 686h; int
0x1800ba404  mov     rdx, r12; char *
0x1800ba407  mov     rcx, rax; this
0x1800ba40a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba40f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba416  jb      loc_1800BA715
0x1800ba41c  mov     edx, 0BEh
0x1800ba421  jmp     loc_1800BA34E
0x1800ba426  mov     ecx, [rbp+var_10]
0x1800ba429  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800ba42d  add     ecx, [rbp+var_C]; cbMaxLength
0x1800ba430  mov     [rbp+ppBuffer], 0
0x1800ba438  call    cs:__imp_MFCreateMemoryBuffer
0x1800ba43f  nop     dword ptr [rax+rax+00h]
0x1800ba444  mov     ebx, eax
0x1800ba446  test    eax, eax
0x1800ba448  jns     loc_1800BA4FD
0x1800ba44e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba455  test    rcx, rcx
0x1800ba458  jnz     short loc_1800BA4A1
0x1800ba45a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba461  nop     dword ptr [rax+rax+00h]
0x1800ba466  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba46d  mov     rcx, rax
0x1800ba470  test    rax, rax
0x1800ba473  jz      short loc_1800BA493
0x1800ba475  mov     rax, [rax]
0x1800ba478  mov     edx, 7F0h
0x1800ba47d  mov     rax, [rax+8]
0x1800ba481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba486  test    eax, eax
0x1800ba488  jz      short loc_1800BA493
0x1800ba48a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba491  jmp     short loc_1800BA4A1
0x1800ba493  lea     rcx, qword_1801B97E0; this
0x1800ba49a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba4a1  cmp     byte ptr [rcx+8], 0
0x1800ba4a5  jz      short loc_1800BA4C8
0x1800ba4a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba4ac  cmp     [rax+7CCh], ebx
0x1800ba4b2  jz      short loc_1800BA4C8
0x1800ba4b4  mov     r9d, ebx; int
0x1800ba4b7  mov     r8d, 689h; int
0x1800ba4bd  mov     rdx, r12; char *
0x1800ba4c0  mov     rcx, rax; this
0x1800ba4c3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba4c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba4cf  jb      loc_1800BA70C
0x1800ba4d5  mov     edx, 0BFh
0x1800ba4da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba4e1  lea     r8, WPP_d883d89413f235918ed5b1c680996b82_Traceguids
0x1800ba4e8  mov     r9, r14
0x1800ba4eb  mov     [rsp+50h+var_30], ebx
0x1800ba4ef  mov     rcx, [rcx+10h]
0x1800ba4f3  call    WPP_SF_qD
0x1800ba4f8  jmp     loc_1800BA70C
0x1800ba4fd  mov     rcx, [rbp+ppBuffer]
0x1800ba501  xor     edx, edx
0x1800ba503  mov     rax, [rcx]
0x1800ba506  mov     rax, [rax+30h]
0x1800ba50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba50f  mov     ebx, eax
0x1800ba511  test    eax, eax
0x1800ba513  jns     loc_1800BA5AA
0x1800ba519  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba520  test    rcx, rcx
0x1800ba523  jnz     short loc_1800BA56C
0x1800ba525  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba52c  nop     dword ptr [rax+rax+00h]
0x1800ba531  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba538  mov     rcx, rax
0x1800ba53b  test    rax, rax
0x1800ba53e  jz      short loc_1800BA55E
0x1800ba540  mov     rax, [rax]
0x1800ba543  mov     edx, 7F0h
0x1800ba548  mov     rax, [rax+8]
0x1800ba54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba551  test    eax, eax
0x1800ba553  jz      short loc_1800BA55E
0x1800ba555  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba55c  jmp     short loc_1800BA56C
0x1800ba55e  lea     rcx, qword_1801B97E0; this
0x1800ba565  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba56c  cmp     byte ptr [rcx+8], 0
0x1800ba570  jz      short loc_1800BA593
0x1800ba572  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba577  cmp     [rax+7CCh], ebx
0x1800ba57d  jz      short loc_1800BA593
0x1800ba57f  mov     r9d, ebx; int
0x1800ba582  mov     r8d, 68Ah; int
0x1800ba588  mov     rdx, r12; char *
0x1800ba58b  mov     rcx, rax; this
0x1800ba58e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba593  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba59a  jb      loc_1800BA70C
0x1800ba5a0  mov     edx, 0C0h
0x1800ba5a5  jmp     loc_1800BA4DA
0x1800ba5aa  mov     r9, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800ba5ae  xor     r8d, r8d; unsigned int
0x1800ba5b1  mov     rdx, [rdi]; struct IMFMediaBuffer *
0x1800ba5b4  mov     rcx, r14; this
0x1800ba5b7  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x1800ba5bc  mov     ebx, eax
0x1800ba5be  test    eax, eax
0x1800ba5c0  jns     loc_1800BA657
0x1800ba5c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba5cd  test    rcx, rcx
0x1800ba5d0  jnz     short loc_1800BA619
0x1800ba5d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba5d9  nop     dword ptr [rax+rax+00h]
0x1800ba5de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba5e5  mov     rcx, rax
0x1800ba5e8  test    rax, rax
0x1800ba5eb  jz      short loc_1800BA60B
0x1800ba5ed  mov     rax, [rax]
0x1800ba5f0  mov     edx, 7F0h
0x1800ba5f5  mov     rax, [rax+8]
0x1800ba5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba5fe  test    eax, eax
0x1800ba600  jz      short loc_1800BA60B
0x1800ba602  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba609  jmp     short loc_1800BA619
0x1800ba60b  lea     rcx, qword_1801B97E0; this
0x1800ba612  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba619  cmp     byte ptr [rcx+8], 0
0x1800ba61d  jz      short loc_1800BA640
0x1800ba61f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba624  cmp     [rax+7CCh], ebx
0x1800ba62a  jz      short loc_1800BA640
0x1800ba62c  mov     r9d, ebx; int
0x1800ba62f  mov     r8d, 68Bh; int
0x1800ba635  mov     rdx, r12; char *
0x1800ba638  mov     rcx, rax; this
0x1800ba63b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba640  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba647  jb      loc_1800BA70C
0x1800ba64d  mov     edx, 0C1h
0x1800ba652  jmp     loc_1800BA4DA
0x1800ba657  mov     r9, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800ba65b  xor     r8d, r8d; unsigned int
0x1800ba65e  mov     rdx, rsi; struct IMFMediaBuffer *
0x1800ba661  mov     rcx, r14; this
0x1800ba664  call    ?AppendToBuffer@CMP3MediaSourcePlugin@@AEAAJPEAUIMFMediaBuffer@@K0@Z; CMP3MediaSourcePlugin::AppendToBuffer(IMFMediaBuffer *,ulong,IMFMediaBuffer *)
0x1800ba669  mov     ebx, eax
0x1800ba66b  test    eax, eax
0x1800ba66d  jns     loc_1800BA700
0x1800ba673  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba67a  test    rcx, rcx
0x1800ba67d  jnz     short loc_1800BA6C6
0x1800ba67f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ba686  nop     dword ptr [rax+rax+00h]
0x1800ba68b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba692  mov     rcx, rax
0x1800ba695  test    rax, rax
0x1800ba698  jz      short loc_1800BA6B8
0x1800ba69a  mov     rax, [rax]
0x1800ba69d  mov     edx, 7F0h
0x1800ba6a2  mov     rax, [rax+8]
0x1800ba6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba6ab  test    eax, eax
0x1800ba6ad  jz      short loc_1800BA6B8
0x1800ba6af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba6b6  jmp     short loc_1800BA6C6
0x1800ba6b8  lea     rcx, qword_1801B97E0; this
0x1800ba6bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ba6c6  cmp     byte ptr [rcx+8], 0
0x1800ba6ca  jz      short loc_1800BA6ED
0x1800ba6cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ba6d1  cmp     [rax+7CCh], ebx
0x1800ba6d7  jz      short loc_1800BA6ED
0x1800ba6d9  mov     r9d, ebx; int
0x1800ba6dc  mov     r8d, 68Ch; int
0x1800ba6e2  mov     rdx, r12; char *
0x1800ba6e5  mov     rcx, rax; this
0x1800ba6e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ba6ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ba6f4  jb      short loc_1800BA70C
0x1800ba6f6  mov     edx, 0C2h
0x1800ba6fb  jmp     loc_1800BA4DA
0x1800ba700  lea     rdx, [rbp+ppBuffer]
0x1800ba704  mov     rcx, rdi
0x1800ba707  call    ??4?$ComSmartPtr@UIMFMediaBuffer@@@@QEAAPEAUIMFMediaBuffer@@AEBV0@@Z; ComSmartPtr<IMFMediaBuffer>::operator=(ComSmartPtr<IMFMediaBuffer> const &)
0x1800ba70c  lea     rcx, [rbp+ppBuffer]; void *
0x1800ba710  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800ba715  lea     rcx, [rbp+var_20]; this
0x1800ba719  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ba71e  mov     eax, ebx
0x1800ba720  mov     rcx, [rbp+var_8]
0x1800ba724  xor     rcx, rsp; StackCookie
0x1800ba727  call    __security_check_cookie
0x1800ba72c  mov     rbx, [rsp+50h+arg_10]
0x1800ba734  add     rsp, 50h
  ... truncated ...
```
