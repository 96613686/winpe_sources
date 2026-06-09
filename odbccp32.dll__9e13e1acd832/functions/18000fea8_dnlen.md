# dnlen

- ea: `0x18000fea8`
- end: `0x18000fec9`
- name: `dnlen`
- size: `33`
- prototype: `__int16 __fastcall(_BYTE *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ec20`
- `0x18000f2b0`
- `0x18000f3e0`
- `0x18000f600`

## callees

- `0x18000fea8`

## pseudocode

```c
__int16 __fastcall dnlen(_BYTE *a1)
{
  __int16 result; // ax
  bool v2; // zf
  _BYTE *v3; // rdx

  result = 0;
  if ( a1 )
  {
    while ( 1 )
    {
      v2 = *a1 == 0;
      v3 = ++a1;
      if ( v2 && !*v3 )
        break;
      ++result;
    }
    result += 2;
  }
  return result;
}

```

## disassembly

```asm
0x18000fea8  xor     eax, eax
0x18000feaa  test    rcx, rcx
0x18000fead  jz      short locret_18000FEC8
0x18000feaf  cmp     byte ptr [rcx], 0
0x18000feb2  lea     rdx, [rcx+1]
0x18000feb6  mov     rcx, rdx
0x18000feb9  jnz     short loc_18000FEC0
0x18000febb  cmp     byte ptr [rdx], 0
0x18000febe  jz      short loc_18000FEC4
0x18000fec0  inc     eax
0x18000fec2  jmp     short loc_18000FEAF
0x18000fec4  add     ax, 2
0x18000fec8  retn
```
