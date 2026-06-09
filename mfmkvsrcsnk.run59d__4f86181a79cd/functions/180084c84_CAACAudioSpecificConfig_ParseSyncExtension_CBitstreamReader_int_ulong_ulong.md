# CAACAudioSpecificConfig::ParseSyncExtension(CBitstreamReader &,int *,ulong *,ulong *)

- ea: `0x180084c84`
- end: `0x180084fc9`
- name: `?ParseSyncExtension@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAHPEAK2@Z`
- size: `837`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18007ec30`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18007e76c`
- `0x18007e940`
- `0x180084c84`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084dc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084f27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084cee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084dc0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084e76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084f27`

## string_xrefs

- `0x180084c94`: `CAACAudioSpecificConfig::ParseSyncExtension`

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
              v31 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v25 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v12 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180084c84  push    rbx
0x180084c86  push    rbp
0x180084c87  push    rsi
0x180084c88  push    rdi
0x180084c89  push    r12
0x180084c8b  push    r14
0x180084c8d  sub     rsp, 48h
0x180084c91  mov     rsi, r8
0x180084c94  lea     r12, aCaacaudiospeci_0; "CAACAudioSpecificConfig::ParseSyncExten"...
0x180084c9b  mov     r14, rdx
0x180084c9e  mov     rdi, rcx
0x180084ca1  mov     rdx, r12; char *
0x180084ca4  lea     rcx, [rsp+78h+var_48]; this
0x180084ca9  mov     r8d, 2CBh; int
0x180084caf  mov     rbp, r9
0x180084cb2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180084cb7  lea     r8, [rsp+78h+var_44]; unsigned int *
0x180084cbc  mov     [rsp+78h+var_44], 0
0x180084cc4  mov     edx, 0Bh; int
0x180084cc9  mov     dword ptr [r14], 0
0x180084cd0  mov     rcx, rdi; this
0x180084cd3  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x180084cd8  mov     ebx, eax
0x180084cda  test    eax, eax
0x180084cdc  jns     loc_180084D91
0x180084ce2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ce9  test    rcx, rcx
0x180084cec  jnz     short loc_180084D35
0x180084cee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084cf5  nop     dword ptr [rax+rax+00h]
0x180084cfa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d01  mov     rcx, rax
0x180084d04  test    rax, rax
0x180084d07  jz      short loc_180084D27
0x180084d09  mov     rax, [rax]
0x180084d0c  mov     edx, 7F0h
0x180084d11  mov     rax, [rax+8]
0x180084d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084d1a  test    eax, eax
0x180084d1c  jz      short loc_180084D27
0x180084d1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d25  jmp     short loc_180084D35
0x180084d27  lea     rcx, qword_1800DBF70; this
0x180084d2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084d35  cmp     byte ptr [rcx+8], 0
0x180084d39  jz      short loc_180084D5C
0x180084d3b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084d40  cmp     [rax+7CCh], ebx
0x180084d46  jz      short loc_180084D5C
0x180084d48  mov     r9d, ebx; int
0x180084d4b  mov     r8d, 2D1h; int
0x180084d51  mov     rdx, r12; char *
0x180084d54  mov     rcx, rax; this
0x180084d57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084d5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084d63  jb      loc_180084FAF
0x180084d69  mov     edx, 3Bh ; ';'
0x180084d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180084d75  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x180084d7c  xor     r9d, r9d
0x180084d7f  mov     [rsp+78h+var_58], ebx
0x180084d83  mov     rcx, [rcx+10h]
0x180084d87  call    WPP_SF_qD
0x180084d8c  jmp     loc_180084FAF
0x180084d91  cmp     [rsp+78h+var_44], 2B7h
0x180084d99  jnz     loc_180084FAF
0x180084d9f  mov     rdx, rsi; unsigned int *
0x180084da2  mov     rcx, rdi; this
0x180084da5  call    ?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)
0x180084daa  mov     ebx, eax
0x180084dac  test    eax, eax
0x180084dae  jns     loc_180084E45
0x180084db4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084dbb  test    rcx, rcx
0x180084dbe  jnz     short loc_180084E07
0x180084dc0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084dc7  nop     dword ptr [rax+rax+00h]
0x180084dcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084dd3  mov     rcx, rax
0x180084dd6  test    rax, rax
0x180084dd9  jz      short loc_180084DF9
0x180084ddb  mov     rax, [rax]
0x180084dde  mov     edx, 7F0h
0x180084de3  mov     rax, [rax+8]
0x180084de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084dec  test    eax, eax
0x180084dee  jz      short loc_180084DF9
0x180084df0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084df7  jmp     short loc_180084E07
0x180084df9  lea     rcx, qword_1800DBF70; this
0x180084e00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e07  cmp     byte ptr [rcx+8], 0
0x180084e0b  jz      short loc_180084E2E
0x180084e0d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084e12  cmp     [rax+7CCh], ebx
0x180084e18  jz      short loc_180084E2E
0x180084e1a  mov     r9d, ebx; int
0x180084e1d  mov     r8d, 2D8h; int
0x180084e23  mov     rdx, r12; char *
0x180084e26  mov     rcx, rax; this
0x180084e29  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084e2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084e35  jb      loc_180084FAF
0x180084e3b  mov     edx, 3Ch ; '<'
0x180084e40  jmp     loc_180084D6E
0x180084e45  cmp     dword ptr [rsi], 5
0x180084e48  jnz     loc_180084FAF
0x180084e4e  lea     r8, [rsp+78h+var_44]; unsigned int *
0x180084e53  mov     edx, 1; int
0x180084e58  mov     rcx, rdi; this
0x180084e5b  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x180084e60  mov     ebx, eax
0x180084e62  test    eax, eax
0x180084e64  jns     loc_180084EFB
0x180084e6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e71  test    rcx, rcx
0x180084e74  jnz     short loc_180084EBD
0x180084e76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084e7d  nop     dword ptr [rax+rax+00h]
0x180084e82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084e89  mov     rcx, rax
0x180084e8c  test    rax, rax
0x180084e8f  jz      short loc_180084EAF
0x180084e91  mov     rax, [rax]
0x180084e94  mov     edx, 7F0h
0x180084e99  mov     rax, [rax+8]
0x180084e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ea2  test    eax, eax
0x180084ea4  jz      short loc_180084EAF
0x180084ea6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ead  jmp     short loc_180084EBD
0x180084eaf  lea     rcx, qword_1800DBF70; this
0x180084eb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084ebd  cmp     byte ptr [rcx+8], 0
0x180084ec1  jz      short loc_180084EE4
0x180084ec3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084ec8  cmp     [rax+7CCh], ebx
0x180084ece  jz      short loc_180084EE4
0x180084ed0  mov     r9d, ebx; int
0x180084ed3  mov     r8d, 2DFh; int
0x180084ed9  mov     rdx, r12; char *
0x180084edc  mov     rcx, rax; this
0x180084edf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084ee4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084eeb  jb      loc_180084FAF
0x180084ef1  mov     edx, 3Dh ; '='
0x180084ef6  jmp     loc_180084D6E
0x180084efb  cmp     [rsp+78h+var_44], 0
0x180084f00  jz      loc_180084FAF
0x180084f06  mov     rdx, rbp; unsigned int *
0x180084f09  mov     rcx, rdi; this
0x180084f0c  call    ?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z; CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)
0x180084f11  mov     ebx, eax
0x180084f13  test    eax, eax
0x180084f15  jns     loc_180084FA8
0x180084f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f22  test    rcx, rcx
0x180084f25  jnz     short loc_180084F6E
0x180084f27  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084f2e  nop     dword ptr [rax+rax+00h]
0x180084f33  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f3a  mov     rcx, rax
0x180084f3d  test    rax, rax
0x180084f40  jz      short loc_180084F60
0x180084f42  mov     rax, [rax]
0x180084f45  mov     edx, 7F0h
0x180084f4a  mov     rax, [rax+8]
0x180084f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f53  test    eax, eax
0x180084f55  jz      short loc_180084F60
0x180084f57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f5e  jmp     short loc_180084F6E
0x180084f60  lea     rcx, qword_1800DBF70; this
0x180084f67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084f6e  cmp     byte ptr [rcx+8], 0
0x180084f72  jz      short loc_180084F95
0x180084f74  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084f79  cmp     [rax+7CCh], ebx
0x180084f7f  jz      short loc_180084F95
0x180084f81  mov     r9d, ebx; int
0x180084f84  mov     r8d, 2E6h; int
0x180084f8a  mov     rdx, r12; char *
0x180084f8d  mov     rcx, rax; this
0x180084f90  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180084f95  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180084f9c  jb      short loc_180084FAF
0x180084f9e  mov     edx, 3Eh ; '>'
0x180084fa3  jmp     loc_180084D6E
0x180084fa8  mov     dword ptr [r14], 1
0x180084faf  lea     rcx, [rsp+78h+var_48]; this
0x180084fb4  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180084fb9  mov     eax, ebx
0x180084fbb  add     rsp, 48h
0x180084fbf  pop     r14
0x180084fc1  pop     r12
0x180084fc3  pop     rdi
0x180084fc4  pop     rsi
0x180084fc5  pop     rbp
0x180084fc6  pop     rbx
0x180084fc7  retn
```
