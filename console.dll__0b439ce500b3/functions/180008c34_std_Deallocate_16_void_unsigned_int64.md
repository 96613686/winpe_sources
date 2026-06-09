# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x180008c34`
- end: `0x180008c6c`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008d24`
- `0x18000d928`
- `0x180015114`
- `0x1800151ac`
- `0x1800151e8`
- `0x1800156f8`
- `0x180015778`
- `0x180016c14`
- `0x1800196e0`

## callees

- `0x180001980`
- `0x180008c34`
- `0x180008cf8`

## pseudocode

```c
void __fastcall std::_Deallocate<16>(void *a1, unsigned __int64 a2)
{
  void *v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = a2;
  v2 = a1;
  if ( a2 >= 0x1000 )
  {
    std::_Adjust_manually_vector_aligned(&v2, &v3);
    a1 = v2;
  }
  operator delete(a1);
}

```

## disassembly

```asm
0x180008c34  mov     rax, rsp
0x180008c37  mov     [rax+10h], rdx
0x180008c3b  mov     [rax+8], rcx
0x180008c3f  sub     rsp, 28h
0x180008c43  cmp     rdx, 1000h
0x180008c4a  jb      short loc_180008C63
0x180008c4c  lea     rdx, [rax+10h]; unsigned __int64 *
0x180008c50  lea     rcx, [rax+8]; void **
0x180008c54  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x180008c59  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x180008c5e  mov     rcx, [rsp+28h+arg_0]; void *
0x180008c63  add     rsp, 28h
0x180008c67  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
