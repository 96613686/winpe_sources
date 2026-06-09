# CCountedObject::AddRef(void)

- ea: `0x180003850`
- end: `0x180003855`
- name: `?AddRef@CCountedObject@@QEAAXXZ`
- size: `5`
- prototype: `void __fastcall(CCountedObject *__hidden this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005bf4`
- `0x180005f24`
- `0x180007c2c`
- `0x180007d0c`
- `0x180007e34`
- `0x180008558`
- `0x180009580`

## pseudocode

```c
void __fastcall CCountedObject::AddRef(CCountedObject *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180003850  lock inc dword ptr [rcx+8]
0x180003854  retn
```
