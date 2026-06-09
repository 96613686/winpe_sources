# RdsDWMDirectUpdateProcessor::Initialize(void)

- ea: `0x18000fb78`
- end: `0x18000fcb2`
- name: `?Initialize@RdsDWMDirectUpdateProcessor@@IEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18000f7cc`

## callees

- `0x180001724`
- `0x180003d7c`
- `0x18000ba64`
- `0x18000fb78`
- `0x180012238`
- `0x18002b960`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fc8d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000fc8d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000fc7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18000fc7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fb9a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fba9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000fba9`

## string_xrefs

- `0x18000fbfd`: `Failed to create the I/O processor`
- `0x18000fc24`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::Initialize(RdsDWMDirectUpdateProcessor *this)
{
  unsigned int v1; // ebx
  DWORD CurrentProcessId; // eax
  int Instance; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+50h] [rbp+17h] BYREF
  int v8; // [rsp+54h] [rbp+1Bh] BYREF
  const char *v9; // [rsp+58h] [rbp+1Fh] BYREF
  const char *v10; // [rsp+60h] [rbp+27h] BYREF
  const char *v11; // [rsp+68h] [rbp+2Fh] BYREF
  const char *v12; // [rsp+70h] [rbp+37h] BYREF
  GUID ActivityId; // [rsp+78h] [rbp+3Fh] BYREF

  v1 = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect((RdsDWMDirectUpdateProcessor *)g_Processor);
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &stru_1800440EC);
  if ( qword_1800440B8
    || (Instance = RdsDwmDirectDriverIO_CreateInstance(&qword_1800440B8), v1 = Instance, Instance >= 0) )
  {
    QueryPerformanceFrequency(&Frequency);
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v7 = 279;
    v9 = "Failed to create the I/O processor";
    v8 = Instance;
    v10 = "Initialize";
    v11 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
    v12 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&dword_18003B8F4,
      v4,
      v5,
      (const unsigned __int16 **)&v12,
      (__int64)&v8,
      (const unsigned __int16 **)&v11,
      (__int64)&v7,
      (const unsigned __int16 **)&v10,
      (const unsigned __int16 **)&v9);
  }
  EventActivityIdControl(2u, &ActivityId);
  return v1;
}

```

## disassembly

```asm
0x18000fb78  mov     [rsp-8+arg_0], rbx
0x18000fb7d  push    rbp
0x18000fb7e  lea     rbp, [rsp-57h]
0x18000fb83  sub     rsp, 90h
0x18000fb8a  mov     rax, cs:__security_cookie
0x18000fb91  xor     rax, rsp
0x18000fb94  mov     [rbp+57h+var_8], rax
0x18000fb98  xor     ebx, ebx
0x18000fb9a  call    cs:__imp_GetCurrentProcessId
0x18000fba0  mov     ecx, eax; dwProcessId
0x18000fba2  lea     rdx, pSessionId; pSessionId
0x18000fba9  call    cs:__imp_ProcessIdToSessionId
0x18000fbaf  lea     rcx, ?g_Processor@@3VRdsDWMDirectUpdateProcessor@@A; this
0x18000fbb6  call    ?ResetStateOnSessionReconnect@RdsDWMDirectUpdateProcessor@@IEAAXXZ; RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(void)
0x18000fbbb  lea     rdx, stru_1800440EC; struct _GUID *
0x18000fbc2  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18000fbc6  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18000fbcb  cmp     cs:qword_1800440B8, rbx
0x18000fbd2  jnz     loc_18000FC77
0x18000fbd8  lea     rcx, qword_1800440B8; struct IRdsDWMDirectDriverIO **
0x18000fbdf  call    ?RdsDwmDirectDriverIO_CreateInstance@@YAJPEAPEAUIRdsDWMDirectDriverIO@@@Z; RdsDwmDirectDriverIO_CreateInstance(IRdsDWMDirectDriverIO * *)
0x18000fbe4  mov     ebx, eax
0x18000fbe6  test    eax, eax
0x18000fbe8  jns     loc_18000FC77
0x18000fbee  mov     ecx, cs:dword_180044008
0x18000fbf4  cmp     ecx, 2
0x18000fbf7  jbe     loc_18000FC84
0x18000fbfd  lea     rax, aFailedToCreate_6; "Failed to create the I/O processor"
0x18000fc04  mov     [rbp+57h+var_40], 117h
0x18000fc0b  mov     [rbp+57h+var_38], rax
0x18000fc0f  lea     rdx, dword_18003B8F4
0x18000fc16  lea     rax, aInitialize; "Initialize"
0x18000fc1d  mov     [rbp+57h+var_3C], ebx
0x18000fc20  mov     [rbp+57h+var_30], rax
0x18000fc24  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000fc2b  mov     [rbp+57h+var_28], rax
0x18000fc2f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000fc36  mov     [rbp+57h+var_20], rax
0x18000fc3a  lea     rax, [rbp+57h+var_38]
0x18000fc3e  mov     [rsp+90h+var_48], rax
0x18000fc43  lea     rax, [rbp+57h+var_30]
0x18000fc47  mov     [rsp+90h+var_50], rax
0x18000fc4c  lea     rax, [rbp+57h+var_40]
0x18000fc50  mov     [rsp+90h+var_58], rax
0x18000fc55  lea     rax, [rbp+57h+var_28]
0x18000fc59  mov     [rsp+90h+var_60], rax
0x18000fc5e  lea     rax, [rbp+57h+var_3C]
0x18000fc62  mov     [rsp+90h+var_68], rax
0x18000fc67  lea     rax, [rbp+57h+var_20]
0x18000fc6b  mov     [rsp+90h+var_70], rax
0x18000fc70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000fc75  jmp     short loc_18000FC84
0x18000fc77  lea     rcx, Frequency; lpFrequency
0x18000fc7e  call    cs:__imp_QueryPerformanceFrequency
0x18000fc84  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000fc88  mov     ecx, 2; ControlCode
0x18000fc8d  call    cs:__imp_EventActivityIdControl
0x18000fc93  mov     eax, ebx
0x18000fc95  mov     rcx, [rbp+57h+var_8]
0x18000fc99  xor     rcx, rsp; StackCookie
0x18000fc9c  call    __security_check_cookie
0x18000fca1  mov     rbx, [rsp+90h+arg_0]
0x18000fca9  add     rsp, 90h
0x18000fcb0  pop     rbp
0x18000fcb1  retn
```
