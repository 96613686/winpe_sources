# DeleteQuotes(ushort *)

- ea: `0x1800090e0`
- end: `0x180009115`
- name: `?DeleteQuotes@@YAXPEAG@Z`
- size: `53`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df10`
- `0x180010b5c`
- `0x1800114b4`
- `0x180012a04`

## callees

- `0x1800090e0`

## pseudocode

```c
void __fastcall DeleteQuotes(unsigned __int16 *a1)
{
  unsigned __int16 v1; // ax
  unsigned __int16 *v2; // rdx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = a1;
    do
    {
      if ( v1 != 34 )
        *a1++ = *v2;
      if ( !*v2 )
        break;
      v1 = *++v2;
    }
    while ( *v2 );
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x1800090e0  movzx   eax, word ptr [rcx]
0x1800090e3  xor     r8d, r8d
0x1800090e6  test    ax, ax
0x1800090e9  jz      short loc_180009110
0x1800090eb  mov     rdx, rcx
0x1800090ee  cmp     ax, 22h ; '"'
0x1800090f2  jz      short loc_1800090FE
0x1800090f4  movzx   eax, word ptr [rdx]
0x1800090f7  mov     [rcx], ax
0x1800090fa  add     rcx, 2
0x1800090fe  cmp     [rdx], r8w
0x180009102  jz      short loc_180009110
0x180009104  add     rdx, 2
0x180009108  movzx   eax, word ptr [rdx]
0x18000910b  test    ax, ax
0x18000910e  jnz     short loc_1800090EE
0x180009110  mov     [rcx], r8w
0x180009114  retn
```
