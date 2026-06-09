# CRDPENCONPendingConnectionContext::ReadData(void)

- ea: `0x14006d354`
- end: `0x14006da53`
- name: `?ReadData@CRDPENCONPendingConnectionContext@@QEAAJXZ`
- size: `1791`
- prototype: `__int64 __fastcall(CRDPENCONPendingConnectionContext *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14006d14c`
- `0x14006d22c`

## callees

- `0x140001010`
- `0x1400019e8`
- `0x140001b00`
- `0x140001fbc`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14006d2c8`
- `0x14006d354`
- `0x140090d34`

## import_xrefs

- `WS2_32!__imp_recv` at `0x14006d3a0`
- `WS2_32!__imp_recv` at `0x14006d6ff`
- `WS2_32!__imp_recv` at `0x14006d3a0`
- `WS2_32!__imp_recv` at `0x14006d6ff`
- `WS2_32!__imp_WSAGetLastError` at `0x14006d42f`
- `WS2_32!__imp_WSAGetLastError` at `0x14006d77d`
- `WS2_32!__imp_WSAGetLastError` at `0x14006d42f`
- `WS2_32!__imp_WSAGetLastError` at `0x14006d77d`

## string_xrefs

- `0x14006d3b7`: `ReadData`
- `0x14006d49a`: `ReadData`
- `0x14006d59e`: `ReadData`
- `0x14006d718`: `ReadData`
- `0x14006d7de`: `ReadData`
- `0x14006d89e`: `ReadData`
- `0x14006d960`: `ReadData`
- `0x14006da23`: `ReadData`
- `0x14006d857`: `Got enough bytes for to complete the connection`
- `0x14006d3db`: `Read 0 bytes from the pending connection socket`
- `0x14006d73c`: `Read 0 bytes from the pending connection socket`
- `0x14006d44e`: `Not enough bytes available to read (%d < %d)`
- `0x14006d799`: `Not enough bytes available to read (%d < %d)`
- `0x14006d4be`: `Error reading from the pending connection socket`
- `0x14006d802`: `Error reading from the pending connection socket`

## pseudocode

```c
__int64 __fastcall CRDPENCONPendingConnectionContext::ReadData(CRDPENCONPendingConnectionContext *this)
{
  _DWORD *v1; // rdi
  int v3; // edi
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  __int64 *v7; // rdx
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
  __int16 *v26; // rdx
  char *v27; // rdx
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
      if ( (unsigned int)dword_140152118 <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 92;
      v34 = "ReadData";
      v7 = qword_1401402E0;
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
        if ( (unsigned int)dword_140152118 <= 4 )
          return 1;
        v33 = -1;
        v10 = "Not enough bytes available to read (%d < %d)";
        v11 = (__int64 *)&byte_1401402A7;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v32) = 102;
        v34 = "ReadData";
        v13 = word_140140262;
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
      if ( (unsigned int)dword_140152118 <= 4 )
        return 1;
      v33 = v4;
      v10 = "Not enough data for preconnection blob (%d < %d)";
      v11 = qword_1401400E8;
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
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v31 = "OOM on allocating %d size pcb";
        v33 = 129;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)byte_140140121,
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
      if ( (unsigned int)dword_140152118 <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 164;
      v34 = "ReadData";
      v7 = (__int64 *)byte_1401400A3;
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
      v31 = "Read 0 bytes from the pending connection socket";
      v8 = &v31;
      goto LABEL_6;
    }
    if ( v24 == -1 )
    {
      if ( WSAGetLastError() == 10035 )
      {
        if ( (unsigned int)dword_140152118 > 4 )
        {
          LODWORD(v32) = v23;
          v34 = "Not enough bytes available to read (%d < %d)";
          v33 = -1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v4,
            (unsigned int)word_14014006A,
            v5,
            v6,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32);
        }
        return 1;
      }
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v32) = 172;
        v34 = "ReadData";
        v13 = (__int16 *)byte_14014021D;
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
    if ( (unsigned int)dword_140152118 > 4 )
    {
      v32 = "Got enough bytes for to complete the connection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140152118,
        (unsigned int)&dword_1401401FC,
        v5,
        v6,
        (__int64)&v32);
    }
    v25 = *((_DWORD *)this + 12);
    if ( v25 < 0x10 )
    {
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v30 = "PCB size too small %d";
        v33 = 187;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&byte_14014019F,
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
      if ( (unsigned int)dword_140152118 <= 4 )
        return 0;
      v26 = &word_14014017E;
LABEL_62:
      v32 = "V1 PCB or no string in V2 PCB";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140152118,
        (_DWORD)v26,
        v5,
        v6,
        (__int64)&v32);
      return 0;
    }
    if ( v25 >= 0x12 )
    {
      v29 = *((unsigned __int16 *)v1 + 8);
      if ( !(_WORD)v29 )
      {
        if ( (unsigned int)dword_140152118 <= 4 )
          return 0;
        v26 = (__int16 *)&dword_140140004;
        goto LABEL_62;
      }
      if ( (unsigned int)(2 * v29) < 0xFFFFFFEE && 2 * (int)v29 + 18 <= (int)v25 )
      {
        *((_WORD *)v1 + v29 + 8) = 0;
        *((_QWORD *)this + 9) = (char *)v1 + 18;
        return 0;
      }
      if ( (unsigned int)dword_140152118 > 2 )
      {
        LODWORD(v32) = 227;
        v34 = "ReadData";
        v27 = &byte_14013FFBF;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v28 = "Overflow detected in PCB buffer";
        goto LABEL_67;
      }
    }
    else if ( (unsigned int)dword_140152118 > 2 )
    {
      LODWORD(v32) = 205;
      v34 = "ReadData";
      v27 = byte_140140025;
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
0x14006d354  push    rbp
0x14006d356  push    rbx
0x14006d357  push    rsi
0x14006d358  push    rdi
0x14006d359  push    r15
0x14006d35b  mov     rbp, rsp
0x14006d35e  sub     rsp, 60h
0x14006d362  mov     rdi, [rcx+38h]
0x14006d366  mov     rbx, rcx
0x14006d369  mov     rcx, [rcx]; unsigned __int64
0x14006d36c  call    ?RDPENCHLPWS_IsSocketInReadableState@@YAH_K@Z; RDPENCHLPWS_IsSocketInReadableState(unsigned __int64)
0x14006d371  xor     r15d, r15d
0x14006d374  test    eax, eax
0x14006d376  jz      loc_14006D483
0x14006d37c  cmp     dword ptr [rbx+40h], 4
0x14006d380  jnb     loc_14006D61E
0x14006d386  mov     edx, [rbx+40h]
0x14006d389  lea     edi, [r15+4]
0x14006d38d  sub     edi, [rbx+40h]
0x14006d390  add     rdx, 44h ; 'D'
0x14006d394  mov     rcx, [rbx]; s
0x14006d397  add     rdx, rbx; buf
0x14006d39a  mov     r8d, edi; len
0x14006d39d  xor     r9d, r9d; flags
0x14006d3a0  call    cs:__imp_recv
0x14006d3a6  mov     ecx, eax
0x14006d3a8  test    eax, eax
0x14006d3aa  jnz     short loc_14006D426
0x14006d3ac  mov     eax, cs:dword_140152118
0x14006d3b2  cmp     eax, 2
0x14006d3b5  jbe     short loc_14006D41F
0x14006d3b7  lea     rax, aReaddata; "ReadData"
0x14006d3be  mov     dword ptr [rbp+arg_0], 5Ch ; '\'
0x14006d3c5  mov     [rbp+arg_10], rax
0x14006d3c9  lea     rdx, qword_1401402E0
0x14006d3d0  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006d3d7  mov     [rbp+arg_18], rax
0x14006d3db  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x14006d3e2  mov     [rbp+var_10], rax
0x14006d3e6  lea     rax, [rbp+arg_10]
0x14006d3ea  mov     [rsp+60h+var_20], rax
0x14006d3ef  lea     rax, [rbp+arg_0]
0x14006d3f3  mov     [rsp+60h+var_28], rax
0x14006d3f8  lea     rax, [rbp+arg_18]
0x14006d3fc  mov     [rsp+60h+var_30], rax
0x14006d401  lea     rax, [rbp+arg_8]
0x14006d405  mov     [rsp+60h+var_38], rax
0x14006d40a  lea     rax, [rbp+var_10]
0x14006d40e  mov     [rsp+60h+var_40], rax
0x14006d413  mov     [rbp+arg_8], 80004005h
0x14006d41a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14006d41f  mov     ebx, 80004004h
0x14006d424  jmp     short loc_14006D488
0x14006d426  cmp     ecx, 0FFFFFFFFh
0x14006d429  jnz     loc_14006D50E
0x14006d42f  call    cs:__imp_WSAGetLastError
0x14006d435  cmp     eax, 2733h
0x14006d43a  mov     eax, cs:dword_140152118
0x14006d440  jnz     short loc_14006D495
0x14006d442  cmp     eax, 4
0x14006d445  jbe     short loc_14006D483
0x14006d447  mov     [rbp+arg_8], 0FFFFFFFFh
0x14006d44e  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x14006d455  lea     rdx, byte_1401402A7
0x14006d45c  mov     [rbp+arg_10], rax
0x14006d460  lea     rax, [rbp+arg_0]
0x14006d464  mov     [rsp+60h+var_30], rax
0x14006d469  lea     rax, [rbp+arg_8]
0x14006d46d  mov     [rsp+60h+var_38], rax
0x14006d472  lea     rax, [rbp+arg_10]
0x14006d476  mov     [rsp+60h+var_40], rax
0x14006d47b  mov     dword ptr [rbp+arg_0], edi
0x14006d47e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006d483  mov     ebx, 1
0x14006d488  mov     eax, ebx
0x14006d48a  add     rsp, 60h
0x14006d48e  pop     r15
0x14006d490  pop     rdi
0x14006d491  pop     rsi
0x14006d492  pop     rbx
0x14006d493  pop     rbp
0x14006d494  retn
0x14006d495  cmp     eax, 2
0x14006d498  jbe     short loc_14006D502
0x14006d49a  lea     rax, aReaddata; "ReadData"
0x14006d4a1  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x14006d4a8  mov     [rbp+arg_10], rax
0x14006d4ac  lea     rdx, word_140140262
0x14006d4b3  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006d4ba  mov     [rbp+arg_18], rax
0x14006d4be  lea     rax, aErrorReadingFr; "Error reading from the pending connecti"...
0x14006d4c5  mov     [rbp+var_10], rax
0x14006d4c9  lea     rax, [rbp+arg_10]
0x14006d4cd  mov     [rsp+60h+var_20], rax
0x14006d4d2  lea     rax, [rbp+arg_0]
0x14006d4d6  mov     [rsp+60h+var_28], rax
0x14006d4db  lea     rax, [rbp+arg_18]
0x14006d4df  mov     [rsp+60h+var_30], rax
0x14006d4e4  lea     rax, [rbp+arg_8]
0x14006d4e8  mov     [rsp+60h+var_38], rax
0x14006d4ed  lea     rax, [rbp+var_10]
0x14006d4f1  mov     [rsp+60h+var_40], rax
0x14006d4f6  mov     [rbp+arg_8], 80004005h
0x14006d4fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14006d502  call    RDPENCHLPWSErr2Hr
0x14006d507  mov     ebx, eax
0x14006d509  jmp     loc_14006D488
0x14006d50e  cmp     edi, ecx
0x14006d510  jnz     loc_14006D6C7
0x14006d516  add     [rbx+40h], ecx
0x14006d519  mov     ecx, [rbx+44h]; Size
0x14006d51c  mov     [rbx+30h], ecx
0x14006d51f  lea     eax, [rcx-1]
0x14006d522  cmp     eax, 0FFFh
0x14006d527  ja      loc_14006D666
0x14006d52d  cmp     ecx, 4
0x14006d530  ja      short loc_14006D571
0x14006d532  mov     ebx, 80070057h
0x14006d537  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d53e  lea     rax, WPP_GLOBAL_Control
0x14006d545  cmp     rcx, rax
0x14006d548  jz      loc_14006D488
0x14006d54e  test    byte ptr [rcx+1Ch], 1
0x14006d552  jz      loc_14006D488
0x14006d558  cmp     byte ptr [rcx+19h], 2
0x14006d55c  jb      loc_14006D488
0x14006d562  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006d567  mov     edx, 0Bh
0x14006d56c  jmp     loc_14006D6A0
0x14006d571  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006d576  mov     [rbx+38h], rax
0x14006d57a  mov     rdi, rax
0x14006d57d  test    rax, rax
0x14006d580  jnz     loc_14006D612
0x14006d586  mov     eax, cs:dword_140152118
0x14006d58c  cmp     eax, 2
0x14006d58f  jbe     short loc_14006D608
0x14006d591  mov     eax, [rbx+30h]
0x14006d594  lea     rdx, byte_140140121
0x14006d59b  mov     dword ptr [rbp+arg_0], eax
0x14006d59e  lea     rax, aReaddata; "ReadData"
0x14006d5a5  mov     [rbp+arg_18], rax
0x14006d5a9  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006d5b0  mov     [rbp+var_10], rax
0x14006d5b4  lea     rax, aOomOnAllocatin; "OOM on allocating %d size pcb"
0x14006d5bb  mov     [rbp+var_8], rax
0x14006d5bf  lea     rax, [rbp+arg_0]
0x14006d5c3  mov     [rsp+60h+var_18], rax
0x14006d5c8  lea     rax, [rbp+arg_18]
0x14006d5cc  mov     [rsp+60h+var_20], rax
0x14006d5d1  lea     rax, [rbp+arg_8]
0x14006d5d5  mov     [rsp+60h+var_28], rax
0x14006d5da  lea     rax, [rbp+var_10]
0x14006d5de  mov     [rsp+60h+var_30], rax
0x14006d5e3  lea     rax, [rbp+arg_10]
0x14006d5e7  mov     [rsp+60h+var_38], rax
0x14006d5ec  lea     rax, [rbp+var_8]
0x14006d5f0  mov     [rsp+60h+var_40], rax
0x14006d5f5  mov     [rbp+arg_8], 81h
0x14006d5fc  mov     dword ptr [rbp+arg_10], 80004005h
0x14006d603  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14006d608  mov     ebx, 8007000Eh
0x14006d60d  jmp     loc_14006D488
0x14006d612  mov     eax, [rbx+30h]
0x14006d615  mov     [rdi], eax
0x14006d617  mov     dword ptr [rbx+2Ch], 4
0x14006d61e  mov     esi, [rbx+30h]
0x14006d621  cmp     esi, [rbx+2Ch]
0x14006d624  ja      loc_14006D6EC
0x14006d62a  mov     ebx, 80070057h
0x14006d62f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d636  lea     rax, WPP_GLOBAL_Control
0x14006d63d  cmp     rcx, rax
0x14006d640  jz      loc_14006D488
0x14006d646  test    byte ptr [rcx+1Ch], 1
0x14006d64a  jz      loc_14006D488
0x14006d650  cmp     byte ptr [rcx+19h], 2
0x14006d654  jb      loc_14006D488
0x14006d65a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006d65f  mov     edx, 0Ch
0x14006d664  jmp     short loc_14006D6A0
0x14006d666  mov     ebx, 80070057h
0x14006d66b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d672  lea     rax, WPP_GLOBAL_Control
0x14006d679  cmp     rcx, rax
0x14006d67c  jz      loc_14006D488
0x14006d682  test    byte ptr [rcx+1Ch], 1
0x14006d686  jz      loc_14006D488
0x14006d68c  cmp     byte ptr [rcx+19h], 2
0x14006d690  jb      loc_14006D488
0x14006d696  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006d69b  mov     edx, 0Ah
0x14006d6a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d6a7  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006d6ae  mov     r9d, eax
0x14006d6b1  mov     dword ptr [rsp+60h+var_40], 80070057h
0x14006d6b9  mov     rcx, [rcx+10h]
0x14006d6bd  call    WPP_SF_Dd
0x14006d6c2  jmp     loc_14006D488
0x14006d6c7  mov     eax, cs:dword_140152118
0x14006d6cd  cmp     eax, 4
0x14006d6d0  jbe     loc_14006D483
0x14006d6d6  mov     [rbp+arg_8], ecx
0x14006d6d9  lea     rax, aNotEnoughDataF; "Not enough data for preconnection blob "...
0x14006d6e0  lea     rdx, qword_1401400E8
0x14006d6e7  jmp     loc_14006D45C
0x14006d6ec  sub     esi, [rbx+2Ch]
0x14006d6ef  xor     r9d, r9d; flags
0x14006d6f2  mov     edx, [rbx+2Ch]
0x14006d6f5  mov     r8d, esi; len
0x14006d6f8  add     rdx, [rbx+38h]; buf
0x14006d6fc  mov     rcx, [rbx]; s
0x14006d6ff  call    cs:__imp_recv
0x14006d705  test    eax, eax
0x14006d707  jnz     short loc_14006D774
0x14006d709  mov     eax, cs:dword_140152118
0x14006d70f  cmp     eax, 2
0x14006d712  jbe     loc_14006D41F
0x14006d718  lea     rax, aReaddata; "ReadData"
0x14006d71f  mov     dword ptr [rbp+arg_0], 0A4h
0x14006d726  mov     [rbp+arg_10], rax
0x14006d72a  lea     rdx, byte_1401400A3
0x14006d731  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006d738  mov     [rbp+arg_18], rax
0x14006d73c  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x14006d743  mov     [rbp+var_8], rax
0x14006d747  lea     rax, [rbp+arg_10]
0x14006d74b  mov     [rsp+60h+var_20], rax
0x14006d750  lea     rax, [rbp+arg_0]
0x14006d754  mov     [rsp+60h+var_28], rax
0x14006d759  lea     rax, [rbp+arg_18]
0x14006d75d  mov     [rsp+60h+var_30], rax
0x14006d762  lea     rax, [rbp+arg_8]
0x14006d766  mov     [rsp+60h+var_38], rax
0x14006d76b  lea     rax, [rbp+var_8]
0x14006d76f  jmp     loc_14006D40E
0x14006d774  cmp     eax, 0FFFFFFFFh
0x14006d777  jnz     loc_14006D83A
0x14006d77d  call    cs:__imp_WSAGetLastError
0x14006d783  cmp     eax, 2733h
0x14006d788  mov     eax, cs:dword_140152118
0x14006d78e  jnz     short loc_14006D7D5
0x14006d790  cmp     eax, 4
0x14006d793  jbe     loc_14006D483
0x14006d799  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x14006d7a0  mov     dword ptr [rbp+arg_0], esi
0x14006d7a3  mov     [rbp+arg_10], rax
0x14006d7a7  lea     rdx, word_14014006A
0x14006d7ae  lea     rax, [rbp+arg_0]
0x14006d7b2  mov     [rbp+arg_8], 0FFFFFFFFh
0x14006d7b9  mov     [rsp+60h+var_30], rax
0x14006d7be  lea     rax, [rbp+arg_8]
0x14006d7c2  mov     [rsp+60h+var_38], rax
0x14006d7c7  lea     rax, [rbp+arg_10]
0x14006d7cb  mov     [rsp+60h+var_40], rax
0x14006d7d0  jmp     loc_14006D47E
0x14006d7d5  cmp     eax, 2
0x14006d7d8  jbe     loc_14006D502
0x14006d7de  lea     rax, aReaddata; "ReadData"
0x14006d7e5  mov     dword ptr [rbp+arg_0], 0ACh
0x14006d7ec  mov     [rbp+arg_10], rax
0x14006d7f0  lea     rdx, byte_14014021D
0x14006d7f7  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006d7fe  mov     [rbp+arg_18], rax
0x14006d802  lea     rax, aErrorReadingFr; "Error reading from the pending connecti"...
0x14006d809  mov     [rbp+var_8], rax
0x14006d80d  lea     rax, [rbp+arg_10]
0x14006d811  mov     [rsp+60h+var_20], rax
0x14006d816  lea     rax, [rbp+arg_0]
0x14006d81a  mov     [rsp+60h+var_28], rax
0x14006d81f  lea     rax, [rbp+arg_18]
0x14006d823  mov     [rsp+60h+var_30], rax
0x14006d828  lea     rax, [rbp+arg_8]
0x14006d82c  mov     [rsp+60h+var_38], rax
0x14006d831  lea     rax, [rbp+var_8]
0x14006d835  jmp     loc_14006D4F1
0x14006d83a  add     [rbx+2Ch], eax
0x14006d83d  cmp     esi, eax
0x14006d83f  jnz     loc_14006D483
0x14006d845  mov     eax, cs:dword_140152118
0x14006d84b  lea     rsi, dword_140152118
0x14006d852  cmp     eax, 4
0x14006d855  jbe     short loc_14006D87A
0x14006d857  lea     rax, aGotEnoughBytes; "Got enough bytes for to complete the co"...
0x14006d85e  mov     rcx, rsi
0x14006d861  mov     [rbp+arg_0], rax
0x14006d865  lea     rdx, dword_1401401FC
0x14006d86c  lea     rax, [rbp+arg_0]
0x14006d870  mov     [rsp+60h+var_40], rax
0x14006d875  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14006d87a  mov     ecx, [rbx+30h]
0x14006d87d  cmp     ecx, 10h
0x14006d880  jnb     loc_14006D912
0x14006d886  mov     eax, cs:dword_140152118
0x14006d88c  cmp     eax, 2
0x14006d88f  jbe     short loc_14006D908
0x14006d891  mov     eax, [rbx+30h]
0x14006d894  lea     rdx, byte_14014019F
0x14006d89b  mov     dword ptr [rbp+arg_0], eax
0x14006d89e  lea     rax, aReaddata; "ReadData"
  ... truncated ...
```
