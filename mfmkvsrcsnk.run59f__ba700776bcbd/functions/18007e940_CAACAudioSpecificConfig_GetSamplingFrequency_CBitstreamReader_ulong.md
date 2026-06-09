# CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)

- ea: `0x18007e940`
- end: `0x18007ec29`
- name: `?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z`
- size: `745`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18007ec30`
- `0x180084c84`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800432a8`
- `0x1800744d8`
- `0x18007e940`
- `0x180086640`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e99c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007eb61`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007e99c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007eb61`

## string_xrefs

- `0x18007e955`: `CAACAudioSpecificConfig::GetSamplingFrequency`
- `0x18007e9f9`: `CAACAudioSpecificConfig::GetSamplingFrequency`
- `0x18007ebbe`: `CAACAudioSpecificConfig::GetSamplingFrequency`

## pseudocode

```c
__int64 __fastcall CAACAudioSpecificConfig::GetSamplingFrequency(struct CBitstreamReader *this, unsigned int *a2)
{
  __int64 v4; // rdx
  int v5; // edi
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
  _BYTE v19[4]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v20[5]; // [rsp+34h] [rbp-14h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v19,
    "CAACAudioSpecificConfig::GetSamplingFrequency",
    923);
  v20[0] = 0;
  v5 = CBitstreamReader::PopN(this, 4, v20);
  if ( v5 >= 0 )
  {
    if ( v20[0] > 7 )
    {
      switch ( v20[0] )
      {
        case 8u:
          *a2 = 16000;
          break;
        case 9u:
          *a2 = 12000;
          break;
        case 0xAu:
          *a2 = 11025;
          break;
        case 0xBu:
          *a2 = 8000;
          break;
        case 0xCu:
          *a2 = 7350;
          break;
        case 0xFu:
          v5 = CBitstreamReader::PopN(this, 24, a2);
          if ( v5 < 0 )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
              CallStackTracing::s_wpInstance = v16;
              if ( v16
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
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
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAACAudioSpecificConfig::GetSamplingFrequency",
                  948,
                  v5);
            }
            if ( g_wppLevels )
            {
              v11 = 86;
              goto LABEL_12;
            }
          }
          break;
        default:
          if ( byte_1800DC8D1 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 87, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, v20[0]);
          *a2 = 0;
          break;
      }
    }
    else if ( v20[0] == 7 )
    {
      *a2 = 22050;
    }
    else if ( v20[0] )
    {
      switch ( v20[0] )
      {
        case 1u:
          *a2 = 88200;
          break;
        case 2u:
          *a2 = 64000;
          break;
        case 3u:
          *a2 = 48000;
          break;
        case 4u:
          *a2 = 44100;
          break;
        case 5u:
          *a2 = 32000;
          break;
        default:
          *a2 = 24000;
          break;
      }
    }
    else
    {
      *a2 = 96000;
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
        CallStackContext::TraceFailure(v10, "CAACAudioSpecificConfig::GetSamplingFrequency", 927, v5);
    }
    if ( g_wppLevels )
    {
      v11 = 85;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids, 0, v5);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007e940  mov     [rsp+arg_10], rbx
0x18007e945  mov     [rsp+arg_18], rsi
0x18007e94a  push    rdi
0x18007e94b  sub     rsp, 40h
0x18007e94f  mov     rbx, rdx
0x18007e952  mov     rsi, rcx
0x18007e955  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007e95c  mov     r8d, 39Bh; int
0x18007e962  lea     rcx, [rsp+48h+var_18]; this
0x18007e967  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007e96c  lea     r8, [rsp+48h+var_14]; unsigned int *
0x18007e971  mov     [rsp+48h+var_14], 0
0x18007e979  mov     edx, 4; int
0x18007e97e  mov     rcx, rsi; this
0x18007e981  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007e986  mov     edi, eax
0x18007e988  test    eax, eax
0x18007e98a  jns     loc_18007EA43
0x18007e990  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e997  test    rcx, rcx
0x18007e99a  jnz     short loc_18007E9E3
0x18007e99c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007e9a3  nop     dword ptr [rax+rax+00h]
0x18007e9a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e9af  mov     rcx, rax
0x18007e9b2  test    rax, rax
0x18007e9b5  jz      short loc_18007E9D5
0x18007e9b7  mov     rax, [rax]
0x18007e9ba  mov     edx, 7F0h
0x18007e9bf  mov     rax, [rax+8]
0x18007e9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e9c8  test    eax, eax
0x18007e9ca  jz      short loc_18007E9D5
0x18007e9cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e9d3  jmp     short loc_18007E9E3
0x18007e9d5  lea     rcx, qword_1800DBF70; this
0x18007e9dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007e9e3  cmp     byte ptr [rcx+8], 0
0x18007e9e7  jz      short loc_18007EA0E
0x18007e9e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007e9ee  cmp     [rax+7CCh], edi
0x18007e9f4  jz      short loc_18007EA0E
0x18007e9f6  mov     r9d, edi; int
0x18007e9f9  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007ea00  mov     r8d, 39Fh; int
0x18007ea06  mov     rcx, rax; this
0x18007ea09  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ea0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ea15  jb      loc_18007EC0C
0x18007ea1b  mov     edx, 55h ; 'U'
0x18007ea20  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ea27  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007ea2e  xor     r9d, r9d
0x18007ea31  mov     [rsp+48h+var_28], edi
0x18007ea35  mov     rcx, [rcx+10h]
0x18007ea39  call    WPP_SF_qD
0x18007ea3e  jmp     loc_18007EC0C
0x18007ea43  mov     r9d, [rsp+48h+var_14]
0x18007ea48  cmp     r9d, 7
0x18007ea4c  ja      loc_18007EAD6
0x18007ea52  jz      short loc_18007EACB
0x18007ea54  mov     eax, r9d
0x18007ea57  test    r9d, r9d
0x18007ea5a  jz      short loc_18007EAC0
0x18007ea5c  sub     eax, 1
0x18007ea5f  jz      short loc_18007EAB5
0x18007ea61  sub     eax, 1
0x18007ea64  jz      short loc_18007EAAA
0x18007ea66  sub     eax, 1
0x18007ea69  jz      short loc_18007EA9F
0x18007ea6b  sub     eax, 1
0x18007ea6e  jz      short loc_18007EA94
0x18007ea70  sub     eax, 1
0x18007ea73  jz      short loc_18007EA89
0x18007ea75  cmp     eax, 1
0x18007ea78  jnz     loc_18007EB0B
0x18007ea7e  mov     dword ptr [rbx], 5DC0h
0x18007ea84  jmp     loc_18007EC0C
0x18007ea89  mov     dword ptr [rbx], 7D00h
0x18007ea8f  jmp     loc_18007EC0C
0x18007ea94  mov     dword ptr [rbx], 0AC44h
0x18007ea9a  jmp     loc_18007EC0C
0x18007ea9f  mov     dword ptr [rbx], 0BB80h
0x18007eaa5  jmp     loc_18007EC0C
0x18007eaaa  mov     dword ptr [rbx], 0FA00h
0x18007eab0  jmp     loc_18007EC0C
0x18007eab5  mov     dword ptr [rbx], 15888h
0x18007eabb  jmp     loc_18007EC0C
0x18007eac0  mov     dword ptr [rbx], 17700h
0x18007eac6  jmp     loc_18007EC0C
0x18007eacb  mov     dword ptr [rbx], 5622h
0x18007ead1  jmp     loc_18007EC0C
0x18007ead6  mov     eax, r9d
0x18007ead9  sub     eax, 8
0x18007eadc  jz      loc_18007EC06
0x18007eae2  sub     eax, 1
0x18007eae5  jz      loc_18007EBFE
0x18007eaeb  sub     eax, 1
0x18007eaee  jz      loc_18007EBF6
0x18007eaf4  sub     eax, 1
0x18007eaf7  jz      loc_18007EBEE
0x18007eafd  sub     eax, 1
0x18007eb00  jz      loc_18007EBE6
0x18007eb06  cmp     eax, 3
0x18007eb09  jz      short loc_18007EB3B
0x18007eb0b  cmp     cs:byte_1800DC8D1, 1
0x18007eb12  jb      short loc_18007EB30
0x18007eb14  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb1b  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007eb22  mov     edx, 57h ; 'W'
0x18007eb27  mov     rcx, [rcx+38h]
0x18007eb2b  call    WPP_SF_d
0x18007eb30  mov     dword ptr [rbx], 0
0x18007eb36  jmp     loc_18007EC0C
0x18007eb3b  mov     r8, rbx; unsigned int *
0x18007eb3e  mov     edx, 18h; int
0x18007eb43  mov     rcx, rsi; this
0x18007eb46  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007eb4b  mov     edi, eax
0x18007eb4d  test    eax, eax
0x18007eb4f  jns     loc_18007EC0C
0x18007eb55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eb5c  test    rcx, rcx
0x18007eb5f  jnz     short loc_18007EBA8
0x18007eb61  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007eb68  nop     dword ptr [rax+rax+00h]
0x18007eb6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eb74  mov     rcx, rax
0x18007eb77  test    rax, rax
0x18007eb7a  jz      short loc_18007EB9A
0x18007eb7c  mov     rax, [rax]
0x18007eb7f  mov     edx, 7F0h
0x18007eb84  mov     rax, [rax+8]
0x18007eb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb8d  test    eax, eax
0x18007eb8f  jz      short loc_18007EB9A
0x18007eb91  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eb98  jmp     short loc_18007EBA8
0x18007eb9a  lea     rcx, qword_1800DBF70; this
0x18007eba1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007eba8  cmp     byte ptr [rcx+8], 0
0x18007ebac  jz      short loc_18007EBD3
0x18007ebae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007ebb3  cmp     [rax+7CCh], edi
0x18007ebb9  jz      short loc_18007EBD3
0x18007ebbb  mov     r9d, edi; int
0x18007ebbe  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007ebc5  mov     r8d, 3B4h; int
0x18007ebcb  mov     rcx, rax; this
0x18007ebce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007ebd3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ebda  jb      short loc_18007EC0C
0x18007ebdc  mov     edx, 56h ; 'V'
0x18007ebe1  jmp     loc_18007EA20
0x18007ebe6  mov     dword ptr [rbx], 1CB6h
0x18007ebec  jmp     short loc_18007EC0C
0x18007ebee  mov     dword ptr [rbx], 1F40h
0x18007ebf4  jmp     short loc_18007EC0C
0x18007ebf6  mov     dword ptr [rbx], 2B11h
0x18007ebfc  jmp     short loc_18007EC0C
0x18007ebfe  mov     dword ptr [rbx], 2EE0h
0x18007ec04  jmp     short loc_18007EC0C
0x18007ec06  mov     dword ptr [rbx], 3E80h
0x18007ec0c  lea     rcx, [rsp+48h+var_18]; this
0x18007ec11  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007ec16  mov     rbx, [rsp+48h+arg_10]
0x18007ec1b  mov     eax, edi
0x18007ec1d  mov     rsi, [rsp+48h+arg_18]
0x18007ec22  add     rsp, 40h
0x18007ec26  pop     rdi
0x18007ec27  retn
```
