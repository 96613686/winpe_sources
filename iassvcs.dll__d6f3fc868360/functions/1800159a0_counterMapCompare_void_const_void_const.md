# counterMapCompare(void const *,void const *)

- ea: `0x1800159a0`
- end: `0x1800159a5`
- name: `?counterMapCompare@@YAHPEBX0@Z`
- size: `5`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall counterMapCompare(_DWORD *a1, _DWORD *a2)
{
  return (unsigned int)(*a1 - *a2);
}

```

## disassembly

```asm
0x1800159a0  mov     eax, [rcx]
0x1800159a2  sub     eax, [rdx]
0x1800159a4  retn
```
