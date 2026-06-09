# PrjfPreNetworkQueryOpen

- ea: `0x140023d20`
- end: `0x140023d35`
- name: `PrjfPreNetworkQueryOpen`
- size: `21`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall PrjfPreNetworkQueryOpen(__int64 a1, __int64 a2, _QWORD *a3)
{
  *a3 = 0;
  return byte_14001ABCD != 0 ? 3 : 0;
}

```

## disassembly

```asm
0x140023d20  mov     qword ptr [r8], 0
0x140023d27  mov     al, cs:byte_14001ABCD
0x140023d2d  neg     al
0x140023d2f  sbb     eax, eax
0x140023d31  and     eax, 3
0x140023d34  retn
```
