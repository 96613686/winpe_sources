# ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)

- ea: `0x18000b4d0`
- end: `0x18000b51b`
- name: `?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008cf0`
- `0x1800099d4`

## callees

- `0x18000b4d0`

## import_xrefs

- `msvcrt!free` at `0x18000b4e5`
- `msvcrt!free` at `0x18000b4fb`
- `msvcrt!free` at `0x18000b4e5`
- `msvcrt!free` at `0x18000b4fb`

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
0x18000b4d0  mov     [rsp+arg_0], rbx
0x18000b4d5  push    rdi
0x18000b4d6  sub     rsp, 20h
0x18000b4da  mov     rbx, rcx
0x18000b4dd  mov     rcx, [rcx]; Block
0x18000b4e0  test    rcx, rcx
0x18000b4e3  jz      short loc_18000B4F2
0x18000b4e5  call    cs:__imp_free
0x18000b4eb  mov     qword ptr [rbx], 0
0x18000b4f2  mov     rcx, [rbx+8]; Block
0x18000b4f6  test    rcx, rcx
0x18000b4f9  jz      short loc_18000B509
0x18000b4fb  call    cs:__imp_free
0x18000b501  mov     qword ptr [rbx+8], 0
0x18000b509  mov     dword ptr [rbx+10h], 0
0x18000b510  mov     rbx, [rsp+28h+arg_0]
0x18000b515  add     rsp, 20h
0x18000b519  pop     rdi
0x18000b51a  retn
```
