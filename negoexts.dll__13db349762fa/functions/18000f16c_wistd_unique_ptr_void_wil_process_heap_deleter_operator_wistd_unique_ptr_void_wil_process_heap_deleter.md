# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x18000f16c`
- end: `0x18000f198`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e244`
- `0x18000f0c8`

## callees

- `0x18000f16c`
- `0x18001145c`

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
0x18000f16c  push    rbx
0x18000f16e  sub     rsp, 20h
0x18000f172  mov     rax, [rdx]
0x18000f175  mov     rbx, rcx
0x18000f178  mov     qword ptr [rdx], 0
0x18000f17f  mov     rcx, [rcx]; this
0x18000f182  mov     [rbx], rax
0x18000f185  test    rcx, rcx
0x18000f188  jz      short loc_18000F18F
0x18000f18a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000f18f  mov     rax, rbx
0x18000f192  add     rsp, 20h
0x18000f196  pop     rbx
0x18000f197  retn
```
