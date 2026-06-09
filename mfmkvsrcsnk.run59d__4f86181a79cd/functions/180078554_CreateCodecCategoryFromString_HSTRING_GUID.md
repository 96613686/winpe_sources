# CreateCodecCategoryFromString(HSTRING__ *,_GUID *)

- ea: `0x180078554`
- end: `0x1800789c5`
- name: `?CreateCodecCategoryFromString@@YAJPEAUHSTRING__@@PEAU_GUID@@@Z`
- size: `1137`
- prototype: `__int64 __fastcall(HSTRING string1, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800789cc`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18007817c`
- `0x180078554`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800785b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007868e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180078761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180078834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800785b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18007868e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180078761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180078834`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800785d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800786b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078783`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800788fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800785d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800786b0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078783`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180078856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800788fe`

## string_xrefs

- `0x180078584`: `CreateCodecCategoryFromString`

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
        v9 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v25 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v32 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v35 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v18 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180078554  mov     [rsp-18h+arg_10], rbx
0x180078559  mov     [rsp-18h+arg_18], rsi
0x18007855e  push    rbp
0x18007855f  push    rdi
0x180078560  push    r15
0x180078562  mov     rbp, rsp
0x180078565  sub     rsp, 60h
0x180078569  mov     rax, cs:__security_cookie
0x180078570  xor     rax, rsp
0x180078573  mov     [rbp+var_8], rax
0x180078577  mov     rdi, rdx
0x18007857a  mov     [rbp+result], 0
0x180078581  mov     rsi, rcx
0x180078584  lea     r15, aCreatecodeccat; "CreateCodecCategoryFromString"
0x18007858b  mov     rdx, r15; char *
0x18007858e  lea     rcx, [rbp+var_2C]; this
0x180078592  mov     r8d, 322h; int
0x180078598  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007859d  lea     rdx, aAudiodecoder; "audioDecoder"
0x1800785a4  lea     rcx, [rbp+string]; string
0x1800785a8  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x1800785ad  lea     r8, [rbp+result]; result
0x1800785b1  mov     rcx, rsi; string1
0x1800785b4  mov     rdx, [rax]; string2
0x1800785b7  call    cs:__imp_WindowsCompareStringOrdinal
0x1800785be  nop     dword ptr [rax+rax+00h]
0x1800785c3  mov     ebx, eax
0x1800785c5  test    eax, eax
0x1800785c7  jns     loc_18007865E
0x1800785cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800785d4  test    rcx, rcx
0x1800785d7  jnz     short loc_180078620
0x1800785d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800785e0  nop     dword ptr [rax+rax+00h]
0x1800785e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800785ec  mov     rcx, rax
0x1800785ef  test    rax, rax
0x1800785f2  jz      short loc_180078612
0x1800785f4  mov     rax, [rax]
0x1800785f7  mov     edx, 7F0h
0x1800785fc  mov     rax, [rax+8]
0x180078600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078605  test    eax, eax
0x180078607  jz      short loc_180078612
0x180078609  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078610  jmp     short loc_180078620
0x180078612  lea     rcx, qword_1800DBF70; this
0x180078619  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078620  cmp     byte ptr [rcx+8], 0
0x180078624  jz      short loc_180078647
0x180078626  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007862b  cmp     [rax+7CCh], ebx
0x180078631  jz      short loc_180078647
0x180078633  mov     r9d, ebx; int
0x180078636  mov     r8d, 322h; int
0x18007863c  mov     rdx, r15; char *
0x18007863f  mov     rcx, rax; this
0x180078642  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180078647  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007864e  jb      loc_180078998
0x180078654  mov     edx, 6Ah ; 'j'
0x180078659  jmp     loc_18007897A
0x18007865e  cmp     [rbp+result], 0
0x180078662  jnz     short loc_180078674
0x180078664  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_DECODER.Data1
0x18007866b  movdqu  xmmword ptr [rdi], xmm0
0x18007866f  jmp     loc_180078998
0x180078674  lea     rdx, aVideodecoder; "videoDecoder"
0x18007867b  lea     rcx, [rbp+string]; string
0x18007867f  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x180078684  lea     r8, [rbp+result]; result
0x180078688  mov     rcx, rsi; string1
0x18007868b  mov     rdx, [rax]; string2
0x18007868e  call    cs:__imp_WindowsCompareStringOrdinal
0x180078695  nop     dword ptr [rax+rax+00h]
0x18007869a  mov     ebx, eax
0x18007869c  test    eax, eax
0x18007869e  jns     loc_180078735
0x1800786a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800786ab  test    rcx, rcx
0x1800786ae  jnz     short loc_1800786F7
0x1800786b0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800786b7  nop     dword ptr [rax+rax+00h]
0x1800786bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800786c3  mov     rcx, rax
0x1800786c6  test    rax, rax
0x1800786c9  jz      short loc_1800786E9
0x1800786cb  mov     rax, [rax]
0x1800786ce  mov     edx, 7F0h
0x1800786d3  mov     rax, [rax+8]
0x1800786d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800786dc  test    eax, eax
0x1800786de  jz      short loc_1800786E9
0x1800786e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800786e7  jmp     short loc_1800786F7
0x1800786e9  lea     rcx, qword_1800DBF70; this
0x1800786f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800786f7  cmp     byte ptr [rcx+8], 0
0x1800786fb  jz      short loc_18007871E
0x1800786fd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078702  cmp     [rax+7CCh], ebx
0x180078708  jz      short loc_18007871E
0x18007870a  mov     r9d, ebx; int
0x18007870d  mov     r8d, 328h; int
0x180078713  mov     rdx, r15; char *
0x180078716  mov     rcx, rax; this
0x180078719  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007871e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078725  jb      loc_180078998
0x18007872b  mov     edx, 6Bh ; 'k'
0x180078730  jmp     loc_18007897A
0x180078735  cmp     [rbp+result], 0
0x180078739  jnz     short loc_180078747
0x18007873b  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180078742  jmp     loc_18007866B
0x180078747  lea     rdx, aAudioencoder; "audioEncoder"
0x18007874e  lea     rcx, [rbp+string]; string
0x180078752  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x180078757  lea     r8, [rbp+result]; result
0x18007875b  mov     rcx, rsi; string1
0x18007875e  mov     rdx, [rax]; string2
0x180078761  call    cs:__imp_WindowsCompareStringOrdinal
0x180078768  nop     dword ptr [rax+rax+00h]
0x18007876d  mov     ebx, eax
0x18007876f  test    eax, eax
0x180078771  jns     loc_180078808
0x180078777  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007877e  test    rcx, rcx
0x180078781  jnz     short loc_1800787CA
0x180078783  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007878a  nop     dword ptr [rax+rax+00h]
0x18007878f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078796  mov     rcx, rax
0x180078799  test    rax, rax
0x18007879c  jz      short loc_1800787BC
0x18007879e  mov     rax, [rax]
0x1800787a1  mov     edx, 7F0h
0x1800787a6  mov     rax, [rax+8]
0x1800787aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800787af  test    eax, eax
0x1800787b1  jz      short loc_1800787BC
0x1800787b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800787ba  jmp     short loc_1800787CA
0x1800787bc  lea     rcx, qword_1800DBF70; this
0x1800787c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800787ca  cmp     byte ptr [rcx+8], 0
0x1800787ce  jz      short loc_1800787F1
0x1800787d0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800787d5  cmp     [rax+7CCh], ebx
0x1800787db  jz      short loc_1800787F1
0x1800787dd  mov     r9d, ebx; int
0x1800787e0  mov     r8d, 32Eh; int
0x1800787e6  mov     rdx, r15; char *
0x1800787e9  mov     rcx, rax; this
0x1800787ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800787f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800787f8  jb      loc_180078998
0x1800787fe  mov     edx, 6Ch ; 'l'
0x180078803  jmp     loc_18007897A
0x180078808  cmp     [rbp+result], 0
0x18007880c  jnz     short loc_18007881A
0x18007880e  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x180078815  jmp     loc_18007866B
0x18007881a  lea     rdx, aVideoencoder; "videoEncoder"
0x180078821  lea     rcx, [rbp+string]; string
0x180078825  call    ??$?0$0N@@StringReference@Internal@Windows@@QEAA@AEAY0N@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[13])
0x18007882a  lea     r8, [rbp+result]; result
0x18007882e  mov     rcx, rsi; string1
0x180078831  mov     rdx, [rax]; string2
0x180078834  call    cs:__imp_WindowsCompareStringOrdinal
0x18007883b  nop     dword ptr [rax+rax+00h]
0x180078840  mov     ebx, eax
0x180078842  test    eax, eax
0x180078844  jns     loc_1800788DB
0x18007884a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078851  test    rcx, rcx
0x180078854  jnz     short loc_18007889D
0x180078856  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007885d  nop     dword ptr [rax+rax+00h]
0x180078862  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078869  mov     rcx, rax
0x18007886c  test    rax, rax
0x18007886f  jz      short loc_18007888F
0x180078871  mov     rax, [rax]
0x180078874  mov     edx, 7F0h
0x180078879  mov     rax, [rax+8]
0x18007887d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078882  test    eax, eax
0x180078884  jz      short loc_18007888F
0x180078886  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007888d  jmp     short loc_18007889D
0x18007888f  lea     rcx, qword_1800DBF70; this
0x180078896  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007889d  cmp     byte ptr [rcx+8], 0
0x1800788a1  jz      short loc_1800788C4
0x1800788a3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800788a8  cmp     [rax+7CCh], ebx
0x1800788ae  jz      short loc_1800788C4
0x1800788b0  mov     r9d, ebx; int
0x1800788b3  mov     r8d, 334h; int
0x1800788b9  mov     rdx, r15; char *
0x1800788bc  mov     rcx, rax; this
0x1800788bf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800788c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800788cb  jb      loc_180078998
0x1800788d1  mov     edx, 6Dh ; 'm'
0x1800788d6  jmp     loc_18007897A
0x1800788db  cmp     [rbp+result], 0
0x1800788df  jnz     short loc_1800788ED
0x1800788e1  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x1800788e8  jmp     loc_18007866B
0x1800788ed  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800788f4  mov     ebx, 0C00D36BBh
0x1800788f9  test    rcx, rcx
0x1800788fc  jnz     short loc_180078945
0x1800788fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180078905  nop     dword ptr [rax+rax+00h]
0x18007890a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180078911  mov     rcx, rax
0x180078914  test    rax, rax
0x180078917  jz      short loc_180078937
0x180078919  mov     rax, [rax]
0x18007891c  mov     edx, 7F0h
0x180078921  mov     rax, [rax+8]
0x180078925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007892a  test    eax, eax
0x18007892c  jz      short loc_180078937
0x18007892e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180078935  jmp     short loc_180078945
0x180078937  lea     rcx, qword_1800DBF70; this
0x18007893e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180078945  cmp     byte ptr [rcx+8], 0
0x180078949  jz      short loc_18007896C
0x18007894b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180078950  cmp     [rax+7CCh], ebx
0x180078956  jz      short loc_18007896C
0x180078958  mov     r9d, ebx; int
0x18007895b  mov     r8d, 33Bh; int
0x180078961  mov     rdx, r15; char *
0x180078964  mov     rcx, rax; this
0x180078967  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007896c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078973  jb      short loc_180078998
0x180078975  mov     edx, 6Eh ; 'n'
0x18007897a  mov     rcx, cs:WPP_GLOBAL_Control
0x180078981  lea     r8, WPP_99bcbd65aa833b005deca75f8cdcbbf8_Traceguids
0x180078988  xor     r9d, r9d
0x18007898b  mov     [rsp+60h+var_40], ebx
0x18007898f  mov     rcx, [rcx+10h]
0x180078993  call    WPP_SF_qD
0x180078998  lea     rcx, [rbp+var_2C]; this
0x18007899c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800789a1  mov     eax, ebx
0x1800789a3  mov     rcx, [rbp+var_8]
0x1800789a7  xor     rcx, rsp; StackCookie
0x1800789aa  call    __security_check_cookie
0x1800789af  lea     r11, [rsp+60h+var_s0]
0x1800789b4  mov     rbx, [r11+30h]
0x1800789b8  mov     rsi, [r11+38h]
0x1800789bc  mov     rsp, r11
0x1800789bf  pop     r15
0x1800789c1  pop     rdi
0x1800789c2  pop     rbp
0x1800789c3  retn
```
