# wil::details::static_lazy<ProfExtTelemetry>::Completer::~Completer(void)

- ea: `0x1800079e0`
- end: `0x180007a46`
- name: `??1Completer@?$static_lazy@VProfExtTelemetry@@@details@wil@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007924`

## callees

- `0x1800079e0`
- `0x180007a4c`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007a3a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfExtTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rdx
  union _RTL_RUN_ONCE v4; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v3.Ptr = *(PVOID *)(wil::details::static_lazy<ProfExtLogging>::get(
                          a1,
                          _lambda_f30e259b4f6aaa1d9b72e9c722b6ea54_::_lambda_invoker_cdecl_)
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
0x1800079e0  mov     [rsp+arg_0], rbx
0x1800079e5  push    rdi
0x1800079e6  sub     rsp, 20h
0x1800079ea  cmp     dword ptr [rcx+8], 0
0x1800079ee  mov     rdi, rcx
0x1800079f1  jnz     short loc_180007A26
0x1800079f3  mov     rbx, [rcx]
0x1800079f6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f30e259b4f6aaa1d9b72e9c722b6ea54_@@CA@XZ; _lambda_f30e259b4f6aaa1d9b72e9c722b6ea54_::_lambda_invoker_cdecl_(void)
0x1800079fd  call    ?get@?$static_lazy@VProfExtLogging@@@details@wil@@QEAAPEAVProfExtLogging@@P6AXXZ@Z; wil::details::static_lazy<ProfExtLogging>::get(void (*)(void))
0x180007a02  lea     rcx, [rbx+8]
0x180007a06  mov     rdx, [rax+8]
0x180007a0a  mov     rax, [rbx+8]
0x180007a0e  mov     [rbx+10h], rdx
0x180007a12  mov     byte ptr [rbx+18h], 0
0x180007a16  mov     dword ptr [rbx+1Ch], 1
0x180007a1d  mov     rax, [rax+8]
0x180007a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a26  mov     rcx, [rdi]
0x180007a29  mov     edx, [rdi+8]
0x180007a2c  lea     r8, [rcx+8]
0x180007a30  mov     rbx, [rsp+28h+arg_0]
0x180007a35  add     rsp, 20h
0x180007a39  pop     rdi
0x180007a3a  jmp     cs:__imp_InitOnceComplete
```
