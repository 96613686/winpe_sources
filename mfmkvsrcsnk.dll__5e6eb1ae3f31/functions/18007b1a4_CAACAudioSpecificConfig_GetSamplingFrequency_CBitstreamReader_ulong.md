# CAACAudioSpecificConfig::GetSamplingFrequency(CBitstreamReader &,ulong *)

- ea: `0x18007b1a4`
- end: `0x18007b480`
- name: `?GetSamplingFrequency@CAACAudioSpecificConfig@@CAJAEAVCBitstreamReader@@PEAK@Z`
- size: `732`
- prototype: `__int64 __fastcall(struct CBitstreamReader *this, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18007b488`
- `0x180081210`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180041538`
- `0x180071330`
- `0x18007b1a4`
- `0x180082b6c`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b3bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b200`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007b3bf`

## string_xrefs

- `0x18007b1b9`: `CAACAudioSpecificConfig::GetSamplingFrequency`
- `0x18007b257`: `CAACAudioSpecificConfig::GetSamplingFrequency`
- `0x18007b416`: `CAACAudioSpecificConfig::GetSamplingFrequency`

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
                v15 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          if ( byte_1800D78D1 )
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18007b1a4  mov     [rsp+arg_10], rbx
0x18007b1a9  mov     [rsp+arg_18], rsi
0x18007b1ae  push    rdi
0x18007b1af  sub     rsp, 40h
0x18007b1b3  mov     rbx, rdx
0x18007b1b6  mov     rsi, rcx
0x18007b1b9  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007b1c0  mov     r8d, 39Bh; int
0x18007b1c6  lea     rcx, [rsp+48h+var_18]; this
0x18007b1cb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18007b1d0  lea     r8, [rsp+48h+var_14]; unsigned int *
0x18007b1d5  mov     [rsp+48h+var_14], 0
0x18007b1dd  mov     edx, 4; int
0x18007b1e2  mov     rcx, rsi; this
0x18007b1e5  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007b1ea  mov     edi, eax
0x18007b1ec  test    eax, eax
0x18007b1ee  jns     loc_18007B2A1
0x18007b1f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b1fb  test    rcx, rcx
0x18007b1fe  jnz     short loc_18007B241
0x18007b200  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b206  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b20d  mov     rcx, rax
0x18007b210  test    rax, rax
0x18007b213  jz      short loc_18007B233
0x18007b215  mov     rax, [rax]
0x18007b218  mov     edx, 7F0h
0x18007b21d  mov     rax, [rax+8]
0x18007b221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b226  test    eax, eax
0x18007b228  jz      short loc_18007B233
0x18007b22a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b231  jmp     short loc_18007B241
0x18007b233  lea     rcx, qword_1800D6F70; this
0x18007b23a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b241  cmp     byte ptr [rcx+8], 0
0x18007b245  jz      short loc_18007B26C
0x18007b247  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b24c  cmp     [rax+7CCh], edi
0x18007b252  jz      short loc_18007B26C
0x18007b254  mov     r9d, edi; int
0x18007b257  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007b25e  mov     r8d, 39Fh; int
0x18007b264  mov     rcx, rax; this
0x18007b267  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b26c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b273  jb      loc_18007B464
0x18007b279  mov     edx, 55h ; 'U'
0x18007b27e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b285  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007b28c  xor     r9d, r9d
0x18007b28f  mov     [rsp+48h+var_28], edi
0x18007b293  mov     rcx, [rcx+10h]
0x18007b297  call    WPP_SF_qD
0x18007b29c  jmp     loc_18007B464
0x18007b2a1  mov     r9d, [rsp+48h+var_14]
0x18007b2a6  cmp     r9d, 7
0x18007b2aa  ja      loc_18007B334
0x18007b2b0  jz      short loc_18007B329
0x18007b2b2  mov     eax, r9d
0x18007b2b5  test    r9d, r9d
0x18007b2b8  jz      short loc_18007B31E
0x18007b2ba  sub     eax, 1
0x18007b2bd  jz      short loc_18007B313
0x18007b2bf  sub     eax, 1
0x18007b2c2  jz      short loc_18007B308
0x18007b2c4  sub     eax, 1
0x18007b2c7  jz      short loc_18007B2FD
0x18007b2c9  sub     eax, 1
0x18007b2cc  jz      short loc_18007B2F2
0x18007b2ce  sub     eax, 1
0x18007b2d1  jz      short loc_18007B2E7
0x18007b2d3  cmp     eax, 1
0x18007b2d6  jnz     loc_18007B369
0x18007b2dc  mov     dword ptr [rbx], 5DC0h
0x18007b2e2  jmp     loc_18007B464
0x18007b2e7  mov     dword ptr [rbx], 7D00h
0x18007b2ed  jmp     loc_18007B464
0x18007b2f2  mov     dword ptr [rbx], 0AC44h
0x18007b2f8  jmp     loc_18007B464
0x18007b2fd  mov     dword ptr [rbx], 0BB80h
0x18007b303  jmp     loc_18007B464
0x18007b308  mov     dword ptr [rbx], 0FA00h
0x18007b30e  jmp     loc_18007B464
0x18007b313  mov     dword ptr [rbx], 15888h
0x18007b319  jmp     loc_18007B464
0x18007b31e  mov     dword ptr [rbx], 17700h
0x18007b324  jmp     loc_18007B464
0x18007b329  mov     dword ptr [rbx], 5622h
0x18007b32f  jmp     loc_18007B464
0x18007b334  mov     eax, r9d
0x18007b337  sub     eax, 8
0x18007b33a  jz      loc_18007B45E
0x18007b340  sub     eax, 1
0x18007b343  jz      loc_18007B456
0x18007b349  sub     eax, 1
0x18007b34c  jz      loc_18007B44E
0x18007b352  sub     eax, 1
0x18007b355  jz      loc_18007B446
0x18007b35b  sub     eax, 1
0x18007b35e  jz      loc_18007B43E
0x18007b364  cmp     eax, 3
0x18007b367  jz      short loc_18007B399
0x18007b369  cmp     cs:byte_1800D78D1, 1
0x18007b370  jb      short loc_18007B38E
0x18007b372  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b379  lea     r8, WPP_4e941f9307c03dae3e748ea9d1e0c920_Traceguids
0x18007b380  mov     edx, 57h ; 'W'
0x18007b385  mov     rcx, [rcx+38h]
0x18007b389  call    WPP_SF_d
0x18007b38e  mov     dword ptr [rbx], 0
0x18007b394  jmp     loc_18007B464
0x18007b399  mov     r8, rbx; unsigned int *
0x18007b39c  mov     edx, 18h; int
0x18007b3a1  mov     rcx, rsi; this
0x18007b3a4  call    ?PopN@CBitstreamReader@@QEAAJHPEAK@Z; CBitstreamReader::PopN(int,ulong *)
0x18007b3a9  mov     edi, eax
0x18007b3ab  test    eax, eax
0x18007b3ad  jns     loc_18007B464
0x18007b3b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b3ba  test    rcx, rcx
0x18007b3bd  jnz     short loc_18007B400
0x18007b3bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007b3c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b3cc  mov     rcx, rax
0x18007b3cf  test    rax, rax
0x18007b3d2  jz      short loc_18007B3F2
0x18007b3d4  mov     rax, [rax]
0x18007b3d7  mov     edx, 7F0h
0x18007b3dc  mov     rax, [rax+8]
0x18007b3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3e5  test    eax, eax
0x18007b3e7  jz      short loc_18007B3F2
0x18007b3e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b3f0  jmp     short loc_18007B400
0x18007b3f2  lea     rcx, qword_1800D6F70; this
0x18007b3f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18007b400  cmp     byte ptr [rcx+8], 0
0x18007b404  jz      short loc_18007B42B
0x18007b406  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18007b40b  cmp     [rax+7CCh], edi
0x18007b411  jz      short loc_18007B42B
0x18007b413  mov     r9d, edi; int
0x18007b416  lea     rdx, aCaacaudiospeci_3; "CAACAudioSpecificConfig::GetSamplingFre"...
0x18007b41d  mov     r8d, 3B4h; int
0x18007b423  mov     rcx, rax; this
0x18007b426  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18007b42b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007b432  jb      short loc_18007B464
0x18007b434  mov     edx, 56h ; 'V'
0x18007b439  jmp     loc_18007B27E
0x18007b43e  mov     dword ptr [rbx], 1CB6h
0x18007b444  jmp     short loc_18007B464
0x18007b446  mov     dword ptr [rbx], 1F40h
0x18007b44c  jmp     short loc_18007B464
0x18007b44e  mov     dword ptr [rbx], 2B11h
0x18007b454  jmp     short loc_18007B464
0x18007b456  mov     dword ptr [rbx], 2EE0h
0x18007b45c  jmp     short loc_18007B464
0x18007b45e  mov     dword ptr [rbx], 3E80h
0x18007b464  lea     rcx, [rsp+48h+var_18]; this
0x18007b469  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007b46e  mov     rbx, [rsp+48h+arg_10]
0x18007b473  mov     eax, edi
0x18007b475  mov     rsi, [rsp+48h+arg_18]
0x18007b47a  add     rsp, 40h
0x18007b47e  pop     rdi
0x18007b47f  retn
```
