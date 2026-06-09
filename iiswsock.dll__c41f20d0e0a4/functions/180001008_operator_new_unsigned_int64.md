# operator new(unsigned __int64)

- ea: `0x180001008`
- end: `0x180001041`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e44`
- `0x180003d60`
- `0x1800041dc`
- `0x180004bac`
- `0x180004ebc`
- `0x180005394`
- `0x180005568`
- `0x180006c98`
- `0x1800079b0`
- `0x180008080`

## callees

- `0x180001008`
- `0x180001526`
- `0x18000153e`

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
0x180001008  mov     [rsp+arg_0], rbx
0x18000100d  push    rdi
0x18000100e  sub     rsp, 20h
0x180001012  mov     rdi, rcx
0x180001015  jmp     short loc_180001026
0x180001017  mov     rcx, rdi; Size
0x18000101a  call    _callnewh_0
0x18000101f  test    eax, eax
0x180001021  jz      short loc_180001033
0x180001023  mov     rcx, rdi; Size
0x180001026  call    malloc_0
0x18000102b  mov     rbx, rax
0x18000102e  test    rax, rax
0x180001031  jz      short loc_180001017
0x180001033  mov     rax, rbx
0x180001036  mov     rbx, [rsp+28h+arg_0]
0x18000103b  add     rsp, 20h
0x18000103f  pop     rdi
0x180001040  retn
```
