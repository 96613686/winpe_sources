# FIPfOpenAttemptsInitialize

- ea: `0x1400166b4`
- end: `0x1400166d1`
- name: `FIPfOpenAttemptsInitialize`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140018078`

## pseudocode

```c
_QWORD *__fastcall FIPfOpenAttemptsInitialize(_QWORD *a1)
{
  _QWORD *result; // rax

  *a1 = 0;
  a1[1] = 0;
  a1[4] = 0;
  a1[5] = 0;
  result = a1 + 2;
  a1[3] = a1 + 2;
  a1[2] = a1 + 2;
  return result;
}

```

## disassembly

```asm
0x1400166b4  xor     eax, eax
0x1400166b6  mov     [rcx], rax
0x1400166b9  mov     [rcx+8], rax
0x1400166bd  mov     [rcx+20h], rax
0x1400166c1  mov     [rcx+28h], rax
0x1400166c5  lea     rax, [rcx+10h]
0x1400166c9  mov     [rax+8], rax
0x1400166cd  mov     [rax], rax
0x1400166d0  retn
```
