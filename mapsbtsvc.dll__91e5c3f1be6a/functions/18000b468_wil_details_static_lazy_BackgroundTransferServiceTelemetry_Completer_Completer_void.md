# wil::details::static_lazy<BackgroundTransferServiceTelemetry>::Completer::~Completer(void)

- ea: `0x18000b468`
- end: `0x18000b4c9`
- name: `??1Completer@?$static_lazy@VBackgroundTransferServiceTelemetry@@@details@wil@@QEAA@XZ`
- size: `97`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010f98`

## callees

- `0x18000b468`
- `0x18001104c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b4c2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<BackgroundTransferServiceTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rdx
  union _RTL_RUN_ONCE v4; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v3.Ptr = *(PVOID *)(wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::get(
                          a1,
                          _lambda_d12e33ce4d37313aafa8795421aadc17_::_lambda_invoker_cdecl_)
                      + 8);
    v4.Ptr = v2[1].Ptr;
    v2[2].Ptr = v3.Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v4.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000b468  mov     [rsp+arg_0], rbx
0x18000b46d  push    rdi
0x18000b46e  sub     rsp, 20h
0x18000b472  cmp     dword ptr [rcx+8], 0
0x18000b476  mov     rdi, rcx
0x18000b479  jnz     short loc_18000B4AE
0x18000b47b  mov     rbx, [rcx]
0x18000b47e  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d12e33ce4d37313aafa8795421aadc17_@@CA@XZ; _lambda_d12e33ce4d37313aafa8795421aadc17_::_lambda_invoker_cdecl_(void)
0x18000b485  call    ?get@?$static_lazy@VMapsBackgroudTransferTraceLogging@@@details@wil@@QEAAPEAVMapsBackgroudTransferTraceLogging@@P6AXXZ@Z; wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::get(void (*)(void))
0x18000b48a  lea     rcx, [rbx+8]
0x18000b48e  mov     rdx, [rax+8]
0x18000b492  mov     rax, [rbx+8]
0x18000b496  mov     [rbx+10h], rdx
0x18000b49a  mov     byte ptr [rbx+18h], 0
0x18000b49e  mov     dword ptr [rbx+1Ch], 1
0x18000b4a5  mov     rax, [rax+8]
0x18000b4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ae  mov     rcx, [rdi]
0x18000b4b1  mov     edx, [rdi+8]
0x18000b4b4  lea     r8, [rcx+8]
0x18000b4b8  mov     rbx, [rsp+28h+arg_0]
0x18000b4bd  add     rsp, 20h
0x18000b4c1  pop     rdi
0x18000b4c2  jmp     cs:__imp_InitOnceComplete
```
