# wil::verify_hresult<long>(long)

- ea: `0x180003e84`
- end: `0x180003e87`
- name: `??$verify_hresult@J@wil@@YAJJ@Z`
- size: `3`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023e8`
- `0x18000244c`
- `0x1800024c4`
- `0x180002544`
- `0x1800025d8`
- `0x180002648`
- `0x1800026b8`
- `0x180002728`
- `0x1800027a8`
- `0x180002820`
- `0x18000d0c8`
- `0x18000d13d`
- `0x18000d1b5`
- `0x18000e15a`

## pseudocode

```c
__int64 __fastcall wil::verify_hresult<long>(unsigned int a1)
{
  return a1;
}

```

## disassembly

```asm
0x180003e84  mov     eax, ecx
0x180003e86  retn
```
