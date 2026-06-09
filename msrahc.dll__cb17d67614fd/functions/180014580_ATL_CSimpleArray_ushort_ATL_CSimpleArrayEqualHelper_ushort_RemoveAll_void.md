# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x180014580`
- end: `0x1800145b5`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800143d0`
- `0x180014468`

## callees

- `0x180014580`

## import_xrefs

- `msvcrt!free` at `0x180014595`
- `msvcrt!free` at `0x180014595`

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
0x180014580  mov     [rsp+arg_0], rbx
0x180014585  push    rdi
0x180014586  sub     rsp, 20h
0x18001458a  mov     rbx, rcx
0x18001458d  mov     rcx, [rcx]; Block
0x180014590  test    rcx, rcx
0x180014593  jz      short loc_1800145A2
0x180014595  call    cs:__imp_free
0x18001459b  mov     qword ptr [rbx], 0
0x1800145a2  mov     qword ptr [rbx+8], 0
0x1800145aa  mov     rbx, [rsp+28h+arg_0]
0x1800145af  add     rsp, 20h
0x1800145b3  pop     rdi
0x1800145b4  retn
```
