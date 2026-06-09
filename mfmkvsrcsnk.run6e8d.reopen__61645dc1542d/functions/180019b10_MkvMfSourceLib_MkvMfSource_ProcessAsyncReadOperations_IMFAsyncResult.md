# MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations(IMFAsyncResult *)

- ea: `0x180019b10`
- end: `0x180019ebb`
- name: `?ProcessAsyncReadOperations@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncResult@@@Z`
- size: `939`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800148a0`
- `0x180015ad0`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180014ff0`
- `0x180019b10`
- `0x18001ac70`
- `0x180020d44`
- `0x180020d84`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019b3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019d6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e9a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019bf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019cb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019bf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019cb8`

## string_xrefs

- `0x180019b53`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`
- `0x180019c58`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`
- `0x180019d1c`: `MkvMfSourceLib::MkvMfSource::ProcessAsyncReadOperations`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  if ( (unsigned __int8)byte_1800D78D3 >= 4u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 144, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v18);
    v17 = (__int64 *)&this[50];
  }
LABEL_37:
  if ( *v17 < 0 && LODWORD(v19->lpVtbl) != 3 )
  {
    BYTE6(this[60].lpVtbl) = 0;
    if ( (unsigned __int8)byte_1800D78D3 >= 4u )
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
    if ( (unsigned __int8)byte_1800D78D3 >= 4u )
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
0x180019b10  push    rbp
0x180019b12  push    rbx
0x180019b13  push    rsi
0x180019b14  push    rdi
0x180019b15  push    r14
0x180019b17  push    r15
0x180019b19  mov     rbp, rsp
0x180019b1c  sub     rsp, 78h
0x180019b20  mov     rax, cs:__security_cookie
0x180019b27  xor     rax, rsp
0x180019b2a  mov     [rbp+var_18], rax
0x180019b2e  mov     r15, rdx
0x180019b31  mov     r14, rcx
0x180019b34  lea     rbx, [rcx+68h]
0x180019b38  mov     [rbp+var_40], rbx
0x180019b3c  mov     rcx, rbx; lpCriticalSection
0x180019b3f  call    cs:__imp_EnterCriticalSection
0x180019b45  nop
0x180019b46  mov     [rbp+var_44], 0
0x180019b4d  mov     r8d, 511h; int
0x180019b53  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x180019b5a  lea     rcx, [rbp+var_48]; this
0x180019b5e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019b63  nop
0x180019b64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180019b6b  cmp     byte ptr [rcx+8], 0
0x180019b6f  jz      short loc_180019BD3
0x180019b71  cmp     qword ptr [r14+2B0h], 0
0x180019b79  jz      short loc_180019BD3
0x180019b7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019b80  mov     rsi, rax
0x180019b83  mov     rdx, [r14+2B0h]
0x180019b8a  mov     rcx, [rdx]
0x180019b8d  mov     rax, [rcx+128h]
0x180019b94  mov     rcx, rdx
0x180019b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b9c  mov     edi, eax
0x180019b9e  mov     r8, [r14+2B0h]
0x180019ba5  mov     rcx, [r8]
0x180019ba8  mov     rax, [rcx+118h]
0x180019baf  lea     rdx, [rbp+var_28]
0x180019bb3  mov     rcx, r8
0x180019bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bbb  movups  xmm0, xmmword ptr [rax]
0x180019bbe  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x180019bc6  mov     [rsi+7E0h], edi
0x180019bcc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019bd3  mov     [rbp+var_38], r14
0x180019bd7  lea     rax, [rbp+var_44]
0x180019bdb  mov     [rbp+var_30], rax
0x180019bdf  test    r15, r15
0x180019be2  jnz     loc_180019C9E
0x180019be8  mov     [rbp+var_44], 80070057h
0x180019bef  test    rcx, rcx
0x180019bf2  jnz     short loc_180019C35
0x180019bf4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019bfa  mov     rcx, rax
0x180019bfd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c04  test    rax, rax
0x180019c07  jz      short loc_180019C27
0x180019c09  mov     rax, [rax]
0x180019c0c  mov     edx, 7F0h
0x180019c11  mov     rax, [rax+8]
0x180019c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c1a  test    eax, eax
0x180019c1c  jz      short loc_180019C27
0x180019c1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c25  jmp     short loc_180019C35
0x180019c27  lea     rcx, qword_1800D6F70; this
0x180019c2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c35  cmp     byte ptr [rcx+8], 0
0x180019c39  jz      short loc_180019C67
0x180019c3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019c40  mov     r9d, [rbp+var_44]; int
0x180019c44  test    r9d, r9d
0x180019c47  jns     short loc_180019C67
0x180019c49  cmp     [rax+7CCh], r9d
0x180019c50  jz      short loc_180019C67
0x180019c52  mov     r8d, 515h; int
0x180019c58  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x180019c5f  mov     rcx, rax; this
0x180019c62  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019c67  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019c6e  jb      short loc_180019C96
0x180019c70  mov     edx, 8Eh
0x180019c75  mov     eax, [rbp+var_44]
0x180019c78  mov     [rsp+78h+var_58], eax
0x180019c7c  mov     r9, r14
0x180019c7f  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c8d  mov     rcx, [rcx+10h]
0x180019c91  call    WPP_SF_qD
0x180019c96  mov     edi, [rbp+var_44]
0x180019c99  jmp     loc_180019D5E
0x180019c9e  cmp     qword ptr [r14+90h], 0
0x180019ca6  jnz     loc_180019D78
0x180019cac  mov     [rbp+var_44], 0C00D3E85h
0x180019cb3  test    rcx, rcx
0x180019cb6  jnz     short loc_180019CF9
0x180019cb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019cbe  mov     rcx, rax
0x180019cc1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cc8  test    rax, rax
0x180019ccb  jz      short loc_180019CEB
0x180019ccd  mov     rax, [rax]
0x180019cd0  mov     edx, 7F0h
0x180019cd5  mov     rax, [rax+8]
0x180019cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cde  test    eax, eax
0x180019ce0  jz      short loc_180019CEB
0x180019ce2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ce9  jmp     short loc_180019CF9
0x180019ceb  lea     rcx, qword_1800D6F70; this
0x180019cf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019cf9  cmp     byte ptr [rcx+8], 0
0x180019cfd  jz      short loc_180019D2B
0x180019cff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019d04  mov     r9d, [rbp+var_44]; int
0x180019d08  test    r9d, r9d
0x180019d0b  jns     short loc_180019D2B
0x180019d0d  cmp     [rax+7CCh], r9d
0x180019d14  jz      short loc_180019D2B
0x180019d16  mov     r8d, 519h; int
0x180019d1c  lea     rdx, aMkvmfsourcelib_141; "MkvMfSourceLib::MkvMfSource::ProcessAsy"...
0x180019d23  mov     rcx, rax; this
0x180019d26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019d2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019d32  jb      short loc_180019D5B
0x180019d34  mov     edx, 8Fh
0x180019d39  mov     eax, [rbp+var_44]
0x180019d3c  mov     [rsp+78h+var_58], eax
0x180019d40  mov     r9, r14
0x180019d43  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d51  mov     rcx, [rcx+10h]
0x180019d55  call    WPP_SF_qD
0x180019d5a  nop
0x180019d5b  mov     edi, [rbp+var_44]
0x180019d5e  lea     rcx, [rbp+var_48]; this
0x180019d62  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019d67  nop
0x180019d68  mov     rcx, rbx; lpCriticalSection
0x180019d6b  call    cs:__imp_LeaveCriticalSection
0x180019d71  mov     eax, edi
0x180019d73  jmp     loc_180019EA2
0x180019d78  lea     r15, [r14+190h]
0x180019d7f  mov     rdi, r15
0x180019d82  mov     rcx, r14
0x180019d85  call    ?OnAsyncRead@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::OnAsyncRead(void)
0x180019d8a  test    eax, eax
0x180019d8c  jnz     short loc_180019DA4
0x180019d8e  lea     rdi, [r14+190h]
0x180019d95  cmp     qword ptr [rdi], 0
0x180019d99  jl      short loc_180019D82
0x180019d9b  lea     rsi, [r14+208h]
0x180019da2  jmp     short loc_180019DDF
0x180019da4  lea     rsi, [r14+208h]
0x180019dab  mov     [rsi], eax
0x180019dad  cmp     cs:byte_1800D78D3, 4
0x180019db4  jb      short loc_180019DDF
0x180019db6  mov     edx, 90h
0x180019dbb  mov     [rsp+78h+var_58], eax
0x180019dbf  mov     r9, r14
0x180019dc2  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dd0  mov     rcx, [rcx+88h]
0x180019dd7  call    WPP_SF_qD
0x180019ddc  mov     rdi, r15
0x180019ddf  cmp     qword ptr [rdi], 0
0x180019de3  jge     short loc_180019E4A
0x180019de5  cmp     dword ptr [rsi], 3
0x180019de8  jz      short loc_180019E4A
0x180019dea  mov     byte ptr [r14+1E6h], 0
0x180019df2  cmp     cs:byte_1800D78D3, 4
0x180019df9  jb      short loc_180019E29
0x180019dfb  movzx   eax, byte ptr [r14+1E5h]
0x180019e03  mov     edx, 91h
0x180019e08  mov     [rsp+78h+var_58], eax
0x180019e0c  mov     r9, r14
0x180019e0f  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e1d  mov     rcx, [rcx+88h]
0x180019e24  call    WPP_SF_qD
0x180019e29  cmp     byte ptr [r14+1E5h], 0
0x180019e31  jnz     short loc_180019E4A
0x180019e33  mov     byte ptr [r14+1E5h], 1
0x180019e3b  lea     rdx, [r14+1F8h]; struct IMFAsyncCallback *
0x180019e42  mov     rcx, r14; this
0x180019e45  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x180019e4a  cmp     dword ptr [r14+208h], 3
0x180019e52  jnz     short loc_180019E8D
0x180019e54  cmp     cs:byte_1800D78D3, 4
0x180019e5b  jb      short loc_180019E7F
0x180019e5d  mov     edx, 92h
0x180019e62  mov     r9, r14
0x180019e65  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180019e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e73  mov     rcx, [rcx+88h]
0x180019e7a  call    WPP_SF_q
0x180019e7f  mov     dword ptr [rsi], 1
0x180019e85  mov     byte ptr [r14+1E6h], 0
0x180019e8d  lea     rcx, [rbp+var_48]; this
0x180019e91  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019e96  nop
0x180019e97  mov     rcx, rbx; lpCriticalSection
0x180019e9a  call    cs:__imp_LeaveCriticalSection
0x180019ea0  xor     eax, eax
0x180019ea2  mov     rcx, [rbp+var_18]
0x180019ea6  xor     rcx, rsp; StackCookie
0x180019ea9  call    __security_check_cookie
0x180019eae  add     rsp, 78h
0x180019eb2  pop     r15
0x180019eb4  pop     r14
0x180019eb6  pop     rdi
0x180019eb7  pop     rsi
0x180019eb8  pop     rbx
0x180019eb9  pop     rbp
0x180019eba  retn
```
