# GetLangIdFromSzLang(ushort const *)

- ea: `0x1800102c0`
- end: `0x18001031f`
- name: `?GetLangIdFromSzLang@@YAKPEBG@Z`
- size: `95`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b40`
- `0x1800093a8`
- `0x180010430`
- `0x180010f28`
- `0x180011180`
- `0x1800113b0`

## callees

- `0x1800102c0`

## pseudocode

```c
__int64 __fastcall GetLangIdFromSzLang(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  __int64 v3; // r9
  unsigned int i; // r8d
  int v5; // edx
  int v6; // ecx
  int v7; // edx

  v2 = 0;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  for ( i = 0; i < (unsigned int)v3; ++i )
  {
    v5 = 16 * v2;
    v6 = a1[i];
    if ( (unsigned __int16)(v6 - 48) > 9u )
    {
      if ( (unsigned __int16)(v6 - 97) > 5u )
      {
        if ( (unsigned __int16)(v6 - 65) > 5u )
          return 0;
        v7 = v5 - 55;
      }
      else
      {
        v7 = v5 - 87;
      }
    }
    else
    {
      v7 = v5 - 48;
    }
    v2 = v6 + v7;
  }
  return v2;
}

```

## disassembly

```asm
0x1800102c0  xor     r11d, r11d
0x1800102c3  mov     r10, rcx
0x1800102c6  mov     edx, r11d
0x1800102c9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800102cd  inc     r9
0x1800102d0  cmp     [rcx+r9*2], r11w
0x1800102d5  jnz     short loc_1800102CD
0x1800102d7  mov     r8d, r11d
0x1800102da  cmp     r8d, r9d
0x1800102dd  jnb     short loc_18001031C
0x1800102df  mov     eax, r8d
0x1800102e2  shl     edx, 4
0x1800102e5  movzx   ecx, word ptr [r10+rax*2]
0x1800102ea  lea     eax, [rcx-30h]
0x1800102ed  cmp     ax, 9
0x1800102f1  ja      short loc_1800102F8
0x1800102f3  add     edx, 0FFFFFFD0h
0x1800102f6  jmp     short loc_180010312
0x1800102f8  lea     eax, [rcx-61h]
0x1800102fb  cmp     ax, 5
0x1800102ff  ja      short loc_180010306
0x180010301  add     edx, 0FFFFFFA9h
0x180010304  jmp     short loc_180010312
0x180010306  lea     eax, [rcx-41h]
0x180010309  cmp     ax, 5
0x18001030d  ja      short loc_180010319
0x18001030f  add     edx, 0FFFFFFC9h
0x180010312  add     edx, ecx
0x180010314  inc     r8d
0x180010317  jmp     short loc_1800102DA
0x180010319  mov     edx, r11d
0x18001031c  mov     eax, edx
0x18001031e  retn
```
