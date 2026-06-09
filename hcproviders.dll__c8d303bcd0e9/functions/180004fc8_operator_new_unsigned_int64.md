# operator new(unsigned __int64)

- ea: `0x180004fc8`
- end: `0x180005001`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180001490`
- `0x1800019f0`
- `0x1800020d0`
- `0x180002650`
- `0x180003320`
- `0x180003450`
- `0x180003810`
- `0x180004550`
- `0x180007f20`
- `0x180008768`
- `0x180008bec`
- `0x180009458`
- `0x180009b04`
- `0x180009cdc`

## callees

- `0x180004fc8`
- `0x1800054e2`
- `0x1800054ee`

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
0x180004fc8  mov     [rsp+arg_0], rbx
0x180004fcd  push    rdi
0x180004fce  sub     rsp, 20h
0x180004fd2  mov     rdi, rcx
0x180004fd5  jmp     short loc_180004FE6
0x180004fd7  mov     rcx, rdi; Size
0x180004fda  call    _callnewh_0
0x180004fdf  test    eax, eax
0x180004fe1  jz      short loc_180004FF3
0x180004fe3  mov     rcx, rdi; Size
0x180004fe6  call    malloc_0
0x180004feb  mov     rbx, rax
0x180004fee  test    rax, rax
0x180004ff1  jz      short loc_180004FD7
0x180004ff3  mov     rax, rbx
0x180004ff6  mov     rbx, [rsp+28h+arg_0]
0x180004ffb  add     rsp, 20h
0x180004fff  pop     rdi
0x180005000  retn
```
