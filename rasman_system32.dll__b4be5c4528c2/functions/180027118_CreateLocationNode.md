# CreateLocationNode

- ea: `0x180027118`
- end: `0x180027160`
- name: `CreateLocationNode`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026640`

## callees

- `0x18002700c`
- `0x180027118`

## pseudocode

```c
_QWORD *__fastcall CreateLocationNode(int a1, int a2, int a3)
{
  _QWORD *result; // rax
  _QWORD *v7; // r9
  _DWORD *v8; // rax

  result = DtlCreateSizedNode(0xCu);
  v7 = result;
  if ( result )
  {
    v8 = (_DWORD *)result[2];
    *v8 = a1;
    v8[1] = a2;
    v8[2] = a3;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180027118  mov     [rsp+arg_0], rbx
0x18002711d  mov     [rsp+arg_8], rsi
0x180027122  push    rdi
0x180027123  sub     rsp, 20h
0x180027127  mov     esi, ecx
0x180027129  mov     ebx, r8d
0x18002712c  mov     ecx, 0Ch
0x180027131  mov     edi, edx
0x180027133  call    DtlCreateSizedNode
0x180027138  mov     r9, rax
0x18002713b  test    rax, rax
0x18002713e  jz      short loc_18002714F
0x180027140  mov     rax, [rax+10h]
0x180027144  mov     [rax], esi
0x180027146  mov     [rax+4], edi
0x180027149  mov     [rax+8], ebx
0x18002714c  mov     rax, r9
0x18002714f  mov     rbx, [rsp+28h+arg_0]
0x180027154  mov     rsi, [rsp+28h+arg_8]
0x180027159  add     rsp, 20h
0x18002715d  pop     rdi
0x18002715e  retn
```
