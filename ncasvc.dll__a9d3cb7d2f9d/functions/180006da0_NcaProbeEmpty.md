# NcaProbeEmpty

- ea: `0x180006da0`
- end: `0x180006dc5`
- name: `NcaProbeEmpty`
- size: `37`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e90`
- `0x180005da0`
- `0x180006470`
- `0x180011bc0`

## callees

- `0x180003770`

## pseudocode

```c
__int64 __fastcall NcaProbeEmpty(__int64 a1)
{
  __int64 result; // rax

  NcaFree(*(LPVOID *)(a1 + 8));
  result = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180006da0  push    rbx
0x180006da2  sub     rsp, 20h
0x180006da6  mov     rbx, rcx
0x180006da9  mov     rcx, [rcx+8]; lpMem
0x180006dad  call    NcaFree
0x180006db2  xorps   xmm0, xmm0
0x180006db5  xor     eax, eax
0x180006db7  movups  xmmword ptr [rbx], xmm0
0x180006dba  mov     [rbx+10h], rax
0x180006dbe  add     rsp, 20h
0x180006dc2  pop     rbx
0x180006dc3  retn
```
