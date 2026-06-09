# AslStringXmlSanitize

- ea: `0x140009c14`
- end: `0x140009c76`
- name: `AslStringXmlSanitize`
- size: `98`
- prototype: `__int64 __fastcall(_WORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000d190`
- `0x14000d858`
- `0x14000e0c4`
- `0x14000f3a8`

## callees

- `0x140009c14`

## pseudocode

```c
__int64 __fastcall AslStringXmlSanitize(_WORD *a1)
{
  unsigned __int64 v2; // rax
  unsigned __int64 i; // rdx
  wchar_t v4; // r9
  __int64 v5; // r8

  if ( !a1 )
    return 3221225485LL;
  if ( *a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
    for ( i = 0; i < v2; ++i )
    {
      v4 = a1[i];
      v5 = 0;
      while ( v4 < asc_140016780[2 * v5] || v4 > asc_140016780[2 * v5 + 1] )
      {
        if ( (unsigned __int64)++v5 >= 5 )
        {
          a1[i] = 64;
          break;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140009c14  xor     r10d, r10d
0x140009c17  test    rcx, rcx
0x140009c1a  jnz     short loc_140009C22
0x140009c1c  mov     eax, 0C000000Dh
0x140009c21  retn
0x140009c22  cmp     [rcx], r10w
0x140009c26  jz      short loc_140009C73
0x140009c28  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009c2c  inc     rax
0x140009c2f  cmp     [rcx+rax*2], r10w
0x140009c34  jnz     short loc_140009C2C
0x140009c36  mov     rdx, r10
0x140009c39  test    rax, rax
0x140009c3c  jz      short loc_140009C73
0x140009c3e  lea     r11, asc_140016780; " ~"
0x140009c45  movzx   r9d, word ptr [rcx+rdx*2]
0x140009c4a  mov     r8, r10
0x140009c4d  cmp     r9w, [r11+r8*4]
0x140009c52  jb      short loc_140009C5C
0x140009c54  cmp     r9w, [r11+r8*4+2]
0x140009c5a  jbe     short loc_140009C6B
0x140009c5c  inc     r8
0x140009c5f  cmp     r8, 5
0x140009c63  jb      short loc_140009C4D
0x140009c65  mov     word ptr [rcx+rdx*2], 40h ; '@'
0x140009c6b  inc     rdx
0x140009c6e  cmp     rdx, rax
0x140009c71  jb      short loc_140009C45
0x140009c73  xor     eax, eax
0x140009c75  retn
```
