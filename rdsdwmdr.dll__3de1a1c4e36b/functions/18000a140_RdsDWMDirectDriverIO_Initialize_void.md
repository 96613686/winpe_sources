# RdsDWMDirectDriverIO::Initialize(void)

- ea: `0x18000a140`
- end: `0x18000a2be`
- name: `?Initialize@RdsDWMDirectDriverIO@@MEAAJXZ`
- size: `382`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800010f8`
- `0x180001724`
- `0x180008fa4`
- `0x180009a4c`
- `0x18000a140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b0`
- `GDI32!CreateDCW` at `0x18000a19a`
- `GDI32!CreateDCW` at `0x18000a19a`

## string_xrefs

- `0x18000a1d4`: `CreateDC failed`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectDriverIO::Initialize(const WCHAR *this)
{
  const unsigned __int16 *v2; // rdx
  __int64 v3; // rcx
  signed int RDPDriverDeviceName; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  HDC DCW; // rax
  signed int LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  const char *v16; // [rsp+50h] [rbp-18h] BYREF
  const char *v17; // [rsp+58h] [rbp-10h] BYREF
  const char *v18; // [rsp+90h] [rbp+28h] BYREF
  signed int v19; // [rsp+98h] [rbp+30h] BYREF
  const char *v20; // [rsp+A0h] [rbp+38h] BYREF
  const char *v21; // [rsp+A8h] [rbp+40h] BYREF

  RDPDriverDeviceName = RdsDWMDirectDriverIO::GetRDPDriverDeviceName((RdsDWMDirectDriverIO *)(this - 4));
  if ( RDPDriverDeviceName < 0 )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v18 = "RdsDWMDirectDriverIO not running under RDPUDD!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)&byte_180038817,
        v5,
        v6,
        (const unsigned __int16 **)&v18);
    }
    if ( (unsigned int)RdsDWMDirectDriverIO::GetDxgkAdapter((RdsDWMDirectDriverIO *)(this - 4), v2)
      && (unsigned int)dword_180044008 > 4 )
    {
      v18 = "RdsDWMDirectDriverIO running under RDPIDD.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v12,
        (__int64)&word_1800387EE,
        v13,
        v14,
        (const unsigned __int16 **)&v18);
    }
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v18 = "RdsDWMDirectDriverIO running under RDPUDD.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v3,
        (__int64)byte_180038895,
        v5,
        v6,
        (const unsigned __int16 **)&v18);
    }
    DCW = CreateDCW(this + 24, this + 24, 0, 0);
    *((_QWORD *)this + 72) = DCW;
    if ( !DCW )
    {
      LastError = GetLastError();
      RDPDriverDeviceName = LastError;
      if ( LastError > 0 )
        RDPDriverDeviceName = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v18) = 445;
        v20 = "CreateDC failed";
        v19 = RDPDriverDeviceName;
        v21 = "Initialize";
        v16 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
        v17 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v9,
          (__int64)&unk_180038840,
          v10,
          v11,
          (const unsigned __int16 **)&v17,
          (__int64)&v19,
          (const unsigned __int16 **)&v16,
          (__int64)&v18,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v20);
      }
    }
  }
  return (unsigned int)RDPDriverDeviceName;
}

```

## disassembly

```asm
0x18000a140  push    rbp
0x18000a142  push    rbx
0x18000a143  push    rsi
0x18000a144  push    rdi
0x18000a145  mov     rbp, rsp
0x18000a148  sub     rsp, 68h
0x18000a14c  mov     rdi, rcx
0x18000a14f  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x18000a153  call    ?GetRDPDriverDeviceName@RdsDWMDirectDriverIO@@IEAAJXZ; RdsDWMDirectDriverIO::GetRDPDriverDeviceName(void)
0x18000a158  mov     ebx, eax
0x18000a15a  test    eax, eax
0x18000a15c  js      loc_18000A24E
0x18000a162  mov     edx, cs:dword_180044008
0x18000a168  cmp     edx, 4
0x18000a16b  jbe     short loc_18000A18D
0x18000a16d  lea     rax, aRdsdwmdirectdr_2; "RdsDWMDirectDriverIO running under RDPU"...
0x18000a174  mov     [rbp+arg_0], rax
0x18000a178  lea     rdx, byte_180038895
0x18000a17f  lea     rax, [rbp+arg_0]
0x18000a183  mov     [rsp+68h+var_48], rax
0x18000a188  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000a18d  lea     rcx, [rdi+30h]; pwszDriver
0x18000a191  xor     r9d, r9d; pdm
0x18000a194  mov     rdx, rcx; pwszDevice
0x18000a197  xor     r8d, r8d; pszPort
0x18000a19a  call    cs:__imp_CreateDCW
0x18000a1a0  mov     [rdi+240h], rax
0x18000a1a7  test    rax, rax
0x18000a1aa  jnz     loc_18000A2B3
0x18000a1b0  call    cs:__imp_GetLastError
0x18000a1b6  mov     ebx, eax
0x18000a1b8  test    eax, eax
0x18000a1ba  jle     short loc_18000A1C5
0x18000a1bc  movzx   ebx, ax
0x18000a1bf  or      ebx, 80070000h
0x18000a1c5  mov     eax, cs:dword_180044008
0x18000a1cb  cmp     eax, 2
0x18000a1ce  jbe     loc_18000A2B3
0x18000a1d4  lea     rax, aCreatedcFailed; "CreateDC failed"
0x18000a1db  mov     dword ptr [rbp+arg_0], 1BDh
0x18000a1e2  mov     [rbp+arg_10], rax
0x18000a1e6  lea     rdx, unk_180038840
0x18000a1ed  lea     rax, aInitialize; "Initialize"
0x18000a1f4  mov     [rbp+arg_8], ebx
0x18000a1f7  mov     [rbp+arg_18], rax
0x18000a1fb  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000a202  mov     [rbp+var_18], rax
0x18000a206  lea     rax, aErrorCondition; "Error condition failed"
0x18000a20d  mov     [rbp+var_10], rax
0x18000a211  lea     rax, [rbp+arg_10]
0x18000a215  mov     [rsp+68h+var_20], rax
0x18000a21a  lea     rax, [rbp+arg_18]
0x18000a21e  mov     [rsp+68h+var_28], rax
0x18000a223  lea     rax, [rbp+arg_0]
0x18000a227  mov     [rsp+68h+var_30], rax
0x18000a22c  lea     rax, [rbp+var_18]
0x18000a230  mov     [rsp+68h+var_38], rax
0x18000a235  lea     rax, [rbp+arg_8]
0x18000a239  mov     [rsp+68h+var_40], rax
0x18000a23e  lea     rax, [rbp+var_10]
0x18000a242  mov     [rsp+68h+var_48], rax
0x18000a247  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000a24c  jmp     short loc_18000A2B3
0x18000a24e  mov     eax, cs:dword_180044008
0x18000a254  cmp     eax, 4
0x18000a257  jbe     short loc_18000A279
0x18000a259  lea     rax, aRdsdwmdirectdr_0; "RdsDWMDirectDriverIO not running under "...
0x18000a260  mov     [rbp+arg_0], rax
0x18000a264  lea     rdx, byte_180038817
0x18000a26b  lea     rax, [rbp+arg_0]
0x18000a26f  mov     [rsp+68h+var_48], rax
0x18000a274  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000a279  lea     rcx, [rdi-8]; this
0x18000a27d  call    ?GetDxgkAdapter@RdsDWMDirectDriverIO@@IEAAHPEBG@Z; RdsDWMDirectDriverIO::GetDxgkAdapter(ushort const *)
0x18000a282  test    eax, eax
0x18000a284  jz      short loc_18000A2B1
0x18000a286  mov     eax, cs:dword_180044008
0x18000a28c  cmp     eax, 4
0x18000a28f  jbe     short loc_18000A2B1
0x18000a291  lea     rax, aRdsdwmdirectdr_1; "RdsDWMDirectDriverIO running under RDPI"...
0x18000a298  mov     [rbp+arg_0], rax
0x18000a29c  lea     rdx, word_1800387EE
0x18000a2a3  lea     rax, [rbp+arg_0]
0x18000a2a7  mov     [rsp+68h+var_48], rax
0x18000a2ac  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000a2b1  xor     ebx, ebx
0x18000a2b3  mov     eax, ebx
0x18000a2b5  add     rsp, 68h
0x18000a2b9  pop     rdi
0x18000a2ba  pop     rsi
0x18000a2bb  pop     rbx
0x18000a2bc  pop     rbp
0x18000a2bd  retn
```
