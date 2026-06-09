# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1800136c4`
- end: `0x1800136f1`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011c80`
- `0x180013620`

## callees

- `0x1800136c4`
- `0x18001fe7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wil::details **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(
        wil::details **a1,
        wil::details **a2)
{
  wil::details *v3; // rax
  wil::details *v4; // rcx

  v3 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v3;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x1800136c4  push    rbx
0x1800136c6  sub     rsp, 20h
0x1800136ca  mov     rbx, rcx
0x1800136cd  mov     rax, [rdx]
0x1800136d0  mov     qword ptr [rdx], 0
0x1800136d7  mov     rcx, [rcx]; this
0x1800136da  mov     [rbx], rax
0x1800136dd  test    rcx, rcx
0x1800136e0  jz      short loc_1800136E8
0x1800136e2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800136e7  nop
0x1800136e8  mov     rax, rbx
0x1800136eb  add     rsp, 20h
0x1800136ef  pop     rbx
0x1800136f0  retn
```
