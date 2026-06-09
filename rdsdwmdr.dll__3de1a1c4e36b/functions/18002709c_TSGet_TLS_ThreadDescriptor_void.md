# TSGet_TLS_ThreadDescriptor(void)

- ea: `0x18002709c`
- end: `0x180027142`
- name: `?TSGet_TLS_ThreadDescriptor@@YAPEAVCTS_TLS_ThreadDescriptor@@XZ`
- size: `166`
- prototype: `struct CTS_TLS_ThreadDescriptor *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800222f0`
- `0x1800234e0`

## callees

- `0x18000160c`
- `0x18001ec90`
- `0x18002709c`

## string_xrefs

- `0x1800270ca`: `TSGet_TLS_ThreadDescriptor`
- `0x1800270e3`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800270f5`: `Failed to get thread descriptor`

## pseudocode

```c
struct CTS_TLS_ThreadDescriptor *__fastcall TSGet_TLS_ThreadDescriptor(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v9; // [rsp+50h] [rbp-18h] BYREF
  void *v10; // [rsp+80h] [rbp+18h] BYREF
  int v11; // [rsp+88h] [rbp+20h] BYREF
  const char *v12; // [rsp+90h] [rbp+28h] BYREF
  const char *v13; // [rsp+98h] [rbp+30h] BYREF

  v4 = 0;
  v10 = 0;
  if ( (int)PAL_System_ThreadGetContext(g_PAL_SYS_threadContextIndex, &v10, a3, a4) >= 0 )
    return (struct CTS_TLS_ThreadDescriptor *)v10;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v10) = 54;
    v12 = "TSGet_TLS_ThreadDescriptor";
    v11 = -2147467259;
    v13 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    v9 = "Failed to get thread descriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v5,
      (__int64)qword_18003FE48,
      v6,
      v7,
      (const unsigned __int16 **)&v9,
      (__int64)&v11,
      (const unsigned __int16 **)&v13,
      (__int64)&v10,
      (const unsigned __int16 **)&v12);
  }
  return (struct CTS_TLS_ThreadDescriptor *)v4;
}

```

## disassembly

```asm
0x18002709c  push    rbp
0x18002709e  push    rbx
0x18002709f  mov     rbp, rsp
0x1800270a2  sub     rsp, 68h
0x1800270a6  xor     ebx, ebx
0x1800270a8  mov     [rbp+arg_0], rbx
0x1800270ac  mov     ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; unsigned int
0x1800270b2  lea     rdx, [rbp+arg_0]; void **
0x1800270b6  call    ?PAL_System_ThreadGetContext@@YAJKPEAPEAX@Z; PAL_System_ThreadGetContext(ulong,void * *)
0x1800270bb  test    eax, eax
0x1800270bd  jns     short loc_180027134
0x1800270bf  mov     eax, cs:dword_180044008
0x1800270c5  cmp     eax, 2
0x1800270c8  jbe     short loc_180027138
0x1800270ca  lea     rax, aTsgetTlsThread; "TSGet_TLS_ThreadDescriptor"
0x1800270d1  mov     dword ptr [rbp+arg_0], 36h ; '6'
0x1800270d8  mov     [rbp+arg_10], rax
0x1800270dc  lea     rdx, qword_18003FE48
0x1800270e3  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800270ea  mov     [rbp+arg_8], 80004005h
0x1800270f1  mov     [rbp+arg_18], rax
0x1800270f5  lea     rax, aFailedToGetThr; "Failed to get thread descriptor"
0x1800270fc  mov     [rbp+var_18], rax
0x180027100  lea     rax, [rbp+arg_10]
0x180027104  mov     [rsp+68h+var_28], rax
0x180027109  lea     rax, [rbp+arg_0]
0x18002710d  mov     [rsp+68h+var_30], rax
0x180027112  lea     rax, [rbp+arg_18]
0x180027116  mov     [rsp+68h+var_38], rax
0x18002711b  lea     rax, [rbp+arg_8]
0x18002711f  mov     [rsp+68h+var_40], rax
0x180027124  lea     rax, [rbp+var_18]
0x180027128  mov     [rsp+68h+var_48], rax
0x18002712d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180027132  jmp     short loc_180027138
0x180027134  mov     rbx, [rbp+arg_0]
0x180027138  mov     rax, rbx
0x18002713b  add     rsp, 68h
0x18002713f  pop     rbx
0x180027140  pop     rbp
0x180027141  retn
```
