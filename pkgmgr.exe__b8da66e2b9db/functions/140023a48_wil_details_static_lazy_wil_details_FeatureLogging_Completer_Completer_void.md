# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x140023a48`
- end: `0x140023aa2`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140024314`

## callees

- `0x140001a48`
- `0x140023a48`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140023a9b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
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
    TraceLoggingRegisterEx_EventRegister_2U(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x140023a48  mov     [rsp+arg_0], rbx
0x140023a4d  push    rdi
0x140023a4e  sub     rsp, 20h
0x140023a52  cmp     dword ptr [rcx+8], 0
0x140023a56  mov     rdi, rcx
0x140023a59  jnz     short loc_140023A87
0x140023a5b  mov     rbx, [rcx]
0x140023a5e  mov     rcx, [rbx+20h]; CallbackContext
0x140023a62  mov     [rbx+10h], rcx
0x140023a66  mov     byte ptr [rbx+18h], 1
0x140023a6a  call    TraceLoggingRegisterEx_EventRegister_2U
0x140023a6f  mov     rax, [rbx+8]
0x140023a73  lea     rcx, [rbx+8]
0x140023a77  mov     dword ptr [rbx+1Ch], 1
0x140023a7e  mov     rax, [rax+8]
0x140023a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023a87  mov     rcx, [rdi]
0x140023a8a  mov     edx, [rdi+8]
0x140023a8d  lea     r8, [rcx+8]
0x140023a91  mov     rbx, [rsp+28h+arg_0]
0x140023a96  add     rsp, 20h
0x140023a9a  pop     rdi
0x140023a9b  jmp     cs:__imp_InitOnceComplete
```
