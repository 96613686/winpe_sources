# NormalizeNteStatus

- ea: `0x1800048f0`
- end: `0x180004a80`
- name: `NormalizeNteStatus`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `64`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180001e10`
- `0x180002270`
- `0x180002800`
- `0x180002dc0`
- `0x180003020`
- `0x180003120`
- `0x180003270`
- `0x180003360`
- `0x1800035c0`
- `0x180003880`
- `0x180003d40`
- `0x180003f60`
- `0x1800041b0`
- `0x180004550`
- `0x180005540`
- `0x1800057a0`
- `0x180005bb0`
- `0x180005d00`
- `0x1800064b0`
- `0x180006bc0`
- `0x180006d60`
- `0x180006ed0`
- `0x180007240`
- `0x1800076b0`
- `0x180007860`
- `0x1800079a0`
- `0x180007b30`
- `0x180007dd0`
- `0x180007f40`
- `0x180008f50`
- `0x180009090`
- `0x180009190`
- `0x180009270`
- `0x180009310`
- `0x180009410`
- `0x180009570`
- `0x180009ca0`
- `0x180009f20`
- `0x18000a13c`
- `0x18000a520`
- `0x18000df70`
- `0x18000e120`
- `0x18000e2c0`
- `0x18000e3f0`
- `0x18000e560`
- `0x18000e6a0`
- `0x18000ec30`
- `0x18000ef60`
- `0x18000f140`
- `0x18000f250`

## callees

- `0x1800048f0`

## pseudocode

```c
__int64 __fastcall NormalizeNteStatus(unsigned int a1)
{
  __int64 result; // rax

  if ( (a1 & 0x1FFF0000) == 0x90000 || (a1 & 0x1FFF0000) == 0x100000 )
    return a1;
  if ( a1 == 3 )
    return (unsigned int)-2146893807;
  if ( a1 > 0x216 )
  {
    if ( a1 > 0xC000007B )
    {
      if ( a1 <= 0xC0000135 )
      {
        if ( a1 == -1073741515 )
          return (unsigned int)-2146893794;
        if ( a1 != -1073741670 )
        {
          if ( a1 == -1073741637 )
            return (unsigned int)-2146893783;
          if ( a1 != -1073741595 )
            return a1;
          return (unsigned int)-2146893779;
        }
        return (unsigned int)-2146893810;
      }
      if ( a1 != -1073741511 && a1 != -1073741502 )
      {
        if ( a1 == -1073700864 )
          return (unsigned int)-2146893818;
        return a1;
      }
    }
    else if ( a1 != -1073741701 )
    {
      if ( a1 <= 0xC0000008 )
      {
        if ( a1 == -1073741816 )
          return (unsigned int)-2146893786;
        if ( a1 != 1359 )
        {
          switch ( a1 )
          {
            case 0x800704C0:
              return (unsigned int)-2147023680;
            case 0x800704C7:
              return (unsigned int)-2147023673;
            case 0x80070578:
              return (unsigned int)-2147023496;
          }
          return a1;
        }
        return (unsigned int)-2146893779;
      }
      if ( a1 == -1073741811 )
        return (unsigned int)-2146893785;
      if ( a1 != -1073741801 )
      {
        if ( a1 == -1073741789 )
          return (unsigned int)-2146893784;
        return a1;
      }
      return (unsigned int)-2146893810;
    }
    return (unsigned int)-2146893795;
  }
  if ( a1 == 534 )
    return (unsigned int)-2147024362;
  switch ( a1 )
  {
    case 0u:
      result = 0;
      break;
    case 2u:
      return (unsigned int)-2146893807;
    case 5u:
      return (unsigned int)-2146893808;
    case 8u:
    case 0xEu:
      return (unsigned int)-2146893810;
    case 0x57u:
      return (unsigned int)-2146893785;
    case 0x70u:
      return (unsigned int)-2147024784;
    case 0x7Au:
      return (unsigned int)-2146893784;
    case 0xB7u:
      return (unsigned int)-2146893809;
    default:
      return a1;
  }
  return result;
}

```

## disassembly

```asm
0x1800048f0  mov     eax, ecx
0x1800048f2  and     eax, 1FFF0000h
0x1800048f7  cmp     eax, 90000h
0x1800048fc  jnz     short loc_180004901
0x1800048fe  mov     eax, ecx; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004900  retn
0x180004901  cmp     eax, 100000h
0x180004906  jz      short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004908  cmp     ecx, 3
0x18000490b  jnz     short loc_180004914
0x18000490d  mov     ecx, 80090011h; jumptable 0000000180004943 case 2
0x180004912  jmp     short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004914  cmp     ecx, 216h
0x18000491a  ja      short loc_180004966
0x18000491c  jz      short loc_18000495F
0x18000491e  cmp     ecx, 0B7h; switch 184 cases
0x180004924  ja      short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004926  lea     r8, cs:180000000h
0x18000492d  mov     eax, ecx
0x18000492f  movzx   eax, ds:(byte_180004AA4 - 180000000h)[r8+rax]
0x180004938  mov     edx, ds:(jpt_180004943 - 180000000h)[r8+rax*4]
0x180004940  add     rdx, r8
0x180004943  jmp     rdx; switch jump
0x180004945  xor     ecx, ecx; jumptable 0000000180004943 case 0
0x180004947  mov     eax, ecx
0x180004949  retn
0x18000494a  mov     ecx, 80090010h; jumptable 0000000180004943 case 5
0x18000494f  jmp     short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004951  mov     ecx, 80070070h; jumptable 0000000180004943 case 112
0x180004956  jmp     short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004958  mov     ecx, 8009000Fh; jumptable 0000000180004943 case 183
0x18000495d  jmp     short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000495f  mov     ecx, 80070216h
0x180004964  jmp     short def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004966  cmp     ecx, 0C000007Bh
0x18000496c  ja      loc_180004A02
0x180004972  jz      loc_180004A76
0x180004978  cmp     ecx, 0C0000008h
0x18000497e  ja      short loc_1800049D2
0x180004980  jz      short loc_1800049C8
0x180004982  cmp     ecx, 54Fh
0x180004988  jz      loc_180004A28
0x18000498e  cmp     ecx, 800704C0h
0x180004994  jz      short loc_1800049BE
0x180004996  cmp     ecx, 800704C7h
0x18000499c  jz      short loc_1800049B4
0x18000499e  cmp     ecx, 80070578h
0x1800049a4  jnz     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049aa  mov     ecx, 80070578h
0x1800049af  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049b4  mov     ecx, 800704C7h
0x1800049b9  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049be  mov     ecx, 800704C0h
0x1800049c3  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049c8  mov     ecx, 80090026h
0x1800049cd  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049d2  cmp     ecx, 0C000000Dh
0x1800049d8  jz      short loc_1800049F8; jumptable 0000000180004943 case 87
0x1800049da  cmp     ecx, 0C0000017h
0x1800049e0  jz      short loc_180004A3C; jumptable 0000000180004943 cases 8,14
0x1800049e2  cmp     ecx, 0C0000023h
0x1800049e8  jnz     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049ee  mov     ecx, 80090028h; jumptable 0000000180004943 case 122
0x1800049f3  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x1800049f8  mov     ecx, 80090027h; jumptable 0000000180004943 case 87
0x1800049fd  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a02  cmp     ecx, 0C0000135h
0x180004a08  ja      short loc_180004A50
0x180004a0a  jz      short loc_180004A46
0x180004a0c  cmp     ecx, 0C000009Ah
0x180004a12  jz      short loc_180004A3C; jumptable 0000000180004943 cases 8,14
0x180004a14  cmp     ecx, 0C00000BBh
0x180004a1a  jz      short loc_180004A32
0x180004a1c  cmp     ecx, 0C00000E5h
0x180004a22  jnz     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a28  mov     ecx, 8009002Dh
0x180004a2d  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a32  mov     ecx, 80090029h
0x180004a37  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a3c  mov     ecx, 8009000Eh; jumptable 0000000180004943 cases 8,14
0x180004a41  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a46  mov     ecx, 8009001Eh
0x180004a4b  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a50  cmp     ecx, 0C0000139h
0x180004a56  jz      short loc_180004A76
0x180004a58  cmp     ecx, 0C0000142h
0x180004a5e  jz      short loc_180004A76
0x180004a60  cmp     ecx, 0C000A000h
0x180004a66  jnz     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a6c  mov     ecx, 80090006h
0x180004a71  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
0x180004a76  mov     ecx, 8009001Dh
0x180004a7b  jmp     def_180004943; jumptable 0000000180004943 default case, cases 1,3,4,6,7,9-13,15-86,88-111,113-121,123-182
```
