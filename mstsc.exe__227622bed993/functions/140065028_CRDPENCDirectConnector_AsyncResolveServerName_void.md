# CRDPENCDirectConnector::AsyncResolveServerName(void)

- ea: `0x140065028`
- end: `0x1400653ce`
- name: `?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ`
- size: `934`
- prototype: `__int64 __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400662a4`

## callees

- `0x140001b00`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140065028`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x1400652d1`
- `KERNEL32!GetExitCodeThread` at `0x1400652d1`
- `KERNEL32!WaitForMultipleObjects` at `0x1400651e4`
- `KERNEL32!WaitForMultipleObjects` at `0x1400651e4`
- `KERNEL32!CreateThread` at `0x1400650ba`
- `KERNEL32!CreateThread` at `0x1400650ba`
- `KERNEL32!CloseHandle` at `0x1400653ae`
- `KERNEL32!CloseHandle` at `0x1400653ae`
- `KERNEL32!GetLastError` at `0x1400650d0`
- `KERNEL32!GetLastError` at `0x1400651fe`
- `KERNEL32!GetLastError` at `0x1400652df`
- `KERNEL32!GetLastError` at `0x1400650d0`
- `KERNEL32!GetLastError` at `0x1400651fe`
- `KERNEL32!GetLastError` at `0x1400652df`

## string_xrefs

- `0x14006531a`: `Failed to get the resolve name thread exit code. error: 0x%x`
- `0x140065117`: `Create ResolveServerName Thread failed with error: 0x%x`

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
      WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
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
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_9;
    v10 = byte_14013D613;
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v13);
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v10 = byte_14013D6AB;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v15);
    }
    return (DWORD)-2092629996;
  }
  else
  {
    if ( !GetExitCodeThread(*((HANDLE *)this + 42), &ExitCode) )
    {
      ExitCode = GetLastError();
      if ( (unsigned int)dword_140150118 > 2 )
      {
        v10 = (char *)&word_14013D6FE;
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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids, v17, v16);
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
0x140065028  push    rbp
0x14006502a  push    rbx
0x14006502b  push    rdi
0x14006502c  push    r14
0x14006502e  lea     rbp, [rsp-3Fh]
0x140065033  sub     rsp, 88h
0x14006503a  mov     rdi, rcx
0x14006503d  mov     rax, cs:WPP_GLOBAL_Control
0x140065044  lea     r14, WPP_GLOBAL_Control
0x14006504b  mov     ebx, 800h
0x140065050  cmp     rax, r14
0x140065053  jz      short loc_140065084
0x140065055  test    [rax+1Ch], ebx
0x140065058  jz      short loc_140065084
0x14006505a  cmp     byte ptr [rax+19h], 5
0x14006505e  jb      short loc_140065084
0x140065060  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065065  mov     rcx, cs:WPP_GLOBAL_Control
0x14006506c  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x140065073  mov     edx, 2Ch ; ','
0x140065078  mov     r9d, eax
0x14006507b  mov     rcx, [rcx+10h]
0x14006507f  call    WPP_SF_d
0x140065084  mov     rcx, [rdi+20h]
0x140065088  mov     [rbp+57h+ExitCode], 0
0x14006508f  mov     rax, [rcx]
0x140065092  mov     rax, [rax+8]
0x140065096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006509b  mov     r9, rdi; lpParameter
0x14006509e  mov     [rsp+0A0h+lpThreadId], 0; lpThreadId
0x1400650a7  lea     r8, ?STATIC_ThreadProcResolveServerName@CRDPENCDirectConnector@@KAXPEAX@Z; lpStartAddress
0x1400650ae  mov     [rsp+0A0h+dwCreationFlags], 0; dwCreationFlags
0x1400650b6  xor     edx, edx; dwStackSize
0x1400650b8  xor     ecx, ecx; lpThreadAttributes
0x1400650ba  call    cs:__imp_CreateThread
0x1400650c0  mov     [rdi+150h], rax
0x1400650c7  test    rax, rax
0x1400650ca  jnz     loc_140065184
0x1400650d0  call    cs:__imp_GetLastError
0x1400650d6  mov     rcx, [rdi+20h]
0x1400650da  mov     [rbp+57h+ExitCode], eax
0x1400650dd  mov     rax, [rcx]
0x1400650e0  mov     rax, [rax+10h]
0x1400650e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400650e9  mov     eax, cs:dword_140150118
0x1400650ef  cmp     eax, 2
0x1400650f2  jbe     short loc_14006516B
0x1400650f4  mov     eax, [rbp+57h+ExitCode]
0x1400650f7  lea     rdx, byte_14013D613
0x1400650fe  mov     [rbp+57h+arg_8], eax
0x140065101  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x140065108  mov     [rbp+57h+var_50], rax
0x14006510c  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140065113  mov     [rbp+57h+var_48], rax
0x140065117  lea     rax, aCreateResolves; "Create ResolveServerName Thread failed "...
0x14006511e  mov     [rbp+57h+var_40], rax
0x140065122  lea     rax, [rbp+57h+arg_8]
0x140065126  mov     [rsp+0A0h+var_58], rax
0x14006512b  lea     rax, [rbp+57h+var_50]
0x14006512f  mov     [rsp+0A0h+var_60], rax
0x140065134  lea     rax, [rbp+57h+arg_10]
0x140065138  mov     [rsp+0A0h+var_68], rax
0x14006513d  lea     rax, [rbp+57h+var_48]
0x140065141  mov     [rsp+0A0h+var_70], rax
0x140065146  lea     rax, [rbp+57h+arg_18]
0x14006514a  mov     [rsp+0A0h+lpThreadId], rax
0x14006514f  lea     rax, [rbp+57h+var_40]
0x140065153  mov     [rbp+57h+arg_10], 2FDh
0x14006515a  mov     [rbp+57h+arg_18], 80004005h
0x140065161  mov     qword ptr [rsp+0A0h+dwCreationFlags], rax
0x140065166  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14006516b  mov     ebx, [rbp+57h+ExitCode]
0x14006516e  test    ebx, ebx
0x140065170  jle     loc_1400653BF
0x140065176  movzx   ebx, bx
0x140065179  or      ebx, 80070000h
0x14006517f  jmp     loc_1400653BF
0x140065184  mov     rax, cs:WPP_GLOBAL_Control
0x14006518b  cmp     rax, r14
0x14006518e  jz      short loc_1400651BF
0x140065190  test    [rax+1Ch], ebx
0x140065193  jz      short loc_1400651BF
0x140065195  cmp     byte ptr [rax+19h], 5
0x140065199  jb      short loc_1400651BF
0x14006519b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400651a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400651a7  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1400651ae  mov     edx, 2Dh ; '-'
0x1400651b3  mov     r9d, eax
0x1400651b6  mov     rcx, [rcx+10h]
0x1400651ba  call    WPP_SF_d
0x1400651bf  mov     rax, [rdi+150h]
0x1400651c6  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1400651ca  xor     r8d, r8d; bWaitAll
0x1400651cd  mov     [rbp+57h+Handles], rax
0x1400651d1  mov     rax, [rdi+128h]
0x1400651d8  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400651dc  mov     [rbp+57h+var_30], rax
0x1400651e0  lea     ecx, [r8+2]; nCount
0x1400651e4  call    cs:__imp_WaitForMultipleObjects
0x1400651ea  mov     [rbp+57h+ExitCode], eax
0x1400651ed  test    eax, eax
0x1400651ef  jz      loc_1400652C6
0x1400651f5  cmp     eax, 1
0x1400651f8  jz      loc_140065281
0x1400651fe  call    cs:__imp_GetLastError
0x140065204  mov     [rbp+57h+ExitCode], eax
0x140065207  mov     eax, cs:dword_140150118
0x14006520d  cmp     eax, 2
0x140065210  jbe     loc_14006516B
0x140065216  mov     eax, [rbp+57h+ExitCode]
0x140065219  lea     rdx, byte_14013D6AB
0x140065220  mov     [rbp+57h+arg_8], eax
0x140065223  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x14006522a  mov     [rbp+57h+var_40], rax
0x14006522e  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140065235  mov     [rbp+57h+var_48], rax
0x140065239  lea     rax, aWaitforsingleo; "WaitForSingleObject return error: 0x%x"
0x140065240  mov     [rbp+57h+var_50], rax
0x140065244  lea     rax, [rbp+57h+arg_8]
0x140065248  mov     [rsp+0A0h+var_58], rax
0x14006524d  lea     rax, [rbp+57h+var_40]
0x140065251  mov     [rsp+0A0h+var_60], rax
0x140065256  lea     rax, [rbp+57h+arg_10]
0x14006525a  mov     [rsp+0A0h+var_68], rax
0x14006525f  lea     rax, [rbp+57h+var_48]
0x140065263  mov     [rsp+0A0h+var_70], rax
0x140065268  lea     rax, [rbp+57h+arg_18]
0x14006526c  mov     [rsp+0A0h+lpThreadId], rax
0x140065271  lea     rax, [rbp+57h+var_50]
0x140065275  mov     [rbp+57h+arg_10], 32Dh
0x14006527c  jmp     loc_14006515A
0x140065281  mov     rax, cs:WPP_GLOBAL_Control
0x140065288  cmp     rax, r14
0x14006528b  jz      short loc_1400652BC
0x14006528d  test    [rax+1Ch], ebx
0x140065290  jz      short loc_1400652BC
0x140065292  cmp     byte ptr [rax+19h], 4
0x140065296  jb      short loc_1400652BC
0x140065298  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006529d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400652a4  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1400652ab  mov     edx, 2Fh ; '/'
0x1400652b0  mov     r9d, eax
0x1400652b3  mov     rcx, [rcx+10h]
0x1400652b7  call    WPP_SF_d
0x1400652bc  mov     ebx, 83450014h
0x1400652c1  jmp     loc_1400653BF
0x1400652c6  mov     rcx, [rdi+150h]; hThread
0x1400652cd  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x1400652d1  call    cs:__imp_GetExitCodeThread
0x1400652d7  test    eax, eax
0x1400652d9  jnz     loc_140065362
0x1400652df  call    cs:__imp_GetLastError
0x1400652e5  mov     [rbp+57h+ExitCode], eax
0x1400652e8  mov     eax, cs:dword_140150118
0x1400652ee  cmp     eax, 2
0x1400652f1  jbe     loc_14006516B
0x1400652f7  mov     eax, [rbp+57h+ExitCode]
0x1400652fa  lea     rdx, word_14013D6FE
0x140065301  mov     [rbp+57h+arg_8], eax
0x140065304  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x14006530b  mov     [rbp+57h+var_40], rax
0x14006530f  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140065316  mov     [rbp+57h+var_48], rax
0x14006531a  lea     rax, aFailedToGetThe_16; "Failed to get the resolve name thread e"...
0x140065321  mov     [rbp+57h+var_50], rax
0x140065325  lea     rax, [rbp+57h+arg_8]
0x140065329  mov     [rsp+0A0h+var_58], rax
0x14006532e  lea     rax, [rbp+57h+var_40]
0x140065332  mov     [rsp+0A0h+var_60], rax
0x140065337  lea     rax, [rbp+57h+arg_10]
0x14006533b  mov     [rsp+0A0h+var_68], rax
0x140065340  lea     rax, [rbp+57h+var_48]
0x140065344  mov     [rsp+0A0h+var_70], rax
0x140065349  lea     rax, [rbp+57h+arg_18]
0x14006534d  mov     [rsp+0A0h+lpThreadId], rax
0x140065352  lea     rax, [rbp+57h+var_50]
0x140065356  mov     [rbp+57h+arg_10], 314h
0x14006535d  jmp     loc_14006515A
0x140065362  mov     rax, cs:WPP_GLOBAL_Control
0x140065369  cmp     rax, r14
0x14006536c  jz      short loc_1400653A4
0x14006536e  test    [rax+1Ch], ebx
0x140065371  jz      short loc_1400653A4
0x140065373  cmp     byte ptr [rax+19h], 4
0x140065377  jb      short loc_1400653A4
0x140065379  mov     ebx, [rbp+57h+ExitCode]
0x14006537c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140065381  mov     rcx, cs:WPP_GLOBAL_Control
0x140065388  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006538f  mov     edx, 2Eh ; '.'
0x140065394  mov     [rsp+0A0h+dwCreationFlags], ebx
0x140065398  mov     r9d, eax
0x14006539b  mov     rcx, [rcx+10h]
0x14006539f  call    WPP_SF_Dd
0x1400653a4  mov     rcx, [rdi+150h]; hObject
0x1400653ab  mov     ebx, [rbp+57h+ExitCode]
0x1400653ae  call    cs:__imp_CloseHandle
0x1400653b4  mov     qword ptr [rdi+150h], 0
0x1400653bf  mov     eax, ebx
0x1400653c1  add     rsp, 88h
0x1400653c8  pop     r14
0x1400653ca  pop     rdi
0x1400653cb  pop     rbx
0x1400653cc  pop     rbp
0x1400653cd  retn
```
