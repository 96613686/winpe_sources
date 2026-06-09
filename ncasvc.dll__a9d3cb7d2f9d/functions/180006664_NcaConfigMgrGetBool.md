# NcaConfigMgrGetBool

- ea: `0x180006664`
- end: `0x1800066a2`
- name: `NcaConfigMgrGetBool`
- size: `62`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007b58`
- `0x180014620`

## callees

- `0x180006664`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrGetBool(int a1)
{
  __int64 result; // rax

  switch ( a1 )
  {
    case 3:
      return 1;
    case 4:
      return DWORD2(xmmword_180028BF8);
    case 5:
      return HIDWORD(xmmword_180028BF8);
    case 6:
      return (unsigned int)xmmword_180028C08;
  }
  result = 0;
  if ( a1 == 8 )
    return (unsigned int)xmmword_180028C18;
  return result;
}

```

## disassembly

```asm
0x180006664  cmp     ecx, 3
0x180006667  jnz     short loc_18000666E
0x180006669  lea     eax, [rcx-2]
0x18000666c  retn
0x18000666e  cmp     ecx, 4
0x180006671  jnz     short loc_18000667B
0x180006673  mov     eax, dword ptr cs:xmmword_180028BF8+8
0x180006679  retn
0x18000667b  cmp     ecx, 5
0x18000667e  jnz     short loc_180006688
0x180006680  mov     eax, dword ptr cs:xmmword_180028BF8+0Ch
0x180006686  retn
0x180006688  cmp     ecx, 6
0x18000668b  jnz     short loc_180006695
0x18000668d  mov     eax, dword ptr cs:xmmword_180028C08
0x180006693  retn
0x180006695  xor     eax, eax
0x180006697  cmp     ecx, 8
0x18000669a  cmovz   eax, dword ptr cs:xmmword_180028C18
0x1800066a1  retn
```
