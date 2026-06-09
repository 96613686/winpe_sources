# sub_4AFF711

- ea: `0x4aff711`
- end: `0x4aff723`
- name: `sub_4AFF711`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_4AFF711()
{
  _BYTE *v0; // rax
  _DWORD *v1; // rbx
  bool v2; // cf

  LOBYTE(v0) = *(_BYTE *)v1;
  *v0 ^= (unsigned __int8)v0;
  v2 = __CFADD__((_DWORD)v0, *v1);
  *v1 += (_DWORD)v0;
  *v0 += (_BYTE)v0 + v2;
  __asm { sysret }
}

```

## disassembly

```asm
0x4aff711  mov     al, [rbx]
0x4aff713  xor     [rax], al
0x4aff715  cmp     eax, 3003h
0x4aff71a  add     edx, [rax+0]
0x4aff71d  add     [rbx], eax
0x4aff71f  adc     [rax], al
0x4aff721  sysret
```
