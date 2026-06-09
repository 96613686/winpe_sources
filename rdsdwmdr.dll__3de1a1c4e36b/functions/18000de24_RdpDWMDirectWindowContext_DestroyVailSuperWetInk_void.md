# RdpDWMDirectWindowContext::DestroyVailSuperWetInk(void)

- ea: `0x18000de24`
- end: `0x18000df34`
- name: `?DestroyVailSuperWetInk@RdpDWMDirectWindowContext@@QEAAJXZ`
- size: `272`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800103d8`

## callees

- `0x180001188`
- `0x18000160c`
- `0x18000de24`
- `0x18002c010`

## string_xrefs

- `0x18000dedd`: `OnDestroyVailSuperWetInk failed: Aux redirection channel is not ready`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::DestroyVailSuperWetInk(
        RdpDWMDirectWindowContext *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v10; // [rsp+50h] [rbp-10h] BYREF
  int v11; // [rsp+70h] [rbp+10h] BYREF
  const char *v12; // [rsp+78h] [rbp+18h] BYREF
  const char *v13; // [rsp+80h] [rbp+20h] BYREF
  const char *v14; // [rsp+88h] [rbp+28h] BYREF

  v5 = *((_QWORD *)this + 83);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 32LL))(v5, *((_QWORD *)this + 8));
    if ( v6 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v11 = v6;
      v12 = "DestroyVailSuperWetInk";
      v13 = "Failed to send the vail super wet ink destruction message";
      v14 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"DestroyVailSuperWetInk",
        (__int64)word_1800392E2,
        v7,
        v8,
        (const unsigned __int16 **)&v14,
        (const unsigned __int16 **)&v13,
        (__int64)&v11,
        (const unsigned __int16 **)&v12);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v11 = 553;
    v14 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v13 = "DestroyVailSuperWetInk";
    v10 = "OnDestroyVailSuperWetInk failed: Aux redirection channel is not ready";
    LODWORD(v12) = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)"DestroyVailSuperWetInk",
      (__int64)byte_18003929D,
      a3,
      a4,
      (const unsigned __int16 **)&v10,
      (__int64)&v12,
      (const unsigned __int16 **)&v14,
      (__int64)&v11,
      (const unsigned __int16 **)&v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18000de24  push    rbp
0x18000de26  mov     rbp, rsp
0x18000de29  sub     rsp, 60h
0x18000de2d  mov     rdx, rcx
0x18000de30  mov     rcx, [rcx+298h]
0x18000de37  test    rcx, rcx
0x18000de3a  jz      short loc_18000DEB9
0x18000de3c  mov     rax, [rcx]
0x18000de3f  mov     rdx, [rdx+40h]
0x18000de43  mov     rax, [rax+20h]
0x18000de47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de4c  test    eax, eax
0x18000de4e  jns     loc_18000DF2C
0x18000de54  mov     ecx, cs:dword_180044008
0x18000de5a  cmp     ecx, 3
0x18000de5d  jbe     loc_18000DF2C
0x18000de63  mov     [rbp+arg_0], eax
0x18000de66  lea     rcx, aDestroyvailsup; "DestroyVailSuperWetInk"
0x18000de6d  lea     rax, aFailedToSendTh_8; "Failed to send the vail super wet ink d"...
0x18000de74  mov     [rbp+arg_8], rcx
0x18000de78  mov     [rbp+arg_10], rax
0x18000de7c  lea     rdx, word_1800392E2
0x18000de83  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000de8a  mov     [rbp+arg_18], rax
0x18000de8e  lea     rax, [rbp+arg_8]
0x18000de92  mov     [rsp+60h+var_28], rax
0x18000de97  lea     rax, [rbp+arg_0]
0x18000de9b  mov     [rsp+60h+var_30], rax
0x18000dea0  lea     rax, [rbp+arg_10]
0x18000dea4  mov     [rsp+60h+var_38], rax
0x18000dea9  lea     rax, [rbp+arg_18]
0x18000dead  mov     [rsp+60h+var_40], rax
0x18000deb2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000deb7  jmp     short loc_18000DF2C
0x18000deb9  mov     eax, cs:dword_180044008
0x18000debf  cmp     eax, 2
0x18000dec2  jbe     short loc_18000DF2C
0x18000dec4  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000decb  mov     [rbp+arg_0], 229h
0x18000ded2  mov     [rbp+arg_18], rax
0x18000ded6  lea     rcx, aDestroyvailsup; "DestroyVailSuperWetInk"
0x18000dedd  lea     rax, aOndestroyvails_0; "OnDestroyVailSuperWetInk failed: Aux re"...
0x18000dee4  mov     [rbp+arg_10], rcx
0x18000dee8  mov     [rbp+var_10], rax
0x18000deec  lea     rdx, byte_18003929D
0x18000def3  lea     rax, [rbp+arg_10]
0x18000def7  mov     dword ptr [rbp+arg_8], 8000FFFFh
0x18000defe  mov     [rsp+60h+var_20], rax
0x18000df03  lea     rax, [rbp+arg_0]
0x18000df07  mov     [rsp+60h+var_28], rax
0x18000df0c  lea     rax, [rbp+arg_18]
0x18000df10  mov     [rsp+60h+var_30], rax
0x18000df15  lea     rax, [rbp+arg_8]
0x18000df19  mov     [rsp+60h+var_38], rax
0x18000df1e  lea     rax, [rbp+var_10]
0x18000df22  mov     [rsp+60h+var_40], rax
0x18000df27  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000df2c  xor     eax, eax
0x18000df2e  add     rsp, 60h
0x18000df32  pop     rbp
0x18000df33  retn
```
