# CAC3MediaSourcePlugin::FindNextFrameHeader(ulong *,unsigned __int64 *)

- ea: `0x1800ace8c`
- end: `0x1800ad6b2`
- name: `?FindNextFrameHeader@CAC3MediaSourcePlugin@@AEAAHPEAKPEA_K@Z`
- size: `2086`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *__hidden this, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800c8bd0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180030e8c`
- `0x180034d10`
- `0x180079680`
- `0x180084ee8`
- `0x1800a85c0`
- `0x1800ace8c`
- `0x180110ed0`
- `0x180138280`
- `0x1801382d0`
- `0x180139470`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800acf22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad18e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad2bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad360`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad402`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad548`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800acf22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad119`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad18e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad2bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad360`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad402`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ad548`

## string_xrefs

- `0x1800aced1`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800acf7f`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad319`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad3c2`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad45f`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad4e2`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad5a5`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad5f5`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800ad63e`: `CAC3MediaSourcePlugin::FindNextFrameHeader`

## pseudocode

```c
__int64 __fastcall CAC3MediaSourcePlugin::FindNextFrameHeader(
        CAC3MediaSourcePlugin *this,
        unsigned int *a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v6; // r13
  __int64 v7; // rdx
  int NextIndependentFrame; // esi
  wchar_t *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned __int64 v14; // rsi
  int v15; // eax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  unsigned __int64 v25; // r14
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  unsigned __int64 v33; // rax
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  unsigned __int64 *v40; // rcx
  struct CallStackContext *v41; // rax
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  _BYTE v48[4]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v49; // [rsp+34h] [rbp-4Ch]
  __int64 v50; // [rsp+38h] [rbp-48h] BYREF
  int v51; // [rsp+40h] [rbp-40h]
  __int16 v52; // [rsp+44h] [rbp-3Ch]
  unsigned __int64 v53; // [rsp+48h] [rbp-38h]
  int v54; // [rsp+50h] [rbp-30h]
  unsigned __int64 *v55; // [rsp+58h] [rbp-28h]
  unsigned __int8 v56[8]; // [rsp+60h] [rbp-20h] BYREF

  v55 = a3;
  *a2 = 0;
  *a3 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v49 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v48,
    "CAC3MediaSourcePlugin::FindNextFrameHeader",
    1312);
  v6 = *((_QWORD *)this + 65);
  NextIndependentFrame = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), v56, 2u);
  if ( NextIndependentFrame < 0 )
  {
    v9 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != NextIndependentFrame )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAC3MediaSourcePlugin::FindNextFrameHeader",
          1313,
          NextIndependentFrame);
    }
    if ( g_wppLevels )
    {
      v12 = 102;
      goto LABEL_123;
    }
    goto LABEL_124;
  }
  do
  {
    while ( 1 )
    {
      if ( v56[0] == 11 && v56[1] == 119 )
        goto LABEL_16;
      if ( v56[0] != 119 )
        break;
      if ( v56[1] == 11 )
      {
LABEL_16:
        NextIndependentFrame = CSourcePluginBufferReader::Read(
                                 (CAC3MediaSourcePlugin *)((char *)this + 48),
                                 &v56[2],
                                 0xAu);
        if ( NextIndependentFrame < 0 )
        {
          v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
            CallStackTracing::s_wpInstance = v43;
            if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              v42 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v42 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v42 + 8) )
          {
            v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
            if ( *((_DWORD *)v44 + 499) != NextIndependentFrame )
              CallStackContext::TraceFailure(
                v44,
                "CAC3MediaSourcePlugin::FindNextFrameHeader",
                1321,
                NextIndependentFrame);
          }
          if ( g_wppLevels )
          {
            v12 = 103;
            goto LABEL_123;
          }
          goto LABEL_124;
        }
        CAC3FrameHeader::Parse((CAC3FrameHeader *)&v50, v56);
        if ( (unsigned int)CAC3FrameHeader::IsValidFrameHeader((CAC3FrameHeader *)&v50) )
        {
          if ( (unsigned __int16)(WORD1(v50) - 11) > 5u )
            goto LABEL_89;
          if ( !HIWORD(v54) )
          {
            if ( (_WORD)v54 == 2 )
            {
LABEL_89:
              *a2 = WORD2(v50);
              *a3 = v53;
            }
            else
            {
              if ( (_WORD)v54 )
                goto LABEL_22;
              v25 = v6 + WORD2(v50);
              v15 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v25);
              if ( v15 < 0 )
              {
                if ( g_wppLevels < 0x20u )
                  goto LABEL_124;
                v26 = 104;
                goto LABEL_44;
              }
              *(_QWORD *)v56 = 0;
              NextIndependentFrame = CAC3MediaSourcePlugin::FindNextIndependentFrame(this, (unsigned __int64 *)v56);
              if ( NextIndependentFrame == -1072863856 )
              {
                if ( (*((_BYTE *)this + 568) & 4) == 0 )
                {
                  v28 = *((_QWORD *)this + 70);
                  if ( (unsigned __int64)(v28 - 1) > 0xFFFFFFFFFFFFFFFDuLL
                    || !CSourcePluginBufferReader::HasDataAtPosition(
                          (CAC3MediaSourcePlugin *)((char *)this + 48),
                          v28 - 1) )
                  {
                    if ( g_wppLevels >= 0x20u )
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        108,
                        WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
                        this,
                        -1072863856);
                    goto LABEL_124;
                  }
                }
                v15 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v25);
                if ( v15 < 0 )
                {
                  if ( g_wppLevels < 0x20u )
                    goto LABEL_124;
                  v26 = 105;
LABEL_44:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v26,
                    WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
                    this,
                    v15);
                  goto LABEL_124;
                }
                *(_DWORD *)v56 = 0;
                NextIndependentFrame = CSourcePluginBufferReader::GetAvailableBufferSize(
                                         (CAC3MediaSourcePlugin *)((char *)this + 48),
                                         (unsigned int *)v56);
                if ( NextIndependentFrame < 0 )
                {
                  v30 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                    CallStackTracing::s_wpInstance = v31;
                    if ( v31
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                    {
                      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v30 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v30 + 8) )
                  {
                    v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                    if ( *((_DWORD *)v32 + 499) != NextIndependentFrame )
                      CallStackContext::TraceFailure(
                        v32,
                        "CAC3MediaSourcePlugin::FindNextFrameHeader",
                        1363,
                        NextIndependentFrame);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 106;
                    goto LABEL_123;
                  }
                  goto LABEL_124;
                }
                v33 = v25 + *(unsigned int *)v56;
                if ( v33 < v25 )
                {
                  v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
                    CallStackTracing::s_wpInstance = v35;
                    if ( v35
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                    {
                      v34 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v34 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  NextIndependentFrame = -2147024362;
                  if ( *((_BYTE *)v34 + 8) )
                  {
                    v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                    if ( *((_DWORD *)v36 + 499) != -2147024362 )
                      CallStackContext::TraceFailure(
                        v36,
                        "CAC3MediaSourcePlugin::FindNextFrameHeader",
                        1366,
                        -2147024362);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 107;
                    goto LABEL_123;
                  }
                  goto LABEL_124;
                }
              }
              else
              {
                if ( NextIndependentFrame < 0 )
                {
                  v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                    CallStackTracing::s_wpInstance = v38;
                    if ( v38
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                    {
                      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v37 = &qword_1801B97E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                    }
                  }
                  if ( *((_BYTE *)v37 + 8) )
                  {
                    v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                    if ( *((_DWORD *)v39 + 499) != NextIndependentFrame )
                      CallStackContext::TraceFailure(
                        v39,
                        "CAC3MediaSourcePlugin::FindNextFrameHeader",
                        1373,
                        NextIndependentFrame);
                  }
                  if ( g_wppLevels )
                  {
                    v12 = 109;
                    goto LABEL_123;
                  }
                  goto LABEL_124;
                }
                LODWORD(v33) = *(_DWORD *)v56;
              }
              v40 = v55;
              *a2 = v33 - v6;
              *v40 = v53;
            }
            v49 = 1;
            goto LABEL_124;
          }
LABEL_22:
          v14 = v6 + WORD2(v50);
          v15 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v14);
          if ( v15 < 0 )
          {
            if ( g_wppLevels < 0x20u )
              goto LABEL_124;
            v26 = 110;
            goto LABEL_44;
          }
          v6 = v14;
          NextIndependentFrame = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), v56, 2u);
          if ( NextIndependentFrame < 0 )
          {
            v17 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
              CallStackTracing::s_wpInstance = v18;
              if ( v18
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
              {
                v17 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v17 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v17 + 8) )
            {
              v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
              if ( *((_DWORD *)v41 + 499) != NextIndependentFrame )
                CallStackContext::TraceFailure(
                  v41,
                  "CAC3MediaSourcePlugin::FindNextFrameHeader",
                  1387,
                  NextIndependentFrame);
            }
            if ( g_wppLevels )
            {
              v12 = 111;
              goto LABEL_123;
            }
            goto LABEL_124;
          }
        }
        else
        {
          v15 = CAC3MediaSourcePlugin::TrySetBufferReaderPosition(this, v6 + 2);
          if ( v15 < 0 )
          {
            if ( g_wppLevels < 0x20u )
              goto LABEL_124;
            v26 = 112;
            goto LABEL_44;
          }
          v6 += 2LL;
        }
      }
      else
      {
LABEL_36:
        v6 += 2LL;
        NextIndependentFrame = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), v56, 2u);
        if ( NextIndependentFrame < 0 )
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
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
            v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v46 + 499) != NextIndependentFrame )
              CallStackContext::TraceFailure(
                v46,
                "CAC3MediaSourcePlugin::FindNextFrameHeader",
                1414,
                NextIndependentFrame);
          }
          if ( g_wppLevels )
          {
            v12 = 114;
LABEL_123:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              WPP_bdcd4858ee7534a410bb12c03f1ca367_Traceguids,
              this,
              NextIndependentFrame);
          }
          goto LABEL_124;
        }
      }
    }
    if ( v56[1] != 11 )
      goto LABEL_36;
    v56[0] = 11;
    ++v6;
    NextIndependentFrame = CSourcePluginBufferReader::Read((CAC3MediaSourcePlugin *)((char *)this + 48), &v56[1], 1u);
  }
  while ( NextIndependentFrame >= 0 );
  v20 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
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
    v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
    if ( *((_DWORD *)v45 + 499) != NextIndependentFrame )
      CallStackContext::TraceFailure(v45, "CAC3MediaSourcePlugin::FindNextFrameHeader", 1409, NextIndependentFrame);
  }
  if ( g_wppLevels )
  {
    v12 = 113;
    goto LABEL_123;
  }
LABEL_124:
  *((_QWORD *)this + 65) = v6;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
  return v49;
}

```

## disassembly

```asm
0x1800ace8c  push    rbp
0x1800ace8e  push    rbx
0x1800ace8f  push    rsi
0x1800ace90  push    r12
0x1800ace92  push    r13
0x1800ace94  push    r14
0x1800ace96  push    r15
0x1800ace98  mov     rbp, rsp
0x1800ace9b  sub     rsp, 80h
0x1800acea2  mov     rax, cs:__security_cookie
0x1800acea9  xor     rax, rsp
0x1800aceac  mov     [rbp+var_10], rax
0x1800aceb0  xor     eax, eax
0x1800aceb2  mov     [rbp+var_28], r8
0x1800aceb6  mov     [rdx], eax
0x1800aceb8  mov     r14, r8
0x1800acebb  mov     [r8], rax
0x1800acebe  mov     r12, rdx
0x1800acec1  mov     rbx, rcx
0x1800acec4  mov     [rbp+var_48], rax
0x1800acec8  mov     r8d, 520h; int
0x1800acece  mov     [rbp+var_40], eax
0x1800aced1  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800aced8  mov     [rbp+var_3C], ax
0x1800acedc  lea     rcx, [rbp+var_50]; this
0x1800acee0  mov     [rbp+var_38], rax
0x1800acee4  mov     [rbp+var_30], eax
0x1800acee7  mov     [rbp+var_4C], eax
0x1800aceea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800aceef  lea     r15, [rbx+30h]
0x1800acef3  mov     r8d, 2; unsigned int
0x1800acef9  mov     r13, [r15+1D8h]
0x1800acf00  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800acf04  mov     rcx, r15; this
0x1800acf07  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800acf0c  mov     esi, eax
0x1800acf0e  test    eax, eax
0x1800acf10  jns     loc_1800ACFAB
0x1800acf16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acf1d  test    rcx, rcx
0x1800acf20  jnz     short loc_1800ACF69
0x1800acf22  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800acf29  nop     dword ptr [rax+rax+00h]
0x1800acf2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acf35  mov     rcx, rax
0x1800acf38  test    rax, rax
0x1800acf3b  jz      short loc_1800ACF5B
0x1800acf3d  mov     rax, [rax]
0x1800acf40  mov     edx, 7F0h
0x1800acf45  mov     rax, [rax+8]
0x1800acf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf4e  test    eax, eax
0x1800acf50  jz      short loc_1800ACF5B
0x1800acf52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acf59  jmp     short loc_1800ACF69
0x1800acf5b  lea     rcx, qword_1801B97E0; this
0x1800acf62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800acf69  cmp     byte ptr [rcx+8], 0
0x1800acf6d  jz      short loc_1800ACF94
0x1800acf6f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800acf74  cmp     [rax+7CCh], esi
0x1800acf7a  jz      short loc_1800ACF94
0x1800acf7c  mov     r9d, esi; int
0x1800acf7f  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800acf86  mov     r8d, 521h; int
0x1800acf8c  mov     rcx, rax; this
0x1800acf8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800acf94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800acf9b  jb      loc_1800AD67F
0x1800acfa1  mov     edx, 66h ; 'f'
0x1800acfa6  jmp     loc_1800AD661
0x1800acfab  cmp     [rbp+var_20], 0Bh
0x1800acfaf  mov     al, [rbp+var_20+1]
0x1800acfb2  jnz     short loc_1800ACFB8
0x1800acfb4  cmp     al, 77h ; 'w'
0x1800acfb6  jz      short loc_1800ACFCA
0x1800acfb8  cmp     [rbp+var_20], 77h ; 'w'
0x1800acfbc  jnz     loc_1800AD0E3
0x1800acfc2  cmp     al, 0Bh
0x1800acfc4  jnz     loc_1800AD15D
0x1800acfca  mov     r8d, 0Ah; unsigned int
0x1800acfd0  lea     rdx, [rbp+var_20+2]; unsigned __int8 *
0x1800acfd4  mov     rcx, r15; this
0x1800acfd7  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800acfdc  mov     esi, eax
0x1800acfde  test    eax, eax
0x1800acfe0  js      loc_1800AD53C
0x1800acfe6  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800acfea  lea     rcx, [rbp+var_48]; this
0x1800acfee  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800acff3  lea     rcx, [rbp+var_48]; this
0x1800acff7  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800acffc  test    eax, eax
0x1800acffe  jz      loc_1800AD0C6
0x1800ad004  movzx   eax, word ptr [rbp+var_48+2]
0x1800ad008  sub     ax, 0Bh
0x1800ad00c  cmp     ax, 5
0x1800ad010  ja      loc_1800AD4A3
0x1800ad016  xor     eax, eax
0x1800ad018  cmp     ax, word ptr [rbp+var_30+2]
0x1800ad01c  jnz     short loc_1800AD039
0x1800ad01e  mov     eax, 2
0x1800ad023  cmp     ax, word ptr [rbp+var_30]
0x1800ad027  jz      loc_1800AD4A3
0x1800ad02d  xor     eax, eax
0x1800ad02f  cmp     ax, word ptr [rbp+var_30]
0x1800ad033  jz      loc_1800AD1D2
0x1800ad039  movzx   esi, word ptr [rbp+var_48+4]
0x1800ad03d  mov     rcx, rbx; this
0x1800ad040  add     rsi, r13
0x1800ad043  mov     rdx, rsi; unsigned __int64
0x1800ad046  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800ad04b  test    eax, eax
0x1800ad04d  js      loc_1800AD50E
0x1800ad053  mov     r8d, 2; unsigned int
0x1800ad059  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800ad05d  mov     rcx, r15; this
0x1800ad060  mov     r13, rsi
0x1800ad063  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800ad068  mov     esi, eax
0x1800ad06a  test    eax, eax
0x1800ad06c  jns     loc_1800ACFAB
0x1800ad072  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad079  test    rcx, rcx
0x1800ad07c  jnz     loc_1800AD4CC
0x1800ad082  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ad089  nop     dword ptr [rax+rax+00h]
0x1800ad08e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad095  mov     rcx, rax
0x1800ad098  test    rax, rax
0x1800ad09b  jz      loc_1800AD4BE
0x1800ad0a1  mov     rax, [rax]
0x1800ad0a4  mov     edx, 7F0h
0x1800ad0a9  mov     rax, [rax+8]
0x1800ad0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0b2  test    eax, eax
0x1800ad0b4  jz      loc_1800AD4BE
0x1800ad0ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad0c1  jmp     loc_1800AD4CC
0x1800ad0c6  lea     rdx, [r13+2]; unsigned __int64
0x1800ad0ca  mov     rcx, rbx; this
0x1800ad0cd  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800ad0d2  test    eax, eax
0x1800ad0d4  js      loc_1800AD525
0x1800ad0da  add     r13, 2
0x1800ad0de  jmp     loc_1800ACFAB
0x1800ad0e3  cmp     al, 0Bh
0x1800ad0e5  jnz     short loc_1800AD15D
0x1800ad0e7  mov     r8d, 1; unsigned int
0x1800ad0ed  mov     [rbp+var_20], al
0x1800ad0f0  lea     rdx, [rbp+var_20+1]; unsigned __int8 *
0x1800ad0f4  mov     rcx, r15; this
0x1800ad0f7  inc     r13
0x1800ad0fa  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800ad0ff  mov     esi, eax
0x1800ad101  test    eax, eax
0x1800ad103  jns     loc_1800ACFAB
0x1800ad109  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad110  test    rcx, rcx
0x1800ad113  jnz     loc_1800AD5DF
0x1800ad119  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ad120  nop     dword ptr [rax+rax+00h]
0x1800ad125  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad12c  mov     rcx, rax
0x1800ad12f  test    rax, rax
0x1800ad132  jz      loc_1800AD5D1
0x1800ad138  mov     rax, [rax]
0x1800ad13b  mov     edx, 7F0h
0x1800ad140  mov     rax, [rax+8]
0x1800ad144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad149  test    eax, eax
0x1800ad14b  jz      loc_1800AD5D1
0x1800ad151  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad158  jmp     loc_1800AD5DF
0x1800ad15d  mov     eax, 2
0x1800ad162  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800ad166  mov     r8d, eax; unsigned int
0x1800ad169  mov     rcx, r15; this
0x1800ad16c  add     r13, rax
0x1800ad16f  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800ad174  mov     esi, eax
0x1800ad176  test    eax, eax
0x1800ad178  jns     loc_1800ACFAB
0x1800ad17e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad185  test    rcx, rcx
0x1800ad188  jnz     loc_1800AD628
0x1800ad18e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ad195  nop     dword ptr [rax+rax+00h]
0x1800ad19a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad1a1  mov     rcx, rax
0x1800ad1a4  test    rax, rax
0x1800ad1a7  jz      loc_1800AD61A
0x1800ad1ad  mov     rax, [rax]
0x1800ad1b0  mov     edx, 7F0h
0x1800ad1b5  mov     rax, [rax+8]
0x1800ad1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad1be  test    eax, eax
0x1800ad1c0  jz      loc_1800AD61A
0x1800ad1c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad1cd  jmp     loc_1800AD628
0x1800ad1d2  movzx   r14d, word ptr [rbp+var_48+4]
0x1800ad1d7  mov     rcx, rbx; this
0x1800ad1da  add     r14, r13
0x1800ad1dd  mov     rdx, r14; unsigned __int64
0x1800ad1e0  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800ad1e5  test    eax, eax
0x1800ad1e7  jns     short loc_1800AD204
0x1800ad1e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800ad1f0  jb      loc_1800AD67F
0x1800ad1f6  mov     edx, 68h ; 'h'
0x1800ad1fb  mov     [rsp+80h+var_60], eax
0x1800ad1ff  jmp     loc_1800AD665
0x1800ad204  lea     rdx, [rbp+var_20]; unsigned __int64 *
0x1800ad208  mov     qword ptr [rbp+var_20], 0
0x1800ad210  mov     rcx, rbx; this
0x1800ad213  call    ?FindNextIndependentFrame@CAC3MediaSourcePlugin@@AEAAJPEA_K@Z; CAC3MediaSourcePlugin::FindNextIndependentFrame(unsigned __int64 *)
0x1800ad218  mov     esi, eax
0x1800ad21a  cmp     eax, 0C00D6590h
0x1800ad21f  jnz     loc_1800AD3EE
0x1800ad225  test    byte ptr [rbx+238h], 4
0x1800ad22c  jnz     short loc_1800AD26D
0x1800ad22e  mov     rdx, [rbx+230h]
0x1800ad235  lea     rax, [rdx-1]
0x1800ad239  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ad23d  ja      short loc_1800AD24E
0x1800ad23f  dec     rdx; unsigned __int64
0x1800ad242  mov     rcx, r15; this
0x1800ad245  call    ?HasDataAtPosition@CSourcePluginBufferReader@@QEAA_N_K@Z; CSourcePluginBufferReader::HasDataAtPosition(unsigned __int64)
0x1800ad24a  test    al, al
0x1800ad24c  jnz     short loc_1800AD26D
0x1800ad24e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800ad255  jb      loc_1800AD67F
0x1800ad25b  mov     edx, 6Ch ; 'l'
0x1800ad260  mov     [rsp+80h+var_60], 0C00D6590h
0x1800ad268  jmp     loc_1800AD665
0x1800ad26d  mov     rdx, r14; unsigned __int64
0x1800ad270  mov     rcx, rbx; this
0x1800ad273  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800ad278  test    eax, eax
0x1800ad27a  jns     short loc_1800AD293
0x1800ad27c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800ad283  jb      loc_1800AD67F
0x1800ad289  mov     edx, 69h ; 'i'
0x1800ad28e  jmp     loc_1800AD1FB
0x1800ad293  lea     rdx, [rbp+var_20]; unsigned int *
0x1800ad297  mov     dword ptr [rbp+var_20], 0
0x1800ad29e  mov     rcx, r15; this
0x1800ad2a1  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800ad2a6  mov     esi, eax
0x1800ad2a8  test    eax, eax
0x1800ad2aa  jns     loc_1800AD345
0x1800ad2b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad2b7  test    rcx, rcx
0x1800ad2ba  jnz     short loc_1800AD303
0x1800ad2bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ad2c3  nop     dword ptr [rax+rax+00h]
0x1800ad2c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad2cf  mov     rcx, rax
0x1800ad2d2  test    rax, rax
0x1800ad2d5  jz      short loc_1800AD2F5
0x1800ad2d7  mov     rax, [rax]
0x1800ad2da  mov     edx, 7F0h
0x1800ad2df  mov     rax, [rax+8]
0x1800ad2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad2e8  test    eax, eax
0x1800ad2ea  jz      short loc_1800AD2F5
0x1800ad2ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad2f3  jmp     short loc_1800AD303
0x1800ad2f5  lea     rcx, qword_1801B97E0; this
0x1800ad2fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad303  cmp     byte ptr [rcx+8], 0
0x1800ad307  jz      short loc_1800AD32E
0x1800ad309  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ad30e  cmp     [rax+7CCh], esi
0x1800ad314  jz      short loc_1800AD32E
0x1800ad316  mov     r9d, esi; int
0x1800ad319  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800ad320  mov     r8d, 553h; int
0x1800ad326  mov     rcx, rax; this
0x1800ad329  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ad32e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ad335  jb      loc_1800AD67F
0x1800ad33b  mov     edx, 6Ah ; 'j'
0x1800ad340  jmp     loc_1800AD661
0x1800ad345  mov     eax, dword ptr [rbp+var_20]
0x1800ad348  add     rax, r14
0x1800ad34b  cmp     rax, r14
0x1800ad34e  jnb     loc_1800AD48F
0x1800ad354  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad35b  test    rcx, rcx
0x1800ad35e  jnz     short loc_1800AD3A7
0x1800ad360  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ad367  nop     dword ptr [rax+rax+00h]
0x1800ad36c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ad373  mov     rcx, rax
0x1800ad376  test    rax, rax
0x1800ad379  jz      short loc_1800AD399
0x1800ad37b  mov     rax, [rax]
0x1800ad37e  mov     edx, 7F0h
0x1800ad383  mov     rax, [rax+8]
  ... truncated ...
```
