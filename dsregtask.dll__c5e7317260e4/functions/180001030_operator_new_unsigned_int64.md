# operator new(unsigned __int64)

- ea: `0x180001030`
- end: `0x180001069`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f50`
- `0x180002b40`

## callees

- `0x180001030`
- `0x180001d06`
- `0x180001d7e`

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
0x180001030  mov     [rsp+arg_0], rbx
0x180001035  push    rdi
0x180001036  sub     rsp, 20h
0x18000103a  mov     rdi, rcx
0x18000103d  jmp     short loc_18000104E
0x18000103f  mov     rcx, rdi
0x180001042  call    _o__callnewh_0
0x180001047  test    eax, eax
0x180001049  jz      short loc_18000105B
0x18000104b  mov     rcx, rdi; Size
0x18000104e  call    _o_malloc_0
0x180001053  mov     rbx, rax
0x180001056  test    rax, rax
0x180001059  jz      short loc_18000103F
0x18000105b  mov     rax, rbx
0x18000105e  mov     rbx, [rsp+28h+arg_0]
0x180001063  add     rsp, 20h
0x180001067  pop     rdi
0x180001068  retn
```
