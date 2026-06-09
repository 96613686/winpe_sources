# sub_1C0DD20

- ea: `0x1c0dd20`
- end: `0x1c0dd26`
- name: `sub_1C0DD20`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_1C0DD20(__int64 a1, __int64 a2, _BYTE *a3, _BYTE *a4)
{
  __int64 result; // rax
  bool v5; // cf

  v5 = __CFADD__((_BYTE)result, *a4);
  *a4 += result;
  *a3 += v5 + 52;
  return result;
}

```

## disassembly

```asm
0x1c0dd20  add     [rcx], al
0x1c0dd22  adc     byte ptr [rdx], 34h ; '4'
0x1c0dd25  retn
```
