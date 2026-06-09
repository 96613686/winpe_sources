# wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)

- ea: `0x1800032bc`
- end: `0x1800032d2`
- name: `??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800033d4`
- `0x1800050c0`

## pseudocode

```c
_QWORD *__fastcall wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(_QWORD *a1, __int64 a2, __int64 a3)
{
  *a1 = a2;
  a1[1] = a2 + 80 * a3;
  return a1;
}

```

## disassembly

```asm
0x1800032bc  lea     rax, [r8+r8*4]
0x1800032c0  mov     [rcx], rdx
0x1800032c3  shl     rax, 4
0x1800032c7  add     rax, rdx
0x1800032ca  mov     [rcx+8], rax
0x1800032ce  mov     rax, rcx
0x1800032d1  retn
```
