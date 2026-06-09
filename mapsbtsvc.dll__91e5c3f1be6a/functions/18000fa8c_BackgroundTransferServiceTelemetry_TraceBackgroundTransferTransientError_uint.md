# BackgroundTransferServiceTelemetry::TraceBackgroundTransferTransientError_(uint)

- ea: `0x18000fa8c`
- end: `0x18000fb08`
- name: `?TraceBackgroundTransferTransientError_@BackgroundTransferServiceTelemetry@@QEAAXI@Z`
- size: `124`
- prototype: `void __fastcall(BackgroundTransferServiceTelemetry *this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000cba4`

## callees

- `0x180001758`
- `0x180001e70`
- `0x18000fa8c`
- `0x18001104c`

## pseudocode

```c
void __fastcall BackgroundTransferServiceTelemetry::TraceBackgroundTransferTransientError_(
        BackgroundTransferServiceTelemetry *this,
        int a2)
{
  _DWORD *v3; // rcx
  int v4; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v5[32]; // [rsp+38h] [rbp-40h] BYREF
  int *v6; // [rsp+58h] [rbp-20h]
  __int64 v7; // [rsp+60h] [rbp-18h]

  v3 = *(_DWORD **)(wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::get(
                      this,
                      _lambda_d12e33ce4d37313aafa8795421aadc17_::_lambda_invoker_cdecl_)
                  + 8);
  if ( *v3 > 5u )
  {
    v4 = a2;
    v6 = &v4;
    v7 = 4;
    tlgWriteTransfer_EventWriteTransfer(v3, byte_1800189B9, 0, 0, 3, v5);
  }
}

```

## disassembly

```asm
0x18000fa8c  push    rbx
0x18000fa8e  sub     rsp, 70h
0x18000fa92  mov     rax, cs:__security_cookie
0x18000fa99  xor     rax, rsp
0x18000fa9c  mov     [rsp+78h+var_10], rax
0x18000faa1  mov     ebx, edx
0x18000faa3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d12e33ce4d37313aafa8795421aadc17_@@CA@XZ; _lambda_d12e33ce4d37313aafa8795421aadc17_::_lambda_invoker_cdecl_(void)
0x18000faaa  call    ?get@?$static_lazy@VMapsBackgroudTransferTraceLogging@@@details@wil@@QEAAPEAVMapsBackgroudTransferTraceLogging@@P6AXXZ@Z; wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::get(void (*)(void))
0x18000faaf  mov     rcx, [rax+8]
0x18000fab3  mov     eax, [rcx]
0x18000fab5  cmp     eax, 5
0x18000fab8  jbe     short loc_18000FAF5
0x18000faba  lea     rax, [rsp+78h+var_48]
0x18000fabf  mov     [rsp+78h+var_48], ebx
0x18000fac3  mov     [rsp+78h+var_20], rax
0x18000fac8  lea     rdx, byte_1800189B9
0x18000facf  lea     rax, [rsp+78h+var_40]
0x18000fad4  mov     [rsp+78h+var_18], 4
0x18000fadd  mov     [rsp+78h+var_50], rax
0x18000fae2  xor     r9d, r9d
0x18000fae5  xor     r8d, r8d
0x18000fae8  mov     [rsp+78h+var_58], 3
0x18000faf0  call    _tlgWriteTransfer_EventWriteTransfer
0x18000faf5  mov     rcx, [rsp+78h+var_10]
0x18000fafa  xor     rcx, rsp; StackCookie
0x18000fafd  call    __security_check_cookie
0x18000fb02  add     rsp, 70h
0x18000fb06  pop     rbx
0x18000fb07  retn
```
