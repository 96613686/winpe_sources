# operator new(unsigned __int64)

- ea: `0x180001020`
- end: `0x180001059`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f2c`
- `0x180002c30`
- `0x1800055ac`
- `0x18000cc50`
- `0x18000e1bc`
- `0x1800107c8`
- `0x1800117cc`
- `0x180011d90`
- `0x180012068`

## callees

- `0x180001020`
- `0x180001732`
- `0x18000173e`

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
0x180001020  mov     [rsp+arg_0], rbx
0x180001025  push    rdi
0x180001026  sub     rsp, 20h
0x18000102a  mov     rdi, rcx
0x18000102d  jmp     short loc_18000103E
0x18000102f  mov     rcx, rdi; Size
0x180001032  call    _callnewh_0
0x180001037  test    eax, eax
0x180001039  jz      short loc_18000104B
0x18000103b  mov     rcx, rdi; Size
0x18000103e  call    malloc_0
0x180001043  mov     rbx, rax
0x180001046  test    rax, rax
0x180001049  jz      short loc_18000102F
0x18000104b  mov     rax, rbx
0x18000104e  mov     rbx, [rsp+28h+arg_0]
0x180001053  add     rsp, 20h
0x180001057  pop     rdi
0x180001058  retn
```
