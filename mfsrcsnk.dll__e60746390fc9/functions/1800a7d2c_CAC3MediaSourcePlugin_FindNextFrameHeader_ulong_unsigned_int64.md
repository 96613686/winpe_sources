# CAC3MediaSourcePlugin::FindNextFrameHeader(ulong *,unsigned __int64 *)

- ea: `0x1800a7d2c`
- end: `0x1800a8521`
- name: `?FindNextFrameHeader@CAC3MediaSourcePlugin@@AEAAHPEAKPEA_K@Z`
- size: `2037`
- prototype: `__int64 __fastcall(CAC3MediaSourcePlugin *__hidden this, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800c2d10`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800370f0`
- `0x18003b91c`
- `0x180073b14`
- `0x180080520`
- `0x1800a3694`
- `0x1800a7d2c`
- `0x1801099f0`
- `0x180130c90`
- `0x180130ce0`
- `0x180131e30`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7dc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7f1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7fad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a801c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8144`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a81e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a827e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a83be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7dc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7f1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a7fad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a801c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8144`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a81e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a827e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a83be`

## string_xrefs

- `0x1800a7d71`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a7e19`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a819b`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a823e`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a82d5`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a8358`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a8415`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a8465`: `CAC3MediaSourcePlugin::FindNextFrameHeader`
- `0x1800a84ae`: `CAC3MediaSourcePlugin::FindNextFrameHeader`

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
        v9 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v42 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v30 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v34 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v37 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v17 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v23 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v20 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800a7d2c  push    rbp
0x1800a7d2e  push    rbx
0x1800a7d2f  push    rsi
0x1800a7d30  push    r12
0x1800a7d32  push    r13
0x1800a7d34  push    r14
0x1800a7d36  push    r15
0x1800a7d38  mov     rbp, rsp
0x1800a7d3b  sub     rsp, 80h
0x1800a7d42  mov     rax, cs:__security_cookie
0x1800a7d49  xor     rax, rsp
0x1800a7d4c  mov     [rbp+var_10], rax
0x1800a7d50  xor     eax, eax
0x1800a7d52  mov     [rbp+var_28], r8
0x1800a7d56  mov     [rdx], eax
0x1800a7d58  mov     r14, r8
0x1800a7d5b  mov     [r8], rax
0x1800a7d5e  mov     r12, rdx
0x1800a7d61  mov     rbx, rcx
0x1800a7d64  mov     [rbp+var_48], rax
0x1800a7d68  mov     r8d, 520h; int
0x1800a7d6e  mov     [rbp+var_40], eax
0x1800a7d71  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800a7d78  mov     [rbp+var_3C], ax
0x1800a7d7c  lea     rcx, [rbp+var_50]; this
0x1800a7d80  mov     [rbp+var_38], rax
0x1800a7d84  mov     [rbp+var_30], eax
0x1800a7d87  mov     [rbp+var_4C], eax
0x1800a7d8a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a7d8f  lea     r15, [rbx+30h]
0x1800a7d93  mov     r8d, 2; unsigned int
0x1800a7d99  mov     r13, [r15+1D8h]
0x1800a7da0  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800a7da4  mov     rcx, r15; this
0x1800a7da7  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a7dac  mov     esi, eax
0x1800a7dae  test    eax, eax
0x1800a7db0  jns     loc_1800A7E45
0x1800a7db6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7dbd  test    rcx, rcx
0x1800a7dc0  jnz     short loc_1800A7E03
0x1800a7dc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a7dc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7dcf  mov     rcx, rax
0x1800a7dd2  test    rax, rax
0x1800a7dd5  jz      short loc_1800A7DF5
0x1800a7dd7  mov     rax, [rax]
0x1800a7dda  mov     edx, 7F0h
0x1800a7ddf  mov     rax, [rax+8]
0x1800a7de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7de8  test    eax, eax
0x1800a7dea  jz      short loc_1800A7DF5
0x1800a7dec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7df3  jmp     short loc_1800A7E03
0x1800a7df5  lea     rcx, qword_1801B07E0; this
0x1800a7dfc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7e03  cmp     byte ptr [rcx+8], 0
0x1800a7e07  jz      short loc_1800A7E2E
0x1800a7e09  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a7e0e  cmp     [rax+7CCh], esi
0x1800a7e14  jz      short loc_1800A7E2E
0x1800a7e16  mov     r9d, esi; int
0x1800a7e19  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800a7e20  mov     r8d, 521h; int
0x1800a7e26  mov     rcx, rax; this
0x1800a7e29  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a7e2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a7e35  jb      loc_1800A84EF
0x1800a7e3b  mov     edx, 66h ; 'f'
0x1800a7e40  jmp     loc_1800A84D1
0x1800a7e45  cmp     [rbp+var_20], 0Bh
0x1800a7e49  mov     al, [rbp+var_20+1]
0x1800a7e4c  jnz     short loc_1800A7E52
0x1800a7e4e  cmp     al, 77h ; 'w'
0x1800a7e50  jz      short loc_1800A7E64
0x1800a7e52  cmp     [rbp+var_20], 77h ; 'w'
0x1800a7e56  jnz     loc_1800A7F77
0x1800a7e5c  cmp     al, 0Bh
0x1800a7e5e  jnz     loc_1800A7FEB
0x1800a7e64  mov     r8d, 0Ah; unsigned int
0x1800a7e6a  lea     rdx, [rbp+var_20+2]; unsigned __int8 *
0x1800a7e6e  mov     rcx, r15; this
0x1800a7e71  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a7e76  mov     esi, eax
0x1800a7e78  test    eax, eax
0x1800a7e7a  js      loc_1800A83B2
0x1800a7e80  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800a7e84  lea     rcx, [rbp+var_48]; this
0x1800a7e88  call    ?Parse@CAC3FrameHeader@@QEAAXPEAE@Z; CAC3FrameHeader::Parse(uchar *)
0x1800a7e8d  lea     rcx, [rbp+var_48]; this
0x1800a7e91  call    ?IsValidFrameHeader@CAC3FrameHeader@@QEAAHXZ; CAC3FrameHeader::IsValidFrameHeader(void)
0x1800a7e96  test    eax, eax
0x1800a7e98  jz      loc_1800A7F5A
0x1800a7e9e  movzx   eax, word ptr [rbp+var_48+2]
0x1800a7ea2  sub     ax, 0Bh
0x1800a7ea6  cmp     ax, 5
0x1800a7eaa  ja      loc_1800A8319
0x1800a7eb0  xor     eax, eax
0x1800a7eb2  cmp     ax, word ptr [rbp+var_30+2]
0x1800a7eb6  jnz     short loc_1800A7ED3
0x1800a7eb8  mov     eax, 2
0x1800a7ebd  cmp     ax, word ptr [rbp+var_30]
0x1800a7ec1  jz      loc_1800A8319
0x1800a7ec7  xor     eax, eax
0x1800a7ec9  cmp     ax, word ptr [rbp+var_30]
0x1800a7ecd  jz      loc_1800A805A
0x1800a7ed3  movzx   esi, word ptr [rbp+var_48+4]
0x1800a7ed7  mov     rcx, rbx; this
0x1800a7eda  add     rsi, r13
0x1800a7edd  mov     rdx, rsi; unsigned __int64
0x1800a7ee0  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a7ee5  test    eax, eax
0x1800a7ee7  js      loc_1800A8384
0x1800a7eed  mov     r8d, 2; unsigned int
0x1800a7ef3  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800a7ef7  mov     rcx, r15; this
0x1800a7efa  mov     r13, rsi
0x1800a7efd  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a7f02  mov     esi, eax
0x1800a7f04  test    eax, eax
0x1800a7f06  jns     loc_1800A7E45
0x1800a7f0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7f13  test    rcx, rcx
0x1800a7f16  jnz     loc_1800A8342
0x1800a7f1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a7f22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7f29  mov     rcx, rax
0x1800a7f2c  test    rax, rax
0x1800a7f2f  jz      loc_1800A8334
0x1800a7f35  mov     rax, [rax]
0x1800a7f38  mov     edx, 7F0h
0x1800a7f3d  mov     rax, [rax+8]
0x1800a7f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7f46  test    eax, eax
0x1800a7f48  jz      loc_1800A8334
0x1800a7f4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7f55  jmp     loc_1800A8342
0x1800a7f5a  lea     rdx, [r13+2]; unsigned __int64
0x1800a7f5e  mov     rcx, rbx; this
0x1800a7f61  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a7f66  test    eax, eax
0x1800a7f68  js      loc_1800A839B
0x1800a7f6e  add     r13, 2
0x1800a7f72  jmp     loc_1800A7E45
0x1800a7f77  cmp     al, 0Bh
0x1800a7f79  jnz     short loc_1800A7FEB
0x1800a7f7b  mov     r8d, 1; unsigned int
0x1800a7f81  mov     [rbp+var_20], al
0x1800a7f84  lea     rdx, [rbp+var_20+1]; unsigned __int8 *
0x1800a7f88  mov     rcx, r15; this
0x1800a7f8b  inc     r13
0x1800a7f8e  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a7f93  mov     esi, eax
0x1800a7f95  test    eax, eax
0x1800a7f97  jns     loc_1800A7E45
0x1800a7f9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7fa4  test    rcx, rcx
0x1800a7fa7  jnz     loc_1800A844F
0x1800a7fad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a7fb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7fba  mov     rcx, rax
0x1800a7fbd  test    rax, rax
0x1800a7fc0  jz      loc_1800A8441
0x1800a7fc6  mov     rax, [rax]
0x1800a7fc9  mov     edx, 7F0h
0x1800a7fce  mov     rax, [rax+8]
0x1800a7fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7fd7  test    eax, eax
0x1800a7fd9  jz      loc_1800A8441
0x1800a7fdf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a7fe6  jmp     loc_1800A844F
0x1800a7feb  mov     eax, 2
0x1800a7ff0  lea     rdx, [rbp+var_20]; unsigned __int8 *
0x1800a7ff4  mov     r8d, eax; unsigned int
0x1800a7ff7  mov     rcx, r15; this
0x1800a7ffa  add     r13, rax
0x1800a7ffd  call    ?Read@CSourcePluginBufferReader@@QEAAJPEAEK@Z; CSourcePluginBufferReader::Read(uchar *,ulong)
0x1800a8002  mov     esi, eax
0x1800a8004  test    eax, eax
0x1800a8006  jns     loc_1800A7E45
0x1800a800c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8013  test    rcx, rcx
0x1800a8016  jnz     loc_1800A8498
0x1800a801c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8022  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8029  mov     rcx, rax
0x1800a802c  test    rax, rax
0x1800a802f  jz      loc_1800A848A
0x1800a8035  mov     rax, [rax]
0x1800a8038  mov     edx, 7F0h
0x1800a803d  mov     rax, [rax+8]
0x1800a8041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8046  test    eax, eax
0x1800a8048  jz      loc_1800A848A
0x1800a804e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8055  jmp     loc_1800A8498
0x1800a805a  movzx   r14d, word ptr [rbp+var_48+4]
0x1800a805f  mov     rcx, rbx; this
0x1800a8062  add     r14, r13
0x1800a8065  mov     rdx, r14; unsigned __int64
0x1800a8068  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a806d  test    eax, eax
0x1800a806f  jns     short loc_1800A808C
0x1800a8071  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800a8078  jb      loc_1800A84EF
0x1800a807e  mov     edx, 68h ; 'h'
0x1800a8083  mov     [rsp+80h+var_60], eax
0x1800a8087  jmp     loc_1800A84D5
0x1800a808c  lea     rdx, [rbp+var_20]; unsigned __int64 *
0x1800a8090  mov     qword ptr [rbp+var_20], 0
0x1800a8098  mov     rcx, rbx; this
0x1800a809b  call    ?FindNextIndependentFrame@CAC3MediaSourcePlugin@@AEAAJPEA_K@Z; CAC3MediaSourcePlugin::FindNextIndependentFrame(unsigned __int64 *)
0x1800a80a0  mov     esi, eax
0x1800a80a2  cmp     eax, 0C00D6590h
0x1800a80a7  jnz     loc_1800A826A
0x1800a80ad  test    byte ptr [rbx+238h], 4
0x1800a80b4  jnz     short loc_1800A80F5
0x1800a80b6  mov     rdx, [rbx+230h]
0x1800a80bd  lea     rax, [rdx-1]
0x1800a80c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a80c5  ja      short loc_1800A80D6
0x1800a80c7  dec     rdx; unsigned __int64
0x1800a80ca  mov     rcx, r15; this
0x1800a80cd  call    ?HasDataAtPosition@CSourcePluginBufferReader@@QEAA_N_K@Z; CSourcePluginBufferReader::HasDataAtPosition(unsigned __int64)
0x1800a80d2  test    al, al
0x1800a80d4  jnz     short loc_1800A80F5
0x1800a80d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800a80dd  jb      loc_1800A84EF
0x1800a80e3  mov     edx, 6Ch ; 'l'
0x1800a80e8  mov     [rsp+80h+var_60], 0C00D6590h
0x1800a80f0  jmp     loc_1800A84D5
0x1800a80f5  mov     rdx, r14; unsigned __int64
0x1800a80f8  mov     rcx, rbx; this
0x1800a80fb  call    ?TrySetBufferReaderPosition@CAC3MediaSourcePlugin@@AEAAJ_K@Z; CAC3MediaSourcePlugin::TrySetBufferReaderPosition(unsigned __int64)
0x1800a8100  test    eax, eax
0x1800a8102  jns     short loc_1800A811B
0x1800a8104  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x1800a810b  jb      loc_1800A84EF
0x1800a8111  mov     edx, 69h ; 'i'
0x1800a8116  jmp     loc_1800A8083
0x1800a811b  lea     rdx, [rbp+var_20]; unsigned int *
0x1800a811f  mov     dword ptr [rbp+var_20], 0
0x1800a8126  mov     rcx, r15; this
0x1800a8129  call    ?GetAvailableBufferSize@CSourcePluginBufferReader@@QEAAJPEAK@Z; CSourcePluginBufferReader::GetAvailableBufferSize(ulong *)
0x1800a812e  mov     esi, eax
0x1800a8130  test    eax, eax
0x1800a8132  jns     loc_1800A81C7
0x1800a8138  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a813f  test    rcx, rcx
0x1800a8142  jnz     short loc_1800A8185
0x1800a8144  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a814a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8151  mov     rcx, rax
0x1800a8154  test    rax, rax
0x1800a8157  jz      short loc_1800A8177
0x1800a8159  mov     rax, [rax]
0x1800a815c  mov     edx, 7F0h
0x1800a8161  mov     rax, [rax+8]
0x1800a8165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a816a  test    eax, eax
0x1800a816c  jz      short loc_1800A8177
0x1800a816e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8175  jmp     short loc_1800A8185
0x1800a8177  lea     rcx, qword_1801B07E0; this
0x1800a817e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8185  cmp     byte ptr [rcx+8], 0
0x1800a8189  jz      short loc_1800A81B0
0x1800a818b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8190  cmp     [rax+7CCh], esi
0x1800a8196  jz      short loc_1800A81B0
0x1800a8198  mov     r9d, esi; int
0x1800a819b  lea     rdx, aCac3mediasourc_14; "CAC3MediaSourcePlugin::FindNextFrameHea"...
0x1800a81a2  mov     r8d, 553h; int
0x1800a81a8  mov     rcx, rax; this
0x1800a81ab  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a81b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a81b7  jb      loc_1800A84EF
0x1800a81bd  mov     edx, 6Ah ; 'j'
0x1800a81c2  jmp     loc_1800A84D1
0x1800a81c7  mov     eax, dword ptr [rbp+var_20]
0x1800a81ca  add     rax, r14
0x1800a81cd  cmp     rax, r14
0x1800a81d0  jnb     loc_1800A8305
0x1800a81d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a81dd  test    rcx, rcx
0x1800a81e0  jnz     short loc_1800A8223
0x1800a81e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a81e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a81ef  mov     rcx, rax
0x1800a81f2  test    rax, rax
0x1800a81f5  jz      short loc_1800A8215
0x1800a81f7  mov     rax, [rax]
0x1800a81fa  mov     edx, 7F0h
0x1800a81ff  mov     rax, [rax+8]
0x1800a8203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8208  test    eax, eax
0x1800a820a  jz      short loc_1800A8215
0x1800a820c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8213  jmp     short loc_1800A8223
0x1800a8215  lea     rcx, qword_1801B07E0; this
  ... truncated ...
```
