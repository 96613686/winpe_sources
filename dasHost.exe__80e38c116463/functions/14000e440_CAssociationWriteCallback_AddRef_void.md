# CAssociationWriteCallback::AddRef(void)

- ea: `0x14000e440`
- end: `0x14000e44d`
- name: `?AddRef@CAssociationWriteCallback@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CAssociationWriteCallback *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CAssociationWriteCallback::AddRef(CAssociationWriteCallback *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x14000e440  mov     eax, 1
0x14000e445  lock xadd [rcx+8], eax
0x14000e44a  inc     eax
0x14000e44c  retn
```
