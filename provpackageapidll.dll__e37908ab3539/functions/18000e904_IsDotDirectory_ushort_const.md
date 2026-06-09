# IsDotDirectory(ushort const *)

- ea: `0x18000e904`
- end: `0x18000e941`
- name: `?IsDotDirectory@@YAHPEBG@Z`
- size: `61`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f78`
- `0x18000e328`
- `0x18000e948`

## callees

- `0x18000e904`

## pseudocode

```c
_BOOL8 __fastcall IsDotDirectory(const unsigned __int16 *a1)
{
  int v2; // edx

  if ( *a1 == 46 && !a1[1] )
    return 1;
  v2 = *a1 - 46;
  if ( *a1 == 46 )
  {
    v2 = a1[1] - 46;
    if ( a1[1] == 46 )
      v2 = a1[2];
  }
  return v2 == 0;
}

```

## disassembly

```asm
0x18000e904  xor     r8d, r8d
0x18000e907  lea     r9d, [r8+2Eh]
0x18000e90b  cmp     [rcx], r9w
0x18000e90f  jnz     short loc_18000E91D
0x18000e911  cmp     [rcx+2], r8w
0x18000e916  jnz     short loc_18000E91D
0x18000e918  lea     eax, [r8+1]
0x18000e91c  retn
0x18000e91d  movzx   edx, word ptr [rcx]
0x18000e920  sub     edx, r9d
0x18000e923  jnz     short loc_18000E938
0x18000e925  movzx   edx, word ptr [rcx+2]
0x18000e929  sub     edx, r9d
0x18000e92c  jnz     short loc_18000E938
0x18000e92e  movzx   edx, word ptr [rcx+4]
0x18000e932  movzx   ecx, r8w
0x18000e936  sub     edx, ecx
0x18000e938  test    edx, edx
0x18000e93a  mov     eax, r8d
0x18000e93d  setz    al
0x18000e940  retn
```
