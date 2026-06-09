# wil::verify_hresult<long>(long)

- ea: `0x1400032e8`
- end: `0x1400032eb`
- name: `??$verify_hresult@J@wil@@YAJJ@Z`
- size: `3`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b454`
- `0x14000ca40`
- `0x14000cd30`
- `0x14000cf10`

## pseudocode

```c
__int64 __fastcall wil::verify_hresult<long>(unsigned int a1)
{
  return a1;
}

```

## disassembly

```asm
0x1400032e8  mov     eax, ecx
0x1400032ea  retn
```
