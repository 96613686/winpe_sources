# mkvparser::Track::Create(mkvparser::Segment *,mkvparser::Track::Info const &,__int64,__int64,mkvparser::Track * &)

- ea: `0x180089310`
- end: `0x1800895c3`
- name: `?Create@Track@mkvparser@@SAJPEAVSegment@2@AEBVInfo@12@_J2AEAPEAV12@@Z`
- size: `691`
- prototype: `__int64 __fastcall(struct mkvparser::Segment *, const struct mkvparser::Track::Info *this, __int64, __int64, struct mkvparser::Track **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800ab330`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800873ac`
- `0x180088724`
- `0x180089310`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008944b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089507`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089362`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008944b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089507`

## string_xrefs

- `0x180089340`: `mkvparser::Track::Create`
- `0x18008941c`: `mkvparser::Track::Create`

## pseudocode

```c
__int64 __fastcall mkvparser::Track::Create(
        struct mkvparser::Segment *a1,
        const struct mkvparser::Track::Info *this,
        __int64 a3,
        __int64 a4,
        struct mkvparser::Track **a5)
{
  struct mkvparser::Track **v5; // r14
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  int v15; // ebx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  mkvparser::Track *v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // rdi
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax

  v5 = a5;
  if ( *a5 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&a5, "mkvparser::Track::Create", 5327);
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v15 = -2147024809;
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024809 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Track::Create", 5327, -2147024809);
    }
    if ( g_wppLevels )
    {
      v17 = 460;
LABEL_37:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v15);
    }
  }
  else
  {
    v18 = (mkvparser::Track *)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v18 )
      v19 = (void (__fastcall ***)(_QWORD, __int64))mkvparser::Track::Track(v18, a1, a3, a4);
    else
      v19 = 0;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&a5, "mkvparser::Track::Create", 5331);
    if ( v19 )
    {
      v15 = mkvparser::Track::Info::Copy(this, (struct mkvparser::Track::Info *)(v19 + 4));
      if ( v15 >= 0 )
      {
        *v5 = (struct mkvparser::Track *)v19;
        v15 = 0;
        goto LABEL_39;
      }
      (**v19)(v19, 1);
      v29 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
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
        if ( *((_DWORD *)v31 + 499) != v15 )
          CallStackContext::TraceFailure(v31, "mkvparser::Track::Create", 5337, v15);
      }
      if ( g_wppLevels )
      {
        v17 = 462;
        goto LABEL_37;
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
      v15 = -2147024882;
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v25, "mkvparser::Track::Create", 5331, -2147024882);
      }
      if ( g_wppLevels )
      {
        v17 = 461;
        goto LABEL_37;
      }
    }
  }
LABEL_39:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&a5);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180089310  mov     rax, rsp
0x180089313  push    rbx
0x180089314  push    rbp
0x180089315  push    rsi
0x180089316  push    rdi
0x180089317  push    r14
0x180089319  sub     rsp, 30h
0x18008931d  mov     r14, [rsp+58h+arg_20]
0x180089325  mov     rdi, r9
0x180089328  mov     rsi, r8
0x18008932b  mov     rbx, rdx
0x18008932e  mov     rbp, rcx
0x180089331  cmp     qword ptr [r14], 0
0x180089335  jz      loc_1800893E9
0x18008933b  mov     edi, 14CFh
0x180089340  lea     rsi, aMkvparserTrack_0; "mkvparser::Track::Create"
0x180089347  mov     r8d, edi; int
0x18008934a  lea     rcx, [rax+28h]; this
0x18008934e  mov     rdx, rsi; char *
0x180089351  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089356  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008935d  test    rcx, rcx
0x180089360  jnz     short loc_1800893A9
0x180089362  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089369  nop     dword ptr [rax+rax+00h]
0x18008936e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089375  mov     rcx, rax
0x180089378  test    rax, rax
0x18008937b  jz      short loc_18008939B
0x18008937d  mov     rax, [rax]
0x180089380  mov     edx, 7F0h
0x180089385  mov     rax, [rax+8]
0x180089389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008938e  test    eax, eax
0x180089390  jz      short loc_18008939B
0x180089392  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089399  jmp     short loc_1800893A9
0x18008939b  lea     rcx, qword_1800DBF70; this
0x1800893a2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800893a9  cmp     byte ptr [rcx+8], 0
0x1800893ad  mov     ebx, 80070057h
0x1800893b2  jz      short loc_1800893D2
0x1800893b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800893b9  cmp     [rax+7CCh], ebx
0x1800893bf  jz      short loc_1800893D2
0x1800893c1  mov     r9d, ebx; int
0x1800893c4  mov     r8d, edi; int
0x1800893c7  mov     rdx, rsi; char *
0x1800893ca  mov     rcx, rax; this
0x1800893cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800893d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800893d9  jb      loc_1800895A8
0x1800893df  mov     edx, 1CCh
0x1800893e4  jmp     loc_180089583
0x1800893e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800893f0  mov     ecx, 0B8h; unsigned __int64
0x1800893f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800893fa  test    rax, rax
0x1800893fd  jz      short loc_180089415
0x1800893ff  mov     r9, rdi; __int64
0x180089402  mov     r8, rsi; __int64
0x180089405  mov     rdx, rbp; struct mkvparser::Segment *
0x180089408  mov     rcx, rax; this
0x18008940b  call    ??0Track@mkvparser@@IEAA@PEAVSegment@1@_J1@Z; mkvparser::Track::Track(mkvparser::Segment *,__int64,__int64)
0x180089410  mov     rdi, rax
0x180089413  jmp     short loc_180089417
0x180089415  xor     edi, edi
0x180089417  mov     ebp, 14D3h
0x18008941c  lea     rsi, aMkvparserTrack_0; "mkvparser::Track::Create"
0x180089423  mov     r8d, ebp; int
0x180089426  lea     rcx, [rsp+58h+arg_20]; this
0x18008942e  mov     rdx, rsi; char *
0x180089431  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180089436  test    rdi, rdi
0x180089439  jnz     loc_1800894D2
0x18008943f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089446  test    rcx, rcx
0x180089449  jnz     short loc_180089492
0x18008944b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089452  nop     dword ptr [rax+rax+00h]
0x180089457  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008945e  mov     rcx, rax
0x180089461  test    rax, rax
0x180089464  jz      short loc_180089484
0x180089466  mov     rax, [rax]
0x180089469  mov     edx, 7F0h
0x18008946e  mov     rax, [rax+8]
0x180089472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089477  test    eax, eax
0x180089479  jz      short loc_180089484
0x18008947b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089482  jmp     short loc_180089492
0x180089484  lea     rcx, qword_1800DBF70; this
0x18008948b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089492  cmp     byte ptr [rcx+8], 0
0x180089496  mov     ebx, 8007000Eh
0x18008949b  jz      short loc_1800894BB
0x18008949d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800894a2  cmp     [rax+7CCh], ebx
0x1800894a8  jz      short loc_1800894BB
0x1800894aa  mov     r9d, ebx; int
0x1800894ad  mov     r8d, ebp; int
0x1800894b0  mov     rdx, rsi; char *
0x1800894b3  mov     rcx, rax; this
0x1800894b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800894bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800894c2  jb      loc_1800895A8
0x1800894c8  mov     edx, 1CDh
0x1800894cd  jmp     loc_180089583
0x1800894d2  lea     rdx, [rdi+20h]; struct mkvparser::Track::Info *
0x1800894d6  mov     rcx, rbx; this
0x1800894d9  call    ?Copy@Info@Track@mkvparser@@QEBAJAEAV123@@Z; mkvparser::Track::Info::Copy(mkvparser::Track::Info &)
0x1800894de  mov     ebx, eax
0x1800894e0  test    eax, eax
0x1800894e2  jns     loc_1800895A3
0x1800894e8  mov     rcx, [rdi]
0x1800894eb  mov     edx, 1
0x1800894f0  mov     rax, [rcx]
0x1800894f3  mov     rcx, rdi
0x1800894f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089502  test    rcx, rcx
0x180089505  jnz     short loc_18008954E
0x180089507  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008950e  nop     dword ptr [rax+rax+00h]
0x180089513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008951a  mov     rcx, rax
0x18008951d  test    rax, rax
0x180089520  jz      short loc_180089540
0x180089522  mov     rax, [rax]
0x180089525  mov     edx, 7F0h
0x18008952a  mov     rax, [rax+8]
0x18008952e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089533  test    eax, eax
0x180089535  jz      short loc_180089540
0x180089537  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008953e  jmp     short loc_18008954E
0x180089540  lea     rcx, qword_1800DBF70; this
0x180089547  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008954e  cmp     byte ptr [rcx+8], 0
0x180089552  jz      short loc_180089575
0x180089554  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089559  cmp     [rax+7CCh], ebx
0x18008955f  jz      short loc_180089575
0x180089561  mov     r9d, ebx; int
0x180089564  mov     r8d, 14D9h; int
0x18008956a  mov     rdx, rsi; char *
0x18008956d  mov     rcx, rax; this
0x180089570  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180089575  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008957c  jb      short loc_1800895A8
0x18008957e  mov     edx, 1CEh
0x180089583  mov     rcx, cs:WPP_GLOBAL_Control
0x18008958a  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180089591  xor     r9d, r9d
0x180089594  mov     [rsp+58h+var_38], ebx
0x180089598  mov     rcx, [rcx+10h]
0x18008959c  call    WPP_SF_qD
0x1800895a1  jmp     short loc_1800895A8
0x1800895a3  mov     [r14], rdi
0x1800895a6  xor     ebx, ebx
0x1800895a8  lea     rcx, [rsp+58h+arg_20]; this
0x1800895b0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800895b5  mov     eax, ebx
0x1800895b7  add     rsp, 30h
0x1800895bb  pop     r14
0x1800895bd  pop     rdi
0x1800895be  pop     rsi
0x1800895bf  pop     rbp
0x1800895c0  pop     rbx
0x1800895c1  retn
```
