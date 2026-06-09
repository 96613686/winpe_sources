# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x140007118`
- end: `0x140007144`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140008cd4`
- `0x140009920`

## callees

- `0x1400045bc`
- `0x140007118`

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
0x140007118  push    rbx
0x14000711a  sub     rsp, 20h
0x14000711e  mov     rax, [rdx]
0x140007121  mov     rbx, rcx
0x140007124  mov     qword ptr [rdx], 0
0x14000712b  mov     rcx, [rcx]; this
0x14000712e  mov     [rbx], rax
0x140007131  test    rcx, rcx
0x140007134  jz      short loc_14000713B
0x140007136  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000713b  mov     rax, rbx
0x14000713e  add     rsp, 20h
0x140007142  pop     rbx
0x140007143  retn
```
