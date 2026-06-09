# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x180006398`
- end: `0x1800063e3`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003354`
- `0x18000439c`

## callees

- `0x180006398`

## import_xrefs

- `msvcrt!free` at `0x1800063ad`
- `msvcrt!free` at `0x1800063c3`
- `msvcrt!free` at `0x1800063ad`
- `msvcrt!free` at `0x1800063c3`

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
0x180006398  mov     [rsp+arg_0], rbx
0x18000639d  push    rdi
0x18000639e  sub     rsp, 20h
0x1800063a2  mov     rbx, rcx
0x1800063a5  mov     rcx, [rcx]; Block
0x1800063a8  test    rcx, rcx
0x1800063ab  jz      short loc_1800063BA
0x1800063ad  call    cs:__imp_free
0x1800063b3  mov     qword ptr [rbx], 0
0x1800063ba  mov     rcx, [rbx+8]; Block
0x1800063be  test    rcx, rcx
0x1800063c1  jz      short loc_1800063D1
0x1800063c3  call    cs:__imp_free
0x1800063c9  mov     qword ptr [rbx+8], 0
0x1800063d1  mov     dword ptr [rbx+10h], 0
0x1800063d8  mov     rbx, [rsp+28h+arg_0]
0x1800063dd  add     rsp, 20h
0x1800063e1  pop     rdi
0x1800063e2  retn
```
