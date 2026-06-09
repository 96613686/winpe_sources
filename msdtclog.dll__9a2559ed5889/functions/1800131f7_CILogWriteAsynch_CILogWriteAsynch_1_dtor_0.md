# _CILogWriteAsynch::CILogWriteAsynch_::_1_::dtor$0

- ea: `0x1800131f7`
- end: `0x180013207`
- name: `_CILogWriteAsynch::CILogWriteAsynch_::_1_::dtor$0`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800052b8`

## pseudocode

```c
void __fastcall CILogWriteAsynch::CILogWriteAsynch_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSemExclusive::~CSemExclusive((CSemExclusive *)(*(_QWORD *)(a2 + 48) + 32LL));
}

```

## disassembly

```asm
0x1800131f7  mov     rcx, [rdx+30h]
0x1800131fe  add     rcx, 20h ; ' '; this
0x180013202  jmp     ??1CSemExclusive@@QEAA@XZ; CSemExclusive::~CSemExclusive(void)
```
