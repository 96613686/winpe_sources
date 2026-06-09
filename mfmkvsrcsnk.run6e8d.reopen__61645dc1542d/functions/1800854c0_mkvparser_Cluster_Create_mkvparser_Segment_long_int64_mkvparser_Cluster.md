# mkvparser::Cluster::Create(mkvparser::Segment *,long,__int64,mkvparser::Cluster * &)

- ea: `0x1800854c0`
- end: `0x180085758`
- name: `?Create@Cluster@mkvparser@@SAJPEAVSegment@2@J_JAEAPEAV12@@Z`
- size: `664`
- prototype: `__int64 __fastcall(struct mkvparser::Segment *, int, __int64, struct Cluster **)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800870cc`
- `0x180088614`
- `0x18008a45c`
- `0x18008b0dc`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800854c0`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085513`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800855ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008569c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085513`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800855ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008569c`

## string_xrefs

- `0x1800854e7`: `mkvparser::Cluster::Create`
- `0x18008556f`: `mkvparser::Cluster::Create`
- `0x180085609`: `mkvparser::Cluster::Create`
- `0x1800856f8`: `mkvparser::Cluster::Create`

## pseudocode

```c
__int64 __fastcall mkvparser::Cluster::Create(struct mkvparser::Segment *a1, int a2, __int64 a3, struct Cluster **a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  unsigned int v13; // ebx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // r14
  struct Cluster *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v28; // [rsp+50h] [rbp+8h] BYREF

  *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v28, "mkvparser::Cluster::Create", 7564);
  if ( a1 )
  {
    if ( a3 >= 0 )
    {
      v19 = *((_QWORD *)a1 + 2);
      v20 = (struct Cluster *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v20 )
      {
        *a4 = v20;
        *((_QWORD *)v20 + 1) = v19 + a3;
        *((_QWORD *)v20 + 3) = v19 + a3;
        *((_QWORD *)v20 + 4) = -1;
        v13 = 0;
        *((_QWORD *)v20 + 5) = -1;
        *((_DWORD *)v20 + 15) = -1;
        *(_QWORD *)v20 = a1;
        *((_DWORD *)v20 + 4) = a2;
        *((_QWORD *)v20 + 6) = 0;
        *((_DWORD *)v20 + 14) = 0;
      }
      else
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        *a4 = 0;
        if ( !v24 )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v13 = -2147024882;
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Cluster::Create", 7574, -2147024882);
        }
        if ( g_wppLevels )
        {
          v15 = 685;
          goto LABEL_35;
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
      v13 = -2147024809;
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v18, "mkvparser::Cluster::Create", 7568, -2147024809);
      }
      if ( g_wppLevels )
      {
        v15 = 684;
        goto LABEL_35;
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
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "mkvparser::Cluster::Create", 7564, -2147024809);
    }
    if ( g_wppLevels )
    {
      v15 = 683;
LABEL_35:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return v13;
}

```

## disassembly

```asm
0x1800854c0  mov     [rsp+arg_8], rbx
0x1800854c5  mov     [rsp+arg_10], rbp
0x1800854ca  push    rsi
0x1800854cb  push    rdi
0x1800854cc  push    r14
0x1800854ce  sub     rsp, 30h
0x1800854d2  mov     rdi, r8
0x1800854d5  mov     qword ptr [r9], 0
0x1800854dc  mov     ebp, edx
0x1800854de  mov     rsi, rcx
0x1800854e1  mov     r14d, 1D8Ch
0x1800854e7  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x1800854ee  mov     r8d, r14d; int
0x1800854f1  lea     rcx, [rsp+48h+arg_0]; this
0x1800854f6  mov     rbx, r9
0x1800854f9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800854fe  test    rsi, rsi
0x180085501  jnz     loc_180085598
0x180085507  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008550e  test    rcx, rcx
0x180085511  jnz     short loc_180085554
0x180085513  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085519  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085520  mov     rcx, rax
0x180085523  test    rax, rax
0x180085526  jz      short loc_180085546
0x180085528  mov     rax, [rax]
0x18008552b  mov     edx, 7F0h
0x180085530  mov     rax, [rax+8]
0x180085534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085539  test    eax, eax
0x18008553b  jz      short loc_180085546
0x18008553d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085544  jmp     short loc_180085554
0x180085546  lea     rcx, qword_1800D6F70; this
0x18008554d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085554  cmp     byte ptr [rcx+8], 0
0x180085558  mov     ebx, 80070057h
0x18008555d  jz      short loc_180085581
0x18008555f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085564  cmp     [rax+7CCh], ebx
0x18008556a  jz      short loc_180085581
0x18008556c  mov     r9d, ebx; int
0x18008556f  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x180085576  mov     r8d, r14d; int
0x180085579  mov     rcx, rax; this
0x18008557c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085581  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085588  jb      loc_180085739
0x18008558e  mov     edx, 2ABh
0x180085593  jmp     loc_18008571B
0x180085598  test    rdi, rdi
0x18008559b  jns     loc_180085635
0x1800855a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800855a8  test    rcx, rcx
0x1800855ab  jnz     short loc_1800855EE
0x1800855ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800855b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800855ba  mov     rcx, rax
0x1800855bd  test    rax, rax
0x1800855c0  jz      short loc_1800855E0
0x1800855c2  mov     rax, [rax]
0x1800855c5  mov     edx, 7F0h
0x1800855ca  mov     rax, [rax+8]
0x1800855ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855d3  test    eax, eax
0x1800855d5  jz      short loc_1800855E0
0x1800855d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800855de  jmp     short loc_1800855EE
0x1800855e0  lea     rcx, qword_1800D6F70; this
0x1800855e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800855ee  cmp     byte ptr [rcx+8], 0
0x1800855f2  mov     ebx, 80070057h
0x1800855f7  jz      short loc_18008561E
0x1800855f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800855fe  cmp     [rax+7CCh], ebx
0x180085604  jz      short loc_18008561E
0x180085606  mov     r9d, ebx; int
0x180085609  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x180085610  mov     r8d, 1D90h; int
0x180085616  mov     rcx, rax; this
0x180085619  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008561e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085625  jb      loc_180085739
0x18008562b  mov     edx, 2ACh
0x180085630  jmp     loc_18008571B
0x180085635  mov     r14, [rsi+10h]
0x180085639  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085640  mov     ecx, 40h ; '@'; unsigned __int64
0x180085645  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008564a  test    rax, rax
0x18008564d  jz      short loc_180085689
0x18008564f  lea     rcx, [r14+rdi]
0x180085653  mov     [rbx], rax
0x180085656  mov     [rax+8], rcx
0x18008565a  mov     [rax+18h], rcx
0x18008565e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180085662  mov     [rax+20h], rcx
0x180085666  xor     ebx, ebx
0x180085668  mov     [rax+28h], rcx
0x18008566c  mov     [rax+3Ch], ecx
0x18008566f  mov     [rax], rsi
0x180085672  mov     [rax+10h], ebp
0x180085675  mov     qword ptr [rax+30h], 0
0x18008567d  mov     dword ptr [rax+38h], 0
0x180085684  jmp     loc_180085739
0x180085689  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085690  mov     qword ptr [rbx], 0
0x180085697  test    rcx, rcx
0x18008569a  jnz     short loc_1800856DD
0x18008569c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800856a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800856a9  mov     rcx, rax
0x1800856ac  test    rax, rax
0x1800856af  jz      short loc_1800856CF
0x1800856b1  mov     rax, [rax]
0x1800856b4  mov     edx, 7F0h
0x1800856b9  mov     rax, [rax+8]
0x1800856bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856c2  test    eax, eax
0x1800856c4  jz      short loc_1800856CF
0x1800856c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800856cd  jmp     short loc_1800856DD
0x1800856cf  lea     rcx, qword_1800D6F70; this
0x1800856d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800856dd  cmp     byte ptr [rcx+8], 0
0x1800856e1  mov     ebx, 8007000Eh
0x1800856e6  jz      short loc_18008570D
0x1800856e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800856ed  cmp     [rax+7CCh], ebx
0x1800856f3  jz      short loc_18008570D
0x1800856f5  mov     r9d, ebx; int
0x1800856f8  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x1800856ff  mov     r8d, 1D96h; int
0x180085705  mov     rcx, rax; this
0x180085708  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008570d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085714  jb      short loc_180085739
0x180085716  mov     edx, 2ADh
0x18008571b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085722  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180085729  xor     r9d, r9d
0x18008572c  mov     [rsp+48h+var_28], ebx
0x180085730  mov     rcx, [rcx+10h]
0x180085734  call    WPP_SF_qD
0x180085739  lea     rcx, [rsp+48h+arg_0]; this
0x18008573e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180085743  mov     rbp, [rsp+48h+arg_10]
0x180085748  mov     eax, ebx
0x18008574a  mov     rbx, [rsp+48h+arg_8]
0x18008574f  add     rsp, 30h
0x180085753  pop     r14
0x180085755  pop     rdi
0x180085756  pop     rsi
0x180085757  retn
```
