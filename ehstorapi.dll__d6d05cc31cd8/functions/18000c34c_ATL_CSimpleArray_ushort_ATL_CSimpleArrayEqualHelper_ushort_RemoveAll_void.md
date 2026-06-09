# ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)

- ea: `0x18000c34c`
- end: `0x18000c381`
- name: `?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c250`
- `0x18000c2b0`

## callees

- `0x18000c34c`

## import_xrefs

- `msvcrt!free` at `0x18000c361`
- `msvcrt!free` at `0x18000c361`

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
0x18000c34c  mov     [rsp+arg_0], rbx
0x18000c351  push    rdi
0x18000c352  sub     rsp, 20h
0x18000c356  mov     rbx, rcx
0x18000c359  mov     rcx, [rcx]; Block
0x18000c35c  test    rcx, rcx
0x18000c35f  jz      short loc_18000C36E
0x18000c361  call    cs:__imp_free
0x18000c367  mov     qword ptr [rbx], 0
0x18000c36e  mov     qword ptr [rbx+8], 0
0x18000c376  mov     rbx, [rsp+28h+arg_0]
0x18000c37b  add     rsp, 20h
0x18000c37f  pop     rdi
0x18000c380  retn
```
