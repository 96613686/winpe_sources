# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x1800122d4`
- end: `0x1800122f5`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002632a`

## callees

- `0x1800122d4`
- `0x18001fe7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800122d4  sub     rsp, 28h
0x1800122d8  mov     rax, [rcx]
0x1800122db  mov     qword ptr [rcx], 0
0x1800122e2  test    rax, rax
0x1800122e5  jz      short loc_1800122F0
0x1800122e7  mov     rcx, rax; this
0x1800122ea  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800122ef  nop
0x1800122f0  add     rsp, 28h
0x1800122f4  retn
```
