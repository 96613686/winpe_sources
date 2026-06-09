# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x1800164b0`
- end: `0x1800164dc`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018bd4`
- `0x180019d50`

## callees

- `0x1800164b0`
- `0x180016f7c`

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
0x1800164b0  push    rbx
0x1800164b2  sub     rsp, 20h
0x1800164b6  mov     rax, [rdx]
0x1800164b9  mov     rbx, rcx
0x1800164bc  mov     qword ptr [rdx], 0
0x1800164c3  mov     rcx, [rcx]; this
0x1800164c6  mov     [rbx], rax
0x1800164c9  test    rcx, rcx
0x1800164cc  jz      short loc_1800164D3
0x1800164ce  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800164d3  mov     rax, rbx
0x1800164d6  add     rsp, 20h
0x1800164da  pop     rbx
0x1800164db  retn
```
