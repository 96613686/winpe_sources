# CsrReferenceThread

- ea: `0x1800073c0`
- end: `0x1800073c5`
- name: `CsrReferenceThread`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall CsrReferenceThread(__int64 a1)
{
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 76));
}

```

## disassembly

```asm
0x1800073c0  lock inc dword ptr [rcx+4Ch]
0x1800073c4  retn
```
