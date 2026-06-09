# EtwpValidateFilterDescriptors(uchar,ulong,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x180009488`
- end: `0x1800097d8`
- name: `?EtwpValidateFilterDescriptors@@YAKEKKPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `848`
- prototype: `unsigned int __fastcall(unsigned __int8, unsigned int, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800098ec`
- `0x18000ad70`

## callees

- `0x180009488`

## pseudocode

```c
__int64 __fastcall EtwpValidateFilterDescriptors(char a1, int a2, unsigned int a3, struct _EVENT_FILTER_DESCRIPTOR *a4)
{
  unsigned int v7; // edx
  int v8; // r8d
  int v9; // ebp
  int v10; // esi
  ULONGLONG Ptr; // r10
  unsigned __int64 Size; // r9
  ULONG Type; // ecx
  int v14; // r10d
  bool v15; // zf
  bool v16; // cc
  __int64 v18; // r10
  __int64 v19; // r10

  if ( !a4 || a3 > 0xD || !a2 && !a1 )
    return 87;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !a3 )
    return v7;
  while ( 1 )
  {
    Ptr = a4[v10].Ptr;
    if ( !Ptr )
      return 87;
    Size = a4[v10].Size;
    if ( !(_DWORD)Size )
      return 87;
    Type = a4[v10].Type;
    if ( Type > 0x80000100 )
    {
      switch ( Type )
      {
        case 0x80000200:
          if ( (v8 & 0x80000200) == 0x80000200 )
            return 87;
          if ( a1 )
            return 87;
          if ( (unsigned int)(Size - 6) > 0x3FA )
            return 87;
          v19 = *(unsigned __int16 *)(Ptr + 2);
          if ( Size != 2 * v19 + 4 || (unsigned __int16)(v19 - 1) > 0x3Fu )
            return 87;
          v8 |= 0x80000200;
          break;
        case 0x80000400:
          if ( (v8 & 0x80000400) == 0x80000400
            || a1
            || (unsigned int)(Size - 25) > 0xFE7
            || !*(_WORD *)(Ptr + 18)
            || Size < 2 * (unsigned __int64)*(unsigned __int16 *)(Ptr + 18) + 20 )
          {
            return 87;
          }
          v8 |= 0x80000400;
          break;
        case 0x80001000:
          if ( (v8 & 0x80001000) == 0x80001000 )
            return 87;
          if ( a1 )
            return 87;
          if ( (unsigned int)(Size - 6) > 0x3FA )
            return 87;
          v18 = *(unsigned __int16 *)(Ptr + 2);
          if ( Size != 2 * v18 + 4 || (unsigned __int16)(v18 - 1) > 0x3Fu )
            return 87;
          v8 |= 0x80001000;
          break;
        case 0x80002000:
          if ( (v8 & 0x80002000) == 0x80002000
            || a1
            || (unsigned int)(Size - 25) > 0xFE7
            || !*(_WORD *)(Ptr + 18)
            || Size < 2 * (unsigned __int64)*(unsigned __int16 *)(Ptr + 18) + 20 )
          {
            return 87;
          }
          v8 |= 0x80002000;
          break;
        default:
          v14 = -2147467264;
          if ( Type == -2147467264 )
          {
            if ( (v8 & 0x80004000) == 0x80004000 || a1 || (_DWORD)Size != 24 )
              return 87;
            goto LABEL_24;
          }
          v14 = -2147450880;
          if ( Type == -2147450880 )
          {
            if ( (v8 & 0x80008000) == 0x80008000 || a1 )
              return 87;
LABEL_22:
            v16 = (unsigned int)Size <= 0x400;
LABEL_23:
            if ( !v16 )
              return 87;
LABEL_24:
            v8 |= v14;
            break;
          }
LABEL_37:
          if ( v9 || (unsigned int)Size > 0x400 )
            return 87;
          v9 = 1;
          break;
      }
    }
    else
    {
      if ( Type != -2147483392 )
      {
        if ( Type + 0x7FFFFFFF <= 1 )
          goto LABEL_72;
        v14 = -2147483644;
        if ( Type == -2147483644 )
        {
          if ( (v8 & 0x80000004) == 0x80000004 )
            return 87;
          v16 = ((unsigned int)Size >> 2) - 1 <= 7;
          goto LABEL_23;
        }
        v14 = -2147483640;
        switch ( Type )
        {
          case 0x80000008:
            if ( (v8 & 0x80000008) == 0x80000008 )
              return 87;
            goto LABEL_22;
          case 0x80000010:
            v15 = (v8 & 0x80000010) == -2147483632;
LABEL_16:
            if ( v15 || a1 || (unsigned int)Size > 0x400 )
              return 87;
            v8 |= 0x80000010;
            goto LABEL_72;
          case 0x80000020:
            v15 = (v8 & 0x80000020) == -2147483616;
            goto LABEL_16;
        }
        goto LABEL_37;
      }
      if ( (v8 & 0x80000100) == 0x80000100 || a1 || (unsigned int)Size > 0x1000 )
        return 87;
      v8 |= 0x80000100;
    }
LABEL_72:
    if ( ++v10 >= a3 )
      return v7;
  }
}

```

## disassembly

```asm
0x180009488  push    rbx
0x18000948a  push    rbp
0x18000948b  push    rsi
0x18000948c  push    rdi
0x18000948d  push    r12
0x18000948f  push    r13
0x180009491  push    r14
0x180009493  push    r15
0x180009495  xor     r14d, r14d
0x180009498  mov     rdi, r9
0x18000949b  mov     ebx, r8d
0x18000949e  mov     r11b, cl
0x1800094a1  test    r9, r9
0x1800094a4  jz      loc_1800097C6
0x1800094aa  cmp     ebx, 0Dh
0x1800094ad  ja      loc_1800097C6
0x1800094b3  test    edx, edx
0x1800094b5  jnz     short loc_1800094BF
0x1800094b7  test    cl, cl
0x1800094b9  jz      loc_1800097C6
0x1800094bf  mov     edx, r14d
0x1800094c2  mov     r8d, r14d
0x1800094c5  mov     ebp, r14d
0x1800094c8  mov     esi, r14d
0x1800094cb  test    ebx, ebx
0x1800094cd  jz      loc_180009654
0x1800094d3  mov     r15d, 1
0x1800094d9  mov     r13d, 80000010h
0x1800094df  mov     r12d, 400h
0x1800094e5  mov     ecx, esi
0x1800094e7  add     rcx, rcx
0x1800094ea  mov     r10, [rdi+rcx*8]
0x1800094ee  test    r10, r10
0x1800094f1  jz      loc_18000964F
0x1800094f7  mov     r9d, [rdi+rcx*8+8]
0x1800094fc  test    r9d, r9d
0x1800094ff  jz      loc_18000964F
0x180009505  mov     ecx, [rdi+rcx*8+0Ch]
0x180009509  cmp     ecx, 80000100h
0x18000950f  ja      loc_1800095E8
0x180009515  jz      loc_1800095C4
0x18000951b  lea     eax, [rcx+7FFFFFFFh]
0x180009521  cmp     eax, r15d
0x180009524  jbe     loc_1800097B6
0x18000952a  mov     r10d, 80000004h
0x180009530  cmp     ecx, r10d
0x180009533  jz      short loc_1800095A8
0x180009535  mov     r10d, 80000008h
0x18000953b  cmp     ecx, r10d
0x18000953e  jz      short loc_180009588
0x180009540  cmp     ecx, r13d
0x180009543  jz      short loc_18000957D
0x180009545  mov     r10d, 80000020h
0x18000954b  cmp     ecx, r10d
0x18000954e  jnz     loc_18000962A
0x180009554  mov     eax, r8d
0x180009557  and     eax, r10d
0x18000955a  cmp     eax, r10d
0x18000955d  jz      loc_18000964F
0x180009563  test    r11b, r11b
0x180009566  jnz     loc_18000964F
0x18000956c  cmp     r9d, r12d
0x18000956f  ja      loc_18000964F
0x180009575  or      r8d, r13d
0x180009578  jmp     loc_1800097B6
0x18000957d  mov     eax, r8d
0x180009580  and     eax, r13d
0x180009583  cmp     eax, r13d
0x180009586  jmp     short loc_18000955D
0x180009588  mov     eax, r8d
0x18000958b  and     eax, r10d
0x18000958e  cmp     eax, r10d
0x180009591  jz      loc_18000964F
0x180009597  cmp     r9d, r12d
0x18000959a  ja      loc_18000964F
0x1800095a0  or      r8d, r10d
0x1800095a3  jmp     loc_1800097B6
0x1800095a8  mov     eax, r8d
0x1800095ab  and     eax, r10d
0x1800095ae  cmp     eax, r10d
0x1800095b1  jz      loc_18000964F
0x1800095b7  shr     r9d, 2
0x1800095bb  sub     r9d, r15d
0x1800095be  cmp     r9d, 7
0x1800095c2  jmp     short loc_18000959A
0x1800095c4  mov     ecx, 80000100h
0x1800095c9  mov     eax, r8d
0x1800095cc  and     eax, ecx
0x1800095ce  cmp     eax, ecx
0x1800095d0  jz      short loc_18000964F
0x1800095d2  test    r11b, r11b
0x1800095d5  jnz     short loc_18000964F
0x1800095d7  cmp     r9d, 1000h
0x1800095de  ja      short loc_18000964F
0x1800095e0  or      r8d, ecx
0x1800095e3  jmp     loc_1800097B6
0x1800095e8  cmp     ecx, 80000200h
0x1800095ee  jz      loc_180009760
0x1800095f4  cmp     ecx, 80000400h
0x1800095fa  jz      loc_18000970C
0x180009600  cmp     ecx, 80001000h
0x180009606  jz      loc_1800096B9
0x18000960c  cmp     ecx, 80002000h
0x180009612  jz      short loc_180009676
0x180009614  mov     r10d, 80004000h
0x18000961a  cmp     ecx, r10d
0x18000961d  jz      short loc_18000965B
0x18000961f  mov     r10d, 80008000h
0x180009625  cmp     ecx, r10d
0x180009628  jz      short loc_18000963B
0x18000962a  test    ebp, ebp
0x18000962c  jnz     short loc_18000964F
0x18000962e  cmp     r9d, r12d
0x180009631  ja      short loc_18000964F
0x180009633  mov     ebp, r15d
0x180009636  jmp     loc_1800097B6
0x18000963b  mov     eax, r8d
0x18000963e  and     eax, r10d
0x180009641  cmp     eax, r10d
0x180009644  jz      short loc_18000964F
0x180009646  test    r11b, r11b
0x180009649  jz      loc_180009597
0x18000964f  mov     edx, 57h ; 'W'
0x180009654  mov     eax, edx
0x180009656  jmp     loc_1800097CB
0x18000965b  mov     eax, r8d
0x18000965e  and     eax, r10d
0x180009661  cmp     eax, r10d
0x180009664  jz      short loc_18000964F
0x180009666  test    r11b, r11b
0x180009669  jnz     short loc_18000964F
0x18000966b  cmp     r9d, 18h
0x18000966f  jnz     short loc_18000964F
0x180009671  jmp     loc_1800095A0
0x180009676  mov     ecx, 80002000h
0x18000967b  mov     eax, r8d
0x18000967e  and     eax, ecx
0x180009680  cmp     eax, ecx
0x180009682  jz      short loc_18000964F
0x180009684  test    r11b, r11b
0x180009687  jnz     short loc_18000964F
0x180009689  lea     eax, [r9-19h]
0x18000968d  cmp     eax, 0FE7h
0x180009692  ja      short loc_18000964F
0x180009694  cmp     [r10+12h], r14w
0x180009699  jz      short loc_18000964F
0x18000969b  movzx   eax, word ptr [r10+12h]
0x1800096a0  lea     rcx, ds:14h[rax*2]
0x1800096a8  cmp     r9, rcx
0x1800096ab  jb      short loc_18000964F
0x1800096ad  or      r8d, 80002000h
0x1800096b4  jmp     loc_1800097B6
0x1800096b9  mov     ecx, 80001000h
0x1800096be  mov     eax, r8d
0x1800096c1  and     eax, ecx
0x1800096c3  cmp     eax, ecx
0x1800096c5  jz      short loc_18000964F
0x1800096c7  test    r11b, r11b
0x1800096ca  jnz     short loc_18000964F
0x1800096cc  lea     eax, [r9-6]
0x1800096d0  cmp     eax, 3FAh
0x1800096d5  ja      loc_18000964F
0x1800096db  movzx   r10d, word ptr [r10+2]
0x1800096e0  lea     rcx, ds:4[r10*2]
0x1800096e8  cmp     r9, rcx
0x1800096eb  jnz     loc_18000964F
0x1800096f1  sub     r10w, r15w
0x1800096f5  cmp     r10w, 3Fh ; '?'
0x1800096fa  ja      loc_18000964F
0x180009700  or      r8d, 80001000h
0x180009707  jmp     loc_1800097B6
0x18000970c  mov     ecx, 80000400h
0x180009711  mov     eax, r8d
0x180009714  and     eax, ecx
0x180009716  cmp     eax, ecx
0x180009718  jz      loc_18000964F
0x18000971e  test    r11b, r11b
0x180009721  jnz     loc_18000964F
0x180009727  lea     eax, [r9-19h]
0x18000972b  cmp     eax, 0FE7h
0x180009730  ja      loc_18000964F
0x180009736  cmp     [r10+12h], r14w
0x18000973b  jz      loc_18000964F
0x180009741  movzx   eax, word ptr [r10+12h]
0x180009746  lea     rcx, ds:14h[rax*2]
0x18000974e  cmp     r9, rcx
0x180009751  jb      loc_18000964F
0x180009757  or      r8d, 80000400h
0x18000975e  jmp     short loc_1800097B6
0x180009760  mov     ecx, 80000200h
0x180009765  mov     eax, r8d
0x180009768  and     eax, ecx
0x18000976a  cmp     eax, ecx
0x18000976c  jz      loc_18000964F
0x180009772  test    r11b, r11b
0x180009775  jnz     loc_18000964F
0x18000977b  lea     eax, [r9-6]
0x18000977f  cmp     eax, 3FAh
0x180009784  ja      loc_18000964F
0x18000978a  movzx   r10d, word ptr [r10+2]
0x18000978f  lea     rcx, ds:4[r10*2]
0x180009797  cmp     r9, rcx
0x18000979a  jnz     loc_18000964F
0x1800097a0  sub     r10w, r15w
0x1800097a4  cmp     r10w, 3Fh ; '?'
0x1800097a9  ja      loc_18000964F
0x1800097af  or      r8d, 80000200h
0x1800097b6  add     esi, r15d
0x1800097b9  cmp     esi, ebx
0x1800097bb  jb      loc_1800094E5
0x1800097c1  jmp     loc_180009654
0x1800097c6  mov     eax, 57h ; 'W'
0x1800097cb  pop     r15
0x1800097cd  pop     r14
0x1800097cf  pop     r13
0x1800097d1  pop     r12
0x1800097d3  pop     rdi
0x1800097d4  pop     rsi
0x1800097d5  pop     rbp
0x1800097d6  pop     rbx
0x1800097d7  retn
```
