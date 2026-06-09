# CDSLink::AddRef(void)

- ea: `0x18000efd0`
- end: `0x18000efdd`
- name: `?AddRef@CDSLink@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CDSLink *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eff0`

## pseudocode

```c
__int64 __fastcall CDSLink::AddRef(CDSLink *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 20);
}

```

## disassembly

```asm
0x18000efd0  mov     eax, 1
0x18000efd5  lock xadd [rcx+50h], eax
0x18000efda  inc     eax
0x18000efdc  retn
```
