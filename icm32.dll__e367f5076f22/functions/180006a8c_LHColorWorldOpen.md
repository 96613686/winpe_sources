# LHColorWorldOpen

- ea: `0x180006a8c`
- end: `0x180006ae2`
- name: `LHColorWorldOpen`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006964`

## callees

- `0x180006a8c`
- `0x18001d15d`
- `0x18003d00e`

## pseudocode

```c
__int64 __fastcall LHColorWorldOpen(_QWORD *a1)
{
  void *v2; // rax
  void *v3; // rdi
  unsigned int v4; // ebx

  v2 = malloc_0(0x218u);
  v3 = v2;
  v4 = v2 == 0 ? 8 : 0;
  if ( v2 )
  {
    memset_0(v2, 0, 0x218u);
    *a1 = v3;
  }
  return v4;
}

```

## disassembly

```asm
0x180006a8c  mov     [rsp+arg_0], rbx
0x180006a91  mov     [rsp+arg_8], rsi
0x180006a96  push    rdi
0x180006a97  sub     rsp, 20h
0x180006a9b  mov     rsi, rcx
0x180006a9e  mov     ecx, 218h; Size
0x180006aa3  call    malloc_0
0x180006aa8  mov     rdx, rax
0x180006aab  mov     rdi, rax
0x180006aae  neg     rdx
0x180006ab1  sbb     ebx, ebx
0x180006ab3  not     ebx
0x180006ab5  and     ebx, 8
0x180006ab8  test    rax, rax
0x180006abb  jz      short loc_180006AD0
0x180006abd  xor     edx, edx; Val
0x180006abf  mov     r8d, 218h; Size
0x180006ac5  mov     rcx, rax; void *
0x180006ac8  call    memset_0
0x180006acd  mov     [rsi], rdi
0x180006ad0  mov     rsi, [rsp+28h+arg_8]
0x180006ad5  mov     eax, ebx
0x180006ad7  mov     rbx, [rsp+28h+arg_0]
0x180006adc  add     rsp, 20h
0x180006ae0  pop     rdi
0x180006ae1  retn
```
