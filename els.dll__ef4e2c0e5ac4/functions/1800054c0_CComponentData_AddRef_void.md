# CComponentData::AddRef(void)

- ea: `0x1800054c0`
- end: `0x1800054cd`
- name: `?AddRef@CComponentData@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CComponentData *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800054e0`
- `0x1800054f0`
- `0x180005500`
- `0x180005510`
- `0x180005520`
- `0x180005530`

## pseudocode

```c
__int64 __fastcall CComponentData::AddRef(CComponentData *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 15);
}

```

## disassembly

```asm
0x1800054c0  mov     eax, 1
0x1800054c5  lock xadd [rcx+3Ch], eax
0x1800054ca  inc     eax
0x1800054cc  retn
```
