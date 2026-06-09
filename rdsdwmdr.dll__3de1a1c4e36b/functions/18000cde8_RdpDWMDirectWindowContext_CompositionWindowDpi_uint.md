# RdpDWMDirectWindowContext::CompositionWindowDpi(uint)

- ea: `0x18000cde8`
- end: `0x18000cefb`
- name: `?CompositionWindowDpi@RdpDWMDirectWindowContext@@QEAAJI@Z`
- size: `275`
- prototype: `__int64 __fastcall(RdpDWMDirectWindowContext *this, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fe68`

## callees

- `0x180001188`
- `0x18000160c`
- `0x18000cde8`
- `0x18002c010`

## string_xrefs

- `0x18000ce2d`: `CompositionWindowDpi`
- `0x18000ce9d`: `CompositionWindowDpi`
- `0x18000cea4`: `OnCompositionWindowDpi failed: Aux redirection channel is not ready`

## pseudocode

```c
__int64 __fastcall RdpDWMDirectWindowContext::CompositionWindowDpi(
        RdpDWMDirectWindowContext *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // r8
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v11; // [rsp+50h] [rbp-10h] BYREF
  const char *v12; // [rsp+58h] [rbp-8h] BYREF
  int v13; // [rsp+70h] [rbp+10h] BYREF
  const char *v14; // [rsp+80h] [rbp+20h] BYREF
  const char *v15; // [rsp+88h] [rbp+28h] BYREF

  v4 = a2;
  v6 = *((_QWORD *)this + 83);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 40LL))(v6, *((_QWORD *)this + 8), v4);
    if ( v7 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      v13 = v7;
      v14 = "CompositionWindowDpi";
      v15 = "Failed to send the window dpi message";
      v11 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)"CompositionWindowDpi",
        (__int64)word_180039262,
        v8,
        v9,
        (const unsigned __int16 **)&v11,
        (const unsigned __int16 **)&v15,
        (__int64)&v13,
        (const unsigned __int16 **)&v14);
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    v13 = 582;
    v11 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrwindowrenderingcontext.cpp";
    v15 = "CompositionWindowDpi";
    v12 = "OnCompositionWindowDpi failed: Aux redirection channel is not ready";
    LODWORD(v14) = -2147418113;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (__int64)"CompositionWindowDpi",
      (__int64)byte_18003921D,
      v4,
      a4,
      (const unsigned __int16 **)&v12,
      (__int64)&v14,
      (const unsigned __int16 **)&v11,
      (__int64)&v13,
      (const unsigned __int16 **)&v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18000cde8  push    rbp
0x18000cdea  mov     rbp, rsp
0x18000cded  sub     rsp, 60h
0x18000cdf1  mov     r8d, edx
0x18000cdf4  mov     rdx, rcx
0x18000cdf7  mov     rcx, [rcx+298h]
0x18000cdfe  test    rcx, rcx
0x18000ce01  jz      short loc_18000CE80
0x18000ce03  mov     rax, [rcx]
0x18000ce06  mov     rdx, [rdx+40h]
0x18000ce0a  mov     rax, [rax+28h]
0x18000ce0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce13  test    eax, eax
0x18000ce15  jns     loc_18000CEF3
0x18000ce1b  mov     ecx, cs:dword_180044008
0x18000ce21  cmp     ecx, 3
0x18000ce24  jbe     loc_18000CEF3
0x18000ce2a  mov     [rbp+arg_0], eax
0x18000ce2d  lea     rcx, aCompositionwin; "CompositionWindowDpi"
0x18000ce34  lea     rax, aFailedToSendTh_5; "Failed to send the window dpi message"
0x18000ce3b  mov     [rbp+arg_10], rcx
0x18000ce3f  mov     [rbp+arg_18], rax
0x18000ce43  lea     rdx, word_180039262
0x18000ce4a  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18000ce51  mov     [rbp+var_10], rax
0x18000ce55  lea     rax, [rbp+arg_10]
0x18000ce59  mov     [rsp+60h+var_28], rax
0x18000ce5e  lea     rax, [rbp+arg_0]
0x18000ce62  mov     [rsp+60h+var_30], rax
0x18000ce67  lea     rax, [rbp+arg_18]
0x18000ce6b  mov     [rsp+60h+var_38], rax
0x18000ce70  lea     rax, [rbp+var_10]
0x18000ce74  mov     [rsp+60h+var_40], rax
0x18000ce79  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000ce7e  jmp     short loc_18000CEF3
0x18000ce80  mov     eax, cs:dword_180044008
0x18000ce86  cmp     eax, 2
0x18000ce89  jbe     short loc_18000CEF3
0x18000ce8b  lea     rax, aClientcoreTerm_4; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x18000ce92  mov     [rbp+arg_0], 246h
0x18000ce99  mov     [rbp+var_10], rax
0x18000ce9d  lea     rcx, aCompositionwin; "CompositionWindowDpi"
0x18000cea4  lea     rax, aOncompositionw; "OnCompositionWindowDpi failed: Aux redi"...
0x18000ceab  mov     [rbp+arg_18], rcx
0x18000ceaf  mov     [rbp+var_8], rax
0x18000ceb3  lea     rdx, byte_18003921D
0x18000ceba  lea     rax, [rbp+arg_18]
0x18000cebe  mov     dword ptr [rbp+arg_10], 8000FFFFh
0x18000cec5  mov     [rsp+60h+var_20], rax
0x18000ceca  lea     rax, [rbp+arg_0]
0x18000cece  mov     [rsp+60h+var_28], rax
0x18000ced3  lea     rax, [rbp+var_10]
0x18000ced7  mov     [rsp+60h+var_30], rax
0x18000cedc  lea     rax, [rbp+arg_10]
0x18000cee0  mov     [rsp+60h+var_38], rax
0x18000cee5  lea     rax, [rbp+var_8]
0x18000cee9  mov     [rsp+60h+var_40], rax
0x18000ceee  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000cef3  xor     eax, eax
0x18000cef5  add     rsp, 60h
0x18000cef9  pop     rbp
0x18000cefa  retn
```
