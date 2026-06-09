# SafeFree(void *)

- ea: `0x1800035a0`
- end: `0x1800035d1`
- name: `?SafeFree@@YAHPEAX@Z`
- size: `49`
- prototype: `BOOL __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dd8`
- `0x180002f28`

## callees

- `0x1800035a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035b7`

## pseudocode

```c
BOOL __fastcall SafeFree(void *a1)
{
  HANDLE ProcessHeap; // rax

  if ( !a1 )
    return 1;
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1800035a0  push    rbx
0x1800035a2  sub     rsp, 20h
0x1800035a6  mov     rbx, rcx
0x1800035a9  test    rcx, rcx
0x1800035ac  jnz     short loc_1800035B7
0x1800035ae  lea     eax, [rcx+1]
0x1800035b1  add     rsp, 20h
0x1800035b5  pop     rbx
0x1800035b6  retn
0x1800035b7  call    cs:__imp_GetProcessHeap
0x1800035bd  mov     r8, rbx
0x1800035c0  xor     edx, edx
0x1800035c2  mov     rcx, rax
0x1800035c5  add     rsp, 20h
0x1800035c9  pop     rbx
0x1800035ca  jmp     cs:__imp_HeapFree
```
