# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x14000f3c8`
- end: `0x14000f3f4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008c20`
- `0x14000fa30`
- `0x140017bc8`

## callees

- `0x14000f3c8`
- `0x140011c6c`

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
0x14000f3c8  push    rbx
0x14000f3ca  sub     rsp, 20h
0x14000f3ce  mov     rax, [rdx]
0x14000f3d1  mov     rbx, rcx
0x14000f3d4  mov     qword ptr [rdx], 0
0x14000f3db  mov     rcx, [rcx]; this
0x14000f3de  mov     [rbx], rax
0x14000f3e1  test    rcx, rcx
0x14000f3e4  jz      short loc_14000F3EB
0x14000f3e6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000f3eb  mov     rax, rbx
0x14000f3ee  add     rsp, 20h
0x14000f3f2  pop     rbx
0x14000f3f3  retn
```
