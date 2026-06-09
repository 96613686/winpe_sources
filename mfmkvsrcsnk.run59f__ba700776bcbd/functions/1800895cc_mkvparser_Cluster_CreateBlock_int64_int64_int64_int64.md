# mkvparser::Cluster::CreateBlock(__int64,__int64,__int64,__int64)

- ea: `0x1800895cc`
- end: `0x180089ab6`
- name: `?CreateBlock@Cluster@mkvparser@@AEAAJ_J000@Z`
- size: `1258`
- prototype: `__int64 __usercall@<rax>(mkvparser::Cluster *__hidden this@<rcx>, __int64@<rdx>, __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800a24c8`
- `0x1800aa330`

## callees

- `0x180001ff0`
- `0x180003760`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800895cc`
- `0x180089abc`
- `0x18008aaf4`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089639`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008973e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089846`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008995c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089639`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008973e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089846`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008995c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089a10`

## string_xrefs

- `0x180089617`: `mkvparser::Cluster::CreateBlock`
- `0x1800896e9`: `mkvparser::Cluster::CreateBlock`

## pseudocode

```c
__int64 __fastcall mkvparser::Cluster::CreateBlock(
        mkvparser::Cluster *this,
        __int64 a2,
        struct mkvparser::IMkvReader *a3,
        __int64 a4,
        __int64 a5)
{
  struct mkvparser::IMkvReader *v6; // r15
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  int BlockGroup; // esi
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  int v24; // eax
  int v25; // r15d
  unsigned __int64 v26; // rax
  _QWORD *v27; // r12
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  _QWORD *v35; // rdx
  __int64 *v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 *v47; // rcx
  CallStackTracing *v48; // rax
  struct CallStackContext *v49; // rax
  char v50; // [rsp+68h] [rbp+38h] BYREF
  struct mkvparser::IMkvReader *v51; // [rsp+70h] [rbp+40h]

  v51 = a3;
  v6 = a3;
  if ( a2 != 160 && a2 != 163 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v50, "mkvparser::Cluster::CreateBlock", 7891);
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
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
    BlockGroup = -1072875842;
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875842 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Cluster::CreateBlock", 7891, -1072875842);
    }
    if ( !g_wppLevels )
      goto LABEL_14;
    v16 = 714;
LABEL_13:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
      this,
      BlockGroup);
LABEL_14:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
    return (unsigned int)BlockGroup;
  }
  if ( *((int *)this + 15) >= 0 )
  {
    v24 = *((_DWORD *)this + 14);
    if ( *((_DWORD *)this + 15) >= v24 )
    {
      v25 = 2 * v24;
      if ( v24 >= 0x3FFFFFFF )
        v25 = 0x7FFFFFFF;
      v26 = 8LL * v25;
      if ( !is_mul_ok(v25, 8u) )
        v26 = -1;
      v27 = operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
      CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v50, "mkvparser::Cluster::CreateBlock", 7912);
      if ( !v27 )
      {
        v31 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
          CallStackTracing::s_wpInstance = v32;
          if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          {
            v31 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v31 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        BlockGroup = -2147024882;
        if ( *((_BYTE *)v31 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
          if ( *((_DWORD *)v33 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v33, "mkvparser::Cluster::CreateBlock", 7912, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_14;
        v16 = 716;
        goto LABEL_13;
      }
      v34 = (__int64 *)*((_QWORD *)this + 6);
      v35 = v27;
      v36 = &v34[*((int *)this + 15)];
      while ( v34 != v36 )
      {
        v37 = *v34++;
        *v35++ = v37;
      }
      operator delete(*((void **)this + 6));
      *((_QWORD *)this + 6) = v27;
      *((_DWORD *)this + 14) = v25;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
      v6 = v51;
    }
  }
  else
  {
    *((_DWORD *)this + 14) = 1024;
    *((_QWORD *)this + 6) = operator new[](0x2000u, (const struct std::nothrow_t *)&std::nothrow);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v50, "mkvparser::Cluster::CreateBlock", 7900);
    if ( !*((_QWORD *)this + 6) )
    {
      v21 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      BlockGroup = -2147024882;
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)v23 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v23, "mkvparser::Cluster::CreateBlock", 7900, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v16 = 715;
      goto LABEL_13;
    }
    *((_DWORD *)this + 15) = 0;
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
  }
  if ( a2 == 160 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v50, "mkvparser::Cluster::CreateBlock", 7931);
    BlockGroup = mkvparser::Cluster::CreateBlockGroup((mkvparser ***)this, v6, a4, a5);
    if ( BlockGroup < 0 )
    {
      v41 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
        CallStackTracing::s_wpInstance = v42;
        if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v41 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
        if ( *((_DWORD *)v43 + 499) != BlockGroup )
          CallStackContext::TraceFailure(v43, "mkvparser::Cluster::CreateBlock", 7931, BlockGroup);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v16 = 717;
      goto LABEL_13;
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v50, "mkvparser::Cluster::CreateBlock", 7935);
    BlockGroup = mkvparser::Cluster::CreateSimpleBlock(this, (__int64)v6, a4);
    if ( BlockGroup < 0 )
    {
      v47 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45, v46);
        CallStackTracing::s_wpInstance = v48;
        if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
        {
          v47 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v47 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v47);
        if ( *((_DWORD *)v49 + 499) != BlockGroup )
          CallStackContext::TraceFailure(v49, "mkvparser::Cluster::CreateBlock", 7935, BlockGroup);
      }
      if ( !g_wppLevels )
        goto LABEL_14;
      v16 = 718;
      goto LABEL_13;
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v50);
  return 0;
}

```

## disassembly

```asm
0x1800895cc  mov     [rsp-28h+arg_0], rsi
0x1800895d1  mov     [rsp-28h+arg_18], rdi
0x1800895d6  mov     [rsp-28h+arg_10], r8
0x1800895db  push    rbp
0x1800895dc  push    r12
0x1800895de  push    r13
0x1800895e0  push    r14
0x1800895e2  push    r15
0x1800895e4  mov     rbp, rsp
0x1800895e7  sub     rsp, 30h
0x1800895eb  mov     r13, r9
0x1800895ee  mov     r15, r8
0x1800895f1  mov     rsi, rdx
0x1800895f4  mov     rdi, rcx
0x1800895f7  cmp     rdx, 0A0h
0x1800895fe  jz      loc_1800896E5
0x180089604  cmp     rdx, 0A3h
0x18008960b  jz      loc_1800896E5
0x180089611  mov     r15d, 1ED3h
0x180089617  lea     r14, aMkvparserClust; "mkvparser::Cluster::CreateBlock"
0x18008961e  mov     r8d, r15d; int
0x180089621  lea     rcx, [rbp+arg_8]; this
0x180089625  mov     rdx, r14; char *
0x180089628  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008962d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089634  test    rcx, rcx
0x180089637  jnz     short loc_180089680
0x180089639  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089640  nop     dword ptr [rax+rax+00h]
0x180089645  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008964c  mov     rcx, rax
0x18008964f  test    rax, rax
0x180089652  jz      short loc_180089672
0x180089654  mov     rax, [rax]
0x180089657  mov     edx, 7F0h
0x18008965c  mov     rax, [rax+8]
0x180089660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089665  test    eax, eax
0x180089667  jz      short loc_180089672
0x180089669  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089670  jmp     short loc_180089680
0x180089672  lea     rcx, qword_1800DBF70; this
0x180089679  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089680  cmp     byte ptr [rcx+8], 0
0x180089684  mov     esi, 0C00D36BEh
0x180089689  jz      short loc_1800896A9
0x18008968b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089690  cmp     [rax+7CCh], esi
0x180089696  jz      short loc_1800896A9
0x180089698  mov     r9d, esi; int
0x18008969b  mov     r8d, r15d; int
0x18008969e  mov     rdx, r14; char *
0x1800896a1  mov     rcx, rax; this
0x1800896a4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800896a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800896b0  jb      short loc_1800896D5
0x1800896b2  mov     edx, 2CAh
0x1800896b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800896be  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800896c5  mov     r9, rdi
0x1800896c8  mov     [rsp+30h+var_10], esi
0x1800896cc  mov     rcx, [rcx+10h]
0x1800896d0  call    WPP_SF_qD
0x1800896d5  lea     rcx, [rbp+arg_8]; this
0x1800896d9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800896de  mov     eax, esi
0x1800896e0  jmp     loc_180089A9D
0x1800896e5  cmp     dword ptr [rcx+3Ch], 0
0x1800896e9  lea     r14, aMkvparserClust; "mkvparser::Cluster::CreateBlock"
0x1800896f0  jge     loc_1800897DA
0x1800896f6  mov     dword ptr [rcx+38h], 400h
0x1800896fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180089704  mov     ecx, 2000h; unsigned __int64
0x180089709  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008970e  mov     r12d, 1EDCh
0x180089714  mov     [rdi+30h], rax
0x180089718  mov     r8d, r12d; int
0x18008971b  lea     rcx, [rbp+arg_8]; this
0x18008971f  mov     rdx, r14; char *
0x180089722  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089727  cmp     qword ptr [rdi+30h], 0
0x18008972c  jnz     loc_1800897C5
0x180089732  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089739  test    rcx, rcx
0x18008973c  jnz     short loc_180089785
0x18008973e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089745  nop     dword ptr [rax+rax+00h]
0x18008974a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089751  mov     rcx, rax
0x180089754  test    rax, rax
0x180089757  jz      short loc_180089777
0x180089759  mov     rax, [rax]
0x18008975c  mov     edx, 7F0h
0x180089761  mov     rax, [rax+8]
0x180089765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008976a  test    eax, eax
0x18008976c  jz      short loc_180089777
0x18008976e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089775  jmp     short loc_180089785
0x180089777  lea     rcx, qword_1800DBF70; this
0x18008977e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089785  cmp     byte ptr [rcx+8], 0
0x180089789  mov     esi, 8007000Eh
0x18008978e  jz      short loc_1800897AE
0x180089790  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089795  cmp     [rax+7CCh], esi
0x18008979b  jz      short loc_1800897AE
0x18008979d  mov     r9d, esi; int
0x1800897a0  mov     r8d, r12d; int
0x1800897a3  mov     rdx, r14; char *
0x1800897a6  mov     rcx, rax; this
0x1800897a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800897ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800897b5  jb      loc_1800896D5
0x1800897bb  mov     edx, 2CBh
0x1800897c0  jmp     loc_1800896B7
0x1800897c5  lea     rcx, [rbp+arg_8]; this
0x1800897c9  mov     dword ptr [rdi+3Ch], 0
0x1800897d0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800897d5  jmp     loc_180089912
0x1800897da  mov     eax, [rcx+38h]
0x1800897dd  cmp     [rcx+3Ch], eax
0x1800897e0  jl      loc_180089912
0x1800897e6  lea     r15d, [rax+rax]
0x1800897ea  cmp     eax, 3FFFFFFFh
0x1800897ef  jl      short loc_1800897F7
0x1800897f1  mov     r15d, 7FFFFFFFh
0x1800897f7  movsxd  rcx, r15d
0x1800897fa  mov     eax, 8
0x1800897ff  mul     rcx
0x180089802  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180089809  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180089810  cmovb   rax, rcx
0x180089814  mov     rcx, rax; unsigned __int64
0x180089817  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008981c  mov     r8d, 1EE8h; int
0x180089822  lea     rcx, [rbp+arg_8]; this
0x180089826  mov     rdx, r14; char *
0x180089829  mov     r12, rax
0x18008982c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089831  test    r12, r12
0x180089834  jnz     loc_1800898D0
0x18008983a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089841  test    rcx, rcx
0x180089844  jnz     short loc_18008988D
0x180089846  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008984d  nop     dword ptr [rax+rax+00h]
0x180089852  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089859  mov     rcx, rax
0x18008985c  test    rax, rax
0x18008985f  jz      short loc_18008987F
0x180089861  mov     rax, [rax]
0x180089864  mov     edx, 7F0h
0x180089869  mov     rax, [rax+8]
0x18008986d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089872  test    eax, eax
0x180089874  jz      short loc_18008987F
0x180089876  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008987d  jmp     short loc_18008988D
0x18008987f  lea     rcx, qword_1800DBF70; this
0x180089886  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008988d  cmp     byte ptr [rcx+8], 0
0x180089891  mov     esi, 8007000Eh
0x180089896  jz      short loc_1800898B9
0x180089898  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008989d  cmp     [rax+7CCh], esi
0x1800898a3  jz      short loc_1800898B9
0x1800898a5  mov     r9d, esi; int
0x1800898a8  mov     r8d, 1EE8h; int
0x1800898ae  mov     rdx, r14; char *
0x1800898b1  mov     rcx, rax; this
0x1800898b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800898b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800898c0  jb      loc_1800896D5
0x1800898c6  mov     edx, 2CCh
0x1800898cb  jmp     loc_1800896B7
0x1800898d0  mov     rcx, [rdi+30h]
0x1800898d4  mov     rdx, r12
0x1800898d7  movsxd  rax, dword ptr [rdi+3Ch]
0x1800898db  lea     r8, [rcx+rax*8]
0x1800898df  jmp     short loc_1800898EF
0x1800898e1  mov     rax, [rcx]
0x1800898e4  add     rcx, 8
0x1800898e8  mov     [rdx], rax
0x1800898eb  lea     rdx, [rdx+8]
0x1800898ef  cmp     rcx, r8
0x1800898f2  jnz     short loc_1800898E1
0x1800898f4  mov     rcx, [rdi+30h]; Block
0x1800898f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800898fd  lea     rcx, [rbp+arg_8]; this
0x180089901  mov     [rdi+30h], r12
0x180089905  mov     [rdi+38h], r15d
0x180089909  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008990e  mov     r15, [rbp+arg_10]
0x180089912  lea     rcx, [rbp+arg_8]; this
0x180089916  mov     rdx, r14; char *
0x180089919  cmp     rsi, 0A0h
0x180089920  jnz     loc_1800899DE
0x180089926  mov     r12d, 1EFBh
0x18008992c  mov     r8d, r12d; int
0x18008992f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089934  mov     r9, [rbp+arg_20]; __int64
0x180089938  mov     r8, r13; __int64
0x18008993b  mov     rdx, r15; __int64
0x18008993e  mov     rcx, rdi; this
0x180089941  call    ?CreateBlockGroup@Cluster@mkvparser@@AEAAJ_J00@Z; mkvparser::Cluster::CreateBlockGroup(__int64,__int64,__int64)
0x180089946  mov     esi, eax
0x180089948  test    eax, eax
0x18008994a  jns     loc_180089A92
0x180089950  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089957  test    rcx, rcx
0x18008995a  jnz     short loc_1800899A3
0x18008995c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089963  nop     dword ptr [rax+rax+00h]
0x180089968  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008996f  mov     rcx, rax
0x180089972  test    rax, rax
0x180089975  jz      short loc_180089995
0x180089977  mov     rax, [rax]
0x18008997a  mov     edx, 7F0h
0x18008997f  mov     rax, [rax+8]
0x180089983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089988  test    eax, eax
0x18008998a  jz      short loc_180089995
0x18008998c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089993  jmp     short loc_1800899A3
0x180089995  lea     rcx, qword_1800DBF70; this
0x18008999c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800899a3  cmp     byte ptr [rcx+8], 0
0x1800899a7  jz      short loc_1800899C7
0x1800899a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800899ae  cmp     [rax+7CCh], esi
0x1800899b4  jz      short loc_1800899C7
0x1800899b6  mov     r9d, esi; int
0x1800899b9  mov     r8d, r12d; int
0x1800899bc  mov     rdx, r14; char *
0x1800899bf  mov     rcx, rax; this
0x1800899c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800899c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800899ce  jb      loc_1800896D5
0x1800899d4  mov     edx, 2CDh
0x1800899d9  jmp     loc_1800896B7
0x1800899de  mov     r12d, 1EFFh
0x1800899e4  mov     r8d, r12d; int
0x1800899e7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800899ec  mov     r8, r13; __int64
0x1800899ef  mov     rdx, r15; __int64
0x1800899f2  mov     rcx, rdi; this
0x1800899f5  call    ?CreateSimpleBlock@Cluster@mkvparser@@AEAAJ_J0@Z; mkvparser::Cluster::CreateSimpleBlock(__int64,__int64)
0x1800899fa  mov     esi, eax
0x1800899fc  test    eax, eax
0x1800899fe  jns     loc_180089A92
0x180089a04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a0b  test    rcx, rcx
0x180089a0e  jnz     short loc_180089A57
0x180089a10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089a17  nop     dword ptr [rax+rax+00h]
0x180089a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a23  mov     rcx, rax
0x180089a26  test    rax, rax
0x180089a29  jz      short loc_180089A49
0x180089a2b  mov     rax, [rax]
0x180089a2e  mov     edx, 7F0h
0x180089a33  mov     rax, [rax+8]
0x180089a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089a3c  test    eax, eax
0x180089a3e  jz      short loc_180089A49
0x180089a40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a47  jmp     short loc_180089A57
0x180089a49  lea     rcx, qword_1800DBF70; this
0x180089a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089a57  cmp     byte ptr [rcx+8], 0
0x180089a5b  jz      short loc_180089A7B
0x180089a5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089a62  cmp     [rax+7CCh], esi
0x180089a68  jz      short loc_180089A7B
0x180089a6a  mov     r9d, esi; int
0x180089a6d  mov     r8d, r12d; int
0x180089a70  mov     rdx, r14; char *
0x180089a73  mov     rcx, rax; this
0x180089a76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089a7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180089a82  jb      loc_1800896D5
0x180089a88  mov     edx, 2CEh
0x180089a8d  jmp     loc_1800896B7
0x180089a92  lea     rcx, [rbp+arg_8]; this
0x180089a96  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180089a9b  xor     eax, eax
0x180089a9d  mov     rsi, [rsp+30h+arg_0]
0x180089aa2  mov     rdi, [rsp+30h+arg_18]
0x180089aa7  add     rsp, 30h
0x180089aab  pop     r15
0x180089aad  pop     r14
0x180089aaf  pop     r13
0x180089ab1  pop     r12
0x180089ab3  pop     rbp
0x180089ab4  retn
```
