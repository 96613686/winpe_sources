# LuafvIsExcludedName

- ea: `0x14001cb80`
- end: `0x14001cc15`
- name: `LuafvIsExcludedName`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001a3c8`
- `0x14001af8c`
- `0x14001c420`
- `0x14001cb34`

## callees

- `0x14001cb80`
- `0x14001cc20`

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

  if ( !byte_14000F11D )
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
    return IsExcludedExtension(v3 + 1, v7, 0, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x14001cb80  sub     rsp, 28h
0x14001cb84  cmp     cs:byte_14000F11D, 0
0x14001cb8b  jz      short loc_14001CBF6
0x14001cb8d  movzx   eax, word ptr [rcx]
0x14001cb90  test    ax, ax
0x14001cb93  jz      short loc_14001CBF6
0x14001cb95  mov     rdx, [rcx+8]
0x14001cb99  xor     r8d, r8d
0x14001cb9c  lea     r10, [rdx+rax]
0x14001cba0  lea     rax, [r10-2]
0x14001cba4  cmp     rax, rdx
0x14001cba7  jb      short loc_14001CBF6
0x14001cba9  nop     dword ptr [rax+00000000h]
0x14001cbb0  movzx   ecx, word ptr [rax]
0x14001cbb3  cmp     cx, 2Eh ; '.'
0x14001cbb7  jz      short loc_14001CBFE
0x14001cbb9  cmp     cx, 3Ah ; ':'
0x14001cbbd  jz      short loc_14001CC0D
0x14001cbbf  cmp     cx, 5Ch ; '\'
0x14001cbc3  jz      short loc_14001CBCE
0x14001cbc5  sub     rax, 2
0x14001cbc9  cmp     rax, rdx
0x14001cbcc  jnb     short loc_14001CBB0
0x14001cbce  test    r8, r8
0x14001cbd1  jz      short loc_14001CBF6
0x14001cbd3  lea     rcx, [r8+2]
0x14001cbd7  sub     r10, rcx
0x14001cbda  sar     r10, 1
0x14001cbdd  test    r10d, r10d
0x14001cbe0  jz      short loc_14001CBF6
0x14001cbe2  xor     r9d, r9d
0x14001cbe5  xor     r8d, r8d
0x14001cbe8  mov     edx, r10d
0x14001cbeb  call    IsExcludedExtension
0x14001cbf0  add     rsp, 28h
0x14001cbf4  retn
0x14001cbf6  xor     al, al
0x14001cbf8  add     rsp, 28h
0x14001cbfc  retn
0x14001cbfe  test    r8, r8
0x14001cc01  mov     rcx, rax
0x14001cc04  cmovnz  rcx, r8
0x14001cc08  mov     r8, rcx
0x14001cc0b  jmp     short loc_14001CBC5
0x14001cc0d  mov     r10, rax
0x14001cc10  xor     r8d, r8d
0x14001cc13  jmp     short loc_14001CBC5
```
