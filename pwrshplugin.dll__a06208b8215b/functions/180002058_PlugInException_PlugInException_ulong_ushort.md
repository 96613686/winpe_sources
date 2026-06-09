# PlugInException::PlugInException(ulong,ushort *)

- ea: `0x180002058`
- end: `0x180002062`
- name: `??0PlugInException@@QEAA@KPEAG@Z`
- size: `10`
- prototype: `PlugInException *__fastcall(PlugInException *this, int, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002170`
- `0x180002fac`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x180004370`

## pseudocode

```c
PlugInException *__fastcall PlugInException::PlugInException(PlugInException *this, int a2, unsigned __int16 *a3)
{
  PlugInException *result; // rax

  *(_DWORD *)this = a2;
  result = this;
  *((_QWORD *)this + 1) = a3;
  return result;
}

```

## disassembly

```asm
0x180002058  mov     [rcx], edx
0x18000205a  mov     rax, rcx
0x18000205d  mov     [rcx+8], r8
0x180002061  retn
```
