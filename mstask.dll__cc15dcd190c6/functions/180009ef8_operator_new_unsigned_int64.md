# operator new(unsigned __int64)

- ea: `0x180009ef8`
- end: `0x180009f31`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `42`
- callee_count: `3`
- tags: ``

## callers

- `0x180001770`
- `0x180002530`
- `0x180002ab0`
- `0x180002ea0`
- `0x180003830`
- `0x180003ce0`
- `0x180003eb0`
- `0x180004060`
- `0x180004590`
- `0x180005270`
- `0x180005cd0`
- `0x180006120`
- `0x180006550`
- `0x180006ba0`
- `0x180006dd0`
- `0x180006ec0`
- `0x180007290`
- `0x180007860`
- `0x18000865c`
- `0x180009210`
- `0x180009490`
- `0x18000bb50`
- `0x18000d870`
- `0x18000dc70`
- `0x18000dd40`
- `0x18000de70`
- `0x18000df10`
- `0x18000f770`
- `0x18000fb90`
- `0x18000fc80`
- `0x1800101b4`
- `0x1800105a8`
- `0x180010710`
- `0x180010c90`
- `0x180011568`
- `0x180011fc0`
- `0x180012fe8`
- `0x1800144ac`
- `0x180014aa0`
- `0x180015570`
- `0x180016e14`
- `0x180019678`

## callees

- `0x180009ef8`
- `0x18000a734`
- `0x18000a740`

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
0x180009ef8  mov     [rsp+arg_0], rbx
0x180009efd  push    rdi
0x180009efe  sub     rsp, 20h
0x180009f02  mov     rdi, rcx
0x180009f05  jmp     short loc_180009F16
0x180009f07  mov     rcx, rdi; Size
0x180009f0a  call    _callnewh_0
0x180009f0f  test    eax, eax
0x180009f11  jz      short loc_180009F23
0x180009f13  mov     rcx, rdi; Size
0x180009f16  call    malloc_0
0x180009f1b  mov     rbx, rax
0x180009f1e  test    rax, rax
0x180009f21  jz      short loc_180009F07
0x180009f23  mov     rax, rbx
0x180009f26  mov     rbx, [rsp+28h+arg_0]
0x180009f2b  add     rsp, 20h
0x180009f2f  pop     rdi
0x180009f30  retn
```
