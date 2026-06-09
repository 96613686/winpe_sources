# ReadLong

- ea: `0x18001a620`
- end: `0x18001a67a`
- name: `ReadLong`
- size: `90`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180008714`
- `0x18000c588`
- `0x18000e014`
- `0x18000f198`
- `0x180012640`
- `0x18001a3bc`

## callees

- `0x18001a208`
- `0x18001a620`

## pseudocode

```c
__int64 __fastcall ReadLong(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  _QWORD *v4; // rcx
  __int64 v5; // r9
  int *v6; // r10

  result = CheckInOffset(a1, a3, 4);
  if ( !(_WORD)result )
  {
    result = 0;
    *v6 = *(unsigned __int8 *)(v5 + *v4 + 3)
        | ((*(unsigned __int8 *)(v5 + *v4 + 2)
          | ((*(unsigned __int8 *)(v5 + *v4 + 1) | (*(unsigned __int8 *)(v5 + *v4) << 8)) << 8)) << 8);
  }
  return result;
}

```

## disassembly

```asm
0x18001a620  sub     rsp, 28h
0x18001a624  mov     r9d, r8d
0x18001a627  mov     r10, rdx
0x18001a62a  mov     edx, r9d
0x18001a62d  mov     r8d, 4
0x18001a633  call    CheckInOffset
0x18001a638  xor     r11d, r11d
0x18001a63b  test    ax, ax
0x18001a63e  jnz     short loc_18001A675
0x18001a640  mov     rcx, [rcx]
0x18001a643  movzx   eax, byte ptr [r9+rcx+1]
0x18001a649  movzx   r8d, byte ptr [r9+rcx]
0x18001a64e  shl     r8d, 8
0x18001a652  or      r8d, eax
0x18001a655  movzx   eax, byte ptr [r9+rcx+2]
0x18001a65b  shl     r8d, 8
0x18001a65f  or      r8d, eax
0x18001a662  movzx   eax, byte ptr [r9+rcx+3]
0x18001a668  shl     r8d, 8
0x18001a66c  or      r8d, eax
0x18001a66f  mov     eax, r11d
0x18001a672  mov     [r10], r8d
0x18001a675  add     rsp, 28h
0x18001a679  retn
```
