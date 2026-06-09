# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000732c`
- end: `0x180007361`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006e88`
- `0x180006f24`
- `0x18002677c`

## callees

- `0x18000732c`

## import_xrefs

- `msvcrt!free` at `0x180007341`
- `msvcrt!free` at `0x180007341`

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
0x18000732c  mov     [rsp+arg_0], rbx
0x180007331  push    rdi
0x180007332  sub     rsp, 20h
0x180007336  mov     rbx, rcx
0x180007339  mov     rcx, [rcx]; Block
0x18000733c  test    rcx, rcx
0x18000733f  jz      short loc_18000734E
0x180007341  call    cs:__imp_free
0x180007347  mov     qword ptr [rbx], 0
0x18000734e  mov     qword ptr [rbx+8], 0
0x180007356  mov     rbx, [rsp+28h+arg_0]
0x18000735b  add     rsp, 20h
0x18000735f  pop     rdi
0x180007360  retn
```
