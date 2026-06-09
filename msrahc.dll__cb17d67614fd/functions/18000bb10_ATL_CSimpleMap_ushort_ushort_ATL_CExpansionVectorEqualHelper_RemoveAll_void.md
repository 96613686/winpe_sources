# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x18000bb10`
- end: `0x18000bb5b`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089e8`
- `0x180009fa4`

## callees

- `0x18000bb10`

## import_xrefs

- `msvcrt!free` at `0x18000bb25`
- `msvcrt!free` at `0x18000bb3b`
- `msvcrt!free` at `0x18000bb25`
- `msvcrt!free` at `0x18000bb3b`

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
0x18000bb10  mov     [rsp+arg_0], rbx
0x18000bb15  push    rdi
0x18000bb16  sub     rsp, 20h
0x18000bb1a  mov     rbx, rcx
0x18000bb1d  mov     rcx, [rcx]; Block
0x18000bb20  test    rcx, rcx
0x18000bb23  jz      short loc_18000BB32
0x18000bb25  call    cs:__imp_free
0x18000bb2b  mov     qword ptr [rbx], 0
0x18000bb32  mov     rcx, [rbx+8]; Block
0x18000bb36  test    rcx, rcx
0x18000bb39  jz      short loc_18000BB49
0x18000bb3b  call    cs:__imp_free
0x18000bb41  mov     qword ptr [rbx+8], 0
0x18000bb49  mov     dword ptr [rbx+10h], 0
0x18000bb50  mov     rbx, [rsp+28h+arg_0]
0x18000bb55  add     rsp, 20h
0x18000bb59  pop     rdi
0x18000bb5a  retn
```
