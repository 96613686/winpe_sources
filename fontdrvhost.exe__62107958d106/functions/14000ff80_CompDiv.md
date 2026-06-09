# CompDiv

- ea: `0x14000ff80`
- end: `0x14000ffc6`
- name: `CompDiv`
- size: `70`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000c29c`
- `0x14000cf80`
- `0x14000d918`
- `0x14000e19c`
- `0x14000e348`
- `0x14000eaa8`
- `0x140010640`
- `0x140014364`
- `0x14001e250`
- `0x14001ee40`
- `0x140020740`
- `0x1400239e0`
- `0x140024280`
- `0x140029e04`
- `0x140029f2c`
- `0x14002a840`
- `0x14002ddc0`
- `0x140049848`
- `0x140055d70`
- `0x14005e090`

## callees

- `0x14000ff80`

## pseudocode

```c
__int64 __fastcall CompDiv(int a1, __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r8

  v2 = a1 / 2;
  v3 = a2 - v2;
  if ( a1 < 0 == a2 < 0 )
    v3 = v2 + a2;
  if ( a1 )
    return v3 / a1;
  else
    return (v3 < 0) + 0x7FFFFFFFLL;
}

```

## disassembly

```asm
0x14000ff80  mov     r8, rdx
0x14000ff83  mov     eax, ecx
0x14000ff85  cdq
0x14000ff86  mov     r10, r8
0x14000ff89  sub     eax, edx
0x14000ff8b  shr     r10, 3Fh
0x14000ff8f  sar     eax, 1
0x14000ff91  mov     edx, ecx
0x14000ff93  movsxd  r9, eax
0x14000ff96  shr     edx, 1Fh
0x14000ff99  lea     rax, [r9+r8]
0x14000ff9d  sub     r8, r9
0x14000ffa0  cmp     dl, r10b
0x14000ffa3  cmovz   r8, rax
0x14000ffa7  test    ecx, ecx
0x14000ffa9  jz      short loc_14000FFB7
0x14000ffab  mov     rax, r8
0x14000ffae  movsxd  rcx, ecx
0x14000ffb1  cqo
0x14000ffb3  idiv    rcx
0x14000ffb6  retn
0x14000ffb7  xor     eax, eax
0x14000ffb9  test    r8, r8
0x14000ffbc  sets    al
0x14000ffbf  add     rax, 7FFFFFFFh
0x14000ffc5  retn
```
