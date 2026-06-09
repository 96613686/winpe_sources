# sqlite3ThreadProc

- ea: `0x140070980`
- end: `0x1400709aa`
- name: `sqlite3ThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x14007099c`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x14007099c`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadProc(__int64 a1)
{
  *(_QWORD *)(a1 + 32) = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 24));
  _o__endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x140070980  push    rbx
0x140070982  sub     rsp, 20h
0x140070986  mov     rbx, rcx
0x140070989  mov     rcx, [rcx+18h]
0x14007098d  mov     rax, [rbx+10h]
0x140070991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140070996  xor     ecx, ecx
0x140070998  mov     [rbx+20h], rax
0x14007099c  call    cs:__imp__o__endthreadex
0x1400709a2  xor     eax, eax
0x1400709a4  add     rsp, 20h
0x1400709a8  pop     rbx
0x1400709a9  retn
```
