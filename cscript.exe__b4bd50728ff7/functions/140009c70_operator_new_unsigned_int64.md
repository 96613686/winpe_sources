# operator new(unsigned __int64)

- ea: `0x140009c70`
- end: `0x140009ca9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x140001bd0`
- `0x140002054`
- `0x140002260`
- `0x140002a70`
- `0x140003e2c`
- `0x1400046bc`
- `0x140007580`
- `0x140008530`
- `0x14000929c`
- `0x140009474`
- `0x140009514`
- `0x1400096bc`
- `0x14000d830`
- `0x14000e110`
- `0x140010810`
- `0x140010a20`
- `0x140011f90`
- `0x140013904`
- `0x140013bf8`
- `0x1400152bc`

## callees

- `0x140009c70`
- `0x140009dab`
- `0x140009db7`

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
0x140009c70  mov     [rsp+arg_0], rbx
0x140009c75  push    rdi
0x140009c76  sub     rsp, 20h
0x140009c7a  mov     rdi, rcx
0x140009c7d  jmp     short loc_140009C8E
0x140009c7f  mov     rcx, rdi; Size
0x140009c82  call    _callnewh_0
0x140009c87  test    eax, eax
0x140009c89  jz      short loc_140009C9B
0x140009c8b  mov     rcx, rdi; Size
0x140009c8e  call    malloc_0
0x140009c93  mov     rbx, rax
0x140009c96  test    rax, rax
0x140009c99  jz      short loc_140009C7F
0x140009c9b  mov     rax, rbx
0x140009c9e  mov     rbx, [rsp+28h+arg_0]
0x140009ca3  add     rsp, 20h
0x140009ca7  pop     rdi
0x140009ca8  retn
```
