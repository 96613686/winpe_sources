# CConfigServiceProvider2Impl::AddRef(void)

- ea: `0x180008340`
- end: `0x18000834d`
- name: `?AddRef@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CConfigServiceProvider2Impl *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x1800064c0`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::AddRef(CConfigServiceProvider2Impl *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 10);
}

```

## disassembly

```asm
0x180008340  mov     eax, 1
0x180008345  lock xadd [rcx+28h], eax
0x18000834a  inc     eax
0x18000834c  retn
```
