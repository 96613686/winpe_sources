# RemoveCancelRoutineSafe

- ea: `0x140019ea0`
- end: `0x140019eb1`
- name: `RemoveCancelRoutineSafe`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018b0`

## pseudocode

```c
bool __fastcall RemoveCancelRoutineSafe(__int64 a1)
{
  return _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0) != 0;
}

```

## disassembly

```asm
0x140019ea0  xor     edx, edx
0x140019ea2  mov     al, 1
0x140019ea4  xchg    rdx, [rcx+68h]
0x140019ea8  xor     ecx, ecx
0x140019eaa  test    rdx, rdx
0x140019ead  cmovz   eax, ecx
0x140019eb0  retn
```
