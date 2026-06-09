# SmartNewPtr

- ea: `0x180018b68`
- end: `0x180018b96`
- name: `SmartNewPtr`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x180006f00`
- `0x180007130`
- `0x180007418`
- `0x18000f8a0`
- `0x1800105b0`
- `0x180018b28`
- `0x180019b00`
- `0x18001bb30`
- `0x18001de14`
- `0x18001e97c`
- `0x18001ef48`
- `0x18001f14c`
- `0x18001f23c`
- `0x18001f98c`
- `0x180020984`
- `0x1800211ec`
- `0x18002145c`
- `0x180021554`
- `0x18002167c`
- `0x1800217fc`
- `0x180021a38`

## callees

- `0x18001d15d`

## pseudocode

```c
void *__fastcall SmartNewPtr(int a1, _WORD *a2)
{
  void *result; // rax

  result = malloc_0(a1);
  *a2 = result == 0 ? 8 : 0;
  return result;
}

```

## disassembly

```asm
0x180018b68  push    rbx
0x180018b6a  sub     rsp, 20h
0x180018b6e  movsxd  rcx, ecx; Size
0x180018b71  mov     rbx, rdx
0x180018b74  call    malloc_0
0x180018b79  mov     rcx, rax
0x180018b7c  neg     rcx
0x180018b7f  sbb     r8w, r8w
0x180018b83  not     r8w
0x180018b87  and     r8w, 8
0x180018b8c  mov     [rbx], r8w
0x180018b90  add     rsp, 20h
0x180018b94  pop     rbx
0x180018b95  retn
```
