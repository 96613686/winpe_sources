# operator new(unsigned __int64)

- ea: `0x180001254`
- end: `0x18000128d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180002660`
- `0x180003110`
- `0x180005fd4`
- `0x180006700`
- `0x180007630`
- `0x18000b3c0`
- `0x18000c4e0`

## callees

- `0x180001254`
- `0x180001858`
- `0x180001864`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001254  mov     [rsp+arg_0], rbx
0x180001259  push    rdi
0x18000125a  sub     rsp, 20h
0x18000125e  mov     rdi, rcx
0x180001261  jmp     short loc_180001272
0x180001263  mov     rcx, rdi; Size
0x180001266  call    _callnewh_0
0x18000126b  test    eax, eax
0x18000126d  jz      short loc_18000127F
0x18000126f  mov     rcx, rdi; Size
0x180001272  call    malloc_0
0x180001277  mov     rbx, rax
0x18000127a  test    rax, rax
0x18000127d  jz      short loc_180001263
0x18000127f  mov     rax, rbx
0x180001282  mov     rbx, [rsp+28h+arg_0]
0x180001287  add     rsp, 20h
0x18000128b  pop     rdi
0x18000128c  retn
```
