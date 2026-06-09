# wil::details::static_lazy<IntlCplTraceLogging>::Completer::~Completer(void)

- ea: `0x180009154`
- end: `0x1800091ae`
- name: `??1Completer@?$static_lazy@VIntlCplTraceLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a2fc`

## callees

- `0x1800016a0`
- `0x180009154`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800091a7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<IntlCplTraceLogging>::Completer::~Completer(_DWORD *a1)
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
0x180009154  mov     [rsp+arg_0], rbx
0x180009159  push    rdi
0x18000915a  sub     rsp, 20h
0x18000915e  cmp     dword ptr [rcx+8], 0
0x180009162  mov     rdi, rcx
0x180009165  jnz     short loc_180009193
0x180009167  mov     rbx, [rcx]
0x18000916a  mov     rcx, [rbx+20h]; CallbackContext
0x18000916e  mov     [rbx+10h], rcx
0x180009172  mov     byte ptr [rbx+18h], 1
0x180009176  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000917b  mov     rax, [rbx+8]
0x18000917f  lea     rcx, [rbx+8]
0x180009183  mov     dword ptr [rbx+1Ch], 1
0x18000918a  mov     rax, [rax+8]
0x18000918e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009193  mov     rcx, [rdi]
0x180009196  mov     edx, [rdi+8]
0x180009199  lea     r8, [rcx+8]
0x18000919d  mov     rbx, [rsp+28h+arg_0]
0x1800091a2  add     rsp, 20h
0x1800091a6  pop     rdi
0x1800091a7  jmp     cs:__imp_InitOnceComplete
```
