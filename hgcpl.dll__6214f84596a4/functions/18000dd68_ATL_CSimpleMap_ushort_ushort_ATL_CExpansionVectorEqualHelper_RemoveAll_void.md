# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x18000dd68`
- end: `0x18000ddb3`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd2c`
- `0x18000c894`

## callees

- `0x18000dd68`

## import_xrefs

- `msvcrt!free` at `0x18000dd7d`
- `msvcrt!free` at `0x18000dd93`
- `msvcrt!free` at `0x18000dd7d`
- `msvcrt!free` at `0x18000dd93`

## pseudocode

```c
void __fastcall ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    free(v3);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18000dd68  mov     [rsp+arg_0], rbx
0x18000dd6d  push    rdi
0x18000dd6e  sub     rsp, 20h
0x18000dd72  mov     rbx, rcx
0x18000dd75  mov     rcx, [rcx]; Block
0x18000dd78  test    rcx, rcx
0x18000dd7b  jz      short loc_18000DD8A
0x18000dd7d  call    cs:__imp_free
0x18000dd83  mov     qword ptr [rbx], 0
0x18000dd8a  mov     rcx, [rbx+8]; Block
0x18000dd8e  test    rcx, rcx
0x18000dd91  jz      short loc_18000DDA1
0x18000dd93  call    cs:__imp_free
0x18000dd99  mov     qword ptr [rbx+8], 0
0x18000dda1  mov     dword ptr [rbx+10h], 0
0x18000dda8  mov     rbx, [rsp+28h+arg_0]
0x18000ddad  add     rsp, 20h
0x18000ddb1  pop     rdi
0x18000ddb2  retn
```
