# CList<tagPORTDEST *>::RemoveDataFromList(tagPORTDEST * const &)

- ea: `0x18000b0a0`
- end: `0x18000b0d5`
- name: `?RemoveDataFromList@?$CList@PEAUtagPORTDEST@@@@UEAAXAEBQEAUtagPORTDEST@@@Z`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b0a0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CList<tagPORTDEST *>::RemoveDataFromList(__int64 a1)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  if ( result )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, result);
  return result;
}

```

## disassembly

```asm
0x18000b0a0  push    rbx
0x18000b0a2  sub     rsp, 20h
0x18000b0a6  mov     rax, [rcx]
0x18000b0a9  mov     rbx, rcx
0x18000b0ac  mov     rax, [rax+20h]
0x18000b0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b5  mov     rcx, rax
0x18000b0b8  test    rax, rax
0x18000b0bb  jz      short loc_18000B0CF
0x18000b0bd  mov     rdx, [rbx]
0x18000b0c0  mov     rax, [rdx+10h]
0x18000b0c4  mov     rdx, rcx
0x18000b0c7  mov     rcx, rbx
0x18000b0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0cf  add     rsp, 20h
0x18000b0d3  pop     rbx
0x18000b0d4  retn
```
