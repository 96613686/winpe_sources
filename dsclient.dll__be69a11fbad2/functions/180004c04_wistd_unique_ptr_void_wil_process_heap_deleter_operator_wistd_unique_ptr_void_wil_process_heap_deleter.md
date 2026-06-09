# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180004c04`
- end: `0x180004c30`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007240`
- `0x180008228`

## callees

- `0x180004c04`
- `0x18000563c`

## pseudocode

```c
wil::details **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(
        wil::details **a1,
        wil::details **a2)
{
  wil::details *v2; // rax
  wil::details *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x180004c04  push    rbx
0x180004c06  sub     rsp, 20h
0x180004c0a  mov     rax, [rdx]
0x180004c0d  mov     rbx, rcx
0x180004c10  mov     qword ptr [rdx], 0
0x180004c17  mov     rcx, [rcx]; this
0x180004c1a  mov     [rbx], rax
0x180004c1d  test    rcx, rcx
0x180004c20  jz      short loc_180004C27
0x180004c22  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004c27  mov     rax, rbx
0x180004c2a  add     rsp, 20h
0x180004c2e  pop     rbx
0x180004c2f  retn
```
