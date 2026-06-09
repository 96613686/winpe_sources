# wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(void)

- ea: `0x18001c614`
- end: `0x18001c66e`
- name: `??1Completer@?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013348`

## callees

- `0x1800016ac`
- `0x18001c614`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c667`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x18001c614  mov     [rsp+arg_0], rbx
0x18001c619  push    rdi
0x18001c61a  sub     rsp, 20h
0x18001c61e  cmp     dword ptr [rcx+8], 0
0x18001c622  mov     rdi, rcx
0x18001c625  jnz     short loc_18001C653
0x18001c627  mov     rbx, [rcx]
0x18001c62a  mov     rcx, [rbx+20h]; CallbackContext
0x18001c62e  mov     [rbx+10h], rcx
0x18001c632  mov     byte ptr [rbx+18h], 1
0x18001c636  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001c63b  mov     rax, [rbx+8]
0x18001c63f  lea     rcx, [rbx+8]
0x18001c643  mov     dword ptr [rbx+1Ch], 1
0x18001c64a  mov     rax, [rax+8]
0x18001c64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c653  mov     rcx, [rdi]
0x18001c656  mov     edx, [rdi+8]
0x18001c659  lea     r8, [rcx+8]
0x18001c65d  mov     rbx, [rsp+28h+arg_0]
0x18001c662  add     rsp, 20h
0x18001c666  pop     rdi
0x18001c667  jmp     cs:__imp_InitOnceComplete
```
