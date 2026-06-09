# CAC3MediaSourcePlugin::FindNextIndependentFrame(unsigned __int64 *)

- ea: `0x1800a85c0`
- end: `0x1800a8ac9`
- name: `?FindNextIndependentFrame@CAC3MediaSourcePlugin@@AEAAJPEA_K@Z`
- size: `1289`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800ace8c`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180034d10`
- `0x180079680`
- `0x1800a85c0`
- `0x180110ed0`
- `0x180138280`
- `0x1801382d0`
- `0x180139470`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8792`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a88d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a896a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a89ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8647`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8792`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a88d5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a896a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a89ff`

## string_xrefs

- `0x1800a85ec`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`
- `0x1800a86a4`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`
- `0x1800a887a`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`
- `0x1800a8932`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`
- `0x1800a89c7`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`
- `0x1800a8a5c`: `CAC3MediaSourcePlugin::FindNextIndependentFrame`

## pseudocode

```c
__int64 __fastcall CAC3MediaSourcePlugin::FindNextIndependentFrame(CAC3MediaSourcePlugin *this, unsigned __int64 *a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rdx
  int v6; // ebx
  wchar_t *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  struct CallStackContext *v19; // rax
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  _BYTE v30[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v31; // [rsp+38h] [rbp-38h] BYREF
  int v32; // [rsp+40h] [rbp-30h]
  __int16 v33; // [rsp+44h] [rbp-2Ch]
  __int64 v34; // [rsp+48h] [rbp-28h]
  int v35; // [rsp+50h] [rbp-20h]
  unsigned __int8 v36; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 v37; // [rsp+59h] [rbp-17h] BYREF
  unsigned __int8 v38[14]; // [rsp+5Ah] [rbp-16h] BYREF

  *a2 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v30,
    "CAC3MediaSourcePlugin::FindNextIndependentFrame",
    1440);
  v4 = *((_QWORD *)this + 65);
  v6 = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), &v36, 2u);
  if ( v6 < 0 )
  {
    v7 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAC3MediaSourcePlugin::FindNextIndependentFrame",
          1441,
          v6);
    }
    if ( g_wppLevels )
    {
      v10 = 116;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( v36 == 11 && v37 == 119 )
      {
LABEL_16:
        v6 = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), v38, 0xAu);
        if ( v6 < 0 )
        {
          v20 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
            CallStackTracing::s_wpInstance = v21;
            if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
            {
              v20 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v20 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v20 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)v22 + 499) != v6 )
              CallStackContext::TraceFailure(v22, "CAC3MediaSourcePlugin::FindNextIndependentFrame", 1449, v6);
          }
          if ( g_wppLevels )
          {
            v10 = 117;
            goto LABEL_74;
          }
          goto LABEL_75;
        }
        CAC3FrameHeader::Parse((CAC3FrameHeader *)&v31, &v36);
        if ( (unsigned int)CAC3FrameHeader::IsValidFrameHeader((CAC3FrameHeader *)&v31)
          && (unsigned __int16)(WORD1(v31) - 11) <= 5u )
        {
          if ( (v35 & 0xFFFD) == 0 )
          {
            *a2 = v4;
            goto LABEL_75;
          }
          v4 += WORD2(v31);
          v12 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v4);
          v6 = v12;
          if ( v12 < 0 )
          {
            if ( g_wppLevels < 0x20u )
              goto LABEL_75;
            v16 = 118;
            goto LABEL_42;
          }
          v6 = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), &v36, 2u);
          if ( v6 < 0 )
          {
            v14 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
              CallStackTracing::s_wpInstance = v15;
              if ( v15
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
              {
                v14 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v14 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v14 + 8) )
            {
              v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
              if ( *((_DWORD *)v19 + 499) != v6 )
                CallStackContext::TraceFailure(v19, "CAC3MediaSourcePlugin::FindNextIndependentFrame", 1470, v6);
            }
            if ( g_wppLevels )
            {
              v10 = 119;
              goto LABEL_74;
            }
            goto LABEL_75;
          }
        }
        else
        {
          v4 += 2LL;
          v12 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v4);
          v6 = v12;
          if ( v12 < 0 )
          {
            if ( g_wppLevels < 0x20u )
              goto LABEL_75;
            v16 = 120;
LABEL_42:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v16,
              WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
              this,
              v12);
            goto LABEL_75;
          }
        }
      }
      if ( v36 != 119 )
        break;
      if ( v37 == 11 )
        goto LABEL_16;
LABEL_32:
      v6 = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), &v36, 2u);
      if ( v6 < 0 )
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)v28 + 499) != v6 )
            CallStackContext::TraceFailure(v28, "CAC3MediaSourcePlugin::FindNextIndependentFrame", 1491, v6);
        }
        if ( g_wppLevels )
        {
          v10 = 122;
LABEL_74:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids, this, v6);
        }
        goto LABEL_75;
      }
      v4 += 2LL;
    }
    if ( v37 != 11 )
      goto LABEL_32;
    v36 = 11;
    v6 = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), &v37, 1u);
    if ( v6 < 0 )
      break;
    ++v4;
  }
  v23 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
    CallStackTracing::s_wpInstance = v24;
    if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
    {
      v23 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v23 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v23 + 8) )
  {
    v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
    if ( *((_DWORD *)v25 + 499) != v6 )
      CallStackContext::TraceFailure(v25, "CAC3MediaSourcePlugin::FindNextIndependentFrame", 1486, v6);
  }
  if ( g_wppLevels )
  {
    v10 = 121;
    goto LABEL_74;
  }
LABEL_75:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a85c0  mov     [rsp-28h+arg_10], rbx
0x1800a85c5  push    rbp
0x1800a85c6  push    rsi
0x1800a85c7  push    rdi
0x1800a85c8  push    r14
0x1800a85ca  push    r15
0x1800a85cc  mov     rbp, rsp
0x1800a85cf  sub     rsp, 70h
0x1800a85d3  mov     rax, cs:__security_cookie
0x1800a85da  xor     rax, rsp
0x1800a85dd  mov     [rbp+var_8], rax
0x1800a85e1  xor     eax, eax
0x1800a85e3  mov     r15, rdx
0x1800a85e6  mov     [rdx], rax
0x1800a85e9  mov     rsi, rcx
0x1800a85ec  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a85f3  mov     [rbp+var_38], rax
0x1800a85f7  mov     r8d, 5A0h; int
0x1800a85fd  mov     [rbp+var_30], eax
0x1800a8600  lea     rcx, [rbp+var_40]; this
0x1800a8604  mov     [rbp+var_2C], ax
0x1800a8608  mov     [rbp+var_28], rax
0x1800a860c  mov     [rbp+var_20], eax
0x1800a860f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8614  lea     r14, [rsi+30h]
0x1800a8618  mov     r8d, 2; unsigned int
0x1800a861e  mov     rdi, [r14+1D8h]
0x1800a8625  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x1800a8629  mov     rcx, r14; this
0x1800a862c  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a8631  mov     ebx, eax
0x1800a8633  test    eax, eax
0x1800a8635  jns     loc_1800A86D0
0x1800a863b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8642  test    rcx, rcx
0x1800a8645  jnz     short loc_1800A868E
0x1800a8647  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a864e  nop     dword ptr [rax+rax+00h]
0x1800a8653  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a865a  mov     rcx, rax
0x1800a865d  test    rax, rax
0x1800a8660  jz      short loc_1800A8680
0x1800a8662  mov     rax, [rax]
0x1800a8665  mov     edx, 7F0h
0x1800a866a  mov     rax, [rax+8]
0x1800a866e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8673  test    eax, eax
0x1800a8675  jz      short loc_1800A8680
0x1800a8677  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a867e  jmp     short loc_1800A868E
0x1800a8680  lea     rcx, qword_1801B97E0; this
0x1800a8687  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a868e  cmp     byte ptr [rcx+8], 0
0x1800a8692  jz      short loc_1800A86B9
0x1800a8694  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8699  cmp     [rax+7CCh], ebx
0x1800a869f  jz      short loc_1800A86B9
0x1800a86a1  mov     r9d, ebx; int
0x1800a86a4  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a86ab  mov     r8d, 5A1h; int
0x1800a86b1  mov     rcx, rax; this
0x1800a86b4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a86b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a86c0  jb      loc_1800A8A9D
0x1800a86c6  mov     edx, 74h ; 't'
0x1800a86cb  jmp     loc_1800A8A7F
0x1800a86d0  cmp     [rbp+var_18], 0Bh
0x1800a86d4  mov     al, [rbp+var_17]
0x1800a86d7  jnz     short loc_1800A86DD
0x1800a86d9  cmp     al, 77h ; 'w'
0x1800a86db  jz      short loc_1800A86EF
0x1800a86dd  cmp     [rbp+var_18], 77h ; 'w'
0x1800a86e1  jnz     loc_1800A8806
0x1800a86e7  cmp     al, 0Bh
0x1800a86e9  jnz     loc_1800A8831
0x1800a86ef  mov     r8d, 0Ah; unsigned int
0x1800a86f5  lea     rdx, [rbp+var_16]; unsigned __int8 *
0x1800a86f9  mov     rcx, r14; this
0x1800a86fc  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a8701  mov     ebx, eax
0x1800a8703  test    eax, eax
0x1800a8705  js      loc_1800A88C9
0x1800a870b  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x1800a870f  lea     rcx, [rbp+var_38]; this
0x1800a8713  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800a8718  lea     rcx, [rbp+var_38]; this
0x1800a871c  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800a8721  test    eax, eax
0x1800a8723  jz      loc_1800A87D6
0x1800a8729  movzx   eax, word ptr [rbp+var_38+2]
0x1800a872d  sub     ax, 0Bh
0x1800a8731  cmp     ax, 5
0x1800a8735  ja      loc_1800A87D6
0x1800a873b  mov     eax, 0FFFDh
0x1800a8740  test    word ptr [rbp+var_20], ax
0x1800a8744  jz      loc_1800A88C1
0x1800a874a  movzx   eax, word ptr [rbp+var_38+4]
0x1800a874e  mov     rcx, rsi; this
0x1800a8751  add     rdi, rax
0x1800a8754  mov     rdx, rdi; unsigned __int64
0x1800a8757  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a875c  mov     ebx, eax
0x1800a875e  test    eax, eax
0x1800a8760  js      loc_1800A88A6
0x1800a8766  mov     r8d, 2; unsigned int
0x1800a876c  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x1800a8770  mov     rcx, r14; this
0x1800a8773  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a8778  mov     ebx, eax
0x1800a877a  test    eax, eax
0x1800a877c  jns     loc_1800A86D0
0x1800a8782  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8789  test    rcx, rcx
0x1800a878c  jnz     loc_1800A8864
0x1800a8792  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8799  nop     dword ptr [rax+rax+00h]
0x1800a879e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a87a5  mov     rcx, rax
0x1800a87a8  test    rax, rax
0x1800a87ab  jz      loc_1800A8856
0x1800a87b1  mov     rax, [rax]
0x1800a87b4  mov     edx, 7F0h
0x1800a87b9  mov     rax, [rax+8]
0x1800a87bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a87c2  test    eax, eax
0x1800a87c4  jz      loc_1800A8856
0x1800a87ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a87d1  jmp     loc_1800A8864
0x1800a87d6  add     rdi, 2
0x1800a87da  mov     rcx, rsi; this
0x1800a87dd  mov     rdx, rdi; unsigned __int64
0x1800a87e0  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a87e5  mov     ebx, eax
0x1800a87e7  test    eax, eax
0x1800a87e9  jns     loc_1800A86D0
0x1800a87ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800a87f6  jb      loc_1800A8A9D
0x1800a87fc  mov     edx, 78h ; 'x'
0x1800a8801  jmp     loc_1800A88B8
0x1800a8806  cmp     al, 0Bh
0x1800a8808  jnz     short loc_1800A8831
0x1800a880a  mov     r8d, 1; unsigned int
0x1800a8810  mov     [rbp+var_18], al
0x1800a8813  lea     rdx, [rbp+var_17]; unsigned __int8 *
0x1800a8817  mov     rcx, r14; this
0x1800a881a  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a881f  mov     ebx, eax
0x1800a8821  test    eax, eax
0x1800a8823  js      loc_1800A895E
0x1800a8829  inc     rdi
0x1800a882c  jmp     loc_1800A86D0
0x1800a8831  mov     r8d, 2; unsigned int
0x1800a8837  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x1800a883b  mov     rcx, r14; this
0x1800a883e  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a8843  mov     ebx, eax
0x1800a8845  test    eax, eax
0x1800a8847  js      loc_1800A89F3
0x1800a884d  add     rdi, 2
0x1800a8851  jmp     loc_1800A86D0
0x1800a8856  lea     rcx, qword_1801B97E0; this
0x1800a885d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8864  cmp     byte ptr [rcx+8], 0
0x1800a8868  jz      short loc_1800A888F
0x1800a886a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a886f  cmp     [rax+7CCh], ebx
0x1800a8875  jz      short loc_1800A888F
0x1800a8877  mov     r9d, ebx; int
0x1800a887a  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a8881  mov     r8d, 5BEh; int
0x1800a8887  mov     rcx, rax; this
0x1800a888a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a888f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8896  jb      loc_1800A8A9D
0x1800a889c  mov     edx, 77h ; 'w'
0x1800a88a1  jmp     loc_1800A8A7F
0x1800a88a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800a88ad  jb      loc_1800A8A9D
0x1800a88b3  mov     edx, 76h ; 'v'
0x1800a88b8  mov     [rsp+70h+var_50], eax
0x1800a88bc  jmp     loc_1800A8A83
0x1800a88c1  mov     [r15], rdi
0x1800a88c4  jmp     loc_1800A8A9D
0x1800a88c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a88d0  test    rcx, rcx
0x1800a88d3  jnz     short loc_1800A891C
0x1800a88d5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a88dc  nop     dword ptr [rax+rax+00h]
0x1800a88e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a88e8  mov     rcx, rax
0x1800a88eb  test    rax, rax
0x1800a88ee  jz      short loc_1800A890E
0x1800a88f0  mov     rax, [rax]
0x1800a88f3  mov     edx, 7F0h
0x1800a88f8  mov     rax, [rax+8]
0x1800a88fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8901  test    eax, eax
0x1800a8903  jz      short loc_1800A890E
0x1800a8905  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a890c  jmp     short loc_1800A891C
0x1800a890e  lea     rcx, qword_1801B97E0; this
0x1800a8915  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a891c  cmp     byte ptr [rcx+8], 0
0x1800a8920  jz      short loc_1800A8947
0x1800a8922  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8927  cmp     [rax+7CCh], ebx
0x1800a892d  jz      short loc_1800A8947
0x1800a892f  mov     r9d, ebx; int
0x1800a8932  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a8939  mov     r8d, 5A9h; int
0x1800a893f  mov     rcx, rax; this
0x1800a8942  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8947  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a894e  jb      loc_1800A8A9D
0x1800a8954  mov     edx, 75h ; 'u'
0x1800a8959  jmp     loc_1800A8A7F
0x1800a895e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8965  test    rcx, rcx
0x1800a8968  jnz     short loc_1800A89B1
0x1800a896a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8971  nop     dword ptr [rax+rax+00h]
0x1800a8976  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a897d  mov     rcx, rax
0x1800a8980  test    rax, rax
0x1800a8983  jz      short loc_1800A89A3
0x1800a8985  mov     rax, [rax]
0x1800a8988  mov     edx, 7F0h
0x1800a898d  mov     rax, [rax+8]
0x1800a8991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8996  test    eax, eax
0x1800a8998  jz      short loc_1800A89A3
0x1800a899a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a89a1  jmp     short loc_1800A89B1
0x1800a89a3  lea     rcx, qword_1801B97E0; this
0x1800a89aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a89b1  cmp     byte ptr [rcx+8], 0
0x1800a89b5  jz      short loc_1800A89DC
0x1800a89b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a89bc  cmp     [rax+7CCh], ebx
0x1800a89c2  jz      short loc_1800A89DC
0x1800a89c4  mov     r9d, ebx; int
0x1800a89c7  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a89ce  mov     r8d, 5CEh; int
0x1800a89d4  mov     rcx, rax; this
0x1800a89d7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a89dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a89e3  jb      loc_1800A8A9D
0x1800a89e9  mov     edx, 79h ; 'y'
0x1800a89ee  jmp     loc_1800A8A7F
0x1800a89f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a89fa  test    rcx, rcx
0x1800a89fd  jnz     short loc_1800A8A46
0x1800a89ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8a06  nop     dword ptr [rax+rax+00h]
0x1800a8a0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8a12  mov     rcx, rax
0x1800a8a15  test    rax, rax
0x1800a8a18  jz      short loc_1800A8A38
0x1800a8a1a  mov     rax, [rax]
0x1800a8a1d  mov     edx, 7F0h
0x1800a8a22  mov     rax, [rax+8]
0x1800a8a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8a2b  test    eax, eax
0x1800a8a2d  jz      short loc_1800A8A38
0x1800a8a2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8a36  jmp     short loc_1800A8A46
0x1800a8a38  lea     rcx, qword_1801B97E0; this
0x1800a8a3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8a46  cmp     byte ptr [rcx+8], 0
0x1800a8a4a  jz      short loc_1800A8A71
0x1800a8a4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8a51  cmp     [rax+7CCh], ebx
0x1800a8a57  jz      short loc_1800A8A71
0x1800a8a59  mov     r9d, ebx; int
0x1800a8a5c  lea     rdx, aCac3mediasourc_10; "CAC3MediaSourcePlugin::FindNextIndepend"...
0x1800a8a63  mov     r8d, 5D3h; int
0x1800a8a69  mov     rcx, rax; this
0x1800a8a6c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8a71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8a78  jb      short loc_1800A8A9D
0x1800a8a7a  mov     edx, 7Ah ; 'z'
0x1800a8a7f  mov     [rsp+70h+var_50], ebx
0x1800a8a83  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8a8a  lea     r8, WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids
0x1800a8a91  mov     r9, rsi
0x1800a8a94  mov     rcx, [rcx+10h]
0x1800a8a98  call    WPP_SF_qD
0x1800a8a9d  lea     rcx, [rbp+var_40]; this
0x1800a8aa1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a8aa6  mov     eax, ebx
0x1800a8aa8  mov     rcx, [rbp+var_8]
0x1800a8aac  xor     rcx, rsp; StackCookie
0x1800a8aaf  call    __security_check_cookie
0x1800a8ab4  mov     rbx, [rsp+70h+arg_10]
0x1800a8abc  add     rsp, 70h
0x1800a8ac0  pop     r15
0x1800a8ac2  pop     r14
0x1800a8ac4  pop     rdi
0x1800a8ac5  pop     rsi
0x1800a8ac6  pop     rbp
  ... truncated ...
```
