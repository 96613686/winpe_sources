# CAACAudioSpecificConfig::ParseData(ulong,uchar const *)

- ea: `0x18007ec30`
- end: `0x18007f2dc`
- name: `?ParseData@CAACAudioSpecificConfig@@QEAAJKPEBE@Z`
- size: `1708`
- prototype: `__int64 __fastcall(CAACAudioSpecificConfig *__hidden this, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x18005ff50`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800432a8`
- `0x180066af0`
- `0x180066b6c`
- `0x1800744d8`
- `0x18007e76c`
- `0x18007e940`
- `0x18007ec30`
- `0x1800833ec`
- `0x180084c84`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ecd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ed9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ee4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f0bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ecd9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ed9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007ee4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f010`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007f0bf`

## string_xrefs

- `0x18007ec5a`: `CAACAudioSpecificConfig::ParseData`
- `0x18007f06d`: `CAACAudioSpecificConfig::ParseData`
- `0x18007f11c`: `CAACAudioSpecificConfig::ParseData`

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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v24 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          if ( byte_1800DC8D1 )
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
    if ( (unsigned __int8)byte_1800DC8D1 >= 0x10u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
    v27 = 1;
    v48 = 1;
LABEL_53:
    v29 = v47;
    if ( v47 == 5 || v47 == 29 )
    {
      if ( (unsigned __int8)byte_1800DC8D1 >= 0x10u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids);
      if ( v29 == 29 )
      {
        v55 = 1;
        if ( (unsigned __int8)byte_1800DC8D1 >= 0x10u )
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
            v34 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v40 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        if ( (unsigned __int8)byte_1800DC8D1 >= 0x10u )
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, v56, v57);
      }
    }
    else if ( v48 )
    {
      if ( byte_1800DC8D1 )
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
            if ( (unsigned __int8)byte_1800DC8D1 >= 0x10u )
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
      v18 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18007ec30  push    rbp
0x18007ec32  push    rbx
0x18007ec33  push    rsi
0x18007ec34  push    rdi
0x18007ec35  push    r12
0x18007ec37  push    r13
0x18007ec39  push    r14
0x18007ec3b  push    r15
0x18007ec3d  lea     rbp, [rsp-1Fh]
0x18007ec42  sub     rsp, 98h
0x18007ec49  mov     rax, cs:__security_cookie
0x18007ec50  xor     rax, rsp
0x18007ec53  mov     [rbp+57h+var_50], rax
0x18007ec57  mov     rbx, r8
0x18007ec5a  lea     r14, aCaacaudiospeci_2; "CAACAudioSpecificConfig::ParseData"
0x18007ec61  mov     edi, edx
0x18007ec63  mov     rsi, rcx
0x18007ec66  mov     rdx, r14; char *
0x18007ec69  lea     rcx, [rbp+57h+var_A0]; this
0x18007ec6d  mov     r8d, 139h; int
0x18007ec73  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007ec78  xor     r12d, r12d
0x18007ec7b  mov     [rbp+57h+var_68], rbx
0x18007ec7f  mov     eax, r12d
0x18007ec82  mov     [rbp+57h+var_60], r12d
0x18007ec86  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x18007ec8a  mov     [rbp+57h+var_5C], edi
0x18007ec8d  lea     rcx, [rbp+57h+var_68]; this
0x18007ec91  mov     [rbp+57h+var_58], r12d
0x18007ec95  lea     r15d, [r12+1]
0x18007ec9a  mov     [rbp+57h+var_54], 100h
0x18007eca0  mov     [rbp+57h+var_9C], r12d
0x18007eca4  mov     [rbp+57h+var_80], r12d
0x18007eca8  mov     [rbp+57h+var_84], eax
0x18007ecab  mov     [rbp+57h+var_8C], eax
0x18007ecae  mov     [rbp+57h+var_90], r12d
0x18007ecb2  mov     [rbp+57h+var_78], r12d
0x18007ecb6  mov     [rbp+57h+var_74], r12d
0x18007ecba  mov     [rbp+57h+var_70], r12d
0x18007ecbe  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x18007ecc3  mov     ebx, eax
0x18007ecc5  test    eax, eax
0x18007ecc7  jns     loc_18007ED7C
0x18007eccd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ecd4  test    rcx, rcx
0x18007ecd7  jnz     short loc_18007ED20
0x18007ecd9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ece0  nop     dword ptr [rax+rax+00h]
0x18007ece5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ecec  mov     rcx, rax
0x18007ecef  test    rax, rax
0x18007ecf2  jz      short loc_18007ED12
0x18007ecf4  mov     rax, [rax]
0x18007ecf7  mov     edx, 7F0h
0x18007ecfc  mov     rax, [rax+8]
0x18007ed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed05  test    eax, eax
0x18007ed07  jz      short loc_18007ED12
0x18007ed09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed10  jmp     short loc_18007ED20
0x18007ed12  lea     rcx, qword_1800DBF70; this
0x18007ed19  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed20  cmp     [rcx+8], r12b
0x18007ed24  jz      short loc_18007ED47
0x18007ed26  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ed2b  cmp     [rax+7CCh], ebx
0x18007ed31  jz      short loc_18007ED47
0x18007ed33  mov     r9d, ebx; int
0x18007ed36  mov     r8d, 14Fh; int
0x18007ed3c  mov     rdx, r14; char *
0x18007ed3f  mov     rcx, rax; this
0x18007ed42  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ed47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007ed4e  jb      loc_18007F2B0
0x18007ed54  mov     edx, 0Bh
0x18007ed59  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007ed60  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed67  mov     r9, rsi
0x18007ed6a  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18007ed6e  mov     rcx, [rcx+10h]
0x18007ed72  call    WPP_SF_qD
0x18007ed77  jmp     loc_18007F2B0
0x18007ed7c  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x18007ed80  lea     rcx, [rbp+57h+var_68]; this
0x18007ed84  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x18007ed89  mov     ebx, eax
0x18007ed8b  test    eax, eax
0x18007ed8d  jns     loc_18007EE24
0x18007ed93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ed9a  test    rcx, rcx
0x18007ed9d  jnz     short loc_18007EDE6
0x18007ed9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007eda6  nop     dword ptr [rax+rax+00h]
0x18007edab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007edb2  mov     rcx, rax
0x18007edb5  test    rax, rax
0x18007edb8  jz      short loc_18007EDD8
0x18007edba  mov     rax, [rax]
0x18007edbd  mov     edx, 7F0h
0x18007edc2  mov     rax, [rax+8]
0x18007edc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007edcb  test    eax, eax
0x18007edcd  jz      short loc_18007EDD8
0x18007edcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007edd6  jmp     short loc_18007EDE6
0x18007edd8  lea     rcx, qword_1800DBF70; this
0x18007eddf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ede6  cmp     [rcx+8], r12b
0x18007edea  jz      short loc_18007EE0D
0x18007edec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007edf1  cmp     [rax+7CCh], ebx
0x18007edf7  jz      short loc_18007EE0D
0x18007edf9  mov     r9d, ebx; int
0x18007edfc  mov     r8d, 151h; int
0x18007ee02  mov     rdx, r14; char *
0x18007ee05  mov     rcx, rax; this
0x18007ee08  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ee0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007ee14  jb      loc_18007F2B0
0x18007ee1a  mov     edx, 0Ch
0x18007ee1f  jmp     loc_18007ED59
0x18007ee24  lea     r8, [rbp+57h+var_90]; unsigned int *
0x18007ee28  mov     edx, 4; int
0x18007ee2d  lea     rcx, [rbp+57h+var_68]; this
0x18007ee31  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007ee36  mov     ebx, eax
0x18007ee38  test    eax, eax
0x18007ee3a  jns     loc_18007EED1
0x18007ee40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee47  test    rcx, rcx
0x18007ee4a  jnz     short loc_18007EE93
0x18007ee4c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007ee53  nop     dword ptr [rax+rax+00h]
0x18007ee58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee5f  mov     rcx, rax
0x18007ee62  test    rax, rax
0x18007ee65  jz      short loc_18007EE85
0x18007ee67  mov     rax, [rax]
0x18007ee6a  mov     edx, 7F0h
0x18007ee6f  mov     rax, [rax+8]
0x18007ee73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee78  test    eax, eax
0x18007ee7a  jz      short loc_18007EE85
0x18007ee7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee83  jmp     short loc_18007EE93
0x18007ee85  lea     rcx, qword_1800DBF70; this
0x18007ee8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007ee93  cmp     [rcx+8], r12b
0x18007ee97  jz      short loc_18007EEBA
0x18007ee99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ee9e  cmp     [rax+7CCh], ebx
0x18007eea4  jz      short loc_18007EEBA
0x18007eea6  mov     r9d, ebx; int
0x18007eea9  mov     r8d, 156h; int
0x18007eeaf  mov     rdx, r14; char *
0x18007eeb2  mov     rcx, rax; this
0x18007eeb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007eeba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007eec1  jb      loc_18007F2B0
0x18007eec7  mov     edx, 0Dh
0x18007eecc  jmp     loc_18007ED59
0x18007eed1  mov     ecx, [rbp+57h+var_90]
0x18007eed4  lea     rdi, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007eedb  mov     [rbp+57h+var_88], r15d
0x18007eedf  mov     edx, r12d
0x18007eee2  mov     [rbp+57h+var_98], edx
0x18007eee5  mov     r13d, r12d
0x18007eee8  mov     [rbp+57h+var_94], r12d
0x18007eeec  mov     eax, ecx
0x18007eeee  mov     [rbp+57h+var_7C], r12d
0x18007eef2  test    ecx, ecx
0x18007eef4  jz      short loc_18007EF63
0x18007eef6  sub     eax, r15d
0x18007eef9  jz      short loc_18007EF5A
0x18007eefb  sub     eax, r15d
0x18007eefe  jz      short loc_18007EF5A
0x18007ef00  sub     eax, r15d
0x18007ef03  jz      short loc_18007EF5A
0x18007ef05  sub     eax, r15d
0x18007ef08  jz      short loc_18007EF5A
0x18007ef0a  sub     eax, r15d
0x18007ef0d  jz      short loc_18007EF5A
0x18007ef0f  sub     eax, r15d
0x18007ef12  jz      short loc_18007EF4E
0x18007ef14  cmp     eax, r15d
0x18007ef17  jz      short loc_18007EF46
0x18007ef19  cmp     cs:byte_1800DC8D1, r15b
0x18007ef20  jb      short loc_18007EF40
0x18007ef22  mov     r9d, ecx
0x18007ef25  mov     edx, 0Fh
0x18007ef2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef31  mov     r8, rdi
0x18007ef34  mov     rcx, [rcx+38h]
0x18007ef38  call    WPP_SF_d
0x18007ef3d  mov     edx, r12d
0x18007ef40  mov     [rbp+57h+var_88], r12d
0x18007ef44  jmp     short loc_18007EF8A
0x18007ef46  mov     r13d, 7
0x18007ef4c  jmp     short loc_18007EF54
0x18007ef4e  mov     r13d, 5
0x18007ef54  mov     [rbp+57h+var_94], r15d
0x18007ef58  jmp     short loc_18007EF8A
0x18007ef5a  mov     r13d, ecx
0x18007ef5d  mov     [rbp+57h+var_94], r12d
0x18007ef61  jmp     short loc_18007EF8A
0x18007ef63  cmp     cs:byte_1800DC8D1, 10h
0x18007ef6a  jb      short loc_18007EF84
0x18007ef6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef73  mov     edx, 0Eh
0x18007ef78  mov     r8, rdi
0x18007ef7b  mov     rcx, [rcx+38h]
0x18007ef7f  call    WPP_SF_
0x18007ef84  mov     edx, r15d
0x18007ef87  mov     [rbp+57h+var_98], edx
0x18007ef8a  mov     r14d, [rbp+57h+var_9C]
0x18007ef8e  cmp     r14d, 5
0x18007ef92  jz      short loc_18007EFA2
0x18007ef94  cmp     r14d, 1Dh
0x18007ef98  jz      short loc_18007EFA2
0x18007ef9a  mov     r15d, r12d
0x18007ef9d  jmp     loc_18007F15F
0x18007efa2  cmp     cs:byte_1800DC8D1, 10h
0x18007efa9  jb      short loc_18007EFC3
0x18007efab  mov     rcx, cs:WPP_GLOBAL_Control
0x18007efb2  mov     edx, 10h
0x18007efb7  mov     r8, rdi
0x18007efba  mov     rcx, [rcx+38h]
0x18007efbe  call    WPP_SF_
0x18007efc3  cmp     r14d, 1Dh
0x18007efc7  jnz     short loc_18007EFED
0x18007efc9  mov     [rbp+57h+var_7C], r15d
0x18007efcd  cmp     cs:byte_1800DC8D1, 10h
0x18007efd4  jb      short loc_18007EFED
0x18007efd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007efdd  lea     edx, [r14-0Ch]
0x18007efe1  mov     r8, rdi
0x18007efe4  mov     rcx, [rcx+38h]
0x18007efe8  call    WPP_SF_
0x18007efed  lea     rdx, [rbp+57h+var_8C]; unsigned int *
0x18007eff1  lea     rcx, [rbp+57h+var_68]; this
0x18007eff5  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x18007effa  mov     ebx, eax
0x18007effc  test    eax, eax
0x18007effe  jns     loc_18007F09C
0x18007f004  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f00b  test    rcx, rcx
0x18007f00e  jnz     short loc_18007F057
0x18007f010  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007f017  nop     dword ptr [rax+rax+00h]
0x18007f01c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f023  mov     rcx, rax
0x18007f026  test    rax, rax
0x18007f029  jz      short loc_18007F049
0x18007f02b  mov     rax, [rax]
0x18007f02e  mov     edx, 7F0h
0x18007f033  mov     rax, [rax+8]
0x18007f037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f03c  test    eax, eax
0x18007f03e  jz      short loc_18007F049
0x18007f040  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f047  jmp     short loc_18007F057
0x18007f049  lea     rcx, qword_1800DBF70; this
0x18007f050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f057  cmp     [rcx+8], r12b
0x18007f05b  jz      short loc_18007F082
0x18007f05d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007f062  cmp     [rax+7CCh], ebx
0x18007f068  jz      short loc_18007F082
0x18007f06a  mov     r9d, ebx; int
0x18007f06d  lea     rdx, aCaacaudiospeci_2; "CAACAudioSpecificConfig::ParseData"
0x18007f074  mov     r8d, 189h; int
0x18007f07a  mov     rcx, rax; this
0x18007f07d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007f082  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x18007f089  jb      loc_18007F2B0
0x18007f08f  mov     edx, 12h
0x18007f094  mov     r8, rdi
0x18007f097  jmp     loc_18007ED60
0x18007f09c  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x18007f0a0  lea     rcx, [rbp+57h+var_68]; this
0x18007f0a4  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x18007f0a9  mov     ebx, eax
0x18007f0ab  test    eax, eax
0x18007f0ad  jns     loc_18007F148
0x18007f0b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f0ba  test    rcx, rcx
0x18007f0bd  jnz     short loc_18007F106
0x18007f0bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007f0c6  nop     dword ptr [rax+rax+00h]
0x18007f0cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007f0d2  mov     rcx, rax
0x18007f0d5  test    rax, rax
0x18007f0d8  jz      short loc_18007F0F8
0x18007f0da  mov     rax, [rax]
0x18007f0dd  mov     edx, 7F0h
0x18007f0e2  mov     rax, [rax+8]
0x18007f0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f0eb  test    eax, eax
0x18007f0ed  jz      short loc_18007F0F8
0x18007f0ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
