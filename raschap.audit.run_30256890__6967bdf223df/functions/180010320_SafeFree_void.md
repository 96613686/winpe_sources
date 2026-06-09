# SafeFree(void *)

- ea: `0x180010320`
- end: `0x180010351`
- name: `?SafeFree@@YAHPEAX@Z`
- size: `49`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fdf0`
- `0x180010048`
- `0x180010218`
- `0x18001029c`
- `0x1800240ec`
- `0x1800241c0`
- `0x180024398`
- `0x1800252e0`

## callees

- `0x180010320`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001034a`

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
0x180010320  push    rbx
0x180010322  sub     rsp, 20h
0x180010326  mov     rbx, rcx
0x180010329  test    rcx, rcx
0x18001032c  jnz     short loc_180010337
0x18001032e  lea     eax, [rcx+1]
0x180010331  add     rsp, 20h
0x180010335  pop     rbx
0x180010336  retn
0x180010337  call    cs:__imp_GetProcessHeap
0x18001033d  mov     r8, rbx
0x180010340  xor     edx, edx
0x180010342  mov     rcx, rax
0x180010345  add     rsp, 20h
0x180010349  pop     rbx
0x18001034a  jmp     cs:__imp_HeapFree
```
