# CRDPENCDirectConnector::AsyncResolveServerName(void)

- ea: `0x140067198`
- end: `0x14006753e`
- name: `?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ`
- size: `934`
- prototype: `__int64 __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140068414`

## callees

- `0x140001b00`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140067198`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetExitCodeThread` at `0x140067441`
- `KERNEL32!GetExitCodeThread` at `0x140067441`
- `KERNEL32!WaitForMultipleObjects` at `0x140067354`
- `KERNEL32!WaitForMultipleObjects` at `0x140067354`
- `KERNEL32!CreateThread` at `0x14006722a`
- `KERNEL32!CreateThread` at `0x14006722a`
- `KERNEL32!CloseHandle` at `0x14006751e`
- `KERNEL32!CloseHandle` at `0x14006751e`
- `KERNEL32!GetLastError` at `0x140067240`
- `KERNEL32!GetLastError` at `0x14006736e`
- `KERNEL32!GetLastError` at `0x14006744f`
- `KERNEL32!GetLastError` at `0x140067240`
- `KERNEL32!GetLastError` at `0x14006736e`
- `KERNEL32!GetLastError` at `0x14006744f`

## string_xrefs

- `0x14006748a`: `Failed to get the resolve name thread exit code. error: 0x%x`
- `0x140067287`: `Create ResolveServerName Thread failed with error: 0x%x`

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
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_9;
    v10 = byte_14013F74B;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v10 = byte_14013F7E3;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        v10 = (char *)&word_14013F836;
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
0x140067198  push    rbp
0x14006719a  push    rbx
0x14006719b  push    rdi
0x14006719c  push    r14
0x14006719e  lea     rbp, [rsp-3Fh]
0x1400671a3  sub     rsp, 88h
0x1400671aa  mov     rdi, rcx
0x1400671ad  mov     rax, cs:WPP_GLOBAL_Control
0x1400671b4  lea     r14, WPP_GLOBAL_Control
0x1400671bb  mov     ebx, 800h
0x1400671c0  cmp     rax, r14
0x1400671c3  jz      short loc_1400671F4
0x1400671c5  test    [rax+1Ch], ebx
0x1400671c8  jz      short loc_1400671F4
0x1400671ca  cmp     byte ptr [rax+19h], 5
0x1400671ce  jb      short loc_1400671F4
0x1400671d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400671d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400671dc  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1400671e3  mov     edx, 2Ch ; ','
0x1400671e8  mov     r9d, eax
0x1400671eb  mov     rcx, [rcx+10h]
0x1400671ef  call    WPP_SF_d
0x1400671f4  mov     rcx, [rdi+20h]
0x1400671f8  mov     [rbp+57h+ExitCode], 0
0x1400671ff  mov     rax, [rcx]
0x140067202  mov     rax, [rax+8]
0x140067206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006720b  mov     r9, rdi; lpParameter
0x14006720e  mov     [rsp+0A0h+lpThreadId], 0; lpThreadId
0x140067217  lea     r8, ?STATIC_ThreadProcResolveServerName@CRDPENCDirectConnector@@KAXPEAX@Z; lpStartAddress
0x14006721e  mov     [rsp+0A0h+dwCreationFlags], 0; dwCreationFlags
0x140067226  xor     edx, edx; dwStackSize
0x140067228  xor     ecx, ecx; lpThreadAttributes
0x14006722a  call    cs:__imp_CreateThread
0x140067230  mov     [rdi+150h], rax
0x140067237  test    rax, rax
0x14006723a  jnz     loc_1400672F4
0x140067240  call    cs:__imp_GetLastError
0x140067246  mov     rcx, [rdi+20h]
0x14006724a  mov     [rbp+57h+ExitCode], eax
0x14006724d  mov     rax, [rcx]
0x140067250  mov     rax, [rax+10h]
0x140067254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140067259  mov     eax, cs:dword_140152118
0x14006725f  cmp     eax, 2
0x140067262  jbe     short loc_1400672DB
0x140067264  mov     eax, [rbp+57h+ExitCode]
0x140067267  lea     rdx, byte_14013F74B
0x14006726e  mov     [rbp+57h+arg_8], eax
0x140067271  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x140067278  mov     [rbp+57h+var_50], rax
0x14006727c  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140067283  mov     [rbp+57h+var_48], rax
0x140067287  lea     rax, aCreateResolves; "Create ResolveServerName Thread failed "...
0x14006728e  mov     [rbp+57h+var_40], rax
0x140067292  lea     rax, [rbp+57h+arg_8]
0x140067296  mov     [rsp+0A0h+var_58], rax
0x14006729b  lea     rax, [rbp+57h+var_50]
0x14006729f  mov     [rsp+0A0h+var_60], rax
0x1400672a4  lea     rax, [rbp+57h+arg_10]
0x1400672a8  mov     [rsp+0A0h+var_68], rax
0x1400672ad  lea     rax, [rbp+57h+var_48]
0x1400672b1  mov     [rsp+0A0h+var_70], rax
0x1400672b6  lea     rax, [rbp+57h+arg_18]
0x1400672ba  mov     [rsp+0A0h+lpThreadId], rax
0x1400672bf  lea     rax, [rbp+57h+var_40]
0x1400672c3  mov     [rbp+57h+arg_10], 2FDh
0x1400672ca  mov     [rbp+57h+arg_18], 80004005h
0x1400672d1  mov     qword ptr [rsp+0A0h+dwCreationFlags], rax
0x1400672d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400672db  mov     ebx, [rbp+57h+ExitCode]
0x1400672de  test    ebx, ebx
0x1400672e0  jle     loc_14006752F
0x1400672e6  movzx   ebx, bx
0x1400672e9  or      ebx, 80070000h
0x1400672ef  jmp     loc_14006752F
0x1400672f4  mov     rax, cs:WPP_GLOBAL_Control
0x1400672fb  cmp     rax, r14
0x1400672fe  jz      short loc_14006732F
0x140067300  test    [rax+1Ch], ebx
0x140067303  jz      short loc_14006732F
0x140067305  cmp     byte ptr [rax+19h], 5
0x140067309  jb      short loc_14006732F
0x14006730b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140067310  mov     rcx, cs:WPP_GLOBAL_Control
0x140067317  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006731e  mov     edx, 2Dh ; '-'
0x140067323  mov     r9d, eax
0x140067326  mov     rcx, [rcx+10h]
0x14006732a  call    WPP_SF_d
0x14006732f  mov     rax, [rdi+150h]
0x140067336  lea     rdx, [rbp+57h+Handles]; lpHandles
0x14006733a  xor     r8d, r8d; bWaitAll
0x14006733d  mov     [rbp+57h+Handles], rax
0x140067341  mov     rax, [rdi+128h]
0x140067348  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14006734c  mov     [rbp+57h+var_30], rax
0x140067350  lea     ecx, [r8+2]; nCount
0x140067354  call    cs:__imp_WaitForMultipleObjects
0x14006735a  mov     [rbp+57h+ExitCode], eax
0x14006735d  test    eax, eax
0x14006735f  jz      loc_140067436
0x140067365  cmp     eax, 1
0x140067368  jz      loc_1400673F1
0x14006736e  call    cs:__imp_GetLastError
0x140067374  mov     [rbp+57h+ExitCode], eax
0x140067377  mov     eax, cs:dword_140152118
0x14006737d  cmp     eax, 2
0x140067380  jbe     loc_1400672DB
0x140067386  mov     eax, [rbp+57h+ExitCode]
0x140067389  lea     rdx, byte_14013F7E3
0x140067390  mov     [rbp+57h+arg_8], eax
0x140067393  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x14006739a  mov     [rbp+57h+var_40], rax
0x14006739e  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400673a5  mov     [rbp+57h+var_48], rax
0x1400673a9  lea     rax, aWaitforsingleo; "WaitForSingleObject return error: 0x%x"
0x1400673b0  mov     [rbp+57h+var_50], rax
0x1400673b4  lea     rax, [rbp+57h+arg_8]
0x1400673b8  mov     [rsp+0A0h+var_58], rax
0x1400673bd  lea     rax, [rbp+57h+var_40]
0x1400673c1  mov     [rsp+0A0h+var_60], rax
0x1400673c6  lea     rax, [rbp+57h+arg_10]
0x1400673ca  mov     [rsp+0A0h+var_68], rax
0x1400673cf  lea     rax, [rbp+57h+var_48]
0x1400673d3  mov     [rsp+0A0h+var_70], rax
0x1400673d8  lea     rax, [rbp+57h+arg_18]
0x1400673dc  mov     [rsp+0A0h+lpThreadId], rax
0x1400673e1  lea     rax, [rbp+57h+var_50]
0x1400673e5  mov     [rbp+57h+arg_10], 32Dh
0x1400673ec  jmp     loc_1400672CA
0x1400673f1  mov     rax, cs:WPP_GLOBAL_Control
0x1400673f8  cmp     rax, r14
0x1400673fb  jz      short loc_14006742C
0x1400673fd  test    [rax+1Ch], ebx
0x140067400  jz      short loc_14006742C
0x140067402  cmp     byte ptr [rax+19h], 4
0x140067406  jb      short loc_14006742C
0x140067408  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006740d  mov     rcx, cs:WPP_GLOBAL_Control
0x140067414  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006741b  mov     edx, 2Fh ; '/'
0x140067420  mov     r9d, eax
0x140067423  mov     rcx, [rcx+10h]
0x140067427  call    WPP_SF_d
0x14006742c  mov     ebx, 83450014h
0x140067431  jmp     loc_14006752F
0x140067436  mov     rcx, [rdi+150h]; hThread
0x14006743d  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x140067441  call    cs:__imp_GetExitCodeThread
0x140067447  test    eax, eax
0x140067449  jnz     loc_1400674D2
0x14006744f  call    cs:__imp_GetLastError
0x140067455  mov     [rbp+57h+ExitCode], eax
0x140067458  mov     eax, cs:dword_140152118
0x14006745e  cmp     eax, 2
0x140067461  jbe     loc_1400672DB
0x140067467  mov     eax, [rbp+57h+ExitCode]
0x14006746a  lea     rdx, word_14013F836
0x140067471  mov     [rbp+57h+arg_8], eax
0x140067474  lea     rax, aAsyncresolvese; "AsyncResolveServerName"
0x14006747b  mov     [rbp+57h+var_40], rax
0x14006747f  lea     rax, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140067486  mov     [rbp+57h+var_48], rax
0x14006748a  lea     rax, aFailedToGetThe_16; "Failed to get the resolve name thread e"...
0x140067491  mov     [rbp+57h+var_50], rax
0x140067495  lea     rax, [rbp+57h+arg_8]
0x140067499  mov     [rsp+0A0h+var_58], rax
0x14006749e  lea     rax, [rbp+57h+var_40]
0x1400674a2  mov     [rsp+0A0h+var_60], rax
0x1400674a7  lea     rax, [rbp+57h+arg_10]
0x1400674ab  mov     [rsp+0A0h+var_68], rax
0x1400674b0  lea     rax, [rbp+57h+var_48]
0x1400674b4  mov     [rsp+0A0h+var_70], rax
0x1400674b9  lea     rax, [rbp+57h+arg_18]
0x1400674bd  mov     [rsp+0A0h+lpThreadId], rax
0x1400674c2  lea     rax, [rbp+57h+var_50]
0x1400674c6  mov     [rbp+57h+arg_10], 314h
0x1400674cd  jmp     loc_1400672CA
0x1400674d2  mov     rax, cs:WPP_GLOBAL_Control
0x1400674d9  cmp     rax, r14
0x1400674dc  jz      short loc_140067514
0x1400674de  test    [rax+1Ch], ebx
0x1400674e1  jz      short loc_140067514
0x1400674e3  cmp     byte ptr [rax+19h], 4
0x1400674e7  jb      short loc_140067514
0x1400674e9  mov     ebx, [rbp+57h+ExitCode]
0x1400674ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400674f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400674f8  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1400674ff  mov     edx, 2Eh ; '.'
0x140067504  mov     [rsp+0A0h+dwCreationFlags], ebx
0x140067508  mov     r9d, eax
0x14006750b  mov     rcx, [rcx+10h]
0x14006750f  call    WPP_SF_Dd
0x140067514  mov     rcx, [rdi+150h]; hObject
0x14006751b  mov     ebx, [rbp+57h+ExitCode]
0x14006751e  call    cs:__imp_CloseHandle
0x140067524  mov     qword ptr [rdi+150h], 0
0x14006752f  mov     eax, ebx
0x140067531  add     rsp, 88h
0x140067538  pop     r14
0x14006753a  pop     rdi
0x14006753b  pop     rbx
0x14006753c  pop     rbp
0x14006753d  retn
```
