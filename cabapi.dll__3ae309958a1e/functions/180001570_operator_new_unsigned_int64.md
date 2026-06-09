# operator new(unsigned __int64)

- ea: `0x180001570`
- end: `0x1800015ac`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `19`
- callee_count: `5`
- tags: ``

## callers

- `0x180002230`
- `0x180002ddc`
- `0x180003030`
- `0x180007b64`
- `0x1800080a0`
- `0x18000ab80`
- `0x18000acb0`
- `0x18000adf0`
- `0x18000af44`
- `0x18000c38c`
- `0x18000c7a4`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000da00`
- `0x18000dc30`
- `0x18000dd60`
- `0x18000debc`
- `0x18000fe48`
- `0x180010d4c`

## callees

- `0x180001570`
- `0x180001b90`
- `0x180001ef2`
- `0x180001fa6`
- `0x180006764`

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
0x180001570  push    rbx
0x180001572  sub     rsp, 20h
0x180001576  mov     rbx, rcx
0x180001579  jmp     short loc_18000158A
0x18000157b  mov     rcx, rbx
0x18000157e  call    _o__callnewh_0
0x180001583  test    eax, eax
0x180001585  jz      short loc_18000159A
0x180001587  mov     rcx, rbx; Size
0x18000158a  call    _o_malloc_0
0x18000158f  test    rax, rax
0x180001592  jz      short loc_18000157B
0x180001594  add     rsp, 20h
0x180001598  pop     rbx
0x180001599  retn
0x18000159a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000159e  jz      short loc_1800015A6
0x1800015a0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800015a6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
