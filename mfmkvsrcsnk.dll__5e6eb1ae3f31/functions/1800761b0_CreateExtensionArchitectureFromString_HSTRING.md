# CreateExtensionArchitectureFromString(HSTRING__ *)

- ea: `0x1800761b0`
- end: `0x180076566`
- name: `?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180076bb0`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180074d6c`
- `0x1800761b0`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076488`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007620e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800762ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800763b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180076499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007620e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800762ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800763b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180076499`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007646f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007646f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007622a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007630b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800763ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800764b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007622a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007630b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800763ce`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800764b5`

## string_xrefs

- `0x1800761d6`: `CreateExtensionArchitectureFromString`

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
              v29 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x1800761b0  mov     [rsp-18h+arg_8], rbx
0x1800761b5  mov     [rsp-18h+arg_10], rsi
0x1800761ba  push    rbp
0x1800761bb  push    rdi
0x1800761bc  push    r15
0x1800761be  mov     rbp, rsp
0x1800761c1  sub     rsp, 60h
0x1800761c5  mov     rax, cs:__security_cookie
0x1800761cc  xor     rax, rsp
0x1800761cf  mov     [rbp+var_8], rax
0x1800761d3  mov     rsi, rcx
0x1800761d6  lea     r15, aCreateextensio; "CreateExtensionArchitectureFromString"
0x1800761dd  xor     ebx, ebx
0x1800761df  lea     rcx, [rbp+var_2C]; this
0x1800761e3  mov     rdx, r15; char *
0x1800761e6  mov     [rbp+result], ebx
0x1800761e9  mov     r8d, 360h; int
0x1800761ef  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800761f4  lea     rdx, aX86; "x86"
0x1800761fb  lea     rcx, [rbp+string]; string
0x1800761ff  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x180076204  lea     r8, [rbp+result]; result
0x180076208  mov     rcx, rsi; string1
0x18007620b  mov     rdx, [rax]; string2
0x18007620e  call    cs:__imp_WindowsCompareStringOrdinal
0x180076214  mov     edi, eax
0x180076216  test    eax, eax
0x180076218  jns     loc_1800762C6
0x18007621e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076225  test    rcx, rcx
0x180076228  jnz     short loc_18007626B
0x18007622a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076230  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076237  mov     rcx, rax
0x18007623a  test    rax, rax
0x18007623d  jz      short loc_18007625D
0x18007623f  mov     rax, [rax]
0x180076242  mov     edx, 7F0h
0x180076247  mov     rax, [rax+8]
0x18007624b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076250  test    eax, eax
0x180076252  jz      short loc_18007625D
0x180076254  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007625b  jmp     short loc_18007626B
0x18007625d  lea     rcx, qword_1800D6F70; this
0x180076264  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007626b  cmp     [rcx+8], bl
0x18007626e  jz      short loc_180076291
0x180076270  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076275  cmp     [rax+7CCh], edi
0x18007627b  jz      short loc_180076291
0x18007627d  mov     r9d, edi; int
0x180076280  mov     r8d, 360h; int
0x180076286  mov     rdx, r15; char *
0x180076289  mov     rcx, rax; this
0x18007628c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076291  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076298  jb      loc_18007653A
0x18007629e  mov     edx, 6Fh ; 'o'
0x1800762a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800762aa  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800762b1  xor     r9d, r9d
0x1800762b4  mov     [rsp+60h+var_40], edi
0x1800762b8  mov     rcx, [rcx+10h]
0x1800762bc  call    WPP_SF_qD
0x1800762c1  jmp     loc_18007653A
0x1800762c6  cmp     [rbp+result], ebx
0x1800762c9  jnz     short loc_1800762D5
0x1800762cb  mov     ebx, 1
0x1800762d0  jmp     loc_18007653A
0x1800762d5  lea     rdx, aX64; "x64"
0x1800762dc  lea     rcx, [rbp+string]; string
0x1800762e0  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800762e5  lea     r8, [rbp+result]; result
0x1800762e9  mov     rcx, rsi; string1
0x1800762ec  mov     rdx, [rax]; string2
0x1800762ef  call    cs:__imp_WindowsCompareStringOrdinal
0x1800762f5  mov     edi, eax
0x1800762f7  test    eax, eax
0x1800762f9  jns     loc_180076389
0x1800762ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180076306  test    rcx, rcx
0x180076309  jnz     short loc_18007634C
0x18007630b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180076311  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180076318  mov     rcx, rax
0x18007631b  test    rax, rax
0x18007631e  jz      short loc_18007633E
0x180076320  mov     rax, [rax]
0x180076323  mov     edx, 7F0h
0x180076328  mov     rax, [rax+8]
0x18007632c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076331  test    eax, eax
0x180076333  jz      short loc_18007633E
0x180076335  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007633c  jmp     short loc_18007634C
0x18007633e  lea     rcx, qword_1800D6F70; this
0x180076345  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007634c  cmp     [rcx+8], bl
0x18007634f  jz      short loc_180076372
0x180076351  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076356  cmp     [rax+7CCh], edi
0x18007635c  jz      short loc_180076372
0x18007635e  mov     r9d, edi; int
0x180076361  mov     r8d, 367h; int
0x180076367  mov     rdx, r15; char *
0x18007636a  mov     rcx, rax; this
0x18007636d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076372  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076379  jb      loc_18007653A
0x18007637f  mov     edx, 70h ; 'p'
0x180076384  jmp     loc_1800762A3
0x180076389  cmp     [rbp+result], ebx
0x18007638c  jnz     short loc_180076398
0x18007638e  mov     ebx, 2
0x180076393  jmp     loc_18007653A
0x180076398  lea     rdx, aArm; "arm"
0x18007639f  lea     rcx, [rbp+string]; string
0x1800763a3  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x1800763a8  lea     r8, [rbp+result]; result
0x1800763ac  mov     rcx, rsi; string1
0x1800763af  mov     rdx, [rax]; string2
0x1800763b2  call    cs:__imp_WindowsCompareStringOrdinal
0x1800763b8  mov     edi, eax
0x1800763ba  test    eax, eax
0x1800763bc  jns     loc_18007644C
0x1800763c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800763c9  test    rcx, rcx
0x1800763cc  jnz     short loc_18007640F
0x1800763ce  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800763d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800763db  mov     rcx, rax
0x1800763de  test    rax, rax
0x1800763e1  jz      short loc_180076401
0x1800763e3  mov     rax, [rax]
0x1800763e6  mov     edx, 7F0h
0x1800763eb  mov     rax, [rax+8]
0x1800763ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763f4  test    eax, eax
0x1800763f6  jz      short loc_180076401
0x1800763f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800763ff  jmp     short loc_18007640F
0x180076401  lea     rcx, qword_1800D6F70; this
0x180076408  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007640f  cmp     [rcx+8], bl
0x180076412  jz      short loc_180076435
0x180076414  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076419  cmp     [rax+7CCh], edi
0x18007641f  jz      short loc_180076435
0x180076421  mov     r9d, edi; int
0x180076424  mov     r8d, 36Eh; int
0x18007642a  mov     rdx, r15; char *
0x18007642d  mov     rcx, rax; this
0x180076430  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180076435  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007643c  jb      loc_18007653A
0x180076442  mov     edx, 71h ; 'q'
0x180076447  jmp     loc_1800762A3
0x18007644c  cmp     [rbp+result], ebx
0x18007644f  jnz     short loc_18007645B
0x180076451  mov     ebx, 3
0x180076456  jmp     loc_18007653A
0x18007645b  lea     r9, [rbp+string]; string
0x18007645f  mov     edx, 5; length
0x180076464  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180076468  lea     rcx, aArm64; "arm64"
0x18007646f  call    cs:__imp_WindowsCreateStringReference
0x180076475  test    eax, eax
0x180076477  jns     short loc_18007648E
0x180076479  xor     r9d, r9d; lpArguments
0x18007647c  xor     r8d, r8d; nNumberOfArguments
0x18007647f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180076484  lea     edx, [r9+1]; dwExceptionFlags
0x180076488  call    cs:__imp_RaiseException
0x18007648e  mov     rdx, [rbp+string]; string2
0x180076492  lea     r8, [rbp+result]; result
0x180076496  mov     rcx, rsi; string1
0x180076499  call    cs:__imp_WindowsCompareStringOrdinal
0x18007649f  mov     edi, eax
0x1800764a1  test    eax, eax
0x1800764a3  jns     loc_18007652F
0x1800764a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800764b0  test    rcx, rcx
0x1800764b3  jnz     short loc_1800764F6
0x1800764b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800764bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800764c2  mov     rcx, rax
0x1800764c5  test    rax, rax
0x1800764c8  jz      short loc_1800764E8
0x1800764ca  mov     rax, [rax]
0x1800764cd  mov     edx, 7F0h
0x1800764d2  mov     rax, [rax+8]
0x1800764d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800764db  test    eax, eax
0x1800764dd  jz      short loc_1800764E8
0x1800764df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800764e6  jmp     short loc_1800764F6
0x1800764e8  lea     rcx, qword_1800D6F70; this
0x1800764ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800764f6  cmp     [rcx+8], bl
0x1800764f9  jz      short loc_18007651C
0x1800764fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180076500  cmp     [rax+7CCh], edi
0x180076506  jz      short loc_18007651C
0x180076508  mov     r9d, edi; int
0x18007650b  mov     r8d, 375h; int
0x180076511  mov     rdx, r15; char *
0x180076514  mov     rcx, rax; this
0x180076517  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007651c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180076523  jb      short loc_18007653A
0x180076525  mov     edx, 72h ; 'r'
0x18007652a  jmp     loc_1800762A3
0x18007652f  cmp     [rbp+result], ebx
0x180076532  mov     eax, 4
0x180076537  cmovz   ebx, eax
0x18007653a  lea     rcx, [rbp+var_2C]; this
0x18007653e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180076543  mov     eax, ebx
0x180076545  mov     rcx, [rbp+var_8]
0x180076549  xor     rcx, rsp; StackCookie
0x18007654c  call    __security_check_cookie
0x180076551  lea     r11, [rsp+60h+var_s0]
0x180076556  mov     rbx, [r11+28h]
0x18007655a  mov     rsi, [r11+30h]
0x18007655e  mov     rsp, r11
0x180076561  pop     r15
0x180076563  pop     rdi
0x180076564  pop     rbp
0x180076565  retn
```
