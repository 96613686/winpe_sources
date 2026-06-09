# TaskAlloc(unsigned __int64)

- ea: `0x18002dc50`
- end: `0x18002dc81`
- name: `?TaskAlloc@@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002aff0`
- `0x18002bdb8`
- `0x18002d31c`

## callees

- `0x1800028b8`
- `0x180031010`

## pseudocode

```c
void *__fastcall TaskAlloc(__int64 a1)
{
  void *v1; // rbx

  v1 = (void *)((__int64 (__fastcall *)(LPMALLOC, __int64))ppMalloc->lpVtbl->Alloc)(ppMalloc, a1);
  OnNullThrowOOM(v1);
  return v1;
}

```

## disassembly

```asm
0x18002dc50  push    rbx
0x18002dc52  sub     rsp, 20h
0x18002dc56  mov     rdx, rcx
0x18002dc59  mov     rcx, cs:ppMalloc
0x18002dc60  mov     rax, [rcx]
0x18002dc63  mov     rax, [rax+18h]
0x18002dc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc6c  mov     rcx, rax; void *
0x18002dc6f  mov     rbx, rax
0x18002dc72  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18002dc77  mov     rax, rbx
0x18002dc7a  add     rsp, 20h
0x18002dc7e  pop     rbx
0x18002dc7f  retn
```
