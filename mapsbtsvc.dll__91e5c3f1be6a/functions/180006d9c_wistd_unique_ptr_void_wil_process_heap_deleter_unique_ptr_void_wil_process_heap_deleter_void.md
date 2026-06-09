# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180006d9c`
- end: `0x180006dbc`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(wil::details **, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008104`
- `0x180013e32`

## callees

- `0x180006d9c`
- `0x18000722c`

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
0x180006d9c  sub     rsp, 28h
0x180006da0  mov     rax, [rcx]
0x180006da3  mov     qword ptr [rcx], 0
0x180006daa  test    rax, rax
0x180006dad  jz      short loc_180006DB7
0x180006daf  mov     rcx, rax; this
0x180006db2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180006db7  add     rsp, 28h
0x180006dbb  retn
```
