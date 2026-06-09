# operator new(unsigned __int64)

- ea: `0x180002250`
- end: `0x180002289`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002290`
- `0x180003980`

## callees

- `0x180001c36`
- `0x180001ca4`
- `0x180002250`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180002250  mov     [rsp+arg_0], rbx
0x180002255  push    rdi
0x180002256  sub     rsp, 20h
0x18000225a  mov     rdi, rcx
0x18000225d  jmp     short loc_18000226E
0x18000225f  mov     rcx, rdi
0x180002262  call    _o__callnewh_0
0x180002267  test    eax, eax
0x180002269  jz      short loc_18000227B
0x18000226b  mov     rcx, rdi; Size
0x18000226e  call    _o_malloc_0
0x180002273  mov     rbx, rax
0x180002276  test    rax, rax
0x180002279  jz      short loc_18000225F
0x18000227b  mov     rax, rbx
0x18000227e  mov     rbx, [rsp+28h+arg_0]
0x180002283  add     rsp, 20h
0x180002287  pop     rdi
0x180002288  retn
```
