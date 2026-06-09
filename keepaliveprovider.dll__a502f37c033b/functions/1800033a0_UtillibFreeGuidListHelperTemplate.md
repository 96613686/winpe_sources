# UtillibFreeGuidListHelperTemplate

- ea: `0x1800033a0`
- end: `0x1800033dc`
- name: `UtillibFreeGuidListHelperTemplate`
- size: `60`
- prototype: `void __fastcall(_QWORD *lpMem)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001f9c`

## callees

- `0x1800033a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033c3`

## pseudocode

```c
void __fastcall UtillibFreeGuidListHelperTemplate(_QWORD *lpMem)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbx
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    v1 = lpMem;
    do
    {
      v2 = (_QWORD *)*v1;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
      v1 = v2;
    }
    while ( v2 );
  }
}

```

## disassembly

```asm
0x1800033a0  test    rcx, rcx
0x1800033a3  jz      short locret_1800033DB
0x1800033a5  mov     [rsp+arg_0], rbx
0x1800033aa  push    rdi
0x1800033ab  sub     rsp, 20h
0x1800033af  mov     rdi, rcx
0x1800033b2  mov     rbx, [rdi]
0x1800033b5  call    cs:__imp_GetProcessHeap
0x1800033bb  mov     r8, rdi; lpMem
0x1800033be  xor     edx, edx; dwFlags
0x1800033c0  mov     rcx, rax; hHeap
0x1800033c3  call    cs:__imp_HeapFree
0x1800033c9  mov     rdi, rbx
0x1800033cc  test    rbx, rbx
0x1800033cf  jnz     short loc_1800033B2
0x1800033d1  mov     rbx, [rsp+28h+arg_0]
0x1800033d6  add     rsp, 20h
0x1800033da  pop     rdi
0x1800033db  retn
```
