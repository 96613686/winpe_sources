# sub_478DD7F

- ea: `0x478dd7f`
- end: `0x478dd8b`
- name: `sub_478DD7F`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_478DD7F()
{
  _BYTE *v0; // rax
  _DWORD *v1; // rbx
  bool v2; // cf

  *v0 ^= (unsigned __int8)v0;
  *v1 -= (_DWORD)v0;
  *v0 &= (unsigned __int8)v0;
  v2 = __CFADD__((_BYTE)v0, 3);
  LOBYTE(v0) = (_BYTE)v0 + 3;
  *v0 += (_BYTE)v0 + v2;
  __asm { sysret }
}

```

## disassembly

```asm
0x478dd7f  xor     [rax], al
0x478dd81  sbb     [rbx], eax
0x478dd83  and     [rax], al
0x478dd85  add     al, 3
0x478dd87  adc     [rax], al
0x478dd89  sysret
```
