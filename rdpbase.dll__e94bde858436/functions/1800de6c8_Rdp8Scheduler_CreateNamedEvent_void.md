# Rdp8Scheduler::CreateNamedEvent(void)

- ea: `0x1800de6c8`
- end: `0x1800dea80`
- name: `?CreateNamedEvent@Rdp8Scheduler@@AEAAJXZ`
- size: `952`
- prototype: `__int64 __fastcall(Rdp8Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800deca0`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x18006e6a8`
- `0x18007963c`
- `0x1800de6c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800de740`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800de740`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de701`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de701`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de71a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de71a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800de731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800de731`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800de79e`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800de79e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800de792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800de792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de74a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de862`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de859`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800de859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de78c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de90b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de78c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de90b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800de76d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800de76d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800de916`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800de916`

## string_xrefs

- `0x1800de898`: `CreateNamedEvent`
- `0x1800de951`: `CreateNamedEvent`
- `0x1800dea0b`: `CreateNamedEvent`
- `0x1800de8bf`: `CreateEvent failed`
- `0x1800de938`: `Failed to create wait event name string`

## pseudocode

```c
__int64 __fastcall Rdp8Scheduler::CreateNamedEvent(Rdp8Scheduler *this)
{
  int v2; // r15d
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  const unsigned __int16 *v10; // r8
  int v11; // ecx
  int v12; // edi
  int v13; // r8d
  int v14; // r9d
  HANDLE EventW; // rsi
  signed int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int16 *v20; // rdx
  int v22; // [rsp+50h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-28h] BYREF
  const char *v24; // [rsp+60h] [rbp-20h] BYREF
  const char *v25; // [rsp+68h] [rbp-18h] BYREF
  const char *v26; // [rsp+70h] [rbp-10h] BYREF
  const char *v27; // [rsp+78h] [rbp-8h] BYREF
  unsigned int TokenInformation; // [rsp+B8h] [rbp+38h] BYREF
  DWORD ReturnLength; // [rsp+C0h] [rbp+40h] BYREF
  DWORD pSessionId; // [rsp+C8h] [rbp+48h] BYREF

  pSessionId = 0;
  TokenInformation = 0;
  v2 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_40;
  if ( GetLastError() != 1008 )
    goto LABEL_10;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_40:
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      if ( TokenInformation )
        v2 = 1;
    }
    else
    {
      GetLastError();
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    GetLastError();
  }
LABEL_10:
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v7;
  }
  while ( 1 )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( (unsigned int)rand_s(&TokenInformation) )
    {
      v7 = -2147418113;
      if ( (unsigned int)CallbackContext <= 2 )
        return v7;
      LODWORD(TokenHandle) = 1161;
      v20 = word_1801BC8AA;
      goto LABEL_36;
    }
    if ( (unsigned int)rand_s(&ReturnLength) )
    {
      v7 = -2147418113;
      if ( (unsigned int)CallbackContext <= 2 )
        return v7;
      LODWORD(TokenHandle) = 1167;
      v20 = word_1801BC85A;
LABEL_36:
      v22 = -2147418113;
      v27 = "rand_s failed";
      v26 = "CreateNamedEvent";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
      v24 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147418113,
        (_DWORD)v20,
        v8,
        v9,
        (__int64)&v24,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&TokenHandle,
        (__int64)&v26,
        (__int64)&v27);
      return v7;
    }
    if ( pSessionId || (v10 = L"Global\\RDPSchedulerEvent%lld", v2) )
      v10 = L"Local\\RDPSchedulerEvent%lld";
    v12 = StringCchPrintfW(
            (unsigned __int16 *)this + 464,
            0x104u,
            v10,
            ReturnLength | ((unsigned __int64)TokenInformation << 32));
    if ( v12 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(TokenHandle) = 1181;
        v26 = "Failed to create wait event name string";
        v22 = v12;
        v25 = "CreateNamedEvent";
        v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
        v27 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)word_1801BC80A,
          v13,
          v14,
          (__int64)&v27,
          (__int64)&v22,
          (__int64)&v24,
          (__int64)&TokenHandle,
          (__int64)&v25,
          (__int64)&v26);
      }
      return (unsigned int)v12;
    }
    EventW = CreateEventW(
               (LPSECURITY_ATTRIBUTES)(((unsigned __int64)this + 1480) & -(__int64)(*((_DWORD *)this + 369) != 0)),
               0,
               0,
               (LPCWSTR)this + 464);
    v16 = GetLastError();
    v7 = v16;
    if ( !EventW )
      break;
    if ( v16 != 183 )
    {
      *((_QWORD *)this + 181) = EventW;
      return (unsigned int)v12;
    }
    CloseHandle(EventW);
LABEL_27:
    Sleep(0x64u);
  }
  if ( v16 == 5 )
    goto LABEL_27;
  if ( v16 > 0 )
    v7 = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v22 = 1206;
    v24 = "CreateNamedEvent";
    LODWORD(TokenHandle) = v7;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
    v26 = "CreateEvent failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)word_1801BC7C2,
      v18,
      v19,
      (__int64)&v26,
      (__int64)&TokenHandle,
      (__int64)&v25,
      (__int64)&v22,
      (__int64)&v24);
  }
  return v7;
}

```

## disassembly

```asm
0x1800de6c8  mov     [rsp-28h+arg_0], rbx
0x1800de6cd  push    rbp
0x1800de6ce  push    rsi
0x1800de6cf  push    rdi
0x1800de6d0  push    r14
0x1800de6d2  push    r15
0x1800de6d4  mov     rbp, rsp
0x1800de6d7  sub     rsp, 80h
0x1800de6de  mov     r14, rcx
0x1800de6e1  mov     [rbp+pSessionId], 0
0x1800de6e8  mov     [rbp+TokenInformation], 0
0x1800de6ef  xor     r15d, r15d
0x1800de6f2  mov     [rbp+TokenHandle], 0
0x1800de6fa  mov     [rbp+arg_10], 0
0x1800de701  call    cs:__imp_GetCurrentThread
0x1800de707  lea     ebx, [r15+1]
0x1800de70b  mov     rcx, rax; ThreadHandle
0x1800de70e  lea     edi, [rbx+7]
0x1800de711  mov     r8d, ebx; OpenAsSelf
0x1800de714  mov     edx, edi; DesiredAccess
0x1800de716  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800de71a  call    cs:__imp_OpenThreadToken
0x1800de720  test    eax, eax
0x1800de722  jnz     short loc_1800DE752
0x1800de724  call    cs:__imp_GetLastError
0x1800de72a  cmp     eax, 3F0h
0x1800de72f  jnz     short loc_1800DE792
0x1800de731  call    cs:__imp_GetCurrentProcess
0x1800de737  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800de73b  mov     edx, edi; DesiredAccess
0x1800de73d  mov     rcx, rax; ProcessHandle
0x1800de740  call    cs:__imp_OpenProcessToken
0x1800de746  test    eax, eax
0x1800de748  jnz     short loc_1800DE752
0x1800de74a  call    cs:__imp_GetLastError
0x1800de750  jmp     short loc_1800DE792
0x1800de752  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800de756  lea     rax, [rbp+arg_10]
0x1800de75a  mov     r9d, 4; TokenInformationLength
0x1800de760  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800de765  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800de769  lea     edx, [r9+19h]; TokenInformationClass
0x1800de76d  call    cs:__imp_GetTokenInformation
0x1800de773  test    eax, eax
0x1800de775  jz      short loc_1800DE782
0x1800de777  cmp     [rbp+TokenInformation], r15d
0x1800de77b  jz      short loc_1800DE788
0x1800de77d  mov     r15d, ebx
0x1800de780  jmp     short loc_1800DE788
0x1800de782  call    cs:__imp_GetLastError
0x1800de788  mov     rcx, [rbp+TokenHandle]; hObject
0x1800de78c  call    cs:__imp_CloseHandle
0x1800de792  call    cs:__imp_GetCurrentProcessId
0x1800de798  mov     ecx, eax; dwProcessId
0x1800de79a  lea     rdx, [rbp+pSessionId]; pSessionId
0x1800de79e  call    cs:__imp_ProcessIdToSessionId
0x1800de7a4  test    eax, eax
0x1800de7a6  jnz     short loc_1800DE7C6
0x1800de7a8  call    cs:__imp_GetLastError
0x1800de7ae  mov     ebx, eax
0x1800de7b0  test    eax, eax
0x1800de7b2  jle     loc_1800DEA67
0x1800de7b8  movzx   ebx, ax
0x1800de7bb  or      ebx, 80070000h
0x1800de7c1  jmp     loc_1800DEA67
0x1800de7c6  lea     rcx, [rbp+TokenInformation]
0x1800de7ca  mov     [rbp+TokenInformation], 0
0x1800de7d1  mov     [rbp+arg_10], 0
0x1800de7d8  call    rand_s
0x1800de7dd  test    eax, eax
0x1800de7df  jnz     loc_1800DE9DD
0x1800de7e5  lea     rcx, [rbp+arg_10]
0x1800de7e9  call    rand_s
0x1800de7ee  test    eax, eax
0x1800de7f0  jnz     loc_1800DE9B7
0x1800de7f6  mov     r9d, [rbp+TokenInformation]
0x1800de7fa  mov     eax, [rbp+arg_10]
0x1800de7fd  shl     r9, 20h
0x1800de801  or      r9, rax
0x1800de804  cmp     [rbp+pSessionId], 0
0x1800de808  jnz     short loc_1800DE816
0x1800de80a  lea     r8, aGlobalRdpsched; "Global\\RDPSchedulerEvent%lld"
0x1800de811  test    r15d, r15d
0x1800de814  jz      short loc_1800DE81D
0x1800de816  lea     r8, aLocalRdpschedu; "Local\\RDPSchedulerEvent%lld"
0x1800de81d  lea     rbx, [r14+3A0h]
0x1800de824  mov     edx, 104h; unsigned __int64
0x1800de829  mov     rcx, rbx; unsigned __int16 *
0x1800de82c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800de831  mov     edi, eax
0x1800de833  test    eax, eax
0x1800de835  js      loc_1800DE92D
0x1800de83b  mov     ecx, [r14+5C4h]
0x1800de842  lea     rdx, [r14+5C8h]
0x1800de849  neg     ecx
0x1800de84b  mov     r9, rbx; lpName
0x1800de84e  sbb     rcx, rcx
0x1800de851  xor     r8d, r8d; bInitialState
0x1800de854  and     rcx, rdx; lpEventAttributes
0x1800de857  xor     edx, edx; bManualReset
0x1800de859  call    cs:__imp_CreateEventW
0x1800de85f  mov     rsi, rax
0x1800de862  call    cs:__imp_GetLastError
0x1800de868  mov     ebx, eax
0x1800de86a  test    rsi, rsi
0x1800de86d  jnz     loc_1800DE901
0x1800de873  cmp     eax, 5
0x1800de876  jz      loc_1800DE911
0x1800de87c  test    eax, eax
0x1800de87e  jle     short loc_1800DE889
0x1800de880  movzx   ebx, ax
0x1800de883  or      ebx, 80070000h
0x1800de889  mov     eax, cs:CallbackContext
0x1800de88f  cmp     eax, 2
0x1800de892  jbe     loc_1800DEA67
0x1800de898  lea     rax, aCreatenamedeve; "CreateNamedEvent"
0x1800de89f  mov     [rbp+var_30], 4B6h
0x1800de8a6  mov     [rbp+var_20], rax
0x1800de8aa  lea     rdx, word_1801BC7C2
0x1800de8b1  lea     rax, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800de8b8  mov     dword ptr [rbp+TokenHandle], ebx
0x1800de8bb  mov     [rbp+var_18], rax
0x1800de8bf  lea     rax, aCreateeventFai; "CreateEvent failed"
0x1800de8c6  mov     [rbp+var_10], rax
0x1800de8ca  lea     rax, [rbp+var_20]
0x1800de8ce  mov     [rsp+80h+var_40], rax
0x1800de8d3  lea     rax, [rbp+var_30]
0x1800de8d7  mov     [rsp+80h+var_48], rax
0x1800de8dc  lea     rax, [rbp+var_18]
0x1800de8e0  mov     [rsp+80h+var_50], rax
0x1800de8e5  lea     rax, [rbp+TokenHandle]
0x1800de8e9  mov     [rsp+80h+var_58], rax
0x1800de8ee  lea     rax, [rbp+var_10]
0x1800de8f2  mov     [rsp+80h+ReturnLength], rax
0x1800de8f7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800de8fc  jmp     loc_1800DEA67
0x1800de901  cmp     eax, 0B7h
0x1800de906  jnz     short loc_1800DE921
0x1800de908  mov     rcx, rsi; hObject
0x1800de90b  call    cs:__imp_CloseHandle
0x1800de911  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800de916  call    cs:__imp_Sleep
0x1800de91c  jmp     loc_1800DE7C6
0x1800de921  mov     [r14+5A8h], rsi
0x1800de928  jmp     loc_1800DE9B0
0x1800de92d  mov     eax, cs:CallbackContext
0x1800de933  cmp     eax, 2
0x1800de936  jbe     short loc_1800DE9B0
0x1800de938  lea     rax, aFailedToCreate_31; "Failed to create wait event name string"
0x1800de93f  mov     dword ptr [rbp+TokenHandle], 49Dh
0x1800de946  mov     [rbp+var_10], rax
0x1800de94a  lea     rdx, word_1801BC80A
0x1800de951  lea     rax, aCreatenamedeve; "CreateNamedEvent"
0x1800de958  mov     [rbp+var_30], edi
0x1800de95b  mov     [rbp+var_18], rax
0x1800de95f  lea     rax, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800de966  mov     [rbp+var_20], rax
0x1800de96a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800de971  mov     [rbp+var_8], rax
0x1800de975  lea     rax, [rbp+var_10]
0x1800de979  mov     [rsp+80h+var_38], rax
0x1800de97e  lea     rax, [rbp+var_18]
0x1800de982  mov     [rsp+80h+var_40], rax
0x1800de987  lea     rax, [rbp+TokenHandle]
0x1800de98b  mov     [rsp+80h+var_48], rax
0x1800de990  lea     rax, [rbp+var_20]
0x1800de994  mov     [rsp+80h+var_50], rax
0x1800de999  lea     rax, [rbp+var_30]
0x1800de99d  mov     [rsp+80h+var_58], rax
0x1800de9a2  lea     rax, [rbp+var_8]
0x1800de9a6  mov     [rsp+80h+ReturnLength], rax
0x1800de9ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800de9b0  mov     ebx, edi
0x1800de9b2  jmp     loc_1800DEA67
0x1800de9b7  mov     eax, cs:CallbackContext
0x1800de9bd  mov     ecx, 8000FFFFh
0x1800de9c2  mov     ebx, ecx
0x1800de9c4  cmp     eax, 2
0x1800de9c7  jbe     loc_1800DEA67
0x1800de9cd  mov     dword ptr [rbp+TokenHandle], 48Fh
0x1800de9d4  lea     rdx, word_1801BC85A
0x1800de9db  jmp     short loc_1800DE9FD
0x1800de9dd  mov     eax, cs:CallbackContext
0x1800de9e3  mov     ecx, 8000FFFFh
0x1800de9e8  mov     ebx, ecx
0x1800de9ea  cmp     eax, 2
0x1800de9ed  jbe     short loc_1800DEA67
0x1800de9ef  mov     dword ptr [rbp+TokenHandle], 489h
0x1800de9f6  lea     rdx, word_1801BC8AA
0x1800de9fd  lea     rax, aRandSFailed; "rand_s failed"
0x1800dea04  mov     [rbp+var_30], ecx
0x1800dea07  mov     [rbp+var_8], rax
0x1800dea0b  lea     rax, aCreatenamedeve; "CreateNamedEvent"
0x1800dea12  mov     [rbp+var_10], rax
0x1800dea16  lea     rax, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dea1d  mov     [rbp+var_18], rax
0x1800dea21  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800dea28  mov     [rbp+var_20], rax
0x1800dea2c  lea     rax, [rbp+var_8]
0x1800dea30  mov     [rsp+80h+var_38], rax
0x1800dea35  lea     rax, [rbp+var_10]
0x1800dea39  mov     [rsp+80h+var_40], rax
0x1800dea3e  lea     rax, [rbp+TokenHandle]
0x1800dea42  mov     [rsp+80h+var_48], rax
0x1800dea47  lea     rax, [rbp+var_18]
0x1800dea4b  mov     [rsp+80h+var_50], rax
0x1800dea50  lea     rax, [rbp+var_30]
0x1800dea54  mov     [rsp+80h+var_58], rax
0x1800dea59  lea     rax, [rbp+var_20]
0x1800dea5d  mov     [rsp+80h+ReturnLength], rax
0x1800dea62  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800dea67  mov     eax, ebx
0x1800dea69  mov     rbx, [rsp+80h+arg_0]
0x1800dea71  add     rsp, 80h
0x1800dea78  pop     r15
0x1800dea7a  pop     r14
0x1800dea7c  pop     rdi
0x1800dea7d  pop     rsi
0x1800dea7e  pop     rbp
0x1800dea7f  retn
```
