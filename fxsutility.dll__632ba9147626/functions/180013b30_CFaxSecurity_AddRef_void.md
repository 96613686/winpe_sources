# CFaxSecurity::AddRef(void)

- ea: `0x180013b30`
- end: `0x180013b3d`
- name: `?AddRef@CFaxSecurity@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CFaxSecurity *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::AddRef(CFaxSecurity *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x180013b30  mov     eax, 1
0x180013b35  lock xadd [rcx+18h], eax
0x180013b3a  inc     eax
0x180013b3c  retn
```
