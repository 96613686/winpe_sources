# EfsTelemetry::EfsRpcWebDavUsage<ulong &>(ulong &)

- ea: `0x180008db0`
- end: `0x180008f24`
- name: `??$EfsRpcWebDavUsage@AEAK@EfsTelemetry@@SAXAEAK@Z`
- size: `372`
- prototype: `__int64 __fastcall(WINBOOL *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000bfd4`

## callees

- `0x180001640`
- `0x180002038`
- `0x180008db0`
- `0x18000b04c`
- `0x18000d1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008e78`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008e78`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008df8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008df8`

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
    qword_180018918 = 0;
    Context = &qword_180018910;
    qword_180018910 = &wil::TraceLoggingProvider::`vftable';
    byte_180018920 = 0;
    dword_180018924 = 0;
    qword_180018928 = (struct _tlgProvider_t *)&`EfsTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_72ec5bf5b39a476118e22f5cc18a8f54_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180018910, qword_180018928, v2);
    InitOnceComplete(&`EfsTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_180018910);
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
        return tlgWriteTransfer_EventWriteTransfer(v3, byte_180014719, 0, 0, 4, v8, fPending, 0x1000000);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008db0  mov     [rsp-8+arg_0], rbx
0x180008db5  mov     [rsp-8+arg_8], rdi
0x180008dba  push    rbp
0x180008dbb  lea     rbp, [rsp-57h]
0x180008dc0  sub     rsp, 90h
0x180008dc7  mov     rax, cs:__security_cookie
0x180008dce  xor     rax, rsp
0x180008dd1  mov     [rbp+57h+var_10], rax
0x180008dd5  mov     rbx, rcx
0x180008dd8  mov     [rbp+57h+Context], 0
0x180008de0  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180008de7  mov     [rbp+57h+fPending], 0
0x180008dee  lea     r9, [rbp+57h+Context]; lpContext
0x180008df2  xor     edx, edx; dwFlags
0x180008df4  lea     r8, [rbp+57h+fPending]; fPending
0x180008df8  call    cs:__imp_InitOnceBeginInitialize
0x180008dff  nop     dword ptr [rax+rax+00h]
0x180008e04  test    eax, eax
0x180008e06  jz      short loc_180008E84
0x180008e08  cmp     [rbp+57h+fPending], 0
0x180008e0c  jz      short loc_180008E84
0x180008e0e  lea     rdi, qword_180018910
0x180008e15  mov     cs:qword_180018918, 0
0x180008e20  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180008e27  mov     [rbp+57h+Context], rdi
0x180008e2b  mov     cs:qword_180018910, rax
0x180008e32  mov     cs:byte_180018920, 0
0x180008e39  mov     cs:dword_180018924, 0
0x180008e43  lea     rax, ?__hInner@?1???0StaticHandle@EfsTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EfsTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008e4a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_72ec5bf5b39a476118e22f5cc18a8f54_@@CA@XZ; void (__cdecl *)()
0x180008e51  mov     cs:qword_180018928, rax
0x180008e58  call    atexit
0x180008e5d  mov     rdx, cs:qword_180018928; struct _tlgProvider_t *
0x180008e64  mov     rcx, rdi; this
0x180008e67  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008e6c  mov     r8, rdi; lpContext
0x180008e6f  lea     rcx, ?wrapper@?1??Instance@EfsTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VEfsTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180008e76  xor     edx, edx; dwFlags
0x180008e78  call    cs:__imp_InitOnceComplete
0x180008e7f  nop     dword ptr [rax+rax+00h]
0x180008e84  mov     rax, [rbp+57h+Context]
0x180008e88  mov     rcx, [rax+8]
0x180008e8c  mov     eax, [rcx]
0x180008e8e  cmp     eax, 5
0x180008e91  jbe     short loc_180008F02
0x180008e93  mov     rdx, [rcx+18h]
0x180008e97  mov     r8, 800000000000h
0x180008ea1  mov     rax, [rcx+10h]
0x180008ea5  test    r8, rax
0x180008ea8  jz      short loc_180008F02
0x180008eaa  mov     rax, rdx
0x180008ead  and     rax, r8
0x180008eb0  cmp     rax, rdx
0x180008eb3  jnz     short loc_180008F02
0x180008eb5  mov     eax, [rbx]
0x180008eb7  mov     edx, 4
0x180008ebc  mov     [rbp+57h+fPending], eax
0x180008ebf  xor     r9d, r9d
0x180008ec2  lea     rax, [rbp+57h+Context]
0x180008ec6  mov     [rbp+57h+var_28], rdx
0x180008eca  mov     [rbp+57h+var_20], rax
0x180008ece  xor     r8d, r8d
0x180008ed1  lea     rax, [rbp+57h+fPending]
0x180008ed5  mov     [rbp+57h+Context], 1000000h
0x180008edd  mov     [rbp+57h+var_30], rax
0x180008ee1  lea     rax, [rbp+57h+var_50]
0x180008ee5  mov     [rsp+90h+var_68], rax
0x180008eea  mov     [rsp+90h+var_70], edx
0x180008eee  lea     rdx, byte_180014719
0x180008ef5  mov     [rbp+57h+var_18], 8
0x180008efd  call    _tlgWriteTransfer_EventWriteTransfer
0x180008f02  mov     rcx, [rbp+57h+var_10]
0x180008f06  xor     rcx, rsp; StackCookie
0x180008f09  call    __security_check_cookie
0x180008f0e  lea     r11, [rsp+90h+var_s0]
0x180008f16  mov     rbx, [r11+10h]
0x180008f1a  mov     rdi, [r11+18h]
0x180008f1e  mov     rsp, r11
0x180008f21  pop     rbp
0x180008f22  retn
```
