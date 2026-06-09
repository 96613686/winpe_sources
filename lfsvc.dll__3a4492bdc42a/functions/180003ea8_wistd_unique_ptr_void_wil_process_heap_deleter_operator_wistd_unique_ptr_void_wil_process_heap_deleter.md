# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180003ea8`
- end: `0x180003ed4`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: `wil::details **__fastcall(wil::details **, wil::details **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003494`
- `0x180003de8`

## callees

- `0x180003ea8`
- `0x180006b7c`

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
0x180003ea8  push    rbx
0x180003eaa  sub     rsp, 20h
0x180003eae  mov     rax, [rdx]
0x180003eb1  mov     rbx, rcx
0x180003eb4  mov     qword ptr [rdx], 0
0x180003ebb  mov     rcx, [rcx]; this
0x180003ebe  mov     [rbx], rax
0x180003ec1  test    rcx, rcx
0x180003ec4  jz      short loc_180003ECB
0x180003ec6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003ecb  mov     rax, rbx
0x180003ece  add     rsp, 20h
0x180003ed2  pop     rbx
0x180003ed3  retn
```
