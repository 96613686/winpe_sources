# CSW::~CSW(void)

- ea: `0x140003d28`
- end: `0x140003d3f`
- name: `??1CSW@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(CReadWriteLock **this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140003c5c`
- `0x140003f54`
- `0x14000456c`
- `0x1400060f4`
- `0x1400073d0`
- `0x14000a48c`
- `0x14000c720`
- `0x14001d1ac`
- `0x14001d218`
- `0x14001e19e`

## callees

- `0x140003d28`
- `0x14001cbcc`

## pseudocode

```c
void __fastcall CSW::~CSW(CReadWriteLock **this)
{
  CReadWriteLock *v1; // rcx

  v1 = *this;
  if ( v1 )
    CReadWriteLock::UnlockWrite(v1);
}

```

## disassembly

```asm
0x140003d28  sub     rsp, 28h
0x140003d2c  mov     rcx, [rcx]; this
0x140003d2f  test    rcx, rcx
0x140003d32  jz      short loc_140003D3A
0x140003d34  call    ?UnlockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::UnlockWrite(void)
0x140003d39  nop
0x140003d3a  add     rsp, 28h
0x140003d3e  retn
```
