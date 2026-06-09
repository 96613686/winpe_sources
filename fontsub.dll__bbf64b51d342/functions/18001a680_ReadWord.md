# ReadWord

- ea: `0x18001a680`
- end: `0x18001a6c1`
- name: `ReadWord`
- size: `65`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b888`
- `0x18000bdd4`
- `0x18000c588`
- `0x18000d108`
- `0x18000de24`
- `0x18000e014`
- `0x18000e214`
- `0x18000e754`
- `0x18000f198`
- `0x1800109fc`
- `0x180010fd4`
- `0x180011f48`
- `0x180012640`
- `0x180014bc0`
- `0x180014dc0`
- `0x1800168d0`
- `0x180017a48`
- `0x180017cd4`
- `0x180017f04`
- `0x180018b84`
- `0x18001a3bc`

## callees

- `0x18001a208`
- `0x18001a680`

## pseudocode

```c
__int64 __fastcall ReadWord(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  _QWORD *v4; // rcx
  __int64 v5; // r9
  _WORD *v6; // r11

  result = CheckInOffset(a1, a3, 2);
  if ( !(_WORD)result )
  {
    result = 0;
    *v6 = _byteswap_ushort(*(_WORD *)(v5 + *v4));
  }
  return result;
}

```

## disassembly

```asm
0x18001a680  sub     rsp, 28h
0x18001a684  mov     r9d, r8d
0x18001a687  mov     r11, rdx
0x18001a68a  mov     edx, r9d
0x18001a68d  mov     r8d, 2
0x18001a693  call    CheckInOffset
0x18001a698  xor     r8d, r8d
0x18001a69b  test    ax, ax
0x18001a69e  jnz     short loc_18001A6BC
0x18001a6a0  mov     rax, [rcx]
0x18001a6a3  movzx   edx, byte ptr [r9+rax]
0x18001a6a8  movzx   eax, byte ptr [r9+rax+1]
0x18001a6ae  shl     dx, 8
0x18001a6b2  or      dx, ax
0x18001a6b5  mov     eax, r8d
0x18001a6b8  mov     [r11], dx
0x18001a6bc  add     rsp, 28h
0x18001a6c0  retn
```
