# CAACAudioSpecificConfig::GetAudioObjectType(CBitstreamReader &,ulong *)

- ea: `0x18007afdc`
- end: `0x18007b19c`
- name: `?GetAudioObjectType@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z`
- size: `448`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007b488`
- `0x180081210`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x18007afdc`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b02e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b0fe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b02e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b0fe`

## string_xrefs

- `0x18007aff1`: `CAACAudioSpecificConfig::GetAudioObjectType`
- `0x18007b085`: `CAACAudioSpecificConfig::GetAudioObjectType`
- `0x18007b155`: `CAACAudioSpecificConfig::GetAudioObjectType`

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
          v15 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18007afdc  mov     [rsp+arg_10], rbx
0x18007afe1  mov     [rsp+arg_18], rsi
0x18007afe6  push    rdi
0x18007afe7  sub     rsp, 40h
0x18007afeb  mov     rdi, rdx
0x18007afee  mov     rsi, rcx
0x18007aff1  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007aff8  mov     r8d, 387h; int
0x18007affe  lea     rcx, [rsp+48h+var_18]; this
0x18007b003  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007b008  mov     r8, rdi; unsigned int *
0x18007b00b  mov     edx, 5; int
0x18007b010  mov     rcx, rsi; this
0x18007b013  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007b018  mov     ebx, eax
0x18007b01a  test    eax, eax
0x18007b01c  jns     loc_18007B0CF
0x18007b022  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b029  test    rcx, rcx
0x18007b02c  jnz     short loc_18007B06F
0x18007b02e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b034  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b03b  mov     rcx, rax
0x18007b03e  test    rax, rax
0x18007b041  jz      short loc_18007B061
0x18007b043  mov     rax, [rax]
0x18007b046  mov     edx, 7F0h
0x18007b04b  mov     rax, [rax+8]
0x18007b04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b054  test    eax, eax
0x18007b056  jz      short loc_18007B061
0x18007b058  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b05f  jmp     short loc_18007B06F
0x18007b061  lea     rcx, qword_1800D6F70; this
0x18007b068  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b06f  cmp     byte ptr [rcx+8], 0
0x18007b073  jz      short loc_18007B09A
0x18007b075  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b07a  cmp     [rax+7CCh], ebx
0x18007b080  jz      short loc_18007B09A
0x18007b082  mov     r9d, ebx; int
0x18007b085  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007b08c  mov     r8d, 389h; int
0x18007b092  mov     rcx, rax; this
0x18007b095  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b09a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b0a1  jb      loc_18007B180
0x18007b0a7  mov     edx, 52h ; 'R'
0x18007b0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b0b3  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007b0ba  xor     r9d, r9d
0x18007b0bd  mov     [rsp+48h+var_28], ebx
0x18007b0c1  mov     rcx, [rcx+10h]
0x18007b0c5  call    WPP_SF_qD
0x18007b0ca  jmp     loc_18007B180
0x18007b0cf  cmp     dword ptr [rdi], 1Fh
0x18007b0d2  jnz     loc_18007B180
0x18007b0d8  mov     r8, rdi; unsigned int *
0x18007b0db  mov     edx, 6; int
0x18007b0e0  mov     rcx, rsi; this
0x18007b0e3  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007b0e8  mov     ebx, eax
0x18007b0ea  test    eax, eax
0x18007b0ec  jns     loc_18007B17D
0x18007b0f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b0f9  test    rcx, rcx
0x18007b0fc  jnz     short loc_18007B13F
0x18007b0fe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b104  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b10b  mov     rcx, rax
0x18007b10e  test    rax, rax
0x18007b111  jz      short loc_18007B131
0x18007b113  mov     rax, [rax]
0x18007b116  mov     edx, 7F0h
0x18007b11b  mov     rax, [rax+8]
0x18007b11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b124  test    eax, eax
0x18007b126  jz      short loc_18007B131
0x18007b128  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b12f  jmp     short loc_18007B13F
0x18007b131  lea     rcx, qword_1800D6F70; this
0x18007b138  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b13f  cmp     byte ptr [rcx+8], 0
0x18007b143  jz      short loc_18007B16A
0x18007b145  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b14a  cmp     [rax+7CCh], ebx
0x18007b150  jz      short loc_18007B16A
0x18007b152  mov     r9d, ebx; int
0x18007b155  lea     rdx, aCaacaudiospeci; "CAACAudioSpecificConfig::GetAudioObject"...
0x18007b15c  mov     r8d, 38Dh; int
0x18007b162  mov     rcx, rax; this
0x18007b165  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b16a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b171  jb      short loc_18007B180
0x18007b173  mov     edx, 53h ; 'S'
0x18007b178  jmp     loc_18007B0AC
0x18007b17d  add     dword ptr [rdi], 20h ; ' '
0x18007b180  lea     rcx, [rsp+48h+var_18]; this
0x18007b185  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007b18a  mov     rsi, [rsp+48h+arg_18]
0x18007b18f  mov     eax, ebx
0x18007b191  mov     rbx, [rsp+48h+arg_10]
0x18007b196  add     rsp, 40h
0x18007b19a  pop     rdi
0x18007b19b  retn
```
