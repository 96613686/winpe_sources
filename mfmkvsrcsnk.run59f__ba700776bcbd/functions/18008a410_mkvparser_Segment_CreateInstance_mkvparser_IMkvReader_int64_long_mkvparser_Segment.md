# mkvparser::Segment::CreateInstance(mkvparser::IMkvReader *,__int64 &,long &,mkvparser::Segment * &)

- ea: `0x18008a410`
- end: `0x18008aaeb`
- name: `?CreateInstance@Segment@mkvparser@@SAJPEAUIMkvReader@2@AEA_JAEAJAEAPEAV12@@Z`
- size: `1755`
- prototype: `__int64 __fastcall(struct mkvparser::IMkvReader *this, __int64 *, int *, struct mkvparser::Segment **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001fdc0`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18008a410`
- `0x1800902b8`
- `0x1800adea8`
- `0x1800ae378`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a506`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a5c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a713`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a865`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a8ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008aa29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a506`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a5c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a713`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a865`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a8ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008a994`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008aa29`

## string_xrefs

- `0x18008a42a`: `mkvparser::Segment::CreateInstance`
- `0x18008a775`: `mkvparser::Segment::CreateInstance`
- `0x18008a8c7`: `mkvparser::Segment::CreateInstance`
- `0x18008a95c`: `mkvparser::Segment::CreateInstance`
- `0x18008a9f1`: `mkvparser::Segment::CreateInstance`
- `0x18008aa86`: `mkvparser::Segment::CreateInstance`

## pseudocode

```c
__int64 __fastcall mkvparser::Segment::CreateInstance(
        struct mkvparser::IMkvReader *this,
        struct mkvparser::IMkvReader **a2,
        __int64 *a3,
        struct mkvparser::Segment **a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int UIntLength; // ebx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  int *v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rax
  struct mkvparser::IMkvReader *v30; // r15
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  struct mkvparser::IMkvReader *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  struct mkvparser::IMkvReader *v38; // rdx
  __int64 v39; // rcx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rbx
  _QWORD *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  struct mkvparser::IMkvReader *v48; // rcx
  __int64 *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 *v55; // rcx
  CallStackTracing *v56; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v58; // rcx
  CallStackTracing *v59; // rax
  struct CallStackContext *v60; // rax
  int *v62; // [rsp+20h] [rbp-20h]
  int *v63; // [rsp+20h] [rbp-20h]
  __int64 v64; // [rsp+30h] [rbp-10h] BYREF
  __int64 v65; // [rsp+38h] [rbp-8h] BYREF
  __int64 v66; // [rsp+80h] [rbp+40h] BYREF
  __int64 v67; // [rsp+98h] [rbp+58h] BYREF

  *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v66, "mkvparser::Segment::CreateInstance", 932);
  if ( this )
  {
    if ( (__int64)*a2 >= 0 )
    {
      v19 = *(_QWORD *)this;
      v64 = 0;
      v65 = 0;
      UIntLength = (*(__int64 (__fastcall **)(struct mkvparser::IMkvReader *, __int64 *, __int64 *))(v19 + 8))(
                     this,
                     &v64,
                     &v65);
      if ( UIntLength >= 0 )
      {
        while ( 1 )
        {
          UIntLength = mkvparser::GetUIntLength(this, *a2, (__int64)a3, v22);
          if ( UIntLength < 0 )
            break;
          v29 = (*(__int64 (__fastcall **)(struct mkvparser::IMkvReader *))(*(_QWORD *)this + 16LL))(this);
          v30 = *a2;
          if ( *(int *)a3 <= *(_QWORD *)(v29 + 16) )
          {
            v67 = 0;
            UIntLength = mkvparser::ReadID(this, v30, (__int64)&v67, a3, v62);
            if ( UIntLength < 0 )
            {
              v55 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
                CallStackTracing::s_wpInstance = v56;
                if ( v56
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
                {
                  v55 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v55 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v55 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v55);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != UIntLength )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "mkvparser::Segment::CreateInstance",
                    972,
                    UIntLength);
              }
              if ( g_wppLevels )
              {
                v15 = 84;
                goto LABEL_99;
              }
              goto LABEL_100;
            }
            *a2 = (struct mkvparser::IMkvReader *)((char *)*a2 + *(int *)a3);
            v35 = *a2;
            v66 = 0;
            UIntLength = mkvparser::ReadUInt(this, v35, (__int64)&v66, a3, v63);
            if ( UIntLength < 0 )
            {
              v52 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36, v37, v22);
                CallStackTracing::s_wpInstance = v53;
                if ( v53
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                {
                  v52 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v52 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              if ( *((_BYTE *)v52 + 8) )
              {
                v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                if ( *((_DWORD *)v54 + 499) != UIntLength )
                  CallStackContext::TraceFailure(v54, "mkvparser::Segment::CreateInstance", 979, UIntLength);
              }
              if ( g_wppLevels )
              {
                v15 = 85;
                goto LABEL_99;
              }
              goto LABEL_100;
            }
            *a2 = (struct mkvparser::IMkvReader *)((char *)*a2 + *(int *)a3);
            v38 = *a2;
            v39 = (1LL << (7 * *(_BYTE *)a3)) - 1;
            if ( v67 == 408125543 )
            {
              v43 = v66;
              if ( v66 == v39 || v64 < 0 || (__int64)v38 + v66 > v64 )
                v43 = -1;
              v44 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v44 )
              {
                v48 = *a2;
                v44[3] = v43;
                UIntLength = 0;
                v44[2] = v48;
                *v44 = this;
                v44[1] = v30;
                v44[4] = 0;
                v44[5] = 0;
                *((_DWORD *)v44 + 12) = 0;
                v44[7] = 0;
                v44[8] = 0;
                v44[9] = 0;
                v44[10] = 0;
                v44[11] = 0;
                v44[12] = v48;
                v44[13] = 0;
                v44[14] = 0;
                v44[15] = 0;
                v44[16] = 0;
                v44[17] = 0;
                v44[18] = 0;
                v44[19] = 0;
                v44[20] = 0;
                v44[21] = 0;
                *((_DWORD *)v44 + 44) = 0;
                *a4 = (struct mkvparser::Segment *)v44;
                goto LABEL_100;
              }
              v49 = (__int64 *)CallStackTracing::s_wpInstance;
              *a4 = 0;
              if ( !v49 )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              UIntLength = -2147024882;
              if ( *((_BYTE *)v49 + 8) )
              {
                v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
                if ( *((_DWORD *)v51 + 499) != -2147024882 )
                  CallStackContext::TraceFailure(v51, "mkvparser::Segment::CreateInstance", 999, -2147024882);
              }
              if ( g_wppLevels )
              {
                v15 = 86;
                goto LABEL_99;
              }
              goto LABEL_100;
            }
            if ( v66 == v39 )
            {
              v40 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v37, v22);
                CallStackTracing::s_wpInstance = v41;
                if ( v41
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v40 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
                }
              }
              UIntLength = -1072875842;
              if ( *((_BYTE *)v40 + 8) )
              {
                v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                if ( *((_DWORD *)v42 + 499) != -1072875842 )
                  CallStackContext::TraceFailure(v42, "mkvparser::Segment::CreateInstance", 1006, -1072875842);
              }
              if ( g_wppLevels )
              {
                v15 = 87;
                goto LABEL_99;
              }
              goto LABEL_100;
            }
            v31 = (__int64)v38 + v66;
          }
          else
          {
            v31 = (__int64)v30 + 1;
          }
          *a2 = (struct mkvparser::IMkvReader *)v31;
        }
        v58 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v59 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
          CallStackTracing::s_wpInstance = v59;
          if ( v59 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v59 + 8LL))(v59, 2032) )
          {
            v58 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v58 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v58 + 8) )
        {
          v60 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v58);
          if ( *((_DWORD *)v60 + 499) != UIntLength )
            CallStackContext::TraceFailure(v60, "mkvparser::Segment::CreateInstance", 961, UIntLength);
        }
        if ( g_wppLevels )
        {
          v15 = 83;
          goto LABEL_99;
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != UIntLength )
            CallStackContext::TraceFailure(v25, "mkvparser::Segment::CreateInstance", 940, UIntLength);
        }
        if ( g_wppLevels )
        {
          v15 = 82;
          goto LABEL_99;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
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
      UIntLength = -2147024809;
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v18, "mkvparser::Segment::CreateInstance", 936, -2147024809);
      }
      if ( g_wppLevels )
      {
        v15 = 81;
        goto LABEL_99;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    UIntLength = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "mkvparser::Segment::CreateInstance", 932, -2147024809);
    }
    if ( g_wppLevels )
    {
      v15 = 80;
LABEL_99:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
        0,
        UIntLength);
    }
  }
LABEL_100:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v66);
  return (unsigned int)UIntLength;
}

```

## disassembly

```asm
0x18008a410  mov     [rsp-38h+arg_8], rbx
0x18008a415  push    rbp
0x18008a416  push    rsi
0x18008a417  push    rdi
0x18008a418  push    r12
0x18008a41a  push    r13
0x18008a41c  push    r14
0x18008a41e  push    r15
0x18008a420  mov     rbp, rsp
0x18008a423  sub     rsp, 40h
0x18008a427  mov     r14, r8
0x18008a42a  lea     r15, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x18008a431  mov     rdi, rdx
0x18008a434  mov     rsi, rcx
0x18008a437  xor     r13d, r13d
0x18008a43a  lea     rcx, [rbp+arg_0]; this
0x18008a43e  mov     rdx, r15; char *
0x18008a441  mov     [r9], r13
0x18008a444  mov     r8d, 3A4h; int
0x18008a44a  mov     r12, r9
0x18008a44d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008a452  test    rsi, rsi
0x18008a455  jnz     loc_18008A4F1
0x18008a45b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a462  test    rcx, rcx
0x18008a465  jnz     short loc_18008A4AE
0x18008a467  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008a46e  nop     dword ptr [rax+rax+00h]
0x18008a473  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a47a  mov     rcx, rax
0x18008a47d  test    rax, rax
0x18008a480  jz      short loc_18008A4A0
0x18008a482  mov     rax, [rax]
0x18008a485  mov     edx, 7F0h
0x18008a48a  mov     rax, [rax+8]
0x18008a48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a493  test    eax, eax
0x18008a495  jz      short loc_18008A4A0
0x18008a497  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a49e  jmp     short loc_18008A4AE
0x18008a4a0  lea     rcx, qword_1800DBF70; this
0x18008a4a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a4ae  mov     ebx, 80070057h
0x18008a4b3  cmp     [rcx+8], r13b
0x18008a4b7  jz      short loc_18008A4DA
0x18008a4b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a4be  cmp     [rax+7CCh], ebx
0x18008a4c4  jz      short loc_18008A4DA
0x18008a4c6  mov     r9d, ebx; int
0x18008a4c9  mov     r8d, 3A4h; int
0x18008a4cf  mov     rdx, r15; char *
0x18008a4d2  mov     rcx, rax; this
0x18008a4d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a4da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008a4e1  jb      loc_18008AAC7
0x18008a4e7  mov     edx, 50h ; 'P'
0x18008a4ec  jmp     loc_18008AAA9
0x18008a4f1  cmp     [rdi], r13
0x18008a4f4  jge     loc_18008A590
0x18008a4fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a501  test    rcx, rcx
0x18008a504  jnz     short loc_18008A54D
0x18008a506  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008a50d  nop     dword ptr [rax+rax+00h]
0x18008a512  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a519  mov     rcx, rax
0x18008a51c  test    rax, rax
0x18008a51f  jz      short loc_18008A53F
0x18008a521  mov     rax, [rax]
0x18008a524  mov     edx, 7F0h
0x18008a529  mov     rax, [rax+8]
0x18008a52d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a532  test    eax, eax
0x18008a534  jz      short loc_18008A53F
0x18008a536  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a53d  jmp     short loc_18008A54D
0x18008a53f  lea     rcx, qword_1800DBF70; this
0x18008a546  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a54d  mov     ebx, 80070057h
0x18008a552  cmp     [rcx+8], r13b
0x18008a556  jz      short loc_18008A579
0x18008a558  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a55d  cmp     [rax+7CCh], ebx
0x18008a563  jz      short loc_18008A579
0x18008a565  mov     r9d, ebx; int
0x18008a568  mov     r8d, 3A8h; int
0x18008a56e  mov     rdx, r15; char *
0x18008a571  mov     rcx, rax; this
0x18008a574  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a579  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008a580  jb      loc_18008AAC7
0x18008a586  mov     edx, 51h ; 'Q'
0x18008a58b  jmp     loc_18008AAA9
0x18008a590  mov     rax, [rsi]
0x18008a593  lea     r8, [rbp+var_8]
0x18008a597  lea     rdx, [rbp+var_10]
0x18008a59b  mov     [rbp+var_10], r13
0x18008a59f  mov     rcx, rsi
0x18008a5a2  mov     [rbp+var_8], r13
0x18008a5a6  mov     rax, [rax+8]
0x18008a5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5af  mov     ebx, eax
0x18008a5b1  test    eax, eax
0x18008a5b3  jns     loc_18008A64A
0x18008a5b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a5c0  test    rcx, rcx
0x18008a5c3  jnz     short loc_18008A60C
0x18008a5c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008a5cc  nop     dword ptr [rax+rax+00h]
0x18008a5d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a5d8  mov     rcx, rax
0x18008a5db  test    rax, rax
0x18008a5de  jz      short loc_18008A5FE
0x18008a5e0  mov     rax, [rax]
0x18008a5e3  mov     edx, 7F0h
0x18008a5e8  mov     rax, [rax+8]
0x18008a5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a5f1  test    eax, eax
0x18008a5f3  jz      short loc_18008A5FE
0x18008a5f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a5fc  jmp     short loc_18008A60C
0x18008a5fe  lea     rcx, qword_1800DBF70; this
0x18008a605  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a60c  cmp     [rcx+8], r13b
0x18008a610  jz      short loc_18008A633
0x18008a612  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a617  cmp     [rax+7CCh], ebx
0x18008a61d  jz      short loc_18008A633
0x18008a61f  mov     r9d, ebx; int
0x18008a622  mov     r8d, 3ACh; int
0x18008a628  mov     rdx, r15; char *
0x18008a62b  mov     rcx, rax; this
0x18008a62e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a633  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008a63a  jb      loc_18008AAC7
0x18008a640  mov     edx, 52h ; 'R'
0x18008a645  jmp     loc_18008AAA9
0x18008a64a  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x18008a64d  mov     r8, r14; __int64
0x18008a650  mov     rcx, rsi; this
0x18008a653  call    ?GetUIntLength@mkvparser@@YAJPEAUIMkvReader@1@_JAEAJ@Z; mkvparser::GetUIntLength(mkvparser::IMkvReader *,__int64,long &)
0x18008a658  mov     ebx, eax
0x18008a65a  test    eax, eax
0x18008a65c  js      loc_18008AA1D
0x18008a662  mov     rax, [rsi]
0x18008a665  mov     rcx, rsi
0x18008a668  mov     rax, [rax+10h]
0x18008a66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a671  mov     r15, [rdi]
0x18008a674  mov     rcx, [rax+10h]
0x18008a678  movsxd  rax, dword ptr [r14]
0x18008a67b  cmp     rax, rcx
0x18008a67e  jle     short loc_18008A686
0x18008a680  lea     rax, [r15+1]
0x18008a684  jmp     short loc_18008A6FF
0x18008a686  mov     r9, r14; __int64 *
0x18008a689  mov     [rbp+arg_18], r13
0x18008a68d  lea     r8, [rbp+arg_18]; __int64
0x18008a691  mov     rdx, r15; struct mkvparser::IMkvReader *
0x18008a694  mov     rcx, rsi; this
0x18008a697  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x18008a69c  mov     ebx, eax
0x18008a69e  test    eax, eax
0x18008a6a0  js      loc_18008A988
0x18008a6a6  movsxd  rax, dword ptr [r14]
0x18008a6a9  lea     r8, [rbp+arg_0]; __int64
0x18008a6ad  add     [rdi], rax
0x18008a6b0  mov     r9, r14; __int64 *
0x18008a6b3  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x18008a6b6  mov     rcx, rsi; this
0x18008a6b9  mov     [rbp+arg_0], r13
0x18008a6bd  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x18008a6c2  mov     ebx, eax
0x18008a6c4  test    eax, eax
0x18008a6c6  js      loc_18008A8F3
0x18008a6cc  movsxd  rax, dword ptr [r14]
0x18008a6cf  add     [rdi], rax
0x18008a6d2  mov     eax, 1
0x18008a6d7  imul    ecx, [r14], 7
0x18008a6db  mov     rdx, [rdi]
0x18008a6de  shl     rax, cl
0x18008a6e1  cmp     [rbp+arg_18], 18538067h
0x18008a6e9  lea     rcx, [rax-1]
0x18008a6ed  jz      loc_18008A7A1
0x18008a6f3  mov     rax, [rbp+arg_0]
0x18008a6f7  cmp     rax, rcx
0x18008a6fa  jz      short loc_18008A707
0x18008a6fc  add     rax, rdx
0x18008a6ff  mov     [rdi], rax
0x18008a702  jmp     loc_18008A64A
0x18008a707  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a70e  test    rcx, rcx
0x18008a711  jnz     short loc_18008A75A
0x18008a713  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008a71a  nop     dword ptr [rax+rax+00h]
0x18008a71f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a726  mov     rcx, rax
0x18008a729  test    rax, rax
0x18008a72c  jz      short loc_18008A74C
0x18008a72e  mov     rax, [rax]
0x18008a731  mov     edx, 7F0h
0x18008a736  mov     rax, [rax+8]
0x18008a73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a73f  test    eax, eax
0x18008a741  jz      short loc_18008A74C
0x18008a743  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a74a  jmp     short loc_18008A75A
0x18008a74c  lea     rcx, qword_1800DBF70; this
0x18008a753  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a75a  mov     ebx, 0C00D36BEh
0x18008a75f  cmp     [rcx+8], r13b
0x18008a763  jz      short loc_18008A78A
0x18008a765  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a76a  cmp     [rax+7CCh], ebx
0x18008a770  jz      short loc_18008A78A
0x18008a772  mov     r9d, ebx; int
0x18008a775  lea     rdx, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x18008a77c  mov     r8d, 3EEh; int
0x18008a782  mov     rcx, rax; this
0x18008a785  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a78a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008a791  jb      loc_18008AAC7
0x18008a797  mov     edx, 57h ; 'W'
0x18008a79c  jmp     loc_18008AAA9
0x18008a7a1  mov     rbx, [rbp+arg_0]
0x18008a7a5  cmp     rbx, rcx
0x18008a7a8  jz      short loc_18008A7BC
0x18008a7aa  mov     rcx, [rbp+var_10]
0x18008a7ae  test    rcx, rcx
0x18008a7b1  js      short loc_18008A7BC
0x18008a7b3  lea     rax, [rdx+rbx]
0x18008a7b7  cmp     rax, rcx
0x18008a7ba  jle     short loc_18008A7C0
0x18008a7bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008a7c0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a7c7  mov     ecx, 0B8h; unsigned __int64
0x18008a7cc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008a7d1  test    rax, rax
0x18008a7d4  jz      short loc_18008A855
0x18008a7d6  mov     rcx, [rdi]
0x18008a7d9  mov     [rax+18h], rbx
0x18008a7dd  mov     ebx, r13d
0x18008a7e0  mov     [rax+10h], rcx
0x18008a7e4  mov     [rax], rsi
0x18008a7e7  mov     [rax+8], r15
0x18008a7eb  mov     [rax+20h], r13
0x18008a7ef  mov     [rax+28h], r13
0x18008a7f3  mov     [rax+30h], r13d
0x18008a7f7  mov     [rax+38h], r13
0x18008a7fb  mov     [rax+40h], r13
0x18008a7ff  mov     [rax+48h], r13
0x18008a803  mov     [rax+50h], r13
0x18008a807  mov     [rax+58h], r13
0x18008a80b  mov     [rax+60h], rcx
0x18008a80f  mov     [rax+68h], r13
0x18008a813  mov     [rax+70h], r13
0x18008a817  mov     [rax+78h], r13
0x18008a81b  mov     [rax+80h], r13
0x18008a822  mov     [rax+88h], r13
0x18008a829  mov     [rax+90h], r13
0x18008a830  mov     [rax+98h], r13
0x18008a837  mov     [rax+0A0h], r13
0x18008a83e  mov     [rax+0A8h], r13
0x18008a845  mov     [rax+0B0h], r13d
0x18008a84c  mov     [r12], rax
0x18008a850  jmp     loc_18008AAC7
0x18008a855  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a85c  mov     [r12], r13
0x18008a860  test    rcx, rcx
0x18008a863  jnz     short loc_18008A8AC
0x18008a865  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008a86c  nop     dword ptr [rax+rax+00h]
0x18008a871  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a878  mov     rcx, rax
0x18008a87b  test    rax, rax
0x18008a87e  jz      short loc_18008A89E
0x18008a880  mov     rax, [rax]
0x18008a883  mov     edx, 7F0h
0x18008a888  mov     rax, [rax+8]
0x18008a88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a891  test    eax, eax
0x18008a893  jz      short loc_18008A89E
0x18008a895  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a89c  jmp     short loc_18008A8AC
0x18008a89e  lea     rcx, qword_1800DBF70; this
0x18008a8a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008a8ac  mov     ebx, 8007000Eh
0x18008a8b1  cmp     [rcx+8], r13b
0x18008a8b5  jz      short loc_18008A8DC
0x18008a8b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008a8bc  cmp     [rax+7CCh], ebx
0x18008a8c2  jz      short loc_18008A8DC
0x18008a8c4  mov     r9d, ebx; int
0x18008a8c7  lea     rdx, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x18008a8ce  mov     r8d, 3E7h; int
0x18008a8d4  mov     rcx, rax; this
0x18008a8d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008a8dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008a8e3  jb      loc_18008AAC7
0x18008a8e9  mov     edx, 56h ; 'V'
  ... truncated ...
```
