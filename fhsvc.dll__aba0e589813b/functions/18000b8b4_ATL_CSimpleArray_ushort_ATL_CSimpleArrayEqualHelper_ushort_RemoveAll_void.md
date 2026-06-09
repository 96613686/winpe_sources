# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000b8b4`
- end: `0x18000b8e9`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800097d0`

## callees

- `0x18000b8b4`

## import_xrefs

- `msvcrt!free` at `0x18000b8c9`
- `msvcrt!free` at `0x18000b8c9`

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
0x18000b8b4  mov     [rsp+arg_0], rbx
0x18000b8b9  push    rdi
0x18000b8ba  sub     rsp, 20h
0x18000b8be  mov     rbx, rcx
0x18000b8c1  mov     rcx, [rcx]; Block
0x18000b8c4  test    rcx, rcx
0x18000b8c7  jz      short loc_18000B8D6
0x18000b8c9  call    cs:__imp_free
0x18000b8cf  mov     qword ptr [rbx], 0
0x18000b8d6  mov     qword ptr [rbx+8], 0
0x18000b8de  mov     rbx, [rsp+28h+arg_0]
0x18000b8e3  add     rsp, 20h
0x18000b8e7  pop     rdi
0x18000b8e8  retn
```
