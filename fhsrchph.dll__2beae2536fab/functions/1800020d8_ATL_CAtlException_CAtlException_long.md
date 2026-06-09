# ATL::CAtlException::CAtlException(long)

- ea: `0x1800020d8`
- end: `0x1800020de`
- name: `??0CAtlException@ATL@@QEAA@J@Z`
- size: `6`
- prototype: `ATL::CAtlException *__fastcall(ATL::CAtlException *this, int)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000278c`
- `0x180007a40`
- `0x180009604`
- `0x1800099e4`

## pseudocode

```c
ATL::CAtlException *__fastcall ATL::CAtlException::CAtlException(ATL::CAtlException *this, int a2)
{
  *(_DWORD *)this = a2;
  return this;
}

```

## disassembly

```asm
0x1800020d8  mov     [rcx], edx
0x1800020da  mov     rax, rcx
0x1800020dd  retn
```
