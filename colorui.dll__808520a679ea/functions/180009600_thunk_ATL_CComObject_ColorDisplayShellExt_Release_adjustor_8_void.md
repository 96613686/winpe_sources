# [thunk]:ATL::CComObject<ColorDisplayShellExt>::Release`adjustor{8}' (void)

- ea: `0x180009600`
- end: `0x180009609`
- name: `?Release@?$CComObject@VColorDisplayShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009580`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorDisplayShellExt>::Release(__int64 a1)
{
  return ATL::CComObject<ColorCaptureShellExt>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x180009600  sub     rcx, 8
0x180009604  jmp     ?Release@?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAKXZ; ATL::CComObject<ColorCaptureShellExt>::Release(void)
```
