# RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk(RdpDWMDirectWindowContext *)

- ea: `0x1800103d8`
- end: `0x180010543`
- name: `?ProcessDestroyVailSuperWetInk@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@@Z`
- size: `363`
- prototype: `int(RdsDWMDirectUpdateProcessor *__hidden this, struct RdpDWMDirectWindowContext *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180010a30`

## callees

- `0x180001724`
- `0x180001bfc`
- `0x18000de24`
- `0x1800103d8`

## string_xrefs

- `0x180010428`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800104e6`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010483`: `RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk(
        __int64 this,
        struct RdpDWMDirectWindowContext *a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // ebx
  __int16 *v6; // rdx
  const unsigned __int16 **v7; // rax
  const unsigned __int16 **v9; // [rsp+30h] [rbp-38h]
  const char *v10; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp-10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF
  const char *v13; // [rsp+88h] [rbp+20h] BYREF
  const char *v14; // [rsp+90h] [rbp+28h] BYREF
  const char *v15; // [rsp+98h] [rbp+30h] BYREF

  v12 = this;
  if ( a2 )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v12 = *((_QWORD *)a2 + 8);
      v13 = "RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        this,
        (__int64)&byte_18003A0A7,
        a3,
        a4,
        (const unsigned __int16 **)&v13,
        (__int64)&v12);
    }
    v5 = RdpDWMDirectWindowContext::DestroyVailSuperWetInk(a2, (__int64)a2, a3, a4);
    if ( v5 < 0 )
    {
      this = (unsigned int)dword_180044008;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v12) = 1148;
        v14 = "Failed to send destroy vail super wet ink object message";
        v6 = word_18003A05A;
        v15 = "ProcessDestroyVailSuperWetInk";
        v11[0] = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v10 = "Error HResult failed";
        v9 = (const unsigned __int16 **)v11;
        v7 = (const unsigned __int16 **)&v10;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v5 = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      LODWORD(v12) = 1137;
      v14 = "No target window for the destroy vail super wet ink message.";
      v6 = word_18003A0D2;
      v15 = "ProcessDestroyVailSuperWetInk";
      v10 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v11[0] = "Error condition failed";
      v9 = (const unsigned __int16 **)&v10;
      v7 = (const unsigned __int16 **)v11;
LABEL_9:
      LODWORD(v13) = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        this,
        (__int64)v6,
        a3,
        a4,
        v7,
        (__int64)&v13,
        v9,
        (__int64)&v12,
        (const unsigned __int16 **)&v15,
        (const unsigned __int16 **)&v14);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800103d8  mov     r11, rsp
0x1800103db  mov     [r11+8], rcx
0x1800103df  push    rbp
0x1800103e0  push    rbx
0x1800103e1  mov     rbp, rsp
0x1800103e4  sub     rsp, 68h
0x1800103e8  mov     eax, cs:dword_180044008
0x1800103ee  mov     rbx, rdx
0x1800103f1  test    rdx, rdx
0x1800103f4  jnz     short loc_18001046F
0x1800103f6  mov     ebx, 8000FFFFh
0x1800103fb  cmp     eax, 2
0x1800103fe  jbe     loc_18001053A
0x180010404  lea     rax, aNoTargetWindow_2; "No target window for the destroy vail s"...
0x18001040b  mov     dword ptr [rbp+arg_0], 471h
0x180010412  mov     [rbp+arg_10], rax
0x180010416  lea     rdx, word_18003A0D2
0x18001041d  lea     rax, aProcessdestroy; "ProcessDestroyVailSuperWetInk"
0x180010424  mov     [rbp+arg_18], rax
0x180010428  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18001042f  mov     [rbp+var_18], rax
0x180010433  lea     rax, aErrorCondition; "Error condition failed"
0x18001043a  mov     [rbp+var_10], rax
0x18001043e  lea     rax, [rbp+arg_10]
0x180010442  mov     [r11-30h], rax
0x180010446  lea     rax, [rbp+arg_18]
0x18001044a  mov     [r11-38h], rax
0x18001044e  lea     rax, [rbp+arg_0]
0x180010452  mov     [r11-40h], rax
0x180010456  lea     rax, [rbp+var_18]
0x18001045a  mov     [r11-48h], rax
0x18001045e  lea     rax, [rbp+arg_8]
0x180010462  mov     [r11-50h], rax
0x180010466  lea     rax, [rbp+var_10]
0x18001046a  jmp     loc_18001052D
0x18001046f  cmp     eax, 5
0x180010472  jbe     short loc_1800104A5
0x180010474  mov     rax, [rdx+40h]
0x180010478  lea     rdx, byte_18003A0A7
0x18001047f  mov     [rbp+arg_0], rax
0x180010483  lea     rax, aRdsdwmdirectup_2; "RdsDWMDirectUpdateProcessor::ProcessDes"...
0x18001048a  mov     [rbp+arg_8], rax
0x18001048e  lea     rax, [rbp+arg_0]
0x180010492  mov     [rsp+68h+var_40], rax
0x180010497  lea     rax, [rbp+arg_8]
0x18001049b  mov     [rsp+68h+var_48], rax
0x1800104a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800104a5  mov     rcx, rbx; this
0x1800104a8  call    ?DestroyVailSuperWetInk@RdpDWMDirectWindowContext@@QEAAJXZ; RdpDWMDirectWindowContext::DestroyVailSuperWetInk(void)
0x1800104ad  mov     ebx, eax
0x1800104af  test    eax, eax
0x1800104b1  jns     loc_18001053A
0x1800104b7  mov     ecx, cs:dword_180044008
0x1800104bd  cmp     ecx, 2
0x1800104c0  jbe     short loc_18001053A
0x1800104c2  lea     rax, aFailedToSendDe; "Failed to send destroy vail super wet i"...
0x1800104c9  mov     dword ptr [rbp+arg_0], 47Ch
0x1800104d0  mov     [rbp+arg_10], rax
0x1800104d4  lea     rdx, word_18003A05A
0x1800104db  lea     rax, aProcessdestroy; "ProcessDestroyVailSuperWetInk"
0x1800104e2  mov     [rbp+arg_18], rax
0x1800104e6  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800104ed  mov     [rbp+var_10], rax
0x1800104f1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800104f8  mov     [rbp+var_18], rax
0x1800104fc  lea     rax, [rbp+arg_10]
0x180010500  mov     [rsp+68h+var_20], rax
0x180010505  lea     rax, [rbp+arg_18]
0x180010509  mov     [rsp+68h+var_28], rax
0x18001050e  lea     rax, [rbp+arg_0]
0x180010512  mov     [rsp+68h+var_30], rax
0x180010517  lea     rax, [rbp+var_10]
0x18001051b  mov     [rsp+68h+var_38], rax
0x180010520  lea     rax, [rbp+arg_8]
0x180010524  mov     [rsp+68h+var_40], rax
0x180010529  lea     rax, [rbp+var_18]
0x18001052d  mov     [rsp+68h+var_48], rax
0x180010532  mov     dword ptr [rbp+arg_8], ebx
0x180010535  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001053a  mov     eax, ebx
0x18001053c  add     rsp, 68h
0x180010540  pop     rbx
0x180010541  pop     rbp
0x180010542  retn
```
