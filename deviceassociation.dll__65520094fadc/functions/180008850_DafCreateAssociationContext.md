# DafCreateAssociationContext

- ea: `0x180008850`
- end: `0x180008878`
- name: `DafCreateAssociationContext`
- size: `40`
- prototype: `__int64 __fastcall(int, int, int, __int64, struct _DAC_CLIENT_CONTEXT **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008880`

## pseudocode

```c
__int64 __fastcall DafCreateAssociationContext(__int64 a1, int a2, int a3, __int64 a4, RPC_BINDING_HANDLE **a5)
{
  return DafCreateAssociationContextForApp(0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180008850  sub     rsp, 38h
0x180008854  mov     rax, [rsp+38h+arg_20]
0x180008859  mov     [rsp+38h+var_10], rax; struct _DAC_CLIENT_CONTEXT **
0x18000885e  mov     [rsp+38h+var_18], r9; __int64
0x180008863  mov     r9d, r8d; int
0x180008866  mov     r8d, edx; int
0x180008869  mov     rdx, rcx; int
0x18000886c  xor     ecx, ecx; int
0x18000886e  call    DafCreateAssociationContextForApp
0x180008873  add     rsp, 38h
0x180008877  retn
```
