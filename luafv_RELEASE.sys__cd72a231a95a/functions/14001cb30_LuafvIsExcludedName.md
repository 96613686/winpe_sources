# LuafvIsExcludedName

- ea: `0x14001cb30`
- end: `0x14001cbc5`
- name: `LuafvIsExcludedName`
- size: `149`
- prototype: `char __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a378`
- `0x14001af3c`
- `0x14001c3d0`
- `0x14001cae4`

## callees

- `0x14001cb30`
- `0x14001cbd0`

## pseudocode

```c
char __fastcall LuafvIsExcludedName(unsigned __int16 *a1)
{
  __int64 v1; // rax
  unsigned __int64 v2; // rdx
  _WORD *v3; // r8
  _WORD *v4; // r10
  _WORD *v5; // rax
  __int16 v6; // cx
  __int64 v7; // r10
  _WORD *v9; // rcx

  if ( !byte_14000EADD )
    return 0;
  v1 = *a1;
  if ( !(_WORD)v1 )
    return 0;
  v2 = *((_QWORD *)a1 + 1);
  v3 = 0;
  v4 = (_WORD *)(v2 + v1);
  v5 = (_WORD *)(v2 + v1 - 2);
  if ( (unsigned __int64)v5 < v2 )
    return 0;
  do
  {
    v6 = *v5;
    if ( *v5 == 46 )
    {
      v9 = v5;
      if ( v3 )
        v9 = v3;
      v3 = v9;
    }
    else if ( v6 == 58 )
    {
      v4 = v5;
      v3 = 0;
    }
    else if ( v6 == 92 )
    {
      break;
    }
    --v5;
  }
  while ( (unsigned __int64)v5 >= v2 );
  if ( v3 && (v7 = v4 - (v3 + 1), (_DWORD)v7) )
    return IsExcludedExtension(v3 + 1, (unsigned int)v7, 0, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x14001cb30  sub     rsp, 28h
0x14001cb34  cmp     cs:byte_14000EADD, 0
0x14001cb3b  jz      short loc_14001CBA6
0x14001cb3d  movzx   eax, word ptr [rcx]
0x14001cb40  test    ax, ax
0x14001cb43  jz      short loc_14001CBA6
0x14001cb45  mov     rdx, [rcx+8]
0x14001cb49  xor     r8d, r8d
0x14001cb4c  lea     r10, [rdx+rax]
0x14001cb50  lea     rax, [r10-2]
0x14001cb54  cmp     rax, rdx
0x14001cb57  jb      short loc_14001CBA6
0x14001cb59  nop     dword ptr [rax+00000000h]
0x14001cb60  movzx   ecx, word ptr [rax]
0x14001cb63  cmp     cx, 2Eh ; '.'
0x14001cb67  jz      short loc_14001CBAE
0x14001cb69  cmp     cx, 3Ah ; ':'
0x14001cb6d  jz      short loc_14001CBBD
0x14001cb6f  cmp     cx, 5Ch ; '\'
0x14001cb73  jz      short loc_14001CB7E
0x14001cb75  sub     rax, 2
0x14001cb79  cmp     rax, rdx
0x14001cb7c  jnb     short loc_14001CB60
0x14001cb7e  test    r8, r8
0x14001cb81  jz      short loc_14001CBA6
0x14001cb83  lea     rcx, [r8+2]
0x14001cb87  sub     r10, rcx
0x14001cb8a  sar     r10, 1
0x14001cb8d  test    r10d, r10d
0x14001cb90  jz      short loc_14001CBA6
0x14001cb92  xor     r9d, r9d
0x14001cb95  xor     r8d, r8d
0x14001cb98  mov     edx, r10d
0x14001cb9b  call    IsExcludedExtension
0x14001cba0  add     rsp, 28h
0x14001cba4  retn
0x14001cba6  xor     al, al
0x14001cba8  add     rsp, 28h
0x14001cbac  retn
0x14001cbae  test    r8, r8
0x14001cbb1  mov     rcx, rax
0x14001cbb4  cmovnz  rcx, r8
0x14001cbb8  mov     r8, rcx
0x14001cbbb  jmp     short loc_14001CB75
0x14001cbbd  mov     r10, rax
0x14001cbc0  xor     r8d, r8d
0x14001cbc3  jmp     short loc_14001CB75
```
