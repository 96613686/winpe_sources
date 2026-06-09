# ESIMPM::EsimPoMgr::WaitTillOOBEComplete(void)

- ea: `0x14002537c`
- end: `0x140025643`
- name: `?WaitTillOOBEComplete@EsimPoMgr@ESIMPM@@AEAAKXZ`
- size: `711`
- prototype: `unsigned int __fastcall(ESIMPM::EsimPoMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140024d88`

## callees

- `0x140001278`
- `0x140001308`
- `0x14000168c`
- `0x14002537c`
- `0x14002564c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400255a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400255a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140025422`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140025422`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400253a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400253a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025440`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025440`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x140025396`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x1400254b3`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x140025396`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x1400254b3`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x14002545d`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x14002545d`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x14002560a`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x14002560a`

## string_xrefs

- `0x1400253bc`: `ESIMPM::EsimPoMgr::WaitTillOOBEComplete`
- `0x140025492`: `ESIMPM::EsimPoMgr::WaitTillOOBEComplete`
- `0x1400254dc`: `ESIMPM::EsimPoMgr::WaitTillOOBEComplete`
- `0x1400254fc`: `ESIMPM::EsimPoMgr::WaitTillOOBEComplete`
- `0x14002561a`: `UnregisterWaitUntilOOBECompleted failed [errCode: %d]`

## pseudocode

```c
__int64 __fastcall ESIMPM::EsimPoMgr::WaitTillOOBEComplete(ESIMPM::EsimPoMgr *this)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  DWORD LastError; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rdx
  char *v9; // rdx
  HANDLE EventW; // rax
  HANDLE v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  DWORD v15; // eax
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  const char *v18; // [rsp+70h] [rbp+20h] BYREF
  int v19; // [rsp+78h] [rbp+28h] BYREF
  const char *v20; // [rsp+80h] [rbp+30h] BYREF
  int v21; // [rsp+88h] [rbp+38h] BYREF

  v18 = (const char *)this;
  v19 = 0;
  if ( !(unsigned int)OOBEComplete(&v19) )
  {
    LastError = GetLastError();
    if ( LastError == 50 )
    {
      if ( (unsigned int)dword_140075078 > 4 )
      {
        v18 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v4,
          (__int64)byte_14006A93B,
          v6,
          v7,
          (const unsigned __int16 **)&v18);
      }
      return 0;
    }
    if ( (unsigned int)dword_140075078 <= 2 )
      return LastError;
    v8 = byte_14006A909;
LABEL_16:
    v20 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
    LODWORD(v18) = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v4,
      (__int64)v8,
      v6,
      v7,
      (__int64)&v18,
      (const unsigned __int16 **)&v20);
    return LastError;
  }
  LastError = 0;
  if ( v19 )
  {
    if ( (unsigned int)dword_140075078 <= 4 )
      return LastError;
    v9 = byte_14006A8E3;
LABEL_21:
    v18 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v1,
      (__int64)v9,
      v2,
      v3,
      (const unsigned __int16 **)&v18);
    return LastError;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v11 = ESIMPM::EsimPoMgr::m_waitOobeHandle;
  ESIMPM::EsimPoMgr::m_waitOobeHandle = EventW;
  if ( (unsigned __int64)v11 + 1 > 1 )
    CloseHandle(v11);
  ESIMPM::EsimPoMgr::m_OobeRegisterHandle = 0;
  if ( !(unsigned int)RegisterWaitUntilOOBECompleted(
                        ESIMPM::EsimPoMgr::s_OobeCompletedCallback,
                        0,
                        &ESIMPM::EsimPoMgr::m_OobeRegisterHandle) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_140075078 <= 2 )
      return LastError;
    v8 = &byte_14006A89F;
    goto LABEL_16;
  }
  if ( (unsigned int)OOBEComplete(&v19) && v19 )
  {
    if ( (unsigned int)dword_140075078 <= 4 )
      return LastError;
    v9 = byte_14006A875;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_140075078 > 4 )
  {
    v18 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v1,
      (__int64)&word_14006A83E,
      v2,
      v3,
      (const unsigned __int16 **)&v18);
  }
  if ( (unsigned int)dword_140075040 > 5
    && (qword_140075050 & 0x800000000000LL) != 0
    && (qword_140075058 & 0x800000000000LL) == qword_140075058 )
  {
    LOBYTE(v18) = 0;
    LODWORD(v20) = 1;
    v21 = 0;
    v17 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      qword_140075058,
      (__int64)&dword_14006A7EC,
      v2,
      v3,
      (__int64)&v17,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v18);
  }
  if ( WaitForSingleObject(ESIMPM::EsimPoMgr::m_waitOobeHandle, 0xFFFFFFFF) )
  {
    LastError = 31;
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v20 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
      LODWORD(v18) = 31;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v12,
        (__int64)byte_14006A79B,
        v13,
        v14,
        (__int64)&v18,
        (const unsigned __int16 **)&v20);
    }
  }
  else if ( (unsigned int)dword_140075078 > 4 )
  {
    v18 = "ESIMPM::EsimPoMgr::WaitTillOOBEComplete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v12,
      (__int64)word_14006A76A,
      v13,
      v14,
      (const unsigned __int16 **)&v18);
  }
  if ( !(unsigned int)UnregisterWaitUntilOOBECompleted(ESIMPM::EsimPoMgr::m_OobeRegisterHandle) )
  {
    v15 = GetLastError();
    ESIMPM::Log::Warning(
      "ESIMPM::EsimPoMgr::WaitTillOOBEComplete",
      0,
      L"UnregisterWaitUntilOOBECompleted failed [errCode: %d]",
      v15);
  }
  ESIMPM::EsimPoMgr::m_OobeRegisterHandle = 0;
  return LastError;
}

```

## disassembly

```asm
0x14002537c  mov     [rsp-18h+arg_0], rcx
0x140025381  push    rbp
0x140025382  push    rbx
0x140025383  push    rdi
0x140025384  mov     rbp, rsp
0x140025387  sub     rsp, 50h
0x14002538b  lea     rcx, [rbp+arg_8]
0x14002538f  mov     [rbp+arg_8], 0
0x140025396  call    cs:__imp_OOBEComplete
0x14002539c  test    eax, eax
0x14002539e  jnz     short loc_1400253F4
0x1400253a0  call    cs:__imp_GetLastError
0x1400253a6  mov     edi, eax
0x1400253a8  cmp     eax, 32h ; '2'
0x1400253ab  mov     eax, cs:dword_140075078
0x1400253b1  jnz     short loc_1400253DF
0x1400253b3  cmp     eax, 4
0x1400253b6  jbe     short loc_1400253D8
0x1400253b8  lea     rax, [rbp+arg_0]
0x1400253bc  lea     rbx, aEsimpmEsimpomg_16; "ESIMPM::EsimPoMgr::WaitTillOOBEComplete"
0x1400253c3  mov     [rsp+50h+var_30], rax
0x1400253c8  lea     rdx, byte_14006A93B
0x1400253cf  mov     [rbp+arg_0], rbx
0x1400253d3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400253d8  xor     edi, edi
0x1400253da  jmp     loc_140025639
0x1400253df  cmp     eax, 2
0x1400253e2  jbe     loc_140025639
0x1400253e8  lea     rdx, byte_14006A909
0x1400253ef  jmp     loc_140025485
0x1400253f4  xor     edi, edi
0x1400253f6  cmp     [rbp+arg_8], edi
0x1400253f9  jz      short loc_140025416
0x1400253fb  mov     eax, cs:dword_140075078
0x140025401  cmp     eax, 4
0x140025404  jbe     loc_140025639
0x14002540a  lea     rdx, byte_14006A8E3
0x140025411  jmp     loc_1400254D8
0x140025416  xor     r9d, r9d; lpName
0x140025419  xor     r8d, r8d; bInitialState
0x14002541c  xor     ecx, ecx; lpEventAttributes
0x14002541e  lea     edx, [r9+1]; bManualReset
0x140025422  call    cs:__imp_CreateEventW
0x140025428  mov     rcx, cs:?m_waitOobeHandle@EsimPoMgr@ESIMPM@@0V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; hObject
0x14002542f  mov     cs:?m_waitOobeHandle@EsimPoMgr@ESIMPM@@0V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A, rax; tlx::unique_any<tlx::file_handle_traits> ESIMPM::EsimPoMgr::m_waitOobeHandle
0x140025436  lea     rax, [rcx+1]
0x14002543a  cmp     rax, 1
0x14002543e  jbe     short loc_140025446
0x140025440  call    cs:__imp_CloseHandle
0x140025446  lea     r8, ?m_OobeRegisterHandle@EsimPoMgr@ESIMPM@@0PEAXEA; void * ESIMPM::EsimPoMgr::m_OobeRegisterHandle
0x14002544d  mov     cs:?m_OobeRegisterHandle@EsimPoMgr@ESIMPM@@0PEAXEA, rdi; void * ESIMPM::EsimPoMgr::m_OobeRegisterHandle
0x140025454  xor     edx, edx
0x140025456  lea     rcx, ?s_OobeCompletedCallback@EsimPoMgr@ESIMPM@@CAXPEAX@Z; ESIMPM::EsimPoMgr::s_OobeCompletedCallback(void *)
0x14002545d  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x140025463  test    eax, eax
0x140025465  jnz     short loc_1400254AF
0x140025467  call    cs:__imp_GetLastError
0x14002546d  mov     edi, eax
0x14002546f  mov     eax, cs:dword_140075078
0x140025475  cmp     eax, 2
0x140025478  jbe     loc_140025639
0x14002547e  lea     rdx, byte_14006A89F
0x140025485  lea     rax, [rbp+arg_10]
0x140025489  mov     [rsp+50h+var_28], rax
0x14002548e  lea     rax, [rbp+arg_0]
0x140025492  lea     rbx, aEsimpmEsimpomg_16; "ESIMPM::EsimPoMgr::WaitTillOOBEComplete"
0x140025499  mov     [rsp+50h+var_30], rax
0x14002549e  mov     [rbp+arg_10], rbx
0x1400254a2  mov     dword ptr [rbp+arg_0], edi
0x1400254a5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400254aa  jmp     loc_140025639
0x1400254af  lea     rcx, [rbp+arg_8]
0x1400254b3  call    cs:__imp_OOBEComplete
0x1400254b9  test    eax, eax
0x1400254bb  jz      short loc_1400254F6
0x1400254bd  cmp     [rbp+arg_8], edi
0x1400254c0  jz      short loc_1400254F6
0x1400254c2  mov     eax, cs:dword_140075078
0x1400254c8  cmp     eax, 4
0x1400254cb  jbe     loc_140025639
0x1400254d1  lea     rdx, byte_14006A875
0x1400254d8  lea     rax, [rbp+arg_0]
0x1400254dc  lea     rbx, aEsimpmEsimpomg_16; "ESIMPM::EsimPoMgr::WaitTillOOBEComplete"
0x1400254e3  mov     [rsp+50h+var_30], rax
0x1400254e8  mov     [rbp+arg_0], rbx
0x1400254ec  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400254f1  jmp     loc_140025639
0x1400254f6  mov     eax, cs:dword_140075078
0x1400254fc  lea     rbx, aEsimpmEsimpomg_16; "ESIMPM::EsimPoMgr::WaitTillOOBEComplete"
0x140025503  cmp     eax, 4
0x140025506  jbe     short loc_140025521
0x140025508  lea     rax, [rbp+arg_0]
0x14002550c  mov     [rbp+arg_0], rbx
0x140025510  lea     rdx, word_14006A83E
0x140025517  mov     [rsp+50h+var_30], rax
0x14002551c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140025521  mov     eax, cs:dword_140075040
0x140025527  cmp     eax, 5
0x14002552a  jbe     short loc_14002559A
0x14002552c  mov     rcx, cs:qword_140075058
0x140025533  mov     rdx, 800000000000h
0x14002553d  mov     rax, cs:qword_140075050
0x140025544  test    rdx, rax
0x140025547  jz      short loc_14002559A
0x140025549  mov     rax, rcx
0x14002554c  and     rax, rdx
0x14002554f  cmp     rax, rcx
0x140025552  jnz     short loc_14002559A
0x140025554  lea     rax, [rbp+arg_0]
0x140025558  mov     byte ptr [rbp+arg_0], dil
0x14002555c  mov     [rsp+50h+var_18], rax
0x140025561  lea     rdx, dword_14006A7EC
0x140025568  lea     rax, [rbp+arg_10]
0x14002556c  mov     dword ptr [rbp+arg_10], 1
0x140025573  mov     [rsp+50h+var_20], rax
0x140025578  lea     rax, [rbp+arg_18]
0x14002557c  mov     [rsp+50h+var_28], rax
0x140025581  lea     rax, [rbp+var_10]
0x140025585  mov     [rsp+50h+var_30], rax
0x14002558a  mov     [rbp+arg_18], edi
0x14002558d  mov     [rbp+var_10], 1000800h
0x140025595  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002559a  mov     rcx, cs:?m_waitOobeHandle@EsimPoMgr@ESIMPM@@0V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; hHandle
0x1400255a1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400255a4  call    cs:__imp_WaitForSingleObject
0x1400255aa  test    eax, eax
0x1400255ac  mov     eax, cs:dword_140075078
0x1400255b2  jz      short loc_1400255E5
0x1400255b4  mov     edi, 1Fh
0x1400255b9  cmp     eax, 2
0x1400255bc  jbe     short loc_140025603
0x1400255be  lea     rax, [rbp+arg_10]
0x1400255c2  mov     [rbp+arg_10], rbx
0x1400255c6  mov     [rsp+50h+var_28], rax
0x1400255cb  lea     rdx, byte_14006A79B
0x1400255d2  lea     rax, [rbp+arg_0]
0x1400255d6  mov     dword ptr [rbp+arg_0], edi
0x1400255d9  mov     [rsp+50h+var_30], rax
0x1400255de  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400255e3  jmp     short loc_140025603
0x1400255e5  cmp     eax, 4
0x1400255e8  jbe     short loc_140025603
0x1400255ea  lea     rax, [rbp+arg_0]
0x1400255ee  mov     [rbp+arg_0], rbx
0x1400255f2  lea     rdx, word_14006A76A
0x1400255f9  mov     [rsp+50h+var_30], rax
0x1400255fe  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140025603  mov     rcx, cs:?m_OobeRegisterHandle@EsimPoMgr@ESIMPM@@0PEAXEA; void * ESIMPM::EsimPoMgr::m_OobeRegisterHandle
0x14002560a  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x140025610  test    eax, eax
0x140025612  jnz     short loc_14002562E
0x140025614  call    cs:__imp_GetLastError
0x14002561a  lea     r8, aUnregisterwait; "UnregisterWaitUntilOOBECompleted failed"...
0x140025621  xor     edx, edx; struct _GUID *
0x140025623  mov     r9d, eax
0x140025626  mov     rcx, rbx; char *
0x140025629  call    ?Warning@Log@ESIMPM@@SAXPEBDPEBU_GUID@@PEBGZZ; ESIMPM::Log::Warning(char const *,_GUID const *,ushort const *,...)
0x14002562e  mov     cs:?m_OobeRegisterHandle@EsimPoMgr@ESIMPM@@0PEAXEA, 0; void * ESIMPM::EsimPoMgr::m_OobeRegisterHandle
0x140025639  mov     eax, edi
0x14002563b  add     rsp, 50h
0x14002563f  pop     rdi
0x140025640  pop     rbx
0x140025641  pop     rbp
0x140025642  retn
```
