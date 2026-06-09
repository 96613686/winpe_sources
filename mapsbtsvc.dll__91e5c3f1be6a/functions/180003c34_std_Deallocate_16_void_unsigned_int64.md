# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180003c34`
- end: `0x180003c6c`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `41`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003df4`
- `0x180004430`
- `0x180004454`
- `0x1800044b0`
- `0x1800045d0`
- `0x180005a1c`
- `0x180005bd0`
- `0x18000612c`
- `0x18000a060`
- `0x18000a08c`
- `0x18000a0b8`
- `0x18000a31c`
- `0x18000b028`
- `0x18000b04c`
- `0x18000b070`
- `0x18000b0cc`
- `0x18000b128`
- `0x18000b244`
- `0x18000b274`
- `0x18000b2c4`
- `0x18000b2f0`
- `0x18000b31c`
- `0x18000b420`
- `0x18000b6f8`
- `0x18000f49c`
- `0x18000fc98`
- `0x18000fe00`
- `0x180010448`
- `0x180010594`
- `0x180010798`
- `0x180010808`
- `0x180010954`
- `0x1800119e0`
- `0x180011a60`
- `0x180011a98`
- `0x180012124`
- `0x180012198`
- `0x180012d90`
- `0x180013168`
- `0x180013348`
- `0x180014970`

## callees

- `0x180001e94`
- `0x180003c34`
- `0x1800059c4`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *Block; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  Block = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&Block, &v3);
    a1 = Block;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180003c34  mov     rax, rsp
0x180003c37  mov     [rax+10h], rdx
0x180003c3b  mov     [rax+8], rcx
0x180003c3f  sub     rsp, 28h
0x180003c43  cmp     rdx, 1000h
0x180003c4a  jb      short loc_180003C63
0x180003c4c  lea     rdx, [rax+10h]; unsigned __int64 *
0x180003c50  lea     rcx, [rax+8]; void **
0x180003c54  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180003c59  mov     rdx, [rsp+28h+arg_8]
0x180003c5e  mov     rcx, [rsp+28h+Block]; Block
0x180003c63  add     rsp, 28h
0x180003c67  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
