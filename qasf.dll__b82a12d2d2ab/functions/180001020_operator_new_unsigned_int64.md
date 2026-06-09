# operator new(unsigned __int64)

- ea: `0x180001020`
- end: `0x180001059`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `29`
- callee_count: `3`
- tags: ``

## callers

- `0x180001014`
- `0x180001df0`
- `0x180003c00`
- `0x1800040d0`
- `0x180004170`
- `0x180004850`
- `0x1800048c0`
- `0x180006f48`
- `0x180007bb0`
- `0x1800081a0`
- `0x1800083d0`
- `0x1800085e0`
- `0x1800090f0`
- `0x18000ab04`
- `0x18000d040`
- `0x18000e444`
- `0x18000f3c0`
- `0x180010224`
- `0x180010dfc`
- `0x180012130`
- `0x180014ea0`
- `0x180016500`
- `0x180016540`
- `0x1800165e8`
- `0x180017fd0`
- `0x180019d10`
- `0x18001b610`
- `0x18001bf60`
- `0x18001c39c`

## callees

- `0x180001020`
- `0x180001c76`
- `0x180001ce4`

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
0x180001020  mov     [rsp+arg_0], rbx
0x180001025  push    rdi
0x180001026  sub     rsp, 20h
0x18000102a  mov     rdi, rcx
0x18000102d  jmp     short loc_18000103E
0x18000102f  mov     rcx, rdi
0x180001032  call    _o__callnewh_0
0x180001037  test    eax, eax
0x180001039  jz      short loc_18000104B
0x18000103b  mov     rcx, rdi; Size
0x18000103e  call    _o_malloc_0
0x180001043  mov     rbx, rax
0x180001046  test    rax, rax
0x180001049  jz      short loc_18000102F
0x18000104b  mov     rax, rbx
0x18000104e  mov     rbx, [rsp+28h+arg_0]
0x180001053  add     rsp, 20h
0x180001057  pop     rdi
0x180001058  retn
```
