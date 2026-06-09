# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1400171f0`
- end: `0x140017211`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ef1e`

## callees

- `0x1400171f0`
- `0x14001801c`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rax

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    wil::details::FreeProcessHeap(v2, a2);
}

```

## disassembly

```asm
0x1400171f0  sub     rsp, 28h
0x1400171f4  mov     rax, [rcx]
0x1400171f7  mov     qword ptr [rcx], 0
0x1400171fe  test    rax, rax
0x140017201  jz      short loc_14001720C
0x140017203  mov     rcx, rax; this
0x140017206  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14001720b  nop
0x14001720c  add     rsp, 28h
0x140017210  retn
```
