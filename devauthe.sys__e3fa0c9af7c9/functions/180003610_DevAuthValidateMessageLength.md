# _DevAuthValidateMessageLength

- ea: `0x180003610`
- end: `0x180003696`
- name: `_DevAuthValidateMessageLength`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035bc`
- `0x18000490c`

## callees

- `0x180003610`

## pseudocode

```c
__int64 __fastcall DevAuthValidateMessageLength(unsigned __int8 a1, int a2)
{
  unsigned int v2; // ecx
  bool v3; // zf

  if ( a1 > 6u )
  {
    if ( a1 == 7 )
    {
      v2 = 0;
      v3 = a2 == 36;
      goto LABEL_19;
    }
    if ( a1 == 8 )
    {
      v2 = 0;
      v3 = a2 == 68;
      goto LABEL_19;
    }
    if ( (unsigned int)a1 - 11 < 2 )
    {
      v2 = 0;
      v3 = a2 == 4;
      goto LABEL_19;
    }
    return 0;
  }
  switch ( a1 )
  {
    case 6u:
LABEL_8:
      v2 = 0;
      v3 = a2 == 260;
LABEL_19:
      LOBYTE(v2) = v3;
      return v2;
    case 1u:
      v2 = 0;
      v3 = a2 == 44;
      goto LABEL_19;
    case 2u:
      v2 = 0;
      v3 = a2 == 84;
      goto LABEL_19;
  }
  if ( a1 != 3 && a1 != 4 )
  {
    if ( a1 == 5 )
      goto LABEL_8;
    return 0;
  }
  return (unsigned int)(a2 - 5) <= 0x3FE;
}

```

## disassembly

```asm
0x180003610  movzx   r8d, cl
0x180003614  cmp     r8d, 6
0x180003618  ja      short loc_180003661
0x18000361a  jz      short loc_18000363A
0x18000361c  sub     r8d, 1
0x180003620  jz      short loc_18000365A
0x180003622  sub     r8d, 1
0x180003626  jz      short loc_180003653
0x180003628  sub     r8d, 1
0x18000362c  jz      short loc_180003644
0x18000362e  sub     r8d, 1
0x180003632  jz      short loc_180003644
0x180003634  cmp     r8d, 1
0x180003638  jnz     short loc_180003679
0x18000363a  xor     ecx, ecx
0x18000363c  cmp     edx, 104h
0x180003642  jmp     short loc_180003690
0x180003644  xor     ecx, ecx
0x180003646  lea     eax, [rdx-5]
0x180003649  cmp     eax, 3FEh
0x18000364e  setbe   cl
0x180003651  jmp     short loc_180003693
0x180003653  xor     ecx, ecx
0x180003655  cmp     edx, 54h ; 'T'
0x180003658  jmp     short loc_180003690
0x18000365a  xor     ecx, ecx
0x18000365c  cmp     edx, 2Ch ; ','
0x18000365f  jmp     short loc_180003690
0x180003661  sub     r8d, 7
0x180003665  jz      short loc_18000368B
0x180003667  sub     r8d, 1
0x18000366b  jz      short loc_180003684
0x18000366d  sub     r8d, 3
0x180003671  jz      short loc_18000367D
0x180003673  cmp     r8d, 1
0x180003677  jz      short loc_18000367D
0x180003679  xor     eax, eax
0x18000367b  retn
0x18000367d  xor     ecx, ecx
0x18000367f  cmp     edx, 4
0x180003682  jmp     short loc_180003690
0x180003684  xor     ecx, ecx
0x180003686  cmp     edx, 44h ; 'D'
0x180003689  jmp     short loc_180003690
0x18000368b  xor     ecx, ecx
0x18000368d  cmp     edx, 24h ; '$'
0x180003690  setz    cl
0x180003693  mov     eax, ecx
0x180003695  retn
```
