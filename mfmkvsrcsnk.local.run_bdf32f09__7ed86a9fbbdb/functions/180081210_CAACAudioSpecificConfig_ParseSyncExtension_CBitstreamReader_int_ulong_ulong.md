# CAACAudioSpecificConfig::ParseSyncExtension(CBitstreamReader &,int *,ulong *,ulong *)

- ea: `0x180081210`
- end: `0x18008153c`
- name: `?ParseSyncExtension@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAHPEAK2@Z`
- size: `812`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18007b488`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18007afdc`
- `0x18007b1a4`
- `0x180081210`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008127a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180081346`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800813f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800814a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008127a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180081346`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800813f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800814a1`

## string_xrefs

- `0x180081220`: `CAACAudioSpecificConfig::ParseSyncExtension`

## pseudocode

```c
__int64 __fastcall CAACAudioSpecificConfig::ParseSyncExtension(
        struct CBitstreamReader *this,
        int *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  int AudioObjectType; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v35[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v36[17]; // [rsp+34h] [rbp-44h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v35,
    "CAACAudioSpecificConfig::ParseSyncExtension",
    715);
  v36[0] = 0;
  *a2 = 0;
  AudioObjectType = CBitstreamReader::PopN(this, 11, v36);
  if ( AudioObjectType >= 0 )
  {
    if ( v36[0] != 695 )
      goto LABEL_50;
    AudioObjectType = CAACAudioSpecificConfig::GetAudioObjectType(this, a3);
    if ( AudioObjectType >= 0 )
    {
      if ( *a3 != 5 )
        goto LABEL_50;
      AudioObjectType = CBitstreamReader::PopN(this, 1, v36);
      if ( AudioObjectType >= 0 )
      {
        if ( v36[0] )
        {
          AudioObjectType = CAACAudioSpecificConfig::GetSamplingFrequency(this, a4);
          if ( AudioObjectType >= 0 )
          {
            *a2 = 1;
            goto LABEL_50;
          }
          v31 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != AudioObjectType )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CAACAudioSpecificConfig::ParseSyncExtension",
                742,
                AudioObjectType);
          }
          if ( g_wppLevels )
          {
            v15 = 62;
            goto LABEL_12;
          }
        }
      }
      else
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
          if ( *((_DWORD *)v27 + 499) != AudioObjectType )
            CallStackContext::TraceFailure(v27, "CAACAudioSpecificConfig::ParseSyncExtension", 735, AudioObjectType);
        }
        if ( g_wppLevels )
        {
          v15 = 61;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != AudioObjectType )
          CallStackContext::TraceFailure(v21, "CAACAudioSpecificConfig::ParseSyncExtension", 728, AudioObjectType);
      }
      if ( g_wppLevels )
      {
        v15 = 60;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != AudioObjectType )
        CallStackContext::TraceFailure(v14, "CAACAudioSpecificConfig::ParseSyncExtension", 721, AudioObjectType);
    }
    if ( g_wppLevels )
    {
      v15 = 59;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids,
        0,
        AudioObjectType);
    }
  }
LABEL_50:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v35);
  return (unsigned int)AudioObjectType;
}

```

## disassembly

```asm
0x180081210  push    rbx
0x180081212  push    rbp
0x180081213  push    rsi
0x180081214  push    rdi
0x180081215  push    r12
0x180081217  push    r14
0x180081219  sub     rsp, 48h
0x18008121d  mov     rsi, r8
0x180081220  lea     r12, aCaacaudiospeci_0; "CAACAudioSpecificConfig::ParseSyncExten"...
0x180081227  mov     r14, rdx
0x18008122a  mov     rdi, rcx
0x18008122d  mov     rdx, r12; char *
0x180081230  lea     rcx, [rsp+78h+var_48]; this
0x180081235  mov     r8d, 2CBh; int
0x18008123b  mov     rbp, r9
0x18008123e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180081243  lea     r8, [rsp+78h+var_44]; unsigned int *
0x180081248  mov     [rsp+78h+var_44], 0
0x180081250  mov     edx, 0Bh; int
0x180081255  mov     dword ptr [r14], 0
0x18008125c  mov     rcx, rdi; this
0x18008125f  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x180081264  mov     ebx, eax
0x180081266  test    eax, eax
0x180081268  jns     loc_180081317
0x18008126e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180081275  test    rcx, rcx
0x180081278  jnz     short loc_1800812BB
0x18008127a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180081280  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180081287  mov     rcx, rax
0x18008128a  test    rax, rax
0x18008128d  jz      short loc_1800812AD
0x18008128f  mov     rax, [rax]
0x180081292  mov     edx, 7F0h
0x180081297  mov     rax, [rax+8]
0x18008129b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800812a0  test    eax, eax
0x1800812a2  jz      short loc_1800812AD
0x1800812a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800812ab  jmp     short loc_1800812BB
0x1800812ad  lea     rcx, qword_1800D6F70; this
0x1800812b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800812bb  cmp     byte ptr [rcx+8], 0
0x1800812bf  jz      short loc_1800812E2
0x1800812c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800812c6  cmp     [rax+7CCh], ebx
0x1800812cc  jz      short loc_1800812E2
0x1800812ce  mov     r9d, ebx; int
0x1800812d1  mov     r8d, 2D1h; int
0x1800812d7  mov     rdx, r12; char *
0x1800812da  mov     rcx, rax; this
0x1800812dd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800812e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800812e9  jb      loc_180081523
0x1800812ef  mov     edx, 3Bh ; ';'
0x1800812f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812fb  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x180081302  xor     r9d, r9d
0x180081305  mov     [rsp+78h+var_58], ebx
0x180081309  mov     rcx, [rcx+10h]
0x18008130d  call    WPP_SF_qD
0x180081312  jmp     loc_180081523
0x180081317  cmp     [rsp+78h+var_44], 2B7h
0x18008131f  jnz     loc_180081523
0x180081325  mov     rdx, rsi; unsigned int *
0x180081328  mov     rcx, rdi; this
0x18008132b  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x180081330  mov     ebx, eax
0x180081332  test    eax, eax
0x180081334  jns     loc_1800813C5
0x18008133a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180081341  test    rcx, rcx
0x180081344  jnz     short loc_180081387
0x180081346  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008134c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180081353  mov     rcx, rax
0x180081356  test    rax, rax
0x180081359  jz      short loc_180081379
0x18008135b  mov     rax, [rax]
0x18008135e  mov     edx, 7F0h
0x180081363  mov     rax, [rax+8]
0x180081367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008136c  test    eax, eax
0x18008136e  jz      short loc_180081379
0x180081370  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180081377  jmp     short loc_180081387
0x180081379  lea     rcx, qword_1800D6F70; this
0x180081380  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180081387  cmp     byte ptr [rcx+8], 0
0x18008138b  jz      short loc_1800813AE
0x18008138d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180081392  cmp     [rax+7CCh], ebx
0x180081398  jz      short loc_1800813AE
0x18008139a  mov     r9d, ebx; int
0x18008139d  mov     r8d, 2D8h; int
0x1800813a3  mov     rdx, r12; char *
0x1800813a6  mov     rcx, rax; this
0x1800813a9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800813ae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800813b5  jb      loc_180081523
0x1800813bb  mov     edx, 3Ch ; '<'
0x1800813c0  jmp     loc_1800812F4
0x1800813c5  cmp     dword ptr [rsi], 5
0x1800813c8  jnz     loc_180081523
0x1800813ce  lea     r8, [rsp+78h+var_44]; unsigned int *
0x1800813d3  mov     edx, 1; int
0x1800813d8  mov     rcx, rdi; this
0x1800813db  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x1800813e0  mov     ebx, eax
0x1800813e2  test    eax, eax
0x1800813e4  jns     loc_180081475
0x1800813ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800813f1  test    rcx, rcx
0x1800813f4  jnz     short loc_180081437
0x1800813f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800813fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180081403  mov     rcx, rax
0x180081406  test    rax, rax
0x180081409  jz      short loc_180081429
0x18008140b  mov     rax, [rax]
0x18008140e  mov     edx, 7F0h
0x180081413  mov     rax, [rax+8]
0x180081417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008141c  test    eax, eax
0x18008141e  jz      short loc_180081429
0x180081420  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180081427  jmp     short loc_180081437
0x180081429  lea     rcx, qword_1800D6F70; this
0x180081430  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180081437  cmp     byte ptr [rcx+8], 0
0x18008143b  jz      short loc_18008145E
0x18008143d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180081442  cmp     [rax+7CCh], ebx
0x180081448  jz      short loc_18008145E
0x18008144a  mov     r9d, ebx; int
0x18008144d  mov     r8d, 2DFh; int
0x180081453  mov     rdx, r12; char *
0x180081456  mov     rcx, rax; this
0x180081459  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008145e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180081465  jb      loc_180081523
0x18008146b  mov     edx, 3Dh ; '='
0x180081470  jmp     loc_1800812F4
0x180081475  cmp     [rsp+78h+var_44], 0
0x18008147a  jz      loc_180081523
0x180081480  mov     rdx, rbp; unsigned int *
0x180081483  mov     rcx, rdi; this
0x180081486  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x18008148b  mov     ebx, eax
0x18008148d  test    eax, eax
0x18008148f  jns     loc_18008151C
0x180081495  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008149c  test    rcx, rcx
0x18008149f  jnz     short loc_1800814E2
0x1800814a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800814a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800814ae  mov     rcx, rax
0x1800814b1  test    rax, rax
0x1800814b4  jz      short loc_1800814D4
0x1800814b6  mov     rax, [rax]
0x1800814b9  mov     edx, 7F0h
0x1800814be  mov     rax, [rax+8]
0x1800814c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814c7  test    eax, eax
0x1800814c9  jz      short loc_1800814D4
0x1800814cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800814d2  jmp     short loc_1800814E2
0x1800814d4  lea     rcx, qword_1800D6F70; this
0x1800814db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800814e2  cmp     byte ptr [rcx+8], 0
0x1800814e6  jz      short loc_180081509
0x1800814e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800814ed  cmp     [rax+7CCh], ebx
0x1800814f3  jz      short loc_180081509
0x1800814f5  mov     r9d, ebx; int
0x1800814f8  mov     r8d, 2E6h; int
0x1800814fe  mov     rdx, r12; char *
0x180081501  mov     rcx, rax; this
0x180081504  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180081509  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180081510  jb      short loc_180081523
0x180081512  mov     edx, 3Eh ; '>'
0x180081517  jmp     loc_1800812F4
0x18008151c  mov     dword ptr [r14], 1
0x180081523  lea     rcx, [rsp+78h+var_48]; this
0x180081528  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008152d  mov     eax, ebx
0x18008152f  add     rsp, 48h
0x180081533  pop     r14
0x180081535  pop     r12
0x180081537  pop     rdi
0x180081538  pop     rsi
0x180081539  pop     rbp
0x18008153a  pop     rbx
0x18008153b  retn
```
