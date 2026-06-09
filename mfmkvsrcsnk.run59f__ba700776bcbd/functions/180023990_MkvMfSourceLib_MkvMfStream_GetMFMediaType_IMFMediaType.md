# MkvMfSourceLib::MkvMfStream::GetMFMediaType(IMFMediaType * *)

- ea: `0x180023990`
- end: `0x180023ba7`
- name: `?GetMFMediaType@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFMediaType@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct IMFMediaType **)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002ddc0`
- `0x1800315a0`
- `0x180033e50`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180023990`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800239d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023acc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800239d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180023acc`
- `MFPlat!MFCreateMediaType` at `0x180023aaa`
- `MFPlat!MFCreateMediaType` at `0x180023aaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfStream::GetMFMediaType(
        MkvMfSourceLib::MkvMfStream *this,
        struct IMFMediaType **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  HRESULT v9; // ebx
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFMediaType *v17; // rax
  char v19; // [rsp+48h] [rbp+10h] BYREF
  IMFMediaType *ppMFType; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    ppMFType = 0;
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v19,
      "MkvMfSourceLib::MkvMfStream::GetMFMediaType",
      142);
    v9 = MFCreateMediaType(&ppMFType);
    if ( v9 >= 0 )
    {
      v17 = ppMFType;
      ppMFType = 0;
      *a2 = v17;
      v9 = 0;
    }
    else
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfStream::GetMFMediaType", 142, v9);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v9);
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v19,
      "MkvMfSourceLib::MkvMfStream::GetMFMediaType",
      138);
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
        CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfStream::GetMFMediaType", 138, -2147467261);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
        this,
        -2147467261);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180023990  mov     [rsp+arg_0], rbx
0x180023995  mov     [rsp+arg_18], rsi
0x18002399a  push    rdi
0x18002399b  sub     rsp, 30h
0x18002399f  mov     rdi, rdx
0x1800239a2  mov     rsi, rcx
0x1800239a5  test    rdx, rdx
0x1800239a8  jnz     loc_180023A84
0x1800239ae  mov     edi, 8Ah
0x1800239b3  mov     r8d, edi; int
0x1800239b6  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x1800239bd  lea     rcx, [rsp+38h+arg_8]; this
0x1800239c2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800239c7  nop
0x1800239c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800239cf  test    rcx, rcx
0x1800239d2  jnz     short loc_180023A1B
0x1800239d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800239db  nop     dword ptr [rax+rax+00h]
0x1800239e0  mov     rcx, rax
0x1800239e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800239ea  test    rax, rax
0x1800239ed  jz      short loc_180023A0D
0x1800239ef  mov     rax, [rax]
0x1800239f2  mov     edx, 7F0h
0x1800239f7  mov     rax, [rax+8]
0x1800239fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a00  test    eax, eax
0x180023a02  jz      short loc_180023A0D
0x180023a04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023a0b  jmp     short loc_180023A1B
0x180023a0d  lea     rcx, qword_1800DBF70; this
0x180023a14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180023a1b  mov     ebx, 80004003h
0x180023a20  cmp     byte ptr [rcx+8], 0
0x180023a24  jz      short loc_180023A48
0x180023a26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023a2b  cmp     [rax+7CCh], ebx
0x180023a31  jz      short loc_180023A48
0x180023a33  mov     r9d, ebx; int
0x180023a36  mov     r8d, edi; int
0x180023a39  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180023a40  mov     rcx, rax; this
0x180023a43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023a48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023a4f  jb      short loc_180023A75
0x180023a51  mov     edx, 10h
0x180023a56  mov     [rsp+38h+var_18], ebx
0x180023a5a  mov     r9, rsi
0x180023a5d  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180023a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a6b  mov     rcx, [rcx+10h]
0x180023a6f  call    WPP_SF_qD
0x180023a74  nop
0x180023a75  lea     rcx, [rsp+38h+arg_8]; this
0x180023a7a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180023a7f  jmp     loc_180023B94
0x180023a84  mov     [rsp+38h+ppMFType], 0
0x180023a8d  mov     r8d, 8Eh; int
0x180023a93  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180023a9a  lea     rcx, [rsp+38h+arg_8]; this
0x180023a9f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180023aa4  nop
0x180023aa5  lea     rcx, [rsp+38h+ppMFType]; ppMFType
0x180023aaa  call    cs:__imp_MFCreateMediaType
0x180023ab1  nop     dword ptr [rax+rax+00h]
0x180023ab6  mov     ebx, eax
0x180023ab8  test    eax, eax
0x180023aba  jns     loc_180023B6C
0x180023ac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023ac7  test    rcx, rcx
0x180023aca  jnz     short loc_180023B13
0x180023acc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180023ad3  nop     dword ptr [rax+rax+00h]
0x180023ad8  mov     rcx, rax
0x180023adb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180023ae2  test    rax, rax
0x180023ae5  jz      short loc_180023B05
0x180023ae7  mov     rax, [rax]
0x180023aea  mov     edx, 7F0h
0x180023aef  mov     rax, [rax+8]
0x180023af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023af8  test    eax, eax
0x180023afa  jz      short loc_180023B05
0x180023afc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180023b03  jmp     short loc_180023B13
0x180023b05  lea     rcx, qword_1800DBF70; this
0x180023b0c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180023b13  cmp     byte ptr [rcx+8], 0
0x180023b17  jz      short loc_180023B3E
0x180023b19  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180023b1e  cmp     [rax+7CCh], ebx
0x180023b24  jz      short loc_180023B3E
0x180023b26  mov     r9d, ebx; int
0x180023b29  mov     r8d, 8Eh; int
0x180023b2f  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180023b36  mov     rcx, rax; this
0x180023b39  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180023b3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180023b45  jb      short loc_180023B7F
0x180023b47  mov     edx, 11h
0x180023b4c  mov     [rsp+38h+var_18], ebx
0x180023b50  mov     r9, rsi
0x180023b53  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180023b5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b61  mov     rcx, [rcx+10h]
0x180023b65  call    WPP_SF_qD
0x180023b6a  jmp     short loc_180023B7F
0x180023b6c  mov     rax, [rsp+38h+ppMFType]
0x180023b71  mov     [rsp+38h+ppMFType], 0
0x180023b7a  mov     [rdi], rax
0x180023b7d  xor     ebx, ebx
0x180023b7f  lea     rcx, [rsp+38h+arg_8]; this
0x180023b84  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180023b89  nop
0x180023b8a  lea     rcx, [rsp+38h+ppMFType]
0x180023b8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023b94  mov     eax, ebx
0x180023b96  mov     rbx, [rsp+38h+arg_0]
0x180023b9b  mov     rsi, [rsp+38h+arg_18]
0x180023ba0  add     rsp, 30h
0x180023ba4  pop     rdi
0x180023ba5  retn
```
