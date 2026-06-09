# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1800041e4`
- end: `0x180004210`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032ec`
- `0x1800038b4`

## callees

- `0x1800041b8`
- `0x1800041e4`

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
0x1800041e4  push    rbx
0x1800041e6  sub     rsp, 20h
0x1800041ea  mov     rax, [rdx]
0x1800041ed  mov     rbx, rcx
0x1800041f0  mov     qword ptr [rdx], 0
0x1800041f7  mov     rcx, [rcx]; this
0x1800041fa  mov     [rbx], rax
0x1800041fd  test    rcx, rcx
0x180004200  jz      short loc_180004207
0x180004202  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004207  mov     rax, rbx
0x18000420a  add     rsp, 20h
0x18000420e  pop     rbx
0x18000420f  retn
```
