# CRDPENCDirectConnector::AsyncResolveServerName(void)

- ea: `0x1800ea318`
- end: `0x1800ea6be`
- name: `?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ`
- size: `934`
- prototype: `__int64 __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800eb644`

## callees

- `0x180004970`
- `0x180046a84`
- `0x18006f440`
- `0x1800721d4`
- `0x1800ea318`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800ea5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800ea5c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ea3aa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800ea3aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea5cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ea5cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea69e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ea69e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ea4d4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800ea4d4`

## string_xrefs

- `0x1800ea407`: `Create ResolveServerName Thread failed with error: 0x%x`
- `0x1800ea60a`: `Failed to get the resolve name thread exit code. error: 0x%x`

## pseudocode

```c
__int64 __fastcall CRDPENCDirectConnector::AsyncResolveServerName(CRDPENCDirectConnector *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v3; // rcx
  HANDLE Thread; // rax
  DWORD LastError; // eax
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  char *v10; // rdx
  const char **v11; // rax
  DWORD v12; // ebx
  unsigned int v13; // eax
  DWORD v14; // eax
  unsigned int v15; // eax
  DWORD v16; // ebx
  unsigned int v17; // eax
  const char **v19; // [rsp+40h] [rbp-9h]
  const char *v20; // [rsp+50h] [rbp+7h] BYREF
  const char *v21; // [rsp+58h] [rbp+Fh] BYREF
  const char *v22; // [rsp+60h] [rbp+17h] BYREF
  HANDLE Handles[7]; // [rsp+68h] [rbp+1Fh] BYREF
  DWORD ExitCode; // [rsp+B0h] [rbp+67h] BYREF
  DWORD v25; // [rsp+B8h] [rbp+6Fh] BYREF
  int v26; // [rsp+C0h] [rbp+77h] BYREF
  int v27; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v3 = *((_QWORD *)this + 4);
  ExitCode = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  Thread = CreateThread(0, 0, CRDPENCDirectConnector::STATIC_ThreadProcResolveServerName, this, 0, 0);
  *((_QWORD *)this + 42) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v6 = *((_QWORD *)this + 4);
    ExitCode = LastError;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_9;
    v10 = byte_1801BEEB1;
    v25 = ExitCode;
    v20 = "AsyncResolveServerName";
    v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
    v22 = "Create ResolveServerName Thread failed with error: 0x%x";
    v19 = &v20;
    v11 = &v22;
    v26 = 765;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v13);
  }
  Handles[0] = *((HANDLE *)this + 42);
  Handles[1] = *((HANDLE *)this + 37);
  v14 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  ExitCode = v14;
  if ( v14 )
  {
    if ( v14 != 1 )
    {
      ExitCode = GetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v10 = (char *)&word_1801BEE5E;
        v25 = ExitCode;
        v22 = "AsyncResolveServerName";
        v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
        v20 = "WaitForSingleObject return error: 0x%x";
        v19 = &v22;
        v11 = &v20;
        v26 = 813;
LABEL_8:
        v27 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (_DWORD)v10,
          v8,
          v9,
          (__int64)v11,
          (__int64)&v27,
          (__int64)&v21,
          (__int64)&v26,
          (__int64)v19,
          (__int64)&v25);
        goto LABEL_9;
      }
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v15);
    }
    return (DWORD)-2092629996;
  }
  else
  {
    if ( !GetExitCodeThread(*((HANDLE *)this + 42), &ExitCode) )
    {
      ExitCode = GetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v10 = byte_1801BEE0B;
        v25 = ExitCode;
        v22 = "AsyncResolveServerName";
        v21 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
        v20 = "Failed to get the resolve name thread exit code. error: 0x%x";
        v19 = &v22;
        v11 = &v20;
        v26 = 788;
        goto LABEL_8;
      }
LABEL_9:
      v12 = ExitCode;
      if ( (int)ExitCode > 0 )
        return (unsigned __int16)ExitCode | 0x80070000;
      return v12;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = ExitCode;
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v17, v16);
    }
    v12 = ExitCode;
    CloseHandle(*((HANDLE *)this + 42));
    *((_QWORD *)this + 42) = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x1800ea318  push    rbp
0x1800ea31a  push    rbx
0x1800ea31b  push    rdi
0x1800ea31c  push    r14
0x1800ea31e  lea     rbp, [rsp-3Fh]
0x1800ea323  sub     rsp, 88h
0x1800ea32a  mov     rdi, rcx
0x1800ea32d  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea334  lea     r14, WPP_GLOBAL_Control
0x1800ea33b  mov     ebx, 800h
0x1800ea340  cmp     rax, r14
0x1800ea343  jz      short loc_1800EA374
0x1800ea345  test    [rax+1Ch], ebx
0x1800ea348  jz      short loc_1800EA374
0x1800ea34a  cmp     byte ptr [rax+19h], 5
0x1800ea34e  jb      short loc_1800EA374
0x1800ea350  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea355  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea35c  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800ea363  mov     edx, 2Ch ; ','
0x1800ea368  mov     r9d, eax
0x1800ea36b  mov     rcx, [rcx+10h]
0x1800ea36f  call    WPP_SF_d
0x1800ea374  mov     rcx, [rdi+20h]
0x1800ea378  mov     [rbp+57h+ExitCode], 0
0x1800ea37f  mov     rax, [rcx]
0x1800ea382  mov     rax, [rax+8]
0x1800ea386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea38b  mov     r9, rdi; lpParameter
0x1800ea38e  mov     [rsp+0A0h+lpThreadId], 0; lpThreadId
0x1800ea397  lea     r8, ?STATIC_ThreadProcResolveServerName@CRDPENCDirectConnector@@KAXPEAX@Z; lpStartAddress
0x1800ea39e  mov     [rsp+0A0h+dwCreationFlags], 0; dwCreationFlags
0x1800ea3a6  xor     edx, edx; dwStackSize
0x1800ea3a8  xor     ecx, ecx; lpThreadAttributes
0x1800ea3aa  call    cs:__imp_CreateThread
0x1800ea3b0  mov     [rdi+150h], rax
0x1800ea3b7  test    rax, rax
0x1800ea3ba  jnz     loc_1800EA474
0x1800ea3c0  call    cs:__imp_GetLastError
0x1800ea3c6  mov     rcx, [rdi+20h]
0x1800ea3ca  mov     [rbp+57h+ExitCode], eax
0x1800ea3cd  mov     rax, [rcx]
0x1800ea3d0  mov     rax, [rax+10h]
0x1800ea3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ea3d9  mov     eax, cs:CallbackContext
0x1800ea3df  cmp     eax, 2
0x1800ea3e2  jbe     short loc_1800EA45B
0x1800ea3e4  mov     eax, [rbp+57h+ExitCode]
0x1800ea3e7  lea     rdx, byte_1801BEEB1
0x1800ea3ee  mov     [rbp+57h+arg_8], eax
0x1800ea3f1  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x1800ea3f8  mov     [rbp+57h+var_50], rax
0x1800ea3fc  lea     rax, aOnecoreTermsrv_46; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ea403  mov     [rbp+57h+var_48], rax
0x1800ea407  lea     rax, aCreateResolves; "Create ResolveServerName Thread failed "...
0x1800ea40e  mov     [rbp+57h+var_40], rax
0x1800ea412  lea     rax, [rbp+57h+arg_8]
0x1800ea416  mov     [rsp+0A0h+var_58], rax
0x1800ea41b  lea     rax, [rbp+57h+var_50]
0x1800ea41f  mov     [rsp+0A0h+var_60], rax
0x1800ea424  lea     rax, [rbp+57h+arg_10]
0x1800ea428  mov     [rsp+0A0h+var_68], rax
0x1800ea42d  lea     rax, [rbp+57h+var_48]
0x1800ea431  mov     [rsp+0A0h+var_70], rax
0x1800ea436  lea     rax, [rbp+57h+arg_18]
0x1800ea43a  mov     [rsp+0A0h+lpThreadId], rax
0x1800ea43f  lea     rax, [rbp+57h+var_40]
0x1800ea443  mov     [rbp+57h+arg_10], 2FDh
0x1800ea44a  mov     [rbp+57h+arg_18], 80004005h
0x1800ea451  mov     qword ptr [rsp+0A0h+dwCreationFlags], rax
0x1800ea456  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ea45b  mov     ebx, [rbp+57h+ExitCode]
0x1800ea45e  test    ebx, ebx
0x1800ea460  jle     loc_1800EA6AF
0x1800ea466  movzx   ebx, bx
0x1800ea469  or      ebx, 80070000h
0x1800ea46f  jmp     loc_1800EA6AF
0x1800ea474  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea47b  cmp     rax, r14
0x1800ea47e  jz      short loc_1800EA4AF
0x1800ea480  test    [rax+1Ch], ebx
0x1800ea483  jz      short loc_1800EA4AF
0x1800ea485  cmp     byte ptr [rax+19h], 5
0x1800ea489  jb      short loc_1800EA4AF
0x1800ea48b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea490  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea497  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800ea49e  mov     edx, 2Dh ; '-'
0x1800ea4a3  mov     r9d, eax
0x1800ea4a6  mov     rcx, [rcx+10h]
0x1800ea4aa  call    WPP_SF_d
0x1800ea4af  mov     rax, [rdi+150h]
0x1800ea4b6  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800ea4ba  xor     r8d, r8d; bWaitAll
0x1800ea4bd  mov     [rbp+57h+Handles], rax
0x1800ea4c1  mov     rax, [rdi+128h]
0x1800ea4c8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800ea4cc  mov     [rbp+57h+var_30], rax
0x1800ea4d0  lea     ecx, [r8+2]; nCount
0x1800ea4d4  call    cs:__imp_WaitForMultipleObjects
0x1800ea4da  mov     [rbp+57h+ExitCode], eax
0x1800ea4dd  test    eax, eax
0x1800ea4df  jz      loc_1800EA5B6
0x1800ea4e5  cmp     eax, 1
0x1800ea4e8  jz      loc_1800EA571
0x1800ea4ee  call    cs:__imp_GetLastError
0x1800ea4f4  mov     [rbp+57h+ExitCode], eax
0x1800ea4f7  mov     eax, cs:CallbackContext
0x1800ea4fd  cmp     eax, 2
0x1800ea500  jbe     loc_1800EA45B
0x1800ea506  mov     eax, [rbp+57h+ExitCode]
0x1800ea509  lea     rdx, word_1801BEE5E
0x1800ea510  mov     [rbp+57h+arg_8], eax
0x1800ea513  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x1800ea51a  mov     [rbp+57h+var_40], rax
0x1800ea51e  lea     rax, aOnecoreTermsrv_46; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ea525  mov     [rbp+57h+var_48], rax
0x1800ea529  lea     rax, aWaitforsingleo; "WaitForSingleObject return error: 0x%x"
0x1800ea530  mov     [rbp+57h+var_50], rax
0x1800ea534  lea     rax, [rbp+57h+arg_8]
0x1800ea538  mov     [rsp+0A0h+var_58], rax
0x1800ea53d  lea     rax, [rbp+57h+var_40]
0x1800ea541  mov     [rsp+0A0h+var_60], rax
0x1800ea546  lea     rax, [rbp+57h+arg_10]
0x1800ea54a  mov     [rsp+0A0h+var_68], rax
0x1800ea54f  lea     rax, [rbp+57h+var_48]
0x1800ea553  mov     [rsp+0A0h+var_70], rax
0x1800ea558  lea     rax, [rbp+57h+arg_18]
0x1800ea55c  mov     [rsp+0A0h+lpThreadId], rax
0x1800ea561  lea     rax, [rbp+57h+var_50]
0x1800ea565  mov     [rbp+57h+arg_10], 32Dh
0x1800ea56c  jmp     loc_1800EA44A
0x1800ea571  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea578  cmp     rax, r14
0x1800ea57b  jz      short loc_1800EA5AC
0x1800ea57d  test    [rax+1Ch], ebx
0x1800ea580  jz      short loc_1800EA5AC
0x1800ea582  cmp     byte ptr [rax+19h], 4
0x1800ea586  jb      short loc_1800EA5AC
0x1800ea588  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea58d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea594  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800ea59b  mov     edx, 2Fh ; '/'
0x1800ea5a0  mov     r9d, eax
0x1800ea5a3  mov     rcx, [rcx+10h]
0x1800ea5a7  call    WPP_SF_d
0x1800ea5ac  mov     ebx, 83450014h
0x1800ea5b1  jmp     loc_1800EA6AF
0x1800ea5b6  mov     rcx, [rdi+150h]; hThread
0x1800ea5bd  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x1800ea5c1  call    cs:__imp_GetExitCodeThread
0x1800ea5c7  test    eax, eax
0x1800ea5c9  jnz     loc_1800EA652
0x1800ea5cf  call    cs:__imp_GetLastError
0x1800ea5d5  mov     [rbp+57h+ExitCode], eax
0x1800ea5d8  mov     eax, cs:CallbackContext
0x1800ea5de  cmp     eax, 2
0x1800ea5e1  jbe     loc_1800EA45B
0x1800ea5e7  mov     eax, [rbp+57h+ExitCode]
0x1800ea5ea  lea     rdx, byte_1801BEE0B
0x1800ea5f1  mov     [rbp+57h+arg_8], eax
0x1800ea5f4  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x1800ea5fb  mov     [rbp+57h+var_40], rax
0x1800ea5ff  lea     rax, aOnecoreTermsrv_46; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800ea606  mov     [rbp+57h+var_48], rax
0x1800ea60a  lea     rax, aFailedToGetThe_30; "Failed to get the resolve name thread e"...
0x1800ea611  mov     [rbp+57h+var_50], rax
0x1800ea615  lea     rax, [rbp+57h+arg_8]
0x1800ea619  mov     [rsp+0A0h+var_58], rax
0x1800ea61e  lea     rax, [rbp+57h+var_40]
0x1800ea622  mov     [rsp+0A0h+var_60], rax
0x1800ea627  lea     rax, [rbp+57h+arg_10]
0x1800ea62b  mov     [rsp+0A0h+var_68], rax
0x1800ea630  lea     rax, [rbp+57h+var_48]
0x1800ea634  mov     [rsp+0A0h+var_70], rax
0x1800ea639  lea     rax, [rbp+57h+arg_18]
0x1800ea63d  mov     [rsp+0A0h+lpThreadId], rax
0x1800ea642  lea     rax, [rbp+57h+var_50]
0x1800ea646  mov     [rbp+57h+arg_10], 314h
0x1800ea64d  jmp     loc_1800EA44A
0x1800ea652  mov     rax, cs:WPP_GLOBAL_Control
0x1800ea659  cmp     rax, r14
0x1800ea65c  jz      short loc_1800EA694
0x1800ea65e  test    [rax+1Ch], ebx
0x1800ea661  jz      short loc_1800EA694
0x1800ea663  cmp     byte ptr [rax+19h], 4
0x1800ea667  jb      short loc_1800EA694
0x1800ea669  mov     ebx, [rbp+57h+ExitCode]
0x1800ea66c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ea671  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea678  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1800ea67f  mov     edx, 2Eh ; '.'
0x1800ea684  mov     [rsp+0A0h+dwCreationFlags], ebx
0x1800ea688  mov     r9d, eax
0x1800ea68b  mov     rcx, [rcx+10h]
0x1800ea68f  call    WPP_SF_Dd
0x1800ea694  mov     rcx, [rdi+150h]; hObject
0x1800ea69b  mov     ebx, [rbp+57h+ExitCode]
0x1800ea69e  call    cs:__imp_CloseHandle
0x1800ea6a4  mov     qword ptr [rdi+150h], 0
0x1800ea6af  mov     eax, ebx
0x1800ea6b1  add     rsp, 88h
0x1800ea6b8  pop     r14
0x1800ea6ba  pop     rdi
0x1800ea6bb  pop     rbx
0x1800ea6bc  pop     rbp
0x1800ea6bd  retn
```
