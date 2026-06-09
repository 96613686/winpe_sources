# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180004498`
- end: `0x1800044b8`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065a0`

## callees

- `0x180004498`
- `0x1800052cc`

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
0x180004498  sub     rsp, 28h
0x18000449c  mov     rax, [rcx]
0x18000449f  mov     qword ptr [rcx], 0
0x1800044a6  test    rax, rax
0x1800044a9  jz      short loc_1800044B3
0x1800044ab  mov     rcx, rax; this
0x1800044ae  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800044b3  add     rsp, 28h
0x1800044b7  retn
```
