# DrDevice::ShouldCreateDevice(void)

- ea: `0x14001f8f0`
- end: `0x14001f8f6`
- name: `?ShouldCreateDevice@DrDevice@@UEAAHXZ`
- size: `6`
- prototype: `__int64 __fastcall(DrDevice *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall DrDevice::ShouldCreateDevice(DrDevice *this)
{
  return 1;
}

```

## disassembly

```asm
0x14001f8f0  mov     eax, 1
0x14001f8f5  retn
```
