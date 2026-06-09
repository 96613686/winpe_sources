# operator new(unsigned __int64)

- ea: `0x180001014`
- end: `0x18000104d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800069b0`
- `0x180006ac0`
- `0x180006bc0`
- `0x180006cd0`
- `0x180006dd0`
- `0x180006ed0`
- `0x180006fd0`

## callees

- `0x180001014`
- `0x180001554`
- `0x180001746`

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
0x180001014  mov     [rsp+arg_0], rbx
0x180001019  push    rdi
0x18000101a  sub     rsp, 20h
0x18000101e  mov     rdi, rcx
0x180001021  jmp     short loc_180001032
0x180001023  mov     rcx, rdi; Size
0x180001026  call    _callnewh_0
0x18000102b  test    eax, eax
0x18000102d  jz      short loc_18000103F
0x18000102f  mov     rcx, rdi; Size
0x180001032  call    malloc_0
0x180001037  mov     rbx, rax
0x18000103a  test    rax, rax
0x18000103d  jz      short loc_180001023
0x18000103f  mov     rax, rbx
0x180001042  mov     rbx, [rsp+28h+arg_0]
0x180001047  add     rsp, 20h
0x18000104b  pop     rdi
0x18000104c  retn
```
