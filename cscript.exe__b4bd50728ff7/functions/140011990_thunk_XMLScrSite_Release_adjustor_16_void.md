# [thunk]:XMLScrSite::Release`adjustor{16}' (void)

- ea: `0x140011990`
- end: `0x140011999`
- name: `?Release@XMLScrSite@@WBA@EAAKXZ`
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
  return XMLScrSite::Release((XMLScrSite *)(a1 - 16));
}

```

## disassembly

```asm
0x140011990  sub     rcx, 10h; this
0x140011994  jmp     ?Release@XMLScrSite@@UEAAKXZ; XMLScrSite::Release(void)
```
