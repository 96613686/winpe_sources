# mkvparser::Segment::CreateInstance(mkvparser::IMkvReader *,__int64 &,long &,mkvparser::Segment * &)

- ea: `0x1800867f0`
- end: `0x180086e9a`
- name: `?CreateInstance@Segment@mkvparser@@SAJPEAUIMkvReader@2@AEA_JAEAJAEAPEAV12@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(struct mkvparser::IMkvReader *this, __int64 *, int *, struct mkvparser::Segment **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001efb0`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800867f0`
- `0x18008c410`
- `0x1800a9220`
- `0x1800a96cc`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086847`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086ae1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086c2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086cc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086d50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086ddf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086847`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800868e0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086999`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086ae1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086c2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086cc1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086d50`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086ddf`

## string_xrefs

- `0x18008680a`: `mkvparser::Segment::CreateInstance`
- `0x180086b3d`: `mkvparser::Segment::CreateInstance`
- `0x180086c89`: `mkvparser::Segment::CreateInstance`
- `0x180086d18`: `mkvparser::Segment::CreateInstance`
- `0x180086da7`: `mkvparser::Segment::CreateInstance`
- `0x180086e36`: `mkvparser::Segment::CreateInstance`

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
                  v55 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v52 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v49 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
                  v40 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v58 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
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
0x1800867f0  mov     [rsp-38h+arg_8], rbx
0x1800867f5  push    rbp
0x1800867f6  push    rsi
0x1800867f7  push    rdi
0x1800867f8  push    r12
0x1800867fa  push    r13
0x1800867fc  push    r14
0x1800867fe  push    r15
0x180086800  mov     rbp, rsp
0x180086803  sub     rsp, 40h
0x180086807  mov     r14, r8
0x18008680a  lea     r15, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x180086811  mov     rdi, rdx
0x180086814  mov     rsi, rcx
0x180086817  xor     r13d, r13d
0x18008681a  lea     rcx, [rbp+arg_0]; this
0x18008681e  mov     rdx, r15; char *
0x180086821  mov     [r9], r13
0x180086824  mov     r8d, 3A4h; int
0x18008682a  mov     r12, r9
0x18008682d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180086832  test    rsi, rsi
0x180086835  jnz     loc_1800868CB
0x18008683b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086842  test    rcx, rcx
0x180086845  jnz     short loc_180086888
0x180086847  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008684d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086854  mov     rcx, rax
0x180086857  test    rax, rax
0x18008685a  jz      short loc_18008687A
0x18008685c  mov     rax, [rax]
0x18008685f  mov     edx, 7F0h
0x180086864  mov     rax, [rax+8]
0x180086868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008686d  test    eax, eax
0x18008686f  jz      short loc_18008687A
0x180086871  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086878  jmp     short loc_180086888
0x18008687a  lea     rcx, qword_1800D6F70; this
0x180086881  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086888  mov     ebx, 80070057h
0x18008688d  cmp     [rcx+8], r13b
0x180086891  jz      short loc_1800868B4
0x180086893  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086898  cmp     [rax+7CCh], ebx
0x18008689e  jz      short loc_1800868B4
0x1800868a0  mov     r9d, ebx; int
0x1800868a3  mov     r8d, 3A4h; int
0x1800868a9  mov     rdx, r15; char *
0x1800868ac  mov     rcx, rax; this
0x1800868af  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800868b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800868bb  jb      loc_180086E77
0x1800868c1  mov     edx, 50h ; 'P'
0x1800868c6  jmp     loc_180086E59
0x1800868cb  cmp     [rdi], r13
0x1800868ce  jge     loc_180086964
0x1800868d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868db  test    rcx, rcx
0x1800868de  jnz     short loc_180086921
0x1800868e0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800868e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800868ed  mov     rcx, rax
0x1800868f0  test    rax, rax
0x1800868f3  jz      short loc_180086913
0x1800868f5  mov     rax, [rax]
0x1800868f8  mov     edx, 7F0h
0x1800868fd  mov     rax, [rax+8]
0x180086901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086906  test    eax, eax
0x180086908  jz      short loc_180086913
0x18008690a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086911  jmp     short loc_180086921
0x180086913  lea     rcx, qword_1800D6F70; this
0x18008691a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086921  mov     ebx, 80070057h
0x180086926  cmp     [rcx+8], r13b
0x18008692a  jz      short loc_18008694D
0x18008692c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086931  cmp     [rax+7CCh], ebx
0x180086937  jz      short loc_18008694D
0x180086939  mov     r9d, ebx; int
0x18008693c  mov     r8d, 3A8h; int
0x180086942  mov     rdx, r15; char *
0x180086945  mov     rcx, rax; this
0x180086948  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008694d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086954  jb      loc_180086E77
0x18008695a  mov     edx, 51h ; 'Q'
0x18008695f  jmp     loc_180086E59
0x180086964  mov     rax, [rsi]
0x180086967  lea     r8, [rbp+var_8]
0x18008696b  lea     rdx, [rbp+var_10]
0x18008696f  mov     [rbp+var_10], r13
0x180086973  mov     rcx, rsi
0x180086976  mov     [rbp+var_8], r13
0x18008697a  mov     rax, [rax+8]
0x18008697e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086983  mov     ebx, eax
0x180086985  test    eax, eax
0x180086987  jns     loc_180086A18
0x18008698d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086994  test    rcx, rcx
0x180086997  jnz     short loc_1800869DA
0x180086999  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008699f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869a6  mov     rcx, rax
0x1800869a9  test    rax, rax
0x1800869ac  jz      short loc_1800869CC
0x1800869ae  mov     rax, [rax]
0x1800869b1  mov     edx, 7F0h
0x1800869b6  mov     rax, [rax+8]
0x1800869ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800869bf  test    eax, eax
0x1800869c1  jz      short loc_1800869CC
0x1800869c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869ca  jmp     short loc_1800869DA
0x1800869cc  lea     rcx, qword_1800D6F70; this
0x1800869d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800869da  cmp     [rcx+8], r13b
0x1800869de  jz      short loc_180086A01
0x1800869e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800869e5  cmp     [rax+7CCh], ebx
0x1800869eb  jz      short loc_180086A01
0x1800869ed  mov     r9d, ebx; int
0x1800869f0  mov     r8d, 3ACh; int
0x1800869f6  mov     rdx, r15; char *
0x1800869f9  mov     rcx, rax; this
0x1800869fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086a01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086a08  jb      loc_180086E77
0x180086a0e  mov     edx, 52h ; 'R'
0x180086a13  jmp     loc_180086E59
0x180086a18  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x180086a1b  mov     r8, r14; __int64
0x180086a1e  mov     rcx, rsi; this
0x180086a21  call    ?GetUIntLength@mkvparser@@YAJPEAUIMkvReader@1@_JAEAJ@Z; mkvparser::GetUIntLength(mkvparser::IMkvReader *,__int64,long &)
0x180086a26  mov     ebx, eax
0x180086a28  test    eax, eax
0x180086a2a  js      loc_180086DD3
0x180086a30  mov     rax, [rsi]
0x180086a33  mov     rcx, rsi
0x180086a36  mov     rax, [rax+10h]
0x180086a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086a3f  mov     r15, [rdi]
0x180086a42  mov     rcx, [rax+10h]
0x180086a46  movsxd  rax, dword ptr [r14]
0x180086a49  cmp     rax, rcx
0x180086a4c  jle     short loc_180086A54
0x180086a4e  lea     rax, [r15+1]
0x180086a52  jmp     short loc_180086ACD
0x180086a54  mov     r9, r14; __int64 *
0x180086a57  mov     [rbp+arg_18], r13
0x180086a5b  lea     r8, [rbp+arg_18]; __int64
0x180086a5f  mov     rdx, r15; struct mkvparser::IMkvReader *
0x180086a62  mov     rcx, rsi; this
0x180086a65  call    ?ReadID@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadID(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180086a6a  mov     ebx, eax
0x180086a6c  test    eax, eax
0x180086a6e  js      loc_180086D44
0x180086a74  movsxd  rax, dword ptr [r14]
0x180086a77  lea     r8, [rbp+arg_0]; __int64
0x180086a7b  add     [rdi], rax
0x180086a7e  mov     r9, r14; __int64 *
0x180086a81  mov     rdx, [rdi]; struct mkvparser::IMkvReader *
0x180086a84  mov     rcx, rsi; this
0x180086a87  mov     [rbp+arg_0], r13
0x180086a8b  call    ?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z; mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)
0x180086a90  mov     ebx, eax
0x180086a92  test    eax, eax
0x180086a94  js      loc_180086CB5
0x180086a9a  movsxd  rax, dword ptr [r14]
0x180086a9d  add     [rdi], rax
0x180086aa0  mov     eax, 1
0x180086aa5  imul    ecx, [r14], 7
0x180086aa9  mov     rdx, [rdi]
0x180086aac  shl     rax, cl
0x180086aaf  cmp     [rbp+arg_18], 18538067h
0x180086ab7  lea     rcx, [rax-1]
0x180086abb  jz      loc_180086B69
0x180086ac1  mov     rax, [rbp+arg_0]
0x180086ac5  cmp     rax, rcx
0x180086ac8  jz      short loc_180086AD5
0x180086aca  add     rax, rdx
0x180086acd  mov     [rdi], rax
0x180086ad0  jmp     loc_180086A18
0x180086ad5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086adc  test    rcx, rcx
0x180086adf  jnz     short loc_180086B22
0x180086ae1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086ae7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086aee  mov     rcx, rax
0x180086af1  test    rax, rax
0x180086af4  jz      short loc_180086B14
0x180086af6  mov     rax, [rax]
0x180086af9  mov     edx, 7F0h
0x180086afe  mov     rax, [rax+8]
0x180086b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086b07  test    eax, eax
0x180086b09  jz      short loc_180086B14
0x180086b0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086b12  jmp     short loc_180086B22
0x180086b14  lea     rcx, qword_1800D6F70; this
0x180086b1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086b22  mov     ebx, 0C00D36BEh
0x180086b27  cmp     [rcx+8], r13b
0x180086b2b  jz      short loc_180086B52
0x180086b2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086b32  cmp     [rax+7CCh], ebx
0x180086b38  jz      short loc_180086B52
0x180086b3a  mov     r9d, ebx; int
0x180086b3d  lea     rdx, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x180086b44  mov     r8d, 3EEh; int
0x180086b4a  mov     rcx, rax; this
0x180086b4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086b52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086b59  jb      loc_180086E77
0x180086b5f  mov     edx, 57h ; 'W'
0x180086b64  jmp     loc_180086E59
0x180086b69  mov     rbx, [rbp+arg_0]
0x180086b6d  cmp     rbx, rcx
0x180086b70  jz      short loc_180086B84
0x180086b72  mov     rcx, [rbp+var_10]
0x180086b76  test    rcx, rcx
0x180086b79  js      short loc_180086B84
0x180086b7b  lea     rax, [rdx+rbx]
0x180086b7f  cmp     rax, rcx
0x180086b82  jle     short loc_180086B88
0x180086b84  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180086b88  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086b8f  mov     ecx, 0B8h; unsigned __int64
0x180086b94  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086b99  test    rax, rax
0x180086b9c  jz      short loc_180086C1D
0x180086b9e  mov     rcx, [rdi]
0x180086ba1  mov     [rax+18h], rbx
0x180086ba5  mov     ebx, r13d
0x180086ba8  mov     [rax+10h], rcx
0x180086bac  mov     [rax], rsi
0x180086baf  mov     [rax+8], r15
0x180086bb3  mov     [rax+20h], r13
0x180086bb7  mov     [rax+28h], r13
0x180086bbb  mov     [rax+30h], r13d
0x180086bbf  mov     [rax+38h], r13
0x180086bc3  mov     [rax+40h], r13
0x180086bc7  mov     [rax+48h], r13
0x180086bcb  mov     [rax+50h], r13
0x180086bcf  mov     [rax+58h], r13
0x180086bd3  mov     [rax+60h], rcx
0x180086bd7  mov     [rax+68h], r13
0x180086bdb  mov     [rax+70h], r13
0x180086bdf  mov     [rax+78h], r13
0x180086be3  mov     [rax+80h], r13
0x180086bea  mov     [rax+88h], r13
0x180086bf1  mov     [rax+90h], r13
0x180086bf8  mov     [rax+98h], r13
0x180086bff  mov     [rax+0A0h], r13
0x180086c06  mov     [rax+0A8h], r13
0x180086c0d  mov     [rax+0B0h], r13d
0x180086c14  mov     [r12], rax
0x180086c18  jmp     loc_180086E77
0x180086c1d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086c24  mov     [r12], r13
0x180086c28  test    rcx, rcx
0x180086c2b  jnz     short loc_180086C6E
0x180086c2d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086c33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086c3a  mov     rcx, rax
0x180086c3d  test    rax, rax
0x180086c40  jz      short loc_180086C60
0x180086c42  mov     rax, [rax]
0x180086c45  mov     edx, 7F0h
0x180086c4a  mov     rax, [rax+8]
0x180086c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086c53  test    eax, eax
0x180086c55  jz      short loc_180086C60
0x180086c57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086c5e  jmp     short loc_180086C6E
0x180086c60  lea     rcx, qword_1800D6F70; this
0x180086c67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086c6e  mov     ebx, 8007000Eh
0x180086c73  cmp     [rcx+8], r13b
0x180086c77  jz      short loc_180086C9E
0x180086c79  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086c7e  cmp     [rax+7CCh], ebx
0x180086c84  jz      short loc_180086C9E
0x180086c86  mov     r9d, ebx; int
0x180086c89  lea     rdx, aMkvparserSegme_7; "mkvparser::Segment::CreateInstance"
0x180086c90  mov     r8d, 3E7h; int
0x180086c96  mov     rcx, rax; this
0x180086c99  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086c9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086ca5  jb      loc_180086E77
0x180086cab  mov     edx, 56h ; 'V'
0x180086cb0  jmp     loc_180086E59
0x180086cb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086cbc  test    rcx, rcx
0x180086cbf  jnz     short loc_180086D02
0x180086cc1  call    cs:__imp_MFGetCallStackTracingWeakReference
  ... truncated ...
```
