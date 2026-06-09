# DfscCredTableDelete

- ea: `0x1400124c8`
- end: `0x14001252e`
- name: `DfscCredTableDelete`
- size: `102`
- prototype: `BOOLEAN __fastcall(struct _RTL_AVL_TABLE *BugCheckParameter2, ULONG_PTR BugCheckParameter3)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140012668`
- `0x14001d9b0`
- `0x140023410`
- `0x1400252b0`

## callees

- `0x1400124c8`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400124dc`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400124dc`
- `ntoskrnl!KeBugCheckEx` at `0x140012505`
- `ntoskrnl!KeBugCheckEx` at `0x140012505`

## pseudocode

```c
BOOLEAN __fastcall DfscCredTableDelete(struct _RTL_AVL_TABLE *BugCheckParameter2, ULONG_PTR BugCheckParameter3)
{
  BOOLEAN result; // al

  result = RtlDeleteElementGenericTableAvl(BugCheckParameter2, *(PVOID *)(BugCheckParameter3 + 32));
  if ( !result )
    KeBugCheckEx(0x10Bu, 1u, (ULONG_PTR)BugCheckParameter2, BugCheckParameter3, BugCheckParameter3 + 8);
  *(_QWORD *)(BugCheckParameter3 + 24) = 0;
  *(_QWORD *)(BugCheckParameter3 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x1400124c8  mov     [rsp+arg_0], rbx
0x1400124cd  push    rdi
0x1400124ce  sub     rsp, 30h
0x1400124d2  mov     rbx, rdx
0x1400124d5  mov     rdi, rcx
0x1400124d8  mov     rdx, [rdx+20h]; Buffer
0x1400124dc  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400124e3  nop     dword ptr [rax+rax+00h]
0x1400124e8  test    al, al
0x1400124ea  jnz     short loc_140012512
0x1400124ec  lea     rax, [rbx+8]
0x1400124f0  mov     r9, rbx; BugCheckParameter3
0x1400124f3  mov     r8, rdi; BugCheckParameter2
0x1400124f6  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x1400124fb  mov     edx, 1; BugCheckParameter1
0x140012500  mov     ecx, 10Bh; BugCheckCode
0x140012505  call    cs:__imp_KeBugCheckEx
0x140012512  mov     qword ptr [rbx+18h], 0
0x14001251a  mov     qword ptr [rbx+20h], 0
0x140012522  mov     rbx, [rsp+38h+arg_0]
0x140012527  add     rsp, 30h
0x14001252b  pop     rdi
0x14001252c  retn
```
