# CConfigServiceProvider2Impl::AddRef(void)

- ea: `0x180007f80`
- end: `0x180007f8d`
- name: `?AddRef@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x1800061d0`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::AddRef(CConfigServiceProvider2Impl *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 10);
}

```

## disassembly

```asm
0x180007f80  mov     eax, 1
0x180007f85  lock xadd [rcx+28h], eax
0x180007f8a  inc     eax
0x180007f8c  retn
```
