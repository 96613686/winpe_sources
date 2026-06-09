# CloudAPHelper::GetServerNonce(ushort * *)

- ea: `0x180093de0`
- end: `0x1800943ac`
- name: `?GetServerNonce@CloudAPHelper@@UEAAJPEAPEAG@Z`
- size: `1484`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180005090`
- `0x180019a80`
- `0x180078820`
- `0x180090460`
- `0x1800937cc`
- `0x180093de0`
- `0x180162010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18009437f`
- `SspiCli!LsaFreeReturnBuffer` at `0x18009437f`

## string_xrefs

- `0x180093ed5`: `GetInstanceOfJsonHelper failed`
- `0x1800940b7`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x180093e61`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180093ef9`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180093fa0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009403f`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800940db`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094214`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800942b6`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009432b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180093f7c`: `spJsonHelper->SetValue(call) failed`
- `0x18009401b`: `spJsonHelper->SetValue(correlationId) failed`
- `0x1800941f0`: `spJsonHelper->SetJsonString failed`
- `0x180094292`: `spJsonHelper->GetValue(ts_nonce) failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::GetServerNonce(CloudAPHelper *this, unsigned __int16 **a2, int a3, int a4)
{
  CloudAPHelper *v5; // r14
  int InstanceOfJsonHelper; // ebx
  char *v7; // rdx
  const char **v8; // rax
  struct IJsonHelper *v9; // rdi
  int v10; // ecx
  unsigned int v11; // r8d
  int v12; // r9d
  const char **v14; // [rsp+38h] [rbp-29h]
  const char **v15; // [rsp+48h] [rbp-19h]
  const char **v16; // [rsp+50h] [rbp-11h]
  int v17; // [rsp+58h] [rbp-9h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-1h] BYREF
  void *Block; // [rsp+68h] [rbp+7h] BYREF
  struct IJsonHelper *v20; // [rsp+70h] [rbp+Fh] BYREF
  const char *v21; // [rsp+78h] [rbp+17h] BYREF
  const char *v22; // [rsp+80h] [rbp+1Fh] BYREF
  const char *v23; // [rsp+88h] [rbp+27h] BYREF
  _QWORD v24[5]; // [rsp+90h] [rbp+2Fh] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+6Fh] BYREF
  unsigned int v26; // [rsp+D8h] [rbp+77h] BYREF
  int v27; // [rsp+E0h] [rbp+7Fh] BYREF

  v20 = 0;
  Block = 0;
  v5 = this;
  v25 = 0;
  Buffer = 0;
  v26 = 0;
  if ( !a2 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_30;
    v27 = 169;
    v21 = "Missing paramter ppNonce";
    v7 = byte_1801AF9FB;
    v22 = "GetServerNonce";
    v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
    v24[0] = "Error condition failed";
    v16 = &v21;
    v15 = &v22;
    v14 = &v23;
    v8 = (const char **)v24;
    goto LABEL_4;
  }
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v20);
  if ( InstanceOfJsonHelper >= 0 )
  {
    v9 = v20;
    InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *))(*(_QWORD *)v20 + 104LL))(
                             v20,
                             L"call");
    if ( InstanceOfJsonHelper >= 0 )
    {
      InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, __int64))(*(_QWORD *)v9 + 120LL))(
                               v9,
                               L"correlationId",
                               (__int64)v5 + 72);
      if ( InstanceOfJsonHelper >= 0 )
      {
        InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, void **, unsigned int *))(*(_QWORD *)v9 + 48LL))(
                                 v9,
                                 &Block,
                                 &v25);
        if ( InstanceOfJsonHelper >= 0 )
        {
          InstanceOfJsonHelper = CloudAPHelper::CallCloudAP(v5, (unsigned __int8 *)Block, v25, &Buffer, &v26);
          if ( InstanceOfJsonHelper >= 0 )
          {
            if ( Buffer && (v11 = v26) != 0 )
            {
              InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v9 + 56LL))(v9);
              if ( InstanceOfJsonHelper >= 0 )
              {
                InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v9 + 88LL))(
                                         v9,
                                         L"ts_nonce",
                                         a2);
                if ( InstanceOfJsonHelper < 0 && (unsigned int)CallbackContext > 2 )
                {
                  v27 = 207;
                  v24[0] = "spJsonHelper->GetValue(ts_nonce) failed";
                  v7 = byte_1801AF7A5;
                  v23 = "GetServerNonce";
                  v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v21 = "Error HResult failed";
                  v16 = (const char **)v24;
                  v15 = &v23;
                  v14 = &v22;
                  v8 = &v21;
                  goto LABEL_4;
                }
              }
              else if ( (unsigned int)CallbackContext > 2 )
              {
                v27 = 204;
                v24[0] = "spJsonHelper->SetJsonString failed";
                v7 = byte_1801AF7F3;
                v23 = "GetServerNonce";
                v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v21 = "Error HResult failed";
                v16 = (const char **)v24;
                v15 = &v23;
                v14 = &v22;
                v8 = &v21;
                goto LABEL_4;
              }
            }
            else
            {
              InstanceOfJsonHelper = -2147467259;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v27 = 194;
                v24[0] = "GetServerNonce";
                v17 = -2147467259;
                v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v22 = "CloudAP returned an empty responce to the nonce request";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v10,
                  (unsigned int)byte_1801AF841,
                  v11,
                  v12,
                  (__int64)&v22,
                  (__int64)&v17,
                  (__int64)&v23,
                  (__int64)&v27,
                  (__int64)v24);
              }
            }
          }
          else if ( (unsigned int)CallbackContext > 3 )
          {
            v27 = InstanceOfJsonHelper;
            v24[0] = "GetServerNonce";
            v23 = "CallCloudAP failed";
            v22 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v10,
              (unsigned int)&byte_1801AF887,
              v11,
              v12,
              (__int64)&v22,
              (__int64)&v23,
              (__int64)&v27,
              (__int64)v24);
          }
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = 186;
          v24[0] = "spJsonHelper->GetJsonStringAsByteArray failed";
          v7 = byte_1801AF8C3;
          v23 = "GetServerNonce";
          v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v21 = "Error HResult failed";
          v16 = (const char **)v24;
          v15 = &v23;
          v14 = &v22;
          v8 = &v21;
          goto LABEL_4;
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v27 = 183;
        v24[0] = "spJsonHelper->SetValue(correlationId) failed";
        v7 = byte_1801AF911;
        v23 = "GetServerNonce";
        v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v21 = "Error HResult failed";
        v16 = (const char **)v24;
        v15 = &v23;
        v14 = &v22;
        v8 = &v21;
        goto LABEL_4;
      }
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 180;
      v24[0] = "spJsonHelper->SetValue(call) failed";
      v7 = &byte_1801AF95F;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
      goto LABEL_4;
    }
  }
  else
  {
    LODWORD(this) = (_DWORD)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v27 = 177;
      v24[0] = "GetInstanceOfJsonHelper failed";
      v7 = byte_1801AF9AD;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
LABEL_4:
      v17 = InstanceOfJsonHelper;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v7,
        a3,
        a4,
        (__int64)v8,
        (__int64)&v17,
        (__int64)v14,
        (__int64)&v27,
        (__int64)v15,
        (__int64)v16);
    }
  }
LABEL_30:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( Block )
    operator delete(Block);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v20);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x180093de0  mov     r11, rsp
0x180093de3  push    rbp
0x180093de4  push    rbx
0x180093de5  push    rsi
0x180093de6  push    rdi
0x180093de7  push    r14
0x180093de9  lea     rbp, [r11-5Fh]
0x180093ded  sub     rsp, 90h
0x180093df4  mov     [rbp+57h+var_48], 0
0x180093dfc  mov     rsi, rdx
0x180093dff  mov     [rbp+57h+Block], 0
0x180093e07  mov     r14, rcx
0x180093e0a  mov     [rbp+57h+arg_8], 0
0x180093e11  mov     [rbp+57h+Buffer], 0
0x180093e19  mov     [rbp+57h+arg_10], 0
0x180093e20  test    rdx, rdx
0x180093e23  jnz     loc_180093EB7
0x180093e29  mov     eax, cs:CallbackContext
0x180093e2f  mov     ebx, 80070057h
0x180093e34  cmp     eax, 2
0x180093e37  jbe     loc_180094376
0x180093e3d  lea     rax, aMissingParamte; "Missing paramter ppNonce"
0x180093e44  mov     [rbp+57h+arg_18], 0A9h
0x180093e4b  mov     [rbp+57h+var_40], rax
0x180093e4f  lea     rdx, byte_1801AF9FB
0x180093e56  lea     rax, aGetservernonce; "GetServerNonce"
0x180093e5d  mov     [rbp+57h+var_38], rax
0x180093e61  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180093e68  mov     [rbp+57h+var_30], rax
0x180093e6c  lea     rax, aErrorCondition; "Error condition failed"
0x180093e73  mov     [rbp+57h+var_28], rax
0x180093e77  lea     rax, [rbp+57h+var_40]
0x180093e7b  mov     [r11-70h], rax
0x180093e7f  lea     rax, [rbp+57h+var_38]
0x180093e83  mov     [r11-78h], rax
0x180093e87  lea     rax, [rbp+57h+arg_18]
0x180093e8b  mov     [r11-80h], rax
0x180093e8f  lea     rax, [rbp+57h+var_30]
0x180093e93  mov     [rsp+0B0h+var_80], rax
0x180093e98  lea     rax, [rbp+57h+var_60]
0x180093e9c  mov     [rsp+0B0h+var_88], rax
0x180093ea1  lea     rax, [rbp+57h+var_28]
0x180093ea5  mov     [rbp+57h+var_60], ebx
0x180093ea8  mov     [rsp+0B0h+var_90], rax
0x180093ead  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180093eb2  jmp     loc_180094376
0x180093eb7  lea     rcx, [rbp+57h+var_48]; struct IJsonHelper **
0x180093ebb  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x180093ec0  mov     ebx, eax
0x180093ec2  test    eax, eax
0x180093ec4  jns     short loc_180093F45
0x180093ec6  mov     ecx, cs:CallbackContext
0x180093ecc  cmp     ecx, 2
0x180093ecf  jbe     loc_180094376
0x180093ed5  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x180093edc  mov     [rbp+57h+arg_18], 0B1h
0x180093ee3  mov     [rbp+57h+var_28], rax
0x180093ee7  lea     rdx, byte_1801AF9AD
0x180093eee  lea     rax, aGetservernonce; "GetServerNonce"
0x180093ef5  mov     [rbp+57h+var_30], rax
0x180093ef9  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180093f00  mov     [rbp+57h+var_38], rax
0x180093f04  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180093f0b  mov     [rbp+57h+var_40], rax
0x180093f0f  lea     rax, [rbp+57h+var_28]
0x180093f13  mov     [rsp+48h], rax
0x180093f18  lea     rax, [rbp+57h+var_30]
0x180093f1c  mov     [rsp+0B0h+var_70], rax
0x180093f21  lea     rax, [rbp+57h+arg_18]
0x180093f25  mov     [rsp+0B0h+var_78], rax
0x180093f2a  lea     rax, [rbp+57h+var_38]
0x180093f2e  mov     [rsp+0B0h+var_80], rax
0x180093f33  lea     rax, [rbp+57h+var_60]
0x180093f37  mov     [rsp+0B0h+var_88], rax
0x180093f3c  lea     rax, [rbp+57h+var_40]
0x180093f40  jmp     loc_180093EA5
0x180093f45  mov     rdi, [rbp+57h+var_48]
0x180093f49  lea     rdx, aCall; "call"
0x180093f50  movsd   xmm2, cs:__real@4022000000000000
0x180093f58  mov     rcx, rdi
0x180093f5b  mov     rax, [rdi]
0x180093f5e  mov     rax, [rax+68h]
0x180093f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f67  mov     ebx, eax
0x180093f69  test    eax, eax
0x180093f6b  jns     short loc_180093FEC
0x180093f6d  mov     eax, cs:CallbackContext
0x180093f73  cmp     eax, 2
0x180093f76  jbe     loc_180094376
0x180093f7c  lea     rax, aSpjsonhelperSe_2; "spJsonHelper->SetValue(call) failed"
0x180093f83  mov     [rbp+57h+arg_18], 0B4h
0x180093f8a  mov     [rbp+57h+var_28], rax
0x180093f8e  lea     rdx, byte_1801AF95F
0x180093f95  lea     rax, aGetservernonce; "GetServerNonce"
0x180093f9c  mov     [rbp+57h+var_30], rax
0x180093fa0  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180093fa7  mov     [rbp+57h+var_38], rax
0x180093fab  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180093fb2  mov     [rbp+57h+var_40], rax
0x180093fb6  lea     rax, [rbp+57h+var_28]
0x180093fba  mov     [rsp+48h], rax
0x180093fbf  lea     rax, [rbp+57h+var_30]
0x180093fc3  mov     [rsp+0B0h+var_70], rax
0x180093fc8  lea     rax, [rbp+57h+arg_18]
0x180093fcc  mov     [rsp+0B0h+var_78], rax
0x180093fd1  lea     rax, [rbp+57h+var_38]
0x180093fd5  mov     [rsp+0B0h+var_80], rax
0x180093fda  lea     rax, [rbp+57h+var_60]
0x180093fde  mov     [rsp+0B0h+var_88], rax
0x180093fe3  lea     rax, [rbp+57h+var_40]
0x180093fe7  jmp     loc_180093EA5
0x180093fec  mov     rax, [rdi]
0x180093fef  lea     r8, [r14+48h]
0x180093ff3  lea     rdx, aCorrelationid; "correlationId"
0x180093ffa  mov     rcx, rdi
0x180093ffd  mov     rax, [rax+78h]
0x180094001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094006  mov     ebx, eax
0x180094008  test    eax, eax
0x18009400a  jns     short loc_18009408B
0x18009400c  mov     eax, cs:CallbackContext
0x180094012  cmp     eax, 2
0x180094015  jbe     loc_180094376
0x18009401b  lea     rax, aSpjsonhelperSe_5; "spJsonHelper->SetValue(correlationId) f"...
0x180094022  mov     [rbp+57h+arg_18], 0B7h
0x180094029  mov     [rbp+57h+var_28], rax
0x18009402d  lea     rdx, byte_1801AF911
0x180094034  lea     rax, aGetservernonce; "GetServerNonce"
0x18009403b  mov     [rbp+57h+var_30], rax
0x18009403f  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094046  mov     [rbp+57h+var_38], rax
0x18009404a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094051  mov     [rbp+57h+var_40], rax
0x180094055  lea     rax, [rbp+57h+var_28]
0x180094059  mov     [rsp+48h], rax
0x18009405e  lea     rax, [rbp+57h+var_30]
0x180094062  mov     [rsp+0B0h+var_70], rax
0x180094067  lea     rax, [rbp+57h+arg_18]
0x18009406b  mov     [rsp+0B0h+var_78], rax
0x180094070  lea     rax, [rbp+57h+var_38]
0x180094074  mov     [rsp+0B0h+var_80], rax
0x180094079  lea     rax, [rbp+57h+var_60]
0x18009407d  mov     [rsp+0B0h+var_88], rax
0x180094082  lea     rax, [rbp+57h+var_40]
0x180094086  jmp     loc_180093EA5
0x18009408b  mov     rax, [rdi]
0x18009408e  lea     r8, [rbp+57h+arg_8]
0x180094092  lea     rdx, [rbp+57h+Block]
0x180094096  mov     rcx, rdi
0x180094099  mov     rax, [rax+30h]
0x18009409d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800940a2  mov     ebx, eax
0x1800940a4  test    eax, eax
0x1800940a6  jns     short loc_180094127
0x1800940a8  mov     eax, cs:CallbackContext
0x1800940ae  cmp     eax, 2
0x1800940b1  jbe     loc_180094376
0x1800940b7  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x1800940be  mov     [rbp+57h+arg_18], 0BAh
0x1800940c5  mov     [rbp+57h+var_28], rax
0x1800940c9  lea     rdx, byte_1801AF8C3
0x1800940d0  lea     rax, aGetservernonce; "GetServerNonce"
0x1800940d7  mov     [rbp+57h+var_30], rax
0x1800940db  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800940e2  mov     [rbp+57h+var_38], rax
0x1800940e6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800940ed  mov     [rbp+57h+var_40], rax
0x1800940f1  lea     rax, [rbp+57h+var_28]
0x1800940f5  mov     [rsp+48h], rax
0x1800940fa  lea     rax, [rbp+57h+var_30]
0x1800940fe  mov     [rsp+0B0h+var_70], rax
0x180094103  lea     rax, [rbp+57h+arg_18]
0x180094107  mov     [rsp+0B0h+var_78], rax
0x18009410c  lea     rax, [rbp+57h+var_38]
0x180094110  mov     [rsp+0B0h+var_80], rax
0x180094115  lea     rax, [rbp+57h+var_60]
0x180094119  mov     [rsp+0B0h+var_88], rax
0x18009411e  lea     rax, [rbp+57h+var_40]
0x180094122  jmp     loc_180093EA5
0x180094127  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18009412b  lea     rax, [rbp+57h+arg_10]
0x18009412f  mov     rdx, [rbp+57h+Block]; unsigned __int8 *
0x180094133  lea     r9, [rbp+57h+Buffer]; void **
0x180094137  mov     rcx, r14; this
0x18009413a  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x18009413f  call    ?CallCloudAP@CloudAPHelper@@AEAAJPEAEKPEAPEAXPEAK@Z; CloudAPHelper::CallCloudAP(uchar *,ulong,void * *,ulong *)
0x180094144  mov     ebx, eax
0x180094146  test    eax, eax
0x180094148  jns     short loc_1800941B2
0x18009414a  mov     eax, cs:CallbackContext
0x180094150  cmp     eax, 3
0x180094153  jbe     loc_180094376
0x180094159  lea     rax, aGetservernonce; "GetServerNonce"
0x180094160  mov     [rbp+57h+arg_18], ebx
0x180094163  mov     [rbp+57h+var_28], rax
0x180094167  lea     rdx, byte_1801AF887
0x18009416e  lea     rax, aCallcloudapFai; "CallCloudAP failed"
0x180094175  mov     [rbp+57h+var_30], rax
0x180094179  lea     rax, aWarningHresult; "Warning HResult failed"
0x180094180  mov     [rbp+57h+var_38], rax
0x180094184  lea     rax, [rbp+57h+var_28]
0x180094188  mov     [rsp+0B0h+var_78], rax
0x18009418d  lea     rax, [rbp+57h+arg_18]
0x180094191  mov     [rsp+0B0h+var_80], rax
0x180094196  lea     rax, [rbp+57h+var_30]
0x18009419a  mov     [rsp+0B0h+var_88], rax
0x18009419f  lea     rax, [rbp+57h+var_38]
0x1800941a3  mov     [rsp+0B0h+var_90], rax
0x1800941a8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800941ad  jmp     loc_180094376
0x1800941b2  mov     rdx, [rbp+57h+Buffer]
0x1800941b6  test    rdx, rdx
0x1800941b9  jz      loc_180094302
0x1800941bf  mov     r8d, [rbp+57h+arg_10]
0x1800941c3  test    r8d, r8d
0x1800941c6  jz      loc_180094302
0x1800941cc  mov     rax, [rdi]
0x1800941cf  mov     rcx, rdi
0x1800941d2  mov     rax, [rax+38h]
0x1800941d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941db  mov     ebx, eax
0x1800941dd  test    eax, eax
0x1800941df  jns     short loc_180094260
0x1800941e1  mov     eax, cs:CallbackContext
0x1800941e7  cmp     eax, 2
0x1800941ea  jbe     loc_180094376
0x1800941f0  lea     rax, aSpjsonhelperSe_3; "spJsonHelper->SetJsonString failed"
0x1800941f7  mov     [rbp+57h+arg_18], 0CCh
0x1800941fe  mov     [rbp+57h+var_28], rax
0x180094202  lea     rdx, byte_1801AF7F3
0x180094209  lea     rax, aGetservernonce; "GetServerNonce"
0x180094210  mov     [rbp+57h+var_30], rax
0x180094214  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18009421b  mov     [rbp+57h+var_38], rax
0x18009421f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180094226  mov     [rbp+57h+var_40], rax
0x18009422a  lea     rax, [rbp+57h+var_28]
0x18009422e  mov     [rsp+48h], rax
0x180094233  lea     rax, [rbp+57h+var_30]
0x180094237  mov     [rsp+0B0h+var_70], rax
0x18009423c  lea     rax, [rbp+57h+arg_18]
0x180094240  mov     [rsp+0B0h+var_78], rax
0x180094245  lea     rax, [rbp+57h+var_38]
0x180094249  mov     [rsp+0B0h+var_80], rax
0x18009424e  lea     rax, [rbp+57h+var_60]
0x180094252  mov     [rsp+0B0h+var_88], rax
0x180094257  lea     rax, [rbp+57h+var_40]
0x18009425b  jmp     loc_180093EA5
0x180094260  mov     rax, [rdi]
0x180094263  lea     rdx, aTsNonce; "ts_nonce"
0x18009426a  mov     r8, rsi
0x18009426d  mov     rcx, rdi
0x180094270  mov     rax, [rax+58h]
0x180094274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094279  mov     ebx, eax
0x18009427b  test    eax, eax
0x18009427d  jns     loc_180094376
0x180094283  mov     eax, cs:CallbackContext
0x180094289  cmp     eax, 2
0x18009428c  jbe     loc_180094376
0x180094292  lea     rax, aSpjsonhelperGe_0; "spJsonHelper->GetValue(ts_nonce) failed"
0x180094299  mov     [rbp+57h+arg_18], 0CFh
0x1800942a0  mov     [rbp+57h+var_28], rax
0x1800942a4  lea     rdx, byte_1801AF7A5
0x1800942ab  lea     rax, aGetservernonce; "GetServerNonce"
0x1800942b2  mov     [rbp+57h+var_30], rax
0x1800942b6  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800942bd  mov     [rbp+57h+var_38], rax
0x1800942c1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800942c8  mov     [rbp+57h+var_40], rax
0x1800942cc  lea     rax, [rbp+57h+var_28]
0x1800942d0  mov     [rsp+48h], rax
0x1800942d5  lea     rax, [rbp+57h+var_30]
0x1800942d9  mov     [rsp+0B0h+var_70], rax
0x1800942de  lea     rax, [rbp+57h+arg_18]
0x1800942e2  mov     [rsp+0B0h+var_78], rax
0x1800942e7  lea     rax, [rbp+57h+var_38]
0x1800942eb  mov     [rsp+0B0h+var_80], rax
0x1800942f0  lea     rax, [rbp+57h+var_60]
0x1800942f4  mov     [rsp+0B0h+var_88], rax
0x1800942f9  lea     rax, [rbp+57h+var_40]
0x1800942fd  jmp     loc_180093EA5
0x180094302  mov     eax, cs:CallbackContext
0x180094308  mov     ebx, 80004005h
0x18009430d  cmp     eax, 2
0x180094310  jbe     short loc_180094376
0x180094312  lea     rax, aGetservernonce; "GetServerNonce"
0x180094319  mov     [rbp+57h+arg_18], 0C2h
0x180094320  mov     [rbp+57h+var_28], rax
0x180094324  lea     rdx, byte_1801AF841
0x18009432b  lea     rax, aOnecoreTermsrv_31; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180094332  mov     [rbp+57h+var_60], ebx
0x180094335  mov     [rbp+57h+var_30], rax
0x180094339  lea     rax, aCloudapReturne_2; "CloudAP returned an empty responce to t"...
0x180094340  mov     [rbp+57h+var_38], rax
0x180094344  lea     rax, [rbp+57h+var_28]
0x180094348  mov     [rsp+0B0h+var_70], rax
0x18009434d  lea     rax, [rbp+57h+arg_18]
0x180094351  mov     [rsp+0B0h+var_78], rax
0x180094356  lea     rax, [rbp+57h+var_30]
  ... truncated ...
```
