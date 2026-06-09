# DynArrayGetCount2

- ea: `0x14000f4d8`
- end: `0x14000f514`
- name: `DynArrayGetCount2`
- size: `60`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d3e8`
- `0x14000d694`
- `0x14000d900`
- `0x14000e3bc`

## callees

- `0x14000f4d8`
- `0x14000f8e8`

## pseudocode

```c
__int64 __fastcall DynArrayGetCount2(__int64 a1, unsigned int a2)
{
  __int64 Item; // rax
  _DWORD *v3; // rax

  Item = _DynArrayGetItem(qword_140015218, a2, 0);
  if ( Item && *(_DWORD *)(Item + 4) == 0x80000 && (v3 = *(_DWORD **)(Item + 16)) != 0 && *v3 == 9 )
    return (unsigned int)v3[1];
  else
    return 0;
}

```

## disassembly

```asm
0x14000f4d8  sub     rsp, 28h
0x14000f4dc  mov     rcx, cs:qword_140015218
0x14000f4e3  xor     r8d, r8d
0x14000f4e6  call    __DynArrayGetItem
0x14000f4eb  test    rax, rax
0x14000f4ee  jz      short loc_14000F50C
0x14000f4f0  cmp     dword ptr [rax+4], 80000h
0x14000f4f7  jnz     short loc_14000F50C
0x14000f4f9  mov     rax, [rax+10h]
0x14000f4fd  test    rax, rax
0x14000f500  jz      short loc_14000F50C
0x14000f502  cmp     dword ptr [rax], 9
0x14000f505  jnz     short loc_14000F50C
0x14000f507  mov     eax, [rax+4]
0x14000f50a  jmp     short loc_14000F50E
0x14000f50c  xor     eax, eax
0x14000f50e  add     rsp, 28h
0x14000f512  retn
```
