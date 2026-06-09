# mkvparser::Track::Create(mkvparser::Segment *,mkvparser::Track::Info const &,__int64,__int64,mkvparser::Track * &)

- ea: `0x180085760`
- end: `0x180085a00`
- name: `?Create@Track@mkvparser@@SAJPEAVSegment@2@AEBVInfo@12@_J2AEAPEAV12@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct mkvparser::Segment *, const struct mkvparser::Track::Info *this, __int64, __int64, struct mkvparser::Track **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800a67dc`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800838ac`
- `0x180084bd0`
- `0x180085760`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800857b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085895`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008594b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800857b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180085895`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008594b`

## string_xrefs

- `0x180085790`: `mkvparser::Track::Create`
- `0x180085866`: `mkvparser::Track::Create`

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
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v15);
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
          v29 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v23 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180085760  mov     rax, rsp
0x180085763  push    rbx
0x180085764  push    rbp
0x180085765  push    rsi
0x180085766  push    rdi
0x180085767  push    r14
0x180085769  sub     rsp, 30h
0x18008576d  mov     r14, [rsp+58h+arg_20]
0x180085775  mov     rdi, r9
0x180085778  mov     rsi, r8
0x18008577b  mov     rbx, rdx
0x18008577e  mov     rbp, rcx
0x180085781  cmp     qword ptr [r14], 0
0x180085785  jz      loc_180085833
0x18008578b  mov     edi, 14CFh
0x180085790  lea     rsi, aMkvparserTrack_0; "mkvparser::Track::Create"
0x180085797  mov     r8d, edi; int
0x18008579a  lea     rcx, [rax+28h]; this
0x18008579e  mov     rdx, rsi; char *
0x1800857a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800857a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857ad  test    rcx, rcx
0x1800857b0  jnz     short loc_1800857F3
0x1800857b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800857b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857bf  mov     rcx, rax
0x1800857c2  test    rax, rax
0x1800857c5  jz      short loc_1800857E5
0x1800857c7  mov     rax, [rax]
0x1800857ca  mov     edx, 7F0h
0x1800857cf  mov     rax, [rax+8]
0x1800857d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800857d8  test    eax, eax
0x1800857da  jz      short loc_1800857E5
0x1800857dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857e3  jmp     short loc_1800857F3
0x1800857e5  lea     rcx, qword_1800D6F70; this
0x1800857ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800857f3  cmp     byte ptr [rcx+8], 0
0x1800857f7  mov     ebx, 80070057h
0x1800857fc  jz      short loc_18008581C
0x1800857fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085803  cmp     [rax+7CCh], ebx
0x180085809  jz      short loc_18008581C
0x18008580b  mov     r9d, ebx; int
0x18008580e  mov     r8d, edi; int
0x180085811  mov     rdx, rsi; char *
0x180085814  mov     rcx, rax; this
0x180085817  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008581c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085823  jb      loc_1800859E6
0x180085829  mov     edx, 1CCh
0x18008582e  jmp     loc_1800859C1
0x180085833  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008583a  mov     ecx, 0B8h; unsigned __int64
0x18008583f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180085844  test    rax, rax
0x180085847  jz      short loc_18008585F
0x180085849  mov     r9, rdi; __int64
0x18008584c  mov     r8, rsi; __int64
0x18008584f  mov     rdx, rbp; struct mkvparser::Segment *
0x180085852  mov     rcx, rax; this
0x180085855  call    ??0Track@mkvparser@@IEAA@PEAVSegment@1@_J1@Z; mkvparser::Track::Track(mkvparser::Segment *,__int64,__int64)
0x18008585a  mov     rdi, rax
0x18008585d  jmp     short loc_180085861
0x18008585f  xor     edi, edi
0x180085861  mov     ebp, 14D3h
0x180085866  lea     rsi, aMkvparserTrack_0; "mkvparser::Track::Create"
0x18008586d  mov     r8d, ebp; int
0x180085870  lea     rcx, [rsp+58h+arg_20]; this
0x180085878  mov     rdx, rsi; char *
0x18008587b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180085880  test    rdi, rdi
0x180085883  jnz     loc_180085916
0x180085889  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085890  test    rcx, rcx
0x180085893  jnz     short loc_1800858D6
0x180085895  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008589b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800858a2  mov     rcx, rax
0x1800858a5  test    rax, rax
0x1800858a8  jz      short loc_1800858C8
0x1800858aa  mov     rax, [rax]
0x1800858ad  mov     edx, 7F0h
0x1800858b2  mov     rax, [rax+8]
0x1800858b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858bb  test    eax, eax
0x1800858bd  jz      short loc_1800858C8
0x1800858bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800858c6  jmp     short loc_1800858D6
0x1800858c8  lea     rcx, qword_1800D6F70; this
0x1800858cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800858d6  cmp     byte ptr [rcx+8], 0
0x1800858da  mov     ebx, 8007000Eh
0x1800858df  jz      short loc_1800858FF
0x1800858e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800858e6  cmp     [rax+7CCh], ebx
0x1800858ec  jz      short loc_1800858FF
0x1800858ee  mov     r9d, ebx; int
0x1800858f1  mov     r8d, ebp; int
0x1800858f4  mov     rdx, rsi; char *
0x1800858f7  mov     rcx, rax; this
0x1800858fa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800858ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180085906  jb      loc_1800859E6
0x18008590c  mov     edx, 1CDh
0x180085911  jmp     loc_1800859C1
0x180085916  lea     rdx, [rdi+20h]; struct mkvparser::Track::Info *
0x18008591a  mov     rcx, rbx; this
0x18008591d  call    ?Copy@Info@Track@mkvparser@@QEBAJAEAV123@@Z; mkvparser::Track::Info::Copy(mkvparser::Track::Info &)
0x180085922  mov     ebx, eax
0x180085924  test    eax, eax
0x180085926  jns     loc_1800859E1
0x18008592c  mov     rcx, [rdi]
0x18008592f  mov     edx, 1
0x180085934  mov     rax, [rcx]
0x180085937  mov     rcx, rdi
0x18008593a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008593f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180085946  test    rcx, rcx
0x180085949  jnz     short loc_18008598C
0x18008594b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180085951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180085958  mov     rcx, rax
0x18008595b  test    rax, rax
0x18008595e  jz      short loc_18008597E
0x180085960  mov     rax, [rax]
0x180085963  mov     edx, 7F0h
0x180085968  mov     rax, [rax+8]
0x18008596c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085971  test    eax, eax
0x180085973  jz      short loc_18008597E
0x180085975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008597c  jmp     short loc_18008598C
0x18008597e  lea     rcx, qword_1800D6F70; this
0x180085985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008598c  cmp     byte ptr [rcx+8], 0
0x180085990  jz      short loc_1800859B3
0x180085992  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180085997  cmp     [rax+7CCh], ebx
0x18008599d  jz      short loc_1800859B3
0x18008599f  mov     r9d, ebx; int
0x1800859a2  mov     r8d, 14D9h; int
0x1800859a8  mov     rdx, rsi; char *
0x1800859ab  mov     rcx, rax; this
0x1800859ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800859b3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800859ba  jb      short loc_1800859E6
0x1800859bc  mov     edx, 1CEh
0x1800859c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800859c8  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800859cf  xor     r9d, r9d
0x1800859d2  mov     [rsp+58h+var_38], ebx
0x1800859d6  mov     rcx, [rcx+10h]
0x1800859da  call    WPP_SF_qD
0x1800859df  jmp     short loc_1800859E6
0x1800859e1  mov     [r14], rdi
0x1800859e4  xor     ebx, ebx
0x1800859e6  lea     rcx, [rsp+58h+arg_20]; this
0x1800859ee  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800859f3  mov     eax, ebx
0x1800859f5  add     rsp, 30h
0x1800859f9  pop     r14
0x1800859fb  pop     rdi
0x1800859fc  pop     rsi
0x1800859fd  pop     rbp
0x1800859fe  pop     rbx
0x1800859ff  retn
```
