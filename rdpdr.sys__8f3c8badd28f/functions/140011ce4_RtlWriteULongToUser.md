# RtlWriteULongToUser

- ea: `0x140011ce4`
- end: `0x140011d22`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: `void __fastcall(_DWORD *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007050`
- `0x140019220`
- `0x140019720`
- `0x140019aa4`
- `0x140019f18`

## callees

- `0x140003051`
- `0x140011ce4`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead_0(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x140011ce4  mov     [rsp+arg_0], rbx
0x140011ce9  push    rdi
0x140011cea  sub     rsp, 20h
0x140011cee  mov     rax, cs:qword_14000F5C0
0x140011cf5  mov     edi, edx
0x140011cf7  mov     rbx, rcx
0x140011cfa  test    rax, rax
0x140011cfd  jz      short loc_140011D06
0x140011cff  call    rax ; qword_14000F5C0
0x140011d01  nop     dword ptr [rax]
0x140011d04  jmp     short loc_140011D16
0x140011d06  mov     edx, 4; Length
0x140011d0b  lea     r8d, [rdx-3]; Alignment
0x140011d0f  call    ProbeForRead_0
0x140011d14  mov     [rbx], edi
0x140011d16  mov     rbx, [rsp+28h+arg_0]
0x140011d1b  add     rsp, 20h
0x140011d1f  pop     rdi
0x140011d20  retn
```
