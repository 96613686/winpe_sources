# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000f5ac`
- end: `0x18000f5d8`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f1f0`
- `0x18000f508`

## callees

- `0x180002a8c`
- `0x18000f5ac`

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
0x18000f5ac  push    rbx
0x18000f5ae  sub     rsp, 20h
0x18000f5b2  mov     rax, [rdx]
0x18000f5b5  mov     rbx, rcx
0x18000f5b8  mov     qword ptr [rdx], 0
0x18000f5bf  mov     rcx, [rcx]; this
0x18000f5c2  mov     [rbx], rax
0x18000f5c5  test    rcx, rcx
0x18000f5c8  jz      short loc_18000F5CF
0x18000f5ca  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000f5cf  mov     rax, rbx
0x18000f5d2  add     rsp, 20h
0x18000f5d6  pop     rbx
0x18000f5d7  retn
```
