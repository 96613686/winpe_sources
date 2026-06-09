# ULongMult(x,x,x)

- ea: `0x1000422a`
- end: `0x10004255`
- name: `_ULongMult@12`
- size: `43`
- prototype: `HRESULT __stdcall(ULONG ulMultiplicand, ULONG ulMultiplier, ULONG *pulResult)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x10004695`
- `0x10006841`
- `0x100101f2`

## callees

- `0x1000422a`

## pseudocode

```c
HRESULT __stdcall ULongMult(ULONG ulMultiplicand, ULONG ulMultiplier, ULONG *pulResult)
{
  unsigned int v3; // edx
  unsigned int v4; // ecx
  int v5; // eax
  HRESULT v6; // edx

  v5 = v3 * v4;
  if ( is_mul_ok(v3, v4) )
  {
    v6 = 0;
  }
  else
  {
    v6 = -2147024362;
    v5 = -1;
  }
  *(_DWORD *)ulMultiplicand = v5;
  return v6;
}

```

## disassembly

```asm
0x1000422a  mov     edi, edi
0x1000422c  push    ebp
0x1000422d  mov     ebp, esp
0x1000422f  mov     eax, ecx
0x10004231  mul     edx
0x10004233  test    edx, edx
0x10004235  ja      short loc_10004242
0x10004237  jb      short loc_1000423E
0x10004239  cmp     eax, 0FFFFFFFFh
0x1000423c  ja      short loc_10004242
0x1000423e  xor     edx, edx
0x10004240  jmp     short loc_1000424A
0x10004242  mov     edx, 80070216h
0x10004247  or      eax, 0FFFFFFFFh
0x1000424a  mov     ecx, [ebp+ulMultiplicand]
0x1000424d  mov     [ecx], eax
0x1000424f  mov     eax, edx
0x10004251  pop     ebp
0x10004252  retn    4
```
