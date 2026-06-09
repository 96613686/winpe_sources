# [thunk]:XMLScrSite::AddRef`adjustor{8}' (void)

- ea: `0x1400111f0`
- end: `0x1400111f9`
- name: `?AddRef@XMLScrSite@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000e580`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRef(__int64 a1)
{
  return XMLScrSite::AddRef((XMLScrSite *)(a1 - 8));
}

```

## disassembly

```asm
0x1400111f0  sub     rcx, 8; this
0x1400111f4  jmp     ?AddRef@XMLScrSite@@UEAAKXZ; XMLScrSite::AddRef(void)
```
