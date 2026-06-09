# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000fa14`
- end: `0x18000fa49`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f918`
- `0x18000f978`

## callees

- `0x18000fa14`

## import_xrefs

- `msvcrt!free` at `0x18000fa29`
- `msvcrt!free` at `0x18000fa29`

## pseudocode

```c
void __fastcall ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x18000fa14  mov     [rsp+arg_0], rbx
0x18000fa19  push    rdi
0x18000fa1a  sub     rsp, 20h
0x18000fa1e  mov     rbx, rcx
0x18000fa21  mov     rcx, [rcx]; Block
0x18000fa24  test    rcx, rcx
0x18000fa27  jz      short loc_18000FA36
0x18000fa29  call    cs:__imp_free
0x18000fa2f  mov     qword ptr [rbx], 0
0x18000fa36  mov     qword ptr [rbx+8], 0
0x18000fa3e  mov     rbx, [rsp+28h+arg_0]
0x18000fa43  add     rsp, 20h
0x18000fa47  pop     rdi
0x18000fa48  retn
```
