# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180007cf8`
- end: `0x180007d24`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a7d4`
- `0x18000b8ec`

## callees

- `0x180007cf8`
- `0x180008794`

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
0x180007cf8  push    rbx
0x180007cfa  sub     rsp, 20h
0x180007cfe  mov     rax, [rdx]
0x180007d01  mov     rbx, rcx
0x180007d04  mov     qword ptr [rdx], 0
0x180007d0b  mov     rcx, [rcx]; this
0x180007d0e  mov     [rbx], rax
0x180007d11  test    rcx, rcx
0x180007d14  jz      short loc_180007D1B
0x180007d16  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007d1b  mov     rax, rbx
0x180007d1e  add     rsp, 20h
0x180007d22  pop     rbx
0x180007d23  retn
```
