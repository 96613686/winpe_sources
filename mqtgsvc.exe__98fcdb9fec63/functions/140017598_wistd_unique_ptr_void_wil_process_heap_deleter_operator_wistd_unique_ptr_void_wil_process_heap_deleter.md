# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x140017598`
- end: `0x1400175c5`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140019be4`
- `0x14001ad14`

## callees

- `0x140017598`
- `0x14001801c`

## pseudocode

```c
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
0x140017598  push    rbx
0x14001759a  sub     rsp, 20h
0x14001759e  mov     rbx, rcx
0x1400175a1  mov     rax, [rdx]
0x1400175a4  mov     qword ptr [rdx], 0
0x1400175ab  mov     rcx, [rcx]; this
0x1400175ae  mov     [rbx], rax
0x1400175b1  test    rcx, rcx
0x1400175b4  jz      short loc_1400175BC
0x1400175b6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400175bb  nop
0x1400175bc  mov     rax, rbx
0x1400175bf  add     rsp, 20h
0x1400175c3  pop     rbx
0x1400175c4  retn
```
