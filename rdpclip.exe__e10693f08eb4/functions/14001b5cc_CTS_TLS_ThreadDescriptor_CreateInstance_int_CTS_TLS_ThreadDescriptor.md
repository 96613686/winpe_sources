# CTS_TLS_ThreadDescriptor::CreateInstance(int,CTS_TLS_ThreadDescriptor * *)

- ea: `0x14001b5cc`
- end: `0x14001b7c0`
- name: `?CreateInstance@CTS_TLS_ThreadDescriptor@@SAJHPEAPEAV1@@Z`
- size: `500`
- prototype: `__int64 __fastcall(int, struct CTS_TLS_ThreadDescriptor **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001aac0`
- `0x14001e790`

## callees

- `0x1400014d4`
- `0x1400028b4`
- `0x140004cf4`
- `0x140005750`
- `0x140019df4`
- `0x14001b5cc`
- `0x14001cef0`
- `0x1400256b4`
- `0x14006b010`

## string_xrefs

- `0x14001b5fa`: `CreateInstance`
- `0x14001b738`: `CreateInstance`
- `0x14001b613`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001b751`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x14001b625`: `Thread descriptor creation NULL pointer passed`
- `0x14001b763`: `OOM on thread descriptor`
- `0x14001b6ec`: `spThreadDescriptor init failed`

## pseudocode

```c
__int64 __fastcall CTS_TLS_ThreadDescriptor::CreateInstance(
        int a1,
        struct CTS_TLS_ThreadDescriptor **a2,
        int a3,
        int a4)
{
  int v6; // ebx
  CTS_TLS_ThreadDescriptor *v7; // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  CTS_TLS_ThreadDescriptor *v11; // rdi
  __int64 v12; // rcx
  int ActivityIdPrefix; // eax
  const char *v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+60h] [rbp-10h] BYREF
  int v18; // [rsp+98h] [rbp+28h] BYREF
  int v19; // [rsp+A0h] [rbp+30h] BYREF
  CTS_TLS_ThreadDescriptor *v20; // [rsp+A8h] [rbp+38h] BYREF

  v20 = 0;
  if ( a2 )
  {
    v7 = (CTS_TLS_ThreadDescriptor *)operator new(0x200u);
    if ( v7 && (v11 = CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(v7, a1)) != 0 )
    {
      TCntPtr<CRdpClipMainWnd>::SafeRelease(&v20);
      v12 = *((_QWORD *)v11 + 4);
      v20 = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      v6 = CTS_TLS_ThreadDescriptor::Initialize((CTS_TLS_ThreadDescriptor *)((char *)v11 + 8));
      if ( v6 >= 0 )
      {
        v20 = 0;
        *a2 = v11;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          155,
          (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
          ActivityIdPrefix,
          (__int64)"spThreadDescriptor init failed",
          v6);
      }
    }
    else
    {
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v18 = 3340;
        v17[0] = "CreateInstance";
        v19 = -2147467259;
        v16 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
        v15 = "OOM on thread descriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v8,
          (unsigned int)word_14007E202,
          v9,
          v10,
          (__int64)&v15,
          (__int64)&v19,
          (__int64)&v16,
          (__int64)&v18,
          (__int64)v17);
      }
      v6 = -2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v18 = 3333;
      v15 = "CreateInstance";
      v19 = -2147467259;
      v16 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v17[0] = "Thread descriptor creation NULL pointer passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (unsigned int)&byte_14007E247,
        a3,
        a4,
        (__int64)v17,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v15);
    }
    v6 = -2147024809;
  }
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001b5cc  mov     r11, rsp
0x14001b5cf  mov     [r11+8], rbx
0x14001b5d3  push    rbp
0x14001b5d4  push    rsi
0x14001b5d5  push    rdi
0x14001b5d6  mov     rbp, rsp
0x14001b5d9  sub     rsp, 70h
0x14001b5dd  mov     rsi, rdx
0x14001b5e0  mov     [rbp+arg_18], 0
0x14001b5e8  mov     ebx, ecx
0x14001b5ea  test    rdx, rdx
0x14001b5ed  jnz     short loc_14001B667
0x14001b5ef  mov     eax, cs:dword_1400880C8
0x14001b5f5  cmp     eax, 2
0x14001b5f8  jbe     short loc_14001B65D
0x14001b5fa  lea     rax, aCreateinstance_1; "CreateInstance"
0x14001b601  mov     [rbp+arg_8], 0D05h
0x14001b608  mov     [rbp+var_20], rax
0x14001b60c  lea     rdx, byte_14007E247
0x14001b613  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001b61a  mov     [rbp+arg_10], 80004005h
0x14001b621  mov     [rbp+var_18], rax
0x14001b625  lea     rax, aThreadDescript; "Thread descriptor creation NULL pointer"...
0x14001b62c  mov     [rbp+var_10], rax
0x14001b630  lea     rax, [rbp+var_20]
0x14001b634  mov     [r11-48h], rax
0x14001b638  lea     rax, [rbp+arg_8]
0x14001b63c  mov     [r11-50h], rax
0x14001b640  lea     rax, [rbp+var_18]
0x14001b644  mov     [r11-58h], rax
0x14001b648  lea     rax, [rbp+arg_10]
0x14001b64c  mov     [r11-60h], rax
0x14001b650  lea     rax, [rbp+var_10]
0x14001b654  mov     [r11-68h], rax
0x14001b658  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001b65d  mov     ebx, 80070057h
0x14001b662  jmp     loc_14001B7A5
0x14001b667  mov     ecx, 200h; Size
0x14001b66c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b671  test    rax, rax
0x14001b674  jz      loc_14001B72D
0x14001b67a  mov     edx, ebx; int
0x14001b67c  mov     rcx, rax; this
0x14001b67f  call    ??0CTS_TLS_ThreadDescriptor@@AEAA@H@Z; CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(int)
0x14001b684  mov     rdi, rax
0x14001b687  test    rax, rax
0x14001b68a  jz      loc_14001B72D
0x14001b690  lea     rcx, [rbp+arg_18]
0x14001b694  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001b699  mov     rcx, [rdi+20h]
0x14001b69d  mov     [rbp+arg_18], rdi
0x14001b6a1  mov     rax, [rcx]
0x14001b6a4  mov     rax, [rax+8]
0x14001b6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6ad  lea     rcx, [rdi+8]; this
0x14001b6b1  call    ?Initialize@CTS_TLS_ThreadDescriptor@@EEAAJXZ; CTS_TLS_ThreadDescriptor::Initialize(void)
0x14001b6b6  mov     ebx, eax
0x14001b6b8  test    eax, eax
0x14001b6ba  jns     short loc_14001B720
0x14001b6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6c3  lea     rax, WPP_GLOBAL_Control
0x14001b6ca  cmp     rcx, rax
0x14001b6cd  jz      loc_14001B7A5
0x14001b6d3  test    byte ptr [rcx+1Ch], 8
0x14001b6d7  jz      loc_14001B7A5
0x14001b6dd  cmp     byte ptr [rcx+19h], 2
0x14001b6e1  jb      loc_14001B7A5
0x14001b6e7  call    RdpX_GetActivityIdPrefix
0x14001b6ec  lea     rcx, aSpthreaddescri; "spThreadDescriptor init failed"
0x14001b6f3  mov     dword ptr [rsp+70h+var_48], ebx
0x14001b6f7  mov     [rsp+70h+var_50], rcx
0x14001b6fc  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x14001b703  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b70a  mov     edx, 9Bh
0x14001b70f  mov     r9d, eax
0x14001b712  mov     rcx, [rcx+10h]
0x14001b716  call    WPP_SF_DsD
0x14001b71b  jmp     loc_14001B7A5
0x14001b720  mov     [rbp+arg_18], 0
0x14001b728  mov     [rsi], rdi
0x14001b72b  jmp     short loc_14001B7A5
0x14001b72d  mov     eax, cs:dword_1400880C8
0x14001b733  cmp     eax, 2
0x14001b736  jbe     short loc_14001B7A0
0x14001b738  lea     rax, aCreateinstance_1; "CreateInstance"
0x14001b73f  mov     [rbp+arg_8], 0D0Ch
0x14001b746  mov     [rbp+var_10], rax
0x14001b74a  lea     rdx, word_14007E202
0x14001b751  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14001b758  mov     [rbp+arg_10], 80004005h
0x14001b75f  mov     [rbp+var_18], rax
0x14001b763  lea     rax, aOomOnThreadDes; "OOM on thread descriptor"
0x14001b76a  mov     [rbp+var_20], rax
0x14001b76e  lea     rax, [rbp+var_10]
0x14001b772  mov     [rsp+70h+var_30], rax
0x14001b777  lea     rax, [rbp+arg_8]
0x14001b77b  mov     [rsp+70h+var_38], rax
0x14001b780  lea     rax, [rbp+var_18]
0x14001b784  mov     [rsp+70h+var_40], rax
0x14001b789  lea     rax, [rbp+arg_10]
0x14001b78d  mov     [rsp+70h+var_48], rax
0x14001b792  lea     rax, [rbp+var_20]
0x14001b796  mov     [rsp+70h+var_50], rax
0x14001b79b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001b7a0  mov     ebx, 8007000Eh
0x14001b7a5  lea     rcx, [rbp+arg_18]
0x14001b7a9  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x14001b7ae  mov     eax, ebx
0x14001b7b0  mov     rbx, [rsp+70h+arg_0]
0x14001b7b8  add     rsp, 70h
0x14001b7bc  pop     rdi
0x14001b7bd  pop     rsi
0x14001b7be  pop     rbp
0x14001b7bf  retn
```
