# DecryptFullBlock

- ea: `0x180002ae4`
- end: `0x180002b36`
- name: `DecryptFullBlock`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001820`

## callees

- `0x180001a50`
- `0x180002aa8`

## pseudocode

```c
__int64 __fastcall DecryptFullBlock(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // r10d

  SystemFunction002(*(_QWORD *)(a1 + 16), *(_BYTE **)(a2 + 16), *(_QWORD *)(a3 + 16));
  *(_QWORD *)(a3 + 16) += 8LL;
  *(_QWORD *)(a1 + 16) += 8LL;
  AdvanceDataKey((unsigned int *)a2);
  return v6;
}

```

## disassembly

```asm
0x180002ae4  mov     [rsp+arg_0], rbx
0x180002ae9  mov     [rsp+arg_8], rsi
0x180002aee  push    rdi
0x180002aef  sub     rsp, 20h
0x180002af3  mov     rdi, r8
0x180002af6  mov     rsi, rdx
0x180002af9  mov     r8, [r8+10h]
0x180002afd  mov     rbx, rcx
0x180002b00  mov     rdx, [rdx+10h]
0x180002b04  mov     rcx, [rcx+10h]
0x180002b08  call    SystemFunction002
0x180002b0d  add     qword ptr [rdi+10h], 8
0x180002b12  mov     rcx, rsi
0x180002b15  add     qword ptr [rbx+10h], 8
0x180002b1a  mov     r10d, eax
0x180002b1d  call    AdvanceDataKey
0x180002b22  mov     rbx, [rsp+28h+arg_0]
0x180002b27  mov     eax, r10d
0x180002b2a  mov     rsi, [rsp+28h+arg_8]
0x180002b2f  add     rsp, 20h
0x180002b33  pop     rdi
0x180002b34  retn
```
