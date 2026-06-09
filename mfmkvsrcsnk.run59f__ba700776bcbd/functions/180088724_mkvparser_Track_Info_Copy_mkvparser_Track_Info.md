# mkvparser::Track::Info::Copy(mkvparser::Track::Info &)

- ea: `0x180088724`
- end: `0x180088d22`
- name: `?Copy@Info@Track@mkvparser@@QEBAJAEAV123@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(mkvparser::Track::Info *__hidden this, struct mkvparser::Track::Info *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180089310`
- `0x18009656c`
- `0x1800a0d58`

## callees

- `0x180003705`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180087364`
- `0x180088724`
- `0x180088d28`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800887b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008890f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800889ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088b22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088bc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800887b9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088864`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008890f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800889ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088b22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088bc3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c6b`

## string_xrefs

- `0x180088742`: `mkvparser::Track::Info::Copy`

## pseudocode

```c
__int64 __fastcall mkvparser::Track::Info::Copy(mkvparser::Track::Info *this, struct mkvparser::Track::Info *a2)
{
  __int64 v5; // rdx
  int v6; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
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
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  unsigned __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  void *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  char v49; // [rsp+60h] [rbp+8h] BYREF

  if ( a2 == this )
    return 0;
  *(_DWORD *)a2 = *(_DWORD *)this;
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 1);
  *((_QWORD *)a2 + 2) = *((_QWORD *)this + 2);
  *((_QWORD *)a2 + 3) = *((_QWORD *)this + 3);
  *((_QWORD *)a2 + 4) = *((_QWORD *)this + 4);
  *((_QWORD *)a2 + 1) = *((_QWORD *)this + 1);
  *((_BYTE *)a2 + 88) = *((_BYTE *)this + 88);
  *((_OWORD *)a2 + 6) = *((_OWORD *)this + 6);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v49, "mkvparser::Track::Info::Copy", 5433);
  v6 = mkvparser::Track::Info::CopyStr(this, 40, a2);
  if ( v6 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Track::Info::Copy", 5433, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 468;
    goto LABEL_59;
  }
  v6 = mkvparser::Track::Info::CopyStr(this, 48, a2);
  if ( v6 < 0 )
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
      if ( *((_DWORD *)v18 + 499) != v6 )
        CallStackContext::TraceFailure(v18, "mkvparser::Track::Info::Copy", 5435, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 469;
    goto LABEL_59;
  }
  v6 = mkvparser::Track::Info::CopyStr(this, 56, a2);
  if ( v6 < 0 )
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
      if ( *((_DWORD *)v24 + 499) != v6 )
        CallStackContext::TraceFailure(v24, "mkvparser::Track::Info::Copy", 5437, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 470;
    goto LABEL_59;
  }
  v6 = mkvparser::Track::Info::CopyStr(this, 64, a2);
  if ( v6 < 0 )
  {
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v27, v28);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != v6 )
        CallStackContext::TraceFailure(v31, "mkvparser::Track::Info::Copy", 5439, v6);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 471;
    goto LABEL_59;
  }
  v32 = *((_QWORD *)this + 10);
  if ( !v32 )
  {
LABEL_94:
    v6 = 0;
    goto LABEL_95;
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v33 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
      CallStackTracing::s_wpInstance = v34;
      if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
      {
        v33 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v6 = -2147467259;
    if ( *((_BYTE *)v33 + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
      if ( *((_DWORD *)v35 + 499) != -2147467259 )
        CallStackContext::TraceFailure(v35, "mkvparser::Track::Info::Copy", 5442, -2147467259);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 472;
    goto LABEL_59;
  }
  if ( *((_QWORD *)a2 + 9) )
  {
    v36 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v6 = -2147024809;
    if ( *((_BYTE *)v36 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v38 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v38, "mkvparser::Track::Info::Copy", 5446, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 473;
    goto LABEL_59;
  }
  if ( *((_QWORD *)a2 + 10) )
  {
    v39 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v27, v28);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v6 = -2147024809;
    if ( *((_BYTE *)v39 + 8) )
    {
      v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
      if ( *((_DWORD *)v41 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v41, "mkvparser::Track::Info::Copy", 5451, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_95;
    v12 = 474;
    goto LABEL_59;
  }
  v42 = mkvparser::SafeArrayAlloc<char>(v26, v32);
  *((_QWORD *)a2 + 9) = v42;
  if ( v42 )
  {
    memcpy_0(v42, *((const void **)this + 9), *((_QWORD *)this + 10));
    *((_QWORD *)a2 + 10) = *((_QWORD *)this + 10);
    goto LABEL_94;
  }
  v46 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
    CallStackTracing::s_wpInstance = v47;
    if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v46 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v6 = -2147024882;
  if ( *((_BYTE *)v46 + 8) )
  {
    v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
    if ( *((_DWORD *)v48 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v48, "mkvparser::Track::Info::Copy", 5455, -2147024882);
  }
  if ( !g_wppLevels )
    goto LABEL_95;
  v12 = 475;
LABEL_59:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v6);
LABEL_95:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180088724  push    rbx
0x180088726  push    rsi
0x180088727  push    rdi
0x180088728  push    r14
0x18008872a  sub     rsp, 38h
0x18008872e  mov     rsi, rdx
0x180088731  mov     rbx, rcx
0x180088734  cmp     rdx, rcx
0x180088737  jnz     short loc_180088740
0x180088739  xor     eax, eax
0x18008873b  jmp     loc_180088D17
0x180088740  mov     eax, [rcx]
0x180088742  lea     r14, aMkvparserTrack_3; "mkvparser::Track::Info::Copy"
0x180088749  mov     [rdx], eax
0x18008874b  mov     r8d, 1539h; int
0x180088751  mov     eax, [rcx+4]
0x180088754  mov     [rdx+4], eax
0x180088757  mov     rax, [rcx+10h]
0x18008875b  mov     [rdx+10h], rax
0x18008875f  mov     rax, [rcx+18h]
0x180088763  mov     [rdx+18h], rax
0x180088767  mov     rax, [rcx+20h]
0x18008876b  mov     [rdx+20h], rax
0x18008876f  mov     rax, [rcx+8]
0x180088773  mov     [rdx+8], rax
0x180088777  mov     al, [rcx+58h]
0x18008877a  mov     [rdx+58h], al
0x18008877d  movups  xmm0, xmmword ptr [rcx+60h]
0x180088781  lea     rcx, [rsp+58h+arg_0]; this
0x180088786  movdqu  xmmword ptr [rdx+60h], xmm0
0x18008878b  mov     rdx, r14; char *
0x18008878e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088793  mov     r8, rsi
0x180088796  mov     edx, 28h ; '('
0x18008879b  mov     rcx, rbx
0x18008879e  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x1800887a3  mov     edi, eax
0x1800887a5  test    eax, eax
0x1800887a7  jns     loc_18008883E
0x1800887ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887b4  test    rcx, rcx
0x1800887b7  jnz     short loc_180088800
0x1800887b9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800887c0  nop     dword ptr [rax+rax+00h]
0x1800887c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887cc  mov     rcx, rax
0x1800887cf  test    rax, rax
0x1800887d2  jz      short loc_1800887F2
0x1800887d4  mov     rax, [rax]
0x1800887d7  mov     edx, 7F0h
0x1800887dc  mov     rax, [rax+8]
0x1800887e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800887e5  test    eax, eax
0x1800887e7  jz      short loc_1800887F2
0x1800887e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800887f0  jmp     short loc_180088800
0x1800887f2  lea     rcx, qword_1800DBF70; this
0x1800887f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088800  cmp     byte ptr [rcx+8], 0
0x180088804  jz      short loc_180088827
0x180088806  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008880b  cmp     [rax+7CCh], edi
0x180088811  jz      short loc_180088827
0x180088813  mov     r9d, edi; int
0x180088816  mov     r8d, 1539h; int
0x18008881c  mov     rdx, r14; char *
0x18008881f  mov     rcx, rax; this
0x180088822  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088827  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008882e  jb      loc_180088D0B
0x180088834  mov     edx, 1D4h
0x180088839  jmp     loc_180088AE8
0x18008883e  mov     r8, rsi
0x180088841  mov     edx, 30h ; '0'
0x180088846  mov     rcx, rbx
0x180088849  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x18008884e  mov     edi, eax
0x180088850  test    eax, eax
0x180088852  jns     loc_1800888E9
0x180088858  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008885f  test    rcx, rcx
0x180088862  jnz     short loc_1800888AB
0x180088864  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008886b  nop     dword ptr [rax+rax+00h]
0x180088870  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088877  mov     rcx, rax
0x18008887a  test    rax, rax
0x18008887d  jz      short loc_18008889D
0x18008887f  mov     rax, [rax]
0x180088882  mov     edx, 7F0h
0x180088887  mov     rax, [rax+8]
0x18008888b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088890  test    eax, eax
0x180088892  jz      short loc_18008889D
0x180088894  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008889b  jmp     short loc_1800888AB
0x18008889d  lea     rcx, qword_1800DBF70; this
0x1800888a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800888ab  cmp     byte ptr [rcx+8], 0
0x1800888af  jz      short loc_1800888D2
0x1800888b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800888b6  cmp     [rax+7CCh], edi
0x1800888bc  jz      short loc_1800888D2
0x1800888be  mov     r9d, edi; int
0x1800888c1  mov     r8d, 153Bh; int
0x1800888c7  mov     rdx, r14; char *
0x1800888ca  mov     rcx, rax; this
0x1800888cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800888d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800888d9  jb      loc_180088D0B
0x1800888df  mov     edx, 1D5h
0x1800888e4  jmp     loc_180088AE8
0x1800888e9  mov     r8, rsi
0x1800888ec  mov     edx, 38h ; '8'
0x1800888f1  mov     rcx, rbx
0x1800888f4  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x1800888f9  mov     edi, eax
0x1800888fb  test    eax, eax
0x1800888fd  jns     loc_180088994
0x180088903  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008890a  test    rcx, rcx
0x18008890d  jnz     short loc_180088956
0x18008890f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088916  nop     dword ptr [rax+rax+00h]
0x18008891b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088922  mov     rcx, rax
0x180088925  test    rax, rax
0x180088928  jz      short loc_180088948
0x18008892a  mov     rax, [rax]
0x18008892d  mov     edx, 7F0h
0x180088932  mov     rax, [rax+8]
0x180088936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008893b  test    eax, eax
0x18008893d  jz      short loc_180088948
0x18008893f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088946  jmp     short loc_180088956
0x180088948  lea     rcx, qword_1800DBF70; this
0x18008894f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088956  cmp     byte ptr [rcx+8], 0
0x18008895a  jz      short loc_18008897D
0x18008895c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088961  cmp     [rax+7CCh], edi
0x180088967  jz      short loc_18008897D
0x180088969  mov     r9d, edi; int
0x18008896c  mov     r8d, 153Dh; int
0x180088972  mov     rdx, r14; char *
0x180088975  mov     rcx, rax; this
0x180088978  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008897d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088984  jb      loc_180088D0B
0x18008898a  mov     edx, 1D6h
0x18008898f  jmp     loc_180088AE8
0x180088994  mov     r8, rsi
0x180088997  mov     edx, 40h ; '@'
0x18008899c  mov     rcx, rbx
0x18008899f  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x1800889a4  mov     edi, eax
0x1800889a6  test    eax, eax
0x1800889a8  jns     loc_180088A3F
0x1800889ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800889b5  test    rcx, rcx
0x1800889b8  jnz     short loc_180088A01
0x1800889ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800889c1  nop     dword ptr [rax+rax+00h]
0x1800889c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800889cd  mov     rcx, rax
0x1800889d0  test    rax, rax
0x1800889d3  jz      short loc_1800889F3
0x1800889d5  mov     rax, [rax]
0x1800889d8  mov     edx, 7F0h
0x1800889dd  mov     rax, [rax+8]
0x1800889e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800889e6  test    eax, eax
0x1800889e8  jz      short loc_1800889F3
0x1800889ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800889f1  jmp     short loc_180088A01
0x1800889f3  lea     rcx, qword_1800DBF70; this
0x1800889fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088a01  cmp     byte ptr [rcx+8], 0
0x180088a05  jz      short loc_180088A28
0x180088a07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088a0c  cmp     [rax+7CCh], edi
0x180088a12  jz      short loc_180088A28
0x180088a14  mov     r9d, edi; int
0x180088a17  mov     r8d, 153Fh; int
0x180088a1d  mov     rdx, r14; char *
0x180088a20  mov     rcx, rax; this
0x180088a23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088a28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088a2f  jb      loc_180088D0B
0x180088a35  mov     edx, 1D7h
0x180088a3a  jmp     loc_180088AE8
0x180088a3f  mov     rdx, [rbx+50h]
0x180088a43  test    rdx, rdx
0x180088a46  jz      loc_180088D09
0x180088a4c  cmp     qword ptr [rbx+48h], 0
0x180088a51  jnz     loc_180088B0B
0x180088a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088a5e  test    rcx, rcx
0x180088a61  jnz     short loc_180088AAA
0x180088a63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088a6a  nop     dword ptr [rax+rax+00h]
0x180088a6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088a76  mov     rcx, rax
0x180088a79  test    rax, rax
0x180088a7c  jz      short loc_180088A9C
0x180088a7e  mov     rax, [rax]
0x180088a81  mov     edx, 7F0h
0x180088a86  mov     rax, [rax+8]
0x180088a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088a8f  test    eax, eax
0x180088a91  jz      short loc_180088A9C
0x180088a93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088a9a  jmp     short loc_180088AAA
0x180088a9c  lea     rcx, qword_1800DBF70; this
0x180088aa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088aaa  cmp     byte ptr [rcx+8], 0
0x180088aae  mov     edi, 80004005h
0x180088ab3  jz      short loc_180088AD6
0x180088ab5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088aba  cmp     [rax+7CCh], edi
0x180088ac0  jz      short loc_180088AD6
0x180088ac2  mov     r9d, edi; int
0x180088ac5  mov     r8d, 1542h; int
0x180088acb  mov     rdx, r14; char *
0x180088ace  mov     rcx, rax; this
0x180088ad1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088ad6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088add  jb      loc_180088D0B
0x180088ae3  mov     edx, 1D8h
0x180088ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180088aef  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180088af6  mov     r9, rbx
0x180088af9  mov     [rsp+58h+var_38], edi
0x180088afd  mov     rcx, [rcx+10h]
0x180088b01  call    WPP_SF_qD
0x180088b06  jmp     loc_180088D0B
0x180088b0b  cmp     qword ptr [rsi+48h], 0
0x180088b10  jz      loc_180088BAC
0x180088b16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088b1d  test    rcx, rcx
0x180088b20  jnz     short loc_180088B69
0x180088b22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088b29  nop     dword ptr [rax+rax+00h]
0x180088b2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088b35  mov     rcx, rax
0x180088b38  test    rax, rax
0x180088b3b  jz      short loc_180088B5B
0x180088b3d  mov     rax, [rax]
0x180088b40  mov     edx, 7F0h
0x180088b45  mov     rax, [rax+8]
0x180088b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088b4e  test    eax, eax
0x180088b50  jz      short loc_180088B5B
0x180088b52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088b59  jmp     short loc_180088B69
0x180088b5b  lea     rcx, qword_1800DBF70; this
0x180088b62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088b69  cmp     byte ptr [rcx+8], 0
0x180088b6d  mov     edi, 80070057h
0x180088b72  jz      short loc_180088B95
0x180088b74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088b79  cmp     [rax+7CCh], edi
0x180088b7f  jz      short loc_180088B95
0x180088b81  mov     r9d, edi; int
0x180088b84  mov     r8d, 1546h; int
0x180088b8a  mov     rdx, r14; char *
0x180088b8d  mov     rcx, rax; this
0x180088b90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088b95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180088b9c  jb      loc_180088D0B
0x180088ba2  mov     edx, 1D9h
0x180088ba7  jmp     loc_180088AE8
0x180088bac  cmp     qword ptr [rsi+50h], 0
0x180088bb1  jz      loc_180088C4D
0x180088bb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088bbe  test    rcx, rcx
0x180088bc1  jnz     short loc_180088C0A
0x180088bc3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088bca  nop     dword ptr [rax+rax+00h]
0x180088bcf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088bd6  mov     rcx, rax
0x180088bd9  test    rax, rax
0x180088bdc  jz      short loc_180088BFC
0x180088bde  mov     rax, [rax]
0x180088be1  mov     edx, 7F0h
0x180088be6  mov     rax, [rax+8]
0x180088bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bef  test    eax, eax
0x180088bf1  jz      short loc_180088BFC
0x180088bf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088bfa  jmp     short loc_180088C0A
0x180088bfc  lea     rcx, qword_1800DBF70; this
0x180088c03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088c0a  cmp     byte ptr [rcx+8], 0
0x180088c0e  mov     edi, 80070057h
0x180088c13  jz      short loc_180088C36
0x180088c15  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088c1a  cmp     [rax+7CCh], edi
0x180088c20  jz      short loc_180088C36
  ... truncated ...
```
