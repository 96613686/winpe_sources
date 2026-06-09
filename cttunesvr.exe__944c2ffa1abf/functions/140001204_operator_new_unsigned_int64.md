# operator new(unsigned __int64)

- ea: `0x140001204`
- end: `0x14000123d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011f8`
- `0x140002d80`
- `0x140002ed0`
- `0x1400031f4`

## callees

- `0x140001204`
- `0x140001622`
- `0x140001a85`

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
0x140001204  mov     [rsp+arg_0], rbx
0x140001209  push    rdi
0x14000120a  sub     rsp, 20h
0x14000120e  mov     rdi, rcx
0x140001211  jmp     short loc_140001222
0x140001213  mov     rcx, rdi; Size
0x140001216  call    _callnewh_0
0x14000121b  test    eax, eax
0x14000121d  jz      short loc_14000122F
0x14000121f  mov     rcx, rdi; Size
0x140001222  call    malloc_0
0x140001227  mov     rbx, rax
0x14000122a  test    rax, rax
0x14000122d  jz      short loc_140001213
0x14000122f  mov     rax, rbx
0x140001232  mov     rbx, [rsp+28h+arg_0]
0x140001237  add     rsp, 20h
0x14000123b  pop     rdi
0x14000123c  retn
```
