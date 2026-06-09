# CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics(int)

- ea: `0x18014e9b0`
- end: `0x18014eea8`
- name: `?UpdateMediaSourceCharacteristics@CMFByteStreamMediaSource@@AEAAJH@Z`
- size: `1272`
- prototype: `__int64 __fastcall(CMFByteStreamMediaSource *__hidden this, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180084c0c`
- `0x18009256c`
- `0x18014a228`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18003e398`
- `0x180079680`
- `0x18007a0bc`
- `0x18013f664`
- `0x18013fe10`
- `0x18014e9b0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014eac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014eb96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ec53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ecff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014edc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014eac3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014eb96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ec53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014ecff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18014edc7`
- `MFPlat!MFCreateMediaEvent` at `0x18014eaa1`
- `MFPlat!MFCreateMediaEvent` at `0x18014eaa1`

## string_xrefs

- `0x18014e9c3`: `CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics(CMFByteStreamMediaSource *this, int a2)
{
  int v4; // r9d
  int v5; // edx
  unsigned int v6; // r8d
  unsigned int v7; // esi
  __int64 v8; // rdx
  HRESULT v9; // ebx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v31; // [rsp+60h] [rbp+8h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v31,
    "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics",
    2772);
  v4 = *((_DWORD *)this + 270);
  v5 = *((_DWORD *)this + 290);
  v6 = v4 & 0xFFFFFF75;
  ppEvent = 0;
  if ( (v5 & 4) != 0 && (unsigned int)CMFByteStreamMediaSource::PluginCanSeek(this) )
    v6 |= 2u;
  if ( (v6 & 2) != 0 && (v5 & 0x100) != 0 && !*((_DWORD *)this + 291) )
    v6 |= 8u;
  v7 = v6 | 0x80;
  if ( (v5 & 0x800) == 0 )
    v7 = v6;
  if ( v4 == v7 )
  {
LABEL_60:
    v9 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 115) + 48LL))(
           *((_QWORD *)this + 115),
           (char *)this + 1040,
           (char *)this + 1048);
    if ( v9 >= 0 )
    {
      if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
        WPP_SF_qII(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          264,
          &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
          this,
          *((_QWORD *)this + 130),
          *((_QWORD *)this + 131));
    }
    else
    {
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics",
            2829,
            v9);
      }
      if ( g_wppLevels )
      {
        v13 = 263;
        goto LABEL_25;
      }
    }
    goto LABEL_73;
  }
  if ( (unsigned __int8)byte_1801BA10B >= 8u )
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      258,
      &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids,
      this,
      v4,
      v7);
  if ( !a2 )
  {
LABEL_59:
    *((_DWORD *)this + 270) = v7;
    goto LABEL_60;
  }
  v9 = MFCreateMediaEvent(0xDBu, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
  if ( v9 < 0 )
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2815, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 259;
LABEL_25:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, this, v9);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  v9 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
         ppEvent,
         &MF_EVENT_SOURCE_CHARACTERISTICS,
         v7);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
           ppEvent,
           &MF_EVENT_SOURCE_CHARACTERISTICS_OLD,
           *((unsigned int *)this + 270));
    if ( v9 < 0 )
    {
      v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( *((_DWORD *)v21 + 499) != v9 )
          CallStackContext::TraceFailure(v21, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2818, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 261;
        goto LABEL_25;
      }
      goto LABEL_73;
    }
    v9 = CMFMediaEventGenerator::QueueEvent((CMFByteStreamMediaSource *)((char *)this + 768), ppEvent);
    if ( v9 < 0 )
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
        v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
        if ( *((_DWORD *)v25 + 499) != v9 )
          CallStackContext::TraceFailure(v25, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2820, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 262;
        goto LABEL_25;
      }
      goto LABEL_73;
    }
    goto LABEL_59;
  }
  v15 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
    CallStackTracing::s_wpInstance = v16;
    if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v15 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v15 + 8) )
  {
    v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
    if ( *((_DWORD *)v17 + 499) != v9 )
      CallStackContext::TraceFailure(v17, "CMFByteStreamMediaSource::UpdateMediaSourceCharacteristics", 2817, v9);
  }
  if ( g_wppLevels )
  {
    v13 = 260;
    goto LABEL_25;
  }
LABEL_73:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppEvent);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v31);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18014e9b0  mov     [rsp+arg_8], rbx
0x18014e9b5  push    rsi
0x18014e9b6  push    rdi
0x18014e9b7  push    r12
0x18014e9b9  push    r14
0x18014e9bb  push    r15
0x18014e9bd  sub     rsp, 30h
0x18014e9c1  mov     ebx, edx
0x18014e9c3  lea     r12, aCmfbytestreamm_53; "CMFByteStreamMediaSource::UpdateMediaSo"...
0x18014e9ca  mov     rdi, rcx
0x18014e9cd  mov     rdx, r12; char *
0x18014e9d0  mov     r8d, 0AD4h; int
0x18014e9d6  lea     rcx, [rsp+58h+arg_0]; this
0x18014e9db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18014e9e0  mov     r9d, [rdi+438h]
0x18014e9e7  mov     r8d, r9d
0x18014e9ea  mov     edx, [rdi+488h]
0x18014e9f0  and     r8d, 0FFFFFF75h
0x18014e9f7  mov     [rsp+58h+arg_10], 0
0x18014ea00  test    dl, 4
0x18014ea03  jz      short loc_18014EA15
0x18014ea05  mov     rcx, rdi; this
0x18014ea08  call    ?PluginCanSeek@CMFByteStreamMediaSource@@AEAAHXZ; CMFByteStreamMediaSource::PluginCanSeek(void)
0x18014ea0d  test    eax, eax
0x18014ea0f  jz      short loc_18014EA15
0x18014ea11  or      r8d, 2
0x18014ea15  test    r8b, 2
0x18014ea19  jz      short loc_18014EA2E
0x18014ea1b  bt      edx, 8
0x18014ea1f  jnb     short loc_18014EA2E
0x18014ea21  cmp     dword ptr [rdi+48Ch], 0
0x18014ea28  jnz     short loc_18014EA2E
0x18014ea2a  or      r8d, 8
0x18014ea2e  mov     esi, r8d
0x18014ea31  lea     r15, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x18014ea38  bts     esi, 7
0x18014ea3c  bt      edx, 0Bh
0x18014ea40  cmovnb  esi, r8d
0x18014ea44  cmp     r9d, esi
0x18014ea47  jz      loc_18014ED8A
0x18014ea4d  cmp     cs:byte_1801BA10B, 8
0x18014ea54  jb      short loc_18014EA7D
0x18014ea56  mov     rcx, cs:WPP_GLOBAL_Control
0x18014ea5d  mov     edx, 102h
0x18014ea62  mov     dword ptr [rsp+58h+var_30], esi
0x18014ea66  mov     r8, r15
0x18014ea69  mov     dword ptr [rsp+58h+ppEvent], r9d
0x18014ea6e  mov     r9, rdi
0x18014ea71  mov     rcx, [rcx+88h]
0x18014ea78  call    WPP_SF_qDD
0x18014ea7d  test    ebx, ebx
0x18014ea7f  jz      loc_18014ED84
0x18014ea85  lea     rax, [rsp+58h+arg_10]
0x18014ea8a  xor     r9d, r9d; pvValue
0x18014ea8d  xor     r8d, r8d; hrStatus
0x18014ea90  mov     [rsp+58h+ppEvent], rax; ppEvent
0x18014ea95  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18014ea9c  mov     ecx, 0DBh; met
0x18014eaa1  call    cs:__imp_MFCreateMediaEvent
0x18014eaa8  nop     dword ptr [rax+rax+00h]
0x18014eaad  mov     ebx, eax
0x18014eaaf  test    eax, eax
0x18014eab1  jns     loc_18014EB62
0x18014eab7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014eabe  test    rcx, rcx
0x18014eac1  jnz     short loc_18014EB0A
0x18014eac3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014eaca  nop     dword ptr [rax+rax+00h]
0x18014eacf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ead6  mov     rcx, rax
0x18014ead9  test    rax, rax
0x18014eadc  jz      short loc_18014EAFC
0x18014eade  mov     rax, [rax]
0x18014eae1  mov     edx, 7F0h
0x18014eae6  mov     rax, [rax+8]
0x18014eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014eaef  test    eax, eax
0x18014eaf1  jz      short loc_18014EAFC
0x18014eaf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014eafa  jmp     short loc_18014EB0A
0x18014eafc  lea     rcx, qword_1801B97E0; this
0x18014eb03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014eb0a  cmp     byte ptr [rcx+8], 0
0x18014eb0e  jz      short loc_18014EB31
0x18014eb10  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014eb15  cmp     [rax+7CCh], ebx
0x18014eb1b  jz      short loc_18014EB31
0x18014eb1d  mov     r9d, ebx; int
0x18014eb20  mov     r8d, 0AFFh; int
0x18014eb26  mov     rdx, r12; char *
0x18014eb29  mov     rcx, rax; this
0x18014eb2c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014eb31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014eb38  jb      loc_18014EE7F
0x18014eb3e  mov     edx, 103h
0x18014eb43  mov     rcx, cs:WPP_GLOBAL_Control
0x18014eb4a  mov     r9, rdi
0x18014eb4d  mov     r8, r15
0x18014eb50  mov     dword ptr [rsp+58h+ppEvent], ebx
0x18014eb54  mov     rcx, [rcx+10h]
0x18014eb58  call    WPP_SF_qD
0x18014eb5d  jmp     loc_18014EE7F
0x18014eb62  mov     rcx, [rsp+58h+arg_10]
0x18014eb67  lea     rdx, MF_EVENT_SOURCE_CHARACTERISTICS
0x18014eb6e  mov     r8d, esi
0x18014eb71  mov     rax, [rcx]
0x18014eb74  mov     rax, [rax+0A8h]
0x18014eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014eb80  mov     ebx, eax
0x18014eb82  test    eax, eax
0x18014eb84  jns     loc_18014EC1B
0x18014eb8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014eb91  test    rcx, rcx
0x18014eb94  jnz     short loc_18014EBDD
0x18014eb96  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014eb9d  nop     dword ptr [rax+rax+00h]
0x18014eba2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014eba9  mov     rcx, rax
0x18014ebac  test    rax, rax
0x18014ebaf  jz      short loc_18014EBCF
0x18014ebb1  mov     rax, [rax]
0x18014ebb4  mov     edx, 7F0h
0x18014ebb9  mov     rax, [rax+8]
0x18014ebbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ebc2  test    eax, eax
0x18014ebc4  jz      short loc_18014EBCF
0x18014ebc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ebcd  jmp     short loc_18014EBDD
0x18014ebcf  lea     rcx, qword_1801B97E0; this
0x18014ebd6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ebdd  cmp     byte ptr [rcx+8], 0
0x18014ebe1  jz      short loc_18014EC04
0x18014ebe3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014ebe8  cmp     [rax+7CCh], ebx
0x18014ebee  jz      short loc_18014EC04
0x18014ebf0  mov     r9d, ebx; int
0x18014ebf3  mov     r8d, 0B01h; int
0x18014ebf9  mov     rdx, r12; char *
0x18014ebfc  mov     rcx, rax; this
0x18014ebff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014ec04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014ec0b  jb      loc_18014EE7F
0x18014ec11  mov     edx, 104h
0x18014ec16  jmp     loc_18014EB43
0x18014ec1b  mov     rcx, [rsp+58h+arg_10]
0x18014ec20  lea     rdx, MF_EVENT_SOURCE_CHARACTERISTICS_OLD
0x18014ec27  mov     r8d, [rdi+438h]
0x18014ec2e  mov     rax, [rcx]
0x18014ec31  mov     rax, [rax+0A8h]
0x18014ec38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ec3d  mov     ebx, eax
0x18014ec3f  test    eax, eax
0x18014ec41  jns     loc_18014ECD8
0x18014ec47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ec4e  test    rcx, rcx
0x18014ec51  jnz     short loc_18014EC9A
0x18014ec53  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014ec5a  nop     dword ptr [rax+rax+00h]
0x18014ec5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ec66  mov     rcx, rax
0x18014ec69  test    rax, rax
0x18014ec6c  jz      short loc_18014EC8C
0x18014ec6e  mov     rax, [rax]
0x18014ec71  mov     edx, 7F0h
0x18014ec76  mov     rax, [rax+8]
0x18014ec7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ec7f  test    eax, eax
0x18014ec81  jz      short loc_18014EC8C
0x18014ec83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ec8a  jmp     short loc_18014EC9A
0x18014ec8c  lea     rcx, qword_1801B97E0; this
0x18014ec93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ec9a  cmp     byte ptr [rcx+8], 0
0x18014ec9e  jz      short loc_18014ECC1
0x18014eca0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014eca5  cmp     [rax+7CCh], ebx
0x18014ecab  jz      short loc_18014ECC1
0x18014ecad  mov     r9d, ebx; int
0x18014ecb0  mov     r8d, 0B02h; int
0x18014ecb6  mov     rdx, r12; char *
0x18014ecb9  mov     rcx, rax; this
0x18014ecbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014ecc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014ecc8  jb      loc_18014EE7F
0x18014ecce  mov     edx, 105h
0x18014ecd3  jmp     loc_18014EB43
0x18014ecd8  mov     rdx, [rsp+58h+arg_10]; struct IMFMediaEvent *
0x18014ecdd  lea     rcx, [rdi+300h]; this
0x18014ece4  call    ?QueueEvent@CMFMediaEventGenerator@@QEAAJPEAUIMFMediaEvent@@@Z; CMFMediaEventGenerator::QueueEvent(IMFMediaEvent *)
0x18014ece9  mov     ebx, eax
0x18014eceb  test    eax, eax
0x18014eced  jns     loc_18014ED84
0x18014ecf3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ecfa  test    rcx, rcx
0x18014ecfd  jnz     short loc_18014ED46
0x18014ecff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014ed06  nop     dword ptr [rax+rax+00h]
0x18014ed0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ed12  mov     rcx, rax
0x18014ed15  test    rax, rax
0x18014ed18  jz      short loc_18014ED38
0x18014ed1a  mov     rax, [rax]
0x18014ed1d  mov     edx, 7F0h
0x18014ed22  mov     rax, [rax+8]
0x18014ed26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014ed2b  test    eax, eax
0x18014ed2d  jz      short loc_18014ED38
0x18014ed2f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ed36  jmp     short loc_18014ED46
0x18014ed38  lea     rcx, qword_1801B97E0; this
0x18014ed3f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ed46  cmp     byte ptr [rcx+8], 0
0x18014ed4a  jz      short loc_18014ED6D
0x18014ed4c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014ed51  cmp     [rax+7CCh], ebx
0x18014ed57  jz      short loc_18014ED6D
0x18014ed59  mov     r9d, ebx; int
0x18014ed5c  mov     r8d, 0B04h; int
0x18014ed62  mov     rdx, r12; char *
0x18014ed65  mov     rcx, rax; this
0x18014ed68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014ed6d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014ed74  jb      loc_18014EE7F
0x18014ed7a  mov     edx, 106h
0x18014ed7f  jmp     loc_18014EB43
0x18014ed84  mov     [rdi+438h], esi
0x18014ed8a  mov     rcx, [rdi+398h]
0x18014ed91  lea     rsi, [rdi+418h]
0x18014ed98  lea     r14, [rdi+410h]
0x18014ed9f  mov     r8, rsi
0x18014eda2  mov     rdx, r14
0x18014eda5  mov     rax, [rcx]
0x18014eda8  mov     rax, [rax+30h]
0x18014edac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014edb1  mov     ebx, eax
0x18014edb3  test    eax, eax
0x18014edb5  jns     loc_18014EE48
0x18014edbb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014edc2  test    rcx, rcx
0x18014edc5  jnz     short loc_18014EE0E
0x18014edc7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18014edce  nop     dword ptr [rax+rax+00h]
0x18014edd3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18014edda  mov     rcx, rax
0x18014eddd  test    rax, rax
0x18014ede0  jz      short loc_18014EE00
0x18014ede2  mov     rax, [rax]
0x18014ede5  mov     edx, 7F0h
0x18014edea  mov     rax, [rax+8]
0x18014edee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014edf3  test    eax, eax
0x18014edf5  jz      short loc_18014EE00
0x18014edf7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18014edfe  jmp     short loc_18014EE0E
0x18014ee00  lea     rcx, qword_1801B97E0; this
0x18014ee07  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18014ee0e  cmp     byte ptr [rcx+8], 0
0x18014ee12  jz      short loc_18014EE35
0x18014ee14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18014ee19  cmp     [rax+7CCh], ebx
0x18014ee1f  jz      short loc_18014EE35
0x18014ee21  mov     r9d, ebx; int
0x18014ee24  mov     r8d, 0B0Dh; int
0x18014ee2a  mov     rdx, r12; char *
0x18014ee2d  mov     rcx, rax; this
0x18014ee30  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18014ee35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18014ee3c  jb      short loc_18014EE7F
0x18014ee3e  mov     edx, 107h
0x18014ee43  jmp     loc_18014EB43
0x18014ee48  cmp     cs:byte_1801BA10B, 10h
0x18014ee4f  jb      short loc_18014EE7F
0x18014ee51  mov     rcx, [r14]
0x18014ee54  mov     edx, 108h
0x18014ee59  mov     rax, [rsi]
0x18014ee5c  mov     r9, rdi
0x18014ee5f  mov     [rsp+58h+var_30], rax
0x18014ee64  mov     r8, r15
0x18014ee67  mov     [rsp+58h+ppEvent], rcx
0x18014ee6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18014ee73  mov     rcx, [rcx+88h]
0x18014ee7a  call    WPP_SF_qII
0x18014ee7f  lea     rcx, [rsp+58h+arg_10]; void *
0x18014ee84  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18014ee89  lea     rcx, [rsp+58h+arg_0]; this
0x18014ee8e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18014ee93  mov     eax, ebx
0x18014ee95  mov     rbx, [rsp+58h+arg_8]
0x18014ee9a  add     rsp, 30h
0x18014ee9e  pop     r15
0x18014eea0  pop     r14
0x18014eea2  pop     r12
0x18014eea4  pop     rdi
0x18014eea5  pop     rsi
0x18014eea6  retn
```
