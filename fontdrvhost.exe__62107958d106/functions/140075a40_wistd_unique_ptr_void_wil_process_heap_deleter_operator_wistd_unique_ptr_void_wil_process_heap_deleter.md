# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x140075a40`
- end: `0x140075a6c`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140075684`
- `0x14007599c`

## callees

- `0x140075a40`
- `0x14007887c`

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
0x140075a40  push    rbx
0x140075a42  sub     rsp, 20h
0x140075a46  mov     rax, [rdx]
0x140075a49  mov     rbx, rcx
0x140075a4c  mov     qword ptr [rdx], 0
0x140075a53  mov     rcx, [rcx]; this
0x140075a56  mov     [rbx], rax
0x140075a59  test    rcx, rcx
0x140075a5c  jz      short loc_140075A63
0x140075a5e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140075a63  mov     rax, rbx
0x140075a66  add     rsp, 20h
0x140075a6a  pop     rbx
0x140075a6b  retn
```
