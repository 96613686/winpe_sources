# wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::Completer::~Completer(void)

- ea: `0x18000b4d0`
- end: `0x18000b52a`
- name: `??1Completer@?$static_lazy@VMapsBackgroudTransferTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001104c`

## callees

- `0x1800015d4`
- `0x18000b4d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000b523`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MapsBackgroudTransferTraceLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000b4d0  mov     [rsp+arg_0], rbx
0x18000b4d5  push    rdi
0x18000b4d6  sub     rsp, 20h
0x18000b4da  cmp     dword ptr [rcx+8], 0
0x18000b4de  mov     rdi, rcx
0x18000b4e1  jnz     short loc_18000B50F
0x18000b4e3  mov     rbx, [rcx]
0x18000b4e6  mov     rcx, [rbx+20h]; CallbackContext
0x18000b4ea  mov     [rbx+10h], rcx
0x18000b4ee  mov     byte ptr [rbx+18h], 1
0x18000b4f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000b4f7  mov     rax, [rbx+8]
0x18000b4fb  lea     rcx, [rbx+8]
0x18000b4ff  mov     dword ptr [rbx+1Ch], 1
0x18000b506  mov     rax, [rax+8]
0x18000b50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50f  mov     rcx, [rdi]
0x18000b512  mov     edx, [rdi+8]
0x18000b515  lea     r8, [rcx+8]
0x18000b519  mov     rbx, [rsp+28h+arg_0]
0x18000b51e  add     rsp, 20h
0x18000b522  pop     rdi
0x18000b523  jmp     cs:__imp_InitOnceComplete
```
