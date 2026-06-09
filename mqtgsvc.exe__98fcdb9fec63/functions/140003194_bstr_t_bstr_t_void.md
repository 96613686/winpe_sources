# _bstr_t::~_bstr_t(void)

- ea: `0x140003194`
- end: `0x140003199`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `47`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d465`
- `0x14001d47b`
- `0x14001d64d`
- `0x14001d663`
- `0x14001d831`
- `0x14001d96f`
- `0x14001d981`
- `0x14001d993`
- `0x14001db79`
- `0x14001dbd3`
- `0x14001dbf7`
- `0x14001dcff`
- `0x14001dd18`
- `0x14001dd31`
- `0x14001dd4a`
- `0x14001ddbe`
- `0x14001ddd0`
- `0x14001dde2`
- `0x14001ddf4`
- `0x14001de18`
- `0x14001de8f`
- `0x14001ded0`
- `0x14001dfc6`
- `0x14001dffb`
- `0x14001e18c`
- `0x14001e5ba`
- `0x14001e5cc`
- `0x14001e5de`
- `0x14001e6af`
- `0x14001e6c1`
- `0x14001e6e5`
- `0x14001e7e6`
- `0x14001e7ff`
- `0x14001e818`
- `0x14001ea5f`
- `0x14001eccd`
- `0x14001ecdf`
- `0x14001ecf5`
- `0x14001ed0b`
- `0x14001ed21`
- `0x14001ed37`
- `0x14001ed7f`
- `0x14001ed95`
- `0x14001edab`
- `0x14001edc1`
- `0x14001edd7`
- `0x14001ee1f`

## callees

- `0x140003868`

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
0x140003194  jmp     ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
```
