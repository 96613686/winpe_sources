# CXMLTag::ByteValueFromWChar(wchar_t)

- ea: `0x18002192c`
- end: `0x1800219bd`
- name: `?ByteValueFromWChar@CXMLTag@@AEAAE_W@Z`
- size: `145`
- prototype: `unsigned __int8 __fastcall(CXMLTag *this, unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c5f0`

## callees

- `0x18002192c`

## pseudocode

```c
unsigned __int8 __fastcall CXMLTag::ByteValueFromWChar(CXMLTag *this, unsigned __int16 a2)
{
  bool v3; // zf
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx

  if ( a2 > 0x61u )
  {
    v4 = a2 - 98;
    v3 = a2 == 98;
  }
  else
  {
    if ( a2 == 97 )
      return 10;
    if ( a2 <= 0x38u )
    {
      if ( a2 != 56 )
      {
        if ( a2 != 48 )
        {
          switch ( a2 )
          {
            case '1':
              return 1;
            case '2':
              return 2;
            case '3':
              return 3;
            case '4':
              return 4;
            case '5':
              return 5;
            case '6':
              return 6;
            case '7':
              return 7;
          }
        }
        return 0;
      }
      return 8;
    }
    if ( a2 == 57 )
      return 9;
    if ( a2 == 65 )
      return 10;
    v4 = a2 - 66;
    v3 = a2 == 66;
  }
  if ( v3 )
    return 11;
  v5 = v4 - 1;
  if ( !v5 )
    return 12;
  v6 = v5 - 1;
  if ( !v6 )
    return 13;
  v7 = v6 - 1;
  if ( !v7 )
    return 14;
  if ( v7 != 1 )
    return 0;
  return 15;
}

```

## disassembly

```asm
0x18002192c  movzx   ecx, dx
0x18002192f  cmp     ecx, 61h ; 'a'
0x180021932  ja      short loc_180021995
0x180021934  jz      short loc_180021992
0x180021936  cmp     ecx, 38h ; '8'
0x180021939  ja      short loc_180021980
0x18002193b  jz      short loc_18002197D
0x18002193d  sub     ecx, 30h ; '0'
0x180021940  jz      short loc_18002197A
0x180021942  sub     ecx, 1
0x180021945  jz      short loc_180021977
0x180021947  sub     ecx, 1
0x18002194a  jz      short loc_180021974
0x18002194c  sub     ecx, 1
0x18002194f  jz      short loc_180021971
0x180021951  sub     ecx, 1
0x180021954  jz      short loc_18002196E
0x180021956  sub     ecx, 1
0x180021959  jz      short loc_18002196B
0x18002195b  sub     ecx, 1
0x18002195e  jz      short loc_180021968
0x180021960  cmp     ecx, 1
0x180021963  jnz     short loc_18002197A
0x180021965  mov     al, 7
0x180021967  retn
0x180021968  mov     al, 6
0x18002196a  retn
0x18002196b  mov     al, 5
0x18002196d  retn
0x18002196e  mov     al, 4
0x180021970  retn
0x180021971  mov     al, 3
0x180021973  retn
0x180021974  mov     al, 2
0x180021976  retn
0x180021977  mov     al, 1
0x180021979  retn
0x18002197a  xor     al, al
0x18002197c  retn
0x18002197d  mov     al, 8
0x18002197f  retn
0x180021980  sub     ecx, 39h ; '9'
0x180021983  jz      short loc_18002198F
0x180021985  sub     ecx, 8
0x180021988  jz      short loc_180021992
0x18002198a  sub     ecx, 1
0x18002198d  jmp     short loc_180021998
0x18002198f  mov     al, 9
0x180021991  retn
0x180021992  mov     al, 0Ah
0x180021994  retn
0x180021995  sub     ecx, 62h ; 'b'
0x180021998  jz      short loc_1800219BA
0x18002199a  sub     ecx, 1
0x18002199d  jz      short loc_1800219B7
0x18002199f  sub     ecx, 1
0x1800219a2  jz      short loc_1800219B4
0x1800219a4  sub     ecx, 1
0x1800219a7  jz      short loc_1800219B1
0x1800219a9  cmp     ecx, 1
0x1800219ac  jnz     short loc_18002197A
0x1800219ae  mov     al, 0Fh
0x1800219b0  retn
0x1800219b1  mov     al, 0Eh
0x1800219b3  retn
0x1800219b4  mov     al, 0Dh
0x1800219b6  retn
0x1800219b7  mov     al, 0Ch
0x1800219b9  retn
0x1800219ba  mov     al, 0Bh
0x1800219bc  retn
```
