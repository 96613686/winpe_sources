# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1800042b8`
- end: `0x1800042e4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ccc`
- `0x180008fbc`

## callees

- `0x1800042b8`
- `0x180005abc`

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
0x1800042b8  push    rbx
0x1800042ba  sub     rsp, 20h
0x1800042be  mov     rax, [rdx]
0x1800042c1  mov     rbx, rcx
0x1800042c4  mov     qword ptr [rdx], 0
0x1800042cb  mov     rcx, [rcx]; this
0x1800042ce  mov     [rbx], rax
0x1800042d1  test    rcx, rcx
0x1800042d4  jz      short loc_1800042DB
0x1800042d6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800042db  mov     rax, rbx
0x1800042de  add     rsp, 20h
0x1800042e2  pop     rbx
0x1800042e3  retn
```
