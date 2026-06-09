# DavIsUrlPathLocal

- ea: `0x1800065b0`
- end: `0x1800065ef`
- name: `DavIsUrlPathLocal`
- size: `63`
- prototype: `__int64 __fastcall(__int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005a50`

## callees

- `0x1800065b0`

## pseudocode

```c
__int64 __fastcall DavIsUrlPathLocal(__int16 *a1)
{
  unsigned int v2; // edx
  __int16 v3; // ax

  if ( !a1 )
    return 0;
  v2 = 0;
  while ( 1 )
  {
    v3 = *a1;
    if ( !*a1 || v2 >= 3 )
      return 1;
    switch ( v3 )
    {
      case '/':
        goto LABEL_10;
      case '.':
        return 0;
      case '\\':
LABEL_10:
        ++v2;
        break;
    }
    ++a1;
  }
}

```

## disassembly

```asm
0x1800065b0  test    rcx, rcx
0x1800065b3  jnz     short loc_1800065B8
0x1800065b5  xor     eax, eax
0x1800065b7  retn
0x1800065b8  xor     edx, edx
0x1800065ba  nop     word ptr [rax+rax+00h]
0x1800065c0  movzx   eax, word ptr [rcx]
0x1800065c3  test    ax, ax
0x1800065c6  jz      short loc_1800065E9
0x1800065c8  cmp     edx, 3
0x1800065cb  jnb     short loc_1800065E9
0x1800065cd  cmp     ax, 2Fh ; '/'
0x1800065d1  jz      short loc_1800065E5
0x1800065d3  cmp     ax, 2Eh ; '.'
0x1800065d7  jz      short loc_1800065B5
0x1800065d9  cmp     ax, 5Ch ; '\'
0x1800065dd  jz      short loc_1800065E5
0x1800065df  add     rcx, 2
0x1800065e3  jmp     short loc_1800065C0
0x1800065e5  inc     edx
0x1800065e7  jmp     short loc_1800065DF
0x1800065e9  mov     eax, 1
0x1800065ee  retn
```
