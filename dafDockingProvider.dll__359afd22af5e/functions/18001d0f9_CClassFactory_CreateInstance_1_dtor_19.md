# _CClassFactory::CreateInstance_::_1_::dtor$19

- ea: `0x18001d0f9`
- end: `0x18001d109`
- name: `_CClassFactory::CreateInstance_::_1_::dtor$19`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d440`

## pseudocode

```c
void __fastcall CClassFactory::CreateInstance_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  CritSec::~CritSec((LPCRITICAL_SECTION)(*(_QWORD *)(a2 + 32) + 24LL));
}

```

## disassembly

```asm
0x18001d0f9  mov     rcx, [rdx+20h]
0x18001d100  add     rcx, 18h; lpCriticalSection
0x18001d104  jmp     ??1CritSec@@QEAA@XZ; CritSec::~CritSec(void)
```
