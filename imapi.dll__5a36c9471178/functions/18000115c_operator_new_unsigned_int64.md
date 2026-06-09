# operator new(unsigned __int64)

- ea: `0x18000115c`
- end: `0x180001195`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x18000119c`
- `0x180002c18`
- `0x180002d30`
- `0x180004784`
- `0x180006224`
- `0x180006320`
- `0x1800064e0`
- `0x180008784`
- `0x1800088b8`
- `0x18000aaa4`
- `0x18000b8f0`
- `0x18000bb64`
- `0x18000bc60`
- `0x18000e958`
- `0x1800108a8`
- `0x180010e98`
- `0x1800110a8`
- `0x180011260`
- `0x180011a00`
- `0x180011d00`
- `0x180015260`
- `0x180015bd8`
- `0x1800165b4`

## callees

- `0x18000115c`
- `0x180001a86`
- `0x180001c41`

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
0x18000115c  mov     [rsp+arg_0], rbx
0x180001161  push    rdi
0x180001162  sub     rsp, 20h
0x180001166  mov     rdi, rcx
0x180001169  jmp     short loc_18000117A
0x18000116b  mov     rcx, rdi; Size
0x18000116e  call    _callnewh_0
0x180001173  test    eax, eax
0x180001175  jz      short loc_180001187
0x180001177  mov     rcx, rdi; Size
0x18000117a  call    malloc_0
0x18000117f  mov     rbx, rax
0x180001182  test    rax, rax
0x180001185  jz      short loc_18000116B
0x180001187  mov     rax, rbx
0x18000118a  mov     rbx, [rsp+28h+arg_0]
0x18000118f  add     rsp, 20h
0x180001193  pop     rdi
0x180001194  retn
```
