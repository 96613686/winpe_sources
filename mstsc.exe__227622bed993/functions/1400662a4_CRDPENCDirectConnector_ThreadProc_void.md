# CRDPENCDirectConnector::ThreadProc(void)

- ea: `0x1400662a4`
- end: `0x140066aae`
- name: `?ThreadProc@CRDPENCDirectConnector@@IEAAXXZ`
- size: `2058`
- prototype: `void __fastcall(CRDPENCDirectConnector *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400660b0`

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
- `0x14003c0f0`
- `0x140065028`
- `0x1400653d4`
- `0x140065478`
- `0x14006585c`
- `0x140065adc`
- `0x1400662a4`
- `0x140072490`
- `0x140072a7c`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!CancelWaitableTimer` at `0x140066783`
- `KERNEL32!CancelWaitableTimer` at `0x140066783`
- `KERNEL32!SetWaitableTimer` at `0x1400666f7`
- `KERNEL32!SetWaitableTimer` at `0x1400666f7`
- `KERNEL32!CreateWaitableTimerExW` at `0x14006664b`
- `KERNEL32!CreateWaitableTimerExW` at `0x14006664b`
- `KERNEL32!CreateEventW` at `0x14006634d`
- `KERNEL32!CreateEventW` at `0x1400665ea`
- `KERNEL32!CreateEventW` at `0x14006634d`
- `KERNEL32!CreateEventW` at `0x1400665ea`
- `KERNEL32!CloseHandle` at `0x140066937`
- `KERNEL32!CloseHandle` at `0x140066937`
- `KERNEL32!GetLastError` at `0x14006635f`
- `KERNEL32!GetLastError` at `0x1400665fc`
- `KERNEL32!GetLastError` at `0x140066659`
- `KERNEL32!GetLastError` at `0x140066701`
- `KERNEL32!GetLastError` at `0x14006635f`
- `KERNEL32!GetLastError` at `0x1400665fc`
- `KERNEL32!GetLastError` at `0x140066659`
- `KERNEL32!GetLastError` at `0x140066701`
- `ADVAPI32!EventActivityIdControl` at `0x140066300`
- `ADVAPI32!EventActivityIdControl` at `0x140066978`
- `ADVAPI32!EventActivityIdControl` at `0x140066300`
- `ADVAPI32!EventActivityIdControl` at `0x140066978`

## string_xrefs

- `0x140066a23`: `Failed to complete the connection`
- `0x140066495`: `ThreadProc`
- `0x140066769`: `ThreadProc`
- `0x1400668fd`: `Failed to create a new connection`

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
      if ( (unsigned int)dword_140150118 > 5 )
      {
        v38 = *((_DWORD *)this + 65);
        v41 = "Trying to connection using Conn Q Interval: %d";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)&word_14013D796,
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
        if ( (unsigned int)dword_140150118 > 2 )
        {
          v41 = "ThreadProc";
          v46 = "Trying the next connector";
          v38 = 623;
          v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
          v39 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v35,
            (unsigned int)&word_14013D666,
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
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v39 = 523;
      v41 = "Failed to resolve any IPS";
      v43 = (unsigned __int64)"ThreadProc";
      v44 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencdcon.cpp";
      v38 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)byte_14013D751,
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
0x1400662a4  push    rbp
0x1400662a6  push    rbx
0x1400662a7  push    rsi
0x1400662a8  push    rdi
0x1400662a9  push    r12
0x1400662ab  push    r13
0x1400662ad  push    r14
0x1400662af  push    r15
0x1400662b1  lea     rbp, [rsp-1Fh]
0x1400662b6  sub     rsp, 0C8h
0x1400662bd  mov     rax, cs:__security_cookie
0x1400662c4  xor     rax, rsp
0x1400662c7  mov     [rbp+57h+var_50], rax
0x1400662cb  xor     r12d, r12d
0x1400662ce  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400662d2  xorps   xmm0, xmm0
0x1400662d5  mov     [rbp+57h+var_A8], r12d
0x1400662d9  movups  [rbp+57h+var_70], xmm0
0x1400662dd  mov     r14, rcx
0x1400662e0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400662e4  movups  xmm0, xmmword ptr [rcx+0F4h]
0x1400662eb  lea     ecx, [r12+4]; ControlCode
0x1400662f0  mov     qword ptr [rbp+57h+DueTime], r12
0x1400662f4  mov     r13d, r12d
0x1400662f7  mov     [rbp+57h+var_90], r15
0x1400662fb  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x140066300  call    cs:__imp_EventActivityIdControl
0x140066306  mov     rcx, [r14+0D8h]
0x14006630d  mov     ebx, r12d
0x140066310  mov     [rbp+57h+var_98], rbx
0x140066314  mov     rax, [rcx]
0x140066317  mov     rax, [rax+40h]
0x14006631b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140066320  mov     rdi, rax
0x140066323  test    rax, rax
0x140066326  jz      short loc_140066341
0x140066328  lea     rcx, [rbp+57h+var_98]
0x14006632c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x140066331  mov     rbx, rdi
0x140066334  lea     rcx, [rbp+57h+var_98]
0x140066338  mov     [rbp+57h+var_98], rbx
0x14006633c  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x140066341  xor     r9d, r9d; lpName
0x140066344  xor     r8d, r8d; bInitialState
0x140066347  xor     ecx, ecx; lpEventAttributes
0x140066349  lea     edx, [r9+1]; bManualReset
0x14006634d  call    cs:__imp_CreateEventW
0x140066353  mov     [r14+128h], rax
0x14006635a  test    rax, rax
0x14006635d  jnz     short loc_1400663CA
0x14006635f  call    cs:__imp_GetLastError
0x140066365  mov     edi, eax
0x140066367  mov     rcx, cs:WPP_GLOBAL_Control
0x14006636e  lea     rax, WPP_GLOBAL_Control
0x140066375  cmp     rcx, rax
0x140066378  jz      short loc_1400663AE
0x14006637a  test    byte ptr [rcx+1Ch], 8
0x14006637e  jz      short loc_1400663AE
0x140066380  cmp     byte ptr [rcx+19h], 2
0x140066384  jb      short loc_1400663AE
0x140066386  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006638b  mov     edx, 1Dh
0x140066390  mov     rcx, cs:WPP_GLOBAL_Control
0x140066397  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006639e  mov     r9d, eax
0x1400663a1  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], edi
0x1400663a5  mov     rcx, [rcx+10h]
0x1400663a9  call    WPP_SF_Dd
0x1400663ae  test    edi, edi
0x1400663b0  jle     short loc_1400663BB
0x1400663b2  movzx   edi, di
0x1400663b5  or      edi, 80070000h
0x1400663bb  test    edi, edi
0x1400663bd  mov     esi, 80004005h
0x1400663c2  cmovns  edi, esi
0x1400663c5  jmp     loc_140066927
0x1400663ca  mov     rcx, r14; this
0x1400663cd  call    ?AsyncResolveServerName@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::AsyncResolveServerName(void)
0x1400663d2  mov     edi, eax
0x1400663d4  test    eax, eax
0x1400663d6  jns     short loc_140066419
0x1400663d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400663df  lea     rax, WPP_GLOBAL_Control
0x1400663e6  cmp     rcx, rax
0x1400663e9  jz      loc_140066927
0x1400663ef  test    byte ptr [rcx+1Ch], 8
0x1400663f3  jz      loc_140066927
0x1400663f9  cmp     byte ptr [rcx+19h], 2
0x1400663fd  jb      loc_140066927
0x140066403  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066408  mov     edx, 1Eh
0x14006640d  lea     rcx, aFailedToResolv; "Failed to resolve server name asynchron"...
0x140066414  jmp     loc_140066904
0x140066419  lea     rcx, [r14+38h]; this
0x14006641d  call    ?SortAddresses@CRDPENCONResolver@@QEAAJXZ; CRDPENCONResolver::SortAddresses(void)
0x140066422  mov     edi, eax
0x140066424  test    eax, eax
0x140066426  jns     short loc_140066469
0x140066428  mov     rcx, cs:WPP_GLOBAL_Control
0x14006642f  lea     rax, WPP_GLOBAL_Control
0x140066436  cmp     rcx, rax
0x140066439  jz      loc_140066927
0x14006643f  test    byte ptr [rcx+1Ch], 8
0x140066443  jz      loc_140066927
0x140066449  cmp     byte ptr [rcx+19h], 2
0x14006644d  jb      loc_140066927
0x140066453  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066458  mov     edx, 1Fh
0x14006645d  lea     rcx, aFailedToSortTh; "Failed to sort the address list"
0x140066464  jmp     loc_140066904
0x140066469  lea     rcx, [r14+38h]; this
0x14006646d  call    ?StartEnum@CRDPENCONResolver@@QEAAIXZ; CRDPENCONResolver::StartEnum(void)
0x140066472  mov     edi, eax
0x140066474  test    eax, eax
0x140066476  jnz     short loc_1400664F6
0x140066478  mov     eax, cs:dword_140150118
0x14006647e  cmp     eax, 2
0x140066481  jbe     short loc_1400664EC
0x140066483  lea     rax, aFailedToResolv_0; "Failed to resolve any IPS"
0x14006648a  mov     [rbp+57h+var_AC], 20Bh
0x140066491  mov     [rbp+57h+var_A0], rax
0x140066495  lea     r15, aThreadproc; "ThreadProc"
0x14006649c  lea     rax, [rbp+57h+var_90]
0x1400664a0  mov     [rbp+57h+var_90], r15
0x1400664a4  mov     [rsp+100h+var_C0], rax
0x1400664a9  lea     r12, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1400664b0  lea     rax, [rbp+57h+var_AC]
0x1400664b4  mov     [rbp+57h+var_88], r12
0x1400664b8  mov     [rsp+100h+var_C8], rax
0x1400664bd  lea     rdx, byte_14013D751
0x1400664c4  lea     rax, [rbp+57h+var_88]
0x1400664c8  mov     esi, 80004005h
0x1400664cd  mov     [rsp+100h+var_D0], rax
0x1400664d2  lea     rax, [rbp+57h+var_B0]
0x1400664d6  mov     qword ptr [rsp+100h+fResume], rax
0x1400664db  lea     rax, [rbp+57h+var_A0]
0x1400664df  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1400664e4  mov     [rbp+57h+var_B0], esi
0x1400664e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400664ec  mov     edi, 83452206h
0x1400664f1  jmp     loc_140066927
0x1400664f6  mov     eax, 8
0x1400664fb  mul     rdi
0x1400664fe  cmovb   rax, r15
0x140066502  mov     rcx, rax; Size
0x140066505  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006650a  lea     rsi, [r14+130h]
0x140066511  mov     r9, rax
0x140066514  mov     [rsi], rax
0x140066517  test    rax, rax
0x14006651a  jnz     short loc_140066571
0x14006651c  mov     rcx, cs:WPP_GLOBAL_Control
0x140066523  lea     rax, WPP_GLOBAL_Control
0x14006652a  cmp     rcx, rax
0x14006652d  jz      short loc_140066567
0x14006652f  test    byte ptr [rcx+1Ch], 8
0x140066533  jz      short loc_140066567
0x140066535  cmp     byte ptr [rcx+19h], 2
0x140066539  jb      short loc_140066567
0x14006653b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066540  mov     rcx, cs:WPP_GLOBAL_Control
0x140066547  lea     r8, WPP_68089e09a916383f9d73b52f9d59fc60_Traceguids
0x14006654e  mov     edx, 20h ; ' '
0x140066553  mov     dword ptr [rsp+100h+lpArgToCompletionRoutine], 8007000Eh
0x14006655b  mov     r9d, eax
0x14006655e  mov     rcx, [rcx+10h]
0x140066562  call    WPP_SF_Dd
0x140066567  mov     edi, 8007000Eh
0x14006656c  jmp     loc_140066927
0x140066571  test    edi, edi
0x140066573  jz      short loc_1400665D2
0x140066575  mov     edx, r12d
0x140066578  cmp     edi, 2
0x14006657b  jb      short loc_1400665C3
0x14006657d  cmp     r9, rsi
0x140066580  ja      short loc_14006658E
0x140066582  lea     eax, [rdi-1]
0x140066585  lea     rax, [r9+rax*8]
0x140066589  cmp     rax, rsi
0x14006658c  jnb     short loc_1400665C3
0x14006658e  mov     eax, edi
0x140066590  and     eax, 0FFFFFFFEh
0x140066593  add     edx, 2
0x140066596  mov     r15d, edx
0x140066599  cmp     edx, eax
0x14006659b  jb      short loc_140066593
0x14006659d  mov     r8d, eax
0x1400665a0  or      rdx, 0FFFFFFFFFFFFFFFFh; Val
0x1400665a4  shr     r8, 1
0x1400665a7  mov     rcx, r9; void *
0x1400665aa  shl     r8, 4
0x1400665ae  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1400665b2  call    memset_0
0x1400665b7  mov     edx, r15d
0x1400665ba  cmp     r15d, edi
0x1400665bd  jnb     short loc_1400665D2
0x1400665bf  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400665c3  mov     rax, [rsi]
0x1400665c6  mov     ecx, edx
0x1400665c8  inc     edx
0x1400665ca  mov     [rax+rcx*8], r15
0x1400665ce  cmp     edx, edi
0x1400665d0  jb      short loc_1400665C3
0x1400665d2  xor     r9d, r9d; lpName
0x1400665d5  mov     [r14+138h], edi
0x1400665dc  xor     r8d, r8d; bInitialState
0x1400665df  mov     [r14+13Ch], r12d
0x1400665e6  xor     edx, edx; bManualReset
0x1400665e8  xor     ecx, ecx; lpEventAttributes
0x1400665ea  call    cs:__imp_CreateEventW
0x1400665f0  mov     [r14+120h], rax
0x1400665f7  test    rax, rax
0x1400665fa  jnz     short loc_14006663E
0x1400665fc  call    cs:__imp_GetLastError
0x140066602  mov     edi, eax
0x140066604  mov     rcx, cs:WPP_GLOBAL_Control
0x14006660b  lea     rax, WPP_GLOBAL_Control
0x140066612  cmp     rcx, rax
0x140066615  jz      loc_1400663AE
0x14006661b  test    byte ptr [rcx+1Ch], 8
0x14006661f  jz      loc_1400663AE
0x140066625  cmp     byte ptr [rcx+19h], 2
0x140066629  jb      loc_1400663AE
0x14006662f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066634  mov     edx, 21h ; '!'
0x140066639  jmp     loc_140066390
0x14006663e  mov     r9d, 1F0003h; dwDesiredAccess
0x140066644  xor     r8d, r8d; dwFlags
0x140066647  xor     edx, edx; lpTimerName
0x140066649  xor     ecx, ecx; lpTimerAttributes
0x14006664b  call    cs:__imp_CreateWaitableTimerExW
0x140066651  mov     r13, rax
0x140066654  test    rax, rax
0x140066657  jnz     short loc_14006669A
0x140066659  call    cs:__imp_GetLastError
0x14006665f  mov     edi, eax
0x140066661  mov     rcx, cs:WPP_GLOBAL_Control
0x140066668  lea     rax, WPP_GLOBAL_Control
0x14006666f  cmp     rcx, rax
0x140066672  jz      loc_1400663AE
0x140066678  test    byte ptr [rcx+1Ch], 8
0x14006667c  jz      loc_1400663AE
0x140066682  cmp     byte ptr [rcx+19h], 2
0x140066686  jb      loc_1400663AE
0x14006668c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066691  lea     edx, [r13+22h]
0x140066695  jmp     loc_140066390
0x14006669a  mov     eax, cs:dword_140150118
0x1400666a0  cmp     eax, 5
0x1400666a3  jbe     short loc_1400666D8
0x1400666a5  mov     eax, [r14+104h]
0x1400666ac  lea     rdx, word_14013D796
0x1400666b3  mov     [rbp+57h+var_B0], eax
0x1400666b6  lea     rax, aTryingToConnec; "Trying to connection using Conn Q Inter"...
0x1400666bd  mov     [rbp+57h+var_A0], rax
0x1400666c1  lea     rax, [rbp+57h+var_B0]
0x1400666c5  mov     qword ptr [rsp+100h+fResume], rax
0x1400666ca  lea     rax, [rbp+57h+var_A0]
0x1400666ce  mov     [rsp+100h+lpArgToCompletionRoutine], rax
0x1400666d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400666d8  mov     r8d, [r14+104h]; lPeriod
0x1400666df  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x1400666e3  mov     [rsp+100h+fResume], r12d; fResume
0x1400666e8  xor     r9d, r9d; pfnCompletionRoutine
0x1400666eb  mov     rcx, r13; hTimer
0x1400666ee  mov     [rsp+100h+lpArgToCompletionRoutine], r12; lpArgToCompletionRoutine
0x1400666f3  mov     qword ptr [rbp+57h+DueTime], r12
0x1400666f7  call    cs:__imp_SetWaitableTimer
0x1400666fd  test    eax, eax
0x1400666ff  jnz     short loc_140066743
0x140066701  call    cs:__imp_GetLastError
0x140066707  mov     edi, eax
0x140066709  mov     rcx, cs:WPP_GLOBAL_Control
0x140066710  lea     rax, WPP_GLOBAL_Control
0x140066717  cmp     rcx, rax
0x14006671a  jz      loc_1400663AE
0x140066720  test    byte ptr [rcx+1Ch], 8
0x140066724  jz      loc_1400663AE
0x14006672a  cmp     byte ptr [rcx+19h], 2
0x14006672e  jb      loc_1400663AE
0x140066734  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140066739  mov     edx, 23h ; '#'
0x14006673e  jmp     loc_140066390
0x140066743  mov     rax, [r14+120h]
0x14006674a  mov     rcx, r14; this
0x14006674d  mov     qword ptr [rbp+57h+var_70+8], rax
0x140066751  mov     qword ptr [rbp+57h+var_70], r13
0x140066755  call    ?CreatePendingConnection@CRDPENCDirectConnector@@IEAAJXZ; CRDPENCDirectConnector::CreatePendingConnection(void)
0x14006675a  mov     edi, eax
0x14006675c  test    eax, eax
0x14006675e  js      loc_1400668D4
0x140066764  mov     esi, 80004005h
0x140066769  lea     r15, aThreadproc; "ThreadProc"
0x140066770  lea     r12, aOnecoreTermsrv_14; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x140066777  cmp     edi, 1
0x14006677a  jnz     loc_140066801
0x140066780  mov     rcx, r13; hTimer
0x140066783  call    cs:__imp_CancelWaitableTimer
0x140066789  mov     edx, [r14+13Ch]
0x140066790  test    edx, edx
  ... truncated ...
```
