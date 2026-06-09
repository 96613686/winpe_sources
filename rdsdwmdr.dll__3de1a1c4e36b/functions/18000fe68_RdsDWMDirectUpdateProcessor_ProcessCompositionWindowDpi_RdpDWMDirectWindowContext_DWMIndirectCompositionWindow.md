# RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi(RdpDWMDirectWindowContext *,_DWMIndirectCompositionWindowDpiMetadata *)

- ea: `0x18000fe68`
- end: `0x18000ffe9`
- name: `?ProcessCompositionWindowDpi@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionWindowDpiMetadata@@@Z`
- size: `385`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *, struct _DWMIndirectCompositionWindowDpiMetadata *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001ca4`
- `0x18000cde8`
- `0x18000fe68`

## string_xrefs

- `0x18000febc`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000ff8b`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18000feb1`: `ProcessCompositionWindowDpi`
- `0x18000ff80`: `ProcessCompositionWindowDpi`
- `0x18000ff1d`: `RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        struct _DWMIndirectCompositionWindowDpiMetadata *a3,
        __int64 a4)
{
  int v6; // ebx
  char *v7; // rdx
  const unsigned __int16 **v8; // rax
  const unsigned __int16 **v10; // [rsp+40h] [rbp-30h]
  const char *v11; // [rsp+50h] [rbp-20h] BYREF
  const char *v12; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  __int64 v15; // [rsp+98h] [rbp+28h] BYREF
  const char *v16; // [rsp+A8h] [rbp+38h] BYREF

  v14 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      LODWORD(v14) = *(_DWORD *)a3;
      v15 = *((_QWORD *)a2 + 8);
      v16 = "RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        this,
        (__int64)&word_180039FBE,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
    v6 = RdpDWMDirectWindowContext::CompositionWindowDpi(a2, *(_DWORD *)a3, (__int64)a3, a4);
    if ( v6 < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v14) = 1188;
        v16 = "Failed to send window dpi message";
        v7 = byte_180039F71;
        v13[0] = "ProcessCompositionWindowDpi";
        v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v11 = "Error HResult failed";
        v10 = (const unsigned __int16 **)v13;
        v8 = (const unsigned __int16 **)&v11;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v14) = 1176;
      v16 = "No target window for the window dpi message.";
      v7 = byte_18003A00D;
      v11 = "ProcessCompositionWindowDpi";
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v13[0] = "Error condition failed";
      v10 = (const unsigned __int16 **)&v11;
      v8 = (const unsigned __int16 **)v13;
LABEL_9:
      LODWORD(v15) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v7,
        (__int64)a3,
        a4,
        v8,
        (__int64)&v15,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        v10,
        (const unsigned __int16 **)&v16);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000fe68  mov     r11, rsp
0x18000fe6b  mov     [r11+8], rcx
0x18000fe6f  push    rbp
0x18000fe70  push    rbx
0x18000fe71  push    rdi
0x18000fe72  mov     rbp, rsp
0x18000fe75  sub     rsp, 70h
0x18000fe79  mov     eax, cs:dword_180044008
0x18000fe7f  mov     rdi, r8
0x18000fe82  mov     rbx, rdx
0x18000fe85  test    rdx, rdx
0x18000fe88  jnz     short loc_18000FF03
0x18000fe8a  mov     ebx, 8000FFFFh
0x18000fe8f  cmp     eax, 2
0x18000fe92  jbe     loc_18000FFDF
0x18000fe98  lea     rax, aNoTargetWindow_0; "No target window for the window dpi mes"...
0x18000fe9f  mov     dword ptr [rbp+arg_0], 498h
0x18000fea6  mov     [rbp+arg_18], rax
0x18000feaa  lea     rdx, byte_18003A00D
0x18000feb1  lea     rax, aProcesscomposi; "ProcessCompositionWindowDpi"
0x18000feb8  mov     [rbp+var_20], rax
0x18000febc  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000fec3  mov     [rbp+var_18], rax
0x18000fec7  lea     rax, aErrorCondition; "Error condition failed"
0x18000fece  mov     [rbp+var_10], rax
0x18000fed2  lea     rax, [rbp+arg_18]
0x18000fed6  mov     [r11-40h], rax
0x18000feda  lea     rax, [rbp+var_20]
0x18000fede  mov     [r11-48h], rax
0x18000fee2  lea     rax, [rbp+arg_0]
0x18000fee6  mov     [r11-50h], rax
0x18000feea  lea     rax, [rbp+var_18]
0x18000feee  mov     [r11-58h], rax
0x18000fef2  lea     rax, [rbp+arg_8]
0x18000fef6  mov     [r11-60h], rax
0x18000fefa  lea     rax, [rbp+var_10]
0x18000fefe  jmp     loc_18000FFD2
0x18000ff03  cmp     eax, 5
0x18000ff06  jbe     short loc_18000FF48
0x18000ff08  mov     eax, [r8]
0x18000ff0b  mov     dword ptr [rbp+arg_0], eax
0x18000ff0e  mov     rax, [rdx+40h]
0x18000ff12  lea     rdx, word_180039FBE
0x18000ff19  mov     [rbp+arg_8], rax
0x18000ff1d  lea     rax, aRdsdwmdirectup_7; "RdsDWMDirectUpdateProcessor::ProcessCom"...
0x18000ff24  mov     [rbp+arg_18], rax
0x18000ff28  lea     rax, [rbp+arg_0]
0x18000ff2c  mov     [rsp+70h+var_40], rax
0x18000ff31  lea     rax, [rbp+arg_8]
0x18000ff35  mov     [rsp+70h+var_48], rax
0x18000ff3a  lea     rax, [rbp+arg_18]
0x18000ff3e  mov     [rsp+70h+var_50], rax
0x18000ff43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000ff48  mov     edx, [rdi]; unsigned int
0x18000ff4a  mov     rcx, rbx; this
0x18000ff4d  call    ?CompositionWindowDpi@RdpDWMDirectWindowContext@@QEAAJI@Z; RdpDWMDirectWindowContext::CompositionWindowDpi(uint)
0x18000ff52  mov     ebx, eax
0x18000ff54  test    eax, eax
0x18000ff56  jns     loc_18000FFDF
0x18000ff5c  mov     ecx, cs:dword_180044008
0x18000ff62  cmp     ecx, 2
0x18000ff65  jbe     short loc_18000FFDF
0x18000ff67  lea     rax, aFailedToSendWi_0; "Failed to send window dpi message"
0x18000ff6e  mov     dword ptr [rbp+arg_0], 4A4h
0x18000ff75  mov     [rbp+arg_18], rax
0x18000ff79  lea     rdx, byte_180039F71
0x18000ff80  lea     rax, aProcesscomposi; "ProcessCompositionWindowDpi"
0x18000ff87  mov     [rbp+var_10], rax
0x18000ff8b  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000ff92  mov     [rbp+var_18], rax
0x18000ff96  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000ff9d  mov     [rbp+var_20], rax
0x18000ffa1  lea     rax, [rbp+arg_18]
0x18000ffa5  mov     [rsp+70h+var_28], rax
0x18000ffaa  lea     rax, [rbp+var_10]
0x18000ffae  mov     [rsp+70h+var_30], rax
0x18000ffb3  lea     rax, [rbp+arg_0]
0x18000ffb7  mov     [rsp+70h+var_38], rax
0x18000ffbc  lea     rax, [rbp+var_18]
0x18000ffc0  mov     [rsp+70h+var_40], rax
0x18000ffc5  lea     rax, [rbp+arg_8]
0x18000ffc9  mov     [rsp+70h+var_48], rax
0x18000ffce  lea     rax, [rbp+var_20]
0x18000ffd2  mov     [rsp+70h+var_50], rax
0x18000ffd7  mov     dword ptr [rbp+arg_8], ebx
0x18000ffda  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000ffdf  mov     eax, ebx
0x18000ffe1  add     rsp, 70h
0x18000ffe5  pop     rdi
0x18000ffe6  pop     rbx
0x18000ffe7  pop     rbp
0x18000ffe8  retn
```
