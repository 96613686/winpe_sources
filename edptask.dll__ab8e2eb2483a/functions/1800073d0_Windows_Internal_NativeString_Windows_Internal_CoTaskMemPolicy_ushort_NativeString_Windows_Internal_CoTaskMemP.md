# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>(void)

- ea: `0x1800073d0`
- end: `0x1800073e1`
- name: `??0?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task`

## callers

- `0x18000ac1c`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x1800073d0  xor     eax, eax
0x1800073d2  mov     [rcx], rax
0x1800073d5  mov     [rcx+8], rax
0x1800073d9  mov     [rcx+10h], rax
0x1800073dd  mov     rax, rcx
0x1800073e0  retn
```
