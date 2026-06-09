# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180022aa0`
- end: `0x180022ae4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026a40`

## callees

- `0x180022aa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ad0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ac2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022ac2`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(void **a1, void **a2)
{
  void *v2; // rax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return a1;
}

```

## disassembly

```asm
0x180022aa0  mov     [rsp+arg_0], rbx
0x180022aa5  push    rdi
0x180022aa6  sub     rsp, 20h
0x180022aaa  mov     rax, [rdx]
0x180022aad  mov     rbx, rcx
0x180022ab0  mov     qword ptr [rdx], 0
0x180022ab7  mov     rdi, [rcx]
0x180022aba  mov     [rcx], rax
0x180022abd  test    rdi, rdi
0x180022ac0  jz      short loc_180022AD6
0x180022ac2  call    cs:__imp_GetProcessHeap
0x180022ac8  mov     r8, rdi; lpMem
0x180022acb  xor     edx, edx; dwFlags
0x180022acd  mov     rcx, rax; hHeap
0x180022ad0  call    cs:__imp_HeapFree
0x180022ad6  mov     rax, rbx
0x180022ad9  mov     rbx, [rsp+28h+arg_0]
0x180022ade  add     rsp, 20h
0x180022ae2  pop     rdi
0x180022ae3  retn
```
