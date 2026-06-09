# EfsTelemetry::EfsRpcWebDavUsage<ulong &>(ulong &)

- ea: `0x1800083cc`
- end: `0x180008533`
- name: `??$EfsRpcWebDavUsage@AEAK@EfsTelemetry@@SAXAEAK@Z`
- size: `359`
- prototype: `__int64 __fastcall(WINBOOL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b3cc`

## callees

- `0x18000163c`
- `0x180002028`
- `0x1800083cc`
- `0x18000a5f4`
- `0x18000c3c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000848e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000848e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008414`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008414`

## pseudocode

```c
__int64 __fastcall EfsTelemetry::EfsRpcWebDavUsage<unsigned long &>(WINBOOL *a1)
{
  void (*v2)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  unsigned int *v3; // rcx
  __int64 result; // rax
  __int64 v5; // rdx
  WINBOOL fPending; // [rsp+30h] [rbp-9h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL *p_fPending; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  LPVOID *p_Context; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`EfsTraceLoggingProvider::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    qword_180017918 = 0;
    Context = &qword_180017910;
    qword_180017910 = &wil::TraceLoggingProvider::`vftable';
    byte_180017920 = 0;
    dword_180017924 = 0;
    qword_180017928 = (struct _tlgProvider_t *)&`EfsTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_72ec5bf5b39a476118e22f5cc18a8f54_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180017910, qword_180017928, v2);
    InitOnceComplete(&`EfsTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_180017910);
  }
  v3 = (unsigned int *)*((_QWORD *)Context + 1);
  result = *v3;
  if ( (unsigned int)result > 5 )
  {
    v5 = *((_QWORD *)v3 + 3);
    result = *((_QWORD *)v3 + 2);
    if ( (result & 0x800000000000LL) != 0 )
    {
      result = v5 & 0x800000000000LL;
      if ( (v5 & 0x800000000000LL) == v5 )
      {
        fPending = *a1;
        v10 = 4;
        p_Context = &Context;
        p_fPending = &fPending;
        v12 = 8;
        return tlgWriteTransfer_EventWriteTransfer(v3, byte_180013711, 0, 0, 4, v8, fPending, 0x1000000);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800083cc  mov     [rsp-8+arg_0], rbx
0x1800083d1  mov     [rsp-8+arg_8], rdi
0x1800083d6  push    rbp
0x1800083d7  lea     rbp, [rsp-57h]
0x1800083dc  sub     rsp, 90h
0x1800083e3  mov     rax, cs:__security_cookie
0x1800083ea  xor     rax, rsp
0x1800083ed  mov     [rbp+57h+var_10], rax
0x1800083f1  mov     rbx, rcx
0x1800083f4  mov     [rbp+57h+Context], 0
0x1800083fc  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180008403  mov     [rbp+57h+fPending], 0
0x18000840a  lea     r9, [rbp+57h+Context]; lpContext
0x18000840e  xor     edx, edx; dwFlags
0x180008410  lea     r8, [rbp+57h+fPending]; fPending
0x180008414  call    cs:__imp_InitOnceBeginInitialize
0x18000841a  test    eax, eax
0x18000841c  jz      short loc_180008494
0x18000841e  cmp     [rbp+57h+fPending], 0
0x180008422  jz      short loc_180008494
0x180008424  lea     rdi, qword_180017910
0x18000842b  mov     cs:qword_180017918, 0
0x180008436  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000843d  mov     [rbp+57h+Context], rdi
0x180008441  mov     cs:qword_180017910, rax
0x180008448  mov     cs:byte_180017920, 0
0x18000844f  mov     cs:dword_180017924, 0
0x180008459  lea     rax, ?__hInner@?1???0StaticHandle@EfsTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EfsTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008460  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_72ec5bf5b39a476118e22f5cc18a8f54_@@CA@XZ; void (__cdecl *)()
0x180008467  mov     cs:qword_180017928, rax
0x18000846e  call    atexit
0x180008473  mov     rdx, cs:qword_180017928; struct _tlgProvider_t *
0x18000847a  mov     rcx, rdi; this
0x18000847d  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008482  mov     r8, rdi; lpContext
0x180008485  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000848c  xor     edx, edx; dwFlags
0x18000848e  call    cs:__imp_InitOnceComplete
0x180008494  mov     rax, [rbp+57h+Context]
0x180008498  mov     rcx, [rax+8]
0x18000849c  mov     eax, [rcx]
0x18000849e  cmp     eax, 5
0x1800084a1  jbe     short loc_180008512
0x1800084a3  mov     rdx, [rcx+18h]
0x1800084a7  mov     r8, 800000000000h
0x1800084b1  mov     rax, [rcx+10h]
0x1800084b5  test    r8, rax
0x1800084b8  jz      short loc_180008512
0x1800084ba  mov     rax, rdx
0x1800084bd  and     rax, r8
0x1800084c0  cmp     rax, rdx
0x1800084c3  jnz     short loc_180008512
0x1800084c5  mov     eax, [rbx]
0x1800084c7  mov     edx, 4
0x1800084cc  mov     [rbp+57h+fPending], eax
0x1800084cf  xor     r9d, r9d
0x1800084d2  lea     rax, [rbp+57h+Context]
0x1800084d6  mov     [rbp+57h+var_28], rdx
0x1800084da  mov     [rbp+57h+var_20], rax
0x1800084de  xor     r8d, r8d
0x1800084e1  lea     rax, [rbp+57h+fPending]
0x1800084e5  mov     [rbp+57h+Context], 1000000h
0x1800084ed  mov     [rbp+57h+var_30], rax
0x1800084f1  lea     rax, [rbp+57h+var_50]
0x1800084f5  mov     [rsp+90h+var_68], rax
0x1800084fa  mov     [rsp+90h+var_70], edx
0x1800084fe  lea     rdx, byte_180013711
0x180008505  mov     [rbp+57h+var_18], 8
0x18000850d  call    _tlgWriteTransfer_EventWriteTransfer
0x180008512  mov     rcx, [rbp+57h+var_10]
0x180008516  xor     rcx, rsp; StackCookie
0x180008519  call    __security_check_cookie
0x18000851e  lea     r11, [rsp+90h+var_s0]
0x180008526  mov     rbx, [r11+10h]
0x18000852a  mov     rdi, [r11+18h]
0x18000852e  mov     rsp, r11
0x180008531  pop     rbp
0x180008532  retn
```
