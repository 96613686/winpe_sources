# RdsDWMDirectUpdateProcessor::RefreshWTSConnectionProperties(void)

- ea: `0x180011c84`
- end: `0x180012075`
- name: `?RefreshWTSConnectionProperties@RdsDWMDirectUpdateProcessor@@IEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012238`

## callees

- `0x180001564`
- `0x180001868`
- `0x180001ca4`
- `0x180001f98`
- `0x180011c84`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fe1`
- `WINSTA!WinStationFreePropertyValue` at `0x180011db0`
- `WINSTA!WinStationFreePropertyValue` at `0x180011f6d`
- `WINSTA!WinStationFreePropertyValue` at `0x180011db0`
- `WINSTA!WinStationFreePropertyValue` at `0x180011f6d`
- `WINSTA!WinStationGetConnectionProperty` at `0x180011cb1`
- `WINSTA!WinStationGetConnectionProperty` at `0x180011e60`
- `WINSTA!WinStationGetConnectionProperty` at `0x180011cb1`
- `WINSTA!WinStationGetConnectionProperty` at `0x180011e60`

## string_xrefs

- `0x180011cc4`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011d0b`: `The protocol stack returned the activity id.`
- `0x180011d50`: `The protocol stack return an invalid property type for the activity id.`
- `0x180011e0c`: `The protocol stack did not return the activity id property`
- `0x180011ea5`: `The protocol stack returned HiDef support level.`
- `0x180011f0d`: `The protocol stack return an invalid property type for the HiDef support.`
- `0x18001202a`: `The protocol stack did not return the HiDef support property`
- `0x180011f9b`: `Failed to read the WTS properties - stack not connected (sessionId=%d).`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::RefreshWTSConnectionProperties(RdsDWMDirectUpdateProcessor *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  signed int LastError; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v15; // eax
  __int64 v16; // [rsp+50h] [rbp-20h] BYREF
  const char *v17; // [rsp+58h] [rbp-18h] BYREF
  const char *v18; // [rsp+60h] [rbp-10h] BYREF
  const char *v19; // [rsp+68h] [rbp-8h] BYREF
  int v20; // [rsp+A8h] [rbp+38h] BYREF
  const char *v21; // [rsp+B0h] [rbp+40h] BYREF
  const char *v22; // [rsp+B8h] [rbp+48h] BYREF

  v16 = 0;
  if ( (unsigned __int8)WinStationGetConnectionProperty(0xFFFFFFFFLL, PROPERTY_TYPE_CORRELATIONID_GUID, &v16) )
  {
    LastError = 0;
    if ( *(_WORD *)v16 == 4 )
    {
      *(_OWORD *)((char *)this + 92) = *(_OWORD *)(v16 + 8);
      if ( (unsigned int)dword_180044008 > 4 )
      {
        v20 = *((_DWORD *)this + 27);
        v21 = (const char *)*((unsigned int *)this + 23);
        v22 = "The protocol stack returned the activity id.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v2,
          (__int64)word_180039D8A,
          v3,
          v4,
          (const unsigned __int16 **)&v22,
          (__int64)&v21,
          (__int64)&v20);
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = *((_DWORD *)this + 27);
      v19 = "The protocol stack return an invalid property type for the activity id.";
      v17 = "RefreshWTSConnectionProperties";
      LODWORD(v21) = 1414;
      v18 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      LODWORD(v22) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v2,
        (__int64)&byte_180039D2F,
        v3,
        v4,
        (const unsigned __int16 **)&v19,
        (__int64)&v22,
        (const unsigned __int16 **)&v18,
        (__int64)&v21,
        (const unsigned __int16 **)&v17,
        (__int64)&v20);
    }
    WinStationFreePropertyValue(v16);
    v16 = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 2250 )
      goto LABEL_25;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = *((_DWORD *)this + 27);
      v19 = "RefreshWTSConnectionProperties";
      LODWORD(v21) = 1429;
      v18 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      LODWORD(v22) = v9;
      v17 = "The protocol stack did not return the activity id property";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)&dword_180039CD4,
        v7,
        v8,
        (const unsigned __int16 **)&v17,
        (__int64)&v22,
        (const unsigned __int16 **)&v18,
        (__int64)&v21,
        (const unsigned __int16 **)&v19,
        (__int64)&v20);
    }
  }
  if ( (unsigned __int8)WinStationGetConnectionProperty(
                          0xFFFFFFFFLL,
                          PROPERTY_TYPE_GET_REMOTEAPP_HD_SUPPORT_LEVEL,
                          &v16) )
  {
    if ( *(_WORD *)v16 == 1 && (v12 = *(_DWORD *)(v16 + 8), v12 <= 3) )
    {
      *((_DWORD *)this + 29) = v12;
      if ( (unsigned int)dword_180044008 > 4 )
      {
        v20 = *((_DWORD *)this + 27);
        LODWORD(v21) = *((_DWORD *)this + 29);
        v22 = "The protocol stack returned HiDef support level.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          1,
          (__int64)&word_180039C86,
          v10,
          v11,
          (const unsigned __int16 **)&v22,
          (__int64)&v21,
          (__int64)&v20);
      }
      if ( *((_DWORD *)this + 29) )
      {
        v13 = *((_QWORD *)this + 5);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 104LL))(v13);
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = *((_DWORD *)this + 27);
      v17 = "The protocol stack return an invalid property type for the HiDef support.";
      v19 = "RefreshWTSConnectionProperties";
      LODWORD(v21) = 1464;
      v18 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      LODWORD(v22) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        1,
        (__int64)byte_180039C2B,
        v10,
        v11,
        (const unsigned __int16 **)&v17,
        (__int64)&v22,
        (const unsigned __int16 **)&v18,
        (__int64)&v21,
        (const unsigned __int16 **)&v19,
        (__int64)&v20);
    }
    WinStationFreePropertyValue(v16);
    v16 = 0;
    goto LABEL_27;
  }
  LastError = GetLastError();
  if ( LastError != 2250 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v20 = *((_DWORD *)this + 27);
      v19 = "RefreshWTSConnectionProperties";
      LODWORD(v21) = 1480;
      v18 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      LODWORD(v22) = v15;
      v17 = "The protocol stack did not return the HiDef support property";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)qword_180039BD0,
        v7,
        v8,
        (const unsigned __int16 **)&v17,
        (__int64)&v22,
        (const unsigned __int16 **)&v18,
        (__int64)&v21,
        (const unsigned __int16 **)&v19,
        (__int64)&v20);
    }
    goto LABEL_27;
  }
LABEL_25:
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v20 = *((_DWORD *)this + 27);
    v21 = "Failed to read the WTS properties - stack not connected (sessionId=%d).";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_180039B99,
      v7,
      v8,
      (const unsigned __int16 **)&v21,
      (__int64)&v20);
  }
LABEL_27:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180011c84  mov     [rsp-28h+arg_0], rbx
0x180011c89  push    rbp
0x180011c8a  push    rdi
0x180011c8b  push    r12
0x180011c8d  push    r14
0x180011c8f  push    r15
0x180011c91  mov     rbp, rsp
0x180011c94  sub     rsp, 70h
0x180011c98  mov     rdi, rcx
0x180011c9b  mov     [rbp+var_20], 0
0x180011ca3  or      ecx, 0FFFFFFFFh
0x180011ca6  lea     r8, [rbp+var_20]
0x180011caa  lea     rdx, PROPERTY_TYPE_CORRELATIONID_GUID
0x180011cb1  call    cs:__imp_WinStationGetConnectionProperty
0x180011cb7  mov     r14d, 4
0x180011cbd  lea     r15, aRefreshwtsconn; "RefreshWTSConnectionProperties"
0x180011cc4  lea     r12, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180011ccb  test    al, al
0x180011ccd  jz      loc_180011DBF
0x180011cd3  mov     rax, [rbp+var_20]
0x180011cd7  xor     ebx, ebx
0x180011cd9  cmp     r14w, [rax]
0x180011cdd  jnz     short loc_180011D38
0x180011cdf  movups  xmm0, xmmword ptr [rax+8]
0x180011ce3  movdqu  xmmword ptr [rdi+5Ch], xmm0
0x180011ce8  mov     eax, cs:dword_180044008
0x180011cee  cmp     eax, r14d
0x180011cf1  jbe     loc_180011DAC
0x180011cf7  mov     eax, [rdi+6Ch]
0x180011cfa  lea     rdx, word_180039D8A
0x180011d01  mov     [rbp+arg_8], eax
0x180011d04  mov     eax, [rdi+5Ch]
0x180011d07  mov     [rbp+arg_10], rax
0x180011d0b  lea     rax, aTheProtocolSta_4; "The protocol stack returned the activit"...
0x180011d12  mov     [rbp+arg_18], rax
0x180011d16  lea     rax, [rbp+arg_8]
0x180011d1a  mov     [rsp+70h+var_40], rax
0x180011d1f  lea     rax, [rbp+arg_10]
0x180011d23  mov     [rsp+70h+var_48], rax
0x180011d28  lea     rax, [rbp+arg_18]
0x180011d2c  mov     [rsp+70h+var_50], rax
0x180011d31  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180011d36  jmp     short loc_180011DAC
0x180011d38  mov     eax, cs:dword_180044008
0x180011d3e  cmp     eax, 2
0x180011d41  jbe     short loc_180011DAC
0x180011d43  mov     eax, [rdi+6Ch]
0x180011d46  lea     rdx, byte_180039D2F
0x180011d4d  mov     [rbp+arg_8], eax
0x180011d50  lea     rax, aTheProtocolSta_3; "The protocol stack return an invalid pr"...
0x180011d57  mov     [rbp+var_8], rax
0x180011d5b  lea     rax, [rbp+arg_8]
0x180011d5f  mov     [rsp+70h+var_28], rax
0x180011d64  lea     rax, [rbp+var_18]
0x180011d68  mov     [rsp+70h+var_30], rax
0x180011d6d  lea     rax, [rbp+arg_10]
0x180011d71  mov     [rsp+70h+var_38], rax
0x180011d76  lea     rax, [rbp+var_10]
0x180011d7a  mov     [rsp+70h+var_40], rax
0x180011d7f  lea     rax, [rbp+arg_18]
0x180011d83  mov     [rsp+70h+var_48], rax
0x180011d88  lea     rax, [rbp+var_8]
0x180011d8c  mov     [rsp+70h+var_50], rax
0x180011d91  mov     [rbp+var_18], r15
0x180011d95  mov     dword ptr [rbp+arg_10], 586h
0x180011d9c  mov     [rbp+var_10], r12
0x180011da0  mov     dword ptr [rbp+arg_18], 8000FFFFh
0x180011da7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180011dac  mov     rcx, [rbp+var_20]
0x180011db0  call    cs:__imp_WinStationFreePropertyValue
0x180011db6  mov     [rbp+var_20], rbx
0x180011dba  jmp     loc_180011E52
0x180011dbf  call    cs:__imp_GetLastError
0x180011dc5  mov     ebx, eax
0x180011dc7  cmp     eax, 8CAh
0x180011dcc  jz      loc_180011F83
0x180011dd2  mov     eax, cs:dword_180044008
0x180011dd8  cmp     eax, 2
0x180011ddb  jbe     short loc_180011E52
0x180011ddd  mov     eax, [rdi+6Ch]
0x180011de0  mov     [rbp+arg_8], eax
0x180011de3  mov     [rbp+var_8], r15
0x180011de7  mov     dword ptr [rbp+arg_10], 595h
0x180011dee  mov     [rbp+var_10], r12
0x180011df2  test    ebx, ebx
0x180011df4  jg      short loc_180011DFA
0x180011df6  mov     eax, ebx
0x180011df8  jmp     short loc_180011E02
0x180011dfa  movzx   eax, bx
0x180011dfd  or      eax, 80070000h
0x180011e02  mov     dword ptr [rbp+arg_18], eax
0x180011e05  lea     rdx, dword_180039CD4
0x180011e0c  lea     rax, aTheProtocolSta_2; "The protocol stack did not return the a"...
0x180011e13  mov     [rbp+var_18], rax
0x180011e17  lea     rax, [rbp+arg_8]
0x180011e1b  mov     [rsp+70h+var_28], rax
0x180011e20  lea     rax, [rbp+var_8]
0x180011e24  mov     [rsp+70h+var_30], rax
0x180011e29  lea     rax, [rbp+arg_10]
0x180011e2d  mov     [rsp+70h+var_38], rax
0x180011e32  lea     rax, [rbp+var_10]
0x180011e36  mov     [rsp+70h+var_40], rax
0x180011e3b  lea     rax, [rbp+arg_18]
0x180011e3f  mov     [rsp+70h+var_48], rax
0x180011e44  lea     rax, [rbp+var_18]
0x180011e48  mov     [rsp+70h+var_50], rax
0x180011e4d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180011e52  lea     r8, [rbp+var_20]
0x180011e56  or      ecx, 0FFFFFFFFh
0x180011e59  lea     rdx, PROPERTY_TYPE_GET_REMOTEAPP_HD_SUPPORT_LEVEL
0x180011e60  call    cs:__imp_WinStationGetConnectionProperty
0x180011e66  test    al, al
0x180011e68  jz      loc_180011FE1
0x180011e6e  mov     rax, [rbp+var_20]
0x180011e72  mov     ecx, 1
0x180011e77  cmp     cx, [rax]
0x180011e7a  jnz     short loc_180011EF5
0x180011e7c  mov     eax, [rax+8]
0x180011e7f  cmp     eax, 3
0x180011e82  ja      short loc_180011EF5
0x180011e84  mov     [rdi+74h], eax
0x180011e87  mov     eax, cs:dword_180044008
0x180011e8d  cmp     eax, r14d
0x180011e90  jbe     short loc_180011ED0
0x180011e92  mov     eax, [rdi+6Ch]
0x180011e95  lea     rdx, word_180039C86
0x180011e9c  mov     [rbp+arg_8], eax
0x180011e9f  mov     eax, [rdi+74h]
0x180011ea2  mov     dword ptr [rbp+arg_10], eax
0x180011ea5  lea     rax, aTheProtocolSta_1; "The protocol stack returned HiDef suppo"...
0x180011eac  mov     [rbp+arg_18], rax
0x180011eb0  lea     rax, [rbp+arg_8]
0x180011eb4  mov     [rsp+70h+var_40], rax
0x180011eb9  lea     rax, [rbp+arg_10]
0x180011ebd  mov     [rsp+70h+var_48], rax
0x180011ec2  lea     rax, [rbp+arg_18]
0x180011ec6  mov     [rsp+70h+var_50], rax
0x180011ecb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011ed0  cmp     dword ptr [rdi+74h], 0
0x180011ed4  jz      loc_180011F69
0x180011eda  mov     rcx, [rdi+28h]
0x180011ede  test    rcx, rcx
0x180011ee1  jz      loc_180011F69
0x180011ee7  mov     rax, [rcx]
0x180011eea  mov     rax, [rax+68h]
0x180011eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ef3  jmp     short loc_180011F69
0x180011ef5  mov     eax, cs:dword_180044008
0x180011efb  cmp     eax, 2
0x180011efe  jbe     short loc_180011F69
0x180011f00  mov     eax, [rdi+6Ch]
0x180011f03  lea     rdx, byte_180039C2B
0x180011f0a  mov     [rbp+arg_8], eax
0x180011f0d  lea     rax, aTheProtocolSta_0; "The protocol stack return an invalid pr"...
0x180011f14  mov     [rbp+var_18], rax
0x180011f18  lea     rax, [rbp+arg_8]
0x180011f1c  mov     [rsp+70h+var_28], rax
0x180011f21  lea     rax, [rbp+var_8]
0x180011f25  mov     [rsp+70h+var_30], rax
0x180011f2a  lea     rax, [rbp+arg_10]
0x180011f2e  mov     [rsp+70h+var_38], rax
0x180011f33  lea     rax, [rbp+var_10]
0x180011f37  mov     [rsp+70h+var_40], rax
0x180011f3c  lea     rax, [rbp+arg_18]
0x180011f40  mov     [rsp+70h+var_48], rax
0x180011f45  lea     rax, [rbp+var_18]
0x180011f49  mov     [rsp+70h+var_50], rax
0x180011f4e  mov     [rbp+var_8], r15
0x180011f52  mov     dword ptr [rbp+arg_10], 5B8h
0x180011f59  mov     [rbp+var_10], r12
0x180011f5d  mov     dword ptr [rbp+arg_18], 8000FFFFh
0x180011f64  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180011f69  mov     rcx, [rbp+var_20]
0x180011f6d  call    cs:__imp_WinStationFreePropertyValue
0x180011f73  mov     [rbp+var_20], 0
0x180011f7b  cmp     ebx, 8CAh
0x180011f81  jnz     short loc_180011FBD
0x180011f83  mov     eax, cs:dword_180044008
0x180011f89  cmp     eax, r14d
0x180011f8c  jbe     short loc_180011FBD
0x180011f8e  mov     eax, [rdi+6Ch]
0x180011f91  lea     rdx, byte_180039B99
0x180011f98  mov     [rbp+arg_8], eax
0x180011f9b  lea     rax, aFailedToReadTh; "Failed to read the WTS properties - sta"...
0x180011fa2  mov     [rbp+arg_10], rax
0x180011fa6  lea     rax, [rbp+arg_8]
0x180011faa  mov     [rsp+70h+var_48], rax
0x180011faf  lea     rax, [rbp+arg_10]
0x180011fb3  mov     [rsp+70h+var_50], rax
0x180011fb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180011fbd  test    ebx, ebx
0x180011fbf  jle     short loc_180011FCA
0x180011fc1  movzx   ebx, bx
0x180011fc4  or      ebx, 80070000h
0x180011fca  mov     eax, ebx
0x180011fcc  mov     rbx, [rsp+70h+arg_0]
0x180011fd4  add     rsp, 70h
0x180011fd8  pop     r15
0x180011fda  pop     r14
0x180011fdc  pop     r12
0x180011fde  pop     rdi
0x180011fdf  pop     rbp
0x180011fe0  retn
0x180011fe1  call    cs:__imp_GetLastError
0x180011fe7  mov     ebx, eax
0x180011fe9  cmp     eax, 8CAh
0x180011fee  jz      short loc_180011F83
0x180011ff0  mov     eax, cs:dword_180044008
0x180011ff6  cmp     eax, 2
0x180011ff9  jbe     short loc_180011FBD
0x180011ffb  mov     eax, [rdi+6Ch]
0x180011ffe  mov     [rbp+arg_8], eax
0x180012001  mov     [rbp+var_8], r15
0x180012005  mov     dword ptr [rbp+arg_10], 5C8h
0x18001200c  mov     [rbp+var_10], r12
0x180012010  test    ebx, ebx
0x180012012  jg      short loc_180012018
0x180012014  mov     eax, ebx
0x180012016  jmp     short loc_180012020
0x180012018  movzx   eax, bx
0x18001201b  or      eax, 80070000h
0x180012020  mov     dword ptr [rbp+arg_18], eax
0x180012023  lea     rdx, qword_180039BD0
0x18001202a  lea     rax, aTheProtocolSta; "The protocol stack did not return the H"...
0x180012031  mov     [rbp+var_18], rax
0x180012035  lea     rax, [rbp+arg_8]
0x180012039  mov     [rsp+70h+var_28], rax
0x18001203e  lea     rax, [rbp+var_8]
0x180012042  mov     [rsp+70h+var_30], rax
0x180012047  lea     rax, [rbp+arg_10]
0x18001204b  mov     [rsp+70h+var_38], rax
0x180012050  lea     rax, [rbp+var_10]
0x180012054  mov     [rsp+70h+var_40], rax
0x180012059  lea     rax, [rbp+arg_18]
0x18001205d  mov     [rsp+70h+var_48], rax
0x180012062  lea     rax, [rbp+var_18]
0x180012066  mov     [rsp+70h+var_50], rax
0x18001206b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180012070  jmp     loc_180011FBD
```
