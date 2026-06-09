# MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations(IMFAsyncResult *)

- ea: `0x18001a6d0`
- end: `0x18001aa9a`
- name: `?ProcessAsyncReadOperations@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z`
- size: `970`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180015260`
- `0x180016520`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x1800159e8`
- `0x18001a6d0`
- `0x18001b8b0`
- `0x180021b58`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a6ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a93d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a93d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001aa72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a7ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a884`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a7ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a884`

## string_xrefs

- `0x18001a719`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`
- `0x18001a824`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`
- `0x18001a8ee`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations(
        struct IMFAsyncCallback *this,
        struct IMFAsyncResult *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rsi
  int v10; // edi
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  unsigned int v13; // edi
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 *v17; // rdi
  int v18; // eax
  struct IMFAsyncCallback *v19; // rsi
  _BYTE v20[4]; // [rsp+30h] [rbp-48h] BYREF
  int v21; // [rsp+34h] [rbp-44h] BYREF
  struct IMFAsyncCallback *v22; // [rsp+38h] [rbp-40h]
  MkvMfSourceLib::MkvMfSource *v23; // [rsp+40h] [rbp-38h]
  int *v24; // [rsp+48h] [rbp-30h]
  char v25[16]; // [rsp+50h] [rbp-28h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)&this[13];
  v22 = this + 13;
  EnterCriticalSection((LPCRITICAL_SECTION)&this[13]);
  v21 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v20,
    "MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations",
    1297);
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && this[86].lpVtbl )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v10 = (*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *))this[86].lpVtbl->QueryInterface + 37))(this[86].lpVtbl);
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *, char *))this[86].lpVtbl->QueryInterface
                                                           + 35))(
                                                            this[86].lpVtbl,
                                                            v25);
    *((_DWORD *)ThreadRelativeContext + 504) = v10;
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
  }
  v23 = (MkvMfSourceLib::MkvMfSource *)this;
  v24 = &v21;
  if ( !a2 )
  {
    v21 = -2147024809;
    if ( !v8 )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
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
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( v21 < 0 && *((_DWORD *)v12 + 499) != v21 )
        CallStackContext::TraceFailure(v12, "MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations", 1301, v21);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
    v13 = v21;
LABEL_30:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
    LeaveCriticalSection(v4);
    return v13;
  }
  if ( !this[18].lpVtbl )
  {
    v21 = -1072873851;
    if ( !v8 )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( v21 < 0 && *((_DWORD *)v15 + 499) != v21 )
        CallStackContext::TraceFailure(v15, "MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations", 1305, v21);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v21);
    v13 = v21;
    goto LABEL_30;
  }
  v17 = (__int64 *)&this[50];
  while ( 1 )
  {
    v18 = MkvMfSourceLib::MkvMfSource::OnAsyncRead(this);
    if ( v18 )
      break;
    v17 = (__int64 *)&this[50];
    if ( (__int64)this[50].lpVtbl >= 0 )
    {
      v19 = this + 65;
      goto LABEL_37;
    }
  }
  v19 = this + 65;
  LODWORD(this[65].lpVtbl) = v18;
  if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 144, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v18);
    v17 = (__int64 *)&this[50];
  }
LABEL_37:
  if ( *v17 < 0 && LODWORD(v19->lpVtbl) != 3 )
  {
    BYTE6(this[60].lpVtbl) = 0;
    if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        145,
        &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
        this,
        BYTE5(this[60].lpVtbl));
    if ( !BYTE5(this[60].lpVtbl) )
    {
      BYTE5(this[60].lpVtbl) = 1;
      MkvMfSourceLib::MkvMfSource::QueueOperation((MkvMfSourceLib::MkvMfSource *)this, this + 63);
    }
  }
  if ( LODWORD(this[65].lpVtbl) == 3 )
  {
    if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 146, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this);
    LODWORD(v19->lpVtbl) = 1;
    BYTE6(this[60].lpVtbl) = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v20);
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x18001a6d0  push    rbp
0x18001a6d2  push    rbx
0x18001a6d3  push    rsi
0x18001a6d4  push    rdi
0x18001a6d5  push    r14
0x18001a6d7  push    r15
0x18001a6d9  mov     rbp, rsp
0x18001a6dc  sub     rsp, 78h
0x18001a6e0  mov     rax, cs:__security_cookie
0x18001a6e7  xor     rax, rsp
0x18001a6ea  mov     [rbp+var_18], rax
0x18001a6ee  mov     r15, rdx
0x18001a6f1  mov     r14, rcx
0x18001a6f4  lea     rbx, [rcx+68h]
0x18001a6f8  mov     [rbp+var_40], rbx
0x18001a6fc  mov     rcx, rbx; lpCriticalSection
0x18001a6ff  call    cs:__imp_EnterCriticalSection
0x18001a706  nop     dword ptr [rax+rax+00h]
0x18001a70b  nop
0x18001a70c  mov     [rbp+var_44], 0
0x18001a713  mov     r8d, 511h; int
0x18001a719  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x18001a720  lea     rcx, [rbp+var_48]; this
0x18001a724  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001a729  nop
0x18001a72a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a731  cmp     byte ptr [rcx+8], 0
0x18001a735  jz      short loc_18001A799
0x18001a737  cmp     qword ptr [r14+2B0h], 0
0x18001a73f  jz      short loc_18001A799
0x18001a741  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a746  mov     rsi, rax
0x18001a749  mov     rdx, [r14+2B0h]
0x18001a750  mov     rcx, [rdx]
0x18001a753  mov     rax, [rcx+128h]
0x18001a75a  mov     rcx, rdx
0x18001a75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a762  mov     edi, eax
0x18001a764  mov     r8, [r14+2B0h]
0x18001a76b  mov     rcx, [r8]
0x18001a76e  mov     rax, [rcx+118h]
0x18001a775  lea     rdx, [rbp+var_28]
0x18001a779  mov     rcx, r8
0x18001a77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a781  movups  xmm0, xmmword ptr [rax]
0x18001a784  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x18001a78c  mov     [rsi+7E0h], edi
0x18001a792  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a799  mov     [rbp+var_38], r14
0x18001a79d  lea     rax, [rbp+var_44]
0x18001a7a1  mov     [rbp+var_30], rax
0x18001a7a5  test    r15, r15
0x18001a7a8  jnz     loc_18001A86A
0x18001a7ae  mov     [rbp+var_44], 80070057h
0x18001a7b5  test    rcx, rcx
0x18001a7b8  jnz     short loc_18001A801
0x18001a7ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a7c1  nop     dword ptr [rax+rax+00h]
0x18001a7c6  mov     rcx, rax
0x18001a7c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7d0  test    rax, rax
0x18001a7d3  jz      short loc_18001A7F3
0x18001a7d5  mov     rax, [rax]
0x18001a7d8  mov     edx, 7F0h
0x18001a7dd  mov     rax, [rax+8]
0x18001a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7e6  test    eax, eax
0x18001a7e8  jz      short loc_18001A7F3
0x18001a7ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a7f1  jmp     short loc_18001A801
0x18001a7f3  lea     rcx, qword_1800DBF70; this
0x18001a7fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a801  cmp     byte ptr [rcx+8], 0
0x18001a805  jz      short loc_18001A833
0x18001a807  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a80c  mov     r9d, [rbp+var_44]; int
0x18001a810  test    r9d, r9d
0x18001a813  jns     short loc_18001A833
0x18001a815  cmp     [rax+7CCh], r9d
0x18001a81c  jz      short loc_18001A833
0x18001a81e  mov     r8d, 515h; int
0x18001a824  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x18001a82b  mov     rcx, rax; this
0x18001a82e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a833  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a83a  jb      short loc_18001A862
0x18001a83c  mov     edx, 8Eh
0x18001a841  mov     eax, [rbp+var_44]
0x18001a844  mov     [rsp+78h+var_58], eax
0x18001a848  mov     r9, r14
0x18001a84b  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001a852  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a859  mov     rcx, [rcx+10h]
0x18001a85d  call    WPP_SF_qD
0x18001a862  mov     edi, [rbp+var_44]
0x18001a865  jmp     loc_18001A930
0x18001a86a  cmp     qword ptr [r14+90h], 0
0x18001a872  jnz     loc_18001A950
0x18001a878  mov     [rbp+var_44], 0C00D3E85h
0x18001a87f  test    rcx, rcx
0x18001a882  jnz     short loc_18001A8CB
0x18001a884  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a88b  nop     dword ptr [rax+rax+00h]
0x18001a890  mov     rcx, rax
0x18001a893  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a89a  test    rax, rax
0x18001a89d  jz      short loc_18001A8BD
0x18001a89f  mov     rax, [rax]
0x18001a8a2  mov     edx, 7F0h
0x18001a8a7  mov     rax, [rax+8]
0x18001a8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b0  test    eax, eax
0x18001a8b2  jz      short loc_18001A8BD
0x18001a8b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a8bb  jmp     short loc_18001A8CB
0x18001a8bd  lea     rcx, qword_1800DBF70; this
0x18001a8c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a8cb  cmp     byte ptr [rcx+8], 0
0x18001a8cf  jz      short loc_18001A8FD
0x18001a8d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a8d6  mov     r9d, [rbp+var_44]; int
0x18001a8da  test    r9d, r9d
0x18001a8dd  jns     short loc_18001A8FD
0x18001a8df  cmp     [rax+7CCh], r9d
0x18001a8e6  jz      short loc_18001A8FD
0x18001a8e8  mov     r8d, 519h; int
0x18001a8ee  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x18001a8f5  mov     rcx, rax; this
0x18001a8f8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a8fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a904  jb      short loc_18001A92D
0x18001a906  mov     edx, 8Fh
0x18001a90b  mov     eax, [rbp+var_44]
0x18001a90e  mov     [rsp+78h+var_58], eax
0x18001a912  mov     r9, r14
0x18001a915  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001a91c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a923  mov     rcx, [rcx+10h]
0x18001a927  call    WPP_SF_qD
0x18001a92c  nop
0x18001a92d  mov     edi, [rbp+var_44]
0x18001a930  lea     rcx, [rbp+var_48]; this
0x18001a934  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001a939  nop
0x18001a93a  mov     rcx, rbx; lpCriticalSection
0x18001a93d  call    cs:__imp_LeaveCriticalSection
0x18001a944  nop     dword ptr [rax+rax+00h]
0x18001a949  mov     eax, edi
0x18001a94b  jmp     loc_18001AA80
0x18001a950  lea     r15, [r14+190h]
0x18001a957  mov     rdi, r15
0x18001a95a  mov     rcx, r14
0x18001a95d  call    ?OnAsyncRead@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::OnAsyncRead(void)
0x18001a962  test    eax, eax
0x18001a964  jnz     short loc_18001A97C
0x18001a966  lea     rdi, [r14+190h]
0x18001a96d  cmp     qword ptr [rdi], 0
0x18001a971  jl      short loc_18001A95A
0x18001a973  lea     rsi, [r14+208h]
0x18001a97a  jmp     short loc_18001A9B7
0x18001a97c  lea     rsi, [r14+208h]
0x18001a983  mov     [rsi], eax
0x18001a985  cmp     cs:byte_1800DC8D3, 4
0x18001a98c  jb      short loc_18001A9B7
0x18001a98e  mov     edx, 90h
0x18001a993  mov     [rsp+78h+var_58], eax
0x18001a997  mov     r9, r14
0x18001a99a  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001a9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a8  mov     rcx, [rcx+88h]
0x18001a9af  call    WPP_SF_qD
0x18001a9b4  mov     rdi, r15
0x18001a9b7  cmp     qword ptr [rdi], 0
0x18001a9bb  jge     short loc_18001AA22
0x18001a9bd  cmp     dword ptr [rsi], 3
0x18001a9c0  jz      short loc_18001AA22
0x18001a9c2  mov     byte ptr [r14+1E6h], 0
0x18001a9ca  cmp     cs:byte_1800DC8D3, 4
0x18001a9d1  jb      short loc_18001AA01
0x18001a9d3  movzx   eax, byte ptr [r14+1E5h]
0x18001a9db  mov     edx, 91h
0x18001a9e0  mov     [rsp+78h+var_58], eax
0x18001a9e4  mov     r9, r14
0x18001a9e7  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f5  mov     rcx, [rcx+88h]
0x18001a9fc  call    WPP_SF_qD
0x18001aa01  cmp     byte ptr [r14+1E5h], 0
0x18001aa09  jnz     short loc_18001AA22
0x18001aa0b  mov     byte ptr [r14+1E5h], 1
0x18001aa13  lea     rdx, [r14+1F8h]; struct IMFAsyncCallback *
0x18001aa1a  mov     rcx, r14; this
0x18001aa1d  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x18001aa22  cmp     dword ptr [r14+208h], 3
0x18001aa2a  jnz     short loc_18001AA65
0x18001aa2c  cmp     cs:byte_1800DC8D3, 4
0x18001aa33  jb      short loc_18001AA57
0x18001aa35  mov     edx, 92h
0x18001aa3a  mov     r9, r14
0x18001aa3d  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001aa44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa4b  mov     rcx, [rcx+88h]
0x18001aa52  call    WPP_SF_q
0x18001aa57  mov     dword ptr [rsi], 1
0x18001aa5d  mov     byte ptr [r14+1E6h], 0
0x18001aa65  lea     rcx, [rbp+var_48]; this
0x18001aa69  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001aa6e  nop
0x18001aa6f  mov     rcx, rbx; lpCriticalSection
0x18001aa72  call    cs:__imp_LeaveCriticalSection
0x18001aa79  nop     dword ptr [rax+rax+00h]
0x18001aa7e  xor     eax, eax
0x18001aa80  mov     rcx, [rbp+var_18]
0x18001aa84  xor     rcx, rsp; StackCookie
0x18001aa87  call    __security_check_cookie
0x18001aa8c  add     rsp, 78h
0x18001aa90  pop     r15
0x18001aa92  pop     r14
0x18001aa94  pop     rdi
0x18001aa95  pop     rsi
0x18001aa96  pop     rbx
0x18001aa97  pop     rbp
0x18001aa98  retn
```
