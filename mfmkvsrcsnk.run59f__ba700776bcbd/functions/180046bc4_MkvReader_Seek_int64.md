# MkvReader::Seek(__int64)

- ea: `0x180046bc4`
- end: `0x1800471c3`
- name: `?Seek@MkvReader@@QEAAJ_J@Z`
- size: `1535`
- prototype: `__int64 __fastcall(MkvReader *__hidden this, __int64)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e670`
- `0x18001895c`
- `0x180019320`
- `0x180019a74`
- `0x18001fbf0`
- `0x180020110`

## callees

- `0x180002400`
- `0x180002e54`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180046bc4`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046c48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046cdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046fb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004704a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047108`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046c48`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046cdf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046d8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046e5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046fb9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004704a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180047108`

## string_xrefs

- `0x180046c08`: `MkvReader::Seek`

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
                  v32 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                    v29 = &qword_1800DBF70;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v35 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v19 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v15 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v12 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180046bc4  mov     [rsp-8+arg_10], rbx
0x180046bc9  push    rbp
0x180046bca  push    rsi
0x180046bcb  push    rdi
0x180046bcc  push    r12
0x180046bce  push    r14
0x180046bd0  lea     rbp, [rsp-360h]
0x180046bd8  sub     rsp, 460h
0x180046bdf  mov     rax, cs:__security_cookie
0x180046be6  xor     rax, rsp
0x180046be9  mov     [rbp+380h+var_30], rax
0x180046bf0  mov     rsi, rdx
0x180046bf3  mov     rdi, rcx
0x180046bf6  mov     [rsp+480h+var_440], 0
0x180046bff  mov     r14d, 2ACh
0x180046c05  mov     r8d, r14d; int
0x180046c08  lea     r12, aMkvreaderSeek; "MkvReader::Seek"
0x180046c0f  mov     rdx, r12; char *
0x180046c12  lea     rcx, [rsp+480h+var_450]; this
0x180046c17  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046c1c  nop
0x180046c1d  mov     rcx, [rdi+10h]
0x180046c21  mov     rax, [rcx]
0x180046c24  lea     rdx, [rsp+480h+var_440]
0x180046c29  mov     rax, [rax+30h]
0x180046c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c32  mov     ebx, eax
0x180046c34  test    eax, eax
0x180046c36  jns     loc_180046CCA
0x180046c3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046c43  test    rcx, rcx
0x180046c46  jnz     short loc_180046C8F
0x180046c48  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046c4f  nop     dword ptr [rax+rax+00h]
0x180046c54  mov     rcx, rax
0x180046c57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046c5e  test    rax, rax
0x180046c61  jz      short loc_180046C81
0x180046c63  mov     rax, [rax]
0x180046c66  mov     edx, 7F0h
0x180046c6b  mov     rax, [rax+8]
0x180046c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c74  test    eax, eax
0x180046c76  jz      short loc_180046C81
0x180046c78  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046c7f  jmp     short loc_180046C8F
0x180046c81  lea     rcx, qword_1800DBF70; this
0x180046c88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046c8f  cmp     byte ptr [rcx+8], 0
0x180046c93  jz      short loc_180046CB3
0x180046c95  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046c9a  cmp     [rax+7CCh], ebx
0x180046ca0  jz      short loc_180046CB3
0x180046ca2  mov     r9d, ebx; int
0x180046ca5  mov     r8d, r14d; int
0x180046ca8  mov     rdx, r12; char *
0x180046cab  mov     rcx, rax; this
0x180046cae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046cb3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046cba  jb      loc_180047190
0x180046cc0  mov     edx, 1Bh
0x180046cc5  jmp     loc_180046E12
0x180046cca  test    rsi, rsi
0x180046ccd  jns     loc_180046D69
0x180046cd3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cda  test    rcx, rcx
0x180046cdd  jnz     short loc_180046D26
0x180046cdf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046ce6  nop     dword ptr [rax+rax+00h]
0x180046ceb  mov     rcx, rax
0x180046cee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046cf5  test    rax, rax
0x180046cf8  jz      short loc_180046D18
0x180046cfa  mov     rax, [rax]
0x180046cfd  mov     edx, 7F0h
0x180046d02  mov     rax, [rax+8]
0x180046d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d0b  test    eax, eax
0x180046d0d  jz      short loc_180046D18
0x180046d0f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d16  jmp     short loc_180046D26
0x180046d18  lea     rcx, qword_1800DBF70; this
0x180046d1f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d26  mov     ebx, 80070057h
0x180046d2b  cmp     byte ptr [rcx+8], 0
0x180046d2f  jz      short loc_180046D52
0x180046d31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046d36  cmp     [rax+7CCh], ebx
0x180046d3c  jz      short loc_180046D52
0x180046d3e  mov     r9d, ebx; int
0x180046d41  mov     r8d, 2B0h; int
0x180046d47  mov     rdx, r12; char *
0x180046d4a  mov     rcx, rax; this
0x180046d4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046d52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046d59  jb      loc_180047190
0x180046d5f  mov     edx, 1Ch
0x180046d64  jmp     loc_180046E12
0x180046d69  cmp     byte ptr [rdi+0E4h], 0
0x180046d70  jnz     loc_180046E35
0x180046d76  cmp     rsi, [rsp+480h+var_440]
0x180046d7b  jnb     loc_180046E35
0x180046d81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046d88  test    rcx, rcx
0x180046d8b  jnz     short loc_180046DD4
0x180046d8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046d94  nop     dword ptr [rax+rax+00h]
0x180046d99  mov     rcx, rax
0x180046d9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046da3  test    rax, rax
0x180046da6  jz      short loc_180046DC6
0x180046da8  mov     rax, [rax]
0x180046dab  mov     edx, 7F0h
0x180046db0  mov     rax, [rax+8]
0x180046db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046db9  test    eax, eax
0x180046dbb  jz      short loc_180046DC6
0x180046dbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046dc4  jmp     short loc_180046DD4
0x180046dc6  lea     rcx, qword_1800DBF70; this
0x180046dcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046dd4  mov     ebx, 0C00D36EEh
0x180046dd9  cmp     byte ptr [rcx+8], 0
0x180046ddd  jz      short loc_180046E00
0x180046ddf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046de4  cmp     [rax+7CCh], ebx
0x180046dea  jz      short loc_180046E00
0x180046dec  mov     r9d, ebx; int
0x180046def  mov     r8d, 2B7h; int
0x180046df5  mov     rdx, r12; char *
0x180046df8  mov     rcx, rax; this
0x180046dfb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046e00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046e07  jb      loc_180047190
0x180046e0d  mov     edx, 1Dh
0x180046e12  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e19  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x180046e20  mov     r9, rdi
0x180046e23  mov     dword ptr [rsp+480h+var_460], ebx
0x180046e27  mov     rcx, [rcx+10h]
0x180046e2b  call    WPP_SF_qD
0x180046e30  jmp     loc_180047190
0x180046e35  mov     rax, [rdi+0C8h]
0x180046e3c  test    rax, rax
0x180046e3f  js      loc_180046EE4
0x180046e45  cmp     rsi, rax
0x180046e48  jle     loc_180046EE4
0x180046e4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e55  test    rcx, rcx
0x180046e58  jnz     short loc_180046EA1
0x180046e5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046e61  nop     dword ptr [rax+rax+00h]
0x180046e66  mov     rcx, rax
0x180046e69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e70  test    rax, rax
0x180046e73  jz      short loc_180046E93
0x180046e75  mov     rax, [rax]
0x180046e78  mov     edx, 7F0h
0x180046e7d  mov     rax, [rax+8]
0x180046e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e86  test    eax, eax
0x180046e88  jz      short loc_180046E93
0x180046e8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046e91  jmp     short loc_180046EA1
0x180046e93  lea     rcx, qword_1800DBF70; this
0x180046e9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ea1  mov     ebx, 80070057h
0x180046ea6  cmp     byte ptr [rcx+8], 0
0x180046eaa  jz      short loc_180046ECD
0x180046eac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180046eb1  cmp     [rax+7CCh], ebx
0x180046eb7  jz      short loc_180046ECD
0x180046eb9  mov     r9d, ebx; int
0x180046ebc  mov     r8d, 2BDh; int
0x180046ec2  mov     rdx, r12; char *
0x180046ec5  mov     rcx, rax; this
0x180046ec8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180046ecd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180046ed4  jb      loc_180047190
0x180046eda  mov     edx, 1Eh
0x180046edf  jmp     loc_180046E12
0x180046ee4  mov     ecx, [rdi+9Ch]
0x180046eea  xor     edx, edx
0x180046eec  mov     rax, rsi
0x180046eef  div     rcx
0x180046ef2  sub     rsi, rdx
0x180046ef5  mov     [rsp+480h+var_448], 0
0x180046efe  mov     rcx, [rdi+10h]
0x180046f02  mov     rax, [rcx]
0x180046f05  lea     rdx, [rsp+480h+var_448]
0x180046f0a  mov     [rsp+480h+var_460], rdx
0x180046f0f  mov     r9d, 1
0x180046f15  mov     r8, rsi
0x180046f18  xor     edx, edx
0x180046f1a  mov     rax, [rax+78h]
0x180046f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f23  mov     r14d, eax
0x180046f26  test    eax, eax
0x180046f28  jns     loc_1800470EE
0x180046f2e  mov     rbx, [rsp+480h+var_440]
0x180046f33  cmp     rsi, rbx
0x180046f36  jnb     loc_18004703E
0x180046f3c  mov     [rsp+480h+var_448], rbx
0x180046f41  mov     r14d, 400h
0x180046f47  mov     r8d, r14d; Size
0x180046f4a  xor     edx, edx; Val
0x180046f4c  lea     rcx, [rsp+480h+var_430]; void *
0x180046f51  call    memset_0
0x180046f56  mov     rcx, rbx
0x180046f59  cmp     rbx, rsi
0x180046f5c  jnb     loc_1800470F3
0x180046f62  mov     [rsp+480h+var_44C], 0
0x180046f6a  mov     rax, rsi
0x180046f6d  sub     rax, rbx
0x180046f70  mov     r8, r14
0x180046f73  cmp     rax, r14
0x180046f76  cmovb   r8, rax
0x180046f7a  mov     rcx, [rdi+10h]
0x180046f7e  mov     rax, [rcx]
0x180046f81  lea     r9, [rsp+480h+var_44C]
0x180046f86  lea     rdx, [rsp+480h+var_430]
0x180046f8b  mov     rax, [rax+48h]
0x180046f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f94  mov     ebx, eax
0x180046f96  test    eax, eax
0x180046f98  js      short loc_180046FAD
0x180046f9a  mov     eax, [rsp+480h+var_44C]
0x180046f9e  mov     rbx, [rsp+480h+var_448]
0x180046fa3  add     rbx, rax
0x180046fa6  mov     [rsp+480h+var_448], rbx
0x180046fab  jmp     short loc_180046F56
0x180046fad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046fb4  test    rcx, rcx
0x180046fb7  jnz     short loc_180047000
0x180046fb9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046fc0  nop     dword ptr [rax+rax+00h]
0x180046fc5  mov     rcx, rax
0x180046fc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046fcf  test    rax, rax
0x180046fd2  jz      short loc_180046FF2
0x180046fd4  mov     rax, [rax]
0x180046fd7  mov     edx, 7F0h
0x180046fdc  mov     rax, [rax+8]
0x180046fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fe5  test    eax, eax
0x180046fe7  jz      short loc_180046FF2
0x180046fe9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046ff0  jmp     short loc_180047000
0x180046ff2  lea     rcx, qword_1800DBF70; this
0x180046ff9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047000  cmp     byte ptr [rcx+8], 0
0x180047004  jz      short loc_180047027
0x180047006  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004700b  cmp     [rax+7CCh], ebx
0x180047011  jz      short loc_180047027
0x180047013  mov     r9d, ebx; int
0x180047016  mov     r8d, 2D4h; int
0x18004701c  mov     rdx, r12; char *
0x18004701f  mov     rcx, rax; this
0x180047022  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180047027  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004702e  jb      loc_180047190
0x180047034  mov     edx, 1Fh
0x180047039  jmp     loc_180046E12
0x18004703e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047045  test    rcx, rcx
0x180047048  jnz     short loc_180047091
0x18004704a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180047051  nop     dword ptr [rax+rax+00h]
0x180047056  mov     rcx, rax
0x180047059  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180047060  test    rax, rax
0x180047063  jz      short loc_180047083
0x180047065  mov     rax, [rax]
0x180047068  mov     edx, 7F0h
0x18004706d  mov     rax, [rax+8]
0x180047071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047076  test    eax, eax
0x180047078  jz      short loc_180047083
0x18004707a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180047081  jmp     short loc_180047091
0x180047083  lea     rcx, qword_1800DBF70; this
0x18004708a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180047091  cmp     byte ptr [rcx+8], 0
0x180047095  jz      short loc_1800470B9
0x180047097  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004709c  cmp     [rax+7CCh], r14d
0x1800470a3  jz      short loc_1800470B9
0x1800470a5  mov     r9d, r14d; int
0x1800470a8  mov     r8d, 2DAh; int
0x1800470ae  mov     rdx, r12; char *
0x1800470b1  mov     rcx, rax; this
0x1800470b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800470b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800470c0  jb      short loc_1800470E6
0x1800470c2  mov     edx, 20h ; ' '
0x1800470c7  mov     dword ptr [rsp+480h+var_460], r14d
0x1800470cc  mov     r9, rdi
0x1800470cf  lea     r8, WPP_ce33925e7ded33c209f42ae20365e85e_Traceguids
0x1800470d6  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
