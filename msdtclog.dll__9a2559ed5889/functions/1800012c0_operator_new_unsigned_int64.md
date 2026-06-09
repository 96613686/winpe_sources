# operator new(unsigned __int64)

- ea: `0x1800012c0`
- end: `0x1800012f9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x18000130c`
- `0x1800042b4`
- `0x1800044c8`
- `0x1800047b0`
- `0x180004a00`
- `0x1800062a0`
- `0x1800065c8`
- `0x1800073b4`
- `0x180008aa0`
- `0x180010364`
- `0x180010d70`
- `0x18001135c`

## callees

- `0x1800012c0`
- `0x1800018ed`
- `0x180001d59`

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
0x1800012c0  mov     [rsp+arg_0], rbx
0x1800012c5  push    rdi
0x1800012c6  sub     rsp, 20h
0x1800012ca  mov     rdi, rcx
0x1800012cd  jmp     short loc_1800012DE
0x1800012cf  mov     rcx, rdi; Size
0x1800012d2  call    _callnewh_0
0x1800012d7  test    eax, eax
0x1800012d9  jz      short loc_1800012EB
0x1800012db  mov     rcx, rdi; Size
0x1800012de  call    malloc_0
0x1800012e3  mov     rbx, rax
0x1800012e6  test    rax, rax
0x1800012e9  jz      short loc_1800012CF
0x1800012eb  mov     rax, rbx
0x1800012ee  mov     rbx, [rsp+28h+arg_0]
0x1800012f3  add     rsp, 20h
0x1800012f7  pop     rdi
0x1800012f8  retn
```
