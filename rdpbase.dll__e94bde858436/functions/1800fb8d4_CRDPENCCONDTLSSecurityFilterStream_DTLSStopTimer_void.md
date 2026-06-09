# CRDPENCCONDTLSSecurityFilterStream::DTLSStopTimer(void)

- ea: `0x1800fb8d4`
- end: `0x1800fb9f0`
- name: `?DTLSStopTimer@CRDPENCCONDTLSSecurityFilterStream@@AEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(CRDPENCCONDTLSSecurityFilterStream *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800fa994`
- `0x1800fb650`
- `0x1800fe1ec`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x1800fb8d4`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb94a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb94a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800fb92b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800fb92b`

## string_xrefs

- `0x1800fb98d`: `DeleteTimerQueueTimer failed after receiving ack !!`

## pseudocode

```c
__int64 __fastcall CRDPENCCONDTLSSecurityFilterStream::DTLSStopTimer(
        CRDPENCCONDTLSSecurityFilterStream *this,
        __int64 a2,
        __int64 a3,
        int a4)
{
  void *v5; // rdx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  const char *v10; // [rsp+50h] [rbp-18h] BYREF
  const char *v11; // [rsp+80h] [rbp+18h] BYREF
  int v12; // [rsp+88h] [rbp+20h] BYREF
  const char *v13; // [rsp+90h] [rbp+28h] BYREF
  const char *v14; // [rsp+98h] [rbp+30h] BYREF

  if ( (unsigned int)CallbackContext > 5 )
  {
    v11 = "DTLSStopTimer called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)&word_1801C4496,
      0,
      a4,
      (__int64)&v11);
  }
  v5 = (void *)*((_QWORD *)this + 53);
  if ( v5 )
  {
    if ( !DeleteTimerQueueTimer(0, v5, 0) )
    {
      if ( GetLastError() == 997 )
      {
LABEL_10:
        *((_QWORD *)this + 53) = 0;
        return 0;
      }
      if ( GetLastError() != 997 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v11) = 1870;
          v13 = "DTLSStopTimer";
          v12 = -2147467259;
          v14 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpdtlsfilterserver.cpp";
          v10 = "DeleteTimerQueueTimer failed after receiving ack !!";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v6,
            (unsigned int)&dword_1801C43FC,
            v7,
            v8,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v14,
            (__int64)&v11,
            (__int64)&v13);
        }
        goto LABEL_10;
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800fb8d4  push    rbp
0x1800fb8d6  push    rbx
0x1800fb8d7  mov     rbp, rsp
0x1800fb8da  sub     rsp, 68h
0x1800fb8de  mov     eax, cs:CallbackContext
0x1800fb8e4  mov     rbx, rcx
0x1800fb8e7  cmp     eax, 5
0x1800fb8ea  jbe     short loc_1800FB916
0x1800fb8ec  lea     rax, aDtlsstoptimerC; "DTLSStopTimer called"
0x1800fb8f3  xor     r8d, r8d
0x1800fb8f6  mov     [rbp+arg_0], rax
0x1800fb8fa  lea     rdx, word_1801C4496
0x1800fb901  lea     rax, [rbp+arg_0]
0x1800fb905  lea     rcx, CallbackContext
0x1800fb90c  mov     [rsp+68h+var_48], rax
0x1800fb911  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800fb916  mov     rdx, [rbx+1A8h]; Timer
0x1800fb91d  test    rdx, rdx
0x1800fb920  jz      loc_1800FB9E7
0x1800fb926  xor     r8d, r8d; CompletionEvent
0x1800fb929  xor     ecx, ecx; TimerQueue
0x1800fb92b  call    cs:__imp_DeleteTimerQueueTimer
0x1800fb931  test    eax, eax
0x1800fb933  jnz     loc_1800FB9CC
0x1800fb939  call    cs:__imp_GetLastError
0x1800fb93f  cmp     eax, 3E5h
0x1800fb944  jz      loc_1800FB9DC
0x1800fb94a  call    cs:__imp_GetLastError
0x1800fb950  cmp     eax, 3E5h
0x1800fb955  jz      short loc_1800FB9CC
0x1800fb957  mov     eax, cs:CallbackContext
0x1800fb95d  cmp     eax, 2
0x1800fb960  jbe     short loc_1800FB9DC
0x1800fb962  lea     rax, aDtlsstoptimer; "DTLSStopTimer"
0x1800fb969  mov     dword ptr [rbp+arg_0], 74Eh
0x1800fb970  mov     [rbp+arg_10], rax
0x1800fb974  lea     rdx, dword_1801C43FC
0x1800fb97b  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fb982  mov     [rbp+arg_8], 80004005h
0x1800fb989  mov     [rbp+arg_18], rax
0x1800fb98d  lea     rax, aDeletetimerque; "DeleteTimerQueueTimer failed after rece"...
0x1800fb994  mov     [rbp+var_18], rax
0x1800fb998  lea     rax, [rbp+arg_10]
0x1800fb99c  mov     [rsp+68h+var_28], rax
0x1800fb9a1  lea     rax, [rbp+arg_0]
0x1800fb9a5  mov     [rsp+68h+var_30], rax
0x1800fb9aa  lea     rax, [rbp+arg_18]
0x1800fb9ae  mov     [rsp+68h+var_38], rax
0x1800fb9b3  lea     rax, [rbp+arg_8]
0x1800fb9b7  mov     [rsp+68h+var_40], rax
0x1800fb9bc  lea     rax, [rbp+var_18]
0x1800fb9c0  mov     [rsp+68h+var_48], rax
0x1800fb9c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800fb9ca  jmp     short loc_1800FB9DC
0x1800fb9cc  mov     rcx, [rbx+20h]
0x1800fb9d0  mov     rax, [rcx]
0x1800fb9d3  mov     rax, [rax+10h]
0x1800fb9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb9dc  mov     qword ptr [rbx+1A8h], 0
0x1800fb9e7  xor     eax, eax
0x1800fb9e9  add     rsp, 68h
0x1800fb9ed  pop     rbx
0x1800fb9ee  pop     rbp
0x1800fb9ef  retn
```
