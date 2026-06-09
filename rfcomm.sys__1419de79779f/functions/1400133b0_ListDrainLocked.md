# ListDrainLocked

- ea: `0x1400133b0`
- end: `0x1400133f8`
- name: `ListDrainLocked`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140006814`
- `0x140012590`
- `0x14001291c`
- `0x140017ab8`
- `0x140017db4`
- `0x140018330`
- `0x1400186b4`
- `0x1400197ec`

## callees

- `0x1400133b0`

## pseudocode

```c
__int64 __fastcall ListDrainLocked(__int64 a1, _QWORD **a2)
{
  unsigned int v2; // r8d
  _QWORD *v3; // rax
  _QWORD *v4; // r9
  _QWORD *v5; // r9

  v2 = 0;
  while ( 1 )
  {
    v3 = *a2;
    if ( *a2 == a2 )
      break;
    if ( (_QWORD **)v3[1] != a2
      || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3)
      || (*a2 = v4, v4[1] = a2, v5 = *(_QWORD **)(a1 + 8), *v5 != a1) )
    {
      __fastfail(3u);
    }
    *v3 = a1;
    ++v2;
    v3[1] = v5;
    *v5 = v3;
    *(_QWORD *)(a1 + 8) = v3;
  }
  return v2;
}

```

## disassembly

```asm
0x1400133b0  xor     r8d, r8d
0x1400133b3  mov     rax, [rdx]
0x1400133b6  cmp     rax, rdx
0x1400133b9  jz      short loc_1400133F4
0x1400133bb  cmp     [rax+8], rdx
0x1400133bf  jnz     short loc_1400133ED
0x1400133c1  mov     r9, [rax]
0x1400133c4  cmp     [r9+8], rax
0x1400133c8  jnz     short loc_1400133ED
0x1400133ca  mov     [rdx], r9
0x1400133cd  mov     [r9+8], rdx
0x1400133d1  mov     r9, [rcx+8]
0x1400133d5  cmp     [r9], rcx
0x1400133d8  jnz     short loc_1400133ED
0x1400133da  mov     [rax], rcx
0x1400133dd  inc     r8d
0x1400133e0  mov     [rax+8], r9
0x1400133e4  mov     [r9], rax
0x1400133e7  mov     [rcx+8], rax
0x1400133eb  jmp     short loc_1400133B3
0x1400133ed  mov     ecx, 3
0x1400133f2  int     29h; Win8: RtlFailFast(ecx)
0x1400133f4  mov     eax, r8d
0x1400133f7  retn
```
