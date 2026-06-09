# [thunk]:XMLScrSite::AddRef`adjustor{16}' (void)

- ea: `0x140011200`
- end: `0x140011209`
- name: `?AddRef@XMLScrSite@@WBA@EAAKXZ`
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
  return XMLScrSite::AddRef((XMLScrSite *)(a1 - 16));
}

```

## disassembly

```asm
0x140011200  sub     rcx, 10h; this
0x140011204  jmp     ?AddRef@XMLScrSite@@UEAAKXZ; XMLScrSite::AddRef(void)
```
