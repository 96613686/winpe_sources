# MMRESULTToHRESULT(uint)

- ea: `0x18001b808`
- end: `0x18001b836`
- name: `?MMRESULTToHRESULT@@YAJI@Z`
- size: `46`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bbe0`
- `0x18001bd10`
- `0x18001bdc0`
- `0x18001c500`
- `0x18001c970`
- `0x18001ca1c`

## callees

- `0x18001b808`

## pseudocode

```c
__int64 __fastcall MMRESULTToHRESULT(int a1)
{
  __int64 result; // rax

  switch ( a1 )
  {
    case 0:
      return 0;
    case 4:
      return 2289570051LL;
    case 7:
      return 2147942414LL;
  }
  result = 2289570095LL;
  if ( a1 != 70 )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x18001b808  test    ecx, ecx
0x18001b80a  jz      short loc_18001B833
0x18001b80c  cmp     ecx, 4
0x18001b80f  jz      short loc_18001B82D
0x18001b811  cmp     ecx, 7
0x18001b814  jz      short loc_18001B827
0x18001b816  cmp     ecx, 46h ; 'F'
0x18001b819  mov     eax, 8878112Fh
0x18001b81e  mov     edx, 80004005h
0x18001b823  cmovnz  eax, edx
0x18001b826  retn
0x18001b827  mov     eax, 8007000Eh
0x18001b82c  retn
0x18001b82d  mov     eax, 88781103h
0x18001b832  retn
0x18001b833  xor     eax, eax
0x18001b835  retn
```
