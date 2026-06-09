# operator new(unsigned __int64)

- ea: `0x1800026d4`
- end: `0x180002710`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x180002718`
- `0x180002b4c`
- `0x180005c00`
- `0x180005fdc`
- `0x180006f8c`
- `0x18000b3e0`
- `0x18001b860`
- `0x18001b900`
- `0x18001b9b8`
- `0x18001f1f0`
- `0x1800210d0`

## callees

- `0x1800026d4`
- `0x180003024`
- `0x1800032b2`
- `0x180003350`
- `0x1800163ac`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800026d4  push    rbx
0x1800026d6  sub     rsp, 20h
0x1800026da  mov     rbx, rcx
0x1800026dd  jmp     short loc_1800026EE
0x1800026df  mov     rcx, rbx
0x1800026e2  call    _o__callnewh_0
0x1800026e7  test    eax, eax
0x1800026e9  jz      short loc_1800026FE
0x1800026eb  mov     rcx, rbx; Size
0x1800026ee  call    _o_malloc_0
0x1800026f3  test    rax, rax
0x1800026f6  jz      short loc_1800026DF
0x1800026f8  add     rsp, 20h
0x1800026fc  pop     rbx
0x1800026fd  retn
0x1800026fe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002702  jz      short loc_18000270A
0x180002704  call    ?__scrt_throw_std_bad_alloc@@YAXXZ
0x18000270a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ
```
