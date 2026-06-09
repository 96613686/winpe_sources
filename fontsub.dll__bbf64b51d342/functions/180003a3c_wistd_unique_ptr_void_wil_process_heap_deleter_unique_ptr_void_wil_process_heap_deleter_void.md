# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180003a3c`
- end: `0x180003a5c`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000509c`

## callees

- `0x180003a3c`
- `0x1800040ac`

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
0x180003a3c  sub     rsp, 28h
0x180003a40  mov     rax, [rcx]
0x180003a43  mov     qword ptr [rcx], 0
0x180003a4a  test    rax, rax
0x180003a4d  jz      short loc_180003A57
0x180003a4f  mov     rcx, rax; this
0x180003a52  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003a57  add     rsp, 28h
0x180003a5b  retn
```
