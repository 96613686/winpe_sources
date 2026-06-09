# CSR::~CSR(void)

- ea: `0x140003d08`
- end: `0x140003d1f`
- name: `??1CSR@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(CReadWriteLock **this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140004324`
- `0x1400043c0`
- `0x140004488`
- `0x140005f98`
- `0x1400060b0`
- `0x140006624`
- `0x140009550`
- `0x14001d1f4`
- `0x14001d206`
- `0x14001d4c0`
- `0x14001d52e`

## callees

- `0x140003d08`
- `0x14001cb30`

## pseudocode

```c
void __fastcall CSR::~CSR(CReadWriteLock **this)
{
  CReadWriteLock *v1; // rcx

  v1 = *this;
  if ( v1 )
    CReadWriteLock::UnlockRead(v1);
}

```

## disassembly

```asm
0x140003d08  sub     rsp, 28h
0x140003d0c  mov     rcx, [rcx]; this
0x140003d0f  test    rcx, rcx
0x140003d12  jz      short loc_140003D1A
0x140003d14  call    ?UnlockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::UnlockRead(void)
0x140003d19  nop
0x140003d1a  add     rsp, 28h
0x140003d1e  retn
```
