# CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)

- ea: `0x18007e76c`
- end: `0x18007e939`
- name: `?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007ec30`
- `0x180084c84`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18007e76c`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e894`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e7be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e894`

## string_xrefs

- `0x18007e781`: `CAACAudioSpecificConfig::GetAudioObjectType`
- `0x18007e81b`: `CAACAudioSpecificConfig::GetAudioObjectType`
- `0x18007e8f1`: `CAACAudioSpecificConfig::GetAudioObjectType`

## pseudocode

```c
__int64 __fastcall CAACAudioSpecificConfig::GetAudioObjectType(struct CBitstreamReader *this, unsigned int *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v19[24]; // [rsp+30h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v19,
    "CAACAudioSpecificConfig::GetAudioObjectType",
    903);
  v5 = CBitstreamReader::PopN(this, 5, a2);
  if ( v5 >= 0 )
  {
    if ( *a2 == 31 )
    {
      v5 = CBitstreamReader::PopN(this, 6, a2);
      if ( v5 >= 0 )
      {
        *a2 += 32;
        goto LABEL_26;
      }
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CAACAudioSpecificConfig::GetAudioObjectType", 909, v5);
      }
      if ( g_wppLevels )
      {
        v11 = 83;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v5 )
        CallStackContext::TraceFailure(v10, "CAACAudioSpecificConfig::GetAudioObjectType", 905, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 82;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, 0, v5);
    }
  }
LABEL_26:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007e76c  mov     [rsp+arg_10], rbx
0x18007e771  mov     [rsp+arg_18], rsi
0x18007e776  push    rdi
0x18007e777  sub     rsp, 40h
0x18007e77b  mov     rdi, rdx
0x18007e77e  mov     rsi, rcx
0x18007e781  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007e788  mov     r8d, 387h; int
0x18007e78e  lea     rcx, [rsp+48h+var_18]; this
0x18007e793  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007e798  mov     r8, rdi; unsigned int *
0x18007e79b  mov     edx, 5; int
0x18007e7a0  mov     rcx, rsi; this
0x18007e7a3  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007e7a8  mov     ebx, eax
0x18007e7aa  test    eax, eax
0x18007e7ac  jns     loc_18007E865
0x18007e7b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e7b9  test    rcx, rcx
0x18007e7bc  jnz     short loc_18007E805
0x18007e7be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e7c5  nop     dword ptr [rax+rax+00h]
0x18007e7ca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e7d1  mov     rcx, rax
0x18007e7d4  test    rax, rax
0x18007e7d7  jz      short loc_18007E7F7
0x18007e7d9  mov     rax, [rax]
0x18007e7dc  mov     edx, 7F0h
0x18007e7e1  mov     rax, [rax+8]
0x18007e7e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7ea  test    eax, eax
0x18007e7ec  jz      short loc_18007E7F7
0x18007e7ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e7f5  jmp     short loc_18007E805
0x18007e7f7  lea     rcx, qword_1800DBF70; this
0x18007e7fe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e805  cmp     byte ptr [rcx+8], 0
0x18007e809  jz      short loc_18007E830
0x18007e80b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e810  cmp     [rax+7CCh], ebx
0x18007e816  jz      short loc_18007E830
0x18007e818  mov     r9d, ebx; int
0x18007e81b  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007e822  mov     r8d, 389h; int
0x18007e828  mov     rcx, rax; this
0x18007e82b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e830  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007e837  jb      loc_18007E91C
0x18007e83d  mov     edx, 52h ; 'R'
0x18007e842  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e849  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007e850  xor     r9d, r9d
0x18007e853  mov     [rsp+48h+var_28], ebx
0x18007e857  mov     rcx, [rcx+10h]
0x18007e85b  call    WPP_SF_qD
0x18007e860  jmp     loc_18007E91C
0x18007e865  cmp     dword ptr [rdi], 1Fh
0x18007e868  jnz     loc_18007E91C
0x18007e86e  mov     r8, rdi; unsigned int *
0x18007e871  mov     edx, 6; int
0x18007e876  mov     rcx, rsi; this
0x18007e879  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007e87e  mov     ebx, eax
0x18007e880  test    eax, eax
0x18007e882  jns     loc_18007E919
0x18007e888  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e88f  test    rcx, rcx
0x18007e892  jnz     short loc_18007E8DB
0x18007e894  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e89b  nop     dword ptr [rax+rax+00h]
0x18007e8a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e8a7  mov     rcx, rax
0x18007e8aa  test    rax, rax
0x18007e8ad  jz      short loc_18007E8CD
0x18007e8af  mov     rax, [rax]
0x18007e8b2  mov     edx, 7F0h
0x18007e8b7  mov     rax, [rax+8]
0x18007e8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8c0  test    eax, eax
0x18007e8c2  jz      short loc_18007E8CD
0x18007e8c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e8cb  jmp     short loc_18007E8DB
0x18007e8cd  lea     rcx, qword_1800DBF70; this
0x18007e8d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e8db  cmp     byte ptr [rcx+8], 0
0x18007e8df  jz      short loc_18007E906
0x18007e8e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e8e6  cmp     [rax+7CCh], ebx
0x18007e8ec  jz      short loc_18007E906
0x18007e8ee  mov     r9d, ebx; int
0x18007e8f1  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007e8f8  mov     r8d, 38Dh; int
0x18007e8fe  mov     rcx, rax; this
0x18007e901  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007e906  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007e90d  jb      short loc_18007E91C
0x18007e90f  mov     edx, 53h ; 'S'
0x18007e914  jmp     loc_18007E842
0x18007e919  add     dword ptr [rdi], 20h ; ' '
0x18007e91c  lea     rcx, [rsp+48h+var_18]; this
0x18007e921  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007e926  mov     rsi, [rsp+48h+arg_18]
0x18007e92b  mov     eax, ebx
0x18007e92d  mov     rbx, [rsp+48h+arg_10]
0x18007e932  add     rsp, 40h
0x18007e936  pop     rdi
0x18007e937  retn
```
