# CreateExtensionArchitectureFromString(HSTRING__ *)

- ea: `0x180094910`
- end: `0x180094cb0`
- name: `?CreateExtensionArchitectureFromString@@YA?AW4MediaExtensionArchitecture@@PEAUHSTRING__@@@Z`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800aa7b0`
- `0x1801929f4`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x180094910`
- `0x18009ac1c`
- `0x1801200d0`
- `0x180187a6c`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009497e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009497e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18009498f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18009498f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180094be6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180094966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180094966`

## string_xrefs

- `0x180094936`: `CreateExtensionArchitectureFromString`

## pseudocode

```c
__int64 __fastcall CreateExtensionArchitectureFromString(HSTRING a1)
{
  unsigned int v2; // ebx
  HRESULT v3; // edi
  CallStackTracing *v4; // rcx
  struct CallStackContext *v5; // rax
  __int64 v6; // rdx
  HSTRING *v7; // rax
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  HSTRING *v10; // rax
  const unsigned __int16 *v11; // rdx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  HSTRING *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  INT32 result; // [rsp+30h] [rbp-30h] BYREF
  CallStackScopeTrace v19; // [rsp+34h] [rbp-2Ch] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  result = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v19, "CreateExtensionArchitectureFromString", 864);
  if ( WindowsCreateStringReference(L"x86", 3u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = WindowsCompareStringOrdinal(a1, string, &result);
  if ( v3 >= 0 )
  {
    if ( !result )
    {
      v2 = 1;
      goto LABEL_52;
    }
    v7 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"x64");
    v3 = WindowsCompareStringOrdinal(a1, *v7, &result);
    if ( v3 >= 0 )
    {
      if ( !result )
      {
        v2 = 2;
        goto LABEL_52;
      }
      v10 = (HSTRING *)Windows::Internal::StringReference::StringReference(&string, L"arm");
      v3 = WindowsCompareStringOrdinal(a1, *v10, &result);
      if ( v3 >= 0 )
      {
        if ( !result )
        {
          v2 = 3;
          goto LABEL_52;
        }
        v14 = (HSTRING *)Windows::Internal::StringReference::StringReference(
                           &string,
                           (const unsigned __int16 (*)[6])v11);
        v3 = WindowsCompareStringOrdinal(a1, *v14, &result);
        if ( v3 >= 0 )
        {
          if ( !result )
            v2 = 4;
        }
        else
        {
          v15 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v15 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v15 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v15->m_fEnabled )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
            if ( ThreadRelativeContext->m_result != v3 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CreateExtensionArchitectureFromString", 885, v3);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v6 = 114;
            goto LABEL_13;
          }
        }
      }
      else
      {
        v12 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v12 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v12->m_fEnabled )
        {
          v13 = CallStackTracing::GetThreadRelativeContext(v12);
          if ( v13->m_result != v3 )
            CallStackContext::TraceFailure(v13, "CreateExtensionArchitectureFromString", 878, v3);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v6 = 113;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v8 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v8->m_fEnabled )
      {
        v9 = CallStackTracing::GetThreadRelativeContext(v8);
        if ( v9->m_result != v3 )
          CallStackContext::TraceFailure(v9, "CreateExtensionArchitectureFromString", 871, v3);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v6 = 112;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v4 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v4 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v4->m_fEnabled )
    {
      v5 = CallStackTracing::GetThreadRelativeContext(v4);
      if ( v5->m_result != v3 )
        CallStackContext::TraceFailure(v5, "CreateExtensionArchitectureFromString", 864, v3);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v6 = 111;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v3);
    }
  }
LABEL_52:
  CallStackScopeTrace::~CallStackScopeTrace(&v19);
  return v2;
}

```

## disassembly

```asm
0x180094910  mov     [rsp-18h+arg_8], rbx
0x180094915  mov     [rsp-18h+arg_10], rsi
0x18009491a  push    rbp
0x18009491b  push    rdi
0x18009491c  push    r12
0x18009491e  mov     rbp, rsp
0x180094921  sub     rsp, 60h
0x180094925  mov     rax, cs:__security_cookie
0x18009492c  xor     rax, rsp
0x18009492f  mov     [rbp+var_8], rax
0x180094933  mov     rsi, rcx
0x180094936  lea     r12, aCreateextensio; "CreateExtensionArchitectureFromString"
0x18009493d  xor     ebx, ebx
0x18009493f  lea     rcx, [rbp+var_2C]; this
0x180094943  mov     rdx, r12; char *
0x180094946  mov     [rbp+result], ebx
0x180094949  mov     r8d, 360h; int
0x18009494f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180094954  lea     r9, [rbp+string]; string
0x180094958  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009495c  lea     edx, [rbx+3]; length
0x18009495f  lea     rcx, aX86; "x86"
0x180094966  call    cs:__imp_WindowsCreateStringReference
0x18009496c  test    eax, eax
0x18009496e  jns     short loc_180094984
0x180094970  xor     r9d, r9d; lpArguments
0x180094973  lea     edx, [rbx+1]; dwExceptionFlags
0x180094976  xor     r8d, r8d; nNumberOfArguments
0x180094979  mov     ecx, 0C000000Dh; dwExceptionCode
0x18009497e  call    cs:__imp_RaiseException
0x180094984  mov     rdx, [rbp+string]; string2
0x180094988  lea     r8, [rbp+result]; result
0x18009498c  mov     rcx, rsi; string1
0x18009498f  call    cs:__imp_WindowsCompareStringOrdinal
0x180094995  mov     edi, eax
0x180094997  test    eax, eax
0x180094999  jns     loc_180094A44
0x18009499f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800949a6  test    rcx, rcx
0x1800949a9  jnz     short loc_1800949E9
0x1800949ab  mov     rax, cs:stru_1801FC290.__vftable
0x1800949b2  lea     rcx, stru_1801FC290
0x1800949b9  mov     edx, 7F0h
0x1800949be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800949c5  mov     rax, [rax+8]
0x1800949c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800949ce  test    eax, eax
0x1800949d0  jnz     short loc_1800949E2
0x1800949d2  lea     rcx, stru_1801F8A30
0x1800949d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800949e0  jmp     short loc_1800949E9
0x1800949e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800949e9  cmp     [rcx+8], bl
0x1800949ec  jz      short loc_180094A0F
0x1800949ee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800949f3  cmp     [rax+7CCh], edi
0x1800949f9  jz      short loc_180094A0F
0x1800949fb  mov     r9d, edi; int
0x1800949fe  mov     r8d, 360h; int
0x180094a04  mov     rdx, r12; char *
0x180094a07  mov     rcx, rax; this
0x180094a0a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094a0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094a16  jb      loc_180094C84
0x180094a1c  mov     edx, 6Fh ; 'o'
0x180094a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180094a28  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180094a2f  xor     r9d, r9d
0x180094a32  mov     [rsp+60h+var_40], edi
0x180094a36  mov     rcx, [rcx+10h]
0x180094a3a  call    WPP_SF_qD
0x180094a3f  jmp     loc_180094C84
0x180094a44  cmp     [rbp+result], ebx
0x180094a47  jnz     short loc_180094A53
0x180094a49  mov     ebx, 1
0x180094a4e  jmp     loc_180094C84
0x180094a53  lea     rdx, aX64; "x64"
0x180094a5a  lea     rcx, [rbp+string]; string
0x180094a5e  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x180094a63  lea     r8, [rbp+result]; result
0x180094a67  mov     rcx, rsi; string1
0x180094a6a  mov     rdx, [rax]; string2
0x180094a6d  call    cs:__imp_WindowsCompareStringOrdinal
0x180094a73  mov     edi, eax
0x180094a75  test    eax, eax
0x180094a77  jns     loc_180094B04
0x180094a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094a84  test    rcx, rcx
0x180094a87  jnz     short loc_180094AC7
0x180094a89  mov     rax, cs:stru_1801FC290.__vftable
0x180094a90  lea     rcx, stru_1801FC290
0x180094a97  mov     edx, 7F0h
0x180094a9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094aa3  mov     rax, [rax+8]
0x180094aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094aac  test    eax, eax
0x180094aae  jnz     short loc_180094AC0
0x180094ab0  lea     rcx, stru_1801F8A30
0x180094ab7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094abe  jmp     short loc_180094AC7
0x180094ac0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180094ac7  cmp     [rcx+8], bl
0x180094aca  jz      short loc_180094AED
0x180094acc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094ad1  cmp     [rax+7CCh], edi
0x180094ad7  jz      short loc_180094AED
0x180094ad9  mov     r9d, edi; int
0x180094adc  mov     r8d, 367h; int
0x180094ae2  mov     rdx, r12; char *
0x180094ae5  mov     rcx, rax; this
0x180094ae8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094aed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094af4  jb      loc_180094C84
0x180094afa  mov     edx, 70h ; 'p'
0x180094aff  jmp     loc_180094A21
0x180094b04  cmp     [rbp+result], ebx
0x180094b07  jnz     short loc_180094B13
0x180094b09  mov     ebx, 2
0x180094b0e  jmp     loc_180094C84
0x180094b13  lea     rdx, aArm; "arm"
0x180094b1a  lea     rcx, [rbp+string]; string
0x180094b1e  call    ??$?0$03@StringReference@Internal@Windows@@QEAA@AEAY03$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[4])
0x180094b23  lea     r8, [rbp+result]; result
0x180094b27  mov     rcx, rsi; string1
0x180094b2a  mov     rdx, [rax]; string2
0x180094b2d  call    cs:__imp_WindowsCompareStringOrdinal
0x180094b33  mov     edi, eax
0x180094b35  test    eax, eax
0x180094b37  jns     loc_180094BC4
0x180094b3d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094b44  test    rcx, rcx
0x180094b47  jnz     short loc_180094B87
0x180094b49  mov     rax, cs:stru_1801FC290.__vftable
0x180094b50  lea     rcx, stru_1801FC290
0x180094b57  mov     edx, 7F0h
0x180094b5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094b63  mov     rax, [rax+8]
0x180094b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094b6c  test    eax, eax
0x180094b6e  jnz     short loc_180094B80
0x180094b70  lea     rcx, stru_1801F8A30
0x180094b77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094b7e  jmp     short loc_180094B87
0x180094b80  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180094b87  cmp     [rcx+8], bl
0x180094b8a  jz      short loc_180094BAD
0x180094b8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094b91  cmp     [rax+7CCh], edi
0x180094b97  jz      short loc_180094BAD
0x180094b99  mov     r9d, edi; int
0x180094b9c  mov     r8d, 36Eh; int
0x180094ba2  mov     rdx, r12; char *
0x180094ba5  mov     rcx, rax; this
0x180094ba8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094bad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094bb4  jb      loc_180094C84
0x180094bba  mov     edx, 71h ; 'q'
0x180094bbf  jmp     loc_180094A21
0x180094bc4  cmp     [rbp+result], ebx
0x180094bc7  jnz     short loc_180094BD3
0x180094bc9  mov     ebx, 3
0x180094bce  jmp     loc_180094C84
0x180094bd3  lea     rcx, [rbp+string]; string
0x180094bd7  call    ??$?0$05@StringReference@Internal@Windows@@QEAA@AEAY05$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[6])
0x180094bdc  lea     r8, [rbp+result]; result
0x180094be0  mov     rcx, rsi; string1
0x180094be3  mov     rdx, [rax]; string2
0x180094be6  call    cs:__imp_WindowsCompareStringOrdinal
0x180094bec  mov     edi, eax
0x180094bee  test    eax, eax
0x180094bf0  jns     loc_180094C79
0x180094bf6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094bfd  test    rcx, rcx
0x180094c00  jnz     short loc_180094C40
0x180094c02  mov     rax, cs:stru_1801FC290.__vftable
0x180094c09  lea     rcx, stru_1801FC290
0x180094c10  mov     edx, 7F0h
0x180094c15  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094c1c  mov     rax, [rax+8]
0x180094c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c25  test    eax, eax
0x180094c27  jnz     short loc_180094C39
0x180094c29  lea     rcx, stru_1801F8A30
0x180094c30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094c37  jmp     short loc_180094C40
0x180094c39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180094c40  cmp     [rcx+8], bl
0x180094c43  jz      short loc_180094C66
0x180094c45  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094c4a  cmp     [rax+7CCh], edi
0x180094c50  jz      short loc_180094C66
0x180094c52  mov     r9d, edi; int
0x180094c55  mov     r8d, 375h; int
0x180094c5b  mov     rdx, r12; char *
0x180094c5e  mov     rcx, rax; this
0x180094c61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094c66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180094c6d  jb      short loc_180094C84
0x180094c6f  mov     edx, 72h ; 'r'
0x180094c74  jmp     loc_180094A21
0x180094c79  cmp     [rbp+result], ebx
0x180094c7c  mov     eax, 4
0x180094c81  cmovz   ebx, eax
0x180094c84  lea     rcx, [rbp+var_2C]; this
0x180094c88  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180094c8d  mov     eax, ebx
0x180094c8f  mov     rcx, [rbp+var_8]
0x180094c93  xor     rcx, rsp; StackCookie
0x180094c96  call    __security_check_cookie
0x180094c9b  lea     r11, [rsp+60h+var_s0]
0x180094ca0  mov     rbx, [r11+28h]
0x180094ca4  mov     rsi, [r11+30h]
0x180094ca8  mov     rsp, r11
0x180094cab  pop     r12
0x180094cad  pop     rdi
0x180094cae  pop     rbp
0x180094caf  retn
```
