# MkvReader::Seek(__int64)

- ea: `0x180044d58`
- end: `0x18004532c`
- name: `?Seek@MkvReader@@QEAAJ_J@Z`
- size: `1492`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e060`
- `0x180017e3c`
- `0x1800187d4`
- `0x180018f04`
- `0x18001ede0`
- `0x18001f300`

## callees

- `0x1800023e0`
- `0x180002e14`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180044d58`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ddc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044f15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800451c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045278`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044ddc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044e6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044f15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180044fdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045135`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800451c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045278`

## string_xrefs

- `0x180044d9c`: `MkvReader::Seek`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvReader::Seek(MkvReader *this, __int64 a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  unsigned __int64 v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // r14d
  unsigned __int64 v27; // rbx
  __int64 v28; // r8
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  _BYTE v39[4]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v40; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v43[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v42 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v39, "MkvReader::Seek", 684);
  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 2) + 48LL))(
         *((_QWORD *)this + 2),
         &v42);
  if ( v5 >= 0 )
  {
    if ( a2 >= 0 )
    {
      if ( *((_BYTE *)this + 228) || a2 >= v42 )
      {
        v18 = *((_QWORD *)this + 25);
        if ( v18 < 0 || a2 <= v18 )
        {
          v22 = a2 - a2 % (unsigned __int64)*((unsigned int *)this + 39);
          v41 = 0;
          v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, __int64, unsigned __int64 *))(**((_QWORD **)this + 2) + 120LL))(
                  *((_QWORD *)this + 2),
                  0,
                  v22,
                  1,
                  &v41);
          if ( v26 >= 0 )
          {
            v27 = v41;
          }
          else
          {
            v27 = v42;
            if ( v22 >= v42 )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
                CallStackTracing::s_wpInstance = v33;
                if ( v33
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
                {
                  v32 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v32 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v32 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v26 )
                  CallStackContext::TraceFailure(ThreadRelativeContext, "MkvReader::Seek", 730, v26);
              }
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids,
                  this,
                  v26);
              v5 = v26;
              goto LABEL_90;
            }
            v41 = v42;
            memset_0(v43, 0, sizeof(v43));
            while ( v27 < v22 )
            {
              v40 = 0;
              v28 = 1024;
              if ( v22 - v27 < 0x400 )
                v28 = v22 - v27;
              v5 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, unsigned int *))(**((_QWORD **)this + 2) + 72LL))(
                     *((_QWORD *)this + 2),
                     v43,
                     v28,
                     &v40);
              if ( v5 < 0 )
              {
                v29 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
                  CallStackTracing::s_wpInstance = v30;
                  if ( v30
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
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
                  if ( *((_DWORD *)v31 + 499) != v5 )
                    CallStackContext::TraceFailure(v31, "MkvReader::Seek", 724, v5);
                }
                if ( g_wppLevels )
                {
                  v11 = 31;
                  goto LABEL_35;
                }
                goto LABEL_90;
              }
              v27 = v40 + v41;
              v41 = v27;
            }
          }
          if ( v27 == v22 )
          {
            v5 = 0;
            goto LABEL_90;
          }
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          v5 = -1072875845;
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v37, "MkvReader::Seek", 735, -1072875845);
          }
          if ( g_wppLevels )
          {
            v11 = 33;
            goto LABEL_35;
          }
        }
        else
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          v5 = -2147024809;
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != -2147024809 )
              CallStackContext::TraceFailure(v21, "MkvReader::Seek", 701, -2147024809);
          }
          if ( g_wppLevels )
          {
            v11 = 30;
            goto LABEL_35;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v5 = -1072875794;
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != -1072875794 )
            CallStackContext::TraceFailure(v17, "MkvReader::Seek", 695, -1072875794);
        }
        if ( g_wppLevels )
        {
          v11 = 29;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      v5 = -2147024809;
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v14, "MkvReader::Seek", 688, -2147024809);
      }
      if ( g_wppLevels )
      {
        v11 = 28;
        goto LABEL_35;
      }
    }
  }
  else
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
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v5 )
        CallStackContext::TraceFailure(v10, "MkvReader::Seek", 684, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 27;
LABEL_35:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids, this, v5);
    }
  }
LABEL_90:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v39);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044d58  mov     [rsp-8+arg_10], rbx
0x180044d5d  push    rbp
0x180044d5e  push    rsi
0x180044d5f  push    rdi
0x180044d60  push    r12
0x180044d62  push    r14
0x180044d64  lea     rbp, [rsp-360h]
0x180044d6c  sub     rsp, 460h
0x180044d73  mov     rax, cs:__security_cookie
0x180044d7a  xor     rax, rsp
0x180044d7d  mov     [rbp+380h+var_30], rax
0x180044d84  mov     rsi, rdx
0x180044d87  mov     rdi, rcx
0x180044d8a  mov     [rsp+480h+var_440], 0
0x180044d93  mov     r14d, 2ACh
0x180044d99  mov     r8d, r14d; int
0x180044d9c  lea     r12, aMkvreaderSeek; "MkvReader::Seek"
0x180044da3  mov     rdx, r12; char *
0x180044da6  lea     rcx, [rsp+480h+var_450]; this
0x180044dab  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180044db0  nop
0x180044db1  mov     rcx, [rdi+10h]
0x180044db5  mov     rax, [rcx]
0x180044db8  lea     rdx, [rsp+480h+var_440]
0x180044dbd  mov     rax, [rax+30h]
0x180044dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044dc6  mov     ebx, eax
0x180044dc8  test    eax, eax
0x180044dca  jns     loc_180044E58
0x180044dd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044dd7  test    rcx, rcx
0x180044dda  jnz     short loc_180044E1D
0x180044ddc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044de2  mov     rcx, rax
0x180044de5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044dec  test    rax, rax
0x180044def  jz      short loc_180044E0F
0x180044df1  mov     rax, [rax]
0x180044df4  mov     edx, 7F0h
0x180044df9  mov     rax, [rax+8]
0x180044dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e02  test    eax, eax
0x180044e04  jz      short loc_180044E0F
0x180044e06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e0d  jmp     short loc_180044E1D
0x180044e0f  lea     rcx, qword_1800D6F70; this
0x180044e16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e1d  cmp     byte ptr [rcx+8], 0
0x180044e21  jz      short loc_180044E41
0x180044e23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044e28  cmp     [rax+7CCh], ebx
0x180044e2e  jz      short loc_180044E41
0x180044e30  mov     r9d, ebx; int
0x180044e33  mov     r8d, r14d; int
0x180044e36  mov     rdx, r12; char *
0x180044e39  mov     rcx, rax; this
0x180044e3c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044e41  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044e48  jb      loc_1800452FA
0x180044e4e  mov     edx, 1Bh
0x180044e53  jmp     loc_180044F94
0x180044e58  test    rsi, rsi
0x180044e5b  jns     loc_180044EF1
0x180044e61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e68  test    rcx, rcx
0x180044e6b  jnz     short loc_180044EAE
0x180044e6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044e73  mov     rcx, rax
0x180044e76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e7d  test    rax, rax
0x180044e80  jz      short loc_180044EA0
0x180044e82  mov     rax, [rax]
0x180044e85  mov     edx, 7F0h
0x180044e8a  mov     rax, [rax+8]
0x180044e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e93  test    eax, eax
0x180044e95  jz      short loc_180044EA0
0x180044e97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044e9e  jmp     short loc_180044EAE
0x180044ea0  lea     rcx, qword_1800D6F70; this
0x180044ea7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044eae  mov     ebx, 80070057h
0x180044eb3  cmp     byte ptr [rcx+8], 0
0x180044eb7  jz      short loc_180044EDA
0x180044eb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044ebe  cmp     [rax+7CCh], ebx
0x180044ec4  jz      short loc_180044EDA
0x180044ec6  mov     r9d, ebx; int
0x180044ec9  mov     r8d, 2B0h; int
0x180044ecf  mov     rdx, r12; char *
0x180044ed2  mov     rcx, rax; this
0x180044ed5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044eda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044ee1  jb      loc_1800452FA
0x180044ee7  mov     edx, 1Ch
0x180044eec  jmp     loc_180044F94
0x180044ef1  cmp     byte ptr [rdi+0E4h], 0
0x180044ef8  jnz     loc_180044FB7
0x180044efe  cmp     rsi, [rsp+480h+var_440]
0x180044f03  jnb     loc_180044FB7
0x180044f09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f10  test    rcx, rcx
0x180044f13  jnz     short loc_180044F56
0x180044f15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044f1b  mov     rcx, rax
0x180044f1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f25  test    rax, rax
0x180044f28  jz      short loc_180044F48
0x180044f2a  mov     rax, [rax]
0x180044f2d  mov     edx, 7F0h
0x180044f32  mov     rax, [rax+8]
0x180044f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f3b  test    eax, eax
0x180044f3d  jz      short loc_180044F48
0x180044f3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f46  jmp     short loc_180044F56
0x180044f48  lea     rcx, qword_1800D6F70; this
0x180044f4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180044f56  mov     ebx, 0C00D36EEh
0x180044f5b  cmp     byte ptr [rcx+8], 0
0x180044f5f  jz      short loc_180044F82
0x180044f61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180044f66  cmp     [rax+7CCh], ebx
0x180044f6c  jz      short loc_180044F82
0x180044f6e  mov     r9d, ebx; int
0x180044f71  mov     r8d, 2B7h; int
0x180044f77  mov     rdx, r12; char *
0x180044f7a  mov     rcx, rax; this
0x180044f7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180044f82  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044f89  jb      loc_1800452FA
0x180044f8f  mov     edx, 1Dh
0x180044f94  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f9b  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180044fa2  mov     r9, rdi
0x180044fa5  mov     dword ptr [rsp+480h+var_460], ebx
0x180044fa9  mov     rcx, [rcx+10h]
0x180044fad  call    WPP_SF_qD
0x180044fb2  jmp     loc_1800452FA
0x180044fb7  mov     rax, [rdi+0C8h]
0x180044fbe  test    rax, rax
0x180044fc1  js      loc_180045060
0x180044fc7  cmp     rsi, rax
0x180044fca  jle     loc_180045060
0x180044fd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fd7  test    rcx, rcx
0x180044fda  jnz     short loc_18004501D
0x180044fdc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180044fe2  mov     rcx, rax
0x180044fe5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180044fec  test    rax, rax
0x180044fef  jz      short loc_18004500F
0x180044ff1  mov     rax, [rax]
0x180044ff4  mov     edx, 7F0h
0x180044ff9  mov     rax, [rax+8]
0x180044ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045002  test    eax, eax
0x180045004  jz      short loc_18004500F
0x180045006  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004500d  jmp     short loc_18004501D
0x18004500f  lea     rcx, qword_1800D6F70; this
0x180045016  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004501d  mov     ebx, 80070057h
0x180045022  cmp     byte ptr [rcx+8], 0
0x180045026  jz      short loc_180045049
0x180045028  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004502d  cmp     [rax+7CCh], ebx
0x180045033  jz      short loc_180045049
0x180045035  mov     r9d, ebx; int
0x180045038  mov     r8d, 2BDh; int
0x18004503e  mov     rdx, r12; char *
0x180045041  mov     rcx, rax; this
0x180045044  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045049  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045050  jb      loc_1800452FA
0x180045056  mov     edx, 1Eh
0x18004505b  jmp     loc_180044F94
0x180045060  mov     ecx, [rdi+9Ch]
0x180045066  xor     edx, edx
0x180045068  mov     rax, rsi
0x18004506b  div     rcx
0x18004506e  sub     rsi, rdx
0x180045071  mov     [rsp+480h+var_448], 0
0x18004507a  mov     rcx, [rdi+10h]
0x18004507e  mov     rax, [rcx]
0x180045081  lea     rdx, [rsp+480h+var_448]
0x180045086  mov     [rsp+480h+var_460], rdx
0x18004508b  mov     r9d, 1
0x180045091  mov     r8, rsi
0x180045094  xor     edx, edx
0x180045096  mov     rax, [rax+78h]
0x18004509a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004509f  mov     r14d, eax
0x1800450a2  test    eax, eax
0x1800450a4  jns     loc_18004525E
0x1800450aa  mov     rbx, [rsp+480h+var_440]
0x1800450af  cmp     rsi, rbx
0x1800450b2  jnb     loc_1800451B4
0x1800450b8  mov     [rsp+480h+var_448], rbx
0x1800450bd  mov     r14d, 400h
0x1800450c3  mov     r8d, r14d; Size
0x1800450c6  xor     edx, edx; Val
0x1800450c8  lea     rcx, [rsp+480h+var_430]; void *
0x1800450cd  call    memset_0
0x1800450d2  mov     rcx, rbx
0x1800450d5  cmp     rbx, rsi
0x1800450d8  jnb     loc_180045263
0x1800450de  mov     [rsp+480h+var_44C], 0
0x1800450e6  mov     rax, rsi
0x1800450e9  sub     rax, rbx
0x1800450ec  mov     r8, r14
0x1800450ef  cmp     rax, r14
0x1800450f2  cmovb   r8, rax
0x1800450f6  mov     rcx, [rdi+10h]
0x1800450fa  mov     rax, [rcx]
0x1800450fd  lea     r9, [rsp+480h+var_44C]
0x180045102  lea     rdx, [rsp+480h+var_430]
0x180045107  mov     rax, [rax+48h]
0x18004510b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045110  mov     ebx, eax
0x180045112  test    eax, eax
0x180045114  js      short loc_180045129
0x180045116  mov     eax, [rsp+480h+var_44C]
0x18004511a  mov     rbx, [rsp+480h+var_448]
0x18004511f  add     rbx, rax
0x180045122  mov     [rsp+480h+var_448], rbx
0x180045127  jmp     short loc_1800450D2
0x180045129  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045130  test    rcx, rcx
0x180045133  jnz     short loc_180045176
0x180045135  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004513b  mov     rcx, rax
0x18004513e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045145  test    rax, rax
0x180045148  jz      short loc_180045168
0x18004514a  mov     rax, [rax]
0x18004514d  mov     edx, 7F0h
0x180045152  mov     rax, [rax+8]
0x180045156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004515b  test    eax, eax
0x18004515d  jz      short loc_180045168
0x18004515f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045166  jmp     short loc_180045176
0x180045168  lea     rcx, qword_1800D6F70; this
0x18004516f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045176  cmp     byte ptr [rcx+8], 0
0x18004517a  jz      short loc_18004519D
0x18004517c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045181  cmp     [rax+7CCh], ebx
0x180045187  jz      short loc_18004519D
0x180045189  mov     r9d, ebx; int
0x18004518c  mov     r8d, 2D4h; int
0x180045192  mov     rdx, r12; char *
0x180045195  mov     rcx, rax; this
0x180045198  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004519d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800451a4  jb      loc_1800452FA
0x1800451aa  mov     edx, 1Fh
0x1800451af  jmp     loc_180044F94
0x1800451b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800451bb  test    rcx, rcx
0x1800451be  jnz     short loc_180045201
0x1800451c0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800451c6  mov     rcx, rax
0x1800451c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800451d0  test    rax, rax
0x1800451d3  jz      short loc_1800451F3
0x1800451d5  mov     rax, [rax]
0x1800451d8  mov     edx, 7F0h
0x1800451dd  mov     rax, [rax+8]
0x1800451e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451e6  test    eax, eax
0x1800451e8  jz      short loc_1800451F3
0x1800451ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800451f1  jmp     short loc_180045201
0x1800451f3  lea     rcx, qword_1800D6F70; this
0x1800451fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045201  cmp     byte ptr [rcx+8], 0
0x180045205  jz      short loc_180045229
0x180045207  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004520c  cmp     [rax+7CCh], r14d
0x180045213  jz      short loc_180045229
0x180045215  mov     r9d, r14d; int
0x180045218  mov     r8d, 2DAh; int
0x18004521e  mov     rdx, r12; char *
0x180045221  mov     rcx, rax; this
0x180045224  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045229  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180045230  jb      short loc_180045256
0x180045232  mov     edx, 20h ; ' '
0x180045237  mov     dword ptr [rsp+480h+var_460], r14d
0x18004523c  mov     r9, rdi
0x18004523f  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180045246  mov     rcx, cs:WPP_GLOBAL_Control
0x18004524d  mov     rcx, [rcx+10h]
0x180045251  call    WPP_SF_qD
0x180045256  mov     ebx, r14d
0x180045259  jmp     loc_1800452FA
0x18004525e  mov     rbx, [rsp+480h+var_448]
0x180045263  cmp     rbx, rsi
  ... truncated ...
```
