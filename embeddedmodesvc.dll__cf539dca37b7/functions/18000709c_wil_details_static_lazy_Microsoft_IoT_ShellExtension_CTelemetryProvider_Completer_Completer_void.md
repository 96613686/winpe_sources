# wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::Completer::~Completer(void)

- ea: `0x18000709c`
- end: `0x1800070f6`
- name: `??1Completer@?$static_lazy@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007970`

## callees

- `0x180001864`
- `0x18000709c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800070ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall wil::details::static_lazy<Microsoft::IoT::ShellExtension::CTelemetryProvider>::Completer::~Completer(
        _DWORD *a1)
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
0x18000709c  mov     [rsp+arg_0], rbx
0x1800070a1  push    rdi
0x1800070a2  sub     rsp, 20h
0x1800070a6  cmp     dword ptr [rcx+8], 0
0x1800070aa  mov     rdi, rcx
0x1800070ad  jnz     short loc_1800070DB
0x1800070af  mov     rbx, [rcx]
0x1800070b2  mov     rcx, [rbx+20h]; CallbackContext
0x1800070b6  mov     [rbx+10h], rcx
0x1800070ba  mov     byte ptr [rbx+18h], 1
0x1800070be  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800070c3  mov     rax, [rbx+8]
0x1800070c7  lea     rcx, [rbx+8]
0x1800070cb  mov     dword ptr [rbx+1Ch], 1
0x1800070d2  mov     rax, [rax+8]
0x1800070d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070db  mov     rcx, [rdi]
0x1800070de  mov     edx, [rdi+8]
0x1800070e1  lea     r8, [rcx+8]
0x1800070e5  mov     rbx, [rsp+28h+arg_0]
0x1800070ea  add     rsp, 20h
0x1800070ee  pop     rdi
0x1800070ef  jmp     cs:__imp_InitOnceComplete
```
