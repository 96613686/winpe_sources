# Rdp8Scheduler::TerminateInstance(void)

- ea: `0x1800dfb80`
- end: `0x1800dff5c`
- name: `?TerminateInstance@Rdp8Scheduler@@UEAAJXZ`
- size: `988`
- prototype: `__int64 __fastcall(Rdp8Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800de584`

## callees

- `0x180005090`
- `0x18000798c`
- `0x180019a80`
- `0x180019ab0`
- `0x1800dfb80`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800dfbec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800dfbec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfbac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800dfbac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfbc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800dfbc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dfbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dfbdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfbf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dfc2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800dfc4b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800dfc4b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dfefc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800dfefc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfc38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dfc38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfc19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800dfc19`

## pseudocode

```c
__int64 __fastcall Rdp8Scheduler::TerminateInstance(Rdp8Scheduler *this)
{
  int v1; // r12d
  int v3; // r15d
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v6; // rcx
  __int64 v7; // rsi
  void *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  int v12; // edi
  __int64 v13; // rcx
  int v14; // eax
  int v15; // ecx
  __int64 v17; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+68h] [rbp-1h] BYREF
  const char *v19; // [rsp+70h] [rbp+7h] BYREF
  const char *v20; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v21[8]; // [rsp+80h] [rbp+17h] BYREF
  int TokenInformation; // [rsp+D0h] [rbp+67h] BYREF
  const char *ReturnLength; // [rsp+D8h] [rbp+6Fh] BYREF
  void *TokenHandle; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+7Fh] BYREF

  v1 = 0;
  TokenInformation = 0;
  v3 = 0;
  TokenHandle = 0;
  LODWORD(ReturnLength) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_45;
  if ( GetLastError() != 1008 )
    goto LABEL_10;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_45:
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
    {
      if ( TokenInformation )
        v3 = 1;
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
  v6 = (void *)*((_QWORD *)this + 17);
  *((_DWORD *)this + 230) = 1;
  SetEvent(v6);
  v7 = 0;
  if ( *((_DWORD *)this + 36) )
  {
    while ( 1 )
    {
      v8 = (void *)*((_QWORD *)this + v7 + 19);
      if ( v8 )
        break;
LABEL_39:
      v7 = (unsigned int)(v7 + 1);
      if ( (unsigned int)v7 >= *((_DWORD *)this + 36) )
        goto LABEL_40;
    }
    while ( 1 )
    {
      if ( WaitForSingleObject(v8, 0x2710u) != 258 )
        goto LABEL_39;
      if ( !v1 && !v3 )
        break;
LABEL_37:
      v8 = (void *)*((_QWORD *)this + v7 + 19);
    }
    v1 = 1;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v18 = *((_QWORD *)this + v7 + 19);
      v20 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
      v21[0] = "Deadlock detected in Rdp8Scheduler";
      TokenInformation = v7;
      v19 = "TerminateInstance";
      LODWORD(ReturnLength) = 798;
      LODWORD(TokenHandle) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned int)&word_1801BCD06,
        v9,
        v10,
        (__int64)v21,
        (__int64)&TokenHandle,
        (__int64)&v20,
        (__int64)&ReturnLength,
        (__int64)&v19,
        (__int64)&TokenInformation,
        (__int64)&v18);
    }
    v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 183);
    v17 = 0;
    v25 = 0;
    if ( v11 )
    {
      v12 = (**v11)(v11, &IID_IRDPENCPlatformContext, &v17);
      if ( v12 >= 0 )
      {
LABEL_23:
        if ( v17 )
          v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 120LL))(v17, &v25);
        if ( v12 < 0 && (unsigned int)CallbackContext > 3 )
        {
          TokenInformation = v12;
          ReturnLength = "TerminateInstance";
          TokenHandle = "GetWatchdog failed!";
          v21[0] = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)qword_1801BCCC8,
            v9,
            v10,
            (__int64)v21,
            (__int64)&TokenHandle,
            (__int64)&TokenInformation,
            (__int64)&ReturnLength);
        }
        v13 = v25;
        if ( v25 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL))(v25, 2);
          v13 = v25;
          v12 = v14;
        }
        if ( v12 < 0 )
        {
          if ( (unsigned int)CallbackContext > 3 )
          {
            TokenInformation = v12;
            ReturnLength = "TerminateInstance";
            TokenHandle = "ReportDeadlockToWatson failed!";
            v21[0] = "HResult failed but continue";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v13,
              (unsigned int)&dword_1801BCC4C,
              v9,
              v10,
              (__int64)v21,
              (__int64)&TokenHandle,
              (__int64)&TokenInformation,
              (__int64)&ReturnLength);
          }
          v13 = v25;
        }
        if ( v13 )
        {
          v25 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v17);
        goto LABEL_37;
      }
    }
    else
    {
      v12 = -2147467261;
    }
    if ( (unsigned int)CallbackContext > 3 )
    {
      TokenInformation = v12;
      ReturnLength = "TerminateInstance";
      TokenHandle = "QueryInterface(IID_IRDPENCPlatformContext) failed!";
      v21[0] = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v11,
        (unsigned int)word_1801BCC8A,
        v9,
        v10,
        (__int64)v21,
        (__int64)&TokenHandle,
        (__int64)&TokenInformation,
        (__int64)&ReturnLength);
    }
    goto LABEL_23;
  }
LABEL_40:
  if ( *((_QWORD *)this + 183) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 1464);
    *((_QWORD *)this + 183) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 1464);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dfb80  push    rbp
0x1800dfb82  push    rbx
0x1800dfb83  push    rsi
0x1800dfb84  push    rdi
0x1800dfb85  push    r12
0x1800dfb87  push    r14
0x1800dfb89  push    r15
0x1800dfb8b  lea     rbp, [rsp-27h]
0x1800dfb90  sub     rsp, 90h
0x1800dfb97  xor     r12d, r12d
0x1800dfb9a  mov     rbx, rcx
0x1800dfb9d  mov     [rbp+57h+TokenInformation], r12d
0x1800dfba1  xor     r15d, r15d
0x1800dfba4  mov     [rbp+57h+TokenHandle], r12
0x1800dfba8  mov     dword ptr [rbp+57h+arg_8], r12d
0x1800dfbac  call    cs:__imp_GetCurrentThread
0x1800dfbb2  lea     esi, [r12+1]
0x1800dfbb7  mov     rcx, rax; ThreadHandle
0x1800dfbba  lea     edi, [rsi+7]
0x1800dfbbd  mov     r8d, esi; OpenAsSelf
0x1800dfbc0  mov     edx, edi; DesiredAccess
0x1800dfbc2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800dfbc6  call    cs:__imp_OpenThreadToken
0x1800dfbcc  test    eax, eax
0x1800dfbce  jnz     short loc_1800DFBFE
0x1800dfbd0  call    cs:__imp_GetLastError
0x1800dfbd6  cmp     eax, 3F0h
0x1800dfbdb  jnz     short loc_1800DFC3E
0x1800dfbdd  call    cs:__imp_GetCurrentProcess
0x1800dfbe3  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800dfbe7  mov     edx, edi; DesiredAccess
0x1800dfbe9  mov     rcx, rax; ProcessHandle
0x1800dfbec  call    cs:__imp_OpenProcessToken
0x1800dfbf2  test    eax, eax
0x1800dfbf4  jnz     short loc_1800DFBFE
0x1800dfbf6  call    cs:__imp_GetLastError
0x1800dfbfc  jmp     short loc_1800DFC3E
0x1800dfbfe  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800dfc02  lea     rax, [rbp+57h+arg_8]
0x1800dfc06  mov     r9d, 4; TokenInformationLength
0x1800dfc0c  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800dfc11  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800dfc15  lea     edx, [r9+19h]; TokenInformationClass
0x1800dfc19  call    cs:__imp_GetTokenInformation
0x1800dfc1f  test    eax, eax
0x1800dfc21  jz      short loc_1800DFC2E
0x1800dfc23  cmp     [rbp+57h+TokenInformation], r12d
0x1800dfc27  jz      short loc_1800DFC34
0x1800dfc29  mov     r15d, esi
0x1800dfc2c  jmp     short loc_1800DFC34
0x1800dfc2e  call    cs:__imp_GetLastError
0x1800dfc34  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800dfc38  call    cs:__imp_CloseHandle
0x1800dfc3e  mov     rcx, [rbx+88h]; hEvent
0x1800dfc45  mov     [rbx+398h], esi
0x1800dfc4b  call    cs:__imp_SetEvent
0x1800dfc51  xor     esi, esi
0x1800dfc53  cmp     [rbx+90h], esi
0x1800dfc59  jbe     loc_1800DFF1B
0x1800dfc5f  lea     rdi, aTerminateinsta; "TerminateInstance"
0x1800dfc66  mov     rcx, [rbx+rsi*8+98h]
0x1800dfc6e  test    rcx, rcx
0x1800dfc71  jz      loc_1800DFF0D
0x1800dfc77  jmp     loc_1800DFEF7
0x1800dfc7c  test    r12d, r12d
0x1800dfc7f  jnz     loc_1800DFEEF
0x1800dfc85  test    r15d, r15d
0x1800dfc88  jnz     loc_1800DFEEF
0x1800dfc8e  mov     eax, cs:CallbackContext
0x1800dfc94  lea     r12d, [r15+1]
0x1800dfc98  cmp     eax, 2
0x1800dfc9b  jbe     loc_1800DFD23
0x1800dfca1  mov     rax, [rbx+rsi*8+98h]
0x1800dfca9  lea     rdx, word_1801BCD06
0x1800dfcb0  mov     [rbp+57h+var_58], rax
0x1800dfcb4  lea     rax, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dfcbb  mov     [rbp+57h+var_48], rax
0x1800dfcbf  lea     rax, aDeadlockDetect; "Deadlock detected in Rdp8Scheduler"
0x1800dfcc6  mov     [rbp+57h+var_40], rax
0x1800dfcca  lea     rax, [rbp+57h+var_58]
0x1800dfcce  mov     [rsp+0C0h+var_70], rax
0x1800dfcd3  lea     rax, [rbp+57h+TokenInformation]
0x1800dfcd7  mov     [rsp+0C0h+var_78], rax
0x1800dfcdc  lea     rax, [rbp+57h+var_50]
0x1800dfce0  mov     [rsp+0C0h+var_80], rax
0x1800dfce5  lea     rax, [rbp+57h+arg_8]
0x1800dfce9  mov     [rsp+0C0h+var_88], rax
0x1800dfcee  lea     rax, [rbp+57h+var_48]
0x1800dfcf2  mov     [rsp+0C0h+var_90], rax
0x1800dfcf7  lea     rax, [rbp+57h+TokenHandle]
0x1800dfcfb  mov     [rsp+0C0h+var_98], rax
0x1800dfd00  lea     rax, [rbp+57h+var_40]
0x1800dfd04  mov     [rsp+0C0h+ReturnLength], rax
0x1800dfd09  mov     [rbp+57h+TokenInformation], esi
0x1800dfd0c  mov     [rbp+57h+var_50], rdi
0x1800dfd10  mov     dword ptr [rbp+57h+arg_8], 31Eh
0x1800dfd17  mov     dword ptr [rbp+57h+TokenHandle], 8000FFFFh
0x1800dfd1e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800dfd23  mov     rcx, [rbx+5B8h]
0x1800dfd2a  mov     [rbp+57h+var_60], 0
0x1800dfd32  mov     [rbp+57h+arg_18], 0
0x1800dfd3a  test    rcx, rcx
0x1800dfd3d  jz      short loc_1800DFD5D
0x1800dfd3f  mov     rax, [rcx]
0x1800dfd42  lea     r8, [rbp+57h+var_60]
0x1800dfd46  lea     rdx, IID_IRDPENCPlatformContext
0x1800dfd4d  mov     rax, [rax]
0x1800dfd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd55  mov     edi, eax
0x1800dfd57  test    eax, eax
0x1800dfd59  jns     short loc_1800DFDC1
0x1800dfd5b  jmp     short loc_1800DFD62
0x1800dfd5d  mov     edi, 80004003h
0x1800dfd62  mov     eax, cs:CallbackContext
0x1800dfd68  cmp     eax, 3
0x1800dfd6b  jbe     short loc_1800DFDC1
0x1800dfd6d  lea     rax, aTerminateinsta; "TerminateInstance"
0x1800dfd74  mov     [rbp+57h+TokenInformation], edi
0x1800dfd77  mov     [rbp+57h+arg_8], rax
0x1800dfd7b  lea     rdx, word_1801BCC8A
0x1800dfd82  lea     rax, aQueryinterface_2; "QueryInterface(IID_IRDPENCPlatformConte"...
0x1800dfd89  mov     [rbp+57h+TokenHandle], rax
0x1800dfd8d  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800dfd94  mov     [rbp+57h+var_40], rax
0x1800dfd98  lea     rax, [rbp+57h+arg_8]
0x1800dfd9c  mov     [rsp+0C0h+var_88], rax
0x1800dfda1  lea     rax, [rbp+57h+TokenInformation]
0x1800dfda5  mov     [rsp+0C0h+var_90], rax
0x1800dfdaa  lea     rax, [rbp+57h+TokenHandle]
0x1800dfdae  mov     [rsp+0C0h+var_98], rax
0x1800dfdb3  lea     rax, [rbp+57h+var_40]
0x1800dfdb7  mov     [rsp+0C0h+ReturnLength], rax
0x1800dfdbc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dfdc1  mov     rcx, [rbp+57h+var_60]
0x1800dfdc5  test    rcx, rcx
0x1800dfdc8  jz      short loc_1800DFDDC
0x1800dfdca  mov     rax, [rcx]
0x1800dfdcd  lea     rdx, [rbp+57h+arg_18]
0x1800dfdd1  mov     rax, [rax+78h]
0x1800dfdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfdda  mov     edi, eax
0x1800dfddc  test    edi, edi
0x1800dfdde  jns     short loc_1800DFE3F
0x1800dfde0  mov     ecx, cs:CallbackContext
0x1800dfde6  cmp     ecx, 3
0x1800dfde9  jbe     short loc_1800DFE3F
0x1800dfdeb  lea     rax, aTerminateinsta; "TerminateInstance"
0x1800dfdf2  mov     [rbp+57h+TokenInformation], edi
0x1800dfdf5  mov     [rbp+57h+arg_8], rax
0x1800dfdf9  lea     rdx, qword_1801BCCC8
0x1800dfe00  lea     rax, aGetwatchdogFai; "GetWatchdog failed!"
0x1800dfe07  mov     [rbp+57h+TokenHandle], rax
0x1800dfe0b  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800dfe12  mov     [rbp+57h+var_40], rax
0x1800dfe16  lea     rax, [rbp+57h+arg_8]
0x1800dfe1a  mov     [rsp+0C0h+var_88], rax
0x1800dfe1f  lea     rax, [rbp+57h+TokenInformation]
0x1800dfe23  mov     [rsp+0C0h+var_90], rax
0x1800dfe28  lea     rax, [rbp+57h+TokenHandle]
0x1800dfe2c  mov     [rsp+0C0h+var_98], rax
0x1800dfe31  lea     rax, [rbp+57h+var_40]
0x1800dfe35  mov     [rsp+0C0h+ReturnLength], rax
0x1800dfe3a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dfe3f  mov     rcx, [rbp+57h+arg_18]
0x1800dfe43  test    rcx, rcx
0x1800dfe46  jz      short loc_1800DFE5F
0x1800dfe48  mov     rax, [rcx]
0x1800dfe4b  mov     edx, 2
0x1800dfe50  mov     rax, [rax+28h]
0x1800dfe54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfe59  mov     rcx, [rbp+57h+arg_18]
0x1800dfe5d  mov     edi, eax
0x1800dfe5f  test    edi, edi
0x1800dfe61  jns     short loc_1800DFEC6
0x1800dfe63  mov     eax, cs:CallbackContext
0x1800dfe69  cmp     eax, 3
0x1800dfe6c  jbe     short loc_1800DFEC2
0x1800dfe6e  lea     rax, aTerminateinsta; "TerminateInstance"
0x1800dfe75  mov     [rbp+57h+TokenInformation], edi
0x1800dfe78  mov     [rbp+57h+arg_8], rax
0x1800dfe7c  lea     rdx, dword_1801BCC4C
0x1800dfe83  lea     rax, aReportdeadlock; "ReportDeadlockToWatson failed!"
0x1800dfe8a  mov     [rbp+57h+TokenHandle], rax
0x1800dfe8e  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800dfe95  mov     [rbp+57h+var_40], rax
0x1800dfe99  lea     rax, [rbp+57h+arg_8]
0x1800dfe9d  mov     [rsp+0C0h+var_88], rax
0x1800dfea2  lea     rax, [rbp+57h+TokenInformation]
0x1800dfea6  mov     [rsp+0C0h+var_90], rax
0x1800dfeab  lea     rax, [rbp+57h+TokenHandle]
0x1800dfeaf  mov     [rsp+0C0h+var_98], rax
0x1800dfeb4  lea     rax, [rbp+57h+var_40]
0x1800dfeb8  mov     [rsp+0C0h+ReturnLength], rax
0x1800dfebd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dfec2  mov     rcx, [rbp+57h+arg_18]
0x1800dfec6  test    rcx, rcx
0x1800dfec9  jz      short loc_1800DFEDF
0x1800dfecb  mov     [rbp+57h+arg_18], 0
0x1800dfed3  mov     rax, [rcx]
0x1800dfed6  mov     rax, [rax+10h]
0x1800dfeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfedf  lea     rcx, [rbp+57h+var_60]; void *
0x1800dfee3  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800dfee8  lea     rdi, aTerminateinsta; "TerminateInstance"
0x1800dfeef  mov     rcx, [rbx+rsi*8+98h]; hHandle
0x1800dfef7  mov     edx, 2710h; dwMilliseconds
0x1800dfefc  call    cs:__imp_WaitForSingleObject
0x1800dff02  cmp     eax, 102h
0x1800dff07  jz      loc_1800DFC7C
0x1800dff0d  inc     esi
0x1800dff0f  cmp     esi, [rbx+90h]
0x1800dff15  jb      loc_1800DFC66
0x1800dff1b  cmp     qword ptr [rbx+5B8h], 0
0x1800dff23  jz      short loc_1800DFF48
0x1800dff25  lea     rcx, [rbx+5B8h]; void *
0x1800dff2c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800dff31  lea     rcx, [rbx+5B8h]
0x1800dff38  mov     qword ptr [rbx+5B8h], 0
0x1800dff43  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800dff48  xor     eax, eax
0x1800dff4a  add     rsp, 90h
0x1800dff51  pop     r15
0x1800dff53  pop     r14
0x1800dff55  pop     r12
0x1800dff57  pop     rdi
0x1800dff58  pop     rsi
0x1800dff59  pop     rbx
0x1800dff5a  pop     rbp
0x1800dff5b  retn
```
