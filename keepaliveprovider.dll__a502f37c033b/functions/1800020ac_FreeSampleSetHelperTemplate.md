# FreeSampleSetHelperTemplate

- ea: `0x1800020ac`
- end: `0x180002107`
- name: `FreeSampleSetHelperTemplate`
- size: `91`
- prototype: `BOOL __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002024`

## callees

- `0x180001f70`
- `0x1800020ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800020e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002100`

## pseudocode

```c
BOOL __fastcall FreeSampleSetHelperTemplate(_QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (_QWORD *)a1[2];
  if ( v1 )
  {
    do
    {
      v3 = (_QWORD *)*v1;
      FREE(v1[1]);
      FREE(v1);
      v1 = v3;
    }
    while ( v3 );
  }
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1800020ac  mov     [rsp+arg_0], rbx
0x1800020b1  mov     [rsp+arg_8], rsi
0x1800020b6  push    rdi
0x1800020b7  sub     rsp, 20h
0x1800020bb  mov     rdi, [rcx+10h]
0x1800020bf  mov     rsi, rcx
0x1800020c2  test    rdi, rdi
0x1800020c5  jz      short loc_1800020E3
0x1800020c7  mov     rcx, [rdi+8]
0x1800020cb  mov     rbx, [rdi]
0x1800020ce  call    FREE
0x1800020d3  mov     rcx, rdi
0x1800020d6  call    FREE
0x1800020db  mov     rdi, rbx
0x1800020de  test    rbx, rbx
0x1800020e1  jnz     short loc_1800020C7
0x1800020e3  call    cs:__imp_GetProcessHeap
0x1800020e9  mov     r8, rsi
0x1800020ec  xor     edx, edx
0x1800020ee  mov     rcx, rax
0x1800020f1  mov     rbx, [rsp+28h+arg_0]
0x1800020f6  mov     rsi, [rsp+28h+arg_8]
0x1800020fb  add     rsp, 20h
0x1800020ff  pop     rdi
0x180002100  jmp     cs:__imp_HeapFree
```
