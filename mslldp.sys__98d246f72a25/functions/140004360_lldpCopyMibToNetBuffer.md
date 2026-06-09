# lldpCopyMibToNetBuffer

- ea: `0x140004360`
- end: `0x1400043d1`
- name: `lldpCopyMibToNetBuffer`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011914`

## callees

- `0x140006840`

## pseudocode

```c
void *__fastcall lldpCopyMibToNetBuffer(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r9
  int v5; // edi
  const void *v6; // rdx
  __int64 v7; // rcx
  int v8; // edi
  __int64 v9; // rbx
  void *result; // rax

  v3 = *(_QWORD *)(a2 + 8);
  v4 = *(_QWORD *)(a2 + 24);
  v5 = *(_DWORD *)(a1 + 988);
  v6 = (const void *)(a1 + 996);
  v7 = (unsigned int)(*(_DWORD *)(a1 + 136) - *(_DWORD *)(a1 + 140));
  v8 = v7 + v5;
  v9 = *(_QWORD *)(v3 + 8);
  *(_DWORD *)(v4 + 6) = *(_DWORD *)(a1 + 144);
  *(_WORD *)(v4 + 10) = *(_WORD *)(a1 + 148);
  result = memmove((void *)(v4 + v7), v6, *(unsigned int *)(a1 + 988));
  *(_DWORD *)(v9 + 24) = v8;
  return result;
}

```

## disassembly

```asm
0x140004360  mov     [rsp+arg_0], rbx
0x140004365  push    rdi
0x140004366  sub     rsp, 20h
0x14000436a  mov     r8d, [rcx+88h]
0x140004371  mov     r10, rcx
0x140004374  sub     r8d, [rcx+8Ch]
0x14000437b  mov     rax, [rdx+8]
0x14000437f  mov     r9, [rdx+18h]
0x140004383  mov     edi, [r10+3DCh]
0x14000438a  lea     rdx, [r10+3E4h]; Src
0x140004391  mov     ecx, r8d
0x140004394  add     edi, r8d
0x140004397  mov     rbx, [rax+8]
0x14000439b  add     rcx, r9; void *
0x14000439e  mov     eax, [r10+90h]
0x1400043a5  mov     [r9+6], eax
0x1400043a9  movzx   eax, word ptr [r10+94h]
0x1400043b1  mov     [r9+0Ah], ax
0x1400043b6  mov     r8d, [r10+3DCh]; Size
0x1400043bd  call    memmove
0x1400043c2  mov     [rbx+18h], edi
0x1400043c5  mov     rbx, [rsp+28h+arg_0]
0x1400043ca  add     rsp, 20h
0x1400043ce  pop     rdi
0x1400043cf  retn
```
