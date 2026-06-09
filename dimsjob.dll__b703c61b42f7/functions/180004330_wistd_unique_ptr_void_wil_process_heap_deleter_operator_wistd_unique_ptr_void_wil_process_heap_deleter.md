# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180004330`
- end: `0x18000435c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003864`
- `0x18000428c`

## callees

- `0x180004330`
- `0x1800064e4`

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
0x180004330  push    rbx
0x180004332  sub     rsp, 20h
0x180004336  mov     rax, [rdx]
0x180004339  mov     rbx, rcx
0x18000433c  mov     qword ptr [rdx], 0
0x180004343  mov     rcx, [rcx]; this
0x180004346  mov     [rbx], rax
0x180004349  test    rcx, rcx
0x18000434c  jz      short loc_180004353
0x18000434e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004353  mov     rax, rbx
0x180004356  add     rsp, 20h
0x18000435a  pop     rbx
0x18000435b  retn
```
