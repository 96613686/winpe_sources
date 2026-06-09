# mkvparser::Track::Info::Copy(mkvparser::Track::Info &)

- ea: `0x180084bd0`
- end: `0x18008519d`
- name: `?Copy@Info@Track@mkvparser@@QEBAJAEAV123@@Z`
- size: `1485`
- prototype: `__int64 __fastcall(mkvparser::Track::Info *__hidden this, struct mkvparser::Track::Info *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180085760`
- `0x1800923e0`
- `0x18009c6dc`

## callees

- `0x1800036c5`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18008385c`
- `0x180084bd0`
- `0x1800851a4`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084d0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084fb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008504b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800850ed`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084c65`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084d0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084daf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e54`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084ef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084fb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008504b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800850ed`

## string_xrefs

- `0x180084bee`: `mkvparser::Track::Info::Copy`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v16 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v29 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v33 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v36 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v39 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v46 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v6);
LABEL_95:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180084bd0  push    rbx
0x180084bd2  push    rsi
0x180084bd3  push    rdi
0x180084bd4  push    r14
0x180084bd6  sub     rsp, 38h
0x180084bda  mov     rsi, rdx
0x180084bdd  mov     rbx, rcx
0x180084be0  cmp     rdx, rcx
0x180084be3  jnz     short loc_180084BEC
0x180084be5  xor     eax, eax
0x180084be7  jmp     loc_180085193
0x180084bec  mov     eax, [rcx]
0x180084bee  lea     r14, aMkvparserTrack_3; "mkvparser::Track::Info::Copy"
0x180084bf5  mov     [rdx], eax
0x180084bf7  mov     r8d, 1539h; int
0x180084bfd  mov     eax, [rcx+4]
0x180084c00  mov     [rdx+4], eax
0x180084c03  mov     rax, [rcx+10h]
0x180084c07  mov     [rdx+10h], rax
0x180084c0b  mov     rax, [rcx+18h]
0x180084c0f  mov     [rdx+18h], rax
0x180084c13  mov     rax, [rcx+20h]
0x180084c17  mov     [rdx+20h], rax
0x180084c1b  mov     rax, [rcx+8]
0x180084c1f  mov     [rdx+8], rax
0x180084c23  mov     al, [rcx+58h]
0x180084c26  mov     [rdx+58h], al
0x180084c29  movups  xmm0, xmmword ptr [rcx+60h]
0x180084c2d  lea     rcx, [rsp+58h+arg_0]; this
0x180084c32  movdqu  xmmword ptr [rdx+60h], xmm0
0x180084c37  mov     rdx, r14; char *
0x180084c3a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180084c3f  mov     r8, rsi
0x180084c42  mov     edx, 28h ; '('
0x180084c47  mov     rcx, rbx
0x180084c4a  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x180084c4f  mov     edi, eax
0x180084c51  test    eax, eax
0x180084c53  jns     loc_180084CE4
0x180084c59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084c60  test    rcx, rcx
0x180084c63  jnz     short loc_180084CA6
0x180084c65  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084c6b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084c72  mov     rcx, rax
0x180084c75  test    rax, rax
0x180084c78  jz      short loc_180084C98
0x180084c7a  mov     rax, [rax]
0x180084c7d  mov     edx, 7F0h
0x180084c82  mov     rax, [rax+8]
0x180084c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c8b  test    eax, eax
0x180084c8d  jz      short loc_180084C98
0x180084c8f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084c96  jmp     short loc_180084CA6
0x180084c98  lea     rcx, qword_1800D6F70; this
0x180084c9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ca6  cmp     byte ptr [rcx+8], 0
0x180084caa  jz      short loc_180084CCD
0x180084cac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084cb1  cmp     [rax+7CCh], edi
0x180084cb7  jz      short loc_180084CCD
0x180084cb9  mov     r9d, edi; int
0x180084cbc  mov     r8d, 1539h; int
0x180084cc2  mov     rdx, r14; char *
0x180084cc5  mov     rcx, rax; this
0x180084cc8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084ccd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084cd4  jb      loc_180085187
0x180084cda  mov     edx, 1D4h
0x180084cdf  jmp     loc_180084F76
0x180084ce4  mov     r8, rsi
0x180084ce7  mov     edx, 30h ; '0'
0x180084cec  mov     rcx, rbx
0x180084cef  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x180084cf4  mov     edi, eax
0x180084cf6  test    eax, eax
0x180084cf8  jns     loc_180084D89
0x180084cfe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d05  test    rcx, rcx
0x180084d08  jnz     short loc_180084D4B
0x180084d0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084d10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d17  mov     rcx, rax
0x180084d1a  test    rax, rax
0x180084d1d  jz      short loc_180084D3D
0x180084d1f  mov     rax, [rax]
0x180084d22  mov     edx, 7F0h
0x180084d27  mov     rax, [rax+8]
0x180084d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d30  test    eax, eax
0x180084d32  jz      short loc_180084D3D
0x180084d34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d3b  jmp     short loc_180084D4B
0x180084d3d  lea     rcx, qword_1800D6F70; this
0x180084d44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d4b  cmp     byte ptr [rcx+8], 0
0x180084d4f  jz      short loc_180084D72
0x180084d51  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084d56  cmp     [rax+7CCh], edi
0x180084d5c  jz      short loc_180084D72
0x180084d5e  mov     r9d, edi; int
0x180084d61  mov     r8d, 153Bh; int
0x180084d67  mov     rdx, r14; char *
0x180084d6a  mov     rcx, rax; this
0x180084d6d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084d72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084d79  jb      loc_180085187
0x180084d7f  mov     edx, 1D5h
0x180084d84  jmp     loc_180084F76
0x180084d89  mov     r8, rsi
0x180084d8c  mov     edx, 38h ; '8'
0x180084d91  mov     rcx, rbx
0x180084d94  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x180084d99  mov     edi, eax
0x180084d9b  test    eax, eax
0x180084d9d  jns     loc_180084E2E
0x180084da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084daa  test    rcx, rcx
0x180084dad  jnz     short loc_180084DF0
0x180084daf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084db5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084dbc  mov     rcx, rax
0x180084dbf  test    rax, rax
0x180084dc2  jz      short loc_180084DE2
0x180084dc4  mov     rax, [rax]
0x180084dc7  mov     edx, 7F0h
0x180084dcc  mov     rax, [rax+8]
0x180084dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084dd5  test    eax, eax
0x180084dd7  jz      short loc_180084DE2
0x180084dd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084de0  jmp     short loc_180084DF0
0x180084de2  lea     rcx, qword_1800D6F70; this
0x180084de9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084df0  cmp     byte ptr [rcx+8], 0
0x180084df4  jz      short loc_180084E17
0x180084df6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084dfb  cmp     [rax+7CCh], edi
0x180084e01  jz      short loc_180084E17
0x180084e03  mov     r9d, edi; int
0x180084e06  mov     r8d, 153Dh; int
0x180084e0c  mov     rdx, r14; char *
0x180084e0f  mov     rcx, rax; this
0x180084e12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084e17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084e1e  jb      loc_180085187
0x180084e24  mov     edx, 1D6h
0x180084e29  jmp     loc_180084F76
0x180084e2e  mov     r8, rsi
0x180084e31  mov     edx, 40h ; '@'
0x180084e36  mov     rcx, rbx
0x180084e39  call    ?CopyStr@Info@Track@mkvparser@@AEBAJPEQ123@PEADAEAV123@@Z; mkvparser::Track::Info::CopyStr(char * mkvparser::Track::Info::*,mkvparser::Track::Info &)
0x180084e3e  mov     edi, eax
0x180084e40  test    eax, eax
0x180084e42  jns     loc_180084ED3
0x180084e48  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e4f  test    rcx, rcx
0x180084e52  jnz     short loc_180084E95
0x180084e54  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084e5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e61  mov     rcx, rax
0x180084e64  test    rax, rax
0x180084e67  jz      short loc_180084E87
0x180084e69  mov     rax, [rax]
0x180084e6c  mov     edx, 7F0h
0x180084e71  mov     rax, [rax+8]
0x180084e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e7a  test    eax, eax
0x180084e7c  jz      short loc_180084E87
0x180084e7e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e85  jmp     short loc_180084E95
0x180084e87  lea     rcx, qword_1800D6F70; this
0x180084e8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e95  cmp     byte ptr [rcx+8], 0
0x180084e99  jz      short loc_180084EBC
0x180084e9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084ea0  cmp     [rax+7CCh], edi
0x180084ea6  jz      short loc_180084EBC
0x180084ea8  mov     r9d, edi; int
0x180084eab  mov     r8d, 153Fh; int
0x180084eb1  mov     rdx, r14; char *
0x180084eb4  mov     rcx, rax; this
0x180084eb7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084ebc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084ec3  jb      loc_180085187
0x180084ec9  mov     edx, 1D7h
0x180084ece  jmp     loc_180084F76
0x180084ed3  mov     rdx, [rbx+50h]
0x180084ed7  test    rdx, rdx
0x180084eda  jz      loc_180085185
0x180084ee0  cmp     qword ptr [rbx+48h], 0
0x180084ee5  jnz     loc_180084F99
0x180084eeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ef2  test    rcx, rcx
0x180084ef5  jnz     short loc_180084F38
0x180084ef7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084efd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f04  mov     rcx, rax
0x180084f07  test    rax, rax
0x180084f0a  jz      short loc_180084F2A
0x180084f0c  mov     rax, [rax]
0x180084f0f  mov     edx, 7F0h
0x180084f14  mov     rax, [rax+8]
0x180084f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f1d  test    eax, eax
0x180084f1f  jz      short loc_180084F2A
0x180084f21  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f28  jmp     short loc_180084F38
0x180084f2a  lea     rcx, qword_1800D6F70; this
0x180084f31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f38  cmp     byte ptr [rcx+8], 0
0x180084f3c  mov     edi, 80004005h
0x180084f41  jz      short loc_180084F64
0x180084f43  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084f48  cmp     [rax+7CCh], edi
0x180084f4e  jz      short loc_180084F64
0x180084f50  mov     r9d, edi; int
0x180084f53  mov     r8d, 1542h; int
0x180084f59  mov     rdx, r14; char *
0x180084f5c  mov     rcx, rax; this
0x180084f5f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084f64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084f6b  jb      loc_180085187
0x180084f71  mov     edx, 1D8h
0x180084f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180084f7d  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180084f84  mov     r9, rbx
0x180084f87  mov     [rsp+58h+var_38], edi
0x180084f8b  mov     rcx, [rcx+10h]
0x180084f8f  call    WPP_SF_qD
0x180084f94  jmp     loc_180085187
0x180084f99  cmp     qword ptr [rsi+48h], 0
0x180084f9e  jz      loc_180085034
0x180084fa4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084fab  test    rcx, rcx
0x180084fae  jnz     short loc_180084FF1
0x180084fb0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084fb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084fbd  mov     rcx, rax
0x180084fc0  test    rax, rax
0x180084fc3  jz      short loc_180084FE3
0x180084fc5  mov     rax, [rax]
0x180084fc8  mov     edx, 7F0h
0x180084fcd  mov     rax, [rax+8]
0x180084fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084fd6  test    eax, eax
0x180084fd8  jz      short loc_180084FE3
0x180084fda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084fe1  jmp     short loc_180084FF1
0x180084fe3  lea     rcx, qword_1800D6F70; this
0x180084fea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ff1  cmp     byte ptr [rcx+8], 0
0x180084ff5  mov     edi, 80070057h
0x180084ffa  jz      short loc_18008501D
0x180084ffc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085001  cmp     [rax+7CCh], edi
0x180085007  jz      short loc_18008501D
0x180085009  mov     r9d, edi; int
0x18008500c  mov     r8d, 1546h; int
0x180085012  mov     rdx, r14; char *
0x180085015  mov     rcx, rax; this
0x180085018  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008501d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085024  jb      loc_180085187
0x18008502a  mov     edx, 1D9h
0x18008502f  jmp     loc_180084F76
0x180085034  cmp     qword ptr [rsi+50h], 0
0x180085039  jz      loc_1800850CF
0x18008503f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085046  test    rcx, rcx
0x180085049  jnz     short loc_18008508C
0x18008504b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085051  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085058  mov     rcx, rax
0x18008505b  test    rax, rax
0x18008505e  jz      short loc_18008507E
0x180085060  mov     rax, [rax]
0x180085063  mov     edx, 7F0h
0x180085068  mov     rax, [rax+8]
0x18008506c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085071  test    eax, eax
0x180085073  jz      short loc_18008507E
0x180085075  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008507c  jmp     short loc_18008508C
0x18008507e  lea     rcx, qword_1800D6F70; this
0x180085085  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008508c  cmp     byte ptr [rcx+8], 0
0x180085090  mov     edi, 80070057h
0x180085095  jz      short loc_1800850B8
0x180085097  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008509c  cmp     [rax+7CCh], edi
0x1800850a2  jz      short loc_1800850B8
0x1800850a4  mov     r9d, edi; int
0x1800850a7  mov     r8d, 154Bh; int
0x1800850ad  mov     rdx, r14; char *
0x1800850b0  mov     rcx, rax; this
0x1800850b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800850b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800850bf  jb      loc_180085187
  ... truncated ...
```
