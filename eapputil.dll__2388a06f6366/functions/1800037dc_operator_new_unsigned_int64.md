# operator new(unsigned __int64)

- ea: `0x1800037dc`
- end: `0x180003818`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `70`
- callee_count: `5`
- tags: ``

## callers

- `0x180003820`
- `0x180003868`
- `0x18000840c`
- `0x18000cdb0`
- `0x18000e2bc`
- `0x18000e3bc`
- `0x18000e4c0`
- `0x18000e5b4`
- `0x18000f900`
- `0x18001109c`
- `0x1800112ec`
- `0x180011424`
- `0x180011aa0`
- `0x180012b00`
- `0x1800137f0`
- `0x180013c58`
- `0x1800141e4`
- `0x1800144b4`
- `0x1800152a8`
- `0x180015464`
- `0x1800155e8`
- `0x180015750`
- `0x1800158bc`
- `0x180016270`
- `0x18001636c`
- `0x180016458`
- `0x1800164e8`
- `0x180016b94`
- `0x180016d94`
- `0x18001eda4`
- `0x18001fc00`
- `0x18001fcc0`
- `0x18001fd60`
- `0x18001fe68`
- `0x18002010c`
- `0x180020388`
- `0x180020644`
- `0x1800207d4`
- `0x180020828`
- `0x180020d88`
- `0x18002137c`
- `0x1800214ac`
- `0x180021640`
- `0x180021764`
- `0x1800223f8`
- `0x18002265c`
- `0x18002344c`
- `0x1800253d0`
- `0x1800256d0`
- `0x180025808`

## callees

- `0x180002ac6`
- `0x180002b60`
- `0x1800037dc`
- `0x180003904`
- `0x1800101e4`

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
0x1800037dc  push    rbx
0x1800037de  sub     rsp, 20h
0x1800037e2  mov     rbx, rcx
0x1800037e5  jmp     short loc_1800037F6
0x1800037e7  mov     rcx, rbx
0x1800037ea  call    _o__callnewh_0
0x1800037ef  test    eax, eax
0x1800037f1  jz      short loc_180003806
0x1800037f3  mov     rcx, rbx; Size
0x1800037f6  call    _o_malloc_0
0x1800037fb  test    rax, rax
0x1800037fe  jz      short loc_1800037E7
0x180003800  add     rsp, 20h
0x180003804  pop     rbx
0x180003805  retn
0x180003806  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000380a  jz      short loc_180003812
0x18000380c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180003812  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
