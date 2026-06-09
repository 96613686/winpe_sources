# MRxDAVComputeNewBufferingState

- ea: `0x140012f80`
- end: `0x140012f8a`
- name: `MRxDAVComputeNewBufferingState`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall MRxDAVComputeNewBufferingState(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x140012f80  mov     dword ptr [r9], 0
0x140012f87  xor     eax, eax
0x140012f89  retn
```
