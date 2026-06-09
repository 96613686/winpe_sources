# operator new(unsigned __int64)

- ea: `0x18000a6dc`
- end: `0x18000a715`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180007720`
- `0x18000793c`
- `0x1800086d0`
- `0x18000a71c`
- `0x180014d84`
- `0x18001a064`
- `0x18001fae0`

## callees

- `0x18000a6dc`
- `0x18000b3b6`
- `0x18000b450`

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
0x18000a6dc  mov     [rsp+arg_0], rbx
0x18000a6e1  push    rdi
0x18000a6e2  sub     rsp, 20h
0x18000a6e6  mov     rdi, rcx
0x18000a6e9  jmp     short loc_18000A6FA
0x18000a6eb  mov     rcx, rdi
0x18000a6ee  call    _o__callnewh_0
0x18000a6f3  test    eax, eax
0x18000a6f5  jz      short loc_18000A707
0x18000a6f7  mov     rcx, rdi; Size
0x18000a6fa  call    _o_malloc_0
0x18000a6ff  mov     rbx, rax
0x18000a702  test    rax, rax
0x18000a705  jz      short loc_18000A6EB
0x18000a707  mov     rax, rbx
0x18000a70a  mov     rbx, [rsp+28h+arg_0]
0x18000a70f  add     rsp, 20h
0x18000a713  pop     rdi
0x18000a714  retn
```
