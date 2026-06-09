# Dfdll::CString::get_HashCode(ulong &)

- ea: `0x180004e10`
- end: `0x180004e22`
- name: `?get_HashCode@CString@Dfdll@@UEAAJAEAK@Z`
- size: `18`
- prototype: `int(Dfdll::CString *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180004cfc`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::get_HashCode(Dfdll::CString *this, unsigned int *a2)
{
  return Dfdll::CBufferBase::get_HashCode((Dfdll::CString *)((char *)this + 8), 0, *((_DWORD *)this + 8), a2);
}

```

## disassembly

```asm
0x180004e10  mov     r8d, [rcx+20h]; unsigned int
0x180004e14  mov     r9, rdx; unsigned int *
0x180004e17  add     rcx, 8; this
0x180004e1b  xor     edx, edx; unsigned int
0x180004e1d  jmp     ?get_HashCode@CBufferBase@Dfdll@@QEAAJIIAEAK@Z; Dfdll::CBufferBase::get_HashCode(uint,uint,ulong &)
```
