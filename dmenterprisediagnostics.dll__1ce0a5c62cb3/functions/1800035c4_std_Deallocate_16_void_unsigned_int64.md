# std::_Deallocate<16>(void *,unsigned __int64)

- ea: `0x1800035c4`
- end: `0x1800035fc`
- name: `??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z`
- size: `56`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `61`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003604`
- `0x180003b10`
- `0x180007b90`
- `0x18000899c`
- `0x180008b34`
- `0x18000fbc0`
- `0x18000fd0c`
- `0x18000fe74`
- `0x18000fed0`
- `0x18000ff2c`
- `0x180010064`
- `0x180010114`
- `0x1800101e4`
- `0x1800102c8`
- `0x18001038c`
- `0x1800114c0`
- `0x1800114e4`
- `0x180011508`
- `0x18001152c`
- `0x18001159c`
- `0x1800115cc`
- `0x1800115fc`
- `0x180011674`
- `0x180011788`
- `0x180011988`
- `0x180011a34`
- `0x180011a58`
- `0x180011a94`
- `0x180017ea4`
- `0x180017ee4`
- `0x1800180ac`
- `0x1800182ec`
- `0x18001878c`
- `0x1800187b0`
- `0x18001880c`
- `0x18001885c`
- `0x18001a288`
- `0x18001bd7c`
- `0x18001bdd8`
- `0x18001be34`
- `0x18001c12c`
- `0x18001c244`
- `0x18001c860`
- `0x18001c884`
- `0x18001c8a8`
- `0x18001c8cc`
- `0x18001c8fc`
- `0x18001c92c`
- `0x18001ca10`
- `0x18001cb64`

## callees

- `0x180001804`
- `0x1800035c4`
- `0x180007184`

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
    a2 = v3;
    a1 = v2;
  }
  operator delete(a1, a2);
}

```

## disassembly

```asm
0x1800035c4  mov     rax, rsp
0x1800035c7  mov     [rax+10h], rdx
0x1800035cb  mov     [rax+8], rcx
0x1800035cf  sub     rsp, 28h
0x1800035d3  cmp     rdx, 1000h
0x1800035da  jb      short loc_1800035F3
0x1800035dc  lea     rdx, [rax+10h]; unsigned __int64 *
0x1800035e0  lea     rcx, [rax+8]; void **
0x1800035e4  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x1800035e9  mov     rdx, [rsp+28h+arg_8]; unsigned __int64
0x1800035ee  mov     rcx, [rsp+28h+arg_0]; void *
0x1800035f3  add     rsp, 28h
0x1800035f7  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
