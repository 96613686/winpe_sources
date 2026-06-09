# DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)

- ea: `0x1400117e0`
- end: `0x140011867`
- name: `?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010fc`
- `0x1400127a0`
- `0x140012f40`
- `0x140012ff0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`
- `0x140014b40`
- `0x140014bf0`
- `0x140014ca0`
- `0x14001f5fc`
- `0x14001fbd8`
- `0x14001fd20`
- `0x140022ab0`
- `0x140023030`
- `0x140023500`

## callees

- `0x140006560`
- `0x1400117e0`
- `0x1400290c0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400117fc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400117fc`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001181e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001181e`

## pseudocode

```c
__int64 __fastcall DrDevice::DiscardBusyExchange(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  __int64 result; // rax

  ExAcquireFastMutex(&DrMutex);
  v4 = *(_QWORD *)(*(_QWORD *)a2 + 32LL);
  *(_QWORD *)(*(_QWORD *)a2 + 32LL) = 0;
  ExReleaseFastMutex(&DrMutex);
  result = DrExchangeManager::Discard(*(_QWORD *)(a1 + 32) + 688LL, a2);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 1);
  return result;
}

```

## disassembly

```asm
0x1400117e0  mov     [rsp+arg_0], rbx
0x1400117e5  mov     [rsp+arg_8], rsi
0x1400117ea  push    rdi
0x1400117eb  sub     rsp, 20h
0x1400117ef  mov     rbx, rcx
0x1400117f2  mov     rdi, rdx
0x1400117f5  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400117fc  call    cs:__imp_ExAcquireFastMutex
0x140011803  nop     dword ptr [rax+rax+00h]
0x140011808  mov     rax, [rdi]
0x14001180b  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140011812  mov     rsi, [rax+20h]
0x140011816  mov     qword ptr [rax+20h], 0
0x14001181e  call    cs:__imp_ExReleaseFastMutex
0x140011825  nop     dword ptr [rax+rax+00h]
0x14001182a  mov     rcx, [rbx+20h]
0x14001182e  mov     rdx, rdi
0x140011831  add     rcx, 2B0h
0x140011838  call    ?Discard@DrExchangeManager@@QEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrExchangeManager::Discard(SmartPtr<DrExchange> &)
0x14001183d  test    rsi, rsi
0x140011840  jz      short loc_140011856
0x140011842  mov     rax, [rsi]
0x140011845  mov     edx, 1
0x14001184a  mov     rcx, rsi
0x14001184d  mov     rax, [rax+10h]
0x140011851  call    _guard_dispatch_icall
0x140011856  mov     rbx, [rsp+28h+arg_0]
0x14001185b  mov     rsi, [rsp+28h+arg_8]
0x140011860  add     rsp, 20h
0x140011864  pop     rdi
0x140011865  retn
```
