# MkvMfSourceLib::MkvMfStream::GetStreamDescriptor(IMFStreamDescriptor * *)

- ea: `0x1800245d0`
- end: `0x1800248f1`
- name: `?GetStreamDescriptor@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFStreamDescriptor@@@Z`
- size: `801`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct IMFStreamDescriptor **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800245d0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800248d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024712`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024800`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024611`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024712`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180024800`

## string_xrefs

- `0x1800245f3`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180024676`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x1800246f4`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180024777`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x1800247c9`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180024863`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MkvMfSourceLib::MkvMfStream::GetStreamDescriptor(
        MkvMfSourceLib::MkvMfStream *this,
        struct IMFStreamDescriptor **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  int v9; // ebx
  struct CallStackContext *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbp
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  char v25; // [rsp+58h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+60h] [rbp+18h]

  if ( a2 )
  {
    v11 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 7) + 104LL);
    v26 = v11;
    EnterCriticalSection(v11);
    if ( !*((_QWORD *)this + 56) )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v25,
        "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor",
        264);
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v9 = -1072873851;
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873851 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor",
            264,
            -1072873851);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
          this,
          -1072873851);
LABEL_37:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
LABEL_40:
      LeaveCriticalSection(v11);
      return (unsigned int)v9;
    }
    if ( !*((_QWORD *)this + 8) )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v25,
        "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor",
        269);
      v9 = (*(__int64 (__fastcall **)(MkvMfSourceLib::MkvMfStream *))(*(_QWORD *)this + 88LL))(this);
      if ( v9 < 0 )
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
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != v9 )
            CallStackContext::TraceFailure(v23, "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor", 269, v9);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v9);
        goto LABEL_37;
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
    }
    (***((void (__fastcall ****)(_QWORD, GUID *, struct IMFStreamDescriptor **))this + 8))(
      *((_QWORD *)this + 8),
      &GUID_56c03d9c_9dbb_45f5_ab4b_d80f47c05938,
      a2);
    v9 = 0;
    goto LABEL_40;
  }
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v25,
    "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor",
    257);
  v7 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
    CallStackTracing::s_wpInstance = v8;
    if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
    {
      v7 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v7 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v9 = -2147467261;
  if ( *((_BYTE *)v7 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
    if ( *((_DWORD *)v10 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfStream::GetStreamDescriptor", 257, -2147467261);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
      this,
      -2147467261);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800245d0  mov     [rsp+arg_0], rbx
0x1800245d5  push    rbp
0x1800245d6  push    rsi
0x1800245d7  push    rdi
0x1800245d8  sub     rsp, 30h
0x1800245dc  mov     rsi, rdx
0x1800245df  mov     rdi, rcx
0x1800245e2  test    rdx, rdx
0x1800245e5  jnz     loc_1800246C1
0x1800245eb  mov     esi, 101h
0x1800245f0  mov     r8d, esi; int
0x1800245f3  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x1800245fa  lea     rcx, [rsp+48h+arg_8]; this
0x1800245ff  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024604  nop
0x180024605  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002460c  test    rcx, rcx
0x18002460f  jnz     short loc_180024658
0x180024611  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024618  nop     dword ptr [rax+rax+00h]
0x18002461d  mov     rcx, rax
0x180024620  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024627  test    rax, rax
0x18002462a  jz      short loc_18002464A
0x18002462c  mov     rax, [rax]
0x18002462f  mov     edx, 7F0h
0x180024634  mov     rax, [rax+8]
0x180024638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463d  test    eax, eax
0x18002463f  jz      short loc_18002464A
0x180024641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024648  jmp     short loc_180024658
0x18002464a  lea     rcx, qword_1800DBF70; this
0x180024651  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024658  mov     ebx, 80004003h
0x18002465d  cmp     byte ptr [rcx+8], 0
0x180024661  jz      short loc_180024685
0x180024663  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024668  cmp     [rax+7CCh], ebx
0x18002466e  jz      short loc_180024685
0x180024670  mov     r9d, ebx; int
0x180024673  mov     r8d, esi; int
0x180024676  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002467d  mov     rcx, rax; this
0x180024680  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180024685  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002468c  jb      short loc_1800246B2
0x18002468e  mov     edx, 17h
0x180024693  mov     [rsp+48h+var_28], ebx
0x180024697  mov     r9, rdi
0x18002469a  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800246a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246a8  mov     rcx, [rcx+10h]
0x1800246ac  call    WPP_SF_qD
0x1800246b1  nop
0x1800246b2  lea     rcx, [rsp+48h+arg_8]; this
0x1800246b7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800246bc  jmp     loc_1800248E1
0x1800246c1  mov     rbp, [rcx+38h]
0x1800246c5  add     rbp, 68h ; 'h'
0x1800246c9  mov     [rsp+48h+arg_10], rbp
0x1800246ce  mov     rcx, rbp; lpCriticalSection
0x1800246d1  call    cs:__imp_EnterCriticalSection
0x1800246d8  nop     dword ptr [rax+rax+00h]
0x1800246dd  nop
0x1800246de  cmp     qword ptr [rdi+1C0h], 0
0x1800246e6  jnz     loc_1800247B8
0x1800246ec  mov     esi, 108h
0x1800246f1  mov     r8d, esi; int
0x1800246f4  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x1800246fb  lea     rcx, [rsp+48h+arg_8]; this
0x180024700  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180024705  nop
0x180024706  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002470d  test    rcx, rcx
0x180024710  jnz     short loc_180024759
0x180024712  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024719  nop     dword ptr [rax+rax+00h]
0x18002471e  mov     rcx, rax
0x180024721  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024728  test    rax, rax
0x18002472b  jz      short loc_18002474B
0x18002472d  mov     rax, [rax]
0x180024730  mov     edx, 7F0h
0x180024735  mov     rax, [rax+8]
0x180024739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002473e  test    eax, eax
0x180024740  jz      short loc_18002474B
0x180024742  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024749  jmp     short loc_180024759
0x18002474b  lea     rcx, qword_1800DBF70; this
0x180024752  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024759  mov     ebx, 0C00D3E85h
0x18002475e  cmp     byte ptr [rcx+8], 0
0x180024762  jz      short loc_180024786
0x180024764  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024769  cmp     [rax+7CCh], ebx
0x18002476f  jz      short loc_180024786
0x180024771  mov     r9d, ebx; int
0x180024774  mov     r8d, esi; int
0x180024777  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002477e  mov     rcx, rax; this
0x180024781  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180024786  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002478d  jb      short loc_1800247B3
0x18002478f  mov     edx, 18h
0x180024794  mov     [rsp+48h+var_28], ebx
0x180024798  mov     r9, rdi
0x18002479b  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x1800247a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247a9  mov     rcx, [rcx+10h]
0x1800247ad  call    WPP_SF_qD
0x1800247b2  nop
0x1800247b3  jmp     loc_18002489F
0x1800247b8  cmp     qword ptr [rdi+40h], 0
0x1800247bd  jnz     loc_1800248B6
0x1800247c3  mov     r8d, 10Dh; int
0x1800247c9  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x1800247d0  lea     rcx, [rsp+48h+arg_8]; this
0x1800247d5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800247da  nop
0x1800247db  mov     rax, [rdi]
0x1800247de  mov     rcx, rdi
0x1800247e1  mov     rax, [rax+58h]
0x1800247e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ea  mov     ebx, eax
0x1800247ec  test    eax, eax
0x1800247ee  jns     loc_1800248AB
0x1800247f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800247fb  test    rcx, rcx
0x1800247fe  jnz     short loc_180024847
0x180024800  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180024807  nop     dword ptr [rax+rax+00h]
0x18002480c  mov     rcx, rax
0x18002480f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180024816  test    rax, rax
0x180024819  jz      short loc_180024839
0x18002481b  mov     rax, [rax]
0x18002481e  mov     edx, 7F0h
0x180024823  mov     rax, [rax+8]
0x180024827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002482c  test    eax, eax
0x18002482e  jz      short loc_180024839
0x180024830  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180024837  jmp     short loc_180024847
0x180024839  lea     rcx, qword_1800DBF70; this
0x180024840  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180024847  cmp     byte ptr [rcx+8], 0
0x18002484b  jz      short loc_180024872
0x18002484d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180024852  cmp     [rax+7CCh], ebx
0x180024858  jz      short loc_180024872
0x18002485a  mov     r9d, ebx; int
0x18002485d  mov     r8d, 10Dh; int
0x180024863  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002486a  mov     rcx, rax; this
0x18002486d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180024872  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180024879  jb      short loc_18002489F
0x18002487b  mov     edx, 19h
0x180024880  mov     [rsp+48h+var_28], ebx
0x180024884  mov     r9, rdi
0x180024887  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x18002488e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024895  mov     rcx, [rcx+10h]
0x180024899  call    WPP_SF_qD
0x18002489e  nop
0x18002489f  lea     rcx, [rsp+48h+arg_8]; this
0x1800248a4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800248a9  jmp     short loc_1800248D2
0x1800248ab  lea     rcx, [rsp+48h+arg_8]; this
0x1800248b0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800248b5  nop
0x1800248b6  mov     rcx, [rdi+40h]
0x1800248ba  mov     rax, [rcx]
0x1800248bd  mov     r8, rsi
0x1800248c0  lea     rdx, _GUID_56c03d9c_9dbb_45f5_ab4b_d80f47c05938
0x1800248c7  mov     rax, [rax]
0x1800248ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248cf  nop
0x1800248d0  xor     ebx, ebx
0x1800248d2  mov     rcx, rbp; lpCriticalSection
0x1800248d5  call    cs:__imp_LeaveCriticalSection
0x1800248dc  nop     dword ptr [rax+rax+00h]
0x1800248e1  mov     eax, ebx
0x1800248e3  mov     rbx, [rsp+48h+arg_0]
0x1800248e8  add     rsp, 30h
0x1800248ec  pop     rdi
0x1800248ed  pop     rsi
0x1800248ee  pop     rbp
0x1800248ef  retn
```
