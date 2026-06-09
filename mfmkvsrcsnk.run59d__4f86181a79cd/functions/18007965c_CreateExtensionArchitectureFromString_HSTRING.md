# CreateExtensionArchitectureFromString(HSTRING__ *)

- ea: `0x18007965c`
- end: `0x180079a4f`
- name: `?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z`
- size: `1011`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a0e4`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x180078124`
- `0x18007965c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007995e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007995e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800796ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800797a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180079876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180079975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800796ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800797a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180079876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180079975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007993f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007993f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800796dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800797c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079898`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079997`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800796dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800797c9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079898`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180079997`

## string_xrefs

- `0x180079682`: `CreateExtensionArchitectureFromString`

## pseudocode

```c
__int64 __fastcall CreateExtensionArchitectureFromString(HSTRING a1)
{
  unsigned int v2; // ebx
  HSTRING *v3; // rax
  __int64 v4; // rdx
  HRESULT v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  HSTRING *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  HSTRING *v19; // rax
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
  struct CallStackContext *ThreadRelativeContext; // rax
  INT32 result; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v34[4]; // [rsp+34h] [rbp-2Ch] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  result = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v34, "CreateExtensionArchitectureFromString", 864);
  v3 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"x86");
  v5 = WindowsCompareStringOrdinal(a1, *v3, &result);
  if ( v5 >= 0 )
  {
    if ( !result )
    {
      v2 = 1;
      goto LABEL_56;
    }
    v12 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"x64");
    v5 = WindowsCompareStringOrdinal(a1, *v12, &result);
    if ( v5 >= 0 )
    {
      if ( !result )
      {
        v2 = 2;
        goto LABEL_56;
      }
      v19 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"arm");
      v5 = WindowsCompareStringOrdinal(a1, *v19, &result);
      if ( v5 >= 0 )
      {
        if ( !result )
        {
          v2 = 3;
          goto LABEL_56;
        }
        if ( WindowsCreateStringReference(L"arm64", 5u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v5 = WindowsCompareStringOrdinal(a1, string, &result);
        if ( v5 >= 0 )
        {
          if ( !result )
            v2 = 4;
        }
        else
        {
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CreateExtensionArchitectureFromString", 885, v5);
          }
          if ( g_wppLevels )
          {
            v11 = 114;
            goto LABEL_12;
          }
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
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v5 )
            CallStackContext::TraceFailure(v25, "CreateExtensionArchitectureFromString", 878, v5);
        }
        if ( g_wppLevels )
        {
          v11 = 113;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v5 )
          CallStackContext::TraceFailure(v18, "CreateExtensionArchitectureFromString", 871, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 112;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v5 )
        CallStackContext::TraceFailure(v10, "CreateExtensionArchitectureFromString", 864, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 111;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v5);
    }
  }
LABEL_56:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  return v2;
}

```

## disassembly

```asm
0x18007965c  mov     [rsp-18h+arg_8], rbx
0x180079661  mov     [rsp-18h+arg_10], rsi
0x180079666  push    rbp
0x180079667  push    rdi
0x180079668  push    r15
0x18007966a  mov     rbp, rsp
0x18007966d  sub     rsp, 60h
0x180079671  mov     rax, cs:__security_cookie
0x180079678  xor     rax, rsp
0x18007967b  mov     [rbp+var_8], rax
0x18007967f  mov     rsi, rcx
0x180079682  lea     r15, aCreateextensio; "CreateExtensionArchitectureFromString"
0x180079689  xor     ebx, ebx
0x18007968b  lea     rcx, [rbp+var_2C]; this
0x18007968f  mov     rdx, r15; char *
0x180079692  mov     [rbp+result], ebx
0x180079695  mov     r8d, 360h; int
0x18007969b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800796a0  lea     rdx, aX86; "x86"
0x1800796a7  lea     rcx, [rbp+string]; string
0x1800796ab  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800796b0  lea     r8, [rbp+result]; result
0x1800796b4  mov     rcx, rsi; string1
0x1800796b7  mov     rdx, [rax]; string2
0x1800796ba  call    cs:__imp_WindowsCompareStringOrdinal
0x1800796c1  nop     dword ptr [rax+rax+00h]
0x1800796c6  mov     edi, eax
0x1800796c8  test    eax, eax
0x1800796ca  jns     loc_18007977E
0x1800796d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800796d7  test    rcx, rcx
0x1800796da  jnz     short loc_180079723
0x1800796dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800796e3  nop     dword ptr [rax+rax+00h]
0x1800796e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800796ef  mov     rcx, rax
0x1800796f2  test    rax, rax
0x1800796f5  jz      short loc_180079715
0x1800796f7  mov     rax, [rax]
0x1800796fa  mov     edx, 7F0h
0x1800796ff  mov     rax, [rax+8]
0x180079703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079708  test    eax, eax
0x18007970a  jz      short loc_180079715
0x18007970c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079713  jmp     short loc_180079723
0x180079715  lea     rcx, qword_1800DBF70; this
0x18007971c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079723  cmp     [rcx+8], bl
0x180079726  jz      short loc_180079749
0x180079728  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007972d  cmp     [rax+7CCh], edi
0x180079733  jz      short loc_180079749
0x180079735  mov     r9d, edi; int
0x180079738  mov     r8d, 360h; int
0x18007973e  mov     rdx, r15; char *
0x180079741  mov     rcx, rax; this
0x180079744  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079749  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079750  jb      loc_180079A22
0x180079756  mov     edx, 6Fh ; 'o'
0x18007975b  mov     rcx, cs:WPP_GLOBAL_Control
0x180079762  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180079769  xor     r9d, r9d
0x18007976c  mov     [rsp+60h+var_40], edi
0x180079770  mov     rcx, [rcx+10h]
0x180079774  call    WPP_SF_qD
0x180079779  jmp     loc_180079A22
0x18007977e  cmp     [rbp+result], ebx
0x180079781  jnz     short loc_18007978D
0x180079783  mov     ebx, 1
0x180079788  jmp     loc_180079A22
0x18007978d  lea     rdx, aX64; "x64"
0x180079794  lea     rcx, [rbp+string]; string
0x180079798  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18007979d  lea     r8, [rbp+result]; result
0x1800797a1  mov     rcx, rsi; string1
0x1800797a4  mov     rdx, [rax]; string2
0x1800797a7  call    cs:__imp_WindowsCompareStringOrdinal
0x1800797ae  nop     dword ptr [rax+rax+00h]
0x1800797b3  mov     edi, eax
0x1800797b5  test    eax, eax
0x1800797b7  jns     loc_18007984D
0x1800797bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800797c4  test    rcx, rcx
0x1800797c7  jnz     short loc_180079810
0x1800797c9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800797d0  nop     dword ptr [rax+rax+00h]
0x1800797d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800797dc  mov     rcx, rax
0x1800797df  test    rax, rax
0x1800797e2  jz      short loc_180079802
0x1800797e4  mov     rax, [rax]
0x1800797e7  mov     edx, 7F0h
0x1800797ec  mov     rax, [rax+8]
0x1800797f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797f5  test    eax, eax
0x1800797f7  jz      short loc_180079802
0x1800797f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079800  jmp     short loc_180079810
0x180079802  lea     rcx, qword_1800DBF70; this
0x180079809  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180079810  cmp     [rcx+8], bl
0x180079813  jz      short loc_180079836
0x180079815  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007981a  cmp     [rax+7CCh], edi
0x180079820  jz      short loc_180079836
0x180079822  mov     r9d, edi; int
0x180079825  mov     r8d, 367h; int
0x18007982b  mov     rdx, r15; char *
0x18007982e  mov     rcx, rax; this
0x180079831  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079836  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007983d  jb      loc_180079A22
0x180079843  mov     edx, 70h ; 'p'
0x180079848  jmp     loc_18007975B
0x18007984d  cmp     [rbp+result], ebx
0x180079850  jnz     short loc_18007985C
0x180079852  mov     ebx, 2
0x180079857  jmp     loc_180079A22
0x18007985c  lea     rdx, aArm; "arm"
0x180079863  lea     rcx, [rbp+string]; string
0x180079867  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x18007986c  lea     r8, [rbp+result]; result
0x180079870  mov     rcx, rsi; string1
0x180079873  mov     rdx, [rax]; string2
0x180079876  call    cs:__imp_WindowsCompareStringOrdinal
0x18007987d  nop     dword ptr [rax+rax+00h]
0x180079882  mov     edi, eax
0x180079884  test    eax, eax
0x180079886  jns     loc_18007991C
0x18007988c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079893  test    rcx, rcx
0x180079896  jnz     short loc_1800798DF
0x180079898  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007989f  nop     dword ptr [rax+rax+00h]
0x1800798a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798ab  mov     rcx, rax
0x1800798ae  test    rax, rax
0x1800798b1  jz      short loc_1800798D1
0x1800798b3  mov     rax, [rax]
0x1800798b6  mov     edx, 7F0h
0x1800798bb  mov     rax, [rax+8]
0x1800798bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800798c4  test    eax, eax
0x1800798c6  jz      short loc_1800798D1
0x1800798c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798cf  jmp     short loc_1800798DF
0x1800798d1  lea     rcx, qword_1800DBF70; this
0x1800798d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800798df  cmp     [rcx+8], bl
0x1800798e2  jz      short loc_180079905
0x1800798e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800798e9  cmp     [rax+7CCh], edi
0x1800798ef  jz      short loc_180079905
0x1800798f1  mov     r9d, edi; int
0x1800798f4  mov     r8d, 36Eh; int
0x1800798fa  mov     rdx, r15; char *
0x1800798fd  mov     rcx, rax; this
0x180079900  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079905  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007990c  jb      loc_180079A22
0x180079912  mov     edx, 71h ; 'q'
0x180079917  jmp     loc_18007975B
0x18007991c  cmp     [rbp+result], ebx
0x18007991f  jnz     short loc_18007992B
0x180079921  mov     ebx, 3
0x180079926  jmp     loc_180079A22
0x18007992b  lea     r9, [rbp+string]; string
0x18007992f  mov     edx, 5; length
0x180079934  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180079938  lea     rcx, aArm64; "arm64"
0x18007993f  call    cs:__imp_WindowsCreateStringReference
0x180079946  nop     dword ptr [rax+rax+00h]
0x18007994b  test    eax, eax
0x18007994d  jns     short loc_18007996A
0x18007994f  xor     r9d, r9d; lpArguments
0x180079952  xor     r8d, r8d; nNumberOfArguments
0x180079955  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007995a  lea     edx, [r9+1]; dwExceptionFlags
0x18007995e  call    cs:__imp_RaiseException
0x180079965  nop     dword ptr [rax+rax+00h]
0x18007996a  mov     rdx, [rbp+string]; string2
0x18007996e  lea     r8, [rbp+result]; result
0x180079972  mov     rcx, rsi; string1
0x180079975  call    cs:__imp_WindowsCompareStringOrdinal
0x18007997c  nop     dword ptr [rax+rax+00h]
0x180079981  mov     edi, eax
0x180079983  test    eax, eax
0x180079985  jns     loc_180079A17
0x18007998b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180079992  test    rcx, rcx
0x180079995  jnz     short loc_1800799DE
0x180079997  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007999e  nop     dword ptr [rax+rax+00h]
0x1800799a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800799aa  mov     rcx, rax
0x1800799ad  test    rax, rax
0x1800799b0  jz      short loc_1800799D0
0x1800799b2  mov     rax, [rax]
0x1800799b5  mov     edx, 7F0h
0x1800799ba  mov     rax, [rax+8]
0x1800799be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799c3  test    eax, eax
0x1800799c5  jz      short loc_1800799D0
0x1800799c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800799ce  jmp     short loc_1800799DE
0x1800799d0  lea     rcx, qword_1800DBF70; this
0x1800799d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800799de  cmp     [rcx+8], bl
0x1800799e1  jz      short loc_180079A04
0x1800799e3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800799e8  cmp     [rax+7CCh], edi
0x1800799ee  jz      short loc_180079A04
0x1800799f0  mov     r9d, edi; int
0x1800799f3  mov     r8d, 375h; int
0x1800799f9  mov     rdx, r15; char *
0x1800799fc  mov     rcx, rax; this
0x1800799ff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180079a04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180079a0b  jb      short loc_180079A22
0x180079a0d  mov     edx, 72h ; 'r'
0x180079a12  jmp     loc_18007975B
0x180079a17  cmp     [rbp+result], ebx
0x180079a1a  mov     eax, 4
0x180079a1f  cmovz   ebx, eax
0x180079a22  lea     rcx, [rbp+var_2C]; this
0x180079a26  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180079a2b  mov     eax, ebx
0x180079a2d  mov     rcx, [rbp+var_8]
0x180079a31  xor     rcx, rsp; StackCookie
0x180079a34  call    __security_check_cookie
0x180079a39  lea     r11, [rsp+60h+var_s0]
0x180079a3e  mov     rbx, [r11+28h]
0x180079a42  mov     rsi, [r11+30h]
0x180079a46  mov     rsp, r11
0x180079a49  pop     r15
0x180079a4b  pop     rdi
0x180079a4c  pop     rbp
0x180079a4d  retn
```
