# CCabFolder::AddRef(void)

- ea: `0x18000d400`
- end: `0x18000d40d`
- name: `?AddRef@CCabFolder@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CCabFolder *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d420`
- `0x18000d430`
- `0x18000d440`
- `0x18000d450`

## pseudocode

```c
__int64 __fastcall CCabFolder::AddRef(CCabFolder *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 10);
}

```

## disassembly

```asm
0x18000d400  mov     eax, 1
0x18000d405  lock xadd [rcx+28h], eax
0x18000d40a  inc     eax
0x18000d40c  retn
```
