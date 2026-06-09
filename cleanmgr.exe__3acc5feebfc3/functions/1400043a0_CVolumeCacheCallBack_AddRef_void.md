# CVolumeCacheCallBack::AddRef(void)

- ea: `0x1400043a0`
- end: `0x1400043ad`
- name: `?AddRef@CVolumeCacheCallBack@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CVolumeCacheCallBack *this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CVolumeCacheCallBack::AddRef(CVolumeCacheCallBack *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x1400043a0  mov     eax, 1
0x1400043a5  lock xadd [rcx+8], eax
0x1400043aa  inc     eax
0x1400043ac  retn
```
