# [thunk]:ATL::CComObject<ColorPrintShellExt>::AddRef`adjustor{8}' (void)

- ea: `0x180004220`
- end: `0x180004229`
- name: `?AddRef@?$CComObject@VColorPrintShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004200`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorPrintShellExt>::AddRef(__int64 a1)
{
  return ATL::CComObject<ColorCaptureShellExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180004220  sub     rcx, 8
0x180004224  jmp     ?AddRef@?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAKXZ; ATL::CComObject<ColorCaptureShellExt>::AddRef(void)
```
