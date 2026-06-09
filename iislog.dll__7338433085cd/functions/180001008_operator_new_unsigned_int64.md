# operator new(unsigned __int64)

- ea: `0x180001008`
- end: `0x180001041`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ea0`
- `0x180002c8c`
- `0x18000373c`
- `0x180004044`
- `0x180004810`
- `0x180004a5c`
- `0x180006870`
- `0x180008720`
- `0x1800097d0`
- `0x180009940`
- `0x180009ab0`
- `0x180009c20`
- `0x180009d50`
- `0x18000a51c`
- `0x18000afb0`
- `0x18000b120`
- `0x18000ba58`
- `0x18000d740`
- `0x18000e600`

## callees

- `0x180001008`
- `0x18000153e`
- `0x180001874`

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
