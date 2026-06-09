# AslStringXmlSanitize

- ea: `0x18000f334`
- end: `0x18000f396`
- name: `AslStringXmlSanitize`
- size: `98`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fd14`
- `0x1800103dc`
- `0x180010c48`
- `0x180012708`

## callees

- `0x18000f334`

## pseudocode

```c
__int64 __fastcall AslStringXmlSanitize(_WORD *a1)
{
  unsigned __int64 v2; // rax
  unsigned __int64 i; // rdx
  unsigned __int16 v4; // r9
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
      while ( v4 < *((_WORD *)qword_18001EC50 + 2 * v5) || v4 > *((_WORD *)qword_18001EC50 + 2 * v5 + 1) )
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
0x18000f334  xor     r10d, r10d
0x18000f337  test    rcx, rcx
0x18000f33a  jnz     short loc_18000F342
0x18000f33c  mov     eax, 0C000000Dh
0x18000f341  retn
0x18000f342  cmp     [rcx], r10w
0x18000f346  jz      short loc_18000F393
0x18000f348  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f34c  inc     rax
0x18000f34f  cmp     [rcx+rax*2], r10w
0x18000f354  jnz     short loc_18000F34C
0x18000f356  mov     rdx, r10
0x18000f359  test    rax, rax
0x18000f35c  jz      short loc_18000F393
0x18000f35e  lea     r11, qword_18001EC50
0x18000f365  movzx   r9d, word ptr [rcx+rdx*2]
0x18000f36a  mov     r8, r10
0x18000f36d  cmp     r9w, [r11+r8*4]
0x18000f372  jb      short loc_18000F37C
0x18000f374  cmp     r9w, [r11+r8*4+2]
0x18000f37a  jbe     short loc_18000F38B
0x18000f37c  inc     r8
0x18000f37f  cmp     r8, 5
0x18000f383  jb      short loc_18000F36D
0x18000f385  mov     word ptr [rcx+rdx*2], 40h ; '@'
0x18000f38b  inc     rdx
0x18000f38e  cmp     rdx, rax
0x18000f391  jb      short loc_18000F365
0x18000f393  xor     eax, eax
0x18000f395  retn
```
