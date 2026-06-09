# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180006540`
- end: `0x180006561`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077f0`

## callees

- `0x180006540`
- `0x180006ae4`

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
0x180006540  sub     rsp, 28h
0x180006544  mov     rax, [rcx]
0x180006547  mov     qword ptr [rcx], 0
0x18000654e  test    rax, rax
0x180006551  jz      short loc_18000655B
0x180006553  mov     rcx, rax; this
0x180006556  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000655b  add     rsp, 28h
0x18000655f  retn
```
