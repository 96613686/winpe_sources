# _CClassFactory::CreateInstance_::_1_::dtor$10

- ea: `0x18001d0b4`
- end: `0x18001d0c7`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$10`
- size: `19`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d440`

## pseudocode

```c
void __fastcall CClassFactory::CreateInstance_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  CritSec::~CritSec((LPCRITICAL_SECTION)(*(_QWORD *)(a2 + 32) + 632LL));
}

```

## disassembly

```asm
0x18001d0b4  mov     rcx, [rdx+20h]
0x18001d0bb  add     rcx, 278h; lpCriticalSection
0x18001d0c2  jmp     ??1CritSec@@QEAA@XZ; CritSec::~CritSec(void)
```
