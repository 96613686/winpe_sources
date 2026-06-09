# create_trees

- ea: `0x18000ed00`
- end: `0x18000eda4`
- name: `create_trees`
- size: `164`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001870`
- `0x18000e558`
- `0x180010130`
- `0x180014568`

## callees

- `0x18000edac`

## pseudocode

```c
__int64 __fastcall create_trees(__int64 a1, int a2)
{
  make_tree(a1, 8 * *(_DWORD *)(a1 + 2208) + 256, a1 + 10560, a1 + 9608, a1 + 13360, a2);
  make_tree(a1, 249, a1 + 15462, a1 + 10309, a1 + 16458, a2);
  return make_tree(a1, 8, (int)a1 + 17206, (int)a1 + 17254, a1 + 17238, 1);
}

```

## disassembly

```asm
0x18000ed00  mov     [rsp+arg_0], rbx
0x18000ed05  push    rdi
0x18000ed06  sub     rsp, 30h
0x18000ed0a  mov     ebx, edx
0x18000ed0c  lea     rax, [rcx+3430h]
0x18000ed13  mov     edx, [rcx+8A0h]
0x18000ed19  lea     r9, [rcx+2588h]
0x18000ed20  lea     r8, [rcx+2940h]
0x18000ed27  mov     [rsp+38h+var_10], ebx
0x18000ed2b  mov     rdi, rcx
0x18000ed2e  mov     [rsp+38h+var_18], rax
0x18000ed33  lea     edx, ds:100h[rdx*8]
0x18000ed3a  call    make_tree
0x18000ed3f  lea     rax, [rdi+404Ah]
0x18000ed46  mov     [rsp+38h+var_10], ebx
0x18000ed4a  lea     r9, [rdi+2845h]
0x18000ed51  mov     [rsp+38h+var_18], rax
0x18000ed56  lea     r8, [rdi+3C66h]
0x18000ed5d  mov     edx, 0F9h
0x18000ed62  mov     rcx, rdi
0x18000ed65  call    make_tree
0x18000ed6a  lea     rax, [rdi+4356h]
0x18000ed71  mov     [rsp+38h+var_10], 1
0x18000ed79  lea     r9, [rdi+4366h]
0x18000ed80  mov     [rsp+38h+var_18], rax
0x18000ed85  lea     r8, [rdi+4336h]
0x18000ed8c  mov     edx, 8
0x18000ed91  mov     rcx, rdi
0x18000ed94  call    make_tree
0x18000ed99  mov     rbx, [rsp+38h+arg_0]
0x18000ed9e  add     rsp, 30h
0x18000eda2  pop     rdi
0x18000eda3  retn
```
