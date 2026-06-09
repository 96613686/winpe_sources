# CreateExtensionArchitectureFromString(HSTRING__ *)

- ea: `0x1800ca498`
- end: `0x1800ca84e`
- name: `?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800347d0`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180054140`
- `0x1800ca400`
- `0x1800ca498`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca770`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ca770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800ca781`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca757`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca5f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca79d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca512`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca5f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca6b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ca79d`

## string_xrefs

- `0x1800ca4be`: `CreateExtensionArchitectureFromString`

## pseudocode

```c
__int64 __fastcall CreateExtensionArchitectureFromString(HSTRING a1)
{
  unsigned int v2; // ebx
  HSTRING *v3; // rax
  HRESULT v4; // edi
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  HSTRING *v9; // rax
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  HSTRING *v13; // rax
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  INT32 result; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v22[4]; // [rsp+34h] [rbp-2Ch] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  result = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v22, "CreateExtensionArchitectureFromString", 864);
  v3 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"x86");
  v4 = WindowsCompareStringOrdinal(a1, *v3, &result);
  if ( v4 >= 0 )
  {
    if ( !result )
    {
      v2 = 1;
      goto LABEL_56;
    }
    v9 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"x64");
    v4 = WindowsCompareStringOrdinal(a1, *v9, &result);
    if ( v4 >= 0 )
    {
      if ( !result )
      {
        v2 = 2;
        goto LABEL_56;
      }
      v13 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"arm");
      v4 = WindowsCompareStringOrdinal(a1, *v13, &result);
      if ( v4 >= 0 )
      {
        if ( !result )
        {
          v2 = 3;
          goto LABEL_56;
        }
        if ( WindowsCreateStringReference(L"arm64", 5u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v4 = WindowsCompareStringOrdinal(a1, string, &result);
        if ( v4 >= 0 )
        {
          if ( !result )
            v2 = 4;
        }
        else
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v17 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CreateExtensionArchitectureFromString", 885, v4);
          }
          if ( g_wppLevels )
          {
            v8 = 114;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v4 )
            CallStackContext::TraceFailure(v16, "CreateExtensionArchitectureFromString", 878, v4);
        }
        if ( g_wppLevels )
        {
          v8 = 113;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != v4 )
          CallStackContext::TraceFailure(v12, "CreateExtensionArchitectureFromString", 871, v4);
      }
      if ( g_wppLevels )
      {
        v8 = 112;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CreateExtensionArchitectureFromString", 864, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 111;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v4);
    }
  }
LABEL_56:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v22);
  return v2;
}

```

## disassembly

```asm
0x1800ca498  mov     [rsp-18h+arg_8], rbx
0x1800ca49d  mov     [rsp-18h+arg_10], rsi
0x1800ca4a2  push    rbp
0x1800ca4a3  push    rdi
0x1800ca4a4  push    r15
0x1800ca4a6  mov     rbp, rsp
0x1800ca4a9  sub     rsp, 60h
0x1800ca4ad  mov     rax, cs:__security_cookie
0x1800ca4b4  xor     rax, rsp
0x1800ca4b7  mov     [rbp+var_8], rax
0x1800ca4bb  mov     rsi, rcx
0x1800ca4be  lea     r15, aCreateextensio; "CreateExtensionArchitectureFromString"
0x1800ca4c5  xor     ebx, ebx
0x1800ca4c7  lea     rcx, [rbp+var_2C]; this
0x1800ca4cb  mov     rdx, r15; char *
0x1800ca4ce  mov     [rbp+result], ebx
0x1800ca4d1  mov     r8d, 360h; int
0x1800ca4d7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ca4dc  lea     rdx, aX86; "x86"
0x1800ca4e3  lea     rcx, [rbp+string]; string
0x1800ca4e7  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800ca4ec  lea     r8, [rbp+result]; result
0x1800ca4f0  mov     rcx, rsi; string1
0x1800ca4f3  mov     rdx, [rax]; string2
0x1800ca4f6  call    cs:__imp_WindowsCompareStringOrdinal
0x1800ca4fc  mov     edi, eax
0x1800ca4fe  test    eax, eax
0x1800ca500  jns     loc_1800CA5AE
0x1800ca506  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca50d  test    rcx, rcx
0x1800ca510  jnz     short loc_1800CA553
0x1800ca512  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca518  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca51f  mov     rcx, rax
0x1800ca522  test    rax, rax
0x1800ca525  jz      short loc_1800CA545
0x1800ca527  mov     rax, [rax]
0x1800ca52a  mov     edx, 7F0h
0x1800ca52f  mov     rax, [rax+8]
0x1800ca533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca538  test    eax, eax
0x1800ca53a  jz      short loc_1800CA545
0x1800ca53c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca543  jmp     short loc_1800CA553
0x1800ca545  lea     rcx, qword_180153440; this
0x1800ca54c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca553  cmp     [rcx+8], bl
0x1800ca556  jz      short loc_1800CA579
0x1800ca558  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca55d  cmp     [rax+7CCh], edi
0x1800ca563  jz      short loc_1800CA579
0x1800ca565  mov     r9d, edi; int
0x1800ca568  mov     r8d, 360h; int
0x1800ca56e  mov     rdx, r15; char *
0x1800ca571  mov     rcx, rax; this
0x1800ca574  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca579  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca580  jb      loc_1800CA822
0x1800ca586  mov     edx, 6Fh ; 'o'
0x1800ca58b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca592  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800ca599  xor     r9d, r9d
0x1800ca59c  mov     [rsp+60h+var_40], edi
0x1800ca5a0  mov     rcx, [rcx+10h]
0x1800ca5a4  call    WPP_SF_qD
0x1800ca5a9  jmp     loc_1800CA822
0x1800ca5ae  cmp     [rbp+result], ebx
0x1800ca5b1  jnz     short loc_1800CA5BD
0x1800ca5b3  mov     ebx, 1
0x1800ca5b8  jmp     loc_1800CA822
0x1800ca5bd  lea     rdx, aX64; "x64"
0x1800ca5c4  lea     rcx, [rbp+string]; string
0x1800ca5c8  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800ca5cd  lea     r8, [rbp+result]; result
0x1800ca5d1  mov     rcx, rsi; string1
0x1800ca5d4  mov     rdx, [rax]; string2
0x1800ca5d7  call    cs:__imp_WindowsCompareStringOrdinal
0x1800ca5dd  mov     edi, eax
0x1800ca5df  test    eax, eax
0x1800ca5e1  jns     loc_1800CA671
0x1800ca5e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca5ee  test    rcx, rcx
0x1800ca5f1  jnz     short loc_1800CA634
0x1800ca5f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca5f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca600  mov     rcx, rax
0x1800ca603  test    rax, rax
0x1800ca606  jz      short loc_1800CA626
0x1800ca608  mov     rax, [rax]
0x1800ca60b  mov     edx, 7F0h
0x1800ca610  mov     rax, [rax+8]
0x1800ca614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca619  test    eax, eax
0x1800ca61b  jz      short loc_1800CA626
0x1800ca61d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca624  jmp     short loc_1800CA634
0x1800ca626  lea     rcx, qword_180153440; this
0x1800ca62d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca634  cmp     [rcx+8], bl
0x1800ca637  jz      short loc_1800CA65A
0x1800ca639  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca63e  cmp     [rax+7CCh], edi
0x1800ca644  jz      short loc_1800CA65A
0x1800ca646  mov     r9d, edi; int
0x1800ca649  mov     r8d, 367h; int
0x1800ca64f  mov     rdx, r15; char *
0x1800ca652  mov     rcx, rax; this
0x1800ca655  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca65a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca661  jb      loc_1800CA822
0x1800ca667  mov     edx, 70h ; 'p'
0x1800ca66c  jmp     loc_1800CA58B
0x1800ca671  cmp     [rbp+result], ebx
0x1800ca674  jnz     short loc_1800CA680
0x1800ca676  mov     ebx, 2
0x1800ca67b  jmp     loc_1800CA822
0x1800ca680  lea     rdx, aArm; "arm"
0x1800ca687  lea     rcx, [rbp+string]; string
0x1800ca68b  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800ca690  lea     r8, [rbp+result]; result
0x1800ca694  mov     rcx, rsi; string1
0x1800ca697  mov     rdx, [rax]; string2
0x1800ca69a  call    cs:__imp_WindowsCompareStringOrdinal
0x1800ca6a0  mov     edi, eax
0x1800ca6a2  test    eax, eax
0x1800ca6a4  jns     loc_1800CA734
0x1800ca6aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca6b1  test    rcx, rcx
0x1800ca6b4  jnz     short loc_1800CA6F7
0x1800ca6b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca6bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca6c3  mov     rcx, rax
0x1800ca6c6  test    rax, rax
0x1800ca6c9  jz      short loc_1800CA6E9
0x1800ca6cb  mov     rax, [rax]
0x1800ca6ce  mov     edx, 7F0h
0x1800ca6d3  mov     rax, [rax+8]
0x1800ca6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca6dc  test    eax, eax
0x1800ca6de  jz      short loc_1800CA6E9
0x1800ca6e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca6e7  jmp     short loc_1800CA6F7
0x1800ca6e9  lea     rcx, qword_180153440; this
0x1800ca6f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca6f7  cmp     [rcx+8], bl
0x1800ca6fa  jz      short loc_1800CA71D
0x1800ca6fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca701  cmp     [rax+7CCh], edi
0x1800ca707  jz      short loc_1800CA71D
0x1800ca709  mov     r9d, edi; int
0x1800ca70c  mov     r8d, 36Eh; int
0x1800ca712  mov     rdx, r15; char *
0x1800ca715  mov     rcx, rax; this
0x1800ca718  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca71d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca724  jb      loc_1800CA822
0x1800ca72a  mov     edx, 71h ; 'q'
0x1800ca72f  jmp     loc_1800CA58B
0x1800ca734  cmp     [rbp+result], ebx
0x1800ca737  jnz     short loc_1800CA743
0x1800ca739  mov     ebx, 3
0x1800ca73e  jmp     loc_1800CA822
0x1800ca743  lea     r9, [rbp+string]; string
0x1800ca747  mov     edx, 5; length
0x1800ca74c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ca750  lea     rcx, aArm64; "arm64"
0x1800ca757  call    cs:__imp_WindowsCreateStringReference
0x1800ca75d  test    eax, eax
0x1800ca75f  jns     short loc_1800CA776
0x1800ca761  xor     r9d, r9d; lpArguments
0x1800ca764  xor     r8d, r8d; nNumberOfArguments
0x1800ca767  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800ca76c  lea     edx, [r9+1]; dwExceptionFlags
0x1800ca770  call    cs:__imp_RaiseException
0x1800ca776  mov     rdx, [rbp+string]; string2
0x1800ca77a  lea     r8, [rbp+result]; result
0x1800ca77e  mov     rcx, rsi; string1
0x1800ca781  call    cs:__imp_WindowsCompareStringOrdinal
0x1800ca787  mov     edi, eax
0x1800ca789  test    eax, eax
0x1800ca78b  jns     loc_1800CA817
0x1800ca791  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca798  test    rcx, rcx
0x1800ca79b  jnz     short loc_1800CA7DE
0x1800ca79d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ca7a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca7aa  mov     rcx, rax
0x1800ca7ad  test    rax, rax
0x1800ca7b0  jz      short loc_1800CA7D0
0x1800ca7b2  mov     rax, [rax]
0x1800ca7b5  mov     edx, 7F0h
0x1800ca7ba  mov     rax, [rax+8]
0x1800ca7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca7c3  test    eax, eax
0x1800ca7c5  jz      short loc_1800CA7D0
0x1800ca7c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca7ce  jmp     short loc_1800CA7DE
0x1800ca7d0  lea     rcx, qword_180153440; this
0x1800ca7d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ca7de  cmp     [rcx+8], bl
0x1800ca7e1  jz      short loc_1800CA804
0x1800ca7e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ca7e8  cmp     [rax+7CCh], edi
0x1800ca7ee  jz      short loc_1800CA804
0x1800ca7f0  mov     r9d, edi; int
0x1800ca7f3  mov     r8d, 375h; int
0x1800ca7f9  mov     rdx, r15; char *
0x1800ca7fc  mov     rcx, rax; this
0x1800ca7ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ca804  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ca80b  jb      short loc_1800CA822
0x1800ca80d  mov     edx, 72h ; 'r'
0x1800ca812  jmp     loc_1800CA58B
0x1800ca817  cmp     [rbp+result], ebx
0x1800ca81a  mov     eax, 4
0x1800ca81f  cmovz   ebx, eax
0x1800ca822  lea     rcx, [rbp+var_2C]; this
0x1800ca826  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ca82b  mov     eax, ebx
0x1800ca82d  mov     rcx, [rbp+var_8]
0x1800ca831  xor     rcx, rsp; StackCookie
0x1800ca834  call    __security_check_cookie
0x1800ca839  lea     r11, [rsp+60h+var_s0]
0x1800ca83e  mov     rbx, [r11+28h]
0x1800ca842  mov     rsi, [r11+30h]
0x1800ca846  mov     rsp, r11
0x1800ca849  pop     r15
0x1800ca84b  pop     rdi
0x1800ca84c  pop     rbp
0x1800ca84d  retn
```
