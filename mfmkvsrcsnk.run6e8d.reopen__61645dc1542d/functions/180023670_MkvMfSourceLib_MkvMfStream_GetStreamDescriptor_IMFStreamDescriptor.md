# MkvMfSourceLib::MkvMfStream::GetStreamDescriptor(IMFStreamDescriptor * *)

- ea: `0x180023670`
- end: `0x180023972`
- name: `?GetStreamDescriptor@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFStreamDescriptor@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct IMFStreamDescriptor **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180023670`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002376b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002376b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002395d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002395d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800236b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800237a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002388e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800236b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800237a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002388e`

## string_xrefs

- `0x180023693`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180023710`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180023788`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180023805`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x180023857`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`
- `0x1800238eb`: `MkvMfSourceLib::MkvMfStream::GetStreamDescriptor`

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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v21 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v7 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180023670  mov     [rsp+arg_0], rbx
0x180023675  push    rbp
0x180023676  push    rsi
0x180023677  push    rdi
0x180023678  sub     rsp, 30h
0x18002367c  mov     rsi, rdx
0x18002367f  mov     rdi, rcx
0x180023682  test    rdx, rdx
0x180023685  jnz     loc_18002375B
0x18002368b  mov     esi, 101h
0x180023690  mov     r8d, esi; int
0x180023693  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002369a  lea     rcx, [rsp+48h+arg_8]; this
0x18002369f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800236a4  nop
0x1800236a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800236ac  test    rcx, rcx
0x1800236af  jnz     short loc_1800236F2
0x1800236b1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800236b7  mov     rcx, rax
0x1800236ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800236c1  test    rax, rax
0x1800236c4  jz      short loc_1800236E4
0x1800236c6  mov     rax, [rax]
0x1800236c9  mov     edx, 7F0h
0x1800236ce  mov     rax, [rax+8]
0x1800236d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236d7  test    eax, eax
0x1800236d9  jz      short loc_1800236E4
0x1800236db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800236e2  jmp     short loc_1800236F2
0x1800236e4  lea     rcx, qword_1800D6F70; this
0x1800236eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800236f2  mov     ebx, 80004003h
0x1800236f7  cmp     byte ptr [rcx+8], 0
0x1800236fb  jz      short loc_18002371F
0x1800236fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023702  cmp     [rax+7CCh], ebx
0x180023708  jz      short loc_18002371F
0x18002370a  mov     r9d, ebx; int
0x18002370d  mov     r8d, esi; int
0x180023710  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x180023717  mov     rcx, rax; this
0x18002371a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002371f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023726  jb      short loc_18002374C
0x180023728  mov     edx, 17h
0x18002372d  mov     [rsp+48h+var_28], ebx
0x180023731  mov     r9, rdi
0x180023734  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x18002373b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023742  mov     rcx, [rcx+10h]
0x180023746  call    WPP_SF_qD
0x18002374b  nop
0x18002374c  lea     rcx, [rsp+48h+arg_8]; this
0x180023751  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180023756  jmp     loc_180023963
0x18002375b  mov     rbp, [rcx+38h]
0x18002375f  add     rbp, 68h ; 'h'
0x180023763  mov     [rsp+48h+arg_10], rbp
0x180023768  mov     rcx, rbp; lpCriticalSection
0x18002376b  call    cs:__imp_EnterCriticalSection
0x180023771  nop
0x180023772  cmp     qword ptr [rdi+1C0h], 0
0x18002377a  jnz     loc_180023846
0x180023780  mov     esi, 108h
0x180023785  mov     r8d, esi; int
0x180023788  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002378f  lea     rcx, [rsp+48h+arg_8]; this
0x180023794  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180023799  nop
0x18002379a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800237a1  test    rcx, rcx
0x1800237a4  jnz     short loc_1800237E7
0x1800237a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800237ac  mov     rcx, rax
0x1800237af  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800237b6  test    rax, rax
0x1800237b9  jz      short loc_1800237D9
0x1800237bb  mov     rax, [rax]
0x1800237be  mov     edx, 7F0h
0x1800237c3  mov     rax, [rax+8]
0x1800237c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237cc  test    eax, eax
0x1800237ce  jz      short loc_1800237D9
0x1800237d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800237d7  jmp     short loc_1800237E7
0x1800237d9  lea     rcx, qword_1800D6F70; this
0x1800237e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800237e7  mov     ebx, 0C00D3E85h
0x1800237ec  cmp     byte ptr [rcx+8], 0
0x1800237f0  jz      short loc_180023814
0x1800237f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800237f7  cmp     [rax+7CCh], ebx
0x1800237fd  jz      short loc_180023814
0x1800237ff  mov     r9d, ebx; int
0x180023802  mov     r8d, esi; int
0x180023805  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002380c  mov     rcx, rax; this
0x18002380f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023814  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002381b  jb      short loc_180023841
0x18002381d  mov     edx, 18h
0x180023822  mov     [rsp+48h+var_28], ebx
0x180023826  mov     r9, rdi
0x180023829  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180023830  mov     rcx, cs:WPP_GLOBAL_Control
0x180023837  mov     rcx, [rcx+10h]
0x18002383b  call    WPP_SF_qD
0x180023840  nop
0x180023841  jmp     loc_180023927
0x180023846  cmp     qword ptr [rdi+40h], 0
0x18002384b  jnz     loc_18002393E
0x180023851  mov     r8d, 10Dh; int
0x180023857  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x18002385e  lea     rcx, [rsp+48h+arg_8]; this
0x180023863  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180023868  nop
0x180023869  mov     rax, [rdi]
0x18002386c  mov     rcx, rdi
0x18002386f  mov     rax, [rax+58h]
0x180023873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023878  mov     ebx, eax
0x18002387a  test    eax, eax
0x18002387c  jns     loc_180023933
0x180023882  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023889  test    rcx, rcx
0x18002388c  jnz     short loc_1800238CF
0x18002388e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180023894  mov     rcx, rax
0x180023897  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002389e  test    rax, rax
0x1800238a1  jz      short loc_1800238C1
0x1800238a3  mov     rax, [rax]
0x1800238a6  mov     edx, 7F0h
0x1800238ab  mov     rax, [rax+8]
0x1800238af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238b4  test    eax, eax
0x1800238b6  jz      short loc_1800238C1
0x1800238b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800238bf  jmp     short loc_1800238CF
0x1800238c1  lea     rcx, qword_1800D6F70; this
0x1800238c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800238cf  cmp     byte ptr [rcx+8], 0
0x1800238d3  jz      short loc_1800238FA
0x1800238d5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800238da  cmp     [rax+7CCh], ebx
0x1800238e0  jz      short loc_1800238FA
0x1800238e2  mov     r9d, ebx; int
0x1800238e5  mov     r8d, 10Dh; int
0x1800238eb  lea     rdx, aMkvmfsourcelib_8; "MkvMfSourceLib::MkvMfStream::GetStreamD"...
0x1800238f2  mov     rcx, rax; this
0x1800238f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800238fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023901  jb      short loc_180023927
0x180023903  mov     edx, 19h
0x180023908  mov     [rsp+48h+var_28], ebx
0x18002390c  mov     r9, rdi
0x18002390f  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180023916  mov     rcx, cs:WPP_GLOBAL_Control
0x18002391d  mov     rcx, [rcx+10h]
0x180023921  call    WPP_SF_qD
0x180023926  nop
0x180023927  lea     rcx, [rsp+48h+arg_8]; this
0x18002392c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180023931  jmp     short loc_18002395A
0x180023933  lea     rcx, [rsp+48h+arg_8]; this
0x180023938  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002393d  nop
0x18002393e  mov     rcx, [rdi+40h]
0x180023942  mov     rax, [rcx]
0x180023945  mov     r8, rsi
0x180023948  lea     rdx, _GUID_56c03d9c_9dbb_45f5_ab4b_d80f47c05938
0x18002394f  mov     rax, [rax]
0x180023952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023957  nop
0x180023958  xor     ebx, ebx
0x18002395a  mov     rcx, rbp; lpCriticalSection
0x18002395d  call    cs:__imp_LeaveCriticalSection
0x180023963  mov     eax, ebx
0x180023965  mov     rbx, [rsp+48h+arg_0]
0x18002396a  add     rsp, 30h
0x18002396e  pop     rdi
0x18002396f  pop     rsi
0x180023970  pop     rbp
0x180023971  retn
```
