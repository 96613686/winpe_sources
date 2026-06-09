# [thunk]:XMLScrSite::Release`adjustor{8}' (void)

- ea: `0x140011980`
- end: `0x140011989`
- name: `?Release@XMLScrSite@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011930`

## pseudocode

```c
__int64 __fastcall XMLScrSite::Release(__int64 a1)
{
  return XMLScrSite::Release((XMLScrSite *)(a1 - 8));
}

```

## disassembly

```asm
0x140011980  sub     rcx, 8; this
0x140011984  jmp     ?Release@XMLScrSite@@UEAAKXZ; XMLScrSite::Release(void)
```
