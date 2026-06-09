# operator new(unsigned __int64)

- ea: `0x180005460`
- end: `0x180005499`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001310`
- `0x180002bb0`
- `0x180002e00`
- `0x1800036d0`
- `0x180003a50`
- `0x180003de0`
- `0x180004180`
- `0x180004d70`
- `0x1800051c0`
- `0x180005380`
- `0x180008c90`

## callees

- `0x180005460`
- `0x180005982`
- `0x18000598e`

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
0x180005460  mov     [rsp+arg_0], rbx
0x180005465  push    rdi
0x180005466  sub     rsp, 20h
0x18000546a  mov     rdi, rcx
0x18000546d  jmp     short loc_18000547E
0x18000546f  mov     rcx, rdi; Size
0x180005472  call    _callnewh_0
0x180005477  test    eax, eax
0x180005479  jz      short loc_18000548B
0x18000547b  mov     rcx, rdi; Size
0x18000547e  call    malloc_0
0x180005483  mov     rbx, rax
0x180005486  test    rax, rax
0x180005489  jz      short loc_18000546F
0x18000548b  mov     rax, rbx
0x18000548e  mov     rbx, [rsp+28h+arg_0]
0x180005493  add     rsp, 20h
0x180005497  pop     rdi
0x180005498  retn
```
