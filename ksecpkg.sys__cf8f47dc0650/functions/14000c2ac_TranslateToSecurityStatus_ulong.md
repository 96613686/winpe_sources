# TranslateToSecurityStatus(ulong)

- ea: `0x14000c2ac`
- end: `0x14000c395`
- name: `?TranslateToSecurityStatus@@YAJK@Z`
- size: `233`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140031100`
- `0x1400311e0`

## callees

- `0x14000c2ac`

## pseudocode

```c
__int64 __fastcall TranslateToSecurityStatus(unsigned int a1)
{
  __int64 result; // rax

  if ( (a1 & 0x1FFF0000) == 0x90000 )
  {
    if ( a1 + 2146893823 <= 0x2E )
      return 2148074244LL;
    if ( a1 + 2146889727 > 0x1FFF || a1 == -2146885616 || a1 == -2146885614 || a1 == -2146885613 )
      return a1;
  }
  if ( !a1 )
    return 0;
  if ( a1 > 0x80092004 )
  {
    switch ( a1 )
    {
      case 0x800B0101:
      case 0x800B0102:
        return 2148074280LL;
      case 0x800B0109:
        return 2148074277LL;
      case 0x800B010C:
        return 2148081680LL;
      default:
        result = 2148074274LL;
        if ( a1 != -2146762481 )
          return 2148074244LL;
        break;
    }
  }
  else
  {
    switch ( a1 )
    {
      case 0x80092004:
        return 2148074253LL;
      case 0xEu:
        return 2148074240LL;
      case 0x57u:
        return 2148074333LL;
      case 0x78u:
        return 2148074242LL;
      case 0x7Au:
        return 2148074273LL;
      case 0x13Bu:
        return 2148074248LL;
      default:
        return 2148074244LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c2ac  mov     eax, ecx
0x14000c2ae  and     eax, 1FFF0000h
0x14000c2b3  cmp     eax, 90000h
0x14000c2b8  jnz     short loc_14000C2F5
0x14000c2ba  lea     eax, [rcx+7FF6FFFFh]
0x14000c2c0  cmp     eax, 2Eh ; '.'
0x14000c2c3  jbe     short loc_14000C2EE
0x14000c2c5  lea     eax, [rcx+7FF6EFFFh]
0x14000c2cb  cmp     eax, 1FFFh
0x14000c2d0  ja      short loc_14000C2EA
0x14000c2d2  cmp     ecx, 80092010h
0x14000c2d8  jz      short loc_14000C2EA
0x14000c2da  cmp     ecx, 80092012h
0x14000c2e0  jz      short loc_14000C2EA
0x14000c2e2  cmp     ecx, 80092013h
0x14000c2e8  jnz     short loc_14000C2F5
0x14000c2ea  mov     eax, ecx
0x14000c2ec  retn
0x14000c2ee  mov     eax, 80090304h
0x14000c2f3  retn
0x14000c2f5  test    ecx, ecx
0x14000c2f7  jnz     short loc_14000C2FD
0x14000c2f9  xor     eax, eax
0x14000c2fb  retn
0x14000c2fd  mov     eax, 80092004h
0x14000c302  cmp     ecx, eax
0x14000c304  ja      short loc_14000C34E
0x14000c306  jz      short loc_14000C347
0x14000c308  cmp     ecx, 0Eh
0x14000c30b  jz      short loc_14000C340
0x14000c30d  cmp     ecx, 57h ; 'W'
0x14000c310  jz      short loc_14000C339
0x14000c312  cmp     ecx, 78h ; 'x'
0x14000c315  jz      short loc_14000C332
0x14000c317  cmp     ecx, 7Ah ; 'z'
0x14000c31a  jz      short loc_14000C32B
0x14000c31c  cmp     ecx, 13Bh
0x14000c322  jnz     short loc_14000C2EE
0x14000c324  mov     eax, 80090308h
0x14000c329  retn
0x14000c32b  mov     eax, 80090321h
0x14000c330  retn
0x14000c332  mov     eax, 80090302h
0x14000c337  retn
0x14000c339  mov     eax, 8009035Dh
0x14000c33e  retn
0x14000c340  mov     eax, 80090300h
0x14000c345  retn
0x14000c347  mov     eax, 8009030Dh
0x14000c34c  retn
0x14000c34e  cmp     ecx, 800B0101h
0x14000c354  jz      short loc_14000C38F
0x14000c356  cmp     ecx, 800B0102h
0x14000c35c  jz      short loc_14000C38F
0x14000c35e  cmp     ecx, 800B0109h
0x14000c364  jz      short loc_14000C388
0x14000c366  cmp     ecx, 800B010Ch
0x14000c36c  jz      short loc_14000C381
0x14000c36e  mov     eax, 80090322h
0x14000c373  cmp     ecx, 800B010Fh
0x14000c379  lea     edx, [rax-1Eh]
0x14000c37c  cmovnz  eax, edx
0x14000c37f  retn
0x14000c381  mov     eax, 80092010h
0x14000c386  retn
0x14000c388  mov     eax, 80090325h
0x14000c38d  retn
0x14000c38f  mov     eax, 80090328h
0x14000c394  retn
```
