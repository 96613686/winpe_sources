# operator new(unsigned __int64)

- ea: `0x140001c08`
- end: `0x140001c41`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001c48`
- `0x140004948`
- `0x140004a44`
- `0x1400058e4`
- `0x14000a904`

## callees

- `0x140001c08`
- `0x140002aca`
- `0x140002b96`

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
0x140001c08  mov     [rsp+arg_0], rbx
0x140001c0d  push    rdi
0x140001c0e  sub     rsp, 20h
0x140001c12  mov     rdi, rcx
0x140001c15  jmp     short loc_140001C26
0x140001c17  mov     rcx, rdi
0x140001c1a  call    _o__callnewh_0
0x140001c1f  test    eax, eax
0x140001c21  jz      short loc_140001C33
0x140001c23  mov     rcx, rdi; Size
0x140001c26  call    _o_malloc_0
0x140001c2b  mov     rbx, rax
0x140001c2e  test    rax, rax
0x140001c31  jz      short loc_140001C17
0x140001c33  mov     rax, rbx
0x140001c36  mov     rbx, [rsp+28h+arg_0]
0x140001c3b  add     rsp, 20h
0x140001c3f  pop     rdi
0x140001c40  retn
```
