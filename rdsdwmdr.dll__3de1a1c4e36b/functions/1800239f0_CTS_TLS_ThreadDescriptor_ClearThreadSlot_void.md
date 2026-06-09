# CTS_TLS_ThreadDescriptor::ClearThreadSlot(void)

- ea: `0x1800239f0`
- end: `0x180023a97`
- name: `?ClearThreadSlot@CTS_TLS_ThreadDescriptor@@AEAAXXZ`
- size: `167`
- prototype: `void __fastcall(CTS_TLS_ThreadDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022b94`
- `0x1800246ec`

## callees

- `0x18000160c`
- `0x18001eeac`
- `0x1800239f0`

## string_xrefs

- `0x180023a32`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x180023a14`: `ClearThreadSlot`
- `0x180023a49`: `Fail to clear thread context TLS entry`

## pseudocode

```c
void __fastcall CTS_TLS_ThreadDescriptor::ClearThreadSlot(CTS_TLS_ThreadDescriptor *this)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  const char *v4; // [rsp+50h] [rbp-18h] BYREF
  int v5; // [rsp+70h] [rbp+8h] BYREF
  int v6; // [rsp+78h] [rbp+10h] BYREF
  const char *v7; // [rsp+80h] [rbp+18h] BYREF
  const char *v8; // [rsp+88h] [rbp+20h] BYREF

  if ( (int)PAL_System_ThreadSetContext(*((_DWORD *)this + 126), 0) < 0 && (unsigned int)dword_180044008 > 2 )
  {
    v5 = 3508;
    v7 = "ClearThreadSlot";
    v6 = -2147467259;
    v8 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v4 = "Fail to clear thread context TLS entry";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v1,
      (__int64)&word_18003F246,
      v2,
      v3,
      (const unsigned __int16 **)&v4,
      (__int64)&v6,
      (const unsigned __int16 **)&v8,
      (__int64)&v5,
      (const unsigned __int16 **)&v7);
  }
}

```

## disassembly

```asm
0x1800239f0  sub     rsp, 68h
0x1800239f4  mov     ecx, [rcx+1F8h]; unsigned int
0x1800239fa  xor     edx, edx; void *
0x1800239fc  call    ?PAL_System_ThreadSetContext@@YAJKPEAX@Z; PAL_System_ThreadSetContext(ulong,void *)
0x180023a01  test    eax, eax
0x180023a03  jns     loc_180023A92
0x180023a09  mov     eax, cs:dword_180044008
0x180023a0f  cmp     eax, 2
0x180023a12  jbe     short loc_180023A92
0x180023a14  lea     rax, aClearthreadslo; "ClearThreadSlot"
0x180023a1b  mov     [rsp+68h+arg_0], 0DB4h
0x180023a23  mov     [rsp+68h+arg_10], rax
0x180023a2b  lea     rdx, word_18003F246
0x180023a32  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180023a39  mov     [rsp+68h+arg_8], 80004005h
0x180023a41  mov     [rsp+68h+arg_18], rax
0x180023a49  lea     rax, aFailToClearThr; "Fail to clear thread context TLS entry"
0x180023a50  mov     [rsp+68h+var_18], rax
0x180023a55  lea     rax, [rsp+68h+arg_10]
0x180023a5d  mov     [rsp+68h+var_28], rax
0x180023a62  lea     rax, [rsp+68h+arg_0]
0x180023a67  mov     [rsp+68h+var_30], rax
0x180023a6c  lea     rax, [rsp+68h+arg_18]
0x180023a74  mov     [rsp+68h+var_38], rax
0x180023a79  lea     rax, [rsp+68h+arg_8]
0x180023a7e  mov     [rsp+68h+var_40], rax
0x180023a83  lea     rax, [rsp+68h+var_18]
0x180023a88  mov     [rsp+68h+var_48], rax
0x180023a8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180023a92  add     rsp, 68h
0x180023a96  retn
```
