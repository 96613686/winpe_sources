# CRDPENCONPendingConnectionContext::ReadData(void)

- ea: `0x180063d08`
- end: `0x18006440d`
- name: `?ReadData@CRDPENCONPendingConnectionContext@@QEAAJXZ`
- size: `1797`
- prototype: `__int64 __fastcall(CRDPENCONPendingConnectionContext *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001a990`
- `0x180048c2c`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180003158`
- `0x180004970`
- `0x18003e3d4`
- `0x180046a84`
- `0x180063d08`
- `0x1800721d4`
- `0x180072470`
- `0x1800787d4`

## import_xrefs

- `WS2_32!__imp_recv` at `0x180063d54`
- `WS2_32!__imp_recv` at `0x1800640b3`
- `WS2_32!__imp_recv` at `0x180063d54`
- `WS2_32!__imp_recv` at `0x1800640b3`
- `WS2_32!__imp_WSAGetLastError` at `0x180063de3`
- `WS2_32!__imp_WSAGetLastError` at `0x180064131`
- `WS2_32!__imp_WSAGetLastError` at `0x180063de3`
- `WS2_32!__imp_WSAGetLastError` at `0x180064131`

## string_xrefs

- `0x180063d6b`: `ReadData`
- `0x180063e4e`: `ReadData`
- `0x180063f52`: `ReadData`
- `0x1800640cc`: `ReadData`
- `0x180064192`: `ReadData`
- `0x180064255`: `ReadData`
- `0x18006431a`: `ReadData`
- `0x1800643dd`: `ReadData`
- `0x180063e02`: `Not enough bytes available to read (%d < %d)`
- `0x18006414d`: `Not enough bytes available to read (%d < %d)`
- `0x180063d8f`: `Read 0 bytes from the pending connection socket`
- `0x1800640f0`: `Read 0 bytes from the pending connection socket`
- `0x180063e72`: `Error reading from the pending connection socket`
- `0x1800641b6`: `Error reading from the pending connection socket`
- `0x18006420b`: `Got enough bytes for to complete the connection`

## pseudocode

```c
__int64 __fastcall CRDPENCONPendingConnectionContext::ReadData(CRDPENCONPendingConnectionContext *this)
{
  _DWORD *v1; // rdi
  int v3; // edi
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int *v7; // rdx
  const char **v8; // rax
  unsigned int v9; // ebx
  const char *v10; // rax
  __int64 *v11; // rdx
  __int16 *v13; // rdx
  const char **v14; // rax
  size_t v15; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v17; // rdx
  _DWORD *v18; // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  unsigned int v22; // esi
  int v23; // esi
  int v24; // eax
  unsigned int v25; // ecx
  char *v26; // rdx
  __int16 *v27; // rdx
  const char *v28; // rax
  __int64 v29; // rdx
  const char *v30; // [rsp+50h] [rbp-10h] BYREF
  const char *v31; // [rsp+58h] [rbp-8h] BYREF
  const char *v32; // [rsp+90h] [rbp+30h] BYREF
  int v33; // [rsp+98h] [rbp+38h] BYREF
  const char *v34; // [rsp+A0h] [rbp+40h] BYREF
  const char *v35; // [rsp+A8h] [rbp+48h] BYREF

  v1 = (_DWORD *)*((_QWORD *)this + 7);
  if ( !(unsigned int)RDPENCHLPWS_IsSocketInReadableState(*(_QWORD *)this) )
    return 1;
  if ( *((_DWORD *)this + 16) < 4u )
  {
    v3 = 4 - *((_DWORD *)this + 16);
    v4 = recv(*(_QWORD *)this, (char *)this + *((unsigned int *)this + 16) + 68, v3, 0);
    if ( !v4 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 92;
      v34 = "ReadData";
      v7 = (int *)byte_1801C5533;
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
      v30 = "Read 0 bytes from the pending connection socket";
      v8 = &v30;
LABEL_6:
      v33 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v4,
        (_DWORD)v7,
        v5,
        v6,
        (__int64)v8,
        (__int64)&v33,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v34);
      return (unsigned int)-2147467260;
    }
    if ( v4 == -1 )
    {
      if ( WSAGetLastError() == 10035 )
      {
        if ( (unsigned int)CallbackContext <= 4 )
          return 1;
        v33 = -1;
        v10 = "Not enough bytes available to read (%d < %d)";
        v11 = qword_1801C5578;
LABEL_12:
        v34 = v10;
        LODWORD(v32) = v3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v4,
          (_DWORD)v11,
          v5,
          v6,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32);
        return 1;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = 102;
        v34 = "ReadData";
        v13 = (__int16 *)byte_1801C5491;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v30 = "Error reading from the pending connection socket";
        v14 = &v30;
LABEL_17:
        v33 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v4,
          (_DWORD)v13,
          v5,
          v6,
          (__int64)v14,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v34);
        return (unsigned int)RDPENCHLPWSErr2Hr();
      }
      return (unsigned int)RDPENCHLPWSErr2Hr();
    }
    if ( v3 != v4 )
    {
      if ( (unsigned int)CallbackContext <= 4 )
        return 1;
      v33 = v4;
      v10 = "Not enough data for preconnection blob (%d < %d)";
      v11 = (__int64 *)byte_1801C5413;
      goto LABEL_12;
    }
    *((_DWORD *)this + 16) += v4;
    v15 = *((unsigned int *)this + 17);
    *((_DWORD *)this + 12) = v15;
    if ( (unsigned int)(v15 - 1) > 0xFFF )
    {
      v9 = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 10;
        goto LABEL_40;
      }
      return v9;
    }
    if ( (unsigned int)v15 <= 4 )
    {
      v9 = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 11;
LABEL_40:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
          CurrentThreadActivityIdPrefix,
          -2147024809);
        return v9;
      }
      return v9;
    }
    v18 = operator new(v15);
    *((_QWORD *)this + 7) = v18;
    v1 = v18;
    if ( !v18 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v31 = "OOM on allocating %d size pcb";
        v33 = 129;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)&word_1801C54D6,
          v20,
          v21,
          (__int64)&v31,
          (__int64)&v34,
          (__int64)&v30,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v32);
      }
      return (unsigned int)-2147024882;
    }
    *v18 = *((_DWORD *)this + 12);
    *((_DWORD *)this + 11) = 4;
  }
  v22 = *((_DWORD *)this + 12);
  if ( v22 > *((_DWORD *)this + 11) )
  {
    v23 = v22 - *((_DWORD *)this + 11);
    v24 = recv(*(_QWORD *)this, (char *)(*((_QWORD *)this + 7) + *((unsigned int *)this + 11)), v23, 0);
    if ( !v24 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 164;
      v34 = "ReadData";
      v7 = &dword_1801C544C;
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
      v31 = "Read 0 bytes from the pending connection socket";
      v8 = &v31;
      goto LABEL_6;
    }
    if ( v24 == -1 )
    {
      if ( WSAGetLastError() == 10035 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v32) = v23;
          v34 = "Not enough bytes available to read (%d < %d)";
          v33 = -1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v4,
            (unsigned int)byte_1801C5395,
            v5,
            v6,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32);
        }
        return 1;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = 172;
        v34 = "ReadData";
        v13 = &word_1801C53CE;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v31 = "Error reading from the pending connection socket";
        v14 = &v31;
        goto LABEL_17;
      }
      return (unsigned int)RDPENCHLPWSErr2Hr();
    }
    *((_DWORD *)this + 11) += v24;
    if ( v23 != v24 )
      return 1;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v32 = "Got enough bytes for to complete the connection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&byte_1801C5317,
        0,
        v6,
        (__int64)&v32);
    }
    v25 = *((_DWORD *)this + 12);
    if ( v25 < 0x10 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v30 = "PCB size too small %d";
        v33 = 187;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)qword_1801C5338,
          v5,
          v6,
          (__int64)&v30,
          (__int64)&v34,
          (__int64)&v31,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v32);
      }
      return (unsigned int)-2147418113;
    }
    *((_DWORD *)this + 20) = v1[3];
    if ( v25 == 16 )
    {
      if ( (unsigned int)CallbackContext <= 4 )
        return 0;
      v26 = byte_1801C52B1;
LABEL_62:
      v32 = "V1 PCB or no string in V2 PCB";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (_DWORD)v26,
        0,
        v6,
        (__int64)&v32);
      return 0;
    }
    if ( v25 >= 0x12 )
    {
      v29 = *((unsigned __int16 *)v1 + 8);
      if ( !(_WORD)v29 )
      {
        if ( (unsigned int)CallbackContext <= 4 )
          return 0;
        v26 = byte_1801C524B;
        goto LABEL_62;
      }
      if ( (unsigned int)(2 * v29) < 0xFFFFFFEE && 2 * (int)v29 + 18 <= (int)v25 )
      {
        *((_WORD *)v1 + v29 + 8) = 0;
        *((_QWORD *)this + 9) = (char *)v1 + 18;
        return 0;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = 227;
        v34 = "ReadData";
        v27 = (__int16 *)&dword_1801C526C;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v28 = "Overflow detected in PCB buffer";
        goto LABEL_67;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v32) = 205;
      v34 = "ReadData";
      v27 = word_1801C52D2;
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
      v28 = "Invalid size for V2 PCB";
LABEL_67:
      v31 = v28;
      v33 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v25,
        (_DWORD)v27,
        v5,
        v6,
        (__int64)&v31,
        (__int64)&v33,
        (__int64)&v35,
        (__int64)&v32,
        (__int64)&v34);
    }
    return (unsigned int)-2147418113;
  }
  v9 = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 12;
    goto LABEL_40;
  }
  return v9;
}

```

## disassembly

```asm
0x180063d08  push    rbp
0x180063d0a  push    rbx
0x180063d0b  push    rsi
0x180063d0c  push    rdi
0x180063d0d  push    r15
0x180063d0f  mov     rbp, rsp
0x180063d12  sub     rsp, 60h
0x180063d16  mov     rdi, [rcx+38h]
0x180063d1a  mov     rbx, rcx
0x180063d1d  mov     rcx, [rcx]; unsigned __int64
0x180063d20  call    ?RDPENCHLPWS_IsSocketInReadableState@@YAH_K@Z; RDPENCHLPWS_IsSocketInReadableState(unsigned __int64)
0x180063d25  xor     r15d, r15d
0x180063d28  test    eax, eax
0x180063d2a  jz      loc_180063E37
0x180063d30  cmp     dword ptr [rbx+40h], 4
0x180063d34  jnb     loc_180063FD2
0x180063d3a  mov     edx, [rbx+40h]
0x180063d3d  lea     edi, [r15+4]
0x180063d41  sub     edi, [rbx+40h]
0x180063d44  add     rdx, 44h ; 'D'
0x180063d48  mov     rcx, [rbx]; s
0x180063d4b  add     rdx, rbx; buf
0x180063d4e  mov     r8d, edi; len
0x180063d51  xor     r9d, r9d; flags
0x180063d54  call    cs:__imp_recv
0x180063d5a  mov     ecx, eax
0x180063d5c  test    eax, eax
0x180063d5e  jnz     short loc_180063DDA
0x180063d60  mov     eax, cs:CallbackContext
0x180063d66  cmp     eax, 2
0x180063d69  jbe     short loc_180063DD3
0x180063d6b  lea     rax, aReaddata; "ReadData"
0x180063d72  mov     dword ptr [rbp+arg_0], 5Ch ; '\'
0x180063d79  mov     [rbp+arg_10], rax
0x180063d7d  lea     rdx, byte_1801C5533
0x180063d84  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180063d8b  mov     [rbp+arg_18], rax
0x180063d8f  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x180063d96  mov     [rbp+var_10], rax
0x180063d9a  lea     rax, [rbp+arg_10]
0x180063d9e  mov     [rsp+60h+var_20], rax
0x180063da3  lea     rax, [rbp+arg_0]
0x180063da7  mov     [rsp+60h+var_28], rax
0x180063dac  lea     rax, [rbp+arg_18]
0x180063db0  mov     [rsp+60h+var_30], rax
0x180063db5  lea     rax, [rbp+arg_8]
0x180063db9  mov     [rsp+60h+var_38], rax
0x180063dbe  lea     rax, [rbp+var_10]
0x180063dc2  mov     [rsp+60h+var_40], rax
0x180063dc7  mov     [rbp+arg_8], 80004005h
0x180063dce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063dd3  mov     ebx, 80004004h
0x180063dd8  jmp     short loc_180063E3C
0x180063dda  cmp     ecx, 0FFFFFFFFh
0x180063ddd  jnz     loc_180063EC2
0x180063de3  call    cs:__imp_WSAGetLastError
0x180063de9  cmp     eax, 2733h
0x180063dee  mov     eax, cs:CallbackContext
0x180063df4  jnz     short loc_180063E49
0x180063df6  cmp     eax, 4
0x180063df9  jbe     short loc_180063E37
0x180063dfb  mov     [rbp+arg_8], 0FFFFFFFFh
0x180063e02  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x180063e09  lea     rdx, qword_1801C5578
0x180063e10  mov     [rbp+arg_10], rax
0x180063e14  lea     rax, [rbp+arg_0]
0x180063e18  mov     [rsp+60h+var_30], rax
0x180063e1d  lea     rax, [rbp+arg_8]
0x180063e21  mov     [rsp+60h+var_38], rax
0x180063e26  lea     rax, [rbp+arg_10]
0x180063e2a  mov     [rsp+60h+var_40], rax
0x180063e2f  mov     dword ptr [rbp+arg_0], edi
0x180063e32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180063e37  mov     ebx, 1
0x180063e3c  mov     eax, ebx
0x180063e3e  add     rsp, 60h
0x180063e42  pop     r15
0x180063e44  pop     rdi
0x180063e45  pop     rsi
0x180063e46  pop     rbx
0x180063e47  pop     rbp
0x180063e48  retn
0x180063e49  cmp     eax, 2
0x180063e4c  jbe     short loc_180063EB6
0x180063e4e  lea     rax, aReaddata; "ReadData"
0x180063e55  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x180063e5c  mov     [rbp+arg_10], rax
0x180063e60  lea     rdx, byte_1801C5491
0x180063e67  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180063e6e  mov     [rbp+arg_18], rax
0x180063e72  lea     rax, aErrorReadingFr_0; "Error reading from the pending connecti"...
0x180063e79  mov     [rbp+var_10], rax
0x180063e7d  lea     rax, [rbp+arg_10]
0x180063e81  mov     [rsp+60h+var_20], rax
0x180063e86  lea     rax, [rbp+arg_0]
0x180063e8a  mov     [rsp+60h+var_28], rax
0x180063e8f  lea     rax, [rbp+arg_18]
0x180063e93  mov     [rsp+60h+var_30], rax
0x180063e98  lea     rax, [rbp+arg_8]
0x180063e9c  mov     [rsp+60h+var_38], rax
0x180063ea1  lea     rax, [rbp+var_10]
0x180063ea5  mov     [rsp+60h+var_40], rax
0x180063eaa  mov     [rbp+arg_8], 80004005h
0x180063eb1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063eb6  call    RDPENCHLPWSErr2Hr
0x180063ebb  mov     ebx, eax
0x180063ebd  jmp     loc_180063E3C
0x180063ec2  cmp     edi, ecx
0x180063ec4  jnz     loc_18006407B
0x180063eca  add     [rbx+40h], ecx
0x180063ecd  mov     ecx, [rbx+44h]; Size
0x180063ed0  mov     [rbx+30h], ecx
0x180063ed3  lea     eax, [rcx-1]
0x180063ed6  cmp     eax, 0FFFh
0x180063edb  ja      loc_18006401A
0x180063ee1  cmp     ecx, 4
0x180063ee4  ja      short loc_180063F25
0x180063ee6  mov     ebx, 80070057h
0x180063eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ef2  lea     rax, WPP_GLOBAL_Control
0x180063ef9  cmp     rcx, rax
0x180063efc  jz      loc_180063E3C
0x180063f02  test    byte ptr [rcx+1Ch], 1
0x180063f06  jz      loc_180063E3C
0x180063f0c  cmp     byte ptr [rcx+19h], 2
0x180063f10  jb      loc_180063E3C
0x180063f16  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063f1b  mov     edx, 0Bh
0x180063f20  jmp     loc_180064054
0x180063f25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063f2a  mov     [rbx+38h], rax
0x180063f2e  mov     rdi, rax
0x180063f31  test    rax, rax
0x180063f34  jnz     loc_180063FC6
0x180063f3a  mov     eax, cs:CallbackContext
0x180063f40  cmp     eax, 2
0x180063f43  jbe     short loc_180063FBC
0x180063f45  mov     eax, [rbx+30h]
0x180063f48  lea     rdx, word_1801C54D6
0x180063f4f  mov     dword ptr [rbp+arg_0], eax
0x180063f52  lea     rax, aReaddata; "ReadData"
0x180063f59  mov     [rbp+arg_18], rax
0x180063f5d  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180063f64  mov     [rbp+var_10], rax
0x180063f68  lea     rax, aOomOnAllocatin; "OOM on allocating %d size pcb"
0x180063f6f  mov     [rbp+var_8], rax
0x180063f73  lea     rax, [rbp+arg_0]
0x180063f77  mov     [rsp+60h+var_18], rax
0x180063f7c  lea     rax, [rbp+arg_18]
0x180063f80  mov     [rsp+60h+var_20], rax
0x180063f85  lea     rax, [rbp+arg_8]
0x180063f89  mov     [rsp+60h+var_28], rax
0x180063f8e  lea     rax, [rbp+var_10]
0x180063f92  mov     [rsp+60h+var_30], rax
0x180063f97  lea     rax, [rbp+arg_10]
0x180063f9b  mov     [rsp+60h+var_38], rax
0x180063fa0  lea     rax, [rbp+var_8]
0x180063fa4  mov     [rsp+60h+var_40], rax
0x180063fa9  mov     [rbp+arg_8], 81h
0x180063fb0  mov     dword ptr [rbp+arg_10], 80004005h
0x180063fb7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180063fbc  mov     ebx, 8007000Eh
0x180063fc1  jmp     loc_180063E3C
0x180063fc6  mov     eax, [rbx+30h]
0x180063fc9  mov     [rdi], eax
0x180063fcb  mov     dword ptr [rbx+2Ch], 4
0x180063fd2  mov     esi, [rbx+30h]
0x180063fd5  cmp     esi, [rbx+2Ch]
0x180063fd8  ja      loc_1800640A0
0x180063fde  mov     ebx, 80070057h
0x180063fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180063fea  lea     rax, WPP_GLOBAL_Control
0x180063ff1  cmp     rcx, rax
0x180063ff4  jz      loc_180063E3C
0x180063ffa  test    byte ptr [rcx+1Ch], 1
0x180063ffe  jz      loc_180063E3C
0x180064004  cmp     byte ptr [rcx+19h], 2
0x180064008  jb      loc_180063E3C
0x18006400e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180064013  mov     edx, 0Ch
0x180064018  jmp     short loc_180064054
0x18006401a  mov     ebx, 80070057h
0x18006401f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064026  lea     rax, WPP_GLOBAL_Control
0x18006402d  cmp     rcx, rax
0x180064030  jz      loc_180063E3C
0x180064036  test    byte ptr [rcx+1Ch], 1
0x18006403a  jz      loc_180063E3C
0x180064040  cmp     byte ptr [rcx+19h], 2
0x180064044  jb      loc_180063E3C
0x18006404a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006404f  mov     edx, 0Ah
0x180064054  mov     rcx, cs:WPP_GLOBAL_Control
0x18006405b  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x180064062  mov     r9d, eax
0x180064065  mov     dword ptr [rsp+60h+var_40], 80070057h
0x18006406d  mov     rcx, [rcx+10h]
0x180064071  call    WPP_SF_Dd
0x180064076  jmp     loc_180063E3C
0x18006407b  mov     eax, cs:CallbackContext
0x180064081  cmp     eax, 4
0x180064084  jbe     loc_180063E37
0x18006408a  mov     [rbp+arg_8], ecx
0x18006408d  lea     rax, aNotEnoughDataF; "Not enough data for preconnection blob "...
0x180064094  lea     rdx, byte_1801C5413
0x18006409b  jmp     loc_180063E10
0x1800640a0  sub     esi, [rbx+2Ch]
0x1800640a3  xor     r9d, r9d; flags
0x1800640a6  mov     edx, [rbx+2Ch]
0x1800640a9  mov     r8d, esi; len
0x1800640ac  add     rdx, [rbx+38h]; buf
0x1800640b0  mov     rcx, [rbx]; s
0x1800640b3  call    cs:__imp_recv
0x1800640b9  test    eax, eax
0x1800640bb  jnz     short loc_180064128
0x1800640bd  mov     eax, cs:CallbackContext
0x1800640c3  cmp     eax, 2
0x1800640c6  jbe     loc_180063DD3
0x1800640cc  lea     rax, aReaddata; "ReadData"
0x1800640d3  mov     dword ptr [rbp+arg_0], 0A4h
0x1800640da  mov     [rbp+arg_10], rax
0x1800640de  lea     rdx, dword_1801C544C
0x1800640e5  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800640ec  mov     [rbp+arg_18], rax
0x1800640f0  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x1800640f7  mov     [rbp+var_8], rax
0x1800640fb  lea     rax, [rbp+arg_10]
0x1800640ff  mov     [rsp+60h+var_20], rax
0x180064104  lea     rax, [rbp+arg_0]
0x180064108  mov     [rsp+60h+var_28], rax
0x18006410d  lea     rax, [rbp+arg_18]
0x180064111  mov     [rsp+60h+var_30], rax
0x180064116  lea     rax, [rbp+arg_8]
0x18006411a  mov     [rsp+60h+var_38], rax
0x18006411f  lea     rax, [rbp+var_8]
0x180064123  jmp     loc_180063DC2
0x180064128  cmp     eax, 0FFFFFFFFh
0x18006412b  jnz     loc_1800641EE
0x180064131  call    cs:__imp_WSAGetLastError
0x180064137  cmp     eax, 2733h
0x18006413c  mov     eax, cs:CallbackContext
0x180064142  jnz     short loc_180064189
0x180064144  cmp     eax, 4
0x180064147  jbe     loc_180063E37
0x18006414d  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x180064154  mov     dword ptr [rbp+arg_0], esi
0x180064157  mov     [rbp+arg_10], rax
0x18006415b  lea     rdx, byte_1801C5395
0x180064162  lea     rax, [rbp+arg_0]
0x180064166  mov     [rbp+arg_8], 0FFFFFFFFh
0x18006416d  mov     [rsp+60h+var_30], rax
0x180064172  lea     rax, [rbp+arg_8]
0x180064176  mov     [rsp+60h+var_38], rax
0x18006417b  lea     rax, [rbp+arg_10]
0x18006417f  mov     [rsp+60h+var_40], rax
0x180064184  jmp     loc_180063E32
0x180064189  cmp     eax, 2
0x18006418c  jbe     loc_180063EB6
0x180064192  lea     rax, aReaddata; "ReadData"
0x180064199  mov     dword ptr [rbp+arg_0], 0ACh
0x1800641a0  mov     [rbp+arg_10], rax
0x1800641a4  lea     rdx, word_1801C53CE
0x1800641ab  lea     rax, aOnecoreTermsrv_16; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800641b2  mov     [rbp+arg_18], rax
0x1800641b6  lea     rax, aErrorReadingFr_0; "Error reading from the pending connecti"...
0x1800641bd  mov     [rbp+var_8], rax
0x1800641c1  lea     rax, [rbp+arg_10]
0x1800641c5  mov     [rsp+60h+var_20], rax
0x1800641ca  lea     rax, [rbp+arg_0]
0x1800641ce  mov     [rsp+60h+var_28], rax
0x1800641d3  lea     rax, [rbp+arg_18]
0x1800641d7  mov     [rsp+60h+var_30], rax
0x1800641dc  lea     rax, [rbp+arg_8]
0x1800641e0  mov     [rsp+60h+var_38], rax
0x1800641e5  lea     rax, [rbp+var_8]
0x1800641e9  jmp     loc_180063EA5
0x1800641ee  add     [rbx+2Ch], eax
0x1800641f1  cmp     esi, eax
0x1800641f3  jnz     loc_180063E37
0x1800641f9  mov     eax, cs:CallbackContext
0x1800641ff  lea     rsi, CallbackContext
0x180064206  cmp     eax, 4
0x180064209  jbe     short loc_180064231
0x18006420b  lea     rax, aGotEnoughBytes; "Got enough bytes for to complete the co"...
0x180064212  xor     r8d, r8d
0x180064215  mov     [rbp+arg_0], rax
0x180064219  lea     rdx, byte_1801C5317
0x180064220  lea     rax, [rbp+arg_0]
0x180064224  mov     rcx, rsi
0x180064227  mov     [rsp+60h+var_40], rax
0x18006422c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064231  mov     ecx, [rbx+30h]
0x180064234  cmp     ecx, 10h
0x180064237  jnb     loc_1800642C9
0x18006423d  mov     eax, cs:CallbackContext
0x180064243  cmp     eax, 2
0x180064246  jbe     short loc_1800642BF
0x180064248  mov     eax, [rbx+30h]
0x18006424b  lea     rdx, qword_1801C5338
0x180064252  mov     dword ptr [rbp+arg_0], eax
  ... truncated ...
```
