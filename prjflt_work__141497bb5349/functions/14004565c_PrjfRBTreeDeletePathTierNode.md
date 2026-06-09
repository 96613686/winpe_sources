# PrjfRBTreeDeletePathTierNode

- ea: `0x14004565c`
- end: `0x14004568b`
- name: `PrjfRBTreeDeletePathTierNode`
- size: `47`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140044c20`

## callees

- `0x140044bb4`
- `0x140044c20`
- `0x14004565c`

## pseudocode

```c
void __fastcall PrjfRBTreeDeletePathTierNode(__int64 a1)
{
  struct _UNICODE_STRING *v1; // rbx
  unsigned __int64 v2; // rcx

  v1 = (struct _UNICODE_STRING *)(a1 - 8);
  v2 = *(_QWORD *)(a1 - 8 + 56);
  if ( v2 )
  {
    PrjfDeletePathTree(v2);
    v1[3].Buffer = 0;
  }
  PrjfDeletePathTierNode(v1);
}

```

## disassembly

```asm
0x14004565c  push    rbx
0x14004565e  sub     rsp, 20h
0x140045662  lea     rbx, [rcx-8]
0x140045666  mov     rcx, [rbx+38h]; P
0x14004566a  test    rcx, rcx
0x14004566d  jz      short loc_14004567C
0x14004566f  call    PrjfDeletePathTree
0x140045674  mov     qword ptr [rbx+38h], 0
0x14004567c  mov     rcx, rbx; P
0x14004567f  call    PrjfDeletePathTierNode
0x140045684  add     rsp, 20h
0x140045688  pop     rbx
0x140045689  retn
```
