# ValidImageSizeForFOURCC(ulong,long,long)

- ea: `0x18000e514`
- end: `0x18000e5b0`
- name: `?ValidImageSizeForFOURCC@@YAHKJJ@Z`
- size: `156`
- prototype: `_BOOL8 __fastcall(int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800040b0`
- `0x18000d350`
- `0x18000e160`

## callees

- `0x18000e514`

## pseudocode

```c
_BOOL8 __fastcall ValidImageSizeForFOURCC(int a1, int a2, int a3)
{
  char v3; // r10
  int v4; // r9d
  int v5; // edx

  v3 = a2;
  v4 = -a3;
  if ( a3 > 0 )
    v4 = a3;
  if ( !a2 || !v4 )
    return 0;
  if ( !a1 || a1 == 3 || a1 == 1448433985 || a1 == 808531030 )
    return 1;
  if ( (a2 & 1) != 0 || (a1 == 1448433993 || a1 == 808596553 || a1 == 842094169 || a1 == 842094158) && (v4 & 1) != 0 )
    return 0;
  v5 = a2 & 3;
  if ( a1 == 825316942 )
    return v5 == 0;
  if ( ((a1 - 1345401945) & 0xFBFFFFFF) == 0 )
    return (v3 & 7) == 0;
  if ( a1 != 961893977 )
    return 1;
  if ( !v5 )
    return (v4 & 3) == 0;
  return 0;
}

```

## disassembly

```asm
0x18000e514  mov     r9d, r8d
0x18000e517  mov     r10d, edx
0x18000e51a  neg     r9d
0x18000e51d  cmovs   r9d, r8d
0x18000e521  test    edx, edx
0x18000e523  jz      loc_18000E5AD
0x18000e529  test    r9d, r9d
0x18000e52c  jz      short loc_18000E5AD
0x18000e52e  test    ecx, ecx
0x18000e530  jz      short loc_18000E5A7
0x18000e532  cmp     ecx, 3
0x18000e535  jz      short loc_18000E5A7
0x18000e537  cmp     ecx, 56555941h
0x18000e53d  jz      short loc_18000E5A7
0x18000e53f  cmp     ecx, 30313456h
0x18000e545  jz      short loc_18000E5A7
0x18000e547  test    r10b, 1
0x18000e54b  jnz     short loc_18000E5AD
0x18000e54d  cmp     ecx, 56555949h
0x18000e553  jz      short loc_18000E56D
0x18000e555  cmp     ecx, 30323449h
0x18000e55b  jz      short loc_18000E56D
0x18000e55d  cmp     ecx, 32315659h
0x18000e563  jz      short loc_18000E56D
0x18000e565  cmp     ecx, 3231564Eh
0x18000e56b  jnz     short loc_18000E573
0x18000e56d  test    r9b, 1
0x18000e571  jnz     short loc_18000E5AD
0x18000e573  and     edx, 3
0x18000e576  cmp     ecx, 3131564Eh
0x18000e57c  jnz     short loc_18000E582
0x18000e57e  test    edx, edx
0x18000e580  jmp     short loc_18000E5A5
0x18000e582  lea     eax, [rcx-50313459h]
0x18000e588  test    eax, 0FBFFFFFFh
0x18000e58d  jz      short loc_18000E5A1
0x18000e58f  cmp     ecx, 39555659h
0x18000e595  jnz     short loc_18000E5A7
0x18000e597  test    edx, edx
0x18000e599  jnz     short loc_18000E5AD
0x18000e59b  test    r9b, 3
0x18000e59f  jmp     short loc_18000E5A5
0x18000e5a1  test    r10b, 7
0x18000e5a5  jnz     short loc_18000E5AD
0x18000e5a7  mov     eax, 1
0x18000e5ac  retn
0x18000e5ad  xor     eax, eax
0x18000e5af  retn
```
