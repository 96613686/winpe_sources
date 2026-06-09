# CreateCodecCategoryFromString(HSTRING__ *,_GUID *)

- ea: `0x1800802e0`
- end: `0x1800807ef`
- name: `?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `1295`
- prototype: `__int64 __fastcall(HSTRING string1, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800a9620`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x1800802e0`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180080799`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180080799`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800807e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008035a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800803d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008041f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180080466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008035a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800803d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18008041f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180080466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008033b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800803ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180080406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008044d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008033b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800803ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180080406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008044d`

## string_xrefs

- `0x18008030e`: `CreateCodecCategoryFromString`

## pseudocode

```c
__int64 __fastcall CreateCodecCategoryFromString(HSTRING string1, struct _GUID *a2)
{
  HRESULT v4; // ebx
  GUID v5; // xmm0
  CallStackTracing *v7; // rcx
  __int64 v8; // rdx
  CallStackTracing *v9; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  struct CallStackContext *v17; // rax
  INT32 result; // [rsp+30h] [rbp-30h] BYREF
  CallStackScopeTrace v19; // [rsp+34h] [rbp-2Ch] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  result = 0;
  CallStackScopeTrace::CallStackScopeTrace(&v19, "CreateCodecCategoryFromString", 802);
  if ( WindowsCreateStringReference(L"audioDecoder", 0xCu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = WindowsCompareStringOrdinal(string1, string, &result);
  if ( v4 < 0 )
  {
    v9 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v9 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v9->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
      if ( ThreadRelativeContext->m_result != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateCodecCategoryFromString", 802, v4);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v8 = 106;
      goto LABEL_25;
    }
  }
  else
  {
    if ( !result )
    {
      v5 = MFT_CATEGORY_AUDIO_DECODER;
LABEL_6:
      *a2 = v5;
      goto LABEL_7;
    }
    if ( WindowsCreateStringReference(L"videoDecoder", 0xCu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = WindowsCompareStringOrdinal(string1, string, &result);
    if ( v4 < 0 )
    {
      v11 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v11 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v11->m_fEnabled )
      {
        v12 = CallStackTracing::GetThreadRelativeContext(v11);
        if ( v12->m_result != v4 )
          CallStackContext::TraceFailure(v12, "CreateCodecCategoryFromString", 808, v4);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v8 = 107;
        goto LABEL_25;
      }
    }
    else
    {
      if ( !result )
      {
        v5 = MFT_CATEGORY_VIDEO_DECODER;
        goto LABEL_6;
      }
      if ( WindowsCreateStringReference(L"audioEncoder", 0xCu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v4 = WindowsCompareStringOrdinal(string1, string, &result);
      if ( v4 < 0 )
      {
        v13 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::s_wpInstance = &stru_1801FC290;
          if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          {
            v13 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &stru_1801F8A30;
            CallStackTracing::s_wpInstance = &stru_1801F8A30;
          }
        }
        if ( v13->m_fEnabled )
        {
          v14 = CallStackTracing::GetThreadRelativeContext(v13);
          if ( v14->m_result != v4 )
            CallStackContext::TraceFailure(v14, "CreateCodecCategoryFromString", 814, v4);
        }
        if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
        {
          v8 = 108;
          goto LABEL_25;
        }
      }
      else
      {
        if ( !result )
        {
          v5 = MFT_CATEGORY_AUDIO_ENCODER;
          goto LABEL_6;
        }
        if ( WindowsCreateStringReference(L"videoEncoder", 0xCu, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v4 = WindowsCompareStringOrdinal(string1, string, &result);
        if ( v4 < 0 )
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
            v16 = CallStackTracing::GetThreadRelativeContext(v15);
            if ( v16->m_result != v4 )
              CallStackContext::TraceFailure(v16, "CreateCodecCategoryFromString", 820, v4);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v8 = 109;
            goto LABEL_25;
          }
        }
        else
        {
          if ( !result )
          {
            v5 = MFT_CATEGORY_VIDEO_ENCODER;
            goto LABEL_6;
          }
          v7 = CallStackTracing::s_wpInstance;
          v4 = -1072875845;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::s_wpInstance = &stru_1801FC290;
            if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
            {
              v7 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v7 = &stru_1801F8A30;
              CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
          }
          if ( v7->m_fEnabled )
          {
            v17 = CallStackTracing::GetThreadRelativeContext(v7);
            if ( v17->m_result != -1072875845 )
              CallStackContext::TraceFailure(v17, "CreateCodecCategoryFromString", 827, -1072875845);
          }
          if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
          {
            v8 = 110;
LABEL_25:
            WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v4);
          }
        }
      }
    }
  }
LABEL_7:
  CallStackScopeTrace::~CallStackScopeTrace(&v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800802e0  mov     [rsp-28h+arg_10], rbx
0x1800802e5  push    rbp
0x1800802e6  push    rsi
0x1800802e7  push    rdi
0x1800802e8  push    r13
0x1800802ea  push    r15
0x1800802ec  mov     rbp, rsp
0x1800802ef  sub     rsp, 60h
0x1800802f3  mov     rax, cs:__security_cookie
0x1800802fa  xor     rax, rsp
0x1800802fd  mov     [rbp+var_8], rax
0x180080301  mov     rdi, rdx
0x180080304  mov     [rbp+result], 0
0x18008030b  mov     rsi, rcx
0x18008030e  lea     r13, aCreatecodeccat; "CreateCodecCategoryFromString"
0x180080315  mov     rdx, r13; char *
0x180080318  lea     rcx, [rbp+var_2C]; this
0x18008031c  mov     r8d, 322h; int
0x180080322  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180080327  lea     r9, [rbp+string]; string
0x18008032b  mov     edx, 0Ch; length
0x180080330  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180080334  lea     rcx, aAudiodecoder; "audioDecoder"
0x18008033b  call    cs:__imp_WindowsCreateStringReference
0x180080341  mov     r15d, 1
0x180080347  test    eax, eax
0x180080349  js      loc_18008078B
0x18008034f  mov     rdx, [rbp+string]; string2
0x180080353  lea     r8, [rbp+result]; result
0x180080357  mov     rcx, rsi; string1
0x18008035a  call    cs:__imp_WindowsCompareStringOrdinal
0x180080360  mov     ebx, eax
0x180080362  test    eax, eax
0x180080364  js      loc_18008052D
0x18008036a  cmp     [rbp+result], 0
0x18008036e  jnz     short loc_1800803A6
0x180080370  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180080377  movdqu  xmmword ptr [rdi], xmm0
0x18008037b  lea     rcx, [rbp+var_2C]; this
0x18008037f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180080384  mov     eax, ebx
0x180080386  mov     rcx, [rbp+var_8]
0x18008038a  xor     rcx, rsp; StackCookie
0x18008038d  call    __security_check_cookie
0x180080392  mov     rbx, [rsp+60h+arg_10]
0x18008039a  add     rsp, 60h
0x18008039e  pop     r15
0x1800803a0  pop     r13
0x1800803a2  pop     rdi
0x1800803a3  pop     rsi
0x1800803a4  pop     rbp
0x1800803a5  retn
0x1800803a6  lea     r9, [rbp+string]; string
0x1800803aa  mov     edx, 0Ch; length
0x1800803af  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800803b3  lea     rcx, aVideodecoder; "videoDecoder"
0x1800803ba  call    cs:__imp_WindowsCreateStringReference
0x1800803c0  test    eax, eax
0x1800803c2  js      loc_1800807A4
0x1800803c8  mov     rdx, [rbp+string]; string2
0x1800803cc  lea     r8, [rbp+result]; result
0x1800803d0  mov     rcx, rsi; string1
0x1800803d3  call    cs:__imp_WindowsCompareStringOrdinal
0x1800803d9  mov     ebx, eax
0x1800803db  test    eax, eax
0x1800803dd  js      loc_1800805BA
0x1800803e3  cmp     [rbp+result], 0
0x1800803e7  jnz     short loc_1800803F2
0x1800803e9  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x1800803f0  jmp     short loc_180080377
0x1800803f2  lea     r9, [rbp+string]; string
0x1800803f6  mov     edx, 0Ch; length
0x1800803fb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800803ff  lea     rcx, aAudioencoder; "audioEncoder"
0x180080406  call    cs:__imp_WindowsCreateStringReference
0x18008040c  test    eax, eax
0x18008040e  js      loc_1800807BD
0x180080414  mov     rdx, [rbp+string]; string2
0x180080418  lea     r8, [rbp+result]; result
0x18008041c  mov     rcx, rsi; string1
0x18008041f  call    cs:__imp_WindowsCompareStringOrdinal
0x180080425  mov     ebx, eax
0x180080427  test    eax, eax
0x180080429  js      loc_180080647
0x18008042f  cmp     [rbp+result], 0
0x180080433  jz      loc_1800804CC
0x180080439  lea     r9, [rbp+string]; string
0x18008043d  mov     edx, 0Ch; length
0x180080442  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180080446  lea     rcx, aVideoencoder; "videoEncoder"
0x18008044d  call    cs:__imp_WindowsCreateStringReference
0x180080453  test    eax, eax
0x180080455  js      loc_1800807D6
0x18008045b  mov     rdx, [rbp+string]; string2
0x18008045f  lea     r8, [rbp+result]; result
0x180080463  mov     rcx, rsi; string1
0x180080466  call    cs:__imp_WindowsCompareStringOrdinal
0x18008046c  mov     ebx, eax
0x18008046e  test    eax, eax
0x180080470  js      loc_1800806D4
0x180080476  cmp     [rbp+result], 0
0x18008047a  jz      short loc_1800804D8
0x18008047c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180080483  mov     ebx, 0C00D36BBh
0x180080488  test    rcx, rcx
0x18008048b  jz      short loc_1800804E4
0x18008048d  cmp     byte ptr [rcx+8], 0
0x180080491  jnz     loc_180080761
0x180080497  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18008049e  jb      loc_18008037B
0x1800804a4  mov     edx, 6Eh ; 'n'
0x1800804a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800804b0  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x1800804b7  xor     r9d, r9d
0x1800804ba  mov     [rsp+60h+var_40], ebx
0x1800804be  mov     rcx, [rcx+10h]
0x1800804c2  call    WPP_SF_qD
0x1800804c7  jmp     loc_18008037B
0x1800804cc  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x1800804d3  jmp     loc_180080377
0x1800804d8  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800804df  jmp     loc_180080377
0x1800804e4  mov     rax, cs:stru_1801FC290.__vftable
0x1800804eb  lea     r8, stru_1801FC290
0x1800804f2  mov     edx, 7F0h
0x1800804f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800804fe  mov     rcx, r8
0x180080501  mov     rax, [rax+8]
0x180080505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008050a  test    eax, eax
0x18008050c  jnz     short loc_180080521
0x18008050e  lea     rcx, stru_1801F8A30
0x180080515  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008051c  jmp     loc_18008048D
0x180080521  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080528  jmp     loc_18008048D
0x18008052d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080534  test    rcx, rcx
0x180080537  jnz     short loc_180080571
0x180080539  mov     rcx, cs:stru_1801FC290.__vftable
0x180080540  lea     r8, stru_1801FC290
0x180080547  mov     edx, 7F0h
0x18008054c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x180080553  mov     rax, [rcx+8]
0x180080557  mov     rcx, r8
0x18008055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008055f  test    eax, eax
0x180080561  jnz     short loc_18008058E
0x180080563  lea     rcx, stru_1801F8A30; this
0x18008056a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180080571  cmp     byte ptr [rcx+8], 0
0x180080575  jnz     short loc_180080597
0x180080577  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18008057e  jb      loc_18008037B
0x180080584  mov     edx, 6Ah ; 'j'
0x180080589  jmp     loc_1800804A9
0x18008058e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080595  jmp     short loc_180080571
0x180080597  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008059c  cmp     [rax+7CCh], ebx
0x1800805a2  jz      short loc_180080577
0x1800805a4  mov     r9d, ebx; int
0x1800805a7  mov     r8d, 322h; int
0x1800805ad  mov     rdx, r13; char *
0x1800805b0  mov     rcx, rax; this
0x1800805b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800805b8  jmp     short loc_180080577
0x1800805ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800805c1  test    rcx, rcx
0x1800805c4  jnz     short loc_1800805FE
0x1800805c6  mov     rax, cs:stru_1801FC290.__vftable
0x1800805cd  lea     r8, stru_1801FC290
0x1800805d4  mov     edx, 7F0h
0x1800805d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800805e0  mov     rcx, r8
0x1800805e3  mov     rax, [rax+8]
0x1800805e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800805ec  test    eax, eax
0x1800805ee  jnz     short loc_18008061B
0x1800805f0  lea     rcx, stru_1801F8A30; this
0x1800805f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800805fe  cmp     byte ptr [rcx+8], 0
0x180080602  jnz     short loc_180080624
0x180080604  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18008060b  jb      loc_18008037B
0x180080611  mov     edx, 6Bh ; 'k'
0x180080616  jmp     loc_1800804A9
0x18008061b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180080622  jmp     short loc_1800805FE
0x180080624  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080629  cmp     [rax+7CCh], ebx
0x18008062f  jz      short loc_180080604
0x180080631  mov     r9d, ebx; int
0x180080634  mov     r8d, 328h; int
0x18008063a  mov     rdx, r13; char *
0x18008063d  mov     rcx, rax; this
0x180080640  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180080645  jmp     short loc_180080604
0x180080647  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008064e  test    rcx, rcx
0x180080651  jnz     short loc_18008068B
0x180080653  mov     rax, cs:stru_1801FC290.__vftable
0x18008065a  lea     r8, stru_1801FC290
0x180080661  mov     edx, 7F0h
0x180080666  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x18008066d  mov     rcx, r8
0x180080670  mov     rax, [rax+8]
0x180080674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080679  test    eax, eax
0x18008067b  jnz     short loc_1800806A8
0x18008067d  lea     rcx, stru_1801F8A30; this
0x180080684  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008068b  cmp     byte ptr [rcx+8], 0
0x18008068f  jnz     short loc_1800806B1
0x180080691  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180080698  jb      loc_18008037B
0x18008069e  mov     edx, 6Ch ; 'l'
0x1800806a3  jmp     loc_1800804A9
0x1800806a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800806af  jmp     short loc_18008068B
0x1800806b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800806b6  cmp     [rax+7CCh], ebx
0x1800806bc  jz      short loc_180080691
0x1800806be  mov     r9d, ebx; int
0x1800806c1  mov     r8d, 32Eh; int
0x1800806c7  mov     rdx, r13; char *
0x1800806ca  mov     rcx, rax; this
0x1800806cd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800806d2  jmp     short loc_180080691
0x1800806d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800806db  test    rcx, rcx
0x1800806de  jnz     short loc_180080718
0x1800806e0  mov     rax, cs:stru_1801FC290.__vftable
0x1800806e7  lea     r8, stru_1801FC290
0x1800806ee  mov     edx, 7F0h
0x1800806f3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r8; CallStackTracing * CallStackTracing::s_wpInstance
0x1800806fa  mov     rcx, r8
0x1800806fd  mov     rax, [rax+8]
0x180080701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080706  test    eax, eax
0x180080708  jnz     short loc_180080735
0x18008070a  lea     rcx, stru_1801F8A30; this
0x180080711  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180080718  cmp     byte ptr [rcx+8], 0
0x18008071c  jnz     short loc_18008073E
0x18008071e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180080725  jb      loc_18008037B
0x18008072b  mov     edx, 6Dh ; 'm'
0x180080730  jmp     loc_1800804A9
0x180080735  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008073c  jmp     short loc_180080718
0x18008073e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080743  cmp     [rax+7CCh], ebx
0x180080749  jz      short loc_18008071E
0x18008074b  mov     r9d, ebx; int
0x18008074e  mov     r8d, 334h; int
0x180080754  mov     rdx, r13; char *
0x180080757  mov     rcx, rax; this
0x18008075a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008075f  jmp     short loc_18008071E
0x180080761  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180080766  cmp     [rax+7CCh], ebx
0x18008076c  jz      loc_180080497
0x180080772  mov     r9d, ebx; int
0x180080775  mov     r8d, 33Bh; int
0x18008077b  mov     rdx, r13; char *
0x18008077e  mov     rcx, rax; this
0x180080781  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180080786  jmp     loc_180080497
0x18008078b  xor     r9d, r9d; lpArguments
0x18008078e  xor     r8d, r8d; nNumberOfArguments
0x180080791  mov     edx, r15d; dwExceptionFlags
0x180080794  mov     ecx, 0C000000Dh; dwExceptionCode
0x180080799  call    cs:__imp_RaiseException
0x18008079f  jmp     loc_18008034F
0x1800807a4  xor     r9d, r9d; lpArguments
0x1800807a7  xor     r8d, r8d; nNumberOfArguments
0x1800807aa  mov     edx, r15d; dwExceptionFlags
0x1800807ad  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800807b2  call    cs:__imp_RaiseException
0x1800807b8  jmp     loc_1800803C8
0x1800807bd  xor     r9d, r9d; lpArguments
0x1800807c0  xor     r8d, r8d; nNumberOfArguments
0x1800807c3  mov     edx, r15d; dwExceptionFlags
0x1800807c6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800807cb  call    cs:__imp_RaiseException
0x1800807d1  jmp     loc_180080414
0x1800807d6  xor     r9d, r9d; lpArguments
0x1800807d9  xor     r8d, r8d; nNumberOfArguments
0x1800807dc  mov     edx, r15d; dwExceptionFlags
0x1800807df  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800807e4  call    cs:__imp_RaiseException
0x1800807ea  jmp     loc_18008045B
```
