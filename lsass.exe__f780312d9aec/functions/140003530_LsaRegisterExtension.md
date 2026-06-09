# LsaRegisterExtension

- ea: `0x140003530`
- end: `0x14000355e`
- name: `LsaRegisterExtension`
- size: `46`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140003530`

## pseudocode

```c
__int64 __fastcall LsaRegisterExtension(int a1, __int64 a2)
{
  __int64 result; // rax

  result = 0;
  if ( a1 )
  {
    if ( a1 == 2 )
    {
      gLsapSspiExtension = a2;
    }
    else if ( a1 == 3 )
    {
      gLsapLookupExtension = a2;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    gLsapRmExtension = a2;
  }
  return result;
}

```

## disassembly

```asm
0x140003530  xor     eax, eax
0x140003532  test    ecx, ecx
0x140003534  jnz     short loc_14000353E
0x140003536  mov     cs:gLsapRmExtension, rdx
0x14000353d  retn
0x14000353e  cmp     ecx, 2
0x140003541  jnz     short loc_14000354B
0x140003543  mov     cs:gLsapSspiExtension, rdx
0x14000354a  retn
0x14000354b  cmp     ecx, 3
0x14000354e  jnz     short loc_140003558
0x140003550  mov     cs:gLsapLookupExtension, rdx
0x140003557  retn
0x140003558  mov     eax, 0C000000Dh
0x14000355d  retn
```
