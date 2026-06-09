# mkvparser::Cluster::CreateBlock(__int64,__int64,__int64,__int64)

- ea: `0x180085a08`
- end: `0x180085ed3`
- name: `?CreateBlock@Cluster@mkvparser@@AEAAJ_J000@Z`
- size: `1227`
- prototype: `__int64 __fastcall(mkvparser::Cluster *this, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18009dd9c`
- `0x1800a5858`

## callees

- `0x180001fd0`
- `0x180003720`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180085a08`
- `0x180085edc`
- `0x180086ea0`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085a75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085b74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085c76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085d86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085e34`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085a75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085b74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085c76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085d86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085e34`

## string_xrefs

- `0x180085a53`: `mkvparser::Cluster::CreateBlock`
- `0x180085b1f`: `mkvparser::Cluster::CreateBlock`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall mkvparser::Cluster::CreateBlock(
        mkvparser::Cluster *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v6; // r15
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
  __int64 v51; // [rsp+70h] [rbp+40h]

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
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids,
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
            v31 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v21 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    BlockGroup = mkvparser::Cluster::CreateBlockGroup(this, v6, a4, a5);
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
          v41 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
    BlockGroup = mkvparser::Cluster::CreateSimpleBlock(this, v6, a4);
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
          v47 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180085a08  mov     [rsp-28h+arg_0], rsi
0x180085a0d  mov     [rsp-28h+arg_18], rdi
0x180085a12  mov     [rsp-28h+arg_10], r8
0x180085a17  push    rbp
0x180085a18  push    r12
0x180085a1a  push    r13
0x180085a1c  push    r14
0x180085a1e  push    r15
0x180085a20  mov     rbp, rsp
0x180085a23  sub     rsp, 30h
0x180085a27  mov     r13, r9
0x180085a2a  mov     r15, r8
0x180085a2d  mov     rsi, rdx
0x180085a30  mov     rdi, rcx
0x180085a33  cmp     rdx, 0A0h
0x180085a3a  jz      loc_180085B1B
0x180085a40  cmp     rdx, 0A3h
0x180085a47  jz      loc_180085B1B
0x180085a4d  mov     r15d, 1ED3h
0x180085a53  lea     r14, aMkvparserClust; "mkvparser::Cluster::CreateBlock"
0x180085a5a  mov     r8d, r15d; int
0x180085a5d  lea     rcx, [rbp+arg_8]; this
0x180085a61  mov     rdx, r14; char *
0x180085a64  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085a69  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085a70  test    rcx, rcx
0x180085a73  jnz     short loc_180085AB6
0x180085a75  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085a7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085a82  mov     rcx, rax
0x180085a85  test    rax, rax
0x180085a88  jz      short loc_180085AA8
0x180085a8a  mov     rax, [rax]
0x180085a8d  mov     edx, 7F0h
0x180085a92  mov     rax, [rax+8]
0x180085a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a9b  test    eax, eax
0x180085a9d  jz      short loc_180085AA8
0x180085a9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085aa6  jmp     short loc_180085AB6
0x180085aa8  lea     rcx, qword_1800D6F70; this
0x180085aaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085ab6  cmp     byte ptr [rcx+8], 0
0x180085aba  mov     esi, 0C00D36BEh
0x180085abf  jz      short loc_180085ADF
0x180085ac1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085ac6  cmp     [rax+7CCh], esi
0x180085acc  jz      short loc_180085ADF
0x180085ace  mov     r9d, esi; int
0x180085ad1  mov     r8d, r15d; int
0x180085ad4  mov     rdx, r14; char *
0x180085ad7  mov     rcx, rax; this
0x180085ada  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085adf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085ae6  jb      short loc_180085B0B
0x180085ae8  mov     edx, 2CAh
0x180085aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180085af4  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180085afb  mov     r9, rdi
0x180085afe  mov     [rsp+30h+var_10], esi
0x180085b02  mov     rcx, [rcx+10h]
0x180085b06  call    WPP_SF_qD
0x180085b0b  lea     rcx, [rbp+arg_8]; this
0x180085b0f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180085b14  mov     eax, esi
0x180085b16  jmp     loc_180085EBB
0x180085b1b  cmp     dword ptr [rcx+3Ch], 0
0x180085b1f  lea     r14, aMkvparserClust; "mkvparser::Cluster::CreateBlock"
0x180085b26  jge     loc_180085C0A
0x180085b2c  mov     dword ptr [rcx+38h], 400h
0x180085b33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085b3a  mov     ecx, 2000h; unsigned __int64
0x180085b3f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085b44  mov     r12d, 1EDCh
0x180085b4a  mov     [rdi+30h], rax
0x180085b4e  mov     r8d, r12d; int
0x180085b51  lea     rcx, [rbp+arg_8]; this
0x180085b55  mov     rdx, r14; char *
0x180085b58  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085b5d  cmp     qword ptr [rdi+30h], 0
0x180085b62  jnz     loc_180085BF5
0x180085b68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085b6f  test    rcx, rcx
0x180085b72  jnz     short loc_180085BB5
0x180085b74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085b7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085b81  mov     rcx, rax
0x180085b84  test    rax, rax
0x180085b87  jz      short loc_180085BA7
0x180085b89  mov     rax, [rax]
0x180085b8c  mov     edx, 7F0h
0x180085b91  mov     rax, [rax+8]
0x180085b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b9a  test    eax, eax
0x180085b9c  jz      short loc_180085BA7
0x180085b9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085ba5  jmp     short loc_180085BB5
0x180085ba7  lea     rcx, qword_1800D6F70; this
0x180085bae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085bb5  cmp     byte ptr [rcx+8], 0
0x180085bb9  mov     esi, 8007000Eh
0x180085bbe  jz      short loc_180085BDE
0x180085bc0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085bc5  cmp     [rax+7CCh], esi
0x180085bcb  jz      short loc_180085BDE
0x180085bcd  mov     r9d, esi; int
0x180085bd0  mov     r8d, r12d; int
0x180085bd3  mov     rdx, r14; char *
0x180085bd6  mov     rcx, rax; this
0x180085bd9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085bde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085be5  jb      loc_180085B0B
0x180085beb  mov     edx, 2CBh
0x180085bf0  jmp     loc_180085AED
0x180085bf5  lea     rcx, [rbp+arg_8]; this
0x180085bf9  mov     dword ptr [rdi+3Ch], 0
0x180085c00  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180085c05  jmp     loc_180085D3C
0x180085c0a  mov     eax, [rcx+38h]
0x180085c0d  cmp     [rcx+3Ch], eax
0x180085c10  jl      loc_180085D3C
0x180085c16  lea     r15d, [rax+rax]
0x180085c1a  cmp     eax, 3FFFFFFFh
0x180085c1f  jl      short loc_180085C27
0x180085c21  mov     r15d, 7FFFFFFFh
0x180085c27  movsxd  rcx, r15d
0x180085c2a  mov     eax, 8
0x180085c2f  mul     rcx
0x180085c32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180085c39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180085c40  cmovb   rax, rcx
0x180085c44  mov     rcx, rax; unsigned __int64
0x180085c47  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180085c4c  mov     r8d, 1EE8h; int
0x180085c52  lea     rcx, [rbp+arg_8]; this
0x180085c56  mov     rdx, r14; char *
0x180085c59  mov     r12, rax
0x180085c5c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085c61  test    r12, r12
0x180085c64  jnz     loc_180085CFA
0x180085c6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085c71  test    rcx, rcx
0x180085c74  jnz     short loc_180085CB7
0x180085c76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085c7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085c83  mov     rcx, rax
0x180085c86  test    rax, rax
0x180085c89  jz      short loc_180085CA9
0x180085c8b  mov     rax, [rax]
0x180085c8e  mov     edx, 7F0h
0x180085c93  mov     rax, [rax+8]
0x180085c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085c9c  test    eax, eax
0x180085c9e  jz      short loc_180085CA9
0x180085ca0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085ca7  jmp     short loc_180085CB7
0x180085ca9  lea     rcx, qword_1800D6F70; this
0x180085cb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085cb7  cmp     byte ptr [rcx+8], 0
0x180085cbb  mov     esi, 8007000Eh
0x180085cc0  jz      short loc_180085CE3
0x180085cc2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085cc7  cmp     [rax+7CCh], esi
0x180085ccd  jz      short loc_180085CE3
0x180085ccf  mov     r9d, esi; int
0x180085cd2  mov     r8d, 1EE8h; int
0x180085cd8  mov     rdx, r14; char *
0x180085cdb  mov     rcx, rax; this
0x180085cde  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085ce3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085cea  jb      loc_180085B0B
0x180085cf0  mov     edx, 2CCh
0x180085cf5  jmp     loc_180085AED
0x180085cfa  mov     rcx, [rdi+30h]
0x180085cfe  mov     rdx, r12
0x180085d01  movsxd  rax, dword ptr [rdi+3Ch]
0x180085d05  lea     r8, [rcx+rax*8]
0x180085d09  jmp     short loc_180085D19
0x180085d0b  mov     rax, [rcx]
0x180085d0e  add     rcx, 8
0x180085d12  mov     [rdx], rax
0x180085d15  lea     rdx, [rdx+8]
0x180085d19  cmp     rcx, r8
0x180085d1c  jnz     short loc_180085D0B
0x180085d1e  mov     rcx, [rdi+30h]; Block
0x180085d22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180085d27  lea     rcx, [rbp+arg_8]; this
0x180085d2b  mov     [rdi+30h], r12
0x180085d2f  mov     [rdi+38h], r15d
0x180085d33  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180085d38  mov     r15, [rbp+arg_10]
0x180085d3c  lea     rcx, [rbp+arg_8]; this
0x180085d40  mov     rdx, r14; char *
0x180085d43  cmp     rsi, 0A0h
0x180085d4a  jnz     loc_180085E02
0x180085d50  mov     r12d, 1EFBh
0x180085d56  mov     r8d, r12d; int
0x180085d59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085d5e  mov     r9, [rbp+arg_20]; __int64
0x180085d62  mov     r8, r13; __int64
0x180085d65  mov     rdx, r15; __int64
0x180085d68  mov     rcx, rdi; this
0x180085d6b  call    ?CreateBlockGroup@Cluster@mkvparser@@AEAAJ_J00@Z; mkvparser::Cluster::CreateBlockGroup(__int64,__int64,__int64)
0x180085d70  mov     esi, eax
0x180085d72  test    eax, eax
0x180085d74  jns     loc_180085EB0
0x180085d7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085d81  test    rcx, rcx
0x180085d84  jnz     short loc_180085DC7
0x180085d86  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085d8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085d93  mov     rcx, rax
0x180085d96  test    rax, rax
0x180085d99  jz      short loc_180085DB9
0x180085d9b  mov     rax, [rax]
0x180085d9e  mov     edx, 7F0h
0x180085da3  mov     rax, [rax+8]
0x180085da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085dac  test    eax, eax
0x180085dae  jz      short loc_180085DB9
0x180085db0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085db7  jmp     short loc_180085DC7
0x180085db9  lea     rcx, qword_1800D6F70; this
0x180085dc0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085dc7  cmp     byte ptr [rcx+8], 0
0x180085dcb  jz      short loc_180085DEB
0x180085dcd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085dd2  cmp     [rax+7CCh], esi
0x180085dd8  jz      short loc_180085DEB
0x180085dda  mov     r9d, esi; int
0x180085ddd  mov     r8d, r12d; int
0x180085de0  mov     rdx, r14; char *
0x180085de3  mov     rcx, rax; this
0x180085de6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085deb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085df2  jb      loc_180085B0B
0x180085df8  mov     edx, 2CDh
0x180085dfd  jmp     loc_180085AED
0x180085e02  mov     r12d, 1EFFh
0x180085e08  mov     r8d, r12d; int
0x180085e0b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085e10  mov     r8, r13; __int64
0x180085e13  mov     rdx, r15; __int64
0x180085e16  mov     rcx, rdi; this
0x180085e19  call    ?CreateSimpleBlock@Cluster@mkvparser@@AEAAJ_J0@Z; mkvparser::Cluster::CreateSimpleBlock(__int64,__int64)
0x180085e1e  mov     esi, eax
0x180085e20  test    eax, eax
0x180085e22  jns     loc_180085EB0
0x180085e28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085e2f  test    rcx, rcx
0x180085e32  jnz     short loc_180085E75
0x180085e34  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085e3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085e41  mov     rcx, rax
0x180085e44  test    rax, rax
0x180085e47  jz      short loc_180085E67
0x180085e49  mov     rax, [rax]
0x180085e4c  mov     edx, 7F0h
0x180085e51  mov     rax, [rax+8]
0x180085e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e5a  test    eax, eax
0x180085e5c  jz      short loc_180085E67
0x180085e5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085e65  jmp     short loc_180085E75
0x180085e67  lea     rcx, qword_1800D6F70; this
0x180085e6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180085e75  cmp     byte ptr [rcx+8], 0
0x180085e79  jz      short loc_180085E99
0x180085e7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085e80  cmp     [rax+7CCh], esi
0x180085e86  jz      short loc_180085E99
0x180085e88  mov     r9d, esi; int
0x180085e8b  mov     r8d, r12d; int
0x180085e8e  mov     rdx, r14; char *
0x180085e91  mov     rcx, rax; this
0x180085e94  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180085e99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085ea0  jb      loc_180085B0B
0x180085ea6  mov     edx, 2CEh
0x180085eab  jmp     loc_180085AED
0x180085eb0  lea     rcx, [rbp+arg_8]; this
0x180085eb4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180085eb9  xor     eax, eax
0x180085ebb  mov     rsi, [rsp+30h+arg_0]
0x180085ec0  mov     rdi, [rsp+30h+arg_18]
0x180085ec5  add     rsp, 30h
0x180085ec9  pop     r15
0x180085ecb  pop     r14
0x180085ecd  pop     r13
0x180085ecf  pop     r12
0x180085ed1  pop     rbp
0x180085ed2  retn
```
