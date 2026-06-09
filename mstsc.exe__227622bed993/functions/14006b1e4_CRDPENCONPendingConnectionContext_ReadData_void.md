# CRDPENCONPendingConnectionContext::ReadData(void)

- ea: `0x14006b1e4`
- end: `0x14006b8e3`
- name: `?ReadData@CRDPENCONPendingConnectionContext@@QEAAJXZ`
- size: `1791`
- prototype: `__int64 __fastcall(CRDPENCONPendingConnectionContext *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14006afdc`
- `0x14006b0bc`

## callees

- `0x140001010`
- `0x1400019e8`
- `0x140001b00`
- `0x140001fbc`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14006b158`
- `0x14006b1e4`
- `0x14008ebc4`

## import_xrefs

- `WS2_32!__imp_recv` at `0x14006b230`
- `WS2_32!__imp_recv` at `0x14006b58f`
- `WS2_32!__imp_recv` at `0x14006b230`
- `WS2_32!__imp_recv` at `0x14006b58f`
- `WS2_32!__imp_WSAGetLastError` at `0x14006b2bf`
- `WS2_32!__imp_WSAGetLastError` at `0x14006b60d`
- `WS2_32!__imp_WSAGetLastError` at `0x14006b2bf`
- `WS2_32!__imp_WSAGetLastError` at `0x14006b60d`

## string_xrefs

- `0x14006b247`: `ReadData`
- `0x14006b32a`: `ReadData`
- `0x14006b42e`: `ReadData`
- `0x14006b5a8`: `ReadData`
- `0x14006b66e`: `ReadData`
- `0x14006b72e`: `ReadData`
- `0x14006b7f0`: `ReadData`
- `0x14006b8b3`: `ReadData`
- `0x14006b6e7`: `Got enough bytes for to complete the connection`
- `0x14006b26b`: `Read 0 bytes from the pending connection socket`
- `0x14006b5cc`: `Read 0 bytes from the pending connection socket`
- `0x14006b2de`: `Not enough bytes available to read (%d < %d)`
- `0x14006b629`: `Not enough bytes available to read (%d < %d)`
- `0x14006b34e`: `Error reading from the pending connection socket`
- `0x14006b692`: `Error reading from the pending connection socket`

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
      if ( (unsigned int)dword_140150118 <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 92;
      v34 = "ReadData";
      v7 = qword_14013E1A8;
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
        if ( (unsigned int)dword_140150118 <= 4 )
          return 1;
        v33 = -1;
        v10 = "Not enough bytes available to read (%d < %d)";
        v11 = (__int64 *)&byte_14013E16F;
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v32) = 102;
        v34 = "ReadData";
        v13 = word_14013E12A;
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
      if ( (unsigned int)dword_140150118 <= 4 )
        return 1;
      v33 = v4;
      v10 = "Not enough data for preconnection blob (%d < %d)";
      v11 = qword_14013DFB0;
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v31 = "OOM on allocating %d size pcb";
        v33 = 129;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)byte_14013E0CD,
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
      if ( (unsigned int)dword_140150118 <= 2 )
        return (unsigned int)-2147467260;
      LODWORD(v32) = 164;
      v34 = "ReadData";
      v7 = (__int64 *)byte_14013DF6B;
      v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
      v31 = "Read 0 bytes from the pending connection socket";
      v8 = &v31;
      goto LABEL_6;
    }
    if ( v24 == -1 )
    {
      if ( WSAGetLastError() == 10035 )
      {
        if ( (unsigned int)dword_140150118 > 4 )
        {
          LODWORD(v32) = v23;
          v34 = "Not enough bytes available to read (%d < %d)";
          v33 = -1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v4,
            (unsigned int)word_14013DF32,
            v5,
            v6,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32);
        }
        return 1;
      }
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v32) = 172;
        v34 = "ReadData";
        v13 = (__int16 *)byte_14013DEED;
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
    if ( (unsigned int)dword_140150118 > 4 )
    {
      v32 = "Got enough bytes for to complete the connection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140150118,
        (unsigned int)&dword_14013E0AC,
        v5,
        v6,
        (__int64)&v32);
    }
    v25 = *((_DWORD *)this + 12);
    if ( v25 < 0x10 )
    {
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v32) = *((_DWORD *)this + 12);
        v35 = "ReadData";
        v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v30 = "PCB size too small %d";
        v33 = 187;
        LODWORD(v34) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&byte_14013E04F,
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
      if ( (unsigned int)dword_140150118 <= 4 )
        return 0;
      v26 = &word_14013E02E;
LABEL_62:
      v32 = "V1 PCB or no string in V2 PCB";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_140150118,
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
        if ( (unsigned int)dword_140150118 <= 4 )
          return 0;
        v26 = (__int16 *)&dword_14013DECC;
        goto LABEL_62;
      }
      if ( (unsigned int)(2 * v29) < 0xFFFFFFEE && 2 * (int)v29 + 18 <= (int)v25 )
      {
        *((_WORD *)v1 + v29 + 8) = 0;
        *((_QWORD *)this + 9) = (char *)v1 + 18;
        return 0;
      }
      if ( (unsigned int)dword_140150118 > 2 )
      {
        LODWORD(v32) = 227;
        v34 = "ReadData";
        v27 = &byte_14013DE87;
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
        v28 = "Overflow detected in PCB buffer";
        goto LABEL_67;
      }
    }
    else if ( (unsigned int)dword_140150118 > 2 )
    {
      LODWORD(v32) = 205;
      v34 = "ReadData";
      v27 = byte_14013DFE9;
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
0x14006b1e4  push    rbp
0x14006b1e6  push    rbx
0x14006b1e7  push    rsi
0x14006b1e8  push    rdi
0x14006b1e9  push    r15
0x14006b1eb  mov     rbp, rsp
0x14006b1ee  sub     rsp, 60h
0x14006b1f2  mov     rdi, [rcx+38h]
0x14006b1f6  mov     rbx, rcx
0x14006b1f9  mov     rcx, [rcx]; unsigned __int64
0x14006b1fc  call    ?RDPENCHLPWS_IsSocketInReadableState@@YAH_K@Z; RDPENCHLPWS_IsSocketInReadableState(unsigned __int64)
0x14006b201  xor     r15d, r15d
0x14006b204  test    eax, eax
0x14006b206  jz      loc_14006B313
0x14006b20c  cmp     dword ptr [rbx+40h], 4
0x14006b210  jnb     loc_14006B4AE
0x14006b216  mov     edx, [rbx+40h]
0x14006b219  lea     edi, [r15+4]
0x14006b21d  sub     edi, [rbx+40h]
0x14006b220  add     rdx, 44h ; 'D'
0x14006b224  mov     rcx, [rbx]; s
0x14006b227  add     rdx, rbx; buf
0x14006b22a  mov     r8d, edi; len
0x14006b22d  xor     r9d, r9d; flags
0x14006b230  call    cs:__imp_recv
0x14006b236  mov     ecx, eax
0x14006b238  test    eax, eax
0x14006b23a  jnz     short loc_14006B2B6
0x14006b23c  mov     eax, cs:dword_140150118
0x14006b242  cmp     eax, 2
0x14006b245  jbe     short loc_14006B2AF
0x14006b247  lea     rax, aReaddata; "ReadData"
0x14006b24e  mov     dword ptr [rbp+arg_0], 5Ch ; '\'
0x14006b255  mov     [rbp+arg_10], rax
0x14006b259  lea     rdx, qword_14013E1A8
0x14006b260  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006b267  mov     [rbp+arg_18], rax
0x14006b26b  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x14006b272  mov     [rbp+var_10], rax
0x14006b276  lea     rax, [rbp+arg_10]
0x14006b27a  mov     [rsp+60h+var_20], rax
0x14006b27f  lea     rax, [rbp+arg_0]
0x14006b283  mov     [rsp+60h+var_28], rax
0x14006b288  lea     rax, [rbp+arg_18]
0x14006b28c  mov     [rsp+60h+var_30], rax
0x14006b291  lea     rax, [rbp+arg_8]
0x14006b295  mov     [rsp+60h+var_38], rax
0x14006b29a  lea     rax, [rbp+var_10]
0x14006b29e  mov     [rsp+60h+var_40], rax
0x14006b2a3  mov     [rbp+arg_8], 80004005h
0x14006b2aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14006b2af  mov     ebx, 80004004h
0x14006b2b4  jmp     short loc_14006B318
0x14006b2b6  cmp     ecx, 0FFFFFFFFh
0x14006b2b9  jnz     loc_14006B39E
0x14006b2bf  call    cs:__imp_WSAGetLastError
0x14006b2c5  cmp     eax, 2733h
0x14006b2ca  mov     eax, cs:dword_140150118
0x14006b2d0  jnz     short loc_14006B325
0x14006b2d2  cmp     eax, 4
0x14006b2d5  jbe     short loc_14006B313
0x14006b2d7  mov     [rbp+arg_8], 0FFFFFFFFh
0x14006b2de  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x14006b2e5  lea     rdx, byte_14013E16F
0x14006b2ec  mov     [rbp+arg_10], rax
0x14006b2f0  lea     rax, [rbp+arg_0]
0x14006b2f4  mov     [rsp+60h+var_30], rax
0x14006b2f9  lea     rax, [rbp+arg_8]
0x14006b2fd  mov     [rsp+60h+var_38], rax
0x14006b302  lea     rax, [rbp+arg_10]
0x14006b306  mov     [rsp+60h+var_40], rax
0x14006b30b  mov     dword ptr [rbp+arg_0], edi
0x14006b30e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14006b313  mov     ebx, 1
0x14006b318  mov     eax, ebx
0x14006b31a  add     rsp, 60h
0x14006b31e  pop     r15
0x14006b320  pop     rdi
0x14006b321  pop     rsi
0x14006b322  pop     rbx
0x14006b323  pop     rbp
0x14006b324  retn
0x14006b325  cmp     eax, 2
0x14006b328  jbe     short loc_14006B392
0x14006b32a  lea     rax, aReaddata; "ReadData"
0x14006b331  mov     dword ptr [rbp+arg_0], 66h ; 'f'
0x14006b338  mov     [rbp+arg_10], rax
0x14006b33c  lea     rdx, word_14013E12A
0x14006b343  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006b34a  mov     [rbp+arg_18], rax
0x14006b34e  lea     rax, aErrorReadingFr; "Error reading from the pending connecti"...
0x14006b355  mov     [rbp+var_10], rax
0x14006b359  lea     rax, [rbp+arg_10]
0x14006b35d  mov     [rsp+60h+var_20], rax
0x14006b362  lea     rax, [rbp+arg_0]
0x14006b366  mov     [rsp+60h+var_28], rax
0x14006b36b  lea     rax, [rbp+arg_18]
0x14006b36f  mov     [rsp+60h+var_30], rax
0x14006b374  lea     rax, [rbp+arg_8]
0x14006b378  mov     [rsp+60h+var_38], rax
0x14006b37d  lea     rax, [rbp+var_10]
0x14006b381  mov     [rsp+60h+var_40], rax
0x14006b386  mov     [rbp+arg_8], 80004005h
0x14006b38d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14006b392  call    RDPENCHLPWSErr2Hr
0x14006b397  mov     ebx, eax
0x14006b399  jmp     loc_14006B318
0x14006b39e  cmp     edi, ecx
0x14006b3a0  jnz     loc_14006B557
0x14006b3a6  add     [rbx+40h], ecx
0x14006b3a9  mov     ecx, [rbx+44h]; Size
0x14006b3ac  mov     [rbx+30h], ecx
0x14006b3af  lea     eax, [rcx-1]
0x14006b3b2  cmp     eax, 0FFFh
0x14006b3b7  ja      loc_14006B4F6
0x14006b3bd  cmp     ecx, 4
0x14006b3c0  ja      short loc_14006B401
0x14006b3c2  mov     ebx, 80070057h
0x14006b3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b3ce  lea     rax, WPP_GLOBAL_Control
0x14006b3d5  cmp     rcx, rax
0x14006b3d8  jz      loc_14006B318
0x14006b3de  test    byte ptr [rcx+1Ch], 1
0x14006b3e2  jz      loc_14006B318
0x14006b3e8  cmp     byte ptr [rcx+19h], 2
0x14006b3ec  jb      loc_14006B318
0x14006b3f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006b3f7  mov     edx, 0Bh
0x14006b3fc  jmp     loc_14006B530
0x14006b401  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006b406  mov     [rbx+38h], rax
0x14006b40a  mov     rdi, rax
0x14006b40d  test    rax, rax
0x14006b410  jnz     loc_14006B4A2
0x14006b416  mov     eax, cs:dword_140150118
0x14006b41c  cmp     eax, 2
0x14006b41f  jbe     short loc_14006B498
0x14006b421  mov     eax, [rbx+30h]
0x14006b424  lea     rdx, byte_14013E0CD
0x14006b42b  mov     dword ptr [rbp+arg_0], eax
0x14006b42e  lea     rax, aReaddata; "ReadData"
0x14006b435  mov     [rbp+arg_18], rax
0x14006b439  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006b440  mov     [rbp+var_10], rax
0x14006b444  lea     rax, aOomOnAllocatin; "OOM on allocating %d size pcb"
0x14006b44b  mov     [rbp+var_8], rax
0x14006b44f  lea     rax, [rbp+arg_0]
0x14006b453  mov     [rsp+60h+var_18], rax
0x14006b458  lea     rax, [rbp+arg_18]
0x14006b45c  mov     [rsp+60h+var_20], rax
0x14006b461  lea     rax, [rbp+arg_8]
0x14006b465  mov     [rsp+60h+var_28], rax
0x14006b46a  lea     rax, [rbp+var_10]
0x14006b46e  mov     [rsp+60h+var_30], rax
0x14006b473  lea     rax, [rbp+arg_10]
0x14006b477  mov     [rsp+60h+var_38], rax
0x14006b47c  lea     rax, [rbp+var_8]
0x14006b480  mov     [rsp+60h+var_40], rax
0x14006b485  mov     [rbp+arg_8], 81h
0x14006b48c  mov     dword ptr [rbp+arg_10], 80004005h
0x14006b493  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14006b498  mov     ebx, 8007000Eh
0x14006b49d  jmp     loc_14006B318
0x14006b4a2  mov     eax, [rbx+30h]
0x14006b4a5  mov     [rdi], eax
0x14006b4a7  mov     dword ptr [rbx+2Ch], 4
0x14006b4ae  mov     esi, [rbx+30h]
0x14006b4b1  cmp     esi, [rbx+2Ch]
0x14006b4b4  ja      loc_14006B57C
0x14006b4ba  mov     ebx, 80070057h
0x14006b4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b4c6  lea     rax, WPP_GLOBAL_Control
0x14006b4cd  cmp     rcx, rax
0x14006b4d0  jz      loc_14006B318
0x14006b4d6  test    byte ptr [rcx+1Ch], 1
0x14006b4da  jz      loc_14006B318
0x14006b4e0  cmp     byte ptr [rcx+19h], 2
0x14006b4e4  jb      loc_14006B318
0x14006b4ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006b4ef  mov     edx, 0Ch
0x14006b4f4  jmp     short loc_14006B530
0x14006b4f6  mov     ebx, 80070057h
0x14006b4fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b502  lea     rax, WPP_GLOBAL_Control
0x14006b509  cmp     rcx, rax
0x14006b50c  jz      loc_14006B318
0x14006b512  test    byte ptr [rcx+1Ch], 1
0x14006b516  jz      loc_14006B318
0x14006b51c  cmp     byte ptr [rcx+19h], 2
0x14006b520  jb      loc_14006B318
0x14006b526  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006b52b  mov     edx, 0Ah
0x14006b530  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b537  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006b53e  mov     r9d, eax
0x14006b541  mov     dword ptr [rsp+60h+var_40], 80070057h
0x14006b549  mov     rcx, [rcx+10h]
0x14006b54d  call    WPP_SF_Dd
0x14006b552  jmp     loc_14006B318
0x14006b557  mov     eax, cs:dword_140150118
0x14006b55d  cmp     eax, 4
0x14006b560  jbe     loc_14006B313
0x14006b566  mov     [rbp+arg_8], ecx
0x14006b569  lea     rax, aNotEnoughDataF; "Not enough data for preconnection blob "...
0x14006b570  lea     rdx, qword_14013DFB0
0x14006b577  jmp     loc_14006B2EC
0x14006b57c  sub     esi, [rbx+2Ch]
0x14006b57f  xor     r9d, r9d; flags
0x14006b582  mov     edx, [rbx+2Ch]
0x14006b585  mov     r8d, esi; len
0x14006b588  add     rdx, [rbx+38h]; buf
0x14006b58c  mov     rcx, [rbx]; s
0x14006b58f  call    cs:__imp_recv
0x14006b595  test    eax, eax
0x14006b597  jnz     short loc_14006B604
0x14006b599  mov     eax, cs:dword_140150118
0x14006b59f  cmp     eax, 2
0x14006b5a2  jbe     loc_14006B2AF
0x14006b5a8  lea     rax, aReaddata; "ReadData"
0x14006b5af  mov     dword ptr [rbp+arg_0], 0A4h
0x14006b5b6  mov     [rbp+arg_10], rax
0x14006b5ba  lea     rdx, byte_14013DF6B
0x14006b5c1  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006b5c8  mov     [rbp+arg_18], rax
0x14006b5cc  lea     rax, aRead0BytesFrom; "Read 0 bytes from the pending connectio"...
0x14006b5d3  mov     [rbp+var_8], rax
0x14006b5d7  lea     rax, [rbp+arg_10]
0x14006b5db  mov     [rsp+60h+var_20], rax
0x14006b5e0  lea     rax, [rbp+arg_0]
0x14006b5e4  mov     [rsp+60h+var_28], rax
0x14006b5e9  lea     rax, [rbp+arg_18]
0x14006b5ed  mov     [rsp+60h+var_30], rax
0x14006b5f2  lea     rax, [rbp+arg_8]
0x14006b5f6  mov     [rsp+60h+var_38], rax
0x14006b5fb  lea     rax, [rbp+var_8]
0x14006b5ff  jmp     loc_14006B29E
0x14006b604  cmp     eax, 0FFFFFFFFh
0x14006b607  jnz     loc_14006B6CA
0x14006b60d  call    cs:__imp_WSAGetLastError
0x14006b613  cmp     eax, 2733h
0x14006b618  mov     eax, cs:dword_140150118
0x14006b61e  jnz     short loc_14006B665
0x14006b620  cmp     eax, 4
0x14006b623  jbe     loc_14006B313
0x14006b629  lea     rax, aNotEnoughBytes; "Not enough bytes available to read (%d "...
0x14006b630  mov     dword ptr [rbp+arg_0], esi
0x14006b633  mov     [rbp+arg_10], rax
0x14006b637  lea     rdx, word_14013DF32
0x14006b63e  lea     rax, [rbp+arg_0]
0x14006b642  mov     [rbp+arg_8], 0FFFFFFFFh
0x14006b649  mov     [rsp+60h+var_30], rax
0x14006b64e  lea     rax, [rbp+arg_8]
0x14006b652  mov     [rsp+60h+var_38], rax
0x14006b657  lea     rax, [rbp+arg_10]
0x14006b65b  mov     [rsp+60h+var_40], rax
0x14006b660  jmp     loc_14006B30E
0x14006b665  cmp     eax, 2
0x14006b668  jbe     loc_14006B392
0x14006b66e  lea     rax, aReaddata; "ReadData"
0x14006b675  mov     dword ptr [rbp+arg_0], 0ACh
0x14006b67c  mov     [rbp+arg_10], rax
0x14006b680  lea     rdx, byte_14013DEED
0x14006b687  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x14006b68e  mov     [rbp+arg_18], rax
0x14006b692  lea     rax, aErrorReadingFr; "Error reading from the pending connecti"...
0x14006b699  mov     [rbp+var_8], rax
0x14006b69d  lea     rax, [rbp+arg_10]
0x14006b6a1  mov     [rsp+60h+var_20], rax
0x14006b6a6  lea     rax, [rbp+arg_0]
0x14006b6aa  mov     [rsp+60h+var_28], rax
0x14006b6af  lea     rax, [rbp+arg_18]
0x14006b6b3  mov     [rsp+60h+var_30], rax
0x14006b6b8  lea     rax, [rbp+arg_8]
0x14006b6bc  mov     [rsp+60h+var_38], rax
0x14006b6c1  lea     rax, [rbp+var_8]
0x14006b6c5  jmp     loc_14006B381
0x14006b6ca  add     [rbx+2Ch], eax
0x14006b6cd  cmp     esi, eax
0x14006b6cf  jnz     loc_14006B313
0x14006b6d5  mov     eax, cs:dword_140150118
0x14006b6db  lea     rsi, dword_140150118
0x14006b6e2  cmp     eax, 4
0x14006b6e5  jbe     short loc_14006B70A
0x14006b6e7  lea     rax, aGotEnoughBytes; "Got enough bytes for to complete the co"...
0x14006b6ee  mov     rcx, rsi
0x14006b6f1  mov     [rbp+arg_0], rax
0x14006b6f5  lea     rdx, dword_14013E0AC
0x14006b6fc  lea     rax, [rbp+arg_0]
0x14006b700  mov     [rsp+60h+var_40], rax
0x14006b705  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x14006b70a  mov     ecx, [rbx+30h]
0x14006b70d  cmp     ecx, 10h
0x14006b710  jnb     loc_14006B7A2
0x14006b716  mov     eax, cs:dword_140150118
0x14006b71c  cmp     eax, 2
0x14006b71f  jbe     short loc_14006B798
0x14006b721  mov     eax, [rbx+30h]
0x14006b724  lea     rdx, byte_14013E04F
0x14006b72b  mov     dword ptr [rbp+arg_0], eax
0x14006b72e  lea     rax, aReaddata; "ReadData"
  ... truncated ...
```
