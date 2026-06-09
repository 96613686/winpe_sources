# CRDPENCDirectConnector::ThreadProc(void)

- ea: `0x140068414`
- end: `0x140068c1e`
- name: `?ThreadProc@CRDPENCDirectConnector@@IEAAXXZ`
- size: `2058`
- prototype: `void __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140068220`

## callees

- `0x140001940`
- `0x1400019e8`
- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x14001e130`
- `0x14003e0b4`
- `0x140067198`
- `0x140067544`
- `0x1400675e8`
- `0x1400679cc`
- `0x140067c4c`
- `0x140068414`
- `0x140074600`
- `0x140074bec`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!CancelWaitableTimer` at `0x1400688f3`
- `KERNEL32!CancelWaitableTimer` at `0x1400688f3`
- `KERNEL32!SetWaitableTimer` at `0x140068867`
- `KERNEL32!SetWaitableTimer` at `0x140068867`
- `KERNEL32!CreateWaitableTimerExW` at `0x1400687bb`
- `KERNEL32!CreateWaitableTimerExW` at `0x1400687bb`
- `KERNEL32!CreateEventW` at `0x1400684bd`
- `KERNEL32!CreateEventW` at `0x14006875a`
- `KERNEL32!CreateEventW` at `0x1400684bd`
- `KERNEL32!CreateEventW` at `0x14006875a`
- `KERNEL32!CloseHandle` at `0x140068aa7`
- `KERNEL32!CloseHandle` at `0x140068aa7`
- `KERNEL32!GetLastError` at `0x1400684cf`
- `KERNEL32!GetLastError` at `0x14006876c`
- `KERNEL32!GetLastError` at `0x1400687c9`
- `KERNEL32!GetLastError` at `0x140068871`
- `KERNEL32!GetLastError` at `0x1400684cf`
- `KERNEL32!GetLastError` at `0x14006876c`
- `KERNEL32!GetLastError` at `0x1400687c9`
- `KERNEL32!GetLastError` at `0x140068871`
- `ADVAPI32!EventActivityIdControl` at `0x140068470`
- `ADVAPI32!EventActivityIdControl` at `0x140068ae8`
- `ADVAPI32!EventActivityIdControl` at `0x140068470`
- `ADVAPI32!EventActivityIdControl` at `0x140068ae8`

## string_xrefs

- `0x140068b93`: `Failed to complete the connection`
- `0x140068605`: `ThreadProc`
- `0x1400688d9`: `ThreadProc`
- `0x140068a6d`: `Failed to create a new connection`

## pseudocode

```c
void __fastcall CRDPENCDirectConnector::ThreadProc(CRDPENCDirectConnector *this)
{
  GUID v2; // xmm0
  HANDLE WaitableTimer; // r13
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rdi
  HANDLE EventW; // rax
  signed int LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned int started; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  unsigned int v18; // edi
  char *v19; // rax
  char *v20; // rsi
  char *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // r15d
  __int64 v26; // rcx
  HANDLE v27; // rax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  LONG v31; // r8d
  unsigned int v32; // edx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+54h] [rbp-55h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-51h]
  const char *v41; // [rsp+60h] [rbp-49h] BYREF
  __int64 v42; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int64 v43; // [rsp+70h] [rbp-39h] BYREF
  const char *v44; // [rsp+78h] [rbp-31h] BYREF
  LARGE_INTEGER DueTime; // [rsp+80h] [rbp-29h] BYREF
  const char *v46; // [rsp+88h] [rbp-21h] BYREF
  __int128 v47; // [rsp+90h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp-9h] BYREF

  v40 = 0;
  v47 = 0;
  v2 = *(GUID *)((char *)this + 244);
  DueTime.QuadPart = 0;
  WaitableTimer = 0;
  v43 = -1;
  ActivityId = v2;
  EventActivityIdControl(4u, &ActivityId);
  v4 = *((_QWORD *)this + 27);
  v5 = 0;
  v42 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
  if ( v6 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v42);
    v5 = v6;
    v42 = v6;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v42);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 37) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_9;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 29;
LABEL_8:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
LABEL_9:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_83;
  }
  LastError = CRDPENCDirectConnector::AsyncResolveServerName(this);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 30;
    v13 = "Failed to resolve server name asynchronously";
    goto LABEL_82;
  }
  LastError = CRDPENCONResolver::SortAddresses((CRDPENCDirectConnector *)((char *)this + 56));
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 31;
    v13 = "Failed to sort the address list";
    goto LABEL_82;
  }
  started = CRDPENCONResolver::StartEnum((CRDPENCDirectConnector *)((char *)this + 56));
  v18 = started;
  if ( started )
  {
    v19 = (char *)operator new(saturated_mul(started, 8u));
    v20 = (char *)this + 304;
    v21 = v19;
    *((_QWORD *)this + 38) = v19;
    if ( v19 )
    {
      if ( v18 )
      {
        v23 = 0;
        if ( v18 < 2 || v19 <= v20 && &v19[8 * v18 - 8] >= v20 )
          goto LABEL_109;
        v24 = v18 & 0xFFFFFFFE;
        do
        {
          v23 += 2;
          v25 = v23;
        }
        while ( v23 < v24 );
        memset_0(v21, -1, 16 * ((unsigned __int64)v24 >> 1));
        v23 = v25;
        if ( v25 < v18 )
        {
LABEL_109:
          do
          {
            v26 = v23++;
            *(_QWORD *)(*(_QWORD *)v20 + 8 * v26) = -1;
          }
          while ( v23 < v18 );
        }
      }
      *((_DWORD *)this + 78) = v18;
      *((_DWORD *)this + 79) = 0;
      v27 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 36) = v27;
      if ( !v27 )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 33;
        goto LABEL_8;
      }
      WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
      if ( !WaitableTimer )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 34;
        goto LABEL_8;
      }
      if ( (unsigned int)dword_140152118 > 5 )
      {
        v38 = *((_DWORD *)this + 65);
        v41 = "Trying to connection using Conn Q Interval: %d";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)&word_14013F8CE,
          v29,
          v30,
          (__int64)&v41,
          (__int64)&v38);
      }
      v31 = *((_DWORD *)this + 65);
      DueTime.QuadPart = 0;
      if ( !SetWaitableTimer(WaitableTimer, &DueTime, v31, 0, 0, 0) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_9;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 35;
        goto LABEL_8;
      }
      *((_QWORD *)&v47 + 1) = *((_QWORD *)this + 36);
      *(_QWORD *)&v47 = WaitableTimer;
      LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
      if ( LastError < 0 )
      {
LABEL_78:
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_83;
        }
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 36;
        v13 = "Failed to create a new connection";
LABEL_82:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          (unsigned int)WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v11,
          (__int64)v13,
          LastError);
        goto LABEL_83;
      }
      while ( 1 )
      {
        if ( LastError == 1 )
        {
          CancelWaitableTimer(WaitableTimer);
          v32 = *((_DWORD *)this + 79);
          if ( !v32 )
          {
LABEL_65:
            LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, 0xFFFFFFFFFFFFFFFFuLL);
            if ( LastError < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = RdpWppGetCurrentThreadActivityIdPrefix();
              v12 = 37;
LABEL_70:
              v13 = "Failed to fire the event";
              goto LABEL_82;
            }
            goto LABEL_83;
          }
          v33 = 0;
          while ( *(_QWORD *)(*((_QWORD *)this + 38) + 8 * v33) == -1 )
          {
            v33 = (unsigned int)(v33 + 1);
            if ( (unsigned int)v33 >= v32 )
              goto LABEL_65;
          }
        }
        LastError = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v5 + 80LL))(v5, 2, &v47);
        if ( LastError < 0 )
          break;
        if ( v40 > 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids);
          }
          LastError = -2147418113;
          goto LABEL_83;
        }
        v34 = CRDPENCDirectConnector::CompletePendingConnection(this, &v43);
        LastError = v34;
        if ( v34 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 39;
            v13 = "Failed to complete the connection";
            goto LABEL_82;
          }
          goto LABEL_83;
        }
        if ( !v34 )
        {
          LastError = CRDPENCDirectConnector::FireConnectionCompleted(this, v43);
          if ( LastError < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 40;
            goto LABEL_70;
          }
          goto LABEL_83;
        }
        if ( (unsigned int)dword_140152118 > 2 )
        {
          v41 = "ThreadProc";
          v46 = "Trying the next connector";
          v38 = 623;
          v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
          v39 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v35,
            (unsigned int)&word_14013F79E,
            v36,
            v37,
            (__int64)&v46,
            (__int64)&v39,
            (__int64)&v44,
            (__int64)&v38,
            (__int64)&v41);
        }
        LastError = CRDPENCDirectConnector::CreatePendingConnection(this);
        if ( LastError < 0 )
          goto LABEL_78;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        v12 = 38;
        v13 = "Wait failed";
        goto LABEL_82;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids,
          v22,
          -2147024882);
      }
      LastError = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v39 = 523;
      v41 = "Failed to resolve any IPS";
      v43 = (unsigned __int64)"ThreadProc";
      v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
      v38 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)byte_14013F889,
        v16,
        v17,
        (__int64)&v41,
        (__int64)&v38,
        (__int64)&v44,
        (__int64)&v39,
        (__int64)&v43);
    }
    LastError = -2092621306;
  }
LABEL_83:
  CRDPENCDirectConnector::ClearPendingConnections(this);
  if ( WaitableTimer )
    CloseHandle(WaitableTimer);
  if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2092629996 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 29) + 32LL))(
      *((_QWORD *)this + 29),
      (unsigned int)LastError);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v42);
  EventActivityIdControl(2u, &ActivityId);
}

```

## disassembly

```asm
0x140068414  push    rbp
0x140068416  push    rbx
0x140068417  push    rsi
0x140068418  push    rdi
0x140068419  push    r12
0x14006841b  push    r13
0x14006841d  push    r14
0x14006841f  push    r15
0x140068421  lea     rbp, [rsp-1Fh]
0x140068426  sub     rsp, 0C8h
0x14006842d  mov     rax, cs:__security_cookie
0x140068434  xor     rax, rsp
0x140068437  mov     [rbp+57h+var_50], rax
0x14006843b  xor     r12d, r12d
0x14006843e  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x140068442  xorps   xmm0, xmm0
0x140068445  mov     [rbp+57h+var_A8], r12d
0x140068449  movups  [rbp+57h+var_70], xmm0
0x14006844d  mov     r14, rcx
0x140068450  or      r15, 0FFFFFFFFFFFFFFFFh
0x140068454  movups  xmm0, xmmword ptr [rcx+0F4h]
0x14006845b  lea     ecx, [r12+4]; ControlCode
0x140068460  mov     qword ptr [rbp+57h+DueTime], r12
0x140068464  mov     r13d, r12d
0x140068467  mov     [rbp+57h+var_90], r15
0x14006846b  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x140068470  call    cs:__imp_EventActivityIdControl
0x140068476  mov     rcx, [r14+0D8h]
0x14006847d  mov     ebx, r12d
0x140068480  mov     [rbp+57h+var_98], rbx
0x140068484  mov     rax, [rcx]
0x140068487  mov     rax, [rax+40h]
0x14006848b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068490  mov     rdi, rax
0x140068493  test    rax, rax
0x140068496  jz      short loc_1400684B1
0x140068498  lea     rcx, [rbp+57h+var_98]
0x14006849c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400684a1  mov     rbx, rdi
0x1400684a4  lea     rcx, [rbp+57h+var_98]
0x1400684a8  mov     [rbp+57h+var_98], rbx
0x1400684ac  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1400684b1  xor     r9d, r9d; lpName
0x1400684b4  xor     r8d, r8d; bInitialState
0x1400684b7  xor     ecx, ecx; lpEventAttributes
0x1400684b9  lea     edx, [r9+1]; bManualReset
0x1400684bd  call    cs:__imp_CreateEventW
0x1400684c3  mov     [r14+128h], rax
0x1400684ca  test    rax, rax
0x1400684cd  jnz     short loc_14006853A
0x1400684cf  call    cs:__imp_GetLastError
0x1400684d5  mov     edi, eax
0x1400684d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400684de  lea     rax, WPP_GLOBAL_Control
0x1400684e5  cmp     rcx, rax
0x1400684e8  jz      short loc_14006851E
0x1400684ea  test    byte ptr [rcx+1Ch], 8
0x1400684ee  jz      short loc_14006851E
0x1400684f0  cmp     byte ptr [rcx+19h], 2
0x1400684f4  jb      short loc_14006851E
0x1400684f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400684fb  mov     edx, 1Dh
0x140068500  mov     rcx, cs:WPP_GLOBAL_Control
0x140068507  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006850e  mov     r9d, eax
0x140068511  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], edi
0x140068515  mov     rcx, [rcx+10h]
0x140068519  call    WPP_SF_Dd
0x14006851e  test    edi, edi
0x140068520  jle     short loc_14006852B
0x140068522  movzx   edi, di
0x140068525  or      edi, 80070000h
0x14006852b  test    edi, edi
0x14006852d  mov     esi, 80004005h
0x140068532  cmovns  edi, esi
0x140068535  jmp     loc_140068A97
0x14006853a  mov     rcx, r14; this
0x14006853d  call    ?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::AsyncResolveServerName(void)
0x140068542  mov     edi, eax
0x140068544  test    eax, eax
0x140068546  jns     short loc_140068589
0x140068548  mov     rcx, cs:WPP_GLOBAL_Control
0x14006854f  lea     rax, WPP_GLOBAL_Control
0x140068556  cmp     rcx, rax
0x140068559  jz      loc_140068A97
0x14006855f  test    byte ptr [rcx+1Ch], 8
0x140068563  jz      loc_140068A97
0x140068569  cmp     byte ptr [rcx+19h], 2
0x14006856d  jb      loc_140068A97
0x140068573  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140068578  mov     edx, 1Eh
0x14006857d  lea     rcx, aFailedToResolv; "Failed to resolve server name asynchron"...
0x140068584  jmp     loc_140068A74
0x140068589  lea     rcx, [r14+38h]; this
0x14006858d  call    ?SortAddresses@CRDPENCONResolver@@QEAAJXZ; CRDPENCONResolver::SortAddresses(void)
0x140068592  mov     edi, eax
0x140068594  test    eax, eax
0x140068596  jns     short loc_1400685D9
0x140068598  mov     rcx, cs:WPP_GLOBAL_Control
0x14006859f  lea     rax, WPP_GLOBAL_Control
0x1400685a6  cmp     rcx, rax
0x1400685a9  jz      loc_140068A97
0x1400685af  test    byte ptr [rcx+1Ch], 8
0x1400685b3  jz      loc_140068A97
0x1400685b9  cmp     byte ptr [rcx+19h], 2
0x1400685bd  jb      loc_140068A97
0x1400685c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400685c8  mov     edx, 1Fh
0x1400685cd  lea     rcx, aFailedToSortTh; "Failed to sort the address list"
0x1400685d4  jmp     loc_140068A74
0x1400685d9  lea     rcx, [r14+38h]; this
0x1400685dd  call    ?StartEnum@CRDPENCONResolver@@QEAAIXZ; CRDPENCONResolver::StartEnum(void)
0x1400685e2  mov     edi, eax
0x1400685e4  test    eax, eax
0x1400685e6  jnz     short loc_140068666
0x1400685e8  mov     eax, cs:dword_140152118
0x1400685ee  cmp     eax, 2
0x1400685f1  jbe     short loc_14006865C
0x1400685f3  lea     rax, aFailedToResolv_0; "Failed to resolve any IPS"
0x1400685fa  mov     [rbp+57h+var_AC], 20Bh
0x140068601  mov     [rbp+57h+var_A0], rax
0x140068605  lea     r15, aThreadproc; "ThreadProc"
0x14006860c  lea     rax, [rbp+57h+var_90]
0x140068610  mov     [rbp+57h+var_90], r15
0x140068614  mov     [rsp+100h+var_C0], rax
0x140068619  lea     r12, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140068620  lea     rax, [rbp+57h+var_AC]
0x140068624  mov     [rbp+57h+var_88], r12
0x140068628  mov     [rsp+100h+var_C8], rax
0x14006862d  lea     rdx, byte_14013F889
0x140068634  lea     rax, [rbp+57h+var_88]
0x140068638  mov     esi, 80004005h
0x14006863d  mov     [rsp+100h+var_D0], rax
0x140068642  lea     rax, [rbp+57h+var_B0]
0x140068646  mov     qword ptr [rsp+100h+fResume], rax
0x14006864b  lea     rax, [rbp+57h+var_A0]
0x14006864f  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x140068654  mov     [rbp+57h+var_B0], esi
0x140068657  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14006865c  mov     edi, 83452206h
0x140068661  jmp     loc_140068A97
0x140068666  mov     eax, 8
0x14006866b  mul     rdi
0x14006866e  cmovb   rax, r15
0x140068672  mov     rcx, rax; Size
0x140068675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006867a  lea     rsi, [r14+130h]
0x140068681  mov     r9, rax
0x140068684  mov     [rsi], rax
0x140068687  test    rax, rax
0x14006868a  jnz     short loc_1400686E1
0x14006868c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068693  lea     rax, WPP_GLOBAL_Control
0x14006869a  cmp     rcx, rax
0x14006869d  jz      short loc_1400686D7
0x14006869f  test    byte ptr [rcx+1Ch], 8
0x1400686a3  jz      short loc_1400686D7
0x1400686a5  cmp     byte ptr [rcx+19h], 2
0x1400686a9  jb      short loc_1400686D7
0x1400686ab  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400686b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400686b7  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x1400686be  mov     edx, 20h ; ' '
0x1400686c3  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], 8007000Eh
0x1400686cb  mov     r9d, eax
0x1400686ce  mov     rcx, [rcx+10h]
0x1400686d2  call    WPP_SF_Dd
0x1400686d7  mov     edi, 8007000Eh
0x1400686dc  jmp     loc_140068A97
0x1400686e1  test    edi, edi
0x1400686e3  jz      short loc_140068742
0x1400686e5  mov     edx, r12d
0x1400686e8  cmp     edi, 2
0x1400686eb  jb      short loc_140068733
0x1400686ed  cmp     r9, rsi
0x1400686f0  ja      short loc_1400686FE
0x1400686f2  lea     eax, [rdi-1]
0x1400686f5  lea     rax, [r9+rax*8]
0x1400686f9  cmp     rax, rsi
0x1400686fc  jnb     short loc_140068733
0x1400686fe  mov     eax, edi
0x140068700  and     eax, 0FFFFFFFEh
0x140068703  add     edx, 2
0x140068706  mov     r15d, edx
0x140068709  cmp     edx, eax
0x14006870b  jb      short loc_140068703
0x14006870d  mov     r8d, eax
0x140068710  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x140068714  shr     r8, 1
0x140068717  mov     rcx, r9; void *
0x14006871a  shl     r8, 4
0x14006871e  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x140068722  call    memset_0
0x140068727  mov     edx, r15d
0x14006872a  cmp     r15d, edi
0x14006872d  jnb     short loc_140068742
0x14006872f  or      r15, 0FFFFFFFFFFFFFFFFh
0x140068733  mov     rax, [rsi]
0x140068736  mov     ecx, edx
0x140068738  inc     edx
0x14006873a  mov     [rax+rcx*8], r15
0x14006873e  cmp     edx, edi
0x140068740  jb      short loc_140068733
0x140068742  xor     r9d, r9d; lpName
0x140068745  mov     [r14+138h], edi
0x14006874c  xor     r8d, r8d; bInitialState
0x14006874f  mov     [r14+13Ch], r12d
0x140068756  xor     edx, edx; bManualReset
0x140068758  xor     ecx, ecx; lpEventAttributes
0x14006875a  call    cs:__imp_CreateEventW
0x140068760  mov     [r14+120h], rax
0x140068767  test    rax, rax
0x14006876a  jnz     short loc_1400687AE
0x14006876c  call    cs:__imp_GetLastError
0x140068772  mov     edi, eax
0x140068774  mov     rcx, cs:WPP_GLOBAL_Control
0x14006877b  lea     rax, WPP_GLOBAL_Control
0x140068782  cmp     rcx, rax
0x140068785  jz      loc_14006851E
0x14006878b  test    byte ptr [rcx+1Ch], 8
0x14006878f  jz      loc_14006851E
0x140068795  cmp     byte ptr [rcx+19h], 2
0x140068799  jb      loc_14006851E
0x14006879f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400687a4  mov     edx, 21h ; '!'
0x1400687a9  jmp     loc_140068500
0x1400687ae  mov     r9d, 1F0003h; dwDesiredAccess
0x1400687b4  xor     r8d, r8d; dwFlags
0x1400687b7  xor     edx, edx; lpTimerName
0x1400687b9  xor     ecx, ecx; lpTimerAttributes
0x1400687bb  call    cs:__imp_CreateWaitableTimerExW
0x1400687c1  mov     r13, rax
0x1400687c4  test    rax, rax
0x1400687c7  jnz     short loc_14006880A
0x1400687c9  call    cs:__imp_GetLastError
0x1400687cf  mov     edi, eax
0x1400687d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400687d8  lea     rax, WPP_GLOBAL_Control
0x1400687df  cmp     rcx, rax
0x1400687e2  jz      loc_14006851E
0x1400687e8  test    byte ptr [rcx+1Ch], 8
0x1400687ec  jz      loc_14006851E
0x1400687f2  cmp     byte ptr [rcx+19h], 2
0x1400687f6  jb      loc_14006851E
0x1400687fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140068801  lea     edx, [r13+22h]
0x140068805  jmp     loc_140068500
0x14006880a  mov     eax, cs:dword_140152118
0x140068810  cmp     eax, 5
0x140068813  jbe     short loc_140068848
0x140068815  mov     eax, [r14+104h]
0x14006881c  lea     rdx, word_14013F8CE
0x140068823  mov     [rbp+57h+var_B0], eax
0x140068826  lea     rax, aTryingToConnec; "Trying to connection using Conn Q Inter"...
0x14006882d  mov     [rbp+57h+var_A0], rax
0x140068831  lea     rax, [rbp+57h+var_B0]
0x140068835  mov     qword ptr [rsp+100h+fResume], rax
0x14006883a  lea     rax, [rbp+57h+var_A0]
0x14006883e  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x140068843  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140068848  mov     r8d, [r14+104h]; lPeriod
0x14006884f  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x140068853  mov     [rsp+100h+fResume], r12d; fResume
0x140068858  xor     r9d, r9d; pfnCompletionRoutine
0x14006885b  mov     rcx, r13; hTimer
0x14006885e  mov     [rsp+100h+lpArgToCompletionRoutine], r12; lpArgToCompletionRoutine
0x140068863  mov     qword ptr [rbp+57h+DueTime], r12
0x140068867  call    cs:__imp_SetWaitableTimer
0x14006886d  test    eax, eax
0x14006886f  jnz     short loc_1400688B3
0x140068871  call    cs:__imp_GetLastError
0x140068877  mov     edi, eax
0x140068879  mov     rcx, cs:WPP_GLOBAL_Control
0x140068880  lea     rax, WPP_GLOBAL_Control
0x140068887  cmp     rcx, rax
0x14006888a  jz      loc_14006851E
0x140068890  test    byte ptr [rcx+1Ch], 8
0x140068894  jz      loc_14006851E
0x14006889a  cmp     byte ptr [rcx+19h], 2
0x14006889e  jb      loc_14006851E
0x1400688a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400688a9  mov     edx, 23h ; '#'
0x1400688ae  jmp     loc_140068500
0x1400688b3  mov     rax, [r14+120h]
0x1400688ba  mov     rcx, r14; this
0x1400688bd  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400688c1  mov     qword ptr [rbp+57h+var_70], r13
0x1400688c5  call    ?CreatePendingConnection@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::CreatePendingConnection(void)
0x1400688ca  mov     edi, eax
0x1400688cc  test    eax, eax
0x1400688ce  js      loc_140068A44
0x1400688d4  mov     esi, 80004005h
0x1400688d9  lea     r15, aThreadproc; "ThreadProc"
0x1400688e0  lea     r12, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400688e7  cmp     edi, 1
0x1400688ea  jnz     loc_140068971
0x1400688f0  mov     rcx, r13; hTimer
0x1400688f3  call    cs:__imp_CancelWaitableTimer
0x1400688f9  mov     edx, [r14+13Ch]
0x140068900  test    edx, edx
  ... truncated ...
```
