# CWinTaskClassFactoryT<CmCleanupWim,1>::AddRef(void)

- ea: `0x1800038f0`
- end: `0x1800038fd`
- name: `?AddRef@?$CWinTaskClassFactoryT@VCmCleanupWim@@$00@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CmCleanupWim,1>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x1800038f0  mov     eax, 1
0x1800038f5  lock xadd [rcx+8], eax
0x1800038fa  inc     eax
0x1800038fc  retn
```
