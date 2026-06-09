# DrDevice::Remove(void)

- ea: `0x14001f8e0`
- end: `0x14001f8e8`
- name: `?Remove@DrDevice@@UEAAXXZ`
- size: `8`
- prototype: `void __fastcall(DrDevice *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## pseudocode

```c
void __fastcall DrDevice::Remove(DrDevice *this)
{
  *((_DWORD *)this + 14) = 1;
}

```

## disassembly

```asm
0x14001f8e0  mov     dword ptr [rcx+38h], 1
0x14001f8e7  retn
```
