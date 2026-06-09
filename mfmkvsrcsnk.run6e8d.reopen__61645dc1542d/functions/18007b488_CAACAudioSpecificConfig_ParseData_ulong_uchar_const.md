# CAACAudioSpecificConfig::ParseData(ulong,uchar const *)

- ea: `0x18007b488`
- end: `0x18007bb15`
- name: `?ParseData@CAACAudioSpecificConfig@@QEAAJKPEBE@Z`
- size: `1677`
- prototype: `__int64 __fastcall(CAACAudioSpecificConfig *__hidden this, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x18005d764`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041538`
- `0x18006408c`
- `0x1800640f8`
- `0x180071330`
- `0x18007afdc`
- `0x18007b1a4`
- `0x18007b488`
- `0x18007fa3c`
- `0x180081210`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b5f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b698`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b8ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b531`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b5f1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b698`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b856`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b8ff`

## string_xrefs

- `0x18007b4b2`: `CAACAudioSpecificConfig::ParseData`
- `0x18007b8ad`: `CAACAudioSpecificConfig::ParseData`
- `0x18007b956`: `CAACAudioSpecificConfig::ParseData`

## pseudocode

```c
__int64 __fastcall CAACAudioSpecificConfig::ParseData(CAACAudioSpecificConfig *this, int a2, const unsigned __int8 *a3)
{
  int v6; // r12d
  __int64 v7; // rdx
  int AudioObjectType; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  int v27; // edx
  unsigned int v28; // r13d
  unsigned int v29; // r14d
  unsigned int v30; // r15d
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  int v43; // eax
  unsigned int v44; // ecx
  _BYTE v46[4]; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v47; // [rsp+34h] [rbp-45h] BYREF
  int v48; // [rsp+38h] [rbp-41h]
  unsigned int v49; // [rsp+3Ch] [rbp-3Dh]
  unsigned int v50; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v51; // [rsp+44h] [rbp-35h] BYREF
  int v52; // [rsp+48h] [rbp-31h]
  unsigned int v53; // [rsp+4Ch] [rbp-2Dh]
  unsigned int v54; // [rsp+50h] [rbp-29h] BYREF
  int v55; // [rsp+54h] [rbp-25h]
  unsigned int v56; // [rsp+58h] [rbp-21h] BYREF
  unsigned int v57; // [rsp+5Ch] [rbp-1Dh] BYREF
  int v58; // [rsp+60h] [rbp-19h] BYREF
  const unsigned __int8 *v59; // [rsp+68h] [rbp-11h] BYREF
  int v60; // [rsp+70h] [rbp-9h]
  int v61; // [rsp+74h] [rbp-5h]
  int v62; // [rsp+78h] [rbp-1h]
  __int16 v63; // [rsp+7Ch] [rbp+3h]

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v46, "CAACAudioSpecificConfig::ParseData", 313);
  v6 = 0;
  v59 = a3;
  v60 = 0;
  v61 = a2;
  v62 = 0;
  v63 = 256;
  v47 = 0;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v50 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  AudioObjectType = CAACAudioSpecificConfig::GetAudioObjectType((struct CBitstreamReader *)&v59, &v47);
  if ( AudioObjectType < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != AudioObjectType )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAACAudioSpecificConfig::ParseData",
          335,
          AudioObjectType);
    }
    if ( g_wppLevels )
    {
      v14 = 11;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids,
        this,
        AudioObjectType);
      goto LABEL_102;
    }
    goto LABEL_102;
  }
  AudioObjectType = CAACAudioSpecificConfig::GetSamplingFrequency((struct CBitstreamReader *)&v59, &v54);
  if ( AudioObjectType >= 0 )
  {
    AudioObjectType = CBitstreamReader::PopN((CBitstreamReader *)&v59, 4, &v50);
    if ( AudioObjectType < 0 )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22, v23);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
        if ( *((_DWORD *)v26 + 499) != AudioObjectType )
          CallStackContext::TraceFailure(v26, "CAACAudioSpecificConfig::ParseData", 342, AudioObjectType);
      }
      if ( g_wppLevels )
      {
        v14 = 13;
        goto LABEL_12;
      }
      goto LABEL_102;
    }
    v52 = 1;
    v27 = 0;
    v48 = 0;
    v28 = 0;
    v49 = 0;
    v55 = 0;
    if ( v50 )
    {
      switch ( v50 )
      {
        case 1u:
        case 2u:
        case 3u:
        case 4u:
        case 5u:
          v28 = v50;
          v49 = 0;
          goto LABEL_53;
        case 6u:
          v28 = 5;
          break;
        case 7u:
          v28 = 7;
          break;
        default:
          if ( byte_1800D78D1 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, v50);
            v27 = 0;
          }
          v52 = 0;
          goto LABEL_53;
      }
      v49 = 1;
      goto LABEL_53;
    }
    if ( (unsigned __int8)byte_1800D78D1 >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
    v27 = 1;
    v48 = 1;
LABEL_53:
    v29 = v47;
    if ( v47 == 5 || v47 == 29 )
    {
      if ( (unsigned __int8)byte_1800D78D1 >= 0x10u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
      if ( v29 == 29 )
      {
        v55 = 1;
        if ( (unsigned __int8)byte_1800D78D1 >= 0x10u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
      }
      AudioObjectType = CAACAudioSpecificConfig::GetSamplingFrequency((struct CBitstreamReader *)&v59, &v51);
      if ( AudioObjectType < 0 )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != AudioObjectType )
            CallStackContext::TraceFailure(v36, "CAACAudioSpecificConfig::ParseData", 393, AudioObjectType);
        }
        if ( g_wppLevels )
        {
          v14 = 18;
          goto LABEL_12;
        }
        goto LABEL_102;
      }
      AudioObjectType = CAACAudioSpecificConfig::GetAudioObjectType((struct CBitstreamReader *)&v59, &v47);
      if ( AudioObjectType < 0 )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != AudioObjectType )
            CallStackContext::TraceFailure(v42, "CAACAudioSpecificConfig::ParseData", 395, AudioObjectType);
        }
        if ( g_wppLevels )
        {
          v14 = 19;
          goto LABEL_12;
        }
        goto LABEL_102;
      }
      v30 = 5;
      v29 = v47;
      v27 = v48;
      v53 = v51;
      v6 = 1;
    }
    else
    {
      v30 = 0;
    }
    if ( v29 <= 0x17
      && (v43 = 16384222, _bittest(&v43, v29))
      && (int)CAACAudioSpecificConfig::ParseGASpecificConfig(
                (struct CBitstreamReader *)&v59,
                v29,
                v27,
                &v56,
                &v57,
                &v58) >= 0 )
    {
      if ( v48 )
      {
        v28 = v56;
        v49 = v57;
        if ( (unsigned __int8)byte_1800D78D1 >= 0x10u )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, v56, v57);
      }
    }
    else if ( v48 )
    {
      if ( byte_1800D78D1 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
      v52 = 0;
    }
    if ( v58 )
    {
      if ( v30 != 5 && (unsigned int)(8 * (v61 - v60) - v62) >= 0x10 )
      {
        v50 = 0;
        v51 = 0;
        v47 = 0;
        if ( (int)CAACAudioSpecificConfig::ParseSyncExtension((struct CBitstreamReader *)&v59, (int *)&v50, &v51, &v47) >= 0 )
        {
          v30 = v51;
          if ( v50 )
          {
            v6 = 1;
            v53 = v47;
            if ( (unsigned __int8)byte_1800D78D1 >= 0x10u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
          }
        }
      }
    }
    v44 = v54;
    *(_DWORD *)this = v52;
    *((_DWORD *)this + 4) = v49;
    *((_DWORD *)this + 6) = v53;
    *((_DWORD *)this + 8) = v55;
    *((_DWORD *)this + 1) = v29;
    *((_DWORD *)this + 2) = v44;
    *((_DWORD *)this + 3) = v28;
    *((_DWORD *)this + 5) = v30;
    *((_DWORD *)this + 7) = v6;
    goto LABEL_102;
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
    if ( *((_DWORD *)v20 + 499) != AudioObjectType )
      CallStackContext::TraceFailure(v20, "CAACAudioSpecificConfig::ParseData", 337, AudioObjectType);
  }
  if ( g_wppLevels )
  {
    v14 = 12;
    goto LABEL_12;
  }
LABEL_102:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v46);
  return (unsigned int)AudioObjectType;
}

```

## disassembly

```asm
0x18007b488  push    rbp
0x18007b48a  push    rbx
0x18007b48b  push    rsi
0x18007b48c  push    rdi
0x18007b48d  push    r12
0x18007b48f  push    r13
0x18007b491  push    r14
0x18007b493  push    r15
0x18007b495  lea     rbp, [rsp-1Fh]
0x18007b49a  sub     rsp, 98h
0x18007b4a1  mov     rax, cs:__security_cookie
0x18007b4a8  xor     rax, rsp
0x18007b4ab  mov     [rbp+57h+var_50], rax
0x18007b4af  mov     rbx, r8
0x18007b4b2  lea     r14, aCaacaudiospeci_2; "CAACAudioSpecificConfig::ParseData"
0x18007b4b9  mov     edi, edx
0x18007b4bb  mov     rsi, rcx
0x18007b4be  mov     rdx, r14; char *
0x18007b4c1  lea     rcx, [rbp+57h+var_A0]; this
0x18007b4c5  mov     r8d, 139h; int
0x18007b4cb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007b4d0  xor     r12d, r12d
0x18007b4d3  mov     [rbp+57h+var_68], rbx
0x18007b4d7  mov     eax, r12d
0x18007b4da  mov     [rbp+57h+var_60], r12d
0x18007b4de  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x18007b4e2  mov     [rbp+57h+var_5C], edi
0x18007b4e5  lea     rcx, [rbp+57h+var_68]; this
0x18007b4e9  mov     [rbp+57h+var_58], r12d
0x18007b4ed  lea     r15d, [r12+1]
0x18007b4f2  mov     [rbp+57h+var_54], 100h
0x18007b4f8  mov     [rbp+57h+var_9C], r12d
0x18007b4fc  mov     [rbp+57h+var_80], r12d
0x18007b500  mov     [rbp+57h+var_84], eax
0x18007b503  mov     [rbp+57h+var_8C], eax
0x18007b506  mov     [rbp+57h+var_90], r12d
0x18007b50a  mov     [rbp+57h+var_78], r12d
0x18007b50e  mov     [rbp+57h+var_74], r12d
0x18007b512  mov     [rbp+57h+var_70], r12d
0x18007b516  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x18007b51b  mov     ebx, eax
0x18007b51d  test    eax, eax
0x18007b51f  jns     loc_18007B5CE
0x18007b525  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b52c  test    rcx, rcx
0x18007b52f  jnz     short loc_18007B572
0x18007b531  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b537  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b53e  mov     rcx, rax
0x18007b541  test    rax, rax
0x18007b544  jz      short loc_18007B564
0x18007b546  mov     rax, [rax]
0x18007b549  mov     edx, 7F0h
0x18007b54e  mov     rax, [rax+8]
0x18007b552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b557  test    eax, eax
0x18007b559  jz      short loc_18007B564
0x18007b55b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b562  jmp     short loc_18007B572
0x18007b564  lea     rcx, qword_1800D6F70; this
0x18007b56b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b572  cmp     [rcx+8], r12b
0x18007b576  jz      short loc_18007B599
0x18007b578  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b57d  cmp     [rax+7CCh], ebx
0x18007b583  jz      short loc_18007B599
0x18007b585  mov     r9d, ebx; int
0x18007b588  mov     r8d, 14Fh; int
0x18007b58e  mov     rdx, r14; char *
0x18007b591  mov     rcx, rax; this
0x18007b594  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b599  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007b5a0  jb      loc_18007BAEA
0x18007b5a6  mov     edx, 0Bh
0x18007b5ab  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007b5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b5b9  mov     r9, rsi
0x18007b5bc  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18007b5c0  mov     rcx, [rcx+10h]
0x18007b5c4  call    WPP_SF_qD
0x18007b5c9  jmp     loc_18007BAEA
0x18007b5ce  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x18007b5d2  lea     rcx, [rbp+57h+var_68]; this
0x18007b5d6  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x18007b5db  mov     ebx, eax
0x18007b5dd  test    eax, eax
0x18007b5df  jns     loc_18007B670
0x18007b5e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b5ec  test    rcx, rcx
0x18007b5ef  jnz     short loc_18007B632
0x18007b5f1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b5f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b5fe  mov     rcx, rax
0x18007b601  test    rax, rax
0x18007b604  jz      short loc_18007B624
0x18007b606  mov     rax, [rax]
0x18007b609  mov     edx, 7F0h
0x18007b60e  mov     rax, [rax+8]
0x18007b612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b617  test    eax, eax
0x18007b619  jz      short loc_18007B624
0x18007b61b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b622  jmp     short loc_18007B632
0x18007b624  lea     rcx, qword_1800D6F70; this
0x18007b62b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b632  cmp     [rcx+8], r12b
0x18007b636  jz      short loc_18007B659
0x18007b638  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b63d  cmp     [rax+7CCh], ebx
0x18007b643  jz      short loc_18007B659
0x18007b645  mov     r9d, ebx; int
0x18007b648  mov     r8d, 151h; int
0x18007b64e  mov     rdx, r14; char *
0x18007b651  mov     rcx, rax; this
0x18007b654  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b659  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007b660  jb      loc_18007BAEA
0x18007b666  mov     edx, 0Ch
0x18007b66b  jmp     loc_18007B5AB
0x18007b670  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18007b674  mov     edx, 4; int
0x18007b679  lea     rcx, [rbp+57h+var_68]; this
0x18007b67d  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007b682  mov     ebx, eax
0x18007b684  test    eax, eax
0x18007b686  jns     loc_18007B717
0x18007b68c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b693  test    rcx, rcx
0x18007b696  jnz     short loc_18007B6D9
0x18007b698  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b69e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b6a5  mov     rcx, rax
0x18007b6a8  test    rax, rax
0x18007b6ab  jz      short loc_18007B6CB
0x18007b6ad  mov     rax, [rax]
0x18007b6b0  mov     edx, 7F0h
0x18007b6b5  mov     rax, [rax+8]
0x18007b6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b6be  test    eax, eax
0x18007b6c0  jz      short loc_18007B6CB
0x18007b6c2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b6c9  jmp     short loc_18007B6D9
0x18007b6cb  lea     rcx, qword_1800D6F70; this
0x18007b6d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b6d9  cmp     [rcx+8], r12b
0x18007b6dd  jz      short loc_18007B700
0x18007b6df  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b6e4  cmp     [rax+7CCh], ebx
0x18007b6ea  jz      short loc_18007B700
0x18007b6ec  mov     r9d, ebx; int
0x18007b6ef  mov     r8d, 156h; int
0x18007b6f5  mov     rdx, r14; char *
0x18007b6f8  mov     rcx, rax; this
0x18007b6fb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b700  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007b707  jb      loc_18007BAEA
0x18007b70d  mov     edx, 0Dh
0x18007b712  jmp     loc_18007B5AB
0x18007b717  mov     ecx, [rbp+57h+var_90]
0x18007b71a  lea     rdi, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007b721  mov     [rbp+57h+var_88], r15d
0x18007b725  mov     edx, r12d
0x18007b728  mov     [rbp+57h+var_98], edx
0x18007b72b  mov     r13d, r12d
0x18007b72e  mov     [rbp+57h+var_94], r12d
0x18007b732  mov     eax, ecx
0x18007b734  mov     [rbp+57h+var_7C], r12d
0x18007b738  test    ecx, ecx
0x18007b73a  jz      short loc_18007B7A9
0x18007b73c  sub     eax, r15d
0x18007b73f  jz      short loc_18007B7A0
0x18007b741  sub     eax, r15d
0x18007b744  jz      short loc_18007B7A0
0x18007b746  sub     eax, r15d
0x18007b749  jz      short loc_18007B7A0
0x18007b74b  sub     eax, r15d
0x18007b74e  jz      short loc_18007B7A0
0x18007b750  sub     eax, r15d
0x18007b753  jz      short loc_18007B7A0
0x18007b755  sub     eax, r15d
0x18007b758  jz      short loc_18007B794
0x18007b75a  cmp     eax, r15d
0x18007b75d  jz      short loc_18007B78C
0x18007b75f  cmp     cs:byte_1800D78D1, r15b
0x18007b766  jb      short loc_18007B786
0x18007b768  mov     r9d, ecx
0x18007b76b  mov     edx, 0Fh
0x18007b770  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b777  mov     r8, rdi
0x18007b77a  mov     rcx, [rcx+38h]
0x18007b77e  call    WPP_SF_d
0x18007b783  mov     edx, r12d
0x18007b786  mov     [rbp+57h+var_88], r12d
0x18007b78a  jmp     short loc_18007B7D0
0x18007b78c  mov     r13d, 7
0x18007b792  jmp     short loc_18007B79A
0x18007b794  mov     r13d, 5
0x18007b79a  mov     [rbp+57h+var_94], r15d
0x18007b79e  jmp     short loc_18007B7D0
0x18007b7a0  mov     r13d, ecx
0x18007b7a3  mov     [rbp+57h+var_94], r12d
0x18007b7a7  jmp     short loc_18007B7D0
0x18007b7a9  cmp     cs:byte_1800D78D1, 10h
0x18007b7b0  jb      short loc_18007B7CA
0x18007b7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7b9  mov     edx, 0Eh
0x18007b7be  mov     r8, rdi
0x18007b7c1  mov     rcx, [rcx+38h]
0x18007b7c5  call    WPP_SF_
0x18007b7ca  mov     edx, r15d
0x18007b7cd  mov     [rbp+57h+var_98], edx
0x18007b7d0  mov     r14d, [rbp+57h+var_9C]
0x18007b7d4  cmp     r14d, 5
0x18007b7d8  jz      short loc_18007B7E8
0x18007b7da  cmp     r14d, 1Dh
0x18007b7de  jz      short loc_18007B7E8
0x18007b7e0  mov     r15d, r12d
0x18007b7e3  jmp     loc_18007B999
0x18007b7e8  cmp     cs:byte_1800D78D1, 10h
0x18007b7ef  jb      short loc_18007B809
0x18007b7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b7f8  mov     edx, 10h
0x18007b7fd  mov     r8, rdi
0x18007b800  mov     rcx, [rcx+38h]
0x18007b804  call    WPP_SF_
0x18007b809  cmp     r14d, 1Dh
0x18007b80d  jnz     short loc_18007B833
0x18007b80f  mov     [rbp+57h+var_7C], r15d
0x18007b813  cmp     cs:byte_1800D78D1, 10h
0x18007b81a  jb      short loc_18007B833
0x18007b81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b823  lea     edx, [r14-0Ch]
0x18007b827  mov     r8, rdi
0x18007b82a  mov     rcx, [rcx+38h]
0x18007b82e  call    WPP_SF_
0x18007b833  lea     rdx, [rbp+57h+var_8C]; unsigned int *
0x18007b837  lea     rcx, [rbp+57h+var_68]; this
0x18007b83b  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x18007b840  mov     ebx, eax
0x18007b842  test    eax, eax
0x18007b844  jns     loc_18007B8DC
0x18007b84a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b851  test    rcx, rcx
0x18007b854  jnz     short loc_18007B897
0x18007b856  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b85c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b863  mov     rcx, rax
0x18007b866  test    rax, rax
0x18007b869  jz      short loc_18007B889
0x18007b86b  mov     rax, [rax]
0x18007b86e  mov     edx, 7F0h
0x18007b873  mov     rax, [rax+8]
0x18007b877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b87c  test    eax, eax
0x18007b87e  jz      short loc_18007B889
0x18007b880  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b887  jmp     short loc_18007B897
0x18007b889  lea     rcx, qword_1800D6F70; this
0x18007b890  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b897  cmp     [rcx+8], r12b
0x18007b89b  jz      short loc_18007B8C2
0x18007b89d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b8a2  cmp     [rax+7CCh], ebx
0x18007b8a8  jz      short loc_18007B8C2
0x18007b8aa  mov     r9d, ebx; int
0x18007b8ad  lea     rdx, aCaacaudiospeci_2; "CAACAudioSpecificConfig::ParseData"
0x18007b8b4  mov     r8d, 189h; int
0x18007b8ba  mov     rcx, rax; this
0x18007b8bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b8c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007b8c9  jb      loc_18007BAEA
0x18007b8cf  mov     edx, 12h
0x18007b8d4  mov     r8, rdi
0x18007b8d7  jmp     loc_18007B5B2
0x18007b8dc  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x18007b8e0  lea     rcx, [rbp+57h+var_68]; this
0x18007b8e4  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x18007b8e9  mov     ebx, eax
0x18007b8eb  test    eax, eax
0x18007b8ed  jns     loc_18007B982
0x18007b8f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b8fa  test    rcx, rcx
0x18007b8fd  jnz     short loc_18007B940
0x18007b8ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b905  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b90c  mov     rcx, rax
0x18007b90f  test    rax, rax
0x18007b912  jz      short loc_18007B932
0x18007b914  mov     rax, [rax]
0x18007b917  mov     edx, 7F0h
0x18007b91c  mov     rax, [rax+8]
0x18007b920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b925  test    eax, eax
0x18007b927  jz      short loc_18007B932
0x18007b929  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b930  jmp     short loc_18007B940
0x18007b932  lea     rcx, qword_1800D6F70; this
0x18007b939  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b940  cmp     [rcx+8], r12b
0x18007b944  jz      short loc_18007B96B
  ... truncated ...
```
