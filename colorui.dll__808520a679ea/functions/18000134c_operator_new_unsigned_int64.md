# operator new(unsigned __int64)

- ea: `0x18000134c`
- end: `0x180001385`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x18000138c`
- `0x180001cd4`
- `0x180004df0`
- `0x180004ed0`
- `0x180004f80`
- `0x180005060`
- `0x180005140`
- `0x180006880`
- `0x18000c018`
- `0x18000c65c`
- `0x18000d060`
- `0x18000d338`
- `0x18000e7ac`
- `0x18000eff0`
- `0x18000fc80`
- `0x18000ffe0`
- `0x180010404`
- `0x180010780`
- `0x180012e80`
- `0x180015428`
- `0x180016530`
- `0x180016fa8`
- `0x1800174f0`
- `0x18001775c`
- `0x1800178d4`
- `0x1800179f0`
- `0x180017ab0`

## callees

- `0x18000134c`
- `0x180001cc8`
- `0x180001cf9`

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
0x18000134c  mov     [rsp+arg_0], rbx
0x180001351  push    rdi
0x180001352  sub     rsp, 20h
0x180001356  mov     rdi, rcx
0x180001359  jmp     short loc_18000136A
0x18000135b  mov     rcx, rdi; Size
0x18000135e  call    _callnewh_0
0x180001363  test    eax, eax
0x180001365  jz      short loc_180001377
0x180001367  mov     rcx, rdi; Size
0x18000136a  call    malloc_0
0x18000136f  mov     rbx, rax
0x180001372  test    rax, rax
0x180001375  jz      short loc_18000135B
0x180001377  mov     rax, rbx
0x18000137a  mov     rbx, [rsp+28h+arg_0]
0x18000137f  add     rsp, 20h
0x180001383  pop     rdi
0x180001384  retn
```
