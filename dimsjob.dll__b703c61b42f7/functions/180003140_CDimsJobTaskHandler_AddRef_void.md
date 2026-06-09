# CDimsJobTaskHandler::AddRef(void)

- ea: `0x180003140`
- end: `0x18000314d`
- name: `?AddRef@CDimsJobTaskHandler@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CDimsJobTaskHandler *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## pseudocode

```c
__int64 __fastcall CDimsJobTaskHandler::AddRef(CDimsJobTaskHandler *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 15);
}

```

## disassembly

```asm
0x180003140  mov     eax, 1
0x180003145  lock xadd [rcx+3Ch], eax
0x18000314a  inc     eax
0x18000314c  retn
```
