# CopyFragments(x,x,x,x)

- ea: `0x100055d1`
- end: `0x100055f7`
- name: `_CopyFragments@16`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1000646f`

## callees

- `0x100055d1`

## pseudocode

```c
int __fastcall CopyFragments(int a1, int a2, int a3, int a4)
{
  int *v4; // esi
  _DWORD *v5; // ecx
  int result; // eax

  v4 = (int *)(a1 + 4 * a3);
  v5 = (_DWORD *)(a1 + 4 * a2);
  do
  {
    result = *v4++;
    *v5++ = result;
    --a4;
  }
  while ( a4 );
  return result;
}

```

## disassembly

```asm
0x100055d1  mov     edi, edi
0x100055d3  push    ebp
0x100055d4  mov     ebp, esp
0x100055d6  mov     eax, [ebp+arg_0]
0x100055d9  push    esi
0x100055da  lea     esi, [ecx+eax*4]
0x100055dd  lea     ecx, [ecx+edx*4]
0x100055e0  mov     edx, [ebp+arg_4]
0x100055e3  mov     eax, [esi]
0x100055e5  lea     esi, [esi+4]
0x100055e8  mov     [ecx], eax
0x100055ea  lea     ecx, [ecx+4]
0x100055ed  sub     edx, 1
0x100055f0  jnz     short loc_100055E3
0x100055f2  pop     esi
0x100055f3  pop     ebp
0x100055f4  retn    8
```
