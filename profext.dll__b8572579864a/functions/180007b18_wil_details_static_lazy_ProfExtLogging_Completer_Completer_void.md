# wil::details::static_lazy<ProfExtLogging>::Completer::~Completer(void)

- ea: `0x180007b18`
- end: `0x180007b77`
- name: `??1Completer@?$static_lazy@VProfExtLogging@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007a4c`

## callees

- `0x180007b18`
- `0x180007b80`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007b6b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfExtLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180007b18  mov     [rsp+arg_0], rbx
0x180007b1d  push    rdi
0x180007b1e  sub     rsp, 20h
0x180007b22  cmp     dword ptr [rcx+8], 0
0x180007b26  mov     rdi, rcx
0x180007b29  jnz     short loc_180007B57
0x180007b2b  mov     rbx, [rcx]
0x180007b2e  mov     rcx, [rbx+20h]
0x180007b32  mov     [rbx+10h], rcx
0x180007b36  mov     byte ptr [rbx+18h], 1
0x180007b3a  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180007b3f  mov     rax, [rbx+8]
0x180007b43  lea     rcx, [rbx+8]
0x180007b47  mov     dword ptr [rbx+1Ch], 1
0x180007b4e  mov     rax, [rax+8]
0x180007b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b57  mov     rcx, [rdi]
0x180007b5a  mov     edx, [rdi+8]
0x180007b5d  lea     r8, [rcx+8]
0x180007b61  mov     rbx, [rsp+28h+arg_0]
0x180007b66  add     rsp, 20h
0x180007b6a  pop     rdi
0x180007b6b  jmp     cs:__imp_InitOnceComplete
```
