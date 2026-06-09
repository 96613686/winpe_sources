# sub_1CB39B7

- ea: `0x1cb39b7`
- end: `0x1cb39c8`
- name: `sub_1CB39B7`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_1CB39B7(__int64 a1)
{
  _BYTE *v1; // rbx
  unsigned int v2; // esp
  __int64 result; // rax
  bool v4; // cf

  result = v2;
  v4 = __CFADD__((_BYTE)result, *((_BYTE *)&dword_1000000 + 2 * a1 + result));
  *((_BYTE *)&dword_1000000 + 2 * a1 + result) += result;
  *v1 = v4 + *v1 - 108;
  return result;
}

```

## disassembly

```asm
0x1cb39b7  xchg    eax, esp
0x1cb39b8  mov     ecx, 0A130001h
0x1cb39bd  add     byte ptr ds:dword_1000000[rax+rdi*2], al
0x1cb39c4  adc     byte ptr [rbx], 94h
0x1cb39c7  retn
```
