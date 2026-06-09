# CTSThread::OnNotifyThreadMessage(void *)

- ea: `0x180025e60`
- end: `0x180025f2c`
- name: `?OnNotifyThreadMessage@CTSThread@@KAIPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(CTSThread *this, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000160c`
- `0x18001c9d0`
- `0x180025d90`
- `0x180025e60`
- `0x18002c010`

## string_xrefs

- `0x180025ecb`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180025eb2`: `OnNotifyThreadMessage`
- `0x180025edd`: `Failed to run thread event queue`

## pseudocode

```c
__int64 __fastcall CTSThread::OnNotifyThreadMessage(CTSThread *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  const char *v11; // [rsp+50h] [rbp-18h] BYREF
  const char *v12; // [rsp+58h] [rbp-10h] BYREF
  int v13; // [rsp+80h] [rbp+18h] BYREF
  int v14; // [rsp+88h] [rbp+20h] BYREF
  CTSThread *v15; // [rsp+90h] [rbp+28h] BYREF
  const char *v16; // [rsp+98h] [rbp+30h] BYREF

  v15 = 0;
  if ( this )
  {
    TCntPtr<CTSThread>::SafeRelease(&v15, a2, a3, a4);
    v5 = *((_QWORD *)this + 5);
    v15 = this;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    if ( (int)CTSThread::OnNotifyThreadEventQueue(this, v6, v7, v8) < 0 && (unsigned int)dword_180044008 > 2 )
    {
      v13 = 3234;
      v16 = "OnNotifyThreadMessage";
      v14 = -2147467259;
      v11 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v12 = "Failed to run thread event queue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (__int64)&byte_18003F39F,
        a3,
        a4,
        (const unsigned __int16 **)&v12,
        (__int64)&v14,
        (const unsigned __int16 **)&v11,
        (__int64)&v13,
        (const unsigned __int16 **)&v16);
    }
  }
  TCntPtr<CTSThread>::SafeRelease(&v15, a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180025e60  push    rbp
0x180025e62  push    rbx
0x180025e63  mov     rbp, rsp
0x180025e66  sub     rsp, 68h
0x180025e6a  mov     [rbp+arg_10], 0
0x180025e72  mov     rbx, rcx
0x180025e75  test    rcx, rcx
0x180025e78  jz      loc_180025F1A
0x180025e7e  lea     rcx, [rbp+arg_10]
0x180025e82  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x180025e87  mov     rcx, [rbx+28h]
0x180025e8b  mov     [rbp+arg_10], rbx
0x180025e8f  mov     rax, [rcx]
0x180025e92  mov     rax, [rax+8]
0x180025e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e9b  mov     rcx, rbx; this
0x180025e9e  call    ?OnNotifyThreadEventQueue@CTSThread@@UEAAJXZ; CTSThread::OnNotifyThreadEventQueue(void)
0x180025ea3  test    eax, eax
0x180025ea5  jns     short loc_180025F1A
0x180025ea7  mov     eax, cs:dword_180044008
0x180025ead  cmp     eax, 2
0x180025eb0  jbe     short loc_180025F1A
0x180025eb2  lea     rax, aOnnotifythread; "OnNotifyThreadMessage"
0x180025eb9  mov     [rbp+arg_0], 0CA2h
0x180025ec0  mov     [rbp+arg_18], rax
0x180025ec4  lea     rdx, byte_18003F39F
0x180025ecb  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180025ed2  mov     [rbp+arg_8], 80004005h
0x180025ed9  mov     [rbp+var_18], rax
0x180025edd  lea     rax, aFailedToRunThr_0; "Failed to run thread event queue"
0x180025ee4  mov     [rbp+var_10], rax
0x180025ee8  lea     rax, [rbp+arg_18]
0x180025eec  mov     [rsp+68h+var_28], rax
0x180025ef1  lea     rax, [rbp+arg_0]
0x180025ef5  mov     [rsp+68h+var_30], rax
0x180025efa  lea     rax, [rbp+var_18]
0x180025efe  mov     [rsp+68h+var_38], rax
0x180025f03  lea     rax, [rbp+arg_8]
0x180025f07  mov     [rsp+68h+var_40], rax
0x180025f0c  lea     rax, [rbp+var_10]
0x180025f10  mov     [rsp+68h+var_48], rax
0x180025f15  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180025f1a  lea     rcx, [rbp+arg_10]
0x180025f1e  call    ?SafeRelease@?$TCntPtr@VCTSThread@@@@AEAAXXZ; TCntPtr<CTSThread>::SafeRelease(void)
0x180025f23  xor     eax, eax
0x180025f25  add     rsp, 68h
0x180025f29  pop     rbx
0x180025f2a  pop     rbp
0x180025f2b  retn
```
