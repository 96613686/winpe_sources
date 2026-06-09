# mkvparser::Cluster::Create(mkvparser::Segment *,long,__int64,mkvparser::Cluster * &)

- ea: `0x18008905c`
- end: `0x180089307`
- name: `?Create@Cluster@mkvparser@@SAJPEAVSegment@2@J_JAEAPEAV12@@Z`
- size: `683`
- prototype: `__int64 __fastcall(struct mkvparser::Segment *, int, __int64, struct Cluster **)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18008ad30`
- `0x18008c320`
- `0x18008e228`
- `0x18008eef8`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18008905c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800890af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008914f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089244`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800890af`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008914f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089244`

## string_xrefs

- `0x180089083`: `mkvparser::Cluster::Create`
- `0x180089111`: `mkvparser::Cluster::Create`
- `0x1800891b1`: `mkvparser::Cluster::Create`
- `0x1800892a6`: `mkvparser::Cluster::Create`

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
            v24 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v28);
  return v13;
}

```

## disassembly

```asm
0x18008905c  mov     [rsp+arg_8], rbx
0x180089061  mov     [rsp+arg_10], rbp
0x180089066  push    rsi
0x180089067  push    rdi
0x180089068  push    r14
0x18008906a  sub     rsp, 30h
0x18008906e  mov     rdi, r8
0x180089071  mov     qword ptr [r9], 0
0x180089078  mov     ebp, edx
0x18008907a  mov     rsi, rcx
0x18008907d  mov     r14d, 1D8Ch
0x180089083  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x18008908a  mov     r8d, r14d; int
0x18008908d  lea     rcx, [rsp+48h+arg_0]; this
0x180089092  mov     rbx, r9
0x180089095  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008909a  test    rsi, rsi
0x18008909d  jnz     loc_18008913A
0x1800890a3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800890aa  test    rcx, rcx
0x1800890ad  jnz     short loc_1800890F6
0x1800890af  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800890b6  nop     dword ptr [rax+rax+00h]
0x1800890bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800890c2  mov     rcx, rax
0x1800890c5  test    rax, rax
0x1800890c8  jz      short loc_1800890E8
0x1800890ca  mov     rax, [rax]
0x1800890cd  mov     edx, 7F0h
0x1800890d2  mov     rax, [rax+8]
0x1800890d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800890db  test    eax, eax
0x1800890dd  jz      short loc_1800890E8
0x1800890df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800890e6  jmp     short loc_1800890F6
0x1800890e8  lea     rcx, qword_1800DBF70; this
0x1800890ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800890f6  cmp     byte ptr [rcx+8], 0
0x1800890fa  mov     ebx, 80070057h
0x1800890ff  jz      short loc_180089123
0x180089101  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089106  cmp     [rax+7CCh], ebx
0x18008910c  jz      short loc_180089123
0x18008910e  mov     r9d, ebx; int
0x180089111  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x180089118  mov     r8d, r14d; int
0x18008911b  mov     rcx, rax; this
0x18008911e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089123  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008912a  jb      loc_1800892E7
0x180089130  mov     edx, 2ABh
0x180089135  jmp     loc_1800892C9
0x18008913a  test    rdi, rdi
0x18008913d  jns     loc_1800891DD
0x180089143  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008914a  test    rcx, rcx
0x18008914d  jnz     short loc_180089196
0x18008914f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089156  nop     dword ptr [rax+rax+00h]
0x18008915b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089162  mov     rcx, rax
0x180089165  test    rax, rax
0x180089168  jz      short loc_180089188
0x18008916a  mov     rax, [rax]
0x18008916d  mov     edx, 7F0h
0x180089172  mov     rax, [rax+8]
0x180089176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008917b  test    eax, eax
0x18008917d  jz      short loc_180089188
0x18008917f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089186  jmp     short loc_180089196
0x180089188  lea     rcx, qword_1800DBF70; this
0x18008918f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089196  cmp     byte ptr [rcx+8], 0
0x18008919a  mov     ebx, 80070057h
0x18008919f  jz      short loc_1800891C6
0x1800891a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800891a6  cmp     [rax+7CCh], ebx
0x1800891ac  jz      short loc_1800891C6
0x1800891ae  mov     r9d, ebx; int
0x1800891b1  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x1800891b8  mov     r8d, 1D90h; int
0x1800891be  mov     rcx, rax; this
0x1800891c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800891c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800891cd  jb      loc_1800892E7
0x1800891d3  mov     edx, 2ACh
0x1800891d8  jmp     loc_1800892C9
0x1800891dd  mov     r14, [rsi+10h]
0x1800891e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800891e8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800891ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800891f2  test    rax, rax
0x1800891f5  jz      short loc_180089231
0x1800891f7  lea     rcx, [r14+rdi]
0x1800891fb  mov     [rbx], rax
0x1800891fe  mov     [rax+8], rcx
0x180089202  mov     [rax+18h], rcx
0x180089206  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008920a  mov     [rax+20h], rcx
0x18008920e  xor     ebx, ebx
0x180089210  mov     [rax+28h], rcx
0x180089214  mov     [rax+3Ch], ecx
0x180089217  mov     [rax], rsi
0x18008921a  mov     [rax+10h], ebp
0x18008921d  mov     qword ptr [rax+30h], 0
0x180089225  mov     dword ptr [rax+38h], 0
0x18008922c  jmp     loc_1800892E7
0x180089231  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089238  mov     qword ptr [rbx], 0
0x18008923f  test    rcx, rcx
0x180089242  jnz     short loc_18008928B
0x180089244  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008924b  nop     dword ptr [rax+rax+00h]
0x180089250  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089257  mov     rcx, rax
0x18008925a  test    rax, rax
0x18008925d  jz      short loc_18008927D
0x18008925f  mov     rax, [rax]
0x180089262  mov     edx, 7F0h
0x180089267  mov     rax, [rax+8]
0x18008926b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089270  test    eax, eax
0x180089272  jz      short loc_18008927D
0x180089274  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008927b  jmp     short loc_18008928B
0x18008927d  lea     rcx, qword_1800DBF70; this
0x180089284  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008928b  cmp     byte ptr [rcx+8], 0
0x18008928f  mov     ebx, 8007000Eh
0x180089294  jz      short loc_1800892BB
0x180089296  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008929b  cmp     [rax+7CCh], ebx
0x1800892a1  jz      short loc_1800892BB
0x1800892a3  mov     r9d, ebx; int
0x1800892a6  lea     rdx, aMkvparserClust_0; "mkvparser::Cluster::Create"
0x1800892ad  mov     r8d, 1D96h; int
0x1800892b3  mov     rcx, rax; this
0x1800892b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800892bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800892c2  jb      short loc_1800892E7
0x1800892c4  mov     edx, 2ADh
0x1800892c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800892d0  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800892d7  xor     r9d, r9d
0x1800892da  mov     [rsp+48h+var_28], ebx
0x1800892de  mov     rcx, [rcx+10h]
0x1800892e2  call    WPP_SF_qD
0x1800892e7  lea     rcx, [rsp+48h+arg_0]; this
0x1800892ec  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800892f1  mov     rbp, [rsp+48h+arg_10]
0x1800892f6  mov     eax, ebx
0x1800892f8  mov     rbx, [rsp+48h+arg_8]
0x1800892fd  add     rsp, 30h
0x180089301  pop     r14
0x180089303  pop     rdi
0x180089304  pop     rsi
0x180089305  retn
```
