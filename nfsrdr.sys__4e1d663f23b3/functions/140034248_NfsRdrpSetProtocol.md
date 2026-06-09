# NfsRdrpSetProtocol

- ea: `0x140034248`
- end: `0x1400343b1`
- name: `NfsRdrpSetProtocol`
- size: `361`
- prototype: `char __fastcall(_BYTE *, _DWORD *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000adb0`

## callees

- `0x140034248`

## pseudocode

```c
char __fastcall NfsRdrpSetProtocol(_BYTE *a1, _DWORD *a2, int a3)
{
  char v3; // r9
  bool v4; // zf
  bool v5; // zf
  int v6; // eax

  v3 = 1;
  switch ( *a2 )
  {
    case 0x186A3:
      if ( !a3 )
      {
        if ( (a1[1416] & 0x10) != 0 )
          goto LABEL_32;
        v4 = (a1[1418] & 4) == 0;
        goto LABEL_31;
      }
      if ( a3 != 1 || a2[2] != 6 )
        return 0;
      if ( (a1[1416] & 0x20) != 0 )
        goto LABEL_39;
      v5 = (a1[1418] & 8) == 0;
LABEL_38:
      if ( v5 )
        return 0;
      goto LABEL_39;
    case 0x186A5:
      if ( !a3 )
      {
        if ( (a1[1416] & 4) != 0 )
          goto LABEL_32;
        v4 = (a1[1418] & 1) == 0;
        goto LABEL_31;
      }
      if ( a3 != 1 || a2[2] != 6 )
        return 0;
      if ( (a1[1416] & 8) != 0 )
        goto LABEL_39;
      v5 = (a1[1418] & 2) == 0;
      goto LABEL_38;
    case 0x186B5:
      if ( !a3 )
      {
        if ( (a1[1416] & 0x40) != 0 )
          goto LABEL_32;
        v4 = (a1[1418] & 0x10) == 0;
        goto LABEL_31;
      }
      if ( a3 != 1 || a2[2] != 6 )
        return 0;
      if ( (char)a1[1416] < 0 )
        goto LABEL_39;
      v5 = (a1[1418] & 0x20) == 0;
      goto LABEL_38;
    case 0x55CDF:
      if ( !a3 )
      {
        if ( (a1[1417] & 4) != 0 )
          goto LABEL_32;
        v4 = (a1[1419] & 1) == 0;
LABEL_31:
        v6 = 17;
        if ( v4 )
        {
LABEL_33:
          a2[2] = v6;
          return v3;
        }
LABEL_32:
        v6 = 6;
        goto LABEL_33;
      }
      if ( a3 != 1 || a2[2] != 6 )
        return 0;
      if ( (a1[1417] & 8) == 0 )
      {
        v5 = (a1[1419] & 2) == 0;
        goto LABEL_38;
      }
LABEL_39:
      a2[2] = 17;
      return v3;
  }
  if ( a3 )
    return 0;
  a2[2] = 6;
  return v3;
}

```

## disassembly

```asm
0x140034248  mov     r10d, [rdx]
0x14003424b  mov     r9d, 1
0x140034251  sub     r10d, 186A3h
0x140034258  jz      loc_14003435A
0x14003425e  sub     r10d, 2
0x140034262  jz      loc_140034322
0x140034268  sub     r10d, 10h
0x14003426c  jz      short loc_1400342DA
0x14003426e  cmp     r10d, 3D62Ah
0x140034275  jz      short loc_14003428C
0x140034277  test    r8d, r8d
0x14003427a  jnz     loc_1400343AA
0x140034280  mov     dword ptr [rdx+8], 6
0x140034287  jmp     loc_1400343AD
0x14003428c  test    r8d, r8d
0x14003428f  jnz     short loc_1400342AA
0x140034291  test    byte ptr [rcx+589h], 4
0x140034298  jnz     loc_140034376
0x14003429e  test    [rcx+58Bh], r9b
0x1400342a5  jmp     loc_14003436F
0x1400342aa  cmp     r8d, r9d
0x1400342ad  jnz     loc_1400343AA
0x1400342b3  mov     eax, 6
0x1400342b8  cmp     [rdx+8], eax
0x1400342bb  jnz     loc_1400343AA
0x1400342c1  test    byte ptr [rcx+589h], 8
0x1400342c8  jnz     loc_1400343A1
0x1400342ce  test    byte ptr [rcx+58Bh], 2
0x1400342d5  jmp     loc_14003439F
0x1400342da  test    r8d, r8d
0x1400342dd  jnz     short loc_1400342F5
0x1400342df  test    byte ptr [rcx+588h], 40h
0x1400342e6  jnz     loc_140034376
0x1400342ec  test    byte ptr [rcx+58Ah], 10h
0x1400342f3  jmp     short loc_14003436F
0x1400342f5  cmp     r8d, r9d
0x1400342f8  jnz     loc_1400343AA
0x1400342fe  mov     eax, 6
0x140034303  cmp     [rdx+8], eax
0x140034306  jnz     loc_1400343AA
0x14003430c  cmp     byte ptr [rcx+588h], 0
0x140034313  jl      loc_1400343A1
0x140034319  test    byte ptr [rcx+58Ah], 20h
0x140034320  jmp     short loc_14003439F
0x140034322  test    r8d, r8d
0x140034325  jnz     short loc_140034339
0x140034327  test    byte ptr [rcx+588h], 4
0x14003432e  jnz     short loc_140034376
0x140034330  test    [rcx+58Ah], r9b
0x140034337  jmp     short loc_14003436F
0x140034339  cmp     r8d, r9d
0x14003433c  jnz     short loc_1400343AA
0x14003433e  mov     eax, 6
0x140034343  cmp     [rdx+8], eax
0x140034346  jnz     short loc_1400343AA
0x140034348  test    byte ptr [rcx+588h], 8
0x14003434f  jnz     short loc_1400343A1
0x140034351  test    byte ptr [rcx+58Ah], 2
0x140034358  jmp     short loc_14003439F
0x14003435a  test    r8d, r8d
0x14003435d  jnz     short loc_140034380
0x14003435f  test    byte ptr [rcx+588h], 10h
0x140034366  jnz     short loc_140034376
0x140034368  test    byte ptr [rcx+58Ah], 4
0x14003436f  mov     eax, 11h
0x140034374  jz      short loc_14003437B
0x140034376  mov     eax, 6
0x14003437b  mov     [rdx+8], eax
0x14003437e  jmp     short loc_1400343AD
0x140034380  cmp     r8d, r9d
0x140034383  jnz     short loc_1400343AA
0x140034385  mov     eax, 6
0x14003438a  cmp     [rdx+8], eax
0x14003438d  jnz     short loc_1400343AA
0x14003438f  test    byte ptr [rcx+588h], 20h
0x140034396  jnz     short loc_1400343A1
0x140034398  test    byte ptr [rcx+58Ah], 8
0x14003439f  jz      short loc_1400343AA
0x1400343a1  mov     dword ptr [rdx+8], 11h
0x1400343a8  jmp     short loc_1400343AD
0x1400343aa  xor     r9b, r9b
0x1400343ad  mov     al, r9b
0x1400343b0  retn
```
