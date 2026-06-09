# operator new(unsigned __int64)

- ea: `0x180001088`
- end: `0x1800010c1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a40`
- `0x180002f68`
- `0x1800030a0`
- `0x180004110`
- `0x180004290`

## callees

- `0x180001088`
- `0x18000166d`
- `0x180001679`

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
0x180001088  mov     [rsp+arg_0], rbx
0x18000108d  push    rdi
0x18000108e  sub     rsp, 20h
0x180001092  mov     rdi, rcx
0x180001095  jmp     short loc_1800010A6
0x180001097  mov     rcx, rdi; Size
0x18000109a  call    _callnewh_0
0x18000109f  test    eax, eax
0x1800010a1  jz      short loc_1800010B3
0x1800010a3  mov     rcx, rdi; Size
0x1800010a6  call    malloc_0
0x1800010ab  mov     rbx, rax
0x1800010ae  test    rax, rax
0x1800010b1  jz      short loc_180001097
0x1800010b3  mov     rax, rbx
0x1800010b6  mov     rbx, [rsp+28h+arg_0]
0x1800010bb  add     rsp, 20h
0x1800010bf  pop     rdi
0x1800010c0  retn
```
