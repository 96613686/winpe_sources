# QuicAddrCompare

- ea: `0x140004840`
- end: `0x140004871`
- name: `QuicAddrCompare`
- size: `49`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003db4`
- `0x140004730`
- `0x14002a048`
- `0x14002fbf8`
- `0x14003ff2c`
- `0x140042c20`

## callees

- `0x140004840`

## pseudocode

```c
bool __fastcall QuicAddrCompare(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx

  if ( *(_WORD *)a1 != *(_WORD *)a2 || *(_WORD *)(a1 + 2) != *(_WORD *)(a2 + 2) )
    return 0;
  if ( *(_WORD *)a1 == 2 )
    return *(_DWORD *)(a1 + 4) == *(_DWORD *)(a2 + 4);
  v4 = *(_QWORD *)(a1 + 8) - *(_QWORD *)(a2 + 8);
  if ( !v4 )
    v4 = *(_QWORD *)(a1 + 16) - *(_QWORD *)(a2 + 16);
  return v4 == 0;
}

```

## disassembly

```asm
0x140004840  mov     r8, rdx
0x140004843  movzx   edx, word ptr [rcx]
0x140004846  cmp     dx, [r8]
0x14000484a  jnz     short loc_14000486E
0x14000484c  movzx   eax, word ptr [r8+2]
0x140004851  cmp     [rcx+2], ax
0x140004855  jnz     short loc_14000486E
0x140004857  cmp     dx, 2
0x14000485b  jnz     loc_14003D3D4
0x140004861  mov     edx, [rcx+4]
0x140004864  cmp     edx, [r8+4]
0x140004868  jnz     short loc_14000486E
0x14000486a  mov     al, 1
0x14000486c  retn
0x14000486e  xor     al, al
0x140004870  retn
0x14003d3d4  mov     rdx, [rcx+8]
0x14003d3d8  sub     rdx, [r8+8]
0x14003d3dc  jnz     short loc_14003D3E6
0x14003d3de  mov     rdx, [rcx+10h]
0x14003d3e2  sub     rdx, [r8+10h]
0x14003d3e6  test    rdx, rdx
0x14003d3e9  setz    al
0x14003d3ec  retn
```
