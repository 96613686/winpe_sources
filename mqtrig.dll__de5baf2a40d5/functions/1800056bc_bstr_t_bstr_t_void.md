# _bstr_t::~_bstr_t(void)

- ea: `0x1800056bc`
- end: `0x1800056c1`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `62`
- callee_count: `1`
- tags: ``

## callers

- `0x18001eb74`
- `0x18001eb8d`
- `0x18001eba6`
- `0x18001ebe3`
- `0x18001ec0f`
- `0x18001ec5f`
- `0x18001ec71`
- `0x18001ec83`
- `0x18001ecb9`
- `0x18001ecdd`
- `0x18001ee1a`
- `0x18001ee3e`
- `0x18001ee62`
- `0x18001ee74`
- `0x18001f0dc`
- `0x18001f0ee`
- `0x18001f124`
- `0x18001f51a`
- `0x18001f52c`
- `0x18001f550`
- `0x18001f574`
- `0x18001f586`
- `0x18001f598`
- `0x18001f5aa`
- `0x18001f725`
- `0x18001f7b9`
- `0x18001ff92`
- `0x180020001`
- `0x180020013`
- `0x180020045`
- `0x180020077`
- `0x180020089`
- `0x180020124`
- `0x180020248`
- `0x18002036c`
- `0x1800204cc`
- `0x1800204de`
- `0x180020a8a`
- `0x180020cec`
- `0x180020cfe`
- `0x180020d34`
- `0x180020d46`
- `0x180020d5c`
- `0x180020d72`
- `0x180020d88`
- `0x180020d9e`
- `0x180020de6`
- `0x180020df8`
- `0x180020e0e`
- `0x180020e24`

## callees

- `0x180009ab0`

## pseudocode

```c
// attributes: thunk
void __fastcall _bstr_t::~_bstr_t(_bstr_t *this)
{
  _bstr_t::_Free(this);
}

```

## disassembly

```asm
0x1800056bc  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
