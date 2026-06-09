# ATL::CAtlException::CAtlException(long)

- ea: `0x18000253c`
- end: `0x180002542`
- name: `??0CAtlException@ATL@@QEAA@J@Z`
- size: `6`
- prototype: `ATL::CAtlException *__fastcall(ATL::CAtlException *this, int)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x18000374c`
- `0x180008e20`
- `0x18000946c`
- `0x180009f4c`
- `0x18000b180`
- `0x18000b3ac`
- `0x18000b5d8`
- `0x18000c60c`
- `0x18000c6bc`
- `0x18000cd50`
- `0x18000d2c0`
- `0x18000d3d0`
- `0x18000e948`
- `0x18000ec5c`
- `0x18000ee48`
- `0x18000ef8c`
- `0x18000f658`
- `0x18000f880`
- `0x18000fa50`
- `0x18000fb3c`

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
0x18000253c  mov     [rcx], edx
0x18000253e  mov     rax, rcx
0x180002541  retn
```
