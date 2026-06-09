# MkvMfSourceLib::MkvMfStream::GetMFMediaType(IMFMediaType * *)

- ea: `0x180022a90`
- end: `0x180022c94`
- name: `?GetMFMediaType@MkvMfStream@MkvMfSourceLib@@UEAAJPEAPEAUIMFMediaType@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfStream *__hidden this, struct IMFMediaType **)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002ca00`
- `0x18002fff0`
- `0x1800327d0`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180022a90`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022bc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022ad4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180022bc0`
- `MFPlat!MFCreateMediaType` at `0x180022ba4`
- `MFPlat!MFCreateMediaType` at `0x180022ba4`

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
          v14 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfStream::GetMFMediaType", 142, v9);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f75889742cf2386418712d98e96b47e0_Traceguids, this, v9);
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
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        WPP_f75889742cf2386418712d98e96b47e0_Traceguids,
        this,
        -2147467261);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v19);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022a90  mov     [rsp+arg_0], rbx
0x180022a95  mov     [rsp+arg_18], rsi
0x180022a9a  push    rdi
0x180022a9b  sub     rsp, 30h
0x180022a9f  mov     rdi, rdx
0x180022aa2  mov     rsi, rcx
0x180022aa5  test    rdx, rdx
0x180022aa8  jnz     loc_180022B7E
0x180022aae  mov     edi, 8Ah
0x180022ab3  mov     r8d, edi; int
0x180022ab6  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180022abd  lea     rcx, [rsp+38h+arg_8]; this
0x180022ac2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180022ac7  nop
0x180022ac8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022acf  test    rcx, rcx
0x180022ad2  jnz     short loc_180022B15
0x180022ad4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022ada  mov     rcx, rax
0x180022add  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022ae4  test    rax, rax
0x180022ae7  jz      short loc_180022B07
0x180022ae9  mov     rax, [rax]
0x180022aec  mov     edx, 7F0h
0x180022af1  mov     rax, [rax+8]
0x180022af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022afa  test    eax, eax
0x180022afc  jz      short loc_180022B07
0x180022afe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022b05  jmp     short loc_180022B15
0x180022b07  lea     rcx, qword_1800D6F70; this
0x180022b0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022b15  mov     ebx, 80004003h
0x180022b1a  cmp     byte ptr [rcx+8], 0
0x180022b1e  jz      short loc_180022B42
0x180022b20  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022b25  cmp     [rax+7CCh], ebx
0x180022b2b  jz      short loc_180022B42
0x180022b2d  mov     r9d, ebx; int
0x180022b30  mov     r8d, edi; int
0x180022b33  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180022b3a  mov     rcx, rax; this
0x180022b3d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022b42  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022b49  jb      short loc_180022B6F
0x180022b4b  mov     edx, 10h
0x180022b50  mov     [rsp+38h+var_18], ebx
0x180022b54  mov     r9, rsi
0x180022b57  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180022b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b65  mov     rcx, [rcx+10h]
0x180022b69  call    WPP_SF_qD
0x180022b6e  nop
0x180022b6f  lea     rcx, [rsp+38h+arg_8]; this
0x180022b74  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180022b79  jmp     loc_180022C82
0x180022b7e  mov     [rsp+38h+ppMFType], 0
0x180022b87  mov     r8d, 8Eh; int
0x180022b8d  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180022b94  lea     rcx, [rsp+38h+arg_8]; this
0x180022b99  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180022b9e  nop
0x180022b9f  lea     rcx, [rsp+38h+ppMFType]; ppMFType
0x180022ba4  call    cs:__imp_MFCreateMediaType
0x180022baa  mov     ebx, eax
0x180022bac  test    eax, eax
0x180022bae  jns     loc_180022C5A
0x180022bb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022bbb  test    rcx, rcx
0x180022bbe  jnz     short loc_180022C01
0x180022bc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180022bc6  mov     rcx, rax
0x180022bc9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180022bd0  test    rax, rax
0x180022bd3  jz      short loc_180022BF3
0x180022bd5  mov     rax, [rax]
0x180022bd8  mov     edx, 7F0h
0x180022bdd  mov     rax, [rax+8]
0x180022be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022be6  test    eax, eax
0x180022be8  jz      short loc_180022BF3
0x180022bea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180022bf1  jmp     short loc_180022C01
0x180022bf3  lea     rcx, qword_1800D6F70; this
0x180022bfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180022c01  cmp     byte ptr [rcx+8], 0
0x180022c05  jz      short loc_180022C2C
0x180022c07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180022c0c  cmp     [rax+7CCh], ebx
0x180022c12  jz      short loc_180022C2C
0x180022c14  mov     r9d, ebx; int
0x180022c17  mov     r8d, 8Eh; int
0x180022c1d  lea     rdx, aMkvmfsourcelib_138; "MkvMfSourceLib::MkvMfStream::GetMFMedia"...
0x180022c24  mov     rcx, rax; this
0x180022c27  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180022c2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180022c33  jb      short loc_180022C6D
0x180022c35  mov     edx, 11h
0x180022c3a  mov     [rsp+38h+var_18], ebx
0x180022c3e  mov     r9, rsi
0x180022c41  lea     r8, WPP_f75889742cf2386418712d98e96b47e0_Traceguids
0x180022c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c4f  mov     rcx, [rcx+10h]
0x180022c53  call    WPP_SF_qD
0x180022c58  jmp     short loc_180022C6D
0x180022c5a  mov     rax, [rsp+38h+ppMFType]
0x180022c5f  mov     [rsp+38h+ppMFType], 0
0x180022c68  mov     [rdi], rax
0x180022c6b  xor     ebx, ebx
0x180022c6d  lea     rcx, [rsp+38h+arg_8]; this
0x180022c72  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180022c77  nop
0x180022c78  lea     rcx, [rsp+38h+ppMFType]
0x180022c7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022c82  mov     eax, ebx
0x180022c84  mov     rbx, [rsp+38h+arg_0]
0x180022c89  mov     rsi, [rsp+38h+arg_18]
0x180022c8e  add     rsp, 30h
0x180022c92  pop     rdi
0x180022c93  retn
```
