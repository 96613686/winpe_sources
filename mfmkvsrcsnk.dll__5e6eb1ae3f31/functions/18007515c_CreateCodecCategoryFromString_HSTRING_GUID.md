# CreateCodecCategoryFromString(HSTRING__ *,_GUID *)

- ea: `0x18007515c`
- end: `0x180075596`
- name: `?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `1082`
- prototype: `__int64 __fastcall(HSTRING string1, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007559c`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180074db8`
- `0x18007515c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800751bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007528a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075418`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800751bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007528a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180075418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800751db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800752a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007536d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075434`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800754d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800751db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800752a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007536d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180075434`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800754d6`

## string_xrefs

- `0x18007518c`: `CreateCodecCategoryFromString`

## pseudocode

```c
__int64 __fastcall CreateCodecCategoryFromString(HSTRING string1, struct _GUID *a2)
{
  HSTRING *v4; // rax
  __int64 v5; // rdx
  HRESULT v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  GUID v13; // xmm0
  HSTRING *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  HSTRING *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  HSTRING *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  INT32 result; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v40[4]; // [rsp+34h] [rbp-2Ch] BYREF
  HSTRING string[4]; // [rsp+38h] [rbp-28h] BYREF

  result = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v40, "CreateCodecCategoryFromString", 802);
  v4 = (HSTRING *)Windows::Internal::StringReference::StringReference(string, L"audioDecoder");
  v6 = WindowsCompareStringOrdinal(string1, *v4, &result);
  if ( v6 < 0 )
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7, v8);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CreateCodecCategoryFromString", 802, v6);
    }
    if ( g_wppLevels )
    {
      v12 = 106;
LABEL_64:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids, 0, v6);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( !result )
  {
    v13 = MFT_CATEGORY_AUDIO_DECODER;
    goto LABEL_14;
  }
  v14 = (HSTRING *)Windows::Internal::StringReference::StringReference(string, L"videoDecoder");
  v6 = WindowsCompareStringOrdinal(string1, *v14, &result);
  if ( v6 >= 0 )
  {
    if ( result )
    {
      v21 = (HSTRING *)Windows::Internal::StringReference::StringReference(string, L"audioEncoder");
      v6 = WindowsCompareStringOrdinal(string1, *v21, &result);
      if ( v6 < 0 )
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != v6 )
            CallStackContext::TraceFailure(v27, "CreateCodecCategoryFromString", 814, v6);
        }
        if ( g_wppLevels )
        {
          v12 = 108;
          goto LABEL_64;
        }
        goto LABEL_65;
      }
      if ( result )
      {
        v28 = (HSTRING *)Windows::Internal::StringReference::StringReference(string, L"videoEncoder");
        v6 = WindowsCompareStringOrdinal(string1, *v28, &result);
        if ( v6 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v6 )
              CallStackContext::TraceFailure(v34, "CreateCodecCategoryFromString", 820, v6);
          }
          if ( g_wppLevels )
          {
            v12 = 109;
            goto LABEL_64;
          }
          goto LABEL_65;
        }
        if ( result )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          v6 = -1072875845;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
            if ( *((_DWORD *)v37 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v37, "CreateCodecCategoryFromString", 827, -1072875845);
          }
          if ( g_wppLevels )
          {
            v12 = 110;
            goto LABEL_64;
          }
          goto LABEL_65;
        }
        v13 = MFT_CATEGORY_VIDEO_ENCODER;
      }
      else
      {
        v13 = MFT_CATEGORY_AUDIO_ENCODER;
      }
    }
    else
    {
      v13 = MFT_CATEGORY_VIDEO_DECODER;
    }
LABEL_14:
    *a2 = v13;
    goto LABEL_65;
  }
  v18 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
    CallStackTracing::s_wpInstance = v19;
    if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v18 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
    if ( *((_DWORD *)v20 + 499) != v6 )
      CallStackContext::TraceFailure(v20, "CreateCodecCategoryFromString", 808, v6);
  }
  if ( g_wppLevels )
  {
    v12 = 107;
    goto LABEL_64;
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v40);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007515c  mov     [rsp-18h+arg_10], rbx
0x180075161  mov     [rsp-18h+arg_18], rsi
0x180075166  push    rbp
0x180075167  push    rdi
0x180075168  push    r15
0x18007516a  mov     rbp, rsp
0x18007516d  sub     rsp, 60h
0x180075171  mov     rax, cs:__security_cookie
0x180075178  xor     rax, rsp
0x18007517b  mov     [rbp+var_8], rax
0x18007517f  mov     rdi, rdx
0x180075182  mov     [rbp+result], 0
0x180075189  mov     rsi, rcx
0x18007518c  lea     r15, aCreatecodeccat; "CreateCodecCategoryFromString"
0x180075193  mov     rdx, r15; char *
0x180075196  lea     rcx, [rbp+var_2C]; this
0x18007519a  mov     r8d, 322h; int
0x1800751a0  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800751a5  lea     rdx, aAudiodecoder; "audioDecoder"
0x1800751ac  lea     rcx, [rbp+string]; string
0x1800751b0  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x1800751b5  lea     r8, [rbp+result]; result
0x1800751b9  mov     rcx, rsi; string1
0x1800751bc  mov     rdx, [rax]; string2
0x1800751bf  call    cs:__imp_WindowsCompareStringOrdinal
0x1800751c5  mov     ebx, eax
0x1800751c7  test    eax, eax
0x1800751c9  jns     loc_18007525A
0x1800751cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800751d6  test    rcx, rcx
0x1800751d9  jnz     short loc_18007521C
0x1800751db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800751e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800751e8  mov     rcx, rax
0x1800751eb  test    rax, rax
0x1800751ee  jz      short loc_18007520E
0x1800751f0  mov     rax, [rax]
0x1800751f3  mov     edx, 7F0h
0x1800751f8  mov     rax, [rax+8]
0x1800751fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075201  test    eax, eax
0x180075203  jz      short loc_18007520E
0x180075205  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007520c  jmp     short loc_18007521C
0x18007520e  lea     rcx, qword_1800D6F70; this
0x180075215  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007521c  cmp     byte ptr [rcx+8], 0
0x180075220  jz      short loc_180075243
0x180075222  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075227  cmp     [rax+7CCh], ebx
0x18007522d  jz      short loc_180075243
0x18007522f  mov     r9d, ebx; int
0x180075232  mov     r8d, 322h; int
0x180075238  mov     rdx, r15; char *
0x18007523b  mov     rcx, rax; this
0x18007523e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180075243  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007524a  jb      loc_18007556A
0x180075250  mov     edx, 6Ah ; 'j'
0x180075255  jmp     loc_18007554C
0x18007525a  cmp     [rbp+result], 0
0x18007525e  jnz     short loc_180075270
0x180075260  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x180075267  movdqu  xmmword ptr [rdi], xmm0
0x18007526b  jmp     loc_18007556A
0x180075270  lea     rdx, aVideodecoder; "videoDecoder"
0x180075277  lea     rcx, [rbp+string]; string
0x18007527b  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x180075280  lea     r8, [rbp+result]; result
0x180075284  mov     rcx, rsi; string1
0x180075287  mov     rdx, [rax]; string2
0x18007528a  call    cs:__imp_WindowsCompareStringOrdinal
0x180075290  mov     ebx, eax
0x180075292  test    eax, eax
0x180075294  jns     loc_180075325
0x18007529a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800752a1  test    rcx, rcx
0x1800752a4  jnz     short loc_1800752E7
0x1800752a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800752ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800752b3  mov     rcx, rax
0x1800752b6  test    rax, rax
0x1800752b9  jz      short loc_1800752D9
0x1800752bb  mov     rax, [rax]
0x1800752be  mov     edx, 7F0h
0x1800752c3  mov     rax, [rax+8]
0x1800752c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800752cc  test    eax, eax
0x1800752ce  jz      short loc_1800752D9
0x1800752d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800752d7  jmp     short loc_1800752E7
0x1800752d9  lea     rcx, qword_1800D6F70; this
0x1800752e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800752e7  cmp     byte ptr [rcx+8], 0
0x1800752eb  jz      short loc_18007530E
0x1800752ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800752f2  cmp     [rax+7CCh], ebx
0x1800752f8  jz      short loc_18007530E
0x1800752fa  mov     r9d, ebx; int
0x1800752fd  mov     r8d, 328h; int
0x180075303  mov     rdx, r15; char *
0x180075306  mov     rcx, rax; this
0x180075309  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007530e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075315  jb      loc_18007556A
0x18007531b  mov     edx, 6Bh ; 'k'
0x180075320  jmp     loc_18007554C
0x180075325  cmp     [rbp+result], 0
0x180075329  jnz     short loc_180075337
0x18007532b  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180075332  jmp     loc_180075267
0x180075337  lea     rdx, aAudioencoder; "audioEncoder"
0x18007533e  lea     rcx, [rbp+string]; string
0x180075342  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x180075347  lea     r8, [rbp+result]; result
0x18007534b  mov     rcx, rsi; string1
0x18007534e  mov     rdx, [rax]; string2
0x180075351  call    cs:__imp_WindowsCompareStringOrdinal
0x180075357  mov     ebx, eax
0x180075359  test    eax, eax
0x18007535b  jns     loc_1800753EC
0x180075361  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075368  test    rcx, rcx
0x18007536b  jnz     short loc_1800753AE
0x18007536d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180075373  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007537a  mov     rcx, rax
0x18007537d  test    rax, rax
0x180075380  jz      short loc_1800753A0
0x180075382  mov     rax, [rax]
0x180075385  mov     edx, 7F0h
0x18007538a  mov     rax, [rax+8]
0x18007538e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075393  test    eax, eax
0x180075395  jz      short loc_1800753A0
0x180075397  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007539e  jmp     short loc_1800753AE
0x1800753a0  lea     rcx, qword_1800D6F70; this
0x1800753a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800753ae  cmp     byte ptr [rcx+8], 0
0x1800753b2  jz      short loc_1800753D5
0x1800753b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800753b9  cmp     [rax+7CCh], ebx
0x1800753bf  jz      short loc_1800753D5
0x1800753c1  mov     r9d, ebx; int
0x1800753c4  mov     r8d, 32Eh; int
0x1800753ca  mov     rdx, r15; char *
0x1800753cd  mov     rcx, rax; this
0x1800753d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800753d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800753dc  jb      loc_18007556A
0x1800753e2  mov     edx, 6Ch ; 'l'
0x1800753e7  jmp     loc_18007554C
0x1800753ec  cmp     [rbp+result], 0
0x1800753f0  jnz     short loc_1800753FE
0x1800753f2  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x1800753f9  jmp     loc_180075267
0x1800753fe  lea     rdx, aVideoencoder; "videoEncoder"
0x180075405  lea     rcx, [rbp+string]; string
0x180075409  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x18007540e  lea     r8, [rbp+result]; result
0x180075412  mov     rcx, rsi; string1
0x180075415  mov     rdx, [rax]; string2
0x180075418  call    cs:__imp_WindowsCompareStringOrdinal
0x18007541e  mov     ebx, eax
0x180075420  test    eax, eax
0x180075422  jns     loc_1800754B3
0x180075428  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007542f  test    rcx, rcx
0x180075432  jnz     short loc_180075475
0x180075434  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007543a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180075441  mov     rcx, rax
0x180075444  test    rax, rax
0x180075447  jz      short loc_180075467
0x180075449  mov     rax, [rax]
0x18007544c  mov     edx, 7F0h
0x180075451  mov     rax, [rax+8]
0x180075455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007545a  test    eax, eax
0x18007545c  jz      short loc_180075467
0x18007545e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075465  jmp     short loc_180075475
0x180075467  lea     rcx, qword_1800D6F70; this
0x18007546e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075475  cmp     byte ptr [rcx+8], 0
0x180075479  jz      short loc_18007549C
0x18007547b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075480  cmp     [rax+7CCh], ebx
0x180075486  jz      short loc_18007549C
0x180075488  mov     r9d, ebx; int
0x18007548b  mov     r8d, 334h; int
0x180075491  mov     rdx, r15; char *
0x180075494  mov     rcx, rax; this
0x180075497  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007549c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800754a3  jb      loc_18007556A
0x1800754a9  mov     edx, 6Dh ; 'm'
0x1800754ae  jmp     loc_18007554C
0x1800754b3  cmp     [rbp+result], 0
0x1800754b7  jnz     short loc_1800754C5
0x1800754b9  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800754c0  jmp     loc_180075267
0x1800754c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800754cc  mov     ebx, 0C00D36BBh
0x1800754d1  test    rcx, rcx
0x1800754d4  jnz     short loc_180075517
0x1800754d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800754dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800754e3  mov     rcx, rax
0x1800754e6  test    rax, rax
0x1800754e9  jz      short loc_180075509
0x1800754eb  mov     rax, [rax]
0x1800754ee  mov     edx, 7F0h
0x1800754f3  mov     rax, [rax+8]
0x1800754f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800754fc  test    eax, eax
0x1800754fe  jz      short loc_180075509
0x180075500  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180075507  jmp     short loc_180075517
0x180075509  lea     rcx, qword_1800D6F70; this
0x180075510  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180075517  cmp     byte ptr [rcx+8], 0
0x18007551b  jz      short loc_18007553E
0x18007551d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180075522  cmp     [rax+7CCh], ebx
0x180075528  jz      short loc_18007553E
0x18007552a  mov     r9d, ebx; int
0x18007552d  mov     r8d, 33Bh; int
0x180075533  mov     rdx, r15; char *
0x180075536  mov     rcx, rax; this
0x180075539  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007553e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180075545  jb      short loc_18007556A
0x180075547  mov     edx, 6Eh ; 'n'
0x18007554c  mov     rcx, cs:WPP_GLOBAL_Control
0x180075553  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x18007555a  xor     r9d, r9d
0x18007555d  mov     [rsp+60h+var_40], ebx
0x180075561  mov     rcx, [rcx+10h]
0x180075565  call    WPP_SF_qD
0x18007556a  lea     rcx, [rbp+var_2C]; this
0x18007556e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180075573  mov     eax, ebx
0x180075575  mov     rcx, [rbp+var_8]
0x180075579  xor     rcx, rsp; StackCookie
0x18007557c  call    __security_check_cookie
0x180075581  lea     r11, [rsp+60h+var_s0]
0x180075586  mov     rbx, [r11+30h]
0x18007558a  mov     rsi, [r11+38h]
0x18007558e  mov     rsp, r11
0x180075591  pop     r15
0x180075593  pop     rdi
0x180075594  pop     rbp
0x180075595  retn
```
