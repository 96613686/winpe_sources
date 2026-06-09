# _tlgCreate2Binary

- ea: `0x18000111c`
- end: `0x18000113b`
- name: `_tlgCreate2Binary`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180012c28`

## pseudocode

```c
__int64 __fastcall tlgCreate2Binary(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  result = a1 + 24;
  *(_QWORD *)(a1 + 8) = 2;
  *(_QWORD *)a1 = a1 + 24;
  *(_QWORD *)(a1 + 16) = a2;
  *(_DWORD *)(a1 + 24) = a3;
  *(_DWORD *)(a1 + 28) = 0;
  return result;
}

```

## disassembly

```asm
0x18000111c  lea     rax, [rcx+18h]
0x180001120  mov     qword ptr [rcx+8], 2
0x180001128  mov     [rcx], rax
0x18000112b  mov     [rcx+10h], rdx
0x18000112f  mov     [rcx+18h], r8d
0x180001133  mov     dword ptr [rcx+1Ch], 0
0x18000113a  retn
```
