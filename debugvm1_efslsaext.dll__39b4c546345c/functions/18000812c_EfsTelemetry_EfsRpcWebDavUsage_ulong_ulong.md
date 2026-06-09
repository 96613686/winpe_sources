# EfsTelemetry::EfsRpcWebDavUsage<ulong &>(ulong &)

- ea: `0x18000812c`
- end: `0x180008293`
- name: `??$EfsRpcWebDavUsage@AEAK@EfsTelemetry@@SAXAEAK@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000842c`

## callees

- `0x18000163c`
- `0x180001f34`
- `0x180005584`
- `0x18000812c`
- `0x180012040`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800081ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800081ee`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008174`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008174`

## pseudocode

```c
int __fastcall EfsTelemetry::EfsRpcWebDavUsage<unsigned long &>(WINBOOL *a1)
{
  void (*v2)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  __int64 v3; // rcx
  __int64 v4; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-9h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL *p_fPending; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  LPVOID *p_Context; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`EfsTraceLoggingProvider::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_18001EC28 = 0;
    Context = &qword_18001EC20;
    qword_18001EC20 = &EfsLsaRpcTelemetryProvider::`vftable';
    byte_18001EC30 = 0;
    dword_18001EC34 = 0;
    qword_18001EC38 = (struct _tlgProvider_t *)&`EfsTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_72ec5bf5b39a476118e22f5cc18a8f54_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18001EC20, qword_18001EC38, v2);
    InitOnceComplete(&`EfsTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_18001EC20);
  }
  v3 = *((_QWORD *)Context + 1);
  LODWORD(v4) = *(_DWORD *)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    v4 = *(_QWORD *)(v3 + 16);
    if ( (v4 & 0x800000000000LL) != 0 )
    {
      LODWORD(v4) = 0;
      if ( (*(_QWORD *)(v3 + 24) & 0x800000000000LL) == *(_QWORD *)(v3 + 24) )
      {
        fPending = *a1;
        v10 = 4;
        p_Context = &Context;
        Context = (LPVOID)0x1000000;
        p_fPending = &fPending;
        v12 = 8;
        LODWORD(v4) = tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)byte_18001AB4B, 0, 0, 4u, &v8);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000812c  mov     [rsp-8+arg_0], rbx
0x180008131  mov     [rsp-8+arg_8], rdi
0x180008136  push    rbp
0x180008137  lea     rbp, [rsp-57h]
0x18000813c  sub     rsp, 90h
0x180008143  mov     rax, cs:__security_cookie
0x18000814a  xor     rax, rsp
0x18000814d  mov     [rbp+57h+var_10], rax
0x180008151  mov     rbx, rcx
0x180008154  mov     [rbp+57h+Context], 0
0x18000815c  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180008163  mov     [rbp+57h+fPending], 0
0x18000816a  lea     r9, [rbp+57h+Context]; lpContext
0x18000816e  xor     edx, edx; dwFlags
0x180008170  lea     r8, [rbp+57h+fPending]; fPending
0x180008174  call    cs:__imp_InitOnceBeginInitialize
0x18000817a  test    eax, eax
0x18000817c  jz      short loc_1800081F4
0x18000817e  cmp     [rbp+57h+fPending], 0
0x180008182  jz      short loc_1800081F4
0x180008184  lea     rdi, qword_18001EC20
0x18000818b  mov     cs:qword_18001EC28, 0
0x180008196  lea     rax, ??_7EfsLsaRpcTelemetryProvider@@6B@; const EfsLsaRpcTelemetryProvider::`vftable'
0x18000819d  mov     [rbp+57h+Context], rdi
0x1800081a1  mov     cs:qword_18001EC20, rax
0x1800081a8  mov     cs:byte_18001EC30, 0
0x1800081af  mov     cs:dword_18001EC34, 0
0x1800081b9  lea     rax, ?__hInner@?1???0StaticHandle@EfsTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EfsTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800081c0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_72ec5bf5b39a476118e22f5cc18a8f54_@@CA@XZ; void (__cdecl *)()
0x1800081c7  mov     cs:qword_18001EC38, rax
0x1800081ce  call    atexit
0x1800081d3  mov     rdx, cs:qword_18001EC38; struct _tlgProvider_t *
0x1800081da  mov     rcx, rdi; this
0x1800081dd  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800081e2  mov     r8, rdi; lpContext
0x1800081e5  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800081ec  xor     edx, edx; dwFlags
0x1800081ee  call    cs:__imp_InitOnceComplete
0x1800081f4  mov     rax, [rbp+57h+Context]
0x1800081f8  mov     rcx, [rax+8]
0x1800081fc  mov     eax, [rcx]
0x1800081fe  cmp     eax, 5
0x180008201  jbe     short loc_180008272
0x180008203  mov     rdx, [rcx+18h]
0x180008207  mov     r8, 800000000000h
0x180008211  mov     rax, [rcx+10h]
0x180008215  test    r8, rax
0x180008218  jz      short loc_180008272
0x18000821a  mov     rax, rdx
0x18000821d  and     rax, r8
0x180008220  cmp     rax, rdx
0x180008223  jnz     short loc_180008272
0x180008225  mov     eax, [rbx]
0x180008227  mov     edx, 4
0x18000822c  mov     [rbp+57h+fPending], eax
0x18000822f  xor     r9d, r9d
0x180008232  lea     rax, [rbp+57h+Context]
0x180008236  mov     [rbp+57h+var_28], rdx
0x18000823a  mov     [rbp+57h+var_20], rax
0x18000823e  xor     r8d, r8d
0x180008241  lea     rax, [rbp+57h+fPending]
0x180008245  mov     [rbp+57h+Context], 1000000h
0x18000824d  mov     [rbp+57h+var_30], rax
0x180008251  lea     rax, [rbp+57h+var_50]
0x180008255  mov     [rsp+90h+var_68], rax
0x18000825a  mov     [rsp+90h+var_70], edx
0x18000825e  lea     rdx, byte_18001AB4B
0x180008265  mov     [rbp+57h+var_18], 8
0x18000826d  call    _tlgWriteTransfer_EventWriteTransfer
0x180008272  mov     rcx, [rbp+57h+var_10]
0x180008276  xor     rcx, rsp; StackCookie
0x180008279  call    __security_check_cookie
0x18000827e  lea     r11, [rsp+90h+var_s0]
0x180008286  mov     rbx, [r11+10h]
0x18000828a  mov     rdi, [r11+18h]
0x18000828e  mov     rsp, r11
0x180008291  pop     rbp
0x180008292  retn
```
